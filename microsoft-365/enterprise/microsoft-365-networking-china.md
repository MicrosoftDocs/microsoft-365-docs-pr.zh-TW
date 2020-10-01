---
title: 適用于中國使用者的 Microsoft 365 全域租使用者效能優化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- M365initiative-CoreDeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文提供針對全球 Microsoft 365 承租人的中國使用者優化網路效能的指導方針。
ms.openlocfilehash: 1f5f51991c5950d46c9d835a98bea86bcb354366
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327506"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a><span data-ttu-id="9a856-103">適用于中國使用者的 Microsoft 365 全域租使用者效能優化</span><span class="sxs-lookup"><span data-stu-id="9a856-103">Microsoft 365 global tenant performance optimization for China users</span></span>

>[!IMPORTANT]
><span data-ttu-id="9a856-104">本指南專屬於使用案例，在該案例中， **企業的 microsoft 365 使用者** 會連接到 **全域 Microsoft 365 租**使用者。</span><span class="sxs-lookup"><span data-stu-id="9a856-104">This guidance is specific to usage scenarios in which **enterprise Microsoft 365 users located in China** connect to a **global Microsoft 365 tenant**.</span></span> <span data-ttu-id="9a856-105">本 **指南不適用於** 由世紀運作之 Office 365 中的承租人。</span><span class="sxs-lookup"><span data-stu-id="9a856-105">This guidance does **not** apply to tenants in Office 365 operated by 21Vianet.</span></span>

<span data-ttu-id="9a856-106">針對具有全球 Microsoft 365 租使用者的企業和中國的公司形象，中國使用者的 Microsoft 365 用戶端效能對中國電信的網際網路架構而言是很複雜的因素。</span><span class="sxs-lookup"><span data-stu-id="9a856-106">For enterprises with global Microsoft 365 tenants and a corporate presence in China, Microsoft 365 client performance for China-based users can be complicated by factors unique to China Telco's Internet architecture.</span></span>

<span data-ttu-id="9a856-107">中國 Isp 對全球公用網際網路的管制 offshore 連線，可流覽周邊裝置，這種裝置可能會高層次的跨邊界網路擁塞。</span><span class="sxs-lookup"><span data-stu-id="9a856-107">China ISPs have regulated offshore connections to the global public Internet that go through perimeter devices which are prone to high-levels of cross-border network congestion.</span></span> <span data-ttu-id="9a856-108">這項擁塞會針對所有進出中國的網際網路流量，建立封包遺失和延遲。</span><span class="sxs-lookup"><span data-stu-id="9a856-108">This congestion creates packet loss and latency for all Internet traffic going into and out of China.</span></span>

![Microsoft 365 流量-未優化](../media/O365-networking/China-O365-unoptimized.png)

