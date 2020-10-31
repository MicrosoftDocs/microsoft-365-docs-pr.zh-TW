---
title: 查詢檢視集中的資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何在評審集中建立及執行查詢，以在高級 eDiscovery 案例中組織資料，以進行更有效率的審閱。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816566"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="e5edb-103">查詢檢視集中的資料</span><span class="sxs-lookup"><span data-stu-id="e5edb-103">Query the data in a review set</span></span>

<span data-ttu-id="e5edb-104">在大多數情況下，可以深入查看檢查集合中的資料，並整理該資料，以促進更有效率的審閱。</span><span class="sxs-lookup"><span data-stu-id="e5edb-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="e5edb-105">使用審閱集中的查詢可協助您將重點放在符合您的審閱準則的檔子集。</span><span class="sxs-lookup"><span data-stu-id="e5edb-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="e5edb-106">在審閱集中建立及執行查詢</span><span class="sxs-lookup"><span data-stu-id="e5edb-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="e5edb-107">若要為審閱集內的檔建立並執行查詢，請選取 [檢查集合] 中的 [ **新增查詢** ]。</span><span class="sxs-lookup"><span data-stu-id="e5edb-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="e5edb-108">在命名查詢並定義條件之後，請選取 [ **儲存** ] 以儲存並執行查詢。</span><span class="sxs-lookup"><span data-stu-id="e5edb-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="e5edb-109">若要執行先前已儲存的查詢，請選取一個已儲存的查詢。</span><span class="sxs-lookup"><span data-stu-id="e5edb-109">To run a query that has been previously saved, select a saved query.</span></span>

![檢查集合查詢](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="e5edb-111">建立審閱集查詢</span><span class="sxs-lookup"><span data-stu-id="e5edb-111">Building a review set query</span></span>

<span data-ttu-id="e5edb-112">您可以使用關鍵字條件中的關鍵字、屬性和條件的組合來建立查詢。</span><span class="sxs-lookup"><span data-stu-id="e5edb-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="e5edb-113">您也可以將條件分組為封鎖 (稱為 *condition group* ) ，以建立更複雜的查詢。</span><span class="sxs-lookup"><span data-stu-id="e5edb-113">You can also group conditions as a block (called a *condition group* ) to build a more complex query.</span></span> <span data-ttu-id="e5edb-114">如需您可以搜尋之中繼資料屬性的清單和描述，請參閱 [Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="e5edb-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="e5edb-115">條件</span><span class="sxs-lookup"><span data-stu-id="e5edb-115">Conditions</span></span>

<span data-ttu-id="e5edb-116">每個審閱集中的可搜尋欄位都有對應的條件，可供您用來建立查詢。</span><span class="sxs-lookup"><span data-stu-id="e5edb-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="e5edb-117">有多種類型的條件：</span><span class="sxs-lookup"><span data-stu-id="e5edb-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="e5edb-118">Freetext： freetext 條件是用於文字欄位（例如 subject）。</span><span class="sxs-lookup"><span data-stu-id="e5edb-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="e5edb-119">您可以將多個搜尋字詞以逗號分隔，以加以列出。</span><span class="sxs-lookup"><span data-stu-id="e5edb-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="e5edb-120">Date：日期條件是用於日期欄位（例如「上次修改日期」）。</span><span class="sxs-lookup"><span data-stu-id="e5edb-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="e5edb-121">搜尋選項：「搜尋選項」條件會為您的考核集中的特定欄位提供可能的值清單。</span><span class="sxs-lookup"><span data-stu-id="e5edb-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="e5edb-122">這適用于在您的考核集中，具有有限數目的可能值的欄位（例如寄件者）。</span><span class="sxs-lookup"><span data-stu-id="e5edb-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="e5edb-123">關鍵字：關鍵字條件是 freetext 條件的特定實例，您可以用來搜尋字詞，或在中使用類似 KQL 的查詢語言。</span><span class="sxs-lookup"><span data-stu-id="e5edb-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="e5edb-124">如需詳細資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="e5edb-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="e5edb-125">查詢語言</span><span class="sxs-lookup"><span data-stu-id="e5edb-125">Query language</span></span>

<span data-ttu-id="e5edb-126">除了條件之外，您還可以使用關鍵字條件中的類似 KQL 的查詢語言來建立您的查詢。</span><span class="sxs-lookup"><span data-stu-id="e5edb-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="e5edb-127">「檢查的複查集」查詢語言支援標準 Boolean 運算子，例如 **and** 、 **OR** 、 **NOT** 和 **NEAR** 。</span><span class="sxs-lookup"><span data-stu-id="e5edb-127">The query language for review set queries supports standard Boolean operators, such as **AND** , **OR** , **NOT** , and **NEAR** .</span></span> <span data-ttu-id="e5edb-128">它也支援單一字元萬用字元 (？ ) 和多字元萬用字元 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="e5edb-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="e5edb-129">篩選</span><span class="sxs-lookup"><span data-stu-id="e5edb-129">Filters</span></span>

<span data-ttu-id="e5edb-130">除了您可以儲存的查詢之外，您還可以使用「複查集」篩選，將其他條件快速套用至審閱集查詢。</span><span class="sxs-lookup"><span data-stu-id="e5edb-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="e5edb-131">使用篩選可協助您進一步精煉「審閱集」查詢所顯示的結果。</span><span class="sxs-lookup"><span data-stu-id="e5edb-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![審閱集合篩選](../media/AeDReviewSetFilters.png)

<span data-ttu-id="e5edb-133">篩選不同于查詢的兩個重要方式：</span><span class="sxs-lookup"><span data-stu-id="e5edb-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="e5edb-134">篩選是暫時性的。</span><span class="sxs-lookup"><span data-stu-id="e5edb-134">Filters are transient.</span></span> <span data-ttu-id="e5edb-135">它們不會存在於現有的會話之外。</span><span class="sxs-lookup"><span data-stu-id="e5edb-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="e5edb-136">換句話說，您無法儲存篩選。</span><span class="sxs-lookup"><span data-stu-id="e5edb-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="e5edb-137">查詢會儲存至複查集，並在開啟評審集時進行存取。</span><span class="sxs-lookup"><span data-stu-id="e5edb-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="e5edb-138">篩選永遠都是累加的。</span><span class="sxs-lookup"><span data-stu-id="e5edb-138">Filters are always additive.</span></span> <span data-ttu-id="e5edb-139">除了目前的複查集查詢之外，還會套用篩選器。</span><span class="sxs-lookup"><span data-stu-id="e5edb-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="e5edb-140">套用不同的查詢會取代目前查詢所傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="e5edb-140">Applying a different query will replace the results returned by the current query.</span></span>
