---
title: 高級 eDiscovery 中的標記與評估
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 請參閱執行評估訓練的步驟，包括標記檔，以及在高級 eDiscovery 中查看評估結果。
ms.openlocfilehash: 57e4e8da0dbeec5e1dba384ae0e62ffb6b3bb03a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936690"
---
# <a name="tagging-and-assessment-in-advanced-ediscovery-classic"></a><span data-ttu-id="0f482-103">高級 eDiscovery （經典）中的標記和評估</span><span class="sxs-lookup"><span data-stu-id="0f482-103">Tagging and Assessment in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="0f482-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="0f482-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="0f482-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="0f482-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="0f482-106">本節說明高級 eDiscovery 相關性評估模組的程式。</span><span class="sxs-lookup"><span data-stu-id="0f482-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="0f482-107">執行評估訓練和分析</span><span class="sxs-lookup"><span data-stu-id="0f482-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="0f482-108">在 [**相關性 \> 追蹤**] 索引標籤中，按一下 [**評估**] 以啟動案例評估。</span><span class="sxs-lookup"><span data-stu-id="0f482-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="0f482-109">例如，在此程式中，會建立一個500檔的範例評估集，並顯示 [標籤] 索引標籤，其中包含 **[標記]** 面板、顯示的檔案內容及其他標記選項。</span><span class="sxs-lookup"><span data-stu-id="0f482-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![相關性標記評量的索引標籤](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="0f482-111">請複查範例中的每個檔案，判斷檔對於每個案例問題的相關性，並使用 [**標記] 面板**窗格中的 [相關性（R）]、[不相關（NR）] 和 [略過] 按鈕來標記檔案。</span><span class="sxs-lookup"><span data-stu-id="0f482-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="0f482-112">評估需要500標記的檔案。</span><span class="sxs-lookup"><span data-stu-id="0f482-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="0f482-113">如果檔案是「略過」，您會收到更多檔案以進行標記。</span><span class="sxs-lookup"><span data-stu-id="0f482-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="0f482-114">在範例中標記所有檔案之後，按一下 [**計算**]。</span><span class="sxs-lookup"><span data-stu-id="0f482-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="0f482-115">在 [**相關性追蹤**] 索引標籤中計算及顯示「評估目前錯誤邊界」和「大量豐富資訊」，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0f482-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="0f482-116">更多有關此對話方塊的詳細資訊，詳見下文的「複查評估結果」一節。</span><span class="sxs-lookup"><span data-stu-id="0f482-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![相關性追蹤 - 評量](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="0f482-118">根據預設，當問題的評估進度指示器已完成時，建議您繼續進行預設的下一個步驟，表示已評審評估範例，並已標記足夠相關的檔案。</span><span class="sxs-lookup"><span data-stu-id="0f482-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="0f482-119">> 否則，如果您想要查看 [**追蹤**] 索引標籤的結果，並控制錯誤和下一個步驟的邊界，請按一下 [**修改**相鄰至**下一個步驟]**，選取 [**繼續評估**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0f482-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="0f482-120">按一下 [**評估**] 核取方塊右邊的 [**修改**]，以查看並指定每個問題的評估參數。</span><span class="sxs-lookup"><span data-stu-id="0f482-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="0f482-121">隨即會顯示每個問題的**評估層級**對話方塊，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="0f482-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![評量層級案例問題](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="0f482-123">在 [**評估層級**] 對話方塊中計算及顯示問題的下列參數：</span><span class="sxs-lookup"><span data-stu-id="0f482-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="0f482-124">**召回評估的目標錯誤邊界**：根據此值，計算出所需審閱之其他檔案的預估數目。</span><span class="sxs-lookup"><span data-stu-id="0f482-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="0f482-125">用於召回的邊界大於75%，且具有95% 信賴等級。</span><span class="sxs-lookup"><span data-stu-id="0f482-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="0f482-126">**需要其他評估**檔案：指出若目前錯誤邊界的需求尚未滿足，則需要多少檔案。</span><span class="sxs-lookup"><span data-stu-id="0f482-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="0f482-127">若要調整目前的錯誤邊界，並查看不同錯誤邊界的影響（每個問題）：</span><span class="sxs-lookup"><span data-stu-id="0f482-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="0f482-128">在 [**選取問題**] 清單中，選取問題。</span><span class="sxs-lookup"><span data-stu-id="0f482-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="0f482-129">在 [**召回評估的目標誤差邊界**] 中，輸入新的值。</span><span class="sxs-lookup"><span data-stu-id="0f482-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="0f482-130">按一下 [**更新值**] 以查看調整的影響。</span><span class="sxs-lookup"><span data-stu-id="0f482-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="0f482-131">按一下 [**評估層級**] 對話方塊中的 [**高級**]，以查看下列其他參數和詳細資料：</span><span class="sxs-lookup"><span data-stu-id="0f482-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![評量層級案例問題的進階檢視](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="0f482-133">**預估豐富**程度：根據目前評估結果估計豐富程度</span><span class="sxs-lookup"><span data-stu-id="0f482-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="0f482-134">**對於假設的召回**：依預設，目標錯誤邊界會套用到高於75% 的召回。</span><span class="sxs-lookup"><span data-stu-id="0f482-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="0f482-135">如果您想要變更此參數，並在不同的召回值範圍中控制錯誤的邊界，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0f482-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="0f482-136">**信賴等級**：根據預設，建議的錯誤邊界為95%。</span><span class="sxs-lookup"><span data-stu-id="0f482-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="0f482-137">若要變更此參數，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0f482-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="0f482-138">**預期的大量豐富的錯誤邊際**：獲得更新的值時，這是大量豐富的錯誤的預期邊界，之後會檢查所有其他的評估檔案。</span><span class="sxs-lookup"><span data-stu-id="0f482-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="0f482-139">**需要其他評估**檔案：針對已更新的值，需要複習以到達目標的其他評估檔案數目。</span><span class="sxs-lookup"><span data-stu-id="0f482-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="0f482-140">**所需的評估檔案總數**：已獲得更新的值、審查所需的評估檔總數。</span><span class="sxs-lookup"><span data-stu-id="0f482-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="0f482-141">**評估中預期相關檔案的數目**：已更新的值，會檢查所有其他評估檔之後整個評估中的預期相關檔案數目。</span><span class="sxs-lookup"><span data-stu-id="0f482-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="0f482-142">如果變更參數，請按一下 [**重新計算值**]。</span><span class="sxs-lookup"><span data-stu-id="0f482-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="0f482-143">當您完成時，請按一下 **[確定]** 以儲存變更（如果有多個問題要查看或修改，請按一下 [**下一步** **]**）。</span><span class="sxs-lookup"><span data-stu-id="0f482-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="0f482-144">在有多個問題時，當所有問題都經過評審或調整之後，就會顯示「**評估層級：摘要**」對話方塊，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="0f482-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![評量層級摘要](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="0f482-146">成功完成評估後，請繼續進行相關性訓練中的下一個階段。</span><span class="sxs-lookup"><span data-stu-id="0f482-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="0f482-147">查看評估結果</span><span class="sxs-lookup"><span data-stu-id="0f482-147">Reviewing assessment results</span></span>

