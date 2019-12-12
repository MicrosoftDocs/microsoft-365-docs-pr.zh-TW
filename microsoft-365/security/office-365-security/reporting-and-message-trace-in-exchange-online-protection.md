---
title: Exchange Online Protection 的報告與訊息追蹤
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。下表將說明 EOP 系統管理員可以使用的報告和疑難排解工具。
ms.openlocfilehash: 251286fca4ed54b87809c46e6e0f47ea618df747
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971504"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="6577a-105">Exchange Online Protection 的報告與訊息追蹤</span><span class="sxs-lookup"><span data-stu-id="6577a-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="6577a-106">Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。</span><span class="sxs-lookup"><span data-stu-id="6577a-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="6577a-107">還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。</span><span class="sxs-lookup"><span data-stu-id="6577a-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="6577a-108">使用情況報告</span><span class="sxs-lookup"><span data-stu-id="6577a-108">Usage reports</span></span>

<span data-ttu-id="6577a-109">**Office 365 群組活動**： 檢視所建立和使用 Office 365 群組的數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6577a-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>

<span data-ttu-id="6577a-110">**電子郵件活動**： 檢視傳送、 接收和讀取整個組織中與特定使用者的郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6577a-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="6577a-111">**電子郵件 app 使用情況**： 檢視可用的電子郵件應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6577a-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="6577a-112">這包括每個應用程式的連線總數以及要連線的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="6577a-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="6577a-113">**信箱使用量**： 檢視儲存空間的相關資訊、 配額使用率、 項目計數，以及信箱的最後一個活動 （傳送或讀取的活動）。</span><span class="sxs-lookup"><span data-stu-id="6577a-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="6577a-114">請參閱下列資源以取得詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="6577a-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="6577a-115">在系統管理中心的 Office 365 群組的 office 365 報告</span><span class="sxs-lookup"><span data-stu-id="6577a-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="6577a-116">在管理中心中的電子郵件活動的 office 365 報告</span><span class="sxs-lookup"><span data-stu-id="6577a-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="6577a-117">在管理中心中的電子郵件 app 使用情況的 office 365 報告</span><span class="sxs-lookup"><span data-stu-id="6577a-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- <span data-ttu-id="6577a-118">[在系統管理中心的 [信箱使用量的 office 365 報告](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)</span><span class="sxs-lookup"><span data-stu-id="6577a-118">[Office 365 Reports in the Admin Center - Mailbox usage](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)</span></span>

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6577a-119">在 Microsoft 365 系統管理中心內的安全性 & 合規性報告</span><span class="sxs-lookup"><span data-stu-id="6577a-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6577a-120">這些增強型的報告可提供享有互動報告體驗若是 EOP 管理員，其中包含摘要資訊，並向下切入如需詳細資訊的能力。</span><span class="sxs-lookup"><span data-stu-id="6577a-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="6577a-121">**進階威脅防護 (ATP)**: 檢視安全連結和屬於 ATP 安全附件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6577a-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="6577a-122">**EOP**： 檢視有關惡意程式碼偵測、 詐騙的郵件、 垃圾郵件偵測和進出組織的郵件流程的資訊。</span><span class="sxs-lookup"><span data-stu-id="6577a-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="6577a-123">檢視 Office 365 進階威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="6577a-123">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="6577a-124">使用 Microsoft Graph 的自訂報告</span><span class="sxs-lookup"><span data-stu-id="6577a-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="6577a-125">以程式設計方式建立可用報告的 Microsoft 365 系統管理中心中使用 Microsoft Graph。</span><span class="sxs-lookup"><span data-stu-id="6577a-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="6577a-126">請參閱子主題的[使用中 Microsoft Graph 的 Office 365 使用情況報告](https://docs.microsoft.com/graph/api/resources/report)。</span><span class="sxs-lookup"><span data-stu-id="6577a-126">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="6577a-127">使用 Microsoft Graph 的自訂報告</span><span class="sxs-lookup"><span data-stu-id="6577a-127">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="6577a-128">以程式設計方式建立報告。</span><span class="sxs-lookup"><span data-stu-id="6577a-128">Programmatically create reports.</span></span> <span data-ttu-id="6577a-129">請參閱[Microsoft Graph 概觀](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="6577a-129">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="6577a-130">郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="6577a-130">Message trace</span></span>

<span data-ttu-id="6577a-131">在電子郵件通過 EOP 時進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="6577a-131">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="6577a-132">您可以判斷服務是否接收、拒絕、延遲或傳遞電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6577a-132">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="6577a-133">它也會顯示是對郵件所採取的行動之前它達到其最終狀態。</span><span class="sxs-lookup"><span data-stu-id="6577a-133">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="6577a-134">您可以使用此資訊來有效回答使用者的問題、 疑難排解郵件流程問題、 驗證原則變更，並此舉可連絡技術支援尋求協助。</span><span class="sxs-lookup"><span data-stu-id="6577a-134">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="6577a-135">請參閱[追蹤電子郵件](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="6577a-135">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="6577a-136">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="6577a-136">Audit logging</span></span>

<span data-ttu-id="6577a-137">追蹤由系統管理員對組織所做的特定變更。</span><span class="sxs-lookup"><span data-stu-id="6577a-137">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="6577a-138">這些報告可協助您疑難排解組態問題，或找出安全性或法規遵循相關問題的原因。</span><span class="sxs-lookup"><span data-stu-id="6577a-138">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="6577a-139">請參閱[EOP 中的稽核報告](auditing-reports-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="6577a-139">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="6577a-140">報告和郵件追蹤資料的可用性與延遲</span><span class="sxs-lookup"><span data-stu-id="6577a-140">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="6577a-141">下表說明可使用 EOP 報告和郵件追蹤資料的時間及時間長短。</span><span class="sxs-lookup"><span data-stu-id="6577a-141">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="6577a-142">**報告類型**</span><span class="sxs-lookup"><span data-stu-id="6577a-142">**Report type**</span></span>|<span data-ttu-id="6577a-143">**資料可用時間 (回顧期間)**</span><span class="sxs-lookup"><span data-stu-id="6577a-143">**Data available for (look back period)**</span></span>|<span data-ttu-id="6577a-144">**延遲**</span><span class="sxs-lookup"><span data-stu-id="6577a-144">**Latency**</span></span>|
|<span data-ttu-id="6577a-145">郵件保護摘要報告</span><span class="sxs-lookup"><span data-stu-id="6577a-145">Mail protection summary reports</span></span>|<span data-ttu-id="6577a-146">90 天</span><span class="sxs-lookup"><span data-stu-id="6577a-146">90 days</span></span>|<span data-ttu-id="6577a-p108">郵件資料彙總大部分會在 24 到 48 小時內完成。部分次要的增量彙總變更最多存在 5 天。</span><span class="sxs-lookup"><span data-stu-id="6577a-p108">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="6577a-149">郵件保護詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="6577a-149">Mail protection detail reports</span></span>|<span data-ttu-id="6577a-150">90 天</span><span class="sxs-lookup"><span data-stu-id="6577a-150">90 days</span></span>|<span data-ttu-id="6577a-p109">針對 7 天內的詳細資料，資料應於 24 小時內出現，但可能要等到 48 小時後才完成。部分次要的增量變更最多存在 5 天。</span><span class="sxs-lookup"><span data-stu-id="6577a-p109">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="6577a-153">若要檢視超過 7 天之郵件的詳細資料報告，結果可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="6577a-153">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="6577a-154">郵件追蹤資料</span><span class="sxs-lookup"><span data-stu-id="6577a-154">Message trace data</span></span>|<span data-ttu-id="6577a-155">90 天</span><span class="sxs-lookup"><span data-stu-id="6577a-155">90 days</span></span>|<span data-ttu-id="6577a-156">針對 7 天內的郵件執行郵件追蹤時，郵件應於 5 到 30 分鐘內出現。</span><span class="sxs-lookup"><span data-stu-id="6577a-156">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="6577a-157">針對超過 7 天的郵件執行郵件追蹤時，結果可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="6577a-157">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="6577a-158">資料可用性和延遲是相同的是否要求透過 Microsoft 365 系統管理中心或遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6577a-158">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
