---
title: 在高級 eDiscovery 中收集案例的資料
f1.keywords:
- NOCSH
ms.author: esclee
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
ms.openlocfilehash: 462c58f8531265026b34fe3d8484736aefa4c5fa
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2020
ms.locfileid: "43799936"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="0ae2f-102">在高級 eDiscovery 中收集案例的資料</span><span class="sxs-lookup"><span data-stu-id="0ae2f-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="0ae2f-103">在您識別出您的案例感興趣的保管人和資料來源之後，即可識別出要深入瞭解的檔集合。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="0ae2f-104">您可以使用 [Advanced eDiscovery] 中的搜尋工具，從 Microsoft 365 中的 custodial 和非 custodial 位置識別相關的檔。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-104">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="0ae2f-105">在您執行搜尋之後，您可以在檢索的專案上查看統計資料，例如，專案數符合搜尋查詢的位置。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="0ae2f-106">您也可以預覽結果的子集。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="0ae2f-107">當您識別想要進一步檢查的檔集合時，您可以將搜尋結果新增至審閱集，以進行收集和處理。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="0ae2f-108">建立搜尋</span><span class="sxs-lookup"><span data-stu-id="0ae2f-108">Create a search</span></span>

<span data-ttu-id="0ae2f-109">在 [**搜尋**] 索引標籤上選取 [**新增搜尋**]，將會啟動一個指導您建立搜尋的嚮導。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="0ae2f-110">如需如何建立搜尋的詳細資訊，請參閱[建立搜尋以收集資料](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="0ae2f-111">在建立搜尋之後，會顯示一個包含詳細資料的浮出頁面頁面。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="0ae2f-112">因為尚未完成搜尋，所以**統計**及**預覽**按鈕最初無法使用。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="0ae2f-113">您可以在 [**搜尋**] 索引標籤上追蹤搜尋進度。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="0ae2f-114">查看搜尋結果和統計資料</span><span class="sxs-lookup"><span data-stu-id="0ae2f-114">View search results and statistics</span></span>

<span data-ttu-id="0ae2f-115">內容搜尋有兩個元件：統計資料（預估）和預覽。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="0ae2f-116">每個元件都完成之後，您會看到 [**搜尋**] 索引標籤的 [搜尋] 索引標籤上的**In progress**對應欄的狀態會**顯示為 [** **已完成**]。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="0ae2f-117">完成搜尋預估後，請選取搜尋以顯示飛出頁面，此頁面會顯示搜尋結果的一些高層次統計資料。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="0ae2f-118">此時，[**統計資料]** 按鈕將會作用中。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="0ae2f-119">您可以選取它，以查看搜尋統計資料，例如：</span><span class="sxs-lookup"><span data-stu-id="0ae2f-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="0ae2f-120">摘要</span><span class="sxs-lookup"><span data-stu-id="0ae2f-120">Summary</span></span>
- <span data-ttu-id="0ae2f-121">主要位置</span><span class="sxs-lookup"><span data-stu-id="0ae2f-121">Top locations</span></span>
- <span data-ttu-id="0ae2f-122">查詢</span><span class="sxs-lookup"><span data-stu-id="0ae2f-122">Queries</span></span>

<span data-ttu-id="0ae2f-123">如需搜尋統計資料的詳細資訊，請參閱[搜尋統計資料](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="0ae2f-124">完成預覽後，**預覽**按鈕將會作用中。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="0ae2f-125">選取它，以預覽結果的抽樣子集。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="0ae2f-126">將搜尋結果新增至檢閱集</span><span class="sxs-lookup"><span data-stu-id="0ae2f-126">Add search results to a review set</span></span>

<span data-ttu-id="0ae2f-127">當您準備好收集並處理整個搜尋結果時，您可以將其新增至審閱集來執行。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="0ae2f-128">如需詳細資訊，請參閱[將資料新增至審閱集](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="0ae2f-129">將非 Microsoft 365 資料新增至審閱集</span><span class="sxs-lookup"><span data-stu-id="0ae2f-129">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="0ae2f-130">在案例的集合過程中，您也可以將非 Office 365 資料新增至審閱集，並與您使用「搜尋」工具收集的 Office 365 資料一起進行審閱及分析。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-130">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="0ae2f-131">當您新增非 Office 365 時，您必須將它與案例中的特定系統管理員相關聯。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-131">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="0ae2f-132">如需詳細資訊，請參閱[Load 非 Microsoft 365 data into a a 審校 set](load-non-Office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae2f-132">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
