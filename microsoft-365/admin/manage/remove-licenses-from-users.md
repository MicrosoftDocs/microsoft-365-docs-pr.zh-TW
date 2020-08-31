---
title: 取消指派給使用者的授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 瞭解如何從使用者帳戶取消指派授權。
ms.date: 07/01/2020
ms.openlocfilehash: 4441fd253c4cf5304562900bf31869eb4e0f21ff
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306536"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="f55b2-103">取消指派給使用者的授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f55b2-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="f55b2-104">The admin center is changing.</span></span> <span data-ttu-id="f55b2-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="f55b2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="f55b2-106">您可以從 [作用中 **使用者** ] 頁面或 [ **授權** ] 頁面上的使用者取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="f55b2-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="f55b2-107">您所使用的方法，取決於您是否要從特定使用者取消指派產品授權，或從特定產品取消指派使用者授權。</span><span class="sxs-lookup"><span data-stu-id="f55b2-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="f55b2-108">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="f55b2-108">Before you begin</span></span>

- <span data-ttu-id="f55b2-109">您必須是全域授權，使用者管理員才能取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="f55b2-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="f55b2-110">如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f55b2-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="f55b2-111">您可以[使用 Office 365 PowerShell 移除使用者帳戶中的授權](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f55b2-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span></span>
- <span data-ttu-id="f55b2-112">您也可以刪除已獲指派授權的 [使用者帳戶](../add-users/delete-a-user.md) ，讓其他使用者可以使用授權。</span><span class="sxs-lookup"><span data-stu-id="f55b2-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="f55b2-113">當您刪除使用者帳戶時，他們的授權會立即可指派給其他人。</span><span class="sxs-lookup"><span data-stu-id="f55b2-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="f55b2-114">使用授權頁面以取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="f55b2-115">當您使用 [ **授權** ] 頁面取消指派授權時，您會取消指派最多20個使用者之特定產品的授權。</span><span class="sxs-lookup"><span data-stu-id="f55b2-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="f55b2-116">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f55b2-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="f55b2-117">選取您要指派授權的產品。</span><span class="sxs-lookup"><span data-stu-id="f55b2-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="f55b2-118">選取您要指派授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="f55b2-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="f55b2-119">選取 [未 **指派的授權**]。</span><span class="sxs-lookup"><span data-stu-id="f55b2-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="f55b2-120">在 [未 **指派的授權** ] 方塊中，選取 [ **取消指派**]。</span><span class="sxs-lookup"><span data-stu-id="f55b2-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="f55b2-121">使用 [作用中使用者] 頁面以取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="f55b2-122">當您使用 [作用中 **使用者** ] 頁面取消指派授權時，您會取消指派使用者的產品授權。</span><span class="sxs-lookup"><span data-stu-id="f55b2-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="f55b2-123">從某位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="f55b2-124">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f55b2-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f55b2-125">選取您要取消指派授權之使用者的列。</span><span class="sxs-lookup"><span data-stu-id="f55b2-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="f55b2-126">在右窗格中，選取 **[授權與應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="f55b2-127">展開 [ **授權** ] 區段，然後清除您要取消指派之授權的方塊，然後選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="f55b2-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="f55b2-128">從某位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="f55b2-129">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f55b2-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f55b2-130">挑選您要取消指派授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="f55b2-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="f55b2-131">在右側的 [ **產品授權** ] 列中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="f55b2-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="f55b2-132">在 [ **產品授權** ] 窗格中，針對您想要取消指派給使用者的授權，將開關切換到 [ **關閉** ] 位置。</span><span class="sxs-lookup"><span data-stu-id="f55b2-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="f55b2-133">例如，如果您關閉 Office 365 企業版 E3 授權，它會在該使用者的授權和該授權下 unassigns 所有服務。</span><span class="sxs-lookup"><span data-stu-id="f55b2-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="f55b2-134">在 **[產品授權]** 窗格底部，選擇 **[儲存]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="f55b2-135">從某位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="f55b2-136">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f55b2-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f55b2-137">挑選您要取消指派授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="f55b2-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="f55b2-138">在右側的 [ **產品授權** ] 列中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="f55b2-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="f55b2-139">在 [ **產品授權** ] 窗格中，針對您想要取消指派給使用者的授權，將開關切換到 [ **關閉** ] 位置。</span><span class="sxs-lookup"><span data-stu-id="f55b2-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="f55b2-140">例如，如果您關閉 Office 365 企業版 E3 授權，它會在該使用者的授權和該授權下 unassigns 所有服務。</span><span class="sxs-lookup"><span data-stu-id="f55b2-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="f55b2-141">在 **[產品授權]** 窗格底部，選擇 **[儲存]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="f55b2-142">從多位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="f55b2-143">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f55b2-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f55b2-144">選取您要取消指派授權的使用者名稱旁邊的圓圈。</span><span class="sxs-lookup"><span data-stu-id="f55b2-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="f55b2-145">在頂端，選取 **[更多選項(...)]**，然後選取 **[管理產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="f55b2-146">在 **[管理產品授權]** 窗格中，選取 **[取得現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f55b2-147">在 [ **取代現有產品** ] 窗格的底部，選取 [ **從選取的使用者移除所有產品授權** ] 核取方塊，然後選取 [ **取代** \> **Close**]。</span><span class="sxs-lookup"><span data-stu-id="f55b2-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="f55b2-148">從多位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="f55b2-149">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f55b2-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f55b2-150">選取您要取消指派所有授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="f55b2-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="f55b2-151">在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="f55b2-152">在 [ **取代現有產品** ] 窗格中，選取 [ **取代現有產品授權指派** \> **] [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f55b2-153">在 [ **取代現有產品** ] 窗格的底部，選取 [ **從選取的使用者移除所有產品授權** ] 核取方塊，然後選取 [ **取代** \> **關閉**] [關閉] \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="f55b2-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="f55b2-154">從多位使用者取消指派授權</span><span class="sxs-lookup"><span data-stu-id="f55b2-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="f55b2-155">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f55b2-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f55b2-156">選取您要取消指派所有授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="f55b2-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="f55b2-157">在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="f55b2-158">在 [ **取代現有產品** ] 窗格中，選取 [ **取代現有產品授權指派** \> **] [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f55b2-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="f55b2-159">在 [ **取代現有產品** ] 窗格的底部，選取 [ **從選取的使用者移除所有產品授權** ] 核取方塊，然後選取 [ **取代** \> **關閉**] [關閉] \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="f55b2-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="f55b2-160">當您移除授權時，使用者的資料會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="f55b2-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="f55b2-161">從使用者移除授權時，與該帳戶相關聯的資料會保留30天。</span><span class="sxs-lookup"><span data-stu-id="f55b2-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="f55b2-162">30天的寬限期過後，便會刪除資料，而且無法復原。</span><span class="sxs-lookup"><span data-stu-id="f55b2-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="f55b2-163">在商務用 OneDrive 中儲存的檔案不會被刪除，除非使用者從 Microsoft 365 系統管理中心中刪除或透過 Active Directory 同步處理移除。</span><span class="sxs-lookup"><span data-stu-id="f55b2-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="f55b2-164">如需詳細資訊，請參閱 [OneDrive 保留和刪除](https://docs.microsoft.com/onedrive/retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="f55b2-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="f55b2-165">移除授權時，使用者的信箱將無法再使用「內容搜尋」或「高級 eDiscovery」等 eDiscovery 工具進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="f55b2-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="f55b2-166">如需詳細資訊，請參閱 [Microsoft 365 中內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)中的「搜尋中斷連線或已取消授權的信箱」。</span><span class="sxs-lookup"><span data-stu-id="f55b2-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="f55b2-167">如果您有企業訂閱（如 Office 365 企業版 E3），Exchange Online 可讓您使用非使用中的 [信箱](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)來保留已刪除之使用者帳戶的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="f55b2-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="f55b2-168">如需詳細資訊，請參閱 [在 Exchange Online 中建立及管理非](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f55b2-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="f55b2-169">若要瞭解如何在移除授權後封鎖使用者對 Microsoft 365 資料的存取，以及如何在以後存取資料，請參閱 [移除離職員工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="f55b2-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="f55b2-170">如果您移除使用者的授權，但他們仍已安裝 Office 應用程式，他們會在使用 Office app 時，看到 [office 中未授權的產品和啟用錯誤](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) 。</span><span class="sxs-lookup"><span data-stu-id="f55b2-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f55b2-171">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f55b2-171">Next steps</span></span>

<span data-ttu-id="f55b2-172">如果您不想將 [未使用的授權重新指派給其他使用者](../../managed-desktop/get-started/assign-licenses.md)，請考慮 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md) ，這樣您就不會支付超過您所需的授權數量。</span><span class="sxs-lookup"><span data-stu-id="f55b2-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="f55b2-173">相關內容</span><span class="sxs-lookup"><span data-stu-id="f55b2-173">Related content</span></span>

<span data-ttu-id="f55b2-174">[從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="f55b2-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="f55b2-175"> (篇文章) \[中指派授權給使用者](assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="f55b2-175">[Assign licenses to users](assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="f55b2-176">[瞭解 Microsoft 365 for business 中的訂閱與授權](../../commerce/licenses/subscriptions-and-licenses.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="f55b2-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>