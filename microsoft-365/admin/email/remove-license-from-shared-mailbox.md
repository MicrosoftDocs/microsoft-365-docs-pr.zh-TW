---
title: 從共用信箱中移除授權
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
ms.openlocfilehash: 401b334efeccf6d7c4caca20be3cc9767b2df945
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432216"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="b1a73-103">從共用信箱移除授權</span><span class="sxs-lookup"><span data-stu-id="b1a73-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b1a73-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="b1a73-104">The admin center is changing.</span></span> <span data-ttu-id="b1a73-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="b1a73-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b1a73-106">共用信箱通常不需要授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="b1a73-107">請遵循下列指示，從共用信箱中移除授權，以便將其指派給使用者或傳回授權，這樣您就不會支付您不需要的授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="b1a73-108">下列案例中需要授權：</span><span class="sxs-lookup"><span data-stu-id="b1a73-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="b1a73-109">共用信箱使用的儲存空間超過 50 GB。</span><span class="sxs-lookup"><span data-stu-id="b1a73-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="b1a73-110">共用信箱使用就地封存。</span><span class="sxs-lookup"><span data-stu-id="b1a73-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="b1a73-111">共用信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="b1a73-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="b1a73-112">移除授權</span><span class="sxs-lookup"><span data-stu-id="b1a73-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b1a73-113">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b1a73-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1a73-114">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b1a73-115">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="b1a73-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="b1a73-116">選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b1a73-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="b1a73-117">一個 [**授權與應用程式**] 索引標籤，展開 [**授權**]，然後取消選取您要移除之授權的方塊。</span><span class="sxs-lookup"><span data-stu-id="b1a73-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="b1a73-118">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="b1a73-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="b1a73-119">當您回到 [作用中**使用者**] 頁面時，共用信箱的狀態將會是 [未**授權**]。</span><span class="sxs-lookup"><span data-stu-id="b1a73-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b1a73-120">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-120">You're still paying for the license.</span></span> <span data-ttu-id="b1a73-121">若要停止付費，請[從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="b1a73-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b1a73-122">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b1a73-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1a73-123">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b1a73-124">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="b1a73-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="b1a73-125">選取 [共用信箱]，然後選取 [**產品授權**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b1a73-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="b1a73-126">[**產品授權**] 頁面上，針對您想要移除的授權，將切換設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="b1a73-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="b1a73-127">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b1a73-127">Select **Save**.</span></span>

5. <span data-ttu-id="b1a73-128">當您回到 [作用中**使用者**] 頁面時，共用信箱的狀態將會是 [未**授權**]。</span><span class="sxs-lookup"><span data-stu-id="b1a73-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b1a73-129">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-129">You're still paying for the license.</span></span> <span data-ttu-id="b1a73-130">若要停止付費，請[從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="b1a73-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b1a73-131">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b1a73-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1a73-132">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b1a73-133">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="b1a73-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="b1a73-134">選取 [共用信箱]，然後選取 [**產品授權**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b1a73-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="b1a73-135">[**產品授權**] 頁面上，針對您想要移除的授權，將切換設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="b1a73-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="b1a73-136">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b1a73-136">Select **Save**.</span></span>

5. <span data-ttu-id="b1a73-137">當您回到 [作用中**使用者**] 頁面時，共用信箱的狀態將會是 [未**授權**]。</span><span class="sxs-lookup"><span data-stu-id="b1a73-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b1a73-138">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="b1a73-138">You're still paying for the license.</span></span> <span data-ttu-id="b1a73-139">若要停止付費，請[從您的訂閱中移除授權](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="b1a73-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="b1a73-140">相關文章</span><span class="sxs-lookup"><span data-stu-id="b1a73-140">Related articles</span></span>

[<span data-ttu-id="b1a73-141">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="b1a73-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="b1a73-142">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="b1a73-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="b1a73-143">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="b1a73-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="b1a73-144">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="b1a73-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="b1a73-145">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="b1a73-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
