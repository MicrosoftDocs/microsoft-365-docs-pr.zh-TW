---
title: 管理付款方式
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
ms.reviewer: jamitche
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 系統管理中心管理您的付款方式。
ms.date: 04/02/2021
ms.openlocfilehash: 4b35b7b8e874915e5f9c792686ff0e368292c802
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107036"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="3add3-103">管理付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-103">Manage payment methods</span></span>

<span data-ttu-id="3add3-104">向 Microsoft 購買商務產品或服務時，您可以使用現有的付款方式，或新增付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-104">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="3add3-105">您可以使用信用卡或轉帳卡，或是銀行帳戶來支付購買的項目。</span><span class="sxs-lookup"><span data-stu-id="3add3-105">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="3add3-106">如果您的商務帳戶有帳單設定檔，且您是帳單設定檔擁有者或帳單設定檔參與者，則可以使用支援信用卡或發票付款的帳單設定檔來購買或支付帳單。</span><span class="sxs-lookup"><span data-stu-id="3add3-106">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="3add3-107">如果您是帳單發票管理員，則只能使用帳單設定檔來支付帳單。</span><span class="sxs-lookup"><span data-stu-id="3add3-107">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="3add3-108">若要深入了解帳單設定檔和角色，請參閱[管理帳單設定檔](manage-billing-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="3add3-108">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="3add3-p103">如果您的商務帳戶沒有帳單設定檔，任何全域或計費系統管理員都可以管理和使用新增到商務帳戶的任何銀行帳戶。不過，您僅能管理或使用您新增的信用卡。</span><span class="sxs-lookup"><span data-stu-id="3add3-p103">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account. However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="3add3-111">使用銀行帳戶付款的選項不適用於部分國家或地區。</span><span class="sxs-lookup"><span data-stu-id="3add3-111">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="3add3-112">您必須使用與您租用戶相同的國家/地區發出的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-112">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3add3-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="3add3-113">Before you begin</span></span>

<span data-ttu-id="3add3-114">您必須是全域或計費管理員，才能執行本文所述的工作。</span><span class="sxs-lookup"><span data-stu-id="3add3-114">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="3add3-115">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3add3-115">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="3add3-116">新增付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-116">Add a payment method</span></span>

