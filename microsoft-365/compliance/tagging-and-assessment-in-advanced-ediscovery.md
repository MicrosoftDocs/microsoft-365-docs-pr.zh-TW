---
title: 標記與 Office 365 進階電子文件探索中的評估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: '檢閱執行評估訓練，包括標記檔案，並檢閱在 Office 365 進階電子文件探索中的評估結果的步驟。 '
ms.openlocfilehash: 067f8933bd7fc1286e468d664bf4dbd754e64f00
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077491"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7a594-103">標記與 Office 365 進階電子文件探索中的評估</span><span class="sxs-lookup"><span data-stu-id="7a594-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="7a594-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="7a594-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7a594-106">本節說明進階電子文件相關性評估模組的程序。</span><span class="sxs-lookup"><span data-stu-id="7a594-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="7a594-107">執行評估訓練和分析</span><span class="sxs-lookup"><span data-stu-id="7a594-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="7a594-108">在**相關性\>追蹤**索引標籤上，按一下 [啟動案例評估的**評估**。</span><span class="sxs-lookup"><span data-stu-id="7a594-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="7a594-109">例如範例評估的一組 500 檔案建立在此程序的目的，並顯示 [**標籤**] 索引標籤，其中包含 [標記] 面板、 顯示的檔案內容及其他標記選項。</span><span class="sxs-lookup"><span data-stu-id="7a594-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![相關性標記評量的索引標籤](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="7a594-111">檢閱每個檔案範例中的，決定每個案例的問題，將檔案的相關性標記不使用 Relevance (R) 檔案相關 （編號） 並略過按鈕中 [**標記] 面板**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="7a594-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="7a594-112">評估需要 500 標記的檔案。</span><span class="sxs-lookup"><span data-stu-id="7a594-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="7a594-113">如果檔案 「 略過 」，您會收到標籤的多個檔案。</span><span class="sxs-lookup"><span data-stu-id="7a594-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="7a594-114">之後標記範例中的所有檔案，按一下 [**計算**]。</span><span class="sxs-lookup"><span data-stu-id="7a594-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="7a594-115">評估目前的錯誤邊界豐富性會計算並顯示在 [**相關性追蹤**] 索引標籤中，展開詳細資料，每個問題，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7a594-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="7a594-116">此對話方塊的詳細說明一節 < 檢閱評估結果 >。</span><span class="sxs-lookup"><span data-stu-id="7a594-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![相關性追蹤 - 評量](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="7a594-118">根據預設，我們建議您，繼續進行預設下一個步驟完成評估進度列指示器問題之後，指出評估範例已經過檢閱，以及足夠的相關檔案已標記。</span><span class="sxs-lookup"><span data-stu-id="7a594-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="7a594-119">> 否則如果您想要檢視的**追蹤**] 索引標籤結果與控制項的邊界的錯誤與下一個步驟中，按一下 [**修改\*\*\*\*下一個步驟**的相鄰位置，選取 [**繼續] 評估**，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="7a594-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="7a594-120">按一下 [**修改**右邊的 [**評估**] 核取方塊來檢視及指定每個問題的評估參數。</span><span class="sxs-lookup"><span data-stu-id="7a594-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="7a594-121">每個問題**評量層級**] 對話方塊隨即顯示，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="7a594-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![評量層級案例問題](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="7a594-123">問題的下列參數會計算並顯示 [**評量層級**] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="7a594-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="7a594-124">**目標錯誤邊界的重新叫用來估計**： 根據此值，請先檢閱所需的其他檔案的估計的數量的計算公式。</span><span class="sxs-lookup"><span data-stu-id="7a594-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="7a594-125">用於重新叫用的邊界是大於 75%並且 95%信賴等級。</span><span class="sxs-lookup"><span data-stu-id="7a594-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="7a594-126">**需要額外評定檔**： 指出多少的多個檔案所需如果不符合目前錯誤邊界的需求。</span><span class="sxs-lookup"><span data-stu-id="7a594-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="7a594-127">若要調整目前錯誤邊界並查看 （每個問題） 不同的錯誤邊界的效果：</span><span class="sxs-lookup"><span data-stu-id="7a594-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="7a594-128">在**選取 [發行**] 清單中，選取 [問題]。</span><span class="sxs-lookup"><span data-stu-id="7a594-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="7a594-129">在**目標錯誤邊界的重新叫用來估計**，輸入新值。</span><span class="sxs-lookup"><span data-stu-id="7a594-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="7a594-130">按一下 [**更新的值**若要查看的調整值的影響。</span><span class="sxs-lookup"><span data-stu-id="7a594-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="7a594-131">在 [**評量層級**] 對話方塊，請參閱下列額外的參數和的詳細資訊，請按一下 [**進階**]:</span><span class="sxs-lookup"><span data-stu-id="7a594-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![評量層級案例問題的進階檢視](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="7a594-133">**估計豐富性**： 預估豐富性根據目前的評估結果</span><span class="sxs-lookup"><span data-stu-id="7a594-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="7a594-134">**假定重新叫用**： 根據預設，目標錯誤邊界適用於記得高於 75%。</span><span class="sxs-lookup"><span data-stu-id="7a594-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="7a594-135">如果您想要變更此參數，並控制的重新叫用值的不同範圍上的錯誤限度，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7a594-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="7a594-136">**信賴等級**： 根據預設，建議的錯誤邊界的信賴度是 95%。</span><span class="sxs-lookup"><span data-stu-id="7a594-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="7a594-137">如果您想要變更此參數，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7a594-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="7a594-138">**預期豐富性錯誤邊界**： 指定更新的值，這是錯誤的豐富性預期的邊界之後所有的其他評估檔案都會進行檢閱。</span><span class="sxs-lookup"><span data-stu-id="7a594-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="7a594-139">**需要額外評定檔**： 指定更新的值，檔案達到目標檢閱該需要額外的評估的數目。</span><span class="sxs-lookup"><span data-stu-id="7a594-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="7a594-140">**總評估檔案所需**： 指定更新的值，總評估檔案所需的檢閱。</span><span class="sxs-lookup"><span data-stu-id="7a594-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="7a594-141">**在評估相關檔案的預期數目**： 指定更新的值，預期整個評估之後檢閱所有的其他評估檔案中的相關檔案的數目。</span><span class="sxs-lookup"><span data-stu-id="7a594-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="7a594-142">如果參數會變更，請按一下 [**重新計算的值**，則請]。</span><span class="sxs-lookup"><span data-stu-id="7a594-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="7a594-143">當您完成之後，如果有一個問題時，按一下 **[確定]** 儲存變更 （或**下一個**時，有多個問題來檢視或修改然後**完成**）。</span><span class="sxs-lookup"><span data-stu-id="7a594-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="7a594-144">當有多個問題之後的所有問題已檢閱或調整，,**評量層級： 摘要**] 對話方塊隨即顯示，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="7a594-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![評量層級摘要](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="7a594-146">成功完成時評估，請繼續相關性訓練的下一個階段。</span><span class="sxs-lookup"><span data-stu-id="7a594-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="7a594-147">檢閱評估結果</span><span class="sxs-lookup"><span data-stu-id="7a594-147">Reviewing assessment results</span></span>

<span data-ttu-id="7a594-148">標記評估範例之後，評估結果會計算並顯示在 [相關性追蹤] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="7a594-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="7a594-149">以下結果會顯示在 expanded 追蹤顯示：</span><span class="sxs-lookup"><span data-stu-id="7a594-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="7a594-150">評估目前錯誤邊界的重新叫用來估計</span><span class="sxs-lookup"><span data-stu-id="7a594-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="7a594-151">估計的豐富性</span><span class="sxs-lookup"><span data-stu-id="7a594-151">Estimated richness</span></span>
    
- <span data-ttu-id="7a594-152">（適用於檢閱） 所需的其他評估檔案</span><span class="sxs-lookup"><span data-stu-id="7a594-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="7a594-153">評估目前錯誤邊界是由進階電子文件建議的錯誤邊界。</span><span class="sxs-lookup"><span data-stu-id="7a594-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="7a594-154">顯示 「 額外評定所需的檔案 」 的數字對應至該建議。</span><span class="sxs-lookup"><span data-stu-id="7a594-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="7a594-155">評估進度列指示器顯示完成評估給定的目前的錯誤邊界的層級。</span><span class="sxs-lookup"><span data-stu-id="7a594-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="7a594-156">評估正在進行中，當使用者將標記評量的另一個範例。</span><span class="sxs-lookup"><span data-stu-id="7a594-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="7a594-157">時評估進度列指示器顯示為完成評估，這表示已完成評估範例檢閱，而且有足夠的相關檔案已標記。</span><span class="sxs-lookup"><span data-stu-id="7a594-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="7a594-158">展開的追蹤顯示會顯示建議的下一個步驟、 評估統計資料，以及存取詳細結果。</span><span class="sxs-lookup"><span data-stu-id="7a594-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="7a594-159">豐富性非常低時，到達相關檔案產生很有用的統計資料的最小數目所需的其他評估檔案的數目是非常高。</span><span class="sxs-lookup"><span data-stu-id="7a594-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="7a594-160">進階電子文件會再建議移至訓練。</span><span class="sxs-lookup"><span data-stu-id="7a594-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="7a594-161">評估進度列指示器會有陰影，而沒有統計資料會提供。</span><span class="sxs-lookup"><span data-stu-id="7a594-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="7a594-162">沒有統計根據穩定時，會有的精確度和信賴等級低層級的結果。</span><span class="sxs-lookup"><span data-stu-id="7a594-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="7a594-163">不過，這些結果可以用來尋找相關的檔案，當您不需要知道找到相關檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="7a594-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="7a594-164">同樣地，此狀態可以用於訓練問題與低豐富性相關性分數其中加速存取檔案相關的特定問題。</span><span class="sxs-lookup"><span data-stu-id="7a594-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="7a594-165">在**相關性\>追蹤**索引標籤上，展開此問題： 顯示、 可用的檢視選項如下: > 建議的下一個步驟，例如：**下一步： 標記**可以藉由按一下其右側的 [**修改**] 按鈕略過 （每個問題）然後在**下一個步驟**中選取不同的步驟。</span><span class="sxs-lookup"><span data-stu-id="7a594-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="7a594-166">當尚未完成評估進度列指示器時，評估就會是 [下一步] 建議的選項，以標記更多的評估檔案，並提高統計資料的正確性。</span><span class="sxs-lookup"><span data-stu-id="7a594-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="7a594-167">您可以變更錯誤邊界，並評估其影響中，按一下 [**修改]**，和**評量層級] 對話方塊**，變更**目標錯誤邊界的重新叫用來估計**，然後按一下 [**更新值**的 # A0。</span><span class="sxs-lookup"><span data-stu-id="7a594-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="7a594-168">此外，該對話方塊中，您可以檢視進階的選項]，按一下 [**進階]**。</span><span class="sxs-lookup"><span data-stu-id="7a594-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="7a594-169">您可以藉由按一下 [**檢視]** 檢視其他評量層級的統計資料和其影響 # A0。</span><span class="sxs-lookup"><span data-stu-id="7a594-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="7a594-170">在 [顯示詳細資料結果對話方塊統計資料時，可每個問題，有至少 500 標記的評估檔案，且至少 18 檔案標示為相關的問題。</span><span class="sxs-lookup"><span data-stu-id="7a594-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7a594-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7a594-171">See also</span></span>

[<span data-ttu-id="7a594-172">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="7a594-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7a594-173">了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="7a594-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7a594-174">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="7a594-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7a594-175">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="7a594-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7a594-176">決定根據結果</span><span class="sxs-lookup"><span data-stu-id="7a594-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7a594-177">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="7a594-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

