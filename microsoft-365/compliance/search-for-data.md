---
title: 搜尋調查中的資料
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
description: ''
ms.openlocfilehash: bff750f5600fc1daa9c6d87a4b42f0c9b1caa252
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632908"
---
# <a name="search-for-data-in-an-investigation"></a><span data-ttu-id="41558-102">搜尋調查中的資料</span><span class="sxs-lookup"><span data-stu-id="41558-102">Search for data in an investigation</span></span>

<span data-ttu-id="41558-103">在資料調查的 [**搜尋] 索引**標籤上，您可以使用關鍵字和條件搜尋內容位置中放錯位置、機密或機密的資料。</span><span class="sxs-lookup"><span data-stu-id="41558-103">On the **Search** tab in a data investigation, you can search for misplaced, confidential, or sensitive data in content locations using keywords and conditions.</span></span> 

<span data-ttu-id="41558-104">在您執行搜尋之後，您可以在搜尋傳回的專案上，查看統計資料，例如，專案數與搜尋查詢相符的內容位置。</span><span class="sxs-lookup"><span data-stu-id="41558-104">After you run a search, you can view statistics on the items returned by the search, such as the content locations that had the most items that matched the search query.</span></span> <span data-ttu-id="41558-105">您也可以預覽結果的子集。</span><span class="sxs-lookup"><span data-stu-id="41558-105">You can also preview a subset of the results.</span></span> <span data-ttu-id="41558-106">在您識別要進一步調查的檔集合之後，您可以將搜尋結果新增至證據集，以進一步處理及分析。</span><span class="sxs-lookup"><span data-stu-id="41558-106">After you've identified the set of documents to investigate further, you can add the results of the search to an evidence set to further process and analyze.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="41558-107">建立搜尋</span><span class="sxs-lookup"><span data-stu-id="41558-107">Create a search</span></span>

