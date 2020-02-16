---
title: Office 365 進階電子文件探索中的結果為基礎的決策
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
description: '了解如何在 Office 365 進階電子文件探索中的決定] 索引標籤提供資料，可協助您決定正確的檢閱一組案例檔案大小。 '
ms.openlocfilehash: b0dd68c294b4555bcf7c9b2cb1c6db455af32e7d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076242"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="0067f-103">Office 365 進階電子文件探索中的結果為基礎的決策</span><span class="sxs-lookup"><span data-stu-id="0067f-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="0067f-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="0067f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="0067f-106">在進階電子文件，決定] 索引標籤，提供檢視和使用來決定檢閱一組案例檔案的大小決策支援統計資料的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="0067f-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="0067f-107">使用 [決定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="0067f-107">Using the Decide tab</span></span>

![決定相關性](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="0067f-109">此索引標籤包含下列特性：</span><span class="sxs-lookup"><span data-stu-id="0067f-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="0067f-110">**此問題**： 從這裡開始，您可以選取從清單感興趣的問題。</span><span class="sxs-lookup"><span data-stu-id="0067f-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="0067f-111">**檢閱重新叫用比率**： 根據相關性分數比較的進階電子文件探索檢閱。</span><span class="sxs-lookup"><span data-stu-id="0067f-111">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="0067f-112">截止點在圖表中的代表對應至相關性分數若要檢閱，檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="0067f-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="0067f-113">這用於在相關性測試階段，然後為匯出閾值挑選。</span><span class="sxs-lookup"><span data-stu-id="0067f-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="0067f-114">重新叫用與精確度之間取得平衡是最佳的作法點位於預設截止點，若要檢閱的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="0067f-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="0067f-115">實際的截止點應根據目標和成本取捨 （%檢閱） 和風險 （%重新叫用） 之使用者所決定。使用滑桿，您可以調整截止點，並調整相關的檔案，以擷取，並驗證決策之前先 %時，請參閱圖和參數，影響。</span><span class="sxs-lookup"><span data-stu-id="0067f-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="0067f-116">**參數**： 檢閱，請記得下, 一步相關以及總成本參數都是屬於整個案例集合的 relation 中設定檢閱累計計算統計資料。</span><span class="sxs-lookup"><span data-stu-id="0067f-116">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="0067f-117">這些參數的定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="0067f-117">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="0067f-118">**檢閱**： 若要檢閱的檔案百分比根據此截止。</span><span class="sxs-lookup"><span data-stu-id="0067f-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="0067f-119">**回想一下**： 檢閱集中相關檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="0067f-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="0067f-120">**下一步與相關**： 若要檢閱並識別目前尚未檢閱中設定的其他相關檔案的成本。</span><span class="sxs-lookup"><span data-stu-id="0067f-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="0067f-121">**總成本**： 成本檢閱此百分比的大小寫的檔案。</span><span class="sxs-lookup"><span data-stu-id="0067f-121">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="0067f-122">成本的參數設定可以設定的大小寫的管理員。</span><span class="sxs-lookup"><span data-stu-id="0067f-122">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="0067f-123">**由相關性分數的通訊群組**： 檔案在暗灰色向左顯示如下的截止分數。</span><span class="sxs-lookup"><span data-stu-id="0067f-123">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="0067f-124">工具提示顯示的相關性分數，以及相關的檔案百分比檢閱檔案中設定關聯的總檔案中。</span><span class="sxs-lookup"><span data-stu-id="0067f-124">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="0067f-125">展開 [詳細資料] 窗格會顯示其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0067f-125">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="0067f-126">集合圖表目錄中的檔案不包括空白或不是很明確的檔案。</span><span class="sxs-lookup"><span data-stu-id="0067f-126">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="0067f-127">家庭檔案數字代表不載入相關性，但仍會計算在內系列的一部分的檔案。</span><span class="sxs-lookup"><span data-stu-id="0067f-127">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0067f-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0067f-128">See also</span></span>

[<span data-ttu-id="0067f-129">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="0067f-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0067f-130">了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="0067f-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0067f-131">標記與評估</span><span class="sxs-lookup"><span data-stu-id="0067f-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0067f-132">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="0067f-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0067f-133">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="0067f-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0067f-134">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="0067f-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

