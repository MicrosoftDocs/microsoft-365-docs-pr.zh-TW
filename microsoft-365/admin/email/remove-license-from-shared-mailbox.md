---
title: 從共用信箱中移除授權
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: '從共用信箱中移除授權，將其指派給其他使用者。 '
ms.openlocfilehash: 1acd549936212db7f722355ed1f2518ff6bbac18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915683"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="f89f3-103">從共用信箱移除授權</span><span class="sxs-lookup"><span data-stu-id="f89f3-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f89f3-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="f89f3-104">The admin center is changing.</span></span> <span data-ttu-id="f89f3-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="f89f3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f89f3-106">共用信箱通常不需要授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="f89f3-107">請遵循下列指示，從共用信箱中移除授權，以便將其指派給使用者或傳回授權，這樣您就不會支付您不需要的授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="f89f3-108">下列案例中需要授權：</span><span class="sxs-lookup"><span data-stu-id="f89f3-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="f89f3-109">共用信箱使用的儲存空間超過 50 GB。</span><span class="sxs-lookup"><span data-stu-id="f89f3-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="f89f3-110">共用信箱使用就地封存。</span><span class="sxs-lookup"><span data-stu-id="f89f3-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="f89f3-111">共用信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f89f3-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="f89f3-112">共用信箱已指派 Microsoft Defender 授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="f89f3-113">移除授權</span><span class="sxs-lookup"><span data-stu-id="f89f3-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f89f3-114">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f89f3-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f89f3-115">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f89f3-116">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="f89f3-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="f89f3-117">選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="f89f3-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="f89f3-118">一個 [ **授權與應用程式** ] 索引標籤，展開 [ **授權** ]，然後取消選取您要移除之授權的方塊。</span><span class="sxs-lookup"><span data-stu-id="f89f3-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="f89f3-119">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="f89f3-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="f89f3-120">當您回到 [作用中 **使用者** ] 頁面時，共用信箱的狀態將會是 [未 **授權**]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f89f3-121">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-121">You're still paying for the license.</span></span> <span data-ttu-id="f89f3-122">若要停止付費，請 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="f89f3-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="f89f3-123">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f89f3-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f89f3-124">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f89f3-125">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="f89f3-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f89f3-126">選取 [共用信箱]，然後選取 [**產品授權**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f89f3-127">[ **產品授權** ] 頁面上，針對您想要移除的授權，將切換設定為 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f89f3-128">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-128">Select **Save**.</span></span>

5. <span data-ttu-id="f89f3-129">當您回到 [作用中 **使用者** ] 頁面時，共用信箱的狀態將會是 [未 **授權**]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f89f3-130">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-130">You're still paying for the license.</span></span> <span data-ttu-id="f89f3-131">若要停止付費，請 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="f89f3-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="f89f3-132">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f89f3-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f89f3-133">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f89f3-134">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="f89f3-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f89f3-135">選取 [共用信箱]，然後選取 [**產品授權**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f89f3-136">[ **產品授權** ] 頁面上，針對您想要移除的授權，將切換設定為 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f89f3-137">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-137">Select **Save**.</span></span>

5. <span data-ttu-id="f89f3-138">當您回到 [作用中 **使用者** ] 頁面時，共用信箱的狀態將會是 [未 **授權**]。</span><span class="sxs-lookup"><span data-stu-id="f89f3-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f89f3-139">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="f89f3-139">You're still paying for the license.</span></span> <span data-ttu-id="f89f3-140">若要停止付費，請 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="f89f3-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="f89f3-141">相關文章</span><span class="sxs-lookup"><span data-stu-id="f89f3-141">Related articles</span></span>

[<span data-ttu-id="f89f3-142">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="f89f3-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f89f3-143">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="f89f3-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f89f3-144">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="f89f3-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f89f3-145">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="f89f3-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f89f3-146">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="f89f3-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)