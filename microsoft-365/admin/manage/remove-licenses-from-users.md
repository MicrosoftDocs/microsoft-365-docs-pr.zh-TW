---
title: 取消指派給使用者的授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- manage_licenses
- okr_smb
- commerce
search.appverid:
- MET150
description: 瞭解如何從使用者帳戶取消指派授權。
ms.date: 07/01/2020
ms.openlocfilehash: 550136c2cfa8d81a31e52a4313dc9c967a55d56e
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398190"
---
# <a name="unassign-licenses-from-users"></a>取消指派給使用者的授權

您可以從 [作用中 **使用者** ] 頁面或 [ **授權** ] 頁面上的使用者取消指派授權。 您所使用的方法，取決於您是否要從特定使用者取消指派產品授權，或從特定產品取消指派使用者授權。

> [!NOTE]
> 身為系統管理員，您無法指派或取消指派組織中使用者購買之自助購買訂閱的授權。 您可以 [接管自助購買訂閱](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)，然後指派或取消指派授權。

## <a name="before-you-begin"></a>開始之前

- 您必須是全域授權，使用者管理員才能取消指派授權。 如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](../add-users/about-admin-roles.md)。
- 您可以[使用 Office 365 PowerShell 移除使用者帳戶中的授權](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)。
- 您也可以刪除已獲指派授權的 [使用者帳戶](../add-users/delete-a-user.md) ，讓其他使用者可以使用授權。 當您刪除使用者帳戶時，他們的授權會立即可指派給其他人。

## <a name="use-the-licenses-page-to-unassign-licenses"></a>使用授權頁面以取消指派授權

當您使用 [ **授權** ] 頁面取消指派授權時，您會取消指派最多20個使用者之特定產品的授權。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** > **授權** ] 頁面。
::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** > **授權** ] 頁面。

::: moniker-end

2. 選取您要指派授權的產品。
3. 選取您要指派授權的使用者。
4. 選取 [未 **指派的授權**]。
5. 在 [未 **指派的授權** ] 方塊中，選取 [ **取消指派**]。

## <a name="use-the-active-users-page-to-unassign-licenses"></a>使用 [作用中使用者] 頁面以取消指派授權

當您使用 [作用中 **使用者** ] 頁面取消指派授權時，您會取消指派使用者的產品授權。

### <a name="unassign-licenses-from-one-user"></a>從某位使用者取消指派授權
  
::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** 作用中 > **使用者** ] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** 作用中 > **使用者** ] 頁面。

::: moniker-end

2. 選取您要取消指派授權之使用者的列。
3. 在右窗格中，選取 **[授權與應用程式]**。
4. 展開 [ **授權** ] 區段，然後清除您要取消指派之授權的方塊，然後選取 [ **儲存變更**]。

###  <a name="unassign-licenses-from-multiple-users"></a>從多位使用者取消指派授權

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** 作用中 > **使用者** ] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** 作用中 > **使用者** ] 頁面。

::: moniker-end

2. 選取您要取消指派授權的使用者名稱旁邊的圓圈。
3. 在頂端，選取 **[更多選項(...)]**，然後選取 **[管理產品授權]**。
4. 在 **[管理產品授權]** 窗格中，選取 **[取得現有產品授權指派]** \> **[下一步]**。
5. 在 [ **取代現有產品** ] 窗格的底部，選取 [ **從選取的使用者移除所有產品授權** ] 核取方塊，然後選取 [ **取代** \> **Close**]。

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>當您移除授權時，使用者的資料會發生什麼事？

- 從使用者移除授權時，與該帳戶相關聯的資料會保留30天。 30天的寬限期過後，便會刪除資料，而且無法復原。
- 在商務用 OneDrive 中儲存的檔案不會被刪除，除非使用者從 Microsoft 365 系統管理中心中刪除或透過 Active Directory 同步處理移除。 如需詳細資訊，請參閱 [OneDrive 保留和刪除](/onedrive/retention-and-deletion)。
- 移除授權時，使用者的信箱將無法再使用「內容搜尋」或「高級 eDiscovery」等 eDiscovery 工具進行搜尋。 如需詳細資訊，請參閱 [Microsoft 365 中內容搜尋](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes)中的「搜尋中斷連線或已取消授權的信箱」。
- 如果您有企業訂閱（如 Office 365 企業版 E3），Exchange Online 可讓您使用非使用中的 [信箱](../../compliance/inactive-mailboxes-in-office-365.md)來保留已刪除之使用者帳戶的信箱資料。 如需詳細資訊，請參閱 [在 Exchange Online 中建立及管理非](../../compliance/create-and-manage-inactive-mailboxes.md)使用中的信箱。
- 若要瞭解如何在移除授權後封鎖使用者對 Microsoft 365 資料的存取，以及如何在以後存取資料，請參閱 [移除離職員工](../add-users/remove-former-employee.md)。
- 如果您移除使用者的授權，但他們仍已安裝 Office 應用程式，他們會在使用 Office app 時，看到 [office 中未授權的產品和啟用錯誤](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 。

## <a name="next-steps"></a>後續步驟

如果您不想將 [未使用的授權重新指派給其他使用者](../../managed-desktop/get-started/assign-licenses.md)，請考慮 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md) ，這樣您就不會支付超過您所需的授權數量。

## <a name="related-content"></a>相關內容

[從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md) (文章) \
[將授權指派給使用者](assign-licenses-to-users.md) (文章)\
[瞭解 Microsoft 365 for business 中的訂閱與授權](../../commerce/licenses/subscriptions-and-licenses.md) (文章) 