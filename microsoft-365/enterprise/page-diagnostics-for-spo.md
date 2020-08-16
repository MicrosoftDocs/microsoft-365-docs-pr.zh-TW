---
title: 使用 Sharepoint Online 網頁診斷工具
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: 使用頁面診斷功能 SharePoint 工具，對照一組預先定義的效能準則來 SharePoint 分析線上新式入口網站和傳統發佈頁面。
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695613"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a><span data-ttu-id="2008b-103">針對 SharePoint 工具使用頁面診斷程式</span><span class="sxs-lookup"><span data-stu-id="2008b-103">Use the Page Diagnostics for SharePoint tool</span></span>

<span data-ttu-id="2008b-104">本文說明如何使用 **SharePoint 工具的頁面診斷** ，對照一組預先定義的效能準則來 SharePoint 分析線上現代化和傳統的網站頁面。</span><span class="sxs-lookup"><span data-stu-id="2008b-104">This article describes how to use the **Page Diagnostics for SharePoint tool** to analyze SharePoint Online modern and classic site pages against a pre-defined set of performance criteria.</span></span>

<span data-ttu-id="2008b-105">您可以為下列專案安裝 SharePoint 工具的頁面診斷程式：</span><span class="sxs-lookup"><span data-stu-id="2008b-105">The Page Diagnostics for SharePoint tool can be installed for:</span></span>

- <span data-ttu-id="2008b-106">**Microsoft edge** [ (edge 延伸) ](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)</span><span class="sxs-lookup"><span data-stu-id="2008b-106">**Microsoft Edge** [(Edge extension)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)</span></span>
- <span data-ttu-id="2008b-107">**Chrome** [ (chrome 副檔名) ](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)</span><span class="sxs-lookup"><span data-stu-id="2008b-107">**Chrome** [(Chrome extension)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)</span></span>

>[!TIP]
><span data-ttu-id="2008b-108">版本 **2.0.0** 及更新版本包含對現代頁面的支援，除了傳統的網站頁面。</span><span class="sxs-lookup"><span data-stu-id="2008b-108">Version **2.0.0** and later includes support for modern pages in addition to classic site pages.</span></span> <span data-ttu-id="2008b-109">如果您不確定所使用的工具版本，可以選取 [ **關於** ] 連結或 [省略號 ( ...] ) 以驗證您的版本。</span><span class="sxs-lookup"><span data-stu-id="2008b-109">If you are unsure which version of the tool you are using, you can select the **About** link or the ellipses (...) to verify your version.</span></span> <span data-ttu-id="2008b-110">使用工具時 **，永遠更新為最新的版本**。</span><span class="sxs-lookup"><span data-stu-id="2008b-110">**Always update to the latest version** when using the tool.</span></span>

