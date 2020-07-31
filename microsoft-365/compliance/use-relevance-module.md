---
title: 使用相關性模組分析證據中的資料
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
description: 瞭解關聯性模組如何使用相關性工作流程的描述，以及資料調查（預覽）中的訓練步驟，來分析證據中的資料。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64bd0101fd2a0804da9e513241a97bc9f133880e
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528159"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="2a29f-103">使用相關性模組分析證據中的資料</span><span class="sxs-lookup"><span data-stu-id="2a29f-103">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="2a29f-104">在 [資料調查（預覽）] 中，相關性模組包含與調查相關的相關性訓練和評論。</span><span class="sxs-lookup"><span data-stu-id="2a29f-104">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="2a29f-105">相關性工作流程的顯示和描述如下：</span><span class="sxs-lookup"><span data-stu-id="2a29f-105">The Relevance workflow is shown and described as follows:</span></span>
  
![相關性工作流程](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="2a29f-107">**評估和追蹤週期**：</span><span class="sxs-lookup"><span data-stu-id="2a29f-107">**Cycles of assessment and tracking**:</span></span>

  - <span data-ttu-id="2a29f-108">**評估**：根據隨機檔案範例來啟用早期評估，並使用這項評估套用決策，以判斷預測編碼程式的效能。</span><span class="sxs-lookup"><span data-stu-id="2a29f-108">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 

  - <span data-ttu-id="2a29f-109">**追蹤**：在監控程式的統計有效性時，計算及顯示評估的過渡結果。</span><span class="sxs-lookup"><span data-stu-id="2a29f-109">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 

- <span data-ttu-id="2a29f-110">**訓練和追蹤週期**</span><span class="sxs-lookup"><span data-stu-id="2a29f-110">**Cycles of training and tracking**</span></span>

  - <span data-ttu-id="2a29f-111">**標記**：資料調查（預覽）瞭解每個問題特有的相關準則，取決於每個問題的專家的重複審查及標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-111">**Tag**: Data Investigations (Preview) learns the Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="2a29f-112">**追蹤**：在監控程式的統計有效性時，計算及顯示相關性訓練的過渡結果。</span><span class="sxs-lookup"><span data-stu-id="2a29f-112">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="2a29f-113">**批次計算**：對整個檔集合套用累計和已知的相關準則，並為每個檔案產生相關性分數。</span><span class="sxs-lookup"><span data-stu-id="2a29f-113">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="2a29f-114">**決定**：套用到整個案例的分析結果會顯示批次計算之後，以及用於進行檔檢查決策的資料顯示。</span><span class="sxs-lookup"><span data-stu-id="2a29f-114">**Decide**: The results of the analysis applied to the entire case are displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="2a29f-115">**測試**：可以測試結果，以驗證資料調查（預覽）處理的有效性和有效性。</span><span class="sxs-lookup"><span data-stu-id="2a29f-115">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="2a29f-116">**搜尋**：完成相關性工作流程之後，您可以在您的工作集中執行查詢時，針對您的問題，使用此輸出（如，讀取檔的百分點）。</span><span class="sxs-lookup"><span data-stu-id="2a29f-116">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="2a29f-117">相關訓練和評論的指導方針</span><span class="sxs-lookup"><span data-stu-id="2a29f-117">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="2a29f-118">以下是有關關聯性訓練和審查的指導方針：</span><span class="sxs-lookup"><span data-stu-id="2a29f-118">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="2a29f-119">**錯誤和不一致**：如果在訓練期間進行標記錯誤，請回到先前的檔案範例以修正這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="2a29f-119">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="2a29f-120">如果有太多錯誤無法修正，或是案例或問題的新觀點，應由系統管理員重新定義相關性準則，並重新啟動相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="2a29f-120">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="2a29f-121">**標記與訓練**：</span><span class="sxs-lookup"><span data-stu-id="2a29f-121">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="2a29f-122">檔案應該以只以內容為基礎的標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-122">Files should be tagged based on content only.</span></span> <span data-ttu-id="2a29f-123">請勿考慮中繼資料，例如保管人、date 或 file path。</span><span class="sxs-lookup"><span data-stu-id="2a29f-123">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="2a29f-124">在標記檔案時，請勿考慮文字中的日期範圍指示。</span><span class="sxs-lookup"><span data-stu-id="2a29f-124">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="2a29f-125">在標記檔案時，請勿考慮內嵌的圖形影像。</span><span class="sxs-lookup"><span data-stu-id="2a29f-125">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="2a29f-126">請忽略套用至相關性的文字將會從相關性的文字視圖中的顯示檔內容中移除。</span><span class="sxs-lookup"><span data-stu-id="2a29f-126">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="2a29f-127">如果在相關性訓練已經開始之後定義了 Ignore text 的值，則會將新的忽略文字套用到從定義的點所建立的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="2a29f-127">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="2a29f-128">您應謹慎使用「忽略文字」功能，因為其使用可能會降低檔分析的效能</span><span class="sxs-lookup"><span data-stu-id="2a29f-128">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="2a29f-129">只有在必要時才使用 [**略過標記**] 選項。</span><span class="sxs-lookup"><span data-stu-id="2a29f-129">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="2a29f-130">資料調查（預覽）不會根據略過的檔案進行訓練。</span><span class="sxs-lookup"><span data-stu-id="2a29f-130">Data Investigations (Preview) doesn't train based on skipped files.</span></span> <span data-ttu-id="2a29f-131">在評估中，如果您很難辨別檔案是否相關，請盡可能將其標記為相關（R）或不相關（NR），而不是選取 [**略過**]。</span><span class="sxs-lookup"><span data-stu-id="2a29f-131">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="2a29f-132">當資料調查（預覽）評估訓練時，可看到這些檔案類型的處理方式。</span><span class="sxs-lookup"><span data-stu-id="2a29f-132">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="2a29f-133">即使具有少量解壓縮文字的檔案，也應該在訓練中以 R/NR 標記，而不是以 "Skip" 的方式進行標記（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="2a29f-133">Even files with a small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="2a29f-134">標籤會影響分類器，只要該檔案可擦讀且可以標示為 R/NR。</span><span class="sxs-lookup"><span data-stu-id="2a29f-134">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="2a29f-135">**[標籤] 索引**標籤上的 [顯示的範例檔案] 清單中的檔順序編號可讓使用者回到檔案的原始顯示順序。</span><span class="sxs-lookup"><span data-stu-id="2a29f-135">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="2a29f-136">您可以回到任何範例，並變更評估與訓練集檔的標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-136">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="2a29f-137">建立下一個範例時，會套用這些變更。</span><span class="sxs-lookup"><span data-stu-id="2a29f-137">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="2a29f-138">以 PDF 格式掃描的 Excel 檔案，在標記檔案時，應與原生 Excel 檔案相同。</span><span class="sxs-lookup"><span data-stu-id="2a29f-138">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="2a29f-139">當您對檔案的相關性標記不確定時，請諮詢專家。</span><span class="sxs-lookup"><span data-stu-id="2a29f-139">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="2a29f-140">在相關性訓練期間不正確的標籤可能會導致在程式的後損毀，而且可能會對整體結果的品質產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="2a29f-140">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="2a29f-141">關鍵字清單中所定義的關鍵字會顯示在 [色彩] 中，以協助使用者在標記時識別相關檔。</span><span class="sxs-lookup"><span data-stu-id="2a29f-141">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="2a29f-142">**批次計算**：由專家標記為 R/NR 的檔案，將會收到0或100的分數。</span><span class="sxs-lookup"><span data-stu-id="2a29f-142">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="2a29f-143">這適用于批次計算之前所進行的標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-143">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="2a29f-144">如果專家在批次計算後將問題切換至空閒狀態，並且繼續標記此問題，則新的已標記分數不會是100/0，而是原始分數。</span><span class="sxs-lookup"><span data-stu-id="2a29f-144">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="2a29f-145">**問題和採樣模式**：當問題工作完成時（相關性訓練是穩定和批次計算）、當問題取消時，或是當其他使用者正在處理問題時，就會關閉問題。</span><span class="sxs-lookup"><span data-stu-id="2a29f-145">**Issues and sampling mode**: Issues are turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="2a29f-146">相關訓練中的步驟</span><span class="sxs-lookup"><span data-stu-id="2a29f-146">Steps in Relevance training</span></span>

<span data-ttu-id="2a29f-147">在 [**相關性 \> 追蹤**] 索引標籤中，「資料調查」提供如何在處理過程中進行處理的建議，以及下列後續步驟。</span><span class="sxs-lookup"><span data-stu-id="2a29f-147">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="2a29f-148">在下列每個步驟都建議使用相關性訓練程式時，說明下列各項的含義。</span><span class="sxs-lookup"><span data-stu-id="2a29f-148">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="2a29f-149">標記/繼續標記：在範例中每個檔案和問題的專家所執行的檔案檢查及相關性標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-149">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="2a29f-150">隱含：現有的範例需要加上標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-150">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="2a29f-151">評估/繼續評估：啟用案例問題相關性的早期驗證，以及針對目前案例匯入的檔案人口相關性的初步觀點。</span><span class="sxs-lookup"><span data-stu-id="2a29f-151">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="2a29f-152">隱含：需要或建議進行更多評估。</span><span class="sxs-lookup"><span data-stu-id="2a29f-152">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="2a29f-153">訓練/繼續訓練：在此過程中，資料調查透過標記檔案範例的專家來瞭解，並取得每個案例內容中的每個問題相關的相關準則。</span><span class="sxs-lookup"><span data-stu-id="2a29f-153">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="2a29f-154">隱含：此問題需要進一步訓練;下一個範例應該建立並加上標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-154">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="2a29f-155">批次計算：相關性處理常式，其中的資料調查會利用其在訓練階段中取得的知識，並將其套用至整個檔人口。</span><span class="sxs-lookup"><span data-stu-id="2a29f-155">Batch calculation: Relevance process in which Data investigations take the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="2a29f-156">會評估相關檔群組中的所有檔案，以取得相關性，並指派相關性分數。</span><span class="sxs-lookup"><span data-stu-id="2a29f-156">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="2a29f-157">隱含：此問題已穩定，可執行批次計算。</span><span class="sxs-lookup"><span data-stu-id="2a29f-157">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="2a29f-158">追趕：「相關性」表示當專家在滾動負載案例期間，從其他檔案負載中所選取的檔案範例會何時審閱及標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-158">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="2a29f-159">隱含：已新增新的負載，必須有追趕才能繼續運作。</span><span class="sxs-lookup"><span data-stu-id="2a29f-159">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="2a29f-160">標記不一致：進程會透過資料調查演算法識別可能對分析造成負面影響的檔標記處理常式中的不一致。</span><span class="sxs-lookup"><span data-stu-id="2a29f-160">Tag inconsistencies: Process identifies, via a Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="2a29f-161">暗示：下一個範例會包括已在先前範例中標記的檔案，而且必須重做其標記。</span><span class="sxs-lookup"><span data-stu-id="2a29f-161">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="2a29f-162">更新分類器：允許使用者套用標記或植入變更。</span><span class="sxs-lookup"><span data-stu-id="2a29f-162">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="2a29f-163">隱含：可以套用標記和植入變更，而不需要手動執行另一個相關性範例。</span><span class="sxs-lookup"><span data-stu-id="2a29f-163">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="2a29f-164">保留：相關性訓練程式已完成。</span><span class="sxs-lookup"><span data-stu-id="2a29f-164">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="2a29f-165">隱含：此時不需要相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="2a29f-165">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="2a29f-166">雖然資料調查引導您完成此程式，但在不同的階段使用建議的後續步驟，但也可讓您在選項卡和頁面之間流覽，並做出選擇，以解決可能與您的個別案例、問題或檔審閱程式相關的情形。</span><span class="sxs-lookup"><span data-stu-id="2a29f-166">Although Data investigations guide you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="2a29f-167">您可以接受或覆寫資料調查下一個步驟處理選項。</span><span class="sxs-lookup"><span data-stu-id="2a29f-167">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="2a29f-168">如果您想要執行的步驟不是建議的下一個步驟，請按一下 [展開的問題顯示幕] 對話方塊中所列的**下一個步驟**，按一下下一個步驟旁邊的 [**修改**] 按鈕，然後選取另一個 [下一步] 選項。</span><span class="sxs-lookup"><span data-stu-id="2a29f-168">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2a29f-169">當您解除鎖定時，有些選項可能仍會停用，因為不支援在程式中使用該位置。</span><span class="sxs-lookup"><span data-stu-id="2a29f-169">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="2a29f-170">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2a29f-170">More information</span></span>

[<span data-ttu-id="2a29f-171">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="2a29f-171">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a29f-172">標記與評估</span><span class="sxs-lookup"><span data-stu-id="2a29f-172">Tagging and assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a29f-173">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="2a29f-173">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a29f-174">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="2a29f-174">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a29f-175">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="2a29f-175">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a29f-176">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="2a29f-176">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="2a29f-177">查詢證據中的資料</span><span class="sxs-lookup"><span data-stu-id="2a29f-177">Query the data in evidence</span></span>](evidence-query.md)
