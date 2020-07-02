---
title: 新增使用者並指派授權
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 瞭解如何同時新增使用者並指派授權給 Microsoft 365。
ms.date: 07/01/2020
ms.openlocfilehash: 016c98fc93bfa1a92274a5b991cf8adbd1131bc9
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015884"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="c7d01-103">同時新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="c7d01-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c7d01-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="c7d01-104">The admin center is changing.</span></span> <span data-ttu-id="c7d01-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c7d01-106">在您的小組中，每個人都需要一個使用者帳戶，才能登入並存取[Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="c7d01-107">新增使用者帳戶的最簡單方法是在 Microsoft 365 系統管理中心一次加入一個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c7d01-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c7d01-108">完成此步驟後，您的使用者就會有 Microsoft 365 授權、登入認證，以及 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="c7d01-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c7d01-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="c7d01-109">Before you begin</span></span>

<span data-ttu-id="c7d01-110">您必須是全域、授權或使用者系統管理員，才能新增使用者並指派授權。</span><span class="sxs-lookup"><span data-stu-id="c7d01-110">You must be a Global, License, or a User admin to add users and assign licenses.</span></span> <span data-ttu-id="c7d01-111">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="c7d01-112">觀賞：在系統管理中心新增使用者</span><span class="sxs-lookup"><span data-stu-id="c7d01-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="c7d01-113">影片中所用的步驟會顯示新增使用者的不同起點，但其餘步驟與下列程式相同。</span><span class="sxs-lookup"><span data-stu-id="c7d01-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="c7d01-114">一次新增一個使用者</span><span class="sxs-lookup"><span data-stu-id="c7d01-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c7d01-115">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7d01-115">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="c7d01-116">移至 [**使用者**] [作用 > 中**使用者**]，然後選取 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c7d01-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="c7d01-117">在 [**設定基礎**] 窗格中，填入基本的使用者資訊，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7d01-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="c7d01-118">**名稱**填入名字和姓氏、顯示名稱和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="c7d01-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="c7d01-119">**網域**為使用者的帳戶選擇網域。</span><span class="sxs-lookup"><span data-stu-id="c7d01-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="c7d01-120">例如，如果使用者的使用者名稱是 Jakob，而且網域是 contoso.com，他們會使用 jakob@contoso.com 登入。</span><span class="sxs-lookup"><span data-stu-id="c7d01-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="c7d01-121">**密碼設定**選擇使用自動產生的密碼或為使用者建立您自己的強式密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="c7d01-122">使用者必須在90天后變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="c7d01-123">或者，您可以選擇**要求此使用者在第一次登入時變更其密碼**。</span><span class="sxs-lookup"><span data-stu-id="c7d01-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="c7d01-124">選擇是否要在使用者新增時以電子郵件傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="c7d01-125">在 [**指派產品授權**] 窗格中，選取該使用者的位置和適當授權。</span><span class="sxs-lookup"><span data-stu-id="c7d01-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="c7d01-126">如果您沒有可用的授權，您仍然可以新增使用者，並購買額外的授權。</span><span class="sxs-lookup"><span data-stu-id="c7d01-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="c7d01-127">展開 [**應用**程式]，選取或取消選取 [應用程式]，以限制使用者擁有授權的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c7d01-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="c7d01-128">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7d01-128">Select **Next**.</span></span>
5. <span data-ttu-id="c7d01-129">在 [**選用設定**] 窗格中，展開 [**角色**]，讓此使用者成為系統管理員。展開 [**設定檔資訊**]，以新增其他有關使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="c7d01-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="c7d01-130">選取 **[下一步]**，查看新使用者的設定，進行任何您想要的變更，然後選取 **[完成新增]**，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="c7d01-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c7d01-131">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7d01-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>
2. <span data-ttu-id="c7d01-132">移至 [**使用者**] [作用 > 中**使用者**]，然後選取 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c7d01-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="c7d01-133">在 [**新增使用者**] 窗格中填入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="c7d01-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="c7d01-134">當您完成時，請選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7d01-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="c7d01-135">**名稱**：請填入名字、姓氏、顯示名稱和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="c7d01-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="c7d01-136">**網域**例如，如果使用者的使用者名稱是 Jakob，而且網域是 contoso.com，他們會輸入 jakob@contoso.com 來登入。</span><span class="sxs-lookup"><span data-stu-id="c7d01-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="c7d01-137">**連絡資訊**：展開並填入行動電話號碼、地址等資訊。</span><span class="sxs-lookup"><span data-stu-id="c7d01-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="c7d01-138">**密碼**使用自動產生的密碼或展開以指定使用者的強式密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="c7d01-139">他們必須在90天后變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-139">They must change their password after 90 days.</span></span> <span data-ttu-id="c7d01-140">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="c7d01-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="c7d01-141">**角色**：如果您需要將這個使用者設為系統管理員的話，請展開此區段。</span><span class="sxs-lookup"><span data-stu-id="c7d01-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="c7d01-142">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="c7d01-142">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="c7d01-143">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="c7d01-143">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7d01-144">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7d01-144">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>
2. <span data-ttu-id="c7d01-145">移至 [**使用者**] [作用 > 中**使用者**]，然後選取 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c7d01-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="c7d01-146">在 [**新增使用者**] 窗格中填入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="c7d01-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="c7d01-147">當您完成時，請選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7d01-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="c7d01-148">**名稱**：請填入名字、姓氏、顯示名稱和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="c7d01-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="c7d01-149">**網域**例如，如果使用者的使用者名稱是 Jakob，而且網域是 contoso.com，他們會輸入 jakob@contoso.com 來登入。</span><span class="sxs-lookup"><span data-stu-id="c7d01-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="c7d01-150">**連絡資訊**：展開並填入行動電話號碼、地址等資訊。</span><span class="sxs-lookup"><span data-stu-id="c7d01-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="c7d01-151">**密碼**使用自動產生的密碼或展開以指定使用者的強式密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="c7d01-152">他們必須在90天后變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-152">They must change their password after 90 days.</span></span> <span data-ttu-id="c7d01-153">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="c7d01-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="c7d01-154">**角色**：如果您需要將這個使用者設為系統管理員的話，請展開此區段。</span><span class="sxs-lookup"><span data-stu-id="c7d01-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="c7d01-155">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="c7d01-155">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="c7d01-156">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="c7d01-156">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="c7d01-157">同時新增多個使用者</span><span class="sxs-lookup"><span data-stu-id="c7d01-157">Add multiple users at the same time</span></span>

<span data-ttu-id="c7d01-158">您可以使用下列任何一種方法，同時新增多個使用者：</span><span class="sxs-lookup"><span data-stu-id="c7d01-158">You can use any of the following methods to add multiple users at the same time:</span></span>
  
- <span data-ttu-id="c7d01-159">**使用試算表大量新增人員。**</span><span class="sxs-lookup"><span data-stu-id="c7d01-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="c7d01-160">請參閱[同時新增多個使用者](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-160">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
- <span data-ttu-id="c7d01-161">**自動新增帳戶並指派授權** 。</span><span class="sxs-lookup"><span data-stu-id="c7d01-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="c7d01-162">請參閱[使用 Office 365 PowerShell 建立使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-162">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="c7d01-163">如果您已熟悉 Windows PowerShell Cmdlet 的用法，請選擇這個方法。</span><span class="sxs-lookup"><span data-stu-id="c7d01-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="c7d01-164">**使用 ActiveDirectory？**</span><span class="sxs-lookup"><span data-stu-id="c7d01-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="c7d01-165">[設定 Office 365 的目錄同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)處理。</span><span class="sxs-lookup"><span data-stu-id="c7d01-165">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="c7d01-166">使用 Azure AD Connect 工具複寫 Microsoft 365 中的 Active Directory 使用者帳戶（及其他 Active Directory 物件）。</span><span class="sxs-lookup"><span data-stu-id="c7d01-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="c7d01-167">[同步處理] 只會新增使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c7d01-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="c7d01-168">您必須先將授權指派給同步處理的使用者，才能使用電子郵件和其他 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c7d01-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="c7d01-169">**從 Exchange 遷移？**</span><span class="sxs-lookup"><span data-stu-id="c7d01-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="c7d01-170">查看[將多個電子郵件帳戶遷移至 Office 365 的方式](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-170">See [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="c7d01-171">當您使用「轉換」、「暫存」或「混合 Exchange」方法將多個信箱遷移至 Microsoft 365 時，會自動將使用者新增為遷移的一部分。</span><span class="sxs-lookup"><span data-stu-id="c7d01-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="c7d01-172">移轉只會新增使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c7d01-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="c7d01-173">您必須先將授權指派給使用者，使用者才能使用電子郵件和其他 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c7d01-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="c7d01-174">如果您未指派授權給使用者，則在30天的寬限期過後，其信箱會停用。</span><span class="sxs-lookup"><span data-stu-id="c7d01-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="c7d01-175">瞭解如何在 Microsoft 365 系統管理中心中[指派授權給使用者](../manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c7d01-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c7d01-176">Next steps</span></span>

<span data-ttu-id="c7d01-177">新增使用者後，您會收到來自 Microsoft 的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="c7d01-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="c7d01-178">電子郵件會包含人員的使用者識別碼和密碼，讓他們能夠登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c7d01-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="c7d01-179">請以正常程序傳達新密碼。</span><span class="sxs-lookup"><span data-stu-id="c7d01-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="c7d01-180">與新的使用者分享[員工快速入門手冊](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，以設定相關專案，例如如何[在 PC 或 Mac 上下載並安裝 office 應用程式](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何[在行動裝置上設定 office 應用程式和電子郵件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。</span><span class="sxs-lookup"><span data-stu-id="c7d01-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="c7d01-181">相關內容</span><span class="sxs-lookup"><span data-stu-id="c7d01-181">Related content</span></span>

<span data-ttu-id="c7d01-182">[將新員工新增至 Microsoft 365](add-new-employee.md) （文章） </span><span class="sxs-lookup"><span data-stu-id="c7d01-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="c7d01-183">[同時將多個使用者新增至 Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) （文章） </span><span class="sxs-lookup"><span data-stu-id="c7d01-183">[Add several users at the same time to Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) (article)</span></span>\
<span data-ttu-id="c7d01-184">[在 Microsoft 365 （文章）中還原使用者](restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="c7d01-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="c7d01-185">[將授權指派給使用者](../manage/assign-licenses-to-users.md)（文章） </span><span class="sxs-lookup"><span data-stu-id="c7d01-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="c7d01-186">[從您的組織刪除使用者](delete-a-user.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="c7d01-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>