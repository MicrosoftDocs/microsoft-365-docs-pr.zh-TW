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
ms.custom: ''
search.appverid:
- MET150
description: 瞭解如何使用 Microsoft 關閉您的帳戶。
ms.openlocfilehash: 43ec3fe2eedc354c0494818f97b01e8de63694c7
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045773"
---
# <a name="close-your-account"></a><span data-ttu-id="ecddb-103">關閉您的帳戶</span><span class="sxs-lookup"><span data-stu-id="ecddb-103">Close your account</span></span>

<span data-ttu-id="ecddb-104">當您使用 Microsoft 關閉您的帳戶時，與您的帳戶相關的所有資訊都會被刪除。</span><span class="sxs-lookup"><span data-stu-id="ecddb-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="ecddb-105">這些資訊包括訂閱、授權、付款方式、使用者及使用者資料。</span><span class="sxs-lookup"><span data-stu-id="ecddb-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="ecddb-106">開始此程式之前，請務必備份您要保留的任何資料。</span><span class="sxs-lookup"><span data-stu-id="ecddb-106">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="ecddb-107">步驟1：刪除使用者</span><span class="sxs-lookup"><span data-stu-id="ecddb-107">Step 1: Delete users</span></span>

<span data-ttu-id="ecddb-108">刪除除了一個全域管理員之外的所有使用者，該全域管理員完成步驟以關閉帳戶。</span><span class="sxs-lookup"><span data-stu-id="ecddb-108">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="ecddb-109">您必須先刪除所有其他使用者，才能在此程式結束之前刪除目錄。</span><span class="sxs-lookup"><span data-stu-id="ecddb-109">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="ecddb-110">若使用者從內部部署進行同步處理，請先關閉同步處理，然後使用 Azure 入口網站或 Azure PowerShell Cmdlet 刪除雲端目錄中的使用者。</span><span class="sxs-lookup"><span data-stu-id="ecddb-110">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="ecddb-111">若要刪除使用者，請參閱<a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin：刪除一或多個使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="ecddb-111">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="ecddb-112">您也可以使用<a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell Cmdlet，成批刪除使用者。</span><span class="sxs-lookup"><span data-stu-id="ecddb-112">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="ecddb-113">如果您的組織使用與 Azure AD 同步處理的 Active Directory，請改為刪除 Active Directory 中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ecddb-113">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="ecddb-114">如需相關指示，請參閱<a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">大量刪除 Azure Active Directory 中的使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="ecddb-114">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="ecddb-115">步驟2：取消所有作用中的訂閱</span><span class="sxs-lookup"><span data-stu-id="ecddb-115">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="ecddb-116">在系統管理中心中，移至 [**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">產品</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ecddb-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="ecddb-117">如果 [訂閱] 清單位於**表格**視圖中，請在右側選取 [**卡片**]。</span><span class="sxs-lookup"><span data-stu-id="ecddb-117">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="ecddb-118">尋找作用中的訂閱，並在 [**設定 & 動作**] 區段中，選取 [**取消訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="ecddb-118">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="ecddb-119">遵循提示完成此程式。</span><span class="sxs-lookup"><span data-stu-id="ecddb-119">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="ecddb-120">重複步驟1到4，以取消所有作用中的訂閱。</span><span class="sxs-lookup"><span data-stu-id="ecddb-120">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="ecddb-121">步驟3：刪除所有已停用的訂閱</span><span class="sxs-lookup"><span data-stu-id="ecddb-121">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="ecddb-122">在系統管理中心中，移至 [**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">產品</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ecddb-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="ecddb-123">如果 [訂閱] 清單位於**表格**視圖中，請在右側選取 [**卡片**]。</span><span class="sxs-lookup"><span data-stu-id="ecddb-123">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="ecddb-124">選取 [**訂閱狀態**] 旁的 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="ecddb-124">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="ecddb-125">尋找停用的訂閱，然後在 [**設定 & 動作**] 區段中，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ecddb-125">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="ecddb-126">在 [**刪除訂閱**] 對話方塊中，選取 [**我瞭解影響**] 核取方塊，然後選取 [**刪除訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="ecddb-126">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="ecddb-127">針對每個停用的訂閱重複步驟4和5，直到刪除所有訂閱為止。</span><span class="sxs-lookup"><span data-stu-id="ecddb-127">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="ecddb-128">步驟4：停用多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="ecddb-128">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="ecddb-129">在系統管理中心中，移至 [**使用者** > 作用中<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ecddb-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ecddb-130">選擇**多重要素驗證**。</span><span class="sxs-lookup"><span data-stu-id="ecddb-130">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="ecddb-131">在 [多重要素驗證] 頁面上，停用您目前所用全域系統管理員帳戶以外的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="ecddb-131">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="ecddb-132">您也可以<a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用 PowerShell 來停用多個使用者的多重要素驗證</a>。</span><span class="sxs-lookup"><span data-stu-id="ecddb-132">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="ecddb-133">步驟5：刪除 Azure Active Directory 中的目錄</span><span class="sxs-lookup"><span data-stu-id="ecddb-133">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="ecddb-134">使用全域系統管理員帳戶登入<a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="ecddb-134">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="ecddb-135">選取 [Azure Active Directory]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecddb-135">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="ecddb-136">切換至您要刪除的目錄。</span><span class="sxs-lookup"><span data-stu-id="ecddb-136">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="ecddb-137">選取 [**刪除目錄**]。</span><span class="sxs-lookup"><span data-stu-id="ecddb-137">Select **Delete directory**.</span></span>

5. <span data-ttu-id="ecddb-138">如果您的目錄失敗一或多項檢查，您會看到有關如何傳遞檢查的詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="ecddb-138">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="ecddb-139">傳遞所有檢查後，請選取 [**刪除**] 以完成程式。</span><span class="sxs-lookup"><span data-stu-id="ecddb-139">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="ecddb-140">完成此最後一個步驟之後，您的 Microsoft 帳戶會關閉並刪除。</span><span class="sxs-lookup"><span data-stu-id="ecddb-140">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
