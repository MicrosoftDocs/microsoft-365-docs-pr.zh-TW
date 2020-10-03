---
title: 使用者提交原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.openlocfilehash: bffa70184a9307869ce6170ba1ea05ae3f084ccf
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350268"
---
# <a name="user-submissions-policies"></a><span data-ttu-id="cd38a-103">使用者提交原則</span><span class="sxs-lookup"><span data-stu-id="cd38a-103">User submissions policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cd38a-104">在使用 Exchange Online 信箱的 Microsoft 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。</span><span class="sxs-lookup"><span data-stu-id="cd38a-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="cd38a-105">當使用者使用各種報告選項送出郵件時，您可以使用此信箱來截取郵件 (只) 或接收郵件副本 (傳送至自訂信箱和 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="cd38a-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="cd38a-106">這項功能可搭配下列郵件報告選項使用：</span><span class="sxs-lookup"><span data-stu-id="cd38a-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="cd38a-107">報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="cd38a-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="cd38a-108">[Outlook 網頁版中 (的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) （以前稱為 Outlook web App）) </span><span class="sxs-lookup"><span data-stu-id="cd38a-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="cd38a-109">Outlook 中用於 iOS 和 Android 的內建報告</span><span class="sxs-lookup"><span data-stu-id="cd38a-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="cd38a-110">如果 [在網頁上的 outlook 中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，讓使用者在這裡提交，將會覆寫該設定，讓使用者再次在 Outlook 的 outlook 中報告郵件。</span><span class="sxs-lookup"><span data-stu-id="cd38a-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="cd38a-111">您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="cd38a-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="cd38a-112">將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統 [管理員提交](admin-submission.md)將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="cd38a-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="cd38a-113">自訂信箱必要條件</span><span class="sxs-lookup"><span data-stu-id="cd38a-113">Custom mailbox prerequisites</span></span>

