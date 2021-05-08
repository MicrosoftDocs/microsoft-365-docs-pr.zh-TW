---
title: 新增使用者並指派授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
description: 了解如何同時新增使用者並指派授權給 Microsoft 365。
ms.date: 07/01/2020
ms.openlocfilehash: 3efa32d21a21ed12041f5731296c1b033374712f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274385"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="b6ae1-103">同時新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="b6ae1-103">Add users and assign licenses at the same time</span></span>

<span data-ttu-id="b6ae1-p101">小組裡的每個人都需要一個使用者帳戶，才能登入並存取[商務用 Microsoft 365](https://www.microsoft.com/microsoft-365/business)。新增使用者帳戶最簡單的方法是在 Microsoft 365 系統管理中心一次新增一個帳戶。完成此步驟後，您的使用者將擁有 Microsoft 365 授權、登入認證及 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-p101">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business). The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center. After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b6ae1-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="b6ae1-107">Before you begin</span></span>

<span data-ttu-id="b6ae1-108">您必須是全域、授權或使用者系統管理員，才能新增使用者並指派授權。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-108">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="b6ae1-109">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-user-in-the-admin-simplified-view"></a><span data-ttu-id="b6ae1-110">在系統管理簡化檢視中新增使用者</span><span class="sxs-lookup"><span data-stu-id="b6ae1-110">Add a user in the admin simplified view</span></span>

<span data-ttu-id="b6ae1-111">如果您在系統管理中心看到此頁面，表示您處於 **系統管理簡化檢視**。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-111">If you're seeing this page in the admin center, you're on the **admin simplified view**.</span></span> <span data-ttu-id="b6ae1-112">遵循下列步驟來新增使用者。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-112">Follow the steps below to add a user.</span></span>

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="螢幕擷取畫面：簡化的系統管理中心檢視":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6ae1-114">移至位於 <https://admin.microsoft.com> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-114">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b6ae1-115">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-115">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6ae1-116">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-116">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="b6ae1-117">選取 [為其他人員建立帳戶 **]**。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-117">Select **Create an account for another person**.</span></span>
3. <span data-ttu-id="b6ae1-118">在 [新增使用者帳戶 **]** 頁面上，填入他們將用於登入的名字和姓氏、顯示名稱和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-118">On the **Add a user account** page, fill in the first and last name, display name, and username they'll use to sign in.</span></span>
4. <span data-ttu-id="b6ae1-119">在 [以分號分隔最多 5 個電子郵件地址 **]** 文字方塊中新增使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-119">Add the email address of the user in the **Up to 5 email addresses...** text box.</span></span> <span data-ttu-id="b6ae1-120">這可確定新使用者會取得登入 Microsoft 365 服務所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-120">This will make sure the new user gets the information they need to sign into Microsoft 365 services.</span></span>
5. <span data-ttu-id="b6ae1-121">如果您想要儲存此資訊，請選取 [新增使用者 **]** 並 [下載登入資訊 **]**。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-121">Select **Add user** and **Download sign-in info** if you want to save this info.</span></span>

## <a name="watch-add-users-in-the-dashboard-view"></a><span data-ttu-id="b6ae1-122">觀看：在儀表板檢視中新增使用者</span><span class="sxs-lookup"><span data-stu-id="b6ae1-122">Watch: Add users in the dashboard view</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="b6ae1-123">影片中使用的步驟顯示新增使用者的不同起點，但其餘步驟與下列程序相同。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-123">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a><span data-ttu-id="b6ae1-124">在儀表板檢視中一次新增一個使用者</span><span class="sxs-lookup"><span data-stu-id="b6ae1-124">Add users one at a time in the dashboard view</span></span>

:::image type="content" source="../../media/classic-admin-center.png" alt-text="螢幕擷取畫面：系統管理中心儀表板檢視":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6ae1-126">移至位於 <https://admin.microsoft.com> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-126">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b6ae1-127">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6ae1-128">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="b6ae1-129">移至 [使用者]  >  [作用中使用者]，然後選取 [新增使用者]。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-129">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="b6ae1-130">在 [設定基本資料 **]** 窗格中，填入基本使用者資訊，然後選取 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-130">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="b6ae1-131">**名稱**：填入名字和姓氏、顯示名稱和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-131">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="b6ae1-p105">**網域**：選擇使用者帳戶的網域。例如，如果使用者的使用者名稱是 Jakob，而網域為 contoso.com，他們可以使用 jakob@contoso.com 來登入。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-p105">**Domain** Choose the domain for the user's account. For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="b6ae1-134">**密碼設定**：選擇使用自動產生的密碼，或是為使用者建立您自己的強式密碼。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-134">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="b6ae1-p106">使用者需要在 90 天後變更他們的密碼。或者，您可以選擇 [要求此使用者在第一次登入時變更密碼 **]**。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-p106">The user must change their password after 90 days. Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="b6ae1-137">選擇是否要在新增使用者時透過電子郵件傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-137">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="b6ae1-138">在 [指派產品授權 **]** 窗格中，選取使用者的位置和適當的授權。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-138">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="b6ae1-139">如果您沒有任何可用的授權，您仍然可以新增使用者，並購買額外的授權。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-139">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="b6ae1-140">展開 [應用程式 **]** 並選取或取消選取應用程式，以限制使用者擁有授權的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-140">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="b6ae1-141">選取 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-141">Select **Next**.</span></span>
5. <span data-ttu-id="b6ae1-142">在 [選用設定 **]** 窗格中，展開 [角色 **]** 以讓此使用者成為系統管理員。展開 [設定檔資訊 **]** 以新增有關使用者的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-142">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="b6ae1-143">選取 [下一步 **]**，檢閱新使用者的設定，進行您喜歡的任何變更，然後選取 [完成新增 **]**，然後選取 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-143">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="b6ae1-144">同時新增多個使用者</span><span class="sxs-lookup"><span data-stu-id="b6ae1-144">Add multiple users at the same time</span></span>

<span data-ttu-id="b6ae1-145">您可以使用下列任一方法，同時新增多個使用者：</span><span class="sxs-lookup"><span data-stu-id="b6ae1-145">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="b6ae1-146">**使用試算表大量新增人員。**</span><span class="sxs-lookup"><span data-stu-id="b6ae1-146">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="b6ae1-147">請參閱[同時新增多個使用者](../../enterprise/add-several-users-at-the-same-time.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-147">See [Add several users at the same time](../../enterprise/add-several-users-at-the-same-time.md).</span></span>
- <span data-ttu-id="b6ae1-p109">**自動新增帳戶並指派授權。** 請參閱 [使用 Microsoft 365 PowerShell 建立使用者帳戶](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)。如果您已熟悉 Windows PowerShell Cmdlet 的用法，請選擇此方法。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-p109">**Automate adding accounts and assigning licenses.** See [Create user accounts with Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="b6ae1-p110">**使用 ActiveDirectory？**[設定 Microsoft 365 的目錄同步](../../enterprise/set-up-directory-synchronization.md)。使用 Azure AD Connect 工具來複製 Microsoft 365 中的 Active Directory 使用者帳戶 (以及其他 Active Directory 物件)。同步處理只會新增使用者帳戶。您必須先將授權指派給同步處理的使用者，之後他們才能使用電子郵件及其他 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-p110">**Using ActiveDirectory?** [Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md). Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365. The sync only adds the user accounts. You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="b6ae1-156">**從 Exchange Server 移轉？**</span><span class="sxs-lookup"><span data-stu-id="b6ae1-156">**Migrating from Exchange?**</span></span> <span data-ttu-id="b6ae1-157">請參閱[將多個電子郵件帳戶移轉到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-157">See [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="b6ae1-158">當您使用完全移轉、分段移轉或混合式 Exchange 方法，將多個信箱移轉到 Microsoft 365 時，您會在移轉過程中自動新增使用者。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-158">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="b6ae1-159">移轉只會新增使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-159">The migration only adds the user accounts.</span></span> <span data-ttu-id="b6ae1-160">您必須先將授權指派給使用者，之後他們才能使用電子郵件及其他 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-160">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="b6ae1-161">如果您未指派授權給使用者，則其信箱會在 30 天的寬限期後停用。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-161">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="b6ae1-162">了解如何[在 Microsoft 365 系統管理中心指派授權指派給使用者](../manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-162">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b6ae1-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b6ae1-163">Next steps</span></span>

<span data-ttu-id="b6ae1-164">新增使用者之後，您會收到來自 Microsoft 的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-164">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="b6ae1-165">電子郵件會包含該人員的使用者識別碼與密碼，讓他們可以登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-165">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="b6ae1-166">以正常程序傳達新密碼。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-166">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="b6ae1-167">請與您的新使用者分享[員工快速入門指南](../../business-video/employee-quick-setup.md)，以設定相關項目，例如如何[在 PC 或 Mac 上下載並安裝 Office 應用程式](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何[在行動裝置上設定 Office 應用程式和電子郵件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="b6ae1-167">Share the [Employee quickstart guide](../../business-video/employee-quick-setup.md) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="b6ae1-168">相關內容</span><span class="sxs-lookup"><span data-stu-id="b6ae1-168">Related content</span></span>

<span data-ttu-id="b6ae1-169">[將新員工新增至 Microsoft 365](add-new-employee.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b6ae1-169">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="b6ae1-170">[同時將多位使用者新增至 Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b6ae1-170">[Add several users at the same time to Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (article)</span></span>\
<span data-ttu-id="b6ae1-171">[在 Microsoft 365 中還原使用者](restore-user.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b6ae1-171">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="b6ae1-172">[將授權指派給使用者](../manage/assign-licenses-to-users.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="b6ae1-172">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="b6ae1-173">[刪除組織中的使用者](delete-a-user.md) (文章)\</span><span class="sxs-lookup"><span data-stu-id="b6ae1-173">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
