---
title: 手動將郵件提交給 Microsoft 進行分析
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 系統管理員和使用者可以深入瞭解如何將電子郵件（適當的郵件標示為壞或壞的郵件允許），以供 Microsoft 進行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6973330c4504bd6478265205f60798b3b7c1875
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811035"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="f609f-103">手動將郵件提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="f609f-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="f609f-104">如果您是 Exchange Online 信箱組織中的系統管理員，建議您在安全性 & 規範中心內使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="f609f-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f609f-105">如需詳細資訊，請參閱[使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f609f-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f609f-106">當您組織中的使用者在其收件匣中收到垃圾郵件（垃圾郵件）或網路釣魚郵件時，或是因為郵件標示為垃圾郵件而未收到合法電子郵件時，可能會令人感到沮喪。</span><span class="sxs-lookup"><span data-stu-id="f609f-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="f609f-107">我們不斷微調垃圾郵件篩選器，使其更準確。</span><span class="sxs-lookup"><span data-stu-id="f609f-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="f609f-108">您和您的使用者可以提交誤報（不良電子郵件標記為壞）、誤報（允許錯誤郵件）和網路以進行分析，以協助此程式。</span><span class="sxs-lookup"><span data-stu-id="f609f-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="f609f-109">由於我們收到大量送出的報送，我們可能無法回答所有要求進行分析。</span><span class="sxs-lookup"><span data-stu-id="f609f-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="f609f-110">將漏報提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f609f-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f609f-111">在 Outlook 和網頁型 Outlook （先前稱為 Outlook Web App）中的使用者可以使用 Microsoft Outlook 的報告訊息增益集，而不是使用下列程式來報告漏報。</span><span class="sxs-lookup"><span data-stu-id="f609f-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="f609f-112">如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="f609f-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f609f-113">如果您收到的郵件透過應識別為垃圾郵件篩選的垃圾郵件篩選，您可以視需要將郵件提交至 Microsoft 垃圾郵件分析和 Microsoft 網路釣魚分析小組。</span><span class="sxs-lookup"><span data-stu-id="f609f-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="f609f-114">分析員會檢查郵件，並將其新增至全服務篩選準則（如果符合分類準則）。</span><span class="sxs-lookup"><span data-stu-id="f609f-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="f609f-115">使用下列其中一個收件者建立新的空白電子郵件訊息：</span><span class="sxs-lookup"><span data-stu-id="f609f-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="f609f-116">**垃圾郵件**：`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f609f-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="f609f-117">**網路釣魚**：`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f609f-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="f609f-118">將垃圾郵件或網路釣魚郵件拖放到新郵件中。</span><span class="sxs-lookup"><span data-stu-id="f609f-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="f609f-119">這會將垃圾郵件或網路釣魚郵件儲存為新郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="f609f-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="f609f-120">請勿複製及貼上郵件內容或轉寄郵件（我們需要原始郵件，才能檢查郵件頭）。</span><span class="sxs-lookup"><span data-stu-id="f609f-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="f609f-121">您可以在新郵件中附加多封郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f609f-122">請確定所有郵件都是相同類型：網路釣魚詐騙郵件或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="f609f-123">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="f609f-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="f609f-124">使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="f609f-125">當您完成時，按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="f609f-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f609f-126">系統管理員可以使用數種不同的方式封鎖正 misidentified 為垃圾郵件的特定郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="f609f-127">如需詳細資訊，請參閱[在 EOP 中建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f609f-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="f609f-128">將誤報提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f609f-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f609f-129">您不用使用下列程式來報告誤報，Outlook 和網頁型 Outlook 中的使用者可以使用 Microsoft Outlook 的報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="f609f-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="f609f-130">如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="f609f-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f609f-131">如果郵件被錯誤地辨識為垃圾郵件，您可以將郵件提交給 Microsoft 垃圾郵件分析小組。</span><span class="sxs-lookup"><span data-stu-id="f609f-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f609f-132">分析員會評估郵件，並根據分析的結果，可以調整整個服務篩選器以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="f609f-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="f609f-133">以收件者的身分建立新的空白電子郵件訊息 `not_junk@office365.microsoft.com` ：</span><span class="sxs-lookup"><span data-stu-id="f609f-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="f609f-134">將 misidentified 郵件拖曳並放入新的郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="f609f-135">這會將 misidentified 郵件儲存為新郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="f609f-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="f609f-136">請勿複製及貼上郵件內容或轉寄郵件（我們需要原始郵件，才能檢查郵件頭）。</span><span class="sxs-lookup"><span data-stu-id="f609f-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="f609f-137">您可以在新郵件中附加多封郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f609f-138">請確定所有郵件都是相同類型：網路釣魚郵件或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="f609f-139">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="f609f-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="f609f-140">使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。</span><span class="sxs-lookup"><span data-stu-id="f609f-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="f609f-141">當您完成時，按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="f609f-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f609f-142">系統管理員有幾種不同的方式可讓特定郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="f609f-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="f609f-143">如需詳細資訊，請參閱[在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f609f-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="f609f-144">建立郵件流程規則，以接收報告給 Microsoft 的郵件副本</span><span class="sxs-lookup"><span data-stu-id="f609f-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="f609f-145">如需相關指示，請參閱[使用郵件流程規則來查看您的使用者向 Microsoft 報告的內容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="f609f-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