<span data-ttu-id="cd38a-114">使用下列文章來設定必要的必要條件，讓使用者報告的郵件進入您的自訂信箱：</span><span class="sxs-lookup"><span data-stu-id="cd38a-114">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="cd38a-115">透過建立 exchange 郵件流程規則來設定垃圾郵件信賴等級，以略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="cd38a-115">Skip spam filtering by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="cd38a-116">請參閱 [使用 EAC 建立郵件流程規則，將郵件的 scl](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages?view=o365-worldwide#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 設定為將 scl 設定為 **-1**。</span><span class="sxs-lookup"><span data-stu-id="cd38a-116">See [Use the EAC to create a mail flow rule that sets the SCL of a message](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages?view=o365-worldwide#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="cd38a-117">關閉掃描附件的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="cd38a-117">Turn off scanning attachments for malware.</span></span> <span data-ttu-id="cd38a-118">使用 [Set up (或 edit) ATP 安全附件原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide#step-2-set-up-or-edit-an-atp-safe-attachments-policy) ，以建立安全附件原則，而不會 **掃描啟用惡意** 代碼的設定。</span><span class="sxs-lookup"><span data-stu-id="cd38a-118">Use [Set up (or edit) an ATP Safe Attachments policy](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide#step-2-set-up-or-edit-an-atp-safe-attachments-policy) to create a Safe Attachments policy with the setting **Off - Attachment will not be scanned for malware** enabled.</span></span>

- <span data-ttu-id="cd38a-119">關閉郵件上的 URL 掃描。</span><span class="sxs-lookup"><span data-stu-id="cd38a-119">Turn off URL scanning on messages.</span></span> <span data-ttu-id="cd38a-120">使用 [ [新增 (] 或 [編輯) ATP 安全連結原則套用至所有或特定的電子郵件](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-links-policies?view=o365-worldwide#step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients) 收件者若要建立安全連結原則， **請選取 [將郵件中的未知潛在惡意 URLs 的動作** ] 設定為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="cd38a-120">Use [Add (or edit) ATP Safe Links policies that apply to all or specific email recipients](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-links-policies?view=o365-worldwide#step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients) to create a Safe Links policy with **Select the action for unknown potentially malicious URLs in messages** set to **Off**.</span></span>

- <span data-ttu-id="cd38a-121">建立反惡意程式碼原則，關閉惡意程式碼零小時自動清除。</span><span class="sxs-lookup"><span data-stu-id="cd38a-121">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="cd38a-122">請參閱[使用安全性 & 規範中心建立反惡意程式碼原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies)，將**惡意軟體設定為零小時自動清除** **。**</span><span class="sxs-lookup"><span data-stu-id="cd38a-122">See [Use the Security & Compliance Center to create anti-malware policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="cd38a-123">建立垃圾郵件篩選原則，以停用以零小時自動清除 (用於垃圾郵件 ZAP 和網路釣魚 ZAP 的 ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="cd38a-123">Create a spam filter policy to disable Zero-hour Auto Purge (ZAP) for Spam ZAP and Phish ZAP.</span></span> <span data-ttu-id="cd38a-124">請參閱 [使用安全性 & 規範中心建立反垃圾郵件原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) ，並清除垃圾郵件 Zap 和網路釣魚 Zap 的 **On** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cd38a-124">See [Use the Security & Compliance Center to create anti-spam policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for Spam ZAP and Phish ZAP.</span></span>

- <span data-ttu-id="cd38a-125">停用垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="cd38a-125">Disable the junk email rule.</span></span> <span data-ttu-id="cd38a-126">使用 [ [設定 Exchange Online 信箱上的垃圾郵件設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes?view=o365-worldwide) ] 以停用垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="cd38a-126">Use [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes?view=o365-worldwide) to disable the junk email rule.</span></span> <span data-ttu-id="cd38a-127">停用之後，EOP 無法根據垃圾郵件篩選判定動作將郵件移至垃圾郵件資料夾。 **將郵件移至垃圾郵件資料夾** 或信箱上的安全清單集合。</span><span class="sxs-lookup"><span data-stu-id="cd38a-127">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="cd38a-128">在您確認您的信箱符合所有適用的先決條件後，請 [使用安全性 & 合規性中心，設定本文中的使用者提交信箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。</span><span class="sxs-lookup"><span data-stu-id="cd38a-128">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cd38a-129">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="cd38a-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cd38a-130">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="cd38a-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cd38a-131">若要直接移至 [ **使用者報送** ] 頁面，請使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="cd38a-131">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="cd38a-132">若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="cd38a-132">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="cd38a-133">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="cd38a-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="cd38a-134">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**組織管理**。</span><span class="sxs-lookup"><span data-stu-id="cd38a-134">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="cd38a-135">使用安全性 & 規範中心設定使用者提交信箱</span><span class="sxs-lookup"><span data-stu-id="cd38a-135">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="cd38a-136">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **使用者報送**。</span><span class="sxs-lookup"><span data-stu-id="cd38a-136">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="cd38a-137">在出現的 [ **使用者提交** ] 頁面中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="cd38a-137">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="cd38a-138">a.</span><span class="sxs-lookup"><span data-stu-id="cd38a-138">a.</span></span> <span data-ttu-id="cd38a-139">\*\*啟用 (建議) 的 Outlook 報告郵件功能 \*\*：若您在網頁型 outlook 中使用報表訊息增益集或內建報告，請選取此選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="cd38a-139">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="cd38a-140">**自訂使用者確認訊息**：按一下此連結。</span><span class="sxs-lookup"><span data-stu-id="cd38a-140">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="cd38a-141">在出現的 [ **自訂確認訊息** ] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="cd38a-141">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="cd38a-142">**提交之前**：在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用「報告郵件增益集」報告郵件之前看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="cd38a-142">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="cd38a-143">您可以使用變數% type%，以包含提交類型 (垃圾郵件、非垃圾郵件、網路釣魚網路等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="cd38a-143">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="cd38a-144">如所述，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：</span><span class="sxs-lookup"><span data-stu-id="cd38a-144">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="cd38a-145">您的電子郵件會向 Microsoft 提交，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="cd38a-145">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="cd38a-146">有些電子郵件可能包含個人或機密資訊。</span><span class="sxs-lookup"><span data-stu-id="cd38a-146">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="cd38a-147">**提交後**：按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="cd38a-147">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="cd38a-148">在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用「報告訊息增益集」報告訊息之後所看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="cd38a-148">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="cd38a-149">您可以使用變數% type% 來包含提交類型。</span><span class="sxs-lookup"><span data-stu-id="cd38a-149">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="cd38a-150">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd38a-150">When you're finished, click **Save**.</span></span> <span data-ttu-id="cd38a-151">若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原**回來]。</span><span class="sxs-lookup"><span data-stu-id="cd38a-151">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="cd38a-152">**將報告的郵件傳送至**：進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="cd38a-152">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="cd38a-153">\*\*Microsoft (建議) \*\*：不使用使用者提交信箱 (所有報告的郵件都移至 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="cd38a-153">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="cd38a-154">**Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cd38a-154">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="cd38a-155">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="cd38a-155">Distribution groups are not allowed.</span></span> <span data-ttu-id="cd38a-156">使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。</span><span class="sxs-lookup"><span data-stu-id="cd38a-156">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="cd38a-157">**自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cd38a-157">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="cd38a-158">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="cd38a-158">Distribution groups are not allowed.</span></span> <span data-ttu-id="cd38a-159">如果您只想要將郵件移至系統管理員或安全性作業小組進行分析，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="cd38a-159">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="cd38a-160">除非系統管理員自行轉寄，否則郵件不會移至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="cd38a-160">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="cd38a-161">美國政府組織 (GCC、GCC 和 DoD) 只能設定 **自訂信箱**。</span><span class="sxs-lookup"><span data-stu-id="cd38a-161">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="cd38a-162">其他兩個選項會停用。</span><span class="sxs-lookup"><span data-stu-id="cd38a-162">The other two options are disabled.</span></span> 

      <span data-ttu-id="cd38a-163">完成後，請按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="cd38a-163">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="cd38a-164">如果您已在 Outlook 網頁版 outlook 上使用 Outlook 來 [停用 outlook 中的垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) ，但您設定上述任一設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集，在網頁型 outlook 中將郵件報告給 microsoft。</span><span class="sxs-lookup"><span data-stu-id="cd38a-164">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="cd38a-165">**停用 Outlook 的報告郵件功能**：如果您使用協力廠商的報表工具，而不是在 web 上的 Outlook 中使用協力廠商的報表工具或內建的報表，請選取這個選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="cd38a-165">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="cd38a-166">選取 [ **使用此自訂信箱以接收使用者報告的提交**]。</span><span class="sxs-lookup"><span data-stu-id="cd38a-166">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="cd38a-167">在出現的方塊中，輸入已存在於 Office 365 的現有信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cd38a-167">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="cd38a-168">這必須是 Exchange Online 中可接收電子郵件的現有信箱。</span><span class="sxs-lookup"><span data-stu-id="cd38a-168">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="cd38a-169">完成後，請按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="cd38a-169">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="cd38a-170">郵件提交格式</span><span class="sxs-lookup"><span data-stu-id="cd38a-170">Message submission format</span></span>

<span data-ttu-id="cd38a-171">傳送至自訂信箱的郵件必須遵循特定提交郵件格式。</span><span class="sxs-lookup"><span data-stu-id="cd38a-171">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="cd38a-172">提交的主旨 (信封標題) 應該使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="cd38a-172">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="cd38a-173">SafetyAPIAction 為下列其中一個整數值：</span><span class="sxs-lookup"><span data-stu-id="cd38a-173">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="cd38a-174">1：垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="cd38a-174">1: Junk</span></span>
- <span data-ttu-id="cd38a-175">2： NotJunk</span><span class="sxs-lookup"><span data-stu-id="cd38a-175">2: NotJunk</span></span>
- <span data-ttu-id="cd38a-176">3：網路釣魚</span><span class="sxs-lookup"><span data-stu-id="cd38a-176">3: Phish</span></span>

<span data-ttu-id="cd38a-177">在下列範例中：</span><span class="sxs-lookup"><span data-stu-id="cd38a-177">In the following example:</span></span>

- <span data-ttu-id="cd38a-178">將郵件報告為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="cd38a-178">The message is being reported as Phish.</span></span>
- <span data-ttu-id="cd38a-179">網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="cd38a-179">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="cd38a-180">寄件者 IP 為167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="cd38a-180">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="cd38a-181">[寄件者] 位址為 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cd38a-181">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="cd38a-182">郵件的主旨行是「測試網路釣魚提交」</span><span class="sxs-lookup"><span data-stu-id="cd38a-182">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="cd38a-183">不遵循此格式的郵件將無法在提交入口網站中正確顯示。</span><span class="sxs-lookup"><span data-stu-id="cd38a-183">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
