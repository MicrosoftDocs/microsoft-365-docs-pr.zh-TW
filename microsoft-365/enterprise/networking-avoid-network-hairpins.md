---
title: 步驟 3：避免網路 Hairpin
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並移除網路 Hairpin 以取得更好的效能。
ms.openlocfilehash: f9499fdb8e8c3f7b77e3349d6cc99f6dbf465870
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066704"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="de012-103">步驟 3：避免網路 Hairpin</span><span class="sxs-lookup"><span data-stu-id="de012-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="de012-104">*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="de012-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![階段 1 - 網路](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="de012-106">當繫結到目的地的流量 (例如內部部署安全性堆疊、雲端存取代理程式或雲端 Web 閘道) 首先被導向另一個中繼位置時，會發生[網路 hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)。</span><span class="sxs-lookup"><span data-stu-id="de012-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="de012-107">範例如下。</span><span class="sxs-lookup"><span data-stu-id="de012-107">Here is an example.</span></span>

![網路 hairpin 範例](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="de012-109">網路 hairpin 也可能是由於網路服務提供者在網際網路上的路由不良所導致。</span><span class="sxs-lookup"><span data-stu-id="de012-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="de012-110">Hairpin 會增加延遲，並可能將流量重新導向距離較遠的位置。</span><span class="sxs-lookup"><span data-stu-id="de012-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="de012-p102">若要最佳化 Microsoft 365 雲端型服務之流量的效能，請檢查提供當地網際網路連線的 ISP 是否在接近該位置之處具有與 Microsoft 全球網路的直接對等關係。這些連線沒有 Hairpin。</span><span class="sxs-lookup"><span data-stu-id="de012-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="de012-p103">如果您為 Microsoft 365 流量使用雲端型網路或安全性服務，請務必評估 Hairpinning 效果，並了解它對效能的影響。請檢查下列各項：</span><span class="sxs-lookup"><span data-stu-id="de012-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="de012-115">針對您的分公司和 Microsoft 全球網路對等點，透過其轉送流量之服務提供者的數目和位置</span><span class="sxs-lookup"><span data-stu-id="de012-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="de012-116">服務提供者與您的 ISP 和 Microsoft 之網路對等關係的品質</span><span class="sxs-lookup"><span data-stu-id="de012-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="de012-117">服務提供者基礎結構中回載的效能影響</span><span class="sxs-lookup"><span data-stu-id="de012-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="de012-118">儘可能將您的邊緣路由器設定為直接傳送信任的 Microsoft 365 流量，而不是透過處理網際網路流量的協力廠商雲端或雲端型網路安全性廠商來進行 Proxy 處理或通道傳送。</span><span class="sxs-lookup"><span data-stu-id="de012-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![略過網路 hairpin 的範例](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="de012-120">做為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step3)。</span><span class="sxs-lookup"><span data-stu-id="de012-120">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="de012-121">下一步</span><span class="sxs-lookup"><span data-stu-id="de012-121">Next step</span></span>

|||
|:-------|:-----|
|![步驟 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="de012-123">設定流量旁路</span><span class="sxs-lookup"><span data-stu-id="de012-123">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