<span data-ttu-id="0f482-148">在標記評估範例後，評估結果會計算並顯示在 [相關性追蹤] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="0f482-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="0f482-149">下列結果會顯示在已展開的軌道顯示中：</span><span class="sxs-lookup"><span data-stu-id="0f482-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="0f482-150">評估召回評估的目前錯誤邊界</span><span class="sxs-lookup"><span data-stu-id="0f482-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="0f482-151">預估豐富豐富</span><span class="sxs-lookup"><span data-stu-id="0f482-151">Estimated richness</span></span>
    
- <span data-ttu-id="0f482-152">需要其他評估檔案（供複查）</span><span class="sxs-lookup"><span data-stu-id="0f482-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="0f482-153">評估目前錯誤邊界是「高級 eDiscovery」所建議的錯誤邊際。</span><span class="sxs-lookup"><span data-stu-id="0f482-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="0f482-154">「需要其他評估檔案」所顯示的數位會對應至該建議。</span><span class="sxs-lookup"><span data-stu-id="0f482-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="0f482-155">評估進度指標會顯示評估的完成程度（指定目前的錯誤邊界）。</span><span class="sxs-lookup"><span data-stu-id="0f482-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="0f482-156">當評估進行中時，使用者將會標記另一個評估範例。</span><span class="sxs-lookup"><span data-stu-id="0f482-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="0f482-157">當評估進度指示器顯示評估為完成時，表示評估範例審閱已完成，而且有足夠的相關檔案已標記。</span><span class="sxs-lookup"><span data-stu-id="0f482-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="0f482-158">展開的曲目顯示會顯示建議的下一個步驟、評估統計資料，以及對詳細結果的存取。</span><span class="sxs-lookup"><span data-stu-id="0f482-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="0f482-159">當豐富程度非常低時，需要的額外評估檔案數目若要產生有用的統計資料，就會非常高。</span><span class="sxs-lookup"><span data-stu-id="0f482-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="0f482-160">「高級 eDiscovery」會建議您移至訓練。</span><span class="sxs-lookup"><span data-stu-id="0f482-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="0f482-161">評估進度指示器會變成陰影，不會提供任何統計資料。</span><span class="sxs-lookup"><span data-stu-id="0f482-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="0f482-162">在缺少以統計為基礎的穩定化時，將會有較低的精確度和信賴等級的結果。</span><span class="sxs-lookup"><span data-stu-id="0f482-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="0f482-163">不過，當您不需要知道所找到之相關檔案的百分比時，可以使用這些結果來尋找相關檔案。</span><span class="sxs-lookup"><span data-stu-id="0f482-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="0f482-164">同樣地，這種狀態也可以用來訓練低豐富的問題，在此情況下，相關性分數可以加速與特定問題相關的檔案存取。</span><span class="sxs-lookup"><span data-stu-id="0f482-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="0f482-165">在 [**相關性 \> 追蹤**] 索引標籤中，展開的 [問題顯示] 中，可使用下列查看選項： > 建議的下一個步驟（如 **[下一步]）：** 按一下其右邊的 [**修改**] 按鈕，然後選取**下一個步驟**中的其他步驟，便可略過（每個問題）標記。</span><span class="sxs-lookup"><span data-stu-id="0f482-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="0f482-166">當評估進度指示器尚未完成時，評估會是下一個建議的選項，以標記更多評估檔案，並增加統計資料的準確性。</span><span class="sxs-lookup"><span data-stu-id="0f482-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="0f482-167">> 您可以變更錯誤邊界並評估其影響，方法是按一下 [**修改**]，然後在 [**評估層級] 對話方塊**中變更**目標誤差邊界，以進行召回評估**，然後按一下 [**更新值**]。</span><span class="sxs-lookup"><span data-stu-id="0f482-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="0f482-168">此外，在此對話方塊中，您可以按一下 [**高級**] 以查看高級選項。</span><span class="sxs-lookup"><span data-stu-id="0f482-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="0f482-169">> 您可以按一下 [ **view**] （查看）以查看其他評估層級統計資料及其影響。</span><span class="sxs-lookup"><span data-stu-id="0f482-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="0f482-170">在 [顯示的詳細結果] 對話方塊中，每個問題都有至少500標記的評估檔案，且至少有18個檔案標示為相關問題的統計資料。</span><span class="sxs-lookup"><span data-stu-id="0f482-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0f482-171">請參閱</span><span class="sxs-lookup"><span data-stu-id="0f482-171">See also</span></span>

[<span data-ttu-id="0f482-172">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="0f482-172">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0f482-173">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="0f482-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0f482-174">標記與相關性訓練</span><span class="sxs-lookup"><span data-stu-id="0f482-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0f482-175">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="0f482-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0f482-176">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="0f482-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0f482-177">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="0f482-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

