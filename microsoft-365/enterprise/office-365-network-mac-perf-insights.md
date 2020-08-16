---
title: 'Microsoft 365 網路洞察力 (預覽) '
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
description: 'Microsoft 365 網路洞察力 (預覽) '
ms.openlocfilehash: b30af89d480383fdc9011d24409e3b418339c70b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688539"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="ad0de-103">Microsoft 365 網路洞察力 (預覽) </span><span class="sxs-lookup"><span data-stu-id="ad0de-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="ad0de-104">**網路洞察力** 是從您的 Microsoft 365 租使用者收集到的即時效能計量，而且只能在您的租使用者中查看其管理使用者。</span><span class="sxs-lookup"><span data-stu-id="ad0de-104">**Network insights** are live performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="ad0de-105">Insights 會顯示在 Microsoft 365 系統管理中心中 <https://portal.microsoft.com/adminportal/home#/networkperformance> 。</span><span class="sxs-lookup"><span data-stu-id="ad0de-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="ad0de-106">深入瞭解有助於為您的辦公室位置設計網路週邊。</span><span class="sxs-lookup"><span data-stu-id="ad0de-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="ad0de-107">每個真知灼見都會針對使用者存取租使用者時，針對每個地理位置的特定一般問題，提供有關效能特性的實際詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ad0de-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="ad0de-108">每個辦公室位置可能會顯示五個特定的網路洞察力：</span><span class="sxs-lookup"><span data-stu-id="ad0de-108">There are five specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="ad0de-109">Backhauled 網路出局</span><span class="sxs-lookup"><span data-stu-id="ad0de-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="ad0de-110">接近您的客戶，偵測到更佳效能</span><span class="sxs-lookup"><span data-stu-id="ad0de-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="ad0de-111">使用非最優 Exchange Online 服務前門</span><span class="sxs-lookup"><span data-stu-id="ad0de-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="ad0de-112">使用非最佳的 SharePoint 線上服務前門</span><span class="sxs-lookup"><span data-stu-id="ad0de-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="ad0de-113">從 SharePoint 前門開始的低下載速度</span><span class="sxs-lookup"><span data-stu-id="ad0de-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)

>[!IMPORTANT]
><span data-ttu-id="ad0de-114">Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="ad0de-114">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="ad0de-115">Backhauled 網路出局</span><span class="sxs-lookup"><span data-stu-id="ad0de-115">Backhauled network egress</span></span>

<span data-ttu-id="ad0de-116">如果網路洞察力服務偵測到網路出局的指定使用者位置的距離超過500英里 (800 公里) ，表示 Microsoft 365 流量正 backhauled 至一般的 Internet edge 裝置或 proxy，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-116">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="ad0de-117">在某些摘要視圖中，此深入瞭解是所謂的「出局」。</span><span class="sxs-lookup"><span data-stu-id="ad0de-117">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled 網路出局](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ad0de-119">案例</span><span class="sxs-lookup"><span data-stu-id="ad0de-119">What does this mean?</span></span>

<span data-ttu-id="ad0de-120">這表示辦公室地點和網路出局之間的距離為500英里 (800 公里) 。</span><span class="sxs-lookup"><span data-stu-id="ad0de-120">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="ad0de-121">Office 位置是由經過模糊處理的用戶端機器位置所識別，網路出局位置是透過對位置資料庫使用反向 IP 位址識別。</span><span class="sxs-lookup"><span data-stu-id="ad0de-121">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="ad0de-122">如果電腦上的 Windows 位置服務停用，則 office 位置可能不准確。</span><span class="sxs-lookup"><span data-stu-id="ad0de-122">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="ad0de-123">如果反向 IP 位址資料庫資訊不正確，網路出局位置可能不准確。</span><span class="sxs-lookup"><span data-stu-id="ad0de-123">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="ad0de-124">此深入瞭解的詳細資料包括辦公室位置、預估的承租人使用者總數、目前的網路出局位置、出局位置的相關性、位置與目前的出局點之間的距離、第一次偵測條件的日期，以及解決條件的日期。</span><span class="sxs-lookup"><span data-stu-id="ad0de-124">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ad0de-125">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="ad0de-125">What should I do?</span></span>

<span data-ttu-id="ad0de-126">針對這種觀點，我們建議網路出口離辦公室位置更近，讓連線可以最佳路由傳送至 Microsoft 的全域網路和最接近的 Microsoft 365 服務前端門。</span><span class="sxs-lookup"><span data-stu-id="ad0de-126">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="ad0de-127">將網路出口關閉至使用者的 office 位置也可讓您日後提高效能，因為 Microsoft 會在未來的網路點擴充目前狀態和 Microsoft 365 服務前門。</span><span class="sxs-lookup"><span data-stu-id="ad0de-127">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="ad0de-128">如需如何解決此問題的詳細資訊，請參閱[Office 365 網路連線原則](microsoft-365-network-connectivity-principles.md)中[本機的出局網路](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)連線。</span><span class="sxs-lookup"><span data-stu-id="ad0de-128">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="ad0de-129">接近您的客戶，偵測到更佳效能</span><span class="sxs-lookup"><span data-stu-id="ad0de-129">Better performance detected for customers near you</span></span>

