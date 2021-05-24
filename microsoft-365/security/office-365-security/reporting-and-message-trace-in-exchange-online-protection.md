---
title: 報告和郵件追蹤
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解可用來 Microsoft Exchange Online Protection (EOP) 系統管理員的報告和疑難排解工具。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae55ded9d907754161813c9f7bfa7eeb14c558a8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625026"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="17fa3-103">EOP 中的報告和郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="17fa3-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="17fa3-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="17fa3-104">**Applies to**</span></span>
- [<span data-ttu-id="17fa3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="17fa3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="17fa3-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="17fa3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="17fa3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17fa3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="17fa3-108">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，EOP 提供許多不同的報告，可協助您判斷組織的整體狀態與健康情況。</span><span class="sxs-lookup"><span data-stu-id="17fa3-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="17fa3-109">還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。</span><span class="sxs-lookup"><span data-stu-id="17fa3-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="17fa3-110">使用情況報告</span><span class="sxs-lookup"><span data-stu-id="17fa3-110">Usage reports</span></span>

<span data-ttu-id="17fa3-111">**Microsoft 365 群組活動**：查看已建立及使用之 Microsoft 365 群組數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="17fa3-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="17fa3-112">**電子郵件活動**：查看您整個組織中傳送、接收和讀取的郵件數目，以及特定使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="17fa3-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="17fa3-113">**電子郵件應用程式使用狀況**：查看使用的電子郵件應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="17fa3-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="17fa3-114">這包括每個應用程式的連線總數，以及所連接之 Outlook 的版本。</span><span class="sxs-lookup"><span data-stu-id="17fa3-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="17fa3-115">**信箱使用狀況**：查看信箱的「傳送或讀取活動」) 使用的儲存空間、配額消耗、專案計數及最後一項活動的相關資訊 (。</span><span class="sxs-lookup"><span data-stu-id="17fa3-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="17fa3-116">如需詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="17fa3-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="17fa3-117">Microsoft 365系統管理中心的報告-Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="17fa3-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="17fa3-118">Microsoft 365系統管理中心內的報告-電子郵件活動</span><span class="sxs-lookup"><span data-stu-id="17fa3-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="17fa3-119">Microsoft 365系統管理中心的報告-電子郵件應用程式使用方式</span><span class="sxs-lookup"><span data-stu-id="17fa3-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="17fa3-120">Microsoft 365系統管理中心的報告-信箱使用量</span><span class="sxs-lookup"><span data-stu-id="17fa3-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="17fa3-121">Microsoft 365 系統管理中心的安全性 & 符合性報告</span><span class="sxs-lookup"><span data-stu-id="17fa3-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="17fa3-122">這些增強型報告提供 EOP 系統管理員的互動式報告經驗（包括摘要資訊），以及深入查看詳細資訊的功能。</span><span class="sxs-lookup"><span data-stu-id="17fa3-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="17fa3-123">**Office 365 的 Defender**：查看有關安全連結的資訊，以及屬於 Office 365 Microsoft Defender 一部分的安全附件。</span><span class="sxs-lookup"><span data-stu-id="17fa3-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="17fa3-124">**EOP**：查看組織中惡意程式碼偵測、欺騙性郵件、垃圾郵件偵測和郵件流程的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="17fa3-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="17fa3-125">View Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="17fa3-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="17fa3-126">使用 Microsoft Graph 的自訂報告</span><span class="sxs-lookup"><span data-stu-id="17fa3-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="17fa3-127">使用 Microsoft Graph，以程式設計方式建立可以在系統管理中心中使用的報告。</span><span class="sxs-lookup"><span data-stu-id="17fa3-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="17fa3-128">如需詳細資訊，請參閱[microsoft Graph](/graph/overview)和[使用 microsoft Graph 中的 Office 365 使用方式報告](/graph/api/resources/report)。</span><span class="sxs-lookup"><span data-stu-id="17fa3-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="17fa3-129">郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="17fa3-129">Message trace</span></span>

<span data-ttu-id="17fa3-130">在電子郵件通過 EOP 時進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="17fa3-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="17fa3-131">您可以判斷服務是否接收、拒絕、延遲或傳遞電子郵件。</span><span class="sxs-lookup"><span data-stu-id="17fa3-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="17fa3-132">它也會顯示在郵件到達其最終狀態前，已對郵件執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="17fa3-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="17fa3-133">您可以使用此資訊來有效地回答使用者的問題、疑難排解郵件流程問題、驗證原則變更，以及緩解聯繫技術支援以尋求協助的需求。</span><span class="sxs-lookup"><span data-stu-id="17fa3-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="17fa3-134">請參閱 [安全性 & 規範中心中的郵件追蹤](message-trace-scc.md)。</span><span class="sxs-lookup"><span data-stu-id="17fa3-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="17fa3-135">稽核記錄</span><span class="sxs-lookup"><span data-stu-id="17fa3-135">Audit logging</span></span>

<span data-ttu-id="17fa3-136">追蹤由系統管理員對組織所做的特定變更。</span><span class="sxs-lookup"><span data-stu-id="17fa3-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="17fa3-137">這些報告可協助您疑難排解組態問題，或找出安全性或法規遵循相關問題的原因。</span><span class="sxs-lookup"><span data-stu-id="17fa3-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="17fa3-138">請參閱[Exchange Online 中的審計報告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)。</span><span class="sxs-lookup"><span data-stu-id="17fa3-138">See [Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="17fa3-139">報告和郵件追蹤資料的可用性與延遲</span><span class="sxs-lookup"><span data-stu-id="17fa3-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="17fa3-140">下表說明可使用 EOP 報告和郵件追蹤資料的時間及時間長短。</span><span class="sxs-lookup"><span data-stu-id="17fa3-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="17fa3-141">報告類型</span><span class="sxs-lookup"><span data-stu-id="17fa3-141">Report type</span></span>|<span data-ttu-id="17fa3-142">資料可用時間 (回顧期間)</span><span class="sxs-lookup"><span data-stu-id="17fa3-142">Data available for (look back period)</span></span>|<span data-ttu-id="17fa3-143">延遲</span><span class="sxs-lookup"><span data-stu-id="17fa3-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="17fa3-144">郵件保護摘要報告</span><span class="sxs-lookup"><span data-stu-id="17fa3-144">Mail protection summary reports</span></span>|<span data-ttu-id="17fa3-145">90 天</span><span class="sxs-lookup"><span data-stu-id="17fa3-145">90 days</span></span>|<span data-ttu-id="17fa3-p106">郵件資料彙總大部分會在 24 到 48 小時內完成。部分次要的增量彙總變更最多存在 5 天。</span><span class="sxs-lookup"><span data-stu-id="17fa3-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="17fa3-148">郵件保護詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="17fa3-148">Mail protection detail reports</span></span>|<span data-ttu-id="17fa3-149">90 天</span><span class="sxs-lookup"><span data-stu-id="17fa3-149">90 days</span></span>|<span data-ttu-id="17fa3-p107">針對 7 天內的詳細資料，資料應於 24 小時內出現，但可能要等到 48 小時後才完成。部分次要的增量變更最多存在 5 天。</span><span class="sxs-lookup"><span data-stu-id="17fa3-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="17fa3-152">若要檢視超過 7 天之郵件的詳細資料報告，結果可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="17fa3-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="17fa3-153">郵件追蹤資料</span><span class="sxs-lookup"><span data-stu-id="17fa3-153">Message trace data</span></span>|<span data-ttu-id="17fa3-154">90 天</span><span class="sxs-lookup"><span data-stu-id="17fa3-154">90 days</span></span>|<span data-ttu-id="17fa3-155">針對 7 天內的郵件執行郵件追蹤時，郵件應於 5 到 30 分鐘內出現。</span><span class="sxs-lookup"><span data-stu-id="17fa3-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="17fa3-156">針對超過 7 天的郵件執行郵件追蹤時，結果可能需要幾個小時。</span><span class="sxs-lookup"><span data-stu-id="17fa3-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="17fa3-157">不論是透過系統管理中心或遠端 PowerShell 所要求的資料可用性和延遲，都是相同的。</span><span class="sxs-lookup"><span data-stu-id="17fa3-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>