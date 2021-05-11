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
ms.openlocfilehash: 87bb8f6fe0e85fc4ac832f2bc4ad746e8d6386eb
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310989"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="7c2d2-103">取消指派給使用者的授權</span><span class="sxs-lookup"><span data-stu-id="7c2d2-103">Unassign licenses from users</span></span>

<span data-ttu-id="7c2d2-104">您可以從 [作用中 **使用者** ] 頁面或 [ **授權** ] 頁面上的使用者取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="7c2d2-105">您所使用的方法，取決於您是否要從特定使用者取消指派產品授權，或從特定產品取消指派使用者授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="7c2d2-106">系統管理員無法指派或取消指派貴組織中的使用者所購買的自助購買訂閱授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="7c2d2-107">您可以 [接管自助購買訂閱](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)，然後指派或取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7c2d2-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="7c2d2-108">Before you begin</span></span>

- <span data-ttu-id="7c2d2-109">您必須是全域授權，使用者管理員才能取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="7c2d2-110">如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="7c2d2-111">您可以[使用 Office 365 PowerShell 移除使用者帳戶中的授權](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="7c2d2-112">您也可以刪除已獲指派授權的 [使用者帳戶](../add-users/delete-a-user.md) ，讓其他使用者可以使用授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="7c2d2-113">當您刪除使用者帳戶時，他們的授權會立即可指派給其他人。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="7c2d2-114">使用授權頁面以取消指派授權</span><span class="sxs-lookup"><span data-stu-id="7c2d2-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="7c2d2-115">當您使用 [ **授權** ] 頁面取消指派授權時，您會取消指派最多20個使用者之特定產品的授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7c2d2-116">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7c2d2-117">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[系統管理員]</a>，前往 **[帳單]** > **[授權]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7c2d2-118">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[系統管理員]</a>，前往 **[帳單]** > **[授權]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="7c2d2-119">選取您要指派授權的產品。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="7c2d2-120">選取您要指派授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="7c2d2-121">選取 [未 **指派的授權**]。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="7c2d2-122">在 [未 **指派的授權** ] 方塊中，選取 [ **取消指派**]。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="7c2d2-123">使用 [作用中使用者] 頁面以取消指派授權</span><span class="sxs-lookup"><span data-stu-id="7c2d2-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="7c2d2-124">當您使用 [作用中 **使用者** ] 頁面取消指派授權時，您會取消指派使用者的產品授權。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="7c2d2-125">從某位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="7c2d2-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="7c2d2-126">在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7c2d2-127">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[系統管理中心]</a> 中，移至 **[帳單]** > **[作用中使用者]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7c2d2-128">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">系統管理中心</a>，移至 **[帳單]** > **[作用中使用者]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="7c2d2-129">選取您要取消指派授權之使用者的列。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="7c2d2-130">在右窗格中，選取 **[授權與應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="7c2d2-131">展開 [ **授權** ] 區段，然後清除您要取消指派之授權的方塊，然後選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="7c2d2-132">從多位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="7c2d2-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7c2d2-133">在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7c2d2-134">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[系統管理中心]</a> 中，移至 **[帳單]** > **[作用中使用者]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7c2d2-135">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">系統管理中心</a>，移至 **[帳單]** > **[作用中使用者]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="7c2d2-136">選取您要取消指派授權的使用者名稱旁邊的圓圈。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="7c2d2-137">在頂端，選取 **[更多選項(...)]**，然後選取 **[管理產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="7c2d2-138">在 **[管理產品授權]** 窗格中，選取 **[取得現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="7c2d2-139">在 [ **取代現有產品** ] 窗格的底部，選取 [ **從選取的使用者移除所有產品授權** ] 核取方塊，然後選取 [ **取代** \> **Close**]。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="7c2d2-140">當您移除授權時，使用者的資料會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="7c2d2-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="7c2d2-141">從使用者移除授權時，與該帳戶相關聯的資料會保留30天。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="7c2d2-142">30天的寬限期過後，便會刪除資料，而且無法復原。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="7c2d2-143">除非使用者從 Microsoft 365 系統管理中心中刪除，或是透過 Active Directory 同步處理移除，否則不會刪除儲存在商務用 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="7c2d2-144">如需詳細資訊，請參閱[OneDrive 保留和刪除](/onedrive/retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="7c2d2-145">移除授權後，使用者的信箱就無法再使用「內容搜尋」（如「內容搜尋」）或 Advanced eDiscovery 等 eDiscovery 工具進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content search or Advanced eDiscovery.</span></span> <span data-ttu-id="7c2d2-146">如需詳細資訊，請參閱 [Content search reference](../../compliance/content-search-reference.md#searching-disconnected-or-de-licensed-mailboxes)中的「搜尋中斷連線或已取消授權的信箱」。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content search reference](../../compliance/content-search-reference.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="7c2d2-147">如果您有 Enterprise 訂閱（如 Office 365 企業版 E3），Exchange Online 可讓您使用非使用中的[信箱](../../compliance/inactive-mailboxes-in-office-365.md)來保留已刪除之使用者帳戶的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="7c2d2-148">如需詳細資訊，請參閱[在 Exchange Online 中建立及管理非](../../compliance/create-and-manage-inactive-mailboxes.md)使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="7c2d2-149">若要瞭解如何在移除授權後封鎖使用者對 Microsoft 365 資料的存取，以及如何在以後存取資料，請參閱[移除離職員工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="7c2d2-150">如果您移除使用者的授權，但仍已安裝 Office 應用程式，他們會在使用 Office 應用程式時，看到[Office 中未授權的產品和啟用錯誤](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7c2d2-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7c2d2-151">Next steps</span></span>

<span data-ttu-id="7c2d2-152">如果您不想將 [未使用的授權重新指派給其他使用者](../../managed-desktop/get-started/assign-licenses.md)，請考慮 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md) ，這樣您就不會支付超過您所需的授權數量。</span><span class="sxs-lookup"><span data-stu-id="7c2d2-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="7c2d2-153">相關內容</span><span class="sxs-lookup"><span data-stu-id="7c2d2-153">Related content</span></span>

<span data-ttu-id="7c2d2-154">[從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="7c2d2-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="7c2d2-155">[將授權指派給使用者](assign-licenses-to-users.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="7c2d2-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="7c2d2-156">[瞭解商務 (文章的 Microsoft 365 訂閱和授權](../../commerce/licenses/subscriptions-and-licenses.md)) </span><span class="sxs-lookup"><span data-stu-id="7c2d2-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>