<span data-ttu-id="ad0de-130">如果網路洞察力服務偵測到大量客戶在您的組織中，其效能低於組織中的使用者，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-130">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="ad0de-131">在某些摘要視圖中，此深入瞭解是 "對等" 的縮寫。</span><span class="sxs-lookup"><span data-stu-id="ad0de-131">This insight is abbreviated as "Peers" in some summary views.</span></span>

![相對網路效能](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ad0de-133">案例</span><span class="sxs-lookup"><span data-stu-id="ad0de-133">What does this mean?</span></span>

<span data-ttu-id="ad0de-134">這項洞察力會檢查與此辦公室位置在相同城市的 Microsoft 365 客戶的匯總效能。</span><span class="sxs-lookup"><span data-stu-id="ad0de-134">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="ad0de-135">如果使用者的平均延遲比鄰近承租人的平均延遲高出10%，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-135">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ad0de-136">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="ad0de-136">What should I do?</span></span>

<span data-ttu-id="ad0de-137">這種情況可能有許多原因，包括公司網路或 ISP、瓶頸或架構設計問題中的延遲。</span><span class="sxs-lookup"><span data-stu-id="ad0de-137">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="ad0de-138">檢查您的 office 網路和目前的 Microsoft 365 前端的路由之間，每個躍點之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="ad0de-138">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="ad0de-139">如需詳細資訊，請參閱 [Office 365 Network Connectivity 原則](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="ad0de-139">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="ad0de-140">使用非最優 Exchange Online 服務前門</span><span class="sxs-lookup"><span data-stu-id="ad0de-140">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="ad0de-141">如果網路洞察力服務偵測到特定位置的使用者未連線到最佳 Exchange Online 服務前門，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-141">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="ad0de-142">在某些摘要視圖中，此深入瞭解是「路由」。</span><span class="sxs-lookup"><span data-stu-id="ad0de-142">This insight is abbreviated as "Routing" in some summary views.</span></span>

![非最優前門](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ad0de-144">案例</span><span class="sxs-lookup"><span data-stu-id="ad0de-144">What does this mean?</span></span>

<span data-ttu-id="ad0de-145">我們會列出 Exchange Online 服務前門，其適用于 office 位置的城市，具有良好的效能。</span><span class="sxs-lookup"><span data-stu-id="ad0de-145">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="ad0de-146">如果目前的測試顯示使用此清單上的 Exchange Online service front 前門，請致電此建議。</span><span class="sxs-lookup"><span data-stu-id="ad0de-146">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ad0de-147">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="ad0de-147">What should I do?</span></span>

<span data-ttu-id="ad0de-148">使用非最優 Exchange Online 服務前門可能是由網路 backhaul 在公司網路出口之前所造成，因此我們建議您在本機和直接的網路出口。</span><span class="sxs-lookup"><span data-stu-id="ad0de-148">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ad0de-149">這種情況也可能是使用遠端 DNS 遞迴解析伺服器所造成，在此情況下，我們建議您將 DNS 遞迴解析程式伺服器與網路出局對齊。</span><span class="sxs-lookup"><span data-stu-id="ad0de-149">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="ad0de-150">使用非最佳的 SharePoint 線上服務前門</span><span class="sxs-lookup"><span data-stu-id="ad0de-150">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="ad0de-151">如果網路洞察力服務偵測到特定位置的使用者未連接到最接近的 SharePoint 線上服務前門，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-151">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="ad0de-152">在某些摘要視圖中，此真知灼見是縮寫為 "Afd"。</span><span class="sxs-lookup"><span data-stu-id="ad0de-152">This insight is abbreviated as "Afd" in some summary views.</span></span>

![非最優前門](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ad0de-154">案例</span><span class="sxs-lookup"><span data-stu-id="ad0de-154">What does this mean?</span></span>

<span data-ttu-id="ad0de-155">我們識別測試用戶端所連接的 SharePoint 線上服務前門。</span><span class="sxs-lookup"><span data-stu-id="ad0de-155">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="ad0de-156">然後，我們會比較該城市的預期 SharePoint Online 服務前門。</span><span class="sxs-lookup"><span data-stu-id="ad0de-156">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="ad0de-157">如果不相符，則建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="ad0de-157">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ad0de-158">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="ad0de-158">What should I do?</span></span>

<span data-ttu-id="ad0de-159">使用非最佳的 SharePoint 線上服務前門可能是由網路 backhaul 在公司網路出口之前所造成，我們建議您在本機和直接的網路出口。</span><span class="sxs-lookup"><span data-stu-id="ad0de-159">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ad0de-160">這種情況也可能是使用遠端 DNS 遞迴解析伺服器所造成，在此情況下，我們建議您將 DNS 遞迴解析程式伺服器與網路出局對齊。</span><span class="sxs-lookup"><span data-stu-id="ad0de-160">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="ad0de-161">從 SharePoint 前門開始的低下載速度</span><span class="sxs-lookup"><span data-stu-id="ad0de-161">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="ad0de-162">如果網路洞察力服務偵測到特定辦公室位置和 SharePoint 線上之間的頻寬低於 1 MBps，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-162">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="ad0de-163">在某些摘要視圖中，此深入瞭解是以「輸送量」做為縮寫。</span><span class="sxs-lookup"><span data-stu-id="ad0de-163">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ad0de-164">案例</span><span class="sxs-lookup"><span data-stu-id="ad0de-164">What does this mean?</span></span>

<span data-ttu-id="ad0de-165">使用者可以從 SharePoint Online 和 OneDrive 商務服務前端取得的下載速度，以每秒 mb 為單位， (Mbits) 。</span><span class="sxs-lookup"><span data-stu-id="ad0de-165">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="ad0de-166">如果此值小於 1 MBps，我們就會提供這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-166">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ad0de-167">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="ad0de-167">What should I do?</span></span>

<span data-ttu-id="ad0de-168">若要改善下載速度，可能需要增加頻寬。</span><span class="sxs-lookup"><span data-stu-id="ad0de-168">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="ad0de-169">或者，在辦公室地點的使用者機器與 SharePoint 線上服務前門之間可能有網路擁塞。</span><span class="sxs-lookup"><span data-stu-id="ad0de-169">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="ad0de-170">這有時稱為 congestive 遺失，它會限制使用者可以使用的下載速度，即使有足夠的頻寬可供使用。</span><span class="sxs-lookup"><span data-stu-id="ad0de-170">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="ad0de-171">中國使用者最佳網路出口</span><span class="sxs-lookup"><span data-stu-id="ad0de-171">China user optimal network egress</span></span>

<span data-ttu-id="ad0de-172">如果貴組織的使用者在中國連接至您的 Microsoft 365 租使用者至其他地理位置，就會顯示這項洞察力。</span><span class="sxs-lookup"><span data-stu-id="ad0de-172">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="ad0de-173">案例</span><span class="sxs-lookup"><span data-stu-id="ad0de-173">What does this mean?</span></span>

<span data-ttu-id="ad0de-174">如果您的組織具備私人 WAN 連線能力，我們建議您在中國的 office 位置，設定網路 WAN 電路，在下列任何位置都有網路出口給網際網路：</span><span class="sxs-lookup"><span data-stu-id="ad0de-174">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="ad0de-175">香港</span><span class="sxs-lookup"><span data-stu-id="ad0de-175">Hong Kong</span></span>
- <span data-ttu-id="ad0de-176">日本</span><span class="sxs-lookup"><span data-stu-id="ad0de-176">Japan</span></span>
- <span data-ttu-id="ad0de-177">台灣</span><span class="sxs-lookup"><span data-stu-id="ad0de-177">Taiwan</span></span>
- <span data-ttu-id="ad0de-178">南韓</span><span class="sxs-lookup"><span data-stu-id="ad0de-178">South Korea</span></span>
- <span data-ttu-id="ad0de-179">新加坡</span><span class="sxs-lookup"><span data-stu-id="ad0de-179">Singapore</span></span>
- <span data-ttu-id="ad0de-180">馬來西亞</span><span class="sxs-lookup"><span data-stu-id="ad0de-180">Malaysia</span></span>

<span data-ttu-id="ad0de-181">來自于這些位置以外之使用者的網際網路出口會降低效能，而在中國內出口的情況可能會因為邊界堵塞而導致高延遲和連線問題。</span><span class="sxs-lookup"><span data-stu-id="ad0de-181">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ad0de-182">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="ad0de-182">What should I do?</span></span>

<span data-ttu-id="ad0de-183">如需如何減輕與此洞察力相關之效能問題的詳細資訊，請參閱 [適用于中國使用者的 Office 365 全域承租人效能優化](microsoft-365-networking-china.md)。</span><span class="sxs-lookup"><span data-stu-id="ad0de-183">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad0de-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="ad0de-184">Related topics</span></span>

[<span data-ttu-id="ad0de-185">Microsoft 365 系統管理中心的網路效能建議 (預覽) </span><span class="sxs-lookup"><span data-stu-id="ad0de-185">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="ad0de-186">Microsoft 365 網路評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="ad0de-186">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="ad0de-187">Microsoft 365 connectivity test in M365 Admin Center (預覽) </span><span class="sxs-lookup"><span data-stu-id="ad0de-187">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="ad0de-188">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="ad0de-188">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)