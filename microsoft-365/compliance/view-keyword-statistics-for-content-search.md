---
title: 查看 eDiscovery 搜尋結果的統計資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用「搜尋統計資料」功能，顯示與「Microsoft 365 規範中心」中的核心 eDiscovery 案例相關聯的內容搜尋和搜尋的統計資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311093"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="30ac2-103">查看 eDiscovery 搜尋結果的統計資料</span><span class="sxs-lookup"><span data-stu-id="30ac2-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="30ac2-104">建立並執行內容搜尋或與核心 eDiscovery 案例相關聯的搜尋之後，您可以查看估計搜尋結果的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="30ac2-105">這包括搜尋結果摘要 (類似搜尋快顯視窗中所顯示之預計搜尋結果的摘要) 、查詢統計資料（如包含符合搜尋查詢之專案的內容位置數），以及具有最相符專案之內容位置的身分識別。</span><span class="sxs-lookup"><span data-stu-id="30ac2-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="30ac2-106">此外，您也可以使用關鍵字清單，設定搜尋，以在搜尋查詢中傳回每個關鍵字的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="30ac2-107">這可讓您比較查詢中每一個關鍵字所傳回的結果數目。</span><span class="sxs-lookup"><span data-stu-id="30ac2-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="30ac2-108">您也可以將搜尋統計資料下載到 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="30ac2-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="30ac2-109">如此可讓您使用 Excel 中的篩選和排序功能來比較結果，並為您的搜尋結果準備報告。</span><span class="sxs-lookup"><span data-stu-id="30ac2-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="30ac2-110">取得搜尋的統計資料</span><span class="sxs-lookup"><span data-stu-id="30ac2-110">Get statistics for searches</span></span>

<span data-ttu-id="30ac2-111">顯示內容搜尋的統計資料，或與核心 eDiscovery 案例相關聯的搜尋：</span><span class="sxs-lookup"><span data-stu-id="30ac2-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="30ac2-112">在 [Microsoft 365 規範中心] 中，按一下 [**全部顯示**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="30ac2-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="30ac2-113">按一下 [ **內容搜尋** ]，然後選取搜尋以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="30ac2-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="30ac2-114">或</span><span class="sxs-lookup"><span data-stu-id="30ac2-114">OR</span></span>

   - <span data-ttu-id="30ac2-115">按一下 [ **eDiscovery**  >  **Core**]，選取案例，然後選取 [**搜尋**] 索引標籤上的搜尋以顯示飛入頁面。</span><span class="sxs-lookup"><span data-stu-id="30ac2-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="30ac2-116">在選取搜尋的飛入頁面上，按一下 [ **搜尋統計資料] 索引** 標籤。</span><span class="sxs-lookup"><span data-stu-id="30ac2-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![[搜尋統計資料] 索引標籤](../media/SearchStatistics1.png)

<span data-ttu-id="30ac2-118">[ **搜尋統計資料] 索引** 標籤包含下列區段，其中包含有關搜尋的不同類型的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="30ac2-119">搜尋內容</span><span class="sxs-lookup"><span data-stu-id="30ac2-119">Search content</span></span>

<span data-ttu-id="30ac2-120">這個區段會顯示搜尋所傳回之預估專案的圖形摘要。</span><span class="sxs-lookup"><span data-stu-id="30ac2-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="30ac2-121">這會指出符合搜尋準則的專案數。</span><span class="sxs-lookup"><span data-stu-id="30ac2-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="30ac2-122">此資訊可讓您瞭解搜尋傳回之專案的預估數目。</span><span class="sxs-lookup"><span data-stu-id="30ac2-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![搜尋搜尋評估](../media/SearchContentReport.png)

