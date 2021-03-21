---
title: '管理自助購買 (系統管理員) '
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 系統管理員可以瞭解如何管理組織中使用者所進行的自我服務購買。
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920177"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="f697a-103">管理自助購買 (管理員)</span><span class="sxs-lookup"><span data-stu-id="f697a-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f697a-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="f697a-104">The admin center is changing.</span></span> <span data-ttu-id="f697a-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="f697a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f697a-106">身為系統管理員，您可以看到組織中人員所進行的自我服務購買。</span><span class="sxs-lookup"><span data-stu-id="f697a-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="f697a-107">您會看到產品名稱、購買購買的訂閱、到期日、購買價格，以及每個自助購買的指派使用者。</span><span class="sxs-lookup"><span data-stu-id="f697a-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="f697a-108">如果您的組織需要，您可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="f697a-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="f697a-109">透過自助購買或集中購買的產品，您可以使用相同的資料管理和存取原則。</span><span class="sxs-lookup"><span data-stu-id="f697a-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="f697a-110">您也可以控制組織中的使用者是否可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="f697a-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="f697a-111">如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="f697a-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="f697a-112">查看自助訂閱</span><span class="sxs-lookup"><span data-stu-id="f697a-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="f697a-113">在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f697a-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f697a-114">在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="f697a-115">若要查看訂閱的詳細資料，請從清單中選擇其中一個。</span><span class="sxs-lookup"><span data-stu-id="f697a-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="f697a-116">查看誰有自助購買訂閱的授權</span><span class="sxs-lookup"><span data-stu-id="f697a-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="f697a-117">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f697a-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="f697a-118">選取 [篩選] 圖示，然後選擇 [ **自我服務**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="f697a-119">選取產品以查看指派給人員的授權。</span><span class="sxs-lookup"><span data-stu-id="f697a-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="f697a-120">如果有多個產品購買的產品，該產品只會列出一次，而且 [ **可用數量** ] 欄會顯示針對該產品購買的所有訂閱總數。</span><span class="sxs-lookup"><span data-stu-id="f697a-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="f697a-121">[ **使用者** ] 清單是依進行自助購買的人員名稱群組。</span><span class="sxs-lookup"><span data-stu-id="f697a-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="f697a-122">若要匯出具有這些訂閱之授權的使用者清單，請選擇您想要匯出的訂閱，然後選擇 [ **匯出使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="f697a-123">停用或啟用自助購買</span><span class="sxs-lookup"><span data-stu-id="f697a-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="f697a-124">您可以針對組織中的使用者停用或啟用自助購買功能。</span><span class="sxs-lookup"><span data-stu-id="f697a-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="f697a-125">**MSCommerce** PowerShell 模組包含 **AllowSelfServicePurchase** 的 **PolicyID** 參數值，可讓您控制組織中的使用者是否可以進行自助購買，以及哪些產品。</span><span class="sxs-lookup"><span data-stu-id="f697a-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="f697a-126">您可以使用 **MSCommerce** PowerShell 模組來：</span><span class="sxs-lookup"><span data-stu-id="f697a-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="f697a-127">查看 **AllowSelfServicePurchase** 參數值的預設狀態（不論是由產品啟用或停用）</span><span class="sxs-lookup"><span data-stu-id="f697a-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="f697a-128">查看適用產品的清單，以及是否啟用或停用自助購買功能</span><span class="sxs-lookup"><span data-stu-id="f697a-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="f697a-129">查看或修改特定產品的目前設定，以啟用或停用</span><span class="sxs-lookup"><span data-stu-id="f697a-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="f697a-130">如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="f697a-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="f697a-131">在單一訂閱下集中授權</span><span class="sxs-lookup"><span data-stu-id="f697a-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="f697a-132">您可以指派現有的授權，或透過現有的合約針對指派給自助購買之使用者的現有協定來購買其他訂閱。</span><span class="sxs-lookup"><span data-stu-id="f697a-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="f697a-133">在您指派這些已集中購買的授權之後，您可以要求購買者取消其現有的訂閱。</span><span class="sxs-lookup"><span data-stu-id="f697a-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="f697a-134">在系統管理中心中，移至 [ **帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">購買服務</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f697a-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="f697a-135">尋找並選擇您想要購買的產品，然後選擇 [ **購買**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="f697a-136">完成其餘步驟以完成購買。</span><span class="sxs-lookup"><span data-stu-id="f697a-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="f697a-137">請遵循 View the [自助購買訂閱授權的](#view-who-has-licenses-for-a-self-service-purchase-subscription) 使用者，在下一個步驟中將使用者清單匯出為參考的使用者。</span><span class="sxs-lookup"><span data-stu-id="f697a-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="f697a-138">將授權指派給在其他訂閱中具有授權的每個人。</span><span class="sxs-lookup"><span data-stu-id="f697a-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="f697a-139">如需完整步驟，請參閱 [將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="f697a-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="f697a-140">聯繫購買自助購買訂閱的人員，並要求他們 [取消](manage-self-service-purchases-users.md#cancel-a-subscription)。</span><span class="sxs-lookup"><span data-stu-id="f697a-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="f697a-141">接管自助購買訂閱</span><span class="sxs-lookup"><span data-stu-id="f697a-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="f697a-142">您可以接管組織中使用者所做的自助購買訂閱。</span><span class="sxs-lookup"><span data-stu-id="f697a-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="f697a-143">當您接管自助購買訂閱時，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="f697a-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="f697a-144">將使用者移至不同的訂閱，並取消原始的訂閱。</span><span class="sxs-lookup"><span data-stu-id="f697a-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="f697a-145">取消自助購買訂閱，並從指派的使用者中移除授權。</span><span class="sxs-lookup"><span data-stu-id="f697a-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="f697a-146">將使用者移至其他訂閱</span><span class="sxs-lookup"><span data-stu-id="f697a-146">Move users to a different subscription</span></span>

<span data-ttu-id="f697a-147">當您將使用者移至不同的訂閱時，會自動取消舊的訂閱。</span><span class="sxs-lookup"><span data-stu-id="f697a-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="f697a-148">最初購買自助購買訂閱的使用者會收到一封電子郵件，指出訂閱已取消。</span><span class="sxs-lookup"><span data-stu-id="f697a-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="f697a-149">您必須具備您要移動使用者的訂閱中每個使用者的可用授權。</span><span class="sxs-lookup"><span data-stu-id="f697a-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="f697a-150">在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f697a-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f697a-151">在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="f697a-152">選取您要接管的訂閱。</span><span class="sxs-lookup"><span data-stu-id="f697a-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="f697a-153">在 [訂閱詳細資料] 頁面的 [ **訂閱與設定** ] 區段中，選取 [ **取得此訂閱的控制權**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="f697a-154">在右窗格中，選取 [ **移動使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="f697a-155">選取您要將使用者移至其中的產品，然後選取 [ **移動使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="f697a-156">在 [ **將使用者移至** ] 方塊中，選取 [ **移動使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="f697a-157">移動程式可能需要數分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="f697a-157">The move process might take several minutes.</span></span> <span data-ttu-id="f697a-158">當程式執行時，請勿關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="f697a-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="f697a-159">移動程式完成後，請關閉 [ **移動完成] 窗格**。</span><span class="sxs-lookup"><span data-stu-id="f697a-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="f697a-160">在 [訂閱詳細資料] 頁面上，自助購買之訂閱的 **訂閱狀態** 會顯示為 [ **已刪除**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="f697a-161">取消自助購買訂閱</span><span class="sxs-lookup"><span data-stu-id="f697a-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="f697a-162">當您選擇取消自助購買訂閱時，具有授權的使用者將無法存取產品。</span><span class="sxs-lookup"><span data-stu-id="f697a-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="f697a-163">最初購買自助購買訂閱的使用者會收到一封電子郵件，指出訂閱已取消。</span><span class="sxs-lookup"><span data-stu-id="f697a-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="f697a-164">在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f697a-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f697a-165">在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="f697a-166">選取您要取消的訂閱。</span><span class="sxs-lookup"><span data-stu-id="f697a-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="f697a-167">在 [訂閱詳細資料] 頁面的 [ **訂閱與設定** ] 區段中，選取 [ **取得此訂閱的控制權**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="f697a-168">在右窗格中，選取 [ **取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="f697a-169">從下拉式清單中選取您取消的原因，然後選取 [ **取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="f697a-170">在 [ **您確定要取消嗎？** ] 方塊中，選取 [ **取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="f697a-171">關閉右窗格。</span><span class="sxs-lookup"><span data-stu-id="f697a-171">Close the right pane.</span></span>
9. <span data-ttu-id="f697a-172">在 [訂閱詳細資料] 頁面上， **訂閱狀態** 會顯示為 [ **已刪除**]。</span><span class="sxs-lookup"><span data-stu-id="f697a-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="f697a-173">需要協助？</span><span class="sxs-lookup"><span data-stu-id="f697a-173">Need help?</span></span> <span data-ttu-id="f697a-174">聯繫我們。</span><span class="sxs-lookup"><span data-stu-id="f697a-174">Contact us.</span></span>

<span data-ttu-id="f697a-175">如需有關自助購買的常見問題，請參閱 [自助購買常見問題](self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="f697a-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="f697a-176">如果您有任何問題或需要協助您購買自助服務，請 [與支援人員聯繫](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="f697a-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>