---
title: 使用者提交原則
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
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
ms.openlocfilehash: 9759bbae1dc49b80859198e11e6f85383cdf2f66
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988125"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="02751-103">使用者提交原則</span><span class="sxs-lookup"><span data-stu-id="02751-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="02751-104">在使用 Exchange Online 信箱的 Microsoft 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。</span><span class="sxs-lookup"><span data-stu-id="02751-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="02751-105">當使用者使用各種報告選項送出郵件時，您可以使用此信箱來截取郵件 (只) 或接收郵件副本 (傳送至自訂信箱和 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="02751-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="02751-106">這項功能可搭配下列郵件報告選項使用：</span><span class="sxs-lookup"><span data-stu-id="02751-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="02751-107">報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="02751-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="02751-108">報表網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="02751-108">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="02751-109">[Outlook 網頁版中 (的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) （以前稱為 Outlook web App）) </span><span class="sxs-lookup"><span data-stu-id="02751-109">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="02751-110">Outlook 中用於 iOS 和 Android 的內建報告</span><span class="sxs-lookup"><span data-stu-id="02751-110">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="02751-111">如果 [在網頁上的 outlook 中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，讓使用者在這裡提交，將會覆寫該設定，讓使用者再次在 Outlook 的 outlook 中報告郵件。</span><span class="sxs-lookup"><span data-stu-id="02751-111">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="02751-112">您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="02751-112">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="02751-113">將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統 [管理員提交](admin-submission.md)將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="02751-113">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="02751-114">自訂信箱必要條件</span><span class="sxs-lookup"><span data-stu-id="02751-114">Custom mailbox prerequisites</span></span>

<span data-ttu-id="02751-115">使用下列文章來設定必要的必要條件，讓使用者報告的郵件進入您的自訂信箱：</span><span class="sxs-lookup"><span data-stu-id="02751-115">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="02751-116">建立 exchange 郵件流程規則以設定垃圾郵件信賴等級，以略過自訂信箱上的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="02751-116">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="02751-117">請參閱 [使用 EAC 建立郵件流程規則，將郵件的 scl](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 設定為將 scl 設定為 **-1**。</span><span class="sxs-lookup"><span data-stu-id="02751-117">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="02751-118">關閉自訂信箱中的惡意程式碼的掃描附件。</span><span class="sxs-lookup"><span data-stu-id="02751-118">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="02751-119">使用 [在 Office 365 中設定安全附件](set-up-atp-safe-attachments-policies.md)原則，以建立安全附件原則，**關閉\*\*\*\*安全附件未知惡意程式碼回應**。</span><span class="sxs-lookup"><span data-stu-id="02751-119">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-atp-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="02751-120">在自訂信箱的郵件上關閉 URL 掃描。</span><span class="sxs-lookup"><span data-stu-id="02751-120">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="02751-121">使用 [在 Office 365 中的 [設定安全連結原則](set-up-atp-safe-links-policies.md) ] 來建立安全連結原則，設定為 [關閉] 時，請選取 [ **關閉** ]，以 **在郵件中選取未知的可能惡意 URLs 動作**。</span><span class="sxs-lookup"><span data-stu-id="02751-121">Use [Set up Safe Links policies in Defender for Office 365](set-up-atp-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="02751-122">建立反惡意程式碼原則，關閉惡意程式碼零小時自動清除。</span><span class="sxs-lookup"><span data-stu-id="02751-122">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="02751-123">請參閱 [使用安全性 & 規範中心建立反惡意程式碼原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，將 **惡意軟體設定為零小時自動清除** **。**</span><span class="sxs-lookup"><span data-stu-id="02751-123">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="02751-124">建立垃圾郵件篩選原則，以停用自訂信箱中垃圾郵件和網路釣魚的零小時自動清除 (ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="02751-124">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="02751-125">請參閱 [使用安全性 & 規範中心建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，並清除 **垃圾郵件 Zap** 和 **網路釣魚 zap** 的 **On** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="02751-125">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="02751-126">停用自訂信箱中的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="02751-126">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="02751-127">使用 [ [設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md) ] 以停用垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="02751-127">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="02751-128">停用之後，EOP 無法根據垃圾郵件篩選判定動作將郵件移至垃圾郵件資料夾。 **將郵件移至垃圾郵件資料夾** 或信箱上的安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="02751-128">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="02751-129">在您確認您的信箱符合所有適用的先決條件後，請 [使用安全性 & 合規性中心，設定本文中的使用者提交信箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。</span><span class="sxs-lookup"><span data-stu-id="02751-129">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="02751-130">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="02751-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="02751-131">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="02751-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="02751-132">若要直接移至 [ **使用者報送** ] 頁面，請使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="02751-132">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="02751-133">若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="02751-133">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="02751-134">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="02751-134">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="02751-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。</span><span class="sxs-lookup"><span data-stu-id="02751-135">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="02751-136">您需要存取 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="02751-136">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="02751-137">如果您嘗試使用的帳戶無法存取 Exchange Online PowerShell，當您指定提交信箱時，您會收到如下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="02751-137">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="02751-138">在您的網域中指定電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="02751-138">Specify an email address in your domain</span></span>

  <span data-ttu-id="02751-139">如需啟用或停用 Exchange Online PowerShell 存取權的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="02751-139">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="02751-140">啟用或停用存取 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="02751-140">Enable or disable access to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="02751-141">Exchange Online 中的用戶端存取規則</span><span class="sxs-lookup"><span data-stu-id="02751-141">Client Access Rules in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="02751-142">使用安全性 & 規範中心設定使用者提交信箱</span><span class="sxs-lookup"><span data-stu-id="02751-142">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="02751-143">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **使用者報送**。</span><span class="sxs-lookup"><span data-stu-id="02751-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="02751-144">在出現的 [ **使用者提交** ] 頁面中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="02751-144">In the **User submissions** page that appears, select one of the following options:</span></span>

   1. <span data-ttu-id="02751-145">**啟用 (建議) 的 Outlook 報告郵件功能**：若您使用報表訊息增益集、網頁型 outlook 中的報表網路釣魚增益集或內建報告，請選取此選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="02751-145">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="02751-146">**自訂使用者確認訊息**：按一下此連結。</span><span class="sxs-lookup"><span data-stu-id="02751-146">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="02751-147">在出現的 [ **自訂確認訊息** ] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="02751-147">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="02751-148">**提交之前**：在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用報告訊息增益集或報告網路釣魚增益集報告郵件之前看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="02751-148">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="02751-149">您可以使用變數% type%，以包含提交類型 (垃圾郵件、非垃圾郵件、網路釣魚網路等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="02751-149">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="02751-150">如所述，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：</span><span class="sxs-lookup"><span data-stu-id="02751-150">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="02751-151">您的電子郵件會向 Microsoft 提交，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="02751-151">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="02751-152">有些電子郵件可能包含個人或機密資訊。</span><span class="sxs-lookup"><span data-stu-id="02751-152">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="02751-153">**提交後**：按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="02751-153">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="02751-154">在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用報告訊息增益集或報告網路釣魚增益集報告訊息之後所看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="02751-154">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="02751-155">您可以使用變數% type% 來包含提交類型。</span><span class="sxs-lookup"><span data-stu-id="02751-155">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="02751-156">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="02751-156">When you're finished, click **Save**.</span></span> <span data-ttu-id="02751-157">若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原** 回來]。</span><span class="sxs-lookup"><span data-stu-id="02751-157">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="02751-158">**將報告的郵件傳送至**：進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="02751-158">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="02751-159">**Microsoft (建議)**：不使用使用者提交信箱 (所有報告的郵件都移至 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="02751-159">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="02751-160">**Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="02751-160">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="02751-161">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="02751-161">Distribution groups are not allowed.</span></span> <span data-ttu-id="02751-162">使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。</span><span class="sxs-lookup"><span data-stu-id="02751-162">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="02751-163">**自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="02751-163">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="02751-164">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="02751-164">Distribution groups are not allowed.</span></span> <span data-ttu-id="02751-165">如果您只想要將郵件移至系統管理員或安全性作業小組進行分析，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="02751-165">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="02751-166">除非系統管理員自行轉寄，否則郵件不會移至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="02751-166">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="02751-167">美國政府組織 (GCC、GCC 和 DoD) 只能設定 **自訂信箱**。</span><span class="sxs-lookup"><span data-stu-id="02751-167">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="02751-168">其他兩個選項會停用。</span><span class="sxs-lookup"><span data-stu-id="02751-168">The other two options are disabled.</span></span>

      <span data-ttu-id="02751-169">完成後，請按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="02751-169">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="02751-170">如果您已在使用 Outlook 的網頁信箱原則上使用 Outlook 在 [outlook 中停用 [垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) ]，但您設定上述任一設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集或報告網路釣魚增益集，在網頁型 outlook 中向 microsoft 報告郵件。</span><span class="sxs-lookup"><span data-stu-id="02751-170">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>

   - <span data-ttu-id="02751-171">**停用 Outlook 的報告郵件功能**：若您使用協力廠商報告工具（而非報告郵件增益集），請在網頁型 Outlook 中使用協力廠商的報表工具，或內建的報告，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="02751-171">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="02751-172">選取 [ **使用此自訂信箱以接收使用者報告的提交**]。</span><span class="sxs-lookup"><span data-stu-id="02751-172">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="02751-173">在出現的方塊中，輸入已存在於 Office 365 的現有信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="02751-173">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="02751-174">這必須是 Exchange Online 中可接收電子郵件的現有信箱。</span><span class="sxs-lookup"><span data-stu-id="02751-174">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="02751-175">完成後，請按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="02751-175">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="02751-176">郵件提交格式</span><span class="sxs-lookup"><span data-stu-id="02751-176">Message submission format</span></span>

<span data-ttu-id="02751-177">傳送至自訂信箱的郵件必須遵循特定提交郵件格式。</span><span class="sxs-lookup"><span data-stu-id="02751-177">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="02751-178">提交的主旨 (信封標題) 應該使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="02751-178">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="02751-179">其中，SafetyAPIAction 是下列其中一個整數值：</span><span class="sxs-lookup"><span data-stu-id="02751-179">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="02751-180">1：垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="02751-180">1: Junk</span></span>
- <span data-ttu-id="02751-181">2：非垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="02751-181">2: Not junk</span></span>
- <span data-ttu-id="02751-182">3：網路釣魚</span><span class="sxs-lookup"><span data-stu-id="02751-182">3: Phishing</span></span>

<span data-ttu-id="02751-183">在下列範例中：</span><span class="sxs-lookup"><span data-stu-id="02751-183">In the following example:</span></span>

- <span data-ttu-id="02751-184">將郵件報告為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="02751-184">The message is being reported as phishing.</span></span>
- <span data-ttu-id="02751-185">網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="02751-185">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="02751-186">寄件者 IP 為167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="02751-186">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="02751-187">[寄件者] 位址為 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="02751-187">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="02751-188">郵件的主旨行是「測試網路釣魚提交」</span><span class="sxs-lookup"><span data-stu-id="02751-188">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="02751-189">不遵循此格式的郵件將無法在提交入口網站中正確顯示。</span><span class="sxs-lookup"><span data-stu-id="02751-189">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
