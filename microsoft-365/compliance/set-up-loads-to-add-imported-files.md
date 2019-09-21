---
title: 設定載入要在 Office 365 進階電子文件探索中新增匯入的檔案
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: '檢閱步驟將匯入的檔案新增至最後一個定義的負載或檔案，再執行 Office 365 進階電子文件探索中的相關性訓練的批次。  '
ms.openlocfilehash: 65e022680cc0bd39bbca3e05a4e3b6d24da1b2ad
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077597"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="37e34-103">設定載入要在 Office 365 進階電子文件探索中新增匯入的檔案</span><span class="sxs-lookup"><span data-stu-id="37e34-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="37e34-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="37e34-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="37e34-106">在進階電子文件，負載是新的批次的檔案新增至案例。</span><span class="sxs-lookup"><span data-stu-id="37e34-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="37e34-107">根據預設，定義一個負載，並加入所有匯入的檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="37e34-108">在執行之前相關性訓練，匯入的檔案必須新增的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="37e34-109">請考量下列案例：</span><span class="sxs-lookup"><span data-stu-id="37e34-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="37e34-110">新的檔案已知會類似於先前檔案載入至案例資料庫，或檔案的前一個負載隨機集從檔案集合。</span><span class="sxs-lookup"><span data-stu-id="37e34-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="37e34-111">在此情況下，將新增至目前的檔案載入的匯入的檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="37e34-112">新的檔案會不同於先前的項目 （例如，從不同的來源），或具有他們正在相似或不同先前載入沒有先備知識。</span><span class="sxs-lookup"><span data-stu-id="37e34-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="37e34-113">在此案例中，將新增至新的檔案載入的匯入的檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="37e34-114">進階電子文件會這辨識為循環負載案例，叫用執行更新性的程序，鎖定相關性訓練和批次計算，直到完成 Catch-up 時，新的負載是整合和訓練。</span><span class="sxs-lookup"><span data-stu-id="37e34-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="37e34-115">將匯入的檔案新增至目前的負載</span><span class="sxs-lookup"><span data-stu-id="37e34-115">Adding imported files to the current load</span></span>

<span data-ttu-id="37e34-116">所有匯入的檔案必須新增至進階電子文件中處理負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="37e34-117">匯入的檔案會新增至最後一個定義的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="37e34-118">如果您稍後匯入其他檔案，他們也必須新增的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="37e34-119">在**相關性\>相關性設定**索引標籤上，選取**負載**。</span><span class="sxs-lookup"><span data-stu-id="37e34-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![相關性設定負載索引標籤](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="37e34-121">**包含檔案**： 選取要包含的檔案] 選項。</span><span class="sxs-lookup"><span data-stu-id="37e34-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="37e34-122">根據預設，將檔案新增至目前的負載根據"All files"母體。</span><span class="sxs-lookup"><span data-stu-id="37e34-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="37e34-123">將所有可用的 culled 的檔案載入至相關性。</span><span class="sxs-lookup"><span data-stu-id="37e34-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="37e34-124">如果您打算載入只有部分的可用的檔案，請先洽詢支援，如載入子集可以有不利的影響相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="37e34-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="37e34-125">在**載入管理**] 下，選取負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="37e34-126">按一下 [**新增檔案**]。</span><span class="sxs-lookup"><span data-stu-id="37e34-126">Click **Add files**.</span></span> <span data-ttu-id="37e34-127">將檔案新增至負載，並會顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="37e34-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="37e34-128">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37e34-128">Click **OK**.</span></span>
    
<span data-ttu-id="37e34-129">檔案的訓練檔案現在在進階電子文件探索相關性處理。</span><span class="sxs-lookup"><span data-stu-id="37e34-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="37e34-130">編輯案例內的負載名稱</span><span class="sxs-lookup"><span data-stu-id="37e34-130">Editing a load name within a case</span></span>

