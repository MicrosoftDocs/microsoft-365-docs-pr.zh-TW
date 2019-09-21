---
title: 標記與相關性訓練中 Office 365 進階電子文件探索
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: '了解標記的步驟，然後會使用 Office 365 進階電子文件探索的相關性訓練階段期間的訓練樣本的 40 個檔案。  '
ms.openlocfilehash: 569fdfd6e5369459d55bb3ecfa2ebc32f0a10005
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077488"
---
# <a name="tagging-and-relevance-training-in-office-365-advanced-ediscovery"></a><span data-ttu-id="af803-103">標記與相關性訓練中 Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="af803-103">Tagging and Relevance training in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="af803-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="af803-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="af803-106">本主題說明使用進階電子文件相關性訓練模組的程序。</span><span class="sxs-lookup"><span data-stu-id="af803-106">This topic describes the procedure for working with the Advanced eDiscovery Relevance training module.</span></span> 
  
<span data-ttu-id="af803-107">進階電子文件，來完成評估，並輸入相關性訓練階段後，會將 40 個檔案的訓練範例帶入用於標示 [標記] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="af803-107">After Assessment is completed in Advanced eDiscovery, and you enter the Relevance training stage, a training sample of 40 files is brought into the Tag tab for tagging.</span></span> 
  
## <a name="performing-relevance-training"></a><span data-ttu-id="af803-108">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="af803-108">Performing Relevance training</span></span>

