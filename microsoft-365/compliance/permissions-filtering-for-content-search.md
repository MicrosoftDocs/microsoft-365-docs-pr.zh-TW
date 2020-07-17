---
title: 設定內容搜尋的權限篩選
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 使用內容搜尋許可權篩選，讓 eDiscovery 管理員只搜尋您組織中信箱和網站的子集。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06fabfd1132166e2439c9790b50b0dbcb5bdca2c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818772"
---
# <a name="configure-permissions-filtering-for-content-search"></a>設定內容搜尋的權限篩選

您可以使用搜尋許可權篩選，讓 eDiscovery 管理員只搜尋您組織中信箱和網站的子集。 您也可以使用權限篩選，讓相同的 eDiscovery 管理員僅搜尋符合特定搜尋準則的信箱或網站內容。 例如，您可以讓 eDiscovery 管理員只在特定位置或部門中搜尋使用者的信箱。 若要這麼做，您可以建立篩選器使用支援的收件者篩選器，以限制特定使用者或使用者群組可搜尋的信箱。 您也可以建立篩選，以指定使用者可搜尋的信箱內容。 可以藉由建立篩選器來完成這個動作，該篩選器會使用可搜尋的郵件屬性。 同樣地，您可以讓 eDiscovery 管理員只搜尋組織中的特定 SharePoint 網站。 您可以藉由建立篩選器來完成這個動作，該篩選器會限制可搜尋的網站。 您也可以建立篩選器，指定可搜尋的網站內容。 可以藉由建立篩選器來完成這個動作，該篩選器會使用可搜尋的網站屬性。

您也可以使用搜尋許可權篩選，在組織中建立邏輯界限（稱為「*符合性邊界*」），以控制特定 eDiscovery 管理員可以搜尋的使用者內容位置（例如信箱、SharePoint 網站和 OneDrive 帳戶）。 如需詳細資訊，請參閱[在 Office 365 中設定 eDiscovery 調查的合規性界限](tagging-and-assessment-in-advanced-ediscovery.md)。
  
「安全性 & 規範中心」中的「內容搜尋」功能支援「搜尋許可權篩選」。 這四個 Cmdlet 可讓您設定及管理搜尋許可權篩選：
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Remove-compliancesecurityfilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>設定許可權篩選的需求

