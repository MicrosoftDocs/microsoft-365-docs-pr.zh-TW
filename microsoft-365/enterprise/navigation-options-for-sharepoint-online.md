---
title: SharePoint Online 的導覽選項
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: 本文說明 SharePoint 線上中啟用 SharePoint 發佈功能的導覽選項網站。
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695590"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="e245d-103">SharePoint Online 的導覽選項</span><span class="sxs-lookup"><span data-stu-id="e245d-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="e245d-104">本文說明 SharePoint 線上中啟用 SharePoint 發佈功能的導覽選項網站。</span><span class="sxs-lookup"><span data-stu-id="e245d-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="e245d-105">導覽的選擇和設定會大幅影響 SharePoint Online 中網站的效能與擴充性。</span><span class="sxs-lookup"><span data-stu-id="e245d-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="e245d-106">只有在集中式入口網站需要時才會使用 SharePoint 發佈網站範本，而且發佈功能應該只在特定網站上啟用，而且只有在絕對需要時才會在使用不當時影響效能。</span><span class="sxs-lookup"><span data-stu-id="e245d-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="e245d-107">如果您使用的是新式 SharePoint 導覽選項（例如，您的百萬位元功能表、級聯導覽或 hub 導覽），本文不會套用到您的網站。</span><span class="sxs-lookup"><span data-stu-id="e245d-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="e245d-108">新式 SharePoint 網站架構利用更平展的網站階層和中樞輻射模型。</span><span class="sxs-lookup"><span data-stu-id="e245d-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="e245d-109">這可讓許多案例達到，而不需要使用 SharePoint 發佈功能。</span><span class="sxs-lookup"><span data-stu-id="e245d-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="e245d-110">導覽選項的概述</span><span class="sxs-lookup"><span data-stu-id="e245d-110">Overview of navigation options</span></span>

