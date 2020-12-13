---
title: 在高級電子檔探索中使用相關性模組
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 深入瞭解「高級 eDiscovery」中的相關性模組，包括工作流程和指導方針，以及訓練和檔案檢查的步驟。
ms.openlocfilehash: 0319ac378fb891d96437f53931213429b111d61d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663282"
---
# <a name="use-the-relevance-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="cbf2f-103">在高級 eDiscovery (傳統) 中使用相關性模組</span><span class="sxs-lookup"><span data-stu-id="cbf2f-103">Use the Relevance module in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="cbf2f-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="cbf2f-106">在 [Advanced eDiscovery] 中，相關性模組包含與案例相關的相關性訓練和評論。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-106">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="cbf2f-107">相關性工作流程的顯示和描述如下：</span><span class="sxs-lookup"><span data-stu-id="cbf2f-107">The Relevance workflow is shown and described as follows:</span></span>
  
![相關性工作流程](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="cbf2f-109">**評估和追蹤週期**：</span><span class="sxs-lookup"><span data-stu-id="cbf2f-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="cbf2f-110">**評估**：「Advanced eDiscovery」會根據隨機的檔案範例來啟用早期評估，並使用這項評估來套用決策，以判斷預測編碼程式的效能。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="cbf2f-111">**追蹤**： Advanced eDiscovery 計算及顯示評估的過渡結果，同時監控處理常式的統計有效性。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="cbf2f-112">**訓練和追蹤週期**：</span><span class="sxs-lookup"><span data-stu-id="cbf2f-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="cbf2f-113">**標記**：「高級電子檔探索」會根據專家的重複檢查和個別檔案的標記，瞭解每個問題特有的相關準則。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="cbf2f-114">**追蹤**： Advanced eDiscovery 計算及顯示相關性訓練的過渡結果，同時監控處理常式的統計有效性。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="cbf2f-115">**批次計算**：「高級 eDiscovery」採用積累和瞭解的相關準則，將其套用至整個檔案集合，並產生每個檔案的相關性分數。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="cbf2f-116">**決定**：「高級電子檔探索」顯示批次計算後，套用到整個案例的分析結果，並顯示資料以進行檔檢查決策。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="cbf2f-117">**測試**：您可以測試高級 ediscovery 結果，以確認高級 ediscovery 處理的有效性和效能。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="cbf2f-118">相關訓練和評論的指導方針</span><span class="sxs-lookup"><span data-stu-id="cbf2f-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="cbf2f-119">以下是有關關聯性訓練和審查的指導方針：</span><span class="sxs-lookup"><span data-stu-id="cbf2f-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="cbf2f-120">**錯誤和不一致**：如果在訓練期間進行標記錯誤，請回到先前的檔案範例以修正這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-120">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="cbf2f-121">如果有太多錯誤無法修正，或是案例或問題的新觀點，應由系統管理員重新定義相關性準則，並重新啟動相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-121">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="cbf2f-122">**標記與訓練**：</span><span class="sxs-lookup"><span data-stu-id="cbf2f-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="cbf2f-123">檔案應該以只以內容為基礎的標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-123">Files should be tagged based on content only.</span></span> <span data-ttu-id="cbf2f-124">請勿考慮中繼資料，例如保管人、date 或 file path。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-124">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="cbf2f-125">在標記檔案時，請勿考慮文字中的日期範圍指示。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="cbf2f-126">在標記檔案時，請勿考慮內嵌的圖形影像。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="cbf2f-127">若要在標記時使用 **格式化的文字視圖** 圖示來查看檔案，請勿考慮文字的格式設定。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-127">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text.</span></span> <span data-ttu-id="cbf2f-128">例如，以刪除線顯示的單字 (一條水平線，指出刪除) 仍會被相關性視為所分析文字的一部分。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-128">For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="cbf2f-129">忽略套用到「案例管理員」或「系統管理員」) 所設定之相關性 (的文字，將會從相關性的文字視圖中的顯示檔案內容中移除。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-129">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="cbf2f-130">如果在相關性訓練已經開始之後定義了 Ignore text 的值，則會將新的忽略文字套用到從定義的點所建立的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-130">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="cbf2f-131">您應謹慎使用「忽略文字」功能，因為其使用可能會降低檔分析的效能</span><span class="sxs-lookup"><span data-stu-id="cbf2f-131">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="cbf2f-132">只有在必要時才使用 [ **略過標記** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-132">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="cbf2f-133">「高級 eDiscovery」不會根據略過的檔案進行訓練。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-133">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="cbf2f-134">在評估中，如果您很難判斷檔案是否相關，最好在可能的情況下，標記為相關 (R) 或不相關 (NR) ，而不是選取 [ **略過**]。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-134">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="cbf2f-135">當 [Advanced eDiscovery] 評估訓練時，可看到這些檔案類型的處理方式。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-135">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="cbf2f-136">即便是具有極少量解壓縮文字的檔案，也應該在訓練中以 R/NR 的身分標記，而不是以「略過」標記（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="cbf2f-137">標籤會影響分類器，只要該檔案可擦讀且可以標示為 R/NR。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="cbf2f-138">**[標籤] 索引** 標籤上的 [顯示的範例檔案] 清單中的檔順序編號可讓使用者回到檔案的原始顯示順序。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="cbf2f-139">您可以回到任何範例，並變更評估與訓練集檔的標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-139">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="cbf2f-140">建立下一個範例時，會套用這些變更。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-140">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="cbf2f-141">以 PDF 格式掃描的 Excel 檔案，在標記檔案時，應與原生 Excel 檔案相同。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="cbf2f-142">當您對檔案的相關性標記不確定時，請諮詢專家。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-142">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="cbf2f-143">在相關性訓練期間不正確的標籤可能會導致在程式的後損毀，而且可能會對整體結果的品質產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-143">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="cbf2f-144">關鍵字清單中所定義的關鍵字會顯示在 [色彩] 中，以協助使用者在標記時識別相關檔。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="cbf2f-145">**批次計算**：由專家標記為 R/NR 的檔案，將會收到0或100的分數。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-145">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="cbf2f-146">這適用于批次計算之前所進行的標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-146">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="cbf2f-147">如果專家在批次計算後將問題切換至空閒狀態，並且繼續標記此問題，則新的已標記分數不會是100/0，而是原始分數。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-147">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="cbf2f-148">**問題和採樣模式**：當工作完成時，通常會關閉問題 (相關性訓練是「穩定」和「批次計算」已執行) 、當問題取消時，或其他使用者正在處理問題時）。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="cbf2f-149">相關訓練中的步驟</span><span class="sxs-lookup"><span data-stu-id="cbf2f-149">Steps in Relevance training</span></span>

<span data-ttu-id="cbf2f-150">在 [ **相關性 \> 追蹤** ] 索引標籤中，Advanced eDiscovery 提供如何在處理過程中進行處理的建議，以及下列後續步驟。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-150">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="cbf2f-151">在下列每個步驟都建議使用相關性訓練程式時，說明下列各項的含義。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-151">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="cbf2f-152">標記/繼續標記：在範例中每個檔案和問題的專家所執行的檔案檢查及相關性標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="cbf2f-153">隱含：現有的範例需要加上標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="cbf2f-154">評估/繼續評估：啟用案例問題相關性的早期驗證，以及針對目前案例匯入的檔案人口相關性的初步觀點。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="cbf2f-155">隱含：需要或建議進行更多評估。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="cbf2f-156">訓練/繼續訓練：在此過程中，高級電子檔探索是透過標記檔案範例的專家，取得的功能，識別每個案例內容中與每個問題相關的相關準則。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="cbf2f-157">隱含：此問題需要進一步訓練;下一個範例應該建立並加上標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="cbf2f-158">批次計算：這是一種相關性處理方式，其中的「高級 eDiscovery」會採取訓練階段所取得的知識，並將其套用至整個檔案的人口。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-158">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="cbf2f-159">會評估相關檔群組中的所有檔案，以取得相關性，並指派相關性分數。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-159">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="cbf2f-160">隱含：此問題已穩定，可執行批次計算。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="cbf2f-161">追趕：「相關性」表示當專家在滾動負載案例期間，從其他檔案負載中所選取的檔案範例會何時審閱及標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="cbf2f-162">隱含：已新增新的負載，必須有追趕才能繼續運作。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="cbf2f-163">標記不一致：進程會透過高級 eDiscovery 演算法識別可能對分析造成負面影響的檔標記處理常式中的不一致。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="cbf2f-164">暗示：下一個範例會包括已在先前範例中標記的檔案，而且必須重做其標記。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="cbf2f-165">更新分類器：允許使用者套用標記或植入變更。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="cbf2f-166">隱含：可以套用標記和植入變更，而不需要手動執行另一個相關性範例。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="cbf2f-167">保留：相關性訓練程式已完成。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="cbf2f-168">隱含：此時不需要相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="cbf2f-169">雖然「高級 eDiscovery」會引導您完成此程式，並在不同的階段進行後續步驟，但也可讓您在選項卡和頁面之間流覽，並做出選擇，以解決可能與您的個別案例、問題或檔審閱程式相關的情形。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="cbf2f-170">您可以接受或覆寫 Advanced eDiscovery 的後續處理選項。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-170">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="cbf2f-171">如果您想要執行的步驟不是建議的下一個步驟，請按一下 [展開的問題顯示幕] 對話方塊中所列的 **下一個步驟** ，按一下下一個步驟旁邊的 [ **修改** ] 按鈕，然後選取另一個 [下一步] 選項。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-171">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cbf2f-172">當您解除鎖定時，有些選項可能仍會停用，因為不支援在程式中使用該位置。</span><span class="sxs-lookup"><span data-stu-id="cbf2f-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cbf2f-173">請參閱</span><span class="sxs-lookup"><span data-stu-id="cbf2f-173">See also</span></span>

[<span data-ttu-id="cbf2f-174">Office 365 進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="cbf2f-174">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="cbf2f-175">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="cbf2f-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cbf2f-176">標記與評估</span><span class="sxs-lookup"><span data-stu-id="cbf2f-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cbf2f-177">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="cbf2f-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cbf2f-178">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="cbf2f-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cbf2f-179">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="cbf2f-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cbf2f-180">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="cbf2f-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

