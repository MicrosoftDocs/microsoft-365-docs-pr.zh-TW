---
title: 請使用內容搜尋網頁組件 (而非內容查詢網頁組件) 來改善 SharePoint Online 中的效能
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
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
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: 瞭解如何將內容查詢網頁元件取代 SharePoint Server 2013 和 SharePoint Online 中的內容搜尋網頁元件，以提升效能。
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688855"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="08757-103">請使用內容搜尋網頁組件 (而非內容查詢網頁組件) 來改善 SharePoint Online 中的效能</span><span class="sxs-lookup"><span data-stu-id="08757-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="08757-104">本文將說明如何在 SharePoint Server 2013 和 SharePoint Online 中，透過將內容查詢網頁組件取代為內容搜尋網頁組件的方式來提升效能。</span><span class="sxs-lookup"><span data-stu-id="08757-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="08757-105">SharePoint Server 2013 和 SharePoint Online 最強大的新功能之一就是內容搜尋網頁組件 (CSWP)。</span><span class="sxs-lookup"><span data-stu-id="08757-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="08757-106">此網頁組件能使用搜尋索引，來快速擷取顯示給使用者的結果。</span><span class="sxs-lookup"><span data-stu-id="08757-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="08757-107">請從內容查詢網頁組件 (CQWP) 改為使用內容搜尋網頁組件，以改善您使用者的效能。</span><span class="sxs-lookup"><span data-stu-id="08757-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="08757-108">改用內容搜尋網頁組件 (而非內容查詢網頁組件) 將大幅改善 SharePoint Online 上的網頁載入效能。</span><span class="sxs-lookup"><span data-stu-id="08757-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="08757-109">您需要進行一些額外的設定以取得正確的查詢結果，但這將有助於提升效能並滿足使用者。</span><span class="sxs-lookup"><span data-stu-id="08757-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="08757-110">比較改用內容搜尋網頁組件 (而非內容查詢網頁組件) 後的效能提升成果</span><span class="sxs-lookup"><span data-stu-id="08757-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="08757-111">以下範例說明當改用內容搜尋網頁組件 (而非內容查詢網頁組件) 後，您可能會體驗到的相對效能提升成果。</span><span class="sxs-lookup"><span data-stu-id="08757-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="08757-112">當網站結構複雜和查詢的內容廣泛時，這些效果的影響會更為顯著。</span><span class="sxs-lookup"><span data-stu-id="08757-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="08757-113">此範例網站具有下列特質：</span><span class="sxs-lookup"><span data-stu-id="08757-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="08757-114">8 個子網站層級。</span><span class="sxs-lookup"><span data-stu-id="08757-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="08757-115">列出使用自訂的「水果」內容類型。</span><span class="sxs-lookup"><span data-stu-id="08757-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="08757-116">網頁組件​​中的內容查詢非常廣泛，會傳回「水果」內容類型的所有項目。</span><span class="sxs-lookup"><span data-stu-id="08757-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="08757-117">此範例的 8 個網站中只使用 50 個項目。</span><span class="sxs-lookup"><span data-stu-id="08757-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="08757-118">對擁有更多內容的網站來說，這些效果會更加明顯。</span><span class="sxs-lookup"><span data-stu-id="08757-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="08757-119">以下為內容查詢網頁組件結果的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="08757-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![顯示網頁組件內容查詢的圖形](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="08757-121">請使用 Internet Explorer 中 F12 開發人員工具的 **[網路]** 索引標籤，查看回應標頭的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="08757-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="08757-122">在下方的螢幕擷取畫面中，載入此頁面時的 **SPRequestDuration** 值為 924 毫秒。</span><span class="sxs-lookup"><span data-stu-id="08757-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![顯示 924 要求期間的螢幕擷取畫面](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="08757-124">**SPRequestDuration** 代表伺服器為了準備該網頁所完成的工作量。</span><span class="sxs-lookup"><span data-stu-id="08757-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="08757-125">將「依查詢顯示內容」網頁組件切換至「依搜尋顯示內容」網頁組件能大幅減少呈現頁面所需的時間。</span><span class="sxs-lookup"><span data-stu-id="08757-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="08757-126">相比之下，擁有等量內容搜尋網頁組件的頁面，傳回相同結果數量時的 **SPRequestDuration** 值為 106 毫秒，如下方的螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="08757-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![顯示 106 要求期間的螢幕擷取畫面](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="08757-128">在 SharePoint Online 中新增內容搜尋網頁組件</span><span class="sxs-lookup"><span data-stu-id="08757-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="08757-129">新增內容搜尋網頁組件的程序與一般內容查詢網頁組件非常類似。</span><span class="sxs-lookup"><span data-stu-id="08757-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="08757-130">請參閱 [「在 SharePoint 中設定內容搜尋網頁組件」](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)中的 *「新增內容搜尋網頁組件」* ​​一節。</span><span class="sxs-lookup"><span data-stu-id="08757-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="08757-131">為您的內容搜尋網頁組件建立正確的搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="08757-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="08757-132">一旦新增內容搜尋網頁組件，您就可以縮小搜尋並傳回想要的項目。</span><span class="sxs-lookup"><span data-stu-id="08757-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="08757-133">如需如何執行此操作的詳細指示，請參閱在 [ SharePoint 中設定內容搜尋網頁組件](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)中的 *「透過設定內容搜尋網頁組件中的進階查詢來顯示內容​」* 一節。</span><span class="sxs-lookup"><span data-stu-id="08757-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="08757-134">建置查詢與測試工具</span><span class="sxs-lookup"><span data-stu-id="08757-134">Query building and testing tool</span></span>

<span data-ttu-id="08757-135">如需能建置並測試複雜查詢的工具，請參閱 Codeplex 上的[搜尋查詢工具](https://sp2013searchtool.codeplex.com/)。</span><span class="sxs-lookup"><span data-stu-id="08757-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

