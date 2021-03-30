---
title: 由世紀運作之 Office 365 的 Azure 資訊保護支援
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 深入瞭解 Office 365 運作的 Azure 資訊保護 (AIP) ，以及如何為中國的客戶設定該功能。
monikerRange: o365-21vianet
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418029"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>由世紀運作之 Office 365 的 Azure 資訊保護支援

本文說明 Azure 資訊保護 (AIP) 支援的 Office 365 （適用于中國）及商業方案，以及在中國為客戶設定 AIP 的特定指示， &mdash; 包括如何安裝 AIP 內部部署掃描器及管理內容掃描工作。

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>由世紀和商務服務運作的 Office 365 AIP 之間的差異

雖然我們的目標是將所有商業的功能和功能提供給中國的客戶 AIP，以供由世紀所運作的 Office 365 使用，但仍有一些遺漏的功能想要反白。

下列清單包含 AIP （由世紀運作之 Office 365）與我們從年 1 2021 月的商務版產品所組成的現有缺口：

- 只有 Microsoft 365 Apps for enterprise (組建11731.10000 或更新) 版本，才能支援資訊版權管理 (IRM) 。 Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。

- 從 Active Directory Rights Management Services (AD RMS) 至 AIP 的遷移目前無法使用。
  
- 支援與商業雲端中的使用者共用受保護的電子郵件。
  
- 目前無法使用商業雲端中的使用者共用檔和電子郵件附件。 這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。
  
- 具有 SharePoint (IRM 保護的網站與文件庫) 的 IRM 目前無法使用。
  
- 目前無法使用 AD RMS 的行動裝置分機。

- Azure 中國的世紀不支援行動 [檢視器](/azure/information-protection/rms-client/mobile-app-faq) 。

- 中國的客戶無法使用 Azure 入口網站的 AIP 區域。 使用 [PowerShell 命令](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) ，而不是在入口網站中執行動作，例如安裝內部部署掃描器及管理內容掃描工作。

## <a name="configure-aip-for-customers-in-china"></a>為中國的客戶設定 AIP

若要為中國的客戶設定 AIP：
1. [啟用租使用者的 Rights Management](#step-1-enable-rights-management-for-the-tenant)。

2. [設定 DNS 加密](#step-2-configure-dns-encryption)。

3. [安裝及設定 AIP 的整合標籤用戶端](#step-3-install-and-configure-the-aip-unified-labeling-client)。

4. [設定 Windows 上的 AIP 應用程式](#step-4-configure-aip-apps-on-windows)。

5. [安裝 AIP 內部部署掃描程式並管理內容掃描工作](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>步驟1：啟用租使用者的版權管理

為使加密正確運作，必須對租使用者啟用 RMS。

1. 檢查 RMS 是否已啟用：

    1. 以系統管理員身分啟動 PowerShell。
    2. 若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。
    3. 使用匯入模組 `Import-Module AipService` 。
    4. 使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。
    5. 執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。

2. 如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。

### <a name="step-2-configure-dns-encryption"></a>步驟2：設定 DNS 加密

若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。 若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。 若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。

此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。 Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。

#### <a name="configure-dns-encryption---windows"></a>設定 DNS 加密-Windows

1. 取得 RMS ID:

    1. 以系統管理員身分啟動 PowerShell。
    2. 若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。
    3. 使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。
    4. 執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。

2. 登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。

    - Service = `_rmsredir`
    - Protocol = `_http`
    - 名稱 = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) 
    - Priority，權數，Seconds，TTL = 預設值

3. 將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。 這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。

4. 使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn` 針對使用者建立) 。 在驗證程式中，可能需要進行其他 DNS 變更。 完成驗證之後，即可建立使用者。

#### <a name="configure-dns-encryption---mac-ios-android"></a>設定 DNS 加密-Mac、iOS、Android

登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。

- Service = `_rmsdisco`
- Protocol = `_http`
- 名稱 = `_tcp`
- Target = `api.aadrm.cn`
- 埠 = `80`
- Priority，權數，Seconds，TTL = 預設值

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>步驟3：安裝及設定 AIP 的整合標籤用戶端

從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載 AIP 整合標籤用戶端。

如需詳細資訊，請參閱：

- [AIP 檔](/azure/information-protection/)
- [AIP 版本歷程記錄與支援原則](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 系統需求](/azure/information-protection/requirements)
- [AIP 快速入門：部署 AIP 用戶端](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理員指南](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 使用者指南](/azure/information-protection/rms-client/clientv2-user-guide)
- [深入瞭解 Microsoft 365 敏感度標籤](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a>步驟4：設定 Windows 上的 AIP 應用程式

Windows 上的 AIP 應用程式需要下列登錄機碼，將其指向正確的 Azure 中國以及主權雲端：

- Registry 節點 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- 名稱 = `CloudEnvType`
- 值 = `6` (預設值 = 0) 
- Type = `REG_DWORD`

> [!IMPORTANT]
> 在卸載後，請確定您沒有刪除登錄機碼。 若機碼為空、不正確或不存在，則該功能將會以預設值 (預設值 = 0 （適用于商業性雲端) ）。 若機碼為空或不正確，則列印錯誤也會新增至記錄檔。

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>步驟5：安裝 AIP 內部部署掃描器及管理內容掃描工作

安裝 AIP 內部部署掃描器，以掃描您的網路和內容共用的機密資料，並套用組織原則中所設定的分類及保護標籤。

- 當您建立及設定 Azure AD 應用程式的 [AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 命令時，[ **要求 API 許可權** ] 窗格會顯示 [ **我的組織使用** ] 索引標籤，而非 [ **Microsoft APIs** ] 索引標籤的 APIs。選取 [ **我的組織所用的 APIs** ]，然後選取 [ **Azure Rights Management 服務**]。

- 安裝掃描程式並管理內容掃描工作時，請使用下列 Cmdlet，而不是商務用產品所用的 Azure 入口網站介面：<br><br>

    | 指令程式 | 描述 |
    |--|--|
    | [載入 AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 將新的存放庫加入至內容掃描工作。 |
    | [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 取得內容掃描工作的詳細資料。 |
    | [AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 取得針對內容掃描工作定義之存放庫的詳細資料。 |
    | [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 會刪除您的內容掃描工作。 |
    | [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 從內容掃描工作中移除存放庫。 |
    | [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 定義內容掃描工作的設定。 |
    | [AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 定義內容掃描工作中現有存放庫的設定。 |
    | | |

> [!TIP]
> [安裝掃描器](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)時，請在[AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner)命令中使用相同的叢集名稱，以將多個掃描器節點與相同的叢集產生關聯。 對多個掃描器節點使用相同的叢集，可讓多個掃描器一起運作，以執行掃描。
> 
> 使用 [AIPScannerConfiguration 指令程式](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) 可傳回有關您的叢集的詳細資料。
> 
如需詳細資訊，請參閱 [何謂 Azure 資訊保護統一的標記掃描器？](/azure/information-protection/deploy-aip-scanner) 和 [使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。