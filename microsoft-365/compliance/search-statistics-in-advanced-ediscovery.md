---
title: 預先探索中的搜尋統計資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 查看您在 Advanced eDiscovery 中執行集合搜尋之後所產生的統計資料，以驗證搜尋結果。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750774"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="09976-103">搜尋 Advanced eDiscovery 中的統計資料</span><span class="sxs-lookup"><span data-stu-id="09976-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="09976-104">驗證搜尋結果的一種方式是查看結果的統計資料，以確保其符合您的預期。</span><span class="sxs-lookup"><span data-stu-id="09976-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="09976-105">搜尋完成時，會在 [搜尋詳細資料] 浮出控制項上顯示高層級統計資料：</span><span class="sxs-lookup"><span data-stu-id="09976-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="09976-106">搜尋所檢索的專案數目及數量</span><span class="sxs-lookup"><span data-stu-id="09976-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="09976-107">在搜尋位置中找到的部分索引或未編制索引的專案數目及數量</span><span class="sxs-lookup"><span data-stu-id="09976-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="09976-108">已搜尋的信箱和位置數目。</span><span class="sxs-lookup"><span data-stu-id="09976-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="09976-109">若要查看詳細的統計資料，請按一下 [搜尋詳細資料] 飛入中的「統計資料」。</span><span class="sxs-lookup"><span data-stu-id="09976-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="09976-110">摘要視圖</span><span class="sxs-lookup"><span data-stu-id="09976-110">Summary view</span></span>

<span data-ttu-id="09976-111">在摘要視圖中，您可以看到搜尋結果依位置類型所細分 (例如 Exchange) 。</span><span class="sxs-lookup"><span data-stu-id="09976-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="09976-112">您可以在每個位置類型上查看：</span><span class="sxs-lookup"><span data-stu-id="09976-112">For each location type, you can see:</span></span>

- <span data-ttu-id="09976-113">專案符合搜尋條件的位置數目</span><span class="sxs-lookup"><span data-stu-id="09976-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="09976-114">從這些位置符合搜尋條件的專案數</span><span class="sxs-lookup"><span data-stu-id="09976-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="09976-115">符合搜尋條件的專案總容量。</span><span class="sxs-lookup"><span data-stu-id="09976-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="09976-116">頂端位置視圖</span><span class="sxs-lookup"><span data-stu-id="09976-116">Top locations view</span></span>

<span data-ttu-id="09976-117">在 [頂端位置] 視圖中，您會看到具有最相符專案的個別位置。</span><span class="sxs-lookup"><span data-stu-id="09976-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="09976-118">針對每個位置，您會看到：</span><span class="sxs-lookup"><span data-stu-id="09976-118">For each location, you will see:</span></span>

- <span data-ttu-id="09976-119">位置名稱 (例如 SharePoint URL) </span><span class="sxs-lookup"><span data-stu-id="09976-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="09976-120">位置類型</span><span class="sxs-lookup"><span data-stu-id="09976-120">Location type</span></span>

- <span data-ttu-id="09976-121">符合搜尋條件的專案數</span><span class="sxs-lookup"><span data-stu-id="09976-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="09976-122">符合搜尋條件的專案總容量。</span><span class="sxs-lookup"><span data-stu-id="09976-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="09976-123">查詢檢視</span><span class="sxs-lookup"><span data-stu-id="09976-123">Queries view</span></span>

<span data-ttu-id="09976-124">如果您已在查詢中使用 (c:s) 關鍵字或關鍵字列，則您可以在每個位置類型的查詢檢視中查看查詢明細。</span><span class="sxs-lookup"><span data-stu-id="09976-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="09976-125">針對每個位置類型，您會看到：</span><span class="sxs-lookup"><span data-stu-id="09976-125">For each location type, you will see:</span></span>

- <span data-ttu-id="09976-126">部分：此欄會包含 "Primary" 或 "關鍵字" 一字。</span><span class="sxs-lookup"><span data-stu-id="09976-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="09976-127">"Primary" 表示列在整個查詢中呈現統計資料，而 "關鍵字" 則表示其中一個查詢元件。</span><span class="sxs-lookup"><span data-stu-id="09976-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="09976-128">查詢：列所參照的實際查詢元件。</span><span class="sxs-lookup"><span data-stu-id="09976-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="09976-129">如果 Part 是 "Primary"，這會是整個查詢;如果 Part 是 "關鍵字"，您會在這裡看到其中一個查詢元件。</span><span class="sxs-lookup"><span data-stu-id="09976-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="09976-130">當您搜尋所有的 contentin 信箱 (但未指定任何關鍵字) 時，實際的查詢 (大小 >= 0) ，這樣就會傳回所有專案。</span><span class="sxs-lookup"><span data-stu-id="09976-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="09976-131">當您搜尋 SharePoint 線上及商務用 OneDrive 網站時，會新增下列兩個元件：</span><span class="sxs-lookup"><span data-stu-id="09976-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="09976-132">不 IsExternalContent:1-排除內部部署 SharePoint 組織中的任何內容</span><span class="sxs-lookup"><span data-stu-id="09976-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="09976-133">非 isOneNotePage： 1-排除所有的 OneNote 檔案，因為這些檔案會是符合搜尋查詢的任何檔的重複專案。</span><span class="sxs-lookup"><span data-stu-id="09976-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="09976-134">專案符合搜尋條件的位置數目。</span><span class="sxs-lookup"><span data-stu-id="09976-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="09976-135">從這些位置符合搜尋條件的專案數。</span><span class="sxs-lookup"><span data-stu-id="09976-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="09976-136">符合搜尋條件的專案總容量。</span><span class="sxs-lookup"><span data-stu-id="09976-136">Total volume of items that matched the search conditions.</span></span>