1. <span data-ttu-id="af803-109">在**相關性\>標籤**] 索引標籤，[標記] 窗格中顯示的左的窗格及顯示檔案的範例中的預設值，用於標示一次一個。</span><span class="sxs-lookup"><span data-stu-id="af803-109">In the **Relevance \> Tag** tab, the Tagging pane is displayed by default in the left pane and the sample files are displayed, one at a time for tagging.</span></span> 
    
    ![相關性標籤面板](media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    <span data-ttu-id="af803-111">在 [**標籤**] 索引標籤會顯示檔案的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="af803-111">In the **Tag** tab, the file's display name is shown.</span></span> <span data-ttu-id="af803-112">這可能是路徑、 電子郵件主旨、 標題、 或使用者定義的名稱。</span><span class="sxs-lookup"><span data-stu-id="af803-112">This could be the path, email subject, title, or user-defined name.</span></span> <span data-ttu-id="af803-113">ID、 檔案路徑或文字路徑可以被複製檔案的路徑上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="af803-113">The ID, file path or text path can be copied by right-clicking on the file's path.</span></span> 
    
    <span data-ttu-id="af803-114">標記檔案範例號碼 （在左邊窗格的頂端）、 （右窗格的底部），此範例中的檔案總數超出目前所顯示的檔案數目與目前範例 （t 底部中的標記檔案總數的統計資料顯示 [**標籤**] 索引標籤他左窗格），這會變更為您標記檔案。</span><span class="sxs-lookup"><span data-stu-id="af803-114">The **Tag** tab tagging statistics show the file sample number (at the top of the left pane), the number of the currently displayed file out of the total files in the sample (bottom of right pane), and the current total number of tagged files in the sample (bottom of the left pane), which changes as you tag files.</span></span> <span data-ttu-id="af803-115">這適用於任何相關性標記中評估、 訓練、 Catch-up 或測試是否完成。</span><span class="sxs-lookup"><span data-stu-id="af803-115">This applies for any Relevance tagging done, whether in Assessment, Training, Catch-up, or Test.</span></span> 
    
    <span data-ttu-id="af803-116">表示註解、 標記和家庭檔案存在的圖示會顯示在 [檔案] 檢視中的列上方檔案。</span><span class="sxs-lookup"><span data-stu-id="af803-116">Icons indicating the existence of comments, tags, and family files are displayed in the file view in a bar above the file.</span></span>
    
2. <span data-ttu-id="af803-117">決定檔案的相關性案例問題和標記，如下表所示，使用 [標記] 選項圖示按鈕或 [鍵盤快速鍵等，該檔案：</span><span class="sxs-lookup"><span data-stu-id="af803-117">Determine the file's relevance for the case issue and tag the file using either the Tagging option icon buttons or keyboard shortcuts, as shown in the following table:</span></span>
    
<span data-ttu-id="af803-118">| |</span><span class="sxs-lookup"><span data-stu-id="af803-118"></span></span>
|<span data-ttu-id="af803-119">**標記] 選項**</span><span class="sxs-lookup"><span data-stu-id="af803-119">**Tagging option**</span></span>|<span data-ttu-id="af803-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="af803-120">**Description**</span></span>|<span data-ttu-id="af803-121">**鍵盤快速鍵**</span><span class="sxs-lookup"><span data-stu-id="af803-121">**Keyboard shortcut**</span></span>|<span data-ttu-id="af803-122">**多個問題-大量標記鍵盤快速鍵**</span><span class="sxs-lookup"><span data-stu-id="af803-122">**For multiple issues - bulk tag keyboard shortcut**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af803-123">R</span><span class="sxs-lookup"><span data-stu-id="af803-123">R</span></span>  <br/> |<span data-ttu-id="af803-124">相關</span><span class="sxs-lookup"><span data-stu-id="af803-124">Relevant</span></span>  <br/> |<span data-ttu-id="af803-125">Z</span><span class="sxs-lookup"><span data-stu-id="af803-125">Z</span></span>  <br/> |<span data-ttu-id="af803-126">Shift + Z</span><span class="sxs-lookup"><span data-stu-id="af803-126">Shift + Z</span></span>  <br/> |
|<span data-ttu-id="af803-127">編號</span><span class="sxs-lookup"><span data-stu-id="af803-127">NR</span></span>  <br/> |<span data-ttu-id="af803-128">不相關</span><span class="sxs-lookup"><span data-stu-id="af803-128">Not relevant</span></span>  <br/> |<span data-ttu-id="af803-129">X</span><span class="sxs-lookup"><span data-stu-id="af803-129">X</span></span>  <br/> |<span data-ttu-id="af803-130">Shift + X</span><span class="sxs-lookup"><span data-stu-id="af803-130">Shift + X</span></span>  <br/> |
|<span data-ttu-id="af803-131">略過</span><span class="sxs-lookup"><span data-stu-id="af803-131">Skip</span></span>  <br/> |<span data-ttu-id="af803-132">略過</span><span class="sxs-lookup"><span data-stu-id="af803-132">Skip</span></span>  <br/> |<span data-ttu-id="af803-133">C</span><span class="sxs-lookup"><span data-stu-id="af803-133">C</span></span>  <br/> |<span data-ttu-id="af803-134">Shift + A</span><span class="sxs-lookup"><span data-stu-id="af803-134">Shift + A</span></span>  <br/> |
   
  - <span data-ttu-id="af803-135">當之後標記一個問題，多個問題存在於檔案中，選取範圍移至下一個問題 （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="af803-135">When multiple issues exist for a file, after tagging one issue, the selection moves to the next issue (if any).</span></span> 
    
  - <span data-ttu-id="af803-136">反白顯示關鍵字時，由系統管理員或案例管理員所定義的關鍵字 (相關性設定\>以反白顯示關鍵字)，將顯示 （在指定的色彩），以協助識別相關的檔案時標記。</span><span class="sxs-lookup"><span data-stu-id="af803-136">Keywords that were defined by the Administrator or Case manager when highlighting keywords (Relevance setup \> Highlighted keywords), will be displayed (in specified colors) to help identify relevant files while tagging.</span></span> <span data-ttu-id="af803-137">如果關鍵字都有雙底線，它可以按下顯示的關鍵字描述的工具提示。</span><span class="sxs-lookup"><span data-stu-id="af803-137">If a keyword has a double underline, it can be clicked to display a tool-tip with the keyword's description.</span></span> 
    
    <span data-ttu-id="af803-138">（選用) 在 [**標籤**] 索引標籤中，按一下 [**標記設定**來設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="af803-138">Optionally, in the **Tag** tab, click **Tag settings** to set the following options:</span></span> 
    
    ![相關性標籤設定](media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - <span data-ttu-id="af803-140">**大量標記**： 使用此選項可透過選取**所有**設定的所有問題 （覆寫已標記問題） 選取的檔案的標籤或選取**其餘**的其餘的無標記問題套用標籤指派多個問題的檔案。</span><span class="sxs-lookup"><span data-stu-id="af803-140">**Bulk tag**: Use this option to assign multiple issues for a file by selecting **All** to set the tag for the selected file for all issues (overrides already tagged issues) or by selecting **The rest** to apply the tag to the remaining untagged issues.</span></span> <span data-ttu-id="af803-141">所選取的選項保持作用中的所有使用者的情況下變更該使用者，才能 （設定為每位使用者的所有使用者的情況下）。</span><span class="sxs-lookup"><span data-stu-id="af803-141">The selected option remains in effect for all of this user's cases until changed by that user (setting is per user for all the user's cases).</span></span> 
    
  - <span data-ttu-id="af803-142">**自動標記**： 選取此核取方塊，可為 [未設定其他問題的檔案相關之後單一相關標記。</span><span class="sxs-lookup"><span data-stu-id="af803-142">**Auto tag**: Select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span></span>
    
  - <span data-ttu-id="af803-143">**自動換頁**： 選取此核取方塊可將顯示的檔案選取範圍移動至下一個檔案，標記的最後一筆或僅無標記的問題時。</span><span class="sxs-lookup"><span data-stu-id="af803-143">**Auto advance**: Select this check box to move the displayed file selection to the next file when tagging the last or only untagged issue.</span></span> 
    
    <span data-ttu-id="af803-144">略過的檔案不會被視為相關性訓練和相關性分數用途。</span><span class="sxs-lookup"><span data-stu-id="af803-144">Skipped files will not be considered for Relevance training and Relevance scoring purposes.</span></span>
    
3. <span data-ttu-id="af803-145">任意文字註解相關聯的檔案，可以檢視及編輯透過在左的窗格中的下拉式清單] 清單中的 [**註解**] 選項。</span><span class="sxs-lookup"><span data-stu-id="af803-145">Free-text comments, associated with a file, can be viewed and edited via the **Comment** option in the left pane drop-down list.</span></span> <span data-ttu-id="af803-146">（選用）</span><span class="sxs-lookup"><span data-stu-id="af803-146">(optional)</span></span> 
    
4. <span data-ttu-id="af803-147">在左的窗格中的下拉式清單] 清單中選取 [**標記準則**] 選項可檢視標記的指導方針。</span><span class="sxs-lookup"><span data-stu-id="af803-147">Guidelines for tagging can be viewed by selecting the **Tagging guidelines** option in the left pane drop-down list.</span></span> 
    