<span data-ttu-id="9a856-110">封包遺失和延遲對網路服務的效能有不利的影響，尤其是需要大量資料交換的服務 (例如大型檔案傳輸) 或需要接近即時效能 (音訊和影片應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="9a856-110">Packet loss and latency is detrimental to the performance of network services, especially services that require large data exchanges (such as large file transfers) or requiring near real-time performance (audio and video applications).</span></span>

<span data-ttu-id="9a856-111">本主題的目標是提供最佳作法，以減輕 Microsoft 365 服務上的中國跨框線網路擁塞的影響。</span><span class="sxs-lookup"><span data-stu-id="9a856-111">The goal of this topic is to provide best practices for mitigating the impact of China cross-border network congestion on Microsoft 365 services.</span></span> <span data-ttu-id="9a856-112">本主題不會解決其他常見的最後一個效能問題，例如由於中國運營商中的複雜路由而導致大量資料包延遲的問題。</span><span class="sxs-lookup"><span data-stu-id="9a856-112">This topic does not address other common last-mile performance issues such as issues of high packet latency due to complex routing within China carriers.</span></span>

## <a name="corporate-network-best-practices"></a><span data-ttu-id="9a856-113">公司網路的最佳作法</span><span class="sxs-lookup"><span data-stu-id="9a856-113">Corporate network best practices</span></span>

<span data-ttu-id="9a856-114">許多具有全球 Microsoft 365 承租人和中國使用者的企業，都已在全球範圍內實施含公司網路流量的私人網路與 offshore 位置之間的流量。</span><span class="sxs-lookup"><span data-stu-id="9a856-114">Many enterprises with global Microsoft 365 tenants and users in China have implemented private networks that carry corporate network traffic between China office locations and offshore locations around the world.</span></span> <span data-ttu-id="9a856-115">這些企業可以利用此網路基礎結構，避免跨框線網路擁塞，並在中國優化其 Microsoft 365 服務效能。</span><span class="sxs-lookup"><span data-stu-id="9a856-115">These enterprises can leverage this network infrastructure to avoid cross-border network congestion and optimize their Microsoft 365 service performance in China.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9a856-116">就像所有私人 WAN 實施一樣，您必須為您的國家和/或地區參考法規需求，以確保您的網路設定符合規範。</span><span class="sxs-lookup"><span data-stu-id="9a856-116">As with all private WAN implementations, you should always consult regulatory requirements for your country and/or region to ensure that your network configuration is in compliance.</span></span>

<span data-ttu-id="9a856-117">第一步，您必須遵循 [Microsoft 365 的網路規劃和效能調整](https://aka.ms/tune)，遵循我們的基準網路指導方針。</span><span class="sxs-lookup"><span data-stu-id="9a856-117">As a first step, it is crucial that you follow our benchmark network guidance at [Network planning and performance tuning for Microsoft 365](https://aka.ms/tune).</span></span> <span data-ttu-id="9a856-118">主要目標應該是盡可能避免從中國網際網路存取全球 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="9a856-118">The primary goal should be to avoid accessing global Microsoft 365 services from the Internet in China if possible.</span></span>

- <span data-ttu-id="9a856-119">利用您現有的私人網路，在中國辦公網路和 offshore 位置之間傳送 Microsoft 365 網路流量，該位置是在中國以外的公用網際網路上出口。</span><span class="sxs-lookup"><span data-stu-id="9a856-119">Leverage your existing private network to carry Microsoft 365 network traffic between China office networks and offshore locations that egress on the public Internet outside China.</span></span> <span data-ttu-id="9a856-120">在中國以外的任何位置幾乎都會提供明確的利益。</span><span class="sxs-lookup"><span data-stu-id="9a856-120">Almost any location outside China will provide a clear benefit.</span></span> <span data-ttu-id="9a856-121">網路系統管理員可以透過使用 [Microsoft 全球網路](https://docs.microsoft.com/azure/networking/microsoft-global-network)的低延遲互連區域中的 egressing 進行進一步的優化。</span><span class="sxs-lookup"><span data-stu-id="9a856-121">Network administrators can further optimize by egressing in areas with low-latency interconnect with the [Microsoft global network](https://docs.microsoft.com/azure/networking/microsoft-global-network).</span></span> <span data-ttu-id="9a856-122">香港，日本和韓國為範例。</span><span class="sxs-lookup"><span data-stu-id="9a856-122">Hong Kong, Japan, and South Korea are examples.</span></span>
- <span data-ttu-id="9a856-123">設定使用者裝置以透過 VPN 連線存取公司網路，以允許 Microsoft 365 流量傳輸公司網路的私人 offshore 連結。</span><span class="sxs-lookup"><span data-stu-id="9a856-123">Configure user devices to access the corporate network over a VPN connection to allow Microsoft 365 traffic to transit the corporate network's private offshore link.</span></span> <span data-ttu-id="9a856-124">確定 VPN 用戶端未設定成使用分割隧道，或使用者裝置已設定為忽略 Microsoft 365 流量的分割隧道。</span><span class="sxs-lookup"><span data-stu-id="9a856-124">Ensure that VPN clients are either not configured to use split tunneling, or that user devices are configured to ignore split tunneling for Microsoft 365 traffic.</span></span>
- <span data-ttu-id="9a856-125">設定您的網路以路由傳送您私人 offshore 連結的所有 Microsoft 365 流量。</span><span class="sxs-lookup"><span data-stu-id="9a856-125">Configure your network to route all Microsoft 365 traffic across your private offshore link.</span></span> <span data-ttu-id="9a856-126">如果您必須將私人連結的流量降到最低，您可以選擇只在 [ **優化** ] 類別中路由終結點，並允許要求 **允許** 和 **預設** 端點傳輸網際網路。</span><span class="sxs-lookup"><span data-stu-id="9a856-126">If you must minimize the volume of traffic on your private link, you can choose to only route endpoints in the **Optimize** category, and allow requests to **Allow** and **Default** endpoints to transit the Internet.</span></span> <span data-ttu-id="9a856-127">這可將優化的流量限制在高延遲和封包遺失的重要服務上，以提升效能，並將頻寬消耗降至最低。</span><span class="sxs-lookup"><span data-stu-id="9a856-127">This will improve performance and minimize bandwidth consumption by limiting optimized traffic to critical services that are most sensitive to high latency and packet loss.</span></span>
- <span data-ttu-id="9a856-128">如果可能的話，請使用 UDP （而非 TCP）即時媒體資料流程流量，例如用於小組。</span><span class="sxs-lookup"><span data-stu-id="9a856-128">If possible, use UDP instead of TCP for live media streaming traffic, such as for Teams.</span></span> <span data-ttu-id="9a856-129">UDP 可提供比 TCP 更佳的即時媒體資料流程效能。</span><span class="sxs-lookup"><span data-stu-id="9a856-129">UDP offers better live media streaming performance than TCP.</span></span>

<span data-ttu-id="9a856-130">如需如何選擇性路由 Microsoft 365 流量的相關資訊，請參閱 [管理 Office 365 端點](managing-office-365-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="9a856-130">For information about how to selectively route Microsoft 365 traffic, see [Managing Office 365 endpoints](managing-office-365-endpoints.md).</span></span> <span data-ttu-id="9a856-131">如需所有全球 Office 365 URLs 及 IP 位址的清單，請參閱 [Office 365 URLs 和 ip 位址範圍](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="9a856-131">For a list of all worldwide Office 365 URLs and IP addresses, see [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>

![Microsoft 365 流量優化](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a><span data-ttu-id="9a856-133">使用者最佳作法</span><span class="sxs-lookup"><span data-stu-id="9a856-133">User best practices</span></span>

<span data-ttu-id="9a856-134">在中國，使用與商業網路無連線的遠端位置（例如，住宅、咖啡店、旅館及分公司）連線至全球 Microsoft 365 承租人的使用者，可能會因為其裝置和 Microsoft 365 之間的流量，必須傳輸中國網路的擁塞網路電路，因此可能會產生較低的網路效能。</span><span class="sxs-lookup"><span data-stu-id="9a856-134">Users in China who connect to global Microsoft 365 tenants from remote locations such as homes, coffee shops, hotels and branch offices with no connection to enterprise networks can experience poor network performance because traffic between their devices and Microsoft 365 must transit China's congested cross-border network circuits.</span></span>

<span data-ttu-id="9a856-135">如果在公司網路中的跨框線私人網路絡和/或 VPN 存取不是一個選項，請訓練您的中國使用者來遵循這些最佳作法，以降低個別使用者的效能問題。</span><span class="sxs-lookup"><span data-stu-id="9a856-135">If cross-border private networks and/or VPN access into the corporate network are not an option, per-user performance issues can still be mitigated by training your China-based users to follow these best practices.</span></span>

- <span data-ttu-id="9a856-136">利用支援快取的豐富 Office 用戶端 (例如，Outlook、小組、OneDrive 等 ) 和避免網路型用戶端。</span><span class="sxs-lookup"><span data-stu-id="9a856-136">Utilize rich Office clients that support caching (e.g. Outlook, Teams, OneDrive, etc.), and avoid web-based clients.</span></span> <span data-ttu-id="9a856-137">Office 用戶端快取及離線存取功能可大幅減少網路擁塞和延遲的影響。</span><span class="sxs-lookup"><span data-stu-id="9a856-137">Office client caching and offline access features can dramatically reduce the impact of network congestion and latency.</span></span>
- <span data-ttu-id="9a856-138">如果您的 Microsoft 365 租使用者已設定 _音訊會議_ 功能，小組使用者可以透過公用交換電話網路 (PSTN) 加入會議。</span><span class="sxs-lookup"><span data-stu-id="9a856-138">If your Microsoft 365 tenant has been configured with the _Audio Conferencing_ feature, Teams users can join meetings via the public switched telephone network (PSTN).</span></span> <span data-ttu-id="9a856-139">如需詳細資訊，請參閱 [Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="9a856-139">For more information, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span>
- <span data-ttu-id="9a856-140">如果使用者遇到網路效能問題，他們應該向其 IT 部門報告疑難排解，並在懷疑 Microsoft 365 服務發生問題時升級至 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="9a856-140">If users experience network performance issues, they should report to their IT department for troubleshooting, and escalate to Microsoft support if trouble with Microsoft 365 services is suspected.</span></span> <span data-ttu-id="9a856-141">並非所有問題都是由跨框線的網路效能所造成。</span><span class="sxs-lookup"><span data-stu-id="9a856-141">Not all issues are caused by cross-border network performance.</span></span>

<span data-ttu-id="9a856-142">Microsoft 正致力於改善 Microsoft 365 使用者經驗，並透過最廣泛的網路架構和特性範圍來改善用戶端的效能。</span><span class="sxs-lookup"><span data-stu-id="9a856-142">Microsoft is continually working to improve the Microsoft 365 user experience and the performance of clients over the widest possible range of network architectures and characteristics.</span></span> <span data-ttu-id="9a856-143">請造訪 [Office 365 技術社區](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) ，以啟動或加入交談、尋找資源，以及提交功能要求和建議。</span><span class="sxs-lookup"><span data-stu-id="9a856-143">Visit the [Office 365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) to start or join a conversation, find resources, and submit feature requests and suggestions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a856-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="9a856-144">Related topics</span></span>

[<span data-ttu-id="9a856-145">Microsoft 365 的網路規劃和效能調整</span><span class="sxs-lookup"><span data-stu-id="9a856-145">Network planning and performance tuning for Microsoft 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="9a856-146">Microsoft 365 網路連線原則</span><span class="sxs-lookup"><span data-stu-id="9a856-146">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="9a856-147">管理 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="9a856-147">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="9a856-148">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="9a856-148">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="9a856-149">Microsoft 全球網路</span><span class="sxs-lookup"><span data-stu-id="9a856-149">Microsoft global network</span></span>](https://docs.microsoft.com/azure/networking/microsoft-global-network)
