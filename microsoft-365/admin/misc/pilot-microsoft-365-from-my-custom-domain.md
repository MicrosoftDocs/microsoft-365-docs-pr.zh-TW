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
ms.openlocfilehash: bdcf86474a7f2edb458075e884c20e56d231df6d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197836"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="6bf34-103">從我的自訂網域試驗 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bf34-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="6bf34-104">您可以使用下列需求和限制試驗 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="6bf34-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="6bf34-105">您目前的電子郵件提供方必須提供電子郵件轉寄功能。</span><span class="sxs-lookup"><span data-stu-id="6bf34-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="6bf34-106">您必須在 DNS 主機服務提供方上管理 Microsoft 365 DNS 記錄，而不是讓 Microsoft 365 為您管理這些記錄。</span><span class="sxs-lookup"><span data-stu-id="6bf34-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="6bf34-107">如需深入了解，請[新增 DNS 記錄以連接您的網域](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf34-107">To learn more, see [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="6bf34-108">其他電子郵件伺服器上的使用者無法使用空閒/忙碌資訊。</span><span class="sxs-lookup"><span data-stu-id="6bf34-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="6bf34-109">系統管理員無法從單一位置管理所有使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6bf34-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="6bf34-110">使用者可能無法使用 Microsoft 365 垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="6bf34-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="6bf34-111">僅針對非常少量的使用者才建議使用此功能，並僅適用使用電子郵件進行試驗。</span><span class="sxs-lookup"><span data-stu-id="6bf34-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="6bf34-112">設定 Microsoft 365 試驗</span><span class="sxs-lookup"><span data-stu-id="6bf34-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="6bf34-113">按照下列步驟設定 Microsoft 365 試驗：</span><span class="sxs-lookup"><span data-stu-id="6bf34-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="6bf34-114">步驟 1:登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="6bf34-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6bf34-115">使用您的工作或學校帳戶，登入 [[Microsoft 365 系統管理中心]](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6bf34-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="6bf34-116">選取左側功能窗格中的 **[設定]** > **[網域]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="6bf34-117">步驟 2：確認您擁有要使用的網域</span><span class="sxs-lookup"><span data-stu-id="6bf34-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="6bf34-118">在 **[網域]** 頁面上，選取 **[新增網域]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="6bf34-119">在方塊中輸入網域名稱，選取 **[使用這個網域]**，然後選取 **[繼續]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="6bf34-120">選取您要用網域測試的服務，例如 [電子郵件] 和 [即時訊息]。</span><span class="sxs-lookup"><span data-stu-id="6bf34-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="6bf34-121">依照 **驗證** 網域頁面上的逐步指示，然後選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="6bf34-122">DNS 變更生效的時間可能在幾分鐘到 72 小時之間。</span><span class="sxs-lookup"><span data-stu-id="6bf34-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="6bf34-123">驗證成功後，會要求您修改您的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="6bf34-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="6bf34-124">步驟 3：在 Exchange Online 中將網域標示為共用</span><span class="sxs-lookup"><span data-stu-id="6bf34-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="6bf34-125">在 Exchange 系統管理中心的 **[郵件流程]** 區段中，選取 **[接受的網域]**，然後選取您要修改的網域。</span><span class="sxs-lookup"><span data-stu-id="6bf34-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="6bf34-126">按兩下以開啟視窗，然後選取 **[內部轉送]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-126">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="6bf34-127">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-127">Select **Save**.</span></span>

    <span data-ttu-id="6bf34-128">此設定可能需要幾分鐘的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="6bf34-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="6bf34-129">步驟 4：解除封鎖現有的電子郵件伺服器 (選用)</span><span class="sxs-lookup"><span data-stu-id="6bf34-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="6bf34-130">Microsoft 365 使用 Exchange Online Protection （EOP）來保護垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="6bf34-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="6bf34-131">如果您目前的郵件伺服器會轉寄大量的垃圾郵件，EOP 可能會封鎖您現有的郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="6bf34-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="6bf34-132">如果您信任其他電子郵件提供方的垃圾郵件防護，您可以在 Microsoft 365 中解除封鎖伺服器。</span><span class="sxs-lookup"><span data-stu-id="6bf34-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="6bf34-133">取消封鎖現有的電子郵件伺服器，就能讓透過您原始伺服器抵達的任何垃圾郵件被送達 Microsoft 365 信箱，而您無法評估 Microsoft 365 防止垃圾郵件的效果。</span><span class="sxs-lookup"><span data-stu-id="6bf34-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="6bf34-134">在 Exchange 系統管理中心流覽窗格中，選取 **[保護]**，然後選取 **[連線篩選]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="6bf34-135">在 **[IP允許清單]** 中，選擇 **+**，然後新增目前電子郵件提供方的郵件伺服器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6bf34-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="6bf34-136">步驟 5：建立使用者帳戶並設定主要 (回覆) 地址</span><span class="sxs-lookup"><span data-stu-id="6bf34-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="6bf34-137">在 Microsoft 365 系統管理中心，選取 **[使用者]** > **[作用中的使用者]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="6bf34-138">新增兩個現有的使用者來建立兩個測試帳戶。</span><span class="sxs-lookup"><span data-stu-id="6bf34-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="6bf34-139">針對每個帳戶，請選取 **+ 新增一名使用者**，並填寫要求的資訊，包含您想測試的密碼方式。</span><span class="sxs-lookup"><span data-stu-id="6bf34-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="6bf34-140">要確保使用者的電子郵件一致，**[使用者名稱]** 欄位必須符合使用者目前的電子郵件地址。 </span><span class="sxs-lookup"><span data-stu-id="6bf34-140">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="6bf34-141">選擇適當的授權，按一下 **[下一步]**，然後按一下 **[完成新增]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="6bf34-142">從 **[使用者名稱]** 旁的下拉式清單中，選取您的自訂網域名稱。</span><span class="sxs-lookup"><span data-stu-id="6bf34-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="6bf34-143">選取 **[建立]** > **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="6bf34-144">步驟 6：將郵件設定為從 Microsoft 365 或 Office 365 流向電子郵件伺服器</span><span class="sxs-lookup"><span data-stu-id="6bf34-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="6bf34-145">要執行此作業有兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="6bf34-145">There are two steps for this:</span></span>

1. <span data-ttu-id="6bf34-146">設定您的 Microsoft 365 或 Office 365 環境。</span><span class="sxs-lookup"><span data-stu-id="6bf34-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="6bf34-147">設定從 Microsoft 365 或 Office 365 到您的電子郵件伺服器的連接器。</span><span class="sxs-lookup"><span data-stu-id="6bf34-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="6bf34-148">1. 設定您的 Microsoft 365 或 Office 365 環境</span><span class="sxs-lookup"><span data-stu-id="6bf34-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="6bf34-149">確認您已在 Microsoft 365 或 Office 365 中完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="6bf34-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="6bf34-150">若要設定連接器，您需要指派的權限才可以開始。</span><span class="sxs-lookup"><span data-stu-id="6bf34-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="6bf34-151">若要檢查所需的權限，請參閱 [EOP 中的功能權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop)主題中的 Microsoft 365 和 Office 365 連接器項目。</span><span class="sxs-lookup"><span data-stu-id="6bf34-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop) topic.</span></span>

2. <span data-ttu-id="6bf34-152">如果您想要 EOP 或 Exchange Online，將您電子郵件伺服器的電子郵件轉送至網際網路，請執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6bf34-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="6bf34-153">使用主體名稱設定的憑證，該主體名稱符合 Microsoft 365 或 Office 365 中公認的網域。</span><span class="sxs-lookup"><span data-stu-id="6bf34-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6bf34-154">我們建議憑證的一般名稱或主體別名要符合組織的主要 SMTP 網域。</span><span class="sxs-lookup"><span data-stu-id="6bf34-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="6bf34-155">如需詳細資訊，請參閱[內部部署電子郵件環境的先決條件](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment)。</span><span class="sxs-lookup"><span data-stu-id="6bf34-155">For details, see [Prerequisites for your on-premises email environment](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="6bf34-156">-或-</span><span class="sxs-lookup"><span data-stu-id="6bf34-156">-OR-</span></span>

   - <span data-ttu-id="6bf34-157">確定您的所有組織寄件者網域與子網域均設定為 Microsoft 365 或 Office 365 中公認的網域。</span><span class="sxs-lookup"><span data-stu-id="6bf34-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="6bf34-158">如需有關定義接受的網域的詳細資訊，請參閱[管理 Exchange Online 中公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)和[啟用 Exchange Online 中子網域的郵件流程](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="6bf34-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="6bf34-159">決定您是否要使用郵件流程規則 (也稱為「傳輸規則」) 或網域名稱來將郵件從 Microsoft 365 或 Office 365 傳遞到您的電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="6bf34-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="6bf34-160">大部分的公司選擇將郵件傳遞給所有公認的網域。</span><span class="sxs-lookup"><span data-stu-id="6bf34-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="6bf34-161">如需詳細資訊，請參閱[案例：條件式郵件路由](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)。</span><span class="sxs-lookup"><span data-stu-id="6bf34-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="6bf34-162">您可以如 [Exchange Online 中的郵件流程規則動作](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)中所述設定郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="6bf34-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="6bf34-163">例如，如果您目前是透過通訊群組清單將郵件導向至多個網站，您可能會想要搭配郵件流程規則來使用連接器。</span><span class="sxs-lookup"><span data-stu-id="6bf34-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="6bf34-164">2. 設定從 Microsoft 365 或 Office 365 到您的電子郵件伺服器的連接器</span><span class="sxs-lookup"><span data-stu-id="6bf34-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="6bf34-165">若要在 Microsoft 365 或 Office 365 中建立連接器，請按一下 **[系統管理員]**，然後按一下 **[Exchange]** 以移至 [Exchange 系統管理中心]。</span><span class="sxs-lookup"><span data-stu-id="6bf34-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="6bf34-166">接下來，請按一下 **[郵件流程]**，然後按一下 **[連接器]**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="6bf34-167">使用精靈設定連接器。</span><span class="sxs-lookup"><span data-stu-id="6bf34-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="6bf34-168">若要啟動精靈，請按一下加號 **+**。</span><span class="sxs-lookup"><span data-stu-id="6bf34-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="6bf34-169">在第一個畫面上，選擇 **[自]** Office 365 和 **[至]** 貴組織的郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="6bf34-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="6bf34-170">按 [**下一步**]，並遵循精靈中的指示。</span><span class="sxs-lookup"><span data-stu-id="6bf34-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="6bf34-171">如果需要詳細資訊，請按一下 [**說明**] 或 [**深入了解**] 連結。</span><span class="sxs-lookup"><span data-stu-id="6bf34-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="6bf34-172">精靈會引導您完成設定。</span><span class="sxs-lookup"><span data-stu-id="6bf34-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="6bf34-173">結束時，請確定您的連接器通過驗證。</span><span class="sxs-lookup"><span data-stu-id="6bf34-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="6bf34-174">如果連接器沒有通過驗證，請按兩下顯示的訊息以取得詳細資訊，並參閱[驗證連接器](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)來協助解決問題。</span><span class="sxs-lookup"><span data-stu-id="6bf34-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="6bf34-175">步驟 7：在 DNS 主機服務提供方上更新您 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="6bf34-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="6bf34-176">登入您的 DNS 主機服務提供方的網站，然後依照 [[新增 DNS 記錄以連結您的網域]](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 指示進行操作。</span><span class="sxs-lookup"><span data-stu-id="6bf34-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="6bf34-177">**請將下列兩者列為例外：**</span><span class="sxs-lookup"><span data-stu-id="6bf34-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="6bf34-178">不建立新的 MX 記錄或變更現有的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="6bf34-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="6bf34-179">如果您已經有先前電子郵件提供方的寄件者原則架構 (SPF) 記錄，則無需為 Exchange Online 建立新的 SPF (TXT) 記錄，只需新增 "include:spf.protection.outlook.com" 至目前的 TXT 記錄即可。</span><span class="sxs-lookup"><span data-stu-id="6bf34-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="6bf34-180">例如， “v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all”。</span><span class="sxs-lookup"><span data-stu-id="6bf34-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="6bf34-181">如果您還沒有 SPF 記錄，請修改 Microsoft 365 所建議的記錄，以包含您目前電子郵件提供方的網域，並新增 spf.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="6bf34-181">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="6bf34-182">這會從兩個電子郵件系統授權外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="6bf34-182">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="6bf34-183">步驟 8：設定目前提供方的電子郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="6bf34-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="6bf34-184">在目前的電子郵件提供方中，為您的使用者電子郵件帳戶設定轉寄至 onmicrosoft.com 網域：</span><span class="sxs-lookup"><span data-stu-id="6bf34-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="6bf34-185">轉寄使用者 A 信箱至 usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6bf34-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="6bf34-186">轉寄使用者 B 信箱至 userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6bf34-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="6bf34-187">當您完成此步驟時，所有傳送到 usera@yourcompany.com 和 userb@yourcompany.com 的電子郵件都可在 Microsoft 365 中使用。</span><span class="sxs-lookup"><span data-stu-id="6bf34-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="6bf34-188">請連絡您目前的電子郵件提供方，以了解設定電子郵件轉寄的確切步驟。</span><span class="sxs-lookup"><span data-stu-id="6bf34-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="6bf34-189">您不需要在目前的電子郵件提供方中保留郵件複本。</span><span class="sxs-lookup"><span data-stu-id="6bf34-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="6bf34-190">大部分提供方轉寄的電子郵件都會原封不動地保留寄件者的 [回覆] 地址，因此回覆會寄給原始寄件者。</span><span class="sxs-lookup"><span data-stu-id="6bf34-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="6bf34-191">步驟 9：測試郵件流程</span><span class="sxs-lookup"><span data-stu-id="6bf34-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="6bf34-192">使用使用者 A 的認證登入 Outlook 網頁應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bf34-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="6bf34-193">執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="6bf34-193">Perform these tests:</span></span>

    - <span data-ttu-id="6bf34-194">將電子郵件（例如）傳送到使用者 B 來測試本地 Microsoft 電子郵件。系統會立即傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6bf34-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="6bf34-195">在此情況下，郵件不會傳送到原始伺服器上的使用者 B 信箱，因為 Microsoft 365 信箱為本機。</span><span class="sxs-lookup"><span data-stu-id="6bf34-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="6bf34-196">透過向使用者，例如使用者 C，傳送電子郵件，以測試傳送電子郵件給現有電子郵件系統中的使用者效果。該電子郵件會傳送到您原始郵件伺服器上使用者 C 的信箱。</span><span class="sxs-lookup"><span data-stu-id="6bf34-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="6bf34-197">請確認已從外部帳戶或從現有電子郵件系統的員工電子郵件帳戶正確設定轉寄。</span><span class="sxs-lookup"><span data-stu-id="6bf34-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="6bf34-198">例如，從使用者 C 或 Hotmail 帳戶的原始伺服器帳戶，向使用者 A 傳送電子郵件，並確認該電子郵件有到達使用者 A 的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="6bf34-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="6bf34-199">步驟 10：移動信箱內容</span><span class="sxs-lookup"><span data-stu-id="6bf34-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="6bf34-200">由於您只會移動兩個測試使用者，而使用者 A 和使用者 B 都使用 Outlook，因此您可以在新 Outlook 設定檔中開啟舊的 .PST 檔案，並複製其中郵件、行事曆專案、聯絡人等等，以移動電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6bf34-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="6bf34-201">如需深入了解，請參閱[從 Outlook 的 .pst 檔案匯入電子郵件、連絡人和行事曆](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。</span><span class="sxs-lookup"><span data-stu-id="6bf34-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="6bf34-202">將檔案匯入至 Microsoft 365 信箱中的適當位置之後，您就可以從任何裝置隨時隨地存取這些專案。</span><span class="sxs-lookup"><span data-stu-id="6bf34-202">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>