- <span data-ttu-id="30ac2-124">**依位置預估專案** 數目：搜尋傳回的預估專案總數。</span><span class="sxs-lookup"><span data-stu-id="30ac2-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="30ac2-125">也會顯示位於 [信箱] 和 [網站] 中的特定專案數目。</span><span class="sxs-lookup"><span data-stu-id="30ac2-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="30ac2-126">**具有點擊作業的預估位置**：包含搜尋傳回之專案的內容位置總數。</span><span class="sxs-lookup"><span data-stu-id="30ac2-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="30ac2-127">也會顯示特定數目的信箱和網站位置。</span><span class="sxs-lookup"><span data-stu-id="30ac2-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="30ac2-128">**依位置 (的資料量（以 MB 為單位）)**：搜尋傳回之所有預估專案的總大小。</span><span class="sxs-lookup"><span data-stu-id="30ac2-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="30ac2-129">也會顯示信箱專案和網站專案的特定大小。</span><span class="sxs-lookup"><span data-stu-id="30ac2-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="30ac2-130">條件報告</span><span class="sxs-lookup"><span data-stu-id="30ac2-130">Condition report</span></span>

<span data-ttu-id="30ac2-131">本節顯示搜尋查詢的統計資料，以及符合搜尋查詢不同部分之估計專案數目的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="30ac2-132">您可以使用這些統計資料來分析符合每個搜尋查詢元件的專案數。</span><span class="sxs-lookup"><span data-stu-id="30ac2-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="30ac2-133">這可協助您細化搜尋準則，並視需要縮小範圍的範圍。</span><span class="sxs-lookup"><span data-stu-id="30ac2-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="30ac2-134">您也可以下載 CSV 格式的此報告複本。</span><span class="sxs-lookup"><span data-stu-id="30ac2-134">You can also download a copy of this report in CSV format.</span></span>

