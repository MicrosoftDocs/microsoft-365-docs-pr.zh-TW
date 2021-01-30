---
title: 'Microsoft 365 網路洞察力 (預覽) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
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
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055470"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="a9730-103">Microsoft 365 網路洞察力 (預覽) </span><span class="sxs-lookup"><span data-stu-id="a9730-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="a9730-104">**網路洞察力** 是從您的 Microsoft 365 租使用者收集到的效能度量，而且只能在您的租使用者中查看其管理使用者。</span><span class="sxs-lookup"><span data-stu-id="a9730-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="a9730-105">Insights 會顯示在 Microsoft 365 系統管理中心中 <https://portal.microsoft.com/adminportal/home#/networkperformance> 。</span><span class="sxs-lookup"><span data-stu-id="a9730-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="a9730-106">深入瞭解有助於為您的辦公室位置設計網路週邊。</span><span class="sxs-lookup"><span data-stu-id="a9730-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="a9730-107">每個真知灼見都會針對使用者存取租使用者時，針對每個地理位置的特定一般問題，提供有關效能特性的實際詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a9730-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="a9730-108">每個辦公室位置都可能顯示六個特定的網路洞察力：</span><span class="sxs-lookup"><span data-stu-id="a9730-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="a9730-109">Backhauled 網路出局</span><span class="sxs-lookup"><span data-stu-id="a9730-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="a9730-110">網路仲介裝置</span><span class="sxs-lookup"><span data-stu-id="a9730-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="a9730-111">接近您的客戶，偵測到更佳效能</span><span class="sxs-lookup"><span data-stu-id="a9730-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="a9730-112">使用非最優 Exchange Online 服務前門</span><span class="sxs-lookup"><span data-stu-id="a9730-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="a9730-113">使用非最佳的 SharePoint 線上服務前門</span><span class="sxs-lookup"><span data-stu-id="a9730-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="a9730-114">從 SharePoint 前門開始的低下載速度</span><span class="sxs-lookup"><span data-stu-id="a9730-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="a9730-115">中國使用者最佳網路出口</span><span class="sxs-lookup"><span data-stu-id="a9730-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="a9730-116">租使用者可能會顯示兩個租使用者層級的網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="a9730-117">這些也會出現在 [producvitivy 分數] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="a9730-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="a9730-118">Exchange 抽樣連接問題影響的連線</span><span class="sxs-lookup"><span data-stu-id="a9730-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="a9730-119">受連線問題影響的 SharePoint 採樣連接</span><span class="sxs-lookup"><span data-stu-id="a9730-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="a9730-120">Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="a9730-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="a9730-121">Backhauled 網路出局</span><span class="sxs-lookup"><span data-stu-id="a9730-121">Backhauled network egress</span></span>

<span data-ttu-id="a9730-122">如果網路洞察力服務偵測到網路出局的指定使用者位置的距離超過500英里 (800 公里) ，表示 Microsoft 365 流量正 backhauled 至一般的 Internet edge 裝置或 proxy，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="a9730-123">在某些摘要視圖中，此深入瞭解是所謂的「出局」。</span><span class="sxs-lookup"><span data-stu-id="a9730-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled 網路出局](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-125">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-125">What does this mean?</span></span>

<span data-ttu-id="a9730-126">這表示辦公室地點和網路出局之間的距離為500英里 (800 公里) 。</span><span class="sxs-lookup"><span data-stu-id="a9730-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="a9730-127">Office 位置是由經過模糊處理的用戶端機器位置所識別，網路出局位置是透過對位置資料庫使用反向 IP 位址識別。</span><span class="sxs-lookup"><span data-stu-id="a9730-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="a9730-128">如果電腦上的 Windows 位置服務停用，則 office 位置可能不准確。</span><span class="sxs-lookup"><span data-stu-id="a9730-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="a9730-129">如果反向 IP 位址資料庫資訊不正確，網路出局位置可能不准確。</span><span class="sxs-lookup"><span data-stu-id="a9730-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="a9730-130">此深入瞭解的詳細資料包括辦公室位置、預估的承租人使用者總數、目前的網路出局位置、出局位置的相關性、位置與目前的出局點之間的距離、第一次偵測條件的日期，以及解決條件的日期。</span><span class="sxs-lookup"><span data-stu-id="a9730-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-131">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-131">What should I do?</span></span>

