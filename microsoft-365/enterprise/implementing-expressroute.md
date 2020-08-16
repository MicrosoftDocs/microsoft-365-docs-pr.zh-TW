---
title: 實作 ExpressRoute for Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: 瞭解如何針對 Office 365 實施 ExpressRoute，它會為許多網際網路面向 Office 365 服務提供其他路由路徑。
ms.openlocfilehash: 767a99f3a27f30b7193fd0d0b8376ff4923daffb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688765"
---
# <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="12889-103">實作 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="12889-103">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="12889-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="12889-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="12889-105">ExpressRoute for Office 365 可提供許多網際網路對向 Office 365 服務的備用路由路徑。</span><span class="sxs-lookup"><span data-stu-id="12889-105">ExpressRoute for Office 365 provides an alternate routing path to many internet facing Office 365 services.</span></span> <span data-ttu-id="12889-106">Office 365 ExpressRoute 的架構是以 Office 365 服務（已透過網際網路存取） ExpressRoute 中的廣告公用 IP 首碼為基礎，以在您的網路中接下來再發佈這些 IP 首碼。</span><span class="sxs-lookup"><span data-stu-id="12889-106">The architecture of ExpressRoute for Office 365 is based on advertising public IP prefixes of Office 365 services that are already accessible over the Internet into your provisioned ExpressRoute circuits for subsequent redistribution of those IP prefixes into your network.</span></span> <span data-ttu-id="12889-107">透過 ExpressRoute，您可以有效地為許多 Office 365 服務啟用多個不同的路由路徑（透過網際網路及透過 ExpressRoute）。</span><span class="sxs-lookup"><span data-stu-id="12889-107">With ExpressRoute you effectively enable several different routing paths, through the internet and through ExpressRoute, for many Office 365 services.</span></span> <span data-ttu-id="12889-108">網路上路由的狀態可能代表如何設計內部網路拓撲的重大變更。</span><span class="sxs-lookup"><span data-stu-id="12889-108">This state of routing on your network may represent a significant change to how your internal network topology is designed.</span></span>
  
 <span data-ttu-id="12889-109">**狀態：** 完成指南 v2</span><span class="sxs-lookup"><span data-stu-id="12889-109">**Status:** Complete Guide v2</span></span>
  
<span data-ttu-id="12889-110">您必須仔細規劃 Office 365 執行的 ExpressRoute，以容納透過透過插入核心網路和網際網路之路由的專用電路，取得可供使用的網路複雜性。</span><span class="sxs-lookup"><span data-stu-id="12889-110">You must carefully plan your ExpressRoute for Office 365 implementation to accommodate for the network complexities of having routing available via both a dedicated circuit with routes injected into your core network and the internet.</span></span> <span data-ttu-id="12889-111">如果您和您的小組沒有在本指南中執行詳細的規劃與測試，當啟用 ExpressRoute 電路時，您會遇到間歇性或總失去與 Office 365 服務的連線能力。</span><span class="sxs-lookup"><span data-stu-id="12889-111">If you and your team don't perform the detailed planning and testing in this guide, there is a high risk you'll experience intermittent or a total loss of connectivity to Office 365 services when the ExpressRoute circuit is enabled.</span></span>
  
<span data-ttu-id="12889-112">若要取得成功的實施，您需要分析基礎結構需求、深入瞭解網路評估與設計，以分段且可控的方式仔細規劃推廣，並建立詳細的驗證和測試計劃。</span><span class="sxs-lookup"><span data-stu-id="12889-112">To have a successful implementation, you will need to analyze your infrastructure requirements, go through detailed network assessment and design, carefully plan the rollout in a staged and controlled manner, and build a detailed validation and testing plan.</span></span> <span data-ttu-id="12889-113">對於大型的分散式環境而言，每個月的實施範圍都很少見。</span><span class="sxs-lookup"><span data-stu-id="12889-113">For a large, distributed environment it's not uncommon to see implementations span several months.</span></span> <span data-ttu-id="12889-114">本指南旨在協助您預先規劃。</span><span class="sxs-lookup"><span data-stu-id="12889-114">This guide is designed to help you plan ahead.</span></span>
  
<span data-ttu-id="12889-115">大量成功的部署可能需要六個月的計畫，而且常常包括來自組織之許多方面的小組成員，包括網路、防火牆和 Proxy 伺服器管理員、Office 365 管理員、安全性、使用者支援、專案管理，以及執行的資助。</span><span class="sxs-lookup"><span data-stu-id="12889-115">Large successful deployments may take six months in planning and often include team members from many areas in the organization including networking, Firewall and Proxy server administrators, Office 365 administrators, security, end-user support, project management, and executive sponsorship.</span></span> <span data-ttu-id="12889-116">您在規劃程式中的投資，可減少因停機或複雜且昂貴的疑難排解而導致部署失敗的可能性。</span><span class="sxs-lookup"><span data-stu-id="12889-116">Your investment in the planning process will reduce the likelihood that you'll experience deployment failures resulting in downtime or complex and expensive troubleshooting.</span></span>
  
<span data-ttu-id="12889-117">在此實施指南開始之前，我們預期會完成下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="12889-117">We expect the following pre-requisites to be completed before this implementation guide is started.</span></span>
  
1. <span data-ttu-id="12889-118">您已完成網路評估，以判斷是否建議和核准 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="12889-118">You've completed a network assessment to determine if ExpressRoute is recommended and approved.</span></span>

2. <span data-ttu-id="12889-119">您已選取 ExpressRoute 網路服務提供者。</span><span class="sxs-lookup"><span data-stu-id="12889-119">You've selected an ExpressRoute network service provider.</span></span> <span data-ttu-id="12889-120">尋找 [ExpressRoute 合作夥伴和對等位置](https://azure.microsoft.com/documentation/articles/expressroute-locations/)的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="12889-120">Find details about the [ExpressRoute partners and peering locations](https://azure.microsoft.com/documentation/articles/expressroute-locations/).</span></span>

