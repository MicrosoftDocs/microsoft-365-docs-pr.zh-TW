---
title: 高級 eDiscovery 中的標記與相關性訓練
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 在 [高級 eDiscovery] 的「相關性訓練」階段中，瞭解標記的步驟，然後再使用40檔案的訓練範例。
ms.openlocfilehash: 56ce30754e04d4a2adcf854093e603f93be5ae36
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936669"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery-classic"></a><span data-ttu-id="a328f-103">高級 eDiscovery （經典）中的標記和關聯性訓練</span><span class="sxs-lookup"><span data-stu-id="a328f-103">Tagging and Relevance training in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="a328f-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a328f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a328f-106">本主題說明使用高級 eDiscovery 相關性訓練模組的程式。</span><span class="sxs-lookup"><span data-stu-id="a328f-106">This topic describes the procedure for working with the Advanced eDiscovery Relevance training module.</span></span> 
  
<span data-ttu-id="a328f-107">在 [Advanced eDiscovery] 中完成評估之後，並輸入相關性訓練階段時，40檔的訓練範例會進入 [標籤] 索引標籤以進行標記。</span><span class="sxs-lookup"><span data-stu-id="a328f-107">After Assessment is completed in Advanced eDiscovery, and you enter the Relevance training stage, a training sample of 40 files is brought into the Tag tab for tagging.</span></span> 
  
## <a name="performing-relevance-training"></a><span data-ttu-id="a328f-108">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="a328f-108">Performing Relevance training</span></span>

