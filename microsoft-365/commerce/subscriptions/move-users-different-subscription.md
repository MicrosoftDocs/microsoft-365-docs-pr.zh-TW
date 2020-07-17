---
title: 將使用者移至其他訂閱
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
description: 瞭解如何在訂閱間移動使用者。
ms.date: 07/01/2020
ms.openlocfilehash: d110ee7c49befa34f5a2cd3bb44dc114aec25b62
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016539"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="cde0f-103">將使用者移至其他訂閱</span><span class="sxs-lookup"><span data-stu-id="cde0f-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cde0f-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="cde0f-104">The admin center is changing.</span></span> <span data-ttu-id="cde0f-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="cde0f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="cde0f-106">如果您有多個訂閱，讓使用者擁有一個訂閱的授權，但想要將其移至另一個訂閱，您可以將現有的授權取代為其他訂閱。</span><span class="sxs-lookup"><span data-stu-id="cde0f-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cde0f-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="cde0f-107">Before you begin</span></span>

<span data-ttu-id="cde0f-108">您必須是全域、授權或使用者系統管理員，才可指派授權。</span><span class="sxs-lookup"><span data-stu-id="cde0f-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="cde0f-109">如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="cde0f-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="cde0f-110">將使用者移至其他訂閱</span><span class="sxs-lookup"><span data-stu-id="cde0f-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cde0f-111">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="cde0f-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cde0f-112">選取您要取代現有授權的使用者名稱旁的圓圈。</span><span class="sxs-lookup"><span data-stu-id="cde0f-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="cde0f-113">在頂端，選取 **[更多選項(...)]**，然後選取 **[管理產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="cde0f-114">在 **[管理產品授權]** 窗格中，選取 **[取得現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="cde0f-115">針對您想要指派給這些使用者的授權，切換到 [**開啟**] 位置。</span><span class="sxs-lookup"><span data-stu-id="cde0f-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="cde0f-116">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="cde0f-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="cde0f-117">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="cde0f-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="cde0f-118">將移除任何先前指派給所選使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="cde0f-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="cde0f-119">在 **[取代現有產品]** 窗格中，選取 **[取代]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cde0f-120">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="cde0f-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cde0f-121">選取您要取代現有授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="cde0f-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="cde0f-122">在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="cde0f-123">在 **[指派產品]** 窗格中，選取 **[取代現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="cde0f-124">針對您想要指派給這些使用者的授權，切換到 [**開啟**] 位置。</span><span class="sxs-lookup"><span data-stu-id="cde0f-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="cde0f-125">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="cde0f-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="cde0f-126">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="cde0f-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="cde0f-127">將移除任何先前指派給所選使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="cde0f-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="cde0f-128">在 **[取代現有產品]** 窗格的底部，選取 **[取代]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cde0f-129">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="cde0f-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cde0f-130">選取您要取代現有授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="cde0f-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="cde0f-131">在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="cde0f-132">在 **[指派產品]** 窗格中，選取 **[取代現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="cde0f-133">針對您想要指派給這些使用者的授權，切換到 [**開啟**] 位置。</span><span class="sxs-lookup"><span data-stu-id="cde0f-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="cde0f-134">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="cde0f-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="cde0f-135">針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。</span><span class="sxs-lookup"><span data-stu-id="cde0f-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="cde0f-136">將移除任何先前指派給所選使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="cde0f-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="cde0f-137">在 **[取代現有產品]** 窗格的底部，選取 **[取代]** \> **[關閉]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="cde0f-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="cde0f-138">後續步驟</span><span class="sxs-lookup"><span data-stu-id="cde0f-138">Next steps</span></span>

<span data-ttu-id="cde0f-139">如果您不想將[未使用的授權重新指派給其他使用者](../../managed-desktop/get-started/assign-licenses.md)，請考慮[從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)，這樣您就不會支付超過您所需的授權數量。</span><span class="sxs-lookup"><span data-stu-id="cde0f-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="cde0f-140">相關內容</span><span class="sxs-lookup"><span data-stu-id="cde0f-140">Related content</span></span>

<span data-ttu-id="cde0f-141">[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="cde0f-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="cde0f-142">[從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="cde0f-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="cde0f-143">[手動變更方案](change-plans-manually.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="cde0f-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="cde0f-144">[瞭解 Microsoft 365 for business 中的訂閱與授權](../licenses/subscriptions-and-licenses.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="cde0f-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="cde0f-145">[購買另一部 Microsoft 365 for business 訂閱](../buy-another-subscription.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="cde0f-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>