---
title: 關閉您的帳戶
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: 瞭解如何使用 Microsoft 關閉您的帳戶。
ms.date: 04/02/2021
ms.openlocfilehash: ed73c191063a328490945c54dc2f5101c88f17e8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537292"
---
# <a name="close-your-account"></a><span data-ttu-id="00cf2-103">關閉您的帳戶</span><span class="sxs-lookup"><span data-stu-id="00cf2-103">Close your account</span></span>

<span data-ttu-id="00cf2-104">當您使用 Microsoft 關閉您的帳戶時，與您的帳戶相關的所有資訊都會被刪除。</span><span class="sxs-lookup"><span data-stu-id="00cf2-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="00cf2-105">這些資訊包括訂閱、授權、付款方式、使用者及使用者資料。</span><span class="sxs-lookup"><span data-stu-id="00cf2-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="00cf2-106">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="00cf2-106">Before you begin</span></span>

<span data-ttu-id="00cf2-107">開始此程序之前，請務必備份任何您想保留的資料。</span><span class="sxs-lookup"><span data-stu-id="00cf2-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="00cf2-108">您必須是全域或計費管理員，才能執行本文所述的工作。</span><span class="sxs-lookup"><span data-stu-id="00cf2-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="00cf2-109">如需詳細資訊，請參閱[關於系統管理員角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="00cf2-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="00cf2-110">步驟1：刪除使用者</span><span class="sxs-lookup"><span data-stu-id="00cf2-110">Step 1: Delete users</span></span>

<span data-ttu-id="00cf2-111">除了一個全域管理員之外，刪除所有使用者。</span><span class="sxs-lookup"><span data-stu-id="00cf2-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="00cf2-112">全域管理員完成步驟以關閉帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cf2-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="00cf2-113">您必須先刪除所有其他使用者，才能在此程式結束之前刪除目錄。</span><span class="sxs-lookup"><span data-stu-id="00cf2-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="00cf2-114">若使用者從內部部署進行同步處理，請先關閉同步處理，然後使用 Azure 入口網站或 Azure PowerShell Cmdlet 刪除雲端目錄中的使用者。</span><span class="sxs-lookup"><span data-stu-id="00cf2-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="00cf2-115">若要刪除使用者，請參閱 [User management admin：刪除一或多個使用者](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)。</span><span class="sxs-lookup"><span data-stu-id="00cf2-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="00cf2-116">您也可以使用 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell Cmdlet，成批刪除使用者。</span><span class="sxs-lookup"><span data-stu-id="00cf2-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="00cf2-117">如果您的組織使用與 Microsoft Azure Active Directory (Azure AD) 同步處理的 Active Directory，請改為從 Active directory 中刪除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cf2-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="00cf2-118">如需相關指示，請參閱[大量刪除使用者的 Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete)。</span><span class="sxs-lookup"><span data-stu-id="00cf2-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="00cf2-119">步驟2：取消所有作用中的訂閱</span><span class="sxs-lookup"><span data-stu-id="00cf2-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="00cf2-120">在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="00cf2-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="00cf2-121">在 [ **產品** ] 索引標籤上，尋找使用中的訂閱。</span><span class="sxs-lookup"><span data-stu-id="00cf2-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="00cf2-122">選取 [ (更多動作) ] 的三個點，然後選取 [ **取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="00cf2-122">Select the three dots (more actions), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="00cf2-123">在 **取消訂閱** 窗格中，選擇取消的原因。</span><span class="sxs-lookup"><span data-stu-id="00cf2-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="00cf2-124">您也可以選擇提供任何意見反應。</span><span class="sxs-lookup"><span data-stu-id="00cf2-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="00cf2-125">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="00cf2-125">Select **Save**.</span></span>
5. <span data-ttu-id="00cf2-126">重複步驟1到4，以取消所有作用中的訂閱。</span><span class="sxs-lookup"><span data-stu-id="00cf2-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="00cf2-127">步驟3：刪除所有已停用的訂閱</span><span class="sxs-lookup"><span data-stu-id="00cf2-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="00cf2-128">在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="00cf2-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="00cf2-129">在 [ **產品** ] 索引標籤上，選取停用的訂閱。</span><span class="sxs-lookup"><span data-stu-id="00cf2-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="00cf2-130">在 [訂閱詳細資料] 頁面上，選取 [ **訂閱和付款設定** ] 區段中的 [ **刪除訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="00cf2-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="00cf2-131">在 [ **刪除訂閱** ] 窗格中，選取 [ **刪除訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="00cf2-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="00cf2-132">在 [ **刪除訂閱** ] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="00cf2-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="00cf2-133">針對每個停用的訂閱，重複步驟3到5，直到刪除所有訂閱為止。</span><span class="sxs-lookup"><span data-stu-id="00cf2-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="00cf2-134">如果您無法立即刪除停用的訂閱， [請與支援人員聯繫](../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="00cf2-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="00cf2-135">步驟4：停用多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="00cf2-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="00cf2-136">使用全域系統管理員帳戶登入系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="00cf2-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="00cf2-137">若要確認您擁有的角色，請參閱 [檢查組織中的系統管理員角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="00cf2-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="00cf2-138">移至 [**使用者** 作用中  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="00cf2-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="00cf2-139">選擇 **多重要素驗證**。</span><span class="sxs-lookup"><span data-stu-id="00cf2-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="00cf2-140">在 [多重要素驗證] 頁面上，停用您目前所用全域系統管理員帳戶以外的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="00cf2-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="00cf2-141">您也可以 [使用 PowerShell 來停用多個使用者的多重要素驗證](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="00cf2-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="00cf2-142">步驟5：在 Azure Active Directory 中刪除目錄</span><span class="sxs-lookup"><span data-stu-id="00cf2-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="00cf2-143">使用全域系統管理員帳戶登入 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 系統管理中心</a> 。</span><span class="sxs-lookup"><span data-stu-id="00cf2-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="00cf2-144">選取 **[Azure Active Directory]**。</span><span class="sxs-lookup"><span data-stu-id="00cf2-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="00cf2-145">切換至您要刪除的組織。</span><span class="sxs-lookup"><span data-stu-id="00cf2-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="00cf2-146">選取 [ **刪除租** 使用者]。</span><span class="sxs-lookup"><span data-stu-id="00cf2-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="00cf2-147">如果您的組織未通過一或多項檢查，您會看到有關如何傳遞檢查的詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="00cf2-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="00cf2-148">傳遞所有檢查後，請選取 [ **刪除** ] 以完成程式。</span><span class="sxs-lookup"><span data-stu-id="00cf2-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="00cf2-149">完成此最後一個步驟之後，您的 Microsoft 帳戶會關閉並刪除。</span><span class="sxs-lookup"><span data-stu-id="00cf2-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
