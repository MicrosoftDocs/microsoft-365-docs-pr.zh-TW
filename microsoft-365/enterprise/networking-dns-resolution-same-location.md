---
title: 步驟 2：設定每個辦公室的當地網際網路連線
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定 DNS 解析以提升效能。
ms.openlocfilehash: 2b3c38a9bf259f453121f7878992d1dc50f2ce97
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073263"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="125a5-103">步驟 2：設定每個辦公室的當地網際網路連線</span><span class="sxs-lookup"><span data-stu-id="125a5-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="125a5-104">*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 與 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="125a5-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="125a5-p101">在步驟 2 中，您確定您的每個辦公室都有當地網際網路連線，並使用當地 DNS 伺服器。這兩個元素需要減少連線延遲，並確定內部部署用戶端電腦連線至 Microsoft 365 雲端型服務的最近進入點。</span><span class="sxs-lookup"><span data-stu-id="125a5-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="125a5-p102">在大型組織的傳統網路中，網際網路流量會透過網路骨幹傳送至網際網路連線。這無法很好地用於將全球分散式軟體即服務 (SaaS) 基礎結構的效能最佳化，此基礎結構包含 Office 365，以及 Microsoft 365 中的 Enterprise Mobility + Security (EMS) 產品。</span><span class="sxs-lookup"><span data-stu-id="125a5-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="125a5-p103">Microsoft 全球網路包含全球 Microsoft 365 雲端服務集的前端伺服器。為獲得最佳效能，內部部署用戶端應該存取地理位置上最接近它們的前端伺服器，而不是透過網路骨幹傳送流量，以及存取最接近組織中央網際網路連線的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="125a5-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="125a5-p104">為了將用戶端要求導向至地理位置上最接近的前端伺服器，Microsoft 的 DNS 伺服器會使用對應用戶端初始連線要求的 DNS 查詢。因此，為達到最低網路延遲：</span><span class="sxs-lookup"><span data-stu-id="125a5-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="125a5-113">您組織的所有辦公室都應具有當地網際網路連線，以[最佳化](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)類別網路流量。</span><span class="sxs-lookup"><span data-stu-id="125a5-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="125a5-114">每個當地網際網路連線應該使用當地 DNS 伺服器，以從該位置傳送連出網際網路流量。</span><span class="sxs-lookup"><span data-stu-id="125a5-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="125a5-115">如需詳細資訊，請參閱[在本機上輸出網路連線](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)。</span><span class="sxs-lookup"><span data-stu-id="125a5-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="125a5-116">做為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step2)。</span><span class="sxs-lookup"><span data-stu-id="125a5-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="125a5-117">後續步驟</span><span class="sxs-lookup"><span data-stu-id="125a5-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="125a5-118">避免網路 Hairpin</span><span class="sxs-lookup"><span data-stu-id="125a5-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
