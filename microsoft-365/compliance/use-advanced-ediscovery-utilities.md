---
title: 使用 Office 365 進階電子文件探索公用程式
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: '了解 Office 365 進階電子文件探索，包括大小寫的記錄檔中的公用程式、 清除資料、 處理錯誤，修改相關性和透明度分析。  '
ms.openlocfilehash: 3952d1ec58b3f55f997079cec16f16ddb301ed89
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601330"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="8c66d-103">使用 Office 365 進階電子文件探索公用程式</span><span class="sxs-lookup"><span data-stu-id="8c66d-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="8c66d-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="8c66d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8c66d-106">顯示且可使用進階電子文件中的公用取決於內容和使用者角色。</span><span class="sxs-lookup"><span data-stu-id="8c66d-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="8c66d-107">案例的記錄檔</span><span class="sxs-lookup"><span data-stu-id="8c66d-107">Case log</span></span>

<span data-ttu-id="8c66d-108">案例的記錄檔提供應用程式的處理活動，可用於疑難排解的追蹤，以及解決錯誤和警告的詳細的清單。</span><span class="sxs-lookup"><span data-stu-id="8c66d-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="8c66d-109">記錄檔可以產生並儲存在本機上的主應用程式或伺服器，或直接傳送到電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8c66d-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="8c66d-110">記錄檔也可以下載至用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="8c66d-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="8c66d-111">用戶端下載選項可能會啟用或停用根據組態及使用者角色。</span><span class="sxs-lookup"><span data-stu-id="8c66d-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="8c66d-112">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="8c66d-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="8c66d-113">在**設定和公用程式\>公用程式**索引標籤上，選取 [**案例記錄\>安裝**。</span><span class="sxs-lookup"><span data-stu-id="8c66d-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="8c66d-114">選取**記錄層級**如下所示：</span><span class="sxs-lookup"><span data-stu-id="8c66d-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="8c66d-115">**標準**： 包含的基本記錄資料。</span><span class="sxs-lookup"><span data-stu-id="8c66d-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="8c66d-116">此選項通常需要針對監視，且應該使用，除非否則建議。</span><span class="sxs-lookup"><span data-stu-id="8c66d-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="8c66d-117">**最少**： 用於非常大型的情況下，並只傳回的最新資料。</span><span class="sxs-lookup"><span data-stu-id="8c66d-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="8c66d-118">按一下 [**執行案例記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="8c66d-118">Click **Run Case log**.</span></span> <span data-ttu-id="8c66d-119">產生記錄檔，並顯示路徑。</span><span class="sxs-lookup"><span data-stu-id="8c66d-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="8c66d-120">在 [工作狀態] 窗格中會顯示目前和最後一個任務的任務進度資訊。</span><span class="sxs-lookup"><span data-stu-id="8c66d-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="8c66d-121">清除資料</span><span class="sxs-lookup"><span data-stu-id="8c66d-121">Clear data</span></span>

<span data-ttu-id="8c66d-122">必要時刪除或重新初始化案例資料，必須被初始化的資料庫執行個體。</span><span class="sxs-lookup"><span data-stu-id="8c66d-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="8c66d-123">清除資料公用程式會刪除所有指定的項目從案例資料庫、 文字檔、 案例] 資料夾和累積的結果。</span><span class="sxs-lookup"><span data-stu-id="8c66d-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="8c66d-124">函式只能由系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="8c66d-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8c66d-125">此巨集指令可還原並不會清除所有的相關性標記和專家使用者所執行的分析。</span><span class="sxs-lookup"><span data-stu-id="8c66d-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="8c66d-126">如有必要，請儲存資料的備份。</span><span class="sxs-lookup"><span data-stu-id="8c66d-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="8c66d-127">極端小心使用此選項。</span><span class="sxs-lookup"><span data-stu-id="8c66d-127">Use this option with extreme care.</span></span> <span data-ttu-id="8c66d-128">刪除標記及排名檔案可能會影響相關性結果。</span><span class="sxs-lookup"><span data-stu-id="8c66d-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="8c66d-129">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="8c66d-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="8c66d-130">在**設定和公用程式\>公用程式**索引標籤上，選取 [**清除資料\>安裝**。</span><span class="sxs-lookup"><span data-stu-id="8c66d-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="8c66d-131">選取的選項。 若要初始化的資訊：</span><span class="sxs-lookup"><span data-stu-id="8c66d-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="8c66d-132">**相關性**： 刪除完成相關性，包括定義負載及要載入的檔案關聯中的所有工作。</span><span class="sxs-lookup"><span data-stu-id="8c66d-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="8c66d-133">它會刪除所有範例和標記。</span><span class="sxs-lookup"><span data-stu-id="8c66d-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="8c66d-134">**近似重複項目和電子郵件執行緒**： 刪除所有分析資訊的近似重複項目和電子郵件執行緒。</span><span class="sxs-lookup"><span data-stu-id="8c66d-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="8c66d-135">**佈景主題**： 刪除佈景主題相關的資料。</span><span class="sxs-lookup"><span data-stu-id="8c66d-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="8c66d-136">**匯出歷程記錄**： 刪除的匯出批次歷程記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="8c66d-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="8c66d-137">按一下 [**清除資料**。</span><span class="sxs-lookup"><span data-stu-id="8c66d-137">Click **Clear data**.</span></span> <span data-ttu-id="8c66d-138">案例資料被清除。</span><span class="sxs-lookup"><span data-stu-id="8c66d-138">The case data is cleared.</span></span> <span data-ttu-id="8c66d-139">在 [**工作狀態**] 窗格中會顯示目前和最後一個任務的任務進度資訊。</span><span class="sxs-lookup"><span data-stu-id="8c66d-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="8c66d-140">修改相關性</span><span class="sxs-lookup"><span data-stu-id="8c66d-140">Modify Relevance</span></span>

<span data-ttu-id="8c66d-141">本節說明如何將略過或回復相關性樣本。</span><span class="sxs-lookup"><span data-stu-id="8c66d-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="8c66d-142">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="8c66d-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="8c66d-143">在**設定和公用程式\>公用程式**索引標籤上，選取 [**修改相關性**。</span><span class="sxs-lookup"><span data-stu-id="8c66d-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="8c66d-144">從選項進行選取：</span><span class="sxs-lookup"><span data-stu-id="8c66d-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="8c66d-145">**略過目前範例-目前的使用者**： 這會標記，以**略過**，執行此公用程式的使用者開啟案例範例中的所有無標記的檔案。</span><span class="sxs-lookup"><span data-stu-id="8c66d-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="8c66d-146">相關性處理將不會標示為**略過**的檔案上執行。</span><span class="sxs-lookup"><span data-stu-id="8c66d-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="8c66d-147">**略過目前範例對所有開啟的範例**： 這會加上標籤，以**略過**，所有無標記的檔案所有開啟的範例中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="8c66d-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="8c66d-148">如果使用者目前已標記範例，是不建議使用此選項。</span><span class="sxs-lookup"><span data-stu-id="8c66d-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="8c66d-149">**回復最後一個範例**： 上次完成的相關性訓練範例將會回復，不論其是否之前或之後的 「 計算 」 程序。</span><span class="sxs-lookup"><span data-stu-id="8c66d-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="8c66d-150">不允許執行更新性樣本的復原。</span><span class="sxs-lookup"><span data-stu-id="8c66d-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="8c66d-151">按一下 [**執行**]，以執行。</span><span class="sxs-lookup"><span data-stu-id="8c66d-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="8c66d-152">透明度分析</span><span class="sxs-lookup"><span data-stu-id="8c66d-152">Transparency analysis</span></span>

<span data-ttu-id="8c66d-153">透明度分析公用程式可讓詳細的檢視的檔案和其指派的相關性分數。</span><span class="sxs-lookup"><span data-stu-id="8c66d-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="8c66d-154">報表可用是例行性檢查或比較人性化與相關性指派進階電子文件檢閱者所定義的檔案的相關性。</span><span class="sxs-lookup"><span data-stu-id="8c66d-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="8c66d-155">除了相關性分數，進階電子文件會計算，並指派考慮關鍵字內容的關鍵字加權。</span><span class="sxs-lookup"><span data-stu-id="8c66d-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="8c66d-156">檔案的相同字可被指派不同的權數，根據內容及位置。</span><span class="sxs-lookup"><span data-stu-id="8c66d-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="8c66d-157">使用色彩濃度範圍從黃色深橙色和 varying 灰網底的增加刻度標記每個關鍵字。</span><span class="sxs-lookup"><span data-stu-id="8c66d-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="8c66d-158">色彩編碼用來以視覺方式表示 [word 的相對的相關性分數的正數或負比重。</span><span class="sxs-lookup"><span data-stu-id="8c66d-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="8c66d-159">在多個問題案例案例中，就會產生透明度分析報告每個問題。</span><span class="sxs-lookup"><span data-stu-id="8c66d-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="8c66d-160">在功能表列中，按一下 [ **Cogwheel**圖示。</span><span class="sxs-lookup"><span data-stu-id="8c66d-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="8c66d-161">在**設定和公用程式\>公用程式**索引標籤上，選取 [**透明度分析\>安裝**。</span><span class="sxs-lookup"><span data-stu-id="8c66d-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="8c66d-162">在 [\* \* 檔案識別碼 \* \*，輸入檔案的檔案識別碼，處理程序。</span><span class="sxs-lookup"><span data-stu-id="8c66d-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="8c66d-163">在 [**問題**] 清單中，選取相關的問題。</span><span class="sxs-lookup"><span data-stu-id="8c66d-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="8c66d-164">按一下 [**透明度分析**。</span><span class="sxs-lookup"><span data-stu-id="8c66d-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="8c66d-165">完成時，會顯示檔案的透明度分析報告，它會顯示特別標示的關鍵字色彩與整體的相關性分數的相互關聯。</span><span class="sxs-lookup"><span data-stu-id="8c66d-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8c66d-166">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8c66d-166">See also</span></span>

[<span data-ttu-id="8c66d-167">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="8c66d-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8c66d-168">定義案例與租用戶設定</span><span class="sxs-lookup"><span data-stu-id="8c66d-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

