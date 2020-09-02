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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: 瞭解如何在 Microsoft 365 系統管理中心中管理您的支付方式。
ms.date: ''
ms.openlocfilehash: 81c7509fb2f3be982890ec6b68dafb83ff0c1876
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324231"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="97994-103">管理付款方式</span><span class="sxs-lookup"><span data-stu-id="97994-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="97994-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="97994-104">The admin center is changing.</span></span> <span data-ttu-id="97994-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="97994-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="97994-106">當您從 Microsoft 購買商務產品或服務時，您可以使用現有的付款條件，也可以新增一個新的付款條件。</span><span class="sxs-lookup"><span data-stu-id="97994-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="97994-107">您可以使用信用卡或轉帳卡或銀行帳戶支付您購買的物品。</span><span class="sxs-lookup"><span data-stu-id="97994-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="97994-108">如果您的企業帳戶具有帳單設定檔，且您是計費設定檔擁有人或計費設定檔參與者，您可以使用信用卡或發票付款所支援的帳單設定檔，以購買或支付鈔票。</span><span class="sxs-lookup"><span data-stu-id="97994-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="97994-109">如果您是計費發票管理員，您只能使用計費設定檔來支付帳單。</span><span class="sxs-lookup"><span data-stu-id="97994-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="97994-110">若要深入瞭解計費設定檔和角色，請參閱 [管理帳單設定檔](manage-billing-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="97994-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="97994-111">如果您的公司帳戶沒有帳單設定檔，任何全域或計費系統管理員都可以管理和使用任何新增至商務帳戶的銀行帳戶。</span><span class="sxs-lookup"><span data-stu-id="97994-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="97994-112">不過，您只能管理或使用您新增的信用卡。</span><span class="sxs-lookup"><span data-stu-id="97994-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="97994-113">在某些國家或地區無法使用以銀行帳戶付款的選項。</span><span class="sxs-lookup"><span data-stu-id="97994-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="97994-114">您必須使用與租使用者相同國家/地區所簽發的支付方式。</span><span class="sxs-lookup"><span data-stu-id="97994-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="97994-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="97994-115">Before you begin</span></span>

<span data-ttu-id="97994-116">您必須是全球或計費系統管理員，才可執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="97994-116">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="97994-117">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="97994-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="97994-118">新增付款方式</span><span class="sxs-lookup"><span data-stu-id="97994-118">Add a payment method</span></span>

