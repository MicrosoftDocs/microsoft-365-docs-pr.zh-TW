---
title: 手動切換商務用 Office 365 方案
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: eb0d0680-5677-41a0-8c46-4b9d47f1c209
ROBOTS: NOINDEX
description: 購買新的訂閱並確保訂閱已列出並使用中，以手動切換商務用 Office 365 訂閱。
ms.openlocfilehash: a652053b204e84f8f2d3973eba76ead1cc7c1410
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540840"
---
# <a name="switch-office-365-for-business-plans-manually"></a><span data-ttu-id="87eb6-103">手動切換商務用 Office 365 方案</span><span class="sxs-lookup"><span data-stu-id="87eb6-103">Switch Office 365 for business plans manually</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="87eb6-104">本文適用于舊版系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="87eb6-104">This article applies to the old admin center.</span></span> <span data-ttu-id="87eb6-105">若要查看有關新系統管理中心的文章，請參閱[手動變更計畫](change-plans-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-105">To view the article about the new admin center, see [Change plans manually](change-plans-manually.md).</span></span> <span data-ttu-id="87eb6-106">新版系統管理中心可供所有 Microsoft 365 系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="87eb6-106">The new admin center is available to all Microsoft 365 admins.</span></span> <span data-ttu-id="87eb6-107">如需詳細資訊，請參閱[關於新的 Microsoft 365 系統管理中心](../../admin/microsoft-365-admin-center-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-107">For more information, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md).</span></span>

::: moniker-end

## <a name="step-1-decide-how-to-switch-plans"></a><span data-ttu-id="87eb6-108">步驟1：決定切換方案的方式</span><span class="sxs-lookup"><span data-stu-id="87eb6-108">Step 1: Decide how to switch plans</span></span>

