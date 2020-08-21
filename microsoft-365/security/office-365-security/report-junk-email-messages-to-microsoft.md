---
title: 將垃圾郵件、非垃圾郵件和網路釣魚郵件報告給 Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解不同的方式，向 Microsoft 報告好的和壞的訊息和檔案，以進行分析。
ms.openlocfilehash: fabe28d084361041ae9e6a8d118dd8c43c2225f7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827638"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="2b164-103">回報訊息和檔案至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="2b164-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="2b164-104">在使用 Exchange Online 中的信箱或獨立 Exchange Online (Protection 中的 Microsoft 365 組織中，使用者與系統管理員都有數種不同的方法，可將電子郵件和檔案報告給 Microsoft，) EOP 不需要 Exchange Online 信箱的組織。</span><span class="sxs-lookup"><span data-stu-id="2b164-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

****

|<span data-ttu-id="2b164-105">方法	</span><span class="sxs-lookup"><span data-stu-id="2b164-105">Method</span></span>|<span data-ttu-id="2b164-106">描述</span><span class="sxs-lookup"><span data-stu-id="2b164-106">Description</span></span>|
|---|---|
|[<span data-ttu-id="2b164-107">使用系統管理提交，將可疑的垃圾郵件、網路釣魚詐騙、URL 和檔案提交給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b164-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="2b164-108">在具有 Exchange Online 信箱的組織中，系統管理員建議的報表方法 (無法在獨立 EOP) 中使用。</span><span class="sxs-lookup"><span data-stu-id="2b164-108">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="2b164-109">啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="2b164-109">Enable the Report Message add-in</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="2b164-110">可搭配 Outlook、outlook for Mac 和 outlook 網頁版上的 outlook (以前稱為 Outlook Web App) ，也是建議的增益集。</span><span class="sxs-lookup"><span data-stu-id="2b164-110">Works with Outlook, Outlook for Mac, and Outlook on the web (formerly known as Outlook Web App), and is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="2b164-111">視您的訂閱而定，使用者使用增益集來報告的郵件可用於系統 [管理提交入口網站](admin-submission.md)、 [自動調查和回應 (AIR) 結果](air-view-investigation-results.md)、 [使用者報告的郵件報告](view-email-security-reports.md#user-reported-messages-report)及 [威脅瀏覽器](threat-explorer-views.md#email--submissions)。</span><span class="sxs-lookup"><span data-stu-id="2b164-111">Depending on your subscription, messages that users reported with the add-in are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span> <br/><br/> <span data-ttu-id="2b164-112">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="2b164-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="2b164-113">如需詳細資訊，請參閱 [在 EOP 中指定使用者送出垃圾郵件和網路釣魚郵件的信箱](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="2b164-113">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in EOP](user-submission.md).</span></span>|
|[<span data-ttu-id="2b164-114">安裝和使用 Microsoft Outlook 的垃圾郵件回報增益集</span><span class="sxs-lookup"><span data-stu-id="2b164-114">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="2b164-115">只能在 Outlook 中運作。</span><span class="sxs-lookup"><span data-stu-id="2b164-115">Only works in Outlook.</span></span>|
|[<span data-ttu-id="2b164-116">在 web 上的 Outlook 中報告垃圾郵件和網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="2b164-116">Report junk and phishing email in Outlook on the web</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="2b164-117">在適用于 Exchange Online 信箱的組織網頁上，使用 Outlook 網頁版內建的功能 (無法在獨立 EOP) 中使用。</span><span class="sxs-lookup"><span data-stu-id="2b164-117">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span> <br/><br/> <span data-ttu-id="2b164-118">使用者報告可在系統 [管理員提交入口網站](admin-submission.md)中使用的訊息。</span><span class="sxs-lookup"><span data-stu-id="2b164-118">Messages that users report are available in [the Admin Submissions portal](admin-submission.md).</span></span> <br/><br/> <span data-ttu-id="2b164-119">您可以設定報告的郵件以複製或重新導向至您指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="2b164-119">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="2b164-120">如需詳細資訊，請參閱 [在 Exchange online 中指定使用者送出垃圾郵件和網路釣魚郵件的信箱](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="2b164-120">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange online](user-submission.md).</span></span>|
|[<span data-ttu-id="2b164-121">手動將郵件提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="2b164-121">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="2b164-122">手動將附加的郵件傳送到垃圾郵件、非垃圾郵件和網路釣魚的特定 Microsoft 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2b164-122">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="2b164-123">使用郵件流程規則來查看您的使用者回報給 Microsoft 哪些內容</span><span class="sxs-lookup"><span data-stu-id="2b164-123">Use mail flow rules to see what your users are reporting to Microsoft</span></span>](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|<span data-ttu-id="2b164-124">瞭解如何建立郵件流程規則 (也稱為傳輸規則) ，當使用者將郵件報告給 Microsoft 進行分析時，會通知您。</span><span class="sxs-lookup"><span data-stu-id="2b164-124">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>
|||
|[<span data-ttu-id="2b164-125">將惡意程式碼和非惡意程式碼提交給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="2b164-125">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="2b164-126">使用 Microsoft 安全性情報網站送出附件及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="2b164-126">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="2b164-127">如果已隔離垃圾郵件或網路釣魚郵件，而不是傳遞郵件，則使用者可以從 Security & 合規性中心的隔離入口網站，將郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="2b164-127">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center.</span></span> <span data-ttu-id="2b164-128">如需詳細資訊，請參閱 [在 Microsoft 365 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="2b164-128">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>
