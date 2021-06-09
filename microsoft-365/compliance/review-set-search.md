---
title: 查詢審閱集中的內容
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
description: 瞭解如何在評審集中建立及執行查詢，以在 Advanced eDiscovery 案例中組織內容，以進行更有效率的審閱。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736389"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="18838-103">查詢和篩選檢閱集中的內容</span><span class="sxs-lookup"><span data-stu-id="18838-103">Query and filter content in a review set</span></span>

<span data-ttu-id="18838-104">在大多數情況下，深入查看審閱集合中的內容，並加以組織，以促進更有效率的審閱。</span><span class="sxs-lookup"><span data-stu-id="18838-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="18838-105">在審閱集中使用篩選和查詢可協助您將重點放在符合您的審閱準則的檔子集。</span><span class="sxs-lookup"><span data-stu-id="18838-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="18838-106">預設篩選器</span><span class="sxs-lookup"><span data-stu-id="18838-106">Default filters</span></span>

<span data-ttu-id="18838-107">在複查集中，審閱集內預先載入了五個預設篩選：</span><span class="sxs-lookup"><span data-stu-id="18838-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="18838-108">關鍵字</span><span class="sxs-lookup"><span data-stu-id="18838-108">Keywords</span></span>
- <span data-ttu-id="18838-109">日期</span><span class="sxs-lookup"><span data-stu-id="18838-109">Date</span></span>
- <span data-ttu-id="18838-110">寄件者/作者</span><span class="sxs-lookup"><span data-stu-id="18838-110">Sender/Author</span></span>
- <span data-ttu-id="18838-111">主旨/職稱</span><span class="sxs-lookup"><span data-stu-id="18838-111">Subject/Title</span></span>
- <span data-ttu-id="18838-112">標記</span><span class="sxs-lookup"><span data-stu-id="18838-112">Tags</span></span>

![預設篩選器類型](../media/DefaultFilterTypes.png)

<span data-ttu-id="18838-114">按一下每個篩選器以加以展開並指派值。</span><span class="sxs-lookup"><span data-stu-id="18838-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="18838-115">按一下篩選外部，以自動將篩選套用至審閱集。</span><span class="sxs-lookup"><span data-stu-id="18838-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="18838-116">下列螢幕擷取畫面顯示設定為在日期範圍內顯示檔的日期篩選器。</span><span class="sxs-lookup"><span data-stu-id="18838-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![展開預設篩選](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="18838-118">新增或移除篩選</span><span class="sxs-lookup"><span data-stu-id="18838-118">Add or remove filters</span></span>

<span data-ttu-id="18838-119">若要新增或移除針對審閱集顯示的篩選，請選取 [ **篩選** ] 以開啟 [篩選器] 面板，它會顯示在飛入頁面上。</span><span class="sxs-lookup"><span data-stu-id="18838-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![篩選器面板](../media/FilterPanel.png)

<span data-ttu-id="18838-121">可用的篩選分為四個區段：</span><span class="sxs-lookup"><span data-stu-id="18838-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="18838-122">**搜尋**：提供不同搜尋功能的篩選器。</span><span class="sxs-lookup"><span data-stu-id="18838-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="18838-123">**分析 & 預測編碼**：當您執行 **檔 & 的電子郵件分析** 工作或使用預測編碼模型時，所產生及新增至檔的篩選屬性。</span><span class="sxs-lookup"><span data-stu-id="18838-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="18838-124">**IDs**：篩選檔的所有 ID 屬性。</span><span class="sxs-lookup"><span data-stu-id="18838-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="18838-125">**專案屬性**：篩選檔案屬性。</span><span class="sxs-lookup"><span data-stu-id="18838-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="18838-126">展開每個區段，並選取或取消選取篩選，以在篩選集中新增或移除篩選。</span><span class="sxs-lookup"><span data-stu-id="18838-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="18838-127">當您新增篩選時，它會顯示在 filter 集合中。</span><span class="sxs-lookup"><span data-stu-id="18838-127">When you add a filter, it's displayed in the filter set.</span></span> 

