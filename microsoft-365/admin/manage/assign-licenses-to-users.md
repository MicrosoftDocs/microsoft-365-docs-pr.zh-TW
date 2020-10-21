---
title: 將授權指派給使用者
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何指派授權給使用者。
ms.date: 08/14/2020
ms.openlocfilehash: ec2f9ae2e580987266c636343a66d7c21138e4c3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645128"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="13c03-103">將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="13c03-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="13c03-104">The admin center is changing.</span></span> <span data-ttu-id="13c03-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="13c03-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="13c03-106">您可以在 **[作用中使用者]** 頁面或 **[授權]** 頁面上指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="13c03-107">所使用的方法取決於您要指派產品授權給特定使用者，還是要將使用者授權指派給特定產品。</span><span class="sxs-lookup"><span data-stu-id="13c03-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="13c03-108">[了解如何同時新增使用者和指派授權](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="13c03-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="13c03-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="13c03-109">Before you begin</span></span>

- <span data-ttu-id="13c03-110">您必須是全域、授權或使用者系統管理員，才能指派授權。</span><span class="sxs-lookup"><span data-stu-id="13c03-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="13c03-111">如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="13c03-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="13c03-112">您可以[使用 Office 365 PowerShell 指派授權給使用者帳戶](https://go.microsoft.com/fwlink/p/?linkid=850410)。</span><span class="sxs-lookup"><span data-stu-id="13c03-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="13c03-113">若要使用以群組為基礎的授權，請參閱[依據 Azure Active Directory 中的群組成員資格將授權指派給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="13c03-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="13c03-114">某些服務 (例如 Sway) 會自動指派給使用者，而不需要您個別指派。</span><span class="sxs-lookup"><span data-stu-id="13c03-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="13c03-115">使用授權頁面來指派授權給使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="13c03-116">使用 **[授權]** 頁面來指派授權時，您可以指派特定產品的授權給最多 20 位使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="13c03-117">在 **[授權]** 頁面上，您會看到您已訂閱的所有產品清單。</span><span class="sxs-lookup"><span data-stu-id="13c03-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="13c03-118">您也會看到每個產品的授權總數、已指派的授權數，以及有多少個可供使用。</span><span class="sxs-lookup"><span data-stu-id="13c03-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="13c03-119">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="13c03-120">選取產品。</span><span class="sxs-lookup"><span data-stu-id="13c03-120">Select a product.</span></span>
3. <span data-ttu-id="13c03-121">在產品詳細資料頁面上，選取 **[指派授權]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="13c03-122">在 **[指派授權給使用者]** 窗格中，開始輸入名稱，然後從結果中選擇，將它新增到清單中。</span><span class="sxs-lookup"><span data-stu-id="13c03-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="13c03-123">一次最多可以新增 20 個使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="13c03-124">選取 **[開啟或關閉應用程式與服務]** 以指派或移除特定項目的存取權。</span><span class="sxs-lookup"><span data-stu-id="13c03-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="13c03-125">完成時，請選取 [指派]\*\*\*\*，然後選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13c03-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="13c03-126">如果發生衝突，則會顯示訊息，告知您發生什麼問題，以及如何修正。</span><span class="sxs-lookup"><span data-stu-id="13c03-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="13c03-127">例如，如果您選取的授權包含發生衝突的服務，則錯誤訊息會指出，請檢查每個授權所包含的服務，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="13c03-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="13c03-128">變更使用者可以存取的應用程式與服務</span><span class="sxs-lookup"><span data-stu-id="13c03-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="13c03-129">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="13c03-130">在 **[授權]** 頁面上，選取特定使用者的列。</span><span class="sxs-lookup"><span data-stu-id="13c03-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="13c03-131">在右窗格中，選取或取消選取您要授與存取權或移除存取權的應用程式與服務。</span><span class="sxs-lookup"><span data-stu-id="13c03-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="13c03-132">完成時，請選取 **[儲存]**，然後選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="13c03-133">使用作用中使用者頁面來指派授權</span><span class="sxs-lookup"><span data-stu-id="13c03-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="13c03-134">使用 **[作用中使用者]** 頁面來指派授權時，您會將使用者授權指派給產品。</span><span class="sxs-lookup"><span data-stu-id="13c03-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="13c03-135">將授權指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="13c03-136">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="13c03-137">選取您要指派授權的使用者名稱旁的圓圈。</span><span class="sxs-lookup"><span data-stu-id="13c03-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="13c03-138">在頂端，選取 **[更多選項(...)]**，然後選取 **[管理產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="13c03-139">在 **[管理產品授權]** 窗格中，選取 **[新增到現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="13c03-140">在 **[新增到現有產品]** 窗格中，針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="13c03-141">根據預設，與這些授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="13c03-142">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="13c03-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="13c03-143">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="13c03-144">在窗格底部，選取 **[新增]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="13c03-145">將授權指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="13c03-146">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="13c03-147">選取您要指派授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="13c03-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="13c03-148">在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="13c03-149">在 **[指派產品]** 窗格中，選取 **[新增到現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="13c03-150">針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="13c03-151">根據預設，與這些授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="13c03-152">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="13c03-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="13c03-153">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="13c03-154">在 **[新增到現有產品]** 窗格底部，選取 **[新增]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="13c03-155">將授權指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="13c03-156">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="13c03-157">選取您要指派授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="13c03-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="13c03-158">在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="13c03-159">在 **[指派產品]** 窗格中，選取 **[新增到現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="13c03-160">針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="13c03-161">根據預設，與這些授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="13c03-162">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="13c03-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="13c03-163">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="13c03-164">在 **[新增到現有產品]** 窗格底部，選取 **[新增]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="13c03-165">將授權指派給一位使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="13c03-166">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="13c03-167">選取您要指派授權的使用者列。</span><span class="sxs-lookup"><span data-stu-id="13c03-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="13c03-168">在右窗格中，選取 **[授權與應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="13c03-169">展開 **[授權]** 區段，選取您要指派之授權的方塊，然後選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="13c03-170">將授權指派給一位使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="13c03-171">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="13c03-172">選取您要指派授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="13c03-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="13c03-173">在右側窗格的 **[產品授權]** 列中，選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="13c03-174">針對您要指派授權的使用者，在 **[產品授權]** 窗格中，將開關切換到 **[開啟]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="13c03-175">根據預設，與該授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="13c03-176">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="13c03-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="13c03-177">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="13c03-178">在 **[產品授權]** 窗格底部，選擇 **[儲存]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="13c03-179">將授權指派給一位使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="13c03-180">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="13c03-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="13c03-181">選取您要指派授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="13c03-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="13c03-182">在右側窗格的 **[產品授權]** 列中，選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="13c03-183">針對您要指派授權的使用者，在 **[產品授權]** 窗格中，將開關切換到 **[開啟]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="13c03-184">根據預設，與該授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="13c03-185">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="13c03-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="13c03-186">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="13c03-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="13c03-187">在 **[產品授權]** 窗格底部，選擇 **[儲存]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="13c03-188">指派授權給來賓使用者</span><span class="sxs-lookup"><span data-stu-id="13c03-188">Assign a license to a guest user</span></span>

<span data-ttu-id="13c03-189">您可以在 Azure Active Directory 系統管理中心中邀請來賓使用者來與您的組織共同作業。</span><span class="sxs-lookup"><span data-stu-id="13c03-189">You can invite guest users to collaborate with your organization in Azure Active directory admin center.</span></span> <span data-ttu-id="13c03-190">若要進一步了解來賓使用者，請參閱[什麼是 Azure Active Directory B2B 中的來賓使用者存取權？](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="13c03-190">To learn about guess users, see [What is guest user access in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span></span> <span data-ttu-id="13c03-191">如果您沒有任何來賓使用者，請參閱[快速入門：在 Azure 入口網站中將來賓使用者新增至您的目錄](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。</span><span class="sxs-lookup"><span data-stu-id="13c03-191">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13c03-192">您必須是全域系統管理員才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="13c03-192">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="13c03-193">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 系統管理中心</a></span><span class="sxs-lookup"><span data-stu-id="13c03-193">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="13c03-194">在功能窗格中，選取 [使用者 **]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-194">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="13c03-195">在 [使用者 | 所有使用者 (預覽)**]** 頁面上，選取 [新增篩選 **]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-195">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="13c03-196">在 [挑選欄位 **]** 功能表中，選擇 [使用者類型 **]**，然後選取 [套用 **]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-196">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="13c03-197">在下一個功能表中，選取 [來賓 **]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-197">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="13c03-198">在結果清單中，選取需要授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="13c03-198">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="13c03-199">在 [管理 **]** 下，選取 [授權 **]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-199">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="13c03-200">選取 [作業 **]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-200">Select **Assignments**.</span></span>
9. <span data-ttu-id="13c03-201">在 [更新授權指派 **]** 頁面上，選取您要為其指派授權的產品。</span><span class="sxs-lookup"><span data-stu-id="13c03-201">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="13c03-202">在右側，除您不要來賓使用者可存取的任何服務的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="13c03-202">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="13c03-203">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="13c03-203">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13c03-204">後續步驟</span><span class="sxs-lookup"><span data-stu-id="13c03-204">Next steps</span></span>

<span data-ttu-id="13c03-205">如果您的使用者尚未安裝 Office 應用程式，則可以與您的使用者分享[員工快速入門手冊](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，以設定相關項目，例如[如何在 PC 或 Mac 上下載並安裝 Microsoft 365 或 Office 2019](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及[如何在行動裝置上設定 Office 應用程式和電子郵件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="13c03-205">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="13c03-206">相關內容</span><span class="sxs-lookup"><span data-stu-id="13c03-206">Related content</span></span>

<span data-ttu-id="13c03-207">[了解訂閱與授權](../../commerce/licenses/subscriptions-and-licenses.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="13c03-207">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="13c03-208">[取消指派給使用者的授權](remove-licenses-from-users.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="13c03-208">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="13c03-209">[購買或移除訂閱授權](../../commerce/licenses/buy-licenses.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="13c03-209">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>