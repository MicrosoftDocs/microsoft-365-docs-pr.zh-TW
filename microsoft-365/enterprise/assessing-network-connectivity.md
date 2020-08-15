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
description: Microsoft 365 的設計目的是讓全球客戶可以使用網際網路連線來連線至服務。 隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而改善。
ms.openlocfilehash: c0bca2f354d71aa2f4f0c2b6fd05cb4786368b43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688650"
---
# <a name="assessing-microsoft-365-network-connectivity"></a><span data-ttu-id="42d29-104">評估 Microsoft 365 網路連線能力</span><span class="sxs-lookup"><span data-stu-id="42d29-104">Assessing Microsoft 365 network connectivity</span></span>

<span data-ttu-id="42d29-105">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="42d29-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="42d29-106">Microsoft 365 的設計目的是讓全球客戶可以使用網際網路連線來連線至服務。</span><span class="sxs-lookup"><span data-stu-id="42d29-106">Microsoft 365 is designed to enable customers all over the world to connect to the service using an internet connection.</span></span> <span data-ttu-id="42d29-107">隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而改善。</span><span class="sxs-lookup"><span data-stu-id="42d29-107">As the service evolves, the security, performance, and reliability of Microsoft 365 are improved based on customers using the internet to establish a connection to the service.</span></span>
  
<span data-ttu-id="42d29-108">規劃使用 Microsoft 365 的客戶應評估其現有和預測的網際網路連線需求，做為部署專案的一部分。</span><span class="sxs-lookup"><span data-stu-id="42d29-108">Customers planning to use Microsoft 365 should assess their existing and forecasted internet connectivity needs as a part of the deployment project.</span></span> <span data-ttu-id="42d29-109">針對企業級部署，可靠且適當地調整 internet 連線能力是使用 Microsoft 365 功能和案例的重要部分。</span><span class="sxs-lookup"><span data-stu-id="42d29-109">For enterprise class deployments reliable and appropriately sized internet connectivity is a critical part of consuming Microsoft 365 features and scenarios.</span></span>
  
<span data-ttu-id="42d29-110">根據您的大小和喜好設定，許多不同的人員和組織可以執行網路評估。</span><span class="sxs-lookup"><span data-stu-id="42d29-110">Network evaluations can be performed by many different people and organizations depending on your size and preferences.</span></span> <span data-ttu-id="42d29-111">評估的網路範圍也會因您在部署程式中所處的位置而有所不同。</span><span class="sxs-lookup"><span data-stu-id="42d29-111">The network scope of the assessment can also vary depending on where you're at in your deployment process.</span></span> <span data-ttu-id="42d29-112">為了協助您更深入瞭解執行網路評估的方式，我們產生了網路評估指南，協助您瞭解可用的選項。</span><span class="sxs-lookup"><span data-stu-id="42d29-112">To help you get a better understanding of what it takes to perform a network assessment, we've produced a network assessment guide to help you understand the options available to you.</span></span> <span data-ttu-id="42d29-113">這種評估會判斷需要新增至部署專案的步驟和資源，讓您能夠成功採用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="42d29-113">This assessment will determine what steps and resources need to be added to the deployment project to enable you to successfully adopt Microsoft 365.</span></span>
  
<span data-ttu-id="42d29-114">綜合網路評估會為網路設計挑戰提供可能的解決方案，以及執行詳細資料。</span><span class="sxs-lookup"><span data-stu-id="42d29-114">A comprehensive network assessment will provide possible solutions to networking design challenges along with implementation details.</span></span> <span data-ttu-id="42d29-115">有些網路評估會顯示對 Microsoft 365 的最佳網路連線能力，可與現有網路和網際網路出口基礎結構的次要設定或設計變更搭配使用。</span><span class="sxs-lookup"><span data-stu-id="42d29-115">Some network assessments will show that optimal network connectivity to Microsoft 365 can be accommodated with minor configuration or design changes to the existing network and internet egress infrastructure.</span></span>

