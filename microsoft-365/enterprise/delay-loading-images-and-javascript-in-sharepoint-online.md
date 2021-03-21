---
title: 延遲載入 SharePoint Online 中的影像和 JavaScript
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
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
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: 瞭解如何使用 JavaScript 延遲載入影像和非必要 JavaScript，縮短 SharePoint 線上頁面的載入時間。
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919161"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="e7329-103">延遲載入 SharePoint Online 中的影像和 JavaScript</span><span class="sxs-lookup"><span data-stu-id="e7329-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="e7329-104">本文說明如何使用 JavaScript 延後載入影像，以及等候載入非必要的 JavaScript，直到載入頁面後，才能縮短 SharePoint 線上頁面的載入時間。</span><span class="sxs-lookup"><span data-stu-id="e7329-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="e7329-105">影像會對 SharePoint 線上的頁面載入速度產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="e7329-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="e7329-106">根據預設，在載入 HTML 頁面時，大多數新式的 Internet 瀏覽器都會預先取得映射。</span><span class="sxs-lookup"><span data-stu-id="e7329-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="e7329-107">這可能會導致頁面在螢幕上看不到，直到使用者向裡滾時，才會在螢幕上顯示。</span><span class="sxs-lookup"><span data-stu-id="e7329-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="e7329-108">影像可以封鎖瀏覽器載入頁面的可見部分。</span><span class="sxs-lookup"><span data-stu-id="e7329-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="e7329-109">若要解決此問題，您可以使用 JavaScript 先略過載入影像。</span><span class="sxs-lookup"><span data-stu-id="e7329-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="e7329-110">此外，載入非必要的 JavaScript 也可以減慢 SharePoint 頁面上的下載時間。</span><span class="sxs-lookup"><span data-stu-id="e7329-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="e7329-111">本主題說明一些方法，可讓您在線上 SharePoint 中使用 JavaScript 來改善頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="e7329-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="e7329-112">在 SharePoint 線上頁面上使用 JavaScript 延遲圖像載入，以提升頁面載入時間</span><span class="sxs-lookup"><span data-stu-id="e7329-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="e7329-113">您可以使用 JavaScript 以避免網頁瀏覽器預先提取圖像。</span><span class="sxs-lookup"><span data-stu-id="e7329-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="e7329-114">這會加快整體檔渲染的速度。</span><span class="sxs-lookup"><span data-stu-id="e7329-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="e7329-115">若要這麼做，您必須從標籤中移除 src 屬性的值 \<img\> ，並將它取代為數據屬性中的檔案路徑，例如： data-src。</span><span class="sxs-lookup"><span data-stu-id="e7329-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="e7329-116">例如：</span><span class="sxs-lookup"><span data-stu-id="e7329-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="e7329-117">使用此方法時，瀏覽器不會立即下載圖像。</span><span class="sxs-lookup"><span data-stu-id="e7329-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="e7329-118">如果此圖像已存在於視區中，JavaScript 會告訴瀏覽器從資料屬性中取得 URL，並將其插入 src 屬性值。</span><span class="sxs-lookup"><span data-stu-id="e7329-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="e7329-119">影像只會在使用者滾動時載入，而且會進入 view。</span><span class="sxs-lookup"><span data-stu-id="e7329-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="e7329-120">若要進行上述所有動作，您必須使用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="e7329-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="e7329-121">在文字檔中，定義 **isElementInViewport ()** 函數，以檢查元素是否位於使用者可以看見的瀏覽器部分。</span><span class="sxs-lookup"><span data-stu-id="e7329-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

<span data-ttu-id="e7329-122">接下來，在 **loadItemsInView ()** 函數中使用 **isElementInViewport ()** 。</span><span class="sxs-lookup"><span data-stu-id="e7329-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="e7329-123">如果資料位於使用者可以看見的瀏覽器中， **loadItemsInView ()** 函數就會載入具有資料 src 屬性值的所有影像。</span><span class="sxs-lookup"><span data-stu-id="e7329-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="e7329-124">將下列函數新增至文字檔：</span><span class="sxs-lookup"><span data-stu-id="e7329-124">Add the following function to the text file:</span></span>
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

