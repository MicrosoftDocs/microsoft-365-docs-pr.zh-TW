---
title: SharePoint Online 效能調整的簡介
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: 本文說明在 SharePoint Online 中設計最佳效能的頁面時所應考量的特定事項。
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909735"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="5daaa-103">SharePoint Online 效能調整的簡介</span><span class="sxs-lookup"><span data-stu-id="5daaa-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="5daaa-104">本文說明在 SharePoint Online 中設計最佳效能的頁面時所應考量的特定事項。</span><span class="sxs-lookup"><span data-stu-id="5daaa-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="5daaa-105">SharePoint Online 度量資訊</span><span class="sxs-lookup"><span data-stu-id="5daaa-105">SharePoint Online metrics</span></span>

<span data-ttu-id="5daaa-106">下列廣泛的 SharePoint Online 度量值提供有關效能的實際環境資料：</span><span class="sxs-lookup"><span data-stu-id="5daaa-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="5daaa-107">頁面載入速度</span><span class="sxs-lookup"><span data-stu-id="5daaa-107">How fast pages load</span></span>
    
- <span data-ttu-id="5daaa-108">每頁所需來回行程次數</span><span class="sxs-lookup"><span data-stu-id="5daaa-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="5daaa-109">服務的問題</span><span class="sxs-lookup"><span data-stu-id="5daaa-109">Issues with the service</span></span>
    
- <span data-ttu-id="5daaa-110">導致效能降低的其他事項</span><span class="sxs-lookup"><span data-stu-id="5daaa-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="5daaa-111">資料所導出的結論</span><span class="sxs-lookup"><span data-stu-id="5daaa-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="5daaa-112">資料會告訴我們：</span><span class="sxs-lookup"><span data-stu-id="5daaa-112">The data tells us:</span></span>
  
- <span data-ttu-id="5daaa-113">大部分頁面在 SharePoint Online 上的執行狀況良好。</span><span class="sxs-lookup"><span data-stu-id="5daaa-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="5daaa-114">非自訂頁面載入速度很快。</span><span class="sxs-lookup"><span data-stu-id="5daaa-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="5daaa-115">商務用 OneDrive、小組網站和系統頁面 (如 _layouts 等) 載入速度都很快。</span><span class="sxs-lookup"><span data-stu-id="5daaa-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="5daaa-116">最慢的 1% SharePoint Online 頁面載入時間需要超過 5000 毫秒。</span><span class="sxs-lookup"><span data-stu-id="5daaa-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="5daaa-117">您可使用的一項簡單基準測試是透過比較您的入口網站載入時間和商務用 OneDrive 首頁載入時間來測量效能，因其使用的自訂功能不多。</span><span class="sxs-lookup"><span data-stu-id="5daaa-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="5daaa-118">在進行網路效能問題疑難排解時，這通常是支援人員要求您完成的第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="5daaa-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="5daaa-119">檢查效能時，請使用標準使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5daaa-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="5daaa-120">網站集合系統管理員、網站擁有者、編輯者或參與者皆屬於其他的安全性群組，擁有額外的權限，因此擁有 SharePoint 在頁面上載入之外的其他元素。</span><span class="sxs-lookup"><span data-stu-id="5daaa-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="5daaa-121">這適用於 SharePoint 內部部署和 Sharepoint，但在內部部署狀況中，差異不會像在 SharePoint Online 中那樣容易發現。</span><span class="sxs-lookup"><span data-stu-id="5daaa-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="5daaa-122">為了正確評估使用者執行頁面的效能，請使用標準使用者帳戶，以避免載入安全性群組相關的製作控制和其他流量。</span><span class="sxs-lookup"><span data-stu-id="5daaa-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="5daaa-123">效能調整的連線類別</span><span class="sxs-lookup"><span data-stu-id="5daaa-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="5daaa-124">您可將伺服器與使用者之間的連線分類成三種主要元件。</span><span class="sxs-lookup"><span data-stu-id="5daaa-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="5daaa-125">在設計 SharePoint Online 頁面以深入瞭解載入時間時，請將這些元件納入考量。</span><span class="sxs-lookup"><span data-stu-id="5daaa-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="5daaa-126">**伺服器**：Microsoft 在資料中心主控的伺服器。</span><span class="sxs-lookup"><span data-stu-id="5daaa-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="5daaa-127">**網路**：Microsoft 網路、網際網路以及資料中心和您的使用者之間的內部部署網路。</span><span class="sxs-lookup"><span data-stu-id="5daaa-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="5daaa-128">**瀏覽器**：載入頁面所在。</span><span class="sxs-lookup"><span data-stu-id="5daaa-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="5daaa-129">在這三種連線中，通常有五個原因會造成 95% 的頁面緩慢情形。</span><span class="sxs-lookup"><span data-stu-id="5daaa-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="5daaa-130">本文將討論這些原因：</span><span class="sxs-lookup"><span data-stu-id="5daaa-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="5daaa-131">瀏覽問題</span><span class="sxs-lookup"><span data-stu-id="5daaa-131">Navigation issues</span></span>
    
