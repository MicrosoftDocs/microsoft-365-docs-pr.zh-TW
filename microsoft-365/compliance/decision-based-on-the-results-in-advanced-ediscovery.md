---
title: 根據 Advanced eDiscovery 的結果決策
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 瞭解 Advanced eDiscovery 中的 [決定] 索引標籤如何提供可協助您決定正確的案例檔案集大小的資料。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769148"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="5fbc4-103">在 Advanced eDiscovery 中以相關性結果為基礎的決策</span><span class="sxs-lookup"><span data-stu-id="5fbc4-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="5fbc4-104">在 Advanced eDiscovery 的 [相關性] 模組中，[判斷] 索引標籤會提供其他資訊，供您用來判斷查看案例檔案集大小，以供查看及使用決策支援的統計資料。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="5fbc4-105">使用 [決定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="5fbc4-105">Using the Decide tab</span></span>

![決定相關性](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="5fbc4-107">此索引標籤包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="5fbc4-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="5fbc4-108">**問題**：在這裡，您可以從清單中選取感興趣的問題。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="5fbc4-109">**回顧-召回比率**：根據相關性分數 Advanced eDiscovery 評審的比較。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="5fbc4-110">圖表中的截止點代表要檢查的檔百分比，對應至相關性分數。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="5fbc4-111">這是用於相關性測試階段和用於剔除的匯出臨界值。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="5fbc4-112">若要檢查的檔案數目是預設的截止點，表示重新開始和精確度之間的平衡是最佳的。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="5fbc4-113">實際的截止點應該取決於目標及成本折衷 (% 考核) 和風險 (% 召回) 。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="5fbc4-114">使用此滑塊，您可以調整截止點，並查看圖表和參數的效果，調整要檢索的相關檔案的百分比，以及驗證決策之前。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="5fbc4-115">**參數**：檢查、召回、接下來的相關及總成本參數是與評審集相對於整個案例集合相關的累計計算統計資料。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="5fbc4-116">這些參數的定義如下：</span><span class="sxs-lookup"><span data-stu-id="5fbc4-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="5fbc4-117">**檢查**：根據此截止點所要複查的檔案百分比。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="5fbc4-118">**召回**：審閱集內相關檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="5fbc4-119">**下一步相關**：檢查和識別目前不在審閱集中的其他相關檔案的成本。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="5fbc4-120">**總成本**：用於審閱此案例檔案百分比的成本。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="5fbc4-121">Cost 參數設定可由 Case 管理員設定。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="5fbc4-122">**依相關性分數發佈**：深色灰度顯示幕中的檔案低於截止分數。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="5fbc4-123">工具提示會顯示與檔總數相關的審閱檔案集中的相關性分數和相關百分比。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="5fbc4-124">展開的 **詳細資料** 窗格會顯示更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="5fbc4-125">集合中的檔案不包括空白或 nebulous 檔案。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="5fbc4-126">「家族檔案」是指未載入相關性的檔案，但仍會計入為該系列的一部分。</span><span class="sxs-lookup"><span data-stu-id="5fbc4-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
