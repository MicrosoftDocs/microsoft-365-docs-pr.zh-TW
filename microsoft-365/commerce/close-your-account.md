---
title: 關閉您的帳戶
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 瞭解如何使用 Microsoft 關閉您的帳戶。
ms.openlocfilehash: f399a1ba4d67abf5982c111e9b915f02324150a5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402175"
---
# <a name="close-your-account"></a><span data-ttu-id="067c6-103">關閉您的帳戶</span><span class="sxs-lookup"><span data-stu-id="067c6-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="067c6-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="067c6-104">The admin center is changing.</span></span> <span data-ttu-id="067c6-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="067c6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="067c6-106">當您使用 Microsoft 關閉您的帳戶時，與您的帳戶相關的所有資訊都會被刪除。</span><span class="sxs-lookup"><span data-stu-id="067c6-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="067c6-107">這些資訊包括訂閱、授權、付款方式、使用者及使用者資料。</span><span class="sxs-lookup"><span data-stu-id="067c6-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="067c6-108">開始此程式之前，請務必備份您要保留的任何資料。</span><span class="sxs-lookup"><span data-stu-id="067c6-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="067c6-109">步驟1：刪除使用者</span><span class="sxs-lookup"><span data-stu-id="067c6-109">Step 1: Delete users</span></span>

<span data-ttu-id="067c6-110">刪除除了一個全域管理員之外的所有使用者，該全域管理員完成步驟以關閉帳戶。</span><span class="sxs-lookup"><span data-stu-id="067c6-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="067c6-111">您必須先刪除所有其他使用者，才能在此程式結束之前刪除目錄。</span><span class="sxs-lookup"><span data-stu-id="067c6-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="067c6-112">若使用者從內部部署進行同步處理，請先關閉同步處理，然後使用 Azure 入口網站或 Azure PowerShell Cmdlet 刪除雲端目錄中的使用者。</span><span class="sxs-lookup"><span data-stu-id="067c6-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="067c6-113">若要刪除使用者，請參閱<a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin：刪除一或多個使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="067c6-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="067c6-114">您也可以使用<a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell Cmdlet，成批刪除使用者。</span><span class="sxs-lookup"><span data-stu-id="067c6-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="067c6-115">如果您的組織使用與 Azure AD 同步處理的 Active Directory，請改為刪除 Active Directory 中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="067c6-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="067c6-116">如需相關指示，請參閱<a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">大量刪除 Azure Active Directory 中的使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="067c6-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="067c6-117">步驟2：取消所有作用中的訂閱</span><span class="sxs-lookup"><span data-stu-id="067c6-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="067c6-118">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">產品</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="067c6-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="067c6-119">如果 [訂閱] 清單位於**表格**視圖中，請在右側選取 [**卡片**]。</span><span class="sxs-lookup"><span data-stu-id="067c6-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="067c6-120">尋找作用中的訂閱，並在 [**設定 & 動作**] 區段中，選取 [**取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="067c6-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="067c6-121">遵循提示完成此程式。</span><span class="sxs-lookup"><span data-stu-id="067c6-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="067c6-122">重複步驟1到4，以取消所有作用中的訂閱。</span><span class="sxs-lookup"><span data-stu-id="067c6-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="067c6-123">步驟3：刪除所有已停用的訂閱</span><span class="sxs-lookup"><span data-stu-id="067c6-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="067c6-124">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">產品</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="067c6-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="067c6-125">如果 [訂閱] 清單位於**表格**視圖中，請在右側選取 [**卡片**]。</span><span class="sxs-lookup"><span data-stu-id="067c6-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="067c6-126">選取 [**訂閱狀態**] 旁的 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="067c6-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="067c6-127">尋找停用的訂閱，然後在 [**設定 & 動作**] 區段中，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="067c6-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="067c6-128">在 [**刪除訂閱**] 對話方塊中，選取 [**我瞭解影響**] 核取方塊，然後選取 [**刪除訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="067c6-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="067c6-129">針對每個停用的訂閱重複步驟4和5，直到刪除所有訂閱為止。</span><span class="sxs-lookup"><span data-stu-id="067c6-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="067c6-130">步驟4：停用多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="067c6-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="067c6-131">在系統管理中心中，移至 [**使用者**作用中  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="067c6-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="067c6-132">選擇**多重要素驗證**。</span><span class="sxs-lookup"><span data-stu-id="067c6-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="067c6-133">在 [多重要素驗證] 頁面上，停用您目前所用全域系統管理員帳戶以外的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="067c6-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="067c6-134">您也可以<a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用 PowerShell 來停用多個使用者的多重要素驗證</a>。</span><span class="sxs-lookup"><span data-stu-id="067c6-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="067c6-135">步驟5：刪除 Azure Active Directory 中的目錄</span><span class="sxs-lookup"><span data-stu-id="067c6-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="067c6-136">使用全域系統管理員帳戶登入<a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="067c6-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="067c6-137">選取 [Azure Active Directory]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="067c6-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="067c6-138">切換至您要刪除的目錄。</span><span class="sxs-lookup"><span data-stu-id="067c6-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="067c6-139">選取 [**刪除目錄**]。</span><span class="sxs-lookup"><span data-stu-id="067c6-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="067c6-140">如果您的目錄失敗一或多項檢查，您會看到有關如何傳遞檢查的詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="067c6-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="067c6-141">傳遞所有檢查後，請選取 [**刪除**] 以完成程式。</span><span class="sxs-lookup"><span data-stu-id="067c6-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="067c6-142">完成此最後一個步驟之後，您的 Microsoft 帳戶會關閉並刪除。</span><span class="sxs-lookup"><span data-stu-id="067c6-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
