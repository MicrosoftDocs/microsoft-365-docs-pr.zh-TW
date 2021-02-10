---
title: 在 Outlook 中報告 iOS 和 Android 的垃圾郵件和網路釣魚電子郵件
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解 Outlook 中內建的垃圾郵件、非垃圾郵件和網路釣魚電子郵件報告選項，以供 iOS 和 Android。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166816"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="b19eb-103">在適用于 Exchange Online 的 iOS 和 Android 的 Outlook 中報告垃圾郵件和網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="b19eb-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b19eb-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="b19eb-104">**Applies to**</span></span>
- [<span data-ttu-id="b19eb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b19eb-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="b19eb-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="b19eb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b19eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b19eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b19eb-108">在使用 [混合式新式驗證](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)的 Exchange Online 或內部部署信箱中有信箱的 Microsoft 365 組織中，您可以使用內建的報告選項，在 Outlook 中 IOS 和 Android 提交誤報 (正常電子郵件標示為垃圾郵件) 、false 負片 (不良電子郵件允許) ，以及網路釣魚郵件至 Exchange Online PROTECTION (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="b19eb-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b19eb-109">開始之前，您必須瞭解哪些事項</span><span class="sxs-lookup"><span data-stu-id="b19eb-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="b19eb-110">如果您是 Exchange Online 信箱組織中的系統管理員，建議您在安全性 & 規範中心內使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="b19eb-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="b19eb-111">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="b19eb-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="b19eb-112">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="b19eb-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="b19eb-113">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="b19eb-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="b19eb-114">如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="b19eb-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b19eb-115">如果在使用者提交原則中停用 Outlook 的垃圾郵件報告，則垃圾郵件或網路釣魚郵件會移至 [垃圾郵件] 資料夾，而不會向您的系統管理員或 Microsoft 報告。</span><span class="sxs-lookup"><span data-stu-id="b19eb-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="b19eb-116">在 Outlook 中報告 iOS 和 Android 的垃圾郵件和網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="b19eb-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="b19eb-117">對於收件匣中的郵件，或任何其他電子郵件資料夾（除垃圾郵件之外），請使用下列步驟來報告 iOS 和 Android 的垃圾郵件和網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="b19eb-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="b19eb-118">選取一或多封郵件。</span><span class="sxs-lookup"><span data-stu-id="b19eb-118">Select one or more messages.</span></span>
2. <span data-ttu-id="b19eb-119">在右上角敲擊三個垂直點。</span><span class="sxs-lookup"><span data-stu-id="b19eb-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="b19eb-120">[動作] 功能表隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="b19eb-120">The action menu opens.</span></span>

   ![從 [動作] 功能表報告垃圾郵件或網路釣魚電子郵件](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="b19eb-122">點擊 [ **報告垃圾郵件** ]，然後選取 [ **垃圾郵件** 或 **網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="b19eb-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![報告垃圾郵件或網路釣魚電子郵件](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="b19eb-124">在出現的對話方塊中，您可以選擇 [ **報告** ] 或 [ **不是致謝**]。</span><span class="sxs-lookup"><span data-stu-id="b19eb-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="b19eb-125">在選擇 [ **不謝謝**] 的情況下，如果您已攻入 **垃圾** 郵件，則會將郵件移至 [垃圾郵件] 資料夾，如果您對郵件進行 **網路釣魚** 。</span><span class="sxs-lookup"><span data-stu-id="b19eb-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="b19eb-126">選取 [ **報告** ]，也可以將郵件複本傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="b19eb-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![報告垃圾郵件或網路釣魚電子郵件報告選項](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="b19eb-128">如果您變更主意，請在出現的 toast 通知上選取 [ **撤銷** ]。</span><span class="sxs-lookup"><span data-stu-id="b19eb-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="b19eb-129">郵件會保留在 [收件匣] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b19eb-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="b19eb-130">在 Outlook 的 [垃圾郵件] 資料夾中報告 iOS 和 Android 的非垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b19eb-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="b19eb-131">在 [垃圾郵件] 資料夾中，使用下列步驟來報告垃圾郵件誤報：</span><span class="sxs-lookup"><span data-stu-id="b19eb-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="b19eb-132">選取一或多封郵件。</span><span class="sxs-lookup"><span data-stu-id="b19eb-132">Select one or more messages.</span></span>
2. <span data-ttu-id="b19eb-133">在右上角敲擊三個垂直點。</span><span class="sxs-lookup"><span data-stu-id="b19eb-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="b19eb-134">[動作] 功能表隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="b19eb-134">The action menu opens.</span></span>

   ![從 [動作] 功能表報告非垃圾郵件](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="b19eb-136">點擊 [ **非垃圾郵件**]。</span><span class="sxs-lookup"><span data-stu-id="b19eb-136">Tap **Not junk**.</span></span>

<span data-ttu-id="b19eb-137">Toast 通知會顯示電子郵件已移至您的收件匣。</span><span class="sxs-lookup"><span data-stu-id="b19eb-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="b19eb-138">如果您變更主意，請選取 toast 通知上的 [ **復原** ]。</span><span class="sxs-lookup"><span data-stu-id="b19eb-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="b19eb-139">電子郵件仍會保留在 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b19eb-139">The email remains in the Junk folder.</span></span>
