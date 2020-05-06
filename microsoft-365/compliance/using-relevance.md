---
title: 使用相關性模組分析高級 eDiscovery 中的資料
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
description: 瞭解相關性模組如何分析證據中的資料，以及高級 eDiscovery 中的相關工作流程與訓練步驟的描述。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4babb0aa7693bc1107cc7594da967bca2d307228
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034465"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="7d394-103">使用相關性模組分析高級 eDiscovery 中的資料</span><span class="sxs-lookup"><span data-stu-id="7d394-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="7d394-104">在 [Advanced eDiscovery] 中，相關性模組包含與案例相關的相關性訓練和評論。</span><span class="sxs-lookup"><span data-stu-id="7d394-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="7d394-105">若要使用相關性工作流程，請移至 [管理審閱集內的審閱集]，然後按一下 [顯示相關性]。</span><span class="sxs-lookup"><span data-stu-id="7d394-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="7d394-106">您必須先完成一些步驟，才能開始工作流程：</span><span class="sxs-lookup"><span data-stu-id="7d394-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="7d394-107">處理常式：新增至審閱集合的每個負載集會在這裡顯示為 "容器"。</span><span class="sxs-lookup"><span data-stu-id="7d394-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="7d394-108">您必須先處理這些檔，才能將其新增至相關性模組;您也可以在其中將其標記為植入或預先標記特定問題的位置。</span><span class="sxs-lookup"><span data-stu-id="7d394-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="7d394-109">新增至相關性：在 [ \>相關性載入] 底下，您可以新增已處理成相關性的檔，讓他們可以進行訓練。</span><span class="sxs-lookup"><span data-stu-id="7d394-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="7d394-110">相關性工作流程的顯示和描述如下：</span><span class="sxs-lookup"><span data-stu-id="7d394-110">The Relevance workflow is shown and described as follows:</span></span>
  
