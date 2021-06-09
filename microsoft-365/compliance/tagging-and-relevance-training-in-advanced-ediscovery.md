---
title: Advanced eDiscovery 中的標記和關聯性訓練
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Advanced eDiscovery 的關聯性訓練階段中，瞭解標記的步驟，並使用40檔案的訓練範例。
ms.openlocfilehash: ae4a9f2e9fd87fdd0679bbfd8f287b6eaa98e41f
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769218"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery"></a><span data-ttu-id="a552e-103">Advanced eDiscovery 中的標記和關聯性訓練</span><span class="sxs-lookup"><span data-stu-id="a552e-103">Tagging and Relevance training in Advanced eDiscovery</span></span>
  
<span data-ttu-id="a552e-104">本文說明在 Advanced eDiscovery 中使用相關性訓練模組的步驟。</span><span class="sxs-lookup"><span data-stu-id="a552e-104">This article describes the procedure for working with the Relevance training module in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="a552e-105">在 Advanced eDiscovery 中完成評估，並輸入相關性訓練階段時，會將40檔案的訓練範例放入 [標籤] 索引標籤中以進行標記。</span><span class="sxs-lookup"><span data-stu-id="a552e-105">After Assessment is completed in Advanced eDiscovery, and you enter the Relevance training stage, a training sample of 40 files is brought into the Tag tab for tagging.</span></span>
  
## <a name="performing-relevance-training"></a><span data-ttu-id="a552e-106">執行相關性訓練</span><span class="sxs-lookup"><span data-stu-id="a552e-106">Performing Relevance training</span></span>

