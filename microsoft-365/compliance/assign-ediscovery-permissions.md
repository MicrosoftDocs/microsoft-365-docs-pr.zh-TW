---
title: 在安全性 & 規範中心指派 eDiscovery 許可權
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
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 使用安全性 & 合規性中心，指派執行 eDiscovery 相關工作所需的許可權。
ms.openlocfilehash: dc7eb61a006b41e519c76e70c768b551ff5126b9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631844"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>在安全性 & 規範中心指派 eDiscovery 許可權

如果您想要讓使用者在 Office 365 或 Microsoft 365 規範中心的安全性 & 合規性中心使用任何 eDiscovery 相關工具，您必須指派適當的許可權。 若要執行此動作，最簡單的方法是在安全性 & 合規性中心的 [**許可權**] 頁面上，加入適當的角色群組。 本主題說明使用安全性 & 合規性中心執行 eDiscovery 和內容搜尋相關工作所需的許可權。 
  
安全性 & 規範中心內主要 eDiscovery 相關角色群組稱為**EDiscovery 管理員**。 這個角色群組中有兩個子群組。 
  
- **Ediscovery 管理員**-ediscovery 管理員可以使用安全性 & 合規性中心的內容搜尋工具來搜尋組織中的內容位置，並執行各種與搜尋相關的動作，例如預覽及匯出搜尋結果。 成員也可以建立及管理 eDiscovery 案例和高級 eDiscovery 案例、新增及移除成員至案例、建立案例保留、執行與案例相關聯的搜尋，以及存取案例資料。 eDiscovery 管理員只可存取及管理他們建立的案例。 他們無法存取或管理其他 eDiscovery 管理員所建立的案例。
    
