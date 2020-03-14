---
title: 設定 Office 365 中電子文件探索調查的合規性界限
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
description: 使用規範界限在 Office 365 組織內建立邏輯界限，以控制 eDiscovery 管理員可搜尋的使用者內容位置。 規範界限使用「搜尋許可權篩選」（也稱為「合規性安全性篩選」）控制特定使用者可搜尋的信箱、SharePoint 網站及 OneDrive 帳戶。
ms.openlocfilehash: 247c2649029d3029bb14ca9873a553f2ef8c356c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634141"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>設定 Office 365 中電子文件探索調查的合規性界限

使用核心 eDiscovery 或高級 eDiscovery 來管理調查時，可以套用本文中的指導方針。

規範界限會在 Office 365 組織內建立邏輯界限，以控制 eDiscovery 管理員可搜尋的使用者內容位置（例如信箱、SharePoint 網站和 OneDrive 帳戶）。 此外，合規性界限控制誰可以存取 eDiscovery 案例，以用於管理組織內的法律、人力資源或其他調查。 對於必須遵守地理 boarders 及法規及政府（通常分為不同的代理商）的跨國公司，必須使用規範界限。 在 Office 365 中，相容性界限可協助您在使用 eDiscovery 案例執行內容搜尋及管理調查時，符合這些需求。
  
我們會使用下圖中的範例，說明規範界限的運作方式。
  
