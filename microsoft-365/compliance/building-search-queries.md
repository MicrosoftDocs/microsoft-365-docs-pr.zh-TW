---
title: 在高級 eDiscovery 中建立搜尋查詢
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: 使用關鍵字和條件，可在 Microsoft 365 中使用 [Advanced eDiscovery] 搜尋資料時縮小搜尋範圍。
ms.openlocfilehash: 3ddd9c38f16fc2dd0fcb96e5fffc79ebbacdbda4
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285799"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a><span data-ttu-id="fd887-103">在高級電子檔探索中建立搜尋集合查詢</span><span class="sxs-lookup"><span data-stu-id="fd887-103">Build search collection queries in Advanced eDiscovery</span></span>

<span data-ttu-id="fd887-104">當您建立搜尋查詢以在高級 eDiscovery 案例中收集資料時，您可以使用關鍵字來尋找特定內容和條件，以縮小搜尋範圍，以傳回與您法律調查最為相關的專案。</span><span class="sxs-lookup"><span data-stu-id="fd887-104">When building search queries to collect data in an Advanced eDiscovery case, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![使用關鍵字和條件來縮小搜尋結果的範圍](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="fd887-106">關鍵字搜尋</span><span class="sxs-lookup"><span data-stu-id="fd887-106">Keyword searches</span></span>

<span data-ttu-id="fd887-107">在搜尋查詢的 [ **關鍵字** ] 方塊中，輸入關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="fd887-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="fd887-108">您可以指定關鍵字、電子郵件內容（如已傳送和接收的日期）或檔案屬性（例如，檔案名或檔最後變更的日期）。</span><span class="sxs-lookup"><span data-stu-id="fd887-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="fd887-109">您可以使用內含布林運算子的更複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="fd887-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="fd887-110">您也可以搜尋機密資訊 (例如，SharePoint 中的檔) 或 OneDrive (不在電子郵件中) ，或是搜尋外部共用的檔。</span><span class="sxs-lookup"><span data-stu-id="fd887-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="fd887-111">如果 [ **關鍵字** ] 方塊是空白的，則位於指定內容位置的所有內容都位於搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="fd887-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>
    
<span data-ttu-id="fd887-112">或者，您也可以選取 [ **顯示關鍵字清單** ] 核取方塊，並在每一列中輸入關鍵字或關鍵字片語。</span><span class="sxs-lookup"><span data-stu-id="fd887-112">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="fd887-113">如果您這麼做，每一列中的關鍵字會以邏輯運算子 (，這會在搜尋查詢語法) 中以類似于在所建立之搜尋查詢中的**OR**運算子的方式，表示為*c:s* 。</span><span class="sxs-lookup"><span data-stu-id="fd887-113">If you do this, the keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="fd887-114">這表示搜尋結果中包含任何列的任何關鍵字的專案。</span><span class="sxs-lookup"><span data-stu-id="fd887-114">This means items that contain any keyword in any row are in the search results.</span></span>

![使用關鍵字清單取得查詢中每個關鍵字的統計資料](../media/KeywordListSearch.png)

<span data-ttu-id="fd887-116">為什麼要使用關鍵字清單？</span><span class="sxs-lookup"><span data-stu-id="fd887-116">Why use the keyword list?</span></span> <span data-ttu-id="fd887-117">您可以取得統計資料，顯示與關鍵字清單中每個關鍵字相符的專案數目。</span><span class="sxs-lookup"><span data-stu-id="fd887-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="fd887-118">這可協助您快速識別最 (及最低) 有效的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="fd887-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="fd887-119">您也可以使用關鍵字片語 (關鍵字] 清單中某列的括弧括住) 。</span><span class="sxs-lookup"><span data-stu-id="fd887-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="fd887-120">如需搜尋統計資料的詳細資訊，請參閱 [搜尋統計資料](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="fd887-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fd887-121">為了避免大型關鍵字清單所造成的問題，您最多隻能有20列的關鍵字清單。</span><span class="sxs-lookup"><span data-stu-id="fd887-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="fd887-122">條件</span><span class="sxs-lookup"><span data-stu-id="fd887-122">Conditions</span></span>
    
<span data-ttu-id="fd887-123">您可以新增搜尋條件，以縮小搜尋範圍，並傳回更精緻的結果集。</span><span class="sxs-lookup"><span data-stu-id="fd887-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="fd887-124">每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。</span><span class="sxs-lookup"><span data-stu-id="fd887-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="fd887-125">條件會以邏輯方式連線至 [關鍵字] 方塊中指定的關鍵字查詢，邏輯運算子 (會以與**AND**運算子功能類似的搜尋查詢語法) 中的*c:c*表示。</span><span class="sxs-lookup"><span data-stu-id="fd887-125">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="fd887-126">這表示專案必須同時滿足關鍵字查詢，以及要包含在搜尋結果中的一或多個條件。</span><span class="sxs-lookup"><span data-stu-id="fd887-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="fd887-127">這是條件協助縮小搜尋結果的方式。</span><span class="sxs-lookup"><span data-stu-id="fd887-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="fd887-128">如需您可以在搜尋查詢中使用的條件清單和描述，請參閱 [關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)中的「搜尋條件」一節。</span><span class="sxs-lookup"><span data-stu-id="fd887-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
