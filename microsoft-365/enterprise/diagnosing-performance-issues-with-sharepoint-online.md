---
title: 診斷 SharePoint Online 的效能問題
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: 本文說明如何使用 Internet Explorer 開發人員工具來診斷 SharePoint Online 網站的常見問題。
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688484"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="c7d0f-103">診斷 SharePoint Online 的效能問題</span><span class="sxs-lookup"><span data-stu-id="c7d0f-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="c7d0f-104">本文說明如何使用 Internet Explorer 開發人員工具來診斷 SharePoint Online 網站的常見問題。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="c7d0f-105">您可以使用三種不同的方式，識別出 SharePoint Online 網站上的頁面對自訂產生效能問題。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="c7d0f-106">F12 工具條網路監視器</span><span class="sxs-lookup"><span data-stu-id="c7d0f-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="c7d0f-107">比較非自訂基準</span><span class="sxs-lookup"><span data-stu-id="c7d0f-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="c7d0f-108">SharePoint 線上回應標頭度量</span><span class="sxs-lookup"><span data-stu-id="c7d0f-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="c7d0f-109">本主題說明如何使用上述每一種方法來診斷效能問題。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="c7d0f-110">當您瞭解問題的原因之後，您可以使用改進 SharePoint 效能的相關文章，對解決方案進行工作 https://aka.ms/tune 。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="c7d0f-111">使用 F12 工具列在 SharePoint Online 中診斷效能</span><span class="sxs-lookup"><span data-stu-id="c7d0f-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="c7d0f-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7d0f-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7d0f-113">在本文中，我們使用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="c7d0f-114">其他瀏覽器上的 F12 開發人員工具的版本具有類似的功能，但看起來可能稍有不同。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="c7d0f-115">如需 F12 開發人員工具的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c7d0f-115">For information on the F12 developer tools, see:</span></span>
  
- [<span data-ttu-id="c7d0f-116">F12 工具的新功能</span><span class="sxs-lookup"><span data-stu-id="c7d0f-116">What's new in F12 Tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [<span data-ttu-id="c7d0f-117">使用 F12 開發人員工具</span><span class="sxs-lookup"><span data-stu-id="c7d0f-117">Using the F12 developer tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522546)

<span data-ttu-id="c7d0f-118">若要顯示開發人員工具，請按 **F12** ，然後按一下 Wi-Fi 圖示：</span><span class="sxs-lookup"><span data-stu-id="c7d0f-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![F12 開發人員工具 WIFI 圖示的螢幕擷取畫面](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="c7d0f-120">在 [ **網路** ] 索引標籤上，按綠色的 [播放] 按鈕載入頁面。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="c7d0f-121">工具會傳回瀏覽器要求的所有檔案，以便取得您要求的頁面。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="c7d0f-122">下列螢幕擷取畫面顯示一個這類清單。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-122">The following screen shot shows one such list.</span></span>
  
![使用頁面要求所傳回之檔案清單的螢幕擷取畫面。](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="c7d0f-124">您也可以在右側看到檔案的下載時間（如螢幕擷取畫面所示）。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![圖表顯示從 SharePoint 載入要求頁面所需的時間](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="c7d0f-126">這可讓您以視覺方式表示檔載入所需的時間。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="c7d0f-127">綠色線代表瀏覽器準備呈現頁面的時間。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="c7d0f-128">這可讓您快速查看可能導致網站上頁面負載變慢的不同檔案。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="c7d0f-129">設定 SharePoint 線上的非自訂基準</span><span class="sxs-lookup"><span data-stu-id="c7d0f-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="c7d0f-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7d0f-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7d0f-131">若要判斷您的網站效能薄弱點，最好的方法是在 SharePoint Online 中設定完全現成的網站集合。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="c7d0f-132">如此一來，您可以將網站的各個層面與您在頁面上沒有自訂的內容進行比較。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="c7d0f-133">商務用 OneDrive 首頁是不太可能有任何自訂之個別網站集合的好例子。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="c7d0f-134">查看 SharePoint 回應標頭資訊</span><span class="sxs-lookup"><span data-stu-id="c7d0f-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="c7d0f-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7d0f-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7d0f-136">在 SharePoint Online 中，您可以在每個檔案的回應標頭中，存取傳送回瀏覽器的資訊。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="c7d0f-137">診斷效能問題最實用的價值是 **SPRequestDuration**，它會顯示要求處理伺服器時所花費的時間量。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="c7d0f-138">這可協助判斷要求是否非常繁重和資源密集。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="c7d0f-139">這是您在伺服器上處理頁面時所能執行的工作程度最佳的洞察力。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="c7d0f-140">若要查看 SharePoint 回應標頭資訊</span><span class="sxs-lookup"><span data-stu-id="c7d0f-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="c7d0f-141">確定您已安裝 F12 工具。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="c7d0f-142">如需下載及安裝這些工具的詳細資訊，請參閱 [F12 工具的新功能](https://go.microsoft.com/fwlink/p/?LinkId=522545)。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-142">For more information on downloading and installing these tools, see [What's new in F12 tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span></span>

2. <span data-ttu-id="c7d0f-143">在 [F12 工具] 的 [ **網路** ] 索引標籤上，按綠色的 [播放] 按鈕載入頁面。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="c7d0f-144">按一下工具傳回的其中一個 .aspx 檔，然後按一下 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![顯示回應標頭的詳細資料](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="c7d0f-146">按一下 [ **回應標頭**]。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-146">Click **Response headers**.</span></span>

    ![圖表顯示回應標頭的 URL](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="c7d0f-148">線上 SharePoint 導致效能問題的原因為何？</span><span class="sxs-lookup"><span data-stu-id="c7d0f-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="c7d0f-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7d0f-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7d0f-150">[SharePoint Online 的文章導覽選項](navigation-options-for-sharepoint-online.md)顯示使用 SPRequestDuration 值的範例，以判斷複雜的結構流覽是否導致頁面在伺服器上處理很長的時間。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="c7d0f-151">在沒有自訂) 的情況下，為基準網站取值 (，可以判斷是否有任何指定的檔案需要很長的時間才能載入。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="c7d0f-152">[SharePoint Online 的導覽選項](navigation-options-for-sharepoint-online.md)中使用的範例是主 .aspx 檔案。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="c7d0f-153">該檔案包含大多數為頁面載入執行的 ASP.NET 程式碼。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="c7d0f-154">視您使用的網站範本而定，當您自訂首頁時，可能會啟動 .aspx、首頁、default.aspx 或其他名稱。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="c7d0f-155">如果此數位的數目遠遠高於您的基準網站，表示頁面上發生效能問題的情況很好。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="c7d0f-156">在您識別網站特有的問題之後，建議的方式是找出導致效能不良的原因，以消除所有可能的原因（如頁面自訂），然後再將其新增回網站一。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="c7d0f-157">當您移除頁面執行良好的足夠自訂之後，即可逐個新增特定的自訂。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="c7d0f-158">例如，如果您有非常複雜的導覽，請嘗試將導覽變更為 [不顯示子網站]，然後檢查開發人員工具，以查看是否有差異。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="c7d0f-159">或者，如果您有大量的內容試妥，請嘗試從您的頁面中移除這些內容，然後查看是否有改進。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="c7d0f-160">如果您消除所有可能的原因，並一次將其新增回一次，您可以輕鬆識別哪些功能是最大的問題，然後再向方案中取得作用。</span><span class="sxs-lookup"><span data-stu-id="c7d0f-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>