- 若要執行相容性安全性篩選 Cmdlet，您必須是 Security & 合規性中心中「組織管理」角色群組的成員。 如需詳細資訊，請參閱[安全性與合規性中心中的權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。
    
- 您必須將 Windows PowerShell 連線到安全性 & 相容性中心與 Exchange Online 組織，才能使用相容性安全性篩選器 Cmdlet。 這是必要的，因為這些 Cmdlet 需要存取信箱內容，這就是您必須連線到 Exchange Online 的原因。 請參閱下一節中的步驟。 
    
- 請參閱[More information](#more-information)一節以取得搜尋權限篩選器的詳細資訊。 
    
- 搜尋許可權篩選適用于非使用中的信箱，這表示您可以使用信箱和信箱內容篩選來限制可搜尋非使用中信箱的人員。 如需許可權篩選和非使用中信箱的其他資訊，請參閱[詳細資訊](#more-information)一節。 
    
-  搜尋許可權篩選無法用來限制誰可以搜尋 Exchange 中的公用資料夾。 
    
- 可在組織中建立的「搜尋許可權」篩選的數目沒有限制。 但是當搜尋許可權篩選超過100時，搜尋效能會受到影響。 若要盡可能使組織中的「搜尋許可權」篩選的數目盡可能小，請盡可能建立篩選器，以在單一篩選中結合 Exchange、SharePoint 及 OneDrive 的規則。
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>在單一遠端 PowerShell 會話中連接至安全性 & 規範中心和 Exchange Online

1. 使用檔案名尾碼 **. ps1**，將下列文字儲存至 Windows PowerShell script 檔案。 例如，您可以將它儲存到名為**ConnectEXO-CC.ps1**的檔案。
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在您的本機電腦上，開啟 [Windows PowerShell]，移至您在上一個步驟中建立的腳本所在的資料夾，然後執行腳本;例如：
    
    ```powershell
    .\ConnectEXO-CC.ps1
    ```

如何知道這是否正常運作？ 在您執行腳本後，安全性 & 規範中心和 Exchange Online 的 Cmdlet 會匯入您的本機 Windows PowerShell 會話。 如果您未收到任何錯誤，便已順利連線。 快速測試是執行安全性 & 規範中心 Cmdlet 和 Exchange Online Cmdlet。 例如，您可以執行**安裝 UnifiedCompliancePrerequisite**和**Get-Mailbox**。 
  
如果您收到錯誤，請檢查下列需求：
  
- 密碼錯誤是常見的問題。再次執行這兩個步驟，並密切注意您在步驟 1 中輸入的使用者名稱和密碼。
    
- 確認您的帳戶可以具有安全規範中心的存取權限。 如需詳細資訊，請參閱 [讓使用者能夠存取安全性與合規性中心](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
    
- 為防止拒絕服務 (DoS) 攻擊，您最多只能為安全性與合規性中心建立三個遠端 PowerShell 連線。
    
- 必須設定 Windows PowerShell 以執行腳本。 這只必須執行一次，而不是每次連線時執行。 若要讓 Windows PowerShell 執行經過簽署的指令碼，請在提高權限的 Windows PowerShell 視窗 (藉由選取 **[以管理員身分執行]** 開啟的 Windows PowerShell 視窗) 中執行下列命令。

    ```powershell
    Set-ExecutionPolicy RemoteSigned
    ```

- 本機電腦與 Office 365 之間必須開啟 TCP 連接埠 80 流量。 該連接埠可能已開啟，但必須考量您的組織是否有限制性網際網路存取原則。

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter**是用來建立搜尋許可權篩選。 下表說明此 Cmdlet 的參數。 建立符合性安全性篩選器需要所有參數。 
  
|**參數**|**描述**|
|:-----|:-----|
| _Action_ <br/> | _Action_參數會指定篩選所套用的搜尋動作類型。 可能的內容搜尋動作是︰  <br/><br/> **匯出：** 匯出搜尋結果時套用篩選器。  <br/> **預覽：** 在預覽搜尋結果時會套用篩選器。  <br/> **清除：** 清除搜尋結果時，會套用篩選器。  <br/> **搜尋：** 在執行搜尋時會套用篩選器。  <br/> **All：** 篩選器會套用到所有的搜尋動作。  <br/> |
| _FilterName_ <br/> |_FilterName_參數會指定許可權篩選器的名稱。 此名稱是用來在使用 **Get-ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter,** 和 **Remove-ComplianceSecurityFilter** Cmdlet 時識別篩選器。  <br/> |
| _篩選_ <br/> | _Filters_參數會指定相容性安全性篩選器的搜尋準則。 您可以建立三種不同類型的篩選：  <br/><br/> **信箱篩選：** 這種篩選類型會指定所指派使用者（由_users_參數指定）可以搜尋的信箱。 此篩選器類型的語法為**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_會指定用於限定可搜尋之信箱的信箱屬性。 例如，信箱篩選器 `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` 允許指派此篩選器的使用者僅搜尋 CustomAttribute10 屬性中具有值 "OttawaUsers" 的信箱。  <br/>  任何支援的可篩選收件者屬性均可用於_MailboxPropertyName_屬性。 如需支援的屬性清單，請參閱可[篩選的-RecipientFilter 參數屬性](https://go.microsoft.com/fwlink/p/?LinkId=784903)。  <br/><br/> **信箱內容篩選：** 此篩選器類型會套用到可搜尋的內容。 它會指定所指派使用者可搜尋的信箱內容。 此篩選器類型的語法為**MailboxContent_** _SearchablePropertyName： Value_，其中_SearchablePropertyName_會指定可在內容搜尋中指定的關鍵字查詢語言（KQL）屬性。 例如，信箱內容篩選器 `MailboxContent_recipients:contoso.com` 允許指派此篩選器的使用者，只搜尋傳送至 contoso.com 網域中收件者的郵件。  <br/>  如需可搜尋郵件屬性的清單，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。 <br/> <br/> **重要：** 單一搜尋篩選無法包含信箱篩選器和信箱內容篩選器。 若要在單一篩選中結合這些專案，您必須使用[篩選器清單](#using-a-filters-list-to-combine-filter-types)。  不過，篩選可以包含相同類型的更複雜查詢。 例如，  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **網站與網站內容篩選：** Business site 相關篩選器有兩個 SharePoint 和 OneDrive，您可以用來指定所指派使用者可搜尋的網站或網站內容：  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  這兩個篩選器是可互換的。 例如， `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 並傳回 `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 相同的結果。 不過，為了協助您識別篩選的功能，您可以使用 `Site_` 來指定與網站相關的屬性（例如網站 URL），並 `SiteContent_` 指定內容相關的屬性（例如檔案類型）。 例如，篩選器 `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 允許指派此篩選器的使用者只搜尋網站集合中的內容 https://contoso.sharepoint.com/sites/doctors 。 篩選器 `"SiteContent_FileExtension -eq 'docx'"` 會允許指派此篩選器的使用者僅搜尋 word 檔（word 2007 和更新版本）。  <br/><br/>  如需可搜尋的網站屬性清單，請參閱[SharePoint 中的編目和 managed 屬性的概述](https://go.microsoft.com/fwlink/p/?LinkId=331599)。 在可**查詢**的資料行中，以**Yes**標示的屬性，可以用來建立網站或網站內容篩選。  <br/><br/> **重要：** 您必須建立搜尋許可權篩選，以明確避免使用者搜尋特定服務中的內容位置（例如防止使用者搜尋任何 Exchange 信箱或任何 SharePoint 網站）。 換句話說，建立搜尋許可權篩選可讓使用者搜尋組織中的所有 SharePoint 網站，不會妨礙該使用者搜尋信箱。 例如，若要讓 SharePoint 系統管理員只搜尋 SharePoint 網站，您必須建立篩選，以防止其搜尋信箱。 同樣地，若要允許 Exchange 管理員只搜尋信箱，您必須建立篩選，以防止使用者搜尋網站。           |
| _使用者_ <br/> |_Users_參數會指定將此篩選器套用至其內容搜尋的使用者。 依其別名或主要 SMTP 位址識別使用者。 您可以指定以逗號分隔的多個值，或者您也可以使用值 **All** 將篩選器指派給所有使用者。  <br/> 您也可以使用_Users_參數來指定安全性 & 規範中心角色群組。 這可讓您建立自訂角色群組，然後為該角色群組指派搜尋權限篩選器。 例如，假設您有多國公司的美國子公司的 eDiscovery 管理員的自訂角色群組。 您可以使用_Users_參數來指定此角色群組（使用角色群組的 Name 屬性），然後使用_Filter_參數，只允許搜尋美國的信箱。  <br/> 使用此參數，無法指定通訊群組。  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>使用篩選清單組合篩選器類型

*篩選清單*是一個包含信箱篩選器和以逗號分隔之網站篩選的篩選器。 只支援使用篩選清單來組合不同類型的篩選器。 在下列範例中，請注意分隔**信箱**和**網站**篩選的逗號：

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

當執行內容搜尋時處理包含篩選清單的篩選器時，會從 [篩選] 清單建立兩個搜尋許可權篩選：一個是以逗號分隔的每個篩選器。 所以在上一個範例中，會建立一個信箱搜尋許可權篩選和一個網站搜尋許可權篩選器。 

另一種使用篩選器清單的方式是建立兩個不同的搜尋許可權篩選。 在前一個範例中，您會為信箱屬性建立一個篩選器，並針對 site 屬性建立一個篩選。 在任何情況下，結果都是相同的。 使用篩選清單或建立個別的「搜尋許可權」篩選是很重要的考慮。

使用篩選器清單時，請牢記下列事項：

- 您必須使用篩選清單來建立包含**信箱**篩選器和**MailboxContent**篩選的篩選器。 

- 如先前所建議，您不需要使用篩選清單，在單一搜尋許可權篩選中包含**網站**和**SiteContent**篩選器。 例如，您可以使用 **-或**運算子組合**網站**和**SiteContent**篩選器。

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- 篩選清單的每個元件都可以包含複雜的篩選語法。 例如，信箱和網站篩選可包含以 **-或**運算子分隔的多個篩選：

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>建立搜尋許可權篩選的範例

以下是使用 **New-ComplianceSecurityFilter** Cmdlet 來建立搜尋權限篩選器的範例。 
  
本範例可讓使用者 annb@contoso.com 只針對加拿大的信箱執行所有內容搜尋動作。 此篩選器包含根據 ISO 3166-1 的三位數數字加拿大國碼。

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

本範例允許使用者的 donh 和 suzanf 僅搜尋「Marketing」值為 CustomAttribute1 信箱屬性的信箱。

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

此範例允許「美國探索管理員」角色群組的成員僅針對美國的信箱執行所有內容搜尋動作。此篩選器包含根據 ISO 3166-1 的三位數數字美國國碼。
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

此範例允許 eDiscovery 管理員角色群組的成員只搜尋 Ottawa Users 通訊群組成員的信箱。 Exchange Online PowerShell 中的 Get-DistributionGroup Cmdlet 是用來尋找 Ottawa 使用者群組的成員。
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

此範例可防止任何使用者從 Executive Team 通訊群組成員的信箱刪除內容。 Exchange Online PowerShell 中的 Get-DistributionGroup Cmdlet 是用來尋找 Executive 團隊群組的成員。

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

此範例允許 OneDrive eDiscovery Manager 自訂角色群組的成員只搜尋組織中商務位置 OneDrive 的內容。

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> 若要限制使用者搜尋特定網站，請使用篩選器 `Site_Path` ，如先前的範例所示。 使用 `Site_Site` 將無法運作。 
  
此範例會限制使用者只能對 2015 年期間傳送的電子郵件執行所有內容搜尋動作。

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

類似於先前的範例，此範例會限制使用者對於在 2015 年進行最後變更的文件執行所有內容搜尋動作。

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

此範例會防止「OneDrive 探索管理員」角色群組的成員在組織中的任何信箱上執行內容搜尋動作。 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

本範例會防止組織中的任何人搜尋 janets 或 sarad 所傳送或接收的電子郵件。

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

本範例會使用篩選清單來合併信箱和網站篩選器。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Remove-compliancesecurityfilter

**Remove-compliancesecurityfilter**是用來傳回搜尋許可權篩選的清單。 使用_FilterName_參數傳回特定搜尋篩選的資訊。 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter**用於修改現有的搜尋許可權篩選。 唯一必要的參數是_FilterName_。 
  
|**參數**|**描述**|
|:-----|:-----|
| _Action_| _Action_參數會指定篩選所套用的搜尋動作類型。 可能的內容搜尋動作是︰ <br/><br/> **匯出：** 匯出搜尋結果時套用篩選器。  <br/> **預覽：** 在預覽搜尋結果時會套用篩選器。  <br/> **清除：** 清除搜尋結果時，會套用篩選器。  <br/> **搜尋：** 在執行搜尋時會套用篩選器。  <br/> **All：** 篩選器會套用到所有的搜尋動作。  <br/> |
| _FilterName_|_FilterName_參數會指定許可權篩選器的名稱。 |
| _篩選_| _Filters_參數會指定相容性安全性篩選器的搜尋準則。 您可以建立兩種不同類型的篩選： <br/><br/>**信箱篩選：** 這種篩選類型會指定所指派使用者（由_users_參數指定）可以搜尋的信箱。 此篩選器類型的語法為**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_會指定用於限定可搜尋之信箱的信箱屬性。 例如，信箱篩選器 `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` 允許指派此篩選器的使用者僅搜尋 CustomAttribute10 屬性中具有值 "OttawaUsers" 的信箱。  任何支援的可篩選收件者屬性均可用於_MailboxPropertyName_屬性。 如需支援的屬性清單，請參閱可[篩選的-RecipientFilter 參數屬性](https://go.microsoft.com/fwlink/p/?LinkId=784903)。 <br/><br/>**信箱內容篩選：** 此篩選器類型會套用到可搜尋的內容。 它會指定所指派使用者可搜尋的信箱內容。 此篩選器類型的語法為**MailboxContent_** _SearchablePropertyName： Value_，其中_SearchablePropertyName_會指定可在內容搜尋中指定的關鍵字查詢語言（KQL）屬性。 例如，信箱內容篩選器 `MailboxContent_recipients:contoso.com` 允許指派此篩選器的使用者，只搜尋傳送至 contoso.com 網域中收件者的郵件。  如需可搜尋郵件屬性的清單，請參閱[內容搜尋的關鍵字查詢](keyword-queries-and-search-conditions.md)。 <br/><br/>**網站與網站內容篩選：** Business site 相關篩選器有兩個 SharePoint 和 OneDrive，您可以用來指定所指派使用者可搜尋的網站或網站內容： <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>這兩個篩選器是可互換的。 例如， `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 並傳回 `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 相同的結果。 不過，為了協助您識別篩選的功能，您可以使用 `Site_` 來指定與網站相關的屬性（例如網站 URL），並 `SiteContent_` 指定內容相關的屬性（例如檔案類型）。 例如，篩選器 `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 允許指派此篩選器的使用者只搜尋網站集合中的內容 https://contoso.spoppe.com/sites/doctors 。 篩選器 `"SiteContent_FileExtension -eq 'docx'"` 會允許指派此篩選器的使用者僅搜尋 word 檔（word 2007 和更新版本）。  <br/><br/>如需可搜尋的網站屬性清單，請參閱[SharePoint 中的編目和 managed 屬性的概述](https://go.microsoft.com/fwlink/p/?LinkId=331599)。 在可**查詢**的資料行中，以**Yes**標示的屬性，可以用來建立網站或網站內容篩選。 <br/><br/>          |
| _使用者_|_Users_參數會指定將此篩選器套用至其內容搜尋的使用者。 因為這是多重值屬性，所以使用此參數指定使用者或使用者群組時，會覆寫現有的使用者清單。 請參閱下列語法範例，以瞭解新增及移除選取的使用者。 <br/><br/>您也可以使用_Users_參數來指定安全性 & 規範中心角色群組。 這可讓您建立自訂角色群組，然後為該角色群組指派搜尋權限篩選器。 例如，假設您有多國公司的美國子公司的 eDiscovery 管理員的自訂角色群組。 您可以使用_Users_參數來指定此角色群組（使用角色群組的 Name 屬性），然後使用_Filter_參數，只允許搜尋美國的信箱。 <br/><br/>使用此參數，無法指定通訊群組。 |

## <a name="examples-of-changing-search-permissions-filters"></a>變更搜尋許可權篩選的範例

這些範例顯示如何使用**remove-compliancesecurityfilter**和**Set-ComplianceSecurityFilter** Cmdlet，將使用者新增到或移除篩選所指派的現有使用者清單。 當您新增或移除篩選器的使用者時，使用其 SMTP 位址指定使用者。 
  
此範例會將使用者新增至篩選器。

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

此範例會從篩選器移除使用者。

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter**用於刪除搜尋篩選器。 您可以使用_FilterName_參數來指定您要刪除的篩選。 
  
## <a name="more-information"></a>其他資訊

- **搜尋權限篩選如何運作？** 當執行內容搜尋時，權限篩選器會新增至搜尋查詢。 許可權篩選會以**和**Boolean 運算子加入搜尋查詢。 例如，您有許可權篩選，可讓王俊元對工作者通訊群組成員的信箱執行所有的搜尋動作。 然後，王俊元會使用搜尋查詢，在組織中的所有信箱上執行內容搜尋 `sender:jerry@adatum.com` 。 因為許可權篩選和搜尋查詢會以邏輯方式結合**and**運算子，所以搜尋會傳回所有 jerry@adatum.com 傳送給任何工作者通訊群組成員的郵件。 
    
- **如果您有多個搜尋權限篩選器會發生什麼情況？** 在內容搜尋查詢中，多個權限篩選器會藉由 **OR** 布林運算子合併。 因此任何篩選器為 true，則會傳回結果。 在內容搜尋中，所有篩選器 (由 **OR** 運算子合併) 隨後會與 **AND** 運算子的搜尋查詢合併。 讓我們採用上一個範例，其中的搜尋篩選器允許王俊元只搜尋工作者通訊群組成員的信箱。 然後我們建立另一個篩選器，防止 Bob 搜尋 Phil 的信箱 ("Mailbox_Alias -ne 'Phil'")。 同時假設 Phil 是 Workers 群組的成員。 當王俊元在組織中的所有信箱上執行內容搜尋時（來自上一個範例），即使您套用篩選器以避免王俊元搜尋 Phil 的信箱，還是會傳回 Phil 信箱的搜尋結果。 原因是允許 Bob 搜尋 Workers 群組的第一個篩選器為 true。 且由於 Phil 是 Workers 群組的成員，因此 Bob 可搜尋 Phil 的信箱。 
    
- **搜尋許可權篩選是否可用於非作用中的信箱？** 是的，您可以使用信箱和信箱內容篩選器來限制可搜尋組織中非使用中信箱的人員。 就像一般信箱一樣，非使用中的信箱必須設定收件者屬性，用來建立許可權篩選。 如有必要，您可以使用**Get-Mailbox-InactiveMailboxOnly**命令來顯示非使用中信箱的屬性。 如需詳細資訊，請參閱[在 Office 365 中建立及管理非](create-and-manage-inactive-mailboxes.md)使用中的信箱。
    
- **搜尋許可權篩選是否適用于公用資料夾？** 否。 如先前所述，「搜尋許可權篩選」無法用來限制誰可以搜尋 Exchange 中的公用資料夾。 例如，許可權篩選器無法從搜尋結果中排除公用資料夾位置中的專案。 
    
- **允許使用者搜尋特定服務中的所有內容位置也會防止他們搜尋不同服務中的內容位置嗎？** 否。 如先前所述，您必須建立搜尋許可權篩選，以明確避免使用者搜尋特定服務中的內容位置（例如防止使用者搜尋任何 Exchange 信箱或任何 SharePoint 網站）。 換句話說，建立搜尋許可權篩選可讓使用者搜尋組織中的所有 SharePoint 網站，不會妨礙該使用者搜尋信箱。 例如，若要讓 SharePoint 系統管理員只搜尋 SharePoint 網站，您必須建立篩選，以防止其搜尋信箱。 同樣地，若要允許 Exchange 管理員只搜尋信箱，您必須建立篩選，以防止使用者搜尋網站。
