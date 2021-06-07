---
title: 在 Outlook 中報告誤判和漏報
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 瞭解如何使用報告郵件功能，在 Outlook 中報告誤報和漏報。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84a5b697f8a4b46cf79c542485bfafb396328f5c
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789240"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="eba83-103">在 Outlook 中報告誤判和漏報</span><span class="sxs-lookup"><span data-stu-id="eba83-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eba83-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="eba83-104">**Applies to**</span></span>
- [<span data-ttu-id="eba83-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eba83-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eba83-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="eba83-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eba83-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eba83-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="eba83-108">如果您是具有 Exchange Online 信箱的 Microsoft 365 組織中的系統管理員，建議您在安全性 & 合規性中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="eba83-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="eba83-109">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="eba83-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="eba83-110">在使用混合式新式驗證的 Exchange Online 或內部部署信箱中使用信箱的 Microsoft 365 組織中，您可以提交 (誤報) 的電子郵件，或傳送至 [垃圾郵件] 資料夾的錯誤電子郵件， (已傳遞至 [收件匣]) 的有害電子郵件或網路釣魚 Exchange Online Protection () EOP。</span><span class="sxs-lookup"><span data-stu-id="eba83-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eba83-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="eba83-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eba83-112">為了獲得最佳的使用者提交經驗，請使用報告訊息增益集或報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="eba83-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="eba83-113">在 Outlook 中報告垃圾郵件或網路釣魚的內建經驗，無法使用[使用者提交原則](./user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="eba83-113">The built-in experience for reporting junk or phishing in Outlook can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="eba83-114">建議您改為使用報表訊息增益集或報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="eba83-114">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

- <span data-ttu-id="eba83-115">所有平臺上的 Outlook 報告訊息增益集及報告網路釣魚增益集 (Outlook 網頁、iOS、Android 和桌面) 。</span><span class="sxs-lookup"><span data-stu-id="eba83-115">The the Report Message add-in and the Report Phishing add-in work for Outlook in all platforms (Outlook on the web, iOS, Android, and Desktop).</span></span>

- <span data-ttu-id="eba83-116">如果您是組織中 Exchange Online 信箱的系統管理員，請使用安全性 & 規範中心中的提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="eba83-116">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="eba83-117">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="eba83-117">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="eba83-118">您可以設定為將郵件直接傳送到 Microsoft、您指定的信箱，或兩者皆傳送。</span><span class="sxs-lookup"><span data-stu-id="eba83-118">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="eba83-119">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="eba83-119">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="eba83-120">如需如何取得及啟用報告訊息或報告網路釣魚增益集的詳細資訊，請參閱 [enable The Report message or The Report 仿冒增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="eba83-120">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="eba83-121">如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="eba83-121">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="eba83-122">使用報告郵件功能</span><span class="sxs-lookup"><span data-stu-id="eba83-122">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="eba83-123">報告垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="eba83-123">Report junk and phishing messages</span></span>

<span data-ttu-id="eba83-124">對於收件匣或任何其他電子郵件資料夾（除了垃圾郵件）以外的郵件，請使用下列方法來報告垃圾郵件和網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="eba83-124">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="eba83-125">選取所選郵件右上角的 [ **其他動作** ] 省略號，從下拉式功能表選取 [ **報告訊息** ]，然後選取 [ **垃圾** 郵件] 或 [ **網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="eba83-125">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   ![報告郵件-更多動作](../../media/report-message-more-actions.png)
   
   ![報告郵件-垃圾郵件和網路釣魚](../../media/report-message-junk-phishing.png)

2. <span data-ttu-id="eba83-128">選取的郵件會傳送至 Microsoft 進行分析，並：</span><span class="sxs-lookup"><span data-stu-id="eba83-128">The selected messages will be sent to Microsoft for analysis and:</span></span>
   - <span data-ttu-id="eba83-129">移至 [垃圾郵件] 資料夾（如果他們已舉報為垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="eba83-129">Moved to the Junk Email folder if they were reported as spam.</span></span>
   - <span data-ttu-id="eba83-130">會在報告為網路釣魚時刪除。</span><span class="sxs-lookup"><span data-stu-id="eba83-130">Deleted if they were reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="eba83-131">報告非垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="eba83-131">Report messages that are not junk</span></span>

1. <span data-ttu-id="eba83-132">選取所選郵件右上角的 [ **其他動作** ] 省略號，選取下拉式功能表中的 [ **報告訊息** ]，然後選取 [不是 **垃圾** 郵件]。</span><span class="sxs-lookup"><span data-stu-id="eba83-132">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Not Junk**.</span></span>

   ![報告郵件-更多動作](../../media/report-message-more-actions.png)
   
   ![報告訊息-不是垃圾郵件](../../media/report-message-not-junk.png)

2. <span data-ttu-id="eba83-135">選取的郵件會傳送至 Microsoft 進行分析，然後移至 [收件匣] 或任何其他指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="eba83-135">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="eba83-136">查看和審閱報告的郵件</span><span class="sxs-lookup"><span data-stu-id="eba83-136">View and review reported messages</span></span>

<span data-ttu-id="eba83-137">若要查看使用者向 Microsoft 報告的郵件，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="eba83-137">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="eba83-138">使用系統管理提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="eba83-138">Use the Admin Submissions portal.</span></span> <span data-ttu-id="eba83-139">如需詳細資訊，請參閱 [View user 報送 To Microsoft](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="eba83-139">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>
- <span data-ttu-id="eba83-140">建立郵件流程規則 (也稱為傳輸規則) 傳送報告郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="eba83-140">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="eba83-141">如需相關指示，請參閱 [使用郵件流程規則來查看向 Microsoft 報告的使用者](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="eba83-141">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