<span data-ttu-id="42d29-116">有些評估會指出 Microsoft 365 的網路連線需要網路元件的額外投資。</span><span class="sxs-lookup"><span data-stu-id="42d29-116">Some assessments will indicate network connectivity to Microsoft 365 will require additional investments in networking components.</span></span> <span data-ttu-id="42d29-117">例如，跨分支辦公室和多個地理區域的商業網路可能需要投資 SD-WAN 解決方案或優化的路由基礎結構，以支援與 Microsoft 365 的網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="42d29-117">For example, enterprise networks that span branch offices and multiple geographic regions may require investments in SD-WAN solutions or optimized routing infrastructure to support internet connectivity to Microsoft 365.</span></span> <span data-ttu-id="42d29-118">有時候，評估會指出與 Microsoft 365 的網路連線，會受到諸如 [商務用 Skype Online 媒體質量](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)等案例的法規或效能需求影響。</span><span class="sxs-lookup"><span data-stu-id="42d29-118">Occasionally an assessment will indicate network connectivity to Microsoft 365 is influenced by regulation or performance requirements for scenarios such as [Skype for Business Online media quality](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).</span></span> <span data-ttu-id="42d29-119">這些額外需求可能會造成網際網路連線基礎結構、路由優化和特殊直接連線的投資。</span><span class="sxs-lookup"><span data-stu-id="42d29-119">These additional requirements may lead to investments in internet connectivity infrastructure, routing optimization, and specialized direct connectivity.</span></span>

<span data-ttu-id="42d29-120">協助您評估網路的一些資源：</span><span class="sxs-lookup"><span data-stu-id="42d29-120">Some resources to help you assess your network:</span></span>