- **Ediscovery 管理員**-Ediscovery 系統管理員是 ediscovery 管理員角色群組的成員，可執行 ediscovery 管理員可執行檔相同內容搜尋與案例管理相關工作。 此外，電子檔探索管理員也可以：
    
  - 存取安全性 & 合規性中心的**ediscovery**和**Advanced ediscovery**頁面上列出的所有案例。 

  - 針對組織中的任何案例，存取高級 eDiscovery 中的案例資料。
    
  - 在將自我新增為案例成員後，管理任何 eDiscovery 案例。
  
  請參閱[詳細資訊](#more-information)一節，瞭解您可能想要組織中的 EDiscovery 系統管理員的原因。

> [!NOTE]
> 若要使用高級電子檔探索來分析使用者的資料，則必須將 Office 365 E5 或 Microsoft E5 授權指派給使用者（資料的保管人）。 或者，具有 E1 或 E3 授權的使用者可以獲指派 E5 附加元件授權。 指派給案例的系統管理員、規範監察官或法務人員，以及使用高級 eDiscovery 收集、查看和分析資料不需要 E5 授權。 如需授權的相關資訊，請參閱[Microsoft 365 授權指南以取得安全性 & 符合性](https://aka.ms/complianceSD)。
  
## <a name="before-you-begin"></a>開始之前

- 您必須是「組織管理」角色群組的成員，或被指派角色管理角色，才能在安全性 & 規範中心內指派 eDiscovery 許可權。
    
- 您可以使用安全性 & 規範中心 PowerShell 中的[Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember)指令程式，將擁有郵件功能的安全性群組新增為 ediscovery 管理員角色群組中的 ediscovery 管理員子群組成員。 不過，您無法將擁有郵件功能的安全性群組新增至 eDiscovery Administrators 子群組。 如需詳細資訊，請參閱[More information](#more-information)一節。 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>在安全性 & 規範中心指派 eDiscovery 許可權

1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的公司或學校帳戶登入。
    
3. 在安全性與合規性中心的左窗格中，選取 [**許可權**]，然後選取 [ **eDiscovery 管理員**] 旁邊的核取方塊。
    
4. 在 [ **EDiscovery 管理員**飛出] 頁面上，根據您想要指派的 eDiscovery 許可權，執行下列其中一項作業。 
  
    **讓使用者成為 EDiscovery 管理員：** 在 [ **EDiscovery 管理員**] 旁，選取 [**編輯**]。 在 [**選擇 ediscovery 管理員**] 區段中，選取 [**選擇 ediscovery 管理員**超連結] ![，然後](../media/ITPro-EAC-AddIcon.gif)選取 [新增圖示] [**新增**]。 選取您要新增為 eDiscovery 管理員的使用者（或使用者），然後選取 [**新增**]。 完成新增使用者的作業後，請選取 [**完成**]。 然後，在 [**編輯選擇 EDiscovery 管理員**飛出] 頁面上，選取 [**儲存**]，將變更儲存至 eDiscovery 管理員成員資格。
  
    **讓使用者成為 EDiscovery 管理員：** 在 [ **EDiscovery 管理員**] 旁，選取 [**編輯**]。 在 [**選擇 ediscovery 管理員**] 區段的 **[ediscovery Administrators**] 底下，選取 **[選擇 ediscovery 系統管理員**]， ![選取 [](../media/ITPro-EAC-AddIcon.gif) **編輯**]，然後選取 [新增圖示] [**新增**]。 選取您要新增為**EDiscovery 管理員**的使用者（或使用者），然後再**新增**。 完成新增使用者的作業後，請選取 [**完成**]。 然後，在 [**編輯選擇 EDiscovery 管理員**飛出] 頁面上，選取 [**儲存**]，將變更儲存至 eDiscovery 管理員成員資格。
      
> [!NOTE]
> 您也可以使用**eDiscoveryCaseAdmin** Cmdlet，讓使用者成為 EDiscovery 系統管理員。 不過，在您可以使用此 Cmdlet 將其設為 eDiscovery 系統管理員之前，必須將該使用者指派為案例管理角色。 如需詳細資訊，請參閱[Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217)。 
  
在 [安全性 & 規範中心] 的 [**許可權**] 頁面上，您也可以將使用者新增至合規性管理員、組織管理和檢閱者角色群組，將其指派給使用者 eDiscovery 相關的許可權。 如需指派給每個角色群組的 eDiscovery 相關 RBAC 角色的說明，請參閱 eDiscovery 各節[相關的 rbac 角色](#rbac-roles-related-to-ediscovery)。 

## <a name="rbac-roles-related-to-ediscovery"></a>EDiscovery 相關的 RBAC 角色

下表列出安全性 & 規範中心內的 eDiscovery 相關 RBAC 角色，並指出預設會指派每個角色的內建角色群組。 
    
|**角色**|**合規性系統管理員**|**eDiscovery 管理員 & 管理員**|**組織管理**|**檢閱者**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|案例管理 <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|合規性搜尋 <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|匯出 <br/> | <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|預覽 <br/>  | <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|檢閱 <br/>  | <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|RMS 解密 <br/>  ||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|搜尋和清除 <br/> | <br/> | <br/> |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
下列各節將說明上表列出的每個 eDiscovery 相關 RBAC 角色。

### <a name="case-management"></a>案例管理

此角色可讓使用者在安全性 & 規範中心內建立、編輯、刪除和控制 eDiscovery 和高級 eDiscovery 案例的存取。 如先前所述，必須先將案例管理角色指派給使用者，才能使用**eDiscoveryCaseAdmin**指令程式，讓他們成為 eDiscovery 管理員。 

### <a name="compliance-search"></a>合規性搜尋

此角色可讓使用者在安全性 & 合規性中心內執行內容搜尋工具，以搜尋信箱和公用資料夾、SharePoint 線上網站 OneDrive、商務用 Skype、商務用 Skype 交談、Microsoft 365 群組和 Microsoft 團隊，以及 Yammer 群組。 此角色可讓使用者取得搜尋結果的預估，並建立匯出報告，但需要其他角色才能啟動內容搜尋動作，例如預覽、匯出或刪除搜尋結果。

獲指派符合性搜尋角色但沒有「預覽」角色的使用者可以預覽已被指派「預覽」角色的使用者在其中啟動預覽動作的搜尋結果。 沒有「預覽」角色的使用者可以在建立初始預覽動作後的兩周內預覽結果。

同樣地，已獲指派符合性搜尋角色，但沒有匯出角色的使用者，可以下載已獲指派「匯出」角色之使用者在其中啟動匯出動作的搜尋結果。 不含「匯出」角色的使用者可以在建立初始匯出動作後，下載兩周的搜尋結果。 之後，除非使用「匯出」角色的人重新開機匯出，否則他們無法下載結果。

如需詳細資訊，請參閱[內容搜尋 In Office 365](content-search.md)。 

### <a name="export"></a>匯出

角色可讓使用者將內容搜尋的結果匯出至本機電腦。 它也可讓他們在 Advanced eDiscovery 中準備用於分析的搜尋結果。 

如需匯出搜尋結果的詳細資訊，請參閱[從安全性 & 合規性中心匯出搜尋結果](export-search-results.md)。

### <a name="hold"></a>Hold

此角色可讓使用者將內容保留在信箱、公用資料夾、網站、商務用 Skype 交談和 Microsoft 365 群組中。 內容處於保留狀態時，內容擁有者仍可修改或刪除原始內容，但是會保留內容直到移除保留或保留期間到期為止。 

如需有關保留的詳細資訊，請參閱：

- [電子文件探索案例](ediscovery-cases.md) 

- [進階 eDiscovery](add-custodians-to-case.md#step-4-place-custodians-on-hold)

### <a name="preview"></a>預覽

此角色可讓使用者查看內容搜尋所傳回的專案清單。 他們也可以開啟並查看清單中的每個專案，以查看其內容。

### <a name="review"></a>檢閱

此角色可讓使用者在[高級 ediscovery （古典）](office-365-advanced-ediscovery.md) （也稱為「*高級 ediscovery v1*」）中存取案例資料。 此角色的主要目的是讓使用者能夠存取高級 eDiscovery （古典）。 獲指派此角色的使用者可以在其成員的安全性 & 規範中心內，查看並開啟「 **eDiscovery** 」頁面上的案例清單。 使用者在安全性 & 規範中心存取案例後，可選取 [**切換至高級 ediscovery** ] 以存取及分析 advanced ediscovery （古典）中的案例資料。 此角色不允許使用者預覽與案例相關聯的內容搜尋結果，或是進行其他內容搜尋或案例管理工作。

> [!NOTE]
> 此時，已被指派「審閱」角色（或「檢閱者」角色群組的成員）的使用者無法存取 Microsoft 365 （也稱為「*高級 ediscovery v2*」）中的「[高級 ediscovery ediscovery」中](overview-ediscovery-20.md)的資料。 若要在高級 eDiscovery v2 中新增成員至案例，讓他們可以查看案例資料，使用者必須是 eDiscovery 管理員角色群組的成員。

### <a name="rms-decrypt"></a>RMS 解密

當您匯出搜尋結果或在高級 eDiscovery 中準備搜尋結果以進行分析時，此角色可讓使用者解密受版權保護的電子郵件。 如需匯出時對搜尋結果進行解密的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md)。

### <a name="search-and-purge"></a>搜尋和清除

此角色可讓使用者批量移除符合內容搜尋準則的資料。 如需詳細資訊，請參閱[搜尋並刪除組織中的電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。 

## <a name="more-information"></a>詳細資訊

- **為什麼要建立 eDiscovery 管理員？** 如先前所述，eDiscovery 系統管理員是 eDiscovery 管理員角色群組的成員，可在您的組織中查看和存取所有 eDiscovery 案例。 存取所有 eDiscovery 案例的能力有兩個重要的目的： 
    
  - 如果身為 eDiscovery 案例唯一成員的人員離開您的組織，沒有任何人 (包括「組織管理」角色群組的成員或「eDiscovery 管理員」角色群組的其他成員) 可以存取該 eDiscovery 案例，因為他們不是案例的成員。 在此情況下，完全無法存取案例的資料。 不過，因為 eDiscovery 管理員可以存取組織中的所有 eDiscovery 案例，所以他們可以查看案例，並將自己或其他 eDiscovery 管理員新增為案例的成員。
    
  - 因為 eDiscovery 管理員可以查看和存取所有的 eDiscovery 和高級 eDiscovery 案例，所以他們可以審核和監控所有案例和相關聯的符合性搜尋。 這可協助避免任何濫用法規遵從性搜尋或 eDiscovery 案例。 而且，由於 eDiscovery 管理員可以存取符合性搜尋結果中可能的敏感資訊，因此您應該限制 eDiscovery 系統管理員的人數。
    
- **我可以將群組新增為 eDiscovery 管理員角色群組的成員嗎？** 如先前所述，您可以使用安全性 & 規範中心 PowerShell 中的**Add-RoleGroupMember** Cmdlet，將擁有郵件功能的安全性群組新增為 ediscovery 管理員角色群組中的 ediscovery 管理員子群組成員。 例如，您可以執行下列命令，將擁有郵件功能的安全性群組新增至 eDiscovery 管理員角色群組。 
    
  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    不支援 Exchange 通訊群組和 Microsoft 365 群組。 您必須使用擁有郵件功能的安全性群組，您可以使用`New-DistributionGroup -Type Security`命令在 Exchange Online PowerShell 中建立。 您也可以在 Exchange 系統管理中心或 Microsoft 365 系統管理中心中，建立已啟用郵件功能的安全性群組（及新增成員）。 在您建立新的已啟用郵件功能的安全性後，可能需要長達60分鐘，才可將其新增至 eDiscovery 管理員角色群組。 
    
    也如先前所述，您無法使用安全性 & 合規性中心 PowerShell 中的**載入 eDiscoveryCaseAdmin**指令程式，讓 eDiscovery 管理員成為啟用郵件功能的安全性群組。 您只可以將個別使用者新增為 eDiscovery 管理員。 
    
    您也無法將擁有郵件功能的安全性群組新增為案例的成員。
