---
title: 建立共用信箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 建立共用信箱讓組織中的多位使用者共同負責讀取及回覆傳送到某個地址的電子郵件。
ms.openlocfilehash: 6fff7b1eaa73944bc4dd744046ad97ee9d2379b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393184"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="62d46-103">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="62d46-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="62d46-104">如果您的組織使用混合式 Exchange 環境，您應使用內部部署 Exchange 系統管理中心 (EAC) 來建立及管理共用信箱。</span><span class="sxs-lookup"><span data-stu-id="62d46-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="62d46-105">請參閱[在 Exchange 系統管理中心建立共用信箱](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="62d46-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="62d46-106">如果您不確定應該建立共用信箱或者 Outlook​​ 的 Microsoft 365 群組，請參閱[比較群組](../create-groups/compare-groups.md)以取得指導。</span><span class="sxs-lookup"><span data-stu-id="62d46-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="62d46-107">請注意，目前無法將共用信箱移轉至 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="62d46-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="62d46-108">如果您想要這麼做，請[在這裡投票](https://go.microsoft.com/fwlink/?linkid=871518)讓我們知道。</span><span class="sxs-lookup"><span data-stu-id="62d46-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="62d46-p103">建立共用信箱能讓一群人輕易監視某個共用電子郵件地址 (例如 info@contoso.com) 的電子郵件，並從該電子郵件地址傳送電子郵件。當群組中的某人回覆一則傳送到共用信箱的郵件時，該封電子郵件會顯示為從共用信箱發出，而非從個別使用者發出。</span><span class="sxs-lookup"><span data-stu-id="62d46-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="62d46-p104">共用信箱中也包含了共用行事曆。許多小型企業喜歡將共用行事曆當做一個可以讓所有人輸入各自約會的地方。舉例來說，如果您有 3 個人負責客戶拜訪，他們就都可以使用共用行事曆來輸入約會。這是能讓每個人都能掌握各自事務的簡便方法。</span><span class="sxs-lookup"><span data-stu-id="62d46-p104">Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="62d46-115">建立共用信箱前，請務必閱讀[關於共用信箱](about-shared-mailboxes.md)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="62d46-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="62d46-116">建立共用信箱和新增成員</span><span class="sxs-lookup"><span data-stu-id="62d46-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="62d46-117">使用全域系統管理員帳戶或 Exchange 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="62d46-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="62d46-118">如果您收到 **[您沒有存取這個頁面或執行這個動作的權限]** 訊息，則代表您不是系統管理員。</span><span class="sxs-lookup"><span data-stu-id="62d46-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="62d46-119">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="62d46-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="62d46-120">[在系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)中，移至 **[群組]** \> **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="62d46-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="62d46-121">[在系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)中，移至 **[群組]** \> **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="62d46-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="62d46-122">在 **[共用信箱]** 頁面上，選取 **[+ 新增信箱]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="62d46-123">輸入共用信箱的名稱。</span><span class="sxs-lookup"><span data-stu-id="62d46-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="62d46-124">精靈會隨後選擇電子郵件地址，但您可再自行編輯。</span><span class="sxs-lookup"><span data-stu-id="62d46-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![為您的共用信箱命名。](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="62d46-126">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-126">Select **Add**.</span></span> <span data-ttu-id="62d46-127">您可能需要等待幾分鐘之後才能開始新增成員。</span><span class="sxs-lookup"><span data-stu-id="62d46-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="62d46-128">在 **[後續步驟]** 底下選取 **[將成員新增到此信箱]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="62d46-129">成員是指能檢視此共用信箱的內送郵件以及外寄回覆的人員。</span><span class="sxs-lookup"><span data-stu-id="62d46-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![選取 [新增成員]](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="62d46-131">選取 **[+ 新增成員]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="62d46-131">Select the **+Add members** button.</span></span> <span data-ttu-id="62d46-132">選取您要讓他們使用此共用信箱人員旁邊的核取記號，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![將成員指派至共用信箱](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="62d46-134">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-134">Select **Close**.</span></span>

<span data-ttu-id="62d46-135">您已經擁有共用信箱，且其中包含了共用行事曆。</span><span class="sxs-lookup"><span data-stu-id="62d46-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="62d46-136">現在繼續進行後續步驟：封鎖登入共用信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="62d46-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="62d46-137">應該使用哪些權限？</span><span class="sxs-lookup"><span data-stu-id="62d46-137">Which permissions should you use?</span></span>

<span data-ttu-id="62d46-138">以下是可與共用信箱搭配使用的權限：</span><span class="sxs-lookup"><span data-stu-id="62d46-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="62d46-139">**完整存取**：「完整存取」權限可讓使用者開啟共用信箱，並做為該信箱的擁有者。</span><span class="sxs-lookup"><span data-stu-id="62d46-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="62d46-140">在存取登入共用信箱後，使用者可以建立行事曆項目，讀取、檢視、刪除和變更電子郵件，以及建立工作和行事曆連絡人。</span><span class="sxs-lookup"><span data-stu-id="62d46-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="62d46-141">不過，除非具有「完整存取權」權限的使用者也有「傳送為」或「代理傳送者」權限，否則無法從共用信箱傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="62d46-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="62d46-142">**傳送為**：「傳送為」權限可讓使用者在傳送郵件時模擬共用信箱。</span><span class="sxs-lookup"><span data-stu-id="62d46-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="62d46-143">例如，如果 Katerina 登入共用信箱 Marketing Department 並傳送一封電子郵件，看起來就像是 Marketing Department 傳送該電子郵件。</span><span class="sxs-lookup"><span data-stu-id="62d46-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="62d46-144">**代理傳送者**：「代理傳送者」權限可讓使用者代表共用信箱傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="62d46-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="62d46-145">例如，如果 John 登入共用信箱 Reception Building 32 並傳送一封電子郵件，該電子郵件看起來就像由「John 代表 Reception Building 32」傳送。</span><span class="sxs-lookup"><span data-stu-id="62d46-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="62d46-146">您不能使用 EAC 來授與「代理傳送者」權限，而必須使用 **Set-Mailbox** Cmdlet 搭配 _GrantSendonBehalf_ 參數。</span><span class="sxs-lookup"><span data-stu-id="62d46-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="62d46-147">使用 EAC 來編輯共用信箱委派</span><span class="sxs-lookup"><span data-stu-id="62d46-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="62d46-148">在 EAC 中，移至 [收件者 **]** \> [共用 **]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="62d46-149">選取共用信箱，然後選取 [編輯 **]** ![編輯圖示](../../media/ITPro-EAC-EditIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="62d46-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="62d46-150">選取 [信箱委派 **]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="62d46-151">若要授與或移除「完整存取」和「傳送為」權限，請選取 [新增 **]** ![新增圖示](../../media/ITPro-EAC-AddIcon.png) 或 [移除 **]** ![移除圖示](../../media/ITPro-EAC-RemoveIcon.gif)，然後選取您想要授與權限的使用者。</span><span class="sxs-lookup"><span data-stu-id="62d46-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="62d46-p115">[完整存取] 權限可讓使用者開啟信箱，以及在信箱中建立與修改項目。[以下列傳送 ] 權限可讓任何人 (信箱擁有者除外) 從該共用信箱傳送電子郵件。這兩者是成功共用信箱作業的必要權限。</span><span class="sxs-lookup"><span data-stu-id="62d46-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="62d46-155">選取 [儲存 **]** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="62d46-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="62d46-156">封鎖登入共用信箱帳戶</span><span class="sxs-lookup"><span data-stu-id="62d46-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="62d46-157">每個共用信箱都有對應的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="62d46-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="62d46-158">注意到當您建立共用信箱時，系統如何要求您提供密碼嗎？</span><span class="sxs-lookup"><span data-stu-id="62d46-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="62d46-159">帳戶有密碼，但它是系統產生的密碼 (未知)。</span><span class="sxs-lookup"><span data-stu-id="62d46-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="62d46-160">您不應使用該帳戶登入共用信箱。</span><span class="sxs-lookup"><span data-stu-id="62d46-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="62d46-161">但是如果系統管理員重設共用信箱使用者帳戶的密碼，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="62d46-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="62d46-162">或者如果攻擊者能夠存取共用信箱帳號憑證，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="62d46-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="62d46-163">這可讓使用者帳戶登入共用信箱，並傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="62d46-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="62d46-164">若要避免發生此情況，您需要封鎖與共用信箱相關聯的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="62d46-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="62d46-165">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="62d46-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="62d46-166">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="62d46-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="62d46-167">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="62d46-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
::: moniker-end

1. <span data-ttu-id="62d46-168">在使用者帳戶清單中，找出共用信箱的帳戶 (例如，將篩選變更為 **[未授權的使用者]**)。</span><span class="sxs-lookup"><span data-stu-id="62d46-168">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

1. <span data-ttu-id="62d46-169">選取 [使用者] 以開啟其 [內容] 窗格，然後選取 **[封鎖此使用者]** 圖示![封鎖此使用者圖示的螢幕擷取畫面](../../media/block-user-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="62d46-169">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="62d46-170">**附註**：如果該帳戶已封鎖，**[封鎖登入]** 將會顯示在頂端，且圖示上會顯示 **[解除封鎖此使用者]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-170">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

1. <span data-ttu-id="62d46-171">在 **[封鎖此使用者?]** 窗格中，選取 **[封鎖使用者，使其無法登入]**，然後選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="62d46-171">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

<span data-ttu-id="62d46-172">如需有關如何使用 Azure AD PowerShell 封鎖帳戶登入的指示 (包含一次封鎖多個帳戶)，請參閱[使用 Office 365 PowerShell 封鎖使用者帳戶](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="62d46-172">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="62d46-173">將共用信箱新增至 Outlook</span><span class="sxs-lookup"><span data-stu-id="62d46-173">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="62d46-174">如果您在貴公司啟用了自動對應功能 (根據預設，大多數人都會這麼做)，當使用者關閉並重新啟動 Outlook 後，共用信箱就會自動顯示在使用者的 Outlook 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="62d46-174">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="62d46-175">自動對應是在使用者的信箱中設定，而非共用信箱。</span><span class="sxs-lookup"><span data-stu-id="62d46-175">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="62d46-176">也就是說，如果您嘗試使用安全性群組來管理哪些人員可以存取共用信箱，自動對應將無法運作。</span><span class="sxs-lookup"><span data-stu-id="62d46-176">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="62d46-177">因此，若要使用自動對應，您就必須明確地指派權限。</span><span class="sxs-lookup"><span data-stu-id="62d46-177">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="62d46-178">根據預設會啟用自動對應。</span><span class="sxs-lookup"><span data-stu-id="62d46-178">Automapping is on by default.</span></span> <span data-ttu-id="62d46-179">若要瞭解如何將它關閉，請參閱[移除共用信箱的自動對應](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="62d46-179">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="62d46-180">若要深入了解 Outlook 中的共用信箱，請參閱：</span><span class="sxs-lookup"><span data-stu-id="62d46-180">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="62d46-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">在 Outlook 中開啟及使用共用信箱</a></span><span class="sxs-lookup"><span data-stu-id="62d46-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="62d46-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">新增共用信箱到 Outlook 網頁版</a></span><span class="sxs-lookup"><span data-stu-id="62d46-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="62d46-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">將共用信箱新增至 Outlook mobile</a></span><span class="sxs-lookup"><span data-stu-id="62d46-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="62d46-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">在 Mac 版 Outlook 中開啟共用資料夾或信箱</a></span><span class="sxs-lookup"><span data-stu-id="62d46-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="62d46-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">新增規則到共用信箱</a></span><span class="sxs-lookup"><span data-stu-id="62d46-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="62d46-186">在行動裝置上使用共用信箱 (手機或平板電腦)</span><span class="sxs-lookup"><span data-stu-id="62d46-186">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="62d46-187">有兩種方式可以行動裝置上存取共用信箱：</span><span class="sxs-lookup"><span data-stu-id="62d46-187">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="62d46-188">在 <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">iOS 版 Outlook 應用程式</a>或 <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Android 版 Outlook 行動裝置應用程式</a>中新增共用信箱。</span><span class="sxs-lookup"><span data-stu-id="62d46-188">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="62d46-189">如需相關指示，請參閱<a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">將共用信箱新增至 Outlook mobile</a>。</span><span class="sxs-lookup"><span data-stu-id="62d46-189">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="62d46-190">開啟您的瀏覽器、登入，然後移至 Outlook 網頁版。</span><span class="sxs-lookup"><span data-stu-id="62d46-190">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="62d46-191">您可以從 Outlook 網頁版存取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="62d46-191">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="62d46-192">如需相關指示，請參閱<a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">新增共用信箱到 Outlook 網頁版</a>。</span><span class="sxs-lookup"><span data-stu-id="62d46-192">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="62d46-193">您只能將共用信箱新增至 iOS 版 Outlook 應用程式或 Android 版 Outlook 行動裝置應用程式</span><span class="sxs-lookup"><span data-stu-id="62d46-193">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="62d46-194">使用共用行事曆</span><span class="sxs-lookup"><span data-stu-id="62d46-194">Use the shared calendar</span></span>

<span data-ttu-id="62d46-p120">當您建立共用信箱時，也會自動建立共用行事曆。相較於 SharePoint 行事曆，我們比較喜歡使用共用信箱行事曆來追蹤約會與人員的動向。共用行事曆已與 Outlook 整合，而且使用方法比 SharePoint 行事曆更簡單。</span><span class="sxs-lookup"><span data-stu-id="62d46-p120">When you created the shared mailbox, you automatically created a shared calendar. We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are. A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="62d46-198">在 Outlook 應用程式中，移至行事曆檢視並選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="62d46-198">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="62d46-199">當您輸入約會後，所有共用信箱的成員都能看見它們。</span><span class="sxs-lookup"><span data-stu-id="62d46-199">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="62d46-200">共用信箱的任何成員都可以建立、檢視及管理行事曆上的約會，就像他們處理其個人約會一樣。</span><span class="sxs-lookup"><span data-stu-id="62d46-200">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="62d46-201">身為共用信箱成員的每個人都可以看到其對共用信箱的變更。</span><span class="sxs-lookup"><span data-stu-id="62d46-201">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-content"></a><span data-ttu-id="62d46-202">相關內容</span><span class="sxs-lookup"><span data-stu-id="62d46-202">Related content</span></span>

<span data-ttu-id="62d46-203">[關於共用信箱](about-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="62d46-203">[About shared mailboxes](about-shared-mailboxes.md) (article)\</span></span>
<span data-ttu-id="62d46-204">[設定共用信箱](configure-a-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="62d46-204">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="62d46-205">[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="62d46-205">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="62d46-206">[從共用信箱移除授權](remove-license-from-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="62d46-206">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="62d46-207">[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="62d46-207">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>