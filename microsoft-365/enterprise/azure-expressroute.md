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
description: 瞭解如何搭配使用 Azure ExpressRoute 搭配 Office 365，並規劃網路實施專案（如果您要使用它進行部署）。
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688244"
---
# <a name="azure-expressroute-for-office-365"></a><span data-ttu-id="4b719-103">Azure ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="4b719-103">Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="4b719-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="4b719-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4b719-105">瞭解 Azure ExpressRoute 與 Office 365 搭配使用的方式，以及如何規劃在部署 Azure ExpressRoute 以與 Office 365 搭配使用時所需的網路實施專案。</span><span class="sxs-lookup"><span data-stu-id="4b719-105">Learn how Azure ExpressRoute is used with Office 365 and how to plan the network implementation project that will be required if you are deploying Azure ExpressRoute for use with Office 365.</span></span> <span data-ttu-id="4b719-106">在 Azure 中執行的基礎結構和平臺服務常常會以網路架構和效能考慮的方式來受益。</span><span class="sxs-lookup"><span data-stu-id="4b719-106">Infrastructure and platform services running in Azure will often benefit by addressing network architecture and performance considerations.</span></span> <span data-ttu-id="4b719-107">在這兩種情況下，我們建議 ExpressRoute Azure。</span><span class="sxs-lookup"><span data-stu-id="4b719-107">We recommend ExpressRoute for Azure in these cases.</span></span> <span data-ttu-id="4b719-108">軟體即服務產品（如 Office 365 和 Dynamics 365）是透過網際網路安全且可靠地存取而建立的。</span><span class="sxs-lookup"><span data-stu-id="4b719-108">Software as a Service offerings like Office 365 and Dynamics 365 have been built to be accessed securely and reliably via the Internet.</span></span> <span data-ttu-id="4b719-109">您可以閱讀 Internet 效能及安全性，以及在 [評估 office 365 網路](assessing-network-connectivity.md)連線的文章中，您可能會考慮 office 365 的 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="4b719-109">You can read about Internet performance and security and when you might consider Azure ExpressRoute for Office 365 in the article [Assessing Office 365 network connectivity](assessing-network-connectivity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4b719-110">若要使用 Office 365 ExpressRoute，必須使用 Microsoft 授權。</span><span class="sxs-lookup"><span data-stu-id="4b719-110">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="4b719-111">當客戶的法規需求規定直接連線時，Microsoft 會檢查每家客戶要求的 ExpressRoute，並授權 Office 365 的使用。</span><span class="sxs-lookup"><span data-stu-id="4b719-111">Microsoft reviews every customer request and authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="4b719-112">如果您有這樣的需求，請提供文位元組選及網路連結，以 [瞭解 Office 365 要求表單 ExpressRoute](https://aka.ms/O365ERReview) 中是否需要直接連線才能開始 Microsoft 複查。</span><span class="sxs-lookup"><span data-stu-id="4b719-112">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="4b719-113">嘗試建立 Office 365 之路由篩選的未授權訂閱將會收到 [錯誤訊息](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="4b719-113">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>

<span data-ttu-id="4b719-114">您現在可以為選取的 Office 365 網路流量，新增到 Office 365 的直接網路連線。</span><span class="sxs-lookup"><span data-stu-id="4b719-114">You can now add a direct network connection to Office 365 for selected Office 365 network traffic.</span></span> <span data-ttu-id="4b719-115">Azure ExpressRoute 提供直接連線、可預知的效能，並提供 Microsoft 網路元件的99.95% 的正常執行時間 SLA。</span><span class="sxs-lookup"><span data-stu-id="4b719-115">Azure ExpressRoute offers a direct connection, predictable performance, and comes with an uptime SLA of 99.95% for the Microsoft networking components.</span></span> <span data-ttu-id="4b719-116">您仍需要網際網路連線，以取得未透過 Azure ExpressRoute 支援的服務。</span><span class="sxs-lookup"><span data-stu-id="4b719-116">You'll still require an internet connection for services that aren't supported over Azure ExpressRoute.</span></span>

