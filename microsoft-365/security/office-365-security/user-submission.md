---
title: 為使用者提交的垃圾郵件和網路釣魚郵件指定信箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.openlocfilehash: 6aa343b337139c4d81f35f78a227634d3b6a8781
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262520"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="706de-103">在 Exchange Online 中指定使用者提交垃圾郵件和網路釣魚郵件的信箱</span><span class="sxs-lookup"><span data-stu-id="706de-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="706de-104">在使用 Exchange Online 信箱的 Microsoft 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。</span><span class="sxs-lookup"><span data-stu-id="706de-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="706de-105">當使用者使用各種報告選項提交郵件時，您可以使用此信箱來攔截郵件（只傳送至自訂信箱），或接收郵件的副本（傳送至自訂信箱和 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="706de-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="706de-106">這項功能可搭配下列郵件報告選項使用：</span><span class="sxs-lookup"><span data-stu-id="706de-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="706de-107">報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="706de-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="706de-108">[Outlook 網頁版中的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)（以前稱為 Outlook web App）</span><span class="sxs-lookup"><span data-stu-id="706de-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="706de-109">如果[在網頁上的 outlook 中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，讓使用者在這裡提交，將會覆寫該設定，讓使用者再次在 Outlook 的 outlook 中報告郵件。</span><span class="sxs-lookup"><span data-stu-id="706de-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="706de-110">您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="706de-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="706de-111">將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統[管理員提交](admin-submission.md)將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="706de-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="706de-112">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="706de-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="706de-113">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="706de-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="706de-114">若要直接移至 [**使用者報送**] 頁面，請使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="706de-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="706de-115">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="706de-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="706de-116">若要連線至獨立 EOP PowerShell，請參閱[connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="706de-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="706de-117">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="706de-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="706de-118">若要設定使用者提交的信箱，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="706de-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="706de-119">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="706de-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="706de-120">使用安全性 & 規範中心設定使用者提交信箱</span><span class="sxs-lookup"><span data-stu-id="706de-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="706de-121">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> **原則**] \> **使用者報送**。</span><span class="sxs-lookup"><span data-stu-id="706de-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="706de-122">在出現的 [**使用者提交**] 頁面中，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="706de-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="706de-123">a.</span><span class="sxs-lookup"><span data-stu-id="706de-123">a.</span></span> <span data-ttu-id="706de-124">**啟用 outlook 的報告郵件功能（建議）**：如果您在網頁型 outlook 中使用報表訊息增益集或內建報告，請選取此選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="706de-124">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="706de-125">**自訂使用者確認訊息**：按一下此連結。</span><span class="sxs-lookup"><span data-stu-id="706de-125">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="706de-126">在出現的 [**自訂確認訊息**] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="706de-126">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="706de-127">**提交之前**：在 [**標題**] 和 [**確認訊息**] 方塊中，輸入使用者在使用「報告郵件增益集」報告郵件之前看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="706de-127">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="706de-128">您可以使用變數% type% 來包含提交類型（垃圾郵件、非垃圾郵件網路釣魚等等）。</span><span class="sxs-lookup"><span data-stu-id="706de-128">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="706de-129">如所述，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：</span><span class="sxs-lookup"><span data-stu-id="706de-129">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="706de-130">您的電子郵件會向 Microsoft 提交，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="706de-130">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="706de-131">有些電子郵件可能包含個人或機密資訊。</span><span class="sxs-lookup"><span data-stu-id="706de-131">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="706de-132">**提交後**：按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="706de-132">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="706de-133">在 [**標題**] 和 [**確認訊息**] 方塊中，輸入使用者在使用「報告訊息增益集」報告訊息之後所看到的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="706de-133">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="706de-134">您可以使用變數% type% 來包含提交類型。</span><span class="sxs-lookup"><span data-stu-id="706de-134">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="706de-135">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="706de-135">When you're finished, click **Save**.</span></span> <span data-ttu-id="706de-136">若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原**回來]。</span><span class="sxs-lookup"><span data-stu-id="706de-136">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="706de-137">**將報告的郵件傳送至**：進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="706de-137">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="706de-138">**Microsoft （建議使用）**：不使用使用者提交信箱（所有報告的郵件都會移至 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="706de-138">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="706de-139">**Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="706de-139">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="706de-140">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="706de-140">Distribution groups are not allowed.</span></span> <span data-ttu-id="706de-141">使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。</span><span class="sxs-lookup"><span data-stu-id="706de-141">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="706de-142">**自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="706de-142">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="706de-143">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="706de-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="706de-144">如果您只想要讓郵件先移至 [系統管理] 或 [安全性作業] 小組進行分析，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="706de-144">Use this option if you want the message to only go to the admin or security operations team for analysis first.</span></span> <span data-ttu-id="706de-145">除非系統管理員轉寄郵件，否則郵件不會移至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="706de-145">Messages will not go to Microsoft unless the admin forwards it.</span></span>

        <span data-ttu-id="706de-146">完成後，請按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="706de-146">When you're finished, click **Confirm**.</span></span>

        ![將報告的郵件傳送至 Microsoft 和自訂信箱](../../media/user-submission-enable-outlook-report-message.png)

     > [!CAUTION]
     > <span data-ttu-id="706de-148">如果您已在 Outlook 網頁版 outlook 上使用 Outlook 來[停用 outlook 中的垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)，但您設定上述任一設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集，在網頁型 outlook 中將郵件報告給 microsoft。</span><span class="sxs-lookup"><span data-stu-id="706de-148">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="706de-149">**停用 Outlook 的報告郵件功能**：如果您使用協力廠商的報表工具，而不是在 web 上的 Outlook 中使用協力廠商的報表工具或內建的報表，請選取這個選項，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="706de-149">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="706de-150">選取 [**使用此自訂信箱以接收使用者報告的提交**]。</span><span class="sxs-lookup"><span data-stu-id="706de-150">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="706de-151">在出現的方塊中，輸入已存在於 Office 365 的現有信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="706de-151">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="706de-152">這必須是 Exchange Online 中可接收電子郵件的現有信箱。</span><span class="sxs-lookup"><span data-stu-id="706de-152">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="706de-153">完成後，請按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="706de-153">When you're finished, click **Confirm**.</span></span>

      ![使用協力廠商工具將報告的郵件傳送至自訂信箱](../../media/user-submission-disable-outlook-report-message.png)
     
## <a name="message-submission-format"></a><span data-ttu-id="706de-155">郵件提交格式</span><span class="sxs-lookup"><span data-stu-id="706de-155">Message submission format</span></span>

<span data-ttu-id="706de-156">傳送至自訂信箱的郵件必須遵循特定提交郵件格式。</span><span class="sxs-lookup"><span data-stu-id="706de-156">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="706de-157">提交的主旨（信封標題）應採用此格式：</span><span class="sxs-lookup"><span data-stu-id="706de-157">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`{(int)safetyApiAction}|{networkId}|{senderIp}|{fromAddress}|({subject.Substring(0, Math.Min(subjectLen, subject.Length))})`

<span data-ttu-id="706de-158">SafetyApiAction 為：</span><span class="sxs-lookup"><span data-stu-id="706de-158">were SafetyApiAction is:</span></span>

- <span data-ttu-id="706de-159">垃圾郵件 = 1</span><span class="sxs-lookup"><span data-stu-id="706de-159">Junk = 1</span></span>
- <span data-ttu-id="706de-160">NotJunk = 2</span><span class="sxs-lookup"><span data-stu-id="706de-160">NotJunk = 2</span></span>
- <span data-ttu-id="706de-161">網路釣魚 = 3</span><span class="sxs-lookup"><span data-stu-id="706de-161">Phish = 3</span></span>

<span data-ttu-id="706de-162">在下列範例中：</span><span class="sxs-lookup"><span data-stu-id="706de-162">In the following example:</span></span>

- <span data-ttu-id="706de-163">將郵件報告為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="706de-163">The message is being reported as Phish.</span></span>
- <span data-ttu-id="706de-164">網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="706de-164">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="706de-165">寄件者 IP 為167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="706de-165">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="706de-166">[寄件者] 位址為 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="706de-166">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="706de-167">郵件的電子郵件主體是「測試網路釣魚提交」</span><span class="sxs-lookup"><span data-stu-id="706de-167">The message's email subject is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="706de-168">不遵循此格式的郵件將無法在提交入口網站中正確顯示。</span><span class="sxs-lookup"><span data-stu-id="706de-168">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