- <span data-ttu-id="42d29-121">如需有關 Microsoft 365 網路的概念資訊，請參閱 [Microsoft 365 網路連線概述](microsoft-365-networking-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="42d29-121">See [Microsoft 365 network connectivity overview](microsoft-365-networking-overview.md) for conceptual information about Microsoft 365 networking.</span></span>
- <span data-ttu-id="42d29-122">請參閱 [Microsoft 365 網路連線原則](https://aka.ms/o365networkingprinciples) ，以瞭解安全管理 Microsoft 365 流量的連線原則，並取得最佳的效能。</span><span class="sxs-lookup"><span data-stu-id="42d29-122">See [Microsoft 365 Network Connectivity Principles](https://aka.ms/o365networkingprinciples) to understand the connectivity principles for securely managing Microsoft 365 traffic and getting the best possible performance.</span></span>
- <span data-ttu-id="42d29-123">註冊 [microsoft FastTrack](https://www.microsoft.com/fasttrack) 以取得 microsoft 365 規劃、設計及部署的指導性協助。</span><span class="sxs-lookup"><span data-stu-id="42d29-123">Sign up for [Microsoft FastTrack](https://www.microsoft.com/fasttrack) for guided assistance with Microsoft 365 planning, design and deployment.</span></span> 
- <span data-ttu-id="42d29-124">請參閱下列 [Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) 一節，以執行基本的連線測試，其可提供有關在指定使用者位置和 Microsoft 365 之間進行的網路連線增強功能的特定指導方針。</span><span class="sxs-lookup"><span data-stu-id="42d29-124">See the [Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) section below to run basic connectivity tests that provide specific guidance about networking connectivity improvements that can be made between a given user location and Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="42d29-125">若要使用 Office 365 ExpressRoute，必須使用 Microsoft 授權。</span><span class="sxs-lookup"><span data-stu-id="42d29-125">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="42d29-126">Microsoft 會在客戶的法規需求規定直接連線時，檢查每個客戶要求，並且只有授權 ExpressRoute 的 Office 365 使用方式。</span><span class="sxs-lookup"><span data-stu-id="42d29-126">Microsoft reviews every customer request and only authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="42d29-127">如果您有這樣的需求，請提供文位元組選及網路連結，以 [瞭解 Office 365 要求表單 ExpressRoute](https://aka.ms/O365ERReview) 中是否需要直接連線才能開始 Microsoft 複查。</span><span class="sxs-lookup"><span data-stu-id="42d29-127">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="42d29-128">嘗試建立 Office 365 之路由篩選的未授權訂閱將會收到 [錯誤訊息](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="42d29-128">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>
  
<span data-ttu-id="42d29-129">規劃 Microsoft 365 的網路評估時，應考慮的要點：</span><span class="sxs-lookup"><span data-stu-id="42d29-129">Key points to consider when planning your network assessment for Microsoft 365:</span></span>
  
- <span data-ttu-id="42d29-130">Microsoft 365 是透過公用網際網路執行的安全、可靠、高效能服務。</span><span class="sxs-lookup"><span data-stu-id="42d29-130">Microsoft 365 is a secure, reliable, high performance service that runs over the public internet.</span></span> <span data-ttu-id="42d29-131">我們會繼續投資以加強服務的這些方面。</span><span class="sxs-lookup"><span data-stu-id="42d29-131">We continue to invest to enhance these aspects of the service.</span></span> <span data-ttu-id="42d29-132">所有 Microsoft 365 服務均可透過網際網路連線取得。</span><span class="sxs-lookup"><span data-stu-id="42d29-132">All Microsoft 365 services are available via internet connectivity.</span></span>

- <span data-ttu-id="42d29-133">我們不斷優化 Microsoft 365 的核心層面，例如，針對網際網路連線的可用性、全域訪問能力和效能。</span><span class="sxs-lookup"><span data-stu-id="42d29-133">We are continually optimizing core aspects of Microsoft 365 such as availability, global reach, and performance for internet based connectivity.</span></span> <span data-ttu-id="42d29-134">例如，許多 Microsoft 365 服務會利用一組擴充的網際網路對向邊緣節點。</span><span class="sxs-lookup"><span data-stu-id="42d29-134">For example, many Microsoft 365 services leverage an expanding set of internet facing edge nodes.</span></span> <span data-ttu-id="42d29-135">此 edge 網路可為透過網際網路的連線提供最佳的鄰近性和效能。</span><span class="sxs-lookup"><span data-stu-id="42d29-135">This edge network offers the best proximity and performance to connections coming over the internet.</span></span>

- <span data-ttu-id="42d29-136">在考慮使用 Microsoft 365 做任何包含的服務（如小組或商務用 Skype Online 語音、影片或會議功能）時，客戶應完成端對端網路評估，並使用 [Microsoft FastTrack](https://www.microsoft.com/fasttrack)符合連線需求。</span><span class="sxs-lookup"><span data-stu-id="42d29-136">When considering using Microsoft 365 for any of the included services such as Teams or Skype for Business Online voice, video, or meeting capabilities, customers should complete an end to end network assessment and meet connectivity requirements using [Microsoft FastTrack](https://www.microsoft.com/fasttrack).</span></span>

<span data-ttu-id="42d29-137">如果您正在評估 Microsoft 365，但不確定從網路評估開始，或發現需要協助您克服的網路設計挑戰，請與您的 Microsoft 帳戶小組合作。</span><span class="sxs-lookup"><span data-stu-id="42d29-137">If you're evaluating Microsoft 365 and aren't sure where to begin with your network assessment or have found network design challenges that you need assistance to overcome, please work with your Microsoft account team.</span></span>

## <a name="the-microsoft-365-connectivity-test"></a><span data-ttu-id="42d29-138">Microsoft 365 connectivity test</span><span class="sxs-lookup"><span data-stu-id="42d29-138">The Microsoft 365 connectivity test</span></span>

<span data-ttu-id="42d29-139">[Microsoft 365 連線測試](https://aka.ms/netonboard)是一項概念證明 (POC) 網路評估工具，可對您的 microsoft 365 租使用者執行基本連線測試，並針對最佳 microsoft 365 效能進行特定的網路設計建議。</span><span class="sxs-lookup"><span data-stu-id="42d29-139">The [Microsoft 365 connectivity test](https://aka.ms/netonboard) is a proof of concept (POC) network assessment tool that runs basic connectivity tests against your Microsoft 365 tenant and makes specific network design recommendations for optimal Microsoft 365 performance.</span></span> <span data-ttu-id="42d29-140">工具強調常見的大型商業網路周邊設計選擇，這些選項對網際網路網頁流覽很有用，但會影響大型 SaaS 應用程式（如 Microsoft 365）的效能。</span><span class="sxs-lookup"><span data-stu-id="42d29-140">The tool highlights common large enterprise network perimeter design choices which are useful for Internet web browsing but impact the performance of large SaaS applications such as Microsoft 365.</span></span>

<span data-ttu-id="42d29-141">網路上架工具會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="42d29-141">The Network Onboarding tool does the following:</span></span>

- <span data-ttu-id="42d29-142">偵測您的位置，您也可以指定要測試的位置。</span><span class="sxs-lookup"><span data-stu-id="42d29-142">Detects your location, or you can specify a location to test</span></span>
- <span data-ttu-id="42d29-143">檢查網路出局的位置</span><span class="sxs-lookup"><span data-stu-id="42d29-143">Checks the location of your network egress</span></span>
- <span data-ttu-id="42d29-144">測試最近的 Microsoft 365 服務前端門的網路路徑</span><span class="sxs-lookup"><span data-stu-id="42d29-144">Tests the network path to the nearest Microsoft 365 service front door</span></span>
- <span data-ttu-id="42d29-145">使用可下載的 Windows 10 應用程式，提供與 proxy 伺服器、防火牆和 DNS 相關的周邊網路設計建議，以進行高級測試。</span><span class="sxs-lookup"><span data-stu-id="42d29-145">Provides advanced tests using a downloadable Windows 10 application that makes perimeter network design recommendations related to proxy servers, firewalls, and DNS.</span></span> <span data-ttu-id="42d29-146">工具也會執行商務用 Skype Online、Microsoft 小組 SharePoint 線上和 Exchange Online 的效能測試。</span><span class="sxs-lookup"><span data-stu-id="42d29-146">The tool also runs performance tests for Skype for Business Online, Microsoft Teams, SharePoint Online and Exchange Online.</span></span>

<span data-ttu-id="42d29-147">工具有兩個元件：一種瀏覽器架構使用者介面，可收集基本連線資訊，以及可執行高級測試並傳回其他評估資料的可下載 Windows 10 應用程式。</span><span class="sxs-lookup"><span data-stu-id="42d29-147">The tool has two components: a browser-based UI that collects basic connectivity information, and a downloadable Windows 10 application that runs advanced tests and returns additional assessment data.</span></span>

<span data-ttu-id="42d29-148">瀏覽器型工具會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="42d29-148">The browser-based tool displays the following information:</span></span>

- <span data-ttu-id="42d29-149">[結果與影響] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="42d29-149">Results and impact tab</span></span>
  - <span data-ttu-id="42d29-150">在使用中的服務前蓋地圖上的位置</span><span class="sxs-lookup"><span data-stu-id="42d29-150">The location on a map of the in-use service front door</span></span>
  - <span data-ttu-id="42d29-151">其他服務前門的地圖上的位置，可提供最佳連線能力</span><span class="sxs-lookup"><span data-stu-id="42d29-151">The location on a map of other service front doors that would provide optimal connectivity</span></span>
  - <span data-ttu-id="42d29-152">與其他 Microsoft 365 客戶相較于您附近的相對效能</span><span class="sxs-lookup"><span data-stu-id="42d29-152">Relative performance compared to other Microsoft 365 customers near you</span></span>
- <span data-ttu-id="42d29-153">詳細資料與解決方案] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="42d29-153">Details and solutions tab</span></span>
  - <span data-ttu-id="42d29-154">依城市和國家/地區的使用者位置</span><span class="sxs-lookup"><span data-stu-id="42d29-154">User location by city and country</span></span>
  - <span data-ttu-id="42d29-155">透過城市、州和國家的網路出局位置</span><span class="sxs-lookup"><span data-stu-id="42d29-155">Network egress location by city, state and country</span></span>
  - <span data-ttu-id="42d29-156">使用者進入網路出局距離</span><span class="sxs-lookup"><span data-stu-id="42d29-156">User to network egress distance</span></span>
  - <span data-ttu-id="42d29-157">Microsoft 365 Exchange Online 服務的前門位置</span><span class="sxs-lookup"><span data-stu-id="42d29-157">Microsoft 365 Exchange Online service front door location</span></span>
  - <span data-ttu-id="42d29-158">適用于使用者位置的最佳 Microsoft 365 Exchange Online 服務前門 (s) </span><span class="sxs-lookup"><span data-stu-id="42d29-158">Optimal Microsoft 365 Exchange Online service front door(s) for user location</span></span>
  - <span data-ttu-id="42d29-159">以較佳效能顯示大都市區域中的客戶</span><span class="sxs-lookup"><span data-stu-id="42d29-159">Customers in your metro area with better performance</span></span>

<span data-ttu-id="42d29-160">「高級測試下載」應用程式提供下列其他資訊：</span><span class="sxs-lookup"><span data-stu-id="42d29-160">The Advanced Tests downloadable application provides the following additional information:</span></span>

- <span data-ttu-id="42d29-161"> (新增) 的詳細資料和方案] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="42d29-161">Details and solutions tab (appended)</span></span>
  - <span data-ttu-id="42d29-162">使用者的預設閘道</span><span class="sxs-lookup"><span data-stu-id="42d29-162">User's default gateway</span></span>
  - <span data-ttu-id="42d29-163">用戶端 DNS 伺服器</span><span class="sxs-lookup"><span data-stu-id="42d29-163">Client DNS Server</span></span>
  - <span data-ttu-id="42d29-164">用戶端 DNS 遞迴解析程式</span><span class="sxs-lookup"><span data-stu-id="42d29-164">Client DNS Recursive Resolver</span></span>
  - <span data-ttu-id="42d29-165">Exchange Online DNS 伺服器</span><span class="sxs-lookup"><span data-stu-id="42d29-165">Exchange Online DNS server</span></span>
  - <span data-ttu-id="42d29-166">線上 DNS 伺服器 SharePoint</span><span class="sxs-lookup"><span data-stu-id="42d29-166">SharePoint Online DNS server</span></span>
  - <span data-ttu-id="42d29-167">Proxy 伺服器識別</span><span class="sxs-lookup"><span data-stu-id="42d29-167">Proxy server identification</span></span>
  - <span data-ttu-id="42d29-168">Media connectivity 檢查</span><span class="sxs-lookup"><span data-stu-id="42d29-168">Media connectivity check</span></span>
  - <span data-ttu-id="42d29-169">媒體質量封包遺失</span><span class="sxs-lookup"><span data-stu-id="42d29-169">Media quality packet loss</span></span>
  - <span data-ttu-id="42d29-170">媒體質量延遲</span><span class="sxs-lookup"><span data-stu-id="42d29-170">Media quality latency</span></span>
  - <span data-ttu-id="42d29-171">媒體質量抖動</span><span class="sxs-lookup"><span data-stu-id="42d29-171">Media quality jitter</span></span>
  - <span data-ttu-id="42d29-172">媒體質量資料包重新排序</span><span class="sxs-lookup"><span data-stu-id="42d29-172">Media quality packet reorder</span></span>
- <span data-ttu-id="42d29-173">對多項特定功能端點的連線性測試</span><span class="sxs-lookup"><span data-stu-id="42d29-173">Connectivity tests to multiple feature-specific endpoints</span></span>
- <span data-ttu-id="42d29-174">網路路徑診斷，包含對 Exchange Online、SharePoint 線上及小組服務的 tracert 和延遲資料</span><span class="sxs-lookup"><span data-stu-id="42d29-174">Network path diagnostics that include tracert and latency data for the Exchange Online, SharePoint Online and Teams services</span></span>

<span data-ttu-id="42d29-175">您可以閱讀有關 Microsoft 365 連線測試的資訊，並提供 [新的 microsoft 365 connectivity TEST POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) 的意見，並提供新的網路設計建議博客文章。</span><span class="sxs-lookup"><span data-stu-id="42d29-175">You can read about the Microsoft 365 connectivity test and provide feedback at the [Updated Microsoft 365 connectivity test POC with new network design recommendations](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) blog post.</span></span> <span data-ttu-id="42d29-176">有關此工具及其他 Microsoft 365 網路更新未來更新的資訊將會發佈到 [Office 365 網路](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) 博客。</span><span class="sxs-lookup"><span data-stu-id="42d29-176">Information about future updates to this tool and other Microsoft 365 networking updates will be posted to the [Office 365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) blog.</span></span>
  
<span data-ttu-id="42d29-177">您可以使用以下簡短連結回來： [ https://aka.ms/o365networkconnectivity 。](https://aka.ms/o365networkconnectivity)</span><span class="sxs-lookup"><span data-stu-id="42d29-177">Here's a short link you can use to come back: [https://aka.ms/o365networkconnectivity.](https://aka.ms/o365networkconnectivity)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="42d29-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="42d29-178">Related topics</span></span>

[<span data-ttu-id="42d29-179">Microsoft 365 網路連線概況</span><span class="sxs-lookup"><span data-stu-id="42d29-179">Microsoft 365 Network Connectivity Overview</span></span>](microsoft-365-networking-overview.md)

[<span data-ttu-id="42d29-180">Microsoft 365 網路連線原則</span><span class="sxs-lookup"><span data-stu-id="42d29-180">Microsoft 365 Network Connectivity Principles</span></span>](https://aka.ms/o365networkingprinciples)

[<span data-ttu-id="42d29-181">管理 Office 365 端點</span><span class="sxs-lookup"><span data-stu-id="42d29-181">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="42d29-182">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="42d29-182">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="42d29-183">Office 365 IP 位址和 URL Web 服務</span><span class="sxs-lookup"><span data-stu-id="42d29-183">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="42d29-184">Microsoft 365 網路和效能調整</span><span class="sxs-lookup"><span data-stu-id="42d29-184">Microsoft 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="42d29-185">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="42d29-185">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