- <span data-ttu-id="5daaa-132">內容彙總</span><span class="sxs-lookup"><span data-stu-id="5daaa-132">Content roll up</span></span>
    
- <span data-ttu-id="5daaa-133">大型檔案</span><span class="sxs-lookup"><span data-stu-id="5daaa-133">Large files</span></span>
    
- <span data-ttu-id="5daaa-134">對伺服器的要求太多</span><span class="sxs-lookup"><span data-stu-id="5daaa-134">Many requests to the server</span></span>
    
- <span data-ttu-id="5daaa-135">網頁組件處理</span><span class="sxs-lookup"><span data-stu-id="5daaa-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="5daaa-136">伺服器連線</span><span class="sxs-lookup"><span data-stu-id="5daaa-136">Server connection</span></span>

<span data-ttu-id="5daaa-137">許多影響 SharePoint 內部部署效能的問題也會在 SharePoint Online 上出現。</span><span class="sxs-lookup"><span data-stu-id="5daaa-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="5daaa-138">一如預期，您有許多手段可控制伺服器在內部部署 SharePoint 中的執行效能。</span><span class="sxs-lookup"><span data-stu-id="5daaa-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="5daaa-139">但在 SharePoint Online 上，情形略有不同。</span><span class="sxs-lookup"><span data-stu-id="5daaa-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="5daaa-140">您讓伺服器執行的工作越多，呈現頁面所需的時間就越長。</span><span class="sxs-lookup"><span data-stu-id="5daaa-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="5daaa-141">而在 SharePoint 中，含有多個網頁組件的複雜頁面才是造成這方面問題的最大禍首。</span><span class="sxs-lookup"><span data-stu-id="5daaa-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="5daaa-142">SharePoint Server 內部部署</span><span class="sxs-lookup"><span data-stu-id="5daaa-142">SharePoint Server on-premises</span></span>
  