![規範界限是由控制對電子檔或系統管理員角色群組存取的搜尋許可權篩選所組成，以控制 eDiscovery 案例的存取](../media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
在此範例中，Contoso 有限公司是由兩個分公司、第四個咖啡和 Coho Winery 所組成的 Office 365 組織。 業務要求 eDiscovery mangers 和調查人員只能在其代理人中搜尋 Exchange 信箱、OneDrive 帳戶及 SharePoint 網站。 此外，eDiscovery 管理員和調查人員只會查看其代理人中的 eDiscovery 案例，而且只能存取他們隸屬的案例。 以下是規範界限如何符合這些需求。
  
- 內容搜尋中的搜尋許可權篩選功能會控制 eDiscovery 管理員和調查人員可搜尋的內容位置。 這表示第四個咖啡機關中的 eDiscovery 管理員和調查人員，只能在第四個咖啡店中搜尋內容位置。 這種限制適用于 Coho Winery 子公司。
    
    角色群組控制誰可以查看安全性 & 合規性中心內的 eDiscovery 案例。 這表示 eDiscovery 管理員和調查人員只能查看其代理人中的 eDiscovery 案例。
    
- 角色群組也會控制誰可以指派成員至 eDiscovery 案例。 這表示 eDiscovery 管理員和調查人員只能將成員指派給他們本身是其成員的情況。
    
以下是設定規范界限的程式：
  
[步驟1：識別使用者屬性以定義您的機構](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步驟2：以 Microsoft 支援檔作為要求來同步處理使用者屬性與 OneDrive 帳戶](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[步驟3：建立每個代理人的角色群組](#step-3-create-a-role-group-for-each-agency)

[步驟4：建立搜尋許可權篩選以強制執行規范界限](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步驟5：建立內部公司調查的 eDiscovery 案例](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步驟1：識別使用者屬性以定義您的機構

第一步是選擇要使用的 Azure Active Directory 屬性，以定義您的機構。 此屬性是用來建立「搜尋許可權」篩選，它會限制 eDiscovery 管理員只搜尋指派此屬性之特定值之使用者的內容位置。 例如，假設 Contoso 決定使用 [**部門**] 屬性。 此屬性的值為第四個咖啡分公司中的使用者`FourthCoffee` ，則為 Coho Winery 子公司中的使用者的值。 `CohoWinery` 在步驟4中，您可以`attribute:value`使用此對（例如，*部門： FourthCoffee*）來限制 eDiscovery 管理員可搜尋的使用者內容位置。 
  
以下是 Azure Active Directory 使用者屬性的清單，您可以用於符合性界限：
  
- Company
    
- CustomAttribute1-CustomAttribute15
    
- 部門
    
- 辦公室

- C （兩個字母的國家/地區碼）
    
雖然有其他使用者屬性可供使用（特別是針對 Exchange 信箱），但以上所列的屬性是目前 OneDrive 支援的屬性。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步驟2：以 Microsoft 支援檔作為要求來同步處理使用者屬性與 OneDrive 帳戶

下一步是以 Microsoft 支援檔為要求，將您在步驟1中所選擇的 Azure Active Directory 屬性同步處理至組織中的所有 OneDrive 帳戶。 進行此同步處理之後，您在步驟1中所選擇的屬性（及其值）將會對應至名稱`ComplianceAttribute`SharePoint 中隱藏的 managed 屬性。 您可以在步驟4中使用此屬性為 OneDrive 建立搜尋許可權篩選。
  
當您將要求提交給 Microsoft 支援時包含下列資訊：
  
- Office 365 組織的預設功能變數名稱
    
- Azure Active Directory 屬性的名稱（步驟1）
    
- 以下是支援要求目的的標題或描述：「啟用相容性安全性篩選器的商務同步處理與 Azure Active Directory 的 OneDrive。 這有助於將要求路由傳送至執行要求的 Office 365 eDiscovery 工程小組。
    
在進行工程變更，並將屬性同步處理至 OneDrive 後，Microsoft 支援將會向您傳送所做變更的組建編號，以及預估的部署日期。 在您提交支援要求後，部署程式通常需要4–6周。
  
 **重要：** 您可以在部署變更之前，先完成步驟3到步驟5。 但是執行內容搜尋時，將不會從搜尋許可權篩選中指定的 OneDrive 網站傳回檔，直到部署變更為止。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>步驟3：建立每個代理人的角色群組

下一步是在安全性 & 規範中心建立角色群組，以與您的機構相符。 建議您在建立角色群組時，您可以複製內建的 eDiscovery 管理員群組、新增適當的成員，以及移除可能不適合您需求的角色。 如需有關 eDiscovery 相關角色的詳細資訊，請參閱[在 Office 365 Security & 合規性中心指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。
  
若要建立角色群組，請移至 [安全性 & 規範中心] 中的 [**許可權**] 頁面，為每個代理人中每個小組建立角色群組，以使用規範界限和 eDiscovery 案例來管理調查。 
  
使用 Contoso 相容性邊界案例，必須建立四個角色群組，並將適當的成員新增至每一個群組。
  
- 第四個咖啡 eDiscovery 管理員
    
- 第四個咖啡調查人員
    
- Coho Winery eDiscovery 管理員
    
- Coho Winery 調查人員
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步驟4：建立搜尋許可權篩選以強制執行規范界限

在您為每個代理商建立角色群組之後，下一步是建立搜尋許可權篩選器，將每個角色群組關聯至特定的代理人，並定義規範界限本身。 您必須為每個代理人建立一個搜尋許可權篩選。 如需建立安全性許可權篩選的詳細資訊，請參閱[設定內容搜尋的許可權篩選](permissions-filtering-for-content-search.md)。
  
以下是用來建立搜尋許可權篩選以用於規範界限的語法。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

以下是命令中每個參數的描述：
  
-  `FilterName`：指定篩選器的名稱。 使用描述或識別篩選所用的代理人的名稱。 
    
-  `Users`：指定套用此篩選器的使用者或群組，這些使用者或群組會套用到其執行的內容搜尋動作。 針對相容性界限，此參數會指定您在建立篩選的代理人中，您在步驟3中建立的角色群組。 附注這是多重值參數，因此您可以包含一或多個角色群組，以逗號分隔。 
    
-  `Filters`：指定篩選的搜尋準則。 針對規範界限，您可以定義下列篩選器。 每個套用至內容位置。 
    
    -  `Mailbox`：指定`Users`參數中定義的角色群組可以搜尋的信箱。 針對符合性界限， *ComplianceAttribute*是您在步驟1中識別的相同屬性，而*AttributeValue*會指定該代理人。 此篩選器允許角色群組的成員只搜尋特定機構中的信箱。例如， `"Mailbox_Department -eq 'FourthCoffee'"`。 
    
    -  `Site`：指定`Users`參數中定義的角色群組可以搜尋的 OneDrive 帳戶。 若為 OneDrive 篩選，請使用實際的`ComplianceAttribute`字串。 這會對應至您在步驟1中所識別的相同屬性，而該屬性會因您在步驟2中提交的支援要求而同步處理至 OneDrive 帳戶;*AttributeValue*指定的代理人。 此篩選器允許角色群組的成員只搜尋特定機構內的 OneDrive 帳戶;例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。
    
    -  `Site_Path`：指定`Users`參數中定義的角色群組可以進行搜尋的 SharePoint 網站。 *SharePointURL*會指定該角色群組的成員可以搜尋的代理人中的網站。 例如，  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 請注意`Site` ， `Site_Path`篩選器是由 **-或**運算子所連接。
    
     > [!NOTE]
     > `Filters`參數的語法包含*篩選器清單*。 篩選清單是一個包含信箱篩選器和以逗號分隔之網站篩選的篩選器。 在上面的範例中，請注意，逗號分隔**Mailbox_ComplianceAttribute**和**Site_ComplianceAttribute**： `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"`。 在執行內容搜尋時處理此篩選器時，會從 [篩選] 清單中建立兩個搜尋許可權篩選：一個信箱篩選器和一個網站篩選器。 使用篩選器清單的另一種方法是，為每個代理人建立兩個個別的「搜尋許可權」篩選：信箱屬性的單一搜尋許可權篩選，以及網站屬性的一個篩選器。 在任何情況下，結果都是相同的。 使用篩選清單或建立個別的「搜尋許可權」篩選是很重要的考慮。

-  `Action`：指定篩選所套用之符合性搜尋動作的類型。 例如，只有`-Action Search`當`Users`參數中定義的角色群組的成員執行內容搜尋時，才會套用篩選器。 在此情況下，匯出搜尋結果時不會套用篩選器。 針對規範界限，請`-Action All`使用，篩選器會套用到所有的搜尋動作。 
    
    如需內容搜尋動作的清單，請參閱[設定內容搜尋的許可權篩選](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的「New-ComplianceSecurityFilter」一節。

以下是兩個搜尋許可權篩選的範例，將建立這些篩選以支援 Contoso 規範界限案例。 這兩個範例都包含以逗號分隔的篩選清單，其中的信箱和網站篩選會包含在相同的搜尋許可權篩選中，並以逗號分隔。
  
 **第四個咖啡**

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

 **Coho Winery**

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>步驟5：建立內部公司調查的 eDiscovery 案例

最後一個步驟是在安全性 & 合規性中心建立 eDiscovery 案例，然後將您在步驟3中建立的角色群組新增為案例成員。 這會產生使用規範界限的兩個重要特徵：
  
- 只有新增至案例之角色群組的成員，才能夠在安全性 & 規範中心中查看和存取案例。 例如，如果第四個「咖啡調查人員」角色群組是案例的唯一成員，則第四個咖啡 eDiscovery 管理員角色群組的成員（或其他任何角色群組的成員）將無法看到或存取此案例。
    
- 當指派給案例的角色群組成員執行與案例相關聯的搜尋時，他們只會能夠搜尋其組織內的內容位置（由您在步驟4中建立的「搜尋許可權」篩選所定義）。

若要建立案例並指派成員：

1. 前往安全性 & 規範中心內的**eDiscovery**或**Advanced ediscovery**頁面，並建立案例。 

2. 在 eDiscovery 案例清單中，按一下您建立的案例名稱。

3. 在 [**管理此案例**飛入] 頁面的 [**管理角色群組**] 底下，按一下![[新增圖示](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新增**]。

    ![將角色群組新增為 eDiscovery 案例的成員](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 在角色群組的清單中，選取您在步驟3中建立的其中一個角色群組，然後按一下 [**新增**]。

5. 按一下 [**管理此案例**] 浮出控制項上的 [**儲存**] 以儲存變更。 

## <a name="compliance-boundary-limitations"></a>規範界限限制

在管理使用性範圍的 eDiscovery 案例和調查時，請牢記下列限制。
  
- 在建立和執行搜尋時，您可以選取您的代理人以外的內容位置。 不過，由於搜尋許可權篩選，來自這些位置的內容不會包含在搜尋結果中。

- 合規性界限不適用於 eDiscovery 案例中的保留。 這表示一個機構中的 eDiscovery 管理員可以將使用者放在不同的代理人中。 不過，如果 eDiscovery 管理員搜尋置於保留狀態之使用者的內容位置，就會強制執行規范界限。 這表示 eDiscovery 管理員無法搜尋使用者的內容位置，即使他們可以將使用者保留。

    此外，保留統計資料只會套用至代理人中的內容位置。

- 搜尋許可權篩選不適用於 Exchange 公用資料夾。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>在多地理位置環境中搜尋和匯出內容

搜尋許可權篩選也可讓您控制要匯出內容的位置，以及在[SharePoint 多地理位置環境](https://go.microsoft.com/fwlink/?linkid=860840)中搜尋內容位置時可搜尋的資料中心。
  
- **匯出搜尋結果：** 您可以從特定資料中心的 Exchange 信箱、SharePoint 網站和 OneDrive 帳戶匯出搜尋結果。 這表示您可以指定要從中匯出搜尋結果的資料中心位置。

    使用**New-ComplianceSecurityFilter**或**Set-ComplianceSecurityFilter** Cmdlet 的**Region**參數，來建立或變更匯出將透過哪一個資料中心進行路由傳送。
  
    |**參數值**|**資料中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美（資料中心在美國）  <br/> |
    |EUR  <br/> |歐洲  <br/> |
    |APC  <br/> |亞太地區  <br/> |
    |CAN <br/> |加拿大|
    |||
    
- **路由內容搜尋：** 您可以將 SharePoint 網站和 OneDrive 帳戶的內容搜尋路由傳送至附屬資料中心。 這表示您可以指定將執行搜尋的資料中心位置。
    
    使用**Region**參數的下列其中一個值，控制搜尋會在搜尋 SharePoint 網站和 OneDrive 帳戶時所執行的資料中心位置。 
  
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
    |||

   如果您未指定「搜尋許可權」篩選的**Region**參數，則會搜尋該組織的預設 SharePoint 區域。 搜尋結果會匯出至最接近的資料中心。

> [!TIP]
> 為了簡化概念， **Region**參數會控制用來搜尋 SharePoint 和 OneDrive 中內容的資料中心。 這不適用於搜尋 Exchange 中的內容，因為 Exchange 內容搜尋不會受資料中心地理位置的限制。 此外，相同的**Region**參數值也可能會規定匯出所傳送的資料中心。 這通常是必要的方式，以跨地理 boarders 控制資料的移動。<br/><br/>如果您使用的是 Advanced eDiscovery，請在 SharePoint 中搜尋內容，而且 OneDrive 並不受資料中心地理位置的限制。 會搜尋所有資料中心。 如需有關高級 eDiscovery 的詳細資訊，請參閱[Microsoft 365 中的 [高級 eDiscovery 解決方案一覽](overview-ediscovery-20.md)。

以下是在建立規範界限之搜尋許可權篩選時使用**Region**參數的範例。 這假設第四個咖啡分公司位於北美，且 Coho Winery 位於歐洲。 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

在多地理位置環境中搜尋和匯出內容時，請牢記下列事項。
  
- **[地區]** 參數不會控制 Exchange 信箱的搜尋。 當您搜尋信箱時，將會搜尋所有資料中心。 若要限制搜尋的 Exchange 信箱範圍，請在建立或變更搜尋許可權篩選時使用**Filters**參數。 
    
- 若要讓 eDiscovery 管理員在多個 SharePoint 區域中進行搜尋，您需要為該 eDiscovery 管理員建立不同的使用者帳戶，以便在搜尋許可權篩選中使用，以指定 SharePoint 網站或 OneDrive 的地區。帳戶位於。 如需有關設定此功能的詳細資訊，請參閱在[Office 365 的內容搜尋](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)中的「搜尋 SharePoint 多地理位置環境中的內容」一節。
    
- 當您在 SharePoint 和 OneDrive 中搜尋內容時， **Region**參數會將搜尋指引至 ediscovery Manager 執行 ediscovery 調查的主要或衛星位置。 [！注意] 如果 eDiscovery 管理員搜尋 SharePoint 和 OneDrive 「搜尋許可權」篩選中指定之區域以外的網站，將不會傳回任何搜尋結果。 
    
- 當您匯出搜尋結果時，所有內容位置（包括 Exchange、商務用 Skype、SharePoint、OneDrive 及其他可使用內容搜尋工具進行搜尋的 Office 365 服務）的內容都會上傳至位於**Region**參數所指定之資料中心的 Azure 存放位置。 這可協助組織在法規遵從性的情況中，不允許透過可控框線匯出內容。 如果 [搜尋許可權] 篩選中未指定任何區域，則會將內容上傳至組織的預設區域。 
    
- 您可以執行下列命令來編輯現有的「搜尋許可權」篩選，以新增或變更區域：

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="frequently-asked-questions"></a>常見問題集

 **誰可以建立及管理搜尋許可權篩選（使用 New-ComplianceSecurityFilter 和 Set-ComplianceSecurityFilter Cmdlet）？**
  
若要建立、查看及修改搜尋許可權篩選，您必須是 Security & 合規性中心內「組織管理」角色群組的成員。
  
 **若將 eDiscovery 管理員指派給跨越多個機關的一個以上角色群組，他們會如何在一個機構或另一個機構搜尋內容？**
  
EDiscovery 管理員可以將參數新增至其搜尋查詢，將搜尋限制在特定的代理人。 例如，如果組織已將**CustomAttribute10**屬性指定給不同的機構，他們可以在搜尋查詢中附加下列專案，以在特定機構中搜尋信箱和 OneDrive 帳戶： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。
  
 **若在搜尋許可權篩選中做為符合性屬性的屬性值已變更，會發生什麼事？**
  
搜尋許可權篩選會花三天的時間，以在篩選中所使用之屬性的值變更時，強制執行規范界限。 例如，在 Contoso 案例中，第四個咖啡機關中的使用者會轉接至 Coho Winery agency。 因此，使用者物件上的**部門**屬性值會從*FourthCoffee*變更為*CohoWinery*。 在此情況下，第四個咖啡 eDiscovery 和投資者會在屬性變更後的三天內，取得該使用者的搜尋結果。 同樣地，在 Coho Winery eDiscovery 管理員和調查人員取得使用者的搜尋結果之前，最多需要花三天。 
  
 **EDiscovery 管理員可以從兩個不同的規範界限查看內容嗎？**
  
是。 若要這樣做，可以將使用者新增至雙方都可以看見的角色群組。
  
 **搜尋許可權篩選器適用于 eDiscovery 案例保留、Office 365 保留原則或 DLP？**
  
否，但目前未這麼做。
  
 **如果我指定區域來控制匯出內容的位置，但我在該地區沒有 SharePoint 組織，仍然可以搜尋 SharePoint 嗎？**
  
如果組織中的「搜尋許可權」篩選中所指定的地區不存在，則會搜尋預設區域。
  
 **組織中可以建立的「搜尋許可權」篩選的數目上限為何？**
  
可在組織中建立的「搜尋許可權」篩選的數目沒有限制。 不過，當搜尋許可權篩選超過100時，搜尋效能會受到影響。 若要盡可能使組織中的「搜尋許可權」篩選的數目盡可能小，請盡可能建立篩選，將 Exchange、SharePoint 及 OneDrive 的規則結合成單一搜尋許可權篩選。
