---
title: 從我的自訂網域試驗 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何只用兩個測試帳戶來試驗自訂365網域的電子郵件功能。
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186038"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="187b9-103">從我的自訂網域試驗 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="187b9-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="187b9-104">您可以使用下列需求和限制試驗 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="187b9-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="187b9-105">您目前的電子郵件提供方必須提供電子郵件轉寄功能。</span><span class="sxs-lookup"><span data-stu-id="187b9-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="187b9-106">您必須在 DNS 主機服務提供方上管理 Microsoft 365 DNS 記錄，而不是讓 Microsoft 365 為您管理這些記錄。</span><span class="sxs-lookup"><span data-stu-id="187b9-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="187b9-107">如需深入了解，請[新增 DNS 記錄以連接您的網域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="187b9-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="187b9-108">其他電子郵件伺服器上的使用者無法使用空閒/忙碌資訊。</span><span class="sxs-lookup"><span data-stu-id="187b9-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="187b9-109">系統管理員無法從單一位置管理所有使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="187b9-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="187b9-110">使用者可能無法使用 Microsoft 365 垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="187b9-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="187b9-111">設定 Microsoft 365 試驗</span><span class="sxs-lookup"><span data-stu-id="187b9-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="187b9-112">按照下列步驟設定 Microsoft 365 試驗：</span><span class="sxs-lookup"><span data-stu-id="187b9-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="187b9-113">步驟 1:登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="187b9-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="187b9-114">使用您的工作或學校帳戶，登入 [[Microsoft 365 系統管理中心]](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="187b9-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="187b9-115">選取左側功能窗格中的 **[設定]** > **[網域]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="187b9-116">步驟 2：確認您擁有要使用的網域</span><span class="sxs-lookup"><span data-stu-id="187b9-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="187b9-117">在 **[網域]** 頁面上，選取 **[新增網域]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="187b9-118">在方塊中輸入網域名稱，選取 **[使用這個網域]**，然後選取 **[繼續]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="187b9-119">選取您要用網域測試的服務，例如 [電子郵件] 和 [即時訊息]。</span><span class="sxs-lookup"><span data-stu-id="187b9-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="187b9-120">依照 **驗證** 網域頁面上的逐步指示，然後選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="187b9-121">DNS 變更生效的時間可能在幾分鐘到 72 小時之間。</span><span class="sxs-lookup"><span data-stu-id="187b9-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="187b9-122">驗證成功後，會要求您修改您的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="187b9-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="187b9-123">步驟 3：在 Exchange Online 中將網域標示為共用</span><span class="sxs-lookup"><span data-stu-id="187b9-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="187b9-124">在 Exchange 系統管理中心的 **[郵件流程]** 區段中，選取 **[接受的網域]**，然後選取您要修改的網域。</span><span class="sxs-lookup"><span data-stu-id="187b9-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="187b9-125">按兩下以開啟視窗，然後選取 **[內部轉送]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="187b9-126">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-126">Select **Save**.</span></span>

    <span data-ttu-id="187b9-127">此設定可能需要幾分鐘的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="187b9-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="187b9-128">步驟 4：解除封鎖現有的電子郵件伺服器 (選用)</span><span class="sxs-lookup"><span data-stu-id="187b9-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="187b9-129">Microsoft 365 使用 Exchange Online Protection （EOP）來保護垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="187b9-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="187b9-130">如果您目前的郵件伺服器會轉寄大量的垃圾郵件，EOP 可能會封鎖您現有的郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="187b9-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="187b9-131">如果您信任其他電子郵件提供方的垃圾郵件防護，您可以在 Microsoft 365 中解除封鎖伺服器。</span><span class="sxs-lookup"><span data-stu-id="187b9-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="187b9-132">取消封鎖現有的電子郵件伺服器，就能讓透過您原始伺服器抵達的任何垃圾郵件被送達 Microsoft 365 信箱，而您無法評估 Microsoft 365 防止垃圾郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="187b9-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="187b9-133">在 Exchange 系統管理中心流覽窗格中，選取 **[保護]**，然後選取 **[連線篩選]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="187b9-134">在 **[IP允許清單]** 中，選擇**+**，然後新增目前電子郵件提供方的郵件伺服器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="187b9-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="187b9-135">步驟 5：建立使用者帳戶並設定主要 (回覆) 地址</span><span class="sxs-lookup"><span data-stu-id="187b9-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="187b9-136">在 Microsoft 365 系統管理中心，選取 **[使用者]** > **[作用中的使用者]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="187b9-137">新增兩個現有的使用者來建立兩個測試帳戶。</span><span class="sxs-lookup"><span data-stu-id="187b9-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="187b9-138">針對每個帳戶，請選取 **+ 新增一名使用者**，並填寫要求的資訊，包含您想測試的密碼方式。</span><span class="sxs-lookup"><span data-stu-id="187b9-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="187b9-139">要確保使用者的電子郵件一致，**[使用者名稱]** 欄位必須符合使用者目前的電子郵件地址。 </span><span class="sxs-lookup"><span data-stu-id="187b9-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="187b9-140">選擇適當的授權，按一下 **[下一步]**，然後按一下 **[完成新增]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="187b9-141">從 **[使用者名稱]** 旁的下拉式清單中，選取您的自訂網域名稱。</span><span class="sxs-lookup"><span data-stu-id="187b9-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="187b9-142">選取 **[建立]** > **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="187b9-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="187b9-143">步驟 6：在 DNS 主機服務提供方上更新您 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="187b9-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="187b9-144">登入您的 DNS 主機服務提供方的網站，然後依照 [[新增 DNS 記錄以連結您的網域]](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 指示進行操作。</span><span class="sxs-lookup"><span data-stu-id="187b9-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="187b9-145">**請將下列兩者列為例外：**</span><span class="sxs-lookup"><span data-stu-id="187b9-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="187b9-146">不建立新的 MX 記錄或變更現有的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="187b9-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="187b9-147">如果您已經有先前電子郵件提供方的寄件者原則架構 (SPF) 記錄，則無需為 Exchange Online 建立新的 SPF (TXT) 記錄，只需新增 "include:spf.protection.outlook.com" 至目前的 TXT 記錄即可。</span><span class="sxs-lookup"><span data-stu-id="187b9-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="187b9-148">例如， “v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all”。</span><span class="sxs-lookup"><span data-stu-id="187b9-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="187b9-149">如果您還沒有 SPF 記錄，請修改 Microsoft 365 所建議的記錄，以包含您目前電子郵件提供方的網域，並新增 spf.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="187b9-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="187b9-150">這會從兩個電子郵件系統授權外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="187b9-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="187b9-151">步驟 7：設定目前提供方的電子郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="187b9-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="187b9-152">在目前的電子郵件提供方中，為您的使用者電子郵件帳戶設定轉寄至 onmicrosoft.com 網域：</span><span class="sxs-lookup"><span data-stu-id="187b9-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="187b9-153">轉寄使用者 A 信箱至 usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="187b9-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="187b9-154">轉寄使用者 B 信箱至 userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="187b9-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="187b9-155">當您完成此步驟時，所有傳送到 usera@yourcompany.com 和 userb@yourcompany.com 的電子郵件都可在 Microsoft 365 中使用。</span><span class="sxs-lookup"><span data-stu-id="187b9-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="187b9-156">請連絡您目前的電子郵件提供方，以了解設定電子郵件轉寄的確切步驟。</span><span class="sxs-lookup"><span data-stu-id="187b9-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="187b9-157">您不需要在目前的電子郵件提供方中保留郵件複本。</span><span class="sxs-lookup"><span data-stu-id="187b9-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="187b9-158">大部分提供方轉寄的電子郵件都會原封不動地保留寄件者的 [回覆] 地址，因此回覆會寄給原始寄件者。</span><span class="sxs-lookup"><span data-stu-id="187b9-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="187b9-159">步驟 8：測試郵件流程</span><span class="sxs-lookup"><span data-stu-id="187b9-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="187b9-160">使用使用者 A 的認證登入 Outlook 網頁應用程式。</span><span class="sxs-lookup"><span data-stu-id="187b9-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="187b9-161">執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="187b9-161">Perform these tests:</span></span>

    - <span data-ttu-id="187b9-162">將電子郵件（例如）傳送到使用者 B 來測試本地 Microsoft 電子郵件。系統會立即傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="187b9-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="187b9-163">在此情況下，郵件不會傳送到原始伺服器上的使用者 B 信箱，因為 Microsoft 365 信箱為本機。</span><span class="sxs-lookup"><span data-stu-id="187b9-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="187b9-164">透過向使用者，例如使用者 C，傳送電子郵件，以測試傳送電子郵件給現有電子郵件系統中的使用者效果。該電子郵件會傳送到您原始郵件伺服器上使用者 C 的信箱。</span><span class="sxs-lookup"><span data-stu-id="187b9-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="187b9-165">請確認已從外部帳戶或從現有電子郵件系統的員工電子郵件帳戶正確設定轉寄。</span><span class="sxs-lookup"><span data-stu-id="187b9-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="187b9-166">例如，從使用者 C 或 Hotmail 帳戶的原始伺服器帳戶，向使用者 A 傳送電子郵件，並確認該電子郵件有到達使用者 A 的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="187b9-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="187b9-167">步驟 9：移動信箱內容</span><span class="sxs-lookup"><span data-stu-id="187b9-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="187b9-168">由於您只會移動兩個測試使用者，而使用者 A 和使用者 B 都使用 Outlook，因此您可以在新 Outlook 設定檔中開啟舊的 .PST 檔案，並複製其中郵件、行事曆專案、聯絡人等等，以移動電子郵件。</span><span class="sxs-lookup"><span data-stu-id="187b9-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="187b9-169">如需深入了解，請參閱[從 Outlook 的 .pst 檔案匯入電子郵件、連絡人和行事曆](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。</span><span class="sxs-lookup"><span data-stu-id="187b9-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="187b9-170">將檔案匯入至 Microsoft 365 信箱中的適當位置之後，您就可以從任何裝置隨時隨地存取這些專案。</span><span class="sxs-lookup"><span data-stu-id="187b9-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="187b9-171">當涉及更多信箱，或如果員工並未使用 Outlook 的話，您可以使用 Exchange 系統管理中心提供的遷移工具。</span><span class="sxs-lookup"><span data-stu-id="187b9-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="187b9-172">若要開始使用，請移至 Exchange 系統管理中心，並依照 [將電子郵件從 IMAP 伺服器遷移到 Exchange Online 信箱] 中的指示進行 - 我們需要新的文章資源]。</span><span class="sxs-lookup"><span data-stu-id="187b9-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>