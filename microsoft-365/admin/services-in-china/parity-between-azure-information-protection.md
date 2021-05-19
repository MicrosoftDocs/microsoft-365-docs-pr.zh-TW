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
description: 深入瞭解 Azure 資訊保護的詳細資訊，請 (AIP) ，以供世紀運作 Office 365 以及如何為中國的客戶進行設定。
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535839"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>由世紀運作之 Office 365 的 Azure 資訊保護支援

本文涵蓋 Azure 資訊保護 (AIP) 支援的 Office 365 （由世紀和商業產品運作），以及在中國為客戶設定 AIP 的特定指示， &mdash; 包括如何安裝 AIP 內部部署掃描器及管理內容掃描工作。

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>AIP 和商務版產品所運作的 Office 365 之間的差異

雖然我們的目標是將所有商業功能和功能提供給中國的客戶 AIP，以供由世紀所運作的 Office 365 使用，但仍有一些遺漏的功能可供您反白。

下列清單包含 AIP 在由世紀所運作的 Office 365 之間的現有缺口，以及從2021年1月的商業產品方案：

- 只有 Microsoft 365 Apps 企業版 (組建11731.10000 或更新) 版本，才支援資訊版權管理 (IRM) 。 Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。

- 目前無法使用從 Active Directory Rights Management Services (AD RMS) 遷移至 AIP。
  
- 支援與商業雲端中的使用者共用受保護的電子郵件。
  
- 目前無法使用商業雲端中的使用者共用檔和電子郵件附件。 這包括由使用者在商業雲端中運作的 Office 365、商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。
  
- 具有 SharePoint (irm 保護的網站與文件庫) 的 irm 目前無法使用。
  
- 目前無法使用 AD RMS 的行動裝置分機。

- Azure 中國的世紀不支援行動 [檢視器](/azure/information-protection/rms-client/mobile-app-faq) 。

- 中國的客戶無法使用 Azure 入口網站的 AIP 區域。 使用 [PowerShell 命令](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) ，而不是在入口網站中執行動作，例如管理及執行內容掃描工作。

## <a name="configure-aip-for-customers-in-china"></a>為中國的客戶設定 AIP

