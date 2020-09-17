---
title: 'Microsoft 365 網路評估 (預覽) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: 15eb514980bb53bd32380e44b6bfa174670f6b85
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948311"
---
# <a name="microsoft-365-network-assessment-preview"></a><span data-ttu-id="c6b34-103">Microsoft 365 網路評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="c6b34-103">Microsoft 365 network assessment (preview)</span></span>

<span data-ttu-id="c6b34-104">在 Microsoft 365 系統管理中心與 Microsoft 365 的連線能力頁面中， **網路評估** 會將許多網路效能度量的匯總，提煉成商業網路周邊健康情況的快照，以點數從 0-100 來表示。</span><span class="sxs-lookup"><span data-stu-id="c6b34-104">In the Microsoft 365 Admin Center's Connectivity to Microsoft 365 page, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network perimeter health, represented by a points value from 0 - 100.</span></span> <span data-ttu-id="c6b34-105">網路評估同時適用于整個承租人和每個地理位置，讓使用者可以從該位置連線到您的租使用者，為 Microsoft 365 系統管理員提供一種簡單的方法來立即抓住商業網路健康情況的 gestalt，並快速深入查看任何全球辦公室位置的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="c6b34-105">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="c6b34-106">網路評估點值是 TCP 延遲、下載速度及 UDP 連線品質度量在查看時所進行的平均衡量。</span><span class="sxs-lookup"><span data-stu-id="c6b34-106">The network assessment points value is an average measurement of TCP latency, download speed and UDP connection quality metrics compiled live at the time they are viewed.</span></span> <span data-ttu-id="c6b34-107">Microsoft 所擁有網路的效能度量會從這些測量值中排除，以確保評估結果對於公司網路明確且特定。</span><span class="sxs-lookup"><span data-stu-id="c6b34-107">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