3. <span data-ttu-id="12889-121">您已閱讀並瞭解 [ExpressRoute 檔](https://azure.microsoft.com/documentation/services/expressroute/) ，且您的內部網路可滿足 ExpressRoute 先決條件端對端。</span><span class="sxs-lookup"><span data-stu-id="12889-121">You've already read and understand the [ExpressRoute documentation](https://azure.microsoft.com/documentation/services/expressroute/) and your internal network is able to meet ExpressRoute pre-requisites end to end.</span></span>

4. <span data-ttu-id="12889-122">您的小組已閱讀頻道9上的所有公開指導方針和檔， [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365) [https://aka.ms/ert](https://aka.ms/ert) 並在頻道9上查看 [Office 365 訓練系列的 Azure ExpressRoute](https://channel9.msdn.com/series/aer) ，以深入瞭解重要的技術詳細資料，包括：</span><span class="sxs-lookup"><span data-stu-id="12889-122">Your team has read all of the public guidance and documentation at [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365), [https://aka.ms/ert](https://aka.ms/ert), and watched the [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to gain an understanding of critical technical details including:</span></span>

      - <span data-ttu-id="12889-123">SaaS 服務的網際網路相依性。</span><span class="sxs-lookup"><span data-stu-id="12889-123">The internet dependencies of SaaS services.</span></span>

      - <span data-ttu-id="12889-124">如何避免對稱路由並處理複雜路由。</span><span class="sxs-lookup"><span data-stu-id="12889-124">How to avoid asymmetric routes and handle complex routing.</span></span>

      - <span data-ttu-id="12889-125">如何結合周邊安全性、可用性和應用層級控制項。</span><span class="sxs-lookup"><span data-stu-id="12889-125">How to incorporate perimeter security, availability, and application level controls.</span></span>

## <a name="begin-by-gathering-requirements"></a><span data-ttu-id="12889-126">請先收集需求</span><span class="sxs-lookup"><span data-stu-id="12889-126">Begin by gathering requirements</span></span>
<span data-ttu-id="12889-127"><a name="requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-127"><a name="requirements"> </a></span></span>

<span data-ttu-id="12889-128">首先，決定您規劃要在組織中採用的功能和服務。</span><span class="sxs-lookup"><span data-stu-id="12889-128">Start by determining which features and services you plan to adopt within your organization.</span></span> <span data-ttu-id="12889-129">您必須決定要使用的不同 Office 365 服務功能，以及網路上的哪些位置將使用這些功能主控人員。</span><span class="sxs-lookup"><span data-stu-id="12889-129">You need to determine which features of the different Office 365 services will be used and which locations on your network will host people using those features.</span></span> <span data-ttu-id="12889-130">在案例目錄中，您需要新增每個案例所需的網路屬性。例如輸入和輸出網路流量流量，以及 Office 365 端點是否可用於 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="12889-130">With the catalog of scenarios, you need to add the network attributes that each of those scenarios require; such as inbound and outbound network traffic flows and if the Office 365 endpoints are available over ExpressRoute or not.</span></span>
  
<span data-ttu-id="12889-131">若要收集組織的需求：</span><span class="sxs-lookup"><span data-stu-id="12889-131">To gather your organization's requirements:</span></span>
  
- <span data-ttu-id="12889-132">編目組織所使用之 Office 365 服務的輸入和輸出網路流量。</span><span class="sxs-lookup"><span data-stu-id="12889-132">Catalog the inbound and outbound network traffic for the Office 365 services your organization is using.</span></span> <span data-ttu-id="12889-133">請參閱 Office 365 URLs 和 IP 位址範圍頁面，瞭解不同 Office 365 案例所需流程的描述。</span><span class="sxs-lookup"><span data-stu-id="12889-133">Consult Office 365 URLs and IP address ranges page for the description of flows that different Office 365 scenarios require.</span></span>

- <span data-ttu-id="12889-134">收集現有網路拓撲的檔，顯示內部 WAN 主幹和拓撲的詳細資料、衛星網站的連線、最後的使用者連線能力、路由傳送至網路周邊出局點，以及 proxy 服務。</span><span class="sxs-lookup"><span data-stu-id="12889-134">Gather documentation of existing network topology showing details of your internal WAN backbone and topology, connectivity of satellite sites, last mile user connectivity, routing to network perimeter egress points, and proxy services.</span></span>

  - <span data-ttu-id="12889-135">識別網狀圖上的輸入服務端點，Office 365 和其他 Microsoft 服務將會連線至，同時顯示網際網路和擬議中的 ExpressRoute 連接路徑。</span><span class="sxs-lookup"><span data-stu-id="12889-135">Identify inbound service endpoints on the network diagrams that Office 365 and other Microsoft services will connect to, showing both internet and proposed ExpressRoute connection paths.</span></span>

  - <span data-ttu-id="12889-136">識別各位置之間的所有地理位置使用者位置和 WAN 連線，以及哪些位置目前擁有網際網路的出入，以及哪些位置已建議將出口到 ExpressRoute 對等位置。</span><span class="sxs-lookup"><span data-stu-id="12889-136">Identify all geographic user locations and WAN connectivity between locations along with which locations currently have an egress to the internet and which locations are proposed to have an egress to an ExpressRoute peering location.</span></span>

  - <span data-ttu-id="12889-137">識別所有 edge 裝置，例如 proxy、防火牆等等，以及將其關聯編目為透過網際網路和 ExpressRoute 的流量。</span><span class="sxs-lookup"><span data-stu-id="12889-137">Identify all edge devices, such as proxies, firewalls, and so on and catalog their relationship to flows going over the Internet and ExpressRoute.</span></span>

  - <span data-ttu-id="12889-138">檔使用者是否會透過直接路由或間接應用程式 proxy，針對網際網路和 ExpressRoute 流量，存取 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="12889-138">Document whether end users will access Office 365 services via direct routing or indirect application proxy for both Internet and ExpressRoute flows.</span></span>

- <span data-ttu-id="12889-139">將您的租使用者位置和符合-me 位置新增至您的網狀圖。</span><span class="sxs-lookup"><span data-stu-id="12889-139">Add the location of your tenant and meet-me locations to your network diagram.</span></span>

- <span data-ttu-id="12889-140">從主要使用者位置到 Office 365，估計預期和觀測的網路效能和延遲特性。</span><span class="sxs-lookup"><span data-stu-id="12889-140">Estimate the expected and observed network performance and latency characteristics from major user locations to Office 365.</span></span> <span data-ttu-id="12889-141">請記住，Office 365 是一組全域和分散式服務，而且使用者將會連線至可能與租使用者位置不同的位置。</span><span class="sxs-lookup"><span data-stu-id="12889-141">Keep in mind that Office 365 is a global and distributed set of services and users will be connecting to locations that may be different from the location of their tenant.</span></span> <span data-ttu-id="12889-142">因此，建議您衡量及優化使用者與最接近的 Microsoft 全球網路 edge 與 ExpressRoute 和網際網路連線之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="12889-142">For this reason, it is recommended to measure and optimize for latency between the user and the closest edge of Microsoft global network over ExpressRoute and Internet connections.</span></span> <span data-ttu-id="12889-143">您可以從網路評估中使用您的結果，以協助您進行這種工作。</span><span class="sxs-lookup"><span data-stu-id="12889-143">You can use your findings from the network assessment to aid with this task.</span></span>

- <span data-ttu-id="12889-144">列出公司網路安全性和高可用性需求，必須符合新的 ExpressRoute 連線。</span><span class="sxs-lookup"><span data-stu-id="12889-144">List company network security and high availability requirements that need to be met with the new ExpressRoute connection.</span></span> <span data-ttu-id="12889-145">例如，當網際網路出口或 ExpressRoute 電路失敗時，使用者如何繼續存取 Office 365。</span><span class="sxs-lookup"><span data-stu-id="12889-145">For example, how do users continue to get access to Office 365 in the event of the Internet egress or ExpressRoute circuit failure.</span></span>

- <span data-ttu-id="12889-146">記錄傳入和傳出 Office 365 網路流量將使用網際網路路徑，以及使用 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="12889-146">Document which inbound and outbound Office 365 network flows will use the Internet path and which will use ExpressRoute.</span></span> <span data-ttu-id="12889-147">您的使用者地理位置和內部部署網路拓朴詳細資料的詳細資訊可能要求計畫與另一個使用者位置不同。</span><span class="sxs-lookup"><span data-stu-id="12889-147">The specifics of geographical locations of your users and details of your on-premises network topology may require the plan to be different from one user location to another.</span></span>

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a><span data-ttu-id="12889-148">編目輸出和輸入的網路流量</span><span class="sxs-lookup"><span data-stu-id="12889-148">Catalog your outbound and inbound network traffic</span></span>
<span data-ttu-id="12889-149"><a name="trafficCatalog"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-149"><a name="trafficCatalog"> </a></span></span>

<span data-ttu-id="12889-150">若要將路由和其他網路複雜性降至最低，我們建議您只針對因法規需求或網路評估的結果而必須透過專用連線進行的網路流量流量，使用 ExpressRoute for Office 365。</span><span class="sxs-lookup"><span data-stu-id="12889-150">To minimize routing and other network complexities, we recommend that you only use ExpressRoute for Office 365 for the network traffic flows that are required to go over a dedicated connection due to regulatory requirements or as the result of the network assessment.</span></span> <span data-ttu-id="12889-151">此外，我們建議您分段 ExpressRoute 路由的範圍，並將輸出和輸入網路流量資料流程當做實施專案的不同和不同階段。</span><span class="sxs-lookup"><span data-stu-id="12889-151">Additionally, we recommend that you stage the scope of ExpressRoute routing and approach outbound and inbound network traffic flows as different and distinct stages of the implementation project.</span></span> <span data-ttu-id="12889-152">僅針對使用者啟動的輸出網路流量流量，部署 Office 365 的 ExpressRoute，並使跨 Internet 的輸入網路流量流動，可協助控制拓撲複雜性的增加，以及引入其他非對稱路由可能性的風險。</span><span class="sxs-lookup"><span data-stu-id="12889-152">Deploy ExpressRoute for Office 365 for just user initiated outbound network traffic flows and leave inbound network traffic flows across the Internet can help to control the increase in topological complexity and risks of introducing additional asymmetric routing possibilities.</span></span>
  
<span data-ttu-id="12889-153">您的網路流量目錄應包含您的內部部署網路與 Microsoft 之間的所有輸入和輸出網路連線清單。</span><span class="sxs-lookup"><span data-stu-id="12889-153">Your network traffic catalog should contain listings of all the inbound and outbound network connections that you'll have between your on-premises network and Microsoft.</span></span>
  
- <span data-ttu-id="12889-154">輸出網路流量流程是指從您的內部部署環境（例如從內部用戶端或伺服器）啟動連接的任何案例，其目的地為 Microsoft 服務。</span><span class="sxs-lookup"><span data-stu-id="12889-154">Outbound network traffic flows are any scenarios where a connection is initiated from your on-premises environment, such as from internal clients or servers, with a destination of the Microsoft services.</span></span> <span data-ttu-id="12889-155">這些連線可能會直接傳送到 Office 365 或間接，例如當連線經由 proxy 伺服器、防火牆或其他網路裝置的路徑上的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="12889-155">These connections may be direct to Office 365 or indirect, such as when the connection goes through proxy servers, firewalls, or other networking devices on the path to Office 365.</span></span>

- <span data-ttu-id="12889-156">輸入網路流量流程是從 Microsoft 雲端啟動至內部部署主機的任何案例。</span><span class="sxs-lookup"><span data-stu-id="12889-156">Inbound network traffic flows are any scenarios where a connection is initiated from the Microsoft cloud to an on-premises host.</span></span> <span data-ttu-id="12889-157">這些連線通常需要透過防火牆和其他安全性基礎結構，客戶安全性原則需要對外發起流程。</span><span class="sxs-lookup"><span data-stu-id="12889-157">These connections typically need to go through firewall and other security infrastructure that customer security policy requires for externally originated flows.</span></span>

<span data-ttu-id="12889-158">閱讀 office [365 ExpressRoute](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)的 [**確保**路由對應] 區段，以判斷哪些服務會傳送輸入流量，並在[office 365 端點](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)參考文章中尋找標示**為 ExpressRoute for office 365**的欄，以判斷其他的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="12889-158">Read the **Ensuring route symmetry** section of the article [Routing with ExpressRoute for Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) to determine which services will send inbound traffic and look for the column marked **ExpressRoute for Office 365** in the [Office 365 endpoints](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) reference article to determine the rest of the connectivity information.</span></span>
  
<span data-ttu-id="12889-159">針對每個需要輸出連線的服務，您會想要描述服務的已規劃連線，包括網路路由、proxy 設定、封包檢查和頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="12889-159">For each service that requires an outbound connection, you'll want to describe the planned connectivity for the service including network routing, proxy configuration, packet inspection, and bandwidth needs.</span></span>
  
<span data-ttu-id="12889-160">針對每個需要輸入連線的服務，您需要一些額外的資訊。</span><span class="sxs-lookup"><span data-stu-id="12889-160">For each service that requires an inbound connection, you'll need some additional information.</span></span> <span data-ttu-id="12889-161">Microsoft 雲端中的伺服器將會建立與您的內部部署網路的連線。</span><span class="sxs-lookup"><span data-stu-id="12889-161">Servers in the Microsoft cloud will establish connections to your on-premises network.</span></span> <span data-ttu-id="12889-162">為了確保能夠正確地進行連線，您會想要說明此連線的所有方面，包括;可接受這些輸入連線的服務的公用 DNS 專案、CIDR 格式的 IPv4 IP 位址、所涉及的 ISP 裝置，以及如何處理這些連線的輸入 NAT 或來源 NAT。</span><span class="sxs-lookup"><span data-stu-id="12889-162">to ensure the connections are made correctly, you'll want to describe all aspects of this connectivity, including; the public DNS entries for the services that will accept these inbound connections, the CIDR formatted IPv4 IP addresses, which ISP equipment is involved, and how inbound NAT or source NAT is handled for these connections.</span></span>
  
<span data-ttu-id="12889-163">不論是透過網際網路或 ExpressRoute 進行連線以確保未引進非對稱路由，都應複查輸入連線。</span><span class="sxs-lookup"><span data-stu-id="12889-163">Inbound connections should be reviewed regardless of whether they're connecting over the internet or ExpressRoute to ensure asymmetric routing hasn't been introduced.</span></span> <span data-ttu-id="12889-164">在某些情況下，Office 365 服務初始化輸入連線的內部部署端點可能也需要由其他 Microsoft 和非 Microsoft 服務存取。</span><span class="sxs-lookup"><span data-stu-id="12889-164">In some cases, on-premises endpoints that Office 365 services initiate inbound connections to may also need to be accessed by other Microsoft and non-Microsoft services.</span></span> <span data-ttu-id="12889-165">使 ExpressRoute 路由傳送至這些服務以進行 Office 365 的目的，不會中斷其他案例。</span><span class="sxs-lookup"><span data-stu-id="12889-165">It is paramount that enabling ExpressRoute routing to these services for Office 365 purposes doesn't break other scenarios.</span></span> <span data-ttu-id="12889-166">在許多情況下，客戶可能需要對內部網路執行特定變更（例如來源為 NAT），以確保在 ExpressRoute 啟用之後，來自 Microsoft 的輸入資料流程仍保持對稱。</span><span class="sxs-lookup"><span data-stu-id="12889-166">In many cases, customers may need to implement specific changes to their internal network, such as source based NAT, to ensure that inbound flows from Microsoft remain symmetric after ExpressRoute is enabled.</span></span>
  
<span data-ttu-id="12889-167">以下是所需詳細資料層級的範例。</span><span class="sxs-lookup"><span data-stu-id="12889-167">Here's a sample of the level of detail required.</span></span> <span data-ttu-id="12889-168">在此情況下，Exchange 混合式會透過 ExpressRoute 路由傳送至內部部署系統。</span><span class="sxs-lookup"><span data-stu-id="12889-168">In this case Exchange Hybrid would route to the on-premises system over ExpressRoute.</span></span>

|<span data-ttu-id="12889-169">**Connection 屬性**</span><span class="sxs-lookup"><span data-stu-id="12889-169">**Connection property**</span></span>|<span data-ttu-id="12889-170">**值**</span><span class="sxs-lookup"><span data-stu-id="12889-170">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="12889-171">**網路流量方向**</span><span class="sxs-lookup"><span data-stu-id="12889-171">**Network traffic direction**</span></span> <br/> |<span data-ttu-id="12889-172">入境</span><span class="sxs-lookup"><span data-stu-id="12889-172">Inbound</span></span>  <br/> |
|<span data-ttu-id="12889-173">**服務**</span><span class="sxs-lookup"><span data-stu-id="12889-173">**Service**</span></span> <br/> |<span data-ttu-id="12889-174">Exchange 混合式</span><span class="sxs-lookup"><span data-stu-id="12889-174">Exchange Hybrid</span></span>  <br/> |
|<span data-ttu-id="12889-175">\*\*公用 Office 365 端點 (來源) \*\*</span><span class="sxs-lookup"><span data-stu-id="12889-175">**Public Office 365 endpoint (source)**</span></span> <br/> |<span data-ttu-id="12889-176">Exchange Online (IP 位址) </span><span class="sxs-lookup"><span data-stu-id="12889-176">Exchange Online (IP addresses)</span></span>  <br/> |
|<span data-ttu-id="12889-177">\*\*Public On-Premises 端點 (目的地) \*\*</span><span class="sxs-lookup"><span data-stu-id="12889-177">**Public On-Premises Endpoint (destination)**</span></span> <br/> |<span data-ttu-id="12889-178">5.5.5.5</span><span class="sxs-lookup"><span data-stu-id="12889-178">5.5.5.5</span></span>  <br/> |
|<span data-ttu-id="12889-179">**公用 (網際網路) DNS 專案**</span><span class="sxs-lookup"><span data-stu-id="12889-179">**Public (Internet) DNS entry**</span></span> <br/> |<span data-ttu-id="12889-180">Autodiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12889-180">Autodiscover.contoso.com</span></span>  <br/> |
|<span data-ttu-id="12889-181">**此內部部署端點是否會供其他 (非 Office 365) Microsoft 服務使用**</span><span class="sxs-lookup"><span data-stu-id="12889-181">**Will this on-premises endpoint be used for by other (non-Office 365) Microsoft services**</span></span> <br/> |<span data-ttu-id="12889-182">否</span><span class="sxs-lookup"><span data-stu-id="12889-182">No</span></span>  <br/> |
|<span data-ttu-id="12889-183">**Internet 上的使用者或系統是否會使用此內部部署端點**</span><span class="sxs-lookup"><span data-stu-id="12889-183">**Will this on-premises endpoint be used by users/systems on the Internet**</span></span> <br/> |<span data-ttu-id="12889-184">是</span><span class="sxs-lookup"><span data-stu-id="12889-184">Yes</span></span>  <br/> |
|<span data-ttu-id="12889-185">**透過公用端點發佈的內部系統**</span><span class="sxs-lookup"><span data-stu-id="12889-185">**Internal systems published through public endpoints**</span></span> <br/> |<span data-ttu-id="12889-186">Exchange Server client access role (內部部署) 192.168.101、192.168.102、192.168.103</span><span class="sxs-lookup"><span data-stu-id="12889-186">Exchange Server client access role (on-premises) 192.168.101, 192.168.102, 192.168.103</span></span>  <br/> |
|<span data-ttu-id="12889-187">**公用端點的 IP 廣告**</span><span class="sxs-lookup"><span data-stu-id="12889-187">**IP advertisement of the public endpoint**</span></span> <br/> |<span data-ttu-id="12889-188">**至網際網路**： 5.5.0.0/16</span><span class="sxs-lookup"><span data-stu-id="12889-188">**To Internet**: 5.5.0.0/16</span></span>  <br/> <span data-ttu-id="12889-189">**若要 ExpressRoute**： 5.5.5.0/24</span><span class="sxs-lookup"><span data-stu-id="12889-189">**To ExpressRoute**: 5.5.5.0/24</span></span>  <br/> |
|<span data-ttu-id="12889-190">**安全性/周邊控制**</span><span class="sxs-lookup"><span data-stu-id="12889-190">**Security/Perimeter Controls**</span></span> <br/> |<span data-ttu-id="12889-191">**網際網路路徑**： DeviceID_002</span><span class="sxs-lookup"><span data-stu-id="12889-191">**Internet path**: DeviceID_002</span></span>  <br/> <span data-ttu-id="12889-192">**ExpressRoute 路徑**： DeviceID_003</span><span class="sxs-lookup"><span data-stu-id="12889-192">**ExpressRoute path**: DeviceID_003</span></span>  <br/> |
|<span data-ttu-id="12889-193">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="12889-193">**High Availability**</span></span> <br/> |<span data-ttu-id="12889-194">跨2地理冗余的主動/主動</span><span class="sxs-lookup"><span data-stu-id="12889-194">Active/Active across 2 geo-redundant</span></span>  <br/> <span data-ttu-id="12889-195">ExpressRoute 電路-芝加哥和達拉斯</span><span class="sxs-lookup"><span data-stu-id="12889-195">ExpressRoute circuits - Chicago and Dallas</span></span>  <br/> |
|<span data-ttu-id="12889-196">**路徑對稱控制**</span><span class="sxs-lookup"><span data-stu-id="12889-196">**Path symmetry control**</span></span> <br/> |<span data-ttu-id="12889-197">**方法**：來源 NAT</span><span class="sxs-lookup"><span data-stu-id="12889-197">**Method**: Source NAT</span></span>  <br/> <span data-ttu-id="12889-198">**網際網路路徑**：來源 NAT 輸入連線至192.168.5。5</span><span class="sxs-lookup"><span data-stu-id="12889-198">**Internet path**: Source NAT inbound connections to 192.168.5.5</span></span>  <br/> |<span data-ttu-id="12889-199">**ExpressRoute 路徑**：從 (芝加哥) 和 192.168.2.0 (達拉斯) 的來源 NAT 連接</span><span class="sxs-lookup"><span data-stu-id="12889-199">**ExpressRoute path**: Source NAT connections to 192.168.1.0 (Chicago) and 192.168.2.0 (Dallas)</span></span>  <br/> |

<span data-ttu-id="12889-200">以下是僅限輸出之服務的範例：</span><span class="sxs-lookup"><span data-stu-id="12889-200">Here's a sample of a service that is outbound only:</span></span>

|<span data-ttu-id="12889-201">**Connection 屬性**</span><span class="sxs-lookup"><span data-stu-id="12889-201">**Connection property**</span></span>|<span data-ttu-id="12889-202">**值**</span><span class="sxs-lookup"><span data-stu-id="12889-202">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="12889-203">**網路流量方向**</span><span class="sxs-lookup"><span data-stu-id="12889-203">**Network traffic direction**</span></span> <br/> |<span data-ttu-id="12889-204">出境</span><span class="sxs-lookup"><span data-stu-id="12889-204">Outbound</span></span>  <br/> |
|<span data-ttu-id="12889-205">**服務**</span><span class="sxs-lookup"><span data-stu-id="12889-205">**Service**</span></span> <br/> |<span data-ttu-id="12889-206">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="12889-206">SharePoint Online</span></span>  <br/> |
|<span data-ttu-id="12889-207">\*\*內部部署端點 (來源) \*\*</span><span class="sxs-lookup"><span data-stu-id="12889-207">**On-premises endpoint (source)**</span></span> <br/> |<span data-ttu-id="12889-208">使用者工作站</span><span class="sxs-lookup"><span data-stu-id="12889-208">User workstation</span></span>  <br/> |
|<span data-ttu-id="12889-209">\*\*公用 Office 365 端點 (目的地) \*\*</span><span class="sxs-lookup"><span data-stu-id="12889-209">**Public Office 365 endpoint (destination)**</span></span> <br/> |<span data-ttu-id="12889-210">SharePoint 線上 (IP 位址) </span><span class="sxs-lookup"><span data-stu-id="12889-210">SharePoint Online (IP addresses)</span></span>  <br/> |
|<span data-ttu-id="12889-211">**公用 (網際網路) DNS 專案**</span><span class="sxs-lookup"><span data-stu-id="12889-211">**Public (Internet) DNS entry**</span></span> <br/> |<span data-ttu-id="12889-212">\*sharepoint.com (及其他 Fqdn) </span><span class="sxs-lookup"><span data-stu-id="12889-212">\*.sharepoint.com (and additional FQDNs)</span></span>  <br/> |
|<span data-ttu-id="12889-213">**CDN 參照**</span><span class="sxs-lookup"><span data-stu-id="12889-213">**CDN Referrals**</span></span> <br/> |<span data-ttu-id="12889-214">cdn.sharepointonline.com (及其他 Fqdn) 由 CDN 提供者所維護) </span><span class="sxs-lookup"><span data-stu-id="12889-214">cdn.sharepointonline.com (and additional FQDNs) - IP addresses maintained by CDN providers)</span></span>  <br/> |
|<span data-ttu-id="12889-215">**IP 播發和 NAT 正在使用中**</span><span class="sxs-lookup"><span data-stu-id="12889-215">**IP advertisement and NAT in use**</span></span> <br/> |<span data-ttu-id="12889-216">**網際網路路徑/來源 NAT**： 1.1.1.0/24</span><span class="sxs-lookup"><span data-stu-id="12889-216">**Internet path/Source NAT**: 1.1.1.0/24</span></span>  <br/> <span data-ttu-id="12889-217">**ExpressRoute 路徑/來源 NAT**： 1.1.2.0/24 (芝加哥) 和 1.1.3.0/24 (達拉斯) </span><span class="sxs-lookup"><span data-stu-id="12889-217">**ExpressRoute path/Source NAT**: 1.1.2.0/24 (Chicago) and 1.1.3.0/24 (Dallas)</span></span>  <br/> |
|<span data-ttu-id="12889-218">**Connectivity 方法**</span><span class="sxs-lookup"><span data-stu-id="12889-218">**Connectivity method**</span></span> <br/> |<span data-ttu-id="12889-219">**Internet**： via layer 7 proxy ( 的 pac 檔案) </span><span class="sxs-lookup"><span data-stu-id="12889-219">**Internet**: via layer 7 proxy (.pac file)</span></span>  <br/> <span data-ttu-id="12889-220">**ExpressRoute**：直接路由 (沒有 proxy) </span><span class="sxs-lookup"><span data-stu-id="12889-220">**ExpressRoute**: direct routing (no proxy)</span></span>  <br/> |
|<span data-ttu-id="12889-221">**安全性/周邊控制**</span><span class="sxs-lookup"><span data-stu-id="12889-221">**Security/Perimeter Controls**</span></span> <br/> |<span data-ttu-id="12889-222">**網際網路路徑**： DeviceID_002</span><span class="sxs-lookup"><span data-stu-id="12889-222">**Internet path**: DeviceID_002</span></span>  <br/> <span data-ttu-id="12889-223">**ExpressRoute 路徑**： DeviceID_003</span><span class="sxs-lookup"><span data-stu-id="12889-223">**ExpressRoute path**: DeviceID_003</span></span>  <br/> |
|<span data-ttu-id="12889-224">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="12889-224">**High Availability**</span></span> <br/> |<span data-ttu-id="12889-225">**網際網路路徑**：重複的網際網路出局</span><span class="sxs-lookup"><span data-stu-id="12889-225">**Internet path**: Redundant internet egress</span></span>  <br/> <span data-ttu-id="12889-226">**ExpressRoute 路徑**：跨2地理位置冗余 ExpressRoute 電路-芝加哥和達拉斯的主動/主動 ' 熱刷」路由</span><span class="sxs-lookup"><span data-stu-id="12889-226">**ExpressRoute path**: Active/Active 'hot potato' routing across 2 geo-redundant ExpressRoute circuits - Chicago and Dallas</span></span>  <br/> |
|<span data-ttu-id="12889-227">**路徑對稱控制**</span><span class="sxs-lookup"><span data-stu-id="12889-227">**Path symmetry control**</span></span> <br/> |<span data-ttu-id="12889-228">**方法**：所有連接的來源 NAT</span><span class="sxs-lookup"><span data-stu-id="12889-228">**Method**: Source NAT for all connections</span></span>  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a><span data-ttu-id="12889-229">您的網路拓撲設計與區域連通性</span><span class="sxs-lookup"><span data-stu-id="12889-229">Your network topology design with regional connectivity</span></span>
<span data-ttu-id="12889-230"><a name="topology"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-230"><a name="topology"> </a></span></span>

