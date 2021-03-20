---
title: 新增或移除 Microsoft 365 群組中的成員
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: 瞭解如何將成員新增至群組、從群組中移除成員及管理 Microsoft 365 系統管理中心中的群組擁有者狀態。
ms.openlocfilehash: 997145b85d2990d5bf7184f5e97a0a8d1c86dae9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907913"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>使用系統管理中心新增或移除 Microsoft 365 群組中的成員

在 Microsoft 365 中，群組成員通常會建立自己的群組、將自己新增至他們想要加入的群組，或由群組擁有者邀請。 如果群組擁有權變更，或者您決定要新增或移除成員，您也可以在系統管理員進行變更。 只有全域系統管理員、Exchange 系統管理員、群組管理員或使用者管理員可以進行這些變更。 [何謂 Microsoft 365 群組？](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> 如果您不是系統管理員，則可以 [使用 Outlook 來新增或移除成員](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)。
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>將成員新增至系統管理中心的群組

1. 在系統管理中心中，移至 [作用中 [**群組**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] 頁面。  

2. 按一下群組名稱。

3. 在 [詳細資料] 窗格的 [ **成員** ] 索引標籤上，選取 [ **全部查看] 和 [管理成員**]，然後選取 [ **新增成員**]。

4. 搜尋或選取要新增的成員名稱。

5. 選取 [儲存]。

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>將群組新增至系統管理員中心的成員

1. 在系統管理中心中，移至 [作用中 [**使用者**](https://admin.microsoft.com/Adminportal/Home?#/users) ] 頁面。  

2. 按一下使用者。

3. 在詳細資料窗格的 [ **帳戶** ] 索引標籤上，選取 [ **管理群組**]。

4. 搜尋或選取您想要新增的群組名稱。

5. 選取 [儲存]。

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>從系統管理中心的群組中移除成員

> [!NOTE]
> 當您從私人群組中移除成員時，會需要5分鐘的時間，才能從群組中封鎖人員。

1. 在系統管理中心中，移至 [作用中 [**群組**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] 頁面。  

2. 按一下群組名稱。

3. 在詳細資料窗格的 [ **成員** ] 索引標籤上，選取 [ **全部查看] 和 [管理成員**]。

4. 選取您要移除的成員旁邊的 X。

5. 選取 [ **儲存** ] 以移除成員。

## <a name="manage-group-owner-status"></a>管理群組擁有者狀態

依預設，建立群組的人員即為群組擁有者。通常，基於備份支援或其他理由，群組將擁有多個擁有者。成員可以升級為擁有者狀態，而擁有者也可以降級為成員狀態。
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>在系統管理中心將成員提升為擁有者狀態

1. 在系統管理中心中，移至 [作用中 [**群組**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] 頁面。  

2. 按一下群組名稱。

3. 在詳細資料窗格的 [ **成員** ] 索引標籤上，選取 [ **全部查看] 和 [管理擁有** 者]。

4. 選取 [ **新增擁有** 者]。

5. 選取您要新增之成員名稱旁邊的核取方塊。

6. 選取 [ **儲存**]，然後 **關閉**]。

### <a name="remove-owner-status-in-the-admin-center"></a>在系統管理中心移除擁有者狀態

1. 在系統管理中心中，移至 [作用中 [**群組**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] 頁面。  

2. 按一下群組名稱。

3. 在詳細資料窗格的 [ **成員** ] 索引標籤上，選取 [ **全部查看] 和 [管理擁有** 者]。

4. 選取擁有者名稱旁邊的 X。

5. 選取 [儲存]。

## <a name="more-on-managing-membership"></a>成員資格的其他資訊

- [在 Azure Active Directory 中動態管理群組](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)：請參閱＜如何動態管理群組的成員資格？＞一節

- 若要將成百上千名使用者新增至群組，請使用 [Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks)。

- [指派新擁有者給孤立的群組](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>管理群組的相關文章

- [將通訊群組清單升級至 Outlook 中的 Microsoft 365 群組](../manage/upgrade-distribution-lists.md)

- [為什麼您應該將 Outlook 中的通訊群組清單升級成群組](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [在 Microsoft 365 群組中管理來賓存取](manage-guest-access-in-groups.md)

- [使用 PowerShell 管理 Microsoft 365 群組](../../enterprise/manage-microsoft-365-groups-with-powershell.md)：本文介紹重要 Cmdlet，並提供範例

- [Microsoft 365 群組命名原則](../../solutions/groups-naming-policy.md)