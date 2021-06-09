---
title: 使用 SharePoint Online 的物件快取
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
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
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: 本文說明在 SharePoint Server 2013 內部部署和 SharePoint Online 中使用物件快取的差異。
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695629"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="042c6-103">使用 SharePoint Online 的物件快取</span><span class="sxs-lookup"><span data-stu-id="042c6-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="042c6-104">本文說明在 SharePoint Server 2013 內部部署和 SharePoint Online 中使用物件快取的差異。</span><span class="sxs-lookup"><span data-stu-id="042c6-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="042c6-105">在 SharePoint 線上部署中，依賴物件快取會有很大的負面影響。</span><span class="sxs-lookup"><span data-stu-id="042c6-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="042c6-106">任何對 SharePoint Online 中物件快取的依賴性都會降低頁面的可靠性。</span><span class="sxs-lookup"><span data-stu-id="042c6-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="042c6-107">SharePoint 線上及 SharePoint Server 2013 物件快取的運作方式</span><span class="sxs-lookup"><span data-stu-id="042c6-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="042c6-108">當以內部部署形式主控 SharePoint Server 2013 時，客戶就擁有主控物件快取的私人前端網頁伺服器。</span><span class="sxs-lookup"><span data-stu-id="042c6-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="042c6-109">這表示快取專用於一個客戶，而且只受限於可使用的記憶體量並指派給物件快取。</span><span class="sxs-lookup"><span data-stu-id="042c6-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="042c6-110">因為內部部署案例只會提供一位客戶，所以前端網頁伺服器通常會讓使用者在相同的網站之間進行要求。</span><span class="sxs-lookup"><span data-stu-id="042c6-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="042c6-111">這表示快取已滿，而且仍然保留所有的清單查詢結果，以及您的使用者定期要求的 SharePoint 物件。</span><span class="sxs-lookup"><span data-stu-id="042c6-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![顯示到內部部署前端網頁伺服器的流量和負載](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="042c6-113">因此，當使用者第二次造訪頁面時，頁面載入時間會有所改善。</span><span class="sxs-lookup"><span data-stu-id="042c6-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="042c6-114">在至少四次載入相同頁面後，頁面會在所有前端網頁伺服器上快取。</span><span class="sxs-lookup"><span data-stu-id="042c6-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="042c6-115">相反地，在 SharePoint Online 中還有許多伺服器，還有許多網站。</span><span class="sxs-lookup"><span data-stu-id="042c6-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="042c6-116">每一位使用者可能會連接到未填入快取的不同前端網頁伺服器。</span><span class="sxs-lookup"><span data-stu-id="042c6-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="042c6-117">或者，也可能是針對伺服器填入快取，但該前端網頁伺服器的下一位使用者要求來自不同網站的頁面。</span><span class="sxs-lookup"><span data-stu-id="042c6-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="042c6-118">或者，即使下一個使用者要求相同頁面（如先前就診所要求），但其快取會在其快取中沒有該頁面的不同前端網頁伺服器上進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="042c6-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="042c6-119">在此情況下，快取根本不會協助使用者。</span><span class="sxs-lookup"><span data-stu-id="042c6-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="042c6-120">在下圖中，每個點都代表使用者要求的頁面及快取的位置。</span><span class="sxs-lookup"><span data-stu-id="042c6-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="042c6-121">不同的色彩代表不同的客戶，以共同使用 SaaS 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="042c6-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![顯示 SharePoint Online 中的物件快取結果](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="042c6-123">如您在圖表中所看到的，任何指定的使用者只要伺服器使用其快取版本的頁面，都是超薄的機會。</span><span class="sxs-lookup"><span data-stu-id="042c6-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="042c6-124">此外，由於較大的輸送量，而且伺服器在許多網站間共用，所以快取不會持續很長的時間，因為可供快取使用的空間。</span><span class="sxs-lookup"><span data-stu-id="042c6-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="042c6-125">針對上述所有原因，使用取得快取物件的使用者，並不是確保線上 SharePoint 中的品質使用者經驗和頁面載入時間的有效方式。</span><span class="sxs-lookup"><span data-stu-id="042c6-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="042c6-126">如果無法依賴物件快取以提升 SharePoint 線上的效能，我們會改用什麼？</span><span class="sxs-lookup"><span data-stu-id="042c6-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="042c6-127">由於您不應該在 SharePoint Online 中依賴快取，因此應該評估使用物件快取的 SharePoint 自訂的替代設計方法。</span><span class="sxs-lookup"><span data-stu-id="042c6-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="042c6-128">這表示使用效能問題的方法，而不依靠物件快取來為使用者產生良好的結果。</span><span class="sxs-lookup"><span data-stu-id="042c6-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="042c6-129">這會在此系列的部分其他文章中說明，包含：</span><span class="sxs-lookup"><span data-stu-id="042c6-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="042c6-130">SharePoint Online 的瀏覽選項</span><span class="sxs-lookup"><span data-stu-id="042c6-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="042c6-131">SharePoint Online 中的縮製和統合</span><span class="sxs-lookup"><span data-stu-id="042c6-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="042c6-132">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="042c6-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="042c6-133">在 SharePoint Online 中延遲載入圖片與 JavaScript</span><span class="sxs-lookup"><span data-stu-id="042c6-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