![相關性工作流程](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="7d394-112">**評估和追蹤週期**：</span><span class="sxs-lookup"><span data-stu-id="7d394-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="7d394-113">**評估**：根據隨機檔案範例來啟用早期評估，並使用這項評估套用決策，以判斷預測編碼程式的效能。</span><span class="sxs-lookup"><span data-stu-id="7d394-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="7d394-114">**追蹤**：在監控程式的統計有效性時，計算及顯示評估的過渡結果。</span><span class="sxs-lookup"><span data-stu-id="7d394-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="7d394-115">**訓練和追蹤週期**</span><span class="sxs-lookup"><span data-stu-id="7d394-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="7d394-116">**標記**：「高級電子檔探索」會根據專家的重複檢查和個別檔案的標記，瞭解每個問題特有的相關準則。</span><span class="sxs-lookup"><span data-stu-id="7d394-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="7d394-117">**追蹤**：在監控程式的統計有效性時，計算及顯示相關性訓練的過渡結果。</span><span class="sxs-lookup"><span data-stu-id="7d394-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="7d394-118">**批次計算**：對整個檔集合套用累計和已知的相關準則，並為每個檔案產生相關性分數。</span><span class="sxs-lookup"><span data-stu-id="7d394-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="7d394-119">**決定**：在批次計算後會顯示套用至整個案例的分析結果，並顯示用於進行檔檢查決策的資料。</span><span class="sxs-lookup"><span data-stu-id="7d394-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="7d394-120">**測試**：可以測試結果，以確認高級 eDiscovery 處理的有效性和效能。</span><span class="sxs-lookup"><span data-stu-id="7d394-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="7d394-121">**搜尋**：完成相關性工作流程之後，您可以在您的複查集內執行查詢時，針對您的問題，使用此輸出（如，讀取檔的百分點）。</span><span class="sxs-lookup"><span data-stu-id="7d394-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="7d394-122">相關訓練和評論的指導方針</span><span class="sxs-lookup"><span data-stu-id="7d394-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="7d394-123">以下是有關關聯性訓練和審查的指導方針：</span><span class="sxs-lookup"><span data-stu-id="7d394-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="7d394-124">**錯誤和不一致**：如果在訓練期間進行標記錯誤，請回到先前的檔案範例以修正這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d394-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="7d394-125">如果有太多錯誤無法修正，或是案例或問題的新觀點，應由系統管理員重新定義相關性準則，並重新啟動相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="7d394-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="7d394-126">**標記與訓練**：</span><span class="sxs-lookup"><span data-stu-id="7d394-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="7d394-127">檔案應該以只以內容為基礎的標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="7d394-128">請勿考慮中繼資料，例如保管人、date 或 file path。</span><span class="sxs-lookup"><span data-stu-id="7d394-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="7d394-129">在標記檔案時，請勿考慮文字中的日期範圍指示。</span><span class="sxs-lookup"><span data-stu-id="7d394-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="7d394-130">在標記檔案時，請勿考慮內嵌的圖形影像。</span><span class="sxs-lookup"><span data-stu-id="7d394-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="7d394-131">請忽略套用至相關性的文字將會從相關性的文字視圖中的顯示檔內容中移除。</span><span class="sxs-lookup"><span data-stu-id="7d394-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="7d394-132">如果在相關性訓練已經開始之後定義了 Ignore text 的值，則會將新的忽略文字套用到從定義的點所建立的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="7d394-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="7d394-133">您應謹慎使用「忽略文字」功能，因為其使用可能會降低檔分析的效能</span><span class="sxs-lookup"><span data-stu-id="7d394-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="7d394-134">只有在必要時才使用 [**略過標記**] 選項。</span><span class="sxs-lookup"><span data-stu-id="7d394-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="7d394-135">「高級 eDiscovery」不會根據略過的檔案進行訓練。</span><span class="sxs-lookup"><span data-stu-id="7d394-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="7d394-136">在評估中，如果您很難辨別檔案是否相關，請盡可能將其標記為相關（R）或不相關（NR），而不是選取 [**略過**]。</span><span class="sxs-lookup"><span data-stu-id="7d394-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="7d394-137">當 [Advanced eDiscovery] 評估訓練時，可看到這些檔案類型的處理方式。</span><span class="sxs-lookup"><span data-stu-id="7d394-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="7d394-138">即便是具有極少量解壓縮文字的檔案，也應該在訓練中以 R/NR 的身分標記，而不是以「略過」標記（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="7d394-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="7d394-139">標籤會影響分類器，只要該檔案可擦讀且可以標示為 R/NR。</span><span class="sxs-lookup"><span data-stu-id="7d394-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="7d394-140">**[標籤] 索引**標籤上的 [顯示的範例檔案] 清單中的檔順序編號可讓使用者回到檔案的原始顯示順序。</span><span class="sxs-lookup"><span data-stu-id="7d394-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="7d394-141">您可以回到任何範例，並變更評估與訓練集檔的標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="7d394-142">建立下一個範例時，會套用這些變更。</span><span class="sxs-lookup"><span data-stu-id="7d394-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="7d394-143">以 PDF 格式掃描的 Excel 檔案，在標記檔案時，應與原生 Excel 檔案相同。</span><span class="sxs-lookup"><span data-stu-id="7d394-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="7d394-144">當您對檔案的相關性標記不確定時，請諮詢專家。</span><span class="sxs-lookup"><span data-stu-id="7d394-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="7d394-145">在相關性訓練期間不正確的標籤可能會導致在程式的後損毀，而且可能會對整體結果的品質產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="7d394-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="7d394-146">關鍵字清單中所定義的關鍵字會顯示在 [色彩] 中，以協助使用者在標記時識別相關檔。</span><span class="sxs-lookup"><span data-stu-id="7d394-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="7d394-147">**批次計算**：由專家標記為 R/NR 的檔案，將會收到0或100的分數。</span><span class="sxs-lookup"><span data-stu-id="7d394-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="7d394-148">這適用于批次計算之前所進行的標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="7d394-149">如果專家在批次計算後將問題切換至空閒狀態，並且繼續標記此問題，則新的已標記分數不會是100/0，而是原始分數。</span><span class="sxs-lookup"><span data-stu-id="7d394-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="7d394-150">**問題和採樣模式**：當工作完成時，通常會關閉問題（相關性訓練是穩定和批次計算）、何時取消問題，或其他使用者正在處理問題。</span><span class="sxs-lookup"><span data-stu-id="7d394-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="7d394-151">相關訓練中的步驟</span><span class="sxs-lookup"><span data-stu-id="7d394-151">Steps in Relevance training</span></span>

<span data-ttu-id="7d394-152">在 [**相關性\>追蹤**] 索引標籤中，Advanced eDiscovery 提供如何在處理過程中進行處理的建議，以及下列後續步驟。</span><span class="sxs-lookup"><span data-stu-id="7d394-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="7d394-153">在下列每個步驟都建議使用相關性訓練程式時，說明下列各項的含義。</span><span class="sxs-lookup"><span data-stu-id="7d394-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="7d394-154">標記/繼續標記：在範例中每個檔案和問題的專家所執行的檔案檢查及相關性標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="7d394-155">隱含：現有的範例需要加上標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="7d394-156">評估/繼續評估：啟用案例問題相關性的早期驗證，以及針對目前案例匯入的檔案人口相關性的初步觀點。</span><span class="sxs-lookup"><span data-stu-id="7d394-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="7d394-157">隱含：需要或建議進行更多評估。</span><span class="sxs-lookup"><span data-stu-id="7d394-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="7d394-158">訓練/繼續訓練：在此過程中，高級電子檔探索是透過標記檔案範例的專家，取得的功能，識別每個案例內容中與每個問題相關的相關準則。</span><span class="sxs-lookup"><span data-stu-id="7d394-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="7d394-159">隱含：此問題需要進一步訓練;下一個範例應該建立並加上標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="7d394-160">批次計算：這是一種相關性處理方式，其中的「高級 eDiscovery」會採取訓練階段所取得的知識，並將其套用至整個檔案的人口。</span><span class="sxs-lookup"><span data-stu-id="7d394-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="7d394-161">會評估相關檔群組中的所有檔案，以取得相關性，並指派相關性分數。</span><span class="sxs-lookup"><span data-stu-id="7d394-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="7d394-162">隱含：此問題已穩定，可執行批次計算。</span><span class="sxs-lookup"><span data-stu-id="7d394-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="7d394-163">追趕：「相關性」表示當專家在滾動負載案例期間，從其他檔案負載中所選取的檔案範例會何時審閱及標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="7d394-164">隱含：已新增新的負載，必須有追趕才能繼續運作。</span><span class="sxs-lookup"><span data-stu-id="7d394-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="7d394-165">標記不一致：進程會透過高級 eDiscovery 演算法識別可能對分析造成負面影響的檔標記處理常式中的不一致。</span><span class="sxs-lookup"><span data-stu-id="7d394-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="7d394-166">暗示：下一個範例會包括已在先前範例中標記的檔案，而且必須重做其標記。</span><span class="sxs-lookup"><span data-stu-id="7d394-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="7d394-167">更新分類器：允許使用者套用標記或植入變更。</span><span class="sxs-lookup"><span data-stu-id="7d394-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="7d394-168">隱含：可以套用標記和植入變更，而不需要手動執行另一個相關性範例。</span><span class="sxs-lookup"><span data-stu-id="7d394-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="7d394-169">保留：相關性訓練程式已完成。</span><span class="sxs-lookup"><span data-stu-id="7d394-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="7d394-170">隱含：此時不需要相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="7d394-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="7d394-171">雖然「高級 eDiscovery」會引導您完成此程式，並在不同的階段進行後續步驟，但也可讓您在選項卡和頁面之間流覽，並做出選擇，以解決可能與您的個別案例、問題或檔審閱程式相關的情形。</span><span class="sxs-lookup"><span data-stu-id="7d394-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="7d394-172">您可以接受或覆寫 Advanced eDiscovery 的後續處理選項。</span><span class="sxs-lookup"><span data-stu-id="7d394-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="7d394-173">如果您想要執行的步驟不是建議的下一個步驟，請按一下 [展開的問題顯示幕] 對話方塊中所列的**下一個步驟**，按一下下一個步驟旁邊的 [**修改**] 按鈕，然後選取另一個 [下一步] 選項。</span><span class="sxs-lookup"><span data-stu-id="7d394-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7d394-174">當您解除鎖定時，有些選項可能仍會停用，因為不支援在程式中使用該位置。</span><span class="sxs-lookup"><span data-stu-id="7d394-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="7d394-175">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7d394-175">More information</span></span>

[<span data-ttu-id="7d394-176">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="7d394-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7d394-177">標記與評估</span><span class="sxs-lookup"><span data-stu-id="7d394-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7d394-178">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="7d394-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7d394-179">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="7d394-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7d394-180">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="7d394-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7d394-181">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="7d394-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="7d394-182">查詢檢視集中的資料</span><span class="sxs-lookup"><span data-stu-id="7d394-182">Query the data in a review set</span></span>](review-set-search.md)
