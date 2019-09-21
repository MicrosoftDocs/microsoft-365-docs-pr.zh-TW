---
title: 在 Office 365 進階電子文件探索中瞭解相關性評估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 取得評估階段和在 Office 365 進階電子文件探索中的相關性訓練期間判斷問題的豐富性其角色的概觀。
ms.openlocfilehash: 77d9449ad15fd3a53709f2a28a96b06ab54556eb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076688"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="eac2c-103">在 Office 365 進階電子文件探索中瞭解相關性評估</span><span class="sxs-lookup"><span data-stu-id="eac2c-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="eac2c-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="eac2c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="eac2c-106">進階電子文件啟用早期評估，例如，定義的問題及案例匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="eac2c-106">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="eac2c-107">進階電子文件可讓專家制定決策相關採用方法，並將它們套用至文件檢閱專案。</span><span class="sxs-lookup"><span data-stu-id="eac2c-107">Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="eac2c-108">了解評估</span><span class="sxs-lookup"><span data-stu-id="eac2c-108">Understanding assessment</span></span>

<span data-ttu-id="eac2c-109">在評估、 專家會檢閱隨機的一組至少 500 檔案，這用來判定問題的豐富性並產生反映訓練結果的統計資料。</span><span class="sxs-lookup"><span data-stu-id="eac2c-109">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="eac2c-110">若要達到有助於進階電子文件提供準確的統計資料，以及有效地判斷穩定點訓練程序中的相關性統計層級找不到足夠相關檔案時，成功評估。</span><span class="sxs-lookup"><span data-stu-id="eac2c-110">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="eac2c-111">較高的相關檔案數目集中評估，更精確的統計資料和穩定性演算法的有效性。</span><span class="sxs-lookup"><span data-stu-id="eac2c-111">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="eac2c-112">評估檔案中的相關檔案的數目，可根據的問題而定。</span><span class="sxs-lookup"><span data-stu-id="eac2c-112">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="eac2c-113">豐富性是預估的百分之集中相關問題的相關檔案。</span><span class="sxs-lookup"><span data-stu-id="eac2c-113">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="eac2c-114">較高的豐富性問題會更快速地問題達到更高版本相關的檔案數目，具有較低的豐富性。</span><span class="sxs-lookup"><span data-stu-id="eac2c-114">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="eac2c-115">非常低的豐富性的問題 (例如，2%或更少) 時，需要設定為達到相當數量的相關檔案非常大評估。</span><span class="sxs-lookup"><span data-stu-id="eac2c-115">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="eac2c-116">統計資料，而一文中所述追蹤及決定] 索引標籤的訓練期間和之後批次計算，包括數量的重新叫用不同檢閱組的估計值。</span><span class="sxs-lookup"><span data-stu-id="eac2c-116">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="eac2c-117">根據樣本的估算設定 （在此案例中，評估檔案） 中的統計資料，包括錯誤的邊界和該錯誤邊界的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="eac2c-117">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="eac2c-118">例如，預估的重新叫用的 80%可能會有 95%的信賴等級錯誤再加上或減去 5%的邊界。</span><span class="sxs-lookup"><span data-stu-id="eac2c-118">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="eac2c-119">這表示估計重新叫用是實際 75%的 85%，而且此估計有 95%信賴。</span><span class="sxs-lookup"><span data-stu-id="eac2c-119">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="eac2c-120">越大評估組的錯誤限度變小，且更精確的統計資料。</span><span class="sxs-lookup"><span data-stu-id="eac2c-120">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="eac2c-121">專家檢閱初始評估的一組 500 檔案之後，相關性是能夠判斷錯誤的重新叫用值的目前邊界。</span><span class="sxs-lookup"><span data-stu-id="eac2c-121">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values.</span></span> <span data-ttu-id="eac2c-122">相關性也會設定預設邊界為它到達最佳化評估組建議的錯誤。</span><span class="sxs-lookup"><span data-stu-id="eac2c-122">Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set.</span></span> <span data-ttu-id="eac2c-123">以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="eac2c-123">Following are some examples:</span></span>
  
- <span data-ttu-id="eac2c-124">如果已設定的評估會產生錯誤，再加上或減去 10%的邊界，將會建議相關性移至訓練 （需要任何額外評定檢閱）。</span><span class="sxs-lookup"><span data-stu-id="eac2c-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="eac2c-125">如果評估組產生的錯誤，再加上或減去 13%限度，相關性可能建議另一組評估檔案，以達到較小的邊界的檢閱。</span><span class="sxs-lookup"><span data-stu-id="eac2c-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="eac2c-126">如果豐富性極低，相關性可能建議停止評估，即使的錯誤限度是大型 （進行統計資料並不實用），因為到達有用的錯誤限度所需的評估集太大。</span><span class="sxs-lookup"><span data-stu-id="eac2c-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="eac2c-127">每一項問題有它自己的豐富性、 目前邊界的錯誤，並如此一來，估計的其他評估的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="eac2c-127">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="eac2c-128">下一步評估集建立根據 （最多 1000 個在一組) 檔案的數目上限。</span><span class="sxs-lookup"><span data-stu-id="eac2c-128">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="eac2c-129">您可以接受的相關性建議或調整目前的錯誤限度根據您的需求。</span><span class="sxs-lookup"><span data-stu-id="eac2c-129">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="eac2c-130">錯誤的目前的預設邊界決定等於或高於 75%的重新叫用。</span><span class="sxs-lookup"><span data-stu-id="eac2c-130">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac2c-131">評估階段可以略過，在**相關性\>追蹤**中有問題，清除 [**評估**] 核取方塊每個問題，然後針對 「 所有問題 」 的擴充檢視] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="eac2c-131">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="eac2c-132">不過，因此，會有這個問題沒有統計資料。</span><span class="sxs-lookup"><span data-stu-id="eac2c-132">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="eac2c-133">清除 [**評估**] 核取方塊 > 只能執行評估之前執行。</span><span class="sxs-lookup"><span data-stu-id="eac2c-133">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="eac2c-134">在多個問題存在於案例中，核取方塊已清除的每一項問題時，才將略過評估</span><span class="sxs-lookup"><span data-stu-id="eac2c-134">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="eac2c-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eac2c-135">See also</span></span>

[<span data-ttu-id="eac2c-136">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="eac2c-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="eac2c-137">標記與評估</span><span class="sxs-lookup"><span data-stu-id="eac2c-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="eac2c-138">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="eac2c-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="eac2c-139">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="eac2c-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="eac2c-140">決定根據結果</span><span class="sxs-lookup"><span data-stu-id="eac2c-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="eac2c-141">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="eac2c-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