![篩選器面板中的篩選區段和屬性清單](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="18838-129">當您展開 [篩選] 面板中的區段時，您會注意到已選取預設的篩選類型。</span><span class="sxs-lookup"><span data-stu-id="18838-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="18838-130">您可以將它們保持選取或取消選取，並將它們從 filter 集合中移除。</span><span class="sxs-lookup"><span data-stu-id="18838-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="18838-131">篩選類型</span><span class="sxs-lookup"><span data-stu-id="18838-131">Filter types</span></span>

<span data-ttu-id="18838-132">審閱集合中的每個可搜尋欄位都有對應的篩選，您可以根據特定欄位來篩選項目。</span><span class="sxs-lookup"><span data-stu-id="18838-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="18838-133">篩選器有多種類型：</span><span class="sxs-lookup"><span data-stu-id="18838-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="18838-134">**Freetext**： freetext 濾鏡會套用至文字欄位，例如 "Subject"。</span><span class="sxs-lookup"><span data-stu-id="18838-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="18838-135">您可以將多個搜尋字詞以逗號分隔，以加以列出。</span><span class="sxs-lookup"><span data-stu-id="18838-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="18838-136">**日期**：日期篩選器用於日期欄位（例如「上次修改日期」）。</span><span class="sxs-lookup"><span data-stu-id="18838-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="18838-137">**搜尋選項**：「搜尋選項篩選」提供可能值的清單 (每個值都顯示一個核取方塊，您可以為審閱中的特定欄位選取) 。</span><span class="sxs-lookup"><span data-stu-id="18838-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="18838-138">此篩選器是用於欄位（例如 "Sender"），其中的審閱集中可能的值有有限的數目。</span><span class="sxs-lookup"><span data-stu-id="18838-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="18838-139">**關鍵字**：關鍵字條件是 freetext 條件的特定實例，可供您用來搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="18838-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="18838-140">您也可以在此類型的篩選中使用類似 KQL 的查詢語言。</span><span class="sxs-lookup"><span data-stu-id="18838-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="18838-141">如需詳細資訊，請參閱本主題中的查詢語言和高級查詢產生器小節。</span><span class="sxs-lookup"><span data-stu-id="18838-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="18838-142">包含及排除篩選關係</span><span class="sxs-lookup"><span data-stu-id="18838-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="18838-143">您可以選擇變更特定篩選的 [包含] 和 [排除] 關聯。</span><span class="sxs-lookup"><span data-stu-id="18838-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="18838-144">例如，在標記篩選中，您可以在下拉式篩選中選取 [ **等於無** ]，以排除以特定標記標記的專案。</span><span class="sxs-lookup"><span data-stu-id="18838-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![排除標記篩選](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="18838-146">將篩選儲存為查詢</span><span class="sxs-lookup"><span data-stu-id="18838-146">Save filters as queries</span></span>

<span data-ttu-id="18838-147">當您對篩選器滿意後，您可以將篩選器組合儲存為篩選器查詢。</span><span class="sxs-lookup"><span data-stu-id="18838-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="18838-148">這可讓您在未來的審閱會話中套用篩選。</span><span class="sxs-lookup"><span data-stu-id="18838-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="18838-149">若要儲存篩選，請選取 **[儲存查詢** 並為其命名]。</span><span class="sxs-lookup"><span data-stu-id="18838-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="18838-150">您或其他檢閱者可以先選取 [ **已儲存的篩選查詢** ] 下拉式清單，然後選取要套用至審閱集檔的篩選器查詢，以執行先前儲存的篩選查詢。</span><span class="sxs-lookup"><span data-stu-id="18838-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![儲存篩選查詢](../media/SaveFilterQuery.png)

<span data-ttu-id="18838-152">若要刪除篩選查詢，請開啟 [篩選] 面板，然後選取查詢旁的 [trashcan] 圖示。</span><span class="sxs-lookup"><span data-stu-id="18838-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![刪除篩選查詢](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="18838-154">查詢語言</span><span class="sxs-lookup"><span data-stu-id="18838-154">Query language</span></span>

<span data-ttu-id="18838-155">除了使用篩選之外，您也可以在關鍵字篩選中使用 KQL 類似的查詢語言來建立您的複查集搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="18838-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="18838-156">「檢查的複查集」查詢語言支援標準 Boolean 運算子，例如 **and**、 **OR**、 **NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="18838-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="18838-157">它也支援單一字元萬用字元 (？ ) 和多字元萬用字元 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="18838-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="18838-158">高級查詢產生器</span><span class="sxs-lookup"><span data-stu-id="18838-158">Advanced query builder</span></span>

<span data-ttu-id="18838-159">您也可以建立更高級的查詢來搜尋審閱集中的檔。</span><span class="sxs-lookup"><span data-stu-id="18838-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="18838-160">開啟 [篩選] 面板，選取 [ **篩選**]，然後展開 [ **搜尋** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="18838-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![新增 KQL 篩選](../media/AddKQLFilter.png)

2. <span data-ttu-id="18838-162">選取 [ **KQL** ] 篩選器，然後按一下 [ **開啟查詢** 建立器]。</span><span class="sxs-lookup"><span data-stu-id="18838-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="18838-163">在此面板中，您可以使用查詢建立器來建立複雜的 KQL 查詢。</span><span class="sxs-lookup"><span data-stu-id="18838-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="18838-164">您可以新增條件，也可以新增條件群組，這些群組是由以邏輯方式連接之多個條件所組成 **及** 或或 **或** 關聯。</span><span class="sxs-lookup"><span data-stu-id="18838-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![使用查詢建立器來設定複雜的篩選查詢](../media/ComplexQuery.png)
