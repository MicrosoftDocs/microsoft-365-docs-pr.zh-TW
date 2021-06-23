---
title: 將垃圾郵件、非垃圾郵件和網路釣魚郵件報告給 Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解不同的方式，向 Microsoft 報告好的和壞的訊息和檔案，以進行分析。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082813"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="5ffa6-103">回報訊息和檔案至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ffa6-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5ffa6-104">**Applies to**</span></span>
- [<span data-ttu-id="5ffa6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ffa6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ffa6-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="5ffa6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ffa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ffa6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5ffa6-108">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，使用者與系統管理員都有數種不同的方法，可向 Microsoft 報告電子郵件和檔案。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="5ffa6-109">方法	</span><span class="sxs-lookup"><span data-stu-id="5ffa6-109">Method</span></span>|<span data-ttu-id="5ffa6-110">描述</span><span class="sxs-lookup"><span data-stu-id="5ffa6-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="5ffa6-111">使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5ffa6-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="5ffa6-112">在具有 Exchange Online 信箱的組織中，系統管理員的建議報告方法 (無法在獨立 EOP) 中使用。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="5ffa6-113">啟用報告訊息或報告網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="5ffa6-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="5ffa6-114">使用 Outlook 和 Outlook 網頁版 (先前稱為 Outlook Web App) 。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="5ffa6-115">視您的訂閱而定，使用者使用增益集來報告的郵件可用於系統 [管理提交入口網站](admin-submission.md)、 [自動調查和回應 (AIR) 結果](air-view-investigation-results.md)、 [使用者報告的訊息報告](view-email-security-reports.md#user-reported-messages-report)及 [Explorer](threat-explorer-views.md#email--submissions)。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="5ffa6-116">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="5ffa6-117">如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="5ffa6-118">在 Outlook 中報告誤判和漏報</span><span class="sxs-lookup"><span data-stu-id="5ffa6-118">Report false positives and false negatives in Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="5ffa6-119">提交誤報 (已封鎖或傳送至 [垃圾郵件] 資料夾) 的良好電子郵件，以及已傳遞至收件匣) 的電子郵件釣魚 (有害電子郵件或網路釣魚程式，使用報告郵件功能 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="5ffa6-120">手動將郵件提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="5ffa6-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="5ffa6-121">手動將附加的郵件傳送到垃圾郵件、非垃圾郵件和網路釣魚的特定 Microsoft 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="5ffa6-122">使用郵件流程規則來查看使用者報告給 Microsoft 的內容</span><span class="sxs-lookup"><span data-stu-id="5ffa6-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="5ffa6-123">瞭解如何建立郵件流程規則 (也稱為傳輸規則) ，當使用者將郵件報告給 Microsoft 進行分析時，會通知您。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="5ffa6-124">將惡意程式碼和非惡意程式碼提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="5ffa6-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="5ffa6-125">使用 Microsoft 安全情報網站提交附件及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="5ffa6-126">如果已隔離垃圾郵件或網路釣魚郵件，而非傳遞郵件，則使用者可以在 Microsoft 365 Defender 入口網站中，從隔離區將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from Quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="5ffa6-127">如需詳細資訊，請參閱[在 Microsoft 365 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5ffa6-128">送出至 Microsoft 的資料是在北美資料中心的 Office 365 法規遵從性界限內。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="5ffa6-129">工程小組的分析人員會檢查資料，以協助改善篩選的效能。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