<span data-ttu-id="a9730-132">針對這種觀點，我們建議網路出口離辦公室位置更近，讓連線可以最佳路由傳送至 Microsoft 的全域網路和最接近的 Microsoft 365 服務前端門。</span><span class="sxs-lookup"><span data-stu-id="a9730-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="a9730-133">將網路出口關閉至使用者的 office 位置也可讓您日後提高效能，因為 Microsoft 會在未來的網路點擴充目前狀態和 Microsoft 365 服務前門。</span><span class="sxs-lookup"><span data-stu-id="a9730-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="a9730-134">如需如何解決此問題的詳細資訊，請參閱[Office 365 網路連線原則](microsoft-365-network-connectivity-principles.md)中[本機的出局網路](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)連線。</span><span class="sxs-lookup"><span data-stu-id="a9730-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="a9730-135">網路仲介裝置</span><span class="sxs-lookup"><span data-stu-id="a9730-135">Network intermediary device</span></span>

<span data-ttu-id="a9730-136">如果我們在您的使用者和 Microsoft 網路之間偵測到可能會影響 Office 365 使用者體驗的裝置，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="a9730-137">針對 Microsoft 資料中心目的地的特定 Microsoft 365 網路流量，建議略過這些功能。</span><span class="sxs-lookup"><span data-stu-id="a9730-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="a9730-138">[Microsoft 365 網路連線原則](microsoft-365-network-connectivity-principles.md)中也會另外說明此建議</span><span class="sxs-lookup"><span data-stu-id="a9730-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-139">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-139">What does this mean?</span></span>

<span data-ttu-id="a9730-140">網路仲介裝置（例如 proxy 伺服器、Vpn 及資料遺失防護裝置）可能會影響 intermediated 流量的 Microsoft 365 用戶端效能和穩定性。</span><span class="sxs-lookup"><span data-stu-id="a9730-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-141">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-141">What should I do?</span></span>

<span data-ttu-id="a9730-142">將偵測到的網路仲介裝置設定為略過處理 Microsoft 365 網路流量。</span><span class="sxs-lookup"><span data-stu-id="a9730-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="a9730-143">接近您的客戶，偵測到更佳效能</span><span class="sxs-lookup"><span data-stu-id="a9730-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="a9730-144">如果網路洞察力服務偵測到大量客戶在您的組織中，其效能低於組織中的使用者，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="a9730-145">在某些摘要視圖中，此深入瞭解是 "對等" 的縮寫。</span><span class="sxs-lookup"><span data-stu-id="a9730-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![相對網路效能](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-147">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-147">What does this mean?</span></span>

<span data-ttu-id="a9730-148">這項洞察力會檢查與此辦公室位置在相同城市的 Microsoft 365 客戶的匯總效能。</span><span class="sxs-lookup"><span data-stu-id="a9730-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="a9730-149">如果使用者的平均延遲比鄰近承租人的平均延遲高出10%，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-150">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-150">What should I do?</span></span>

