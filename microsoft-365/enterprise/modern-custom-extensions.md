---
title: 在 SharePoint Online 新式網站頁面中最佳化自訂延伸模組
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: 深入了解如何在 SharePoint Online 新式網站頁面中最佳化自訂延伸模組的效能。
ms.openlocfilehash: 05d9b9cd9ad70630169595dc42080c718b39dbc8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923051"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="b732e-103">在 SharePoint Online 新式網站頁面中最佳化自訂延伸模組的效能</span><span class="sxs-lookup"><span data-stu-id="b732e-103">Optimize custom extension performance in SharePoint Online modern site pages</span></span>

<span data-ttu-id="b732e-104">本文可協助您了解如何判斷自訂延伸模組如何影響使用者察覺延遲，以及如何修復常見問題。</span><span class="sxs-lookup"><span data-stu-id="b732e-104">This article will help you understand how to determine how custom extensions affect user perceived latency, and how to remediate common issues.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a><span data-ttu-id="b732e-105">使用「適用於 SharePoint 的頁面診斷」工具來分析自訂延伸模組</span><span class="sxs-lookup"><span data-stu-id="b732e-105">Use the Page Diagnostics for SharePoint tool to analyze custom extensions</span></span>

<span data-ttu-id="b732e-106">適用於 SharePoint 的頁面診斷工具是全新 Microsoft Edge (https://www.microsoft.com/edge) 和 Chrome 瀏覽器的擴充功能，可以用來分析 SharePoint Online 新式入口網站與傳統發佈網站頁面。</span><span class="sxs-lookup"><span data-stu-id="b732e-106">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="b732e-107">該工具會針對每個分析頁面提供一份報告，顯示頁面如何針對定義的效能準則組執行。</span><span class="sxs-lookup"><span data-stu-id="b732e-107">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="b732e-108">若要安裝及了解「適用於 SharePoint 的頁面診斷」工具，請造訪[使用適用於 SharePoint Online 的頁面診斷工具](page-diagnostics-for-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="b732e-108">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="b732e-109">網頁診斷工具只能用於 SharePoint Online，且無法在 SharePoint 系統頁面使用。</span><span class="sxs-lookup"><span data-stu-id="b732e-109">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="b732e-110">當您使用「適用於 SharePoint 的頁面診斷」工具分析 SharePoint 網站頁面時，您可以在 _[診斷測試]_ 窗格的 **[擴充功能正影響載入時間]** 和/或 **[使用過多擴充功能]** 結果中，看到超過基準計量的自訂延伸模組相關資訊</span><span class="sxs-lookup"><span data-stu-id="b732e-110">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about custom extensions that exceed the baseline metric in the **Extensions are impacting load time** and/or the **Too many extensions used** result in the _Diagnostic tests_ pane</span></span> 

<span data-ttu-id="b732e-111">可能的結果包括：</span><span class="sxs-lookup"><span data-stu-id="b732e-111">Possible results include:</span></span>

- <span data-ttu-id="b732e-112">**需要注意** (紅色)：載入耗時比 **兩** 秒還要久的任何 _自訂_ 延伸模組。</span><span class="sxs-lookup"><span data-stu-id="b732e-112">**Attention required** (red): Any _custom_ extension that takes longer than **one** second to load.</span></span> <span data-ttu-id="b732e-113">測試結果中顯示的載入時間總計會依據模組載入和初始來細分。</span><span class="sxs-lookup"><span data-stu-id="b732e-113">Total load time as displayed in test results is broken down by module load and init.</span></span> <span data-ttu-id="b732e-114">此外，如果頁面上的延伸模組太多，可能會影響頁面載入時間，而如果頁面上使用 **七個** 以上的延伸模組，系統將會醒目提示。</span><span class="sxs-lookup"><span data-stu-id="b732e-114">Additionally, if there are too many extensions on a page they can impact the page load time and this will be highlighted if **seven** or more extensions are used on the page.</span></span>
- <span data-ttu-id="b732e-115">**改善機會** (黃色)：如果使用 **五個** 以上的延伸模組，系統將會在此區段以警示方式醒目提示，直到使用七個以上的延伸模組之後，就會以 [需要注意] 方式醒目提示。</span><span class="sxs-lookup"><span data-stu-id="b732e-115">**Improvement Opportunities** (yellow) If **five** or more extensions are used they will be highlighted in this section as a warning until seven or more are used which will then be highlighted as Attention Required.</span></span>
- <span data-ttu-id="b732e-116">**無需採取動作** (綠色)：沒有任何延伸模組載入耗時超過一秒。</span><span class="sxs-lookup"><span data-stu-id="b732e-116">**No action required** (green): No extension is taking longer than one second to load.</span></span>

<span data-ttu-id="b732e-117">如果分機影響頁面載入時間，或頁面上的副檔名過多，則結果會顯示在結果的 [ **注意事項** ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="b732e-117">If an extension is impacting page load time or there are too many extensions on the page, the result appears in the **Attention required** section of the results.</span></span> <span data-ttu-id="b732e-118">按一下結果以查看載入緩慢的延伸模組或已醒目提示太多延伸模組的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b732e-118">Click the result to see details about which extension is loading slowly or too many extensions has been highlighted.</span></span> <span data-ttu-id="b732e-119">未來「適用於 SharePoint 的頁面診斷」工具的更新可能會包含分析規則的更新，因此請確保永遠擁有最新版本的工具。</span><span class="sxs-lookup"><span data-stu-id="b732e-119">Future updates to the Page Diagnostics for SharePoint tool may include updates to analysis rules, so please ensure you always have the latest version of the tool.</span></span>

![頁面載入時間結果](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

<span data-ttu-id="b732e-121">結果中提供的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="b732e-121">Information available in the results includes:</span></span>

- <span data-ttu-id="b732e-122">[名稱和識別碼] 顯示可協助您在頁面上尋找延伸模組的識別資訊</span><span class="sxs-lookup"><span data-stu-id="b732e-122">**Name and ID** shows identifying information that can help you find the extension on the page</span></span>
- <span data-ttu-id="b732e-123">**Total** 顯示擴充至模組載入和初始化的總時間。</span><span class="sxs-lookup"><span data-stu-id="b732e-123">**Total** shows the total time for the extension to module load and initialize.</span></span> <span data-ttu-id="b732e-124">它是在頁面上開始執行的分機所用的總相對時間（從開始到結尾）。</span><span class="sxs-lookup"><span data-stu-id="b732e-124">It is the total relative time taken by the extension to execute on the page, from beginning to the end.</span></span>
- <span data-ttu-id="b732e-125">**模組載入** 顯示下載、評估和載入副檔名 JAVASCRIPT 和 CSS 檔案所需的時間。</span><span class="sxs-lookup"><span data-stu-id="b732e-125">**Module Load** shows the time taken to download, evaluate and load the extensions JavaScript and CSS files.</span></span> <span data-ttu-id="b732e-126">接著，它會啟動 Init 處理常式。</span><span class="sxs-lookup"><span data-stu-id="b732e-126">It will then start the Init process.</span></span>
- <span data-ttu-id="b732e-127">**Init** 顯示擴充初始化資料所需的時間。</span><span class="sxs-lookup"><span data-stu-id="b732e-127">**Init** shows the time taken for the extension to initialize the data.</span></span>
    <span data-ttu-id="b732e-128">這是一項非同步呼叫和 init 時間是指當傳回的承諾得以解決時，onInit 函式的時間計算。</span><span class="sxs-lookup"><span data-stu-id="b732e-128">It is an asynchronous call and init time is the calculation of time for the onInit function when the returned promise is resolved.</span></span>

<span data-ttu-id="b732e-129">系統會提供此資訊，協助設計人員和開發人員對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="b732e-129">This information is provided to help designers and developers troubleshoot issues.</span></span> <span data-ttu-id="b732e-130">此資訊應提供給您的設計和開發小組。</span><span class="sxs-lookup"><span data-stu-id="b732e-130">This information should be provided to your design and development team.</span></span>

## <a name="overview-of-extensions"></a><span data-ttu-id="b732e-131">延伸模組的概觀</span><span class="sxs-lookup"><span data-stu-id="b732e-131">Overview of extensions</span></span>

<span data-ttu-id="b732e-132">SharePoint 架構 (SPFx) 延伸模組可用於延伸 SharePoint 使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="b732e-132">SharePoint Framework (SPFx) Extensions can be used to extend the SharePoint user experience.</span></span> <span data-ttu-id="b732e-133">透過 SharePoint 架構延伸模組，您可以自訂 SharePoint 體驗的更多層面，包括通知區域、工具列及清單資料檢視。</span><span class="sxs-lookup"><span data-stu-id="b732e-133">With SharePoint Framework Extensions, you can customize more facets of the SharePoint experience, including notification areas, toolbars, and list data views.</span></span>

<span data-ttu-id="b732e-134">延伸模組對 SharePoint 頁面的效能有不良影響，因為這也會佔用 CPU 和網路資源來執行必要的工作。</span><span class="sxs-lookup"><span data-stu-id="b732e-134">Extensions can have a bad influence on the performance of a SharePoint page as it also takes CPU and network resources to do required work.</span></span>

<span data-ttu-id="b732e-135">延伸模組有四種類型：</span><span class="sxs-lookup"><span data-stu-id="b732e-135">There are four types of extensions:</span></span>

- <span data-ttu-id="b732e-136">**應用程式自訂員** 會在頁面中新增指令碼，並存取已知 HTML 元素預留位置，並以自訂轉譯進行延伸。</span><span class="sxs-lookup"><span data-stu-id="b732e-136">**Application Customizers** adds scripts to the page, and accesses well-known HTML element placeholders and extends them with custom renderings.</span></span>
- <span data-ttu-id="b732e-137">**欄位自訂員** 提供清單中欄位資料的修改檢視。</span><span class="sxs-lookup"><span data-stu-id="b732e-137">**Field Customizers** provides modified views to data for fields within a list.</span></span>
- <span data-ttu-id="b732e-138">**命令集** 延伸 SharePoint 命令面來新增新動作，並提供您可用來實作行為的用戶端程式碼。</span><span class="sxs-lookup"><span data-stu-id="b732e-138">**Command Sets** extend the SharePoint command surfaces to add new actions, and provides client-side code that you can use to implement behaviors.</span></span>
- <span data-ttu-id="b732e-139">**搜尋查詢修改程式 (僅供預覽)** 會在執行搜尋查詢前被叫用。</span><span class="sxs-lookup"><span data-stu-id="b732e-139">**Search Query Modifier (preview only)** are invoked just before the search query is executed.</span></span>

## <a name="remediate-extension-performance-issues"></a><span data-ttu-id="b732e-140">修復延伸模組效能問題</span><span class="sxs-lookup"><span data-stu-id="b732e-140">Remediate extension performance issues</span></span>

<span data-ttu-id="b732e-141">按照本節的指導方針進行，以找出 [延伸模組影響頁面載入時間] 結果中列出的延伸模組效能問題，並加以修復。</span><span class="sxs-lookup"><span data-stu-id="b732e-141">Follow the guidance in this section to identify and remediate performance issues with extensions listed in the **Extensions are impacting page load time** results.</span></span>

>[!NOTE]
><span data-ttu-id="b732e-142">在頁面生命週期的早期階段中，可能會執行應用程式自訂員，因此可能會影響頁面上其他延伸模組的效能。</span><span class="sxs-lookup"><span data-stu-id="b732e-142">Application customizers may be executed in the early stage during the lifecycle of a page and it may influence the performance of other extensions on the page.</span></span>

<span data-ttu-id="b732e-143">頁面診斷工具中的稽核結果會顯示兩個執行延伸模組的階段，以便協助找出潛在的效能影響。</span><span class="sxs-lookup"><span data-stu-id="b732e-143">The audit results in the Page Diagnostic Tool will display two stages of executing an extension in order to help identify the potential performance impact.</span></span>

- <span data-ttu-id="b732e-144">**模組載入時間** 是載入延伸模組所需的時間，這會受到延伸模組的大小影響，因此建議您只組合延伸模組中的必要資料庫，並選擇較輕量的資料庫。</span><span class="sxs-lookup"><span data-stu-id="b732e-144">**Module load** is how long it takes to load the extension, which is impacted by the size of an extension so it is a good idea to only bundle the necessary libraries in the extension and to also choose lighter libraries.</span></span>
- <span data-ttu-id="b732e-145">**初始** 是延伸模組和延伸模組開發人員的初始化時間，應考慮延伸模組是否在初始階段期間執行不必要的工作，或執行太多命令。</span><span class="sxs-lookup"><span data-stu-id="b732e-145">**Init** is the initialization time of the extension and extension developers should consider whether the extension is doing unnecessary work or executing too many commands during the initializing stage.</span></span>

<span data-ttu-id="b732e-146">頁面作者也可以使用稽核結果，查看頁面上是否有太多延伸模組，因為延伸太多會對頁面的效能造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="b732e-146">Page authors can also use the audit result to see whether a page has too many extensions as too many extensions will negatively impact the performance of a page.</span></span>

- <span data-ttu-id="b732e-147">**延伸模組大小和相依性**</span><span class="sxs-lookup"><span data-stu-id="b732e-147">**Extension size and dependencies**</span></span>
  - <span data-ttu-id="b732e-148">若要下載最佳的靜態資源，需要使用 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="b732e-148">Use of the Office 365 CDN is required for optimal static resource download.</span></span> <span data-ttu-id="b732e-149">公用 CDN 來源適用於 _js/css_ 檔案。</span><span class="sxs-lookup"><span data-stu-id="b732e-149">Public CDN origins are preferable for _js/css_ files.</span></span> <span data-ttu-id="b732e-150">如需使用 Office 365 CDN 的詳細資訊，請參閱[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="b732e-150">For more information about using the Office 365 CDN, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="b732e-151">重複使用架構，例如隨附於 SharePoint 架構 (SPFx) 的 _React_ 和 _Fabric imports_。</span><span class="sxs-lookup"><span data-stu-id="b732e-151">Reuse frameworks like _React_ and _Fabric imports_ that come as part of the SharePoint Framework (SPFx).</span></span> <span data-ttu-id="b732e-152">如需詳細資訊，請參閱 [SharePoint 架構的概觀](/sharepoint/dev/spfx/sharepoint-framework-overview) (英文)。</span><span class="sxs-lookup"><span data-stu-id="b732e-152">For more information, see [Overview of the SharePoint Framework](/sharepoint/dev/spfx/sharepoint-framework-overview).</span></span>
  - <span data-ttu-id="b732e-153">請確保使用最新版本的 SharePoint 架構，並且在新版本可用時升級。</span><span class="sxs-lookup"><span data-stu-id="b732e-153">Ensure that you are using the latest version of the SharePoint Framework, and upgrade to new versions as they become available.</span></span>
- <span data-ttu-id="b732e-154">**資料擷取/快取**</span><span class="sxs-lookup"><span data-stu-id="b732e-154">**Data fetching/caching**</span></span>
  - <span data-ttu-id="b732e-155">如果延伸模組依賴額外伺服器呼叫，以擷取資料進行顯示，請確保這些伺服器 API 是快速的及/或實作用戶端快取 (例如針對大型集合使用 _localStorage_ 或 _IndexDB_)。</span><span class="sxs-lookup"><span data-stu-id="b732e-155">If the extension relies on extra server calls to fetch data for display, ensure those server APIs are fast and/or implement client side caching (such as using _localStorage_ or _IndexDB_ for larger sets).</span></span>
  - <span data-ttu-id="b732e-156">如果需要多個呼叫來轉譯重要資料，請考量在伺服器上進行批次處理，或者將要求合併至單一呼叫的其他方法。</span><span class="sxs-lookup"><span data-stu-id="b732e-156">If multiple calls are required to render critical data, consider batching on the server or other methods of consolidating requests to a single call.</span></span>
  - <span data-ttu-id="b732e-157">或者，如果資料的某些元素需要較慢的 API，但是對於初始轉譯並不重要，請將這些項目分離為個別呼叫，在重要資料轉譯之後執行。</span><span class="sxs-lookup"><span data-stu-id="b732e-157">Alternatively, if some elements of data require a slower API, but are not critical to initial rendering, decouple these to a separate call that is executed after critical data is rendered.</span></span>
  - <span data-ttu-id="b732e-158">如果多個組件使用相同的資料，請利用共用資料層來避免重複呼叫。</span><span class="sxs-lookup"><span data-stu-id="b732e-158">If multiple parts use the same data, utilize a common data layer to avoid duplicate calls.</span></span>
- <span data-ttu-id="b732e-159">**轉譯時間**</span><span class="sxs-lookup"><span data-stu-id="b732e-159">**Rendering time**</span></span>
  - <span data-ttu-id="b732e-160">任何媒體來源 (例如影像和影片) 的大小應該調整為容器、裝置及/或網路的限制，以避免下載不必要的大型資產。</span><span class="sxs-lookup"><span data-stu-id="b732e-160">Any media sources like images and videos should be sized to the limits of the container, device and/or network to avoid downloading unnecessary large assets.</span></span> <span data-ttu-id="b732e-161">如需內容相依性的詳細資訊，請參閱[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="b732e-161">For more information about content dependencies, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="b732e-162">避免造成自動重排、複雜 CSS 規則或複雜動畫的 API 呼叫。</span><span class="sxs-lookup"><span data-stu-id="b732e-162">Avoid API calls that cause re-flow, complex CSS rules or complicated animations.</span></span> <span data-ttu-id="b732e-163">如需詳細資訊，請參閱[最小化瀏覽器自動重排](https://developers.google.com/speed/docs/insights/browser-reflow) (英文)。</span><span class="sxs-lookup"><span data-stu-id="b732e-163">For more information, see [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow).</span></span>
  - <span data-ttu-id="b732e-164">避免使用鏈結長時間執行工作。</span><span class="sxs-lookup"><span data-stu-id="b732e-164">Avoid use of chained long running tasks.</span></span> <span data-ttu-id="b732e-165">相反地，將長時間執行工作分開至個別佇列。</span><span class="sxs-lookup"><span data-stu-id="b732e-165">Instead, break long running tasks apart into separate queues.</span></span> <span data-ttu-id="b732e-166">如需詳細資訊，請參閱[最佳化 JavaScript 執行](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)。</span><span class="sxs-lookup"><span data-stu-id="b732e-166">For more information, see [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span></span>
  - <span data-ttu-id="b732e-167">為非同步轉譯媒體或視覺元件保留對應空間，以避免略過畫面格數和間斷 (也稱為 _jank_)。</span><span class="sxs-lookup"><span data-stu-id="b732e-167">Reserve corresponding space for asynchronously rendering media or visual elements to avoid skipped frames and stuttering (also known as _jank_).</span></span>
  - <span data-ttu-id="b732e-168">如果特定瀏覽器不支援轉譯中使用的功能，則載入 polyfill 或排除執行相依程式碼。</span><span class="sxs-lookup"><span data-stu-id="b732e-168">If a certain browser doesn't support a feature used in rendering, either load a polyfill or exclude running dependent code.</span></span> <span data-ttu-id="b732e-169">如果功能不重要，請以事件處理常式的形式來處理資源，以避免記憶體流失。</span><span class="sxs-lookup"><span data-stu-id="b732e-169">If the feature is not critical, dispose resources such as event handlers to avoid memory leaks.</span></span>

<span data-ttu-id="b732e-170">在您進行頁面修訂以修復效能問題之前，請記下分析結果中的頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="b732e-170">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="b732e-171">在修訂後再次執行工具，以查看新結果是否在基準標準內，並檢查新頁面的載入時間，以查看是否有改善。</span><span class="sxs-lookup"><span data-stu-id="b732e-171">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![頁面載入時間結果](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="b732e-173">頁面載入時間會因為各種因素而有所不同，例如網路負載、一天的時間及其他暫時條件。</span><span class="sxs-lookup"><span data-stu-id="b732e-173">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="b732e-174">您應該在進行變更前後測試幾次頁面載入時間，以協助您計算結果的平均值。</span><span class="sxs-lookup"><span data-stu-id="b732e-174">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b732e-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="b732e-175">Related topics</span></span>

[<span data-ttu-id="b732e-176">調整 SharePoint Online 效能</span><span class="sxs-lookup"><span data-stu-id="b732e-176">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="b732e-177">調整 Office 365 效能</span><span class="sxs-lookup"><span data-stu-id="b732e-177">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="b732e-178">SharePoint 新式體驗中的效能</span><span class="sxs-lookup"><span data-stu-id="b732e-178">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="b732e-179">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="b732e-179">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="b732e-180">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b732e-180">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)