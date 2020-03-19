---
title: 將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '您和您的使用者可以將假的否定和誤報垃圾郵件提交給 Microsoft 進行分析。 '
ms.openlocfilehash: 7b53f74be78bc1203189815c6a7adf3337decd21
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856866"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a><span data-ttu-id="218f6-103">將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="218f6-103">Submit spam, non-spam, and phishing scam messages to Microsoft for analysis</span></span>

<span data-ttu-id="218f6-104">當您組織中的使用者收到其收件匣中的垃圾郵件（垃圾郵件）或網路釣魚詐騙郵件時，或是因為郵件標示為垃圾郵件而未收到合法的電子郵件時，可能會令人感到麻煩。</span><span class="sxs-lookup"><span data-stu-id="218f6-104">It can be frustrating when users in your organization receive junk messages (spam) or phishing scam messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="218f6-105">我們不斷微調垃圾郵件篩選器，使其更準確。</span><span class="sxs-lookup"><span data-stu-id="218f6-105">We're constantly fine-tuning our spam filters to be more accurate.</span></span> <span data-ttu-id="218f6-106">您和您的使用者可以將虛假的反垃圾郵件訊息提交給 Microsoft 進行分析，以協助此程式。</span><span class="sxs-lookup"><span data-stu-id="218f6-106">You and your users can help this process by submitting false negative and false positive spam messages to Microsoft for analysis.</span></span> <span data-ttu-id="218f6-107">"False 負值" 是垃圾郵件，應為垃圾郵件，但不會被識別為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-107">A "false negative" is a spam message that should have been but was not identified as spam.</span></span> <span data-ttu-id="218f6-108">"誤報" 是一種合法的電子郵件訊息，錯誤地辨識為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-108">A "false positive" is a legitimate email message that was incorrectly identified as spam.</span></span>

> [!NOTE]
> <span data-ttu-id="218f6-109">由於我們收到大量送出的報送，我們可能無法回答所有要求進行分析。</span><span class="sxs-lookup"><span data-stu-id="218f6-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

