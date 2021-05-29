---
title: 設定 eDiscovery 調查的合規性界限
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
description: 瞭解如何使用規範界限來建立邏輯界限，以控制 eDiscovery 管理員可以在 Microsoft 365 中搜尋的使用者內容位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02e2e2f048ab521ad5640003cb127ed7bfa19641
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706603"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>設定 eDiscovery 調查的合規性界限

使用核心 eDiscovery 或 Advanced eDiscovery 管理調查時，可以套用本文中的指導方針。

規範界限在組織內建立邏輯界限，以控制使用者內容位置 (例如，信箱、OneDrive 帳戶，以及 eDiscovery 管理員可搜尋) 的 SharePoint 網站。 此外，合規性界限控制誰可以存取 eDiscovery 案例，以用於管理組織內的法律、人力資源或其他調查。 對於必須遵守地理 boarders 及法規及政府（通常分為不同的代理商）的跨國公司，必須使用規範界限。 在 Microsoft 365 中，相容性界限可協助您在使用 eDiscovery 案例執行內容搜尋及管理調查時符合這些需求。
  
我們會使用下圖中的範例，說明規範界限的運作方式。
  
![規範界限是由控制對電子檔或系統管理員角色群組存取的搜尋許可權篩選所組成，以控制 eDiscovery 案例的存取](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
在此範例中，Contoso 有限公司是由兩個分公司、第四個咖啡和 Coho Winery 所組成的組織。 業務要求 eDiscovery mangers 和調查人員只能搜尋其代理人中 Exchange 信箱、OneDrive 帳戶及 SharePoint 網站。 此外，eDiscovery 管理員和調查人員只會查看其代理人中的 eDiscovery 案例，而且只能存取他們隸屬的案例。 此外，在這種情況下，調查人員無法保留內容位置或從案例中匯出內容。 以下是規範界限如何符合這些需求。
  
- 內容搜尋中的搜尋許可權篩選功能會控制 eDiscovery 管理員和調查人員可搜尋的內容位置。 這表示 Fourth Coffee 機構內的電子文件探索管理員和調查人員只能搜尋 Fourth Coffee 子公司內的內容位置。 Coho Winery 子公司也有相同的限制。

- 角色群組為符合性界限提供下列功能：

  - 控制哪些人員可以查看安全性 & 合規性中心內的 eDiscovery 案例。 這表示電子文件探索管理員和調查人員只能查看其機構內的電子文件探索案例。

  - 控制誰可以指派成員至 eDiscovery 案例。 這表示電子文件探索管理員和調查人員只能將成員指派給其本身為成員的案例。

  - 新增或移除指派特定許可權的角色，以控制可執行成員的 eDiscovery 相關工作。

以下是設定規范界限的程式：
  
[步驟1：識別使用者屬性以定義您的機構](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步驟2：以 Microsoft 支援檔作為要求來同步處理使用者屬性與 OneDrive 帳戶](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[步驟3：建立每個代理人的角色群組](#step-3-create-a-role-group-for-each-agency)

[步驟4：建立搜尋許可權篩選以強制執行規范界限](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步驟5：建立內部公司調查的 eDiscovery 案例](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>設定規范界限之前

您必須先滿足下列必要條件， (您的 Azure Active Directory (Azure AD) 屬性必須能夠順利同步到步驟 2) 中的使用者 OneDrive 帳戶 (：

- 使用者必須獲指派 Exchange Online 授權和 SharePoint 線上授權。

- 使用者信箱的大小必須至少為 10 MB。 如果使用者的信箱小於 10 MB，用來定義您的組織的屬性不會同步到使用者的 OneDrive 帳戶。

- 規範界限和用來建立搜尋許可權篩選的屬性，都需要 Azure Active Directory (Azure AD) 屬性同步處理至使用者信箱。 若要確認您要使用的屬性已同步處理，請在 Exchange Online PowerShell 中執行[Get-User](/powershell/module/exchange/get-user) Cmdlet。 此 Cmdlet 的輸出會顯示同步處理至 Exchange Online 的 Azure AD 屬性。

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步驟1：識別使用者屬性以定義您的機構

第一步是選擇要使用的 Azure AD 屬性，以定義您的機構。 此屬性是用來建立「搜尋許可權」篩選，它會限制 eDiscovery 管理員只搜尋指派此屬性之特定值之使用者的內容位置。 例如，假設 Contoso 決定使用 [ **部門** ] 屬性。 此屬性的值為第四個咖啡分公司中的使用者，則為  `FourthCoffee`  Coho Winery 子公司中的使用者的值 `CohoWinery` 。 在步驟4中，您可以使用這一  `attribute:value`  對 (例如， *部門： FourthCoffee*) 來限制 eDiscovery 管理員可搜尋的使用者內容位置。 
  
以下是您可以用於規範界限的 Azure AD 使用者屬性清單：
  
- Company

- CustomAttribute1 CustomAttribute15

- 部門

- 辦公室

- C (兩個字母的國家代碼) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup>此屬性會對應至在 Exchange Online PowerShell 中執行 **Get-User** Cmdlet 所傳回的 CountryOrRegion 屬性。 Cmdlet 會傳回當地語系化的國家名稱，該名稱會從兩個字母的國家碼轉譯。 如需詳細資訊，請參閱 [Set-User](/powershell/module/exchange/set-user) Cmdlet 參考文章中的 CountryOrRegion 參數描述。

雖然有更多使用者屬性可供使用，尤其是針對 Exchange 信箱的情況下，上述屬性是 OneDrive 目前支援的屬性。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步驟2：以 Microsoft 支援檔作為要求來同步處理使用者屬性與 OneDrive 帳戶

下一步是以 Microsoft 支援檔為要求，將您在步驟1中所選擇的 Azure AD 屬性同步處理至組織中的所有 OneDrive 帳戶。 進行此同步處理之後，您在步驟1中所選擇的屬性 (及其值) 會對應至名為的隱藏 managed 屬性 `ComplianceAttribute` 。 您可以在步驟4中使用此屬性為 OneDrive 建立搜尋許可權篩選。
  
當您將要求提交給 Microsoft 支援時包含下列資訊：
  
- 組織的預設網功能變數名稱稱

- 步驟1中 (的 Azure AD 屬性名稱) 

- 以下是支援要求目的的標題或描述：「啟用相容性安全性篩選器的 Azure AD 商務用 OneDrive 同步處理」。 這有助於將要求路由傳送至實現要求的 eDiscovery 工程團隊。

在進行工程變更，並將屬性同步處理至 OneDrive 後，Microsoft 支援將會向您傳送所做變更的組建編號，以及預估的部署日期。 在您提交支援要求後，部署程式通常需要4–6周。
  
> [!IMPORTANT]
> 您可以在部署此屬性變更之前，先完成步驟3到步驟5。 但是執行內容搜尋時，不會從搜尋許可權篩選中指定的 OneDrive 帳戶傳回檔，直到部署屬性同步處理之後。
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>步驟3：建立每個代理人的角色群組

下一步是在安全性 & 規範中心建立角色群組，以與您的機構相符。 建議您複製內建的電子文件探索管理員群組、新增適當的成員，以及移除可能不適用於您需求的角色，來建立角色群組。 如需有關 eDiscovery 相關角色的詳細資訊，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。
  
若要建立角色群組，請移至安全性與合規性中心內的 [權限]**** 頁面，然後為每個機構中將會使用合規性界限和電子文件探索案例來管理調查的每個小組建立角色群組。
  
使用 Contoso 相容性邊界案例，必須建立四個角色群組，並將適當的成員新增至每一個群組。
  
- Fourth Coffee 電子文件探索管理員

- Fourth Coffee 調查人員

- Coho Winery 電子文件探索管理員

- Coho Winery 調查人員
  
為了符合 Contoso 合規性邊界案例的需求，您也可以移除「調查人員」角色群組中的 **保留** 和 **匯出** 角色，以防止調查人員在內容位置上放置保留，以及從案例中匯出內容。

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步驟4：建立搜尋許可權篩選以強制執行規范界限

在您為每個代理商建立角色群組之後，下一步是建立搜尋許可權篩選器，將每個角色群組關聯至特定的代理人，並定義規範界限本身。 您必須為每個代理人建立一個搜尋許可權篩選。 如需建立安全性許可權篩選的詳細資訊，請參閱 [設定內容搜尋的許可權篩選](permissions-filtering-for-content-search.md)。
  
以下是用來建立搜尋許可權篩選以用於規範界限的語法。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

以下是命令中每個參數的描述：
  
- `FilterName`：指定篩選器的名稱。 使用描述或識別篩選所用的代理人的名稱。

- `Users`：指定套用此篩選器的使用者或群組，將其套用至執行的搜尋動作。 針對相容性界限，此參數會指定您在建立篩選的代理人中，您在步驟 3) 中所建立的角色群組 (。 附注這是多重值參數，因此您可以包含一或多個角色群組，以逗號分隔。

- `Filters`：指定篩選的搜尋準則。 針對規範界限，您可以定義下列篩選器。 每個套用至內容位置。 

    - `Mailbox`：指定參數中定義的角色群組  `Users` 可以搜尋的信箱。 針對符合性界限，  *ComplianceAttribute*  是您在步驟1中識別的相同屬性，而  *AttributeValue*  會指定該代理人。 此篩選器允許角色群組的成員只搜尋特定機構中的信箱。例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。 

    - `Site`：指定參數中定義的角色群組可以搜尋的 OneDrive 帳戶 `Users` 。 若為 OneDrive 篩選，請使用實際的字串 `ComplianceAttribute` 。 這會對應至您在步驟1中所識別的相同屬性，而該屬性會因您在步驟2中提交的支援要求而同步處理至 OneDrive 帳戶;*AttributeValue* 指定的代理人。 此篩選器允許角色群組的成員只搜尋特定機構內的 OneDrive 帳戶;例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"` 。

    - `Site_Path`：指定參數中定義的角色群組 `Users` 可以進行搜尋的 SharePoint 網站。 *SharePointURL* 會指定該角色群組的成員可以搜尋的代理人中的網站。 例如，  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 請注意 `Site` ， `Site_Path` 篩選器是由 **-或** 運算子所連接。

     > [!NOTE]
     > 參數的語法 `Filters` 包含 *篩選器清單*。 篩選清單是一個包含信箱篩選器和以逗號分隔之網站篩選的篩選器。 在上面的範例中，請注意，逗號分隔 **Mailbox_ComplianceAttribute** 和 **Site_ComplianceAttribute**： `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` 。 在執行內容搜尋時處理此篩選器時，會從 [篩選] 清單中建立兩個搜尋許可權篩選：一個信箱篩選器和一個網站篩選器。 使用篩選器清單的另一種方法是，為每個代理人建立兩個個別的「搜尋許可權」篩選：信箱屬性的單一搜尋許可權篩選，以及網站屬性的一個篩選器。 在任何情況下，結果都是相同的。 使用篩選清單或建立個別的「搜尋許可權」篩選是很重要的考慮。

- `Action`：指定篩選所套用的搜尋動作類型。 例如，  `-Action Search` 只有當參數中定義的角色群組的成員執行搜尋時，才會套用篩選器 `Users` 。 在此情況下，匯出搜尋結果時不會套用篩選器。 針對規範界限，請使用，  `-Action All` 篩選器會套用到所有的搜尋動作。 

    如需搜尋動作的清單，請參閱 [設定內容搜尋的許可權篩選](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的「New-ComplianceSecurityFilter」一節。

以下是為了支援 Contoso 合規性界限案例所會建立的兩個搜尋權限篩選範例。 這兩個範例都包含逗號分隔篩選清單，信箱和網站篩選會包含在相同的搜尋權限篩選中，並以逗號分隔。
  
### <a name="fourth-coffee"></a>第四個咖啡

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>步驟5：建立內部公司調查的 eDiscovery 案例

最後一個步驟是在 Microsoft 365 規範中心建立核心 eDiscovery 案例或 Advanced eDiscovery 案例，然後將您在步驟3中建立的角色群組新增為案例成員。 這會產生使用規範界限的兩個重要特徵：
  
- 只有新增至案例之角色群組的成員，才能夠在安全性 & 規範中心中查看和存取案例。 例如，如果第四個「咖啡調查人員」角色群組是案例的唯一成員，則第四個咖啡 eDiscovery 管理員角色群組的成員 (或任何其他角色群組的成員) 將無法查看或存取此案例。

- 當指派給案例的角色群組成員執行與案例相關聯的搜尋時，他們只能夠搜尋其組織內的內容位置， (由您在步驟4中建立的「搜尋許可權」篩選所定義。 ) 

若要建立案例並指派成員：

1. 移至 Microsoft 365 規範中心內的 **核心 eDiscovery** 或 **Advanced eDiscovery** 頁面，並建立案例。

2. 在案例清單中，按一下您建立的案例名稱。

3. 將角色群組新增為案例的成員。 如需相關指示，請參閱下列其中一篇文章：

   - [新增成員至核心 eDiscovery 案例](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [將成員新增至 Advanced eDiscovery 案例](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> 將角色群組新增至案例時，您只可以新增您是其成員的角色群組。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>在多地理位置環境中搜尋和匯出內容

搜尋許可權篩選也可讓您控制要匯出內容的位置，以及在[SharePoint 多地理位置環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)中搜尋內容位置時可搜尋的資料中心。
  
- **匯出搜尋結果：** 您可以從特定資料中心的 Exchange 信箱、SharePoint 網站和 OneDrive 帳戶匯出搜尋結果。 這表示您可以指定要從中匯出搜尋結果的資料中心位置。

    使用 **New-ComplianceSecurityFilter** 或 **Set-ComplianceSecurityFilter** Cmdlet 的 **Region** 參數，來建立或變更匯出將透過哪一個資料中心進行路由傳送。
  
    |**參數值**|**資料中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美 (資料中心是在美國)   <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN <br/> |加拿大|
    |||

- **路由內容搜尋：** 您可以將 SharePoint 網站和 OneDrive 帳戶的內容搜尋路由傳送至附屬資料中心。 這表示您可以指定將執行搜尋的資料中心位置。

    使用 **Region** 參數的下列其中一個值，控制搜尋會在搜尋 SharePoint 網站和 OneDrive 帳戶時所執行的資料中心位置。 
  
    |**參數值**|**SharePoint 的資料中心路由位置**|
    |:-----|:-----|
    |NAM  <br/> |我們  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN  <br/> |我們  <br/> |
    |AUS  <br/> |亞太地區  <br/> |
    |KOR  <br/> |組織的預設資料中心  <br/> |
    |GBR  <br/> |歐洲  <br/> |
    |JPN  <br/> |亞太地區  <br/> |
    |IND  <br/> |亞太地區  <br/> |
    |議員  <br/> |我們  <br/> |
    |也  <br/> |歐洲 |
    |胸罩  <br/> |北美資料中心 |
    |||

   如果您未指定「搜尋許可權」篩選的 **Region** 參數，則會搜尋該組織的主要 SharePoint 區域。 搜尋結果會匯出至最接近的資料中心。

   為了簡化概念， **Region** 參數會控制用來搜尋 SharePoint 和 OneDrive 中內容的資料中心。 這不會套用至 Exchange 中搜尋內容，因為 Exchange 內容搜尋不會受資料中心地理位置的限制。 此外，相同的 **Region** 參數值也可能會規定匯出所傳送的資料中心。 這通常是必要的方式，以跨地理 boarders 控制資料的移動。

> [!NOTE]
> 如果您正在使用 Advanced eDiscovery，則 **region** 參數不會控制從中匯出資料的區域。 資料是從組織的主要資料中心匯出。 此外，搜尋 SharePoint 和 OneDrive 中的內容並不受資料中心地理位置的限制。 會搜尋所有資料中心。 如需 Advanced eDiscovery 的詳細資訊，請參閱[Microsoft 365 中的 Advanced eDiscovery 解決方案概況](overview-ediscovery-20.md)。

以下是在建立規範界限之搜尋許可權篩選時使用 **Region** 參數的範例。 這假設第四個咖啡分公司位於北美，且 Coho Winery 位於歐洲。 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

在多地理位置環境中搜尋和匯出內容時，請牢記下列事項。
  
- **[地區]** 參數不會控制 Exchange 信箱的搜尋。 當您搜尋信箱時，會搜尋所有資料中心。 若要限制搜尋 Exchange 信箱的範圍，請在建立或變更搜尋許可權篩選時使用 **Filters** 參數。 

- 若要讓 ediscovery 管理員在多個 SharePoint 區域中進行搜尋，您需要為該 ediscovery 管理員建立不同的使用者帳戶，以在「搜尋許可權」篩選中使用，以指定 SharePoint 網站或 OneDrive 帳戶所在的地區。 如需設定此選項的詳細資訊，請參閱[內容搜尋](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)中的「在 SharePoint 多地理位置環境中搜尋內容」一節。

- 在 SharePoint 和 OneDrive 中搜尋內容時， **Region** 參數會將搜尋導向主要或衛星位置，以 ediscovery 管理員進行 ediscovery 調查。 [！注意] 如果 eDiscovery 管理員搜尋 SharePoint 和 OneDrive 「搜尋許可權」篩選中指定之區域以外的網站，將不會傳回任何搜尋結果。

- 匯出搜尋結果時，所有內容位置的內容 (包括 Exchange、商務用 Skype、SharePoint、OneDrive，以及您可以使用內容搜尋工具進行搜尋的其他服務) 會上載至 **Region** 參數所指定之資料中心的 Azure 儲存體位置。 這可協助組織在法規遵從性的情況中，不允許透過可控框線匯出內容。 如果 [搜尋許可權] 篩選中未指定任何區域，則會將內容上傳至組織的主要資料中心。

- 您可以執行下列命令來編輯現有的「搜尋許可權」篩選，以新增或變更區域：

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>使用 SharePoint hub 網站的規範界限

[SharePoint hub 網站](/sharepoint/dev/features/hub-site/hub-site-overview)通常會與 eDiscovery 相容性邊界遵循的相同地理位置或代理商界限對齊。 這表示您可以使用 hub 網站的 site ID 屬性來建立符合性界限。 若要這麼做，請在 SharePoint Online PowerShell 中使用[SPOHubSite 指令程式](/powershell/module/sharepoint-online/get-spohubsite#examples)，以取得 hub 網站的 SiteId，然後使用 [部門 ID] 屬性的此值建立搜尋許可權篩選。

使用下列語法為 SharePoint hub 網站建立搜尋許可權篩選：

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

以下是為 Coho Winery agency 的 hub 網站建立搜尋許可權篩選的範例：

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>規範界限限制

在管理使用性範圍的 eDiscovery 案例和調查時，請牢記下列限制。
  
- 在建立及執行搜尋時，您可以選取機構外部的內容位置。 不過，由於搜尋權限篩選的緣故，這些位置的內容不會包含在搜尋結果中。

- 合規性界限不適用於 eDiscovery 案例中的保留。 這表示某家機構中的電子文件探索管理員可以保留不同機構中的使用者。 不過，如果電子文件探索管理員針對處於保留狀態的使用者搜尋其內容位置，則會強制執行合規性界限。 這表示電子文件探索管理員將無法搜尋使用者的內容位置，即使其可以保留使用者也沒有用。

    此外，保留統計資料只適用於機構中的內容位置。

- 如果您是指派「搜尋許可權」篩選 (信箱或網站篩選) ，而您嘗試匯出包含組織中所有 SharePoint 網站之搜尋的未編制索引項目目，您會收到下列錯誤訊息： `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` 。 如果您是指派「搜尋許可權」篩選，而且想要從 SharePoint 匯出未編制索引的專案，則必須重新執行搜尋，並包含特定 SharePoint 網站進行搜尋。 否則，您只可以從包含所有 SharePoint 網站的搜尋中匯出已編制索引的專案。 如需有關匯出搜尋結果時的選項的詳細資訊，請參閱 [匯出內容搜尋結果](export-search-results.md#step-1-prepare-search-results-for-export)。

- 搜尋權限篩選不會適用於 Exchange 公用資料夾。

## <a name="more-information"></a>詳細資訊

- 如果信箱是取消授權或虛刪除的，Azure AD 屬性就不再同步處理至信箱。 如果信箱已被刪除時保留在信箱上，則保留在信箱中的內容仍受限於符合性界限或搜尋許可權篩選器（根據上次在刪除信箱前同步處理 Azure AD 屬性的時間）。 

    此外，如果信箱是解除授權或虛刪除，使用者的信箱與 OneDrive 帳戶之間的同步處理會停止。 OneDrive 帳戶之符合性屬性的最後一個衝壓值會保持有效。

- 符合性屬性每7天會從使用者的 Exchange 信箱同步處理到其 OneDrive 帳戶。 如先前所述，只有當使用者同時指派 Exchange Online 和 SharePoint 線上授權，且使用者的信箱至少 10 MB 時，才會發生此同步處理。

- 如果使用者的信箱和 OneDrive 帳戶都執行規范界限和搜尋許可權篩選，則建議您不要刪除使用者的信箱，而非刪除其 OneDrive 帳戶。 換句話說，如果您刪除使用者的信箱，您也應該移除該使用者的 OneDrive 帳戶。

- 在某些情況下 (例如退回員工) ，而使用者可能會有兩個或多個 OneDrive 帳戶。 在這些情況下，只會同步處理 Azure AD 中的使用者相關的主要 OneDrive 帳戶。

- 規範界限和搜尋許可權篩選器，取決於在 Exchange、OneDrive 及 SharePoint 中的內容上加蓋的屬性，以及此衝壓內容的後續編制索引。 

- 建議您不要使用排除篩選 (例如 `-not()` 在搜尋許可權篩選) 中使用以內容為基礎的規範界限。 若最近更新之屬性的內容尚未編制索引，使用排除篩選可能會產生意外的結果。 

## <a name="frequently-asked-questions"></a>常見問題集

**神秘可以使用 New-ComplianceSecurityFilter 和 Set-ComplianceSecurityFilter Cmdlet) 來建立及管理搜尋許可權篩選 (？**
  
若要建立、查看及修改搜尋許可權篩選，您必須是 Security & 合規性中心內「組織管理」角色群組的成員。
  
**若將 eDiscovery 管理員指派給跨越多個機關的一個以上角色群組，他們會如何在一個機構或另一個機構搜尋內容？**
  
EDiscovery 管理員可以將參數新增至其搜尋查詢，將搜尋限制在特定的代理人。 例如，如果組織已將 **CustomAttribute10** 屬性指定給不同的機構，他們可以在搜尋查詢中附加下列專案，以在特定機構中搜尋信箱和 OneDrive 帳戶： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` 。
  
**若在搜尋許可權篩選中做為符合性屬性的屬性值已變更，會發生什麼事？**
  
搜尋許可權篩選會花三天的時間，以在篩選中所使用之屬性的值變更時，強制執行規范界限。 例如，在 Contoso 案例中，第四個咖啡機關中的使用者會轉接至 Coho Winery agency。 因此，使用者物件上的 **部門** 屬性值會從 *FourthCoffee* 變更為 *CohoWinery*。 在此情況下，第四個咖啡 eDiscovery 和投資者會在屬性變更後的三天內，取得該使用者的搜尋結果。 同樣地，在 Coho Winery eDiscovery 管理員和調查人員取得使用者的搜尋結果之前，最多需要花三天。
  
**EDiscovery 管理員可以從兩個不同的規範界限查看內容嗎？**
  
是的，您可以在搜尋 Exchange 信箱時，將 eDiscovery 管理員新增至雙方都能看到這兩個機構的角色群組。 不過，當搜尋 SharePoint 網站和 OneDrive 帳戶時，只有當機構位於相同地區或地理位置時，eDiscovery 管理員才能搜尋不同規範界限中的內容。 **附注：** 由於搜尋 SharePoint 中的內容，而且 OneDrive 並未依地理位置系結，所以這些網站的限制不適用於 Advanced eDiscovery。
  
**搜尋許可權篩選器適用于 eDiscovery 案例保留、Microsoft 365 保留原則或 DLP？**
  
否，但目前未這麼做。
  
**如果我指定區域來控制匯出內容的位置，但我在該地區沒有 SharePoint 組織，仍然可以搜尋 SharePoint 嗎？**
  
如果組織中的「搜尋許可權」篩選中所指定的地區不存在，則會搜尋預設區域。
  
**組織中可以建立的「搜尋許可權」篩選的數目上限為何？**
  
可在組織中建立的「搜尋許可權」篩選的數目沒有限制。 不過，當搜尋許可權篩選超過100時，搜尋效能會受到影響。 若要盡可能使組織中的「搜尋許可權」篩選的數目盡可能小，請盡可能建立篩選，將 Exchange、SharePoint 和 OneDrive 的規則結合成單一搜尋許可權篩選。