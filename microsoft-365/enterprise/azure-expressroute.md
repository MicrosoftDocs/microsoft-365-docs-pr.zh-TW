---
title: Azure ExpressRoute for Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: 瞭解如何使用 Azure ExpressRoute 搭配 Office 365 並規劃網路實施專案（如果您要使用它進行部署）。
ms.openlocfilehash: c43957435272e1a3b6f738d33a2dd12e81dfc013
ms.sourcegitcommit: aff2331f9a3f22591f8ace1a646809969d28c120
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52464414"
---
# <a name="azure-expressroute-for-office-365"></a><span data-ttu-id="0cee3-103">Azure ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="0cee3-103">Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="0cee3-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="0cee3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0cee3-105">瞭解如何搭配 Office 365 使用 azure ExpressRoute，以及如何規劃要搭配 Office 365 使用 azure ExpressRoute 時所需的網路實施專案。</span><span class="sxs-lookup"><span data-stu-id="0cee3-105">Learn how Azure ExpressRoute is used with Office 365 and how to plan the network implementation project that will be required if you are deploying Azure ExpressRoute for use with Office 365.</span></span> <span data-ttu-id="0cee3-106">在 Azure 中執行的基礎結構和平臺服務常常會以網路架構和效能考慮的方式來受益。</span><span class="sxs-lookup"><span data-stu-id="0cee3-106">Infrastructure and platform services running in Azure will often benefit by addressing network architecture and performance considerations.</span></span> <span data-ttu-id="0cee3-107">在這兩種情況下，我們建議 ExpressRoute Azure。</span><span class="sxs-lookup"><span data-stu-id="0cee3-107">We recommend ExpressRoute for Azure in these cases.</span></span> <span data-ttu-id="0cee3-108">軟體即服務產品（如 Office 365 和 Dynamics 365）已透過網際網路安全且可靠地存取。</span><span class="sxs-lookup"><span data-stu-id="0cee3-108">Software as a Service offerings like Office 365 and Dynamics 365 have been built to be accessed securely and reliably via the Internet.</span></span> <span data-ttu-id="0cee3-109">您可以閱讀 Internet 效能及安全性，以及在[評估 Office 365 網路](assessing-network-connectivity.md)連線的文章中，您可能會針對 Office 365 考慮 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="0cee3-109">You can read about Internet performance and security and when you might consider Azure ExpressRoute for Office 365 in the article [Assessing Office 365 network connectivity](assessing-network-connectivity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0cee3-110">Microsoft Defender for Endpoint 不會提供與 Azure ExpressRoute 的整合。</span><span class="sxs-lookup"><span data-stu-id="0cee3-110">Microsoft Defender for Endpoint does not provide integration with Azure ExpressRoute.</span></span> <span data-ttu-id="0cee3-111">雖然這不會讓客戶定義 ExpressRoute 規則，可讓客戶從私人網路連接至 Microsoft Defender for Endpoint cloud services，但會在服務或雲端基礎結構演變時，維持規則。</span><span class="sxs-lookup"><span data-stu-id="0cee3-111">While this does not stop customers from defining ExpressRoute rules that enable connectivity from a private network to Microsoft Defender for Endpoint cloud services, it is up to the customer to maintain rules as the service or cloud infrastructure evolves.</span></span>

> [!NOTE]
> <span data-ttu-id="0cee3-112">建議您不要針對 Microsoft 365 ExpressRoute，因為在大多數情況下，它不會提供服務的最佳連線模型。</span><span class="sxs-lookup"><span data-stu-id="0cee3-112">We do not recommend ExpressRoute for Microsoft 365 because it does not provide the best connectivity model for the service in most circumstances.</span></span> <span data-ttu-id="0cee3-113">因此，使用此 Microsoft 365 的連線模型時，需要 Microsoft 授權。</span><span class="sxs-lookup"><span data-stu-id="0cee3-113">As such, Microsoft authorization is required to use this connectivity model for Microsoft 365.</span></span> <span data-ttu-id="0cee3-114">我們只會在必要的少數案例中查看每個客戶要求並授權 ExpressRoute Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0cee3-114">We review every customer request and authorize ExpressRoute for Microsoft 365 only in the rare scenarios where it is necessary.</span></span> <span data-ttu-id="0cee3-115">如需詳細資訊，請閱讀[Microsoft 365 指南的 ExpressRoute](https://aka.ms/erguide) ，並遵循您的生產力、網路及安全性小組的完整檔評論。請與您的 Microsoft 帳戶小組合作，視需要提交例外狀況。</span><span class="sxs-lookup"><span data-stu-id="0cee3-115">Please read the [ExpressRoute for Microsoft 365 guide](https://aka.ms/erguide) for more information and following a comprehensive review of the document with your productivity, network, and security teams, work with your Microsoft account team to submit an exception if needed.</span></span> <span data-ttu-id="0cee3-116">嘗試為 Office 365 建立路由篩選的未授權訂閱將會收到[錯誤訊息](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="0cee3-116">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>