<span data-ttu-id="e245d-111">導覽提供者設定會大幅影響整個網站的效能，而且必須慎重考慮，以挑選流覽提供者和設定，以有效地伸縮 SharePoint 網站的需求。</span><span class="sxs-lookup"><span data-stu-id="e245d-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="e245d-112">有兩個現成的導覽提供者和自訂導覽實現。</span><span class="sxs-lookup"><span data-stu-id="e245d-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="e245d-113">**如果您開啟網站的結構式流覽**快取，則第一個選項（[**結構導覽**](#using-structural-navigation-in-sharepoint-online)）是 Sharepoint Online for 傳統 SharePoint 網站中的建議流覽選項。</span><span class="sxs-lookup"><span data-stu-id="e245d-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="e245d-114">此導覽提供者會顯示目前網站底下的流覽專案，並選擇性地顯示目前網站及其同輩。</span><span class="sxs-lookup"><span data-stu-id="e245d-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="e245d-115">它提供額外的功能，例如安全性修整和網站結構列舉。</span><span class="sxs-lookup"><span data-stu-id="e245d-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="e245d-116">如果停用快取，這會對效能及擴充性產生負面影響，而且可能會受到節流。</span><span class="sxs-lookup"><span data-stu-id="e245d-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="e245d-117">第二個選項是 [**managed (中繼資料) 導覽**](#using-managed-navigation-and-metadata-in-sharepoint-online)）代表使用受管理的中繼資料字片語流覽專案。</span><span class="sxs-lookup"><span data-stu-id="e245d-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="e245d-118">建議您先停用安全修整，除非需要。</span><span class="sxs-lookup"><span data-stu-id="e245d-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="e245d-119">啟用此導覽提供者的安全性調整為安全的預設設定;不過，許多網站不需要安全性調整的額外負荷，因為導覽元素通常對網站的所有使用者都是一致的。</span><span class="sxs-lookup"><span data-stu-id="e245d-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="e245d-120">使用建議的設定來停用安全修整時，此導覽提供者不需要列舉網站結構，高擴充性會影響到可接受的效能。</span><span class="sxs-lookup"><span data-stu-id="e245d-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="e245d-121">除了現成的導覽提供者以外，許多客戶都已成功實施替代的自訂導覽實現。</span><span class="sxs-lookup"><span data-stu-id="e245d-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="e245d-122">請參閱本文中 [的搜尋導向用戶端腳本](#using-search-driven-client-side-scripting) 。</span><span class="sxs-lookup"><span data-stu-id="e245d-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="e245d-123">SharePoint 線上導覽選項的優點和缺點</span><span class="sxs-lookup"><span data-stu-id="e245d-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="e245d-124">下表摘要說明每個選項的優缺點。</span><span class="sxs-lookup"><span data-stu-id="e245d-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="e245d-125">結構導覽</span><span class="sxs-lookup"><span data-stu-id="e245d-125">Structural navigation</span></span>  |<span data-ttu-id="e245d-126">受管理導覽</span><span class="sxs-lookup"><span data-stu-id="e245d-126">Managed navigation</span></span>  |<span data-ttu-id="e245d-127">搜尋導向導覽</span><span class="sxs-lookup"><span data-stu-id="e245d-127">Search-driven navigation</span></span>  |<span data-ttu-id="e245d-128">自訂導覽提供者</span><span class="sxs-lookup"><span data-stu-id="e245d-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e245d-129">優</span><span class="sxs-lookup"><span data-stu-id="e245d-129">Pros:</span></span><br/><br/><span data-ttu-id="e245d-130">易於維護</span><span class="sxs-lookup"><span data-stu-id="e245d-130">Easy to maintain</span></span><br/><span data-ttu-id="e245d-131">已修整安全性</span><span class="sxs-lookup"><span data-stu-id="e245d-131">Security trimmed</span></span><br/><span data-ttu-id="e245d-132">在內容變更時于24小時內自動更新</span><span class="sxs-lookup"><span data-stu-id="e245d-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="e245d-133">優</span><span class="sxs-lookup"><span data-stu-id="e245d-133">Pros:</span></span><br/><br/><span data-ttu-id="e245d-134">易於維護</span><span class="sxs-lookup"><span data-stu-id="e245d-134">Easy to maintain</span></span><br/>|<span data-ttu-id="e245d-135">優</span><span class="sxs-lookup"><span data-stu-id="e245d-135">Pros:</span></span><br/><br/><span data-ttu-id="e245d-136">已修整安全性</span><span class="sxs-lookup"><span data-stu-id="e245d-136">Security trimmed</span></span><br/><span data-ttu-id="e245d-137">新增網站時自動更新</span><span class="sxs-lookup"><span data-stu-id="e245d-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="e245d-138">快速載入時間和本機快取導覽結構</span><span class="sxs-lookup"><span data-stu-id="e245d-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="e245d-139">優</span><span class="sxs-lookup"><span data-stu-id="e245d-139">Pros:</span></span><br/><br/><span data-ttu-id="e245d-140">可用選項的更寬選擇</span><span class="sxs-lookup"><span data-stu-id="e245d-140">Wider choice of options available</span></span><br/><span data-ttu-id="e245d-141">正確使用快取時的快速載入</span><span class="sxs-lookup"><span data-stu-id="e245d-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="e245d-142">許多選項適用于快速回應頁面設計</span><span class="sxs-lookup"><span data-stu-id="e245d-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="e245d-143">缺點：</span><span class="sxs-lookup"><span data-stu-id="e245d-143">Cons:</span></span><br/><br/><span data-ttu-id="e245d-144">**停用緩衝時影響效能**</span><span class="sxs-lookup"><span data-stu-id="e245d-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="e245d-145">受制于節流</span><span class="sxs-lookup"><span data-stu-id="e245d-145">Subject to throttling</span></span><br/>|<span data-ttu-id="e245d-146">缺點：</span><span class="sxs-lookup"><span data-stu-id="e245d-146">Cons:</span></span><br/><br/><span data-ttu-id="e245d-147">不會自動更新以反映網站結構</span><span class="sxs-lookup"><span data-stu-id="e245d-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="e245d-148">在**啟用安全修整**或流覽流覽結構複雜時影響效能</span><span class="sxs-lookup"><span data-stu-id="e245d-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="e245d-149">缺點：</span><span class="sxs-lookup"><span data-stu-id="e245d-149">Cons:</span></span><br/><br/><span data-ttu-id="e245d-150">不能輕鬆地訂購網站</span><span class="sxs-lookup"><span data-stu-id="e245d-150">No ability to easily order sites</span></span><br/><span data-ttu-id="e245d-151">需要自訂主版頁面 (所需的技術技能) </span><span class="sxs-lookup"><span data-stu-id="e245d-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="e245d-152">缺點：</span><span class="sxs-lookup"><span data-stu-id="e245d-152">Cons:</span></span><br/><br/><span data-ttu-id="e245d-153">需要自訂開發</span><span class="sxs-lookup"><span data-stu-id="e245d-153">Custom development is required</span></span><br/><span data-ttu-id="e245d-154">需要儲存外部資料源/快取（例如 Azure）</span><span class="sxs-lookup"><span data-stu-id="e245d-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="e245d-155">網站最適合的選項取決於您的網站需求和您的技術能力。</span><span class="sxs-lookup"><span data-stu-id="e245d-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="e245d-156">如果您想要在內容變更時自動更新的易於設定導覽提供者，則 [啟用](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) 快取的結構導覽是一個不錯的選擇。</span><span class="sxs-lookup"><span data-stu-id="e245d-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="e245d-157">將整體網站結構簡化為新式的 SharePoint 網站，以套用相同的原則，可提高效能，並簡化移至現代 SharePoint 網站的效能。</span><span class="sxs-lookup"><span data-stu-id="e245d-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="e245d-158">這表示的含義是，不需要有數百個網站的單一網站集合 (子網站) ，更好的方法是有許多網站集合，但 (子網站) 很少的子網站。</span><span class="sxs-lookup"><span data-stu-id="e245d-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="e245d-159">在 SharePoint Online 中分析導覽效能</span><span class="sxs-lookup"><span data-stu-id="e245d-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="e245d-160">[SharePoint 工具的頁面診斷](https://aka.ms/perftool)功能是 Microsoft Edge 和 Chrome 瀏覽器的瀏覽器擴充，可分析線上新式入口網站與傳統發佈網站頁面的 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e245d-160">The [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="e245d-161">此工具僅適用于線上 SharePoint，無法在 SharePoint 系統] 頁面上使用。</span><span class="sxs-lookup"><span data-stu-id="e245d-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="e245d-162">工具會針對每個已分析的頁面產生報表，顯示頁面如何針對預先定義的規則集執行，並在測試結果超出基線值時顯示詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e245d-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="e245d-163">SharePoint 線上管理員和設計者可以使用工具來疑難排解效能問題，以確保新頁面在發佈之前已經過優化。</span><span class="sxs-lookup"><span data-stu-id="e245d-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="e245d-164">**SPRequestDuration** 特別是 SharePoint 處理頁面所需的時間。</span><span class="sxs-lookup"><span data-stu-id="e245d-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="e245d-165">大量導覽 (例如在導覽) 中包含頁面、複雜的網站階層，以及其他設定和拓撲選項，都可能會大幅增加持續時間。</span><span class="sxs-lookup"><span data-stu-id="e245d-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="e245d-166">在 SharePoint Online 中使用結構導覽</span><span class="sxs-lookup"><span data-stu-id="e245d-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="e245d-167">這是預設使用的預置導覽，而且是最直接的解決方案。</span><span class="sxs-lookup"><span data-stu-id="e245d-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="e245d-168">不需要任何自訂，非技術使用者也可以輕鬆地新增專案、隱藏專案，以及從 [設定] 頁面中管理導覽。</span><span class="sxs-lookup"><span data-stu-id="e245d-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="e245d-169">建議您 [啟用](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)快取，否則會有昂貴的性能權衡。</span><span class="sxs-lookup"><span data-stu-id="e245d-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="e245d-170">如何實施結構性導覽快取</span><span class="sxs-lookup"><span data-stu-id="e245d-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="e245d-171">在 [**網站設定**  >  **外觀與風格**  >  **導覽**] 底下，您可以驗證是否已選取全域導覽或目前導覽的結構導覽。</span><span class="sxs-lookup"><span data-stu-id="e245d-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="e245d-172">選取 [ **顯示頁面** 會對效能產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="e245d-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![選取 [顯示子網站] 的結構導覽](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="e245d-174">您可以在網站集合層級或網站層級啟用或停用快取，且預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="e245d-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="e245d-175">若要在網站集合層級啟用，請在 [**網站設定**  >  **網站集合管理**  >  **網站集合導覽**] 底下，選取 [**啟用**快取] 方塊。</span><span class="sxs-lookup"><span data-stu-id="e245d-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![在網站層級啟用快取](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="e245d-177">若要在網站層級啟用，請在 [**網站設定**  >  **導覽**] 底下，選取 [**啟用**快取] 方塊。</span><span class="sxs-lookup"><span data-stu-id="e245d-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![在網站層級啟用快取](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="e245d-179">在 SharePoint Online 中使用受管理導覽和中繼資料</span><span class="sxs-lookup"><span data-stu-id="e245d-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="e245d-180">受管理導覽是另一個現成的現成選項，可讓您用來重新建立大部分與結構導覽相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e245d-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="e245d-181">受管理的中繼資料可以設定為啟用或停用安全修整。</span><span class="sxs-lookup"><span data-stu-id="e245d-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="e245d-182">當設定安全性調整為停用時，受管理的導覽會非常有效率，因為它會載入具有大量伺服器呼叫的所有導覽連結。</span><span class="sxs-lookup"><span data-stu-id="e245d-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="e245d-183">不過，啟用安全修整會否定受管理導覽的一些效能優點。</span><span class="sxs-lookup"><span data-stu-id="e245d-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="e245d-184">如果您需要啟用安全修整，建議您執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e245d-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="e245d-185">將所有易記 URL 連結更新為簡單連結</span><span class="sxs-lookup"><span data-stu-id="e245d-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="e245d-186">將必要的安全性調整節點新增為易記 URLs</span><span class="sxs-lookup"><span data-stu-id="e245d-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="e245d-187">將導覽專案數目限制為不超過100，且不超過3層級深度</span><span class="sxs-lookup"><span data-stu-id="e245d-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="e245d-188">許多網站不需要安全性調整，因為導覽結構通常會一致網站的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="e245d-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="e245d-189">如果停用安全性調整，而且在不是所有使用者都可以存取的情況下新增連結，則該連結仍會顯示，但會導致「拒絕存取」訊息。</span><span class="sxs-lookup"><span data-stu-id="e245d-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="e245d-190">沒有意外存取內容的風險。</span><span class="sxs-lookup"><span data-stu-id="e245d-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="e245d-191">如何執行受管理導覽和結果</span><span class="sxs-lookup"><span data-stu-id="e245d-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="e245d-192">關於受管理導覽的詳細資料，有數個 docs.microsoft.com 文章。</span><span class="sxs-lookup"><span data-stu-id="e245d-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="e245d-193">例如，請參閱 [SharePoint Server 中受管理導覽的概述](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)。</span><span class="sxs-lookup"><span data-stu-id="e245d-193">For example, see [Overview of managed navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="e245d-194">為了實施受管理導覽，您可以使用與網站導覽結構相對應的 URLs 來設定字詞。</span><span class="sxs-lookup"><span data-stu-id="e245d-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="e245d-195">管理的導覽甚至可以手動策劃，以在許多情況下取代結構性導覽。</span><span class="sxs-lookup"><span data-stu-id="e245d-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="e245d-196">例如：</span><span class="sxs-lookup"><span data-stu-id="e245d-196">For example:</span></span>

![SharePoint 線上網站結構](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="e245d-198">)</span><span class="sxs-lookup"><span data-stu-id="e245d-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="e245d-199">使用搜尋導向的用戶端腳本</span><span class="sxs-lookup"><span data-stu-id="e245d-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="e245d-200">自訂導覽實現的一個共同類別包含用戶端轉譯的設計模式，以儲存流覽節點的本機快取。</span><span class="sxs-lookup"><span data-stu-id="e245d-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="e245d-201">這些導覽提供者具有以下幾個主要優點：</span><span class="sxs-lookup"><span data-stu-id="e245d-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="e245d-202">它們通常適用于回應頁面設計。</span><span class="sxs-lookup"><span data-stu-id="e245d-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="e245d-203">它們的可擴充性和能力極高，因為它們在呈現時不需資源成本 (，而且在) 超時後會在背景中重新整理。</span><span class="sxs-lookup"><span data-stu-id="e245d-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="e245d-204">這些導覽提供者可以使用各種策略（從簡單靜態設定到不同動態資料提供者）來取得導覽資料。</span><span class="sxs-lookup"><span data-stu-id="e245d-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="e245d-205">資料提供者的範例是使用 **搜尋導向導覽**，這可讓您靈活地列舉流覽節點及有效處理安全性調整。</span><span class="sxs-lookup"><span data-stu-id="e245d-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="e245d-206">另外還有其他常見的選項可建立 **自訂導覽提供者**。</span><span class="sxs-lookup"><span data-stu-id="e245d-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="e245d-207">如需建立自訂導覽提供者的進一步指導，請參閱 [SharePoint Online 入口網站的導覽解決方案](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) 。</span><span class="sxs-lookup"><span data-stu-id="e245d-207">Please review [Navigation solutions for SharePoint Online portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="e245d-208">使用搜尋您可以使用連續編目，利用背景中所建立的索引。</span><span class="sxs-lookup"><span data-stu-id="e245d-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="e245d-209">搜尋結果會從搜尋索引中提取，而結果會進行安全修整。</span><span class="sxs-lookup"><span data-stu-id="e245d-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="e245d-210">在需要安全性調整時，這通常會比預置的流覽提供者更快速。</span><span class="sxs-lookup"><span data-stu-id="e245d-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="e245d-211">使用搜尋結構導覽，尤其是當您有複雜的網站結構時，會大幅加快頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="e245d-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="e245d-212">這透過受管理導覽的主要優點是您可以從安全性調整中受益。</span><span class="sxs-lookup"><span data-stu-id="e245d-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="e245d-213">這種方法包含建立自訂主版頁面，並以自訂 HTML 取代現成的導覽程式碼。</span><span class="sxs-lookup"><span data-stu-id="e245d-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="e245d-214">請遵循下列範例中所述的程式碼來取代檔案中的導覽程式碼 `seattle.html` 。</span><span class="sxs-lookup"><span data-stu-id="e245d-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="e245d-215">在此範例中，您將會開啟檔案 `seattle.html` ，並 `id="DeltaTopNavigation"` 以自訂的 HTML 程式碼取代整個元素。</span><span class="sxs-lookup"><span data-stu-id="e245d-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="e245d-216">範例：取代主版頁面中的現成導覽代碼</span><span class="sxs-lookup"><span data-stu-id="e245d-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="e245d-217">流覽至 [網站設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e245d-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="e245d-218">按一下 [ **主版頁面**] 以開啟主版頁面圖庫。</span><span class="sxs-lookup"><span data-stu-id="e245d-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="e245d-219">您可以從這裡流覽文件庫，並下載檔案 `seattle.master` 。</span><span class="sxs-lookup"><span data-stu-id="e245d-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="e245d-220">使用文字編輯器編輯程式碼，並刪除下列螢幕擷取畫面中的程式碼區塊。</span><span class="sxs-lookup"><span data-stu-id="e245d-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![刪除顯示的程式碼區塊](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="e245d-222">移除 and 標記之間的程式碼 `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` ，並以下列程式碼片段取代它：</span><span class="sxs-lookup"><span data-stu-id="e245d-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="e245d-223">取代您網站集合中載入影像錨點標籤的 URL 中的 URL。</span><span class="sxs-lookup"><span data-stu-id="e245d-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="e245d-224">進行變更之後，請重新命名檔案，然後將其上傳至主版頁面圖庫。</span><span class="sxs-lookup"><span data-stu-id="e245d-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="e245d-225">這會產生新的 .master 檔案。</span><span class="sxs-lookup"><span data-stu-id="e245d-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="e245d-226">此 HTML 是基本標記，會由 JavaScript 程式碼所傳回的搜尋結果填入。</span><span class="sxs-lookup"><span data-stu-id="e245d-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="e245d-227">您必須編輯程式碼，以變更 var root = "site 集合 URL" 的值，如下列程式碼片段所示：</span><span class="sxs-lookup"><span data-stu-id="e245d-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="e245d-228">結果會指派給自身的節點陣列，並使用 linq.js 將輸出指派給陣列 self 階層的物件。</span><span class="sxs-lookup"><span data-stu-id="e245d-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="e245d-229">此陣列是系結至 HTML 的物件。</span><span class="sxs-lookup"><span data-stu-id="e245d-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="e245d-230">若要在 ( toggleView 中完成此動作，您可以將 self 物件傳遞至 applyBinding ( # A3 函式函數。</span><span class="sxs-lookup"><span data-stu-id="e245d-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="e245d-231">這會使階層陣列系結至下列 HTML：</span><span class="sxs-lookup"><span data-stu-id="e245d-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="e245d-232">及的事件處理 `mouseenter` 程式 `mouseexit` 會新增至最上層的導覽，以處理在該函數中所完成的子網站下拉式功能表 `addEventsToElements()` 。</span><span class="sxs-lookup"><span data-stu-id="e245d-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="e245d-233">在我們的複雜導覽範例中，沒有本機快取的全新頁面載入顯示伺服器上所花費的時間已從基準結構導覽中削減，以取得與受管理導覽方法類似的結果。</span><span class="sxs-lookup"><span data-stu-id="e245d-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="e245d-234">關於 JavaScript 檔案 .。。</span><span class="sxs-lookup"><span data-stu-id="e245d-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="e245d-235">若使用自訂 JavaScript，請確定已啟用 public CDN，且檔案位於 CDN 位置。</span><span class="sxs-lookup"><span data-stu-id="e245d-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="e245d-236">整個 JavaScript 檔如下：</span><span class="sxs-lookup"><span data-stu-id="e245d-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="e245d-237">若要匯總上述函數中所示的 `jQuery $(document).ready` 程式碼已 `viewModel object` 建立，然後 `loadNavigationNodes()` 呼叫該物件上的函數。</span><span class="sxs-lookup"><span data-stu-id="e245d-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="e245d-238">此函數會載入先前在用戶端瀏覽器的 HTML5 本機儲存區中所建立的導覽階層，或其呼叫此函數 `queryRemoteInterface()` 。</span><span class="sxs-lookup"><span data-stu-id="e245d-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="e245d-239">`QueryRemoteInterface()``getRequest()`以腳本中所定義的查詢參數來建立要求，然後傳回伺服器的資料。</span><span class="sxs-lookup"><span data-stu-id="e245d-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="e245d-240">此資料基本上是網站集合中所有網站的陣列，都是以具有各種屬性的資料傳輸物件來表示。</span><span class="sxs-lookup"><span data-stu-id="e245d-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="e245d-241">然後，此資料會剖析成先前定義的 `SPO.Models.NavigationNode` 物件，用 `Knockout.js` 來建立可透過資料系結至我們先前所定義之 HTML 的可觀測的屬性。</span><span class="sxs-lookup"><span data-stu-id="e245d-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="e245d-242">然後將物件放入結果陣列中。</span><span class="sxs-lookup"><span data-stu-id="e245d-242">The objects are then put into a results array.</span></span> <span data-ttu-id="e245d-243">此陣列會使用挖空來剖析為 JSON，並儲存在本機瀏覽器儲存體中，以在今後的頁面載入時改善效能。</span><span class="sxs-lookup"><span data-stu-id="e245d-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="e245d-244">這種方法的優點</span><span class="sxs-lookup"><span data-stu-id="e245d-244">Benefits of this approach</span></span>

<span data-ttu-id="e245d-245">[這種方法](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)的一個主要好處是，您可以使用 HTML5 本機儲存區，在下次載入此頁面時，系統會為使用者在本機上儲存導覽。</span><span class="sxs-lookup"><span data-stu-id="e245d-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="e245d-246">使用 search API for 結構性導覽，我們取得了重大效能的增強功能;不過，它需要一些技術功能才能執行及自訂此功能。</span><span class="sxs-lookup"><span data-stu-id="e245d-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="e245d-247">在 [範例的實施](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)中，網站的排序方式與現成的結構流覽的方式相同;字母順序。</span><span class="sxs-lookup"><span data-stu-id="e245d-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="e245d-248">如果您想要從這種順序中偏離，開發及維護的方式會比較複雜。</span><span class="sxs-lookup"><span data-stu-id="e245d-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="e245d-249">此外，此方法也需要您與支援的主版頁面的偏離。</span><span class="sxs-lookup"><span data-stu-id="e245d-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="e245d-250">如果未維護自訂主版頁面，您的網站將會錯過 Microsoft 對主版頁面所做的更新和改進功能。</span><span class="sxs-lookup"><span data-stu-id="e245d-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="e245d-251">上面的程式 [代碼](#about-the-javascript-file) 具有下列相依性：</span><span class="sxs-lookup"><span data-stu-id="e245d-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="e245d-252">mobile https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="e245d-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="e245d-253">KnockoutJS - https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="e245d-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="e245d-254">Linq.js https://linqjs.codeplex.com/ 或 github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="e245d-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="e245d-255">目前的 LinqJS 版本不包含以上程式碼中使用的 ByHierarchy 方法，會中斷導覽程式碼。</span><span class="sxs-lookup"><span data-stu-id="e245d-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="e245d-256">若要修正此問題，請將下列方法新增至 Linq.js 檔案中的該行之前 `Flatten: function ()` 。</span><span class="sxs-lookup"><span data-stu-id="e245d-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="e245d-257">相關主題</span><span class="sxs-lookup"><span data-stu-id="e245d-257">Related topics</span></span>

[<span data-ttu-id="e245d-258">SharePoint Server 中受管理導覽的概觀</span><span class="sxs-lookup"><span data-stu-id="e245d-258">Overview of managed navigation in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="e245d-259">結構導覽快取和效能</span><span class="sxs-lookup"><span data-stu-id="e245d-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)