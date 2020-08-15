---
title: 設定 Microsoft 365 的網路
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 尋找包含資訊的文章連結，以協助您設定 Microsoft 365 的網路，包括網路連線概述和端點清單。
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688312"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="d52cf-103">設定 Microsoft 365 的網路</span><span class="sxs-lookup"><span data-stu-id="d52cf-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="d52cf-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="d52cf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d52cf-105">Microsoft 365 上架的一個重要部分是，確定您的網路和網際網路連線已設定為優化的存取。</span><span class="sxs-lookup"><span data-stu-id="d52cf-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="d52cf-106">將您的內部部署網路設定為存取全域分散式軟體即服務 (SaaS) 雲端與針對內部部署資料中心和中央網際網路連線的流量優化的傳統網路有所不同。</span><span class="sxs-lookup"><span data-stu-id="d52cf-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="d52cf-107">參閱這些文章以了解主要差異，並修改您的邊緣裝置、用戶端電腦與內部部署網路，以為您的內部使用者取得最佳的效能。</span><span class="sxs-lookup"><span data-stu-id="d52cf-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="d52cf-108">Microsoft 365 網路的運作方式</span><span class="sxs-lookup"><span data-stu-id="d52cf-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="d52cf-109">請參閱下列文章，以瞭解 Microsoft 365 的連線能力：</span><span class="sxs-lookup"><span data-stu-id="d52cf-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="d52cf-110">Microsoft 365 網路連線能力概觀</span><span class="sxs-lookup"><span data-stu-id="d52cf-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="d52cf-111">Microsoft 365 網路連接原則</span><span class="sxs-lookup"><span data-stu-id="d52cf-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="d52cf-112">評估 Microsoft 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="d52cf-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="d52cf-113">如需增強效能的建議，請參閱 [Microsoft 365 的網路規劃和效能調整](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="d52cf-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="d52cf-114">支援 Microsoft 365 網路作為網路設備廠商</span><span class="sxs-lookup"><span data-stu-id="d52cf-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="d52cf-p102">如果您是網路設備廠商，請加入 [Office 365 網路合作夥伴計畫](microsoft-365-networking-partner-program.md)。註冊此計畫，將 Office 365 網路連線原則建置到您的產品與解決方案中。</span><span class="sxs-lookup"><span data-stu-id="d52cf-p102">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="d52cf-117">Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-117">Office 365 endpoints</span></span>

<span data-ttu-id="d52cf-118">端點為一組目的地 IP 位址、DNS 網域名稱，以及網際網路上 Office 365 流量的 URL。</span><span class="sxs-lookup"><span data-stu-id="d52cf-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="d52cf-p103">若要最佳化 Office 365 雲端式服務的效能，有些端點需要由用戶端瀏覽器和邊緣網路中的裝置進行特別處理。這些裝置包括防火牆、SSL 中斷和檢查及封包檢查裝置，以及資料外洩防護系統。</span><span class="sxs-lookup"><span data-stu-id="d52cf-p103">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network. These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="d52cf-121">請參閱[管理 Office 365 端點](managing-office-365-endpoints.md)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d52cf-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="d52cf-p104">目前有五種不同的 Office 365 雲端。下表顯示每種雲端的端點清單。</span><span class="sxs-lookup"><span data-stu-id="d52cf-p104">There are currently five different Office 365 clouds. This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="d52cf-124">端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-124">Endpoints</span></span> | <span data-ttu-id="d52cf-125">描述</span><span class="sxs-lookup"><span data-stu-id="d52cf-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="d52cf-126">全球端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="d52cf-127">全球 Office 365 訂閱的端點，包括美國政府社群雲端 (GCC)。</span><span class="sxs-lookup"><span data-stu-id="d52cf-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="d52cf-128">美國政府 DoD 端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="d52cf-129">適用於美國國防部 (DoD) 訂閱的端點。</span><span class="sxs-lookup"><span data-stu-id="d52cf-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="d52cf-130">美國政府 GCC High 端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="d52cf-131">適用於美國政府社群雲端高 (GCC High) 訂閱的端點。</span><span class="sxs-lookup"><span data-stu-id="d52cf-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="d52cf-132">由 21Vianet 營運的 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="d52cf-133">由 21Vianet 營運的 Office 365 端點，其目的是為了符合中國的 Office 365 需求。</span><span class="sxs-lookup"><span data-stu-id="d52cf-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="d52cf-134">Office 365 Germany 端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="d52cf-135">針對德國、歐盟 (EU) 以及歐洲自由貿易聯盟 (EFTA) 中受管制客戶的歐洲個別雲端端點。</span><span class="sxs-lookup"><span data-stu-id="d52cf-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="d52cf-136">若要自動取得您 Office 365 雲端的最新端點清單，請參閱 [Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="d52cf-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="d52cf-137">如需其他端點，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="d52cf-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="d52cf-138">未包含在 Web 服務中的其他端點</span><span class="sxs-lookup"><span data-stu-id="d52cf-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="d52cf-139">Mac 版 Office 2016 中的網路要求</span><span class="sxs-lookup"><span data-stu-id="d52cf-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="d52cf-140">Microsoft 365 網路的其他主題</span><span class="sxs-lookup"><span data-stu-id="d52cf-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="d52cf-141">請參閱下列文章，瞭解 Microsoft 365 網路中的特殊主題：</span><span class="sxs-lookup"><span data-stu-id="d52cf-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="d52cf-142">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="d52cf-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="d52cf-143">Office 365 服務中的 IPv6 支援</span><span class="sxs-lookup"><span data-stu-id="d52cf-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="d52cf-144">Office 365 的 NAT 支援</span><span class="sxs-lookup"><span data-stu-id="d52cf-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="d52cf-145">適用於 Microsoft 365 的 ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="d52cf-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="d52cf-146">請參閱下列文章，了解針對 Office 365 流量使用 ExpressRoute 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="d52cf-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="d52cf-147">Azure ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="d52cf-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="d52cf-148">實作 ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="d52cf-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="d52cf-149">使用 ExpressRoute for Office 365 進行網路規劃</span><span class="sxs-lookup"><span data-stu-id="d52cf-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="d52cf-150">使用 ExpressRoute for Office 365 進行路由傳送</span><span class="sxs-lookup"><span data-stu-id="d52cf-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
