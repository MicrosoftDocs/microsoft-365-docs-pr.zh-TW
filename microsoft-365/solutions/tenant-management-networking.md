---
title: 步驟 2： 適用于企業承租人 Microsoft 365 的最佳網路
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 優化 Microsoft 365 承租人的網路存取。
ms.openlocfilehash: cf9591d2ec027c42f5ef9e7abac6dc9b06744a81
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229176"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="04e80-104">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="04e80-104">Step 2.</span></span> <span data-ttu-id="04e80-105">適用于企業承租人 Microsoft 365 的最佳網路</span><span class="sxs-lookup"><span data-stu-id="04e80-105">Optimal networking for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="04e80-106">適用于企業的 Microsoft 365 包括 Teams 和 Microsoft Intune Exchange Online 等雲端生產力應用程式，以及 Microsoft Azure 的許多身分識別及安全性服務。</span><span class="sxs-lookup"><span data-stu-id="04e80-106">Microsoft 365 for enterprise includes cloud productivity apps such as Teams and Exchange Online, and Microsoft Intune, along with many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="04e80-107">所有這些雲端架構服務的安全性、效能和可靠性都取決於您的內部部署網路上的用戶端裝置和網際網路上的任何位置。</span><span class="sxs-lookup"><span data-stu-id="04e80-107">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices on your on-premises network or any location on the Internet.</span></span> 

<span data-ttu-id="04e80-108">若要優化租使用者的網路存取，您必須：</span><span class="sxs-lookup"><span data-stu-id="04e80-108">To optimize network access for your tenant, you need to:</span></span>