## <a name="planning-azure-expressroute-for-office-365"></a><span data-ttu-id="0cee3-117">規劃 Office 365 的 Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="0cee3-117">Planning Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="0cee3-118">除了網際網路連線之外，您還可以選擇透過直接連線路由傳送其 Office 365 網路流量的子集，以提供可預見性和 Microsoft 網路元件的99.95% 正常運作時間 SLA。</span><span class="sxs-lookup"><span data-stu-id="0cee3-118">In addition to internet connectivity, you may choose to route a subset of their Office 365 network traffic over a direct connection that offers predictability and a 99.95% uptime SLA for the Microsoft networking components.</span></span> <span data-ttu-id="0cee3-119">Azure ExpressRoute 會為您提供與 Office 365 和其他 Microsoft 雲端服務的專用網路連接。</span><span class="sxs-lookup"><span data-stu-id="0cee3-119">Azure ExpressRoute provides you with this dedicated network connection to Office 365 and other Microsoft cloud services.</span></span>

<span data-ttu-id="0cee3-120">不論您是否有現有 MPLS WAN，都可以使用三種方式之一將 ExpressRoute 新增至網路架構;透過支援的雲端 exchange 共同位置提供者、乙太網點對點連線提供者，或透過 MPLS 連線提供者。</span><span class="sxs-lookup"><span data-stu-id="0cee3-120">Regardless of whether you have an existing MPLS WAN, ExpressRoute can be added to your network architecture in one of three ways; through a supported cloud exchange co-location provider, an Ethernet point-to-point connection provider, or through an MPLS connection provider.</span></span> <span data-ttu-id="0cee3-121">查看 [您地區中提供的提供者](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="0cee3-121">See what [providers are available in your region](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="0cee3-122">直接 ExpressRoute 連線功能可讓您連線至所述的應用程式[Office 365 服務](azure-expressroute.md#BKMK_WhatDoIGet)中所述的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0cee3-122">The direct ExpressRoute connection will enable connectivity to the applications outlined in [What Office 365 services are included?](azure-expressroute.md#BKMK_WhatDoIGet) below.</span></span> <span data-ttu-id="0cee3-123">所有其他應用程式和服務的網路流量將繼續穿越網際網路。</span><span class="sxs-lookup"><span data-stu-id="0cee3-123">Network traffic for all other applications and services will continue to traverse the internet.</span></span>

<span data-ttu-id="0cee3-124">請考慮下列高層級網狀圖表，它會顯示一般 Office 365 客戶透過網際網路連線至 microsoft 資料中心，以存取所有 microsoft 應用程式，例如 Office 365、Windows 更新及 TechNet。</span><span class="sxs-lookup"><span data-stu-id="0cee3-124">Consider the following high level network diagram which shows a typical Office 365 customer connecting to Microsoft's datacenters over the internet for access to all Microsoft applications such as Office 365, Windows Update, and TechNet.</span></span> <span data-ttu-id="0cee3-125">客戶不論是從內部部署網路或獨立的網際網路連線，都使用類似的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="0cee3-125">Customers use a similar network path regardless of whether they're connecting from an on-premises network or from an independent internet connection.</span></span>

![Office 365 網路連線能力](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

<span data-ttu-id="0cee3-127">現在，請查看已更新的圖表，它會描述同時使用網際網路與 ExpressRoute 的 Office 365 客戶，以連接至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0cee3-127">Now look at the updated diagram which depicts an Office 365 customer who uses both the internet and ExpressRoute to connect to Office 365.</span></span> <span data-ttu-id="0cee3-128">請注意，有些連線（例如公用 DNS 和內容傳遞網路節點）仍然需要公用網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="0cee3-128">Notice that some connections such as Public DNS and Content Delivery Network nodes still require the public internet connection.</span></span> <span data-ttu-id="0cee3-129">此外，還請注意，未位於其 ExpressRoute 連線大樓中的客戶使用者是透過網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="0cee3-129">Also notice the customer's users who are not located in their ExpressRoute connected building are connecting over the Internet.</span></span>

![Office 365 與 ExpressRoute 的連接](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

<span data-ttu-id="0cee3-131">仍想要更多資訊？</span><span class="sxs-lookup"><span data-stu-id="0cee3-131">Still want more information?</span></span> <span data-ttu-id="0cee3-132">瞭解如何[使用 azure ExpressRoute Office 365 管理網路流量](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)，並瞭解如何為[Office 365 設定 azure ExpressRoute](/azure/expressroute/expressroute-faqs)。</span><span class="sxs-lookup"><span data-stu-id="0cee3-132">Learn how to [manage your network traffic with Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) and learn how to [configure Azure ExpressRoute for Office 365](/azure/expressroute/expressroute-faqs).</span></span> <span data-ttu-id="0cee3-133">我們也針對通道9上的[Office 365 訓練](https://channel9.msdn.com/series/aer)系列記錄了10部分 Azure ExpressRoute，以協助說明更徹底的概念。</span><span class="sxs-lookup"><span data-stu-id="0cee3-133">We've also recorded a 10 part [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to help explain the concepts more thoroughly.</span></span>

## <a name="what-office-365-services-are-included"></a><span data-ttu-id="0cee3-134">包含哪些 Office 365 服務？</span><span class="sxs-lookup"><span data-stu-id="0cee3-134">What Office 365 services are included?</span></span>
<span data-ttu-id="0cee3-135"><a name="BKMK_WhatDoIGet"> </a></span><span class="sxs-lookup"><span data-stu-id="0cee3-135"><a name="BKMK_WhatDoIGet"> </a></span></span>

<span data-ttu-id="0cee3-136">下表列出 ExpressRoute 支援的 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="0cee3-136">The following table lists the Office 365 services that are supported over ExpressRoute.</span></span> <span data-ttu-id="0cee3-137">請複查[Office 365 端點文章](./urls-and-ip-address-ranges.md)，以瞭解這些應用程式的哪些網路要求需要網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="0cee3-137">Please review the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) to understand which network requests for these applications require internet connectivity.</span></span>

| <span data-ttu-id="0cee3-138">包含的應用程式</span><span class="sxs-lookup"><span data-stu-id="0cee3-138">Applications included</span></span> |
|:-----|
|<span data-ttu-id="0cee3-139">Exchange Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-139">Exchange Online<sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-140">Exchange Online Protection<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-140">Exchange Online Protection<sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-141">Delve<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-141">Delve<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="0cee3-142">商務用 Skype線上<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-142">Skype for Business Online<sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-143">Microsoft Teams <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-143">Microsoft Teams <sup>1</sup></span></span> <br/> |
|<span data-ttu-id="0cee3-144">SharePoint線上<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-144">SharePoint Online<sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-145">商務用 OneDrive<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-145">OneDrive for Business<sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-146">Project Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-146">Project Online<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="0cee3-147">入口網站和共用<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-147">Portal and shared<sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-148">Azure Active Directory (Azure AD) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-148">Azure Active Directory (Azure AD) <sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-149">Azure AD 連線<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-149">Azure AD Connect<sup>1</sup></span></span> <br/> <span data-ttu-id="0cee3-150">Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cee3-150">Office<sup>1</sup></span></span> <br/> |

<span data-ttu-id="0cee3-151"><sup>1</sup>每個應用程式都有 ExpressRoute 不支援的網際網路連線需求，請參閱[Office 365 端點文章](./urls-and-ip-address-ranges.md)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0cee3-151"><sup>1</sup> Each of these applications have internet connectivity requirements not supported over ExpressRoute, see the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) for more information.</span></span>

<span data-ttu-id="0cee3-152">Office 365 中未包含的 ExpressRoute 服務，會 Microsoft 365 Apps 企業版用戶端下載、內部部署身分識別提供者 Sign-In，以及 Office 365 在中國使用 21 Vianet (服務運作) 。</span><span class="sxs-lookup"><span data-stu-id="0cee3-152">The services that aren't included with ExpressRoute for Office 365 are Microsoft 365 Apps for enterprise client downloads, On-premises Identity Provider Sign-In, and Office 365 (operated by 21 Vianet) service in China.</span></span>

## <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="0cee3-153">實作 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="0cee3-153">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="0cee3-154">實施 ExpressRoute 需要網路和應用程式擁有人的參與，並需要仔細規劃，以判斷新的 [網路路由架構](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、頻寬需求、安全性的實施方式、高可用性等等。</span><span class="sxs-lookup"><span data-stu-id="0cee3-154">Implementing ExpressRoute requires the involvement of network and application owners and requires careful planning to determine the new [network routing architecture](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), bandwidth requirements, where security will be implemented, high availability, and so on.</span></span> <span data-ttu-id="0cee3-155">若要執行 ExpressRoute，您必須：</span><span class="sxs-lookup"><span data-stu-id="0cee3-155">To implement ExpressRoute, you'll need to:</span></span>

1. <span data-ttu-id="0cee3-156">完全瞭解 Office 365 連線規劃中是否需要 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="0cee3-156">Fully understand the need ExpressRoute satisfies in your Office 365 connectivity planning.</span></span> <span data-ttu-id="0cee3-157">瞭解哪些應用程式會使用網際網路或 ExpressRoute，並利用 internet 和 ExpressRoute Office 365 流量，充分規劃網路容量、安全性和高可用性需求。</span><span class="sxs-lookup"><span data-stu-id="0cee3-157">Understand what applications will use the internet or ExpressRoute and fully plan your network capacity, security, and high availability needs in the context of using both the internet and ExpressRoute for Office 365 traffic.</span></span>

2. <span data-ttu-id="0cee3-158">決定網際網路和 ExpressRoute 流量<sup>1</sup>的出口和對等位置。</span><span class="sxs-lookup"><span data-stu-id="0cee3-158">Determine the egress and peering locations for both internet and ExpressRoute traffic<sup>1</sup>.</span></span>

3. <span data-ttu-id="0cee3-159">決定網際網路和 ExpressRoute 連線所需的容量。</span><span class="sxs-lookup"><span data-stu-id="0cee3-159">Determine the capacity required on the internet and ExpressRoute connections.</span></span>

4. <span data-ttu-id="0cee3-160">制定實施安全性及其他標準周邊控制措施<sup>1</sup>的計畫。</span><span class="sxs-lookup"><span data-stu-id="0cee3-160">Have a plan in place for implementing security and other standard perimeter controls<sup>1</sup>.</span></span>

5. <span data-ttu-id="0cee3-161">具有有效的 Microsoft Azure 帳戶，可訂閱 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="0cee3-161">Have a valid Microsoft Azure account to subscribe to ExpressRoute.</span></span>

6. <span data-ttu-id="0cee3-162">選取連線模型和核准的 [提供者](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="0cee3-162">Select a connectivity model and an [approved provider](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="0cee3-163">請記住，客戶可以選擇多個連線模型或夥伴，而夥伴不需要與您現有的網路提供者相同。</span><span class="sxs-lookup"><span data-stu-id="0cee3-163">Keep in mind, customers can select multiple connectivity models or partners and the partner doesn't need to be the same as your existing network provider.</span></span>

7. <span data-ttu-id="0cee3-164">先驗證部署，再將流量導向 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="0cee3-164">Validate deployment prior to directing traffic to ExpressRoute.</span></span>

8. <span data-ttu-id="0cee3-165">選擇性地 [實施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) ，並評估區域擴充。</span><span class="sxs-lookup"><span data-stu-id="0cee3-165">Optionally [implement QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) and evaluate regional expansion.</span></span>

<span data-ttu-id="0cee3-166"><sup>1</sup> 重要的效能考慮。</span><span class="sxs-lookup"><span data-stu-id="0cee3-166"><sup>1</sup> Important performance considerations.</span></span> <span data-ttu-id="0cee3-167">這裡的決策可能會大幅影響延遲，這對商務用 Skype 的應用程式很重要。</span><span class="sxs-lookup"><span data-stu-id="0cee3-167">Decisions here can dramatically impact latency which is a critical for applications such as Skype for Business.</span></span>

<span data-ttu-id="0cee3-168">如需其他參考，除了[ExpressRoute 檔](/azure/expressroute/expressroute-introduction)之外，還請使用我們的[路由輔助線](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)。</span><span class="sxs-lookup"><span data-stu-id="0cee3-168">For additional references, use our [routing guide](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) in addition to the [ExpressRoute documentation](/azure/expressroute/expressroute-introduction).</span></span>

<span data-ttu-id="0cee3-169">若要購買 Office 365 的 ExpressRoute，您需要與一個或多個[核准的提供者](/azure/expressroute/expressroute-locations)合作，以使用 ExpressRoute 進階版訂閱來布建所需的號碼和大小的電路。</span><span class="sxs-lookup"><span data-stu-id="0cee3-169">To purchase ExpressRoute for Office 365, you'll need to work with one or more [approved providers](/azure/expressroute/expressroute-locations) to provision the desired number and size circuits with an ExpressRoute Premium subscription.</span></span> <span data-ttu-id="0cee3-170">Office 365 購買其他授權。</span><span class="sxs-lookup"><span data-stu-id="0cee3-170">There are no additional licenses to purchase from Office 365.</span></span>

<span data-ttu-id="0cee3-171">您可以使用下列短連結返回這裡：[https://aka.ms/expressrouteoffice365]()</span><span class="sxs-lookup"><span data-stu-id="0cee3-171">Here's a short link you can use to come back: [https://aka.ms/expressrouteoffice365]()</span></span>

<span data-ttu-id="0cee3-172">準備好註冊[Office 365 的 ExpressRoute 了](https://aka.ms/ert)嗎？</span><span class="sxs-lookup"><span data-stu-id="0cee3-172">Ready to sign-up for [ExpressRoute for Office 365](https://aka.ms/ert)?</span></span>

## <a name="related-topics"></a><span data-ttu-id="0cee3-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="0cee3-173">Related Topics</span></span>

[<span data-ttu-id="0cee3-174">評估 Office 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="0cee3-174">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="0cee3-175">管理 ExpressRoute for Office 365 連線</span><span class="sxs-lookup"><span data-stu-id="0cee3-175">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)

[<span data-ttu-id="0cee3-176">使用 ExpressRoute for Office 365 進行路由傳送</span><span class="sxs-lookup"><span data-stu-id="0cee3-176">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)

[<span data-ttu-id="0cee3-177">使用 ExpressRoute for Office 365 進行網路規劃</span><span class="sxs-lookup"><span data-stu-id="0cee3-177">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)

[<span data-ttu-id="0cee3-178">實作 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="0cee3-178">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)

[<span data-ttu-id="0cee3-179">在 Office 365 案例的 ExpressRoute 中使用 BGP 社區</span><span class="sxs-lookup"><span data-stu-id="0cee3-179">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)

[<span data-ttu-id="0cee3-180">商務用 Skype Online 中的媒體品質和網路連線效能</span><span class="sxs-lookup"><span data-stu-id="0cee3-180">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[<span data-ttu-id="0cee3-181">使用基準與效能歷程記錄進行 Office 365 效能調整</span><span class="sxs-lookup"><span data-stu-id="0cee3-181">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="0cee3-182">Office 365 的效能疑難排解規劃</span><span class="sxs-lookup"><span data-stu-id="0cee3-182">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="0cee3-183">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="0cee3-183">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="0cee3-184">Office 365 網路與效能調整</span><span class="sxs-lookup"><span data-stu-id="0cee3-184">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

## <a name="see-also"></a><span data-ttu-id="0cee3-185">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0cee3-185">See also</span></span>

[<span data-ttu-id="0cee3-186">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="0cee3-186">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