1. <span data-ttu-id="a552e-107">在 [ **相關性 \>** 標籤] 索引標籤中，預設會在左窗格中顯示 [標記] 窗格，並顯示範例檔案，一次顯示一個標記。</span><span class="sxs-lookup"><span data-stu-id="a552e-107">In the **Relevance \> Tag** tab, the Tagging pane is displayed by default in the left pane and the sample files are displayed, one at a time for tagging.</span></span>

    ![相關性標籤面板](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    <span data-ttu-id="a552e-109">**在 [卷** 標] 索引標籤中，會顯示檔的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="a552e-109">In the **Tag** tab, the file's display name is shown.</span></span> <span data-ttu-id="a552e-110">這可以是路徑、電子郵件主題、標題或使用者定義的名稱。</span><span class="sxs-lookup"><span data-stu-id="a552e-110">This could be the path, email subject, title, or user-defined name.</span></span> <span data-ttu-id="a552e-111">您可以在檔案的路徑上按一下滑鼠右鍵，以複製識別碼、檔路徑或文字路徑。</span><span class="sxs-lookup"><span data-stu-id="a552e-111">The ID, file path or text path can be copied by right-clicking on the file's path.</span></span>

    <span data-ttu-id="a552e-112">[標籤] 卷 **標標記統計** 資料會顯示左窗格頂端 (的檔案範例編號) 、目前顯示的檔案的總數（從右窗格中的 [下一個] 的 [下一個] 窗格 (中的 [下一個]）和 [範例中的標籤總數]) ，以及在左 (窗格的範例中，會隨著您標籤檔而變更的範例</span><span class="sxs-lookup"><span data-stu-id="a552e-112">The **Tag** tab tagging statistics show the file sample number (at the top of the left pane), the number of the currently displayed file out of the total files in the sample (bottom of right pane), and the current total number of tagged files in the sample (bottom of the left pane), which changes as you tag files.</span></span> <span data-ttu-id="a552e-113">這適用于任何已完成的相關性標記，不論是在評估、訓練、追趕或測試中。</span><span class="sxs-lookup"><span data-stu-id="a552e-113">This applies for any Relevance tagging done, whether in Assessment, Training, Catch-up, or Test.</span></span>

    <span data-ttu-id="a552e-114">指出批註、標記及系列檔是否存在的圖示會顯示在檔案上方的檔案視圖中的檔。</span><span class="sxs-lookup"><span data-stu-id="a552e-114">Icons indicating the existence of comments, tags, and family files are displayed in the file view in a bar above the file.</span></span>

2. <span data-ttu-id="a552e-115">判斷案例問題的相關程度，並使用 [標記] 選項圖示按鈕或快速鍵標記檔案，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="a552e-115">Determine the file's relevance for the case issue and tag the file using either the Tagging option icon buttons or keyboard shortcuts, as shown in the following table:</span></span>

   |<span data-ttu-id="a552e-116">**標記選項**</span><span class="sxs-lookup"><span data-stu-id="a552e-116">**Tagging option**</span></span>|<span data-ttu-id="a552e-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="a552e-117">**Description**</span></span>|<span data-ttu-id="a552e-118">**捷徑**</span><span class="sxs-lookup"><span data-stu-id="a552e-118">**Keyboard shortcut**</span></span>|<span data-ttu-id="a552e-119">**多個問題的大量標記鍵盤快速鍵 ()**</span><span class="sxs-lookup"><span data-stu-id="a552e-119">**Bulk tagging keyboard shortcut (for multiple issues)**</span></span>|
   |-----|-----|-----|-----|
   |<span data-ttu-id="a552e-120">R</span><span class="sxs-lookup"><span data-stu-id="a552e-120">R</span></span>  <br/> |<span data-ttu-id="a552e-121">相關</span><span class="sxs-lookup"><span data-stu-id="a552e-121">Relevant</span></span>  <br/> |<span data-ttu-id="a552e-122">Z</span><span class="sxs-lookup"><span data-stu-id="a552e-122">Z</span></span>  <br/> |`Shift + Z`  <br/> |
   |<span data-ttu-id="a552e-123">星期日</span><span class="sxs-lookup"><span data-stu-id="a552e-123">NR</span></span>  <br/> |<span data-ttu-id="a552e-124">不相關</span><span class="sxs-lookup"><span data-stu-id="a552e-124">Not relevant</span></span>  <br/> |<span data-ttu-id="a552e-125">X</span><span class="sxs-lookup"><span data-stu-id="a552e-125">X</span></span>  <br/> |`Shift + X`  <br/> |
   |<span data-ttu-id="a552e-126">略過</span><span class="sxs-lookup"><span data-stu-id="a552e-126">Skip</span></span>  <br/> |<span data-ttu-id="a552e-127">略過</span><span class="sxs-lookup"><span data-stu-id="a552e-127">Skip</span></span>  <br/> |<span data-ttu-id="a552e-128">C</span><span class="sxs-lookup"><span data-stu-id="a552e-128">C</span></span>  <br/> |`Shift + A`  <br/> |
   |||||

   - <span data-ttu-id="a552e-129">如果有多個問題存在於檔案中，在標記一個問題之後，選取範圍就會移至下一個問題 (如果有任何) 。</span><span class="sxs-lookup"><span data-stu-id="a552e-129">When multiple issues exist for a file, after tagging one issue, the selection moves to the next issue (if any).</span></span>  

   - <span data-ttu-id="a552e-130">當醒目提示的關鍵字 (相關性設定醒目提示的關鍵字) 時，系統會以 \> 指定的色彩顯示 () 的關鍵字，以協助識別標記時的相關檔案。</span><span class="sxs-lookup"><span data-stu-id="a552e-130">Keywords that were defined by the Administrator or Case manager when highlighting keywords (Relevance setup \> Highlighted keywords), will be displayed (in specified colors) to help identify relevant files while tagging.</span></span> <span data-ttu-id="a552e-131">如果關鍵字具有雙底線，可按一下該關鍵字以顯示具有關鍵詞描述的工具提示。</span><span class="sxs-lookup"><span data-stu-id="a552e-131">If a keyword has a double underline, it can be clicked to display a tool-tip with the keyword's description.</span></span>

     <span data-ttu-id="a552e-132">（選用）在 **[卷** 標] 索引標籤中，按一下 [ **標記設定** ] 以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="a552e-132">Optionally, in the **Tag** tab, click **Tag settings** to set the following options:</span></span>

      ![相關性標籤設定](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
   - <span data-ttu-id="a552e-134">**大容量** 標籤：使用此選項可為檔案指派多個問題，方法是選取 [ **全部** ]，為所選取的檔案設定所有問題的標記， (覆寫已標記的問題) 或選取 **[其他** ]，將標記套用至其餘的未加標記的問題。</span><span class="sxs-lookup"><span data-stu-id="a552e-134">**Bulk tag**: Use this option to assign multiple issues for a file by selecting **All** to set the tag for the selected file for all issues (overrides already tagged issues) or by selecting **The rest** to apply the tag to the remaining untagged issues.</span></span> <span data-ttu-id="a552e-135">選取的選項會在所有使用者的案例中一直保持作用，直到使用者變更 (設定為每位使用者) 所有使用者的案例。</span><span class="sxs-lookup"><span data-stu-id="a552e-135">The selected option remains in effect for all of this user's cases until changed by that user (setting is per user for all the user's cases).</span></span>

   - <span data-ttu-id="a552e-136">**自動標記**：選取此核取方塊，可在單一相關標記之後，將檔案的其他問題設定為 [不相關]。</span><span class="sxs-lookup"><span data-stu-id="a552e-136">**Auto tag**: Select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span></span>

   - <span data-ttu-id="a552e-137">**自動推進**：選取此核取方塊，當您將所顯示的檔案選取範圍移至下一個檔時，會將其移至下一個檔案。</span><span class="sxs-lookup"><span data-stu-id="a552e-137">**Auto advance**: Select this check box to move the displayed file selection to the next file when tagging the last or only untagged issue.</span></span>

    <span data-ttu-id="a552e-138">已略過的檔案不會被視為相關性訓練及相關性計分的目的。</span><span class="sxs-lookup"><span data-stu-id="a552e-138">Skipped files will not be considered for Relevance training and Relevance scoring purposes.</span></span>

3. <span data-ttu-id="a552e-139">您可以透過左窗格下拉式清單中的 [ **批註** ] 選項，查看及編輯與檔案相關聯的任意文字批註。</span><span class="sxs-lookup"><span data-stu-id="a552e-139">Free-text comments, associated with a file, can be viewed and edited via the **Comment** option in the left pane drop-down list.</span></span> <span data-ttu-id="a552e-140"> (選用) </span><span class="sxs-lookup"><span data-stu-id="a552e-140">(optional)</span></span>

4. <span data-ttu-id="a552e-141">您可以在左窗格下拉式清單中選取 [ **標記指導方針** ] 選項，以查看標記的指導方針。</span><span class="sxs-lookup"><span data-stu-id="a552e-141">Guidelines for tagging can be viewed by selecting the **Tagging guidelines** option in the left pane drop-down list.</span></span>

5. <span data-ttu-id="a552e-142">當您完成清單中所有檔案的標記且準備好計算結果之後，請按一下 [ **計算**]。</span><span class="sxs-lookup"><span data-stu-id="a552e-142">After you finish tagging all files in the list and are ready to calculate the results, click **Calculate**.</span></span> <span data-ttu-id="a552e-143">顯示 [ **追蹤** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a552e-143">The **Track** tab is displayed.</span></span>  

## <a name="working-with-the-sample-files-list"></a><span data-ttu-id="a552e-144">使用範例檔案清單</span><span class="sxs-lookup"><span data-stu-id="a552e-144">Working with the sample files list</span></span>

<span data-ttu-id="a552e-145">範例檔案清單可讓您在訓練範例中查看檔案的清單，並在一或多個檔案上執行各種動作。</span><span class="sxs-lookup"><span data-stu-id="a552e-145">The sample files list allows you to view a list of the files in a training sample and perform various actions on one or more files.</span></span> <span data-ttu-id="a552e-146">在 [**相關性** 標籤] 索引標籤中 \>  ，**範例** 檔案左窗格會顯示範例檔案的清單，以進行評估、訓練、追趕及不一致的處理常式。</span><span class="sxs-lookup"><span data-stu-id="a552e-146">In the **Relevance** \> **Tag** tab, the **Sample files** left pane displays a list of sample files for processing with Assessment, Training, Catch-up, and Inconsistencies processes.</span></span>
  
1. <span data-ttu-id="a552e-147">在 [ **相關性 \> 標記** ] 索引標籤中，選取左窗格下拉式清單中的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="a552e-147">In the **Relevance \> Tag** tab, select the Sample files in the left pane drop-down list.</span></span> <span data-ttu-id="a552e-148">範例檔案會列在左窗格中。</span><span class="sxs-lookup"><span data-stu-id="a552e-148">The sample files are listed in the left pane.</span></span>

    ![相關性標籤範例檔案清單](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. <span data-ttu-id="a552e-150">在 [ **範例** ] 或 [檔案] 方塊中輸入或選取特定的範例或 **檔編號** ，以選取它。</span><span class="sxs-lookup"><span data-stu-id="a552e-150">Select a specific sample or file number by entering or selecting its number in the **Sample** or **File** boxes.</span></span>

   - <span data-ttu-id="a552e-151">檔順序編號會列 **在 [標籤] 索引** 標籤上顯示之檔案清單的左欄中。按一下頁首，檔案的原始顯示順序會傳回其原始訂單。</span><span class="sxs-lookup"><span data-stu-id="a552e-151">A file sequence number is listed in the left column of the displayed file list on the **Tag** tab. By clicking the header, the original displayed order of the files returns to its original order.</span></span>

   - <span data-ttu-id="a552e-152">按一下檔列時，會在右窗格中顯示其內容。</span><span class="sxs-lookup"><span data-stu-id="a552e-152">Clicking on a file row displays its content in the right pane.</span></span>

   - <span data-ttu-id="a552e-153">使用下方的功能表列選項，在目前範例中的檔案間流覽。</span><span class="sxs-lookup"><span data-stu-id="a552e-153">Navigate between files in the current sample by using the lower menu bar options.</span></span> <span data-ttu-id="a552e-154">此外，導覽鍵盤快速鍵也可供使用：</span><span class="sxs-lookup"><span data-stu-id="a552e-154">In addition, navigational keyboard shortcuts are available:</span></span>
  
     - <span data-ttu-id="a552e-155">移至範例中的第一個檔案： `Shift + Ctrl + <`</span><span class="sxs-lookup"><span data-stu-id="a552e-155">To go to the first file in the sample: `Shift + Ctrl + <`</span></span>

     - <span data-ttu-id="a552e-156">若要移至範例中的上一個檔案： `Shift + <`</span><span class="sxs-lookup"><span data-stu-id="a552e-156">To go to the previous file in the sample: `Shift + <`</span></span>

     - <span data-ttu-id="a552e-157">若要移至範例中的下一個檔案： `Shift + >`</span><span class="sxs-lookup"><span data-stu-id="a552e-157">To go to the next file in the sample: `Shift + >`</span></span>

     - <span data-ttu-id="a552e-158">移至範例中的最後一個檔案： `Shift + Ctrl + >`</span><span class="sxs-lookup"><span data-stu-id="a552e-158">To go to the last file in the sample: `Shift + Ctrl + >`</span></span>
