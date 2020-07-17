---
title: 在高級電子檔探索中設定載入以新增匯入的檔案
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 在 [高級 eDiscovery] 中執行相關性訓練之前，請先參閱步驟，將匯入的檔案新增至檔案的最後一個已定義的負載（或批次處理）。
ms.openlocfilehash: fc05111d9193a935158b4b00a14717877ae148a7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936814"
---
# <a name="set-up-loads-to-add-imported-files-in-advanced-ediscovery-classic"></a><span data-ttu-id="17ad7-103">在 [Advanced eDiscovery （傳統）] 中設定載入匯入檔案的負載</span><span class="sxs-lookup"><span data-stu-id="17ad7-103">Set up loads to add imported files in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="17ad7-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="17ad7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="17ad7-106">在 [Advanced eDiscovery] 中，load 是新增至案例的新批次檔案。</span><span class="sxs-lookup"><span data-stu-id="17ad7-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="17ad7-107">依預設，會定義一個負載，並新增所有匯入的檔案。</span><span class="sxs-lookup"><span data-stu-id="17ad7-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="17ad7-108">在執行相關性訓練之前，必須先將匯入的檔案新增到負載中。</span><span class="sxs-lookup"><span data-stu-id="17ad7-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="17ad7-109">請考量下列案例：</span><span class="sxs-lookup"><span data-stu-id="17ad7-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="17ad7-110">新檔案已知類似先前載入至案例資料庫的檔案，或先前的檔案載入是從檔案集合隨機設定。</span><span class="sxs-lookup"><span data-stu-id="17ad7-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="17ad7-111">在此範例中，將匯入的檔案新增至目前的檔案負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="17ad7-112">新檔案與舊版不同（例如，從不同的來源），或是先前的負載很類似或不同于先前的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="17ad7-113">在此案例中，將匯入的檔案新增至新的檔負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="17ad7-114">「高級 eDiscovery」會將這視為滾動負載案例、呼叫追趕程式、鎖定相關性訓練和批次計算，直到完成追趕，而且新的負載已整合且訓練有素。</span><span class="sxs-lookup"><span data-stu-id="17ad7-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="17ad7-115">將匯入檔新增至目前的負載</span><span class="sxs-lookup"><span data-stu-id="17ad7-115">Adding imported files to the current load</span></span>

<span data-ttu-id="17ad7-116">所有匯入的檔案必須新增至要在高級 eDiscovery 中處理的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="17ad7-117">匯入的檔案會新增至最後定義的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="17ad7-118">如果您稍後匯入其他檔案，也必須將其新增至負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="17ad7-119">在 [**相關性 \> 關聯性設定**] 索引標籤中，選取 [**載入**]。</span><span class="sxs-lookup"><span data-stu-id="17ad7-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![相關性設定負載索引標籤](../media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="17ad7-121">**包含**檔案：選取要包含的檔案選項。</span><span class="sxs-lookup"><span data-stu-id="17ad7-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="17ad7-122">根據預設，將檔案新增至目前的負載是以「所有檔案」的人口。</span><span class="sxs-lookup"><span data-stu-id="17ad7-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="17ad7-123">將所有可用的 culled 檔案載入至關聯性。</span><span class="sxs-lookup"><span data-stu-id="17ad7-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="17ad7-124">如果您計畫只載入可用檔案的子集，請先諮詢支援人員，因為載入子集可能會對相關性訓練產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="17ad7-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="17ad7-125">在 [**載入管理**] 中，選取負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="17ad7-126">按一下 [**新增**檔案]。</span><span class="sxs-lookup"><span data-stu-id="17ad7-126">Click **Add files**.</span></span> <span data-ttu-id="17ad7-127">隨即會在載入中新增檔案，並顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="17ad7-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="17ad7-128">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="17ad7-128">Click **OK**.</span></span>
    
<span data-ttu-id="17ad7-129">您現在可以在高級 eDiscovery 相關性中處理檔案，以進行檔訓練。</span><span class="sxs-lookup"><span data-stu-id="17ad7-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="17ad7-130">編輯案例內的負載名稱</span><span class="sxs-lookup"><span data-stu-id="17ad7-130">Editing a load name within a case</span></span>

