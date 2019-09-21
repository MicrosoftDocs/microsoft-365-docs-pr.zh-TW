---
title: 在 Office 365 進階電子文件探索中追蹤相關性分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: '了解如何檢視，並解譯結果在 Office 365 進階電子文件探索案例問題與相關性訓練狀態。  '
ms.openlocfilehash: 1018b414d0192491feebfbec25d865d4463fa26a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077475"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="cf8c1-103">在 Office 365 進階電子文件探索中追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="cf8c1-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="cf8c1-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="cf8c1-106">進階 eDiscovery 中 [相關性追蹤] 索引標籤會顯示在 [標籤] 索引標籤中執行的相關性訓練的計算的有效性，並指出下一個步驟來反覆訓練程序中所採取的相關性。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="cf8c1-107">追蹤相關性訓練狀態</span><span class="sxs-lookup"><span data-stu-id="cf8c1-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="cf8c1-108">檢視詳細資料如下相關性追蹤記錄中的大小寫的問題，以下**問題名稱**] 對話方塊的下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="cf8c1-109">**評估**： 此進度列指示器顯示何種程度相關性訓練的執行到此點已達到評估目標方面的錯誤限度。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="cf8c1-110">相關性訓練結果的豐富性也會顯示。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="cf8c1-111">**訓練**： 這個可識別的進度指標和工具提示顯示指出相關性訓練結果所展現的穩定性及顯示相關性訓練樣本數字刻度標記的每一項問題。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="cf8c1-112">專家監視反覆相關性訓練程序的進度。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="cf8c1-113">**批次計算**： 此進度列指示器提供完成的批次計算的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="cf8c1-114">**下一步**： 會顯示要執行的下一個步驟的建議。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="cf8c1-115">在範例中，會顯示此問題： 成功完成的評估，以完成的彩色進度列指示器和核取記號表示。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="cf8c1-116">標記正在進行中，但這種情況仍然會被視為不穩定 （也顯示工具提示中所展現的穩定性狀態）。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="cf8c1-117">下一步步驟建議 「 訓練。 」</span><span class="sxs-lookup"><span data-stu-id="cf8c1-117">The next step recommendation is "Training".</span></span> 
    
    ![相關性追蹤訓練步驟 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="cf8c1-119">展開的檢視會顯示其他資訊和選項。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="cf8c1-120">顯示目前錯誤邊界是在評估給定的現有 （已標記） 的評定檔案的目前狀態重新叫用的錯誤邊界。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="cf8c1-121">評估階段可以略過清除每個問題，然後針對 「 所有問題 」 的**評估**核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="cf8c1-122">不過，因此，會有這個問題沒有統計資料。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="cf8c1-123">清除 [**評估**] 核取方塊 > 只能執行評估之前執行。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="cf8c1-124">在多個問題存在於案例中，核取方塊已清除的每一項問題時，才將略過評估</span><span class="sxs-lookup"><span data-stu-id="cf8c1-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="cf8c1-125">當評估就不會完成與第一個範例設定檔的、 評估可能會標示多個檔案的下一步。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="cf8c1-126">在 [**相關性** \> **追蹤**訓練進度列指示器，工具提示指出到達所展現的穩定性所需的額外樣本估計的數。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="cf8c1-127">這項預估值需要其他訓練提供的指導方針。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![相關性追蹤訓練](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="cf8c1-129">當您準備完成標記和若要繼續訓練時，按一下 [**訓練**。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="cf8c1-130">從載入的檔案設定的其他訓練產生另一個範例一組檔案。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="cf8c1-131">您然後都會傳回到標記並訓練多個檔案的 [標籤] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="cf8c1-132">達到穩定訓練層級</span><span class="sxs-lookup"><span data-stu-id="cf8c1-132">Reaching stable training levels</span></span>

<span data-ttu-id="cf8c1-133">評估檔案已得到穩定層級之後，進階電子文件是訓練的準備好進行批次計算。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf8c1-134">通常，三個穩定訓練範例之後下, 一步就是 「 批次計算 」。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="cf8c1-135">可能有例外狀況，例如，若要從先前的範例或植入的檔案時所新增的檔案標記發生變更時。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="cf8c1-136">執行批次計算</span><span class="sxs-lookup"><span data-stu-id="cf8c1-136">Performing Batch calculation</span></span>

<span data-ttu-id="cf8c1-137">批次計算執行為下一個步驟之後訓練成功完成 （時的穩定訓練狀態會顯示進度列中，核取記號和工具提示中的穩定狀態。）批次計算會套用至整個檔案母群體，若要評估的檔案相關性，並將指定相關性分數的相關性訓練期間取得的知識。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="cf8c1-138">多個問題時，批次計算是完成每個問題。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="cf8c1-139">批次計算期間處理的所有檔案時的監視進度。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="cf8c1-140">在這裡，建議的下一個步驟為"None"，這表示沒有其他反覆相關性訓練需要這個時候。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="cf8c1-141">下一個階段是**相關性\>決定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="cf8c1-142">如果您想要匯入批次計算後的新檔案，系統管理員可以新增新的負載匯入的檔案。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf8c1-143">如果您按一下 [**取消**] 批次計算期間，處理程序會儲存什麼已經被執行。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="cf8c1-144">如果您執行一次批次計算時，會從最後一個執行點繼續程序。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="cf8c1-145">評估標記一致性</span><span class="sxs-lookup"><span data-stu-id="cf8c1-145">Assessing tagging consistency</span></span>

<span data-ttu-id="cf8c1-146">如果中已有不一致標記檔案，將會影響分析。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="cf8c1-147">結果不是最佳化或一致性是有疑問時，可以使用進階電子文件探索標記一致性處理程序。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="cf8c1-148">會傳回可能不一致標記檔案的清單，而且您可以檢閱並重新標記，視。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf8c1-149">七個或多個下列評估、 標記一致性可檢視在**相關性**訓練趨之後\>**追蹤** \> **問題** \> **詳細的結果** \> **訓練進度**。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="cf8c1-150">此檢閱一次完成一個問題。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="cf8c1-151">在**相關性\>追蹤**，依序展開 [問題] 列。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="cf8c1-152">至右邊的**下一個步驟**中，按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="cf8c1-153">[**下一步**] 選項後七個訓練範例為選取**標記不一致**，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="cf8c1-154">選取 [**標記不一致**。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="cf8c1-155">[**標籤**] 索引標籤會開啟顯示來重新標記 [必要時的不一致的清單。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="cf8c1-156">按一下 [**計算**]，將變更提交]。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="cf8c1-157">之後標記不一致的情況下一步 「 訓練。 」</span><span class="sxs-lookup"><span data-stu-id="cf8c1-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="cf8c1-158">檢視和使用相關性結果</span><span class="sxs-lookup"><span data-stu-id="cf8c1-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="cf8c1-159">在**相關性\>追蹤**] 索引標籤，依序展開 [問題] 列中，並旁的 [**詳細的結果**中，按一下 [**檢視**]。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="cf8c1-160">詳細的結果窗格會顯示，以顯示與下面說明。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![相關性訓練的詳細結果](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="cf8c1-162">標記摘要</span><span class="sxs-lookup"><span data-stu-id="cf8c1-162">Tagging summary</span></span>

 <span data-ttu-id="cf8c1-163">在範例中，如下所示，**摘要的標記**會顯示每個評估、 訓練及執行更新性檔案標記程序總計。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![相關性追蹤的標記摘要](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="cf8c1-165">關鍵字</span><span class="sxs-lookup"><span data-stu-id="cf8c1-165">Keywords</span></span>

<span data-ttu-id="cf8c1-166">關鍵字是唯一的字串、 單字、 片語或序列進階電子文件所識別檔案是否相關的重要指標為檔案中的字數。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="cf8c1-167">「 包含 」 資料行清單關鍵字和標示為相關，檔案中的權數，「 排除 」 欄會列出關鍵字和標示為不可檔案中的加權相關。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="cf8c1-168">進階電子文件會指派誤判或誤判關鍵字加權值。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="cf8c1-169">較高的權數，高到關鍵字上方會出現檔案在批次計算期間指派較高的相關性分數的可能性。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="cf8c1-170">關鍵字進階電子文件清單可用來補充內建專家或間接例行性檢查清單檔案中的任何一點檢閱程序。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="cf8c1-171">訓練進度</span><span class="sxs-lookup"><span data-stu-id="cf8c1-171">Training progress</span></span>

<span data-ttu-id="cf8c1-172">**訓練進度**窗格包含訓練進度圖形和品質指標顯示畫面中，如以下範例所示。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![相關性追蹤訓練進度](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="cf8c1-174">**訓練品質指標**： 顯示標記一致性的評等，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf8c1-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="cf8c1-175">**良好**： 一致標記檔案。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="cf8c1-176">（顯示綠色亮）</span><span class="sxs-lookup"><span data-stu-id="cf8c1-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="cf8c1-177">**中型**： 某些檔案可能不一致標記。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="cf8c1-178">（黃色燈號顯示）</span><span class="sxs-lookup"><span data-stu-id="cf8c1-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="cf8c1-179">**警告**： 許多檔案可能不一致標記。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="cf8c1-180">（紅色亮顯示）</span><span class="sxs-lookup"><span data-stu-id="cf8c1-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="cf8c1-181">**訓練進度 graph**: F 量值與相關性訓練週期的天數之後顯示相關性訓練穩定性的程度。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="cf8c1-182">當我們從左邊向右移動整個圖表信賴區間以縮小，由，F-量值，以及進階電子文件至判斷所展現的穩定性的相關性相關性訓練結果時已進行最佳化。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf8c1-183">相關性使用 f2 鍵，其中重新叫用收到精確度為倍權數 F 度量評量。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="cf8c1-184">針對案例具有高豐富性 （超過 25%) 相關性使用 F1 （1:1 對比率）。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="cf8c1-185">**相關性設定**可以設定 F 量值的比例\>**進階的設定**。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="cf8c1-186">批次計算結果</span><span class="sxs-lookup"><span data-stu-id="cf8c1-186">Batch calculation results</span></span>

<span data-ttu-id="cf8c1-187">**批次計算結果**] 窗格包含已，如下所示的相關性，計分的檔案數目：</span><span class="sxs-lookup"><span data-stu-id="cf8c1-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="cf8c1-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="cf8c1-188">**Success**</span></span>
    
- <span data-ttu-id="cf8c1-189">**空白**： 不包含文字，例如，僅空格/索引標籤</span><span class="sxs-lookup"><span data-stu-id="cf8c1-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="cf8c1-190">**失敗**： 由於過多的大小或無法讀取</span><span class="sxs-lookup"><span data-stu-id="cf8c1-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="cf8c1-191">**Ignored**： 因為過多的大小</span><span class="sxs-lookup"><span data-stu-id="cf8c1-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="cf8c1-192">**Nebulous**： 包含沒有意義的文字或任何功能] 相關問題</span><span class="sxs-lookup"><span data-stu-id="cf8c1-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="cf8c1-193">空的失敗，已略過或 Nebulous 會收到相關性分數的-1。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="cf8c1-194">訓練統計資料</span><span class="sxs-lookup"><span data-stu-id="cf8c1-194">Training statistics</span></span>

<span data-ttu-id="cf8c1-195">**訓練統計資料**] 窗格會顯示的統計資料和進階電子文件相關性訓練結果為基礎的圖形。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![相關性追蹤訓練統計資料](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="cf8c1-197">此檢視顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="cf8c1-197">This view shows the following:</span></span>
  
- <span data-ttu-id="cf8c1-198">**檢閱重新叫用比率**： 在假設情況下線性檢閱得到的結果的相關性根據比較。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="cf8c1-199">檢閱設定大小組特定估計重新叫用。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="cf8c1-200">**參數**： 累計計算集到整個案例檔案母體 relation 檢閱相關的統計資料。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="cf8c1-201">**檢閱**： 若要檢閱的檔案百分比根據此截止。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="cf8c1-202">**回想一下**： 檢閱集中檔案相關的百分比。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="cf8c1-203">**由相關性分數的通訊群組**： 檔案在暗灰色向左顯示如下的截止分數。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="cf8c1-204">工具提示顯示的相關性分數，以及相關的檔案百分比檢閱檔案中設定關聯的總檔案中。</span><span class="sxs-lookup"><span data-stu-id="cf8c1-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cf8c1-205">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf8c1-205">See also</span></span>

[<span data-ttu-id="cf8c1-206">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="cf8c1-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="cf8c1-207">了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="cf8c1-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cf8c1-208">執行並檢閱評估</span><span class="sxs-lookup"><span data-stu-id="cf8c1-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cf8c1-209">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="cf8c1-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cf8c1-210">決策根據結果</span><span class="sxs-lookup"><span data-stu-id="cf8c1-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cf8c1-211">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="cf8c1-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