![網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

<span data-ttu-id="c6b34-109">「非常低的網路評估」價值表示 Microsoft 365 用戶端在連線至租使用者時發生重大問題，或維持回應的使用者體驗，而高值則表示設定正確的網路，而不會發生很少的效能問題。</span><span class="sxs-lookup"><span data-stu-id="c6b34-109">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience, while a high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="c6b34-110">80% 的值代表正常的基準，您不應預期會因網路效能而收到有關 Microsoft 365 連線或回應回應的一般使用者意見。</span><span class="sxs-lookup"><span data-stu-id="c6b34-110">A value of 80% represents a healthy baseline where you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="c6b34-111">隨著重複網路連線能力的增強，此值會隨著使用者經驗而增加。</span><span class="sxs-lookup"><span data-stu-id="c6b34-111">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c6b34-112">Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="c6b34-112">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="c6b34-113">網路評估面板</span><span class="sxs-lookup"><span data-stu-id="c6b34-113">Network assessment panel</span></span>

<span data-ttu-id="c6b34-114">每個網路評估，不論是限定在租使用者或特定辦公室位置，都會顯示一個包含評估詳細資料的面板。</span><span class="sxs-lookup"><span data-stu-id="c6b34-114">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="c6b34-115">這個面板顯示評估的橫條圖，其百分比和每個元件工作負載的總點數，包括只接收度量資料的工作負載。</span><span class="sxs-lookup"><span data-stu-id="c6b34-115">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="c6b34-116">針對 office 位置網路評估，我們也會顯示基準，此基準是所有 Microsoft 365 用戶端中報告與您辦公室位置的資料。</span><span class="sxs-lookup"><span data-stu-id="c6b34-116">For an office location network assessment, we also show a benchmark which is the median of all Microsoft 365 clients that reported data in the same city as your office location.</span></span>

![範例網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

<span data-ttu-id="c6b34-118">面板中的 **評估分解** 會顯示每個元件工作負載的評估。</span><span class="sxs-lookup"><span data-stu-id="c6b34-118">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="c6b34-119">**評估記錄**會顯示過去30天的評估和基準。</span><span class="sxs-lookup"><span data-stu-id="c6b34-119">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span> <span data-ttu-id="c6b34-120">您也可以使用 [記錄] 索引標籤，在最多兩年中報告任何 office 位置的計量歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="c6b34-120">You can also report on the metrics history for any office location for up to two years using the history tab.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="c6b34-121">租使用者網路評估與 office 位置網路評估</span><span class="sxs-lookup"><span data-stu-id="c6b34-121">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="c6b34-122">網路評估會將辦公位置的網路周邊環境設計，評定為 Microsoft 的網路。</span><span class="sxs-lookup"><span data-stu-id="c6b34-122">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="c6b34-123">對網路周邊的增強功能最適合於每個辦公室位置，或會影響多個位置的增強功能。</span><span class="sxs-lookup"><span data-stu-id="c6b34-123">Improvements to the network perimeter is best done at each office location, or where network connectivity is aggregated there may be improvements that impact multiple locations.</span></span>

<span data-ttu-id="c6b34-124">我們會在 [網路效能一覽表] 頁面上，顯示整個 Microsoft 365 租使用者的網路評估值，以及該位置 [摘要] 頁面上每個偵測到之 office 位置的特定值。</span><span class="sxs-lookup"><span data-stu-id="c6b34-124">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page and a specific value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="c6b34-125">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c6b34-125">Exchange Online</span></span>

<span data-ttu-id="c6b34-126">針對 Exchange Online，從用戶端電腦到 Exchange 前端伺服器的 TCP 延遲是測量。</span><span class="sxs-lookup"><span data-stu-id="c6b34-126">For Exchange Online the TCP latency from the client machine to the Exchange front end server is measured.</span></span> <span data-ttu-id="c6b34-127">這可能會受到網路透過客戶局域網和 WAN 的距離所影響。</span><span class="sxs-lookup"><span data-stu-id="c6b34-127">This can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="c6b34-128">這種情況也可能會受到網路仲介裝置或服務的影響，以延遲連線或造成封包重發。</span><span class="sxs-lookup"><span data-stu-id="c6b34-128">It can also be impacted by network intermediary devices or services which delay the connectivity or cause packets to be resent.</span></span> <span data-ttu-id="c6b34-129">中間的 (也稱為第50個百分點值或 P50 量值，) 是針對前三天的所有度量所取。</span><span class="sxs-lookup"><span data-stu-id="c6b34-129">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span>

<span data-ttu-id="c6b34-130">Exchange Online 評估是使用下表進行。</span><span class="sxs-lookup"><span data-stu-id="c6b34-130">The Exchange Online assessment is made using the following table.</span></span> <span data-ttu-id="c6b34-131">在頻帶中以線性方式指派閾值之間的任何 TCP 延遲數位。</span><span class="sxs-lookup"><span data-stu-id="c6b34-131">Any TCP latency number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="c6b34-132">TCP 延遲</span><span class="sxs-lookup"><span data-stu-id="c6b34-132">TCP Latency</span></span>   | <span data-ttu-id="c6b34-133">點</span><span class="sxs-lookup"><span data-stu-id="c6b34-133">Points</span></span> |
| :------------ | :----- |
| <span data-ttu-id="c6b34-134">10ms 或更少</span><span class="sxs-lookup"><span data-stu-id="c6b34-134">10ms or less</span></span>  | <span data-ttu-id="c6b34-135">100</span><span class="sxs-lookup"><span data-stu-id="c6b34-135">100</span></span>    |
| <span data-ttu-id="c6b34-136">25ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-136">25ms</span></span>          | <span data-ttu-id="c6b34-137">80</span><span class="sxs-lookup"><span data-stu-id="c6b34-137">80</span></span>     |
| <span data-ttu-id="c6b34-138">100ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-138">100ms</span></span>         | <span data-ttu-id="c6b34-139">60</span><span class="sxs-lookup"><span data-stu-id="c6b34-139">60</span></span>     |
| <span data-ttu-id="c6b34-140">200ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-140">200ms</span></span>         | <span data-ttu-id="c6b34-141">40</span><span class="sxs-lookup"><span data-stu-id="c6b34-141">40</span></span>     |
| <span data-ttu-id="c6b34-142">300ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-142">300ms</span></span>         | <span data-ttu-id="c6b34-143">共</span><span class="sxs-lookup"><span data-stu-id="c6b34-143">20</span></span>     |
| <span data-ttu-id="c6b34-144">350ms 或更多</span><span class="sxs-lookup"><span data-stu-id="c6b34-144">350ms or more</span></span> | <span data-ttu-id="c6b34-145">0</span><span class="sxs-lookup"><span data-stu-id="c6b34-145">0</span></span>      |

## <a name="sharepoint-online"></a><span data-ttu-id="c6b34-146">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c6b34-146">SharePoint Online</span></span>

<span data-ttu-id="c6b34-147">針對 SharePoint 線上，可供使用者從 SharePoint Online 或 OneDrive 存取檔的下載速度。</span><span class="sxs-lookup"><span data-stu-id="c6b34-147">For SharePoint Online the download speed available for a user to access a document from SharePoint Online or OneDrive is measured.</span></span> <span data-ttu-id="c6b34-148">這可能會受到用戶端電腦與 Microsoft 網路之間網路環路上可用頻寬的影響。</span><span class="sxs-lookup"><span data-stu-id="c6b34-148">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="c6b34-149">這通常是因為網路擁塞存在於複雜網路裝置或不良覆蓋 Wi-Fi 區域中的網路擁塞所影響。</span><span class="sxs-lookup"><span data-stu-id="c6b34-149">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span> <span data-ttu-id="c6b34-150">下載速度是以每秒 mb 為單位，大約一十分之一每秒額定百萬位元的電路。</span><span class="sxs-lookup"><span data-stu-id="c6b34-150">The download speed is measured in megabytes per second which is approximately one tenth of a circuits rated megabits per second.</span></span> <span data-ttu-id="c6b34-151">第25個百分點值 (也稱為 P25 量值，) 是針對前三天的所有度量所取。</span><span class="sxs-lookup"><span data-stu-id="c6b34-151">The 25th percentile (also known as the P25 measure) is taken for all measurements over the previous three days.</span></span>

<span data-ttu-id="c6b34-152">使用下表進行 SharePoint 線上評估。</span><span class="sxs-lookup"><span data-stu-id="c6b34-152">The SharePoint Online assessment is made using the following table.</span></span> <span data-ttu-id="c6b34-153">在頻帶中以線性方式指派閾值之間的任何下載速度。</span><span class="sxs-lookup"><span data-stu-id="c6b34-153">Any download speed number between the thresholds are assigned points linearly within the band.</span></span>

| <span data-ttu-id="c6b34-154">下載速度</span><span class="sxs-lookup"><span data-stu-id="c6b34-154">Download speed</span></span> | <span data-ttu-id="c6b34-155">點</span><span class="sxs-lookup"><span data-stu-id="c6b34-155">Points</span></span> |
| :------------- | :----- |
| <span data-ttu-id="c6b34-156">20MBps 或更多</span><span class="sxs-lookup"><span data-stu-id="c6b34-156">20MBps or more</span></span> | <span data-ttu-id="c6b34-157">100</span><span class="sxs-lookup"><span data-stu-id="c6b34-157">100</span></span>    |
| <span data-ttu-id="c6b34-158">14MBps</span><span class="sxs-lookup"><span data-stu-id="c6b34-158">14MBps</span></span>         | <span data-ttu-id="c6b34-159">80</span><span class="sxs-lookup"><span data-stu-id="c6b34-159">80</span></span>     |
| <span data-ttu-id="c6b34-160">8MBps</span><span class="sxs-lookup"><span data-stu-id="c6b34-160">8MBps</span></span>          | <span data-ttu-id="c6b34-161">60</span><span class="sxs-lookup"><span data-stu-id="c6b34-161">60</span></span>     |
| <span data-ttu-id="c6b34-162">4MBps</span><span class="sxs-lookup"><span data-stu-id="c6b34-162">4MBps</span></span>          | <span data-ttu-id="c6b34-163">40</span><span class="sxs-lookup"><span data-stu-id="c6b34-163">40</span></span>     |
| <span data-ttu-id="c6b34-164">2MBps</span><span class="sxs-lookup"><span data-stu-id="c6b34-164">2MBps</span></span>          | <span data-ttu-id="c6b34-165">共</span><span class="sxs-lookup"><span data-stu-id="c6b34-165">20</span></span>     |
| <span data-ttu-id="c6b34-166">0MBps</span><span class="sxs-lookup"><span data-stu-id="c6b34-166">0MBps</span></span>          | <span data-ttu-id="c6b34-167">0</span><span class="sxs-lookup"><span data-stu-id="c6b34-167">0</span></span>      |

## <a name="microsoft-teams"></a><span data-ttu-id="c6b34-168">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6b34-168">Microsoft Teams</span></span>

<span data-ttu-id="c6b34-169">針對 Microsoft 小組，網路品質是指 UDP 延遲、UDP 抖動及 UDP 封包遺失。</span><span class="sxs-lookup"><span data-stu-id="c6b34-169">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="c6b34-170">UDP 可用於 Microsoft 小組的通話和會議音訊和影片媒體連線。</span><span class="sxs-lookup"><span data-stu-id="c6b34-170">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="c6b34-171">這可能會受到延遲和下載速度相同的因素所影響，除了 UDP 是分別設定為較為常見的 TCP 通訊協定以外，其他情況也是在網路的 UDP 支援中使用網路中斷性。</span><span class="sxs-lookup"><span data-stu-id="c6b34-171">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span> <span data-ttu-id="c6b34-172">中間的 (也稱為第50個百分點值或 P50 量值，) 是針對前三天的所有度量所取。</span><span class="sxs-lookup"><span data-stu-id="c6b34-172">The median (also known as the 50th percentile or P50 measure) is taken for all measurements over the previous three days.</span></span> 

<span data-ttu-id="c6b34-173">Microsoft 小組評估是使用下表進行。</span><span class="sxs-lookup"><span data-stu-id="c6b34-173">The Microsoft Teams assessment is made using the following table.</span></span> <span data-ttu-id="c6b34-174">所有三個 UDP 測量值都必須超過所列的臨界值，以達到顯示的點數。</span><span class="sxs-lookup"><span data-stu-id="c6b34-174">All three of the UDP measurements must be above the threshold listed to achieve the points shown.</span></span> <span data-ttu-id="c6b34-175">在頻帶內沒有任何單一位置的評估。</span><span class="sxs-lookup"><span data-stu-id="c6b34-175">There are no assessments for a single location within a band.</span></span>

| <span data-ttu-id="c6b34-176">UDP 封包遺失</span><span class="sxs-lookup"><span data-stu-id="c6b34-176">UDP packet loss</span></span> | <span data-ttu-id="c6b34-177">UDP 延遲</span><span class="sxs-lookup"><span data-stu-id="c6b34-177">UDP latency</span></span> | <span data-ttu-id="c6b34-178">UDP 抖動</span><span class="sxs-lookup"><span data-stu-id="c6b34-178">UDP jitter</span></span> | <span data-ttu-id="c6b34-179">點</span><span class="sxs-lookup"><span data-stu-id="c6b34-179">Points</span></span> |
| :-------------- | :---------- | :--------- | :----- |
| <span data-ttu-id="c6b34-180">0.25%</span><span class="sxs-lookup"><span data-stu-id="c6b34-180">0.25%</span></span>           | <span data-ttu-id="c6b34-181">60ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-181">60ms</span></span>        | <span data-ttu-id="c6b34-182">15ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-182">15ms</span></span>       | <span data-ttu-id="c6b34-183">100</span><span class="sxs-lookup"><span data-stu-id="c6b34-183">100</span></span>    |
| <span data-ttu-id="c6b34-184">1.00%</span><span class="sxs-lookup"><span data-stu-id="c6b34-184">1.00%</span></span>           | <span data-ttu-id="c6b34-185">120ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-185">120ms</span></span>       | <span data-ttu-id="c6b34-186">40ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-186">40ms</span></span>       | <span data-ttu-id="c6b34-187">80</span><span class="sxs-lookup"><span data-stu-id="c6b34-187">80</span></span>     |
| <span data-ttu-id="c6b34-188">1.50%</span><span class="sxs-lookup"><span data-stu-id="c6b34-188">1.50%</span></span>           | <span data-ttu-id="c6b34-189">240ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-189">240ms</span></span>       | <span data-ttu-id="c6b34-190">65ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-190">65ms</span></span>       | <span data-ttu-id="c6b34-191">60</span><span class="sxs-lookup"><span data-stu-id="c6b34-191">60</span></span>     |
| <span data-ttu-id="c6b34-192">3.00%</span><span class="sxs-lookup"><span data-stu-id="c6b34-192">3.00%</span></span>           | <span data-ttu-id="c6b34-193">275ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-193">275ms</span></span>       | <span data-ttu-id="c6b34-194">80ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-194">80ms</span></span>       | <span data-ttu-id="c6b34-195">40</span><span class="sxs-lookup"><span data-stu-id="c6b34-195">40</span></span>     |
| <span data-ttu-id="c6b34-196">5.00%</span><span class="sxs-lookup"><span data-stu-id="c6b34-196">5.00%</span></span>           | <span data-ttu-id="c6b34-197">350ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-197">350ms</span></span>       | <span data-ttu-id="c6b34-198">150ms</span><span class="sxs-lookup"><span data-stu-id="c6b34-198">150ms</span></span>      | <span data-ttu-id="c6b34-199">共</span><span class="sxs-lookup"><span data-stu-id="c6b34-199">20</span></span>     |
| <span data-ttu-id="c6b34-200">任何較高</span><span class="sxs-lookup"><span data-stu-id="c6b34-200">Any higher</span></span>      | <span data-ttu-id="c6b34-201">任何較高</span><span class="sxs-lookup"><span data-stu-id="c6b34-201">Any higher</span></span>  | <span data-ttu-id="c6b34-202">任何較高</span><span class="sxs-lookup"><span data-stu-id="c6b34-202">Any higher</span></span> | <span data-ttu-id="c6b34-203">0</span><span class="sxs-lookup"><span data-stu-id="c6b34-203">0</span></span>      |

## <a name="related-topics"></a><span data-ttu-id="c6b34-204">相關主題</span><span class="sxs-lookup"><span data-stu-id="c6b34-204">Related topics</span></span>

[<span data-ttu-id="c6b34-205">Microsoft 365 系統管理中心的網路效能建議 (預覽) </span><span class="sxs-lookup"><span data-stu-id="c6b34-205">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="c6b34-206">Microsoft 365 網路效能深入 (預覽) </span><span class="sxs-lookup"><span data-stu-id="c6b34-206">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="c6b34-207">Microsoft 365 connectivity test in M365 Admin Center (預覽) </span><span class="sxs-lookup"><span data-stu-id="c6b34-207">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="c6b34-208">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="c6b34-208">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
