---
title: 根據高級 eDiscovery 的結果決定
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: 瞭解 [Advanced eDiscovery] 中的 [決定] 索引標籤可如何提供資料，以協助您決定正確的查看案例檔案集大小。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 04c6f0c8fede315f175e0ed6ae265c7463405a62
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528003"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="0a9d4-103">以 Advanced eDiscovery （古典）結果為基礎的決策</span><span class="sxs-lookup"><span data-stu-id="0a9d4-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="0a9d4-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="0a9d4-106">在 [Advanced eDiscovery] 中，[判斷] 索引標籤提供其他資訊，供您用來判斷查看案例檔案集大小的決策支援統計資料。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="0a9d4-107">使用 [決定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="0a9d4-107">Using the Decide tab</span></span>

![決定相關性](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="0a9d4-109">此索引標籤包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="0a9d4-109">This tab includes the following components:</span></span>
  
- <span data-ttu-id="0a9d4-110">**問題**：在這裡，您可以從清單中選取感興趣的問題。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="0a9d4-111">**回顧-召回比率**：根據相關性分數，進行高級 eDiscovery 檢查的比較。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-111">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="0a9d4-112">圖表中的截止點代表要檢查的檔百分比，對應至相關性分數。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="0a9d4-113">這是用於相關性測試階段和用於剔除的匯出臨界值。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="0a9d4-114">若要檢查的檔案數目是預設的截止點，表示重新開始和精確度之間的平衡是最佳的。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="0a9d4-115">實際的截止點應該取決於目標及成本折衷（% 回顧）和風險（% 召回）等使用者。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="0a9d4-116">使用此滑塊，您可以調整截止點，並查看圖表和參數的效果，調整要檢索的相關檔案的百分比，以及驗證決策之前。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-116">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="0a9d4-117">**參數**：檢查、召回、接下來的相關及總成本參數是與評審集相對於整個案例集合相關的累計計算統計資料。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-117">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="0a9d4-118">這些參數的定義如下：</span><span class="sxs-lookup"><span data-stu-id="0a9d4-118">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="0a9d4-119">**檢查**：根據此截止點所要複查的檔案百分比。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-119">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="0a9d4-120">**召回**：審閱集內相關檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-120">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="0a9d4-121">**下一項相關**：檢查和找出目前不在審閱集中的相關檔案的成本。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-121">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="0a9d4-122">**總成本**：用於審閱此案例檔案百分比的成本。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-122">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="0a9d4-123">Cost 參數設定可由 Case 管理員設定。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-123">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="0a9d4-124">**依相關性分數發佈**：深色灰度顯示幕中的檔案低於截止分數。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-124">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="0a9d4-125">工具提示會顯示與檔總數相關的審閱檔案集中的相關性分數和相關百分比。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-125">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="0a9d4-126">展開的詳細資料窗格會顯示其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-126">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="0a9d4-127">集合中的檔案不包括空白或 nebulous 檔案。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-127">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="0a9d4-128">「家族檔案」是指未載入相關性的檔案，但仍會計入為該系列的一部分。</span><span class="sxs-lookup"><span data-stu-id="0a9d4-128">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0a9d4-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="0a9d4-129">Related topics</span></span>

[<span data-ttu-id="0a9d4-130">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="0a9d4-130">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0a9d4-131">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="0a9d4-131">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0a9d4-132">標記與評估</span><span class="sxs-lookup"><span data-stu-id="0a9d4-132">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0a9d4-133">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="0a9d4-133">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0a9d4-134">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="0a9d4-134">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0a9d4-135">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="0a9d4-135">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