<span data-ttu-id="12889-231">在您瞭解服務及其相關的網路流量流程之後，您可以建立一個網狀圖，以包含這些新的連線需求，並說明您將使用 ExpressRoute Office 365 的變更。</span><span class="sxs-lookup"><span data-stu-id="12889-231">Once you understand the services and their associated network traffic flows, you can create a network diagram that incorporates these new connectivity requirements and illustrates the changes you'll make to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="12889-232">您的圖表應包含：</span><span class="sxs-lookup"><span data-stu-id="12889-232">Your diagram should include:</span></span>
  
1. <span data-ttu-id="12889-233">將從其存取 Office 365 和其他服務的所有使用者位置。</span><span class="sxs-lookup"><span data-stu-id="12889-233">All user locations where Office 365 and other services will be accessed from.</span></span>

2. <span data-ttu-id="12889-234">所有網際網路和 ExpressRoute 出局點數。</span><span class="sxs-lookup"><span data-stu-id="12889-234">All internet and ExpressRoute egress points.</span></span>

3. <span data-ttu-id="12889-235">所有用來管理網路連線的輸出和輸入裝置（包括路由器、防火牆、應用程式 proxy 伺服器及入侵偵測/防護）。</span><span class="sxs-lookup"><span data-stu-id="12889-235">All outbound and inbound devices that manage connectivity in and out of the network, including routers, firewalls, application proxy servers, and intrusion detection/prevention.</span></span>

4. <span data-ttu-id="12889-236">所有輸入流量的內部目的地，例如接受來自 ADFS web 應用程式 proxy 伺服器之連線的內部 ADFS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="12889-236">Internal destinations for all inbound traffic, such as internal ADFS servers that accept connections from the ADFS web application proxy servers.</span></span>

5. <span data-ttu-id="12889-237">將要宣告之所有 IP 子網的目錄</span><span class="sxs-lookup"><span data-stu-id="12889-237">Catalog of all IP subnets that will be advertised</span></span>

6. <span data-ttu-id="12889-238">識別每個人員存取 Office 365 的位置，並列出將用於 ExpressRoute 的「搜尋」位置。</span><span class="sxs-lookup"><span data-stu-id="12889-238">Identify each location where people will access Office 365 from and list the meet-me locations that will be used for ExpressRoute.</span></span>

7. <span data-ttu-id="12889-239">內部網路拓撲的位置和部分，在此拓撲中，會接受、篩選和傳播從 ExpressRoute 獲知的 Microsoft IP 首碼。</span><span class="sxs-lookup"><span data-stu-id="12889-239">Locations and portions of your internal network topology, where Microsoft IP prefixes learned from ExpressRoute will be accepted, filtered and propagated to.</span></span>

8. <span data-ttu-id="12889-240">網路拓撲應該會說明每個網路部分的地理位置，以及它如何透過 ExpressRoute 和/或網際網路連線至 Microsoft 網路。</span><span class="sxs-lookup"><span data-stu-id="12889-240">The network topology should illustrate the geographic location of each network segment and how it connects to the Microsoft network over ExpressRoute and/or the Internet.</span></span>

<span data-ttu-id="12889-241">下圖顯示每個使用者使用 Office 365 的位置，以及輸入和輸出路由播發至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="12889-241">The diagram below shows each location where people will be using Office 365 from along with the inbound and outbound routing advertisements to Office 365.</span></span>
  
