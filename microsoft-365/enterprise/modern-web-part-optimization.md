---
title: 在 SharePoint Online 新式網站頁面中最佳化網頁組件效能
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
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: 瞭解如何使用頁面診斷，在 SharePoint 線上新式網站頁面中優化網頁元件的效能。
ms.openlocfilehash: 7dcfcbfe033ef5f4257cc9688b61aca3227ade8b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688544"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="823e1-103">在 SharePoint Online 新式網站頁面中最佳化網頁組件效能</span><span class="sxs-lookup"><span data-stu-id="823e1-103">Optimize web part performance in SharePoint Online modern site pages</span></span>

<span data-ttu-id="823e1-104">SharePoint Online 新式網站頁面包含網頁組件，對整體頁面載入時間有影響。</span><span class="sxs-lookup"><span data-stu-id="823e1-104">SharePoint Online modern site pages contain web parts that can contribute to overall page load times.</span></span> <span data-ttu-id="823e1-105">本文可協助您了解如何判斷頁面中的網頁組件如何影響使用者察覺延遲，以及如何修復常見問題。</span><span class="sxs-lookup"><span data-stu-id="823e1-105">This article will help you understand how to determine how web parts in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="823e1-106">如需有關 SharePoint Online 新式入口網站效能的詳細資訊，請參閱 [SharePoint 新式體驗中的效能](https://docs.microsoft.com/sharepoint/modern-experience-performance)。</span><span class="sxs-lookup"><span data-stu-id="823e1-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a><span data-ttu-id="823e1-107">使用「適用於 SharePoint 的頁面診斷」工具來分析網頁組件</span><span class="sxs-lookup"><span data-stu-id="823e1-107">Use the Page Diagnostics for SharePoint tool to analyze web parts</span></span>

<span data-ttu-id="823e1-108">適用於 SharePoint 的頁面診斷工具是全新 Microsoft Edge (https://www.microsoft.com/edge) 和 Chrome 瀏覽器的擴充功能，可以用來分析 SharePoint Online 新式入口網站與傳統發佈網站頁面。</span><span class="sxs-lookup"><span data-stu-id="823e1-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="823e1-109">該工具會針對每個分析頁面提供一份報告，顯示頁面如何針對定義的效能準則組執行。</span><span class="sxs-lookup"><span data-stu-id="823e1-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="823e1-110">若要安裝及了解「適用於 SharePoint 的頁面診斷」工具，請造訪[使用適用於 SharePoint Online 的頁面診斷工具](page-diagnostics-for-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="823e1-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="823e1-111">網頁診斷工具只能用於 SharePoint Online，且無法在 SharePoint 系統頁面使用。</span><span class="sxs-lookup"><span data-stu-id="823e1-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="823e1-112">當您使用「適用於 SharePoint 的頁面診斷」工具分析 SharePoint 網站頁面時，您可以在 [診斷測試]__ 窗格的 [網頁組件影響頁面載入時間]\*\*\*\* 結果中，看到超過基準計量的網頁組件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="823e1-112">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts that exceed the baseline metric in the **Web parts are impacting page load time** result in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="823e1-113">可能的結果包括：</span><span class="sxs-lookup"><span data-stu-id="823e1-113">Possible results include:</span></span>

- <span data-ttu-id="823e1-114">**需要注意** (紅色)：任何在檢視區 (頁面首先載入的畫面可見部分) 顯示的_自訂_網頁組件，載入會耗時超過**兩**秒。</span><span class="sxs-lookup"><span data-stu-id="823e1-114">**Attention required** (red): Any _custom_ web part that is visible in the viewport (screen visible portion of the page which is loaded first) that takes longer than **two** seconds to load.</span></span> <span data-ttu-id="823e1-115">任何檢視區之外的_自訂_網路組建，載入會耗時超過**四**秒。</span><span class="sxs-lookup"><span data-stu-id="823e1-115">Any _custom_ web parts outside of the viewport that take longer than **four** seconds to load.</span></span> <span data-ttu-id="823e1-116">總計載入時間會顯示在測試結果中，且會依據模組載入、消極式載入、初始、轉譯來細分。</span><span class="sxs-lookup"><span data-stu-id="823e1-116">Total load time is displayed in test results and is broken down by module load, lazy load, init and render.</span></span>
- <span data-ttu-id="823e1-117">**改善機會** (黃色)：可能會影響頁面載入時間的項目會顯示在此區段，應該加以檢閱及監控。</span><span class="sxs-lookup"><span data-stu-id="823e1-117">**Improvement opportunities** (yellow): Items that may be impacting page load time are shown in this section and should be reviewed and monitored.</span></span> <span data-ttu-id="823e1-118">包含「現成 (OOTB)」Microsoft 網頁組件。</span><span class="sxs-lookup"><span data-stu-id="823e1-118">This may include "out of the box" (OOTB) Microsoft web parts.</span></span> <span data-ttu-id="823e1-119">此區段中顯示的任何 Microsoft 網頁組件結果，會自動向 Microsoft 報告，因此**不需要任何動作**。</span><span class="sxs-lookup"><span data-stu-id="823e1-119">Results for any Microsoft web parts shown in this section are automatically reported to Microsoft, so **no action is required**.</span></span> <span data-ttu-id="823e1-120">如果您遇到頁面效能緩慢的情形，且頁面上**所有 Microsoft 網頁組件**顯示在**改善機會**區段的結果中，您應該只記錄支援票證以進行調查。</span><span class="sxs-lookup"><span data-stu-id="823e1-120">You should only log a support ticket for investigation if you are experiencing very slow performance on the page and **all Microsoft web parts** on the page appear in the results in the **Improvement opportunities** section.</span></span> <span data-ttu-id="823e1-121">請注意，未來適用於 SharePoint 的「頁面診斷」工具更新會根據 Microsoft 網頁組件的特定組態，進一步細分結果。</span><span class="sxs-lookup"><span data-stu-id="823e1-121">Note that a future Page Diagnostics for SharePoint tool update will further break down the results based on the specific configuration of the Microsoft web part.</span></span>
- <span data-ttu-id="823e1-122">**不需要任何動作** (綠色)：沒有任何網頁組件傳回資料耗時超過**兩**秒。</span><span class="sxs-lookup"><span data-stu-id="823e1-122">**No action required** (green): No web part is taking longer than **two** seconds to return data.</span></span>

<span data-ttu-id="823e1-123">如果 [網頁組件影響頁面載入時間]\*\*\*\* 結果顯示在結果的 [需要注意]\*\*\*\* 或 [改善機會]\*\*\*\* 區段中，請按一下結果以查看哪些網頁組件導致載入緩慢的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="823e1-123">If the **Web parts are impacting page load time** result appears in either the **Attention required** or **Improvement opportunities** section of the results, click the result to see details about which web parts are loading slowly.</span></span> <span data-ttu-id="823e1-124">未來「適用於 SharePoint 的頁面診斷」工具的更新可能會包含分析規則的更新，因此請確保永遠擁有最新版本的工具。</span><span class="sxs-lookup"><span data-stu-id="823e1-124">Future updates to the Page Diagnostics for SharePoint tool may include updates to analysis rules, so please ensure you always have the latest version of the tool.</span></span>

![頁面診斷工具結果](../media/modern-portal-optimization/pagediag-web-part.png)

<span data-ttu-id="823e1-126">結果中提供的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="823e1-126">Information available in the results includes:</span></span>

- <span data-ttu-id="823e1-127">[製作者]\*\*\*\* 顯示網頁組件是自訂或 Microsoft OOTB</span><span class="sxs-lookup"><span data-stu-id="823e1-127">**Made by** shows whether the web part is custom or Microsoft OOTB</span></span>
- <span data-ttu-id="823e1-128">[名稱和識別碼]\*\*\*\* 顯示可協助您在頁面上尋找網頁組件的識別資訊</span><span class="sxs-lookup"><span data-stu-id="823e1-128">**Name and ID** shows identifying information that can help you find the web part on the page</span></span>
- <span data-ttu-id="823e1-129">[總計]\*\*\*\* 顯示網頁組件載入的時間總計</span><span class="sxs-lookup"><span data-stu-id="823e1-129">**Total** shows the total time for the web part to load</span></span>
- <span data-ttu-id="823e1-130">[模組載入]\*\*\*\* 顯示提取和載入網頁組件元件所需的時間</span><span class="sxs-lookup"><span data-stu-id="823e1-130">**Module Load** shows the time taken to fetch and load the web part components</span></span>
- <span data-ttu-id="823e1-131">[消極式載入]\*\*\*\* 顯示在頁面主要區段中未顯示網頁元件的延遲載入時間</span><span class="sxs-lookup"><span data-stu-id="823e1-131">**Lazy Load** shows the time for deferred loading of web parts not seen in the main section of the page</span></span>
- <span data-ttu-id="823e1-132">[初始]\*\*\*\* 顯示網頁元件初始化所需的時間</span><span class="sxs-lookup"><span data-stu-id="823e1-132">**Init** shows the time taken for web part initialization</span></span>
- <span data-ttu-id="823e1-133">[轉譯]\*\*\*\* 顯示網頁元件提取及轉譯結果所需的時間</span><span class="sxs-lookup"><span data-stu-id="823e1-133">**Render** shows the time taken for the web part to fetch and render results</span></span>

<span data-ttu-id="823e1-134">系統會提供此資訊，協助設計人員和開發人員對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="823e1-134">This information is provided to help designers and developers troubleshoot issues.</span></span> <span data-ttu-id="823e1-135">此資訊應提供給您的設計和開發小組。</span><span class="sxs-lookup"><span data-stu-id="823e1-135">This information should be provided to your design and development team.</span></span>

## <a name="remediate-web-part-performance-issues"></a><span data-ttu-id="823e1-136">修復網頁組件效能問題</span><span class="sxs-lookup"><span data-stu-id="823e1-136">Remediate web part performance issues</span></span>

<span data-ttu-id="823e1-137">按照本節的指導方針進行，以找出 [網頁組件影響頁面載入時間]\*\*\*\* 結果中列出的網頁組件效能問題，並加以修復。</span><span class="sxs-lookup"><span data-stu-id="823e1-137">Follow the guidance in this section to identify and remediate performance issues with web parts listed in the **Web parts are impacting page load time** results.</span></span>

<span data-ttu-id="823e1-138">網頁組件效能不佳有三種可能的原因。</span><span class="sxs-lookup"><span data-stu-id="823e1-138">There are three categories of possible causes for poor web part performance.</span></span> <span data-ttu-id="823e1-139">使用下列資訊以判斷您的案例適用的問題，並進行修復。</span><span class="sxs-lookup"><span data-stu-id="823e1-139">Use the information below to determine which issues apply to your scenario and remediate them.</span></span>

- <span data-ttu-id="823e1-140">網頁組件指令碼大小和相依性</span><span class="sxs-lookup"><span data-stu-id="823e1-140">Web part script size and dependencies</span></span>
  - <span data-ttu-id="823e1-141">最佳化初始指令碼，該指令碼會將主要行案例轉譯為_僅限檢視模式_。</span><span class="sxs-lookup"><span data-stu-id="823e1-141">Optimize the initial script that renders the mainline scenario for _view mode only_.</span></span>
  - <span data-ttu-id="823e1-142">使用 _import()_ 陳述式，移動較少使用的案例，並且編輯模式程式碼 (例如屬性窗格) 以分隔區塊。</span><span class="sxs-lookup"><span data-stu-id="823e1-142">Move the less frequent scenarios and edit mode code (like the property pane) to separate chunks using the _import()_ statement.</span></span>
  - <span data-ttu-id="823e1-143">檢閱 _package.json_ 檔案的相依性，以完全移除任何無作用程式碼。</span><span class="sxs-lookup"><span data-stu-id="823e1-143">Review dependencies of the _package.json_ file to remove any dead code completely.</span></span> <span data-ttu-id="823e1-144">將任何僅限測試/建置相依性移至 devDependencies。</span><span class="sxs-lookup"><span data-stu-id="823e1-144">Move any test/build only dependencies to devDependencies.</span></span>
  - <span data-ttu-id="823e1-145">若要下載最佳的靜態資源，需要使用 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="823e1-145">Use of the Office 365 CDN is required for optimal static resource download.</span></span> <span data-ttu-id="823e1-146">公用 CDN 來源適用於 _js/css_ 檔案。</span><span class="sxs-lookup"><span data-stu-id="823e1-146">Public CDN origins are preferable for _js/css_ files.</span></span> <span data-ttu-id="823e1-147">如需使用 Office 365 CDN 的詳細資訊，請參閱[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="823e1-147">For more information about using the Office 365 CDN, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="823e1-148">重複使用架構，例如隨附於 SharePoint 架構 (SPFx) 的 _React_ 和 _Fabric imports_。</span><span class="sxs-lookup"><span data-stu-id="823e1-148">Reuse frameworks like _React_ and _Fabric imports_ that come as part of the SharePoint Framework (SPFx).</span></span> <span data-ttu-id="823e1-149">如需詳細資訊，請參閱 [SharePoint 架構的概觀](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview) (英文)。</span><span class="sxs-lookup"><span data-stu-id="823e1-149">For more information, see [Overview of the SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span></span>
  - <span data-ttu-id="823e1-150">請確保使用最新版本的 SharePoint 架構，並且在新版本可用時升級。</span><span class="sxs-lookup"><span data-stu-id="823e1-150">Ensure that you are using the latest version of the SharePoint Framework, and upgrade to new versions as they become available.</span></span>
- <span data-ttu-id="823e1-151">資料提取/快取</span><span class="sxs-lookup"><span data-stu-id="823e1-151">Data fetching/caching</span></span>
  - <span data-ttu-id="823e1-152">如果網頁組件依賴額外伺服器呼叫，以提取資料進行顯示，請確保這些伺服器 API 是快速的及/或實作用戶端快取 (例如針對大型集合使用 _localStorage_ 或 _IndexDB_)。</span><span class="sxs-lookup"><span data-stu-id="823e1-152">If the web part relies on extra server calls to fetch data for display, ensure those server APIs are fast and/or implement client side caching (such as using _localStorage_ or _IndexDB_ for larger sets).</span></span>
  - <span data-ttu-id="823e1-153">如果需要多個呼叫來轉譯重要資料，請考量在伺服器上進行批次處理，或者將要求合併至單一呼叫的其他方法。</span><span class="sxs-lookup"><span data-stu-id="823e1-153">If multiple calls are required to render critical data, consider batching on the server or other methods of consolidating requests to a single call.</span></span>
  - <span data-ttu-id="823e1-154">或者，如果資料的某些元素需要較慢的 API，但是對於初始轉譯並不重要，請將這些項目分離為個別呼叫，在重要資料轉譯之後執行。</span><span class="sxs-lookup"><span data-stu-id="823e1-154">Alternatively, if some elements of data require a slower API, but are not critical to initial rendering, decouple these to a separate call that is executed after critical data is rendered.</span></span>
  - <span data-ttu-id="823e1-155">如果多個組件使用相同的資料，請利用共用資料層來避免重複呼叫。</span><span class="sxs-lookup"><span data-stu-id="823e1-155">If multiple parts use the same data, utilize a common data layer to avoid duplicate calls.</span></span>
- <span data-ttu-id="823e1-156">轉譯時間</span><span class="sxs-lookup"><span data-stu-id="823e1-156">Rendering time</span></span>
  - <span data-ttu-id="823e1-157">任何媒體來源 (例如影像和影片) 的大小應該調整為容器、裝置及/或網路的限制，以避免下載不必要的大型資產。</span><span class="sxs-lookup"><span data-stu-id="823e1-157">Any media sources like images and videos should be sized to the limits of the container, device and/or network to avoid downloading unnecessary large assets.</span></span> <span data-ttu-id="823e1-158">如需內容相依性的詳細資訊，請參閱[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="823e1-158">For more information about content dependencies, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="823e1-159">避免造成自動重排、複雜 CSS 規則或複雜動畫的 API 呼叫。</span><span class="sxs-lookup"><span data-stu-id="823e1-159">Avoid API calls that cause re-flow, complex CSS rules or complicated animations.</span></span> <span data-ttu-id="823e1-160">如需詳細資訊，請參閱[最小化瀏覽器自動重排](https://developers.google.com/speed/docs/insights/browser-reflow) (英文)。</span><span class="sxs-lookup"><span data-stu-id="823e1-160">For more information, see [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow).</span></span>
  - <span data-ttu-id="823e1-161">避免使用鏈結長時間執行工作。</span><span class="sxs-lookup"><span data-stu-id="823e1-161">Avoid use of chained long running tasks.</span></span> <span data-ttu-id="823e1-162">相反地，將長時間執行工作分開至個別佇列。</span><span class="sxs-lookup"><span data-stu-id="823e1-162">Instead, break long running tasks apart into separate queues.</span></span> <span data-ttu-id="823e1-163">如需詳細資訊，請參閱[最佳化 JavaScript 執行](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)。</span><span class="sxs-lookup"><span data-stu-id="823e1-163">For more information, see [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span></span>
  - <span data-ttu-id="823e1-164">為非同步轉譯媒體或視覺元件保留對應空間，以避免略過畫面格數和間斷 (也稱為 _jank_)。</span><span class="sxs-lookup"><span data-stu-id="823e1-164">Reserve corresponding space for asynchronously rendering media or visual elements to avoid skipped frames and stuttering (also known as _jank_).</span></span>
  - <span data-ttu-id="823e1-165">如果特定瀏覽器不支援轉譯中使用的功能，則載入 polyfill 或排除執行相依程式碼。</span><span class="sxs-lookup"><span data-stu-id="823e1-165">If a certain browser doesn't support a feature used in rendering, either load a polyfill or exclude running dependent code.</span></span> <span data-ttu-id="823e1-166">如果功能不重要，請以事件處理常式的形式來處理資源，以避免記憶體流失。</span><span class="sxs-lookup"><span data-stu-id="823e1-166">If the feature is not critical, dispose resources such as event handlers to avoid memory leaks.</span></span>

<span data-ttu-id="823e1-167">在您進行頁面修訂以修復效能問題之前，請記下分析結果中的頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="823e1-167">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="823e1-168">在修訂後再次執行工具，以查看新結果是否在基準標準內，並檢查新頁面的載入時間，以查看是否有改善。</span><span class="sxs-lookup"><span data-stu-id="823e1-168">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![頁面載入時間結果](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="823e1-170">頁面載入時間會因為各種因素而有所不同，例如網路負載、一天的時間及其他暫時條件。</span><span class="sxs-lookup"><span data-stu-id="823e1-170">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="823e1-171">您應該在進行變更前後測試幾次頁面載入時間，以協助您計算結果的平均值。</span><span class="sxs-lookup"><span data-stu-id="823e1-171">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="823e1-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="823e1-172">Related topics</span></span>

[<span data-ttu-id="823e1-173">調整 SharePoint Online 效能</span><span class="sxs-lookup"><span data-stu-id="823e1-173">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="823e1-174">調整 Office 365 效能</span><span class="sxs-lookup"><span data-stu-id="823e1-174">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="823e1-175">SharePoint 新式體驗中的效能</span><span class="sxs-lookup"><span data-stu-id="823e1-175">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="823e1-176">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="823e1-176">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="823e1-177">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="823e1-177">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