![條件報告](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="30ac2-136">**位置類型**：查詢統計資料適用的內容位置類型。</span><span class="sxs-lookup"><span data-stu-id="30ac2-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="30ac2-137">**Exchange** 的值會指出信箱位置;值 **SharePoint** 表示網站位置。</span><span class="sxs-lookup"><span data-stu-id="30ac2-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="30ac2-138">**部分**：搜尋查詢的部分適用的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="30ac2-139">**主要** 表示整個搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="30ac2-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="30ac2-140">**關鍵字** 表示列中的統計資料是針對特定的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30ac2-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="30ac2-141">如果您使用關鍵字清單進行搜尋查詢，則會在此表格中包含每個查詢元件的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="30ac2-142">如需詳細資訊，請參閱 [取得搜尋的關鍵字統計資料](#get-keyword-statistics-for-searches)。</span><span class="sxs-lookup"><span data-stu-id="30ac2-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="30ac2-143">**條件**：搜尋查詢的實際元件 (關鍵字或條件) ，其傳回的統計資料會顯示在對應的列中。</span><span class="sxs-lookup"><span data-stu-id="30ac2-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="30ac2-144">**具有點擊的位置**： [ **位置類型** ] 欄) 所指定的內容位置數目 (，包含符合 [ **條件** ] 欄中所列之 primary 或關鍵字查詢的專案。</span><span class="sxs-lookup"><span data-stu-id="30ac2-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="30ac2-145">**專案**：從指定的內容位置 (的專案數，) 符合 [ **條件** ] 欄中所列的查詢。</span><span class="sxs-lookup"><span data-stu-id="30ac2-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="30ac2-146">如先前所述，如果專案包含要搜尋之關鍵字的多個實例，它只會在此欄位中計算一次。</span><span class="sxs-lookup"><span data-stu-id="30ac2-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="30ac2-147">**Size (MB)**：在指定的內容位置中 (的所有專案總大小，) 符合 [ **條件** ] 欄中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="30ac2-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="30ac2-148">主要位置</span><span class="sxs-lookup"><span data-stu-id="30ac2-148">Top locations</span></span>

<span data-ttu-id="30ac2-149">此區段顯示搜尋傳回專案中的特定內容位置的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="30ac2-150">會顯示前 1,000 個位置。</span><span class="sxs-lookup"><span data-stu-id="30ac2-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="30ac2-151">您也可以下載 CSV 格式的此報告複本。</span><span class="sxs-lookup"><span data-stu-id="30ac2-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="30ac2-152">位置名稱 (信箱的電子郵件地址，以及網站) 的 URL。</span><span class="sxs-lookup"><span data-stu-id="30ac2-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="30ac2-153"> (信箱或網站) 的位置類型。</span><span class="sxs-lookup"><span data-stu-id="30ac2-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="30ac2-154">搜尋所傳回的內容位置中的專案數預估。</span><span class="sxs-lookup"><span data-stu-id="30ac2-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="30ac2-155">每個內容位置預估專案的總大小。</span><span class="sxs-lookup"><span data-stu-id="30ac2-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="30ac2-156">取得搜尋的關鍵字統計資料</span><span class="sxs-lookup"><span data-stu-id="30ac2-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="30ac2-157">如先前所述，[ **條件報告** ] 區段會顯示搜尋查詢，以及符合查詢之專案 (和大小) 的數目。</span><span class="sxs-lookup"><span data-stu-id="30ac2-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="30ac2-158">如果您在建立或編輯搜尋查詢時使用關鍵字清單，您可以取得增強的統計資料，顯示與每個關鍵字或關鍵字片語相符的專案數目。</span><span class="sxs-lookup"><span data-stu-id="30ac2-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="30ac2-159">這可協助您快速識別查詢的哪些部分是最 (及最低的) 有效。</span><span class="sxs-lookup"><span data-stu-id="30ac2-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="30ac2-160">例如，如果關鍵字會傳回大量的專案，您可以選擇縮小關鍵字查詢以縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="30ac2-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="30ac2-161">若要建立關鍵字清單並查看搜尋的關鍵字統計資料：</span><span class="sxs-lookup"><span data-stu-id="30ac2-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="30ac2-162">在 [Microsoft 365 規範中心] 中，建立新的內容搜尋或與核心 eDiscovery 案例相關聯的搜尋。</span><span class="sxs-lookup"><span data-stu-id="30ac2-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="30ac2-163">在搜尋嚮導的 [ **條件** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="30ac2-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="30ac2-164">選取 [ **顯示關鍵字清單** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="30ac2-164">select the **Show keyword list** checkbox.</span></span>

   ![顯示關鍵字清單核取方塊](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="30ac2-166">在 [關鍵字] 表格的列中輸入關鍵字或關鍵字階段。</span><span class="sxs-lookup"><span data-stu-id="30ac2-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="30ac2-167">例如，在第一列中輸入 [ **預算** ]，然後在第二列中輸入 [ **安全性** ]，然後在第三列中輸入 **FY2021** 。</span><span class="sxs-lookup"><span data-stu-id="30ac2-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![在清單中輸入最多20個關鍵字或關鍵字片語](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="30ac2-169">為了避免大型關鍵字清單所造成的問題，您最多隻能有20列的搜尋查詢的關鍵字清單中。</span><span class="sxs-lookup"><span data-stu-id="30ac2-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="30ac2-170">將關鍵字新增至您要搜尋並取得統計資料的清單後，請執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="30ac2-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="30ac2-171">當搜尋完成時，請選取它以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="30ac2-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="30ac2-172">在 [ **搜尋統計資料] 索引** 標籤上，按一下 [ **條件] 報告** 以顯示搜尋的關鍵字統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![顯示每個關鍵字的統計資料](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="30ac2-174">如先前的螢幕擷取畫面所示，會顯示每個關鍵字的統計資料。這包括：</span><span class="sxs-lookup"><span data-stu-id="30ac2-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="30ac2-175">搜尋中包含的每個內容位置類型的關鍵字統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="30ac2-176">未編制索引的信箱專案數目。</span><span class="sxs-lookup"><span data-stu-id="30ac2-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="30ac2-177">在 **Part** 欄) 中，每個關鍵字 (的實際搜尋查詢和結果會標示為 **關鍵字**，其中包含搜尋查詢的任何條件。</span><span class="sxs-lookup"><span data-stu-id="30ac2-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="30ac2-178">完整的搜尋查詢 (會在 **Part** 欄) 中識別為 **主要** 的，以及針對每個位置類型的完整查詢的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="30ac2-179">請注意，[ **摘要** ] 索引標籤上顯示的是相同的統計資料。</span><span class="sxs-lookup"><span data-stu-id="30ac2-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
