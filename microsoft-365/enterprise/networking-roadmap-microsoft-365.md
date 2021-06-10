---
title: Microsoft 365 的網路藍圖
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 實施 Microsoft 365 網路的藍圖。
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923549"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="39292-103">Microsoft 365 的網路藍圖</span><span class="sxs-lookup"><span data-stu-id="39292-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="39292-104">適用于企業的 Microsoft 365 包括共同作業和生產力雲端服務、Microsoft Intune，以及 Microsoft Azure 的許多身分識別及安全性服務。</span><span class="sxs-lookup"><span data-stu-id="39292-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="39292-105">這些所有雲端服務都依賴透過網際網路或專用線路從用戶端裝置連線的安全性、效能及可靠性。</span><span class="sxs-lookup"><span data-stu-id="39292-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="39292-106">為了裝載這些服務並且讓世界各地的客戶使用，Microsoft 設計了強調效能和整合的網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="39292-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="39292-107">您的 Microsoft 365 上架重要的一點是，確定您的網路和網際網路連線已設定為優化的存取。</span><span class="sxs-lookup"><span data-stu-id="39292-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="39292-108">將您的內部部署網路設定為存取全域分散式軟體即服務 (SaaS) 雲端與針對內部部署資料中心和中央網際網路連線的流量優化的傳統網路有所不同。</span><span class="sxs-lookup"><span data-stu-id="39292-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="39292-109">參閱這些文章以了解主要差異，並修改您的邊緣裝置、用戶端電腦與內部部署網路，以為您的內部使用者取得最佳的效能。</span><span class="sxs-lookup"><span data-stu-id="39292-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="39292-110">方案</span><span class="sxs-lookup"><span data-stu-id="39292-110">Plan</span></span>

<span data-ttu-id="39292-111">在網路實施的規劃階段：</span><span class="sxs-lookup"><span data-stu-id="39292-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="39292-112">瞭解 Microsoft 365 網路的運作方式</span><span class="sxs-lookup"><span data-stu-id="39292-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="39292-113">評估您目前的網路連線能力</span><span class="sxs-lookup"><span data-stu-id="39292-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="39292-114">判斷 ExpressRoute 是否適合您的組織</span><span class="sxs-lookup"><span data-stu-id="39292-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="39292-115">規劃網路裝置</span><span class="sxs-lookup"><span data-stu-id="39292-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="39292-116">讓您的網路設定進行遷移</span><span class="sxs-lookup"><span data-stu-id="39292-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="39292-117">部署</span><span class="sxs-lookup"><span data-stu-id="39292-117">Deploy</span></span>

<span data-ttu-id="39292-118">在網路實施的部署階段：</span><span class="sxs-lookup"><span data-stu-id="39292-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="39292-119">確定您的商業網路已優化 Microsoft 365 連線能力</span><span class="sxs-lookup"><span data-stu-id="39292-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="39292-120">新增組織的 DNS 網域</span><span class="sxs-lookup"><span data-stu-id="39292-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="39292-121">優化 Microsoft 365 端點的連線能力</span><span class="sxs-lookup"><span data-stu-id="39292-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="39292-122">優化遠端工作者的連線能力</span><span class="sxs-lookup"><span data-stu-id="39292-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="39292-123">如有需要， [設定 ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="39292-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="39292-124">管理</span><span class="sxs-lookup"><span data-stu-id="39292-124">Manage</span></span>

<span data-ttu-id="39292-125">在網路實施的管理階段：</span><span class="sxs-lookup"><span data-stu-id="39292-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="39292-126">確定您的網路裝置使用的是最新的 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="39292-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="39292-127">監視與調整網路效能</span><span class="sxs-lookup"><span data-stu-id="39292-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="39292-128">監視您的 ExpressRoute 連接</span><span class="sxs-lookup"><span data-stu-id="39292-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="39292-129">網路設備廠商</span><span class="sxs-lookup"><span data-stu-id="39292-129">Network equipment vendors</span></span>

<span data-ttu-id="39292-130">如果您是網路設備廠商，請加入[Microsoft 365 網路合作夥伴計畫](microsoft-365-networking-partner-program.md)。</span><span class="sxs-lookup"><span data-stu-id="39292-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="39292-131">在程式中註冊，以建立產品及解決方案中 Microsoft 365 的網路連線性原則。</span><span class="sxs-lookup"><span data-stu-id="39292-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="39292-132">Contoso 如何聯網 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="39292-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="39292-133">看看 Contoso Corporation (虛構但具代表性的跨國企業) 如何為 Microsoft 365 雲端服務[最佳化其網路裝置和網際網路連線](contoso-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="39292-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="39292-135">下一步</span><span class="sxs-lookup"><span data-stu-id="39292-135">Next step</span></span>

<span data-ttu-id="39292-136">使用[Microsoft 365 網路連線能力一覽](microsoft-365-networking-overview.md)來開始您的網路規劃。</span><span class="sxs-lookup"><span data-stu-id="39292-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>