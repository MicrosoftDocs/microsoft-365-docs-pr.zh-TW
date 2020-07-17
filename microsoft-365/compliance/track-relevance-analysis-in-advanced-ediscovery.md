---
title: 在高級 eDiscovery 中追蹤相關性分析
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 瞭解如何在「高級 eDiscovery」中查看及解釋「案例問題」的相關性訓練狀態和結果。
ms.openlocfilehash: bf1fe2fc6c0f3ff80fd7e53d55149a61009e2b32
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936216"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="1a7fd-103">在高級 eDiscovery （經典）中追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="1a7fd-103">Track Relevance analysis in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="1a7fd-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="1a7fd-106">在 [Advanced eDiscovery] 中，[相關性追蹤] 索引標籤會顯示在 [標籤] 索引標籤中所執行相關性訓練的計算有效性，並指出在重複訓練程式中要採取的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="1a7fd-107">追蹤相關性訓練狀態</span><span class="sxs-lookup"><span data-stu-id="1a7fd-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="1a7fd-108">如下列 [**問題名稱**] 對話方塊的 [相關性追蹤] 中所示，請查看下列詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="1a7fd-109">**評估**：此進度指標顯示對此點所做的相關性訓練程度已在錯誤的邊界方面達到評估目標。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="1a7fd-110">也會顯示相關的相關性訓練結果的豐富功能。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="1a7fd-111">**訓練**：這種色彩編碼的進度指示器和工具提示顯示會指出相關性訓練結果的穩定性和數值比例，顯示針對每個問題標示的相關性訓練範例數目。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="1a7fd-112">專家會監視反覆運算相關性訓練程式的進度。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="1a7fd-113">**批次計算**：此進度指標會提供有關批次計算完成的資訊。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="1a7fd-114">**下一步**：顯示要執行下一個步驟的建議。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="1a7fd-115">在此範例中，會顯示成功完成的問題評估，並以已完成的色彩進度指示器和核取記號來表示。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="1a7fd-116">標記正在進行中，但仍會將此案例視為不穩定（在工具提示中也會顯示穩定性狀態）。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="1a7fd-117">接下來的步驟建議是「訓練」。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-117">The next step recommendation is "Training".</span></span> 
    
    ![相關性追蹤訓練步驟 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="1a7fd-119">展開的視圖會顯示其他資訊和選項。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="1a7fd-120">顯示的目前錯誤邊界是指目前評估狀態下的召回錯誤邊界，並提供現有（已標記）的評估檔。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="1a7fd-121">您可以在每個問題旁清除 [**評估**] 核取方塊，然後針對「所有問題」，以略過評估階段。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="1a7fd-122">不過，如此一來，就不會發生此問題的統計資料。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="1a7fd-123">> 清除**評估**核取方塊只會在執行評估之前完成。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="1a7fd-124">如果有多個問題存在於案例中，只有在此核取方塊針對每個問題清除時，才會略過評估。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="1a7fd-125">當第一組範例中的評估未完成時，評估可能是進行其他標記的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="1a7fd-126">在 [**相關性** \> **追蹤**] 中，訓練進度指示器和工具提示會指出達到穩定性所需的額外範例數目。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="1a7fd-127">這種評估為您所需的其他訓練提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![相關性追蹤訓練](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="1a7fd-129">當您完成標記時，如果您需要繼續訓練，請按一下 [**訓練**]。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="1a7fd-130">另一組檔案範例會從載入的檔案集產生，以供其他訓練。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="1a7fd-131">然後您會傳回 [標籤] 索引標籤，以標記及訓練更多檔案。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="1a7fd-132">達到穩定的訓練層級</span><span class="sxs-lookup"><span data-stu-id="1a7fd-132">Reaching stable training levels</span></span>

<span data-ttu-id="1a7fd-133">在評估檔已具備穩定的訓練等級之後，就可以使用「高級 eDiscovery」來進行批次計算。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a7fd-134">通常，在三個穩定的訓練範例後，下一步是「批次計算」。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="1a7fd-135">例如，當先前範例中的檔案卷標已變更時，或新增 seed 檔案時，可能會有例外狀況。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="1a7fd-136">執行批次計算</span><span class="sxs-lookup"><span data-stu-id="1a7fd-136">Performing Batch calculation</span></span>

<span data-ttu-id="1a7fd-137">批次計算會在成功完成訓練時，做為下一個步驟（在工具提示中顯示 [進度列] 中的 [已勾選] 和 [穩定] 狀態時，會執行 [穩定訓練] 狀態）。批次計算會將相關性訓練期間所取得的知識套用到整個檔人口，以評估檔案的相關性並指派相關性分數。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="1a7fd-138">當有一個以上的問題時，批次計算會在每個問題中完成。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="1a7fd-139">在批次計算期間，處理所有檔案時便會監控進度。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="1a7fd-140">在這裡，建議的下一個步驟是 "None"，表示目前不需要任何其他的重複相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="1a7fd-141">下一個階段是 [**相關性 \> 決定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="1a7fd-142">如果您想要在批次計算後匯入新的檔案，系統管理員可以將匯入的檔案新增至新的負載。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a7fd-143">如果您在批次計算期間按一下 [**取消**]，程式就會儲存已執行的內容。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="1a7fd-144">如果您再次執行批次計算，程式將會從上次執行的點繼續。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="1a7fd-145">評估標記一致性</span><span class="sxs-lookup"><span data-stu-id="1a7fd-145">Assessing tagging consistency</span></span>

<span data-ttu-id="1a7fd-146">若檔標記中有不一致，它會影響分析。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="1a7fd-147">當結果不是最優或一致性不確定時，可以使用高級 eDiscovery 標記一致性處理常式。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="1a7fd-148">會傳回可能不一致的標記檔案清單，並視需要加以檢查並重新標記。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a7fd-149">在七個或多個訓練四捨五入後，可在**相關性**追蹤問題中查看標記一致性 \> **Track** \> **Issue** \> 。**詳細結果** \> **訓練進度**</span><span class="sxs-lookup"><span data-stu-id="1a7fd-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="1a7fd-150">此項檢查一次只對一個問題進行。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="1a7fd-151">在 [**相關性 \> 追蹤**] 中，展開問題的列。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="1a7fd-152">在 **[下一步]** 的右側，按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="1a7fd-153">選取 [**標記不一致性**做為**下一個步驟]** 選項，7訓練範例後，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="1a7fd-154">選取 [**標記不一致**。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="1a7fd-155">[**標記**] 索引標籤會開啟，顯示不一致的清單，視需要重新標記。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="1a7fd-156">按一下 [**計算**] 提交變更。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="1a7fd-157">標記不一致的下一個步驟是「訓練」。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="1a7fd-158">查看和使用相關性結果</span><span class="sxs-lookup"><span data-stu-id="1a7fd-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="1a7fd-159">在 [**相關性 \> 追蹤**] 索引標籤中，展開問題的列，然後按一下 [**詳細結果**] 旁邊的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="1a7fd-160">隨即會顯示詳細的結果窗格，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![相關性訓練的詳細結果](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="1a7fd-162">標記摘要</span><span class="sxs-lookup"><span data-stu-id="1a7fd-162">Tagging summary</span></span>

 <span data-ttu-id="1a7fd-163">在下列範例中，**標記摘要**會顯示每個評估、訓練及追趕檔標記程式的總數。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![相關性追蹤的標記摘要](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="1a7fd-165">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1a7fd-165">Keywords</span></span>

<span data-ttu-id="1a7fd-166">關鍵字是由「高級 eDiscovery」識別為有關檔案是否相關的重要標記，而由「高級 eDiscovery」所識別之檔案中的唯一字串、word、片語或字詞順序。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="1a7fd-167">標記為相關的檔案中的「包含」欄清單關鍵字和權重，而「排除」欄會列出標示為不相關之檔案中的關鍵字和重量。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="1a7fd-168">「高級 eDiscovery」會指派負數或正值關鍵字權重值。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="1a7fd-169">權重越高，關鍵字顯示所在檔案的可能性越高，在批次計算期間指派的相關性分數越高。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="1a7fd-170">可使用關鍵字的高級 eDiscovery 清單來補充由專家所建的清單，或在檔案檢查程式中的任何一點以間接的健全檢查。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="1a7fd-171">訓練進度</span><span class="sxs-lookup"><span data-stu-id="1a7fd-171">Training progress</span></span>

<span data-ttu-id="1a7fd-172">[**訓練進度**] 窗格包含訓練進度圖表和品質指示器顯示，如以下範例所示。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![相關性追蹤訓練進度](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="1a7fd-174">**訓練品質指示器**：顯示標記一致性的評級，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a7fd-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="1a7fd-175">**不錯**：檔案以一致的方式標記。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="1a7fd-176">（顯示綠色光）</span><span class="sxs-lookup"><span data-stu-id="1a7fd-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="1a7fd-177">**中**：部分檔的標記可能不一致。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="1a7fd-178">（顯示黃色光）</span><span class="sxs-lookup"><span data-stu-id="1a7fd-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="1a7fd-179">**警告**：許多檔的標記可能不一致。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="1a7fd-180">（顯示紅色光）</span><span class="sxs-lookup"><span data-stu-id="1a7fd-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="1a7fd-181">**訓練進度圖**：顯示與 F 量值比較的相關訓練週期數之後，相關性訓練的穩定性程度。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="1a7fd-182">當我們透過圖形從左向右移動時，置信區間會隨著高級 eDiscovery 相關性而縮小及使用，以判斷相關性訓練結果的穩定性。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a7fd-183">「相關性」會使用 F2，其中的召回會以精確度的精確度接收兩倍的值。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="1a7fd-184">針對具有大量豐富的情況（超過25%），相關性使用 F1 （1:1 比率）。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="1a7fd-185">您可以在 [**相關性設定**] [ \> **高級設定**] 中設定 F 測量比率。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="1a7fd-186">批次計算結果</span><span class="sxs-lookup"><span data-stu-id="1a7fd-186">Batch calculation results</span></span>

<span data-ttu-id="1a7fd-187">「**批次計算結果**」窗格包含相關的計分檔數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a7fd-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="1a7fd-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="1a7fd-188">**Success**</span></span>
    
- <span data-ttu-id="1a7fd-189">**空白**：不含任何文字，例如只有空格/定位字元</span><span class="sxs-lookup"><span data-stu-id="1a7fd-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="1a7fd-190">**失敗**：由於大小過高或無法讀取</span><span class="sxs-lookup"><span data-stu-id="1a7fd-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="1a7fd-191">已**忽略**：由於大小過大</span><span class="sxs-lookup"><span data-stu-id="1a7fd-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="1a7fd-192">**Nebulous**：包含無意義的文字或沒有與問題相關的功能</span><span class="sxs-lookup"><span data-stu-id="1a7fd-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="1a7fd-193">空白、失敗、忽略或 Nebulous 將會收到-1 的相關性分數。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="1a7fd-194">訓練統計資料</span><span class="sxs-lookup"><span data-stu-id="1a7fd-194">Training statistics</span></span>

<span data-ttu-id="1a7fd-195">[**訓練統計資料**] 窗格會根據高級 eDiscovery 相關性訓練中的結果，顯示統計資料和曲線圖。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![相關性追蹤訓練統計資料](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="1a7fd-197">此視圖顯示下列專案：</span><span class="sxs-lookup"><span data-stu-id="1a7fd-197">This view shows the following:</span></span>
  
- <span data-ttu-id="1a7fd-198">**複查-召回比率**：根據 hypothetically 線性評論中的相關性分數，比較結果。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="1a7fd-199">若要設定複查集大小，請估計重新叫用。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="1a7fd-200">**參數**：相對於整個案例的檔案人口，對應于審閱集的累計計算統計資料。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="1a7fd-201">**檢查**：根據此截止點所要複查的檔案百分比。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="1a7fd-202">**召回**：審閱集內相關檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="1a7fd-203">**依相關性分數發佈**：深色灰度顯示幕中的檔案低於截止分數。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="1a7fd-204">工具提示會顯示與檔總數相關的審閱檔案集中的相關性分數和相關百分比。</span><span class="sxs-lookup"><span data-stu-id="1a7fd-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1a7fd-205">請參閱</span><span class="sxs-lookup"><span data-stu-id="1a7fd-205">See also</span></span>

[<span data-ttu-id="1a7fd-206">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="1a7fd-206">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1a7fd-207">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="1a7fd-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1a7fd-208">執行和核查評估</span><span class="sxs-lookup"><span data-stu-id="1a7fd-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1a7fd-209">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="1a7fd-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1a7fd-210">根據結果作出決策</span><span class="sxs-lookup"><span data-stu-id="1a7fd-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1a7fd-211">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="1a7fd-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