<span data-ttu-id="3add3-117">新增付款方式不會將任何訂閱與它相關聯。</span><span class="sxs-lookup"><span data-stu-id="3add3-117">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="3add3-118">若要將單一訂閱指派給付款方式，請參閱[變更單一訂閱的付款方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="3add3-118">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="3add3-119">若要以新的付款方式取代使用另一種付款方式的所有訂閱，請參閱[取代付款方式](#replace-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="3add3-119">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

1. <span data-ttu-id="3add3-120">在系統管理中心中，移至 [帳單 **]**  >  [帳單與付款 **]**  >  [付款方式 <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3add3-120">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="3add3-121">選取 [新增付款方式]。</span><span class="sxs-lookup"><span data-stu-id="3add3-121">Select **Add a payment method**.</span></span>
3. <span data-ttu-id="3add3-122">在 [付款方式] 頁面上，從下拉式功能表選取付款方法。</span><span class="sxs-lookup"><span data-stu-id="3add3-122">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>
4. <span data-ttu-id="3add3-123">輸入新卡片或銀行帳戶的相關資訊，然後選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-123">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="3add3-124">更新付款方式詳細資料</span><span class="sxs-lookup"><span data-stu-id="3add3-124">Update payment method details</span></span>

<span data-ttu-id="3add3-125">您可以變更現有付款方式的信用卡或轉帳卡的名稱、帳單地址或到期日。</span><span class="sxs-lookup"><span data-stu-id="3add3-125">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="3add3-126">不過，您無法變更信用卡或帳戶號碼。</span><span class="sxs-lookup"><span data-stu-id="3add3-126">However, you can't change the card or account number.</span></span> <span data-ttu-id="3add3-127">如果帳戶號碼已變更，請[將其以不同付款方式取代](#replace-a-payment-method)，然後[刪除舊的付款方式](#delete-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="3add3-127">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="3add3-128">在系統管理中心中，移至 [帳單] > [帳單與付款] > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="3add3-128">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="3add3-129">選取付款方式資料列以進行更新。</span><span class="sxs-lookup"><span data-stu-id="3add3-129">Select the row of the payment method to update.</span></span> <span data-ttu-id="3add3-130">在右窗格中，選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-130">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="3add3-131">更新您的付款方式資訊，包括信用卡或轉帳卡上的名稱、帳單地址或到期日，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-131">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="3add3-132">取代付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-132">Replace a payment method</span></span>

<span data-ttu-id="3add3-133">取代付款方式時，會針對使用相同付款方式的所有訂閱和帳單設定檔取代它。</span><span class="sxs-lookup"><span data-stu-id="3add3-133">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="3add3-134">取代付款方式不會刪除現有的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-134">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="3add3-135">該方式仍可供選取並用於其他訂閱和帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="3add3-135">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="3add3-136">若要變更單一訂閱的付款方式，請參閱[變更單一訂閱的付款方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="3add3-136">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="3add3-137">在系統管理中心中，移至 [帳單] > [帳單與付款] > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="3add3-137">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="3add3-138">選取付款方式資料列以進行取代。</span><span class="sxs-lookup"><span data-stu-id="3add3-138">Select the row of the payment method to replace.</span></span> <span data-ttu-id="3add3-139">右側窗格會列出所有帳單設定檔，以及使用所選付款方式的個別訂閱。</span><span class="sxs-lookup"><span data-stu-id="3add3-139">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="3add3-140">在右側窗格中，選取 [取代所有項目的付款方式]。</span><span class="sxs-lookup"><span data-stu-id="3add3-140">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="3add3-141">若要使用現有的付款方式，請從下拉式清單中選擇一個付款方式，然後選取 [取代]。</span><span class="sxs-lookup"><span data-stu-id="3add3-141">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="3add3-142">如果您有與帳單設定檔相關的訂閱，只能使用信用卡或轉帳卡付款。</span><span class="sxs-lookup"><span data-stu-id="3add3-142">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="3add3-143">如果您的銀行帳戶列在 [付款方式] 頁面上，則無法在下拉式清單中選取。</span><span class="sxs-lookup"><span data-stu-id="3add3-143">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>
5. <span data-ttu-id="3add3-144">若要新增新的付款方式，請選取 [新增付款方式]。</span><span class="sxs-lookup"><span data-stu-id="3add3-144">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="3add3-145">在 [新增付款方式] 窗格中，輸入帳戶資訊，然後選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="3add3-145">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="3add3-146">您使用的付款方式必須與您租用戶的國家/地區相同。</span><span class="sxs-lookup"><span data-stu-id="3add3-146">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="3add3-147">已在下拉式清單中選取新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-147">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="3add3-148">選取 [取代]。</span><span class="sxs-lookup"><span data-stu-id="3add3-148">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="3add3-149">變更單一訂閱的付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-149">Change a payment method for a single subscription</span></span>

<span data-ttu-id="3add3-150">您可以變更用來支付單一訂閱的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-150">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="3add3-151">在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3add3-151">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="3add3-152">在 [產品 **]** 索引標籤上，尋找您想要以其他付款方式支付的訂閱。</span><span class="sxs-lookup"><span data-stu-id="3add3-152">On the **Products** tab, find the subscription that you want to pay for with the alternate payment method.</span></span>
3. <span data-ttu-id="3add3-153">選取 [其他動作 **]** (三個點)，然後選取 [取代付款方式 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-153">Select **More actions** (three dots), then select **Replace payment method**.</span></span>
4. <span data-ttu-id="3add3-154">在 [取代付款方式 **]** 窗格中，從下拉式清單選擇其他付款方式，或選擇新增付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-154">In the **Replace payment method** pane, from the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
5. <span data-ttu-id="3add3-155">如果您新增付款方式，請輸入信用卡或帳戶詳細資料，然後選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-155">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
6. <span data-ttu-id="3add3-156">確認選取的付款方式正確無誤，然後選取 [取代 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-156">Verify that the selected payment method is correct, then select **Replace**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="3add3-157">刪除付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-157">Delete a payment method</span></span>

<span data-ttu-id="3add3-158">您只可以刪除未與訂閱或帳單設定檔連結的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-158">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="3add3-159">這適用於所有訂閱，而無論其狀態如何。</span><span class="sxs-lookup"><span data-stu-id="3add3-159">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="3add3-160">刪除未連結訂閱或帳單設定檔的付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-160">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="3add3-161">如果某個付款方式沒有與任何訂閱或帳單設定檔相關聯，您可以立即將其刪除。</span><span class="sxs-lookup"><span data-stu-id="3add3-161">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="3add3-162">在系統管理中心中，移至 [帳單 **]**  >  [帳單與付款 **]**  >  [付款方式 <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3add3-162">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="3add3-163">尋找要刪除的付款方式，選取三個點，然後選取 [刪除 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-163">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="3add3-164">在右窗格底部，選取 [刪除 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-164">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="3add3-165">刪除已連結訂閱或帳單設定檔的付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-165">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="3add3-166">如果某個付款方式已與任何訂閱或帳單設定檔連結，請先以現有的付款方式取代它，或新增付款方式，然後刪除舊的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-166">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="3add3-167">在系統管理中心中，移至 [帳單 **]**  >  [帳單與付款 **]**  >  [付款方式 <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3add3-167">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="3add3-168">選取要刪除的付款方式列。</span><span class="sxs-lookup"><span data-stu-id="3add3-168">Select the row for the payment method to delete.</span></span> <span data-ttu-id="3add3-169">右窗格會列出使用該付款方式的現有訂閱。</span><span class="sxs-lookup"><span data-stu-id="3add3-169">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="3add3-170">在右窗格中，選取 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-170">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="3add3-171">若要使用現有的付款方式，請從下拉式清單中選擇一個付款方式，選取 [下一步 **]**，然後選取 [刪除 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-171">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="3add3-172">如果您有與帳單設定檔相關的訂閱，只能使用卡片或轉帳卡付款。</span><span class="sxs-lookup"><span data-stu-id="3add3-172">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="3add3-173">如果您的銀行帳戶列在 [付款方式 **]** 頁面上，則無法在下拉式清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="3add3-173">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="3add3-174">若要新增新的付款方式，請選取 [新增付款方式 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-174">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="3add3-175">選擇您要新增的付款方式類型，輸入帳戶資訊，然後選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-175">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="3add3-176">已在下拉式清單中選取新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-176">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="3add3-177">選取 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-177">Select **Next**.</span></span>
8. <span data-ttu-id="3add3-178">選取 [刪除 **]**。</span><span class="sxs-lookup"><span data-stu-id="3add3-178">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="3add3-179">疑難排解付款方式</span><span class="sxs-lookup"><span data-stu-id="3add3-179">Troubleshoot payment methods</span></span>

| <span data-ttu-id="3add3-180">問題</span><span class="sxs-lookup"><span data-stu-id="3add3-180">Issue</span></span> | <span data-ttu-id="3add3-181">疑難排解步驟</span><span class="sxs-lookup"><span data-stu-id="3add3-181">Troubleshooting steps</span></span> |
|:----------|:-----|
|<span data-ttu-id="3add3-182">**我收到錯誤訊息指出「瀏覽器目前的設定為封鎖 Cookie」。**</span><span class="sxs-lookup"><span data-stu-id="3add3-182">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="3add3-183">將您的瀏覽器設為允許第三方 Cookie，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="3add3-183">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="3add3-184">**我的信用卡或轉帳卡遭到拒絕。**</span><span class="sxs-lookup"><span data-stu-id="3add3-184">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="3add3-185">如果您使用信用卡或轉帳卡付款，但信用卡遭到拒絕，您會收到一封電子郵件，指出 Microsoft 無法處理付款。</span><span class="sxs-lookup"><span data-stu-id="3add3-185">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="3add3-186">仔細檢查顯示的信用卡詳細資料&mdash;信用卡卡號、到期日、信用卡上的名稱，以及包括省/市、縣/市和郵遞區號在內的地址&mdash;與信用卡和帳單上顯示的資料完全相同。</span><span class="sxs-lookup"><span data-stu-id="3add3-186">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="3add3-187">您可以使用訂閱詳細資料頁面的 [帳單 **]** 區段的 [結算餘額 **]** 連結，更新您的卡片資訊並立即提交付款。</span><span class="sxs-lookup"><span data-stu-id="3add3-187">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="3add3-188">如需詳細資訊，請參閱[如果我有未付餘額，該怎麼辦？](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span><span class="sxs-lookup"><span data-stu-id="3add3-188">For more information, see [What if I have an outstanding balance?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span></span>  <br/><br/>  <span data-ttu-id="3add3-p118">如果您持續看到「被拒絕」訊息，請連絡您的銀行。可能您的卡片未生效。如果您最近收到郵寄的卡片已更新到期日，請確定該卡片已生效。您的銀行也可以告知您，您的卡片是否獲核准進行線上、國際或週期性交易。</span><span class="sxs-lookup"><span data-stu-id="3add3-p118">If you continue to see the "declined" message, contact your bank. It's possible that your card isn't active. If you recently received the card in the mail with an updated expiration date, make sure it's activated. Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="3add3-193">**我想要更新信用卡或銀行帳戶號碼。**</span><span class="sxs-lookup"><span data-stu-id="3add3-193">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="3add3-194">您無法變更現有付款方式的信用卡或帳戶號碼。</span><span class="sxs-lookup"><span data-stu-id="3add3-194">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="3add3-195">如果您的信用卡或帳戶號碼已變更，請[以不同的付款方式取代它](#replace-a-payment-method)，這會將所有作用中的訂閱從該付款方式移至新的付款方式，然後[刪除舊的付款方式](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。</span><span class="sxs-lookup"><span data-stu-id="3add3-195">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="3add3-196">**我的帳戶只有一張信用卡或一個銀行帳戶，而我想移除它。**</span><span class="sxs-lookup"><span data-stu-id="3add3-196">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="3add3-197">如果您只有一個付款方式，您必須[將它以新的付款方式取代](#replace-a-payment-method)，之後才能刪除它。</span><span class="sxs-lookup"><span data-stu-id="3add3-197">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="3add3-198">**我無法新增我的卡片或銀行帳戶。**</span><span class="sxs-lookup"><span data-stu-id="3add3-198">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="3add3-199">您必須使用與您租用戶相同的國家/地區發出的付款方式。</span><span class="sxs-lookup"><span data-stu-id="3add3-199">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="3add3-200">如果您無法輸入您的卡片或銀行帳戶資訊，您可以[連絡客戶支援](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="3add3-200">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-content"></a><span data-ttu-id="3add3-201">相關內容</span><span class="sxs-lookup"><span data-stu-id="3add3-201">Related content</span></span>

<span data-ttu-id="3add3-202">[支付您的商務訂閱費用](pay-for-your-subscription.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="3add3-202">[Pay for your business subscription](pay-for-your-subscription.md) (article)</span></span>\
<span data-ttu-id="3add3-203">[管理帳單設定檔](manage-billing-profiles.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="3add3-203">[Manage billing profiles](manage-billing-profiles.md) (article)</span></span>\
<span data-ttu-id="3add3-204">[變更計費頻率](change-payment-frequency.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="3add3-204">[Change your billing frequency](change-payment-frequency.md) (article)</span></span>