若要為中國的客戶設定 AIP：
1. [啟用租使用者的 Rights Management](#step-1-enable-rights-management-for-the-tenant)。

1. [新增 Microsoft Information Protection Sync service 服務主體](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)。

1. [設定 DNS 加密](#step-3-configure-dns-encryption)。

1. [安裝及設定 AIP 的整合標籤用戶端](#step-4-install-and-configure-the-aip-unified-labeling-client)。

1. [在 Windows 上設定 AIP 應用程式](#step-5-configure-aip-apps-on-windows)。

1. [安裝 AIP 內部部署掃描程式並管理內容掃描工作](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>步驟1：啟用租使用者的版權管理

為使加密正確運作，必須對租使用者啟用 RMS。

1. 檢查 RMS 是否已啟用：

    1. 以系統管理員身分啟動 PowerShell。
    2. 若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。
    3. 使用匯入模組 `Import-Module AipService` 。
    4. 使用服務連線 `Connect-AipService -environmentname azurechinacloud` 。
    5. 執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。

2. 如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>步驟2：新增 Microsoft 資訊保護同步服務服務主體

根據預設，Azure 中國租使用者無法使用 **Microsoft 資訊保護同步處理服務** 服務主體，Azure 資訊保護需要該主體。

1. 使用 [AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) Cmdlet 及 `870c4f2e-85b6-4d43-bdda-6ed9a579b725` Microsoft Information Protection Sync service 的應用程式識別碼，手動建立此服務主體。 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. 新增服務主體後，新增服務所需的相關許可權。

### <a name="step-3-configure-dns-encryption"></a>步驟3：設定 DNS 加密

若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡進行引導。 若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。 若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。

此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。 Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。

#### <a name="configure-dns-encryption---windows"></a>設定 DNS 加密-Windows

1. 取得 RMS ID:

    1. 以系統管理員身分啟動 PowerShell。
    2. 若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。
    3. 使用服務連線 `Connect-AipService -environmentname azurechinacloud` 。
    4. 執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。

2. 登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。

    - Service = `_rmsredir`
    - Protocol = `_http`
    - 名稱 = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) 
    - Priority，權數，Seconds，TTL = 預設值

3. 將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。 這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。

4. 使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn`) 供使用者建立。 在驗證程式中，可能需要進行其他 DNS 變更。 完成驗證之後，即可建立使用者。

#### <a name="configure-dns-encryption---mac-ios-android"></a>設定 DNS 加密-Mac、iOS、Android

登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。

- Service = `_rmsdisco`
- Protocol = `_http`
- 名稱 = `_tcp`
- Target = `api.aadrm.cn`
- 埠 = `80`
- Priority，權數，Seconds，TTL = 預設值


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>步驟4：安裝及設定 AIP 的整合標籤用戶端

從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載並安裝 AIP 的整合標籤用戶端。

如需詳細資訊，請參閱：

- [AIP 檔](/azure/information-protection/)
- [AIP 版本歷程記錄與支援原則](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 系統需求](/azure/information-protection/requirements)
- [AIP 快速入門：部署 AIP 用戶端](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理員指南](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 使用者指南](/azure/information-protection/rms-client/clientv2-user-guide)
- [深入瞭解 Microsoft 365 敏感度標籤](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>步驟5：在 Windows 上設定 AIP 應用程式

Windows 上的 AIP 應用程式需要下列登錄機碼，將其指向正確的 Azure 中國以及主權雲端：

- Registry 節點 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- 名稱 = `CloudEnvType`
- 值 = `6` (預設值 = 0) 
- Type = `REG_DWORD`

> [!IMPORTANT]
> 在卸載後，請確定您沒有刪除登錄機碼。 若機碼為空、不正確或不存在，則該功能將會以預設值 (預設值 = 0 （適用于商業性雲端) ）。 若機碼為空或不正確，則列印錯誤也會新增至記錄檔。

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>步驟6：安裝 AIP 內部部署掃描器及管理內容掃描工作

安裝 AIP 內部部署掃描器，以掃描您的網路和內容共用的機密資料，並套用組織原則中所設定的分類及保護標籤。

設定及管理內容掃描工作時，請使用下列程式，而不是商務用產品所用的 [Azure 入口網站介面](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) 。

如需詳細資訊，請參閱 [何謂 Azure 資訊保護統一的標記掃描器？](/azure/information-protection/deploy-aip-scanner) 和 [使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。

**若要安裝及設定掃描器**：

1. 登入將執行掃描器的 Windows 伺服器電腦。 使用具有本機系統管理員許可權的帳戶，且具有寫入 SQL Server master 資料庫的許可權。

1. 開始使用 PowerShell 關閉]。 如果您先前已安裝 AIP 用戶端和掃描器，請確定 **AIPScanner** 服務已停止。

1. 使用 [以 **系統管理員身分執行**] 選項開啟 Windows PowerShell 會話。

1. 執行[AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner)指令程式，指定您的 SQL Server 實例，以針對 Azure 資訊保護掃描程式建立資料庫，並指定您的掃描器叢集有意義的名稱。

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > 您可以在 [AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 命令中使用相同的叢集名稱，以將多個掃描器節點與同一個叢集產生關聯。 對多個掃描器節點使用相同的叢集，可讓多個掃描器一起運作，以執行掃描。
    > 

1. 使用系統 **管理工具** 服務，確認現在已安裝服務  >  ****。

    已安裝的服務命名為 **Azure 資訊保護掃描器** ，而且會設定為使用您建立的掃描器服務帳戶來執行。

1. 取得 Azure token 以搭配掃描器使用。 Azure AD token 可讓掃描器驗證 Azure 資訊保護服務，讓掃描器以非互動方式執行。 

    1. 開啟 Azure 入口網站，並建立 Azure AD 應用程式，以指定驗證的存取權杖。 如需詳細資訊，請參閱 how [to 以非互動式方式標記檔案以供 Azure 資訊保護](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)。
    
        > [!TIP]
        > 當您建立及設定 Azure AD 應用程式的 [AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 命令時，[ **要求 API 許可權** ] 窗格會顯示 [ **我的組織使用** ] 索引標籤，而非 [ **Microsoft APIs** ] 索引標籤的 APIs。選取 [ **我的組織所用的 APIs** ]，然後選取 [ **Azure Rights Management 服務**]。 
        >

    1. 從 Windows Server 電腦上，如果您的掃描器服務帳戶已授與 **本機登** 入的許可權，請使用此帳戶登入，然後啟動 PowerShell 會話。 
    
        如果您的掃描器服務帳戶無法授與安裝的 **本機登** 入許可權，請使用具有 [AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)的 *OnBehalfOf* 參數（如 [如何以非互動式方式標示 Azure 資訊保護](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)檔案中所述）。

    1. 執行 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)，指定從 Azure AD 應用程式複製的值：

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      例如：

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    掃描器現在具有用於驗證 Azure AD 的權杖。 根據您在 Azure AD 中設定的 **Web 應用程式/API** 用戶端密碼，此權杖的有效期為一年、兩年或永不。 當令牌到期時，您必須重複此程式。

1. 執行 [AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) 指令程式，將掃描器設定為在離線模式下運作。 運行：

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. 執行 [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) Cmdlet 來建立預設內容掃描工作。

    **AIPScannerContentScanJob 指令程式** 中的唯一必要參數會 **強制執行**。 不過，您此時可能會想為內容掃描工作定義其他設定。 例如：

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    以上語法會在您繼續設定時設定下列設定：

    - 讓掃描器執行排程，以進行 *手動*
    - 根據敏感度標籤原則，設定要探索的資訊類型
    - *不* 強制執行敏感度標記原則
    - 使用針對敏感度標記原則所定義的預設標籤，根據內容自動標籤檔
    - *不* 允許重新標記檔案
    - 在掃描及自動標籤時保留檔案詳細資料，包括 *修改日期*、 *上次修改* 時間及 *修改者* 值
    - 在執行時，將掃描器設定為排除 .msg 和 .tmp 檔案的狀態
    - 將預設擁有者設定為執行掃描器時所要使用的帳戶

1. 使用 [AIPScannerRepository 指令程式](/powershell/module/azureinformationprotection/add-aipscannerrepository) 來定義您想要在內容掃描工作中掃描的存放庫。 例如，執行：

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    使用下列其中一個語法，視您要新增的存放庫類型而定：

    - 若為網路共用，請使用 `\\Server\Folder` 。
    - 若為 SharePoint 庫，請使用 `http://sharepoint.contoso.com/Shared%20Documents/Folder` 。
    - 若為本機路徑： `C:\Folder`
    - 若為 UNC 路徑： `\\Server\Folder`

    > [!NOTE]
    > 不支援萬用字元，也不支援 WebDav 位置。
    >
    > 若要稍後修改存放庫，請改用 [AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) Cmdlet。 


視需要繼續執行下列步驟：

- [運行搜索循環並查看掃描器報告](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [使用 PowerShell 設定掃描器套用分類及保護](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [使用 PowerShell 以掃描器來設定 DLP 原則](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

下表列出與安裝掃描器及管理內容掃描工作相關的 PowerShell Cmdlet：

| 指令程式 | 描述 |
|--|--|
| [載入 AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 將新的存放庫加入至內容掃描工作。 |
| [AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|傳回群集的詳細資料。 |
| [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 取得內容掃描工作的詳細資料。 |
| [AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 取得針對內容掃描工作定義之存放庫的詳細資料。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 會刪除您的內容掃描工作。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 從內容掃描工作中移除存放庫。 |
| [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 定義內容掃描工作的設定。 |
| [AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 定義內容掃描工作中現有存放庫的設定。 |
| | |

如需詳細資訊，請參閱：

- [何謂 Azure 資訊保護的整合標籤掃描器？](/azure/information-protection/deploy-aip-scanner)
- [設定及安裝 Azure 資訊保護 (AIP) 整合的標記掃描器](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [僅使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。
