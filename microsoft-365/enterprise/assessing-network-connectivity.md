---
title: 評估 Microsoft 365 網路連線能力
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
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
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 的設計是要讓全球各地的客戶能夠使用網際網路連線來連線至服務。 隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而有所改善。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905473"
---
# <a name="assessing-microsoft-365-network-connectivity"></a><span data-ttu-id="ff9f9-104">評估 Microsoft 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="ff9f9-104">Assessing Microsoft 365 network connectivity</span></span>

<span data-ttu-id="ff9f9-105">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="ff9f9-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ff9f9-106">Microsoft 365 的設計是要讓全球各地的客戶能夠使用網際網路連線來連線至服務。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-106">Microsoft 365 is designed to enable customers all over the world to connect to the service using an internet connection.</span></span> <span data-ttu-id="ff9f9-107">隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而有所改善。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-107">As the service evolves, the security, performance, and reliability of Microsoft 365 are improved based on customers using the internet to establish a connection to the service.</span></span>
  
<span data-ttu-id="ff9f9-108">規劃使用 Microsoft 365 的客戶應評估其現有和預測的網際網路連線需求，做為部署專案的一部分。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-108">Customers planning to use Microsoft 365 should assess their existing and forecasted internet connectivity needs as a part of the deployment project.</span></span> <span data-ttu-id="ff9f9-109">針對企業級部署，可靠且適當地調整 internet 連線能力是使用 Microsoft 365 功能和案例的重要部分。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-109">For enterprise class deployments reliable and appropriately sized internet connectivity is a critical part of consuming Microsoft 365 features and scenarios.</span></span>
  
<span data-ttu-id="ff9f9-110">根據您的大小和喜好設定，許多不同的人員和組織可以執行網路評估。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-110">Network evaluations can be performed by many different people and organizations depending on your size and preferences.</span></span> <span data-ttu-id="ff9f9-111">評估的網路範圍也會因您在部署程式中所處的位置而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-111">The network scope of the assessment can also vary depending on where you're at in your deployment process.</span></span> <span data-ttu-id="ff9f9-112">為了協助您更深入瞭解執行網路評估的方式，我們產生了網路評估指南，協助您瞭解可用的選項。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-112">To help you get a better understanding of what it takes to perform a network assessment, we've produced a network assessment guide to help you understand the options available to you.</span></span> <span data-ttu-id="ff9f9-113">這種評估會決定需要新增至部署專案的步驟和資源，讓您能夠順利採用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-113">This assessment will determine what steps and resources need to be added to the deployment project to enable you to successfully adopt Microsoft 365.</span></span>
  
<span data-ttu-id="ff9f9-114">綜合網路評估會為網路設計挑戰提供可能的解決方案，以及執行詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-114">A comprehensive network assessment will provide possible solutions to networking design challenges along with implementation details.</span></span> <span data-ttu-id="ff9f9-115">有些網路評估會顯示出最佳的網路連線 Microsoft 365 能力，可搭配次要設定或對現有網路和網際網路出口基礎結構進行的設計變更。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-115">Some network assessments will show that optimal network connectivity to Microsoft 365 can be accommodated with minor configuration or design changes to the existing network and internet egress infrastructure.</span></span>

<span data-ttu-id="ff9f9-116">有些評估會指出 Microsoft 365 的網路連線需要網路元件的額外投資。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-116">Some assessments will indicate network connectivity to Microsoft 365 will require additional investments in networking components.</span></span> <span data-ttu-id="ff9f9-117">例如，跨分支辦公室和多個地理區域的商業網路可能需要投資 SD-WAN 解決方案或優化的路由基礎結構，以支援 Microsoft 365 的網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-117">For example, enterprise networks that span branch offices and multiple geographic regions may require investments in SD-WAN solutions or optimized routing infrastructure to support internet connectivity to Microsoft 365.</span></span> <span data-ttu-id="ff9f9-118">有時候，評估會指出對 Microsoft 365 的網路連線會受到諸如[商務用 Skype 線上媒體質量](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)等案例的法規或效能需求影響。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-118">Occasionally an assessment will indicate network connectivity to Microsoft 365 is influenced by regulation or performance requirements for scenarios such as [Skype for Business Online media quality](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).</span></span> <span data-ttu-id="ff9f9-119">這些額外需求可能會造成網際網路連線基礎結構、路由優化和特殊直接連線的投資。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-119">These additional requirements may lead to investments in internet connectivity infrastructure, routing optimization, and specialized direct connectivity.</span></span>

