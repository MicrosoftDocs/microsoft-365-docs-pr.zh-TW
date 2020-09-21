---
title: 'Microsoft 365 網路評估 (預覽) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: 'Microsoft 365 網路評估 (預覽) '
ms.openlocfilehash: 21fb9515ea1621225cffbe23fe87d0daeb5265de
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104543"
---
# <a name="microsoft-365-network-assessment-preview"></a><span data-ttu-id="e383b-103">Microsoft 365 網路評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="e383b-103">Microsoft 365 network assessment (preview)</span></span>

<span data-ttu-id="e383b-104">在 Microsoft 365 系統管理中心的網路連線中， **網路評估** 會將許多網路效能度量的集合提煉成商業網路周邊健康情況的快照，以來自 0-100 的點值來表示。</span><span class="sxs-lookup"><span data-stu-id="e383b-104">In the Microsoft 365 Admin Center's network connectivity, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network perimeter health, represented by a points value from 0 - 100.</span></span> <span data-ttu-id="e383b-105">網路評估會告訴您，客戶負責網路設計的程度會影響 Office 365 使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="e383b-105">A network assessment tells you how much the customer responsible network design is impacting Office 365 user experience.</span></span> <span data-ttu-id="e383b-106">網路評估同時適用于整個承租人和每個地理位置，讓使用者可以從該位置連線到您的租使用者，為 Microsoft 365 系統管理員提供一種簡單的方法來立即抓住商業網路健康情況的 gestalt，並快速深入查看任何全球辦公室位置的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="e383b-106">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="e383b-107">網路評估點值是一天內編譯的 TCP 延遲、下載速度及 UDP 連線品質計量的平均。</span><span class="sxs-lookup"><span data-stu-id="e383b-107">The network assessment points value is an average of TCP latency, download speed and UDP connection quality metrics compiled once a day.</span></span> <span data-ttu-id="e383b-108">Microsoft 所擁有網路的效能度量會從這些測量值中排除，以確保評估結果對於公司網路明確且特定。</span><span class="sxs-lookup"><span data-stu-id="e383b-108">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

