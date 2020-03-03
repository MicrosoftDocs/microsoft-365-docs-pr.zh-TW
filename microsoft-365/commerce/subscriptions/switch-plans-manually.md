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
description: 切換 Office 365 商務版訂閱，以手動方式所購買新訂閱，以確保這兩個訂閱的列和作用。
ms.openlocfilehash: 19efd94f320fcf5dc54f44b70b436f713a663a40
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354705"
---
# <a name="switch-office-365-for-business-plans-manually"></a><span data-ttu-id="21144-103">手動切換商務用 Office 365 方案</span><span class="sxs-lookup"><span data-stu-id="21144-103">Switch Office 365 for business plans manually</span></span>

::: moniker range="o365-worldwide"
> [!NOTE]
> <span data-ttu-id="21144-104">本文適用於舊版系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="21144-104">This article applies to the old admin center.</span></span> <span data-ttu-id="21144-105">檢視文章有關在新版系統管理中心，請參閱[手動變更計劃](change-plans-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="21144-105">To view the article about the new admin center, see [Change plans manually](change-plans-manually.md).</span></span> <span data-ttu-id="21144-106">在新版系統管理中心可用於所有的 Microsoft 365 系統管理員，且您可以選擇使用選取位於頂端的 [首頁] 頁面上**嘗試在新版系統管理中心**的切換。</span><span class="sxs-lookup"><span data-stu-id="21144-106">The new admin center is available to all Microsoft 365 admins, and you can opt in by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span> <span data-ttu-id="21144-107">如需詳細資訊，請參閱[關於新的 Microsoft 365 系統管理中心](../../admin/microsoft-365-admin-center-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="21144-107">For more information, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md).</span></span>
::: moniker-end

## <a name="step-1-decide-how-to-switch-plans"></a><span data-ttu-id="21144-108">步驟 1： 決定如何切換方案</span><span class="sxs-lookup"><span data-stu-id="21144-108">Step 1: Decide how to switch plans</span></span>

<span data-ttu-id="21144-109">切換所有使用者從某個計劃到另一個的最佳方式是使用[使用都切換方案] 按鈕](switch-to-a-different-plan.md#use-the-switch-plans-button)。</span><span class="sxs-lookup"><span data-stu-id="21144-109">The best way to switch all your users from one plan to another is to use the [Use the Switch plans button](switch-to-a-different-plan.md#use-the-switch-plans-button).</span></span> <span data-ttu-id="21144-110">有時無法這樣。</span><span class="sxs-lookup"><span data-stu-id="21144-110">Sometimes this isn't possible.</span></span> <span data-ttu-id="21144-111">改為執行手動參數：</span><span class="sxs-lookup"><span data-stu-id="21144-111">Do a manual switch instead:</span></span>
  
- <span data-ttu-id="21144-112">如果沒有 [**切換方案**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="21144-112">If the **Switch plans** button isn't there.</span></span>

- <span data-ttu-id="21144-113">如果當您選取 [**切換方案**] 按鈕，未列出您想要的計劃。</span><span class="sxs-lookup"><span data-stu-id="21144-113">If, when you select the **Switch plans** button, the plan you want isn't listed.</span></span>

- <span data-ttu-id="21144-114">如果您不想要以相同方式切換所有使用者。</span><span class="sxs-lookup"><span data-stu-id="21144-114">If you don't want to switch all your users in the same way.</span></span> <span data-ttu-id="21144-115">有些企業需要不同的使用者訂閱至不同的計劃。</span><span class="sxs-lookup"><span data-stu-id="21144-115">Some businesses need different users subscribed to different plans.</span></span> <span data-ttu-id="21144-116">使用手動切換參數，此功能。</span><span class="sxs-lookup"><span data-stu-id="21144-116">Use a manual switch for this.</span></span>

<span data-ttu-id="21144-117">若要繼續進行手動切換，請參閱[步驟 2： 購買新訂閱](#step-2-buy-a-new-subscription)本主題中。</span><span class="sxs-lookup"><span data-stu-id="21144-117">To continue with a manual switch, read [Step 2: Buy a new subscription](#step-2-buy-a-new-subscription) in this topic.</span></span>
  
## <a name="step-2-buy-a-new-subscription"></a><span data-ttu-id="21144-118">步驟 2： 購買新訂閱</span><span class="sxs-lookup"><span data-stu-id="21144-118">Step 2: Buy a new subscription</span></span>

 <span data-ttu-id="21144-119">**已購買？**</span><span class="sxs-lookup"><span data-stu-id="21144-119">**Already purchased?**</span></span> <span data-ttu-id="21144-120">如果您已經有您想要移動使用者的訂閱，請跳過此步驟並移至[步驟 3： 檢查您的新訂閱與授權](#step-3-check-your-new-subscription-and-licenses)本主題中。</span><span class="sxs-lookup"><span data-stu-id="21144-120">If you already have a subscription you want to move users to, skip this step and go to [Step 3: Check your new subscription and licenses](#step-3-check-your-new-subscription-and-licenses) in this topic.</span></span>
  
- <span data-ttu-id="21144-121">或-</span><span class="sxs-lookup"><span data-stu-id="21144-121">OR -</span></span>
  
 <span data-ttu-id="21144-122">**購買新訂閱和授權：** 請遵循購買新訂閱的[購買另一個 Office 365 商務版訂閱](../buy-another-subscription.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="21144-122">**Purchase a new subscription and licenses:** Follow the steps in [Buy another Office 365 for business subscription](../buy-another-subscription.md) to buy a new subscription.</span></span>
  
<span data-ttu-id="21144-123">請確定您購買訂閱的使用者現在可以在相同組織。</span><span class="sxs-lookup"><span data-stu-id="21144-123">Make sure you purchase a subscription for the same organization that the users are in now.</span></span> <span data-ttu-id="21144-124">例如，請檢查您想要移動之使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="21144-124">For example, check the email addresses for the users you want to move.</span></span> <span data-ttu-id="21144-125">如果他們的電子郵件地址包含 @contoso.com，您必須購買新訂閱 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="21144-125">If their email addresses include @contoso.com, you must purchase a new subscription for contoso.com.</span></span> <span data-ttu-id="21144-126">包含每一個您想要移動的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="21144-126">Include a license for each user that you want to move.</span></span>
  
 <span data-ttu-id="21144-127">**如果您選擇時需要協助計劃**，請參閱[Office 365 商務版產品比較](https://go.microsoft.com/fwlink/p/?linkid=842056)] 頁面上，或[連絡支援人員](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="21144-127">**If you need help choosing a plan**, see the [Office 365 for business product comparison](https://go.microsoft.com/fwlink/p/?linkid=842056) page, or [call support](../../admin/contact-support-for-business-products.md).</span></span>
  
## <a name="step-3-check-your-new-subscription-and-licenses"></a><span data-ttu-id="21144-128">步驟 3： 檢查您的新訂閱與授權</span><span class="sxs-lookup"><span data-stu-id="21144-128">Step 3: Check your new subscription and licenses</span></span>

1. <span data-ttu-id="21144-129">在 [系統管理中心中，移至**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">訂閱</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-129">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Subscriptions</a> page.</span></span>

    <span data-ttu-id="21144-130">如果您使用的是 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">訂閱</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-130">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

    <span data-ttu-id="21144-131">如果您使用的是由 21Vianet 提供的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">訂閱</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-131">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="21144-132">**確認這兩個訂用帳戶會列出與作用中**</span><span class="sxs-lookup"><span data-stu-id="21144-132">**Verify that both subscriptions are listed and active**</span></span>

    <span data-ttu-id="21144-133">您要移動使用者的訂閱和您要移動使用者的訂閱必須列在一起。</span><span class="sxs-lookup"><span data-stu-id="21144-133">The subscription that you're moving users from and the subscription that you're moving users to must be listed together.</span></span> <span data-ttu-id="21144-134">如果新的訂閱沒有您第一次檢查時，請稍後再試。</span><span class="sxs-lookup"><span data-stu-id="21144-134">If the new subscription isn't there when you first check, try again later.</span></span> <span data-ttu-id="21144-135">這兩個訂用帳戶會列在 [**使用中**的檢查。</span><span class="sxs-lookup"><span data-stu-id="21144-135">Check that both subscriptions are listed under **ACTIVE**.</span></span> <span data-ttu-id="21144-136">[新的訂閱未列出，或不是使用中](#the-new-subscription-isnt-listed-or-isnt-active)。</span><span class="sxs-lookup"><span data-stu-id="21144-136">[The new subscription isn't listed, or isn't active](#the-new-subscription-isnt-listed-or-isnt-active).</span></span>

   <span data-ttu-id="21144-137">**新 Office 365 商務版訂閱與可用的授權**</span><span class="sxs-lookup"><span data-stu-id="21144-137">**The new Office 365 for business subscription with available licenses**</span></span>

    ![[訂閱] 頁面上顯示的新訂閱的授權數。](../../media/65a73e96-7c95-4daa-b6ec-71a4bf74dda5.png)
  
3. <span data-ttu-id="21144-139">**檢查您有足夠的每位使用者的授權**</span><span class="sxs-lookup"><span data-stu-id="21144-139">**Check that you have enough licenses for each user**</span></span>

    <span data-ttu-id="21144-140">每位使用者必須符合其訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="21144-140">Each user needs a license that matches their subscription.</span></span> <span data-ttu-id="21144-141">因此如果您想要將十個使用者移至 Office 365 企業版 E5，您需要確定十個授權可用。</span><span class="sxs-lookup"><span data-stu-id="21144-141">So if you want to move ten users to Office 365 Enterprise E5, you'll need to make sure ten licenses are available.</span></span> <span data-ttu-id="21144-142">在這裡圖片，十個授權已購買 Office 365 企業版 E5，以及所有十個授權可用的工作分派。</span><span class="sxs-lookup"><span data-stu-id="21144-142">In the picture here, ten licenses were purchased for Office 365 Enterprise E5, and all ten licenses are available for assignment.</span></span>

4. <span data-ttu-id="21144-143">**需要更多授權的新訂閱嗎？**</span><span class="sxs-lookup"><span data-stu-id="21144-143">**Need more licenses for the new subscription?**</span></span> <span data-ttu-id="21144-144">移至**訂閱**頁面，並[購買適用於 Office 365 商務版訂閱的授權](../licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="21144-144">Go to the **Subscriptions** page and [Buy licenses for your Office 365 for business subscription](../licenses/buy-licenses.md).</span></span>
  
    [<span data-ttu-id="21144-145">舊授權呢？</span><span class="sxs-lookup"><span data-stu-id="21144-145">What about the old licenses?</span></span>](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a><span data-ttu-id="21144-146">新的訂閱未列出，或不是使用中</span><span class="sxs-lookup"><span data-stu-id="21144-146">The new subscription isn't listed, or isn't active</span></span>

- <span data-ttu-id="21144-147">**如果您購買以發票付款的訂閱**，並正在等待信用是必要的它可能需要長達兩個工作天可用，訂閱才能。</span><span class="sxs-lookup"><span data-stu-id="21144-147">**If you purchased a subscription by invoice** and a credit check is required, it can take up to two working days before the subscription is available.</span></span>

- <span data-ttu-id="21144-148">**如果您購買兩個訂閱，它們都不可以同時列在這裡**，它們可能已購買的不同組織 （適用於不同的網域）。</span><span class="sxs-lookup"><span data-stu-id="21144-148">**If you purchased two subscriptions and they are not both listed here**, they may have been purchased for different organizations (for different domains).</span></span> <span data-ttu-id="21144-149">訂閱無法跨組織界限。</span><span class="sxs-lookup"><span data-stu-id="21144-149">Subscriptions can't cross organization boundaries.</span></span>

- <span data-ttu-id="21144-150">**如果您知道您有其他訂閱**，且未列在這裡，或未列在**作用中**[呼叫的支援](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="21144-150">**If you know you have an additional subscription**, and it's not listed here, or not listed under **ACTIVE**, [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="what-about-the-old-licenses"></a><span data-ttu-id="21144-151">舊授權呢？</span><span class="sxs-lookup"><span data-stu-id="21144-151">What about the old licenses?</span></span>

<span data-ttu-id="21144-152">將在稍後; 移除目前的訂閱的授權您將僅支付的新的使用者授權從然後起。</span><span class="sxs-lookup"><span data-stu-id="21144-152">The licenses for the current subscription will be removed later; you'll only pay for the new user licenses from then on.</span></span>
  
## <a name="step-4-reassign-licenses"></a><span data-ttu-id="21144-153">步驟 4： 重新指派授權</span><span class="sxs-lookup"><span data-stu-id="21144-153">Step 4: Reassign licenses</span></span>

### <a name="reassign-a-license-for-one-user"></a><span data-ttu-id="21144-154">重新指派給一位使用者授權</span><span class="sxs-lookup"><span data-stu-id="21144-154">Reassign a license for one user</span></span>

1. <span data-ttu-id="21144-155">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

    <span data-ttu-id="21144-156">如果您使用的是 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-156">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    <span data-ttu-id="21144-157">如果您使用的是由 21Vianet 提供的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-157">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="21144-158">在 [**作用中使用者**] 頁面上，選取您想要指派授權的使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="21144-158">On the **Active users** page, select the box next to the name of the user who you want to assign a license to.</span></span>

3. <span data-ttu-id="21144-159">在右側的 [在 [**產品授權**] 列中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="21144-159">On the right, in the **Product licenses** row, select **Edit**.</span></span>

4. <span data-ttu-id="21144-160">在 [**產品授權**] 窗格中，將開關切換到**上**位置的授權您想要指派給此位使用者。</span><span class="sxs-lookup"><span data-stu-id="21144-160">In the **Product licenses** pane, switch the toggle to the **On** position for the license you want to assign to this user.</span></span> <span data-ttu-id="21144-161">根據預設，與該授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="21144-161">By default, all services associated with that license are automatically assigned to the user.</span></span>

    > [!TIP]
    > <span data-ttu-id="21144-162">若要限制哪些服務會提供給使用者，將開關切換到您要移除該使用者的服務**關閉**位置。</span><span class="sxs-lookup"><span data-stu-id="21144-162">To limit which services are available to the user, switch the toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="21144-163">例如，如果您想商務擁有存取權，Skype 以外的所有可用服務的使用者，您可以將開關切換 skype for Business Online service 到 [**關閉**] 位置。</span><span class="sxs-lookup"><span data-stu-id="21144-163">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
  
    ![設定使用者的授權指派。](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
5. <span data-ttu-id="21144-165">將開關切換到此使用者不再需要的授權的 [**關閉**] 位置。</span><span class="sxs-lookup"><span data-stu-id="21144-165">Switch the toggle to the **Off** position for licenses that this user no longer needs.</span></span>

6. <span data-ttu-id="21144-166">在 [**產品授權**] 窗格底部，選取 [**指派** \> **Close** \> **關閉**。</span><span class="sxs-lookup"><span data-stu-id="21144-166">At the bottom of the **Product licenses** pane, select **Assign** \> **Close** \> **Close**.</span></span>

### <a name="reassign-licenses-for-multiple-users-at-once"></a><span data-ttu-id="21144-167">一次重新指派多個使用者的授權</span><span class="sxs-lookup"><span data-stu-id="21144-167">Reassign licenses for multiple users at once</span></span>

1. <span data-ttu-id="21144-168">在系統管理中心中，移至 [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>] 頁面上，或選取**使用者** \> **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="21144-168">In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page, or select **Users** \> **Active users**.</span></span>

    <span data-ttu-id="21144-169">如果您使用的是 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-169">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    <span data-ttu-id="21144-170">如果您使用的是由 21Vianet 提供的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="21144-170">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="21144-171">選取您要取代現有授權的使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="21144-171">Select the boxes next to the names of the users who you want to replace existing licenses for.</span></span>

3. <span data-ttu-id="21144-172">在 [**大量動作**] 窗格中，選擇 [**編輯產品授權**]。</span><span class="sxs-lookup"><span data-stu-id="21144-172">In the **Bulk actions** pane, choose **Edit product licenses**.</span></span>

4. <span data-ttu-id="21144-173">在 **[指派產品]** 窗格中，選取 **[取代現有產品授權指派]** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="21144-173">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>

5. <span data-ttu-id="21144-174">將開關切換到**上**位置的產品您想要指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="21144-174">Switch the toggle to the **On** position for the products you want to assign to these users.</span></span>

    > [!TIP]
    > - <span data-ttu-id="21144-175">若要限制哪些服務會提供給使用者，切換至切換到您要移除該使用者的服務**關閉**位置。</span><span class="sxs-lookup"><span data-stu-id="21144-175">To limit which services are available to the user, switch to toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="21144-176">例如，如果您想商務擁有存取權，Skype 以外的所有可用服務的使用者，您可以將開關切換 skype for Business Online service 到 [**關閉**] 位置。</span><span class="sxs-lookup"><span data-stu-id="21144-176">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
    > - <span data-ttu-id="21144-177">將移除任何先前指派給所選使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="21144-177">Any previous license assignments for the selected users will be removed.</span></span>
  
    ![設定使用者的授權指派。](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
6. <span data-ttu-id="21144-179">在 **[取代現有產品]** 窗格中，選取 **[取代]** \> **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="21144-179">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a><span data-ttu-id="21144-180">步驟 5： 取消訂閱，或移除您不再需要 （選用） 的授權</span><span class="sxs-lookup"><span data-stu-id="21144-180">Step 5: Cancel subscriptions or remove licenses that you no longer need (Optional)</span></span>

<span data-ttu-id="21144-181">如果您將所有使用者從一個訂閱移到另一個訂閱，且您不再需要原本的訂閱，可以[取消訂閱](cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="21144-181">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span></span>
  
<span data-ttu-id="21144-182">如果您只將部分使用者移至不同的訂閱，[移除授權](../licenses/remove-licenses-from-subscription.md)，您不再需要時。</span><span class="sxs-lookup"><span data-stu-id="21144-182">If you moved only some users to a different subscription, [remove licenses](../licenses/remove-licenses-from-subscription.md) that you no longer need.</span></span>
  
## <a name="call-support-to-help-you-switch-plans"></a><span data-ttu-id="21144-183">連絡支援服務以協助切換方案</span><span class="sxs-lookup"><span data-stu-id="21144-183">Call support to help you switch plans</span></span>

[<span data-ttu-id="21144-184">電話支援</span><span class="sxs-lookup"><span data-stu-id="21144-184">Call support</span></span>](../../admin/contact-support-for-business-products.md)