- <span data-ttu-id="04e80-109">將您的內部部署使用者與最接近的位置之間的路徑優化至 Microsoft 全球網路。</span><span class="sxs-lookup"><span data-stu-id="04e80-109">Optimize the path between your on-premises users and the closest location to the Microsoft Global Network.</span></span>
- <span data-ttu-id="04e80-110">針對使用遠端存取 VPN 解決方案的遠端使用者，優化對 Microsoft Global 網路的存取。</span><span class="sxs-lookup"><span data-stu-id="04e80-110">Optimize access to the Microsoft Global Network for your remote users that are using a remote access VPN solution.</span></span>
- <span data-ttu-id="04e80-111">使用 [網路 Insights 設計您的辦公室位置的網路周邊。</span><span class="sxs-lookup"><span data-stu-id="04e80-111">Use Network Insights to design the network perimeter for your office locations.</span></span>
- <span data-ttu-id="04e80-112">使用 Office 365 CDN，優化 SharePoint 網站上主控的特定資產的存取權。</span><span class="sxs-lookup"><span data-stu-id="04e80-112">Optimize access to specific assets hosted on SharePoint sites with the Office 365 CDN.</span></span>
- <span data-ttu-id="04e80-113">設定 proxy 和網路 edge 裝置，以略過使用端點清單的 Microsoft 365 信任流量的處理，並在進行變更時自動更新清單。</span><span class="sxs-lookup"><span data-stu-id="04e80-113">Configure proxy and network edge devices to bypass processing for Microsoft 365 trusted traffic with the list of endpoints and automate the updating of the list as changes are made.</span></span>

## <a name="enterprise-on-premises-workers"></a><span data-ttu-id="04e80-114">Enterprise 內部部署工作者</span><span class="sxs-lookup"><span data-stu-id="04e80-114">Enterprise on-premises workers</span></span>

<span data-ttu-id="04e80-115">針對商業網路，您應該在用戶端和最接近的 Microsoft 365 端點之間啟用最高的網路存取，以優化使用者的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="04e80-115">For enterprise networks, you should optimize the end user experience by enabling the highest-performing network access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="04e80-116">使用者經驗的品質與使用者所使用之應用程式的效能和回應能力直接相關。</span><span class="sxs-lookup"><span data-stu-id="04e80-116">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="04e80-117">例如，Microsoft Teams 取決於低延遲，讓使用者電話通話、會議和共用畫面共同作業都沒有任何無任何問題。</span><span class="sxs-lookup"><span data-stu-id="04e80-117">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free.</span></span>

<span data-ttu-id="04e80-118">網路設計中的主要目標是將用戶端裝置中 (RTT) （從用戶端裝置互連至 Microsoft 全域網路）的來回行程時間減至最少，這是 Microsoft 的公用網路主幹，可將所有的 Microsoft 資料中心互連，以低延遲、高可用性 cloud application 進入點（稱為 front 門窗），以遍佈世界各地。</span><span class="sxs-lookup"><span data-stu-id="04e80-118">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client devices to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points, known as front doors, spread around the world.</span></span>

<span data-ttu-id="04e80-119">以下是傳統商業網路的範例。</span><span class="sxs-lookup"><span data-stu-id="04e80-119">Here is an example of a traditional enterprise network.</span></span>

![具有網際網路的中央存取權的傳統商業網路](../media/tenant-management-overview/tenant-management-networking-traditional.png)

<span data-ttu-id="04e80-121">在此圖中，分支機搆透過 (廣域網路) 裝置和 WAN 主幹來連線至總公司。</span><span class="sxs-lookup"><span data-stu-id="04e80-121">In this illustration, branch offices connect to a central office through wide area network (WAN) devices and a WAN backbone.</span></span> <span data-ttu-id="04e80-122">網際網路存取是透過中央辦公室網路 edge 的安全性或 proxy 裝置，以及網際網路服務提供者 (ISP) 。</span><span class="sxs-lookup"><span data-stu-id="04e80-122">Internet access is through a security or proxy device at the network edge of the central office and an Internet service provider (ISP).</span></span> <span data-ttu-id="04e80-123">在網際網路上，Microsoft 全球網路在世界各地有一系列的前端門。</span><span class="sxs-lookup"><span data-stu-id="04e80-123">On the Internet, the Microsoft Global Network has a series of front doors in regions around the world.</span></span> <span data-ttu-id="04e80-124">組織也可以使用中間位置，以進行額外的封包處理及流量的安全性。</span><span class="sxs-lookup"><span data-stu-id="04e80-124">Organizations can also use intermediate locations for additional packet processing and security for traffic.</span></span> <span data-ttu-id="04e80-125">組織的 Microsoft 365 租使用者位於 Microsoft 全球網路內。</span><span class="sxs-lookup"><span data-stu-id="04e80-125">An organization's Microsoft 365 tenant is located within the Microsoft Global Network.</span></span>

<span data-ttu-id="04e80-126">此設定 Microsoft 365 雲端服務的問題如下：</span><span class="sxs-lookup"><span data-stu-id="04e80-126">The problems with this configuration for Microsoft 365 cloud services are:</span></span>

- <span data-ttu-id="04e80-127">針對分公司中的使用者，流量會傳送至非本機前門，增加延遲。</span><span class="sxs-lookup"><span data-stu-id="04e80-127">For users in branch offices, traffic gets sent to non-local front doors, increasing latency.</span></span>
- <span data-ttu-id="04e80-128">傳送流量到中級位置建立網路 hairpin，以對信任的流量執行重複的封包處理，增加延遲。</span><span class="sxs-lookup"><span data-stu-id="04e80-128">Sending traffic to intermediate locations create network hairpins that perform duplicate packet processing on trusted traffic, increasing latency.</span></span>
- <span data-ttu-id="04e80-129">網路 edge 裝置會在信任的流量上執行不必要和重複的封包處理，增加延遲。</span><span class="sxs-lookup"><span data-stu-id="04e80-129">Network edge devices perform unneeded and duplicate packet processing on trusted traffic, increasing latency.</span></span>

<span data-ttu-id="04e80-130">優化 Microsoft 365 網路效能不需要很複雜。</span><span class="sxs-lookup"><span data-stu-id="04e80-130">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="04e80-131">您可以遵循一些重要的原則，盡可能取得最佳效能：</span><span class="sxs-lookup"><span data-stu-id="04e80-131">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="04e80-132">識別 Microsoft 365 網路流量，這是受信任的流量，也就是目的地至 Microsoft 雲端服務的流量。</span><span class="sxs-lookup"><span data-stu-id="04e80-132">Identify Microsoft 365 network traffic, which is trusted traffic destined to Microsoft cloud services.</span></span>
- <span data-ttu-id="04e80-133">從使用者連線到 Microsoft 365 的每個位置，允許從每個位置的 Microsoft 365 網路流量的本機分支出口。</span><span class="sxs-lookup"><span data-stu-id="04e80-133">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365.</span></span>
- <span data-ttu-id="04e80-134">避免網路 hairpin。</span><span class="sxs-lookup"><span data-stu-id="04e80-134">Avoid network hairpins.</span></span>
- <span data-ttu-id="04e80-135">允許 Microsoft 365 流量略過 proxy 和封包檢查裝置。</span><span class="sxs-lookup"><span data-stu-id="04e80-135">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices.</span></span>

<span data-ttu-id="04e80-136">如果您執行這些原則，則會取得針對 Microsoft 365 優化的商業網路。</span><span class="sxs-lookup"><span data-stu-id="04e80-136">If you implement these principles, you get an enterprise network optimized for Microsoft 365.</span></span>

![優化 Microsoft 365 的商業網路](../media/tenant-management-overview/tenant-management-networking-optimized.png)

<span data-ttu-id="04e80-138">在此圖中，分支機搆會透過軟體定義的 WAN 裝置 (SDWAN) 裝置，將信任的 Microsoft 365 流量傳送至最接近的前端，以進行自己的網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="04e80-138">In this illustration, branch offices have their own Internet connection through a software-defined WAN device (SDWAN) device, which sends trusted Microsoft 365 traffic to the regionally closest front door.</span></span> <span data-ttu-id="04e80-139">在總公司，受信任的 Microsoft 365 流量會略過安全性或 proxy 裝置和中級裝置不再使用。</span><span class="sxs-lookup"><span data-stu-id="04e80-139">At the central office, trusted Microsoft 365 traffic bypasses the security or proxy device and intermediate devices are no longer used.</span></span>

<span data-ttu-id="04e80-140">以下是優化設定如何解決傳統 enterprise 網路的延遲問題：</span><span class="sxs-lookup"><span data-stu-id="04e80-140">Here's are how the optimized configuration solves the latency issues of a traditional enterprise network:</span></span>

- <span data-ttu-id="04e80-141">受信任的 Microsoft 365 流量會跳過 WAN 主幹，並將其傳送給所有辦公室的本機前面的門，以減少延遲。</span><span class="sxs-lookup"><span data-stu-id="04e80-141">Trusted Microsoft 365 traffic skips the WAN backbone and is sent to local front doors for all offices, decreasing latency.</span></span>
- <span data-ttu-id="04e80-142">會略過執行重複封包處理的網路 hairpin，以減少 Microsoft 365 信任的流量，減少延遲。</span><span class="sxs-lookup"><span data-stu-id="04e80-142">Network hairpins that perform duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>
- <span data-ttu-id="04e80-143">會略過執行不必要和重複的封包處理的網路 edge 裝置，以 Microsoft 365 信任的流量，縮短延遲。</span><span class="sxs-lookup"><span data-stu-id="04e80-143">Network edge devices that perform unneeded and duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>

<span data-ttu-id="04e80-144">如需詳細資訊，請參閱[Microsoft 365 網路連通性一覽](../enterprise/microsoft-365-networking-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="04e80-144">For more information, see [Microsoft 365 network connectivity overview](../enterprise/microsoft-365-networking-overview.md).</span></span>

## <a name="remote-workers"></a><span data-ttu-id="04e80-145">遠端工作者</span><span class="sxs-lookup"><span data-stu-id="04e80-145">Remote workers</span></span>

<span data-ttu-id="04e80-146">如果您的遠端工作者使用傳統的 VPN 用戶端取得貴組織網路的遠端存取權，請確認 VPN 用戶端支援分割通道。</span><span class="sxs-lookup"><span data-stu-id="04e80-146">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span> <span data-ttu-id="04e80-147">如果沒有分割通道，您所有的遠端工作流量都會透過 VPN 連線傳送，其中必須先將流量轉送給貴組織的邊緣裝置、進行處理，然後透過網際網路傳送。</span><span class="sxs-lookup"><span data-stu-id="04e80-147">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span> <span data-ttu-id="04e80-148">範例如下。</span><span class="sxs-lookup"><span data-stu-id="04e80-148">Here is an example.</span></span>

![來自 VPN 用戶端的網路流量 (不含通道)](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="04e80-150">在此圖中，Microsoft 365 流量必須透過您的組織採取間接的路由，這可以從 VPN 用戶端的物理位置移至遠的 Microsoft 全球網路前門。</span><span class="sxs-lookup"><span data-stu-id="04e80-150">In this illustration, Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft Global Network front door far away from the VPN client’s physical location.</span></span> <span data-ttu-id="04e80-151">這種間接路徑可增加網路流量的延遲，並降低整體效能。</span><span class="sxs-lookup"><span data-stu-id="04e80-151">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="04e80-152">您可以利用分割通道設定 VPN 用戶端，以排除透過 VPN 連線傳送到組織網路的特定類型流量。</span><span class="sxs-lookup"><span data-stu-id="04e80-152">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="04e80-153">若要將 Microsoft 365 雲端資源的存取最佳化，請設定分割通道 VPN 用戶端，排除透過 VPN 連線到 **最佳化** 類別 Microsoft 365 端點的流量。</span><span class="sxs-lookup"><span data-stu-id="04e80-153">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="04e80-154">如需詳細資訊，請參閱[Office 365 端點類別](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)和用於分割隧道的最優化類別端點[清單](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)。</span><span class="sxs-lookup"><span data-stu-id="04e80-154">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) and [the lists](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) of Optimize category endpoints for split tunneling.</span></span>

<span data-ttu-id="04e80-155">以下是分割隧道所產生的流量流量，其中大部分的流量 Microsoft 365 雲端應用程式會略過 VPN 連接。</span><span class="sxs-lookup"><span data-stu-id="04e80-155">Here is the resulting traffic flow for split tunneling, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![來自 VPN 用戶端的網路流量 (含通道)](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="04e80-157">在此圖中，VPN 用戶端直接透過網際網路傳送和接收重要的 Microsoft 365 雲端服務流量，並接收到 Microsoft 全球網路的最近的前門。</span><span class="sxs-lookup"><span data-stu-id="04e80-157">In this illustration, the VPN client sends and receives crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest front door into the Microsoft Global Network.</span></span>

<span data-ttu-id="04e80-158">如需詳細資訊和指導方針，請參閱[使用 VPN 分割通道將遠端使用者的 Office 365 連線能力最佳化](../enterprise/microsoft-365-vpn-split-tunnel.md)。</span><span class="sxs-lookup"><span data-stu-id="04e80-158">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="using-network-insights-preview"></a><span data-ttu-id="04e80-159">使用網路 Insights (預覽) </span><span class="sxs-lookup"><span data-stu-id="04e80-159">Using Network Insights (preview)</span></span>

<span data-ttu-id="04e80-160">網路洞察力是從 Microsoft 365 租使用者收集的效能度量，可協助您為辦公室位置設計網路周邊。</span><span class="sxs-lookup"><span data-stu-id="04e80-160">Network insights are performance metrics collected from your Microsoft 365 tenant that help you design network perimeters for your office locations.</span></span> <span data-ttu-id="04e80-161">每個真知灼見都會針對內部部署使用者存取您租使用者的位置，針對每個地理位置，提供有關特定問題之效能特性的實際詳細資料。</span><span class="sxs-lookup"><span data-stu-id="04e80-161">Each insight provides live details about the performance characteristics for a specified issue for each geographic location where on-premises users are accessing your tenant.</span></span>

<span data-ttu-id="04e80-162">租使用者可能會顯示兩個租使用者層級的網路洞察力：</span><span class="sxs-lookup"><span data-stu-id="04e80-162">There are two tenant level network insights that may be shown for the tenant:</span></span>

- [<span data-ttu-id="04e80-163">受連線問題影響的 Exchange 採樣連接</span><span class="sxs-lookup"><span data-stu-id="04e80-163">Exchange sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="04e80-164">受連線問題影響的 SharePoint 採樣連接</span><span class="sxs-lookup"><span data-stu-id="04e80-164">SharePoint sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

<span data-ttu-id="04e80-165">以下是每個辦公室位置的特定網路洞察力：</span><span class="sxs-lookup"><span data-stu-id="04e80-165">These are the specific network insights for each office location:</span></span>

- [<span data-ttu-id="04e80-166">Backhauled 網路出局</span><span class="sxs-lookup"><span data-stu-id="04e80-166">Backhauled network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [<span data-ttu-id="04e80-167">接近您的客戶，偵測到更佳效能</span><span class="sxs-lookup"><span data-stu-id="04e80-167">Better performance detected for customers near you</span></span>](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="04e80-168">使用非最佳的 Exchange Online 服務前端門</span><span class="sxs-lookup"><span data-stu-id="04e80-168">Use of a non-optimal Exchange Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="04e80-169">使用非最佳的 SharePoint 線上服務前門</span><span class="sxs-lookup"><span data-stu-id="04e80-169">Use of a non-optimal SharePoint Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="04e80-170">從 SharePoint 前門開始的低下載速度</span><span class="sxs-lookup"><span data-stu-id="04e80-170">Low download speed from SharePoint front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="04e80-171">中國使用者最佳網路出口</span><span class="sxs-lookup"><span data-stu-id="04e80-171">China user optimal network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

> [!IMPORTANT]
> <span data-ttu-id="04e80-172">Microsoft 365 系統管理 Center 中的網路洞察力、效能建議和評估目前處於預覽狀態。</span><span class="sxs-lookup"><span data-stu-id="04e80-172">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status.</span></span> <span data-ttu-id="04e80-173">它只適用于已在功能預覽方案中登記 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="04e80-173">It is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

<span data-ttu-id="04e80-174">如需詳細資訊，請參閱[Microsoft 365 網路 Insights](../enterprise/office-365-network-mac-perf-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="04e80-174">For more information, see [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).</span></span>

## <a name="sharepoint-performance-with-the-office-365-cdn"></a><span data-ttu-id="04e80-175">使用 Office 365 SharePoint 效能 CDN</span><span class="sxs-lookup"><span data-stu-id="04e80-175">SharePoint performance with the Office 365 CDN</span></span>

<span data-ttu-id="04e80-176">以雲端為基礎的內容傳遞網路 (CDN) 可讓您減少載入時間、節省頻寬和加快回應速度。</span><span class="sxs-lookup"><span data-stu-id="04e80-176">A cloud-based Content Delivery Network (CDN) allows you to reduce load times, save bandwidth, and speed responsiveness.</span></span> <span data-ttu-id="04e80-177">CDN 會將靜態資產（例如圖形或影片檔案）快取至瀏覽器所要求的位置，以提升效能，這有助於加速下載並減少延遲。</span><span class="sxs-lookup"><span data-stu-id="04e80-177">A CDN improves performance by caching static assets such as graphic or video files closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="04e80-178">您可以使用內建的 Office 365 內容傳遞網路 (CDN) （包含 SharePoint 和 E5 中的 Microsoft 365 E3）以主控靜態資產，以提供更佳的 SharePoint 頁面效能。</span><span class="sxs-lookup"><span data-stu-id="04e80-178">You can use the built-in Office 365 Content Delivery Network (CDN), included with SharePoint in Microsoft 365 E3 and E5, to host static assets to provide better performance for your SharePoint pages.</span></span>

<span data-ttu-id="04e80-179">Office 365 CDN 是由可讓您在多個位置或 _來源_ 主控靜態資產的多個 CDN 組成，並透過全球高速網路提供資產。</span><span class="sxs-lookup"><span data-stu-id="04e80-179">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="04e80-180">根據您想要在 Office 365 CDN 中主控的內容種類，您可以新增 **公用** 來源、**私人** 來源或兩者。</span><span class="sxs-lookup"><span data-stu-id="04e80-180">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins, or both.</span></span>

<span data-ttu-id="04e80-181">部署及設定時，Office 365 CDN 會從公用和私人來源上傳資產，並可讓使用者快速存取遍佈于網際網路的使用者。</span><span class="sxs-lookup"><span data-stu-id="04e80-181">When deployed and configured, the Office 365 CDN uploads assets from public and private origins and makes them available for fast access to users located across the Internet.</span></span>

<span data-ttu-id="04e80-182">![為使用者部署的 Office 365 CDN](../media/O365-CDN/o365-cdn-flow-transparent.svg "為使用者部署的 Office 365 CDN")</span><span class="sxs-lookup"><span data-stu-id="04e80-182">![Office 365 CDN deployed for users](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN deployed for users")</span></span>

<span data-ttu-id="04e80-183">如需詳細資訊，請參閱[Use the Office 365 CDN with SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="04e80-183">For more information, see [Use the Office 365 CDN with SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).</span></span>

## <a name="automated-endpoint-listing"></a><span data-ttu-id="04e80-184">自動化端點清單</span><span class="sxs-lookup"><span data-stu-id="04e80-184">Automated endpoint listing</span></span>

<span data-ttu-id="04e80-185">若要讓您的內部部署用戶端、edge 裝置和雲端式資料包分析服務略過處理信任的 Microsoft 365 流量，您必須使用一組端點（ (IP 位址範圍和 DNS 名稱）進行設定，) 對應 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="04e80-185">To have your on-premises clients, edge devices, and cloud-based packet analysis services skip processing of trusted Microsoft 365 traffic, you must configure them with the set of endpoints (IP address ranges and DNS names) corresponding to Microsoft 365 services.</span></span> <span data-ttu-id="04e80-186">這些端點可以手動設定防火牆和其他 edge security 裝置、用戶端電腦的 PAC 檔案，以略過 proxy，或在分支辦公室 SD-WAN 裝置。</span><span class="sxs-lookup"><span data-stu-id="04e80-186">These endpoints can be manually configured in firewalls and other edge security devices, PAC files for client computers to bypass proxies, or SD-WAN devices at branch offices.</span></span> <span data-ttu-id="04e80-187">不過，端點會隨著時間而變更，需要在這些位置進行手動維護端點清單。</span><span class="sxs-lookup"><span data-stu-id="04e80-187">However, the endpoints change over time, requiring ongoing manual maintenance of the endpoint lists in these locations.</span></span>

<span data-ttu-id="04e80-188">若要在用戶端 PAC 檔案和網路裝置中自動執行 Microsoft 365 端點的清單和變更管理，請使用[Office 365 IP 位址和 URL REST 型 web 服務](../enterprise/microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="04e80-188">To automate the listing and change management for Microsoft 365 endpoints in your client PAC files and network devices, use the [Office 365 IP Address and URL REST-based web service](../enterprise/microsoft-365-ip-web-service.md).</span></span> <span data-ttu-id="04e80-189">這種服務可協助您更好地識別及區別 Microsoft 365 網路流量，讓您更容易評估、設定和保持最新的變更。</span><span class="sxs-lookup"><span data-stu-id="04e80-189">This service helps you better identify and differentiate Microsoft 365 network traffic, making it easier for you to evaluate, configure, and stay current with the latest changes.</span></span>

<span data-ttu-id="04e80-190">您可以使用 PowerShell、Python 或其他語言，依時間決定端點的變更，並設定您的 PAC 檔案和 edge 網路裝置。</span><span class="sxs-lookup"><span data-stu-id="04e80-190">You can use PowerShell, Python, or other languages to determine the changes to endpoints over time and configure your PAC files and edge network devices.</span></span>

<span data-ttu-id="04e80-191">基本過程如下：</span><span class="sxs-lookup"><span data-stu-id="04e80-191">The basic process is:</span></span>

1. <span data-ttu-id="04e80-192">使用 Office 365 IP 位址和 URL web 服務，以及您選擇的設定機制，設定您的 PAC 檔案和網路裝置目前的一組 Microsoft 365 端點。</span><span class="sxs-lookup"><span data-stu-id="04e80-192">Use the Office 365 IP Address and URL web service and the configuration mechanism of your choice to configure your PAC files and network devices with the current set of Microsoft 365 endpoints.</span></span>
2. <span data-ttu-id="04e80-193">執行每日週期性，檢查端點中的變更或使用通知方法。</span><span class="sxs-lookup"><span data-stu-id="04e80-193">Run a daily recurring to check for changes in the endpoints or use a notification method.</span></span>
3. <span data-ttu-id="04e80-194">當偵測到變更時，請重新產生並重新發佈用戶端電腦的 PAC 檔案，並對您的網路裝置進行變更。</span><span class="sxs-lookup"><span data-stu-id="04e80-194">When changes are detected, regenerate and redistribute the PAC file for client computers and make the changes to your network devices.</span></span>

<span data-ttu-id="04e80-195">如需詳細資訊，請參閱[Office 365 IP 位址和 URL web 服務](../enterprise/microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="04e80-195">For more information, see [Office 365 IP Address and URL web service](../enterprise/microsoft-365-ip-web-service.md).</span></span>

## <a name="results-of-step-2"></a><span data-ttu-id="04e80-196">步驟 2 的結果</span><span class="sxs-lookup"><span data-stu-id="04e80-196">Results of Step 2</span></span>

<span data-ttu-id="04e80-197">針對具有最佳網路的 Microsoft 365 租使用者，您已決定：</span><span class="sxs-lookup"><span data-stu-id="04e80-197">For your Microsoft 365 tenant with optimal networking, you have determined:</span></span>

- <span data-ttu-id="04e80-198">如何透過將網際網路連線新增至所有分支辦公室並消除網路 hairpin，以最優化內部部署使用者的網路效能。</span><span class="sxs-lookup"><span data-stu-id="04e80-198">How to optimize network performance for on-premises users by adding Internet connections to all branch offices and eliminating network hairpins.</span></span>
- <span data-ttu-id="04e80-199">如何針對用戶端的 PAC 檔案和網路裝置及服務執行自動信任端點清單，包括 (最適合商業網路) 的持續更新。</span><span class="sxs-lookup"><span data-stu-id="04e80-199">How to implement automated trusted endpoint listing for your client-based PAC files and your network devices and services, including ongoing updates (most suitable for enterprise networks).</span></span>
- <span data-ttu-id="04e80-200">如何支援對內部部署資源的遠端工作者存取。</span><span class="sxs-lookup"><span data-stu-id="04e80-200">How to support the access of remote workers to on-premises resources.</span></span>
- <span data-ttu-id="04e80-201">如何使用網路 Insights</span><span class="sxs-lookup"><span data-stu-id="04e80-201">How to use Network Insights</span></span>
- <span data-ttu-id="04e80-202">如何部署 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="04e80-202">How to deploy the Office 365 CDN.</span></span>

<span data-ttu-id="04e80-203">以下是企業組織及其租使用者的最佳網路的範例。</span><span class="sxs-lookup"><span data-stu-id="04e80-203">Here is an example of an enterprise organization and its tenant with optimal networking.</span></span>

![具有最佳網路的承租人範例](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[<span data-ttu-id="04e80-205">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="04e80-205">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

<span data-ttu-id="04e80-206">在此圖中，此 enterprise 組織的承租人具有：</span><span class="sxs-lookup"><span data-stu-id="04e80-206">In this illustration, the tenant for this enterprise organization has:</span></span>

- <span data-ttu-id="04e80-207">使用 SDWAN 裝置，將信任的 Microsoft 365 流量轉送至本機前門的每個分支辦公室的本機網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="04e80-207">Local internet access for each branch office with an SDWAN device that forwards trusted Microsoft 365 traffic to a local front door.</span></span>
- <span data-ttu-id="04e80-208">無網路 hairpin。</span><span class="sxs-lookup"><span data-stu-id="04e80-208">No network hairpins.</span></span>
- <span data-ttu-id="04e80-209">中央辦公室安全性和 proxy edge 裝置，可將 Microsoft 365 信任的流量轉寄到本機的前門。</span><span class="sxs-lookup"><span data-stu-id="04e80-209">Central office security and proxy edge devices that forward Microsoft 365 trusted traffic to a local front door.</span></span>

## <a name="ongoing-maintenance-for-optimal-networking"></a><span data-ttu-id="04e80-210">持續進行維護以取得最佳網路</span><span class="sxs-lookup"><span data-stu-id="04e80-210">Ongoing maintenance for optimal networking</span></span>

<span data-ttu-id="04e80-211">您可能需要進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="04e80-211">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="04e80-212">更新 edge 裝置，並為端點的變更部署 PAC 檔案，或確認您的自動化程式運作正常。</span><span class="sxs-lookup"><span data-stu-id="04e80-212">Update your edge devices and deployed PAC files for changes in endpoints or verify that your automated process works properly.</span></span>
- <span data-ttu-id="04e80-213">在 Office 365 CDN 中管理資產。</span><span class="sxs-lookup"><span data-stu-id="04e80-213">Manage your assets in the Office 365 CDN.</span></span>
- <span data-ttu-id="04e80-214">針對端點的變更，更新 VPN 用戶端中的分割隧道設定。</span><span class="sxs-lookup"><span data-stu-id="04e80-214">Update the split tunneling configuration in your VPN clients for changes in endpoints.</span></span>

## <a name="next-step"></a><span data-ttu-id="04e80-215">下一步</span><span class="sxs-lookup"><span data-stu-id="04e80-215">Next step</span></span>

<span data-ttu-id="04e80-216">[![步驟3。同步處理您的身分識別並強制執行安全登入](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span><span class="sxs-lookup"><span data-stu-id="04e80-216">[![Step 3. Synchronize your identities and enforce secure sign-ins](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span></span>

<span data-ttu-id="04e80-217">繼續身分 [識別](tenant-management-identity.md) ，以同步處理內部部署帳戶和群組，並強制執行安全使用者登入。</span><span class="sxs-lookup"><span data-stu-id="04e80-217">Continue with [identity](tenant-management-identity.md) to synchronize your on-premises accounts and groups and enforce secure user sign-ins.</span></span>
