---
title: 使用者提交原則
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 321e27f22295a4da17d0eb37b477a1dc7b779d38
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644761"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="3599e-103">使用者提交原則</span><span class="sxs-lookup"><span data-stu-id="3599e-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3599e-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="3599e-104">**Applies to**</span></span>
- [<span data-ttu-id="3599e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3599e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3599e-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="3599e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3599e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3599e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3599e-108">在使用 Exchange Online 信箱的 Microsoft 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。</span><span class="sxs-lookup"><span data-stu-id="3599e-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="3599e-109">當使用者使用各種報告選項送出郵件時，您可以使用此信箱來截取郵件 (只) 或接收郵件副本 (傳送至自訂信箱和 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="3599e-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="3599e-110">這項功能可搭配下列郵件報告選項使用：</span><span class="sxs-lookup"><span data-stu-id="3599e-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="3599e-111">報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="3599e-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="3599e-112">報表網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="3599e-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="3599e-113">[Outlook 網頁版中 (的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) （以前稱為 Outlook web App）) </span><span class="sxs-lookup"><span data-stu-id="3599e-113">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="3599e-114">Outlook 中用於 iOS 和 Android 的內建報告</span><span class="sxs-lookup"><span data-stu-id="3599e-114">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="3599e-115">如果 [在網頁上的 outlook 中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，讓使用者在這裡提交，將會覆寫該設定，讓使用者再次在 Outlook 的 outlook 中報告郵件。</span><span class="sxs-lookup"><span data-stu-id="3599e-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="3599e-116">您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="3599e-116">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="3599e-117">將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統 [管理員提交](admin-submission.md)將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3599e-117">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="3599e-118">自訂信箱必要條件</span><span class="sxs-lookup"><span data-stu-id="3599e-118">Custom mailbox prerequisites</span></span>

<span data-ttu-id="3599e-119">使用下列文章來設定必要的必要條件，讓使用者報告的郵件進入您的自訂信箱：</span><span class="sxs-lookup"><span data-stu-id="3599e-119">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="3599e-120">建立 exchange 郵件流程規則以設定垃圾郵件信賴等級，以略過自訂信箱上的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="3599e-120">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="3599e-121">請參閱 [使用 EAC 建立郵件流程規則，將郵件的 scl](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 設定為將 scl 設定為 **-1**。</span><span class="sxs-lookup"><span data-stu-id="3599e-121">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="3599e-122">關閉自訂信箱中的惡意程式碼的掃描附件。</span><span class="sxs-lookup"><span data-stu-id="3599e-122">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="3599e-123">使用 [在 Office 365 中設定安全附件](set-up-safe-attachments-policies.md)原則，以建立安全附件原則，**關閉\*\*\*\*安全附件未知惡意程式碼回應**。</span><span class="sxs-lookup"><span data-stu-id="3599e-123">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="3599e-124">在自訂信箱的郵件上關閉 URL 掃描。</span><span class="sxs-lookup"><span data-stu-id="3599e-124">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="3599e-125">使用 [在 Office 365 中的 [設定安全連結原則](set-up-safe-links-policies.md) ] 來建立安全連結原則，設定為 [關閉] 時，請選取 [ **關閉** ]，以 **在郵件中選取未知的可能惡意 URLs 動作**。</span><span class="sxs-lookup"><span data-stu-id="3599e-125">Use [Set up Safe Links policies in Defender for Office 365](set-up-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="3599e-126">建立反惡意程式碼原則，關閉惡意程式碼零小時自動清除。</span><span class="sxs-lookup"><span data-stu-id="3599e-126">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="3599e-127">請參閱 [使用安全性 & 規範中心建立反惡意程式碼原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，將 **惡意軟體設定為零小時自動清除** **。**</span><span class="sxs-lookup"><span data-stu-id="3599e-127">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="3599e-128">建立垃圾郵件篩選原則，以停用自訂信箱中垃圾郵件和網路釣魚的零小時自動清除 (ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="3599e-128">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="3599e-129">請參閱 [使用安全性 & 規範中心建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，並清除 **垃圾郵件 Zap** 和 **網路釣魚 zap** 的 **On** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3599e-129">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="3599e-130">停用自訂信箱中的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="3599e-130">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="3599e-131">使用 [ [設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md) ] 以停用垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="3599e-131">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="3599e-132">停用之後，EOP 無法根據垃圾郵件篩選判定動作將郵件移至垃圾郵件資料夾。 **將郵件移至垃圾郵件資料夾** 或信箱上的安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="3599e-132">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="3599e-133">在您確認您的信箱符合所有適用的先決條件後，請 [使用安全性 & 合規性中心，設定本文中的使用者提交信箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。</span><span class="sxs-lookup"><span data-stu-id="3599e-133">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3599e-134">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="3599e-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3599e-135">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="3599e-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3599e-136">若要直接移至 [ **使用者報送** ] 頁面，請使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="3599e-136">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="3599e-137">若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="3599e-137">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="3599e-138">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="3599e-138">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="3599e-139">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。</span><span class="sxs-lookup"><span data-stu-id="3599e-139">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="3599e-140">您需要存取 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3599e-140">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="3599e-141">如果您嘗試使用的帳戶無法存取 Exchange Online PowerShell，當您指定提交信箱時，您會收到如下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="3599e-141">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="3599e-142">在您的網域中指定電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="3599e-142">Specify an email address in your domain</span></span>

  <span data-ttu-id="3599e-143">如需啟用或停用 Exchange Online PowerShell 存取權的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="3599e-143">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="3599e-144">啟用或停用存取 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3599e-144">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="3599e-145">Exchange Online 中的用戶端存取規則</span><span class="sxs-lookup"><span data-stu-id="3599e-145">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="3599e-146">使用安全性 & 規範中心設定使用者提交信箱</span><span class="sxs-lookup"><span data-stu-id="3599e-146">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="3599e-147">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **使用者報送**。</span><span class="sxs-lookup"><span data-stu-id="3599e-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="3599e-148">在出現的 [ **使用者提交** ] 頁面中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="3599e-148">In the **User submissions** page that appears, select one of the following options:</span></span>

      1. <span data-ttu-id="3599e-149">**啟用 (建議) 的 Outlook 報告郵件功能**：若您使用報表訊息增益集、網頁型 outlook 中的報表網路釣魚增益集或內建報告，請選取此選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="3599e-149">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

    - <span data-ttu-id="3599e-150">**自訂使用者確認訊息**：按一下此連結。</span><span class="sxs-lookup"><span data-stu-id="3599e-150">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="3599e-151">在出現的 [ **自訂確認訊息** ] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="3599e-151">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

        - <span data-ttu-id="3599e-152">**提交之前**：在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用報告訊息增益集或報告網路釣魚增益集報告郵件之前看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="3599e-152">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="3599e-153">您可以使用變數% type%，以包含提交類型 (垃圾郵件、非垃圾郵件、網路釣魚網路等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="3599e-153">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

          <span data-ttu-id="3599e-154">如所述，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：</span><span class="sxs-lookup"><span data-stu-id="3599e-154">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="3599e-155">您的電子郵件會向 Microsoft 提交，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="3599e-155">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="3599e-156">有些電子郵件可能包含個人或機密資訊。</span><span class="sxs-lookup"><span data-stu-id="3599e-156">Some emails might contain personal or sensitive information.</span></span>

        - <span data-ttu-id="3599e-157">**提交後**：按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="3599e-157">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="3599e-158">在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用報告訊息增益集或報告網路釣魚增益集報告訊息之後所看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="3599e-158">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="3599e-159">您可以使用變數% type% 來包含提交類型。</span><span class="sxs-lookup"><span data-stu-id="3599e-159">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="3599e-160">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3599e-160">When you're finished, click **Save**.</span></span> <span data-ttu-id="3599e-161">若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原** 回來]。</span><span class="sxs-lookup"><span data-stu-id="3599e-161">To clear these values, click **Restore** back on the **User submissions** page.</span></span>
    
    - <span data-ttu-id="3599e-162">**自訂最終使用者報告選項**：按一下此連結。</span><span class="sxs-lookup"><span data-stu-id="3599e-162">**Customize the end-user reporting options**: Click this link.</span></span> <span data-ttu-id="3599e-163">在出現的 [ **自訂最終使用者報告選項** ] 浮出控制項中，輸入垃圾郵件報告選項的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="3599e-163">In the **Customize end-user reporting options** flyout that appears, enter the descriptive text for Junk email reporting options.</span></span> 
    
      <span data-ttu-id="3599e-164">在 **報告訊息時顯示** 的 [選項] 底下，在下列選項中至少選取一個選項：</span><span class="sxs-lookup"><span data-stu-id="3599e-164">Under **Options to show when messages are reported**, select at least one among the following options:</span></span>
        - <span data-ttu-id="3599e-165">**傳送報告之前向我提問**</span><span class="sxs-lookup"><span data-stu-id="3599e-165">**Ask me before sending a report**</span></span>
        - <span data-ttu-id="3599e-166">**自動傳送報告**</span><span class="sxs-lookup"><span data-stu-id="3599e-166">**Automatically send reports**</span></span>
        - <span data-ttu-id="3599e-167">**從不傳送報告**</span><span class="sxs-lookup"><span data-stu-id="3599e-167">**Never send reports**</span></span>
       
      <span data-ttu-id="3599e-168">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3599e-168">When you're finished, click **Save**.</span></span>

        - <span data-ttu-id="3599e-169">**將報告的郵件傳送至**：進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="3599e-169">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="3599e-170">**Microsoft (建議)**：不使用使用者提交信箱 (所有報告的郵件都移至 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="3599e-170">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="3599e-171">**Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3599e-171">**Both Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="3599e-172">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="3599e-172">Distribution groups are not allowed.</span></span> <span data-ttu-id="3599e-173">使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。</span><span class="sxs-lookup"><span data-stu-id="3599e-173">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="3599e-174">**僅限自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3599e-174">**Custom mailbox only**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="3599e-175">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="3599e-175">Distribution groups are not allowed.</span></span> <span data-ttu-id="3599e-176">如果您只想要將郵件移至系統管理員或安全性作業小組進行分析，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="3599e-176">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="3599e-177">除非系統管理員自行轉寄，否則郵件不會移至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3599e-177">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!NOTE]
          > <span data-ttu-id="3599e-178">美國政府組織 (GCC、GCC 和 DoD) 只能設定 **自訂信箱**。</span><span class="sxs-lookup"><span data-stu-id="3599e-178">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="3599e-179">其他兩個選項會停用。</span><span class="sxs-lookup"><span data-stu-id="3599e-179">The other two options are disabled.</span></span>

          > [!NOTE]
          > <span data-ttu-id="3599e-180">如果組織已設定為僅傳送至自訂信箱，將不會傳送報告的郵件以進行重新掃描，而且使用者報告的郵件入口網站將永遠會是空的。</span><span class="sxs-lookup"><span data-stu-id="3599e-180">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

      <span data-ttu-id="3599e-181">完成後，請按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="3599e-181">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="3599e-182">如果您已在使用 Outlook 的網頁信箱原則上使用 Outlook 在 [outlook 中停用 [垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) ]，但您設定上述任一設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集或報告網路釣魚增益集，在網頁型 outlook 中向 microsoft 報告郵件。</span><span class="sxs-lookup"><span data-stu-id="3599e-182">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>


    2. <span data-ttu-id="3599e-183">**停用 outlook 的報告郵件功能**：如果您使用協力廠商報告工具，而不是報告郵件增益集、報告網路釣魚增益集或網頁型 Outlook 中的內建報告，請選取此選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="3599e-183">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

       <span data-ttu-id="3599e-184">選取 [ **使用此自訂信箱以接收使用者報告的提交**]。</span><span class="sxs-lookup"><span data-stu-id="3599e-184">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="3599e-185">在出現的方塊中，輸入已存在於 Office 365 的現有信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3599e-185">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="3599e-186">這必須是 Exchange Online 中可接收電子郵件的現有信箱。</span><span class="sxs-lookup"><span data-stu-id="3599e-186">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

       <span data-ttu-id="3599e-187">完成後，請按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="3599e-187">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="3599e-188">郵件提交格式</span><span class="sxs-lookup"><span data-stu-id="3599e-188">Message submission format</span></span>

<span data-ttu-id="3599e-189">傳送至自訂信箱的郵件必須遵循特定提交郵件格式。</span><span class="sxs-lookup"><span data-stu-id="3599e-189">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="3599e-190">提交的主旨 (信封標題) 應該使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="3599e-190">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="3599e-191">其中，SafetyAPIAction 是下列其中一個整數值：</span><span class="sxs-lookup"><span data-stu-id="3599e-191">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="3599e-192">1：垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="3599e-192">1: Junk</span></span>
- <span data-ttu-id="3599e-193">2：非垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="3599e-193">2: Not junk</span></span>
- <span data-ttu-id="3599e-194">3：網路釣魚</span><span class="sxs-lookup"><span data-stu-id="3599e-194">3: Phishing</span></span>

<span data-ttu-id="3599e-195">在下列範例中：</span><span class="sxs-lookup"><span data-stu-id="3599e-195">In the following example:</span></span>

- <span data-ttu-id="3599e-196">將郵件報告為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="3599e-196">The message is being reported as phishing.</span></span>
- <span data-ttu-id="3599e-197">網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="3599e-197">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="3599e-198">寄件者 IP 為167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="3599e-198">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="3599e-199">[寄件者] 位址為 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3599e-199">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="3599e-200">郵件的主旨行是「測試網路釣魚提交」</span><span class="sxs-lookup"><span data-stu-id="3599e-200">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="3599e-201">不遵循此格式的郵件將無法在提交入口網站中正確顯示。</span><span class="sxs-lookup"><span data-stu-id="3599e-201">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