<span data-ttu-id="e7329-125">最後，從 **loadItemsInView ()** 中，撥打 **onscroll ()** 如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="e7329-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="e7329-126">這可確保視區中的任何影像都會在使用者需要時載入，但不會在之前載入。</span><span class="sxs-lookup"><span data-stu-id="e7329-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="e7329-127">將下列專案新增至文字檔：</span><span class="sxs-lookup"><span data-stu-id="e7329-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="e7329-128">針對 SharePoint 線上，您必須在 #s4 工作區標籤上的 scroll 事件中附加下列功能 \<div\> 。</span><span class="sxs-lookup"><span data-stu-id="e7329-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="e7329-129">這是因為會覆寫視窗事件，以確保功能區保持附加在頁面頂端。</span><span class="sxs-lookup"><span data-stu-id="e7329-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="e7329-130">將文字檔儲存為副檔名為 .js 的 JavaScript 檔，例如 delayLoadImages.js。</span><span class="sxs-lookup"><span data-stu-id="e7329-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="e7329-131">delayLoadImages.js 寫入完畢後，您可以在 SharePoint 線上中將檔案的內容新增至主版頁面。</span><span class="sxs-lookup"><span data-stu-id="e7329-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="e7329-132">若要這麼做，您可以將腳本連結新增至主版頁面的頁首。</span><span class="sxs-lookup"><span data-stu-id="e7329-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="e7329-133">在主版頁面中，JavaScript 會套用至所有使用該主版頁面版面配置的 SharePoint Online 網站中的所有頁面。</span><span class="sxs-lookup"><span data-stu-id="e7329-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="e7329-134">或者，如果您只想在網站的一個頁面上使用此程式，請使用 [腳本編輯器網頁元件] 將 JavaScript 嵌入頁面中。</span><span class="sxs-lookup"><span data-stu-id="e7329-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="e7329-135">如需詳細資訊，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="e7329-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="e7329-136">操作方法：將主版頁面套用至 SharePoint 2013 的網站</span><span class="sxs-lookup"><span data-stu-id="e7329-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [<span data-ttu-id="e7329-137">操作方法：在 SharePoint 2013 中建立頁面配置</span><span class="sxs-lookup"><span data-stu-id="e7329-137">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="e7329-138">範例：從 SharePoint Online 中的主版頁面參考 JavaScript delayLoadImages.js 檔案</span><span class="sxs-lookup"><span data-stu-id="e7329-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="e7329-139">為了讓這種方式運作，您也需要在主版頁面中參照 jQuery。</span><span class="sxs-lookup"><span data-stu-id="e7329-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="e7329-140">在下列範例中，您可以在初始頁面載入時看到只載入一個影像，但是頁面上有其他數個。</span><span class="sxs-lookup"><span data-stu-id="e7329-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![顯示頁面上載入一個影像的螢幕擷取畫面](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="e7329-142">下列螢幕擷取畫面顯示在其滾到 view 之後所下載的其餘影像。</span><span class="sxs-lookup"><span data-stu-id="e7329-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![顯示頁面上載入數個影像的螢幕擷取畫面](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="e7329-144">延遲使用 JavaScript 的圖像載入可能是提升效能的有效技巧;不過，如果此技術是在公用網站上套用，則搜尋引擎無法編目影像，其方式與編目定期格式的圖像的方式相同。</span><span class="sxs-lookup"><span data-stu-id="e7329-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="e7329-145">這可能會影響搜尋引擎上的排名，因為頁面上的中繼資料在載入時並未真正存在。</span><span class="sxs-lookup"><span data-stu-id="e7329-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="e7329-146">搜尋引擎編目唯讀取 HTML，因此不會在頁面上看到影像做為內容。</span><span class="sxs-lookup"><span data-stu-id="e7329-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="e7329-147">圖像是用來在搜尋結果中排名頁面的因素之一。</span><span class="sxs-lookup"><span data-stu-id="e7329-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="e7329-148">若要解決此問題，一種方法是使用圖像的簡介文字。</span><span class="sxs-lookup"><span data-stu-id="e7329-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="e7329-149">GitHub 程式碼範例：注入 JavaScript 以提升效能</span><span class="sxs-lookup"><span data-stu-id="e7329-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="e7329-150">在 GitHub 上所提供的 [JavaScript 注入](https://go.microsoft.com/fwlink/p/?LinkId=524759) 上，請勿錯過文章和程式碼範例。</span><span class="sxs-lookup"><span data-stu-id="e7329-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7329-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7329-151">See also</span></span>

[<span data-ttu-id="e7329-152">Office 2013 和 Microsoft 365 應用程式中支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="e7329-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="e7329-153">操作方法：將主版頁面套用至 SharePoint 2013 的網站</span><span class="sxs-lookup"><span data-stu-id="e7329-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[<span data-ttu-id="e7329-154">操作方法：在 SharePoint 2013 中建立頁面配置</span><span class="sxs-lookup"><span data-stu-id="e7329-154">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)