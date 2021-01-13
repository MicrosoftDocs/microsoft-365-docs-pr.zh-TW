---
title: 由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840298"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性

雖然我們的目標是將所有商業功能和功能提供給中國的客戶，但其 Azure 資訊保護 (AIP) 適用于由世紀所運作的 Office 365，但仍有一些遺漏的功能，我們想要反白。

下列清單包含在由世紀運作之 Office 365 之 Azure 資訊保護之間的現有缺口，以及從年 1 2021 月的商業產品方案：

- 只有 Microsoft 365 Apps for enterprise (組建11731.10000 或更新) 版本，才能支援資訊版權管理 (IRM) 。 Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。

- 從 Active Directory Rights Management Services 到 Azure 資訊保護的 Active Directory Rights Management Services (AD RMS) 目前無法使用。
  
- 支援將受保護的電子郵件共用至商業雲端中的使用者。
  
- 目前無法將檔和電子郵件附件共用給商業雲端中的使用者。 這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。
  
- 具有 SharePoint (IRM 保護的網站與文件庫) 的 IRM 目前無法使用。
  
- 目前無法使用 AD RMS 的行動裝置分機。

- Azure 中國的世紀不支援行動 [檢視器](/azure/information-protection/rms-client/mobile-app-faq) 。

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>為中國的客戶設定 Azure 資訊保護

### <a name="enable-rights-management-for-the-tenant"></a>啟用租使用者的版權管理

為使加密正確運作，RMS 必須啟用租使用者。

- 檢查 RMS 是否已啟用：
  1. 以系統管理員身分啟動 PowerShell。
  2. 若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。
  3. 使用匯入模組 `Import-Module AipService` 。
  4. 使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。
  5. 執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。

- 如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。

### <a name="dns-configuration-for-encryption-windows"></a> (Windows) 加密的 DNS 設定

若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。 若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。 若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。

此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。 Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。

- 取得 RMS ID:
  1. 以系統管理員身分啟動 PowerShell。
  2. 若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。
  3. 使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。
  4. 執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。

- 登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。
  - Service = `_rmsredir`
  - Protocol = `_http`
  - 名稱 = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) 
  - Priority，權數，Seconds，TTL = 預設值

- 將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。 這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。

- 使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn` 針對使用者建立) 。 在驗證程式中，可能需要進行其他 DNS 變更。 完成驗證之後，即可建立使用者。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>加密 (Mac、iOS、Android) 的 DNS 設定

登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。

- Service = `_rmsdisco`
- Protocol = `_http`
- 名稱 = `_tcp`
- Target = `api.aadrm.cn`
- 埠 = `80`
- Priority，權數，Seconds，TTL = 預設值

### <a name="aip-client-configuration"></a>AIP 用戶端設定

您可以從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載統一 AIP 用戶端。

如需詳細資訊，請參閱：

- [Azure 資訊保護檔](/azure/information-protection/)
- [AIP 版本歷程記錄與支援原則](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 系統需求](/azure/information-protection/requirements)
- [AIP 快速入門：部署 AIP 用戶端](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理員指南](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 使用者指南](/azure/information-protection/rms-client/clientv2-user-guide)
- [深入瞭解 Microsoft 365 敏感度標籤](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a>AIP apps configuration (僅限整合標籤用戶端) 

針對整合的標籤解決方案，Windows 上的 AIP 應用程式需要下列登錄機碼，將其指向適用于 Azure 中國的正確以及主權雲端：

- Registry 節點 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- 名稱 = `CloudEnvType`
- 值 = `6` (預設值 = 0) 
- Type = `REG_DWORD`

> [!IMPORTANT]
> 在卸載後，請確定您沒有刪除登錄機碼。 若機碼為空、不正確或不存在，則該功能將會以預設值 (預設值 = 0 （適用于商業性雲端) ）。 若機碼為空或不正確，則列印錯誤也會新增至記錄檔。

### <a name="manage-azure-information-protection-content-scan-jobs"></a>管理 Azure 資訊保護內容掃描工作

若要使用 Azure 中國掃描器伺服器管理 Azure 資訊保護內容掃描工作，請使用下列 Cmdlet，而不是 Azure 入口網站：<br><br>

| 指令程式 | 描述 |
|--|--|
| [載入 AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 將新的存放庫加入至內容掃描工作。 |
| [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 取得內容掃描工作的詳細資料。 |
| [AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 取得針對內容掃描工作定義之存放庫的詳細資料。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 會刪除您的內容掃描工作。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 從內容掃描工作中移除存放庫。 |
| [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 定義內容掃描工作的設定。 |
| [AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 定義內容掃描工作中現有存放庫的設定。 |

如需詳細資訊，請參閱 [使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。