<span data-ttu-id="87eb6-109">若要將所有使用者從一個計畫切換到另一個計畫，最好的方法是使用 [[使用切換方案] 按鈕](switch-to-a-different-plan.md#use-the-switch-plans-button)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-109">The best way to switch all your users from one plan to another is to use the [Use the Switch plans button](switch-to-a-different-plan.md#use-the-switch-plans-button).</span></span> <span data-ttu-id="87eb6-110">有時候這是不可能的。</span><span class="sxs-lookup"><span data-stu-id="87eb6-110">Sometimes this isn't possible.</span></span> <span data-ttu-id="87eb6-111">改為執行手動切換：</span><span class="sxs-lookup"><span data-stu-id="87eb6-111">Do a manual switch instead:</span></span>
  
- <span data-ttu-id="87eb6-112">如果沒有 [**切換方案**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="87eb6-112">If the **Switch plans** button isn't there.</span></span>

- <span data-ttu-id="87eb6-113">當您選取 [**切換方案**] 按鈕時，您想要的計畫並未列出。</span><span class="sxs-lookup"><span data-stu-id="87eb6-113">If, when you select the **Switch plans** button, the plan you want isn't listed.</span></span>

- <span data-ttu-id="87eb6-114">如果您不想以相同的方式切換所有使用者。</span><span class="sxs-lookup"><span data-stu-id="87eb6-114">If you don't want to switch all your users in the same way.</span></span> <span data-ttu-id="87eb6-115">有些企業需要不同的使用者訂閱不同的方案。</span><span class="sxs-lookup"><span data-stu-id="87eb6-115">Some businesses need different users subscribed to different plans.</span></span> <span data-ttu-id="87eb6-116">針對此使用手動參數。</span><span class="sxs-lookup"><span data-stu-id="87eb6-116">Use a manual switch for this.</span></span>

<span data-ttu-id="87eb6-117">若要繼續手動切換，請參閱本主題中[的步驟2：購買新的訂閱](#step-2-buy-a-new-subscription)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-117">To continue with a manual switch, read [Step 2: Buy a new subscription](#step-2-buy-a-new-subscription) in this topic.</span></span>
  
## <a name="step-2-buy-a-new-subscription"></a><span data-ttu-id="87eb6-118">步驟2：購買新的訂閱</span><span class="sxs-lookup"><span data-stu-id="87eb6-118">Step 2: Buy a new subscription</span></span>

 <span data-ttu-id="87eb6-119">**已購買？**</span><span class="sxs-lookup"><span data-stu-id="87eb6-119">**Already purchased?**</span></span> <span data-ttu-id="87eb6-120">如果您已有要將使用者移至其中的訂閱，請略過此步驟，然後移至 [[步驟3：檢查您](#step-3-check-your-new-subscription-and-licenses)在本主題中的新訂閱與授權]。</span><span class="sxs-lookup"><span data-stu-id="87eb6-120">If you already have a subscription you want to move users to, skip this step and go to [Step 3: Check your new subscription and licenses](#step-3-check-your-new-subscription-and-licenses) in this topic.</span></span>
  
- <span data-ttu-id="87eb6-121">或</span><span class="sxs-lookup"><span data-stu-id="87eb6-121">OR -</span></span>
  
 <span data-ttu-id="87eb6-122">**購買新的訂閱與授權：** 遵循[購買其他商務用 Office 365 訂閱](../buy-another-subscription.md)中的步驟，購買新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="87eb6-122">**Purchase a new subscription and licenses:** Follow the steps in [Buy another Office 365 for business subscription](../buy-another-subscription.md) to buy a new subscription.</span></span>
  
<span data-ttu-id="87eb6-123">請確認您購買的是使用者現在所在組織的訂閱。</span><span class="sxs-lookup"><span data-stu-id="87eb6-123">Make sure you purchase a subscription for the same organization that the users are in now.</span></span> <span data-ttu-id="87eb6-124">例如，檢查您要移動之使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="87eb6-124">For example, check the email addresses for the users you want to move.</span></span> <span data-ttu-id="87eb6-125">如果他們的電子郵件地址包含 @contoso .com，您必須購買 contoso.com 的新訂閱。</span><span class="sxs-lookup"><span data-stu-id="87eb6-125">If their email addresses include @contoso.com, you must purchase a new subscription for contoso.com.</span></span> <span data-ttu-id="87eb6-126">針對每個您想要移動的使用者，加入一個授權。</span><span class="sxs-lookup"><span data-stu-id="87eb6-126">Include a license for each user that you want to move.</span></span>
  
 <span data-ttu-id="87eb6-127">**如果您需要協助選擇計畫**，請參閱[商務用 Office 365 產品比較](https://go.microsoft.com/fwlink/p/?linkid=842056)頁面或[電話支援](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-127">**If you need help choosing a plan**, see the [Office 365 for business product comparison](https://go.microsoft.com/fwlink/p/?linkid=842056) page, or [call support](../../admin/contact-support-for-business-products.md).</span></span>
  
## <a name="step-3-check-your-new-subscription-and-licenses"></a><span data-ttu-id="87eb6-128">步驟3：檢查您的新訂閱與授權</span><span class="sxs-lookup"><span data-stu-id="87eb6-128">Step 3: Check your new subscription and licenses</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="87eb6-129">在系統管理中心中，前往 [帳單]\*\*\*\* \> [訂閱]<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-129">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Subscriptions</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="87eb6-130">在系統管理中心中，前往 [帳單]\*\*\*\* > [訂閱]<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="87eb6-131">在系統管理中心中，前往 [帳單]\*\*\*\* > [訂閱]<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-131">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="87eb6-132">**確認同時列出和使用中的兩個訂閱**</span><span class="sxs-lookup"><span data-stu-id="87eb6-132">**Verify that both subscriptions are listed and active**</span></span>

    <span data-ttu-id="87eb6-133">您要將使用者移至其中的訂閱，以及您要將使用者移至其中的訂閱，必須一起列出。</span><span class="sxs-lookup"><span data-stu-id="87eb6-133">The subscription that you're moving users from and the subscription that you're moving users to must be listed together.</span></span> <span data-ttu-id="87eb6-134">如果您第一次檢查時新的訂閱不在那裡，請稍後再試一次。</span><span class="sxs-lookup"><span data-stu-id="87eb6-134">If the new subscription isn't there when you first check, try again later.</span></span> <span data-ttu-id="87eb6-135">檢查這兩個訂閱均列**在 [作用中]**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-135">Check that both subscriptions are listed under **ACTIVE**.</span></span> <span data-ttu-id="87eb6-136">[未列出或未使用中的新訂閱](#the-new-subscription-isnt-listed-or-isnt-active)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-136">[The new subscription isn't listed, or isn't active](#the-new-subscription-isnt-listed-or-isnt-active).</span></span>

   <span data-ttu-id="87eb6-137">**新的商務用 Office 365 訂閱，含可用的授權**</span><span class="sxs-lookup"><span data-stu-id="87eb6-137">**The new Office 365 for business subscription with available licenses**</span></span>

    ![[訂閱] 頁面，顯示新訂閱的授權數目。](../../media/65a73e96-7c95-4daa-b6ec-71a4bf74dda5.png)
  
3. <span data-ttu-id="87eb6-139">**檢查您是否有足夠的授權可供每個使用者使用**</span><span class="sxs-lookup"><span data-stu-id="87eb6-139">**Check that you have enough licenses for each user**</span></span>

    <span data-ttu-id="87eb6-140">每個使用者都需要符合其訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="87eb6-140">Each user needs a license that matches their subscription.</span></span> <span data-ttu-id="87eb6-141">因此，如果您想要將十位使用者移至 Office 365 企業版 E5，您必須確定有10個授權可供使用。</span><span class="sxs-lookup"><span data-stu-id="87eb6-141">So if you want to move ten users to Office 365 Enterprise E5, you'll need to make sure ten licenses are available.</span></span> <span data-ttu-id="87eb6-142">在這裡的圖片中，Office 365 企業版 E5 購買了10個授權，而且所有10個授權均可供指派。</span><span class="sxs-lookup"><span data-stu-id="87eb6-142">In the picture here, ten licenses were purchased for Office 365 Enterprise E5, and all ten licenses are available for assignment.</span></span>

4. <span data-ttu-id="87eb6-143">**新訂閱需要更多授權？**</span><span class="sxs-lookup"><span data-stu-id="87eb6-143">**Need more licenses for the new subscription?**</span></span> <span data-ttu-id="87eb6-144">移至 [**訂閱**] 頁面，[購買商務用 Office 365 訂閱的授權](../licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-144">Go to the **Subscriptions** page and [Buy licenses for your Office 365 for business subscription](../licenses/buy-licenses.md).</span></span>
  
    [<span data-ttu-id="87eb6-145">舊的授權為何？</span><span class="sxs-lookup"><span data-stu-id="87eb6-145">What about the old licenses?</span></span>](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a><span data-ttu-id="87eb6-146">未列出或未使用的新訂閱</span><span class="sxs-lookup"><span data-stu-id="87eb6-146">The new subscription isn't listed, or isn't active</span></span>

- <span data-ttu-id="87eb6-147">**如果您是透過發票購買訂閱**，而且需要信用檢查，則訂閱可享受兩天前的訂閱。</span><span class="sxs-lookup"><span data-stu-id="87eb6-147">**If you purchased a subscription by invoice** and a credit check is required, it can take up to two working days before the subscription is available.</span></span>

- <span data-ttu-id="87eb6-148">**如果您已購買兩個訂閱，而且不是兩者都列出**，則可能是針對不同的組織購買的。</span><span class="sxs-lookup"><span data-stu-id="87eb6-148">**If you purchased two subscriptions and they are not both listed here**, they may have been purchased for different organizations (for different domains).</span></span> <span data-ttu-id="87eb6-149">訂閱無法跨組織界限。</span><span class="sxs-lookup"><span data-stu-id="87eb6-149">Subscriptions can't cross organization boundaries.</span></span>

- <span data-ttu-id="87eb6-150">**如果您知道有其他訂閱**，但未列在這裡，或未列在 [使用中 **]，請**[致電支援人員](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-150">**If you know you have an additional subscription**, and it's not listed here, or not listed under **ACTIVE**, [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="what-about-the-old-licenses"></a><span data-ttu-id="87eb6-151">舊的授權為何？</span><span class="sxs-lookup"><span data-stu-id="87eb6-151">What about the old licenses?</span></span>

<span data-ttu-id="87eb6-152">將稍後移除目前訂閱的授權;您只需要支付新的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="87eb6-152">The licenses for the current subscription will be removed later; you'll only pay for the new user licenses from then on.</span></span>
  
## <a name="step-4-reassign-licenses"></a><span data-ttu-id="87eb6-153">步驟4：重新指派授權</span><span class="sxs-lookup"><span data-stu-id="87eb6-153">Step 4: Reassign licenses</span></span>

### <a name="reassign-a-license-for-one-user"></a><span data-ttu-id="87eb6-154">為一位使用者重新指派授權</span><span class="sxs-lookup"><span data-stu-id="87eb6-154">Reassign a license for one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="87eb6-155">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="87eb6-156">在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-156">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="87eb6-157">在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-157">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="87eb6-158">在 [作用中**使用者**] 頁面上，選取您要指派授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="87eb6-158">On the **Active users** page, select the box next to the name of the user who you want to assign a license to.</span></span>

3. <span data-ttu-id="87eb6-159">在右側的 [**產品授權**] 列中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="87eb6-159">On the right, in the **Product licenses** row, select **Edit**.</span></span>

4. <span data-ttu-id="87eb6-160">在 [**產品授權**] 窗格中，針對您想要指派給此使用者的授權，將開關切換到 [**開啟**] 位置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-160">In the **Product licenses** pane, switch the toggle to the **On** position for the license you want to assign to this user.</span></span> <span data-ttu-id="87eb6-161">根據預設，與該授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="87eb6-161">By default, all services associated with that license are automatically assigned to the user.</span></span>

    > [!TIP]
    > <span data-ttu-id="87eb6-162">若要限制使用者可使用的服務，請針對您想要針對該使用者移除的服務，將切換切換到 [**關閉**] 位置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-162">To limit which services are available to the user, switch the toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="87eb6-163">例如，如果您想要使用者能夠存取所有可用的服務（商務用 Skype Online 除外），您可以將商務用 Skype Online 服務的切換切換到 [**關閉**] 位置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-163">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
  
    ![設定使用者的授權指派。](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
5. <span data-ttu-id="87eb6-165">針對此使用者不再需要的授權，將開關切換到 [**關閉**] 位置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-165">Switch the toggle to the **Off** position for licenses that this user no longer needs.</span></span>

6. <span data-ttu-id="87eb6-166">在 [**產品授權**] 窗格的底部，選取 [**指派** \> **關閉** \> ] **[關閉]。**</span><span class="sxs-lookup"><span data-stu-id="87eb6-166">At the bottom of the **Product licenses** pane, select **Assign** \> **Close** \> **Close**.</span></span>

### <a name="reassign-licenses-for-multiple-users-at-once"></a><span data-ttu-id="87eb6-167">一次為多位使用者重新指派授權</span><span class="sxs-lookup"><span data-stu-id="87eb6-167">Reassign licenses for multiple users at once</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="87eb6-168">在系統管理中心中，移至 [作用中<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>] 頁面，或選取 [**使用者** \>作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="87eb6-168">In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page, or select **Users** \> **Active users**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="87eb6-169">在系統管理中心中，移至 [**使用者** >作用中<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">使用者</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-169">In the admin center, go to **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="87eb6-170">在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="87eb6-170">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="87eb6-171">選取您要取代現有授權的使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="87eb6-171">Select the boxes next to the names of the users who you want to replace existing licenses for.</span></span>

3. <span data-ttu-id="87eb6-172">在 [**大量動作**] 窗格中，選擇 [**編輯產品授權**]。</span><span class="sxs-lookup"><span data-stu-id="87eb6-172">In the **Bulk actions** pane, choose **Edit product licenses**.</span></span>

4. <span data-ttu-id="87eb6-173">在 **[指派產品]** 窗格中，選取 **[取代現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-173">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>

5. <span data-ttu-id="87eb6-174">針對您想要指派給這些使用者的產品，將開關切換到 [**開啟**] 位置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-174">Switch the toggle to the **On** position for the products you want to assign to these users.</span></span>

    > [!TIP]
    > - <span data-ttu-id="87eb6-175">若要限制使用者可使用的服務，請切換至 [**關閉**] 以切換至您要針對該使用者移除的服務。</span><span class="sxs-lookup"><span data-stu-id="87eb6-175">To limit which services are available to the user, switch to toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="87eb6-176">例如，如果您想要使用者能夠存取所有可用的服務（商務用 Skype Online 除外），您可以將商務用 Skype Online 服務的切換切換到 [**關閉**] 位置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-176">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
    > - <span data-ttu-id="87eb6-177">將移除任何先前指派給所選使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="87eb6-177">Any previous license assignments for the selected users will be removed.</span></span>
  
    ![設定使用者的授權指派。](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
6. <span data-ttu-id="87eb6-179">在 **[取代現有產品]** 窗格中，選取 **[取代]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-179">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a><span data-ttu-id="87eb6-180">步驟5：取消訂閱或移除您不再需要的授權（選用）</span><span class="sxs-lookup"><span data-stu-id="87eb6-180">Step 5: Cancel subscriptions or remove licenses that you no longer need (Optional)</span></span>

<span data-ttu-id="87eb6-181">如果您將所有使用者從一個訂閱移到另一個訂閱，且您不再需要原本的訂閱，可以[取消訂閱](cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-181">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span></span>
  
<span data-ttu-id="87eb6-182">如果您只將部分使用者移至不同的訂閱，請移除您不再需要的[授權](../licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-182">If you moved only some users to a different subscription, [remove licenses](../licenses/remove-licenses-from-subscription.md) that you no longer need.</span></span>
  
## <a name="call-support-to-help-you-switch-plans"></a><span data-ttu-id="87eb6-183">連絡支援服務以協助切換方案</span><span class="sxs-lookup"><span data-stu-id="87eb6-183">Call support to help you switch plans</span></span>

[<span data-ttu-id="87eb6-184">電話支援</span><span class="sxs-lookup"><span data-stu-id="87eb6-184">Call support</span></span>](../../admin/contact-support-for-business-products.md)