5. <span data-ttu-id="af803-148">完成 [標記] 清單中的所有檔案後，當您準備好要計算結果時，按一下 [**計算**]。</span><span class="sxs-lookup"><span data-stu-id="af803-148">After you finish tagging all files in the list and are ready to calculate the results, click **Calculate**.</span></span> <span data-ttu-id="af803-149">會顯示 [**追蹤**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="af803-149">The **Track** tab is displayed.</span></span> 
    
## <a name="working-with-the-sample-files-list"></a><span data-ttu-id="af803-150">使用範例檔案清單</span><span class="sxs-lookup"><span data-stu-id="af803-150">Working with the sample files list</span></span>

<span data-ttu-id="af803-151">範例檔案清單可讓您檢視訓練範例中的檔案清單，並在一或多個檔案上執行各種動作。</span><span class="sxs-lookup"><span data-stu-id="af803-151">The sample files list allows you to view a list of the files in a training sample and perform various action on one or more files.</span></span> <span data-ttu-id="af803-152">在 [**相關性** \> **標籤**] 索引標籤，**範例檔案**左邊的窗格會顯示範例檔案，如評估、 與訓練、 Catch-up，不一致的處理程序的清單。</span><span class="sxs-lookup"><span data-stu-id="af803-152">In the **Relevance** \> **Tag** tab, the **Sample files** left pane displays a list of sample files for processing with Assessment, Training, Catch-up, and Inconsistencies processes.</span></span> 
  
1. <span data-ttu-id="af803-153">在**相關性\>標籤**索引標籤上，選取左的窗格下拉式清單中的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="af803-153">In the **Relevance \> Tag** tab, select the Sample files in the left pane drop-down list.</span></span> <span data-ttu-id="af803-154">在左窗格中列出的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="af803-154">The sample files are listed in the left pane.</span></span> 
    
    ![相關性標籤範例檔案清單](media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. <span data-ttu-id="af803-156">藉由輸入或選取其數字**範例**或**檔案**] 方塊中選取一個特定的範例或檔案數目。</span><span class="sxs-lookup"><span data-stu-id="af803-156">Select a specific sample or file number by entering or selecting its number in the **Sample** or **File** boxes.</span></span> 
    
  -   - <span data-ttu-id="af803-157">檔案序列數字會列在左邊欄位的 [**標籤**] 索引標籤上的顯示的檔案清單。藉由按一下標頭，檔案的原始顯示的順序傳回至其原始的順序。</span><span class="sxs-lookup"><span data-stu-id="af803-157">A file sequence number is listed in the left column of the displayed file list on the **Tag** tab. By clicking the header, the original displayed order of the files returns to its original order.</span></span> 
    
  - <span data-ttu-id="af803-158">在 [檔案] 列上按一下右窗格中顯示其內容。</span><span class="sxs-lookup"><span data-stu-id="af803-158">Clicking on a file row displays its content in the right pane.</span></span>
    
  - <span data-ttu-id="af803-159">瀏覽之間檔案範例中，目前使用較低的功能表列選項。</span><span class="sxs-lookup"><span data-stu-id="af803-159">Navigate between files in the current sample by using the lower menu bar options.</span></span> <span data-ttu-id="af803-160">此外，瀏覽的鍵盤快速鍵可用：</span><span class="sxs-lookup"><span data-stu-id="af803-160">In addition, navigational keyboard shortcuts are available:</span></span>
    
    <span data-ttu-id="af803-161">瀏覽至第一個檔案中的範例： Shift + Ctrl +\<</span><span class="sxs-lookup"><span data-stu-id="af803-161">To navigate to the first file in the sample: Shift + Ctrl + \<</span></span>
    
    <span data-ttu-id="af803-162">瀏覽至範例中的前一個檔案： Shift +\<</span><span class="sxs-lookup"><span data-stu-id="af803-162">To navigate to the previous file in the sample: Shift + \<</span></span>
    
    <span data-ttu-id="af803-163">瀏覽至範例中的下一個檔案： Shift +\></span><span class="sxs-lookup"><span data-stu-id="af803-163">To navigate to the next file in the sample: Shift + \></span></span>
    
    <span data-ttu-id="af803-164">瀏覽至最後一個範例中的檔案： Shift + Ctrl +\></span><span class="sxs-lookup"><span data-stu-id="af803-164">To navigate to the last file in the sample: Shift + Ctrl + \></span></span>
    
## <a name="see-also"></a><span data-ttu-id="af803-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="af803-165">See also</span></span>

[<span data-ttu-id="af803-166">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="af803-166">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="af803-167">了解相關性評估</span><span class="sxs-lookup"><span data-stu-id="af803-167">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="af803-168">標記與評估</span><span class="sxs-lookup"><span data-stu-id="af803-168">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="af803-169">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="af803-169">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="af803-170">決定根據結果</span><span class="sxs-lookup"><span data-stu-id="af803-170">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="af803-171">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="af803-171">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

