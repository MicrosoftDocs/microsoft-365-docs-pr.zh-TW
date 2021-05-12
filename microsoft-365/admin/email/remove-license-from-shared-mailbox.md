---
title: 從共用信箱中移除授權
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: '從共用信箱中移除授權，將其指派給其他使用者。 '
ms.openlocfilehash: 2d0e6e6b1d6222bea80265bf6cc008e21ac3239c
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332651"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="5056f-103">從共用信箱移除授權</span><span class="sxs-lookup"><span data-stu-id="5056f-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="5056f-104">共用信箱通常不需要授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="5056f-105">請遵循下列指示，從共用信箱中移除授權，以便將其指派給使用者或傳回授權，這樣您就不會支付您不需要的授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="5056f-106">下列案例中需要授權：</span><span class="sxs-lookup"><span data-stu-id="5056f-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="5056f-107">共用信箱使用的儲存空間超過 50 GB。</span><span class="sxs-lookup"><span data-stu-id="5056f-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="5056f-108">共用信箱使用就地封存。</span><span class="sxs-lookup"><span data-stu-id="5056f-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="5056f-109">共用信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="5056f-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="5056f-110">共用信箱已指派 Microsoft Defender 授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="5056f-111">移除授權</span><span class="sxs-lookup"><span data-stu-id="5056f-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5056f-112">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="5056f-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5056f-113">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-113">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="5056f-114">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="5056f-114">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="5056f-115">選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="5056f-115">Select the shared mailbox.</span></span>

3. <span data-ttu-id="5056f-116">一個 [ **授權與應用程式** ] 索引標籤，展開 [ **授權** ]，然後取消選取您要移除之授權的方塊。</span><span class="sxs-lookup"><span data-stu-id="5056f-116">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="5056f-117">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="5056f-117">Select **Save changes**.</span></span>

5. <span data-ttu-id="5056f-118">當您回到 [作用中 **使用者** ] 頁面時，共用信箱的狀態將會是 [未 **授權**]。</span><span class="sxs-lookup"><span data-stu-id="5056f-118">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="5056f-119">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-119">You're still paying for the license.</span></span> <span data-ttu-id="5056f-120">若要停止付費，請 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="5056f-120">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5056f-121">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="5056f-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5056f-122">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-122">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="5056f-123">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="5056f-123">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="5056f-124">選取 [共用信箱]，然後選取 [**產品授權**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5056f-124">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="5056f-125">[ **產品授權** ] 頁面上，針對您想要移除的授權，將切換設定為 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="5056f-125">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="5056f-126">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5056f-126">Select **Save**.</span></span>

5. <span data-ttu-id="5056f-127">當您回到 [作用中 **使用者** ] 頁面時，共用信箱的狀態將會是 [未 **授權**]。</span><span class="sxs-lookup"><span data-stu-id="5056f-127">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="5056f-128">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-128">You're still paying for the license.</span></span> <span data-ttu-id="5056f-129">若要停止付費，請 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="5056f-129">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5056f-130">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="5056f-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5056f-131">您必須從 [作用中使用者] 頁面中移除授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-131">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="5056f-132">您無法從共用信箱頁面移除授權，因為授權是使用者設定。</span><span class="sxs-lookup"><span data-stu-id="5056f-132">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="5056f-133">選取 [共用信箱]，然後選取 [**產品授權**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5056f-133">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="5056f-134">[ **產品授權** ] 頁面上，針對您想要移除的授權，將切換設定為 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="5056f-134">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="5056f-135">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5056f-135">Select **Save**.</span></span>

5. <span data-ttu-id="5056f-136">當您回到 [作用中 **使用者** ] 頁面時，共用信箱的狀態將會是 [未 **授權**]。</span><span class="sxs-lookup"><span data-stu-id="5056f-136">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="5056f-137">您仍在支付授權。</span><span class="sxs-lookup"><span data-stu-id="5056f-137">You're still paying for the license.</span></span> <span data-ttu-id="5056f-138">若要停止付費，請 [從您的訂閱中移除授權](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="5056f-138">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="5056f-139">相關文章</span><span class="sxs-lookup"><span data-stu-id="5056f-139">Related articles</span></span>

[<span data-ttu-id="5056f-140">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="5056f-140">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="5056f-141">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="5056f-141">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="5056f-142">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="5056f-142">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="5056f-143">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="5056f-143">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="5056f-144">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="5056f-144">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
