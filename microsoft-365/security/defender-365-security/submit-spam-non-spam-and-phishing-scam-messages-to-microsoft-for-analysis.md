---
title: 手動將郵件提交給 Microsoft 進行分析
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 系統管理員和使用者可以瞭解如何使用電子郵件傳送郵件， (郵件會標示為壞或錯誤的郵件，以供 Microsoft 進行分析) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0a6f564d82750c5ab8156680854c2453cda6971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058488"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="5f096-103">手動將郵件提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="5f096-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f096-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5f096-104">**Applies to**</span></span>
- [<span data-ttu-id="5f096-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5f096-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5f096-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="5f096-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5f096-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f096-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="5f096-108">如果您是 Exchange Online 信箱組織中的系統管理員，建議您在安全性 & 規範中心內使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="5f096-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5f096-109">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="5f096-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="5f096-110">當您組織中的使用者收到垃圾郵件 (其收件匣中的垃圾郵件) 或網路釣魚郵件，或是因為郵件標記為垃圾郵件而未收到合法的電子郵件時，可能會令人感到沮喪。</span><span class="sxs-lookup"><span data-stu-id="5f096-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="5f096-111">我們不斷微調垃圾郵件篩選器，使其更準確。</span><span class="sxs-lookup"><span data-stu-id="5f096-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="5f096-112">您和您的使用者可以提交誤報 (良好的電子郵件標示為壞) ，誤報 (錯誤郵件) ，並將網路釣魚郵件傳送至 Microsoft 進行分析，以協助此處理程式。</span><span class="sxs-lookup"><span data-stu-id="5f096-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="5f096-113">由於我們收到大量送出的報送，我們可能無法回答所有要求進行分析。</span><span class="sxs-lookup"><span data-stu-id="5f096-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="5f096-114">將漏報提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f096-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="5f096-115">「Outlook」和「outlook (網頁版」（先前稱為 Outlook Web App) ）中的使用者可以使用報表訊息增益集或報表網路釣魚增益集，而不是使用下列程式來報告漏報。</span><span class="sxs-lookup"><span data-stu-id="5f096-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="5f096-116">如需如何安裝及使用這些工具的相關資訊，請參閱 [enable The Report Message 增益集](enable-the-report-message-add-in.md) 及 [啟用報告網路釣魚增益集](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="5f096-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="5f096-117">如果您收到的郵件透過應識別為垃圾郵件篩選的垃圾郵件篩選，您可以視需要將郵件提交至 Microsoft 垃圾郵件分析和 Microsoft 網路釣魚分析小組。</span><span class="sxs-lookup"><span data-stu-id="5f096-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="5f096-118">分析員會檢查郵件，並將其新增至全服務篩選準則（如果符合分類準則）。</span><span class="sxs-lookup"><span data-stu-id="5f096-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="5f096-119">使用下列其中一個收件者建立新的空白電子郵件訊息：</span><span class="sxs-lookup"><span data-stu-id="5f096-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="5f096-120">**垃圾郵件**： `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="5f096-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="5f096-121">**網路釣魚**： `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="5f096-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="5f096-122">將垃圾郵件或網路釣魚郵件拖放到新郵件中。</span><span class="sxs-lookup"><span data-stu-id="5f096-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="5f096-123">這會將垃圾郵件或網路釣魚郵件儲存為新郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="5f096-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="5f096-124">請勿複製及貼上郵件的內容，或轉寄郵件 (我們需要原始郵件，才能檢查郵件頭) 。</span><span class="sxs-lookup"><span data-stu-id="5f096-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="5f096-125">您可以在新郵件中附加多封郵件。</span><span class="sxs-lookup"><span data-stu-id="5f096-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="5f096-126">請確定所有郵件都是相同類型：網路釣魚郵件或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="5f096-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="5f096-127">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="5f096-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="5f096-128">使用 .msg (預設 Outlook 格式) 或 .eml (郵件格式的預設 Outlook 格式) 附加郵件的格式。</span><span class="sxs-lookup"><span data-stu-id="5f096-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="5f096-129">當您完成時，按一下 [ **傳送**]。</span><span class="sxs-lookup"><span data-stu-id="5f096-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="5f096-130">系統管理員可以使用數種不同的方式封鎖正 misidentified 為垃圾郵件的特定郵件。</span><span class="sxs-lookup"><span data-stu-id="5f096-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="5f096-131">如需詳細資訊，請參閱 [在 EOP 中建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5f096-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="5f096-132">將誤報提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f096-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="5f096-133">除了使用下列程式來報告誤報之外，Outlook 和 Outlook (網頁版 outlook 中的使用者（以前稱為 Outlook Web App) ）都可以使用報表訊息增益集或報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="5f096-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="5f096-134">如需如何安裝及使用這些工具的相關資訊，請參閱 [enable The Report Message 增益集](enable-the-report-message-add-in.md) 及 [啟用報告網路釣魚增益集](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="5f096-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="5f096-135">如果郵件被錯誤地辨識為垃圾郵件，您可以將郵件提交給 Microsoft 垃圾郵件分析小組。</span><span class="sxs-lookup"><span data-stu-id="5f096-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="5f096-136">分析員會評估郵件，並根據分析的結果 () 可調整整個服務篩選器以允許郵件通過。</span><span class="sxs-lookup"><span data-stu-id="5f096-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="5f096-137">以收件者的身分建立新的空白電子郵件訊息 `not_junk@office365.microsoft.com` ：</span><span class="sxs-lookup"><span data-stu-id="5f096-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="5f096-138">將 misidentified 郵件拖曳並放入新的郵件。</span><span class="sxs-lookup"><span data-stu-id="5f096-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="5f096-139">這會將 misidentified 郵件儲存為新郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="5f096-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="5f096-140">請勿複製及貼上郵件的內容，或轉寄郵件 (我們需要原始郵件，才能檢查郵件頭) 。</span><span class="sxs-lookup"><span data-stu-id="5f096-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="5f096-141">您可以在新郵件中附加多封郵件。</span><span class="sxs-lookup"><span data-stu-id="5f096-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="5f096-142">請確定所有郵件都是相同類型：網路釣魚郵件或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="5f096-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="5f096-143">將新郵件的內文保留空白。</span><span class="sxs-lookup"><span data-stu-id="5f096-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="5f096-144">使用 .msg (預設 Outlook 格式) 或 .eml (郵件格式的預設 Outlook 格式) 附加郵件的格式。</span><span class="sxs-lookup"><span data-stu-id="5f096-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="5f096-145">當您完成時，按一下 [ **傳送**]。</span><span class="sxs-lookup"><span data-stu-id="5f096-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="5f096-146">系統管理員有幾種不同的方式可讓特定郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="5f096-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="5f096-147">如需詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5f096-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="5f096-148">送出至 Microsoft 儲存的資料位於何處？</span><span class="sxs-lookup"><span data-stu-id="5f096-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="5f096-149">資料位於北美資料中心的 Office 365 規範界限內。</span><span class="sxs-lookup"><span data-stu-id="5f096-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="5f096-150">工程小組的分析人員會檢查資料，以協助改善篩選的效能。</span><span class="sxs-lookup"><span data-stu-id="5f096-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="5f096-151">建立郵件流程規則，以接收報告給 Microsoft 的郵件副本</span><span class="sxs-lookup"><span data-stu-id="5f096-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="5f096-152">如需相關指示，請參閱 [使用郵件流程規則來查看您的使用者向 Microsoft 報告的內容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="5f096-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
