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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce
search.appverid:
- MET150
description: 系統管理員可以瞭解如何管理組織中使用者所進行的自我服務購買。
ms.openlocfilehash: febf0ee470e735a454dc7a9e747de5025c7a4a51
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398171"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="3677d-103">管理自助購買 (管理員)</span><span class="sxs-lookup"><span data-stu-id="3677d-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="3677d-104">身為系統管理員，您可以看到組織中人員所進行的自我服務購買。</span><span class="sxs-lookup"><span data-stu-id="3677d-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="3677d-105">您會看到產品名稱、購買購買的訂閱、到期日、購買價格，以及每個自助購買的指派使用者。</span><span class="sxs-lookup"><span data-stu-id="3677d-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="3677d-106">如果您的組織需要，您可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。</span><span class="sxs-lookup"><span data-stu-id="3677d-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="3677d-107">透過自助購買或集中購買的產品，您可以使用相同的資料管理和存取原則。</span><span class="sxs-lookup"><span data-stu-id="3677d-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="3677d-108">您也可以控制組織中的使用者是否可以進行自助購買。</span><span class="sxs-lookup"><span data-stu-id="3677d-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="3677d-109">如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="3677d-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="3677d-110">查看自助訂閱</span><span class="sxs-lookup"><span data-stu-id="3677d-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3677d-111">在系統管理中心，移至 [帳單 **]** > [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3677d-112">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** > **產品** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-112">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3677d-113">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** > **產品** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-113">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="3677d-114">在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="3677d-115">若要查看訂閱的詳細資料，請從清單中選擇其中一個。</span><span class="sxs-lookup"><span data-stu-id="3677d-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="3677d-116">查看誰有自助購買訂閱的授權</span><span class="sxs-lookup"><span data-stu-id="3677d-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="3677d-117">身為系統管理員，您無法指派或取消指派組織中使用者購買之自助購買訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="3677d-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="3677d-118">您可以 [接管自助購買訂閱](#take-over-a-self-service-purchase-subscription)，然後指派或取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="3677d-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3677d-119">在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3677d-120">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** > **授權** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3677d-121">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** > **授權** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="3677d-122">選取 [篩選] 圖示，然後選擇 [ **自我服務**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="3677d-123">選取產品以查看指派給人員的授權。</span><span class="sxs-lookup"><span data-stu-id="3677d-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="3677d-124">如果有多個產品購買的產品，該產品只會列出一次，而且 [ **可用數量** ] 欄會顯示針對該產品購買的所有訂閱總數。</span><span class="sxs-lookup"><span data-stu-id="3677d-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="3677d-125">[ **使用者** ] 清單是依進行自助購買的人員名稱群組。</span><span class="sxs-lookup"><span data-stu-id="3677d-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="3677d-126">若要匯出具有這些訂閱之授權的使用者清單，請選擇您想要匯出的訂閱，然後選擇 [ **匯出使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="3677d-127">停用或啟用自助購買</span><span class="sxs-lookup"><span data-stu-id="3677d-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="3677d-128">您可以針對組織中的使用者停用或啟用自助購買功能。</span><span class="sxs-lookup"><span data-stu-id="3677d-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="3677d-129">**MSCommerce** PowerShell 模組包含 **AllowSelfServicePurchase** 的 **PolicyID** 參數值，可讓您控制組織中的使用者是否可以進行自助購買，以及哪些產品。</span><span class="sxs-lookup"><span data-stu-id="3677d-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="3677d-130">您可以使用 **MSCommerce** PowerShell 模組來：</span><span class="sxs-lookup"><span data-stu-id="3677d-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="3677d-131">查看 **AllowSelfServicePurchase** 參數值的預設狀態（不論是由產品啟用或停用）</span><span class="sxs-lookup"><span data-stu-id="3677d-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="3677d-132">查看適用產品的清單，以及是否啟用或停用自助購買功能</span><span class="sxs-lookup"><span data-stu-id="3677d-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="3677d-133">查看或修改特定產品的目前設定，以啟用或停用</span><span class="sxs-lookup"><span data-stu-id="3677d-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="3677d-134">如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="3677d-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="3677d-135">在單一訂閱下集中授權</span><span class="sxs-lookup"><span data-stu-id="3677d-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="3677d-136">您可以指派現有的授權，或透過現有的合約針對指派給自助購買之使用者的現有協定來購買其他訂閱。</span><span class="sxs-lookup"><span data-stu-id="3677d-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="3677d-137">在您指派這些已集中購買的授權之後，您可以要求購買者取消其現有的訂閱。</span><span class="sxs-lookup"><span data-stu-id="3677d-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3677d-138">在系統管理中心中，移至 [ **帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">購買服務</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3677d-139">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** > **購買服務** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3677d-140">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** > **購買服務** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="3677d-141">尋找並選擇您想要購買的產品，然後選擇 [ **購買**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="3677d-142">完成其餘步驟以完成購買。</span><span class="sxs-lookup"><span data-stu-id="3677d-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="3677d-143">請遵循 View the [自助購買訂閱授權的](#view-who-has-licenses-for-a-self-service-purchase-subscription) 使用者，在下一個步驟中將使用者清單匯出為參考的使用者。</span><span class="sxs-lookup"><span data-stu-id="3677d-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="3677d-144">將授權指派給在其他訂閱中具有授權的每個人。</span><span class="sxs-lookup"><span data-stu-id="3677d-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="3677d-145">如需完整步驟，請參閱 [將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="3677d-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="3677d-146">聯繫購買自助購買訂閱的人員，並要求他們 [取消](manage-self-service-purchases-users.md#cancel-a-subscription)。</span><span class="sxs-lookup"><span data-stu-id="3677d-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="3677d-147">接管自助購買訂閱</span><span class="sxs-lookup"><span data-stu-id="3677d-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="3677d-148">您可以接管組織中使用者所做的自助購買訂閱。</span><span class="sxs-lookup"><span data-stu-id="3677d-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="3677d-149">當您接管自助購買訂閱時，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="3677d-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="3677d-150">將使用者移至不同的訂閱，並取消原始的訂閱。</span><span class="sxs-lookup"><span data-stu-id="3677d-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="3677d-151">取消自助購買訂閱，並從指派的使用者中移除授權。</span><span class="sxs-lookup"><span data-stu-id="3677d-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="3677d-152">將使用者移至其他訂閱</span><span class="sxs-lookup"><span data-stu-id="3677d-152">Move users to a different subscription</span></span>

<span data-ttu-id="3677d-153">當您將使用者移至不同的訂閱時，會自動取消舊的訂閱。</span><span class="sxs-lookup"><span data-stu-id="3677d-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="3677d-154">最初購買自助購買訂閱的使用者會收到一封電子郵件，指出訂閱已取消。</span><span class="sxs-lookup"><span data-stu-id="3677d-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="3677d-155">您必須具備您要移動使用者的訂閱中每個使用者的可用授權。</span><span class="sxs-lookup"><span data-stu-id="3677d-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3677d-156">在系統管理中心，移至 [帳單 **]** > [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3677d-157">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** > **產品** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3677d-158">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** > **產品** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="3677d-159">在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="3677d-160">選取您要接管的訂閱。</span><span class="sxs-lookup"><span data-stu-id="3677d-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="3677d-161">在 [訂閱詳細資料] 頁面的 [ **訂閱與設定** ] 區段中，選取 [ **取得此訂閱的控制權**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="3677d-162">在右窗格中，選取 [ **移動使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="3677d-163">選取您要將使用者移至其中的產品，然後選取 [ **移動使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="3677d-164">在 [ **將使用者移至** ] 方塊中，選取 [ **移動使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="3677d-165">移動程式可能需要數分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="3677d-165">The move process might take several minutes.</span></span> <span data-ttu-id="3677d-166">當程式執行時，請勿關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="3677d-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="3677d-167">移動程式完成後，請關閉 [ **移動完成] 窗格**。</span><span class="sxs-lookup"><span data-stu-id="3677d-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="3677d-168">在 [訂閱詳細資料] 頁面上，自助購買之訂閱的 **訂閱狀態** 會顯示為 [ **已刪除**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="3677d-169">取消自助購買訂閱</span><span class="sxs-lookup"><span data-stu-id="3677d-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="3677d-170">當您選擇取消自助購買訂閱時，具有授權的使用者將無法存取產品。</span><span class="sxs-lookup"><span data-stu-id="3677d-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="3677d-171">最初購買自助購買訂閱的使用者會收到一封電子郵件，指出訂閱已取消。</span><span class="sxs-lookup"><span data-stu-id="3677d-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3677d-172">在系統管理中心，移至 [帳單 **]** > [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3677d-173">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **帳單** > **產品** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3677d-174">在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **帳單** > **產品** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3677d-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="3677d-175">在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="3677d-176">選取您要取消的訂閱。</span><span class="sxs-lookup"><span data-stu-id="3677d-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="3677d-177">在 [訂閱詳細資料] 頁面的 [ **訂閱與設定** ] 區段中，選取 [ **取得此訂閱的控制權**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="3677d-178">在右窗格中，選取 [ **取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="3677d-179">從下拉式清單中選取您取消的原因，然後選取 [ **取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="3677d-180">在 [ **您確定要取消嗎？** ] 方塊中，選取 [ **取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="3677d-181">關閉右窗格。</span><span class="sxs-lookup"><span data-stu-id="3677d-181">Close the right pane.</span></span>
9. <span data-ttu-id="3677d-182">在 [訂閱詳細資料] 頁面上， **訂閱狀態** 會顯示為 [ **已刪除**]。</span><span class="sxs-lookup"><span data-stu-id="3677d-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="3677d-183">需要協助？</span><span class="sxs-lookup"><span data-stu-id="3677d-183">Need help?</span></span> <span data-ttu-id="3677d-184">聯繫我們。</span><span class="sxs-lookup"><span data-stu-id="3677d-184">Contact us.</span></span>

<span data-ttu-id="3677d-185">如需有關自助購買的常見問題，請參閱 [自助購買常見問題](self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="3677d-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="3677d-186">如果您有任何問題或需要協助您購買自助服務，請 [與支援人員聯繫](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="3677d-186">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>