<span data-ttu-id="17ad7-131">若要變更載入名稱，建議使用對此案例很重要的名稱。</span><span class="sxs-lookup"><span data-stu-id="17ad7-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="17ad7-132">在 [**相關性 \> 關聯性設定**] 索引標籤中，選取 [**載入**]。</span><span class="sxs-lookup"><span data-stu-id="17ad7-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="17ad7-133">從 [**載入管理**] 清單中，選取負載，然後按一下 [**編輯**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="17ad7-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="17ad7-134">隨即會顯示 [編輯載入] 視窗。</span><span class="sxs-lookup"><span data-stu-id="17ad7-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="17ad7-135">輸入變更，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="17ad7-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="17ad7-136">將匯入的檔案新增至新的負載</span><span class="sxs-lookup"><span data-stu-id="17ad7-136">Adding imported files to a new load</span></span>

<span data-ttu-id="17ad7-137">開始相關性訓練或執行批次計算之後，您可能會想要匯入並處理一組額外的檔案。</span><span class="sxs-lookup"><span data-stu-id="17ad7-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="17ad7-138">在追趕過程中，您可以建立、標記和分析追趕集。</span><span class="sxs-lookup"><span data-stu-id="17ad7-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="17ad7-139">「高級 eDiscovery」會比較其對新負載中的相關和非相關檔案對先前的負載的評估。</span><span class="sxs-lookup"><span data-stu-id="17ad7-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="17ad7-140">根據結果，系統會提示您進行追趕決策（如有必要），以及高級 eDiscovery 根據累計相關性資訊提供建議。</span><span class="sxs-lookup"><span data-stu-id="17ad7-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="17ad7-141">滾動負載和追趕功能的變化如下：</span><span class="sxs-lookup"><span data-stu-id="17ad7-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="17ad7-142">當您在批次計算後匯入新的檔案時，高級 eDiscovery 會決定檔屬於下列其中一個類別：</span><span class="sxs-lookup"><span data-stu-id="17ad7-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="17ad7-143">類似（同類）：不需要新的自訂舍入訓練，而且從先前的負載累算的知識也可以套用至新的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="17ad7-144">Distinct （異類）：需要新的自訂舍入訓練，且無法套用來自上一個負載的知識。</span><span class="sxs-lookup"><span data-stu-id="17ad7-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="17ad7-145">這些字詞是指的是各載入間的檔相似性層級，而不是在負載內。</span><span class="sxs-lookup"><span data-stu-id="17ad7-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="17ad7-146">在相關性訓練期間匯入新的檔載入時（批次計算之前），追趕可讓您在美國檔組上繼續相關訓練。</span><span class="sxs-lookup"><span data-stu-id="17ad7-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="17ad7-147">「高級 eDiscovery」不會估計新的負載與先前的負載是否類似或不同。</span><span class="sxs-lookup"><span data-stu-id="17ad7-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="17ad7-148">它只會收集有關新負載的資訊，並啟用相關性訓練，以繼續執行新的和前一組檔案。</span><span class="sxs-lookup"><span data-stu-id="17ad7-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="17ad7-149">當相關性訓練中有多個問題和批次計算後的問題，針對所有問題都會執行一次追趕處理常式，並針對每個問題計算及顯示結果。</span><span class="sxs-lookup"><span data-stu-id="17ad7-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="17ad7-150">追趕範例的大小可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="17ad7-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="17ad7-151">這取決於新負載的大小與上一個負載的相對，以及在新增新的負載之前所完成的範例數目。</span><span class="sxs-lookup"><span data-stu-id="17ad7-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="17ad7-152">此追趕範例通常是一組200到2000的檔案，來自新的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="17ad7-153">追趕會停止任何其他工作，並且需要個別的檔標記和審閱。</span><span class="sxs-lookup"><span data-stu-id="17ad7-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="17ad7-154">因此，您可以在大量批次新增檔案時降低系統開銷。</span><span class="sxs-lookup"><span data-stu-id="17ad7-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="17ad7-155">使用追趕和滾動負載新增新的檔載入</span><span class="sxs-lookup"><span data-stu-id="17ad7-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="17ad7-156">在 [**相關性 \> 關聯性設定**] 索引標籤中，選取 [**載入**]。</span><span class="sxs-lookup"><span data-stu-id="17ad7-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="17ad7-157">在 [**載入管理**] 底下，按一下 **+** 圖示以新增負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="17ad7-158">隨即顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="17ad7-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="17ad7-159">按一下 **[是]** 以繼續。</span><span class="sxs-lookup"><span data-stu-id="17ad7-159">Click **Yes** to continue.</span></span> <span data-ttu-id="17ad7-160">隨即會顯示 [**新增載入**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="17ad7-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="17ad7-161">只有在先前的負載中執行動作時，才可以加入新的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="17ad7-162">在 [**新增負載**] 對話方塊的 [**載入名稱**與**描述**] 中輸入資訊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="17ad7-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="17ad7-163">「高級 eDiscovery」會新增新的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="17ad7-164">若要匯入新的載入檔案，請按一下 [**新增**檔案]。</span><span class="sxs-lookup"><span data-stu-id="17ad7-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="17ad7-165">所有新檔案都會新增至此負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-165">All new files are added to this load.</span></span> <span data-ttu-id="17ad7-166">在高級 eDiscovery 匯入檔之後，它會辨識「滾動負載」案例，並指出做為下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="17ad7-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="17ad7-167">按一下對話方塊底部的 [**追趕**] 以執行案例。</span><span class="sxs-lookup"><span data-stu-id="17ad7-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="17ad7-168">單一的追趕集（一般會包含200至2000檔來自新的負載）是針對所有允許同時進行檔標記的問題而建立的。</span><span class="sxs-lookup"><span data-stu-id="17ad7-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="17ad7-169">會提供詳細資料，告知載入是類似還是截然不同，是否要自動合併或分割負載，以及在下一個步驟中處理的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="17ad7-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="17ad7-170">然後您就可以標記檔案並執行計算作業。</span><span class="sxs-lookup"><span data-stu-id="17ad7-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="17ad7-171">標記可讓相關性判斷載入是否類似或截然不同，可讓您繼續處理一組新的檔案。</span><span class="sxs-lookup"><span data-stu-id="17ad7-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="17ad7-172">檢查追趕集之後，請查看追趕結果的**相關性 \> 追蹤**。</span><span class="sxs-lookup"><span data-stu-id="17ad7-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="17ad7-173">如果在相關性訓練期間新增新的檔案負載（也就是說，此問題尚未透過批次計算出），則請**繼續訓練**為下一個步驟，不論追趕的結果為何。</span><span class="sxs-lookup"><span data-stu-id="17ad7-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="17ad7-174">新的和先前的負載會隨著一次的負載和關聯性訓練進行處理，繼續進行。</span><span class="sxs-lookup"><span data-stu-id="17ad7-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="17ad7-175">您現在已完成此程式，可以繼續相關訓練。</span><span class="sxs-lookup"><span data-stu-id="17ad7-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="17ad7-176">如果新的負載是在批次計算後新增的，請繼續執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="17ad7-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="17ad7-177">針對在批次計算後新增的負載，高級 eDiscovery 會判斷新的負載與先前的負載是否類似或截然不同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="17ad7-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="17ad7-178">如果發現負載類似：無需進行其他相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="17ad7-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="17ad7-179">儀表板顯示建議的下一步是執行 \* \* 批次計算 \* \*，以計算新負載的相關性分數。</span><span class="sxs-lookup"><span data-stu-id="17ad7-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="17ad7-180">已發現負載類似，所以可以在新的檔案上執行先前的分類器分析。</span><span class="sxs-lookup"><span data-stu-id="17ad7-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="17ad7-181">若發現負載截然不同：有必要進行相關訓練，下一步是追趕決定。</span><span class="sxs-lookup"><span data-stu-id="17ad7-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="17ad7-182">請選取下列專案的追趕決策：</span><span class="sxs-lookup"><span data-stu-id="17ad7-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="17ad7-183">如果您選取 [**合併載入**]，Advanced eDiscovery 便會合並訓練集的先前和新負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="17ad7-184">雖然第一次載入是透過成批計算，但需要進行更多訓練。</span><span class="sxs-lookup"><span data-stu-id="17ad7-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="17ad7-185">繼續訓練新的和先前的負載。</span><span class="sxs-lookup"><span data-stu-id="17ad7-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="17ad7-186">然後再執行批次計算，並且應該忽略先前的批次計算分數。</span><span class="sxs-lookup"><span data-stu-id="17ad7-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="17ad7-187">當可重新計算現有負載的相關性分數時（例如，當審閱現有的檔載入尚未開始時），請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="17ad7-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="17ad7-188">如果您選取 [**分割載入**]，只會在新的負載上繼續相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="17ad7-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="17ad7-189">在此情況下，先前批次計算分數會維持原樣。</span><span class="sxs-lookup"><span data-stu-id="17ad7-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="17ad7-190">當現有負載的現有相關性分數無法重新計算時（例如，如果已開始審核現有的負載），請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="17ad7-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="17ad7-191">相關性分數會獨立于此點向前管理，而且無法合併。</span><span class="sxs-lookup"><span data-stu-id="17ad7-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="17ad7-192">按一下 [**繼續訓練**]。</span><span class="sxs-lookup"><span data-stu-id="17ad7-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="17ad7-193">請參閱</span><span class="sxs-lookup"><span data-stu-id="17ad7-193">See also</span></span>

[<span data-ttu-id="17ad7-194">Office 365 進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="17ad7-194">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="17ad7-195">定義問題並指派使用者</span><span class="sxs-lookup"><span data-stu-id="17ad7-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="17ad7-196">定義反白顯示的關鍵字和進階選項</span><span class="sxs-lookup"><span data-stu-id="17ad7-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