![內部部署伺服器的螢幕擷取畫面](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="5daaa-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5daaa-144">SharePoint Online</span></span>
  
![伺服器連線的螢幕擷取畫面](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="5daaa-146">在 SharePoint Online 上，某些網頁要求可能實際上最後會呼叫多部伺服器。</span><span class="sxs-lookup"><span data-stu-id="5daaa-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="5daaa-147">原本只是一個要求，最後卻可能演變成涉及多部伺服器的多個要求。</span><span class="sxs-lookup"><span data-stu-id="5daaa-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="5daaa-148">從頁面載入的觀點來看，這些互動不僅成本昂貴且會讓效率變慢。</span><span class="sxs-lookup"><span data-stu-id="5daaa-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="5daaa-149">這些伺服器對伺服器的互動範例如下：</span><span class="sxs-lookup"><span data-stu-id="5daaa-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="5daaa-150">Web 對 SQL Server</span><span class="sxs-lookup"><span data-stu-id="5daaa-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="5daaa-151">Web 對應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="5daaa-151">Web to application servers</span></span>
    
<span data-ttu-id="5daaa-152">另一個導致伺服器互動速度變慢的因素是快取遺漏。</span><span class="sxs-lookup"><span data-stu-id="5daaa-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="5daaa-153">不同於內部部署 SharePoint，雖然機率微乎其微，但您有可能會叫用相同伺服器來取得之前造訪的頁面；這個情形會讓物件快取過時。</span><span class="sxs-lookup"><span data-stu-id="5daaa-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="5daaa-154">網路連線</span><span class="sxs-lookup"><span data-stu-id="5daaa-154">Network connection</span></span>

<span data-ttu-id="5daaa-155">在未利用 WAN 的內部部署 SharePoint 中，您可以在資料中心與使用者之間使用高速連線。</span><span class="sxs-lookup"><span data-stu-id="5daaa-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="5daaa-156">從網路的觀點來看，這通常能簡化管理程序。</span><span class="sxs-lookup"><span data-stu-id="5daaa-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="5daaa-157">在 SharePoint Online 上，則還要再考慮幾個因素，例如：</span><span class="sxs-lookup"><span data-stu-id="5daaa-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="5daaa-158">Microsoft 網路</span><span class="sxs-lookup"><span data-stu-id="5daaa-158">The Microsoft network</span></span>
    
- <span data-ttu-id="5daaa-159">網際網路</span><span class="sxs-lookup"><span data-stu-id="5daaa-159">The Internet</span></span>
    
- <span data-ttu-id="5daaa-160">ISP</span><span class="sxs-lookup"><span data-stu-id="5daaa-160">The ISP</span></span>
    
<span data-ttu-id="5daaa-161">不論您使用哪個 SharePoint (和那個網路) 版本，會導致網路忙碌的因素通常包括：</span><span class="sxs-lookup"><span data-stu-id="5daaa-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="5daaa-162">承載過大</span><span class="sxs-lookup"><span data-stu-id="5daaa-162">Large payload</span></span>
    
- <span data-ttu-id="5daaa-163">檔案太多</span><span class="sxs-lookup"><span data-stu-id="5daaa-163">Many files</span></span>
    
- <span data-ttu-id="5daaa-164">與伺服器的實體距離太遠</span><span class="sxs-lookup"><span data-stu-id="5daaa-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="5daaa-165">您可以在 SharePoint Online 中利用的其中一項功能為 Microsoft CDN (內容傳遞網路)。</span><span class="sxs-lookup"><span data-stu-id="5daaa-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="5daaa-166">CDN 基本上是部署到多個資料中心的分散式伺服器集合。</span><span class="sxs-lookup"><span data-stu-id="5daaa-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="5daaa-167">使用 CDN 時，頁面上的內容可裝載於接近用戶端的伺服器，即便用戶端離原始 SharePoint 伺服器很遠。</span><span class="sxs-lookup"><span data-stu-id="5daaa-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="5daaa-168">Microsoft 未來將多加利用此功能來儲存無法自訂之頁面的本機執行個體，例如 SharePoint Online 管理首頁。</span><span class="sxs-lookup"><span data-stu-id="5daaa-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="5daaa-169">如需有關 CDN 的詳細資訊，請參閱[內容傳遞網路](content-delivery-networks.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="5daaa-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="5daaa-170">您必須注意但可能無能為力的因素是您的 ISP 連線速度。</span><span class="sxs-lookup"><span data-stu-id="5daaa-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="5daaa-171">簡單的速度測試工具會告訴您連線速度。</span><span class="sxs-lookup"><span data-stu-id="5daaa-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="5daaa-172">瀏覽器連線</span><span class="sxs-lookup"><span data-stu-id="5daaa-172">Browser connection</span></span>

<span data-ttu-id="5daaa-173">從效能的觀點來看，有幾個與網頁瀏覽器有關的因素要考慮進去。</span><span class="sxs-lookup"><span data-stu-id="5daaa-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="5daaa-174">造訪複雜頁面會影響效能。</span><span class="sxs-lookup"><span data-stu-id="5daaa-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="5daaa-175">大部分瀏覽器的快取都很小 (大約 90 MB)，而平均網頁大小通常是 1.6 MB 左右。</span><span class="sxs-lookup"><span data-stu-id="5daaa-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="5daaa-176">不需要多久時間就會把快取用完。</span><span class="sxs-lookup"><span data-stu-id="5daaa-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="5daaa-177">頻寬可能也是個問題。</span><span class="sxs-lookup"><span data-stu-id="5daaa-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="5daaa-178">例如，若使用者在另一個工作階段中觀看影片，則會影響您的 SharePoint 網頁效能。</span><span class="sxs-lookup"><span data-stu-id="5daaa-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="5daaa-179">您無法阻止使用者串流媒體，但可控制為使用者載入頁面的方式。</span><span class="sxs-lookup"><span data-stu-id="5daaa-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="5daaa-180">請看下列文章來取得不同的 SharePoint Online 頁面自訂技術和其他最佳作法，以協助您達到最佳效能。</span><span class="sxs-lookup"><span data-stu-id="5daaa-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="5daaa-181">SharePoint Online 的瀏覽選項</span><span class="sxs-lookup"><span data-stu-id="5daaa-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="5daaa-182">使用 Sharepoint Online 網頁診斷工具</span><span class="sxs-lookup"><span data-stu-id="5daaa-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="5daaa-183">SharePoint Online 的影像最佳化</span><span class="sxs-lookup"><span data-stu-id="5daaa-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="5daaa-184">在 SharePoint Online 中延遲載入圖片與 JavaScript</span><span class="sxs-lookup"><span data-stu-id="5daaa-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="5daaa-185">SharePoint Online 中的縮製和統合</span><span class="sxs-lookup"><span data-stu-id="5daaa-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="5daaa-186">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5daaa-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="5daaa-187">使用內容搜尋網頁組件 (而非內容查詢網頁組件) 來改善 SharePoint Online 中的效能</span><span class="sxs-lookup"><span data-stu-id="5daaa-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="5daaa-188">SharePoint Online 容量規劃和負載測試</span><span class="sxs-lookup"><span data-stu-id="5daaa-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="5daaa-189">診斷 SharePoint Online 的效能問題</span><span class="sxs-lookup"><span data-stu-id="5daaa-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="5daaa-190">使用 SharePoint Online 的物件快取</span><span class="sxs-lookup"><span data-stu-id="5daaa-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="5daaa-191">操作方法：如何避免在 SharePoint Online 中受到節流控制或封鎖</span><span class="sxs-lookup"><span data-stu-id="5daaa-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