<span data-ttu-id="37e34-131">如果變更負載名稱，建議使用非常重要的大小寫名稱。</span><span class="sxs-lookup"><span data-stu-id="37e34-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="37e34-132">在**相關性\>相關性設定**索引標籤上，選取**負載**。</span><span class="sxs-lookup"><span data-stu-id="37e34-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="37e34-133">從**負載管理**] 清單中，選取負載並按一下 [**編輯**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="37e34-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="37e34-134">編輯負載視窗隨即出現。</span><span class="sxs-lookup"><span data-stu-id="37e34-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="37e34-135">輸入變更，然後再按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="37e34-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="37e34-136">將匯入的檔案新增至新的負載</span><span class="sxs-lookup"><span data-stu-id="37e34-136">Adding imported files to a new load</span></span>

<span data-ttu-id="37e34-137">啟動相關性訓練或執行批次計算之後, 您可能想要匯入及處理其他一組檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="37e34-138">期間 Catch-up，您可以建立、 標記，並分析 Catch-up 組。</span><span class="sxs-lookup"><span data-stu-id="37e34-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="37e34-139">進階電子文件比較其評估的相關和非相關檔案中先前載入新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="37e34-140">根據結果，會提示您進行 Catch-up 決策，若有必要，和進階電子文件探索提供建議根據給付的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="37e34-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="37e34-141">滾動載入及執行更新性功能，如下所示而有所不同：</span><span class="sxs-lookup"><span data-stu-id="37e34-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="37e34-142">當批次計算後匯入新的檔案載入時，進階電子文件會決定到什麼程度檔案可分為下列類別之一：</span><span class="sxs-lookup"><span data-stu-id="37e34-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="37e34-143">類似 （同質性）： 新的自訂一次相關性訓練，則不需要與從舊的負載累算的知識可套用 「 現狀 」 至新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="37e34-144">Distinct （異質性）： 新的自訂一次相關性訓練是必要的且無法套用累算方式從先前載入的知識。</span><span class="sxs-lookup"><span data-stu-id="37e34-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="37e34-145">這些字詞參照的層次的相似性的負載之間並不是在載入的檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="37e34-146">當匯入新的檔案負載期間 （之前批次計算） 的相關性訓練，Catch-up 可讓您繼續聯合的檔案設定相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="37e34-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="37e34-147">進階電子文件不評估新的負載是相似或不同於先前的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="37e34-148">它只收集新負載的相關資訊，並啟用相關性訓練，繼續在新與前一組檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="37e34-149">當有相關性訓練中的多個問題以及問題批次計算後時，Catch-up 程序會執行一次所有問題皆適用，結果會計算並顯示每個問題。</span><span class="sxs-lookup"><span data-stu-id="37e34-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="37e34-150">Catch-up 樣本大小可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="37e34-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="37e34-151">它取決於的新負載與先前載入的相對大小和完成之前新增新的負載的樣本數。</span><span class="sxs-lookup"><span data-stu-id="37e34-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="37e34-152">Catch-up 範例通常是一組 200 到 2000 檔案從新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="37e34-153">Catch-up 會停止任何其他工作，並需要個別的檔案標記及檢閱。</span><span class="sxs-lookup"><span data-stu-id="37e34-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="37e34-154">因此，您可以降低額外負荷當您在大型的批次中新增新的檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="37e34-155">新增新的檔案負載，使用執行更新性和循環載入</span><span class="sxs-lookup"><span data-stu-id="37e34-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="37e34-156">在**相關性\>相關性設定**索引標籤上，選取**負載**。</span><span class="sxs-lookup"><span data-stu-id="37e34-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="37e34-157">**載入管理**] 下按一下 [**+** 圖示以新增負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="37e34-158">會顯示確認訊息。</span><span class="sxs-lookup"><span data-stu-id="37e34-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="37e34-159">請按一下 [是]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="37e34-159">Click **Yes** to continue.</span></span> <span data-ttu-id="37e34-160">**新增新負載**] 對話方塊隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="37e34-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="37e34-161">如果動作所執行的舊的負載，您只能加入新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="37e34-162">在 [**新增新負載**] 對話方塊中，**載入名稱**與**描述**中輸入資訊，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="37e34-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="37e34-163">進階電子文件會新增新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="37e34-164">若要匯入新的負載檔案，請按一下 [**新增檔案**。</span><span class="sxs-lookup"><span data-stu-id="37e34-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="37e34-165">所有的新檔案新增到此負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-165">All new files are added to this load.</span></span> <span data-ttu-id="37e34-166">進階電子文件匯入檔案之後，它會辨識循環負載案例，並指出 Catch-up 作為下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="37e34-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="37e34-167">按一下 [ **Catch-up** ] 對話方塊的底部執行分析藍本。</span><span class="sxs-lookup"><span data-stu-id="37e34-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="37e34-168">單一 Catch-up 組，通常包含 200 到 2000 檔案與新的負載，會建立允許同時檔案標記的所有問題。</span><span class="sxs-lookup"><span data-stu-id="37e34-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="37e34-169">載入已相似或不同、 進階電子文件是否已合併或自動分割負載及相關資訊，並提供詳細資料有關在下一個步驟的處理。</span><span class="sxs-lookup"><span data-stu-id="37e34-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="37e34-170">您可以接著標記檔案並執行的計算作業。</span><span class="sxs-lookup"><span data-stu-id="37e34-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="37e34-171">標記可讓至判斷負載是否相似或不同的相關性，並可讓您繼續使用上一組新的檔案。</span><span class="sxs-lookup"><span data-stu-id="37e34-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="37e34-172">檢閱 Catch-up 設定之後，請檢視**相關性\>追蹤**Catch-up 結果。</span><span class="sxs-lookup"><span data-stu-id="37e34-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="37e34-173">如果新的檔案載入已新增相關性訓練期間**繼續訓練**（亦即，此問題： 有未尚未經過批次計算），為下一個步驟中的，不論 Catch-up 結果。</span><span class="sxs-lookup"><span data-stu-id="37e34-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="37e34-174">新增與先前載入的處理為一個負載，並相關性訓練繼續聯合組。</span><span class="sxs-lookup"><span data-stu-id="37e34-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="37e34-175">您現在已完成此程序，並可繼續進行相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="37e34-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="37e34-176">如果批次計算後，已新增新的負載，進行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="37e34-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="37e34-177">批次計算後新增新的負載，進階電子文件會決定新負載是否相似或不同於先前的負載，如下所示：</span><span class="sxs-lookup"><span data-stu-id="37e34-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="37e34-178">如果負載找不到要會類似： 是必要的任何其他的相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="37e34-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="37e34-179">儀表板會顯示建議的下一步是執行 \* \* 批次計算 \* \* 再次來計算相關性分數的新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="37e34-180">找不到要很類似，因此可以在新的檔案執行上一個類別器分析的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="37e34-181">如果設為不同找不到負載： 更相關性訓練的必要與下一個步驟是 Catch-up 決策。</span><span class="sxs-lookup"><span data-stu-id="37e34-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="37e34-182">選取 Catch-up 決策如下所示：</span><span class="sxs-lookup"><span data-stu-id="37e34-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="37e34-183">如果您選取 [**合併負載**，進階電子文件合併訓練集前一筆和新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="37e34-184">雖然批次計算八月份第一次載入，但需要更多的訓練。</span><span class="sxs-lookup"><span data-stu-id="37e34-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="37e34-185">繼續一起訓練新增與先前的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="37e34-186">批次計算再執行一次，應忽略先前的批次計算分數。</span><span class="sxs-lookup"><span data-stu-id="37e34-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="37e34-187">相關性分數的現有負載可以重新計算，例如，當現有的檔案載入檢閱尚未啟動時，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="37e34-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="37e34-188">如果您選取**分割載入**，繼續相關性訓練僅在新的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="37e34-189">在此情況下，先前的批次計算分數會保持原樣。</span><span class="sxs-lookup"><span data-stu-id="37e34-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="37e34-190">選擇此選項的現有載入現有的相關性分數無法重新計算，例如，如果已經啟動檢閱現有的負載。</span><span class="sxs-lookup"><span data-stu-id="37e34-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="37e34-191">相關性分數從這個點 + 分開管理，且無法合併。</span><span class="sxs-lookup"><span data-stu-id="37e34-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="37e34-192">按一下 [**繼續訓練**。</span><span class="sxs-lookup"><span data-stu-id="37e34-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="37e34-193">另請參閱</span><span class="sxs-lookup"><span data-stu-id="37e34-193">See also</span></span>

[<span data-ttu-id="37e34-194">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="37e34-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="37e34-195">定義問題並指派使用者</span><span class="sxs-lookup"><span data-stu-id="37e34-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="37e34-196">定義反白顯示的關鍵字和進階選項</span><span class="sxs-lookup"><span data-stu-id="37e34-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

