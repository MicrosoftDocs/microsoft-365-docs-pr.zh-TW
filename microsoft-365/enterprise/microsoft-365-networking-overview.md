---
title: Microsoft 365 網路連線概況
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: 討論為何網路優化對 SaaS 服務、Microsoft 365 網路的目標，以及 SaaS 需要不同的網路與其他工作負載的意義。
ms.openlocfilehash: 4fea7364dc79717583ebca8ce0dbe333ee818f1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688434"
---
# <a name="microsoft-365-network-connectivity-overview"></a><span data-ttu-id="0da44-103">Microsoft 365 網路連線能力一覽</span><span class="sxs-lookup"><span data-stu-id="0da44-103">Microsoft 365 network connectivity overview</span></span>

<span data-ttu-id="0da44-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="0da44-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0da44-105">Microsoft 365 是一種分散式軟體即服務 (SaaS) 雲端，可透過一組不同的微服務和應用程式來提供生產力與共同作業案例。</span><span class="sxs-lookup"><span data-stu-id="0da44-105">Microsoft 365 is a distributed Software-as-a-Service (SaaS) cloud that provides productivity and collaboration scenarios through a diverse set of micro-services and applications.</span></span> <span data-ttu-id="0da44-106">Microsoft 365 （如 Outlook、Word 及 PowerPoint）的用戶端元件會在使用者電腦上執行，並連接至 microsoft 資料中心執行的 Microsoft 365 的其他元件。</span><span class="sxs-lookup"><span data-stu-id="0da44-106">Client components of Microsoft 365 such as Outlook, Word and PowerPoint run on user computers and connect to other components of Microsoft 365 that run in Microsoft datacenters.</span></span> <span data-ttu-id="0da44-107">最重要的因素是判斷 Microsoft 365 使用者體驗的品質為網路可靠性和 Microsoft 365 用戶端與 Microsoft 365 服務前端之間的低延遲。</span><span class="sxs-lookup"><span data-stu-id="0da44-107">The most significant factor that determines the quality of the Microsoft 365 end user experience is network reliability and low latency between Microsoft 365 clients and Microsoft 365 service front doors.</span></span>

<span data-ttu-id="0da44-108">在本文中，您將瞭解 Microsoft 365 網路的目標，以及為何 Microsoft 365 網路需要不同于一般網際網路流量的優化方法。</span><span class="sxs-lookup"><span data-stu-id="0da44-108">In this article, you will learn about the goals of Microsoft 365 networking, and why Microsoft 365 networking requires a different approach to optimization than generic Internet traffic.</span></span>

## <a name="microsoft-365-networking-goals"></a><span data-ttu-id="0da44-109">Microsoft 365 網路目標</span><span class="sxs-lookup"><span data-stu-id="0da44-109">Microsoft 365 networking goals</span></span>

<span data-ttu-id="0da44-110">Microsoft 365 網路的最終目標是在用戶端和最接近的 Microsoft 365 端點之間啟用限制性最低的存取，以優化使用者的經驗。</span><span class="sxs-lookup"><span data-stu-id="0da44-110">The ultimate goal of Microsoft 365 networking is to optimize the end user experience by enabling the least restrictive access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="0da44-111">使用者經驗的品質與使用者所使用之應用程式的效能和回應能力直接相關。</span><span class="sxs-lookup"><span data-stu-id="0da44-111">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="0da44-112">例如，Microsoft 小組視低延遲而定，讓使用者電話通話、會議和共用畫面共同作業不會有任何中斷，而 Outlook 則依賴強大的網路連線功能，以進行即時搜尋功能，以利用伺服器端的索引及 AI 功能。</span><span class="sxs-lookup"><span data-stu-id="0da44-112">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free, and Outlook relies on great networking connectivity for instant search features that leverage server-side indexing and AI capabilities.</span></span>

