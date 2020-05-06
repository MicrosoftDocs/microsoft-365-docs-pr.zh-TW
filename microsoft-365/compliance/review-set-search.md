---
title: 查詢檢視集中的資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何在評審集中建立及執行查詢，以在高級 eDiscovery 案例中組織資料，以進行更有效率的審閱。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1bf4d86ea4aecb33cbb2e7ad7b617cd58a5c086d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034597"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="e9029-103">查詢檢視集中的資料</span><span class="sxs-lookup"><span data-stu-id="e9029-103">Query the data in a review set</span></span>

<span data-ttu-id="e9029-104">在大多數情況下，可以深入查看檢查集合中的資料，並整理該資料，以促進更有效率的審閱。</span><span class="sxs-lookup"><span data-stu-id="e9029-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="e9029-105">使用審閱集中的查詢可協助您將重點放在符合您的審閱準則的檔子集。</span><span class="sxs-lookup"><span data-stu-id="e9029-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="e9029-106">在審閱集中建立及執行查詢</span><span class="sxs-lookup"><span data-stu-id="e9029-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="e9029-107">若要為審閱集內的檔建立並執行查詢，請按一下 [檢查集合] 中的 [**新增查詢**]。</span><span class="sxs-lookup"><span data-stu-id="e9029-107">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="e9029-108">在命名查詢並定義條件之後，按一下 [**儲存**] 儲存並執行查詢。</span><span class="sxs-lookup"><span data-stu-id="e9029-108">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="e9029-109">若要執行先前已儲存的查詢，請按一下已儲存的查詢。</span><span class="sxs-lookup"><span data-stu-id="e9029-109">To run a query that has been previously saved, click a saved query.</span></span>

![檢查集合查詢](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="e9029-111">建立審閱集查詢</span><span class="sxs-lookup"><span data-stu-id="e9029-111">Building a review set query</span></span>

<span data-ttu-id="e9029-112">您可以使用關鍵字條件卡中的條件卡和查詢語言組合，建立查詢。</span><span class="sxs-lookup"><span data-stu-id="e9029-112">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="e9029-113">您也可以將條件卡片組合成組塊（稱為*條件群組*），以建立更複雜的查詢。</span><span class="sxs-lookup"><span data-stu-id="e9029-113">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="e9029-114">如需您可以搜尋之中繼資料屬性的清單和描述，請參閱[Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="e9029-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="e9029-115">條件卡片</span><span class="sxs-lookup"><span data-stu-id="e9029-115">Condition cards</span></span>

<span data-ttu-id="e9029-116">每個審閱集中的可搜尋欄位都有對應的條件卡，可供您用來建立查詢。</span><span class="sxs-lookup"><span data-stu-id="e9029-116">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="e9029-117">有多種狀況卡片類型：</span><span class="sxs-lookup"><span data-stu-id="e9029-117">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="e9029-118">Freetext：透過文字欄位（例如 subject）使用 freetext 條件卡。</span><span class="sxs-lookup"><span data-stu-id="e9029-118">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="e9029-119">您可以將多個搜尋字詞以逗號分隔，以加以列出。</span><span class="sxs-lookup"><span data-stu-id="e9029-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="e9029-120">日期：日期功能卡片用於日期欄位（例如「上次修改日期」）。</span><span class="sxs-lookup"><span data-stu-id="e9029-120">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="e9029-121">搜尋選項：「搜尋選項」條件卡會為您的考核集中的特定欄位提供可能的值清單。</span><span class="sxs-lookup"><span data-stu-id="e9029-121">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="e9029-122">這適用于在您的考核集中，具有有限數目的可能值的欄位（例如寄件者）。</span><span class="sxs-lookup"><span data-stu-id="e9029-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="e9029-123">關鍵字：關鍵字條件卡片是 freetext 條件卡的特定實例，可供您用來搜尋字詞，或使用 KQL 類似的查詢語言。</span><span class="sxs-lookup"><span data-stu-id="e9029-123">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="e9029-124">如需詳細資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="e9029-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="e9029-125">查詢語言</span><span class="sxs-lookup"><span data-stu-id="e9029-125">Query language</span></span>

<span data-ttu-id="e9029-126">除了條件卡片之外，您還可以使用關鍵字智慧卡中的類似 KQL 的查詢語言來建立您的查詢。</span><span class="sxs-lookup"><span data-stu-id="e9029-126">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="e9029-127">「檢查的複查集」查詢語言支援標準 Boolean 運算子，例如**and**、 **OR**、 **NOT**和**NEAR**。</span><span class="sxs-lookup"><span data-stu-id="e9029-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="e9029-128">它也支援單一字元萬用字元（？）和多字元萬用字元（\*）。</span><span class="sxs-lookup"><span data-stu-id="e9029-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="e9029-129">使用篩選</span><span class="sxs-lookup"><span data-stu-id="e9029-129">Using filters</span></span>

<span data-ttu-id="e9029-130">除了您可以儲存的查詢之外，您還可以使用「複查集」篩選，將其他條件快速套用至審閱集查詢。</span><span class="sxs-lookup"><span data-stu-id="e9029-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="e9029-131">這可協助您進一步精煉審閱集查詢所顯示的結果。</span><span class="sxs-lookup"><span data-stu-id="e9029-131">This helps you further refine the results displayed by a review set query.</span></span>

![審閱集合篩選](../media/AeDReviewSetFilters.png)

<span data-ttu-id="e9029-133">篩選不同于查詢的兩個重要方式：</span><span class="sxs-lookup"><span data-stu-id="e9029-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="e9029-134">篩選是暫時性的。</span><span class="sxs-lookup"><span data-stu-id="e9029-134">Filters are transient.</span></span> <span data-ttu-id="e9029-135">它們不會存在於現有的會話之外。</span><span class="sxs-lookup"><span data-stu-id="e9029-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="e9029-136">換句話說，您無法儲存篩選。</span><span class="sxs-lookup"><span data-stu-id="e9029-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="e9029-137">查詢會儲存至複查集，並在開啟評審集時進行存取。</span><span class="sxs-lookup"><span data-stu-id="e9029-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="e9029-138">篩選永遠都是累加的。</span><span class="sxs-lookup"><span data-stu-id="e9029-138">Filters are always additive.</span></span> <span data-ttu-id="e9029-139">除了目前的複查集查詢之外，還會套用篩選器。</span><span class="sxs-lookup"><span data-stu-id="e9029-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="e9029-140">套用不同的查詢會取代目前查詢所傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="e9029-140">Applying a different query will replace the results returned by the current query.</span></span>