<span data-ttu-id="ff9f9-120">協助您評估網路的一些資源：</span><span class="sxs-lookup"><span data-stu-id="ff9f9-120">Some resources to help you assess your network:</span></span>

- <span data-ttu-id="ff9f9-121">如需有關 Microsoft 365 網路的概念資訊，請參閱[Microsoft 365 網路連線概述](microsoft-365-networking-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-121">See [Microsoft 365 network connectivity overview](microsoft-365-networking-overview.md) for conceptual information about Microsoft 365 networking.</span></span>
- <span data-ttu-id="ff9f9-122">請參閱[Microsoft 365 網路連線原則](./microsoft-365-network-connectivity-principles.md)，以瞭解可安全地管理 Microsoft 365 流量，以及取得最佳效能的連線原則。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-122">See [Microsoft 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Microsoft 365 traffic and getting the best possible performance.</span></span>
- <span data-ttu-id="ff9f9-123">在規劃、設計及部署 Microsoft 365，註冊[Microsoft FastTrack](https://www.microsoft.com/fasttrack)以取得引導協助。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-123">Sign up for [Microsoft FastTrack](https://www.microsoft.com/fasttrack) for guided assistance with Microsoft 365 planning, design and deployment.</span></span> 
- <span data-ttu-id="ff9f9-124">請參閱下列的[Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test)一節，以執行基本的連線測試，以提供有關在指定使用者位置和 Microsoft 365 之間進行的網路連線增強功能的特定指導性。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-124">See the [Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) section below to run basic connectivity tests that provide specific guidance about networking connectivity improvements that can be made between a given user location and Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="ff9f9-125">若要使用 Office 365 ExpressRoute，必須使用 Microsoft 授權。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-125">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="ff9f9-126">Microsoft 會檢查每個客戶要求，並且只會授權 ExpressRoute，以供客戶的法規需求直接連線時 Office 365 使用方式。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-126">Microsoft reviews every customer request and only authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="ff9f9-127">如果您有這樣的需求，請提供文位元組選和 web 連結至您所述的規章，表示[ExpressRoute Office 365 要求表單](https://aka.ms/O365ERReview)開始 Microsoft 複查時，必須直接連線。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-127">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="ff9f9-128">嘗試為 Office 365 建立路由篩選的未授權訂閱將會收到[錯誤訊息](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-128">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>
  
<span data-ttu-id="ff9f9-129">規劃 Microsoft 365 的網路評估時，應考慮的要點：</span><span class="sxs-lookup"><span data-stu-id="ff9f9-129">Key points to consider when planning your network assessment for Microsoft 365:</span></span>
  
- <span data-ttu-id="ff9f9-130">Microsoft 365 是透過公用網際網路執行的安全、可靠、高效能服務。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-130">Microsoft 365 is a secure, reliable, high performance service that runs over the public internet.</span></span> <span data-ttu-id="ff9f9-131">我們會繼續投資以加強服務的這些方面。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-131">We continue to invest to enhance these aspects of the service.</span></span> <span data-ttu-id="ff9f9-132">所有 Microsoft 365 服務均可透過網際網路連線來取得。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-132">All Microsoft 365 services are available via internet connectivity.</span></span>

- <span data-ttu-id="ff9f9-133">我們正在不斷優化 Microsoft 365 的核心層面，例如可用性、全域接觸能力，以及網際網路連線的效能。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-133">We are continually optimizing core aspects of Microsoft 365 such as availability, global reach, and performance for internet based connectivity.</span></span> <span data-ttu-id="ff9f9-134">例如，許多 Microsoft 365 服務都會利用一組擴充的網際網路對向邊緣節點。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-134">For example, many Microsoft 365 services leverage an expanding set of internet facing edge nodes.</span></span> <span data-ttu-id="ff9f9-135">此 edge 網路可為透過網際網路的連線提供最佳的鄰近性和效能。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-135">This edge network offers the best proximity and performance to connections coming over the internet.</span></span>

- <span data-ttu-id="ff9f9-136">當您考慮使用 Microsoft 365 進行任何包含的服務，例如 Teams 或商務用 Skype 線上語音、影片或會議功能時，客戶應完成端對端網路評估，並使用[Microsoft FastTrack](https://www.microsoft.com/fasttrack)滿足連線性需求。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-136">When considering using Microsoft 365 for any of the included services such as Teams or Skype for Business Online voice, video, or meeting capabilities, customers should complete an end to end network assessment and meet connectivity requirements using [Microsoft FastTrack](https://www.microsoft.com/fasttrack).</span></span>

<span data-ttu-id="ff9f9-137">如果您正在評估 Microsoft 365，但不確定要從網路評估開始，或發現需要協助您克服的網路設計挑戰，請與您的 Microsoft 帳戶小組合作。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-137">If you're evaluating Microsoft 365 and aren't sure where to begin with your network assessment or have found network design challenges that you need assistance to overcome, please work with your Microsoft account team.</span></span>

## <a name="the-microsoft-365-connectivity-test"></a><span data-ttu-id="ff9f9-138">Microsoft 365 connectivity test</span><span class="sxs-lookup"><span data-stu-id="ff9f9-138">The Microsoft 365 connectivity test</span></span>

<span data-ttu-id="ff9f9-139">[Microsoft 365 連線測試](https://aka.ms/netonboard)是針對 Microsoft 365 租使用者執行基本連線測試 (POC) 網路評估工具的概念證明，並針對最佳 Microsoft 365 效能進行特定的網路設計建議。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-139">The [Microsoft 365 connectivity test](https://aka.ms/netonboard) is a proof of concept (POC) network assessment tool that runs basic connectivity tests against your Microsoft 365 tenant and makes specific network design recommendations for optimal Microsoft 365 performance.</span></span> <span data-ttu-id="ff9f9-140">此工具強調常見的大型商業網路周邊設計選擇，這些選項對網際網路網頁流覽很有用，但會影響大型 SaaS 應用程式（如 Microsoft 365）的效能。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-140">The tool highlights common large enterprise network perimeter design choices which are useful for Internet web browsing but impact the performance of large SaaS applications such as Microsoft 365.</span></span>

<span data-ttu-id="ff9f9-141">網路上架工具會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="ff9f9-141">The Network Onboarding tool does the following:</span></span>

- <span data-ttu-id="ff9f9-142">偵測您的位置，您也可以指定要測試的位置。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-142">Detects your location, or you can specify a location to test</span></span>
- <span data-ttu-id="ff9f9-143">檢查網路出局的位置</span><span class="sxs-lookup"><span data-stu-id="ff9f9-143">Checks the location of your network egress</span></span>
- <span data-ttu-id="ff9f9-144">測試最近 Microsoft 365 服務前門的網路路徑</span><span class="sxs-lookup"><span data-stu-id="ff9f9-144">Tests the network path to the nearest Microsoft 365 service front door</span></span>
- <span data-ttu-id="ff9f9-145">提供使用可下載的 Windows 10 應用程式進行的高級測試，使周邊網路設計建議與 proxy 伺服器、防火牆和 DNS 有關。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-145">Provides advanced tests using a downloadable Windows 10 application that makes perimeter network design recommendations related to proxy servers, firewalls, and DNS.</span></span> <span data-ttu-id="ff9f9-146">工具也會執行商務用 Skype 線上、Microsoft Teams SharePoint 線上及 Exchange Online 的效能測試。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-146">The tool also runs performance tests for Skype for Business Online, Microsoft Teams, SharePoint Online and Exchange Online.</span></span>

<span data-ttu-id="ff9f9-147">工具有兩個元件：一種瀏覽器架構使用者介面，可收集基本連線資訊，以及執行高級測試並傳回其他評估資料的可下載 Windows 10 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-147">The tool has two components: a browser-based UI that collects basic connectivity information, and a downloadable Windows 10 application that runs advanced tests and returns additional assessment data.</span></span>

<span data-ttu-id="ff9f9-148">瀏覽器型工具會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ff9f9-148">The browser-based tool displays the following information:</span></span>

- <span data-ttu-id="ff9f9-149">[結果與影響] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ff9f9-149">Results and impact tab</span></span>
  - <span data-ttu-id="ff9f9-150">在使用中的服務前蓋地圖上的位置</span><span class="sxs-lookup"><span data-stu-id="ff9f9-150">The location on a map of the in-use service front door</span></span>
  - <span data-ttu-id="ff9f9-151">其他服務前門的地圖上的位置，可提供最佳連線能力</span><span class="sxs-lookup"><span data-stu-id="ff9f9-151">The location on a map of other service front doors that would provide optimal connectivity</span></span>
  - <span data-ttu-id="ff9f9-152">與接近您的其他 Microsoft 365 客戶的相對效能</span><span class="sxs-lookup"><span data-stu-id="ff9f9-152">Relative performance compared to other Microsoft 365 customers near you</span></span>
- <span data-ttu-id="ff9f9-153">詳細資料與解決方案] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ff9f9-153">Details and solutions tab</span></span>
  - <span data-ttu-id="ff9f9-154">依城市和國家/地區的使用者位置</span><span class="sxs-lookup"><span data-stu-id="ff9f9-154">User location by city and country</span></span>
  - <span data-ttu-id="ff9f9-155">透過城市、州和國家的網路出局位置</span><span class="sxs-lookup"><span data-stu-id="ff9f9-155">Network egress location by city, state and country</span></span>
  - <span data-ttu-id="ff9f9-156">使用者進入網路出局距離</span><span class="sxs-lookup"><span data-stu-id="ff9f9-156">User to network egress distance</span></span>
  - <span data-ttu-id="ff9f9-157">Microsoft 365 Exchange Online 服務前門位置</span><span class="sxs-lookup"><span data-stu-id="ff9f9-157">Microsoft 365 Exchange Online service front door location</span></span>
  - <span data-ttu-id="ff9f9-158">Microsoft 365 使用者位置) Exchange Online 服務前端 (s 的最佳</span><span class="sxs-lookup"><span data-stu-id="ff9f9-158">Optimal Microsoft 365 Exchange Online service front door(s) for user location</span></span>
  - <span data-ttu-id="ff9f9-159">以較佳效能顯示大都市區域中的客戶</span><span class="sxs-lookup"><span data-stu-id="ff9f9-159">Customers in your metro area with better performance</span></span>

<span data-ttu-id="ff9f9-160">「高級測試下載」應用程式提供下列其他資訊：</span><span class="sxs-lookup"><span data-stu-id="ff9f9-160">The Advanced Tests downloadable application provides the following additional information:</span></span>

- <span data-ttu-id="ff9f9-161"> (新增) 的詳細資料和方案] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ff9f9-161">Details and solutions tab (appended)</span></span>
  - <span data-ttu-id="ff9f9-162">使用者的預設閘道</span><span class="sxs-lookup"><span data-stu-id="ff9f9-162">User's default gateway</span></span>
  - <span data-ttu-id="ff9f9-163">用戶端 DNS 伺服器</span><span class="sxs-lookup"><span data-stu-id="ff9f9-163">Client DNS Server</span></span>
  - <span data-ttu-id="ff9f9-164">用戶端 DNS 遞迴解析程式</span><span class="sxs-lookup"><span data-stu-id="ff9f9-164">Client DNS Recursive Resolver</span></span>
  - <span data-ttu-id="ff9f9-165">Exchange OnlineDNS 伺服器</span><span class="sxs-lookup"><span data-stu-id="ff9f9-165">Exchange Online DNS server</span></span>
  - <span data-ttu-id="ff9f9-166">SharePoint線上 DNS 伺服器</span><span class="sxs-lookup"><span data-stu-id="ff9f9-166">SharePoint Online DNS server</span></span>
  - <span data-ttu-id="ff9f9-167">Proxy 伺服器識別</span><span class="sxs-lookup"><span data-stu-id="ff9f9-167">Proxy server identification</span></span>
  - <span data-ttu-id="ff9f9-168">Media connectivity 檢查</span><span class="sxs-lookup"><span data-stu-id="ff9f9-168">Media connectivity check</span></span>
  - <span data-ttu-id="ff9f9-169">媒體質量封包遺失</span><span class="sxs-lookup"><span data-stu-id="ff9f9-169">Media quality packet loss</span></span>
  - <span data-ttu-id="ff9f9-170">媒體質量延遲</span><span class="sxs-lookup"><span data-stu-id="ff9f9-170">Media quality latency</span></span>
  - <span data-ttu-id="ff9f9-171">媒體質量抖動</span><span class="sxs-lookup"><span data-stu-id="ff9f9-171">Media quality jitter</span></span>
  - <span data-ttu-id="ff9f9-172">媒體質量資料包重新排序</span><span class="sxs-lookup"><span data-stu-id="ff9f9-172">Media quality packet reorder</span></span>
- <span data-ttu-id="ff9f9-173">對多項特定功能端點的連線性測試</span><span class="sxs-lookup"><span data-stu-id="ff9f9-173">Connectivity tests to multiple feature-specific endpoints</span></span>
- <span data-ttu-id="ff9f9-174">網路路徑診斷，包含 Exchange Online 的 tracert 和延遲資料，SharePoint 線上和 Teams 服務</span><span class="sxs-lookup"><span data-stu-id="ff9f9-174">Network path diagnostics that include tracert and latency data for the Exchange Online, SharePoint Online and Teams services</span></span>

<span data-ttu-id="ff9f9-175">您可以閱讀 Microsoft 365 更新的 Microsoft 365 連線測試，並提供[新的網路設計建議，並提供新的網路設計建議，以進行](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130)博客文章。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-175">You can read about the Microsoft 365 connectivity test and provide feedback at the [Updated Microsoft 365 connectivity test POC with new network design recommendations](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) blog post.</span></span> <span data-ttu-id="ff9f9-176">此工具及其他 Microsoft 365 網路更新的未來更新資訊將會發佈到[Office 365 網路](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)博客。</span><span class="sxs-lookup"><span data-stu-id="ff9f9-176">Information about future updates to this tool and other Microsoft 365 networking updates will be posted to the [Office 365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) blog.</span></span>
  
<span data-ttu-id="ff9f9-177">您可以使用以下簡短連結回來： [ https://aka.ms/o365networkconnectivity 。](./microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="ff9f9-177">Here's a short link you can use to come back: [https://aka.ms/o365networkconnectivity.](./microsoft-365-network-connectivity-principles.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ff9f9-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="ff9f9-178">Related topics</span></span>

[<span data-ttu-id="ff9f9-179">Microsoft 365 網路連線概況</span><span class="sxs-lookup"><span data-stu-id="ff9f9-179">Microsoft 365 Network Connectivity Overview</span></span>](microsoft-365-networking-overview.md)

[<span data-ttu-id="ff9f9-180">Microsoft 365 網路連線能力準則</span><span class="sxs-lookup"><span data-stu-id="ff9f9-180">Microsoft 365 Network Connectivity Principles</span></span>](./microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="ff9f9-181">管理 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="ff9f9-181">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="ff9f9-182">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="ff9f9-182">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="ff9f9-183">Office 365 IP 位址和 URL Web 服務</span><span class="sxs-lookup"><span data-stu-id="ff9f9-183">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="ff9f9-184">Microsoft 365 網路和效能調整</span><span class="sxs-lookup"><span data-stu-id="ff9f9-184">Microsoft 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="ff9f9-185">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="ff9f9-185">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)