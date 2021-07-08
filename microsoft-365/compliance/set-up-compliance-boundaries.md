---
title: 設定電子文件探索調查的合規性界限
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 了解如何使用合規性界限來建立邏輯界線，以控制電子文件探索管理員可在 Microsoft 365 中搜尋的使用者內容位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be857277d36d95ac1cd974ccb0c87f2048798450
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194706"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>設定電子文件探索調查的合規性界限

本文中的指引可在使用核心電子文件探索或進階電子文件探索來管理調查時進行套用。

合規性界限可在組織中建立邏輯界限，以控制電子文件探索管理員可搜尋的使用者內容位置 (例如信箱、OneDrive 帳戶和 SharePoint 網站)。 另外，合規性界線也控制誰可以存取用來管理組織內部法律、人力資源或其他調查的電子文件探索案例。 必須遵守地理邊界和法規的跨國公司，以及往往會分割為不同機關的政府機構，常常必須有合規性界限的需要。 在 Microsoft 365 中，合規性界限可協助您在執行內容搜尋及管理電子文件探索案例的調查時符合這些需求。
  
我們使用下列圖例中的範例來說明合規性界限運作的方式。
  
![合規性界限包含搜尋權限篩選，可控制對電子文件探索案例控制存取之機構與系統管理員角色群組的存取權](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
在此範例中，Contoso LTD 是由 Fourth Coffee 和 Coho Winery 這兩個子公司組成的組織。 這個企業要求電子文件探索管理員和調查人員只能搜尋其機構內的 Exchange 信箱、OneDrive 帳戶和 SharePoint 網站。 電子文件探索管理員和調查人員也只能查看其機構中的電子文件探索案例，且只能存取其身為成員的案例。 此外，在此案例中調查人員無法保留內容位置，也無法從案例匯出內容。 以下是合規性界限符合這些需求的方式。
  
- 內容搜尋中的搜尋權限篩選功能可控制電子文件探索管理員和調查人員可以搜尋的內容位置。 這表示 Fourth Coffee 機構內的電子文件探索管理員和調查人員只能搜尋 Fourth Coffee 子公司內的內容位置。 Coho Winery 子公司也有相同的限制。

- [角色群組](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery)提供以下的合規性界限功能：

  - 控制誰可以在 Microsoft 365 合規性中心查看電子文件探索案例。 這表示電子文件探索管理員和調查人員只能查看其機構內的電子文件探索案例。

  - 控制誰能夠將成員指派給電子文件探索案例。 這表示電子文件探索管理員和調查人員只能將成員指派給其本身為成員的案例。

  - 控制成員可以新增或移除指派特定權限角色來執行的電子文件探索相關工作。

以下是設定合規性界限的流程：
  
[步驟 1：識別使用者屬性以定義您的機構](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步驟 2：為每個機構建立角色群組](#step-2-create-a-role-group-for-each-agency)

[步驟 3：建立搜尋權限篩選來強制執行合規性界限](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步驟 4：建立電子文件探索案例以進行機構內部調查](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>在設定合規性界限之前

- 必須為使用者指派 Exchange Online 權限。 若要確認此情況，請使用 Exchange Online PowerShell 中的 [Get-User](/powershell/module/exchange/get-user) Cmdlet。

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步驟 1：識別使用者屬性以定義您的機構

第一個步驟是選擇要用來定義您機構的屬性。 此屬性用來建立搜尋權限篩選，以限制電子文件探索管理員只搜尋獲指派此屬性特定值之使用者的內容位置。 例如，假設 Contoso 決定使用 **[部門]** 屬性。 適用於 Fourth Coffee 子公司中使用者之此屬性的值會是 `FourthCoffee`，而 Coho Winery 子公司中使用者的值會是 `CohoWinery`。 在步驟 3 中，您使用此 `attribute:value` 組 (例如 *部門: FourthCoffee*) 來限制電子文件探索管理員可以搜尋的使用者內容位置。 
  
以下是一些可用於合規性界限的使用者屬性範例：
  
- 公司

- CustomAttribute1 - CustomAttribute15

- 部門

- 辦公室

- CountryOrRegion (兩個字母的國碼 (地區碼))

如需完整清單，請參閱支援的[信箱篩選](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)完整清單。

## <a name="step-2-create-a-role-group-for-each-agency"></a>步驟 2：為每個機構建立角色群組

下一個步驟是在安全性與合規性中心中建立與您的機構對應的角色群組。 建議您複製內建的電子文件探索管理員群組、新增適當的成員，以及移除可能不適用於您需求的角色，來建立角色群組。 如需有關電子文件探索相關角色的資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。
  
若要建立角色群組，請移至安全性與合規性中心內的 [權限]**** 頁面，然後為每個機構中將會使用合規性界限和電子文件探索案例來管理調查的每個小組建立角色群組。
  
使用 Contoso 合規性界限範例案例需要建立四個角色群組，並於個別其中新增適當的成員。
  
- Fourth Coffee 電子文件探索管理員

- Fourth Coffee 調查人員

- Coho Winery 電子文件探索管理員

- Coho Winery 調查人員
  
若要符合 Contoso 合規性界限案例的需求，也請移除調查人員角色群組中的 [保留 **]** 和 [匯出 **]** 角色，以防止調查人員對內容位置進行保留並從案例中匯出內容。

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步驟 3：建立搜尋權限篩選來強制執行合規性界限

為每個機構建立角色群組後，下一個步驟是建立搜尋權限篩選，可將每個角色群組與其特定機構建立關聯，並定義自身的合規性界限。 您必須為每個機構建立一個搜尋權限篩選。 如需建立安全性權限篩選的詳細資訊，請參閱[設定內容搜尋的權限篩選](permissions-filtering-for-content-search.md)。
  
以下是用來建立用於合規性界限之搜尋權限篩選的語法。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

以下是命令中每個參數的描述：
  
- `FilterName`：指定篩選的名稱。 使用描述或識別使用篩選器之機構的名稱。

- `Users`：指定將這個篩選套用至其所執行之搜尋動作的使用者或群組。 適用於合規性界限，此參數會指定您為其建立篩選的機構內角色群組 (在步驟 3 中建立)。 請注意此為多重值參數，因此您可以包含一或多個角色群組 (以逗號分隔)。

- `Filters`：指定篩選的搜尋準則。 適用於合規性界限，您可以定義下列篩選。 每個都適用於一個內容位置。

    - `Mailbox`：指定在 `Users` 參數中定義之角色群組可搜尋的信箱或 OneDrive 帳戶。 此篩選允許角色群組的成員只搜尋特定機構中的信箱或 OneDrive 帳戶；例如 `"Mailbox_Department -eq 'FourthCoffee'"`。

    - `Site_Path`：指定在 `Users` 參數中定義之角色群組可搜尋的 SharePoint 網站。 *SharePointURL* 指定角色群組成員可搜尋的機構中網站。 例如 `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 請注意， `Site` 和 `Site_Path` 篩選是由 **或** 運算子所連接。

     > [!NOTE]
     > `Filters` 參數的語法包含 *篩選清單*。 篩選清單是包含信箱篩選和網站路徑篩選的篩選 (以逗號分隔)。 在之前範例中，請注意逗號會分隔 **Mailbox_MailboxPropertyName** 和 **Site_Path**: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"`。 當在內容搜尋執行期間處理此篩選時，系統會從篩選清單建立兩個搜尋權限篩選：一個信箱篩選器和一個 SharePoint 篩選。 另一個您可以使用的篩選清單替代方案則是為每個機構建立兩個個別的搜尋權限篩選：一個信箱屬性的搜尋權限篩選，以及一個 SharePoint 網站屬性的篩選。 任何情況的結果都會相同。 請按照您的偏好使用篩選清單或建立個別的搜尋權限篩選。

- `Action`：指定篩選要套用至的搜尋動作類型。 例如， `-Action Search` 只有當在 `Users` 參數中定義的角色群組成員執行搜尋時，才會套用篩選。 在這種情況下，匯出搜尋結果時不會套用篩選。 適用於合規性界限，請使用 `-Action All` 以讓篩選套用至所有搜尋動作。 

    如需搜尋動作的清單，請參閱 [設定內容搜尋的權限篩選](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的 <New-ComplianceSecurityFilter> 一節。

以下是為了支援 Contoso 合規性界限案例所會建立的兩個搜尋權限篩選範例。 這兩個範例都包含逗號分隔篩選清單，信箱和網站篩選會包含在相同的搜尋權限篩選中，並以逗號分隔。
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>步驟 4：建立電子文件探索案例以進行機構內部調查

最後一個步驟是在 Microsoft 365 合規性中心建立核心電子文件探索案例或進階電子文件探索案例，然後將在步驟 2 中建立的角色群組新增為案例的成員。 這會造成使用合規性界限的兩個重要特性結果：
  
- 只有新增到案例的角色群組成員才能在安全性與合規性中心查看和存取案例。 例如，如果 Fourth Coffee 調查人員角色群組是案例的唯一成員，則 Fourth Coffee 電子文件探索管理員角色群組的成員 (或任何其他角色群組的成員) 都無法查看或存取案例。

- 當角色群組成員獲指派跟該案例相關聯的搜尋案例時，他們只能搜尋其機構內的內容位置 (由您於步驟 3 中建立之搜尋權限篩選所定義)。

若要建立案例並指派成員：

1. 前往 Microsoft 365 合規性中心的 **核心電子文件探索** 或 **進階電子文件探索** 頁面，然後建立案例。

2. 在案例清單中，按一下您建立的案例名稱。

3. 將角色群組新增為案例的成員。 如需指示，請參閱下列其中一個文章：

   - [將成員新增至核心電子文件探索案例](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [將成員新增至進階電子文件探索案例](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> 將角色群組新增至案例時，您只可以新增您身為其中成員的角色群組。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>在多地理位置環境中搜尋和匯出內容

搜尋權限篩選也讓您控制內容要路由傳送以匯出的位置，以及當搜尋 [SharePoint 多地理位置環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)中的內容位置時，可以搜尋的資料中心。
  
- **匯出搜尋結果：** 您可以從 Exchange 信箱、SharePoint 網站和特定資料中心中的 One Drive 帳戶中匯出搜尋結果。 這表示您可以指定搜尋結果匯出來源的資料中心位置。

    為 **New-ComplianceSecurityFilter** 或 **Set-ComplianceSecurityFilter** 　Cmdlet 使用 [地區 **]** 參數來建立或變更匯出要路由傳送經過的資料中心。
  
    |**參數值**|**資料中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美洲 (資料中心位於美國)  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN <br/> |加拿大|
    |||

- **路由內容搜尋：** 您可以將 SharePoint 網站和 OneDrive 帳戶的內容搜尋路由傳送至衛星資料中心。 這表示您可以指定要執行搜尋的資料中心位置。

    為 [地區 **]** 參數使用以下其中一個值，來控制搜尋 SharePoint 網站和 OneDrive 帳戶時會執行搜尋的資料中心位置。 
  
    |**參數值**|**SharePoint 的資料中心路由位置**|
    |:-----|:-----|
    |NAM  <br/> |美國  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN  <br/> |美國  <br/> |
    |AUS  <br/> |亞太地區  <br/> |
    |KOR  <br/> |組織的預設資料中心  <br/> |
    |GBR  <br/> |歐洲  <br/> |
    |JPN  <br/> |亞太地區  <br/> |
    |IND  <br/> |亞太地區  <br/> |
    |LAM  <br/> |美國  <br/> |
    |NOR  <br/> |歐洲 |
    |BRA  <br/> |北美洲資料中心 |
    |||

   如果您未指定搜尋權限權篩選的 [地區 **]** 參數，系統便會搜尋組織的主要 SharePoint 地區。 搜尋結果會匯出至最接近的資料中心。

   為了簡化概念，[地區 **]** 參數會控制用來搜尋 SharePoint 和 OneDrive 中內容的資料中心。 這不適用於在 Exchange 中搜尋內容，因為 Exchange 內容搜尋不受資料中心的地理位置所限制。 此外，相同的 [地區 **]** 參數值可能也會指定匯出要路由傳送經過的資料中心。 這通常是控制跨地理邊界資料的移動時所必須。

> [!NOTE]
> 如果您使用的是進階電子文件探索，[地區 **]** 參數不會控制資料的匯出來源地區。 資料會從組織的中央位置匯出。 此外，在 SharePoint 和 OneDrive 中搜尋內容不受資料中心的地理位置限制。 系統會搜尋所有資料中心。 如需進階電子文件探索的詳細資訊，請參閱 [Microsoft 365 進階電子文件探索解決方案概述](overview-ediscovery-20.md)。

以下是建立合規性界限的搜尋權限權篩選時使用的 [地區 **]** 參數範例。 這假設 Fourth Coffee 子公司位於北美洲，而 Coho Winery 則位於歐洲。 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

在多地理位置環境中搜尋和匯出內容時，請留意下列事項。
  
- [地區 **]** 參數不會控制 Exchange 信箱的搜尋。 搜尋信箱時，也會搜尋所有資料中心。 若要限制搜尋 Exchange 信箱的範圍，請在建立或變更搜尋權限篩選時使用 [篩選 **]** 參數。

- 如果電子文件探索管理員必須跨多個 SharePoint 地區搜尋，請務必為電子文件探索管理員員建立不同的使用者帳戶在搜尋權限篩選中使用，以用來指定 SharePoint 網站或 OneDrive 帳戶所在的地區。 如需有關設定此項目的資訊，請參閱[內容搜尋](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)中的 <搜尋 SharePoint 多地理位置環境中的內容> 一節。

- 在 SharePoint 和 OneDrive 中搜尋內容時，[地區 **]** 參數會將搜尋導向至電子文件探索管理員會進行電子文件探索調查的主要或衛星位置。 如果電子文件探索管理員搜尋搜尋權限篩選指定之區域以外的 SharePoint 和 OneDrive 網站，則不會傳回搜尋結果。

- 從核心電子文件探索匯出搜尋結果時，來自所有內容位置的內容 (包括 Exchange、商務用 Skype、SharePoint、OneDrive，以及您可以使用 [內容搜尋] 工具搜尋的其他服務) 會上傳至由 [地區 **]** 參數所指定之資料中心的 Azure 儲存體位置。 這可協助組織不允許跨受控制邊界匯出內容而保持合規性。 如果在搜尋權限篩選中未指定任何地區，則內容會上傳到組織的主要資料中心。

  從進階電子文件探索匯出內容時，您無法使用 [地區 **]** 參數控制內容的上傳位置。 內容會上傳到貴組織中央位置資料中心中的 Azure 儲存體位置。 如需根據您中央位置的地理位置清單，請參閱 [Microsoft 365 多地理位置電子文件探索設定](../enterprise/multi-geo-ediscovery-configuration.md)。

- 您可以執行下列命令，編輯現有的搜尋權限篩選以新增或變更地區：

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>使用 SharePoint 中樞網站的合規性界限

[SharePoint 中樞網站](/sharepoint/dev/features/hub-site/hub-site-overview)通常與電子文件探索合規性界限所遵循的相同地理或機構界限保持一致。 這表示您可以使用中樞網站的網站識別碼屬性來建立合規性界限。 若要這樣做，請使用 SharePoint Online PowerShell 中的 [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) Cmdlet 來取得中樞網站的 SiteId，然後為部門識別碼屬性使用此值來建立搜尋權限篩選。

使用下列語法來建立 SharePoint 中樞網站的搜尋權限權篩選：

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

以下是為 Coho Winery 機構中樞網站建立搜尋權限篩選的範例：

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>合規性界限限制

在管理使用合規性界限的電子文件探索案例和調查時，請考量到下列限制。
  
- 在建立及執行搜尋時，您可以選取機構外部的內容位置。 不過，由於搜尋權限篩選的緣故，這些位置的內容不會包含在搜尋結果中。

- 合規性界限不適用於電子文件探索案例中的保留。 這表示某家機構中的電子文件探索管理員可以保留不同機構中的使用者。 不過，如果電子文件探索管理員針對處於保留狀態的使用者搜尋其內容位置，則會強制執行合規性界限。 這表示電子文件探索管理員將無法搜尋使用者的內容位置，即使其可以保留使用者也沒有用。

    此外，保留統計資料只適用於機構中的內容位置。

- 如果您獲指派搜尋權限篩選 (信箱或網站篩選)，且嘗試匯出包含貴組織中所有 SharePoint 網站之搜尋的未編製索引項目，即會收到下列錯誤訊息: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied`。 如果您獲指派搜尋權限篩選，且要匯出 SharePoint 中的未編製索引項目，您必須重新執行搜尋，並包含要搜尋的特定 SharePoint 網站。 否則，您僅能從包含所有 SharePoint 網站的搜尋中匯出已編製索引的項目。 如需匯出搜尋結果時相關選項的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md#step-1-prepare-search-results-for-export)。

- 搜尋權限篩選不適用於 Exchange 公用資料夾。

## <a name="more-information"></a>其他資訊

- 如果信箱已取消授權或虛刪除，則不會再將使用者視為在合規性界限內。 如果信箱在刪除時處於保留狀態，則信箱中保留的內容仍會受合規性界限或搜尋權限篩選的規範。

- 如果已針對使用者實作合規性邊界和搜尋權限篩選，則建議您不要刪除該使用者的信箱以及其 OneDrive 帳戶。 換句話說，如果您刪除使用者的信箱，也應該移除該使用者的 OneDrive 帳戶，因為 mailbox_RecipientFilter 是用來強制執行 OneDrive 的搜尋權限篩選。

- 合規性界限和搜尋權限選取決於在 Exchange、OneDrive 和 SharePoint 中內容上的戳記屬性，以及此戳記內容的後續索引。

- 不建議針對內容型合規性界限使用排除篩選 (例如在搜尋權限篩選中使用 `-not()`)。 如果最近更新屬性的內容尚未編製索引，則使用排除篩選可能會產生未預期的結果。

## <a name="frequently-asked-questions"></a>常見問題集

**誰可以建立和管理搜尋權限篩選 (使用 New-ComplianceSecurityFilter 和 Set-ComplianceSecurityFilter Cmdlet)?**
  
若要建立、檢視及修改搜尋權限篩選，您必須是 Microsoft 365 合規性中心 [組織管理] 角色群組的成員。
  
**如果電子文件探索管理員獲指派超過一個跨多個機構的角色群組，他們如何在一家或另一家機構中搜尋內容?**
  
電子文件探索管理員可以將參數新增至其搜尋查詢，以將搜尋限制為特定機構。 例如，如果組織已指定 **CustomAttribute10** 屬性來區分機構，他們可以在搜尋查詢中附加下列項目，以搜尋特定機構中的信箱和 OneDrive 帳戶：`CustomAttribute10:<value>`。
  
**如果變更搜尋權限篩選中用來做為合規性屬性的屬性值，會發生什麼情況?**
  
如果篩選中使用的屬性值已變更，搜尋權限篩選最多需要三天才能強制執行合規性界限。 例如，在 Contoso 案例中假設 Fourth Coffee 機構中的使用者已轉移到 Coho Winery 機構。 因此，使用者物件上的 **[部門]** 屬性值會從 *FourthCoffee* 變更為 *CohoWinery*。 在這種情況下，Fourth Coffee eDiscovery 和投資者會在屬性變更後最多三天內依舊取得該使用者的搜尋結果。 同樣地，Coho Winery 電子文件探索管理員和調查人員最多需要等三天的時間才能取得該使用者的搜尋結果。
  
**電子文件探索管理員可以看到來自兩種個別合規性界限的內容嗎?**
  
是，在搜尋 Exchange 信箱時，將電子文件探索管理員新增至可看到這兩個機構的角色群組，即可達成此作業。 然而當搜尋 SharePoint 網站和 OneDrive 帳戶時，只有在機構位於相同的地區或地理位置時，電子文件探索管理員才能搜尋不同合規性界限中的內容。 **注意：** 進階電子文件探索中不適用此網站限制，因為搜尋 SharePoint 和 OneDrive 中的內容不受地理位置限制。
  
**搜尋權限篩選是否適用於電子文件探索案例保留、Microsoft 365 保留原則或 DLP?**
  
否，目前還不行。
  
**如果我指定要控制內容匯出位置的地區，但我在該地區沒有 SharePoint 組織，是否仍可搜尋 SharePoint?**
  
如果搜尋權限篩選中指定的地區不存在於貴組織中，則會搜尋預設地區。
  
**組織中可建立的搜尋權限篩選數目上限?**
  
組織中可建立的搜尋權限篩選數目並沒有限制。 不過，當有超過 100 個搜尋權限篩選時，搜尋的效能會受到影響。 若要盡可能減少貴組織的搜尋權限篩選數目，請盡可能建立將 Exchange、SharePoint 和 OneDrive 的規則結合成單一搜尋權限篩選的篩選。