![ExpressRoute 地區地理位置](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
<span data-ttu-id="12889-243">對於輸出流量，使用者會以下列三種方式之一存取 Office 365：</span><span class="sxs-lookup"><span data-stu-id="12889-243">For outbound traffic, the people access Office 365 in one of three ways:</span></span>
  
1. <span data-ttu-id="12889-244">透過北美地區的 [會見-me] 位置來為加州人員提供人員。</span><span class="sxs-lookup"><span data-stu-id="12889-244">Through a meet-me location in North America for the people in California.</span></span>

2. <span data-ttu-id="12889-245">透過香港中的「會見-我」地區的位置，為香港使用者。</span><span class="sxs-lookup"><span data-stu-id="12889-245">Through a meet-me location in Hong Kong for the people in Hong Kong.</span></span>

3. <span data-ttu-id="12889-246">透過來自孟加拉的人員，而不會有較少的人員，也沒有布建 ExpressRoute 電路。</span><span class="sxs-lookup"><span data-stu-id="12889-246">Through the internet in Bangladesh where there are fewer people and no ExpressRoute circuit provisioned.</span></span>

![區域圖表的輸出連線](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
<span data-ttu-id="12889-248">同樣地，來自 Office 365 的輸入網路流量會以下列其中一種方式傳回：</span><span class="sxs-lookup"><span data-stu-id="12889-248">Similarly, the inbound network traffic from Office 365 returns in one of three ways:</span></span>
  
1. <span data-ttu-id="12889-249">透過北美地區的 [會見-me] 位置來為加州人員提供人員。</span><span class="sxs-lookup"><span data-stu-id="12889-249">Through a meet-me location in North America for the people in California.</span></span>

2. <span data-ttu-id="12889-250">透過香港中的「會見-我」地區的位置，為香港使用者。</span><span class="sxs-lookup"><span data-stu-id="12889-250">Through a meet-me location in Hong Kong for the people in Hong Kong.</span></span>

3. <span data-ttu-id="12889-251">透過來自孟加拉的人員，而不會有較少的人員，也沒有布建 ExpressRoute 電路。</span><span class="sxs-lookup"><span data-stu-id="12889-251">Through the internet in Bangladesh where there are fewer people and no ExpressRoute circuit provisioned.</span></span>

![區域圖表的輸入連接](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a><span data-ttu-id="12889-253">決定適當的 [符合我的位置] 位置</span><span class="sxs-lookup"><span data-stu-id="12889-253">Determine the appropriate meet-me location</span></span>

<span data-ttu-id="12889-254">您可以選擇 [符合我的位置] （即您的 ExpressRoute 電路將您的網路連線至 Microsoft 網路的實體位置），受到人員存取 Office 365 的位置影響。</span><span class="sxs-lookup"><span data-stu-id="12889-254">The selection of meet-me locations, which are the physical location where your ExpressRoute circuit connects your network to the Microsoft network, is influenced by the locations where people will access Office 365 from.</span></span> <span data-ttu-id="12889-255">SaaS 方案中，Office 365 不會在 IaaS 或 PaaS 區域模式下運作，其方式與 Azure 相同。</span><span class="sxs-lookup"><span data-stu-id="12889-255">As a SaaS offering, Office 365 does not operate under the IaaS or PaaS regional model in the same way Azure does.</span></span> <span data-ttu-id="12889-256">相反地，Office 365 是一組分散式服務，其中的使用者可能需要跨多個資料中心及地區連接端點，而且不一定位於使用者租使用者所在的相同位置或地區。</span><span class="sxs-lookup"><span data-stu-id="12889-256">Instead, Office 365 is a distributed set of collaboration services, where users may need to connect to endpoints across multiple datacenters and regions, which may not necessarily be in the same location or region where the user's tenant is hosted.</span></span>
  
<span data-ttu-id="12889-257">這表示當您為 Office 365 選取 [符合我的位置] 時，您需要進行的最重要考慮，您的組織中的人員將從該 ExpressRoute 位置進行連接。</span><span class="sxs-lookup"><span data-stu-id="12889-257">This means the most important consideration you need to make when selecting meet-me locations for ExpressRoute for Office 365 is where the people in your organization will be connecting from.</span></span> <span data-ttu-id="12889-258">最佳的 Office 365 連線功能的一般建議是實施路由傳送，這樣一來，Office 365 服務的使用者要求會透過最短的網路路徑傳送至 Microsoft 網路，也通常稱為「熱刷」路由。</span><span class="sxs-lookup"><span data-stu-id="12889-258">The general recommendation for optimal Office 365 connectivity is implement routing, so that user requests to Office 365 services are handed off into the Microsoft network over the shortest network path, this is also often being referred to as 'hot potato' routing.</span></span> <span data-ttu-id="12889-259">例如，如果大部分的 Office 365 使用者位於一或兩個位置，選取 [符合我的位置] 最接近于這些使用者位置最接近的位置，將會建立最佳設計。</span><span class="sxs-lookup"><span data-stu-id="12889-259">For example, if most of the Office 365 users are in one or two locations, selecting meet-me locations that are in the closest proximity to the location of those users will create the optimal design.</span></span> <span data-ttu-id="12889-260">如果您的公司在許多不同的地區都有大量使用者人口，您可能想要考慮有多個 ExpressRoute 電路，並符合我的場所。</span><span class="sxs-lookup"><span data-stu-id="12889-260">If your company has large user populations in many different regions, you may want to consider having multiple ExpressRoute circuits and meet-me locations.</span></span> <span data-ttu-id="12889-261">針對您的某些使用者位置，Microsoft 網路和 Office 365 中最短/最適合的路徑，可能不會透過您的內部 WAN 和 ExpressRoute 符合您的內部網路點，但透過網際網路獲得。</span><span class="sxs-lookup"><span data-stu-id="12889-261">For some of your user locations, the shortest/most optimal path into Microsoft network and Office 365, may not be through your internal WAN and ExpressRoute meet-me points, but via the Internet.</span></span>
  
<span data-ttu-id="12889-262">這通常會有多個可在與您的使用者相對應的區域內選取的 [符合 me] 位置。</span><span class="sxs-lookup"><span data-stu-id="12889-262">Often times, there are multiple meet-me locations that could be selected within a region with relative proximity to your users.</span></span> <span data-ttu-id="12889-263">填寫下表以引導您的決策。</span><span class="sxs-lookup"><span data-stu-id="12889-263">Fill out the following table to guide your decisions.</span></span>

|<span data-ttu-id="12889-264">**在加州和紐約的計畫 ExpressRoute 符合我的場所**</span><span class="sxs-lookup"><span data-stu-id="12889-264">**Planned ExpressRoute meet-me locations in California and New York**</span></span>||
|:-----|:-----|
|<span data-ttu-id="12889-265">位置</span><span class="sxs-lookup"><span data-stu-id="12889-265">Location</span></span>  <br/> |<span data-ttu-id="12889-266">人員人數</span><span class="sxs-lookup"><span data-stu-id="12889-266">Number of people</span></span>  <br/> |<span data-ttu-id="12889-267">透過網際網路出局對 Microsoft 網路的預期延遲</span><span class="sxs-lookup"><span data-stu-id="12889-267">Expected latency to Microsoft network over Internet egress</span></span>  <br/> |<span data-ttu-id="12889-268">對 ExpressRoute 的 Microsoft 網路的預期延遲</span><span class="sxs-lookup"><span data-stu-id="12889-268">Expected latency to Microsoft network over ExpressRoute</span></span>  <br/> |
|<span data-ttu-id="12889-269">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="12889-269">Los Angeles</span></span>  <br/> |<span data-ttu-id="12889-270">10,000</span><span class="sxs-lookup"><span data-stu-id="12889-270">10,000</span></span>  <br/> |<span data-ttu-id="12889-271">~ 15ms</span><span class="sxs-lookup"><span data-stu-id="12889-271">~15ms</span></span>  <br/> |<span data-ttu-id="12889-272">~ 10ms (經由矽谷) </span><span class="sxs-lookup"><span data-stu-id="12889-272">~10ms (via Silicon Valley)</span></span>  <br/> |
|<span data-ttu-id="12889-273">華盛頓</span><span class="sxs-lookup"><span data-stu-id="12889-273">Washington DC</span></span>  <br/> |<span data-ttu-id="12889-274">15,000</span><span class="sxs-lookup"><span data-stu-id="12889-274">15,000</span></span>  <br/> |<span data-ttu-id="12889-275">~ 20 毫秒</span><span class="sxs-lookup"><span data-stu-id="12889-275">~20ms</span></span>  <br/> |<span data-ttu-id="12889-276">~ 10ms 透過紐約 () </span><span class="sxs-lookup"><span data-stu-id="12889-276">~10ms (via New York)</span></span>  <br/> |
|<span data-ttu-id="12889-277">達拉斯</span><span class="sxs-lookup"><span data-stu-id="12889-277">Dallas</span></span>  <br/> |<span data-ttu-id="12889-278">5,000</span><span class="sxs-lookup"><span data-stu-id="12889-278">5,000</span></span>  <br/> |<span data-ttu-id="12889-279">~ 15ms</span><span class="sxs-lookup"><span data-stu-id="12889-279">~15ms</span></span>  <br/> |<span data-ttu-id="12889-280">~ 40ms 透過紐約 () </span><span class="sxs-lookup"><span data-stu-id="12889-280">~40ms (via New York)</span></span>  <br/> |

<span data-ttu-id="12889-281">在顯示 Office 365 地區的全域網路架構之後，ExpressRoute 網路服務提供者的 [符合我的位置]，以及 [依位置排列的人員數量]，可以用來識別是否可以進行任何優化。</span><span class="sxs-lookup"><span data-stu-id="12889-281">Once the global network architecture showing the Office 365 region, ExpressRoute network service provider meet-me locations, and the quantity of people by location has been developed, it can be used to identify if any optimizations can be made.</span></span> <span data-ttu-id="12889-282">它也可能會顯示全域髮夾網路連線，其中的流量會路由傳送到遠處的位置，以便取得「我的位置」的位置。</span><span class="sxs-lookup"><span data-stu-id="12889-282">It may also show global hairpin network connections where traffic routes to a distant location in order to get the meet-me location.</span></span> <span data-ttu-id="12889-283">如果已探索全域網路上的髮夾，則應該先修正此，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="12889-283">If a hairpin on the global network is discovered it should be remediated before continuing.</span></span> <span data-ttu-id="12889-284">請找到另一個 [符合我的位置] 位置，或使用選擇性的網際網路專題討論顯示點，以避免髮夾。</span><span class="sxs-lookup"><span data-stu-id="12889-284">Either find another meet-me location, or use selective Internet breakout egress points to avoid the hairpin.</span></span>
  
<span data-ttu-id="12889-285">第一個圖表顯示一份客戶的範例，其中包含北美地區的兩個實體位置。</span><span class="sxs-lookup"><span data-stu-id="12889-285">The first diagram, shows an example of a customer with two physical locations in North America.</span></span> <span data-ttu-id="12889-286">您可以查看 office 位置、Office 365 租使用者位置的相關資訊，以及數個 ExpressRoute 的符合 me 位置的選項。</span><span class="sxs-lookup"><span data-stu-id="12889-286">You can see the information about office locations, Office 365 tenant locations, and several choices for ExpressRoute meet-me locations.</span></span> <span data-ttu-id="12889-287">在此範例中，客戶根據兩項原則選取 [符合我的位置]，順序如下：</span><span class="sxs-lookup"><span data-stu-id="12889-287">In this example, the customer has selected the meet-me location based on two principles, in order:</span></span>
  
1. <span data-ttu-id="12889-288">最接近組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="12889-288">Closest proximity to the people in their organization.</span></span>

2. <span data-ttu-id="12889-289">最接近于主控 Office 365 的 Microsoft 資料中心的鄰近性。</span><span class="sxs-lookup"><span data-stu-id="12889-289">Closest in proximity to a Microsoft datacenter where Office 365 is hosted.</span></span>

![ExpressRoute US 地理位置會見-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
<span data-ttu-id="12889-291">進一步擴充此概念，第二個圖表會顯示一個包含類似資訊和決策過程的多國客戶的範例。</span><span class="sxs-lookup"><span data-stu-id="12889-291">Expanding this concept slightly further, the second diagram shows an example multi-national customer faced with similar information and decision making.</span></span> <span data-ttu-id="12889-292">此客戶在孟加拉的小型辦公室中，只有十個人的小小組，專注于在地區內成長其足跡。</span><span class="sxs-lookup"><span data-stu-id="12889-292">This customer has a small office in Bangladesh with only a small team of ten people focused on growing their footprint in the region.</span></span> <span data-ttu-id="12889-293">Chennai 中有一個 [符合我的位置] 和 Chennai 中主控 Office 365 的 Microsoft 資料中心，因此符合 me 的位置很有意義;不過，如果是10位人員，額外電路的費用會非常繁重。</span><span class="sxs-lookup"><span data-stu-id="12889-293">There is a meet-me location in Chennai and a Microsoft datacenter with Office 365 hosted in Chennai so a meet-me location would make sense; however, for ten people, the expense of the additional circuit is burdensome.</span></span> <span data-ttu-id="12889-294">當您查看網路時，您需要判斷在網路中傳送網路流量所涉及的延遲，是否比花資本以取得另一部 ExpressRoute 電路更有效。</span><span class="sxs-lookup"><span data-stu-id="12889-294">As you look at your network, you'll need to determine if the latency involved in sending your network traffic across your network is more effective than spending the capital to acquire another ExpressRoute circuit.</span></span>
  
<span data-ttu-id="12889-295">或者，在透過網際網路傳送至 Microsoft 網路的網路流量透過網際網路傳送至其內部網路的網路流量，在下列情況下所述，其他孟加拉的使用者可能會體驗更好的效能。</span><span class="sxs-lookup"><span data-stu-id="12889-295">Alternatively, the ten people in Bangladesh may experience better performance with their network traffic sent over the internet to the Microsoft network than they would routing on their internal network as we showed in the introductory diagrams and reproduced below.</span></span>
  
![區域圖表的輸出連線](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a><span data-ttu-id="12889-297">建立 Office 365 實施方案的 ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="12889-297">Create your ExpressRoute for Office 365 implementation plan</span></span>
<span data-ttu-id="12889-298"><a name="implementation"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-298"><a name="implementation"> </a></span></span>

<span data-ttu-id="12889-299">您的實施計畫應該同時包含設定 ExpressRoute 的技術詳細資料，以及在網路上設定其他所有基礎結構的詳細資料，如下所示。</span><span class="sxs-lookup"><span data-stu-id="12889-299">Your implementation plan should encompass both the technical details of configuring ExpressRoute as well as the details of configuring all the other infrastructure on your network, such as the following.</span></span>
  
- <span data-ttu-id="12889-300">規劃在 ExpressRoute 和網際網路之間分割的服務。</span><span class="sxs-lookup"><span data-stu-id="12889-300">Plan which services split between ExpressRoute and Internet.</span></span>

- <span data-ttu-id="12889-301">規劃頻寬、安全性、高可用性和容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="12889-301">Plan for bandwidth, security, high availability and failover.</span></span>

- <span data-ttu-id="12889-302">設計輸入和輸出路由，包含不同位置的適當路由路徑優化</span><span class="sxs-lookup"><span data-stu-id="12889-302">Design inbound and outbound routing, including proper routing path optimizations for different locations</span></span>

- <span data-ttu-id="12889-303">決定要將哪些 ExpressRoute 路由宣告到您的網路中，以及用戶端選擇網際網路或 ExpressRoute 路徑的機制為何;例如，direct routing 或 application proxy。</span><span class="sxs-lookup"><span data-stu-id="12889-303">Decide how far ExpressRoute routes will be advertised into your network and what is the mechanism for clients to select Internet or ExpressRoute path; for example, direct routing or application proxy.</span></span>

- <span data-ttu-id="12889-304">規劃 DNS 記錄變更，包括 [寄件者原則架構](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx) 專案。</span><span class="sxs-lookup"><span data-stu-id="12889-304">Plan DNS record changes, including [Sender Policy Framework](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx) entries.</span></span>

- <span data-ttu-id="12889-305">規劃 NAT 策略（包括輸出和輸入來源 NAT）。</span><span class="sxs-lookup"><span data-stu-id="12889-305">Plan NAT strategy including outbound and inbound source NAT.</span></span>

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a><span data-ttu-id="12889-306">規劃使用網際網路和 ExpressRoute 網路路徑的路由</span><span class="sxs-lookup"><span data-stu-id="12889-306">Plan your routing with both internet and ExpressRoute network paths</span></span>
<span data-ttu-id="12889-307"><a name="paths"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-307"><a name="paths"> </a></span></span>

- <span data-ttu-id="12889-308">針對您的初始部署，建議使用網際網路的所有輸入服務（例如輸入電子郵件或混合式連線）。</span><span class="sxs-lookup"><span data-stu-id="12889-308">For your initial deployment, all inbound services, such as inbound email or hybrid connectivity, are recommended to use the internet.</span></span>

- <span data-ttu-id="12889-309">規劃使用者用戶端 LAN 路由，例如設定 [PAC/WPAD](https://aka.ms/manageo365endpoints)檔案、預設路由、proxy 伺服器和 BGP 路由播發。</span><span class="sxs-lookup"><span data-stu-id="12889-309">Plan end user client LAN routing, such as [configuring a PAC/WPAD file](https://aka.ms/manageo365endpoints), default route, proxy servers, and BGP route advertisements.</span></span>

- <span data-ttu-id="12889-310">規劃周邊路由，包括 proxy 伺服器、防火牆和雲端 proxy。</span><span class="sxs-lookup"><span data-stu-id="12889-310">Plan perimeter routing, including proxy servers, firewalls, and cloud proxies.</span></span>

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a><span data-ttu-id="12889-311">規劃頻寬、安全性、高可用性和容錯移轉</span><span class="sxs-lookup"><span data-stu-id="12889-311">Plan your bandwidth, security, high availability and failover</span></span>
<span data-ttu-id="12889-312"><a name="availability"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-312"><a name="availability"> </a></span></span>

<span data-ttu-id="12889-313">針對每個主要 Office 365 工作負載，建立所需頻寬的計畫。</span><span class="sxs-lookup"><span data-stu-id="12889-313">Create a plan for bandwidth required for each major Office 365 workload.</span></span> <span data-ttu-id="12889-314">分別評估 Exchange Online、SharePoint 線上和商務用 Skype Online 頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="12889-314">Separately estimate Exchange Online, SharePoint Online, and Skype for Business Online bandwidth requirements.</span></span> <span data-ttu-id="12889-315">您可以使用我們為 Exchange Online 和商務用 Skype 所提供的評估計算機做為開始地點;不過，使用使用者設定檔和位置的具有代表性範例的試驗測試，必須充分瞭解貴組織的頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="12889-315">You can use the estimation calculators we've provided for Exchange Online and Skype for Business as a starting place; however, a pilot test with a representative sample of the user profiles and locations is required to fully understand the bandwidth needs of your organization.</span></span>
  
<span data-ttu-id="12889-316">新增如何處理每個網際網路的安全性和 ExpressRoute 外接位置，請記住 Office 365 的所有 ExpressRoute 連線都使用 public 對等方式，而且仍然必須根據公司的安全性原則（連接至外部網路）加以保護。</span><span class="sxs-lookup"><span data-stu-id="12889-316">Add how security is handled at each internet and ExpressRoute egress location to your plan, remember all ExpressRoute connections to Office 365 use public peering and must still be secured in accordance with your company security policies of connecting to external networks.</span></span>
  
<span data-ttu-id="12889-317">針對您的計畫新增詳細資料，以瞭解哪些人員將會受到哪種類型的中斷影響，以及哪些人員能夠以最簡單的方式執行其工作。</span><span class="sxs-lookup"><span data-stu-id="12889-317">Add details to your plan about which people will be affected by what type of outage and how those people will be able to perform their work at full capacity in the simplest manner.</span></span>
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a><span data-ttu-id="12889-318">規劃頻寬需求，包括抖動、延遲、擁塞和餘地上的商務用 Skype 需求</span><span class="sxs-lookup"><span data-stu-id="12889-318">Plan bandwidth requirements including Skype for Business requirements on Jitter, Latency, Congestion, and Headroom</span></span>
  
<span data-ttu-id="12889-319">商務用 skype Online 也有特定額外的網路需求，這些需求會在文章 [媒體質量與商務用 Skype Online 的網路連線效能](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="12889-319">Skype for Business Online also has specific additional network requirements which are detailed in the article [Media Quality and Network Connectivity Performance in Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).</span></span>
  
<span data-ttu-id="12889-320">請參閱[使用 Office 365 ExpressRoute 的網路規劃](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的**Azure ExpressRoute Azure 規劃的章節頻寬規劃**。</span><span class="sxs-lookup"><span data-stu-id="12889-320">Read the section **Bandwidth planning for Azure ExpressRoute** in [Network planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).</span></span>
  
<span data-ttu-id="12889-321">當您的試驗使用者執行頻寬評估時，您可以使用我們的指南。 [使用基準和效能歷程記錄的 Office 365 效能調整](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)。</span><span class="sxs-lookup"><span data-stu-id="12889-321">When performing a bandwidth assessment with your pilot users, you can use our guide; [Office 365 performance tuning using baselines and performance history](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).</span></span>
  
#### <a name="plan-for-high-availability-requirements"></a><span data-ttu-id="12889-322">規劃高可用性需求</span><span class="sxs-lookup"><span data-stu-id="12889-322">Plan for high availability requirements</span></span>
  
<span data-ttu-id="12889-323">建立高可用性的計畫，以符合您的需求，並將此方案併入更新的網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="12889-323">Create a plan for high availability to meet your needs and incorporate this into your updated network topology diagram.</span></span> <span data-ttu-id="12889-324">[使用 Office 365 ExpressRoute 的網路規劃](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的 Azure ExpressRoute，閱讀本節**高可用性和容錯移轉**。</span><span class="sxs-lookup"><span data-stu-id="12889-324">Read the section **High availability and failover with Azure ExpressRoute** in [Network planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).</span></span>
  
#### <a name="plan-for-network-security-requirements"></a><span data-ttu-id="12889-325">規劃網路安全性需求</span><span class="sxs-lookup"><span data-stu-id="12889-325">Plan for network security requirements</span></span>
  
<span data-ttu-id="12889-326">建立符合網路安全性需求的計畫，並將此方案併入更新的網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="12889-326">Create a plan to meet your network security requirements and incorporate this into your updated network topology diagram.</span></span> <span data-ttu-id="12889-327">閱讀[使用 office 365 ExpressRoute 的網路規劃](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中，將**安全性控制套用至 Azure ExpressRoute for office 365 案例**的章節。</span><span class="sxs-lookup"><span data-stu-id="12889-327">Read the section **Applying security controls to Azure ExpressRoute for Office 365 scenarios** in [Network planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).</span></span>
  
### <a name="design-outbound-service-connectivity"></a><span data-ttu-id="12889-328">設計輸出服務連線</span><span class="sxs-lookup"><span data-stu-id="12889-328">Design outbound service connectivity</span></span>
<span data-ttu-id="12889-329"><a name="outbound"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-329"><a name="outbound"> </a></span></span>

<span data-ttu-id="12889-330">ExpressRoute Office 365 具有可能不熟悉的  *輸出*  網路需求。</span><span class="sxs-lookup"><span data-stu-id="12889-330">ExpressRoute for Office 365 has  *outbound*  network requirements that may be unfamiliar.</span></span> <span data-ttu-id="12889-331">尤其是，將使用者和網路對應至 Office 365 的 IP 位址，並做為到 Microsoft 的輸出網路連線的來源端點，必須遵循下列所述的特定需求。</span><span class="sxs-lookup"><span data-stu-id="12889-331">Specifically, the IP addresses that represent your users and networks to Office 365 and act as the source endpoints for outbound network connections to Microsoft must follow specific requirements outlined below.</span></span>
  
1. <span data-ttu-id="12889-332">端點必須是公用 IP 位址，已註冊至您的公司或電信公司，可提供給您的 ExpressRoute 連線能力。</span><span class="sxs-lookup"><span data-stu-id="12889-332">The endpoints must be public IP addresses, that are registered to your company or to carrier providing ExpressRoute connectivity to you.</span></span>

2. <span data-ttu-id="12889-333">端點必須透過 ExpressRoute 播發及驗證/認可。</span><span class="sxs-lookup"><span data-stu-id="12889-333">The endpoints must be advertised to Microsoft and validated/accepted by ExpressRoute.</span></span>

3. <span data-ttu-id="12889-334">端點不能透過相同或更喜歡的路由躍點數宣告至網際網路。</span><span class="sxs-lookup"><span data-stu-id="12889-334">The endpoints must not be advertised to the Internet with the same or more preferred routing metric.</span></span>

4. <span data-ttu-id="12889-335">端點不得用於連線至未透過 ExpressRoute 設定的 Microsoft 服務。</span><span class="sxs-lookup"><span data-stu-id="12889-335">The endpoints must not be used for connectivity to Microsoft services that are not configured over ExpressRoute.</span></span>

<span data-ttu-id="12889-336">如果您的網路設計不符合這些需求，則由於路由黑色 holing 或非對稱路由，您的使用者可能會在 Office 365 和其他 Microsoft 服務上遇到連線失敗的危險。</span><span class="sxs-lookup"><span data-stu-id="12889-336">If your network design doesn't meet these requirements, there is a high risk your users will experience connectivity failures to Office 365 and other Microsoft services due to route black holing or asymmetric routing.</span></span> <span data-ttu-id="12889-337">當對 Microsoft 服務的要求透過 ExpressRoute 路由傳送時，會發生此情況，但回應會透過網際網路路由傳送回來，反之亦然，回應會被狀態網路裝置（例如防火牆）中斷。</span><span class="sxs-lookup"><span data-stu-id="12889-337">This occurs when requests to Microsoft services are routed over ExpressRoute, but responses are routed back across the internet, or vice versa, and the responses are dropped by stateful network devices such as firewalls.</span></span>
  
<span data-ttu-id="12889-338">您可以用來符合上述需求的最常見方法，就是使用來源 NAT，以作為網路的一部分，或由您的 ExpressRoute 載體所提供。</span><span class="sxs-lookup"><span data-stu-id="12889-338">The most common method you can use to meet the above requirements is to use source NAT, either implemented as a part of your network or provided by your ExpressRoute carrier.</span></span> <span data-ttu-id="12889-339">來源 NAT 可讓您從 ExpressRoute 摘要網際網路網路的詳細資料和私人 IP 位址，以及結合適當的 IP 路由通告，提供一種簡易的機制，以確保路徑對稱。</span><span class="sxs-lookup"><span data-stu-id="12889-339">Source NAT allows you to abstract the details and private IP addressing of your internet network from ExpressRoute and; coupled with proper IP route advertisements, provide an easy mechanism to ensure path symmetry.</span></span> <span data-ttu-id="12889-340">如果您使用 ExpressRoute 對等位置特有的狀態網路裝置，則必須針對每個 ExpressRoute 對等位置執行個別的 NAT 集區，以確保路徑對稱。</span><span class="sxs-lookup"><span data-stu-id="12889-340">If you're using stateful network devices that are specific to ExpressRoute peering locations, you must implement separate NAT pools for each ExpressRoute peering to ensure path symmetry.</span></span>
  
<span data-ttu-id="12889-341">如需詳細資訊，請參閱 [EXPRESSROUTE NAT 需求](https://azure.microsoft.com/documentation/articles/expressroute-nat/)。</span><span class="sxs-lookup"><span data-stu-id="12889-341">Read more about the [ExpressRoute NAT requirements](https://azure.microsoft.com/documentation/articles/expressroute-nat/).</span></span>
  
<span data-ttu-id="12889-342">將輸出連線的變更新增至網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="12889-342">Add the changes for the outbound connectivity to the network topology diagram.</span></span>
  
### <a name="design-inbound-service-connectivity"></a><span data-ttu-id="12889-343">設計輸入服務連線</span><span class="sxs-lookup"><span data-stu-id="12889-343">Design inbound service connectivity</span></span>
<span data-ttu-id="12889-344"><a name="inbound"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-344"><a name="inbound"> </a></span></span>

<span data-ttu-id="12889-345">大部分的 enterprise Office 365 部署會假設某些形式的來自 Office 365 的輸入連線至內部部署服務，例如用於 Exchange、SharePoint 和商務用 Skype 混合式案例、信箱遷移，以及使用 ADFS 基礎結構進行驗證。</span><span class="sxs-lookup"><span data-stu-id="12889-345">The majority of enterprise Office 365 deployments assume some form of inbound connectivity from Office 365 to on-premises services, such as for Exchange, SharePoint, and Skype for Business hybrid scenarios, mailbox migrations, and authentication using ADFS infrastructure.</span></span> <span data-ttu-id="12889-346">當您在內部部署網路與 Microsoft 之間啟用額外的路由路徑，以進行輸出連線 ExpressRoute 時，即使您想要讓這些流程繼續使用網際網路，這些輸入連線可能會不慎受到非對稱路由的影響。</span><span class="sxs-lookup"><span data-stu-id="12889-346">When ExpressRoute you enable an additional routing path between your on-premises network and Microsoft for outbound connectivity, these inbound connections may inadvertently be impacted by asymmetric routing, even if you intend to have those flows continue to use the Internet.</span></span> <span data-ttu-id="12889-347">建議如下所述的防範措施，以確保從 Office 365 至內部部署系統的網際網路輸入流量沒有任何影響。</span><span class="sxs-lookup"><span data-stu-id="12889-347">A few precautions described below are recommended to ensure there is no impact to Internet based inbound flows from Office 365 to on-premises systems.</span></span>
  
<span data-ttu-id="12889-348">若要降低輸入網路流量流程的非對稱路由風險，所有的輸入連線都應該先使用來源 NAT，然後才會將其路由傳送至您的網路網段，使其可在 ExpressRoute 中進行路由查看。</span><span class="sxs-lookup"><span data-stu-id="12889-348">To minimize the risks of asymmetric routing for inbound network traffic flows, all of the inbound connections should use source NAT before they're routed into segments of your network which have routing visibility into ExpressRoute.</span></span> <span data-ttu-id="12889-349">如果允許傳入連線到具有路由 ExpressRoute 可視性的網段，但沒有來源 NAT，來自 Office 365 的要求會進入網際網路，但是回到 Office 365 的回應將優先于 ExpressRoute 網路路徑回到 Microsoft 網路，造成不對稱的路由。</span><span class="sxs-lookup"><span data-stu-id="12889-349">If the incoming connections are allowed onto a network segment with routing visibility into ExpressRoute without source NAT, requests originating from Office 365 will enter from the internet, but the response going back to Office 365 will prefer the ExpressRoute network path back to the Microsoft network, causing asymmetric routing.</span></span>
  
<span data-ttu-id="12889-350">您可以考慮下列其中一個執行模式，以滿足這項需求：</span><span class="sxs-lookup"><span data-stu-id="12889-350">You may consider one of the following implementation patterns to satisfy this requirement:</span></span>
  
1. <span data-ttu-id="12889-351">在要求使用網路設備（例如防火牆或從網際網路到您的內部部署系統的負載平衡器）上的網路設備（例如防火牆或負載平衡器）路由進入內部網路之前，請先執行來源 NAT。</span><span class="sxs-lookup"><span data-stu-id="12889-351">Perform source NAT before requests are routed into your internal network using networking equipment such as firewalls or load balancers on the path from the Internet to your on-premises systems.</span></span>

2. <span data-ttu-id="12889-352">確定 ExpressRoute 路由不會傳播到輸入服務（例如前端伺服器或反向 proxy 系統）的網段，處理網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="12889-352">Ensure that ExpressRoute routes are not propagated to the network segments where inbound services, such as front end servers or reverse proxy systems, handling Internet connections reside.</span></span>

<span data-ttu-id="12889-353">針對您的網路中的這些案例明確會計，並保留透過網際網路的所有輸入網路流量，有助於將非對稱路由的部署和操作風險降至最低。</span><span class="sxs-lookup"><span data-stu-id="12889-353">Explicitly accounting for these scenarios in your network and keeping all inbound network traffic flows over the Internet helps to minimize deployment and operational risk of asymmetric routing.</span></span>
  
<span data-ttu-id="12889-354">在某些情況下，您可能會選擇透過 ExpressRoute 連線來引導某些輸入流量。</span><span class="sxs-lookup"><span data-stu-id="12889-354">There may be cases where you may choose to direct some inbound flows over ExpressRoute connections.</span></span> <span data-ttu-id="12889-355">在這些案例中，請採取下列其他考慮。</span><span class="sxs-lookup"><span data-stu-id="12889-355">For these scenarios, take the following additional considerations into account.</span></span>
  
1. <span data-ttu-id="12889-356">Office 365 只能針對使用公用 Ip 的內部部署端點。</span><span class="sxs-lookup"><span data-stu-id="12889-356">Office 365 can only target on-premises endpoints that use public IPs.</span></span> <span data-ttu-id="12889-357">這表示即使內部部署輸入端點只會透過 ExpressRoute 公開給 Office 365，仍然必須具有與其相關聯的公用 IP。</span><span class="sxs-lookup"><span data-stu-id="12889-357">This means that even if the on-premises inbound endpoint is only exposed to Office 365 over ExpressRoute, it still needs to have public IP associated with it.</span></span>

2. <span data-ttu-id="12889-358">Office 365 服務執行以解析內部部署端點的所有 DNS 名稱解析都是使用公用 DNS。</span><span class="sxs-lookup"><span data-stu-id="12889-358">All DNS name resolution that Office 365 services perform to resolve on-premises endpoints happen using public DNS.</span></span> <span data-ttu-id="12889-359">這表示您必須將輸入服務端點的 FQDN 註冊至網際網路上的 IP 對應。</span><span class="sxs-lookup"><span data-stu-id="12889-359">This means that you must register inbound service endpoints' FQDN to IP mappings on the Internet.</span></span>

3. <span data-ttu-id="12889-360">為了透過 ExpressRoute 接收輸入的網路連線，必須透過 ExpressRoute 將這些端點的公用 IP 子網宣告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="12889-360">In order to receive inbound network connections over ExpressRoute, the public IP subnets for these endpoints must to be advertised to Microsoft over ExpressRoute.</span></span>

4. <span data-ttu-id="12889-361">請仔細評估這些輸入網路流量流量，以確保依照公司的安全性和網路原則套用適當的安全性和網路控制項。</span><span class="sxs-lookup"><span data-stu-id="12889-361">Carefully evaluate these inbound network traffic flows to ensure that proper security and network controls are applied to them in accordance with your company security and network policies.</span></span>

5. <span data-ttu-id="12889-362">當您的內部部署輸入端點透過 ExpressRoute 播發至 Microsoft 時，ExpressRoute 會有效成為所有 Microsoft 服務之端點的首選路由路徑，包括 Office 365。</span><span class="sxs-lookup"><span data-stu-id="12889-362">Once your on-premises inbound endpoints are advertised to Microsoft over ExpressRoute, ExpressRoute will effectively become the preferred routing path to those endpoints for all Microsoft services, including Office 365.</span></span> <span data-ttu-id="12889-363">這表示這些端點子網必須只用于與 Office 365 服務的通訊，而不是 Microsoft 網路上的其他服務。</span><span class="sxs-lookup"><span data-stu-id="12889-363">This means that those endpoint subnets must only be used for communications with Office 365 services and no other services on the Microsoft network.</span></span> <span data-ttu-id="12889-364">否則，您的設計將會造成非對稱路由，來自其他 Microsoft 服務的輸入連線傾向于路由傳送輸入的 ExpressRoute，而傳回路徑會使用網際網路。</span><span class="sxs-lookup"><span data-stu-id="12889-364">Otherwise, your design will cause asymmetric routing where inbound connections from other Microsoft services prefer to route inbound over ExpressRoute, while the return path will use the Internet.</span></span>

6. <span data-ttu-id="12889-365">當 ExpressRoute 的電路或符合我的位置已停機時，您必須確定內部部署輸入端點仍可透過個別網路路徑接受要求。</span><span class="sxs-lookup"><span data-stu-id="12889-365">In the event an ExpressRoute circuit or meet-me location is down, you'll need to ensure the on-premises inbound endpoints are still available to accept requests over a separate network path.</span></span> <span data-ttu-id="12889-366">這可能表示透過多個 ExpressRoute 電路公佈這些端點的子網。</span><span class="sxs-lookup"><span data-stu-id="12889-366">This may mean advertising subnets for those endpoints through multiple ExpressRoute circuits.</span></span>

7. <span data-ttu-id="12889-367">建議您透過 ExpressRoute 為進入網路的所有輸入網路流量資料流程套用來源 NAT，尤其是當這些資料流程跨狀態網路裝置（例如防火牆）。</span><span class="sxs-lookup"><span data-stu-id="12889-367">We recommend applying source NAT for all inbound network traffic flows entering your network through ExpressRoute, especially when these flows cross stateful network devices such as firewalls.</span></span>

8. <span data-ttu-id="12889-368">有些內部部署服務（例如 ADFS proxy 或 Exchange 自動探索）可能會收到來自 Office 365 服務和使用者的來自網際網路的輸入要求。</span><span class="sxs-lookup"><span data-stu-id="12889-368">Some on-premises services, such as ADFS proxy or Exchange autodiscover, may receive inbound requests from both Office 365 services and users from the Internet.</span></span> <span data-ttu-id="12889-369">針對這些要求，Office 365 會將相同的 FQDN 與網際網路上的使用者要求進行目標。</span><span class="sxs-lookup"><span data-stu-id="12889-369">For these requests Office 365 will target the same FQDN as user requests over the Internet.</span></span> <span data-ttu-id="12889-370">允許從網際網路至內部部署端點的輸入使用者連線，同時強制使用 ExpressRoute 的 Office 365 連線，表示大量路由複雜性。</span><span class="sxs-lookup"><span data-stu-id="12889-370">Allowing inbound user connections from the internet to those on-premises endpoints, while forcing Office 365 connections to use ExpressRoute, represents significant routing complexity.</span></span> <span data-ttu-id="12889-371">對於絕大多數使用 ExpressRoute 執行這類複雜案例的客戶，由於運作考慮，所以不建議使用。</span><span class="sxs-lookup"><span data-stu-id="12889-371">For the vast majority of customers implementing such complex scenarios over ExpressRoute is not recommended due to operational considerations.</span></span> <span data-ttu-id="12889-372">這項額外的額外負荷包括管理非對稱路由的風險，而且會要求您認真管理跨多個維度的路由通告和原則。</span><span class="sxs-lookup"><span data-stu-id="12889-372">This additional overhead includes, managing risks of asymmetric routing and will require you to carefully manage routing advertisements and policies across multiple dimensions.</span></span>

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a><span data-ttu-id="12889-373">更新您的網路拓撲計畫，以顯示避免對稱路由的方式</span><span class="sxs-lookup"><span data-stu-id="12889-373">Update your network topology plan to show how you would avoid asymmetric routes</span></span>
<span data-ttu-id="12889-374"><a name="asymmetric"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-374"><a name="asymmetric"> </a></span></span>

<span data-ttu-id="12889-375">您想要避免使用不對稱的路由，以確保您組織中的人員能夠順利使用 Office 365 以及網際網路上的其他重要服務。</span><span class="sxs-lookup"><span data-stu-id="12889-375">You want to avoid asymmetric routing to ensure people in your organization can seamlessly use Office 365 as well as other important services on the internet.</span></span> <span data-ttu-id="12889-376">客戶有兩個常見設定可導致非對稱路由。</span><span class="sxs-lookup"><span data-stu-id="12889-376">There are two common configurations customers have that cause asymmetric routing.</span></span> <span data-ttu-id="12889-377">現在，請查看您計畫要使用的網路設定，並檢查是否有其中一個不對稱的路由案例可以存在。</span><span class="sxs-lookup"><span data-stu-id="12889-377">Now's a good time to review the network configuration you're planning to use and check if one of these asymmetric routing scenarios could exist.</span></span>
  
<span data-ttu-id="12889-378">為了開始，我們會檢查與下列網狀圖表相關的幾個不同情況。</span><span class="sxs-lookup"><span data-stu-id="12889-378">To begin, we'll examine a few different situations associated with the following network diagram.</span></span> <span data-ttu-id="12889-379">在此圖中，所有接收輸入要求的伺服器（例如，ADFS 或內部部署混合伺服器）皆位於新的 Jersey 資料中心，且會通告至網際網路。</span><span class="sxs-lookup"><span data-stu-id="12889-379">In this diagram, all servers that receive inbound requests, such as ADFS or on-premises hybrid servers are in the New Jersey data center and are advertised to the internet.</span></span>
  
1. <span data-ttu-id="12889-380">當周邊網路安全時，傳入要求沒有來源 NAT 可用。</span><span class="sxs-lookup"><span data-stu-id="12889-380">While the perimeter network is secure, there is no Source NAT available for incoming requests.</span></span>

2. <span data-ttu-id="12889-381">新 Jersey 資料中心的伺服器能夠同時查看網際網路和 ExpressRoute 路由。</span><span class="sxs-lookup"><span data-stu-id="12889-381">The servers in the New Jersey data center are able to see both internet and ExpressRoute routes.</span></span>

![ExpressRoute 連線能力概述](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
<span data-ttu-id="12889-383">我們也會針對如何修正這些問題提出建議。</span><span class="sxs-lookup"><span data-stu-id="12889-383">We also have suggestions on how to fix them.</span></span>
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a><span data-ttu-id="12889-384">問題1： Cloud to Internet over Internet 上的內部部署連接</span><span class="sxs-lookup"><span data-stu-id="12889-384">Problem 1: Cloud to on-premises connection over the Internet</span></span>
  
<span data-ttu-id="12889-385">下圖說明當您的網路設定沒有透過網際網路提供來自 Microsoft 雲端之輸入要求的 NAT 時，所採用的非對稱網路路徑。</span><span class="sxs-lookup"><span data-stu-id="12889-385">The following diagram illustrates the asymmetric network path taken when your network configuration doesn't provide NAT for inbound requests from the Microsoft cloud over the internet.</span></span>
  
1. <span data-ttu-id="12889-386">來自 Office 365 的輸入要求會從公用 DNS 中檢索內部部署端點的 IP 位址，並將要求傳送至您的周邊網路。</span><span class="sxs-lookup"><span data-stu-id="12889-386">The inbound request from Office 365 retrieves the IP address of the on-premises endpoint from public DNS and sends the request to your perimeter network.</span></span>

2. <span data-ttu-id="12889-387">在此錯誤的設定中，未在傳送流量的周邊網路上設定或提供來源 NAT，進而產生實際來源 IP 位址，以當作傳回目的地使用。</span><span class="sxs-lookup"><span data-stu-id="12889-387">In this faulty configuration, there is no Source NAT configured or available at the perimeter network where the traffic is sent resulting in the actual source IP address being used as the return destination.</span></span>

  - <span data-ttu-id="12889-388">網路上的伺服器透過任何可用的 ExpressRoute 網路連線，將傳回流量路由傳送至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="12889-388">The server on your network routes the return traffic to Office 365 through any available ExpressRoute network connection.</span></span>

  - <span data-ttu-id="12889-389">結果是該流程到 Office 365 的非對稱路徑，導致連線中斷。</span><span class="sxs-lookup"><span data-stu-id="12889-389">The result is an Asymmetric path for that flow to Office 365, resulting in a broken connection.</span></span>

![ExpressRoute Asymetric 路由問題1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a><span data-ttu-id="12889-391">解決方案1a：來源 NAT</span><span class="sxs-lookup"><span data-stu-id="12889-391">Solution 1a: Source NAT</span></span>
  
<span data-ttu-id="12889-392">只要將來源 NAT 新增至輸入的要求，即可解析這種已設定錯誤的網路。</span><span class="sxs-lookup"><span data-stu-id="12889-392">Simply adding a source NAT to the inbound request resolves this misconfigured network.</span></span> <span data-ttu-id="12889-393">在此圖表中：</span><span class="sxs-lookup"><span data-stu-id="12889-393">In this diagram:</span></span>
  
1. <span data-ttu-id="12889-394">傳入要求會繼續透過新的 Jersey 資料中心周邊網路進入。</span><span class="sxs-lookup"><span data-stu-id="12889-394">The incoming request continues to enter through the New Jersey data center's perimeter network.</span></span> <span data-ttu-id="12889-395">此時間源 NAT 可供使用。</span><span class="sxs-lookup"><span data-stu-id="12889-395">This time Source NAT is available.</span></span>

2. <span data-ttu-id="12889-396">伺服器的回應會傳回與來源 NAT 相關聯的 IP 位址，而不是原始 IP 位址，進而導致回應沿著相同的網路路徑傳回。</span><span class="sxs-lookup"><span data-stu-id="12889-396">The response from the server routes back toward the IP associated with the Source NAT instead of the original IP address, resulting in the response returning along the same network path.</span></span>

![ExpressRoute Asymetric 路由解決方案1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a><span data-ttu-id="12889-398">解決方案1b：路由範圍</span><span class="sxs-lookup"><span data-stu-id="12889-398">Solution 1b: Route Scoping</span></span>
  
<span data-ttu-id="12889-399">或者，您也可以選擇不允許公佈 ExpressRoute BGP 首碼，移除這些電腦的備用網路路徑。</span><span class="sxs-lookup"><span data-stu-id="12889-399">Alternatively, you can choose to not allow the ExpressRoute BGP prefixes to be advertised, removing the alternate network path for those computers.</span></span> <span data-ttu-id="12889-400">在此圖表中：</span><span class="sxs-lookup"><span data-stu-id="12889-400">In this diagram:</span></span>
  
1. <span data-ttu-id="12889-401">傳入要求會繼續透過新的 Jersey 資料中心周邊網路進入。</span><span class="sxs-lookup"><span data-stu-id="12889-401">The incoming request continues to enter through the New Jersey data center's perimeter network.</span></span> <span data-ttu-id="12889-402">這段時間，新的 Jersey 資料中心無法使用透過 ExpressRoute 電路宣告給 Microsoft 的首碼。</span><span class="sxs-lookup"><span data-stu-id="12889-402">This time the prefixes advertised from Microsoft over the ExpressRoute circuit are not available to the New Jersey data center.</span></span>

2. <span data-ttu-id="12889-403">伺服器發回的 IP 位址會傳回與原始 IP 位址相關聯的 IP 位址，而這會導致回應是沿著相同的網路路徑傳回。</span><span class="sxs-lookup"><span data-stu-id="12889-403">The response from the server routes back toward the IP associated with the original IP address over the only route available, resulting in the response returning along the same network path.</span></span>

![ExpressRoute Asymetric 路由解決方案2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a><span data-ttu-id="12889-405">問題2： Cloud over ExpressRoute 上的內部部署連接</span><span class="sxs-lookup"><span data-stu-id="12889-405">Problem 2: Cloud to on-premises connection over ExpressRoute</span></span>
  
<span data-ttu-id="12889-406">下圖說明當您的網路設定不會提供來自 Microsoft cloud over ExpressRoute 之輸入要求的 NAT 時，所採用的非對稱網路路徑。</span><span class="sxs-lookup"><span data-stu-id="12889-406">The following diagram illustrates the asymmetric network path taken when your network configuration doesn't provide NAT for inbound requests from the Microsoft cloud over ExpressRoute.</span></span>
  
1. <span data-ttu-id="12889-407">來自 Office 365 的輸入要求會從 DNS 中檢索 IP 位址，並將要求傳送至您的周邊網路。</span><span class="sxs-lookup"><span data-stu-id="12889-407">The inbound request from Office 365 retrieves the IP address from DNS and sends the request to your perimeter network.</span></span>

2. <span data-ttu-id="12889-408">在此錯誤的設定中，未在傳送流量的周邊網路上設定或提供來源 NAT，進而產生實際來源 IP 位址，以當作傳回目的地使用。</span><span class="sxs-lookup"><span data-stu-id="12889-408">In this faulty configuration, there is no Source NAT configured or available at the perimeter network where the traffic is sent resulting in the actual source IP address being used as the return destination.</span></span>

  - <span data-ttu-id="12889-409">網路上的電腦會透過任何可用的 ExpressRoute 網路連線，將傳回流量路由傳送至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="12889-409">The computer on your network routes the return traffic to Office 365 through any available ExpressRoute network connection.</span></span>

  - <span data-ttu-id="12889-410">其結果是與 Office 365 的非對稱連接。</span><span class="sxs-lookup"><span data-stu-id="12889-410">The result is an Asymmetric connection to Office 365.</span></span>

![ExpressRoute Asymetric 路由問題2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a><span data-ttu-id="12889-412">解決方案2：來源 NAT</span><span class="sxs-lookup"><span data-stu-id="12889-412">Solution 2: Source NAT</span></span>
  
<span data-ttu-id="12889-413">只要將來源 NAT 新增至輸入的要求，即可解析這種已設定錯誤的網路。</span><span class="sxs-lookup"><span data-stu-id="12889-413">Simply adding a source NAT to the inbound request resolves this misconfigured network.</span></span> <span data-ttu-id="12889-414">在此圖表中：</span><span class="sxs-lookup"><span data-stu-id="12889-414">In this diagram:</span></span>
  
1. <span data-ttu-id="12889-415">傳入的要求會繼續透過紐約資料中心的周邊網路進入。</span><span class="sxs-lookup"><span data-stu-id="12889-415">The incoming request continues to enter through the New York data center's perimeter network.</span></span> <span data-ttu-id="12889-416">此時間源 NAT 可供使用。</span><span class="sxs-lookup"><span data-stu-id="12889-416">This time Source NAT is available.</span></span>

2. <span data-ttu-id="12889-417">伺服器的回應會傳回與來源 NAT 相關聯的 IP 位址，而不是原始 IP 位址，進而導致回應沿著相同的網路路徑傳回。</span><span class="sxs-lookup"><span data-stu-id="12889-417">The response from the server routes back toward the IP associated with the Source NAT instead of the original IP address, resulting in the response returning along the same network path.</span></span>

![ExpressRoute Asymetric 路由解決方案3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a><span data-ttu-id="12889-419">紙張驗證網路設計是否有對稱路徑</span><span class="sxs-lookup"><span data-stu-id="12889-419">Paper verify that the network design has path symmetry</span></span>

<span data-ttu-id="12889-420">此時，您必須驗證您的執行計畫是否為您將使用 Office 365 的不同案例提供路由對稱的功能。</span><span class="sxs-lookup"><span data-stu-id="12889-420">At this point, you need to verify on paper that your implementation plan offers route symmetry for the different scenarios in which you'll be using Office 365.</span></span> <span data-ttu-id="12889-421">當人員使用服務的不同功能時，您會識別預計會採取的特定網路路由。</span><span class="sxs-lookup"><span data-stu-id="12889-421">You'll identify the specific network route that is expected to be taken when a person uses different features of the service.</span></span> <span data-ttu-id="12889-422">從內部部署網路和 WAN 路由傳送至周邊裝置，到連接路徑;ExpressRoute 或網際網路，以及連線到線上端點的連線。</span><span class="sxs-lookup"><span data-stu-id="12889-422">From the on-premises network and WAN routing, to the perimeter devices, to the connectivity path; ExpressRoute or the internet, and on to the connection to the online endpoint.</span></span>
  
<span data-ttu-id="12889-423">您必須針對先前識別為組織所採用之服務的所有 Office 365 網路服務執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="12889-423">You'll need to do this for all of the Office 365 network services that were previously identified as services that your organization will adopt.</span></span>
  
<span data-ttu-id="12889-424">這可協助您逐步完成與第二個人的路由。</span><span class="sxs-lookup"><span data-stu-id="12889-424">It helps to do this paper walk through of routes with a second person.</span></span> <span data-ttu-id="12889-425">向使用者說明，每個網路躍點預期會從何處取得下一個路由，並確保您熟悉路由路徑。</span><span class="sxs-lookup"><span data-stu-id="12889-425">Explain to them where each network hop is expected to get its next route from and ensure that you're familiar with the routing paths.</span></span> <span data-ttu-id="12889-426">請記住，ExpressRoute 一定會提供更具範圍的路由給 Microsoft server IP 位址，使其具有低於網際網路預設路由的路由成本。</span><span class="sxs-lookup"><span data-stu-id="12889-426">Remember that ExpressRoute will always provide a more scoped route to Microsoft server IP addresses giving it lower route cost than an Internet default route.</span></span>
  
### <a name="design-client-connectivity-configuration"></a><span data-ttu-id="12889-427">設計 Client Connectivity Configuration</span><span class="sxs-lookup"><span data-stu-id="12889-427">Design Client Connectivity Configuration</span></span>
<span data-ttu-id="12889-428"><a name="asymmetric"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-428"><a name="asymmetric"> </a></span></span>

![使用具有 ExpressRoute 的 PAC 檔案](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
<span data-ttu-id="12889-430">如果您使用 proxy 伺服器進行網際網路系結流量，則需要調整任何 PAC 或用戶端設定檔，以確保網路上的用戶端電腦已正確設定為將您想要的 ExpressRoute 流量傳送至 Office 365，而不需要 transiting proxy 伺服器，而其餘的流量（包括部分 Office 365 流量）會傳送至相關的 proxy。</span><span class="sxs-lookup"><span data-stu-id="12889-430">If you're using a proxy server for internet bound traffic then you need to adjust any PAC or client configuration files to ensure client computers on your network are correctly configured to send the ExpressRoute traffic you desire to Office 365 without transiting your proxy server, and the remaining traffic, including some Office 365 traffic, is sent to the relevant proxy.</span></span> <span data-ttu-id="12889-431">如需 [管理 Office 365 端點](https://aka.ms/manageo365endpoints) （例如 PAC 檔案）的指南，請參閱本指南。</span><span class="sxs-lookup"><span data-stu-id="12889-431">Read our guide on [managing Office 365 endpoints](https://aka.ms/manageo365endpoints) for example PAC files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12889-432">端點經常變更，只要每週。</span><span class="sxs-lookup"><span data-stu-id="12889-432">The endpoints change frequently, as often as weekly.</span></span> <span data-ttu-id="12889-433">您應根據貴組織已採用的服務和功能，只進行變更，以減少所需的變更數目，以減少保持最新的變更數目。</span><span class="sxs-lookup"><span data-stu-id="12889-433">You should only make changes based on the services and features your organization has adopted to reduce the number of changes you'll need to make to stay current.</span></span> <span data-ttu-id="12889-434">請密切注意 RSS 摘要中的 [ **有效日期** ]：在此 rss 摘要中已宣告變更，且記錄保留所有過去的變更為止，已宣告的 IP 位址可能不會宣告或從通告中移除，直到達到有效日期為止。</span><span class="sxs-lookup"><span data-stu-id="12889-434">Pay close attention to the **Effective Date** in the RSS feed where the changes are announced and a record is kept of all past changes, IP addresses that are announced may not be advertised, or removed from advertisement, until the effective date is reached.</span></span>
  
## <a name="build-your-deployment-and-testing-procedures"></a><span data-ttu-id="12889-435">建立部署及測試程式</span><span class="sxs-lookup"><span data-stu-id="12889-435">Build your deployment and testing procedures</span></span>
<span data-ttu-id="12889-436"><a name="testing"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-436"><a name="testing"> </a></span></span>

<span data-ttu-id="12889-437">您的實施計畫應同時包含測試和回滾規劃。</span><span class="sxs-lookup"><span data-stu-id="12889-437">Your implementation plan should include both testing and rollback planning.</span></span> <span data-ttu-id="12889-438">如果您的實施未如期運作，方案應設計為在探索問題之前，影響最少人數。</span><span class="sxs-lookup"><span data-stu-id="12889-438">If your implementation isn't functioning as expected, the plan should be designed to affect the least number of people before problems are discovered.</span></span> <span data-ttu-id="12889-439">以下是您的方案應考慮的一些高層次原則。</span><span class="sxs-lookup"><span data-stu-id="12889-439">The following are some high level principles your plan should consider.</span></span>
  
1. <span data-ttu-id="12889-440">階段網路段和使用者服務上架，以將中斷降至最低。</span><span class="sxs-lookup"><span data-stu-id="12889-440">Stage the network segment and user service onboarding to minimize disruption.</span></span>

2. <span data-ttu-id="12889-441">規劃使用 traceroute 與 TCP 連線的測試路由，並從不同的網際網路連線主機進行連接。</span><span class="sxs-lookup"><span data-stu-id="12889-441">Plan for testing routes with traceroute and TCP connect from a separate internet connected host.</span></span>

3. <span data-ttu-id="12889-442">在具有測試 Office 365 租使用者的隔離測試網路上，您最好會進行輸入和輸出服務的測試。</span><span class="sxs-lookup"><span data-stu-id="12889-442">Preferably, testing of inbound and outbound services should be done on an isolated test network with a test Office 365 tenant.</span></span>

      - <span data-ttu-id="12889-443">或者，如果客戶尚未使用 Office 365 或進行試驗，也可以在生產網路上執行測試。</span><span class="sxs-lookup"><span data-stu-id="12889-443">Alternatively, testing can be performed on a production network if the customer is not yet using Office 365 or is in pilot.</span></span>

      - <span data-ttu-id="12889-444">或者，您也可以在實際執行中斷期間進行測試，而不是僅供測試及監視之用。</span><span class="sxs-lookup"><span data-stu-id="12889-444">Alternatively, testing can be performed during a production outage that is set aside for test and monitoring only.</span></span>

      - <span data-ttu-id="12889-445">或者，您可以在每個第三層路由器節點上檢查每個服務的路由，以進行測試。</span><span class="sxs-lookup"><span data-stu-id="12889-445">Alternatively, testing can be done by checking routes for each service on each layer 3 router node.</span></span> <span data-ttu-id="12889-446">只有在缺乏實體測試帶來風險的情況時，才可使用此回退功能。</span><span class="sxs-lookup"><span data-stu-id="12889-446">This fall back should only be used if no other testing is possible since a lack of physical testing introduces risk.</span></span>

### <a name="build-your-deployment-procedures"></a><span data-ttu-id="12889-447">建立部署程式</span><span class="sxs-lookup"><span data-stu-id="12889-447">Build your deployment procedures</span></span>

<span data-ttu-id="12889-448">您的部署程式應該向幾個階段中的小小組人員進行測試，然後再部署至較大的人員群組。</span><span class="sxs-lookup"><span data-stu-id="12889-448">Your deployment procedures should roll out to small groups of people in stages to allow for testing before deploying to larger groups of people.</span></span> <span data-ttu-id="12889-449">以下是幾種方法來分段 ExpressRoute 的部署。</span><span class="sxs-lookup"><span data-stu-id="12889-449">The following are several ways to stage the deployment of ExpressRoute.</span></span>
  
1. <span data-ttu-id="12889-450">使用 Microsoft 對等設定 ExpressRoute，並將路由播發轉送到單一主機，只用于分段測試目的。</span><span class="sxs-lookup"><span data-stu-id="12889-450">Set up ExpressRoute with Microsoft peering and have the route advertisements forwarded to a single host only for staged testing purposes.</span></span>

2. <span data-ttu-id="12889-451">將路由傳送至 ExpressRoute 網路的單一網段，一開始，並依網路段或地區展開路由廣告。</span><span class="sxs-lookup"><span data-stu-id="12889-451">Advertise routes to the ExpressRoute network to a single network segment at first and expand route advertisements by network segment or region.</span></span>

3. <span data-ttu-id="12889-452">如果是第一次部署 Office 365，請使用 ExpressRoute 網路部署做為少數人員的示範。</span><span class="sxs-lookup"><span data-stu-id="12889-452">If deploying Office 365 for the first time, use the ExpressRoute network deployment as a pilot for a small number of people.</span></span>

4. <span data-ttu-id="12889-453">如果使用 proxy 伺服器，您也可以設定測試 PAC 檔案，以引導少量的人員在進行測試與意見 ExpressRoute 之前新增其他。</span><span class="sxs-lookup"><span data-stu-id="12889-453">If using proxy servers, you can alternatively configure a test PAC file to direct a small number of people to ExpressRoute with testing and feedback before adding more.</span></span>

<span data-ttu-id="12889-454">您的實施計畫應該列出必須採取的每個部署程式，或需要用來部署網路設定的命令。</span><span class="sxs-lookup"><span data-stu-id="12889-454">Your implementation plan should list each of the deployment procedures that must be taken or commands that need to be used to deploy the networking configuration.</span></span> <span data-ttu-id="12889-455">當網路停機時間到達所做的所有變更時，應從已預先撰寫的書面部署計畫和對等方檢查。</span><span class="sxs-lookup"><span data-stu-id="12889-455">When the network outage time arrives all of the changes being made should be from the written deployment plan which was written in advance and peer reviewed.</span></span> <span data-ttu-id="12889-456">請參閱我們 ExpressRoute 之技術設定的指導方針。</span><span class="sxs-lookup"><span data-stu-id="12889-456">See our guidance on the technical configuration of ExpressRoute.</span></span>
  
- <span data-ttu-id="12889-457">如果您已變更任何內部部署伺服器的 IP 位址以繼續傳送電子郵件，請更新您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="12889-457">Updating your SPF TXT records if you've changed IP addresses for any on-premises servers that will continue to send email.</span></span>

- <span data-ttu-id="12889-458">如果您已變更 IP 位址以容納新的 NAT 設定，則為內部部署伺服器更新任何 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="12889-458">Updating any DNS entries for on-premises servers if you've changed IP addresses to accommodate a new NAT configuration.</span></span>

- <span data-ttu-id="12889-459">確定您已訂閱 Office 365 端點通知的 RSS 摘要，以維護任何路由或 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="12889-459">Ensure you've subscribed to the RSS feed for Office 365 endpoint notifications to maintain any routing or proxy configurations.</span></span>

<span data-ttu-id="12889-460">完成 ExpressRoute 部署後，應執行測試計劃中的程式。</span><span class="sxs-lookup"><span data-stu-id="12889-460">After your ExpressRoute deployment is complete the procedures in the test plan should be executed.</span></span> <span data-ttu-id="12889-461">應該記錄每個程式的結果。</span><span class="sxs-lookup"><span data-stu-id="12889-461">Results for each procedure should be logged.</span></span> <span data-ttu-id="12889-462">您必須在此事件中包含復原原始實際執行環境的程式，測試計劃結果表示執行失敗。</span><span class="sxs-lookup"><span data-stu-id="12889-462">You must include procedures for rolling back to the original production environment in the event the test plan results indicate the implementation was not successful.</span></span>
  
### <a name="build-your-test-procedures"></a><span data-ttu-id="12889-463">建立測試程式</span><span class="sxs-lookup"><span data-stu-id="12889-463">Build your test procedures</span></span>

<span data-ttu-id="12889-464">您的測試程式應該包含每個用於 Office 365 的輸出和輸入網路服務的測試，將使用 ExpressRoute，而不是會使用。</span><span class="sxs-lookup"><span data-stu-id="12889-464">Your testing procedures should include tests for each outbound and inbound network service for Office 365 both that will be using ExpressRoute and ones that will not.</span></span> <span data-ttu-id="12889-465">程式應包括從每個唯一的網路位置進行測試，包括在公司局域網中非內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="12889-465">The procedures should include testing from each unique network location including users who are not on-premises in the corporate LAN.</span></span>
  
<span data-ttu-id="12889-466">測試活動的一些範例包含下列各項。</span><span class="sxs-lookup"><span data-stu-id="12889-466">Some examples of test activities include the following.</span></span>
  
1. <span data-ttu-id="12889-467">從您的內部部署路由器 Ping 至您的網路操作員路由器。</span><span class="sxs-lookup"><span data-stu-id="12889-467">Ping from your on-premises router to your network operator router.</span></span>

2. <span data-ttu-id="12889-468">驗證您的內部部署路由器是否已接收 500 + Office 365 和 CRM Online IP 位址廣告。</span><span class="sxs-lookup"><span data-stu-id="12889-468">Validate the 500+ Office 365 and CRM Online IP address advertisements are received by your on-premises router.</span></span>

3. <span data-ttu-id="12889-469">驗證您的輸入和輸出 NAT 是在 ExpressRoute 和內部網路之間運作。</span><span class="sxs-lookup"><span data-stu-id="12889-469">Validate your inbound and outbound NAT is operating between ExpressRoute and the internal network.</span></span>

4. <span data-ttu-id="12889-470">驗證從您的路由器宣告到您的 NAT 的路由。</span><span class="sxs-lookup"><span data-stu-id="12889-470">Validate that routes to your NAT are being advertised from your router.</span></span>

5. <span data-ttu-id="12889-471">驗證 ExpressRoute 已接受您宣告的首碼。</span><span class="sxs-lookup"><span data-stu-id="12889-471">Validate that ExpressRoute has accepted your advertised prefixes.</span></span>

      - <span data-ttu-id="12889-472">使用下列 Cmdlet 來確認對等通告：</span><span class="sxs-lookup"><span data-stu-id="12889-472">Use the following cmdlet to verify peering advertisements:</span></span>

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. <span data-ttu-id="12889-473">驗證您的公用 NAT IP 範圍不會透過任何其他 ExpressRoute 或公用網際網路網路電路宣告給 Microsoft，除非它是先前範例中的較大範圍的特定子集。</span><span class="sxs-lookup"><span data-stu-id="12889-473">Validate your public NAT IP range is not advertised to Microsoft through any other ExpressRoute or public Internet network circuit unless it is a specific subset of a larger range as in the previous example.</span></span>

7. <span data-ttu-id="12889-474">ExpressRoute 電路成對，請驗證兩個 BGP 會話是否都在執行中。</span><span class="sxs-lookup"><span data-stu-id="12889-474">ExpressRoute circuits are paired, validate that both BGP sessions are running.</span></span>

8. <span data-ttu-id="12889-475">在 NAT 內設定單一主機，並使用 ping、tracert 和 tcpping 來測試跨新電路與主機 outlook.office365.com 的連線能力。</span><span class="sxs-lookup"><span data-stu-id="12889-475">Set up a single host on the inside of your NAT and use ping, tracert, and tcpping to test connectivity across the new circuit to the host outlook.office365.com.</span></span> <span data-ttu-id="12889-476">或者，您也可以在鏡像的埠上使用 Wireshark 或 Microsoft 網路監視器3.4 之類的工具，以驗證您能夠連線至與 outlook.office365.com 相關聯的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="12889-476">Alternatively, you could use a tool such as Wireshark or Microsoft Network Monitor 3.4 on a mirrored port to the MSEE to validate you're able to connect to the IP address associated with outlook.office365.com.</span></span>

9. <span data-ttu-id="12889-477">測試適用于 Exchange Online 的應用層級功能。</span><span class="sxs-lookup"><span data-stu-id="12889-477">Test application level functionality for Exchange Online.</span></span>

  - <span data-ttu-id="12889-478">測試 Outlook 可連線至 Exchange Online 及傳送/接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="12889-478">Test Outlook is able to connect to Exchange Online and send/receive email.</span></span>

  - <span data-ttu-id="12889-479">測試 Outlook 可使用線上模式。</span><span class="sxs-lookup"><span data-stu-id="12889-479">Test Outlook is able to use online-mode.</span></span>

  - <span data-ttu-id="12889-480">測試 smartphone 連線能力及傳送/接收能力。</span><span class="sxs-lookup"><span data-stu-id="12889-480">Test smartphone connectivity and send/receive capability.</span></span>

10. <span data-ttu-id="12889-481">測試 SharePoint 線上的應用層級功能</span><span class="sxs-lookup"><span data-stu-id="12889-481">Test application level functionality for SharePoint Online</span></span>

  - <span data-ttu-id="12889-482">測試 Business sync 用戶端的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="12889-482">Test OneDrive for Business sync client.</span></span>

  - <span data-ttu-id="12889-483">測試 SharePoint 線上 web 存取。</span><span class="sxs-lookup"><span data-stu-id="12889-483">Test SharePoint Online web access.</span></span>

11. <span data-ttu-id="12889-484">測試商務用 Skype 通話案例的應用層級功能：</span><span class="sxs-lookup"><span data-stu-id="12889-484">Test application level functionality for Skype for Business calling scenarios:</span></span>

  - <span data-ttu-id="12889-485">加入電話會議做為已驗證的使用者 [由使用者初始化的邀請]。</span><span class="sxs-lookup"><span data-stu-id="12889-485">Join to conference call as authenticated user [invite initiated by end user].</span></span>

  - <span data-ttu-id="12889-486">邀請使用者撥打電話會議 [從 MCU 傳送邀請]。</span><span class="sxs-lookup"><span data-stu-id="12889-486">Invite user to conference call [invite sent from MCU].</span></span>

  - <span data-ttu-id="12889-487">使用商務用 Skype web 應用程式以匿名使用者的身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="12889-487">Join conference as anonymous user using the Skype for Business web application.</span></span>

  - <span data-ttu-id="12889-488">從您的有線電腦連線、IP 電話及行動裝置加入通話。</span><span class="sxs-lookup"><span data-stu-id="12889-488">Join call from your wired PC connection, IP phone, and mobile device.</span></span>

  - <span data-ttu-id="12889-489">呼叫同盟使用者 o 呼叫至 PSTN 驗證：通話已完成，通話品質可接受，連線時間是可接受的。</span><span class="sxs-lookup"><span data-stu-id="12889-489">Call to federated user o Call to PSTN Validation: call is completed, call quality is acceptable, connection time is acceptable.</span></span>

  - <span data-ttu-id="12889-490">確認已針對承租人和同盟使用者的兩個成員更新連絡人的狀態。</span><span class="sxs-lookup"><span data-stu-id="12889-490">Verify presence status for contacts is updated for both members of the tenant and federated users.</span></span>

### <a name="common-problems"></a><span data-ttu-id="12889-491">常見問題</span><span class="sxs-lookup"><span data-stu-id="12889-491">Common problems</span></span>

<span data-ttu-id="12889-492">非對稱路由是最常見的實施問題。</span><span class="sxs-lookup"><span data-stu-id="12889-492">Asymmetric routing is the most common implementation problem.</span></span> <span data-ttu-id="12889-493">以下是一些要尋找的常見來源：</span><span class="sxs-lookup"><span data-stu-id="12889-493">Here are some common sources to look for:</span></span>
  
- <span data-ttu-id="12889-494">就地使用開放或單層網路路由拓撲，但沒有源 NAT。</span><span class="sxs-lookup"><span data-stu-id="12889-494">Using an open or flat network routing topology without source NAT in place.</span></span>

- <span data-ttu-id="12889-495">不使用 SNAT 透過網際網路和 ExpressRoute 連接來路由傳送至輸入服務。</span><span class="sxs-lookup"><span data-stu-id="12889-495">Not using SNAT to route to inbound services through both the internet and ExpressRoute connections.</span></span>

- <span data-ttu-id="12889-496">在部署廣泛之前，請勿在測試網路上測試 ExpressRoute 上的輸入服務。</span><span class="sxs-lookup"><span data-stu-id="12889-496">Not testing inbound services on ExpressRoute on a test network prior to deploying broadly.</span></span>

## <a name="deploying-expressroute-connectivity-through-your-network"></a><span data-ttu-id="12889-497">透過您的網路部署 ExpressRoute 連通性</span><span class="sxs-lookup"><span data-stu-id="12889-497">Deploying ExpressRoute connectivity through your network</span></span>
<span data-ttu-id="12889-498"><a name="testing"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-498"><a name="testing"> </a></span></span>

<span data-ttu-id="12889-499">將您的部署逐步劃分到網路的一個網段，以逐步向網路的不同部分推出，並以每個新的網路區段復原的計畫。</span><span class="sxs-lookup"><span data-stu-id="12889-499">Stage your deployment to one segment of the network at a time, progressively rolling out the connectivity to different parts of the network with a plan to roll back for each new network segment.</span></span> <span data-ttu-id="12889-500">如果您的部署與 Office 365 部署一致，請先部署 Office 365 試驗使用者，然後再從那裡進行擴充。</span><span class="sxs-lookup"><span data-stu-id="12889-500">If your deployment is aligned with an Office 365 deployment, deploy to your Office 365 pilot users first and extend from there.</span></span>
  
<span data-ttu-id="12889-501">先進行測試，然後再進行實際執行：</span><span class="sxs-lookup"><span data-stu-id="12889-501">First for your test and then for production:</span></span>
  
- <span data-ttu-id="12889-502">執行部署步驟以啟用 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="12889-502">Run the deployment steps to enable ExpressRoute.</span></span>

- <span data-ttu-id="12889-503">測試您的查看網路路由是否如預期。</span><span class="sxs-lookup"><span data-stu-id="12889-503">Test your seeing the network routes are as expected.</span></span>

- <span data-ttu-id="12889-504">在每個輸入和輸出服務上執行測試。</span><span class="sxs-lookup"><span data-stu-id="12889-504">Perform testing on each inbound and outbound service.</span></span>

- <span data-ttu-id="12889-505">如果您探索任何問題，就會復原。</span><span class="sxs-lookup"><span data-stu-id="12889-505">Rollback if you discover any issues.</span></span>

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a><span data-ttu-id="12889-506">使用測試網路段設定 ExpressRoute 的測試連接</span><span class="sxs-lookup"><span data-stu-id="12889-506">Set up a test connection to ExpressRoute with a test network segment</span></span>

<span data-ttu-id="12889-507">現在，您已完成的計畫是在一小段時間進行測試。</span><span class="sxs-lookup"><span data-stu-id="12889-507">Now that you have the completed plan on paper it is time to test at a small scale.</span></span> <span data-ttu-id="12889-508">在此測試中，您將建立單一 ExpressRoute 連線與 Microsoft 對等網路對內部部署網路上的測試子網的關聯。</span><span class="sxs-lookup"><span data-stu-id="12889-508">In this test you will establish a single ExpressRoute connection with Microsoft Peering to a test subnet on your on-premises network.</span></span> <span data-ttu-id="12889-509">您可以設定 [試用版 Office 365 租](https://go.microsoft.com/fwlink/p/?LinkID=403802) 使用者與 test 子網間的連線，並在測試子網中包含您將在生產環境中使用的所有輸出和輸入服務。</span><span class="sxs-lookup"><span data-stu-id="12889-509">You can configure a [trial Office 365 tenant](https://go.microsoft.com/fwlink/p/?LinkID=403802) with connectivity to and from the test subnet and include all outbound and inbound services that you will be using in production in the test subnet.</span></span> <span data-ttu-id="12889-510">設定測試網路段的 DNS，並建立所有輸入和輸出服務。</span><span class="sxs-lookup"><span data-stu-id="12889-510">Set up DNS for the test network segment and establish all inbound and outbound services.</span></span> <span data-ttu-id="12889-511">執行測試計劃，並確定您熟悉每個服務和路由傳播的路由。</span><span class="sxs-lookup"><span data-stu-id="12889-511">Execute your test plan and ensure that you are familiar with the routing for each service and the route propagation.</span></span>
  
### <a name="execute-the-deployment-and-test-plans"></a><span data-ttu-id="12889-512">執行部署和測試計劃</span><span class="sxs-lookup"><span data-stu-id="12889-512">Execute the deployment and test plans</span></span>

<span data-ttu-id="12889-513">當您完成上述專案時，請核對您已完成的區域，並確定您和您的小組已在執行部署和測試計劃之前，先查看這些專案。</span><span class="sxs-lookup"><span data-stu-id="12889-513">As you complete the items described above, check off the areas you've completed and ensure you and your team have reviewed them before executing your deployment and testing plans.</span></span>
  
- <span data-ttu-id="12889-514">網路變更所涉及的輸出和輸入服務清單。</span><span class="sxs-lookup"><span data-stu-id="12889-514">List of outbound and inbound services that are involved in the network change.</span></span>

- <span data-ttu-id="12889-515">全域網路架構圖表顯示網際網路出口和 ExpressRoute 的 [符合我的位置] 位置。</span><span class="sxs-lookup"><span data-stu-id="12889-515">Global network architecture diagram showing both internet egress and ExpressRoute meet-me locations.</span></span>

- <span data-ttu-id="12889-516">示範用於每個已部署服務之不同網路路徑的網路路由圖表。</span><span class="sxs-lookup"><span data-stu-id="12889-516">Network routing diagram demonstrating the different network paths used for each service deployed.</span></span>

- <span data-ttu-id="12889-517">部署計畫，包含必要時執行變更和回滾的步驟。</span><span class="sxs-lookup"><span data-stu-id="12889-517">A deployment plan with steps to implement the changes and rollback if needed.</span></span>

- <span data-ttu-id="12889-518">測試每個 Office 365 和網路服務的測試計劃。</span><span class="sxs-lookup"><span data-stu-id="12889-518">A test plan for testing each Office 365 and network service.</span></span>

- <span data-ttu-id="12889-519">已完成輸入和輸出服務之實際執行路由的紙張驗證。</span><span class="sxs-lookup"><span data-stu-id="12889-519">Completed paper validation of production routes for inbound and outbound services.</span></span>

- <span data-ttu-id="12889-520">測試網段上的完整測試，包括可用性測試。</span><span class="sxs-lookup"><span data-stu-id="12889-520">A completed test across a test network segment including availability testing.</span></span>

<span data-ttu-id="12889-521">選擇一個長時間足以透過整個部署計畫及測試計劃執行的中斷時段，並有一些時間可供進行疑難排解，以及在必要時回復的時間。</span><span class="sxs-lookup"><span data-stu-id="12889-521">Choose an outage window that is long enough to run through the entire deployment plan and the test plan, has some time available for troubleshooting and time for rolling back if required.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="12889-522">由於透過網際網路和 ExpressRoute 進行路由的複雜性質，建議您在此視窗中新增額外的緩衝時間，以處理複雜路由疑難排解。</span><span class="sxs-lookup"><span data-stu-id="12889-522">Due to the complex nature of routing over both the internet and ExpressRoute, it is recommended that additional buffer time is added to this window to handle troubleshooting complex routing.</span></span>
  
### <a name="configure-qos-for-skype-for-business-online"></a><span data-ttu-id="12889-523">為商務用 Skype Online 設定 QoS</span><span class="sxs-lookup"><span data-stu-id="12889-523">Configure QoS for Skype for Business Online</span></span>

<span data-ttu-id="12889-524">QoS 是取得商務用 Skype Online 之語音和會議效益的必要。</span><span class="sxs-lookup"><span data-stu-id="12889-524">QoS is necessary to obtain voice and meeting benefits for Skype for Business Online.</span></span> <span data-ttu-id="12889-525">您可以在確保 ExpressRoute 網路連接不會封鎖任何其他 Office 365 服務存取之後，設定 QoS。</span><span class="sxs-lookup"><span data-stu-id="12889-525">You can configure QoS after you have ensured that the ExpressRoute network connection does not block any of your other Office 365 service access.</span></span> <span data-ttu-id="12889-526">QoS 的設定會在 [ExpressRoute 和 QoS 的商務用 Skype Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 中說明。</span><span class="sxs-lookup"><span data-stu-id="12889-526">Configuration for QoS is described in the article [ExpressRoute and QoS in Skype for Business Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) .</span></span>
  
## <a name="troubleshooting-your-implementation"></a><span data-ttu-id="12889-527">您的實施疑難排解</span><span class="sxs-lookup"><span data-stu-id="12889-527">Troubleshooting your implementation</span></span>
<span data-ttu-id="12889-528"><a name="troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="12889-528"><a name="troubleshooting"> </a></span></span>

<span data-ttu-id="12889-529">第一個要注意的地方是在實施方案中未錯過任何專案，在此實施方案中的步驟。</span><span class="sxs-lookup"><span data-stu-id="12889-529">The first place to look is at the steps in this implementation guide, were any missed in your implementation plan?</span></span> <span data-ttu-id="12889-530">若有可能複製錯誤並加以調試，請傳回並執行進一步的小型網路測試。</span><span class="sxs-lookup"><span data-stu-id="12889-530">Go back and run further small network testing if possible to replicate the error and debug it there.</span></span>
  
<span data-ttu-id="12889-531">識別測試期間哪些輸入或輸出服務失敗。</span><span class="sxs-lookup"><span data-stu-id="12889-531">Identify which inbound or outbound services failed during testing.</span></span> <span data-ttu-id="12889-532">針對每個失敗的服務，明確取得 IP 位址與子網。</span><span class="sxs-lookup"><span data-stu-id="12889-532">Get specifically the IP addresses and subnets for each of the services which failed.</span></span> <span data-ttu-id="12889-533">繼續進行並流覽紙張上的網路拓撲圖表，並驗證路由。</span><span class="sxs-lookup"><span data-stu-id="12889-533">Go ahead and walk the network topology diagram on paper and validate the routing.</span></span> <span data-ttu-id="12889-534">特別驗證通告 ExpressRoute 路由的位置，在中斷期間（如果可能有追蹤）進行路由測試。</span><span class="sxs-lookup"><span data-stu-id="12889-534">Validate specifically where the ExpressRoute routing is advertised to, Test that routing during the outage if possible with traces.</span></span>
  
<span data-ttu-id="12889-535">以網路追蹤方式執行 PSPing 每個用戶端點，並評估來源和目的地 IP 位址，以驗證其是否如預期。</span><span class="sxs-lookup"><span data-stu-id="12889-535">Run PSPing with a network trace to each customer endpoint and evaluate source and destination IP addresses to validate that they are as expected.</span></span> <span data-ttu-id="12889-536">對您在埠25公開的任何郵件主機執行 telnet，確認在預期的情況中，SNAT 會隱藏原始來源 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="12889-536">Run telnet to any mail host that you expose on port 25 and verify that SNAT is hiding the original source IP address if this is expected.</span></span>
  
<span data-ttu-id="12889-537">請記住，當您使用 ExpressRoute 連線部署 Office 365 時，您必須確定 ExpressRoute 的網路設定為最優化設計，而且您也對網路上的其他元件（例如用戶端電腦）進行優化。</span><span class="sxs-lookup"><span data-stu-id="12889-537">Keep in mind that while deploying Office 365 with an ExpressRoute connection you'll need to ensure both the network configuration for ExpressRoute is optimally designed and you've also optimized the other components on your network such as client computers.</span></span> <span data-ttu-id="12889-538">除了使用此規劃指南來疑難排解可能錯過的步驟之外，我們也撰寫了 [Office 365 的性能疑難排解計畫](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) 。</span><span class="sxs-lookup"><span data-stu-id="12889-538">In addition to using this planning guide to troubleshoot the steps you may have missed, we also have written a [Performance troubleshooting plan for Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .</span></span>
  
<span data-ttu-id="12889-539">您可以使用下列短連結返回這裡：[https://aka.ms/implementexpressroute365](https://aka.ms/implementexpressroute365)</span><span class="sxs-lookup"><span data-stu-id="12889-539">Here's a short link you can use to come back: [https://aka.ms/implementexpressroute365](https://aka.ms/implementexpressroute365)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="12889-540">相關主題</span><span class="sxs-lookup"><span data-stu-id="12889-540">Related Topics</span></span>

[<span data-ttu-id="12889-541">評估 Office 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="12889-541">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="12889-542">Azure ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="12889-542">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
  
[<span data-ttu-id="12889-543">管理 ExpressRoute for Office 365 連線</span><span class="sxs-lookup"><span data-stu-id="12889-543">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)
  
[<span data-ttu-id="12889-544">使用 ExpressRoute for Office 365 進行路由傳送</span><span class="sxs-lookup"><span data-stu-id="12889-544">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
  
[<span data-ttu-id="12889-545">使用 ExpressRoute for Office 365 進行網路規劃</span><span class="sxs-lookup"><span data-stu-id="12889-545">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
  
[<span data-ttu-id="12889-546">在 ExpressRoute for Office 365 案例中使用 BGP 社區</span><span class="sxs-lookup"><span data-stu-id="12889-546">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)
  
[<span data-ttu-id="12889-547">商務用 Skype Online 中的媒體品質和網路連線效能</span><span class="sxs-lookup"><span data-stu-id="12889-547">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="12889-548">針對商務用 Skype Online 最佳化您的網路</span><span class="sxs-lookup"><span data-stu-id="12889-548">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[<span data-ttu-id="12889-549">商務用 Skype Online 中的 ExpressRoute 與 QoS</span><span class="sxs-lookup"><span data-stu-id="12889-549">ExpressRoute and QoS in Skype for Business Online</span></span>](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[<span data-ttu-id="12889-550">使用 ExpressRoute 的通話流程</span><span class="sxs-lookup"><span data-stu-id="12889-550">Call flow using ExpressRoute</span></span>](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[<span data-ttu-id="12889-551">使用基準與效能歷程記錄進行 Office 365 效能調整</span><span class="sxs-lookup"><span data-stu-id="12889-551">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
[<span data-ttu-id="12889-552">Office 365 的效能疑難排解規劃</span><span class="sxs-lookup"><span data-stu-id="12889-552">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)
  
[<span data-ttu-id="12889-553">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="12889-553">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="12889-554">Office 365 網路與效能調整</span><span class="sxs-lookup"><span data-stu-id="12889-554">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)