1. <span data-ttu-id="a328f-109">在 [\*\*相關性 \> \*\*標籤] 索引標籤中，預設會在左窗格中顯示 [標記] 窗格，並顯示範例檔案，一次顯示一個標記。</span><span class="sxs-lookup"><span data-stu-id="a328f-109">In the **Relevance \> Tag** tab, the Tagging pane is displayed by default in the left pane and the sample files are displayed, one at a time for tagging.</span></span> 
    
    ![相關性標籤面板](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    <span data-ttu-id="a328f-111">**在 [卷**標] 索引標籤中，會顯示檔的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="a328f-111">In the **Tag** tab, the file's display name is shown.</span></span> <span data-ttu-id="a328f-112">這可以是路徑、電子郵件主題、標題或使用者定義的名稱。</span><span class="sxs-lookup"><span data-stu-id="a328f-112">This could be the path, email subject, title, or user-defined name.</span></span> <span data-ttu-id="a328f-113">您可以在檔案的路徑上按一下滑鼠右鍵，以複製識別碼、檔路徑或文字路徑。</span><span class="sxs-lookup"><span data-stu-id="a328f-113">The ID, file path or text path can be copied by right-clicking on the file's path.</span></span> 
    
    <span data-ttu-id="a328f-114">**標記**標籤標記統計資料會顯示檔案範例號碼（位於左窗格上方）、目前顯示的檔案輸出範例中的總檔案數目（右窗格的底部），以及範例中已標記檔案（左窗格底部）的目前總數目，這會隨著您的標記檔而變更。</span><span class="sxs-lookup"><span data-stu-id="a328f-114">The **Tag** tab tagging statistics show the file sample number (at the top of the left pane), the number of the currently displayed file out of the total files in the sample (bottom of right pane), and the current total number of tagged files in the sample (bottom of the left pane), which changes as you tag files.</span></span> <span data-ttu-id="a328f-115">這適用于任何已完成的相關性標記，不論是在評估、訓練、追趕或測試中。</span><span class="sxs-lookup"><span data-stu-id="a328f-115">This applies for any Relevance tagging done, whether in Assessment, Training, Catch-up, or Test.</span></span> 
    
    <span data-ttu-id="a328f-116">指出批註、標記及系列檔是否存在的圖示會顯示在檔案上方的檔案視圖中的檔。</span><span class="sxs-lookup"><span data-stu-id="a328f-116">Icons indicating the existence of comments, tags, and family files are displayed in the file view in a bar above the file.</span></span>
    
2. <span data-ttu-id="a328f-117">判斷案例問題的相關程度，並使用 [標記] 選項圖示按鈕或快速鍵標記檔案，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="a328f-117">Determine the file's relevance for the case issue and tag the file using either the Tagging option icon buttons or keyboard shortcuts, as shown in the following table:</span></span>

|<span data-ttu-id="a328f-118">**標記選項**</span><span class="sxs-lookup"><span data-stu-id="a328f-118">**Tagging option**</span></span>|<span data-ttu-id="a328f-119">**描述**</span><span class="sxs-lookup"><span data-stu-id="a328f-119">**Description**</span></span>|<span data-ttu-id="a328f-120">**捷徑**</span><span class="sxs-lookup"><span data-stu-id="a328f-120">**Keyboard shortcut**</span></span>|<span data-ttu-id="a328f-121">**針對多個問題-大量標記鍵盤快速鍵**</span><span class="sxs-lookup"><span data-stu-id="a328f-121">**For multiple issues - bulk tag keyboard shortcut**</span></span>|
|-----|-----|-----|-----|
|<span data-ttu-id="a328f-122">R</span><span class="sxs-lookup"><span data-stu-id="a328f-122">R</span></span>  <br/> |<span data-ttu-id="a328f-123">相關</span><span class="sxs-lookup"><span data-stu-id="a328f-123">Relevant</span></span>  <br/> |<span data-ttu-id="a328f-124">Z</span><span class="sxs-lookup"><span data-stu-id="a328f-124">Z</span></span>  <br/> |<span data-ttu-id="a328f-125">Shift + Z</span><span class="sxs-lookup"><span data-stu-id="a328f-125">Shift + Z</span></span>  <br/> |
|<span data-ttu-id="a328f-126">星期日</span><span class="sxs-lookup"><span data-stu-id="a328f-126">NR</span></span>  <br/> |<span data-ttu-id="a328f-127">不相關</span><span class="sxs-lookup"><span data-stu-id="a328f-127">Not relevant</span></span>  <br/> |<span data-ttu-id="a328f-128">X</span><span class="sxs-lookup"><span data-stu-id="a328f-128">X</span></span>  <br/> |<span data-ttu-id="a328f-129">Shift + X</span><span class="sxs-lookup"><span data-stu-id="a328f-129">Shift + X</span></span>  <br/> |
|<span data-ttu-id="a328f-130">略過</span><span class="sxs-lookup"><span data-stu-id="a328f-130">Skip</span></span>  <br/> |<span data-ttu-id="a328f-131">略過</span><span class="sxs-lookup"><span data-stu-id="a328f-131">Skip</span></span>  <br/> |<span data-ttu-id="a328f-132">C</span><span class="sxs-lookup"><span data-stu-id="a328f-132">C</span></span>  <br/> |<span data-ttu-id="a328f-133">Shift + A</span><span class="sxs-lookup"><span data-stu-id="a328f-133">Shift + A</span></span>  <br/> |
   
  - <span data-ttu-id="a328f-134">如果有多個問題存在於檔案中，在標記一個問題之後，選取範圍就會移至下一個問題（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="a328f-134">When multiple issues exist for a file, after tagging one issue, the selection moves to the next issue (if any).</span></span> 
    
  - <span data-ttu-id="a328f-135">當醒目提示關鍵字（相關性設定高亮顯示關鍵字）時，系統管理員或案例管理員所定義的關鍵字 \> ，可協助識別標記時的相關檔案。</span><span class="sxs-lookup"><span data-stu-id="a328f-135">Keywords that were defined by the Administrator or Case manager when highlighting keywords (Relevance setup \> Highlighted keywords), will be displayed (in specified colors) to help identify relevant files while tagging.</span></span> <span data-ttu-id="a328f-136">如果關鍵字具有雙底線，可按一下該關鍵字以顯示具有關鍵詞描述的工具提示。</span><span class="sxs-lookup"><span data-stu-id="a328f-136">If a keyword has a double underline, it can be clicked to display a tool-tip with the keyword's description.</span></span> 
    
    <span data-ttu-id="a328f-137">（選用）在 **[卷**標] 索引標籤中，按一下 [**標記設定**] 以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="a328f-137">Optionally, in the **Tag** tab, click **Tag settings** to set the following options:</span></span> 
    
    ![相關性標籤設定](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - <span data-ttu-id="a328f-139">**大量**標籤：使用此選項，可選取 [**全部**]，為所選取的檔案設定所有問題（覆寫已標記的問題）的標記，或選取**其餘**專案將標記套用至其餘的未加標記的問題，以指定檔案的多個問題。</span><span class="sxs-lookup"><span data-stu-id="a328f-139">**Bulk tag**: Use this option to assign multiple issues for a file by selecting **All** to set the tag for the selected file for all issues (overrides already tagged issues) or by selecting **The rest** to apply the tag to the remaining untagged issues.</span></span> <span data-ttu-id="a328f-140">選取的選項會在所有此使用者的情況下保持作用，直到該使用者變更為止（設定為每位使用者的所有使用者案例）。</span><span class="sxs-lookup"><span data-stu-id="a328f-140">The selected option remains in effect for all of this user's cases until changed by that user (setting is per user for all the user's cases).</span></span> 
    
  - <span data-ttu-id="a328f-141">**自動標記**：選取此核取方塊，可在單一相關標記之後，將檔案的其他問題設定為 [不相關]。</span><span class="sxs-lookup"><span data-stu-id="a328f-141">**Auto tag**: Select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span></span>
    
  - <span data-ttu-id="a328f-142">**自動推進**：選取此核取方塊，當您將所顯示的檔案選取範圍移至下一個檔時，會將其移至下一個檔案。</span><span class="sxs-lookup"><span data-stu-id="a328f-142">**Auto advance**: Select this check box to move the displayed file selection to the next file when tagging the last or only untagged issue.</span></span> 
    
    <span data-ttu-id="a328f-143">已略過的檔案不會被視為相關性訓練及相關性計分的目的。</span><span class="sxs-lookup"><span data-stu-id="a328f-143">Skipped files will not be considered for Relevance training and Relevance scoring purposes.</span></span>
    
3. <span data-ttu-id="a328f-144">您可以透過左窗格下拉式清單中的 [**批註**] 選項，查看及編輯與檔案相關聯的任意文字批註。</span><span class="sxs-lookup"><span data-stu-id="a328f-144">Free-text comments, associated with a file, can be viewed and edited via the **Comment** option in the left pane drop-down list.</span></span> <span data-ttu-id="a328f-145">選</span><span class="sxs-lookup"><span data-stu-id="a328f-145">(optional)</span></span> 
    
4. <span data-ttu-id="a328f-146">您可以在左窗格下拉式清單中選取 [**標記指導方針**] 選項，以查看標記的指導方針。</span><span class="sxs-lookup"><span data-stu-id="a328f-146">Guidelines for tagging can be viewed by selecting the **Tagging guidelines** option in the left pane drop-down list.</span></span> 
    
5. <span data-ttu-id="a328f-147">當您完成清單中所有檔案的標記且準備好計算結果之後，請按一下 [**計算**]。</span><span class="sxs-lookup"><span data-stu-id="a328f-147">After you finish tagging all files in the list and are ready to calculate the results, click **Calculate**.</span></span> <span data-ttu-id="a328f-148">顯示 [**追蹤**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a328f-148">The **Track** tab is displayed.</span></span> 
    
## <a name="working-with-the-sample-files-list"></a><span data-ttu-id="a328f-149">使用範例檔案清單</span><span class="sxs-lookup"><span data-stu-id="a328f-149">Working with the sample files list</span></span>

<span data-ttu-id="a328f-150">範例檔案清單可讓您在訓練範例中查看檔案的清單，並在一或多個檔案上執行各種動作。</span><span class="sxs-lookup"><span data-stu-id="a328f-150">The sample files list allows you to view a list of the files in a training sample and perform various action on one or more files.</span></span> <span data-ttu-id="a328f-151">在 [**相關性**標籤] 索引標籤中 \> **Tag** ，**範例**檔案左窗格會顯示範例檔案的清單，以進行評估、訓練、追趕及不一致的處理常式。</span><span class="sxs-lookup"><span data-stu-id="a328f-151">In the **Relevance** \> **Tag** tab, the **Sample files** left pane displays a list of sample files for processing with Assessment, Training, Catch-up, and Inconsistencies processes.</span></span> 
  
1. <span data-ttu-id="a328f-152">在 [**相關性 \> 標記**] 索引標籤中，選取左窗格下拉式清單中的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="a328f-152">In the **Relevance \> Tag** tab, select the Sample files in the left pane drop-down list.</span></span> <span data-ttu-id="a328f-153">範例檔案會列在左窗格中。</span><span class="sxs-lookup"><span data-stu-id="a328f-153">The sample files are listed in the left pane.</span></span> 
    
    ![相關性標籤範例檔案清單](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. <span data-ttu-id="a328f-155">在 [**範例**] 或 [檔案] 方塊中輸入或選取特定的範例或**檔編號**，以選取它。</span><span class="sxs-lookup"><span data-stu-id="a328f-155">Select a specific sample or file number by entering or selecting its number in the **Sample** or **File** boxes.</span></span> 
    
  -   - <span data-ttu-id="a328f-156">檔順序編號會列**在 [標籤] 索引**標籤上顯示之檔案清單的左欄中。按一下頁首，檔案的原始顯示順序會傳回其原始訂單。</span><span class="sxs-lookup"><span data-stu-id="a328f-156">A file sequence number is listed in the left column of the displayed file list on the **Tag** tab. By clicking the header, the original displayed order of the files returns to its original order.</span></span> 
    
  - <span data-ttu-id="a328f-157">按一下檔列時，會在右窗格中顯示其內容。</span><span class="sxs-lookup"><span data-stu-id="a328f-157">Clicking on a file row displays its content in the right pane.</span></span>
    
  - <span data-ttu-id="a328f-158">使用下方的功能表列選項，在目前範例中的檔案間流覽。</span><span class="sxs-lookup"><span data-stu-id="a328f-158">Navigate between files in the current sample by using the lower menu bar options.</span></span> <span data-ttu-id="a328f-159">此外，導覽鍵盤快速鍵也可供使用：</span><span class="sxs-lookup"><span data-stu-id="a328f-159">In addition, navigational keyboard shortcuts are available:</span></span>
    
    <span data-ttu-id="a328f-160">流覽至範例中的第一個檔案： Shift + Ctrl +\<</span><span class="sxs-lookup"><span data-stu-id="a328f-160">To navigate to the first file in the sample: Shift + Ctrl + \<</span></span>
    
    <span data-ttu-id="a328f-161">若要流覽至範例中的上一個檔案： Shift +\<</span><span class="sxs-lookup"><span data-stu-id="a328f-161">To navigate to the previous file in the sample: Shift + \<</span></span>
    
    <span data-ttu-id="a328f-162">流覽至範例中的下一個檔案： Shift +\></span><span class="sxs-lookup"><span data-stu-id="a328f-162">To navigate to the next file in the sample: Shift + \></span></span>
    
    <span data-ttu-id="a328f-163">若要流覽至範例中的最後一個檔案： Shift + Ctrl +\></span><span class="sxs-lookup"><span data-stu-id="a328f-163">To navigate to the last file in the sample: Shift + Ctrl + \></span></span>
    
## <a name="see-also"></a><span data-ttu-id="a328f-164">請參閱</span><span class="sxs-lookup"><span data-stu-id="a328f-164">See also</span></span>

[<span data-ttu-id="a328f-165">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="a328f-165">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a328f-166">瞭解相關評估</span><span class="sxs-lookup"><span data-stu-id="a328f-166">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a328f-167">標記與評估</span><span class="sxs-lookup"><span data-stu-id="a328f-167">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a328f-168">追蹤相關性分析</span><span class="sxs-lookup"><span data-stu-id="a328f-168">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a328f-169">根據結果決定</span><span class="sxs-lookup"><span data-stu-id="a328f-169">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a328f-170">測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="a328f-170">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