1. <span data-ttu-id="41558-108">在調查中，按一下 [**搜尋**] 索引標籤，然後按一下 [**新增搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="41558-108">In an investigation, click the **Searches** tab, and then click **New search**.</span></span> 

    <span data-ttu-id="41558-109">隨即會顯示一個嚮導，引導您完成建立搜尋的程式。</span><span class="sxs-lookup"><span data-stu-id="41558-109">A wizard is displayed that guides you through the process of creating a search.</span></span>

2. <span data-ttu-id="41558-110">輸入搜尋名稱和選用的搜尋描述。</span><span class="sxs-lookup"><span data-stu-id="41558-110">Enter a search name and an optional description for the search.</span></span>

3. <span data-ttu-id="41558-111">定義您的搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="41558-111">Define your search criteria.</span></span> <span data-ttu-id="41558-112">您可以使用預先建立的條件卡，或使用關鍵字查詢中的搜尋屬性名稱，來新增搜尋的條件。</span><span class="sxs-lookup"><span data-stu-id="41558-112">You can add conditions for the search by using the pre-built condition cards or by using search property names in the keyword query.</span></span> <span data-ttu-id="41558-113">如需詳細資訊，請參閱[建立搜尋查詢](build-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="41558-113">For more information, see [Build search queries](build-search-queries.md).</span></span>

4. <span data-ttu-id="41558-114">選擇要搜尋的內容位置（資料來源）。</span><span class="sxs-lookup"><span data-stu-id="41558-114">Choose the content locations (data sources) to search.</span></span> <span data-ttu-id="41558-115">您可以選取感興趣之特定人員的內容位置（如果您已新增任何調查）來限定搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="41558-115">You can scope the search by selecting the content locations of specific people of interest (if you added any to the investigation).</span></span> <span data-ttu-id="41558-116">如果您已新增調查的興趣人員，您可以遵循[管理相關人員的](manage-people-of-interest.md#add-people-of-interest)步驟來新增。</span><span class="sxs-lookup"><span data-stu-id="41558-116">If you have added people of interest to the investigation, you can add them by following the steps in [Manage people of interest](manage-people-of-interest.md#add-people-of-interest).</span></span>
 
   <span data-ttu-id="41558-117">有時候，您可能需要先搜尋您組織中的所有內容位置。</span><span class="sxs-lookup"><span data-stu-id="41558-117">Sometimes you may first need to search all content locations in your organization.</span></span> <span data-ttu-id="41558-118">或者，您可能需要搜尋不是由特定人員所擁有的位置。</span><span class="sxs-lookup"><span data-stu-id="41558-118">Alternatively, you may need to search locations that aren't owned by a specific person.</span></span> <span data-ttu-id="41558-119">在此案例中，您可以選擇搜尋整個組織或特定服務的所有位置（例如 Exchange、SharePoint、商務 OneDrive 或小組）。</span><span class="sxs-lookup"><span data-stu-id="41558-119">In this scenario, you can choose to search your entire organization, or all locations for a specific services (such as Exchange, SharePoint, OneDrive of Business, or Teams.</span></span>

5. <span data-ttu-id="41558-120">儲存並執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="41558-120">Save and run the search.</span></span>

<span data-ttu-id="41558-121">在建立搜尋之後，會顯示搜尋的詳細資料頁面。</span><span class="sxs-lookup"><span data-stu-id="41558-121">After the search is created, a flyout page is displayed with details about the search.</span></span> <span data-ttu-id="41558-122">「**統計資料**」和「**預覽**」按鈕最初會變成灰色，因為搜尋尚未完成。</span><span class="sxs-lookup"><span data-stu-id="41558-122">The **Statistics** and **Preview** buttons are initially grayed out because the search hasn't completed.</span></span> <span data-ttu-id="41558-123">您可以透過監視 [**搜尋**] 索引標籤上的 [**狀態**] 欄，追蹤搜尋的進度。</span><span class="sxs-lookup"><span data-stu-id="41558-123">You can track the progress of the search by monitoring the **Status** column on the **Searches** tab.</span></span>

## <a name="view-statistics-and-search-results"></a><span data-ttu-id="41558-124">查看統計資料和搜尋結果</span><span class="sxs-lookup"><span data-stu-id="41558-124">View statistics and search results</span></span>

<span data-ttu-id="41558-125">在您建立及開始資料調查搜尋之後，該工具會使用您定義的搜尋準則（搜尋查詢和內容位置），並在 live service 中搜尋索引，以尋找符合搜尋準則的專案。</span><span class="sxs-lookup"><span data-stu-id="41558-125">After you create and start a data investigation search, the tool uses the search criteria (the search query and content locations) that you defined and searches an index in the live service for items that match your search criteria.</span></span> <span data-ttu-id="41558-126">搜尋完成時，會傳回三個搜尋元件：</span><span class="sxs-lookup"><span data-stu-id="41558-126">There are three components of a search that are returned when the search is complete:</span></span> 

- <span data-ttu-id="41558-127">**評估**–由於搜尋只會搜尋索引（而不是實際的內容位置），因此搜尋結果是預估（根據符合搜尋結果的索引中找到的專案）。</span><span class="sxs-lookup"><span data-stu-id="41558-127">**Estimate** – Because the search only searches an index (rather than the actual content locations), the results of a search are an estimate (based on what was found in the index that matched the search results).</span></span> <span data-ttu-id="41558-128">預估的摘要會顯示在 [**狀態**] 底下的 [搜尋飛出] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="41558-128">A summary of the estimate is displayed on the search flyout page under **Status**.</span></span> <span data-ttu-id="41558-129">搜尋的評估程式狀態會顯示在 [**評估狀態**] 欄的 [**搜尋**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="41558-129">The status for the estimate process for a search is displayed on the **Searches** tab in the **Estimate status** column.</span></span> <span data-ttu-id="41558-130">當搜尋預估完成時，此狀態會設定為 [**成功**]。</span><span class="sxs-lookup"><span data-stu-id="41558-130">When the search estimate is complete, this status is set to **Successful**.</span></span>

- <span data-ttu-id="41558-131">**統計資料**–統計資料提供更多關於搜尋結果的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="41558-131">**Statistics** – Statistics provide more detailed information about the search results.</span></span> <span data-ttu-id="41558-132">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="41558-132">This includes the following:</span></span>

    - <span data-ttu-id="41558-133">摘要–類似于飛入頁面上所顯示之搜尋評估結果的統計資料。</span><span class="sxs-lookup"><span data-stu-id="41558-133">Summary – Statistics similar to the search estimate results displayed on the flyout page.</span></span>
    - <span data-ttu-id="41558-134">上一個位置-搜尋的每個內容位置中符合搜尋查詢之專案數的統計資料。</span><span class="sxs-lookup"><span data-stu-id="41558-134">Top locations - Statistics about the number of items that match the search query in each content location that was searched.</span></span> 
    - <span data-ttu-id="41558-135">查詢–搜尋查詢的詳細統計資料，包含符合搜尋查詢中每個條件的專案數。</span><span class="sxs-lookup"><span data-stu-id="41558-135">Queries – Detailed statistics about the search query, including the number of items that match each condition in a search query.</span></span>

    <span data-ttu-id="41558-136">按一下彈出頁面上的 [**統計資料**] 以查看這些統計資料。</span><span class="sxs-lookup"><span data-stu-id="41558-136">Click **Statistics** on the flyout page to view these statistics.</span></span> <span data-ttu-id="41558-137">在 [**搜尋**] 索引標籤的 [**評估狀態**] 值設為 [**成功**] 之前，此按鈕為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="41558-137">This button is inactive until the value of the **Estimate status** on the **Searches** tab is set to **Successful**.</span></span> <span data-ttu-id="41558-138">如需搜尋統計資料的詳細資訊，請參閱[搜尋統計資料](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="41558-138">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

- <span data-ttu-id="41558-139">**預覽**–搜尋完成時，您可以從搜尋傳回之搜尋結果的範例子集，查看實際專案。</span><span class="sxs-lookup"><span data-stu-id="41558-139">**Preview** – When the search is complete, you can view the actual items from a sample subset of the search results returned by the search.</span></span> <span data-ttu-id="41558-140">您可以在專案類型的原生視圖中查看，任何也可以查看該專案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="41558-140">YOu can view in the native view of the item type, any you can also view metadata about the item.</span></span> <span data-ttu-id="41558-141">若要快速判斷您的搜尋結果是否符合您的預期，或是需要編輯並再次執行搜尋，這是一種很好的方式。</span><span class="sxs-lookup"><span data-stu-id="41558-141">This is a good way to quickly determine if your search results are what you expected or if you need to edit the search and run it again.</span></span> <span data-ttu-id="41558-142">按一下彈出頁面上的 [**預覽**]，以查看搜尋結果中的專案。</span><span class="sxs-lookup"><span data-stu-id="41558-142">Click  **Preview** on the flyout page to view items from the search results.</span></span> <span data-ttu-id="41558-143">在 [**搜尋**] 索引標籤上的**預覽狀態**值設定為 [**成功**] 之前，此按鈕為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="41558-143">This button is inactive until the value of the **Preview status** on the **Searches** tab is set to **Successful**.</span></span>
 
> [!NOTE]
> <span data-ttu-id="41558-144">[**搜尋**] 索引標籤上的 [**評估狀態**] 和 [**預覽狀態**] 欄的狀態**值會送**出、**進行中**及**成功**。</span><span class="sxs-lookup"><span data-stu-id="41558-144">The status values for the **Estimate status** and **Preview status** columns on the **Searches** tab are **Submitted**, **In progress**, and **Successful**.</span></span> <span data-ttu-id="41558-145">如果搜尋發生錯誤，則會顯示 [**失敗**] 狀態。</span><span class="sxs-lookup"><span data-stu-id="41558-145">If there is an error with the search, the status of **Failed** is displayed.</span></span>

## <a name="add-search-results-to-evidence"></a><span data-ttu-id="41558-146">將搜尋結果新增至證據</span><span class="sxs-lookup"><span data-stu-id="41558-146">Add search results to evidence</span></span>

<span data-ttu-id="41558-147">當您符合搜尋的結果並準備好分析和修正這些搜尋結果時，您可以將其新增至調查中的證據集。</span><span class="sxs-lookup"><span data-stu-id="41558-147">When you're satisfied with the results of a search and you're ready to analyze and remediate those search results, you can add them to an evidence set in the investigation.</span></span> <span data-ttu-id="41558-148">當您將專案新增至 [**證據**] 索引標籤上的證據集時，會發生下列三種情況：</span><span class="sxs-lookup"><span data-stu-id="41558-148">When you add items to an evidence set on the **Evidence** tab, the following three things occur:</span></span>

- <span data-ttu-id="41558-149">會再次執行搜尋，並將搜尋的最新結果新增至證據集。</span><span class="sxs-lookup"><span data-stu-id="41558-149">The search is run again, and the latest results of the search are added to the evidence set.</span></span> <span data-ttu-id="41558-150">這表示新增至證據的專案可能與搜尋快顯視窗中所顯示的估計搜尋結果不同。</span><span class="sxs-lookup"><span data-stu-id="41558-150">That means the items that are added to evidence may be different than the estimated search results displayed on the search flyout page.</span></span> <span data-ttu-id="41558-151">如果您上次執行搜尋的時間與將搜尋結果新增至證據之間的某些時間，則可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="41558-151">This might happen if some time has passed between the last time you ran the search and when you add the search results to evidence.</span></span>

- <span data-ttu-id="41558-152">搜尋結果中的所有專案都會從 live service 中的資料來源複製，然後複製至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="41558-152">All items in the search results are copied from the data source in the live service, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="41558-153">所有專案（包括內容和中繼資料）都會重新建立索引，這樣證據集中的所有資料在調查期間都會完全可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="41558-153">All items (including the content and metadata) are re-indexed so that all data in the evidence set is fully searchable during your investigation.</span></span> <span data-ttu-id="41558-154">當您在調查期間搜尋證據集中的資料時，重新編制資料的索引會產生完整且快速的搜尋。</span><span class="sxs-lookup"><span data-stu-id="41558-154">Re-indexing the data results in thorough and fast searches when you search the data in the evidence set during your investigation.</span></span>

<span data-ttu-id="41558-155">將實際資料複製到 Azure 中的證據集的其中一個優點是，針對時間敏感型或關鍵事件，您可以立即刪除 live service 中原始資料來源中的可疑內容，然後再分析已複製到 Azure 儲存位置隔離環境中的證據，以迅速遏制損毀。</span><span class="sxs-lookup"><span data-stu-id="41558-155">One advantage of copying the live data to an evidence set in Azure is that for time-sensitive or critical incidents, you can quickly contain the damage by immediately deleting suspicious content in the original data source in the live service and then investigating the incident by analyzing the evidence that was copied to the quarantined environment of the Azure Storage location.</span></span> 

<span data-ttu-id="41558-156">將原始資料複製到證據集，也可讓您透過高級分析工具（例如主題偵測、接近重複偵測和電子郵件線索識別）來協助您進行調查。</span><span class="sxs-lookup"><span data-stu-id="41558-156">Copying the original data to the evidence set also facilitates your investigation by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span>

<span data-ttu-id="41558-157">如有必要，您也可以將非 Microcsoft 365 資料來源中的資料新增至證據集，使其與您從 Microsoft 365 收集的資料儲存在一起。</span><span class="sxs-lookup"><span data-stu-id="41558-157">If necessary, you can also add data from non-Microcsoft 365 data sources to an evidence set so that it's stored along with the data you collect from Microsoft 365.</span></span>

<span data-ttu-id="41558-158">若要將資料新增至證據集，請選取 [**搜尋**] 索引標籤上的搜尋，然後按一下彈出頁面上的 [**將結果新增至證據**]。</span><span class="sxs-lookup"><span data-stu-id="41558-158">To add data to an evidence set, select a search on the **Searches** tab, and then clicking **Add results to evidence** on the flyout page.</span></span> <span data-ttu-id="41558-159">您可以將資料新增至現有的證據集，或是即時建立新的證據集。</span><span class="sxs-lookup"><span data-stu-id="41558-159">You can add data to an existing evidence set or create a new evidence set on the fly.</span></span>

### <a name="tracking-the-progress-of-adding-search-results-to-evidence"></a><span data-ttu-id="41558-160">追蹤將搜尋結果新增至證據的進度</span><span class="sxs-lookup"><span data-stu-id="41558-160">Tracking the progress of adding search results to evidence</span></span>

<span data-ttu-id="41558-161">將資料新增至證據集是一個長時間執行的處理常式。</span><span class="sxs-lookup"><span data-stu-id="41558-161">Adding data to an evidence set is a long-running process.</span></span> <span data-ttu-id="41558-162">此套裝程式含從 Microsoft 365 （例如，從信箱和網站）收集原始資料來源的專案，並將其複製到 Azure 存放區位置（此複製程式也稱為*攝取*），然後重新編制專案的索引。</span><span class="sxs-lookup"><span data-stu-id="41558-162">The process includes collecting the items the original data source from Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="41558-163">您可以在 [**工作**] 索引標籤上，或是在 [**新增資料至證據**] 欄中的 [**搜尋**] 索引標籤上追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="41558-163">You can either track the progress on the **Jobs** tab or on the **Searches** tab in the **Added data to evidence** column.</span></span> <span data-ttu-id="41558-164">完成證據處理的處理之後，您可以移至 [**證據**] 索引標籤，按一下證據集，然後視需要搜尋、檢查、標記和匯出相關資料，以開始進行調查。</span><span class="sxs-lookup"><span data-stu-id="41558-164">After the processing of evidence processing is completed, you can go to the **Evidence** tab, click the evidence set, and then start your investigation by searching, reviewing, tagging, and exporting the relevant data as necessary.</span></span>
