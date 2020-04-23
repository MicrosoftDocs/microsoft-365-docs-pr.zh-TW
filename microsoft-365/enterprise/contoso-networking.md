---
title: Contoso Corporation 的網路
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 網路基礎結構，以及如何使用其 SD-WAN 技術，以取得與 Microsoft 365 企業版雲端服務的最佳網路效能。
ms.openlocfilehash: 4e649796b30b96db3b36de2dabec1f276728d3ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625275"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="b4ece-103">Contoso Corporation 的網路</span><span class="sxs-lookup"><span data-stu-id="b4ece-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="b4ece-p101">為了採用內含雲端的基礎結構，Contoso 的網路工程師了解網路流量到雲端服務的基礎轉移。他們並非使用著重在 Contoso 更高階辦公室階層的網路連線和流量的內部中樞與輪輻模型，而是致力於將使用者位置對應至當地網際網路輸出，以及將當地連線對應至網際網路上最接近的 Microsoft 365 網路位置。</span><span class="sxs-lookup"><span data-stu-id="b4ece-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="b4ece-106">Contoso 的網路基礎結構</span><span class="sxs-lookup"><span data-stu-id="b4ece-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="b4ece-107">跨全球連結其辦公室的 Contoso 網路元素如下：</span><span class="sxs-lookup"><span data-stu-id="b4ece-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="b4ece-108">多重通訊協定標籤切換 (MPLS) WAN 網路</span><span class="sxs-lookup"><span data-stu-id="b4ece-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="b4ece-p102">MPLS WAN 會以輪輻和中樞組態，將巴黎總部連線到區域辦公室，以及將區域辦公室連線到衛星辦公室。這適用於讓使用者存取伺服器，這些伺服器組成巴黎辦公室中的企業營運應用程式。它也會將任何一般網際網路流量路由傳送到巴黎辦公室，在其中網路安全性裝置會清除要求。在每個辦公室內，路由器會將流量傳遞給子網路上的有線主機或無線存取點，子網路使用私人 IP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="b4ece-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="b4ece-113">Microsoft 365 流量的當地直接網際網路存取</span><span class="sxs-lookup"><span data-stu-id="b4ece-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="b4ece-p103">每個辦公室都有一個軟體定義的 WAN (SD-WAN) 裝置與一或多個當地網際網路 ISP 網路線路，透過 Proxy 伺服器具有自己的網際網路連線。這通常會實作為與當地 ISP 的 WAN 連結，同時提供公用 IP 位址和當地 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b4ece-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="b4ece-116">網際網路呈現方式</span><span class="sxs-lookup"><span data-stu-id="b4ece-116">Internet presence</span></span>

  <span data-ttu-id="b4ece-p104">Contoso 擁有 contoso.com 公用網域名稱。用來訂購產品的 Contoso 公用網站是位於巴黎園區網際網路連線資料中心的一組伺服器。Contoso 在網際網路上使用 /24 公用 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="b4ece-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="b4ece-120">圖 1 顯示 Contoso 的網路基礎結構及其與網際網路的連線。</span><span class="sxs-lookup"><span data-stu-id="b4ece-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Contoso 的網路](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="b4ece-122">**圖 1：Contoso 的網路**</span><span class="sxs-lookup"><span data-stu-id="b4ece-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="b4ece-123">使用 SD-WAN 以取得與 Microsoft 的最佳化網路連線</span><span class="sxs-lookup"><span data-stu-id="b4ece-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="b4ece-124">Contoso 遵循 [Microsoft 365 網路連線原則](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) (部分機器翻譯)，以便：</span><span class="sxs-lookup"><span data-stu-id="b4ece-124">Contoso followed [Microsoft 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) to:</span></span>

1. <span data-ttu-id="b4ece-125">識別並區分 Microsoft 365 網路流量</span><span class="sxs-lookup"><span data-stu-id="b4ece-125">Identify and differentiate Microsoft 365 network traffic</span></span>
2. <span data-ttu-id="b4ece-126">在當地輸出網路連線</span><span class="sxs-lookup"><span data-stu-id="b4ece-126">Egress network connections locally</span></span>
3. <span data-ttu-id="b4ece-127">避免網路 hairpin</span><span class="sxs-lookup"><span data-stu-id="b4ece-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="b4ece-128">略過重複的網路安全性裝置</span><span class="sxs-lookup"><span data-stu-id="b4ece-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="b4ece-129">Microsoft 365 的網路流量有三種類別：[最佳化]、[允許] 和 [預設]。</span><span class="sxs-lookup"><span data-stu-id="b4ece-129">There are three categories of network traffic for Microsoft 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="b4ece-130">[最佳化] 和 [允許] 流量是受信任的網路流量，在端點經過加密並受到保護，目的地是 Microsoft 365 網路。</span><span class="sxs-lookup"><span data-stu-id="b4ece-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="b4ece-131">Contoso 決定：</span><span class="sxs-lookup"><span data-stu-id="b4ece-131">Contoso decided to:</span></span>

- <span data-ttu-id="b4ece-132">針對最佳化和允許類別流量使用直接網際網路輸出，並且將所有預設類別流量轉送到巴黎中央網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="b4ece-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="b4ece-133">在每個辦公室的位置部署 SD_WAN 裝置，作為一個簡單的方法，來遵循這些原則並達成 Microsoft 365 雲端式服務的最佳化網路效能。</span><span class="sxs-lookup"><span data-stu-id="b4ece-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="b4ece-134">SD-WAN 裝置有一個給當地辦公室網路使用的 LAN 連接埠，和多個 WAN 連接埠。</span><span class="sxs-lookup"><span data-stu-id="b4ece-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="b4ece-135">一個 WAN 連接埠會連線到其 MPLS 網路，另一個 WAN 連接埠則會連線到當地 ISP 線路。</span><span class="sxs-lookup"><span data-stu-id="b4ece-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="b4ece-136">SD-WAN 裝置會透過 ISP 連結路由 [最佳化] 和 [允許] 類別的網路流量。</span><span class="sxs-lookup"><span data-stu-id="b4ece-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="b4ece-137">Contoso 的企業營運應用程式基礎結構</span><span class="sxs-lookup"><span data-stu-id="b4ece-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="b4ece-138">Contoso 已針對以下地點架構其企業營運應用程式和伺服器內部網路基礎結構：</span><span class="sxs-lookup"><span data-stu-id="b4ece-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="b4ece-139">衛星辦公室使用當地快取伺服器以儲存經常存取的文件和內部網站。</span><span class="sxs-lookup"><span data-stu-id="b4ece-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="b4ece-p107">地區中樞針對地區和衛星辦公室使用地區應用程式伺服器，這些伺服器會與巴黎總部的伺服器同步處理。</span><span class="sxs-lookup"><span data-stu-id="b4ece-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="b4ece-142">巴黎園區的資料中樞包含服務整個組織的集中式應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="b4ece-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="b4ece-143">圖 2 顯示在 Contoso 內部網路存取伺服器時的網路流量百分比。</span><span class="sxs-lookup"><span data-stu-id="b4ece-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Contoso 的內部應用程式基礎結構](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="b4ece-145">**圖 2：Contoso 的內部應用程式基礎結構**</span><span class="sxs-lookup"><span data-stu-id="b4ece-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="b4ece-p108">對於衛星或地區中樞辦公室的使用者來說，有 60% 員工所需要的資源均由衛星和地區中樞辦公室伺服器提供，而另外的 40% 資源要求則必須透過 WAN 連結至巴黎園區。</span><span class="sxs-lookup"><span data-stu-id="b4ece-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="b4ece-148">Contoso 的網路分析和針對 Microsoft 365 企業版的網路準備</span><span class="sxs-lookup"><span data-stu-id="b4ece-148">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b4ece-p109">Contoso 的使用者對於 Microsoft 365 企業版服務採用的成功與否，取決於網際網路的高可用性和高效能的連線，或是否可直接與 Microsoft 雲端服務連線。Contoso 會採取這些步驟來規劃及實作對 Microsoft 365 企業版雲端服務的最佳化連線：</span><span class="sxs-lookup"><span data-stu-id="b4ece-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="b4ece-151">建立公司 WAN 網路圖以協助規劃</span><span class="sxs-lookup"><span data-stu-id="b4ece-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="b4ece-p110">Contoso 藉由建立圖表 (顯示他們的位置、現有網路連線能力、其現有周邊網路裝置和網路上受管理的服務類別) 開始網路規劃。他們會針對網路連線規劃及實作的每個後續步驟，使用這個圖表。</span><span class="sxs-lookup"><span data-stu-id="b4ece-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="b4ece-154">建立 Microsoft 365 企業版網路連線的計劃</span><span class="sxs-lookup"><span data-stu-id="b4ece-154">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="b4ece-155">Contoso 使用 [Microsoft 365 網路連線原則](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) (部分機器翻譯) 及提供參考網路架構，來決定 SD WAN 作為其 Microsoft 365 連線的偏好拓撲。</span><span class="sxs-lookup"><span data-stu-id="b4ece-155">Contoso used the [Microsoft 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="b4ece-156">在每個辦公室分析網際網路連線使用率和 MPLS WAN 頻寬，並且視需要增加頻寬</span><span class="sxs-lookup"><span data-stu-id="b4ece-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="b4ece-157">每個辦公室都會進行分析以取得目前使用量，並且會增加線路，讓預測的 Microsoft 365 雲端式流量可以運作，同時有平均 20% 的未使用容量。</span><span class="sxs-lookup"><span data-stu-id="b4ece-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="b4ece-158">對 Microsoft 網路服務的最佳化效能</span><span class="sxs-lookup"><span data-stu-id="b4ece-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="b4ece-159">Contoso 決定了 Office 365、Intune 和 Azure 端點的組合，並且在網際網路路徑中設定了防火牆、安全性裝置和其他系統以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="b4ece-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="b4ece-160">Office 365 [最佳化] 和 [允許] 類別流量的端點已設定為進入 SD-WAN 裝置以便透過 ISP 線路路由。</span><span class="sxs-lookup"><span data-stu-id="b4ece-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="b4ece-161">設定內部 DNS</span><span class="sxs-lookup"><span data-stu-id="b4ece-161">Configured internal DNS</span></span>

   <span data-ttu-id="b4ece-162">DNS 必須能夠運作，並且可以在本機針對 Microsoft 365 流量進行查閱。</span><span class="sxs-lookup"><span data-stu-id="b4ece-162">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="b4ece-163">已驗證的網路端點和連接埠連線</span><span class="sxs-lookup"><span data-stu-id="b4ece-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="b4ece-164">Contoso 會執行由 Microsoft 提供的網路連線測試工具，以驗證 Microsoft 365 企業版雲端服務的連線。</span><span class="sxs-lookup"><span data-stu-id="b4ece-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="b4ece-165">針對網路連線來最佳化員工電腦</span><span class="sxs-lookup"><span data-stu-id="b4ece-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="b4ece-166">個別電腦會經過檢查，以確定已安裝最新的作業系統更新，而且在所有用戶端上的端點安全性監視均在使用中。</span><span class="sxs-lookup"><span data-stu-id="b4ece-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="b4ece-167">下一步</span><span class="sxs-lookup"><span data-stu-id="b4ece-167">Next step</span></span>

<span data-ttu-id="b4ece-168">[了解](contoso-identity.md) Contoso 如何針對員工在雲端中利用其內部部署 Active Directory Domain Services (AD DS)，以及如何針對客戶和商務合作夥伴利用同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="b4ece-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4ece-169">請參閱</span><span class="sxs-lookup"><span data-stu-id="b4ece-169">See also</span></span>

[<span data-ttu-id="b4ece-170">Microsoft 365 企業版的網路</span><span class="sxs-lookup"><span data-stu-id="b4ece-170">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="b4ece-171">部署指南</span><span class="sxs-lookup"><span data-stu-id="b4ece-171">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b4ece-172">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="b4ece-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
