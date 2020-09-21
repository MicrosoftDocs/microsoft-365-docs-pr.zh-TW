---
title: 在高級 eDiscovery 中收集案例的資料
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
description: 瞭解如何使用 Advanced eDiscovery 中的搜尋工具，識別要在調查中查看的檔組。
ms.custom: seo-marvel-2020
ms.openlocfilehash: 725c289324a8e4d5bd4d7a7b9ddd9e091b6d6241
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956196"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="91b71-103">在高級 eDiscovery 中收集案例的資料</span><span class="sxs-lookup"><span data-stu-id="91b71-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="91b71-104">在您識別出您的案例感興趣的保管人和資料來源之後，即可識別出要深入瞭解的檔集合。</span><span class="sxs-lookup"><span data-stu-id="91b71-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="91b71-105">您可以使用 [Advanced eDiscovery] 中的搜尋工具，從 Microsoft 365 中的 custodial 和非 custodial 位置識別相關的檔。</span><span class="sxs-lookup"><span data-stu-id="91b71-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="91b71-106">在您執行搜尋之後，您可以在檢索的專案上查看統計資料，例如，專案數符合搜尋查詢的位置。</span><span class="sxs-lookup"><span data-stu-id="91b71-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="91b71-107">您也可以預覽結果的子集。</span><span class="sxs-lookup"><span data-stu-id="91b71-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="91b71-108">當您識別想要進一步檢查的檔集合時，您可以將搜尋結果新增至審閱集，以進行收集和處理。</span><span class="sxs-lookup"><span data-stu-id="91b71-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="91b71-109">建立搜尋</span><span class="sxs-lookup"><span data-stu-id="91b71-109">Create a search</span></span>

<span data-ttu-id="91b71-110">在 [**搜尋**] 索引標籤上選取 [**新增搜尋**]，將會啟動一個指導您建立搜尋的嚮導。</span><span class="sxs-lookup"><span data-stu-id="91b71-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="91b71-111">如需如何建立搜尋的詳細資訊，請參閱 [建立搜尋以收集資料](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="91b71-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="91b71-112">在建立搜尋之後，會顯示一個包含詳細資料的浮出頁面頁面。</span><span class="sxs-lookup"><span data-stu-id="91b71-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="91b71-113">因為尚未完成搜尋，所以 **統計** 及 **預覽** 按鈕最初無法使用。</span><span class="sxs-lookup"><span data-stu-id="91b71-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="91b71-114">您可以在 [ **搜尋** ] 索引標籤上追蹤搜尋進度。</span><span class="sxs-lookup"><span data-stu-id="91b71-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="91b71-115">查看搜尋結果和統計資料</span><span class="sxs-lookup"><span data-stu-id="91b71-115">View search results and statistics</span></span>

<span data-ttu-id="91b71-116">內容搜尋有兩個元件：統計資料 (估計) 和預覽。</span><span class="sxs-lookup"><span data-stu-id="91b71-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="91b71-117">每個元件都完成之後，您會看到 [**搜尋**] 索引標籤的 [搜尋] 索引標籤上的**In progress**對應欄的狀態會**顯示為 [** **已完成**]。</span><span class="sxs-lookup"><span data-stu-id="91b71-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="91b71-118">完成搜尋預估後，請選取搜尋以顯示飛出頁面，此頁面會顯示搜尋結果的一些高層次統計資料。</span><span class="sxs-lookup"><span data-stu-id="91b71-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="91b71-119">此時，[ **統計資料]** 按鈕將會作用中。</span><span class="sxs-lookup"><span data-stu-id="91b71-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="91b71-120">您可以選取它，以查看搜尋統計資料，例如：</span><span class="sxs-lookup"><span data-stu-id="91b71-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="91b71-121">摘要</span><span class="sxs-lookup"><span data-stu-id="91b71-121">Summary</span></span>
- <span data-ttu-id="91b71-122">主要位置</span><span class="sxs-lookup"><span data-stu-id="91b71-122">Top locations</span></span>
- <span data-ttu-id="91b71-123">查詢</span><span class="sxs-lookup"><span data-stu-id="91b71-123">Queries</span></span>

<span data-ttu-id="91b71-124">如需搜尋統計資料的詳細資訊，請參閱 [搜尋統計資料](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="91b71-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="91b71-125">完成預覽後， **預覽** 按鈕將會作用中。</span><span class="sxs-lookup"><span data-stu-id="91b71-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="91b71-126">選取它，以預覽結果的抽樣子集。</span><span class="sxs-lookup"><span data-stu-id="91b71-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="91b71-127">將搜尋結果新增至檢閱集</span><span class="sxs-lookup"><span data-stu-id="91b71-127">Add search results to a review set</span></span>

<span data-ttu-id="91b71-128">當您準備好收集並處理整個搜尋結果時，您可以將其新增至審閱集來執行。</span><span class="sxs-lookup"><span data-stu-id="91b71-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="91b71-129">如需詳細資訊，請參閱 [將資料新增至審閱集](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="91b71-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="91b71-130">將非 Microsoft 365 資料新增至審閱集</span><span class="sxs-lookup"><span data-stu-id="91b71-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="91b71-131">在案例的集合過程中，您也可以將非 Office 365 資料新增至審閱集，並與您使用「搜尋」工具收集的 Office 365 資料一起進行審閱及分析。</span><span class="sxs-lookup"><span data-stu-id="91b71-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="91b71-132">當您新增非 Office 365 時，您必須將它與案例中的特定系統管理員相關聯。</span><span class="sxs-lookup"><span data-stu-id="91b71-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="91b71-133">如需詳細資訊，請參閱 [Load 非 Microsoft 365 data into a a 審校 set](load-non-Office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="91b71-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
