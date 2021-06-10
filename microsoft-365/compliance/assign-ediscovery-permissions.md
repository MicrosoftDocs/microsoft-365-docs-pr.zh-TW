---
title: 在 Microsoft 365 規範中心內指派 eDiscovery 許可權
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 使用「Microsoft 365 規範中心」指派執行 eDiscovery 相關工作所需的許可權。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63afafbb8254169e266e5a3305df64aa9d271f79
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782450"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>在 Microsoft 365 規範中心內指派 eDiscovery 許可權

如果您想要讓使用者在 Microsoft 365 規範中心使用任何[eDiscovery 相關工具](ediscovery.md)，您必須指派適當的許可權。 若要執行此動作，最簡單的方法是在「規範中心」的 [ **許可權** ] 頁面上，將適當的角色群組新增至人員。 本主題說明執行 eDiscovery 工作所需的許可權。
  
Microsoft 365 規範中心內主要 eDiscovery 相關角色群組稱為 **eDiscovery 管理員**。 此角色群組內有兩個子群組。
  
- **Ediscovery 管理員** -ediscovery 管理員可以使用 ediscovery 搜尋工具來搜尋組織中的內容位置，並執行各種與搜尋相關的動作，例如預覽及匯出搜尋結果。 成員也可以在核心 eDiscovery 和 Advanced eDiscovery 中建立及管理案例、在案例中新增及移除成員、建立案例保留、執行與案例相關聯的搜尋，以及存取案例資料。 電子文件探索管理員只能存取和管理其建立的案例。 其無法存取或管理其他電子文件探索管理員所建立的案例。
  
