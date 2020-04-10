---
title: 指派系統管理員角色 Microsoft 365 系統管理中心
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 瞭解如何將系統管理員角色指派給您公司中的使用者或多位使用者，以便他們可以在系統管理中心執行特定工作。
ms.openlocfilehash: 3f22ef22571dd04dd3364a95ed860f53b8ff207b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211916"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="c1848-103">指派系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="c1848-103">Assign admin roles</span></span>

<span data-ttu-id="c1848-104">如果您是購買 Microsoft 商務版訂閱的人員，您必須是全域系統管理員。這表示您對訂閱中的產品擁有無限制的控制，而且您可以存取大部分的資料。</span><span class="sxs-lookup"><span data-stu-id="c1848-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="c1848-105">如需詳細資訊，請參閱[關於系統管理員角色](about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c1848-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="c1848-106">當您加入新的使用者時，如果您不是指派系統管理員角色，則其為*使用者角色*，且沒有任何 Microsoft 系統管理中心的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="c1848-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="c1848-107">不過，如果您需要協助完成，您可以將系統管理員角色指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="c1848-108">例如，如果您需要人員協助重設密碼，您不應該將其指派為全域系統管理員角色，您應該將密碼系統管理員角色指派給他們。</span><span class="sxs-lookup"><span data-stu-id="c1848-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="c1848-109">如果有太多全域系統管理員，但對您的資料和線上業務的存取不受限制，則會有安全性風險。</span><span class="sxs-lookup"><span data-stu-id="c1848-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

<span data-ttu-id="c1848-110">觀賞有關新增管理員的簡短影片。</span><span class="sxs-lookup"><span data-stu-id="c1848-110">Watch a short video about adding an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="c1848-111">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="c1848-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c1848-112">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="c1848-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

## <a name="assign-admin-roles"></a><span data-ttu-id="c1848-113">指派系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="c1848-113">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="c1848-114">您可以使用兩種不同的方式指派角色給使用者：</span><span class="sxs-lookup"><span data-stu-id="c1848-114">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="c1848-115">您可以移至使用者的詳細資料，以及**管理角色**，將角色指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-115">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="c1848-116">或者，您可以移至 [**角色**] 並選取角色，然後將多個使用者新增至該角色。</span><span class="sxs-lookup"><span data-stu-id="c1848-116">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="c1848-117">使用角色將系統管理員角色指派給使用者</span><span class="sxs-lookup"><span data-stu-id="c1848-117">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="c1848-118">在系統管理中心中，移至**角色** > **角色**，以查看組織可使用的所有系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="c1848-118">In the admin center, go to **Roles** > **Roles** to view all of the admin roles available for your organization.</span></span>
2. <span data-ttu-id="c1848-119">選取您要指派給使用者的系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="c1848-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="c1848-120">選取 [指派的系統**管理員** > ] [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c1848-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="c1848-121">輸入使用者的**顯示名稱**或使用者名稱，然後從建議**清單中選取**使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="c1848-122">在您完成之前，新增多個使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="c1848-123">選取 [**儲存**]，然後將使用者新增至指派的系統管理員清單。</span><span class="sxs-lookup"><span data-stu-id="c1848-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="c1848-124">指派使用者至使用中使用者的系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="c1848-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="c1848-125">在系統管理中心中，移至 [**使用者** >作用中[使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c1848-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="c1848-126">在 [作用中**使用者**] 頁面上，選取您要變更其系統管理員角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="c1848-127">在彈出窗格中，選取 [**角色**] 旁邊的 [**管理角色**]。</span><span class="sxs-lookup"><span data-stu-id="c1848-127">In the flyout pane, next to **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="c1848-128">選取您要指派給使用者的系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="c1848-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="c1848-129">如果您找不到所要的角色，請選取清單底部的 [**全部顯示**]。</span><span class="sxs-lookup"><span data-stu-id="c1848-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c1848-130">在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="c1848-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c1848-131">在 [作用中**使用者**] 頁面上，選取您要變更其系統管理員角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="c1848-132">在彈出窗格中，選取 [**角色**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="c1848-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="c1848-133">如果您看不到 [**編輯**] 選項，則表示您沒有編輯權，也無法將系統管理員角色指派給其他人。</span><span class="sxs-lookup"><span data-stu-id="c1848-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="c1848-134">在您的企業中要求全域系統管理員為您指派角色。</span><span class="sxs-lookup"><span data-stu-id="c1848-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="c1848-135">在小型企業中，企業擁有者（購買訂閱的人員）是全域系統管理員。在大型企業中，IT 部門的主要人員是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c1848-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="c1848-136">選取 [**自訂管理員**]，以查看我們為您自訂的角色清單。</span><span class="sxs-lookup"><span data-stu-id="c1848-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="c1848-137">如需每個角色的說明，請參閱[關於系統管理員角色。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c1848-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c1848-138">在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="c1848-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c1848-139">在 [作用中**使用者**] 頁面上，選取您要變更其系統管理員角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="c1848-140">在彈出窗格中，選取 [**角色**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="c1848-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="c1848-141">如果您看不到 [**編輯**] 選項，則表示您沒有編輯權，也無法將系統管理員角色指派給其他人。</span><span class="sxs-lookup"><span data-stu-id="c1848-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="c1848-142">在您的企業中要求全域系統管理員為您指派角色。</span><span class="sxs-lookup"><span data-stu-id="c1848-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="c1848-143">在小型企業中，企業擁有者（購買訂閱的人員）是全域系統管理員。在大型企業中，IT 部門的主要人員是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c1848-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="c1848-144">選取 [**自訂管理員**]，以查看我們為您自訂的角色清單。</span><span class="sxs-lookup"><span data-stu-id="c1848-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="c1848-145">如需每個角色的說明，請參閱[關於系統管理員角色。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c1848-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="c1848-146">指派系統管理員角色給多個使用者</span><span class="sxs-lookup"><span data-stu-id="c1848-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="c1848-147">如果您知道 PowerShell，請參閱[使用 PowerShell 指派角色給使用者帳戶](https://go.microsoft.com/fwlink/?linkid=854257)。</span><span class="sxs-lookup"><span data-stu-id="c1848-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](https://go.microsoft.com/fwlink/?linkid=854257).</span></span> <span data-ttu-id="c1848-148">這最適合用來指派角色給數百個使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="c1848-149">使用下列指示指派角色給數十個使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"


## <a name="didnt-work-for-you"></a><span data-ttu-id="c1848-150">無法運作嗎？</span><span class="sxs-lookup"><span data-stu-id="c1848-150">Didn't work for you?</span></span>

<span data-ttu-id="c1848-151">您可能沒有適當的許可權，因此您沒有許可權指派系統管理員角色給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="c1848-151">You might not have the correct permissions and so you don't have access to assign admin roles to other users.</span></span> <span data-ttu-id="c1848-152">請委託其他系統管理員為您指派角色。</span><span class="sxs-lookup"><span data-stu-id="c1848-152">Ask another admin to assign roles for you.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="c1848-153">相關文章</span><span class="sxs-lookup"><span data-stu-id="c1848-153">Related articles</span></span>

[<span data-ttu-id="c1848-154">使用 PowerShell 將角色指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="c1848-154">Assign roles to user accounts with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[<span data-ttu-id="c1848-155">授權或移除夥伴關係</span><span class="sxs-lookup"><span data-stu-id="c1848-155">Authorize or remove partner relationships</span></span>](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)

[<span data-ttu-id="c1848-156">使用 Exchange 系統管理中心新增備選電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="c1848-156">Add an alternative email address using the Exchange admin center</span></span>](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)