<span data-ttu-id="97994-119">新增支付方式並不會將任何訂閱關聯。</span><span class="sxs-lookup"><span data-stu-id="97994-119">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="97994-120">若要指派單一訂閱給支付方式，請參閱 [變更單一訂閱的付款條件](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="97994-120">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="97994-121">若要以新的付款條件取代所有使用另一種付款條件的訂閱，請參閱 [取代支付方式](#replace-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="97994-121">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

1. <span data-ttu-id="97994-122">在系統管理中心中，移至**帳單**  >  **& 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="97994-122">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="97994-123">選取 [新增付款方式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97994-123">Select **Add a payment method**.</span></span>
3. <span data-ttu-id="97994-124">在 [付款方式]\*\*\*\* 頁面上，從下拉式功能表選取付款方法。</span><span class="sxs-lookup"><span data-stu-id="97994-124">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>
4. <span data-ttu-id="97994-125">輸入新卡片或銀行帳戶的資訊，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="97994-125">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="97994-126">更新支付方式詳細資料</span><span class="sxs-lookup"><span data-stu-id="97994-126">Update payment method details</span></span>

<span data-ttu-id="97994-127">您可以變更現有支付方式的信用卡或借方卡、帳單位址或到期日的名稱。</span><span class="sxs-lookup"><span data-stu-id="97994-127">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="97994-128">不過，您無法變更信用卡或帳戶號碼。</span><span class="sxs-lookup"><span data-stu-id="97994-128">However, you can't change the card or account number.</span></span> <span data-ttu-id="97994-129">如果帳戶號碼已變更，請 [使用不同的付款條件取代它](#replace-a-payment-method)，然後再 [刪除舊的](#delete-a-payment-method)帳戶號碼。</span><span class="sxs-lookup"><span data-stu-id="97994-129">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="97994-130">在系統管理中心中，移至**帳單**  >  **& 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="97994-130">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="97994-131">選取要更新之付款條件的列。</span><span class="sxs-lookup"><span data-stu-id="97994-131">Select the row of the payment method to update.</span></span> <span data-ttu-id="97994-132">在右窗格中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="97994-132">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="97994-133">更新您的付款條件資訊，包括信用卡或借方卡上的名稱、帳單位址或到期日，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="97994-133">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="97994-134">取代支付方式</span><span class="sxs-lookup"><span data-stu-id="97994-134">Replace a payment method</span></span>

<span data-ttu-id="97994-135">當您取代付款條件時，您會將其更換為使用相同付款條件的所有訂閱和計費設定檔。</span><span class="sxs-lookup"><span data-stu-id="97994-135">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="97994-136">若要取代支付方式，不會刪除現有的支付方式。</span><span class="sxs-lookup"><span data-stu-id="97994-136">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="97994-137">仍可供您選取和使用其他訂閱和計費設定檔。</span><span class="sxs-lookup"><span data-stu-id="97994-137">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="97994-138">若要變更單一訂閱的付款條件，請參閱 [變更單一訂閱的支付方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="97994-138">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="97994-139">在系統管理中心中，移至**帳單**  >  **& 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="97994-139">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="97994-140">選取要取代的付款條件列。</span><span class="sxs-lookup"><span data-stu-id="97994-140">Select the row of the payment method to replace.</span></span> <span data-ttu-id="97994-141">右窗格會列出所有記帳設定檔，以及使用所選付款條件的個別訂閱。</span><span class="sxs-lookup"><span data-stu-id="97994-141">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="97994-142">在右窗格中，選取 [ **取代所有專案的支付方式**]。</span><span class="sxs-lookup"><span data-stu-id="97994-142">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="97994-143">若要使用現有的付款條件，請從下拉式清單中選擇一個，然後選取 [ **取代**]。</span><span class="sxs-lookup"><span data-stu-id="97994-143">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="97994-144">如果您有與帳單設定檔相關聯的訂閱，則只能使用信用或轉帳卡支付費用。</span><span class="sxs-lookup"><span data-stu-id="97994-144">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="97994-145">如果您已在 [ **付款條件** ] 頁面上列出銀行帳戶，則無法從下拉式清單中選取。</span><span class="sxs-lookup"><span data-stu-id="97994-145">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>
5. <span data-ttu-id="97994-146">若要新增支付方式，請選取 [ **新增支付方式**]。</span><span class="sxs-lookup"><span data-stu-id="97994-146">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="97994-147">在 [ **新增支付方式** ] 窗格中，輸入帳戶資訊，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="97994-147">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="97994-148">您必須使用與租使用者相同國家/地區的支付方式。</span><span class="sxs-lookup"><span data-stu-id="97994-148">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="97994-149">已在下拉式清單中選取新的付款條件。</span><span class="sxs-lookup"><span data-stu-id="97994-149">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="97994-150">選取 [取代]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97994-150">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="97994-151">變更單一訂閱的支付方式</span><span class="sxs-lookup"><span data-stu-id="97994-151">Change a payment method for a single subscription</span></span>

<span data-ttu-id="97994-152">您可以變更用來支付單一訂閱的支付方式。</span><span class="sxs-lookup"><span data-stu-id="97994-152">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="97994-153">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">產品</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="97994-153">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="97994-154">在 [ **產品** ] 索引標籤上，尋找您要使用其他支付方式支付的訂閱。</span><span class="sxs-lookup"><span data-stu-id="97994-154">On the **Products** tab, find the subscription that you want to pay for with the alternate payment method.</span></span>
3. <span data-ttu-id="97994-155">選取 [ **其他動作** (三點) ]，然後選取 [ **取代支付方式**]。</span><span class="sxs-lookup"><span data-stu-id="97994-155">Select **More actions** (three dots), then select **Replace payment method**.</span></span>
4. <span data-ttu-id="97994-156">在 [ **取代支付方式** ] 窗格的下拉式清單中，選擇另一個付款條件，或選擇新增支付方式。</span><span class="sxs-lookup"><span data-stu-id="97994-156">In the **Replace payment method** pane, from the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
5. <span data-ttu-id="97994-157">如果您新增付款條件，請輸入名片或帳戶詳細資料，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="97994-157">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
6. <span data-ttu-id="97994-158">請確認選取的支付方式正確，然後選取 [ **取代**]。</span><span class="sxs-lookup"><span data-stu-id="97994-158">Verify that the selected payment method is correct, then select **Replace**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="97994-159">刪除付款條件</span><span class="sxs-lookup"><span data-stu-id="97994-159">Delete a payment method</span></span>

<span data-ttu-id="97994-160">您只可刪除未附加至訂閱或計費設定檔的付款條件。</span><span class="sxs-lookup"><span data-stu-id="97994-160">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="97994-161">這適用于所有的訂閱，不論其狀態。</span><span class="sxs-lookup"><span data-stu-id="97994-161">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="97994-162">刪除未附加任何訂閱或計費設定檔的支付方式</span><span class="sxs-lookup"><span data-stu-id="97994-162">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="97994-163">如果付款條件沒有關聯任何訂閱或計費設定檔，您可以立即將其刪除。</span><span class="sxs-lookup"><span data-stu-id="97994-163">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="97994-164">在系統管理中心中，移至**帳單**  >  **& 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="97994-164">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="97994-165">尋找要刪除的支付方式，選取三個點，然後選取 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="97994-165">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="97994-166">在右窗格的底部，選取 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="97994-166">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="97994-167">刪除附加有訂閱或計費設定檔的支付方式</span><span class="sxs-lookup"><span data-stu-id="97994-167">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="97994-168">如果支付方式附加至任何訂閱或計費設定檔，請先將其取代為現有的付款條件，或新增新的付款條件，然後再刪除舊的支付方式。</span><span class="sxs-lookup"><span data-stu-id="97994-168">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="97994-169">在系統管理中心中，移至**帳單**  >  **& 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="97994-169">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="97994-170">選取要刪除之付款條件的列。</span><span class="sxs-lookup"><span data-stu-id="97994-170">Select the row for the payment method to delete.</span></span> <span data-ttu-id="97994-171">右窗格會列出使用該支付方式的現有訂閱。</span><span class="sxs-lookup"><span data-stu-id="97994-171">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="97994-172">在右窗格中，選取 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="97994-172">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="97994-173">若要使用現有的付款條件，請從下拉式清單中選擇一個，然後選取 **[下一步]**，然後選取 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="97994-173">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="97994-174">如果您有與帳單設定檔相關聯的訂閱，則只能使用信用卡支付。</span><span class="sxs-lookup"><span data-stu-id="97994-174">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="97994-175">如果您已在 [ **付款條件** ] 頁面上列出銀行帳戶，則不能在下拉式清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="97994-175">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="97994-176">若要新增支付方式，請選取 [ **新增支付方式**]。</span><span class="sxs-lookup"><span data-stu-id="97994-176">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="97994-177">選擇您要新增的付款條件類型、輸入帳戶資訊，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="97994-177">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="97994-178">已在下拉式清單中選取新的付款條件。</span><span class="sxs-lookup"><span data-stu-id="97994-178">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="97994-179">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97994-179">Select **Next**.</span></span>
8. <span data-ttu-id="97994-180">選取 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97994-180">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="97994-181">針對付款方式進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="97994-181">Troubleshoot payment methods</span></span>

|<span data-ttu-id="97994-182">**問題**</span><span class="sxs-lookup"><span data-stu-id="97994-182">**Issue**</span></span>|<span data-ttu-id="97994-183">**疑難排解步驟**</span><span class="sxs-lookup"><span data-stu-id="97994-183">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="97994-184">**我收到錯誤訊息，指出：「瀏覽器目前設定為封鎖 cookie」。**</span><span class="sxs-lookup"><span data-stu-id="97994-184">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="97994-185">將您的瀏覽器設為允許協力廠商 Cookie，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="97994-185">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="97994-186">**我的信用卡或轉帳卡遭到拒絕。**</span><span class="sxs-lookup"><span data-stu-id="97994-186">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="97994-187">如果您是以信用卡或轉帳卡支付，而且您的卡遭到拒絕，您會收到一封電子郵件，指出 Microsoft 無法處理付款。</span><span class="sxs-lookup"><span data-stu-id="97994-187">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="97994-188">請仔細檢查卡詳細資料 &mdash; 卡號碼、到期日、卡片上的名稱，以及位址（包括城市、州及郵遞區號）， &mdash; 是否與您在卡片和您的報表上的顯示方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="97994-188">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="97994-189">您可以使用 [訂閱詳細資料] 頁面的 [**帳單**] 區段中的 [**結算餘額**] 連結，更新您的卡片資訊，並立即送出付款。</span><span class="sxs-lookup"><span data-stu-id="97994-189">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="97994-190">如需詳細資訊，請參閱 [什麼是我的信用卡遭到拒絕和付款逾期到期？](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="97994-190">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="97994-191">如果還是繼續看到 [拒絕] 訊息，請連絡您的銀行。</span><span class="sxs-lookup"><span data-stu-id="97994-191">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="97994-192">您的卡片可能不是使用中。</span><span class="sxs-lookup"><span data-stu-id="97994-192">It's possible that your card isn't active.</span></span> <span data-ttu-id="97994-193">如果您最近在具有更新到期日的郵件中收到卡片，請確定已啟用。</span><span class="sxs-lookup"><span data-stu-id="97994-193">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="97994-194">您的銀行也可告訴您，您的卡片是否未獲批准線上、國際或週期性交易。</span><span class="sxs-lookup"><span data-stu-id="97994-194">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="97994-195">**我想更新卡或銀行帳戶號碼。**</span><span class="sxs-lookup"><span data-stu-id="97994-195">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="97994-196">您無法變更現有支付方式上的信用卡或帳號。</span><span class="sxs-lookup"><span data-stu-id="97994-196">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="97994-197">如果您的卡或帳號已變更，請 [使用不同的付款條件取代它](#replace-a-payment-method)，以將所有使用中的訂閱從付款條件移至新的付款條件，然後 [刪除舊的付款條件](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。</span><span class="sxs-lookup"><span data-stu-id="97994-197">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="97994-198">**我的帳戶上只有一個卡或銀行帳戶，而且我想要將它移除。**</span><span class="sxs-lookup"><span data-stu-id="97994-198">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="97994-199">如果您只有一個付款條件，您必須先將 [它取代為新的付款條件](#replace-a-payment-method) ，才能將它刪除。</span><span class="sxs-lookup"><span data-stu-id="97994-199">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="97994-200">**我無法新增我的卡或銀行帳戶。**</span><span class="sxs-lookup"><span data-stu-id="97994-200">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="97994-201">您必須使用與租使用者相同國家/地區所簽發的支付方式。</span><span class="sxs-lookup"><span data-stu-id="97994-201">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="97994-202">如果您無法輸入名片或銀行帳戶資訊，可以 [聯繫支援](../../admin/contact-support-for-business-products.md)人員。</span><span class="sxs-lookup"><span data-stu-id="97994-202">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-content"></a><span data-ttu-id="97994-203">相關內容</span><span class="sxs-lookup"><span data-stu-id="97994-203">Related content</span></span>

<span data-ttu-id="97994-204">[支付您的商務訂閱](pay-for-your-subscription.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="97994-204">[Pay for your business subscription](pay-for-your-subscription.md) (article)</span></span>\
<span data-ttu-id="97994-205">[管理帳單設定檔](manage-billing-profiles.md) (篇文章) </span><span class="sxs-lookup"><span data-stu-id="97994-205">[Manage billing profiles](manage-billing-profiles.md) (article)</span></span>\
<span data-ttu-id="97994-206">[變更您的帳單頻率](change-payment-frequency.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="97994-206">[Change your billing frequency](change-payment-frequency.md) (article)</span></span>