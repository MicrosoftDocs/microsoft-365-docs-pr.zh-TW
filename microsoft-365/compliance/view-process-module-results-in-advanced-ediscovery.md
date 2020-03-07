---
title: 在 Office 365 進階電子文件探索中檢視處理序模組結果
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
description: '了解如何尋找 Office 365 進階電子文件探索，包括任務狀態和處理程序摘要中執行的處理序模組結果。  '
ms.openlocfilehash: 76619d5899171e8ec105c359cefdb4b8689a8d8a
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557601"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="a9dd8-103">在進階電子文件 （傳統） 中檢視處理序模組結果</span><span class="sxs-lookup"><span data-stu-id="a9dd8-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="a9dd8-104">在**準備**之後\>初始化**程序**，您可以檢視進度和結果。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a9dd8-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="a9dd8-107">程序的工作狀態</span><span class="sxs-lookup"><span data-stu-id="a9dd8-107">Process task status</span></span>

<span data-ttu-id="a9dd8-108">在 [**準備** \> **程序** \> **結果**，頁面會顯示目前狀態 （如果目前正在執行程序） 或最後一個的處理序狀態任務狀態在下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![處理序模組的工作狀態](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="a9dd8-110">顯示的工作會視所選取的處理程序選項而異。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="a9dd8-111">**清查**： 進階電子文件會逐一查看所有程序所選取的檔案，並執行基本資料收集。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="a9dd8-112">**計算簽章**： 計算 MD5 數位簽章。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="a9dd8-113">**組合擷取**： 擷取內部或包含從複合檔案 (例如，PST，郵遞區號，MSG) 檔案以遞迴方式。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="a9dd8-114">解壓縮的檔案儲存在這種情況的案例資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="a9dd8-115">**同步處理資料庫**： Internal database 程序。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="a9dd8-116">**檔案副本**： 副本程序的檔案。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="a9dd8-117">永遠顯示這項工作，即使已選取 [進階的複製檔案] 選項。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="a9dd8-118">**文字擷取**： 進階電子文件原生檔案時，會使用 DTSearch 這些檔案中擷取文字。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="a9dd8-119">擷取的文字，這些檔案會儲存為案例的資料夾中的文字檔案。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="a9dd8-120">**更新的中繼資料**： 處理的載入的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="a9dd8-121">**Finalizing**： 終結資料的內部處理載入案例檔案 （例如，找出錯誤及成功檔案）。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="a9dd8-122">任務狀態： 工作完成後顯示。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="a9dd8-123">執行工作時，會顯示執行的持續時間。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9dd8-124">已完成的工作可能也包含完成處理的檔案或檔案發生錯誤的總數。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="a9dd8-125">[取消] 提供停止處理程序執行，並再將回復到先前的資料填入 [復原] 選項，或儲存已處理的資料。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="a9dd8-126">復原會清除所有已處理的資料。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-126">Rollback clears all processed data.</span></span> <span data-ttu-id="a9dd8-127">如果您不想要選取 「 取消 「 在此視窗中的選擇選項不適用於回復 （例如，您計劃重新載入這些檔案），會遺失已處理的資料。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="a9dd8-128">處理程序摘要</span><span class="sxs-lookup"><span data-stu-id="a9dd8-128">Process summary</span></span>

<span data-ttu-id="a9dd8-129">在 [準備\>程序\>結果\>程序摘要，明細載入的檔案的結果會顯示是根據成功檔案處理和錯誤的結果。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="a9dd8-130">Panes 呈現匯入的檔案統計資料的圖形顯示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a9dd8-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="a9dd8-131">**處理程序摘要累積**d： 所有檔案的情況下。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="a9dd8-132">**上次處理摘要**： 從最後一個工作階段或巨集指令載入的檔案。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="a9dd8-133">**系列上次**： 系列資訊 （如果有的話） 的情況。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="a9dd8-134">如果已新增**植入**的檔案，植入的檔案數目會列出每個已定義檔案的問題。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="a9dd8-135">如果**植入**檔案的標示失敗，也記下。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="a9dd8-136">如果**預先標記**檔案已經新增，預先標記檔案的數目會列出每個已定義檔案的問題。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="a9dd8-137">如果**預先標記**檔案的標示失敗，也記下。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![處理序模組摘要](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="a9dd8-139">處理程序摘要累積版本和上一個圖表</span><span class="sxs-lookup"><span data-stu-id="a9dd8-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="a9dd8-140">左列包含來源 + 解壓縮的檔案： 這是所有檔案找到。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="a9dd8-141">右橫條圖、 處理，包括：</span><span class="sxs-lookup"><span data-stu-id="a9dd8-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="a9dd8-142">檔案載入錯誤</span><span class="sxs-lookup"><span data-stu-id="a9dd8-142">Files with load errors</span></span>
    
- <span data-ttu-id="a9dd8-143">已成功載入的檔案，其中可能包含：</span><span class="sxs-lookup"><span data-stu-id="a9dd8-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="a9dd8-144">**現有**： 之前已載入並立即載入一次 （包括重複項目） 的檔案。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="a9dd8-145">**文字**： 具有文字的唯一檔案。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="a9dd8-146">**非文字**： 空白文字檔案，空白的原生文字檔案，原生非文字檔案。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="a9dd8-147">**重複**s： 重複具有檔案的文字。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="a9dd8-148">上次處理錯誤</span><span class="sxs-lookup"><span data-stu-id="a9dd8-148">Last process errors</span></span>

<span data-ttu-id="a9dd8-149">在 [準備\>程序\>結果\>會顯示最後一個程序錯誤，在最後一個工作階段或執行動作的錯誤詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a9dd8-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![處理序模組錯誤](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="a9dd8-151">請參閱</span><span class="sxs-lookup"><span data-stu-id="a9dd8-151">See also</span></span>

[<span data-ttu-id="a9dd8-152">進階電子文件 （傳統）</span><span class="sxs-lookup"><span data-stu-id="a9dd8-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a9dd8-153">執行處理序模組及載入資料</span><span class="sxs-lookup"><span data-stu-id="a9dd8-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