## <a name="planning-azure-expressroute-for-office-365"></a><span data-ttu-id="4b719-117">規劃 Office 365 的 Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="4b719-117">Planning Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="4b719-118">除了網際網路連線之外，您還可以選擇透過直接連線路由傳送其 Office 365 網路流量的子集，以提供 Microsoft 網路元件的可預見性和99.95% 的運作時間 SLA。</span><span class="sxs-lookup"><span data-stu-id="4b719-118">In addition to internet connectivity, you may choose to route a subset of their Office 365 network traffic over a direct connection that offers predictability and a 99.95% uptime SLA for the Microsoft networking components.</span></span> <span data-ttu-id="4b719-119">Azure ExpressRoute 為您提供 Office 365 和其他 Microsoft 雲端服務的這種專用網路連接。</span><span class="sxs-lookup"><span data-stu-id="4b719-119">Azure ExpressRoute provides you with this dedicated network connection to Office 365 and other Microsoft cloud services.</span></span>

<span data-ttu-id="4b719-120">不論您是否有現有 MPLS WAN，都可以使用三種方式之一將 ExpressRoute 新增至網路架構;透過支援的雲端 exchange 共同位置提供者、乙太網點對點連線提供者，或透過 MPLS 連線提供者。</span><span class="sxs-lookup"><span data-stu-id="4b719-120">Regardless of whether you have an existing MPLS WAN, ExpressRoute can be added to your network architecture in one of three ways; through a supported cloud exchange co-location provider, an Ethernet point-to-point connection provider, or through an MPLS connection provider.</span></span> <span data-ttu-id="4b719-121">查看 [您地區中提供的提供者](https://azure.microsoft.com/documentation/articles/expressroute-locations/)。</span><span class="sxs-lookup"><span data-stu-id="4b719-121">See what [providers are available in your region](https://azure.microsoft.com/documentation/articles/expressroute-locations/).</span></span> <span data-ttu-id="4b719-122">直接 ExpressRoute 連線將會啟用與 [包含 Office 365 服務](azure-expressroute.md#BKMK_WhatDoIGet) 之應用程式的連線，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4b719-122">The direct ExpressRoute connection will enable connectivity to the applications outlined in [What Office 365 services are included?](azure-expressroute.md#BKMK_WhatDoIGet) below.</span></span> <span data-ttu-id="4b719-123">所有其他應用程式和服務的網路流量將繼續穿越網際網路。</span><span class="sxs-lookup"><span data-stu-id="4b719-123">Network traffic for all other applications and services will continue to traverse the internet.</span></span>

<span data-ttu-id="4b719-124">請考慮下列高層級網狀圖表，它會顯示一般的 Office 365 客戶連線到網際網路上的 Microsoft 資料中心，以存取所有的 Microsoft 應用程式，例如 Office 365、Windows Update 及 TechNet。</span><span class="sxs-lookup"><span data-stu-id="4b719-124">Consider the following high level network diagram which shows a typical Office 365 customer connecting to Microsoft's datacenters over the internet for access to all Microsoft applications such as Office 365, Windows Update, and TechNet.</span></span> <span data-ttu-id="4b719-125">客戶不論是從內部部署網路或獨立的網際網路連線，都使用類似的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="4b719-125">Customers use a similar network path regardless of whether they're connecting from an on-premises network or from an independent internet connection.</span></span>

![Office 365 網路連線能力](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

<span data-ttu-id="4b719-127">現在請查看已更新的圖表，它會描述同時使用網際網路和 ExpressRoute 連接至 Office 365 的 Office 365 客戶。</span><span class="sxs-lookup"><span data-stu-id="4b719-127">Now look at the updated diagram which depicts an Office 365 customer who uses both the internet and ExpressRoute to connect to Office 365.</span></span> <span data-ttu-id="4b719-128">請注意，有些連線（例如公用 DNS 和內容傳遞網路節點）仍然需要公用網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="4b719-128">Notice that some connections such as Public DNS and Content Delivery Network nodes still require the public internet connection.</span></span> <span data-ttu-id="4b719-129">此外，還請注意，未位於其 ExpressRoute 連線大樓中的客戶使用者是透過網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="4b719-129">Also notice the customer's users who are not located in their ExpressRoute connected building are connecting over the Internet.</span></span>

![使用 ExpressRoute 的 Office 365 連線能力](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

<span data-ttu-id="4b719-131">仍想要更多資訊？</span><span class="sxs-lookup"><span data-stu-id="4b719-131">Still want more information?</span></span> <span data-ttu-id="4b719-132">瞭解如何 [使用適用于 office 365 的 azure ExpressRoute 管理網路流量](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) ，並瞭解如何 [設定 Office 365 的 azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-faqs/)。</span><span class="sxs-lookup"><span data-stu-id="4b719-132">Learn how to [manage your network traffic with Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) and learn how to [configure Azure ExpressRoute for Office 365](https://azure.microsoft.com/documentation/articles/expressroute-faqs/).</span></span> <span data-ttu-id="4b719-133">我們也在頻道9上記錄了 [Office 365 訓練](https://channel9.msdn.com/series/aer) 系列的10個 part Azure ExpressRoute，以協助說明更徹底的概念。</span><span class="sxs-lookup"><span data-stu-id="4b719-133">We've also recorded a 10 part [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to help explain the concepts more thoroughly.</span></span>

## <a name="what-office-365-services-are-included"></a><span data-ttu-id="4b719-134">包含哪些 Office 365 服務？</span><span class="sxs-lookup"><span data-stu-id="4b719-134">What Office 365 services are included?</span></span>
<span data-ttu-id="4b719-135"><a name="BKMK_WhatDoIGet"> </a></span><span class="sxs-lookup"><span data-stu-id="4b719-135"><a name="BKMK_WhatDoIGet"> </a></span></span>

<span data-ttu-id="4b719-136">下表列出 ExpressRoute 支援的 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="4b719-136">The following table lists the Office 365 services that are supported over ExpressRoute.</span></span> <span data-ttu-id="4b719-137">請參閱 [Office 365 端點文章](https://aka.ms/o365endpoints) ，以瞭解這些應用程式的哪些網路要求需要網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="4b719-137">Please review the [Office 365 endpoints article](https://aka.ms/o365endpoints) to understand which network requests for these applications require internet connectivity.</span></span>

|<span data-ttu-id="4b719-138">**包含的應用程式**</span><span class="sxs-lookup"><span data-stu-id="4b719-138">**Applications included**</span></span>|
|:-----|
|<span data-ttu-id="4b719-139">Exchange Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-139">Exchange Online<sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-140">Exchange Online Protection<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-140">Exchange Online Protection<sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-141">Delve<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-141">Delve<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="4b719-142">商務用 Skype Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-142">Skype for Business Online<sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-143">Microsoft 團隊 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-143">Microsoft Teams <sup>1</sup></span></span> <br/> |
|<span data-ttu-id="4b719-144">SharePoint 線上<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-144">SharePoint Online<sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-145">Business<sup>1</sup>的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="4b719-145">OneDrive for Business<sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-146">Project Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-146">Project Online<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="4b719-147">入口網站和共用<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-147">Portal and shared<sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-148">Azure Active Directory (Azure AD) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-148">Azure Active Directory (Azure AD) <sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-149">Azure AD Connect<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-149">Azure AD Connect<sup>1</sup></span></span> <br/> <span data-ttu-id="4b719-150">Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b719-150">Office<sup>1</sup></span></span> <br/> |

<span data-ttu-id="4b719-151"><sup>1</sup> 這兩個應用程式都不受 ExpressRoute 支援網際網路連線性需求，請參閱 [Office 365 端點文章](https://aka.ms/o365endpoints) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4b719-151"><sup>1</sup> Each of these applications have internet connectivity requirements not supported over ExpressRoute, see the [Office 365 endpoints article](https://aka.ms/o365endpoints) for more information.</span></span>

<span data-ttu-id="4b719-152">未隨附于 Office 365 ExpressRoute 的服務是適用于企業用戶端下載、內部部署身分識別提供者 Sign-In 和 Office 365 (（中國中的 21 Vianet) 服務）的 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4b719-152">The services that aren't included with ExpressRoute for Office 365 are Microsoft 365 Apps for enterprise client downloads, On-premises Identity Provider Sign-In, and Office 365 (operated by 21 Vianet) service in China.</span></span>

## <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="4b719-153">實作 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="4b719-153">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="4b719-154">實施 ExpressRoute 需要網路和應用程式擁有人的參與，並需要仔細規劃，以判斷新的 [網路路由架構](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、頻寬需求、安全性的實施方式、高可用性等等。</span><span class="sxs-lookup"><span data-stu-id="4b719-154">Implementing ExpressRoute requires the involvement of network and application owners and requires careful planning to determine the new [network routing architecture](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), bandwidth requirements, where security will be implemented, high availability, and so on.</span></span> <span data-ttu-id="4b719-155">若要執行 ExpressRoute，您必須：</span><span class="sxs-lookup"><span data-stu-id="4b719-155">To implement ExpressRoute, you'll need to:</span></span>

1. <span data-ttu-id="4b719-156">完全瞭解 Office 365 連線規劃中的需求 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="4b719-156">Fully understand the need ExpressRoute satisfies in your Office 365 connectivity planning.</span></span> <span data-ttu-id="4b719-157">瞭解哪些應用程式會使用網際網路或 ExpressRoute，並利用 internet 和 ExpressRoute 的 Office 365 流量，充分規劃網路容量、安全性和高可用性需求。</span><span class="sxs-lookup"><span data-stu-id="4b719-157">Understand what applications will use the internet or ExpressRoute and fully plan your network capacity, security, and high availability needs in the context of using both the internet and ExpressRoute for Office 365 traffic.</span></span>

2. <span data-ttu-id="4b719-158">決定網際網路和 ExpressRoute 流量<sup>1</sup>的出口和對等位置。</span><span class="sxs-lookup"><span data-stu-id="4b719-158">Determine the egress and peering locations for both internet and ExpressRoute traffic<sup>1</sup>.</span></span>

3. <span data-ttu-id="4b719-159">決定網際網路和 ExpressRoute 連線所需的容量。</span><span class="sxs-lookup"><span data-stu-id="4b719-159">Determine the capacity required on the internet and ExpressRoute connections.</span></span>

4. <span data-ttu-id="4b719-160">制定實施安全性及其他標準周邊控制措施<sup>1</sup>的計畫。</span><span class="sxs-lookup"><span data-stu-id="4b719-160">Have a plan in place for implementing security and other standard perimeter controls<sup>1</sup>.</span></span>

5. <span data-ttu-id="4b719-161">具有有效的 Microsoft Azure 帳戶來訂閱 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="4b719-161">Have a valid Microsoft Azure account to subscribe to ExpressRoute.</span></span>

6. <span data-ttu-id="4b719-162">選取連線模型和核准的 [提供者](https://azure.microsoft.com/documentation/articles/expressroute-locations/)。</span><span class="sxs-lookup"><span data-stu-id="4b719-162">Select a connectivity model and an [approved provider](https://azure.microsoft.com/documentation/articles/expressroute-locations/).</span></span> <span data-ttu-id="4b719-163">請記住，客戶可以選擇多個連線模型或夥伴，而夥伴不需要與您現有的網路提供者相同。</span><span class="sxs-lookup"><span data-stu-id="4b719-163">Keep in mind, customers can select multiple connectivity models or partners and the partner doesn't need to be the same as your existing network provider.</span></span>

7. <span data-ttu-id="4b719-164">先驗證部署，再將流量導向 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="4b719-164">Validate deployment prior to directing traffic to ExpressRoute.</span></span>

8. <span data-ttu-id="4b719-165">選擇性地 [實施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) ，並評估區域擴充。</span><span class="sxs-lookup"><span data-stu-id="4b719-165">Optionally [implement QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) and evaluate regional expansion.</span></span>

<span data-ttu-id="4b719-166"><sup>1</sup> 重要的效能考慮。</span><span class="sxs-lookup"><span data-stu-id="4b719-166"><sup>1</sup> Important performance considerations.</span></span> <span data-ttu-id="4b719-167">這裡的決策可能會大幅影響延遲，這對於商務用 Skype 之類的應用程式很重要。</span><span class="sxs-lookup"><span data-stu-id="4b719-167">Decisions here can dramatically impact latency which is a critical for applications such as Skype for Business.</span></span>

<span data-ttu-id="4b719-168">如需其他參考，除了[ExpressRoute 檔](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)之外，還請使用我們的[路由輔助線](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)。</span><span class="sxs-lookup"><span data-stu-id="4b719-168">For additional references, use our [routing guide](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) in addition to the [ExpressRoute documentation](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).</span></span>

<span data-ttu-id="4b719-169">若要購買 Office 365 ExpressRoute，您必須與一或多個核准的 [提供者](https://azure.microsoft.com/documentation/articles/expressroute-locations/) 合作，以使用 ExpressRoute 優質訂閱來布建所需號碼和大小的電路。</span><span class="sxs-lookup"><span data-stu-id="4b719-169">To purchase ExpressRoute for Office 365, you'll need to work with one or more [approved providers](https://azure.microsoft.com/documentation/articles/expressroute-locations/) to provision the desired number and size circuits with an ExpressRoute Premium subscription.</span></span> <span data-ttu-id="4b719-170">沒有其他可從 Office 365 購買的授權。</span><span class="sxs-lookup"><span data-stu-id="4b719-170">There are no additional licenses to purchase from Office 365.</span></span>

<span data-ttu-id="4b719-171">您可以使用下列短連結返回這裡：[https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)</span><span class="sxs-lookup"><span data-stu-id="4b719-171">Here's a short link you can use to come back: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)</span></span>

<span data-ttu-id="4b719-172">準備好註冊 [Office 365 的 ExpressRoute](https://aka.ms/ert)嗎？</span><span class="sxs-lookup"><span data-stu-id="4b719-172">Ready to sign-up for [ExpressRoute for Office 365](https://aka.ms/ert)?</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b719-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="4b719-173">Related Topics</span></span>

[<span data-ttu-id="4b719-174">評估 Office 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="4b719-174">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="4b719-175">管理 ExpressRoute for Office 365 連線</span><span class="sxs-lookup"><span data-stu-id="4b719-175">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)

[<span data-ttu-id="4b719-176">使用 ExpressRoute for Office 365 進行路由傳送</span><span class="sxs-lookup"><span data-stu-id="4b719-176">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)

[<span data-ttu-id="4b719-177">使用 ExpressRoute for Office 365 進行網路規劃</span><span class="sxs-lookup"><span data-stu-id="4b719-177">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)

[<span data-ttu-id="4b719-178">實作 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="4b719-178">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)

[<span data-ttu-id="4b719-179">在 ExpressRoute for Office 365 案例中使用 BGP 社區</span><span class="sxs-lookup"><span data-stu-id="4b719-179">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)

[<span data-ttu-id="4b719-180">商務用 Skype Online 中的媒體品質和網路連線效能</span><span class="sxs-lookup"><span data-stu-id="4b719-180">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[<span data-ttu-id="4b719-181">使用基準與效能歷程記錄進行 Office 365 效能調整</span><span class="sxs-lookup"><span data-stu-id="4b719-181">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="4b719-182">Office 365 的效能疑難排解規劃</span><span class="sxs-lookup"><span data-stu-id="4b719-182">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="4b719-183">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="4b719-183">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="4b719-184">Office 365 網路與效能調整</span><span class="sxs-lookup"><span data-stu-id="4b719-184">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

## <a name="see-also"></a><span data-ttu-id="4b719-185">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4b719-185">See also</span></span>

[<span data-ttu-id="4b719-186">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="4b719-186">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)