<span data-ttu-id="0da44-113">網路設計中的主要目標是將用戶端電腦上的往返時間 (RTT) 減至 Microsoft 全球網路，以減少延遲時間，這是 Microsoft 的公用網路主幹，可將所有的 Microsoft 資料中心互連，以低延遲的方式，高可用性的雲端應用程式進入點遍佈世界各地。</span><span class="sxs-lookup"><span data-stu-id="0da44-113">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client machines to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points spread around the world.</span></span> <span data-ttu-id="0da44-114">您可以在 [Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) 中，深入了解 Microsoft 全域網路。</span><span class="sxs-lookup"><span data-stu-id="0da44-114">You can learn more about the Microsoft Global Network at [How Microsoft builds its fast and reliable global network](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span></span>

<span data-ttu-id="0da44-115">優化 Microsoft 365 網路效能不需要很複雜。</span><span class="sxs-lookup"><span data-stu-id="0da44-115">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="0da44-116">您可以遵循一些重要的原則，盡可能取得最佳效能：</span><span class="sxs-lookup"><span data-stu-id="0da44-116">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="0da44-117">識別 Microsoft 365 網路流量</span><span class="sxs-lookup"><span data-stu-id="0da44-117">Identify Microsoft 365 network traffic</span></span>
- <span data-ttu-id="0da44-118">允許從每個使用者連接至 Microsoft 365 的位置，將 Microsoft 365 網路流量的本機分支出口至網際網路</span><span class="sxs-lookup"><span data-stu-id="0da44-118">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365</span></span>
- <span data-ttu-id="0da44-119">允許 Microsoft 365 流量略過 proxy 和封包檢查裝置</span><span class="sxs-lookup"><span data-stu-id="0da44-119">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices</span></span>

<span data-ttu-id="0da44-120">如需 Microsoft 365 網路連線原則的詳細資訊，請參閱 [microsoft 365 Network Connectivity 原則](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="0da44-120">For more information on Microsoft 365 network connectivity principles, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="traditional-network-architectures-and-saas"></a><span data-ttu-id="0da44-121">傳統的網路架構和 SaaS</span><span class="sxs-lookup"><span data-stu-id="0da44-121">Traditional network architectures and SaaS</span></span>

<span data-ttu-id="0da44-122">傳統的用戶端/伺服器工作負載的網路結構原則，是針對用戶端和端點之間的流量所設計，不會延伸到公司網路周邊外。</span><span class="sxs-lookup"><span data-stu-id="0da44-122">Traditional network architecture principles for client/server workloads are designed around the assumption that traffic between clients and endpoints does not extend outside the corporate network perimeter.</span></span> <span data-ttu-id="0da44-123">此外，在許多商業網路中，所有的輸出網際網路連線都透過公司網路，以及從中心位置出口。</span><span class="sxs-lookup"><span data-stu-id="0da44-123">Also, in many enterprise networks, all outbound Internet connections traverse the corporate network, and egress from a central location.</span></span>

<span data-ttu-id="0da44-124">在傳統的網路架構中，一般網際網路流量的較高延遲是為了維護網路周邊安全性所需的權衡性，而 Internet 流量的效能優化通常是在網路出局點升級或擴充設備。</span><span class="sxs-lookup"><span data-stu-id="0da44-124">In traditional network architectures, higher latency for generic Internet traffic is a necessary tradeoff in order to maintain network perimeter security, and performance optimization for Internet traffic typically involves upgrading or scaling out the equipment at network egress points.</span></span> <span data-ttu-id="0da44-125">不過，此方法不會解決 SaaS 服務（例如 Microsoft 365）的最佳網路效能需求。</span><span class="sxs-lookup"><span data-stu-id="0da44-125">However, this approach does not address the requirements for optimum network performance of SaaS services such as Microsoft 365.</span></span>

## <a name="identifying-microsoft-365-network-traffic"></a><span data-ttu-id="0da44-126">識別 Microsoft 365 網路流量</span><span class="sxs-lookup"><span data-stu-id="0da44-126">Identifying Microsoft 365 network traffic</span></span>

<span data-ttu-id="0da44-127">我們可讓您更容易識別 Microsoft 365 網路流量，並簡化網路識別碼的管理。</span><span class="sxs-lookup"><span data-stu-id="0da44-127">We're making it easier to identify Microsoft 365 network traffic and making it simpler to manage the network identification.</span></span>

- <span data-ttu-id="0da44-128">新的網路端點類別，讓高緊急的網路流量有別于不受網際網路延遲影響的網路流量。</span><span class="sxs-lookup"><span data-stu-id="0da44-128">New categories of network endpoints to differentiate highly critical network traffic from network traffic which is not impacted by Internet latencies.</span></span> <span data-ttu-id="0da44-129">在最重要的 "Optimize" 類別中，只會有少數 URLs 和支援 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0da44-129">There are just a handful of URLs and supporting IP Addresses in the most critical “Optimize” category.</span></span>
- <span data-ttu-id="0da44-130">Web 服務的腳本使用方式或直接裝置設定，以及 Microsoft 365 網路身分識別的變更管理。</span><span class="sxs-lookup"><span data-stu-id="0da44-130">Web services for script usage or direct device configuration and change management of Microsoft 365 network identification.</span></span> <span data-ttu-id="0da44-131">您可以從 web 服務或 RSS 格式，或是使用 Microsoft 流程範本的電子郵件，取得變更。</span><span class="sxs-lookup"><span data-stu-id="0da44-131">Changes are available from the web service, or in RSS format, or on email using a Microsoft Flow template.</span></span>
- <span data-ttu-id="0da44-132">[Office 365 網路合作夥伴計畫](https://aka.ms/Office365NPP) ，可提供遵循 microsoft 365 網路連線性原則的裝置或服務，並具有簡易的設定。</span><span class="sxs-lookup"><span data-stu-id="0da44-132">[Office 365 Network partner program](https://aka.ms/Office365NPP) with Microsoft partners who provide devices or services that follow Microsoft 365 network connectivity principles and have simple configuration.</span></span>

## <a name="securing-microsoft-365-connections"></a><span data-ttu-id="0da44-133">保護 Microsoft 365 連線</span><span class="sxs-lookup"><span data-stu-id="0da44-133">Securing Microsoft 365 connections</span></span>

<span data-ttu-id="0da44-134">傳統網路安全性的目標是強化公司網路周邊網路，免於入侵和惡意攻擊。</span><span class="sxs-lookup"><span data-stu-id="0da44-134">The goal of traditional network security is to harden the corporate network perimeter against intrusion and malicious exploits.</span></span> <span data-ttu-id="0da44-135">大部分的商業網路會利用類似 proxy 伺服器、防火牆、SSL 中斷及檢查、深度封包檢查和資料遺失防護系統等技術，強制進行網際網路流量的網路安全性。</span><span class="sxs-lookup"><span data-stu-id="0da44-135">Most enterprise networks enforce network security for Internet traffic using technologies like proxy servers, firewalls, SSL break and inspect, deep packet inspection, and data loss prevention systems.</span></span> <span data-ttu-id="0da44-136">這些技術為一般網際網路要求提供重要的風險降低，但是當套用至 Microsoft 365 端點時，可能會大幅降低效能、延展性和使用者體驗的品質。</span><span class="sxs-lookup"><span data-stu-id="0da44-136">These technologies provide important risk mitigation for generic Internet requests but can dramatically reduce performance, scalability, and the quality of end user experience when applied to Microsoft 365 endpoints.</span></span>

<span data-ttu-id="0da44-137">Microsoft 365 可協助滿足您組織的內容安全性和資料使用方式相容性的需求，其採用專為 Microsoft 365 功能和工作負載而設計的內建安全性和控管功能。</span><span class="sxs-lookup"><span data-stu-id="0da44-137">Microsoft 365 helps meet your organization's needs for content security and data usage compliance with built-in security and governance features designed specifically for Microsoft 365 features and workloads.</span></span> <span data-ttu-id="0da44-138">如需 Microsoft 365 安全性和合規性的詳細資訊，請參閱 [Office 365 安全性藍圖](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="0da44-138">For more information about Microsoft 365 security and compliance, see the [Office 365 security roadmap](https://docs.microsoft.com/office365/securitycompliance/security-roadmap).</span></span> <span data-ttu-id="0da44-139">如需 Microsoft 的建議和支援位置的詳細資訊，請參閱在 Microsoft 365 流量上執行高級的處理的高級網路解決方案，請參閱 [使用協力廠商網路裝置或 Office 365 流量的解決方案](https://support.microsoft.com/help/2690045)。</span><span class="sxs-lookup"><span data-stu-id="0da44-139">For more information about Microsoft’s recommendations and support position on advanced network solutions that perform advanced-level processing on Microsoft 365 traffic, see [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045).</span></span>

## <a name="why-is-microsoft-365-networking-different"></a><span data-ttu-id="0da44-140">為什麼 Microsoft 365 網路是不同的？</span><span class="sxs-lookup"><span data-stu-id="0da44-140">Why is Microsoft 365 networking different?</span></span>

<span data-ttu-id="0da44-141">Microsoft 365 的設計是要使用端點安全性和加密網路連線以取得最佳效能，以減少周邊安全性強制執行的需要。</span><span class="sxs-lookup"><span data-stu-id="0da44-141">Microsoft 365 is designed for optimal performance using endpoint security and encrypted network connections, reducing the need for perimeter security enforcement.</span></span> <span data-ttu-id="0da44-142">Microsoft 365 資料中心位於世界各地，而且其設計目的是使用各種方法將用戶端連線至最佳可用服務端點。</span><span class="sxs-lookup"><span data-stu-id="0da44-142">Microsoft 365 datacenters are located across the world and the service is designed to use various methods for connecting clients to best available service endpoints.</span></span> <span data-ttu-id="0da44-143">因為使用者資料與處理是在許多 Microsoft 資料中心之間散佈，所以用戶端電腦不能連接任何單一網路端點。</span><span class="sxs-lookup"><span data-stu-id="0da44-143">Since user data and processing is distributed between many Microsoft datacenters, there is no single network endpoint to which client machines can connect.</span></span> <span data-ttu-id="0da44-144">實際上，microsoft 全球網路的資料和365服務會透過 Microsoft 全球網路進行動態優化，以適應使用者存取使用者的地理位置。</span><span class="sxs-lookup"><span data-stu-id="0da44-144">In fact, data and services in your Microsoft 365 tenant are dynamically optimized by the Microsoft Global Network to adapt to the geographic locations from which they are accessed by end users.</span></span>

<span data-ttu-id="0da44-145">當 Microsoft 365 流量受到封包檢查及集中送出的出入時，就會建立某些常見效能問題：</span><span class="sxs-lookup"><span data-stu-id="0da44-145">Certain common performance issues are created when Microsoft 365 traffic is subject to packet inspection and centralized egress:</span></span>

- <span data-ttu-id="0da44-146">高延遲可能會造成影片和音訊資料流程效能極低，以及資料檢索、搜尋、即時共同作業、行事曆空閒/忙碌資訊、產品內容及其他服務的回應速度很慢</span><span class="sxs-lookup"><span data-stu-id="0da44-146">High latency can cause extremely poor performance of video and audio streams, and slow response of data retrieval, searches, real-time collaboration, calendar free/busy information, in-product content and other services</span></span>
- <span data-ttu-id="0da44-147">從中心位置 Egressing 連線會破壞 Microsoft 365 全域網路的動態路由功能，增加延遲時間和往返時間</span><span class="sxs-lookup"><span data-stu-id="0da44-147">Egressing connections from a central location defeats the dynamic routing capabilities of the Microsoft 365 global network, adding latency and round-trip time</span></span>
- <span data-ttu-id="0da44-148">解密 SSL 安全的 Microsoft 365 網路流量並重新加密可能會造成通訊協定錯誤，並有安全性風險</span><span class="sxs-lookup"><span data-stu-id="0da44-148">Decrypting SSL secured Microsoft 365 network traffic and re-encrypting it can cause protocol errors and has security risk</span></span>

<span data-ttu-id="0da44-149">透過讓用戶端流量盡可能接近其地理位置，縮短 Microsoft 365 進入點的網路路徑，可提高連線效能及 Microsoft 365 中的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0da44-149">Shortening the network path to Microsoft 365 entry points by allowing client traffic to egress as close as possible to their geographic location can improve connectivity performance and the end user experience in Microsoft 365.</span></span> <span data-ttu-id="0da44-150">它也有助於減少對 Microsoft 365 效能和可靠性之網路架構的未來變更影響。</span><span class="sxs-lookup"><span data-stu-id="0da44-150">It can also help to reduce the impact of future changes to the network architecture on Microsoft 365 performance and reliability.</span></span> <span data-ttu-id="0da44-151">最佳連線模型是永遠在使用者的位置提供網路出局，不論這是在公司網路或是家用、旅館、咖啡店和機場等遠端位置。</span><span class="sxs-lookup"><span data-stu-id="0da44-151">The optimum connectivity model is to always provide network egress at the user's location, regardless of whether this is on the corporate network or remote locations such as home, hotels, coffee shops and airports.</span></span> <span data-ttu-id="0da44-152">一般網際網路流量和以 WAN 為基礎的公司網路流量將會分開傳送，不會使用本機直接出局模型。</span><span class="sxs-lookup"><span data-stu-id="0da44-152">Generic Internet traffic and WAN based corporate network traffic would be separately routed and not use the local direct egress model.</span></span> <span data-ttu-id="0da44-153">下圖呈現這個本機直接出口模型。</span><span class="sxs-lookup"><span data-stu-id="0da44-153">This local direct egress model is represented in the diagram below.</span></span>

![本機出口網路架構](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

<span data-ttu-id="0da44-155">本機出局架構針對傳統模型上的 Microsoft 365 網路流量，具有下列優點：</span><span class="sxs-lookup"><span data-stu-id="0da44-155">The local egress architecture has the following benefits for Microsoft 365 network traffic over the traditional model:</span></span>
  
- <span data-ttu-id="0da44-156">藉由最佳化路由長度，提供最佳的 Microsoft 365 效能。</span><span class="sxs-lookup"><span data-stu-id="0da44-156">Provides optimal Microsoft 365 performance by optimizing route length.</span></span> <span data-ttu-id="0da44-157">使用者連線會以 Microsoft 全球網路的 _分散式服務前端_ 基礎結構，動態路由傳送至最接近的 Microsoft 365 進入點，而流量會透過 microsoft 的超低延遲高可用性纖程內部路由傳送至資料和服務端點。</span><span class="sxs-lookup"><span data-stu-id="0da44-157">End user connections are dynamically routed to the nearest Microsoft 365 entry point by the Microsoft Global Network's _Distributed Service Front Door_ infrastructure, and traffic is then routed internally to data and service endpoints over Microsoft's ultra-low latency high availability fiber.</span></span>
- <span data-ttu-id="0da44-158">透過允許 Microsoft 365 流量的本機出口，以略過代理和流量檢查裝置，減少公司網路基礎結構的負載。</span><span class="sxs-lookup"><span data-stu-id="0da44-158">Reduces the load on corporate network infrastructure by allowing local egress for Microsoft 365 traffic, bypassing proxies and traffic inspection devices.</span></span>
- <span data-ttu-id="0da44-159">利用用戶端端點安全性和雲端安全性功能，以避免應用冗余網路安全性技術，來保護兩端的連線。</span><span class="sxs-lookup"><span data-stu-id="0da44-159">Secures connections on both ends by leveraging client endpoint security and cloud security features, avoiding application of redundant network security technologies.</span></span>

> [!NOTE]
> <span data-ttu-id="0da44-160">_分散式服務前端_基礎結構是 Microsoft 全球網路的高可用性和可伸縮網路 edge，具有地理位置分散的位置。</span><span class="sxs-lookup"><span data-stu-id="0da44-160">The _Distributed Service Front Door_ infrastructure is the Microsoft Global Network's highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="0da44-161">它會終止使用者連線，並有效地將其路由傳送至 Microsoft 全球網路中。</span><span class="sxs-lookup"><span data-stu-id="0da44-161">It terminates end user connections and efficiently routes them within the Microsoft Global Network.</span></span> <span data-ttu-id="0da44-162">您可以在 [Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) 中，深入了解 Microsoft 全域網路。</span><span class="sxs-lookup"><span data-stu-id="0da44-162">You can learn more about the Microsoft Global Network at [How Microsoft builds its fast and reliable global network](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span></span>

<span data-ttu-id="0da44-163">如需瞭解及套用 Microsoft 365 network connectivity 原則的詳細資訊，請參閱 [microsoft 365 網路連線原則](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="0da44-163">For more information on understanding and applying Microsoft 365 network connectivity principles, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="conclusion"></a><span data-ttu-id="0da44-164">總結</span><span class="sxs-lookup"><span data-stu-id="0da44-164">Conclusion</span></span>

<span data-ttu-id="0da44-165">優化 Microsoft 365 網路效能實際上是為了移除不必要的障礙。</span><span class="sxs-lookup"><span data-stu-id="0da44-165">Optimizing Microsoft 365 network performance really comes down to removing unnecessary impediments.</span></span> <span data-ttu-id="0da44-166">將 Microsoft 365 連線視為信任的流量，可防止資料包檢查和對 proxy 頻寬的競爭帶來延遲。</span><span class="sxs-lookup"><span data-stu-id="0da44-166">By treating Microsoft 365 connections as trusted traffic, you can prevent latency from being introduced by packet inspection and competition for proxy bandwidth.</span></span> <span data-ttu-id="0da44-167">允許用戶端機器與 Office 365 端點之間的本機連線，可讓流量透過 Microsoft 全球網路動態路由傳送。</span><span class="sxs-lookup"><span data-stu-id="0da44-167">Allowing local connections between client machines and Office 365 endpoints enables traffic to be dynamically routed through the Microsoft Global Network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0da44-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="0da44-168">Related Topics</span></span>

[<span data-ttu-id="0da44-169">Microsoft 365 網路連線原則</span><span class="sxs-lookup"><span data-stu-id="0da44-169">Microsoft 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="0da44-170">管理 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="0da44-170">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="0da44-171">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="0da44-171">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="0da44-172">Office 365 IP 位址和 URL Web 服務</span><span class="sxs-lookup"><span data-stu-id="0da44-172">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="0da44-173">評估 Microsoft 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="0da44-173">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="0da44-174">Microsoft 365 的網路規劃和效能調整</span><span class="sxs-lookup"><span data-stu-id="0da44-174">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="0da44-175">使用基準與效能歷程記錄進行 Office 365 效能調整</span><span class="sxs-lookup"><span data-stu-id="0da44-175">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="0da44-176">Office 365 的效能疑難排解規劃</span><span class="sxs-lookup"><span data-stu-id="0da44-176">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="0da44-177">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="0da44-177">Content Delivery Networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="0da44-178">Microsoft 365 連線測試</span><span class="sxs-lookup"><span data-stu-id="0da44-178">Microsoft 365 connectivity test</span></span>](https://aka.ms/netonboard)

[<span data-ttu-id="0da44-179">Microsoft 如何建置其快速且可靠的全域網路</span><span class="sxs-lookup"><span data-stu-id="0da44-179">How Microsoft builds its fast and reliable global network</span></span>](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[<span data-ttu-id="0da44-180">Office 365 網路部落格</span><span class="sxs-lookup"><span data-stu-id="0da44-180">Office 365 Networking blog</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
