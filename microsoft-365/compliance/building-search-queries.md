---
title: 建立搜尋查詢
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
description: 在 Microsoft 365 中使用高级电子数据展示时，使用关键字和条件来缩小搜索范围。
ms.openlocfilehash: c4b2c5b6983b556ad87b553dde767c2160674a78
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076666"
---
# <a name="build-search-queries"></a><span data-ttu-id="8f187-103">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="8f187-103">Build search queries</span></span>

<span data-ttu-id="8f187-104">构建搜索查询时，可以使用关键字查找特定内容和条件，以缩小搜索范围，以返回与您的法律调查最相关的项目。</span><span class="sxs-lookup"><span data-stu-id="8f187-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![使用关键字和条件缩小搜索结果范围](media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="8f187-106">关键字搜索</span><span class="sxs-lookup"><span data-stu-id="8f187-106">Keyword searches</span></span>

<span data-ttu-id="8f187-107">在搜索查询**的"关键字"** 框中键入关键字查询。</span><span class="sxs-lookup"><span data-stu-id="8f187-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="8f187-108">您可以指定关键字、电子邮件属性（如发送和接收日期）或文档属性（如文件名或文档上次更改的日期）。</span><span class="sxs-lookup"><span data-stu-id="8f187-108">You can specify keywords, email message properties, (such as sent and received dates), or document properties (such as file names or the date that a document was last changed).</span></span> <span data-ttu-id="8f187-109">您可以使用使用布尔运算符的更复杂的查询，例如\*\*\*\* AND、OR、NOT 和\*\*\*\*\*\*NEAR\*\* \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8f187-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="8f187-110">您还可以在 SharePoint 和 OneDrive 中的文档中搜索敏感信息（如社会保险号），或者搜索外部共享的文档。</span><span class="sxs-lookup"><span data-stu-id="8f187-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="8f187-111">如果将**关键字**框留空，则位于指定内容位置的所有内容都在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="8f187-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>
    
<span data-ttu-id="8f187-112">或者，您可以**单击"显示关键字列表"** 复选框，并在每行中键入关键字或关键字短语。</span><span class="sxs-lookup"><span data-stu-id="8f187-112">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="8f187-113">如果这样做，则每行中的关键字由逻辑运算符（在搜索查询语法中表示为*c：s）* 连接，该逻辑运算符的功能与创建的搜索查询中的**OR**运算符类似。</span><span class="sxs-lookup"><span data-stu-id="8f187-113">If you do this, the keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="8f187-114">这意味着包含任何行中的任何关键字的项目都在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="8f187-114">This means that items that contain any keyword in any row are in the search results.</span></span>

![使用关键字列表获取查询中每个关键字的统计信息](media/KeywordListSearch.png)

<span data-ttu-id="8f187-116">为什么要使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="8f187-116">Why use the keyword list?</span></span> <span data-ttu-id="8f187-117">您可以获取显示关键字列表中每个关键字匹配的项目数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="8f187-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="8f187-118">这可以帮助您快速识别最有效（也是最不有效）的关键字。</span><span class="sxs-lookup"><span data-stu-id="8f187-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="8f187-119">您还可以在关键字列表中的一行中使用关键字短语（用括号括起来）。</span><span class="sxs-lookup"><span data-stu-id="8f187-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="8f187-120">有关搜索统计信息的详细信息，请参阅[搜索统计信息](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="8f187-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8f187-121">为了帮助减少由大型关键字列表引起的问题，关键字列表中最多只能有 20 行。</span><span class="sxs-lookup"><span data-stu-id="8f187-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="8f187-122">條件</span><span class="sxs-lookup"><span data-stu-id="8f187-122">Conditions</span></span>
    
<span data-ttu-id="8f187-123">您可以添加搜索条件以缩小搜索范围并返回更精细的结果集。</span><span class="sxs-lookup"><span data-stu-id="8f187-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="8f187-124">每个条件都会向启动搜索时创建和运行的搜索查询添加一个子句。</span><span class="sxs-lookup"><span data-stu-id="8f187-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="8f187-125">条件由逻辑运算符（在搜索查询语法中表示为*c：c）* 逻辑连接到关键字查询（在关键字框中指定），该逻辑运算符的功能与**AND**运算符类似。</span><span class="sxs-lookup"><span data-stu-id="8f187-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="8f187-126">这意味着项必须满足关键字查询和搜索结果中包含的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="8f187-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="8f187-127">這就是條件如何協助您縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="8f187-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="8f187-128">有关可在搜索查询中使用的条件的列表和说明，请参阅[关键字查询和搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的"搜索条件"部分。</span><span class="sxs-lookup"><span data-stu-id="8f187-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