- **電子文件探索系統管理員** - 電子文件探索系統管理員是電子文件探索管理員角色群組的成員，而且可以和電子文件探索管理員一樣，執行相同的內容搜尋和案例管理相關工作。 此外，電子文件探索系統管理員還可以︰
  
  - 存取 Microsoft 365 規範中心的 **核心 eDiscovery** 和 **Advanced eDiscovery** 頁面上列出的所有案例。

  - 存取組織中任何案例的進階電子文件探索案例資料。
  
  - 在自行新增為案例的成員之後管理任何電子文件探索案例。
  
  針對您可能想要組織中的 eDiscovery 系統管理員的原因，請參閱 [詳細資訊](#more-information)。

> [!NOTE]
> 若要使用 Advanced eDiscovery 來分析使用者的資料，使用者必須 (資料) 指派 Office 365 E5 或 Microsoft 365 E5 授權。 或者，可以指派 Microsoft 365 E5 合規性的使用者或 Microsoft 365 的 eDiscovery 和審核附加元件授權，以 Office 365 E1 或 Office 365 或 Microsoft 365 E3 授權。 指派給案例的系統管理員、規範官員或法務人員，以及使用 Advanced eDiscovery 來收集、查看和分析資料不需要 E5 授權。 如需 Advanced eDiscovery 授權的詳細資訊，請參閱[Advanced eDiscovery 中的訂閱與授權](overview-ediscovery-20.md#subscriptions-and-licensing)。
  
## <a name="before-you-assign-permissions"></a>指派許可權之前

- 您必須是「組織管理」角色群組的成員，或被指派角色管理角色，才能在 Microsoft 365 規範中心指派 eDiscovery 許可權。

- 您可以使用安全性 & 規範中心 PowerShell 中的 [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) 指令程式，將擁有郵件功能的安全性群組新增為 ediscovery 管理員角色群組中的 ediscovery 管理員子群組成員。 不過，您無法將擁有郵件功能的安全性群組新增至 eDiscovery Administrators 子群組。 如需詳細資訊，請參閱 [詳細資訊](#more-information)。 
  
## <a name="assign-ediscovery-permissions"></a>指派電子文件探索權限

1. 移至 <https://compliance.microsoft.com> 並使用可指派許可權的帳戶登入。
  
2. 在 Microsoft 365 規範中心的左窗格中，選取 [**許可權**]。

3. 在 [ **許可權 & 角色** ] 頁面的 [ **規範中心**] 底下，按一下 [ **角色**]。

4. 在 [ **規範中心角色** ] 頁面上，選取 [ **eDiscovery 管理員**]。
  
5. 在 [ **EDiscovery 管理員** 飛出] 頁面上，根據您想要指派的 eDiscovery 許可權，執行下列其中一項作業。
  
    **讓使用者成為 EDiscovery 管理員：** 在 [ **EDiscovery 管理員**] 旁，選取 [ **編輯**]。 在 [ **選擇 EDiscovery 管理員** ] 嚮導頁面上，按一下 [ ![ 新增圖示] [ ](../media/ITPro-EAC-AddIcon.gif) **新增**]。 選取您要新增為 eDiscovery 管理員的使用者 (或使用者) ，然後選取 [ **新增**]。 完成新增使用者的作業後，請選取 [ **完成**]。 然後，在 [ **編輯選擇 EDiscovery 管理員** ] 頁面上，選取 [ **儲存** ]，將變更儲存至 eDiscovery 管理員成員資格。
  
    **讓使用者成為 EDiscovery 管理員：** 在 [ **EDiscovery 系統管理員**] 旁，選取 [ **編輯**]。 在 [ **選擇 EDiscovery 管理員** ] 頁面上，按一下 [ ![ 新增圖示] [ ](../media/ITPro-EAC-AddIcon.gif) **新增**]。 選取您要新增為 **EDiscovery 管理員** 的使用者 (或使用者) ，然後  **新增**。 完成新增使用者的作業後，請選取 [ **完成**]。 然後，在 [ **編輯選擇 EDiscovery 管理員** 嚮導] 頁面上，選取 [ **儲存** ]，將變更儲存至 eDiscovery 管理員成員資格。
  
> [!NOTE]
> 您也可以使用 **eDiscoveryCaseAdmin** Cmdlet，讓使用者成為 EDiscovery 系統管理員。 不過，在您可以使用此 Cmdlet 將其設為 eDiscovery 系統管理員之前，必須將該使用者指派為案例管理角色。 如需詳細資訊，請參閱 [Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin)。 
  
在 Microsoft 365 規範中心的 [**許可權**] 頁面上，您也可以將使用者新增至合規性管理員、組織管理和檢閱者角色群組，將其指派給使用者 eDiscovery 相關的許可權。 如需指派給每個角色群組的 eDiscovery 相關 RBAC 角色的說明，請參閱 [與 ediscovery 相關的 RBAC 角色](#rbac-roles-related-to-ediscovery)。

## <a name="rbac-roles-related-to-ediscovery"></a>EDiscovery 相關的 RBAC 角色

下表列出 Microsoft 365 規範中心內的 eDiscovery 相關 RBAC 角色，並指出預設會指派每個角色的內建角色群組。
  
| 角色 | 合規性系統管理員 | eDiscovery 管理員 & 管理員 | 組織管理 | 檢閱者 |
|:-----|:-----:|:-----:|:-----:|:-----:|
|案例管理 <br/> |![核取記號](../media/checkmark.png) <br/> |![核取記號](../media/checkmark.png) <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> |
|通訊 <br/> | <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> | <br/> |
|合規性搜尋 <br/> |![核取記號](../media/checkmark.png) <br/> |![核取記號](../media/checkmark.png) <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> |
|監管人 <br/> | <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> | <br/> |
|匯出 <br/> | <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![核取記號](../media/checkmark.png) <br/> |![核取記號](../media/checkmark.png) <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> |
|預覽 <br/>  | <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> | <br/> |
|檢閱 <br/>  | <br/> |![核取記號](../media/checkmark.png) <br/> | <br/> |![核取記號](../media/checkmark.png) <br/> |
|RMS 解密 <br/>  ||![核取記號](../media/checkmark.png) <br/> |||
|搜尋和清除 <br/> | <br/> | <br/> |![核取記號](../media/checkmark.png)           <br/> | <br/> |
||||
  
下列各節將說明上表列出的每個 eDiscovery 相關 RBAC 角色。

### <a name="case-management"></a>案例管理

此角色可讓使用者建立、編輯、刪除及控制 Microsoft 365 規範中心內的核心 eDiscovery 和 Advanced eDiscovery 案例的存取。 如先前所述，必須先將案例管理角色指派給使用者，才能使用 **eDiscoveryCaseAdmin** 指令程式，讓他們成為 eDiscovery 管理員。

如需詳細資訊，請參閱：

- [開始使用核心電子文件探索](get-started-core-ediscovery.md)

- [開始使用進階電子文件探索](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>通訊

此角色可讓使用者管理 Advanced eDiscovery 案例中識別的保管人的所有通訊。 這包括建立保留通知、保留提醒及上報到管理。 使用者也可以追蹤保留通知的保管人認可，並管理每位保管人所用的保管人入口網站存取，以追蹤識別為系統管理員的情況。

如需詳細資訊，請參閱使用[Advanced eDiscovery 中的通訊](managing-custodian-communications.md)。

### <a name="compliance-search"></a>合規性搜尋

此角色可讓使用者在 Microsoft 365 規範中心內執行「內容搜尋」工具，以搜尋信箱和公用資料夾、SharePoint 線上網站、商務用 OneDrive 網站、商務用 Skype 交談、Microsoft 365 群組，以及 Microsoft Teams 群組。 此角色可讓使用者取得搜尋結果的預估，並建立匯出報告，但需要其他角色才能啟動內容搜尋動作，例如預覽、匯出或刪除搜尋結果。

獲指派符合性搜尋角色但沒有「預覽」角色的使用者可以預覽已被指派「預覽」角色的使用者在其中啟動預覽動作的搜尋結果。 沒有「預覽」角色的使用者可以在建立初始預覽動作後的兩周內預覽結果。

同樣地，已獲指派符合性搜尋角色，但沒有匯出角色的使用者，可以下載已獲指派「匯出」角色之使用者在其中啟動匯出動作的搜尋結果。 不含「匯出」角色的使用者可以在建立初始匯出動作後，下載兩周的搜尋結果。 之後，除非使用「匯出」角色的人重新開機匯出，否則他們無法下載結果。

如需詳細資訊，請參閱[Office 365 中的內容搜尋](content-search.md)。

### <a name="custodian"></a>監管人

此角色可讓使用者在 Advanced eDiscovery 案例中識別及管理保管人，並使用 Azure Active Directory 和其他來源中的資訊，來尋找與保管人相關聯的資料來源。 使用者可以在案例中建立其他資料來源（例如信箱、SharePoint 網站和與保管人 Teams）。 使用者也可以在與保管人相關聯的資料來源上進行合法保留，以在案例的上下文中保留內容。

如需詳細資訊，請參閱[Advanced eDiscovery 中的使用保管人](managing-custodians.md)。

### <a name="export"></a>匯出

角色可讓使用者將內容搜尋的結果匯出至本機電腦。 它也可讓他們在 Advanced eDiscovery 中準備用於分析的搜尋結果。

如需匯出搜尋結果的詳細資訊，請參閱[從 Microsoft 365 合規性中心匯出搜尋結果](export-search-results.md)。

### <a name="hold"></a>Hold

此角色可讓使用者將內容保留在信箱、公用資料夾、網站、商務用 Skype 交談及 Microsoft 365 群組中。 內容處於保留狀態時，內容的擁有者仍可修改或刪除原始內容，但這個內容會保留到保留狀態移除或保留期間到期為止。

如需有關保留的詳細資訊，請參閱：

- [在核心 eDiscovery 中建立保留](create-ediscovery-holds.md) 

- [在 Advanced eDiscovery 中建立保留](add-custodians-to-case.md)

### <a name="preview"></a>預覽

此角色可讓使用者查看內容搜尋所傳回的專案清單。 其也可開啟和檢視清單中的每個項目，以檢視其內容。

### <a name="review"></a>檢閱

此角色可讓使用者在[Advanced eDiscovery](overview-ediscovery-20.md)中存取審閱集。 獲指派此角色的使用者可以查看並開啟「eDiscovery > 高級」頁面的 [ **eDiscovery 高級**] Microsoft 365 頁面上的案例清單。 使用者存取 Advanced eDiscovery 案例後，即可選取 [**檢查集合**] 以存取案例資料。 此角色不允許使用者預覽與案例相關聯的集合搜尋結果，或執行其他搜尋或案例管理工作。 具有此角色的使用者只可以存取審閱集中的資料。

### <a name="rms-decrypt"></a>RMS 解密

此角色可讓使用者在預覽搜尋結果及匯出解密許可權保護的電子郵件訊息時，查看受版權保護的電子郵件。 此角色也可讓使用者在加密的檔案附加至 eDiscovery 搜尋結果所包含的電子郵件訊息時，查看 (和匯出) 以 [Microsoft 加密技術](encryption.md) 加密的檔案。 此外，此角色可讓使用者在 Advanced eDiscovery 中檢查及查詢新增至審閱集的加密電子郵件附件。 如需有關 eDiscovery 中解密的詳細資訊，請參閱[Microsoft 365 eDiscovery tools 中的解密](ediscovery-decryption.md)。

### <a name="search-and-purge"></a>搜尋和清除

此角色可讓使用者批量移除符合內容搜尋準則的資料。 如需詳細資訊，請參閱 [搜尋並刪除組織中的電子郵件訊息](search-for-and-delete-messages-in-your-organization.md)。

## <a name="more-information"></a>其他資訊

- **為什麼要建立 eDiscovery 管理員？** 如先前所述，eDiscovery 系統管理員是 eDiscovery 管理員角色群組的成員，可在您的組織中查看和存取所有 eDiscovery 案例。 存取所有 eDiscovery 案例的能力有兩個重要的目的：

  - 如果身為 eDiscovery 案例唯一成員的人員離開您的組織，沒有任何人 (包括「組織管理」角色群組的成員或「eDiscovery 管理員」角色群組的其他成員) 可以存取該 eDiscovery 案例，因為他們不是案例的成員。 在此情況下，完全無法存取案例的資料。 不過，因為 eDiscovery 管理員可以存取組織中的所有 eDiscovery 案例，所以他們可以查看案例，並將自己或其他 eDiscovery 管理員新增為案例的成員。

  - 因為 eDiscovery 管理員可以查看和存取所有核心 eDiscovery 和 Advanced eDiscovery 案例，所以他們可以審核和監控所有案例和相關聯的符合性搜尋。 這可協助避免任何濫用法規遵從性搜尋或 eDiscovery 案例。 而且，由於 eDiscovery 管理員可以存取符合性搜尋結果中可能的敏感資訊，因此您應該限制 eDiscovery 系統管理員的人數。

- **我可以將群組新增為 eDiscovery 管理員角色群組的成員嗎？** 如先前所述，您可以使用安全性 & 規範中心 PowerShell 中的 **Add-RoleGroupMember** Cmdlet，將擁有郵件功能的安全性群組新增為 ediscovery 管理員角色群組中的 ediscovery 管理員子群組成員。 例如，您可以執行下列命令，將擁有郵件功能的安全性群組新增至 eDiscovery 管理員角色群組。 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    不支援通訊群組和 Microsoft 365 群組 Exchange。 您必須使用擁有郵件功能的安全性群組，您可以執行 Exchange Online PowerShell 中建立該安全性群組 `New-DistributionGroup -Type Security` 。 您也可以建立已啟用郵件功能的安全性群組 (並新增) 在 Exchange 系統管理中心或 Microsoft 365 系統管理中心中的成員。 在您建立新的已啟用郵件功能的安全性後，可能需要長達60分鐘，才可將其新增至 eDiscovery 管理員角色群組。 

    也如先前所述，您無法使用安全性 & 合規性中心 PowerShell 中的 **載入 eDiscoveryCaseAdmin** 指令程式，讓 eDiscovery 管理員成為啟用郵件功能的安全性群組。 您只可以將個別使用者新增為 eDiscovery 管理員。

    您也無法將擁有郵件功能的安全性群組新增為案例的成員。