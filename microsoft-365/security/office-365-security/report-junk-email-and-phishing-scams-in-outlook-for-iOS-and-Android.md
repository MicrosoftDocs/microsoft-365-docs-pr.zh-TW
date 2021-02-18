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
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289170"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="34302-103">在適用于 Exchange Online 的 iOS 和 Android 的 Outlook 中報告垃圾郵件和網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="34302-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34302-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="34302-104">**Applies to**</span></span>
- [<span data-ttu-id="34302-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="34302-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="34302-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="34302-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="34302-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34302-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="34302-108">在使用 [混合式新式驗證](../../enterprise/hybrid-modern-auth-overview.md)的 Exchange Online 或內部部署信箱中有信箱的 Microsoft 365 組織中，您可以使用內建的報告選項，在 Outlook 中 IOS 和 Android 提交誤報 (正常電子郵件標示為垃圾郵件) 、false 負片 (不良電子郵件允許) ，以及網路釣魚郵件至 Exchange Online PROTECTION (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="34302-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="34302-109">開始之前，您必須瞭解哪些事項</span><span class="sxs-lookup"><span data-stu-id="34302-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="34302-110">為了獲得最佳的使用者提交經驗，我們建議使用報告訊息和報告網路釣魚增益集。請參閱 [enable The Report Message 增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) 及 [啟用報告網路釣魚增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="34302-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="34302-111">如果您是 Exchange Online 信箱組織中的系統管理員，建議您在安全性 & 規範中心內使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="34302-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="34302-112">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="34302-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="34302-113">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="34302-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="34302-114">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="34302-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="34302-115">如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="34302-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="34302-116">如果在使用者提交原則中停用 Outlook 的垃圾郵件報告，則垃圾郵件或網路釣魚郵件會移至 [垃圾郵件] 資料夾，而不會向您的系統管理員或 Microsoft 報告。</span><span class="sxs-lookup"><span data-stu-id="34302-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>