<span data-ttu-id="218f6-110">系統管理員可以將電子郵件、url 和附件傳送給 Microsoft 以供審閱。</span><span class="sxs-lookup"><span data-stu-id="218f6-110">Admins can send email, url, and attachments to Microsoft for review.</span></span> <span data-ttu-id="218f6-111">請參閱[Office 365 ATP 中的系統管理員報送](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="218f6-111">See [Admin submissions in Office 365 ATP](admin-submission.md).</span></span>

## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a><span data-ttu-id="218f6-112">提交透過垃圾郵件篩選器傳遞的垃圾郵件或網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="218f6-112">Submit junk or phishing messages that passed through the spam filters</span></span>

<span data-ttu-id="218f6-113">如果您收到的郵件是透過垃圾郵件篩選器傳遞，而且應歸類為垃圾郵件篩選器或網路釣魚詐騙，您可以視需要將 "假否定" 郵件提交至 Microsoft 垃圾郵件分析和 Microsoft 網路釣魚分析小組。</span><span class="sxs-lookup"><span data-stu-id="218f6-113">If you receive a message that passed through the spam filters that and should be classified as junk or a phishing scam, you can submit the "false negative" message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams, as appropriate.</span></span> <span data-ttu-id="218f6-114">分析員會檢查郵件，並將其新增至全服務篩選準則（如果符合分類準則）。</span><span class="sxs-lookup"><span data-stu-id="218f6-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

<span data-ttu-id="218f6-115">如需適用于整個組織的垃圾郵件設定，請參閱[使用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件，以避免誤報負面問題](reduce-spam-email.md)。</span><span class="sxs-lookup"><span data-stu-id="218f6-115">For more spam settings that apply to the whole organization, see [Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md).</span></span> <span data-ttu-id="218f6-116">本文包含協助避免誤報的秘訣。</span><span class="sxs-lookup"><span data-stu-id="218f6-116">This article contains tips to help prevent false negatives.</span></span>

<span data-ttu-id="218f6-117">您可以透過下列方式提交垃圾郵件：</span><span class="sxs-lookup"><span data-stu-id="218f6-117">You can submit junk email messages in the following ways:</span></span>

- <span data-ttu-id="218f6-118">針對網頁使用者的 Outlook 和 Outlook，請使用 Microsoft Outlook 的報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="218f6-118">For Outlook and Outlook on the web users, use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="218f6-119">如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="218f6-119">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="218f6-120">您也可以使用電子郵件將郵件提交至 Microsoft，以歸類為垃圾郵件或網路釣魚詐騙，如下列程式所述。</span><span class="sxs-lookup"><span data-stu-id="218f6-120">You can also use email to submit messages to Microsoft that should be classified as junk or phishing scams, as described in the following procedure.</span></span>

### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a><span data-ttu-id="218f6-121">使用電子郵件將垃圾郵件（垃圾郵件）或網路釣魚詐騙郵件提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="218f6-121">Use email to submit junk (spam) or phishing scam messages to Microsoft</span></span>

<span data-ttu-id="218f6-122">若要將垃圾郵件或網路釣魚詐騙郵件提交給 Microsoft：</span><span class="sxs-lookup"><span data-stu-id="218f6-122">To submit a junk or phishing scam message to Microsoft:</span></span>

1. <span data-ttu-id="218f6-123">建立空白的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="218f6-123">Create a blank email message.</span></span>

2. <span data-ttu-id="218f6-124">將郵寄地址視為審閱郵件的 Microsoft 小組，如下所示：</span><span class="sxs-lookup"><span data-stu-id="218f6-124">Address the message to the Microsoft team that reviews messages, as follows:</span></span>

   - <span data-ttu-id="218f6-125">若為垃圾郵件： junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="218f6-125">For junk messages: junk@office365.microsoft.com</span></span>

   - <span data-ttu-id="218f6-126">對於網路釣魚詐騙郵件： phish@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="218f6-126">For phishing scam messages: phish@office365.microsoft.com</span></span>

3. <span data-ttu-id="218f6-127">將垃圾郵件或網路釣魚詐騙郵件複製並貼到新郵件中以附件形式傳送。</span><span class="sxs-lookup"><span data-stu-id="218f6-127">Copy and paste the junk or phishing scam message into the new message as an attachment.</span></span>

   > [!NOTE]
   > <span data-ttu-id="218f6-128">•您可以在新郵件中附加多封郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-128">• You can attach multiple messages in the new message.</span></span> <span data-ttu-id="218f6-129">請確定所有郵件都是相同類型：網路釣魚詐騙郵件或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-129">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span> <br/><br/><span data-ttu-id="218f6-130">•將新郵件的本文保留空白。</span><span class="sxs-lookup"><span data-stu-id="218f6-130">• Leave the body of the new message empty.</span></span> <br/><br/><span data-ttu-id="218f6-131">•使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-131">• Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

4. <span data-ttu-id="218f6-132">按一下 **[傳送]**。</span><span class="sxs-lookup"><span data-stu-id="218f6-132">Click **Send**.</span></span>

## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a><span data-ttu-id="218f6-133">提交已標記為垃圾郵件的郵件，但應該允許透過</span><span class="sxs-lookup"><span data-stu-id="218f6-133">Submit messages that were tagged as junk but should have been allowed through</span></span>

<span data-ttu-id="218f6-134">如果郵件被錯誤地識別為垃圾郵件，您可以將 "誤報" 郵件提交給 Microsoft 垃圾郵件分析小組。</span><span class="sxs-lookup"><span data-stu-id="218f6-134">If a message was incorrectly identified as junk, you can submit the "false positive" message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="218f6-135">分析員會評估和分析郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-135">The analysts will evaluate and analyze the message.</span></span> <span data-ttu-id="218f6-136">我們可以根據分析的結果調整全服務的垃圾郵件內容篩選規則，以便允許郵件通行。</span><span class="sxs-lookup"><span data-stu-id="218f6-136">Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
  
<span data-ttu-id="218f6-137">管理員可以查看更多垃圾郵件設定資訊，以套用至整個組織。</span><span class="sxs-lookup"><span data-stu-id="218f6-137">Administrators can review more spam setting information that applies to a whole organization.</span></span> <span data-ttu-id="218f6-138">請參閱操作[方法：協助確保郵件不會標示為垃圾](prevent-email-from-being-marked-as-spam.md)郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-138">See [How to help ensure that a message isn't marked as spam](prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="218f6-139">如果您有系統管理員層級的控制，而您想要避免誤報，則此資訊非常有用。</span><span class="sxs-lookup"><span data-stu-id="218f6-139">This information is helpful if you have administrator-level control and you want to prevent false positives.</span></span>
  
<span data-ttu-id="218f6-140">您可以透過下列方式提交非垃圾郵件：</span><span class="sxs-lookup"><span data-stu-id="218f6-140">You can submit non-spam messages in the following ways:</span></span>

- <span data-ttu-id="218f6-141">如果您在設定內容篩選器時使用 [**將郵件移至垃圾郵件資料夾**] 動作（這是預設動作），使用者可以在其 Outlook 或 outlook 網頁版（先前稱為 Outlook web App）的 [垃圾郵件] 資料夾中，放開誤報郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-141">If you use the **Move message to Junk Email folder** action when you configure your content filters (this is the default action), users can release false positive messages in their Outlook or Outlook on the web (formerly known as Outlook Web App) Junk Email folder.</span></span>

  - <span data-ttu-id="218f6-142">Outlook 使用者可以使用 [**非垃圾**郵件] 按滑鼠右鍵按一下功能表選項，來釋放 false 的肯定郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-142">Outlook users can release false positive messages by using the **Not Junk** right-click menu option.</span></span> <span data-ttu-id="218f6-143">不過，他們必須透過電子郵件將郵件提交給 Microsoft，如本文中的程式所示。</span><span class="sxs-lookup"><span data-stu-id="218f6-143">However, they must submit the message to Microsoft through email, as shown in the procedure in this article.</span></span>

  - <span data-ttu-id="218f6-144">Web 使用者上的 Outlook 可發放誤報郵件，並將其提交給 Microsoft 進行分析，以使用「**標記為非垃圾**郵件」動作。</span><span class="sxs-lookup"><span data-stu-id="218f6-144">Outlook on the web users can release false positive messages and submit them to Microsoft for analysis using the **Mark as not junk** action.</span></span> <span data-ttu-id="218f6-145">如需如何執行此動作的詳細資訊，請參閱[在 Outlook 網頁版中報告垃圾郵件和網路釣魚詐騙](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="218f6-145">For more information about how to do this, see [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span>

- <span data-ttu-id="218f6-146">當您設定內容篩選器時，如果您使用 [**隔離郵件**] 動作，而非 [**將郵件移至垃圾郵件資料夾**] 動作，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="218f6-146">If you use the **Quarantine message** action instead of the **Move message to Junk Email folder** action when you configure your content filters:</span></span>

  - <span data-ttu-id="218f6-147">系統管理員可以釋放被當成垃圾郵件隔離的郵件，並從 Exchange 系統管理中心將這些郵件回報為誤判。</span><span class="sxs-lookup"><span data-stu-id="218f6-147">Administrators can release spam-quarantined messages and report them as false positives from the Exchange admin center.</span></span> <span data-ttu-id="218f6-148">如需詳細資訊，請參閱[在 Office 365 中以系統管理員身分管理隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="218f6-148">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

  - <span data-ttu-id="218f6-149">使用者可以放開自己的垃圾隔離郵件，並透過下列頻道將其報告為誤報：</span><span class="sxs-lookup"><span data-stu-id="218f6-149">Users can release their own spam-quarantined messages and report them as false positives through the following channels:</span></span>

  - <span data-ttu-id="218f6-150">Exchange 系統管理中心 (EAC) 使用者介面。</span><span class="sxs-lookup"><span data-stu-id="218f6-150">The Exchange admin center (EAC) user interface.</span></span> <span data-ttu-id="218f6-151">如需詳細資訊，請參閱 [Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="218f6-151">For more information, see [Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="218f6-152">使用者垃圾郵件通知訊息 (如果您的系統管理員已加以啟用)。</span><span class="sxs-lookup"><span data-stu-id="218f6-152">End-user spam notification messages (if they're enabled by your administrator).</span></span>

- <span data-ttu-id="218f6-153">您也可以使用電子郵件將不應歸類為垃圾郵件的郵件提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="218f6-153">You can also use email to submit messages to Microsoft that should not be classified as spam.</span></span> <span data-ttu-id="218f6-154">當您執行此動作時，請確定您使用下列程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="218f6-154">When you do this, make sure that you use the steps in the following procedure.</span></span>

### <a name="use-email-to-submit-false-positive-messages"></a><span data-ttu-id="218f6-155">使用電子郵件來提交誤判的郵件</span><span class="sxs-lookup"><span data-stu-id="218f6-155">Use email to submit false positive messages</span></span>

<span data-ttu-id="218f6-156">使用 [[使用電子郵件將垃圾郵件提交給 Microsoft] 或 [網路釣魚詐騙郵件](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft)] 區段中所述的相同程式，但會將郵件傳送至 not_junk@office365.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="218f6-156">Use the same procedure as described in the [Use email to submit junk (spam) or phishing scam messages to Microsoft](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft) section, but send the message to not_junk@office365.microsoft.com.</span></span>

## <a name="spam-evaluation-and-rules-deployment"></a><span data-ttu-id="218f6-157">垃圾郵件評估和規則部署</span><span class="sxs-lookup"><span data-stu-id="218f6-157">Spam evaluation and rules deployment</span></span>

<span data-ttu-id="218f6-158">垃圾郵件分析小組會檢查您提交的郵件，並調整垃圾郵件篩選器以避免今後的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-158">The spam analysis team examines messages that you submit, and adjusts the spam filters to prevent future junk mail.</span></span> <span data-ttu-id="218f6-159">因此，Office 365 垃圾郵件篩選器會 areconstantly 精緻。</span><span class="sxs-lookup"><span data-stu-id="218f6-159">As a result, Office 365 spam filters areconstantly refined.</span></span> <span data-ttu-id="218f6-160">任何提交的項目都是在整個網路層級接受評估。</span><span class="sxs-lookup"><span data-stu-id="218f6-160">Any submitted items are evaluated at the network-wide level.</span></span> <span data-ttu-id="218f6-161">誤報會檢查並評估提交可能的規則，以允許今後透過垃圾郵件篩選器的郵件。</span><span class="sxs-lookup"><span data-stu-id="218f6-161">False positive submissions are examined and assessed for possible rule adjustment to allow future messages through the spam filters.</span></span> <span data-ttu-id="218f6-162">因此，通知服務的誤報和否定的否定（未篩選的垃圾郵件），對您和使用全域網路的所有客戶都很有利。</span><span class="sxs-lookup"><span data-stu-id="218f6-162">Therefore, notifying the service of false positives and also false negatives (unfiltered spam) is advantageous for you and all customers who use the global network.</span></span> <span data-ttu-id="218f6-163">垃圾郵件小組會在每封提交的郵件中檢查各項指標，例如：</span><span class="sxs-lookup"><span data-stu-id="218f6-163">The spam team examines indicators within each submitted message, such as the following:</span></span>

- <span data-ttu-id="218f6-164">寄件者地址</span><span class="sxs-lookup"><span data-stu-id="218f6-164">From address</span></span>

- <span data-ttu-id="218f6-165">傳送方 IP 位址</span><span class="sxs-lookup"><span data-stu-id="218f6-165">Sending IP address</span></span>

- <span data-ttu-id="218f6-166">關鍵字</span><span class="sxs-lookup"><span data-stu-id="218f6-166">Keywords</span></span>

- <span data-ttu-id="218f6-167">詞組</span><span class="sxs-lookup"><span data-stu-id="218f6-167">Phrases</span></span>

- <span data-ttu-id="218f6-168">傳輸頻率</span><span class="sxs-lookup"><span data-stu-id="218f6-168">Frequency of transmission</span></span>

- <span data-ttu-id="218f6-169">其他趨勢和模式</span><span class="sxs-lookup"><span data-stu-id="218f6-169">Other trends and patterns</span></span>

<span data-ttu-id="218f6-170">審閱此資訊之後，垃圾郵件小組可能會變更服務的垃圾郵件篩選層。</span><span class="sxs-lookup"><span data-stu-id="218f6-170">After they review this information, the spam team might make changes to the service's spam filtering layers.</span></span> <span data-ttu-id="218f6-171">如需垃圾郵件小組的詳細資訊，您可以收看下列英文版影片：</span><span class="sxs-lookup"><span data-stu-id="218f6-171">For more information about the spam team, you can watch the following English-only video:</span></span>

[<span data-ttu-id="218f6-172">Microsoft Exchange 垃圾郵件小組影片</span><span class="sxs-lookup"><span data-stu-id="218f6-172">Microsoft Exchange Spam team video</span></span>](https://youtu.be/-TpX_-GMC7o?hd=1)

<span data-ttu-id="218f6-173">垃圾郵件評估是一種持續執行的程式，不論原始語言或字元集為何都會套用。</span><span class="sxs-lookup"><span data-stu-id="218f6-173">Spam evaluation is an ongoing process that applies regardless of the originating language or character set.</span></span> <span data-ttu-id="218f6-174">因為垃圾郵件可能會含糊含糊或甚至缺乏主旨或郵件內文中的文字，所以垃圾郵件小組會依靠其他郵件特性來執行篩選。</span><span class="sxs-lookup"><span data-stu-id="218f6-174">Because a spam message can be vague or even lack text in the subject or message body, the spam team relies on other message characteristics to perform filtering.</span></span> <span data-ttu-id="218f6-175">這表示，當垃圾郵件小組將提供的郵件標示為垃圾郵件，並且對規則基礎進行必要變更之後，該郵件將來便會遭到封鎖，除非其特性又被修改到足可避開我們的篩選器。</span><span class="sxs-lookup"><span data-stu-id="218f6-175">This means that after the spam team flags a given message as spam and makes the necessary changes to its rule base, that message will be blocked in the future until its characteristics have been modified enough to avoid our filters.</span></span> <span data-ttu-id="218f6-176">我們會不斷地部署新的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="218f6-176">New spam rules are deployed continuously.</span></span> <span data-ttu-id="218f6-177">個別報送之規則的時間範圍視報送的數量和品質而有所不同。</span><span class="sxs-lookup"><span data-stu-id="218f6-177">Time frames for rules on individual submissions vary depending on the quantity and quality of submissions.</span></span> <span data-ttu-id="218f6-178">因為新的垃圾郵件規則是針對所有客戶進行全域設定，所以並非個別的垃圾郵件提交會產生新的垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="218f6-178">Because new spam rules are set globally for all customers, not all individual spam submissions will result in a new spam rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="218f6-179">相關資訊</span><span class="sxs-lookup"><span data-stu-id="218f6-179">For more information</span></span>

[<span data-ttu-id="218f6-180">反垃圾郵件和反惡意程式碼防護</span><span class="sxs-lookup"><span data-stu-id="218f6-180">Anti-spam and anti-malware protection</span></span>](anti-spam-and-anti-malware-protection.md)
  
[<span data-ttu-id="218f6-181">如何協助確保郵件不會標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="218f6-181">How to help ensure that a message isn't marked as spam</span></span>](prevent-email-from-being-marked-as-spam.md)
  
[<span data-ttu-id="218f6-182">利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件以避免誤判正常</span><span class="sxs-lookup"><span data-stu-id="218f6-182">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
  

[<span data-ttu-id="218f6-183">利用 Office 365 垃圾郵件篩選器封鎖電子郵件垃圾郵件，以避免誤判問題</span><span class="sxs-lookup"><span data-stu-id="218f6-183">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
