---
title: 在 Microsoft 365 系統管理中心建立、編輯或刪除安全性群組
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: 瞭解如何建立、編輯或刪除安全性群組。
ms.openlocfilehash: 8f76b5fa803ea43e53e89cf6479eb7572a2857c2
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537592"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心建立、編輯或刪除安全性群組

在 [Microsoft 365 **群組**] 頁面上，您可以建立使用者帳戶群組，供您在 SharePoint 線上和 CRM online 中指派相同的許可權。 例如，管理員可以建立安全性群組以授與 SharePoint 網站存取權給特定群組的人員。 只有全域及使用者管理管理員擁有建立、編輯或刪除安全性群組的權限；如需管理員角色的詳細資訊，請參閱 [指派管理員角色](../add-users/assign-admin-roles.md)。 
  
您也可以使用 [Exchange Online 和 SharePoint Online 中的群組](#groups-in-exchange-online-and-sharepoint-online)來傳送電子郵件或指派權限給使用者群組，以及使用 [Exchange Online 和 SharePoint Online 中的群組](#groups-in-exchange-online-and-sharepoint-online)來授與網站及網站集合權限與存取權給使用者。 
  
> [!IMPORTANT]
>  打算使用網站信箱？ 透過安全性群組新增而不是個別新增至 SharePoint 網站的所有使用者僅能從 SharePoint 使用網站信箱。 這些使用者將無法從 Outlook 存取網站信箱。 如需詳細資訊，請參閱[使用 Microsoft 365 群組，而不是網站信箱](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)。 
  
## <a name="manage-security-groups-in-the-admin-center"></a>管理系統管理中心的安全性群組

### <a name="add-a-security-group"></a>新增安全性群組

1. 在 Microsoft 365 系統管理中心，移至 [**群組**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。
  
2. 在 [ **群組** ] 頁面上，選取 [ **新增群組**]。
    
3. 在 [ **選擇群組類型** ] 頁面上，選擇 [ **安全性**]。 
    
4. 遵循步驟完成群組的建立。 
 
### <a name="add-members-to-a-security-group"></a>新增成員至安全性群組
    
1. 在 [ **群組** ] 頁面上選取安全性群組名稱，然後在 [ **成員** ] 索引標籤上，選取 [ **全部查看] 和 [管理成員**]。 
    
2. 在 [群組] 窗格中，選取 [ **新增成員** ]，然後從清單中選擇人員，或在 **搜尋** 方塊中輸入您要新增的人員名稱，然後選取 [ **儲存**]。
    
    若要移除成員，請選取其名稱旁邊的 X。 
  
### <a name="edit-a-security-group"></a>編輯安全性群組

1. 在系統管理中心中，移至 [ **群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a> ] 頁面。
  
2. 在 [ **群組** ] 頁面上，選取群組的名稱。 
    
3. 在 [設定] 窗格中，選取 **[一般** ] 索引標籤或 [ **成員** ] 索引標籤，即可編輯群組詳細資料或成員。

### <a name="delete-a-security-group"></a>刪除安全性群組

1. 在系統管理中心中，移至 [**群組**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。
    
2. 在 [ **群組** ] 頁面上，選取群組的名稱。 
    
3. 選取 [ **刪除群組** (wasetbin 圖示) ]，然後選取 [ **刪除**] 加以確認。
    
    一旦刪除群組，請選取 [ **關閉** ]。 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Exchange Online 和 SharePoint Online 中的群組

如果您想要建立使用者群組，以便同時將電子郵件傳送給他們，您可以移至 [**管理** \> **Exchange** 收件者 \>  \> **群組**]，以在 Exchange 系統管理中心進行。 接下來，選取 [**新增**] ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) ，然後選取您要建立的群組類型： 
  
- **通訊群組**：用於發送訊息至使用者群組。 也稱為  *啟用郵件功能的通訊群組* 或  *通訊群組清單*。 如需詳細資訊，請參閱 [管理通訊群組](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)。
    
- **安全性群組**：可以用來將訊息發送至使用者群組，或是用於授與資源的存取權限。 這個群組又稱為 *啟用郵件功能的安全性群組*。 如需詳細資訊，請參閱 [管理擁有郵件功能的安全性群組](/Exchange/recipients/mail-enabled-security-groups)。
    
- **動態通訊群組**：每次傳送郵件時，此通訊群組類型就會根據您所定義的篩選和條件重新計算收件者清單。 如需詳細資訊，請參閱 [管理動態通訊群組](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)。
    
在 Exchange 系統管理中心建立通訊群組和擁有郵件功能的安全性群組之後，其名稱和使用者清單會出現在 [**安全性群組**] 頁面上。 您可以在這兩個位置刪除這些群組，但是僅可在 Exchange 系統管理中心對這些群組進行編輯。 動態通訊群組不會顯示在 [ **安全性群組** ] 頁面上。 
  
 SharePoint 群組會在您建立網站集合時自動建立。 預設群組會使用 SharePoint 中的預設權限等級 (有時稱為 SharePoint 角色) 來授與使用者權限與存取權。 如需詳細資訊，請參閱[Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups)。
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>安全性群組與我在 SharePoint 中建立的安全性群組有何不同？

安全性群組可以與 SharePoint、Exchange、MDM、Windows 等搭配使用。 您在 SharePoint 中所建立的安全性群組只能透過該 SharePoint 網站集合加以識別。
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>我需要使用安全性群組來保護組織的安全嗎？

否。 這只是另一種可管理組織安全性的方式。 您可以永遠授與使用者許可權，並個別地存取網站。 不過，使用安全性群組，您可以輕鬆管理較大的使用者群組。
  
## <a name="can-i-send-email-to-a-security-group"></a>我可以將電子郵件傳送至安全性群組嗎？

是。 不過，如果您想要使用群組進行電子郵件及共同作業，建議您改為[建立 Microsoft 365 群組](../create-groups/create-groups.md)。 
