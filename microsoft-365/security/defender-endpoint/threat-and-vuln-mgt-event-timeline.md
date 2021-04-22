---
title: 威脅和弱點管理中的事件時程表
description: 事件時程表是一種風險資訊摘要，可協助您解讀組織中的風險被引進方式，以及哪些緩解措施減少。
keywords: 事件時程表，Microsoft Defender for Endpoint 事件時程表，Microsoft Defender for Endpoint tvm 事件時程表，威脅和弱點管理，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933478"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="a40e3-104">事件時程表-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="a40e3-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a40e3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a40e3-105">**Applies to:**</span></span>
- [<span data-ttu-id="a40e3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a40e3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a40e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a40e3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a40e3-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="a40e3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a40e3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a40e3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="a40e3-110">事件時程表是一種危險資訊摘要，可協助您透過新的漏洞或利用手段，協助您解釋風險在組織中的引進方式。</span><span class="sxs-lookup"><span data-stu-id="a40e3-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="a40e3-111">您可以查看可能影響組織風險的事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="a40e3-112">例如，您可以找出已引進的新漏洞、可被攻擊者利用的漏洞、新增至利用方式套件的漏洞，等等。</span><span class="sxs-lookup"><span data-stu-id="a40e3-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="a40e3-113">事件時程表也會告訴您 [暴露分數](tvm-exposure-score.md) 和 [Microsoft 安全評分](tvm-microsoft-secure-score-devices.md) 的情景，以判斷大型變更的原因。</span><span class="sxs-lookup"><span data-stu-id="a40e3-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="a40e3-114">事件可能會影響裝置或您的裝置得分。</span><span class="sxs-lookup"><span data-stu-id="a40e3-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="a40e3-115">根據已設定優先順序的 [安全性建議](tvm-security-recommendation.md)，以降低您的危險性。</span><span class="sxs-lookup"><span data-stu-id="a40e3-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="a40e3-116">若要取得有關新弱點事件的電子郵件，請參閱 [在 Microsoft Defender For Endpoint 中設定弱點電子郵件通知](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="a40e3-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="a40e3-117">流覽至 [事件時程表] 頁面</span><span class="sxs-lookup"><span data-stu-id="a40e3-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="a40e3-118">[威脅和弱點管理儀表板](tvm-dashboard-insights.md)也有三個入門點：</span><span class="sxs-lookup"><span data-stu-id="a40e3-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="a40e3-119">**組織公開評分**：將滑鼠游標移至 [一段時間的披露分數] 圖表中的事件點上方，然後選取 [查看此天的所有事件]。</span><span class="sxs-lookup"><span data-stu-id="a40e3-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="a40e3-120">事件代表軟體弱點。</span><span class="sxs-lookup"><span data-stu-id="a40e3-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="a40e3-121">**適用于裝置的 Microsoft 安全計分**：將游標移到 [您的裝置一段時間的分數] 圖表中的事件點上方，然後選取 [查看此天的所有事件]。</span><span class="sxs-lookup"><span data-stu-id="a40e3-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="a40e3-122">事件代表新的設定評估。</span><span class="sxs-lookup"><span data-stu-id="a40e3-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="a40e3-123">**最上層的事件卡片**：選取上方事件表底部的 [顯示更多]。</span><span class="sxs-lookup"><span data-stu-id="a40e3-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="a40e3-124">這張卡片會顯示過去7天的三個最 impactful 事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="a40e3-125">Impactful 事件可以包含如果事件會影響大量的裝置，或是嚴重缺陷。</span><span class="sxs-lookup"><span data-stu-id="a40e3-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="a40e3-126">裝置圖形的披露分數和 Microsoft 安全評分</span><span class="sxs-lookup"><span data-stu-id="a40e3-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="a40e3-127">在 [威脅與弱點管理] 儀表板中，將游標移到 [曝光分數] 圖上方，以查看該天中影響裝置的主要軟體弱點事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="a40e3-128">將游標移至 [裝置的 Microsoft 安全評分] 圖表，以查看會影響得分的新安全性設定評估。</span><span class="sxs-lookup"><span data-stu-id="a40e3-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="a40e3-129">如果沒有會影響裝置或您的裝置得分的事件，則不會顯示任何事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="a40e3-130">![](images/tvm-event-timeline-exposure-score350.png) 
 ![ 適用于裝置懸停的公開分數懸停 Microsoft 安全分數](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="a40e3-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="a40e3-131">深入查看該天的事件</span><span class="sxs-lookup"><span data-stu-id="a40e3-131">Drill down to events from that day</span></span>

<span data-ttu-id="a40e3-132">選取 [ **顯示此天的所有事件** ] 會帶您前往該天之自訂日期範圍的 [事件時程表] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a40e3-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![事件時程表選取的自訂日期範圍](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="a40e3-134">選取 [ **自訂範圍** ]，將日期範圍變更為另一個自訂的範圍，或是預先設定的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="a40e3-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![事件時程表日期範圍選項](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="a40e3-136">事件時程表概述</span><span class="sxs-lookup"><span data-stu-id="a40e3-136">Event timeline overview</span></span>

<span data-ttu-id="a40e3-137">在 [事件時程表] 頁面上，您可以查看與事件相關的所有必要資訊。</span><span class="sxs-lookup"><span data-stu-id="a40e3-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="a40e3-138">功能：</span><span class="sxs-lookup"><span data-stu-id="a40e3-138">Features:</span></span>

- <span data-ttu-id="a40e3-139">自訂欄</span><span class="sxs-lookup"><span data-stu-id="a40e3-139">Customize columns</span></span>
- <span data-ttu-id="a40e3-140">依事件種類或受影響裝置的百分比篩選</span><span class="sxs-lookup"><span data-stu-id="a40e3-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="a40e3-141">每頁 View 30、50或100專案</span><span class="sxs-lookup"><span data-stu-id="a40e3-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="a40e3-142">頁面頂端的兩個大數位會顯示新的漏洞及可攻擊的漏洞數目，而不是事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="a40e3-143">有些事件可能會有多個漏洞，有些漏洞可能會有多個事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![事件時程表頁面](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="a40e3-145">Columns</span><span class="sxs-lookup"><span data-stu-id="a40e3-145">Columns</span></span>

- <span data-ttu-id="a40e3-146">**Date**： month、day、year</span><span class="sxs-lookup"><span data-stu-id="a40e3-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="a40e3-147">**事件**： impactful 事件，包含受影響裝置的元件、類型和數目</span><span class="sxs-lookup"><span data-stu-id="a40e3-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="a40e3-148">**相關元件**：軟體</span><span class="sxs-lookup"><span data-stu-id="a40e3-148">**Related component**: software</span></span>
- <span data-ttu-id="a40e3-149">「**原始影響裝置**」：此事件原來發生時，受影響裝置的數目和百分比。</span><span class="sxs-lookup"><span data-stu-id="a40e3-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="a40e3-150">您也可以依原始影響裝置的百分比進行篩選，而不是裝置的總數目。</span><span class="sxs-lookup"><span data-stu-id="a40e3-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="a40e3-151">**目前受影響的裝置**：此事件目前影響之裝置的目前數量和百分比。</span><span class="sxs-lookup"><span data-stu-id="a40e3-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="a40e3-152">您可以選取 [ **自訂** 欄位] 來找到此欄位。</span><span class="sxs-lookup"><span data-stu-id="a40e3-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="a40e3-153">**類型**：會反映影響分數的時間戳記事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="a40e3-154">可以篩選它們。</span><span class="sxs-lookup"><span data-stu-id="a40e3-154">They can be filtered.</span></span>
    - <span data-ttu-id="a40e3-155">加入利用套件的 exploit</span><span class="sxs-lookup"><span data-stu-id="a40e3-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="a40e3-156">已驗證利用漏洞</span><span class="sxs-lookup"><span data-stu-id="a40e3-156">Exploit was verified</span></span>
    - <span data-ttu-id="a40e3-157">新的公開利用方式</span><span class="sxs-lookup"><span data-stu-id="a40e3-157">New public exploit</span></span>
    - <span data-ttu-id="a40e3-158">新的弱點</span><span class="sxs-lookup"><span data-stu-id="a40e3-158">New vulnerability</span></span>
    - <span data-ttu-id="a40e3-159">新的設定評估</span><span class="sxs-lookup"><span data-stu-id="a40e3-159">New configuration assessment</span></span>
- <span data-ttu-id="a40e3-160">**分數趨勢**：披露分數趨勢</span><span class="sxs-lookup"><span data-stu-id="a40e3-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="a40e3-161">圖示</span><span class="sxs-lookup"><span data-stu-id="a40e3-161">Icons</span></span>

<span data-ttu-id="a40e3-162">事件旁會顯示下列圖示：</span><span class="sxs-lookup"><span data-stu-id="a40e3-162">The following icons show up next to events:</span></span>

- ![bug 圖示](images/tvm-black-bug-icon.png) <span data-ttu-id="a40e3-164">新的公開利用方式</span><span class="sxs-lookup"><span data-stu-id="a40e3-164">New public exploit</span></span>
- ![報告警告圖示](images/report-warning-icon.png) <span data-ttu-id="a40e3-166">已發佈新的弱點</span><span class="sxs-lookup"><span data-stu-id="a40e3-166">New vulnerability was published</span></span>
- ![exploit 工具組](images/bug-lightning-icon2.png) <span data-ttu-id="a40e3-168">在利用方式套件中找到的漏洞</span><span class="sxs-lookup"><span data-stu-id="a40e3-168">Exploit found in exploit kit</span></span>
- ![具有警告圖示的 bug 圖示](images/bug-caution-icon2.png) <span data-ttu-id="a40e3-170">已驗證利用漏洞</span><span class="sxs-lookup"><span data-stu-id="a40e3-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="a40e3-171">深入查看特定事件</span><span class="sxs-lookup"><span data-stu-id="a40e3-171">Drill down to a specific event</span></span>

<span data-ttu-id="a40e3-172">一旦您選取事件後，就會出現一個快顯視窗，列出會影響裝置的詳細資料和目前 Cve。</span><span class="sxs-lookup"><span data-stu-id="a40e3-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="a40e3-173">您可以顯示更多 Cve 或查看相關的建議。</span><span class="sxs-lookup"><span data-stu-id="a40e3-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="a40e3-174">「分數趨勢」下方的箭號可協助您判斷該事件是否可能升高或降低組織的暴露分數。</span><span class="sxs-lookup"><span data-stu-id="a40e3-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="a40e3-175">暴露程度越高表示裝置變得更容易遭到利用。</span><span class="sxs-lookup"><span data-stu-id="a40e3-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![事件時程表浮出控制項](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="a40e3-177">從那裡，選取 [ **移至相關安全性建議** ] [ [安全性建議] 頁面](tvm-security-recommendation.md)中的建議，以解決新的軟體弱點。</span><span class="sxs-lookup"><span data-stu-id="a40e3-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="a40e3-178">在安全性建議中讀取描述和弱點詳細資料之後，您可以提交修復要求，並在 [ [修正] 頁面](tvm-remediation.md)中追蹤要求。</span><span class="sxs-lookup"><span data-stu-id="a40e3-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="a40e3-179">在軟體頁面中查看事件時程表</span><span class="sxs-lookup"><span data-stu-id="a40e3-179">View Event timelines in software pages</span></span>

<span data-ttu-id="a40e3-180">若要開啟 [軟體] 頁面，請選取事件 > 選取 [超連結軟體名稱] (如 [Visual Studio 2017) ] 中的浮出控制項中名為 "相關元件" 的區段中。</span><span class="sxs-lookup"><span data-stu-id="a40e3-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="a40e3-181">深入瞭解軟體頁面</span><span class="sxs-lookup"><span data-stu-id="a40e3-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="a40e3-182">完整頁面會顯示特定軟體的所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a40e3-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="a40e3-183">將滑鼠移到圖形上方，以查看該特定軟體的事件時程表。</span><span class="sxs-lookup"><span data-stu-id="a40e3-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![含事件時程表圖形的軟體頁面](images/tvm-event-timeline-software2.png)

<span data-ttu-id="a40e3-185">流覽至 [事件時程表] 索引標籤，以查看與該軟體相關的所有事件。</span><span class="sxs-lookup"><span data-stu-id="a40e3-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="a40e3-186">您也可以查看安全性建議、發現的漏洞、已安裝的裝置及版本發行。</span><span class="sxs-lookup"><span data-stu-id="a40e3-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![含事件時程表索引標籤的軟體頁面](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="a40e3-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="a40e3-188">Related topics</span></span>

- [<span data-ttu-id="a40e3-189">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="a40e3-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a40e3-190">儀表板</span><span class="sxs-lookup"><span data-stu-id="a40e3-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="a40e3-191">暴險分數</span><span class="sxs-lookup"><span data-stu-id="a40e3-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="a40e3-192">安全性建議</span><span class="sxs-lookup"><span data-stu-id="a40e3-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="a40e3-193">修正安全性漏洞</span><span class="sxs-lookup"><span data-stu-id="a40e3-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="a40e3-194">軟體庫存</span><span class="sxs-lookup"><span data-stu-id="a40e3-194">Software inventory</span></span>](tvm-software-inventory.md)

