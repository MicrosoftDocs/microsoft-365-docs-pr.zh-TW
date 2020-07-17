---
title: 在高級電子檔探索中查看進程模組結果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 瞭解如何在高級 eDiscovery 中尋找處理模組的結果，包括任務狀態和流程摘要。
ms.openlocfilehash: 26ef87c762fc5c77f2374978bf4a425940dd5f37
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936166"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="23dd9-103">在高級 eDiscovery （古典）中查看進程模組結果</span><span class="sxs-lookup"><span data-stu-id="23dd9-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="23dd9-104">啟動**準備** \> **Process**程式後，您可以查看進度和結果。</span><span class="sxs-lookup"><span data-stu-id="23dd9-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="23dd9-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="23dd9-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="23dd9-107">進程任務狀態</span><span class="sxs-lookup"><span data-stu-id="23dd9-107">Process task status</span></span>

<span data-ttu-id="23dd9-108">在 [**準備** \> **處理** \> **結果**] 中，頁面會顯示目前的狀態（如果是正在執行的處理常式）或 [最後一個處理的狀態] 工作狀態，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="23dd9-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![處理序模組的工作狀態](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="23dd9-110">顯示的工作可能會因選取的處理選項而異。</span><span class="sxs-lookup"><span data-stu-id="23dd9-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="23dd9-111">**庫存**：高級電子檔探索會迴圈查看所有選取進行處理的檔案，並執行基本資料收集。</span><span class="sxs-lookup"><span data-stu-id="23dd9-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="23dd9-112">**計算簽名**：計算 MD5 數位簽章。</span><span class="sxs-lookup"><span data-stu-id="23dd9-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="23dd9-113">複合詞**提取**：以遞迴方式從複合檔案（例如，PST，ZIP，MSG）解壓縮內封或包含的檔案。</span><span class="sxs-lookup"><span data-stu-id="23dd9-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="23dd9-114">解壓縮的檔案會儲存在案例的 case 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="23dd9-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="23dd9-115">**同步處理資料庫**：內部資料庫處理常式。</span><span class="sxs-lookup"><span data-stu-id="23dd9-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="23dd9-116">檔案**複本**：複製處理檔案。</span><span class="sxs-lookup"><span data-stu-id="23dd9-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="23dd9-117">即使已選取 [高級複製檔案] 選項，此工作還是會一直顯示。</span><span class="sxs-lookup"><span data-stu-id="23dd9-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="23dd9-118">**文字提取**：有原生檔案時，「高級 eDiscovery」會使用 DTSearch 從這些檔案中解壓縮文字。</span><span class="sxs-lookup"><span data-stu-id="23dd9-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="23dd9-119">這些檔案的解壓縮文字會儲存為案例資料夾中的文字檔。</span><span class="sxs-lookup"><span data-stu-id="23dd9-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="23dd9-120">**更新中繼資料**：處理已載入的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="23dd9-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="23dd9-121">**完成**：處理已載入之案例檔案之資料的內部處理（例如，識別錯誤和成功檔案）。</span><span class="sxs-lookup"><span data-stu-id="23dd9-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="23dd9-122">工作狀態：顯示在任務完成之後。</span><span class="sxs-lookup"><span data-stu-id="23dd9-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="23dd9-123">在執行工作時，會顯示 [執行持續時間]。</span><span class="sxs-lookup"><span data-stu-id="23dd9-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23dd9-124">已完成的工作也可以包含完成處理的檔案或發生錯誤的檔案的總數。</span><span class="sxs-lookup"><span data-stu-id="23dd9-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="23dd9-125">「取消」提供回滾選項，可停止程式的執行，然後回到先前的資料填充或儲存的已處理資料。</span><span class="sxs-lookup"><span data-stu-id="23dd9-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="23dd9-126">Rollback 會清除所有已處理的資料。</span><span class="sxs-lookup"><span data-stu-id="23dd9-126">Rollback clears all processed data.</span></span> <span data-ttu-id="23dd9-127">如果您不想要處理的資料遺失（例如，您計畫重新載入這些檔案），請選取此視窗中的 [取消] 選項，以選擇不復原。</span><span class="sxs-lookup"><span data-stu-id="23dd9-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="23dd9-128">進程摘要</span><span class="sxs-lookup"><span data-stu-id="23dd9-128">Process summary</span></span>

<span data-ttu-id="23dd9-129">在 [準備 \> 處理 \> 結果] \> 流程摘要中，會根據成功的檔案處理及錯誤結果，顯示已載入檔案結果的分解。</span><span class="sxs-lookup"><span data-stu-id="23dd9-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="23dd9-130">此窗格呈現匯入的檔案統計資料的圖形顯示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="23dd9-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="23dd9-131">**進程摘要會累積**d：案例中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="23dd9-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="23dd9-132">**進程摘要最後**：從上一個會話或動作中載入的檔案。</span><span class="sxs-lookup"><span data-stu-id="23dd9-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="23dd9-133">**過去的家族**：在案例中的系列資訊（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="23dd9-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="23dd9-134">如果已新增**seed**檔案，則會針對檔案所定義的每個問題列出 seed 檔案數目。</span><span class="sxs-lookup"><span data-stu-id="23dd9-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="23dd9-135">如果**植**入檔的標記失敗，也會注明。</span><span class="sxs-lookup"><span data-stu-id="23dd9-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="23dd9-136">如果新增**預先標記**的檔案，則會針對檔案所定義的每個問題列出預先標記的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="23dd9-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="23dd9-137">如果**預先標記**檔的標記失敗，也會注明。</span><span class="sxs-lookup"><span data-stu-id="23dd9-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![處理序模組摘要](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="23dd9-139">處理摘要及最後一個圖表</span><span class="sxs-lookup"><span data-stu-id="23dd9-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="23dd9-140">左邊的列包括來源 + 解壓縮的檔案：這是找到的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="23dd9-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="23dd9-141">正確的列（處理的）包括：</span><span class="sxs-lookup"><span data-stu-id="23dd9-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="23dd9-142">有載入錯誤的檔案</span><span class="sxs-lookup"><span data-stu-id="23dd9-142">Files with load errors</span></span>
    
- <span data-ttu-id="23dd9-143">已成功載入檔案，可能包括：</span><span class="sxs-lookup"><span data-stu-id="23dd9-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="23dd9-144">**現有**：以前載入和現在載入的檔案（包括重複）。</span><span class="sxs-lookup"><span data-stu-id="23dd9-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="23dd9-145">**Text**：具有文字的唯一檔。</span><span class="sxs-lookup"><span data-stu-id="23dd9-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="23dd9-146">**非文字**：空白的文字檔、空白的原生文字檔、原生非文字檔。</span><span class="sxs-lookup"><span data-stu-id="23dd9-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="23dd9-147">**重複**s：具有文字的重複檔案。</span><span class="sxs-lookup"><span data-stu-id="23dd9-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="23dd9-148">最後處理常式錯誤</span><span class="sxs-lookup"><span data-stu-id="23dd9-148">Last process errors</span></span>

<span data-ttu-id="23dd9-149">在 [準備 \> 處理結果] 中 \> \> ，會顯示最後一個會話或執行的錯誤詳細資料中的處理常式錯誤。</span><span class="sxs-lookup"><span data-stu-id="23dd9-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![處理序模組錯誤](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="23dd9-151">請參閱</span><span class="sxs-lookup"><span data-stu-id="23dd9-151">See also</span></span>

[<span data-ttu-id="23dd9-152">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="23dd9-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="23dd9-153">執行處理模組及載入資料</span><span class="sxs-lookup"><span data-stu-id="23dd9-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