<span data-ttu-id="2008b-111">適用於 SharePoint 的頁面診斷工具是全新 Microsoft Edge (https://www.microsoft.com/edge) 和 Chrome 瀏覽器的擴充功能，可以用來分析 SharePoint Online 新式入口網站與傳統發佈網站頁面。</span><span class="sxs-lookup"><span data-stu-id="2008b-111">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="2008b-112">此工具僅適用于線上 SharePoint，無法在 SharePoint 系統] 頁面上使用。</span><span class="sxs-lookup"><span data-stu-id="2008b-112">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="2008b-113">工具會針對每個已分析的頁面產生報表，顯示頁面如何針對預先定義的規則集執行，並在測試結果超出基線值時顯示詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2008b-113">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="2008b-114">SharePoint Online 管理員和設計者可以使用工具來疑難排解效能問題，並確保新頁面在發佈之前已經過優化。</span><span class="sxs-lookup"><span data-stu-id="2008b-114">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues and to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="2008b-115">頁面診斷工具專門設計用來分析 SharePoint 網站頁面，而不是 allitems 的系統頁面（如： *.aspx* 或 *SharePoint .aspx*）。</span><span class="sxs-lookup"><span data-stu-id="2008b-115">The Page Diagnostics tool is designed to analyze SharePoint site pages only, not system pages such as *allitems.aspx* or *sharepoint.aspx*.</span></span> <span data-ttu-id="2008b-116">如果您嘗試在系統頁面或任何其他非網站頁面上執行該工具，您將會收到錯誤訊息，建議您無法針對該類型的頁面執行該工具。</span><span class="sxs-lookup"><span data-stu-id="2008b-116">If you attempt to run the tool on a system page or any other non-site page, you will receive an error message advising that the tool cannot be run for that type of page.</span></span>

![必須在 SharePoint 頁面上執行](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

<span data-ttu-id="2008b-118">這不是工具中的錯誤，因為評估文件庫或系統頁面時沒有任何值。</span><span class="sxs-lookup"><span data-stu-id="2008b-118">This is not an error in the tool as there is no value in assessing libraries or system pages.</span></span> <span data-ttu-id="2008b-119">請流覽至 SharePoint 網站頁面以使用工具。</span><span class="sxs-lookup"><span data-stu-id="2008b-119">Please navigate to a SharePoint site page to use the tool.</span></span> <span data-ttu-id="2008b-120">如果 SharePoint 頁面上發生此錯誤，請檢查主版頁面，確定尚未移除 SharePoint metatags。</span><span class="sxs-lookup"><span data-stu-id="2008b-120">If this error occurs on a SharePoint page, please check the master page to ensure that the SharePoint metatags have not been removed.</span></span>

<span data-ttu-id="2008b-121">若要提供工具的意見反應，請選取工具右上角的省略號，然後選取 [ [提供意見](https://go.microsoft.com/fwlink/?linkid=874109)反應]。</span><span class="sxs-lookup"><span data-stu-id="2008b-121">To provide feedback about the tool, select the ellipsis at the top right corner of the tool and then select [Give feedback](https://go.microsoft.com/fwlink/?linkid=874109).</span></span>

![提供意見](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a><span data-ttu-id="2008b-123">安裝 SharePoint 工具的頁面診斷程式</span><span class="sxs-lookup"><span data-stu-id="2008b-123">Install the Page Diagnostics for SharePoint tool</span></span>

<span data-ttu-id="2008b-124">本節中的安裝程式會同時適用于 Chrome 和 Microsoft Edge 瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="2008b-124">The installation procedure in this section will work for both the Chrome and Microsoft Edge browsers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2008b-125">Microsoft 不會讀取由「SharePoint 工具」頁面診斷進行分析的資料或頁面內容，也不會捕獲任何個人資訊、網站或下載資訊。</span><span class="sxs-lookup"><span data-stu-id="2008b-125">Microsoft does not read data or page content that is analyzed by the Page Diagnostics for SharePoint tool, and we do not capture any personal information, website or download information.</span></span> <span data-ttu-id="2008b-126">由工具記錄的唯一可識別資訊是租使用者名稱、失敗的規則計數，以及執行該工具的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="2008b-126">The only identifiable information logged to Microsoft by the tool is the tenant name, counts of rules that have failed and the date and time the tool was run.</span></span> <span data-ttu-id="2008b-127">Microsoft 使用此資訊來更深入瞭解新式入口網站，併發布網站使用量趨勢和常見效能問題。</span><span class="sxs-lookup"><span data-stu-id="2008b-127">This information is used by Microsoft to better understand modern portal and publishing site usage trends and common performance issues.</span></span>

1. <span data-ttu-id="2008b-128">針對適用于 **Microsoft Edge** [ (Edge 擴充 ](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) 的 SharePoint 工具安裝頁面診斷，) 或 **chrome** [ (chrome 副檔名) ](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)。</span><span class="sxs-lookup"><span data-stu-id="2008b-128">Install the Page Diagnostics for SharePoint tool for **Microsoft Edge** [(Edge extension)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) or **Chrome** [(Chrome extension)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi).</span></span> <span data-ttu-id="2008b-129">請查看存放區中「描述」頁面上提供的使用者隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="2008b-129">Please review the User Privacy Policy provided on the description page in the store.</span></span> <span data-ttu-id="2008b-130">在您的瀏覽器中新增工具時，您會看到下列許可權通知。</span><span class="sxs-lookup"><span data-stu-id="2008b-130">When adding the tool to your browser, you will see the following permissions notice.</span></span>

    ![副檔名許可權](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    <span data-ttu-id="2008b-132">因為頁面上可能包含來自 SharePoint 以外之位置的內容，視頁面上的網頁元件及自訂專案而定，所以已存在此通知。</span><span class="sxs-lookup"><span data-stu-id="2008b-132">This notice is in place because a page may contain content from locations outside of SharePoint depending on the web parts and customizations on the page.</span></span> <span data-ttu-id="2008b-133">這表示，當您按一下 [開始] 按鈕時，此工具會讀取要求和回應，而且只適用于執行工具所在的使用中 SharePoint] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2008b-133">This means that the tool will read the requests and responses when the start button is clicked and only for the active SharePoint tab where the tool is running.</span></span> <span data-ttu-id="2008b-134">此資訊是透過網頁瀏覽器在本機捕獲，可透過您透過工具的 [_網路追蹤_] 索引標籤中的 [**匯出至 JSON** ] 或 [**匯出至 HAR** ] 按鈕供您使用。**資訊不會傳送至 Microsoft 或由 Microsoft 所捕獲**。</span><span class="sxs-lookup"><span data-stu-id="2008b-134">This information is captured locally by the web browser and is available to you via the **Export to JSON** or **Export to HAR** button in the tool's _Network trace_ tab. **The information is not sent to or captured by Microsoft.**</span></span> <span data-ttu-id="2008b-135"> (此工具會尊重您在 [這裡](https://go.microsoft.com/fwlink/p/?linkid=857875)存取的 Microsoft 隱私權原則。 ) </span><span class="sxs-lookup"><span data-stu-id="2008b-135">(The tool respects the Microsoft privacy policy accessible [here](https://go.microsoft.com/fwlink/p/?linkid=857875).)</span></span>

    <span data-ttu-id="2008b-136">「 _管理您的下載_ 」許可權涵蓋如何使用此工具的 **匯出至 JSON** 功能。</span><span class="sxs-lookup"><span data-stu-id="2008b-136">The _Manage your downloads_ permission covers use of the tool's **Export to JSON** functionality.</span></span> <span data-ttu-id="2008b-137">請遵照貴公司專屬的隱私權指導方針，在組織外共用 JSON 檔案，因為結果包含 URLs，而且可以分類為 PII (個人身分識別資訊) 。</span><span class="sxs-lookup"><span data-stu-id="2008b-137">Please follow your company's own privacy guidelines before sharing the JSON file outside of your organization, as the results contain URLs and that can be classified as PII (Personally Identifiable Information).</span></span>
1. <span data-ttu-id="2008b-138">如果您想要在 Incognito 或 InPrivate 模式中使用工具，請遵循瀏覽器的程式：</span><span class="sxs-lookup"><span data-stu-id="2008b-138">If you want to use the tool in Incognito or InPrivate mode, follow the procedure for your browser:</span></span>
    1. <span data-ttu-id="2008b-139">在 Microsoft Edge 中，流覽至 [ **副檔名** ] 或在 URL 欄中輸入 _edge://extensions_ ，然後選取分機的 **詳細資料** 。</span><span class="sxs-lookup"><span data-stu-id="2008b-139">In Microsoft Edge, navigate to **Extensions** or type _edge://extensions_ in the URL bar and select **Details** for the extension.</span></span> <span data-ttu-id="2008b-140">在 [副檔名] 設定中，選取 [ **允許在 InPrivate**] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2008b-140">In the extension settings, select the checkbox for **allow in InPrivate**.</span></span>
    1. <span data-ttu-id="2008b-141">在 Chrome 中，流覽至 [ **副檔名** ] 或在 URL 欄中輸入 _chrome://extensions_ ，然後選取分機的 **詳細資料** 。</span><span class="sxs-lookup"><span data-stu-id="2008b-141">In Chrome, navigate to **Extensions** or type _chrome://extensions_ in the URL bar and select **Details** for the extension.</span></span> <span data-ttu-id="2008b-142">在 [副檔名] 設定中，選取 [ **允許在 Incognito 中**的滑塊]。</span><span class="sxs-lookup"><span data-stu-id="2008b-142">In the extension settings, select the slider for **allow in Incognito**.</span></span>
1. <span data-ttu-id="2008b-143">流覽至您要審閱 SharePoint Online 上的 [SharePoint 網站] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2008b-143">Navigate to the SharePoint site page on SharePoint Online that you would like to review.</span></span> <span data-ttu-id="2008b-144">我們允許對頁面上的專案進行「延遲載入」;因此，此工具不會自動停止 (這種設計是為了容納) 所有的頁面載入案例。</span><span class="sxs-lookup"><span data-stu-id="2008b-144">We have allowed for "delay loading" of items on pages; therefore, the tool will not stop automatically (this is by design to accommodate all page load scenarios).</span></span> <span data-ttu-id="2008b-145">若要停止收集，請選取 [ **停止**]。</span><span class="sxs-lookup"><span data-stu-id="2008b-145">To stop collection, select **Stop**.</span></span> <span data-ttu-id="2008b-146">在停止資料收集之前，請確定頁面載入已完成，否則您只會捕獲部分追蹤。</span><span class="sxs-lookup"><span data-stu-id="2008b-146">Make sure that the page load has completed before you stop data collection or you will only capture a partial trace.</span></span>
1. <span data-ttu-id="2008b-147">按一下分機的工具列按鈕</span><span class="sxs-lookup"><span data-stu-id="2008b-147">Click on the extension's toolbar button</span></span> ![SharePoint 標誌的頁面診斷](../media/page-diagnostics-for-spo/pagediag-icon32.png) <span data-ttu-id="2008b-149">若要載入工具，將會出現下列副檔名快顯功能表視窗：</span><span class="sxs-lookup"><span data-stu-id="2008b-149">to load the tool and you will be presented with the following extension popup window:</span></span>

    ![頁面診斷工具快顯功能表](../media/page-diagnostics-for-spo/pagediag-Landing.png)

<span data-ttu-id="2008b-151">選取 [ **開始** ] 以開始收集資料以供分析。</span><span class="sxs-lookup"><span data-stu-id="2008b-151">Select **Start** to begin collecting data for analysis.</span></span>

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a><span data-ttu-id="2008b-152">您會在 SharePoint 工具的頁面診斷資訊中看到的內容</span><span class="sxs-lookup"><span data-stu-id="2008b-152">What you'll see in the Page Diagnostics for SharePoint tool</span></span>

1. <span data-ttu-id="2008b-153">按一下工具右上角的 [省略號 ( ... ) ，以尋找下列連結：</span><span class="sxs-lookup"><span data-stu-id="2008b-153">Click the ellipses (...) in the top right corner of the tool to find the following links:</span></span>
   1. <span data-ttu-id="2008b-154">[ **其他資源** ] 連結提供有關工具的一般指導及詳細資訊，包括傳回本文的連結。</span><span class="sxs-lookup"><span data-stu-id="2008b-154">The **Additional resources** link provides general guidance and details regarding the tool including a link back to this article.</span></span>
   1. <span data-ttu-id="2008b-155">[ **提供意見** 反應] 連結可提供 _SharePoint 網站與共同作業使用者語音_ 網站的連結。</span><span class="sxs-lookup"><span data-stu-id="2008b-155">The **Give feedback** link provides a link to the _SharePoint Sites and Collaboration User Voice_ site.</span></span>
   1. <span data-ttu-id="2008b-156">[ **關於** ] 連結包括目前已安裝的工具版本，以及該工具的協力廠商通知的直接連結。</span><span class="sxs-lookup"><span data-stu-id="2008b-156">The **About** link includes the currently installed version of the tool and a direct link to the tool's third party notice.</span></span>  
1. <span data-ttu-id="2008b-157">**相關識別碼、SPRequestDuration、SPIISLatency**、**頁面載入時間**及**URL**詳細資料都是資訊性的，可用於少數用途。</span><span class="sxs-lookup"><span data-stu-id="2008b-157">The **Correlation ID, SPRequestDuration, SPIISLatency**, **Page load time**, and **URL** details are informational and can be used for a few purposes.</span></span>

    ![頁面診斷詳細資料](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - <span data-ttu-id="2008b-159">當您使用 Microsoft 支援時， **CorrelationID**是一個重要的元素，因為它可讓使用者收集特定頁面的其他診斷資料。</span><span class="sxs-lookup"><span data-stu-id="2008b-159">**CorrelationID** is an important element when working with Microsoft Support as it allows them to gather additional diagnostic data for the specific page.</span></span>
   - <span data-ttu-id="2008b-160">**SPRequestDuration** 是 SharePoint 處理頁面所用的時間。</span><span class="sxs-lookup"><span data-stu-id="2008b-160">**SPRequestDuration** is the time taken for SharePoint to process the page.</span></span> <span data-ttu-id="2008b-161">結構化導覽、大圖像、大量 API 通話都可能會導致工期更長。</span><span class="sxs-lookup"><span data-stu-id="2008b-161">Structural navigation, large images, lots of API calls could all contribute to longer durations.</span></span>
   - <span data-ttu-id="2008b-162">**SPIISLatency** 是 SharePoint 線上開始載入頁面時所花費的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="2008b-162">**SPIISLatency** is the time in milliseconds taken for SharePoint Online begin loading the page.</span></span> <span data-ttu-id="2008b-163">此值不包含 web 應用程式回應所需的時間。</span><span class="sxs-lookup"><span data-stu-id="2008b-163">This value does not include the time taken for the web application to respond.</span></span>
   - <span data-ttu-id="2008b-164">**頁面載入時間** 是指從要求的時間到在瀏覽器中接收及呈現回應時間的頁面所記錄的總時間。</span><span class="sxs-lookup"><span data-stu-id="2008b-164">**Page load time** is the total time recorded by the page from the time of the request to the time the response was received and rendered in the browser.</span></span> <span data-ttu-id="2008b-165">這個值會受到各種因素的影響，包括網路延遲、電腦效能，以及瀏覽器載入頁面所需的時間。</span><span class="sxs-lookup"><span data-stu-id="2008b-165">This value is affected by a variety of factors including network latency, the performance of the computer and the time it takes for the browser to load the page.</span></span>
   - <span data-ttu-id="2008b-166">**頁面 URL** (統一資源定位器) 是目前頁面的網頁位址。</span><span class="sxs-lookup"><span data-stu-id="2008b-166">The **Page URL** (Uniform Resource Locator) is the web address of the current page.</span></span>

1. <span data-ttu-id="2008b-167">[ [**診斷測試**](#how-to-use-the-diagnostic-tests-tab) ] 索引標籤會以三個類別顯示分析結果。 **不需要任何動作**、 **改進機遇** 及 **必要的注意事項**。</span><span class="sxs-lookup"><span data-stu-id="2008b-167">The [**Diagnostic tests**](#how-to-use-the-diagnostic-tests-tab) tab displays the analysis results in three categories; **No action required**, **Improvement opportunities** and **Attention required**.</span></span> <span data-ttu-id="2008b-168">每個測試結果都是以下列其中一個類別中的專案表示，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="2008b-168">Each test result is represented by an item in one of these categories as described in the following table:</span></span>

    |<span data-ttu-id="2008b-169">類別</span><span class="sxs-lookup"><span data-stu-id="2008b-169">Category</span></span>  |<span data-ttu-id="2008b-170">色彩</span><span class="sxs-lookup"><span data-stu-id="2008b-170">Color</span></span>  |<span data-ttu-id="2008b-171">描述</span><span class="sxs-lookup"><span data-stu-id="2008b-171">Description</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="2008b-172">**需要注意**</span><span class="sxs-lookup"><span data-stu-id="2008b-172">**Attention required**</span></span> |<span data-ttu-id="2008b-173">紅色</span><span class="sxs-lookup"><span data-stu-id="2008b-173">Red</span></span> |<span data-ttu-id="2008b-174">測試結果會超出比較基準值，而且會影響頁面效能。</span><span class="sxs-lookup"><span data-stu-id="2008b-174">Test result falls outside the baseline value and is affecting page performance.</span></span> <span data-ttu-id="2008b-175">遵循修復指導方針。</span><span class="sxs-lookup"><span data-stu-id="2008b-175">Follow remediation guidance.</span></span>|
    |<span data-ttu-id="2008b-176">**改進機會**</span><span class="sxs-lookup"><span data-stu-id="2008b-176">**Improvement opportunities**</span></span> |<span data-ttu-id="2008b-177">黃色</span><span class="sxs-lookup"><span data-stu-id="2008b-177">Yellow</span></span> |<span data-ttu-id="2008b-178">測試結果會超出基準值，而且可能會影響效能問題。</span><span class="sxs-lookup"><span data-stu-id="2008b-178">Test result falls outside the baseline value and could be contributing to performance issues.</span></span> <span data-ttu-id="2008b-179">可能會套用特定測試準則。</span><span class="sxs-lookup"><span data-stu-id="2008b-179">Test-specific criteria may apply.</span></span>|
    |<span data-ttu-id="2008b-180">**不需要採取任何動作**</span><span class="sxs-lookup"><span data-stu-id="2008b-180">**No action required**</span></span> |<span data-ttu-id="2008b-181">綠色</span><span class="sxs-lookup"><span data-stu-id="2008b-181">Green</span></span> |<span data-ttu-id="2008b-182">測試結果介於測試的比較基準值內。</span><span class="sxs-lookup"><span data-stu-id="2008b-182">Test result falls within the test's baseline value.</span></span>|

    ![頁面診斷](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. <span data-ttu-id="2008b-184">[ [**網路追蹤**](#how-to-use-the-network-trace-tab) ] 索引標籤提供頁面組建要求和回應的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2008b-184">A [**Network trace**](#how-to-use-the-network-trace-tab) tab provides details about page build requests and responses.</span></span>

## <a name="how-to-use-the-diagnostic-tests-tab"></a><span data-ttu-id="2008b-185">如何使用 [診斷測試] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="2008b-185">How to use the Diagnostic tests tab</span></span>

<span data-ttu-id="2008b-186">當您使用 SharePoint 工具的頁面診斷來分析 SharePoint 新式入口網站頁面或傳統發佈網站頁面時，會使用預先定義的規則來分析結果，以比較比較基準值和顯示在 [ **診斷測試** ] 索引標籤中的結果。某些測試的規則可能會針對新式入口網站和傳統發佈網站使用不同的比較基準值，具體取決於兩者之間的特定效能</span><span class="sxs-lookup"><span data-stu-id="2008b-186">When you analyze a SharePoint modern portal page or classic publishing site page with the Page Diagnostics for SharePoint tool, results are analyzed using pre-defined rules that compare results against baseline values and displayed in the **Diagnostic tests** tab. Rules for certain tests may use different baseline values for modern portal and classic publishing sites depending on how specific performance characteristics differ between the two.</span></span>

<span data-ttu-id="2008b-187">出現在 [增加 **機會** ] 或 [ **注意事項** ] 類別中的測試結果指出應該針對建議的做法評審的區域，並可供選取以顯示結果的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="2008b-187">Test results that appear in the **Improvement opportunities** or **Attention required** categories indicate areas that should be reviewed against recommended practices, and can be selected to display additional information about the result.</span></span> <span data-ttu-id="2008b-188">每個專案的詳細資料包括「 _深入瞭解_ 」連結，它會直接向您傳送與測試相關的適當指導方針。</span><span class="sxs-lookup"><span data-stu-id="2008b-188">Details for each item include a _Learn more_ link which will take you directly to the appropriate guidance related to the test.</span></span> <span data-ttu-id="2008b-189">[ **無必要動作** ] 類別中顯示的測試結果表示符合相關的規則，且選取時不會顯示其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2008b-189">Test results that appear in the **No action required** category indicate compliance with the relevant rule and do not display additional details when selected.</span></span>

<span data-ttu-id="2008b-190">[診斷測試] 索引標籤中的資訊不會告訴您如何設計頁面，但是會強調可能影響頁面效能的因素。</span><span class="sxs-lookup"><span data-stu-id="2008b-190">The information in the Diagnostics tests tab will not tell you how to design pages, but will highlight factors that may impact page performance.</span></span> <span data-ttu-id="2008b-191">某些頁面功能和自訂對頁面效能的影響不可避免，應檢查是否有潛在的修復，或在其影響很大時省略頁面。</span><span class="sxs-lookup"><span data-stu-id="2008b-191">Some page functionality and customizations have an unavoidable impact on page performance, and should be reviewed for potential remediation or omission from the page if their impact is substantial.</span></span>

<span data-ttu-id="2008b-192">紅色或黃色結果也可能表示重新整理資料的網頁元件過於頻繁。</span><span class="sxs-lookup"><span data-stu-id="2008b-192">Red or yellow results may also indicate web parts that refresh data too frequently.</span></span> <span data-ttu-id="2008b-193">例如，公司新聞並非每秒都會更新，但是自訂網頁元件通常是用來每秒提取最新的新聞，而不是執行可改善整體使用者體驗的快取元素。</span><span class="sxs-lookup"><span data-stu-id="2008b-193">For example, corporate news is not updated every second but custom web parts are often built to fetch the latest news every second instead of implementing caching elements that could improve the overall user experience.</span></span> <span data-ttu-id="2008b-194">在頁面上加入網頁元件時，請務必注意，如果是透過評估每個可用參數的值來降低其效能影響，以確保針對其預定用途進行適當設定，請務必注意。</span><span class="sxs-lookup"><span data-stu-id="2008b-194">Keep in mind when including web parts on a page that there are often simple ways to reduce their performance impact by evaluating the value of each available parameter to ensure it is set appropriately for its intended purpose.</span></span>

>[!NOTE]
><span data-ttu-id="2008b-195">未啟用發佈功能的傳統小組網站無法使用 Cdn。</span><span class="sxs-lookup"><span data-stu-id="2008b-195">Classic team sites that don't have the publishing feature enabled cannot make use of CDNs.</span></span> <span data-ttu-id="2008b-196">當您在這些網站上執行工具時，CDN 測試預期會失敗而且可以忽略，但其餘的測試皆適用。</span><span class="sxs-lookup"><span data-stu-id="2008b-196">When you run the tool on these sites, the CDN test is expected to fail and can be ignored, but all of the remaining tests are applicable.</span></span> <span data-ttu-id="2008b-197">SharePoint 發佈功能的其他功能可增加頁面載入時間，所以不應該只為允許啟用 CDN 功能。</span><span class="sxs-lookup"><span data-stu-id="2008b-197">The additional functionality of the SharePoint publishing feature can increase page load times, so it should not be enabled just to allow CDN functionality.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2008b-198">已定期新增及更新測試規則因此，請參閱最新版的工具，以取得目前的規則及測試結果中所含特定資訊的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2008b-198">Test rules are added and updated regularly so please refer to the latest version of the tool for details about current rules and specific information included in test results.</span></span> <span data-ttu-id="2008b-199">您可以透過管理您的分機來驗證版本，而且分機將會告知是否有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="2008b-199">You can verify the version by managing your extensions and the extension will advise whether an update is available.</span></span>

## <a name="how-to-use-the-network-trace-tab"></a><span data-ttu-id="2008b-200">如何使用 [網路追蹤] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="2008b-200">How to use the Network Trace tab</span></span>

<span data-ttu-id="2008b-201">[ **網路追蹤** ] 索引標籤提供兩個要求的詳細資訊，用以建立頁面及從 SharePoint 收到的回應。</span><span class="sxs-lookup"><span data-stu-id="2008b-201">The **Network Trace** tab provides detailed information about both requests to build the page and the responses received from SharePoint.</span></span>

1. <span data-ttu-id="2008b-202">**尋找標記為紅色的專案載入時間**。</span><span class="sxs-lookup"><span data-stu-id="2008b-202">**Look for item load times flagged as red**.</span></span> <span data-ttu-id="2008b-203">每個要求和回應都是以色彩編碼，以指出其對整體頁面效能的影響，使用下列延遲度量值：</span><span class="sxs-lookup"><span data-stu-id="2008b-203">Each request and response is color coded to indicate its impact on overall page performance using the following latency metrics:</span></span>
    - <span data-ttu-id="2008b-204">綠色： \< 500ms</span><span class="sxs-lookup"><span data-stu-id="2008b-204">Green: \< 500ms</span></span>
    - <span data-ttu-id="2008b-205">黃色： 500-1000ms</span><span class="sxs-lookup"><span data-stu-id="2008b-205">Yellow: 500-1000ms</span></span>
    - <span data-ttu-id="2008b-206">紅色： \> 1000ms</span><span class="sxs-lookup"><span data-stu-id="2008b-206">Red: \> 1000ms</span></span>

    ![網路追蹤](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    <span data-ttu-id="2008b-208">在上面顯示的圖像中，紅色專案與預設頁面有關。</span><span class="sxs-lookup"><span data-stu-id="2008b-208">In the image shown above, the red item pertains to the default page.</span></span> <span data-ttu-id="2008b-209">除非1000ms 中載入的頁面 \< (小於1秒的) ，否則它永遠會顯示紅色。</span><span class="sxs-lookup"><span data-stu-id="2008b-209">It will always show red unless the page loads in \< 1000ms (less than 1 second).</span></span>

2. <span data-ttu-id="2008b-210">**測試專案載入時間**。</span><span class="sxs-lookup"><span data-stu-id="2008b-210">**Test item load times**.</span></span> <span data-ttu-id="2008b-211">在某些情況下，由於瀏覽器已經快取這些專案，因此不會有任何時間或色彩指示器。</span><span class="sxs-lookup"><span data-stu-id="2008b-211">In some cases there will be no time or color indicator because the items have already been cached by the browser.</span></span> <span data-ttu-id="2008b-212">若要正確地進行此項測試，請開啟頁面，清除瀏覽器快取，然後按一下 [ **啟動** ]，將會強制 "冷" 頁面載入，並成為初始頁面載入的實際反映。</span><span class="sxs-lookup"><span data-stu-id="2008b-212">To test this correctly, open the page, clear browser cache, and then click **Start** as that will force a "cold" page load and be a true reflection of the initial page load.</span></span> <span data-ttu-id="2008b-213">這樣一來，就應該將它與「暖色」頁面負載進行比較，以協助判斷頁面上快取哪些專案。</span><span class="sxs-lookup"><span data-stu-id="2008b-213">This should then be compared to the "warm" page load as that will also help determine what items are being cached on the page.</span></span>

3. <span data-ttu-id="2008b-214">**與其他可協助調查問題的相關詳細資訊共用**。</span><span class="sxs-lookup"><span data-stu-id="2008b-214">**Share relevant details with others who can help investigate issues**.</span></span> <span data-ttu-id="2008b-215">若要與您的開發人員或技術支援人員共用工具中所提供的詳細資料或資訊，請按一下 [ **匯出至 JSON** (]，如) 上的圖像中所示。</span><span class="sxs-lookup"><span data-stu-id="2008b-215">To share the details or information provided in the tool with your developers or a technical support person, click **Export to JSON** (as shown in the image above).</span></span> <span data-ttu-id="2008b-216">這可讓您透過 JSON 檔案檢視器來下載結果。</span><span class="sxs-lookup"><span data-stu-id="2008b-216">That will enable you to download the results, viewable with a JSON file viewer.</span></span>

    <span data-ttu-id="2008b-217">如果您選擇使用預覽功能 [ *啟用匯出至 har* ]，則匯出類型會顯示為 [ **匯出至 har**]。</span><span class="sxs-lookup"><span data-stu-id="2008b-217">If you have opted to use the preview feature *enable Export to HAR* then the export type will show as **Export to HAR**.</span></span>

    ![網路追蹤](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> <span data-ttu-id="2008b-219">這些結果包含 URLs，而且可以分類為 PII (個人身分識別資訊) 。</span><span class="sxs-lookup"><span data-stu-id="2008b-219">These results contain URLs and that can be classified as PII (Personally Identifiable Information).</span></span> <span data-ttu-id="2008b-220">在發佈該資訊之前，請務必遵循組織的指導方針。</span><span class="sxs-lookup"><span data-stu-id="2008b-220">Make sure to follow your organization's guidelines before distributing that information.</span></span>

## <a name="engaging-with-microsoft-support"></a><span data-ttu-id="2008b-221">與 Microsoft 支援人員接洽</span><span class="sxs-lookup"><span data-stu-id="2008b-221">Engaging with Microsoft Support</span></span>

<span data-ttu-id="2008b-222">我們已包含 **Microsoft 支援層級功能** ，只應在直接使用支援案例時使用。</span><span class="sxs-lookup"><span data-stu-id="2008b-222">We have included a **Microsoft Support level feature** that should only be utilized when working directly on a support case.</span></span> <span data-ttu-id="2008b-223">使用此功能時，不需要支援小組合作，也不會對您提供任何好處，而且可使頁面執行速度大幅減慢。</span><span class="sxs-lookup"><span data-stu-id="2008b-223">Utilizing this feature will provide no benefit to you when used without support team engagement, and can make the page perform significantly slower.</span></span> <span data-ttu-id="2008b-224">在工具中使用此功能時，不需要額外的資訊，因為會將額外資訊新增至服務中的記錄。</span><span class="sxs-lookup"><span data-stu-id="2008b-224">There is no additional information when using this feature in the tool as the additional information is added to the logging in the service.</span></span>

<span data-ttu-id="2008b-225">不會顯示任何變更，只是因為您將會收到您的通知，您會收到您的通知，而您的頁面效能將會隨著2-3 倍于啟用的速度而大幅降低。</span><span class="sxs-lookup"><span data-stu-id="2008b-225">No change is visible except that you will be notified that you have enabled it and your page performance will be significantly degraded by 2-3 times slower performance whilst enabled.</span></span> <span data-ttu-id="2008b-226">它只會與特定頁面及該作用中的會話相關。</span><span class="sxs-lookup"><span data-stu-id="2008b-226">It will only be relevant for the particular page and that active session.</span></span> <span data-ttu-id="2008b-227">基於這個理由，應慎用此方式，僅在主動與支援時使用。</span><span class="sxs-lookup"><span data-stu-id="2008b-227">For this reason, this should be used sparingly and only when actively engaged with support.</span></span>

### <a name="to-enable-the-microsoft-support-level-feature"></a><span data-ttu-id="2008b-228">啟用 Microsoft 支援層級功能</span><span class="sxs-lookup"><span data-stu-id="2008b-228">To enable the Microsoft Support level feature</span></span>

1. <span data-ttu-id="2008b-229">開啟 SharePoint 工具的頁面診斷程式。</span><span class="sxs-lookup"><span data-stu-id="2008b-229">Open the Page Diagnostics for SharePoint tool.</span></span>
2. <span data-ttu-id="2008b-230">在鍵盤上按下 **ALT 鍵-L**。</span><span class="sxs-lookup"><span data-stu-id="2008b-230">On your keyboard, press **ALT-Shift-L**.</span></span> <span data-ttu-id="2008b-231">這會顯示 [ **啟用支援記錄** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2008b-231">This will display the **Enable support logging** check box.</span></span>
3. <span data-ttu-id="2008b-232">選取核取方塊，然後按一下 [ **開始** ] 以重新載入頁面並產生詳細記錄。</span><span class="sxs-lookup"><span data-stu-id="2008b-232">Select the check box, and then click **Start** to reload the page and generate verbose logging.</span></span>

    ![啟用支援選項](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    <span data-ttu-id="2008b-234">您應記下 (顯示在) 工具上方的 CorrelationID，並將其提供給支援代表，讓他們可以收集有關診斷會話的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="2008b-234">You should note the CorrelationID (displayed at the top of the tool) and provide it to your support representative to enable them to gather additional information about the diagnostic session.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2008b-235">相關主題</span><span class="sxs-lookup"><span data-stu-id="2008b-235">Related topics</span></span>

[<span data-ttu-id="2008b-236">調整 SharePoint Online 效能</span><span class="sxs-lookup"><span data-stu-id="2008b-236">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="2008b-237">調整 Office 365 效能</span><span class="sxs-lookup"><span data-stu-id="2008b-237">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="2008b-238">SharePoint 新式體驗中的效能</span><span class="sxs-lookup"><span data-stu-id="2008b-238">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="2008b-239">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="2008b-239">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="2008b-240">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2008b-240">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)