![網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

<span data-ttu-id="e383b-110">「非常低的網路評估」價值表示 Microsoft 365 用戶端在連線至租使用者時發生重大問題，或維持回應的使用者體驗，而高值則表示設定正確的網路，而不會發生很少的效能問題。</span><span class="sxs-lookup"><span data-stu-id="e383b-110">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience, while a high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="e383b-111">80% 的值代表正常的基準，您不應預期會因網路效能而收到有關 Microsoft 365 連線或回應回應的一般使用者意見。</span><span class="sxs-lookup"><span data-stu-id="e383b-111">A value of 80% represents a healthy baseline where you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="e383b-112">隨著重複網路連線能力的增強，此值會隨著使用者經驗而增加。</span><span class="sxs-lookup"><span data-stu-id="e383b-112">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

| <span data-ttu-id="e383b-113">網路評估</span><span class="sxs-lookup"><span data-stu-id="e383b-113">Network assessment</span></span> | <span data-ttu-id="e383b-114">預期的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="e383b-114">Expected user experience</span></span> |
| :----------------- | :----------------------- |
| <span data-ttu-id="e383b-115">100</span><span class="sxs-lookup"><span data-stu-id="e383b-115">100</span></span>                | <span data-ttu-id="e383b-116">最佳</span><span class="sxs-lookup"><span data-stu-id="e383b-116">Best</span></span>                     |
| <span data-ttu-id="e383b-117">80</span><span class="sxs-lookup"><span data-stu-id="e383b-117">80</span></span>                 | <span data-ttu-id="e383b-118">符合建議</span><span class="sxs-lookup"><span data-stu-id="e383b-118">Meets recommendations</span></span>    |
| <span data-ttu-id="e383b-119">60</span><span class="sxs-lookup"><span data-stu-id="e383b-119">60</span></span>                 | <span data-ttu-id="e383b-120">可以接受</span><span class="sxs-lookup"><span data-stu-id="e383b-120">Acceptable</span></span>               |
| <span data-ttu-id="e383b-121">40</span><span class="sxs-lookup"><span data-stu-id="e383b-121">40</span></span>                 | <span data-ttu-id="e383b-122">使用者可能會遇到問題</span><span class="sxs-lookup"><span data-stu-id="e383b-122">Users may experience issues</span></span> |
| <span data-ttu-id="e383b-123">共</span><span class="sxs-lookup"><span data-stu-id="e383b-123">20</span></span>                 | <span data-ttu-id="e383b-124">使用者可能會抱怨</span><span class="sxs-lookup"><span data-stu-id="e383b-124">Users may complain</span></span>       |
| <span data-ttu-id="e383b-125">0</span><span class="sxs-lookup"><span data-stu-id="e383b-125">0</span></span>                  | <span data-ttu-id="e383b-126">網路問題討論的一般主題</span><span class="sxs-lookup"><span data-stu-id="e383b-126">Network problems a common topic of discussion</span></span> |

>[!IMPORTANT]
><span data-ttu-id="e383b-127">Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="e383b-127">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="e383b-128">網路評估面板</span><span class="sxs-lookup"><span data-stu-id="e383b-128">Network assessment panel</span></span>

<span data-ttu-id="e383b-129">每個網路評估，不論是限定在租使用者或特定辦公室位置，都會顯示一個包含評估詳細資料的面板。</span><span class="sxs-lookup"><span data-stu-id="e383b-129">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="e383b-130">這個面板顯示評估的橫條圖，其百分比和每個元件工作負載的總點數，包括只接收度量資料的工作負載。</span><span class="sxs-lookup"><span data-stu-id="e383b-130">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="e383b-131">針對 office 位置網路評估，我們也會365顯示每五個 quintiles 中，每五個的資料，都與您的辦公室位置報告的資料在相同的城市中。</span><span class="sxs-lookup"><span data-stu-id="e383b-131">For an office location network assessment, we also show a comparison to the percent of Microsoft 365 customers in each of five quintiles that reported data in the same city as your office location.</span></span>

![範例網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

<span data-ttu-id="e383b-133">面板中的 **評估分解** 會顯示每個元件工作負載的評估。</span><span class="sxs-lookup"><span data-stu-id="e383b-133">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="e383b-134">**評估記錄**會顯示過去30天的評估和基準。</span><span class="sxs-lookup"><span data-stu-id="e383b-134">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span> <span data-ttu-id="e383b-135">您也可以使用 [記錄] 索引標籤，在最多兩年中報告任何 office 位置的計量歷程記錄。[記錄] 索引標籤可讓您選取要報告的屬性，並選擇報告的時間範圍您可以反白顯示網路更新專案的影響，並查看網路評估的改進功能。</span><span class="sxs-lookup"><span data-stu-id="e383b-135">You can also report on the metrics history for any office location for up to two years using the history tab. The history tab allows you to select your attributes to report on and by choosing a report timeframe you can highlight the impact of a network update project and see the improvement to your network assessment.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="e383b-136">租使用者網路評估與 office 位置網路評估</span><span class="sxs-lookup"><span data-stu-id="e383b-136">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="e383b-137">網路評估會將辦公位置的網路周邊環境設計，評定為 Microsoft 的網路。</span><span class="sxs-lookup"><span data-stu-id="e383b-137">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="e383b-138">在每個辦公室位置，最適合對網路周邊進行改進。</span><span class="sxs-lookup"><span data-stu-id="e383b-138">Improvements to the network perimeter is best done at each office location.</span></span>

<span data-ttu-id="e383b-139">我們會在 [網路效能一覽表] 頁面上顯示整個 Microsoft 365 租使用者的網路評估值，這是所有 office 位置之網路評估的加權平均值。</span><span class="sxs-lookup"><span data-stu-id="e383b-139">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page which is a weighted average of the network assessments for all office locations.</span></span> <span data-ttu-id="e383b-140">在該位置的 [摘要] 頁面上，每個偵測到之 office 位置的特定網路評估值也是一種。</span><span class="sxs-lookup"><span data-stu-id="e383b-140">There is also a specific network assessment value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="e383b-141">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e383b-141">Exchange Online</span></span>

<span data-ttu-id="e383b-142">針對 Exchange Online，從用戶端電腦到 Exchange 服務前面門的 TCP 延遲是測量。</span><span class="sxs-lookup"><span data-stu-id="e383b-142">For Exchange Online the TCP latency from the client machine to the Exchange service front door is measured.</span></span> <span data-ttu-id="e383b-143">這可能會受到網路透過客戶局域網和 WAN 的距離所影響。</span><span class="sxs-lookup"><span data-stu-id="e383b-143">This can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="e383b-144">這種情況也可能會受到網路仲介裝置或服務的影響，以延遲連線或造成封包重發。</span><span class="sxs-lookup"><span data-stu-id="e383b-144">It can also be impacted by network intermediary devices or services which delay the connectivity or cause packets to be resent.</span></span> <span data-ttu-id="e383b-145">而且會受到最近的 Exchange 服務前端門的距離所影響。</span><span class="sxs-lookup"><span data-stu-id="e383b-145">And it is impacted by how far away the nearest Exchange service front door is.</span></span> <span data-ttu-id="e383b-146">中間的 (也稱為第50個百分點值或 P50 量值，) 是針對前三天的所有度量所取。</span><span class="sxs-lookup"><span data-stu-id="e383b-146">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span>

<span data-ttu-id="e383b-147">Exchange Online 評估是使用下表進行。</span><span class="sxs-lookup"><span data-stu-id="e383b-147">The Exchange Online assessment is made using the following table.</span></span> <span data-ttu-id="e383b-148">在頻帶中以線性方式指派閾值之間的任何 TCP 延遲數位。</span><span class="sxs-lookup"><span data-stu-id="e383b-148">Any TCP latency number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="e383b-149">TCP 延遲</span><span class="sxs-lookup"><span data-stu-id="e383b-149">TCP Latency</span></span>   | <span data-ttu-id="e383b-150">點</span><span class="sxs-lookup"><span data-stu-id="e383b-150">Points</span></span> |
| :------------ | :----- |
| <span data-ttu-id="e383b-151">10ms 或更少</span><span class="sxs-lookup"><span data-stu-id="e383b-151">10ms or less</span></span>  | <span data-ttu-id="e383b-152">100</span><span class="sxs-lookup"><span data-stu-id="e383b-152">100</span></span>    |
| <span data-ttu-id="e383b-153">25ms</span><span class="sxs-lookup"><span data-stu-id="e383b-153">25ms</span></span>          | <span data-ttu-id="e383b-154">80</span><span class="sxs-lookup"><span data-stu-id="e383b-154">80</span></span>     |
| <span data-ttu-id="e383b-155">100ms</span><span class="sxs-lookup"><span data-stu-id="e383b-155">100ms</span></span>         | <span data-ttu-id="e383b-156">60</span><span class="sxs-lookup"><span data-stu-id="e383b-156">60</span></span>     |
| <span data-ttu-id="e383b-157">200ms</span><span class="sxs-lookup"><span data-stu-id="e383b-157">200ms</span></span>         | <span data-ttu-id="e383b-158">40</span><span class="sxs-lookup"><span data-stu-id="e383b-158">40</span></span>     |
| <span data-ttu-id="e383b-159">300ms</span><span class="sxs-lookup"><span data-stu-id="e383b-159">300ms</span></span>         | <span data-ttu-id="e383b-160">共</span><span class="sxs-lookup"><span data-stu-id="e383b-160">20</span></span>     |
| <span data-ttu-id="e383b-161">350ms 或更多</span><span class="sxs-lookup"><span data-stu-id="e383b-161">350ms or more</span></span> | <span data-ttu-id="e383b-162">0</span><span class="sxs-lookup"><span data-stu-id="e383b-162">0</span></span>      |

## <a name="sharepoint-online"></a><span data-ttu-id="e383b-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e383b-163">SharePoint Online</span></span>

<span data-ttu-id="e383b-164">針對 SharePoint 線上，可供使用者從 SharePoint 或 OneDrive 存取檔的下載速度。</span><span class="sxs-lookup"><span data-stu-id="e383b-164">For SharePoint Online the download speed available for a user to access a document from SharePoint or OneDrive is measured.</span></span> <span data-ttu-id="e383b-165">這可能會受到用戶端電腦與 Microsoft 網路之間網路環路上可用頻寬的影響。</span><span class="sxs-lookup"><span data-stu-id="e383b-165">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="e383b-166">這通常是因為網路擁塞存在於複雜網路裝置或不良覆蓋 Wi-Fi 區域中的網路擁塞所影響。</span><span class="sxs-lookup"><span data-stu-id="e383b-166">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span> <span data-ttu-id="e383b-167">下載速度是以每秒 mb 為單位，大約一十分之一每秒額定百萬位元的電路。</span><span class="sxs-lookup"><span data-stu-id="e383b-167">The download speed is measured in megabytes per second which is approximately one tenth of a circuits rated megabits per second.</span></span> <span data-ttu-id="e383b-168">每秒兆單位都很有用，因為您可以直接查看1秒內可下載的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="e383b-168">The MegaByte per second unit is helpful because you can directly see what size file can be downloaded in 1 second.</span></span> <span data-ttu-id="e383b-169">第25個百分點值 (也稱為 P25 量值，) 是針對前三天的所有度量所取。</span><span class="sxs-lookup"><span data-stu-id="e383b-169">The 25th percentile (also known as the P25 measure) is taken for all measurements over the previous three days.</span></span> <span data-ttu-id="e383b-170">這第25個百分點可協助減少隨時間變化的擁塞影響。</span><span class="sxs-lookup"><span data-stu-id="e383b-170">This 25th percentile helps reduce the impact of varying congestion over time.</span></span>

<span data-ttu-id="e383b-171">使用下表進行 SharePoint 線上評估。</span><span class="sxs-lookup"><span data-stu-id="e383b-171">The SharePoint Online assessment is made using the following table.</span></span> <span data-ttu-id="e383b-172">在頻帶中以線性方式指派閾值之間的任何下載速度。</span><span class="sxs-lookup"><span data-stu-id="e383b-172">Any download speed number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="e383b-173">下載速度</span><span class="sxs-lookup"><span data-stu-id="e383b-173">Download speed</span></span> | <span data-ttu-id="e383b-174">點</span><span class="sxs-lookup"><span data-stu-id="e383b-174">Points</span></span> |
| :------------- | :----- |
| <span data-ttu-id="e383b-175">20MBps 或更多</span><span class="sxs-lookup"><span data-stu-id="e383b-175">20MBps or more</span></span> | <span data-ttu-id="e383b-176">100</span><span class="sxs-lookup"><span data-stu-id="e383b-176">100</span></span>    |
| <span data-ttu-id="e383b-177">14MBps</span><span class="sxs-lookup"><span data-stu-id="e383b-177">14MBps</span></span>         | <span data-ttu-id="e383b-178">80</span><span class="sxs-lookup"><span data-stu-id="e383b-178">80</span></span>     |
| <span data-ttu-id="e383b-179">8MBps</span><span class="sxs-lookup"><span data-stu-id="e383b-179">8MBps</span></span>          | <span data-ttu-id="e383b-180">60</span><span class="sxs-lookup"><span data-stu-id="e383b-180">60</span></span>     |
| <span data-ttu-id="e383b-181">4MBps</span><span class="sxs-lookup"><span data-stu-id="e383b-181">4MBps</span></span>          | <span data-ttu-id="e383b-182">40</span><span class="sxs-lookup"><span data-stu-id="e383b-182">40</span></span>     |
| <span data-ttu-id="e383b-183">2MBps</span><span class="sxs-lookup"><span data-stu-id="e383b-183">2MBps</span></span>          | <span data-ttu-id="e383b-184">共</span><span class="sxs-lookup"><span data-stu-id="e383b-184">20</span></span>     |
| <span data-ttu-id="e383b-185">0MBps</span><span class="sxs-lookup"><span data-stu-id="e383b-185">0MBps</span></span>          | <span data-ttu-id="e383b-186">0</span><span class="sxs-lookup"><span data-stu-id="e383b-186">0</span></span>      |

## <a name="microsoft-teams"></a><span data-ttu-id="e383b-187">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e383b-187">Microsoft Teams</span></span>

<span data-ttu-id="e383b-188">針對 Microsoft 小組，網路品質是指 UDP 延遲、UDP 抖動及 UDP 封包遺失。</span><span class="sxs-lookup"><span data-stu-id="e383b-188">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="e383b-189">UDP 可用於 Microsoft 小組的通話和會議音訊和影片媒體連線。</span><span class="sxs-lookup"><span data-stu-id="e383b-189">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="e383b-190">這可能會受到延遲和下載速度相同的因素所影響，除了 UDP 是分別設定為較為常見的 TCP 通訊協定以外，其他情況也是在網路的 UDP 支援中使用網路中斷性。</span><span class="sxs-lookup"><span data-stu-id="e383b-190">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span> <span data-ttu-id="e383b-191">中間的 (也稱為第50個百分點值或 P50 量值，) 是針對前三天的所有度量所取。</span><span class="sxs-lookup"><span data-stu-id="e383b-191">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span> 

<span data-ttu-id="e383b-192">從一到五的比例，我們計算來自這些 UDP 量值的平均觀點評分。</span><span class="sxs-lookup"><span data-stu-id="e383b-192">We calculate a mean opinion score from these UDP measurements for a scale from one to five.</span></span> <span data-ttu-id="e383b-193">然後，我們會對應至 Microsoft 小組網路評估的0-100 點規模。</span><span class="sxs-lookup"><span data-stu-id="e383b-193">Then we map that to the 0-100 points scale for the Microsoft Teams network assessment.</span></span>  <span data-ttu-id="e383b-194">整體正常情況超過87.5 點，整體壞點低於50點。</span><span class="sxs-lookup"><span data-stu-id="e383b-194">Overall good is over 87.5 points and overall bad is below 50 points.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e383b-195">相關主題</span><span class="sxs-lookup"><span data-stu-id="e383b-195">Related topics</span></span>

[<span data-ttu-id="e383b-196">Microsoft 365 系統管理中心的網路連線 (預覽) </span><span class="sxs-lookup"><span data-stu-id="e383b-196">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="e383b-197">Microsoft 365 網路效能深入 (預覽) </span><span class="sxs-lookup"><span data-stu-id="e383b-197">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="e383b-198">Microsoft 365 connectivity test in M365 Admin Center (預覽) </span><span class="sxs-lookup"><span data-stu-id="e383b-198">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="e383b-199">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="e383b-199">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)

[<span data-ttu-id="e383b-200">Microsoft 365 network connectivity test 工具 (預覽) </span><span class="sxs-lookup"><span data-stu-id="e383b-200">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