<span data-ttu-id="a9730-151">這種情況可能有許多原因，包括公司網路或 ISP、瓶頸或架構設計問題中的延遲。</span><span class="sxs-lookup"><span data-stu-id="a9730-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="a9730-152">檢查您的 office 網路和目前的 Microsoft 365 前端的路由之間，每個躍點之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="a9730-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="a9730-153">如需詳細資訊，請參閱 [Microsoft 365 Network Connectivity 原則](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="a9730-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="a9730-154">使用非最優 Exchange Online 服務前門</span><span class="sxs-lookup"><span data-stu-id="a9730-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="a9730-155">如果網路洞察力服務偵測到特定位置的使用者未連線到最佳 Exchange Online 服務前門，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="a9730-156">在某些摘要視圖中，此深入瞭解是「路由」。</span><span class="sxs-lookup"><span data-stu-id="a9730-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![非最佳 EXO 前門](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-158">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-158">What does this mean?</span></span>

<span data-ttu-id="a9730-159">我們會列出 Exchange Online 服務前門，其適用于 office 位置的城市，具有良好的效能。</span><span class="sxs-lookup"><span data-stu-id="a9730-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="a9730-160">如果目前的測試顯示使用此清單上的 Exchange Online service front 前門，請致電此建議。</span><span class="sxs-lookup"><span data-stu-id="a9730-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-161">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-161">What should I do?</span></span>

<span data-ttu-id="a9730-162">使用非最優 Exchange Online 服務前門可能是由網路 backhaul 在公司網路出口之前所造成，因此我們建議您在本機和直接的網路出口。</span><span class="sxs-lookup"><span data-stu-id="a9730-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="a9730-163">這種情況也可能是使用遠端 DNS 遞迴解析伺服器所造成，在此情況下，我們建議您將 DNS 遞迴解析程式伺服器與網路出局對齊。</span><span class="sxs-lookup"><span data-stu-id="a9730-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="a9730-164">使用非最佳的 SharePoint 線上服務前門</span><span class="sxs-lookup"><span data-stu-id="a9730-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="a9730-165">如果網路洞察力服務偵測到特定位置的使用者未連接到最接近的 SharePoint 線上服務前門，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="a9730-166">在某些摘要視圖中，此真知灼見是縮寫為 "Afd"。</span><span class="sxs-lookup"><span data-stu-id="a9730-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![非最佳 SPO 前門](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-168">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-168">What does this mean?</span></span>

<span data-ttu-id="a9730-169">我們識別測試用戶端所連接的 SharePoint 線上服務前門。</span><span class="sxs-lookup"><span data-stu-id="a9730-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="a9730-170">然後，我們會比較該城市的預期 SharePoint Online 服務前門。</span><span class="sxs-lookup"><span data-stu-id="a9730-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="a9730-171">如果不相符，則建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="a9730-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-172">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-172">What should I do?</span></span>

<span data-ttu-id="a9730-173">使用非最佳的 SharePoint 線上服務前門可能是由網路 backhaul 在公司網路出口之前所造成，我們建議您在本機和直接的網路出口。</span><span class="sxs-lookup"><span data-stu-id="a9730-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="a9730-174">這種情況也可能是使用遠端 DNS 遞迴解析伺服器所造成，在此情況下，我們建議您將 DNS 遞迴解析程式伺服器與網路出局對齊。</span><span class="sxs-lookup"><span data-stu-id="a9730-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="a9730-175">從 SharePoint 前門開始的低下載速度</span><span class="sxs-lookup"><span data-stu-id="a9730-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="a9730-176">如果網路洞察力服務偵測到特定辦公室位置和 SharePoint 線上之間的頻寬低於 1 MBps，就會顯示這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="a9730-177">在某些摘要視圖中，此深入瞭解是以「輸送量」做為縮寫。</span><span class="sxs-lookup"><span data-stu-id="a9730-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-178">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-178">What does this mean?</span></span>

<span data-ttu-id="a9730-179">使用者可以從 SharePoint Online 和 OneDrive 商務服務前端取得的下載速度，以每秒 mb 為單位， (Mbits) 。</span><span class="sxs-lookup"><span data-stu-id="a9730-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="a9730-180">如果此值小於 1 MBps，我們就會提供這種洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-181">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-181">What should I do?</span></span>

<span data-ttu-id="a9730-182">若要改善下載速度，可能需要增加頻寬。</span><span class="sxs-lookup"><span data-stu-id="a9730-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="a9730-183">或者，在辦公室地點的使用者機器與 SharePoint 線上服務前門之間可能有網路擁塞。</span><span class="sxs-lookup"><span data-stu-id="a9730-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="a9730-184">這有時稱為 congestive 遺失，它會限制使用者可以使用的下載速度，即使有足夠的頻寬可供使用。</span><span class="sxs-lookup"><span data-stu-id="a9730-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="a9730-185">中國使用者最佳網路出口</span><span class="sxs-lookup"><span data-stu-id="a9730-185">China user optimal network egress</span></span>

<span data-ttu-id="a9730-186">如果貴組織的使用者在中國連接至您的 Microsoft 365 租使用者至其他地理位置，就會顯示這項洞察力。</span><span class="sxs-lookup"><span data-stu-id="a9730-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-187">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-187">What does this mean?</span></span>

<span data-ttu-id="a9730-188">如果您的組織具備私人 WAN 連線能力，我們建議您在中國的 office 位置，設定網路 WAN 電路，在下列任何位置都有網路出口給網際網路：</span><span class="sxs-lookup"><span data-stu-id="a9730-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="a9730-189">香港</span><span class="sxs-lookup"><span data-stu-id="a9730-189">Hong Kong</span></span>
- <span data-ttu-id="a9730-190">日本</span><span class="sxs-lookup"><span data-stu-id="a9730-190">Japan</span></span>
- <span data-ttu-id="a9730-191">台灣</span><span class="sxs-lookup"><span data-stu-id="a9730-191">Taiwan</span></span>
- <span data-ttu-id="a9730-192">韓國</span><span class="sxs-lookup"><span data-stu-id="a9730-192">South Korea</span></span>
- <span data-ttu-id="a9730-193">新加坡</span><span class="sxs-lookup"><span data-stu-id="a9730-193">Singapore</span></span>
- <span data-ttu-id="a9730-194">馬來西亞</span><span class="sxs-lookup"><span data-stu-id="a9730-194">Malaysia</span></span>

<span data-ttu-id="a9730-195">來自于這些位置以外之使用者的網際網路出口會降低效能，而在中國內出口的情況可能會因為邊界堵塞而導致高延遲和連線問題。</span><span class="sxs-lookup"><span data-stu-id="a9730-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-196">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-196">What should I do?</span></span>

<span data-ttu-id="a9730-197">如需如何減輕與此洞察力相關之效能問題的詳細資訊，請參閱 [適用于中國使用者的 Microsoft 365 全域承租人效能優化](microsoft-365-networking-china.md)。</span><span class="sxs-lookup"><span data-stu-id="a9730-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="a9730-198">Exchange 抽樣連接問題影響的連線</span><span class="sxs-lookup"><span data-stu-id="a9730-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="a9730-199">這種洞察力會顯示何時會影響50% 或更多的抽樣連線。</span><span class="sxs-lookup"><span data-stu-id="a9730-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="a9730-200">每個範例的 Exchange 評估為低於60% 的 Exchange 評估所定義的影響。</span><span class="sxs-lookup"><span data-stu-id="a9730-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-201">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-201">What does this mean?</span></span>

<span data-ttu-id="a9730-202">這表示大多數的使用者可能會在連線至 Exchange Online 的 Outlook 中遇到使用者經驗問題。</span><span class="sxs-lookup"><span data-stu-id="a9730-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="a9730-203">樣本百分比可能代表顯示低於60點的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="a9730-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-204">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-204">What should I do?</span></span>

<span data-ttu-id="a9730-205">若尚未啟用 office 位置網路連線，請啟用。</span><span class="sxs-lookup"><span data-stu-id="a9730-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="a9730-206">您想要找出影響 Exchange 的網路連線不良影響哪些分支機搆，並尋找將使用者連線至 Microsoft 網路的方法，以改善網路周邊網路的速度。</span><span class="sxs-lookup"><span data-stu-id="a9730-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="a9730-207">受連線問題影響的 SharePoint 採樣連接</span><span class="sxs-lookup"><span data-stu-id="a9730-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="a9730-208">這種洞察力會顯示何時會影響50% 或更多的抽樣連線。</span><span class="sxs-lookup"><span data-stu-id="a9730-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="a9730-209">每個範例的 SharePoint 評估所定義的影響低於40%。</span><span class="sxs-lookup"><span data-stu-id="a9730-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="a9730-210">案例</span><span class="sxs-lookup"><span data-stu-id="a9730-210">What does this mean?</span></span>

<span data-ttu-id="a9730-211">這表示大多數的使用者可能會遇到 SharePoint 和 OneDrive 的使用者經驗問題。</span><span class="sxs-lookup"><span data-stu-id="a9730-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="a9730-212">樣本百分比可能代表顯示低於40點的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="a9730-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="a9730-213">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="a9730-213">What should I do?</span></span>

<span data-ttu-id="a9730-214">若尚未啟用 office 位置網路連線，請啟用。</span><span class="sxs-lookup"><span data-stu-id="a9730-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="a9730-215">您想要找出會影響 SharePoint 不良網路連線的分支，並尋找一種方法，以將使用者連接至 Microsoft 的網路，以提升網路周邊網路的能力。</span><span class="sxs-lookup"><span data-stu-id="a9730-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9730-216">相關主題</span><span class="sxs-lookup"><span data-stu-id="a9730-216">Related topics</span></span>

[<span data-ttu-id="a9730-217">Microsoft 365 系統管理中心的網路連線 (預覽) </span><span class="sxs-lookup"><span data-stu-id="a9730-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="a9730-218">Microsoft 365 網路評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="a9730-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="a9730-219">Microsoft 365 network connectivity test 工具 (預覽) </span><span class="sxs-lookup"><span data-stu-id="a9730-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="a9730-220">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="a9730-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
