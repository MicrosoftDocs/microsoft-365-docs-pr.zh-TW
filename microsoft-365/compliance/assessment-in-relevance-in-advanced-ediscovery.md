---
title: 在高級電子檔探索中瞭解相關評估
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 深入瞭解 Microsoft 365 Advanced eDiscovery 中的相關訓練期間，判斷問題的豐富程度，以及其角色。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28bbe15a6e3f5611041cf446bd053f59de395d54
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663078"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a><span data-ttu-id="b426f-103">瞭解 Advanced eDiscovery (傳統) 中的相關評估</span><span class="sxs-lookup"><span data-stu-id="b426f-103">Understand Assessment in Relevance in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="b426f-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="b426f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b426f-106">「高級 eDiscovery」可讓您及早評估，例如，針對某一案例定義的問題和匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="b426f-106">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="b426f-107">「高級 eDiscovery」可讓專家決定採用的方法，並將這些決策套用至檔審閱專案。</span><span class="sxs-lookup"><span data-stu-id="b426f-107">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="b426f-108">瞭解評估</span><span class="sxs-lookup"><span data-stu-id="b426f-108">Understanding assessment</span></span>

<span data-ttu-id="b426f-109">在評估中，專家會檢查至少一組500檔案，用來判斷問題的豐富程度，並產生反映訓練結果的統計資料。</span><span class="sxs-lookup"><span data-stu-id="b426f-109">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="b426f-110">當找到足夠的相關檔案以達到統計層級，將有助於高級 eDiscovery 相關性以提供準確的統計資料，並有效地判斷訓練程式中的穩定化點，評估會順利完成。</span><span class="sxs-lookup"><span data-stu-id="b426f-110">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="b426f-111">評估集內相關檔案的數量越高，其統計資料和穩定性演算法的效能就會越精確。</span><span class="sxs-lookup"><span data-stu-id="b426f-111">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="b426f-112">評估檔案中的相關檔案數目取決於問題的豐富程度。</span><span class="sxs-lookup"><span data-stu-id="b426f-112">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="b426f-113">豐富程度是與問題相關之集合中的相關檔案預估百分比。</span><span class="sxs-lookup"><span data-stu-id="b426f-113">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="b426f-114">大量豐富的相關檔案會比使用較低豐富的問題更快速地達到較高的相關檔案。</span><span class="sxs-lookup"><span data-stu-id="b426f-114">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="b426f-115">大量豐富的大量豐富 (問題例如，2% 或更少) 會需要非常大的評估，以達到大量相關檔案。</span><span class="sxs-lookup"><span data-stu-id="b426f-115">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="b426f-116">在訓練和批次計算之後的 [追蹤] 索引標籤中呈現的統計資料，包括針對不同的審查集估計的召回。</span><span class="sxs-lookup"><span data-stu-id="b426f-116">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="b426f-117">在 [統計資料] 中，根據範例 (集進行估計會在此案例中，評估檔) 會包含錯誤的邊界以及該誤差邊界的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="b426f-117">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="b426f-118">例如，估計召回80% 時，可能會有超出95% 信賴等級的正負寬的誤差。</span><span class="sxs-lookup"><span data-stu-id="b426f-118">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="b426f-119">這表示預估的召回實際為 75%-85%，而這預估的估計為95%。</span><span class="sxs-lookup"><span data-stu-id="b426f-119">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="b426f-120">評估集越大，錯誤的邊界就會變小，而且統計資料也會更準確。</span><span class="sxs-lookup"><span data-stu-id="b426f-120">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="b426f-121">在專家檢查500檔的初始評估集合之後，相關性可以判斷召回值的目前錯誤的邊界。</span><span class="sxs-lookup"><span data-stu-id="b426f-121">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="b426f-122">相關性也會建議要達到的預設誤差邊界，以優化評估集。</span><span class="sxs-lookup"><span data-stu-id="b426f-122">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="b426f-123">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="b426f-123">Here are some examples:</span></span>
  
- <span data-ttu-id="b426f-124">如果評估設定已經產生加減或減10% 的誤差，相關性將建議移至訓練 () 不需要其他評估評論。</span><span class="sxs-lookup"><span data-stu-id="b426f-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="b426f-125">如果評估設定產生的誤差為加減或減13%，相關性可能會建議您複查另一組評估檔，以達到較小的邊界。</span><span class="sxs-lookup"><span data-stu-id="b426f-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="b426f-126">如果豐富程度特別低，即使錯誤的邊界很大 (使統計資料變得不) 實用，也可能會導致停止評估，因為這是因為達到有用的錯誤邊界所需的評估設定太大。</span><span class="sxs-lookup"><span data-stu-id="b426f-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="b426f-127">每個問題都有自己的豐富程度、目前的錯誤邊界，以及結果、估計數目的額外評估檔。</span><span class="sxs-lookup"><span data-stu-id="b426f-127">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="b426f-128">下一個評估集是根據 1000 (一組) 中的最大檔案數目。</span><span class="sxs-lookup"><span data-stu-id="b426f-128">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="b426f-129">您可以接受相關性建議，或根據您的需求調整目前的錯誤邊界。</span><span class="sxs-lookup"><span data-stu-id="b426f-129">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="b426f-130">在等於或高於75% 的情況下，會判斷目前的錯誤目前邊界是否可重新叫用。</span><span class="sxs-lookup"><span data-stu-id="b426f-130">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b426f-131">您可以在問題展開的 [ **相關性 \> 追蹤** ] 索引標籤中，清除 [每個問題的 **評估** ] 核取方塊，然後針對「所有問題」，以略過評估階段。</span><span class="sxs-lookup"><span data-stu-id="b426f-131">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="b426f-132">不過，如此一來，就不會發生此問題的統計資料。</span><span class="sxs-lookup"><span data-stu-id="b426f-132">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="b426f-133">> 清除 **評估** 核取方塊只會在執行評估之前完成。</span><span class="sxs-lookup"><span data-stu-id="b426f-133">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="b426f-134">如果有多個問題存在於案例中，只有在此核取方塊針對每個問題清除時，才會略過評估。</span><span class="sxs-lookup"><span data-stu-id="b426f-134">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="b426f-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="b426f-135">Related topics</span></span>

[<span data-ttu-id="b426f-136">Office 365 進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="b426f-136">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b426f-137">標記與評估</span><span class="sxs-lookup"><span data-stu-id="b426f-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b426f-138">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="b426f-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b426f-139">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="b426f-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b426f-140">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="b426f-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b426f-141">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="b426f-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

