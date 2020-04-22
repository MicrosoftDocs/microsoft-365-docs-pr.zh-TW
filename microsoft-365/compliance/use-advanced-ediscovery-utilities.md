---
title: 使用進階電子文件探索公用程式
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
description: '深入瞭解 Advanced eDiscovery 中的公用程式，包括案例記錄、清除資料、處理常式錯誤、修改相關性及透明分析。  '
ms.openlocfilehash: d4495920110916fdd5b07201d50080605ba177b1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633388"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a><span data-ttu-id="e0125-103">使用進階電子文件探索 (傳統版) 公用程式</span><span class="sxs-lookup"><span data-stu-id="e0125-103">Use Advanced eDiscovery (classic) utilities</span></span>

> [!NOTE]
> <span data-ttu-id="e0125-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="e0125-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e0125-106">在高級 eDiscovery 中顯示並可用的公用程式，取決於內容和使用者角色。</span><span class="sxs-lookup"><span data-stu-id="e0125-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="e0125-107">案例記錄</span><span class="sxs-lookup"><span data-stu-id="e0125-107">Case log</span></span>

<span data-ttu-id="e0125-108">案例記錄會提供應用程式處理活動的詳細清單，可用於追蹤、疑難排解以及定址錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="e0125-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="e0125-109">記錄可以產生，並儲存在主機或伺服器的本機上，或直接傳送至電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e0125-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="e0125-110">記錄檔也可以下載到用戶端的電腦。</span><span class="sxs-lookup"><span data-stu-id="e0125-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="e0125-111">您可以根據設定和使用者角色，啟用或停用用戶端下載選項。</span><span class="sxs-lookup"><span data-stu-id="e0125-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="e0125-112">在功能表列中，按一下 [ **Cogwheel** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e0125-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e0125-113">在 [**設定與實用\>程式公用程式**] 索引標籤中，選取 [**案例\>記錄檔設定**]。</span><span class="sxs-lookup"><span data-stu-id="e0125-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="e0125-114">選取**記錄層級**，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0125-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="e0125-115">**Standard**：包括基本記錄資料。</span><span class="sxs-lookup"><span data-stu-id="e0125-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="e0125-116">這通常是監視的必要條件，除非另有建議，否則應該使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e0125-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="e0125-117">**最低**：適用于非常大的情況，只會傳回最新的資料。</span><span class="sxs-lookup"><span data-stu-id="e0125-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="e0125-118">按一下 [**執行案例記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e0125-118">Click **Run Case log**.</span></span> <span data-ttu-id="e0125-119">會產生記錄並顯示路徑。</span><span class="sxs-lookup"><span data-stu-id="e0125-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="e0125-120">目前及最後一項任務的任務進度資訊會顯示在 [任務狀態] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="e0125-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="e0125-121">清除資料</span><span class="sxs-lookup"><span data-stu-id="e0125-121">Clear data</span></span>

<span data-ttu-id="e0125-122">若有必要刪除或重新初始化 case 資料，必須先初始化資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="e0125-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="e0125-123">Clear data 公用程式會從案例資料庫、文字檔、案例資料夾及累計結果中刪除所有指定的專案。</span><span class="sxs-lookup"><span data-stu-id="e0125-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="e0125-124">只有管理員才能執行該功能。</span><span class="sxs-lookup"><span data-stu-id="e0125-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e0125-125">此巨集指令是不可逆的，會清除專家所執行的所有相關性標記和分析。</span><span class="sxs-lookup"><span data-stu-id="e0125-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="e0125-126">視需要儲存資料的備份。</span><span class="sxs-lookup"><span data-stu-id="e0125-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="e0125-127">請特別小心使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e0125-127">Use this option with extreme care.</span></span> <span data-ttu-id="e0125-128">刪除已標記和排名的檔案可能會影響相關性結果。</span><span class="sxs-lookup"><span data-stu-id="e0125-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="e0125-129">在功能表列中，按一下 [ **Cogwheel** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e0125-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e0125-130">在 [**設定與實用\>程式公用程式**] 索引標籤中，選取 [**清除\>資料安裝**]。</span><span class="sxs-lookup"><span data-stu-id="e0125-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="e0125-131">選取要初始化的資訊選項：</span><span class="sxs-lookup"><span data-stu-id="e0125-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="e0125-132">**相關性**：刪除所有在相關性中完成的工作，包括要載入之檔案的負載和關聯的定義。</span><span class="sxs-lookup"><span data-stu-id="e0125-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="e0125-133">它會刪除所有的範例及標記。</span><span class="sxs-lookup"><span data-stu-id="e0125-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="e0125-134">**近乎重複的和電子郵件的執行緒**：刪除近期重複的分析資訊和電子郵件執行緒。</span><span class="sxs-lookup"><span data-stu-id="e0125-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="e0125-135">**主題**：刪除主題相關的資料。</span><span class="sxs-lookup"><span data-stu-id="e0125-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="e0125-136">**匯出歷程記錄**：刪除匯出批次的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="e0125-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="e0125-137">按一下 [**清除資料**]。</span><span class="sxs-lookup"><span data-stu-id="e0125-137">Click **Clear data**.</span></span> <span data-ttu-id="e0125-138">清除案例資料。</span><span class="sxs-lookup"><span data-stu-id="e0125-138">The case data is cleared.</span></span> <span data-ttu-id="e0125-139">目前及最後一項任務的任務進度資訊會顯示在 [**任務狀態**] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="e0125-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="e0125-140">修改相關性</span><span class="sxs-lookup"><span data-stu-id="e0125-140">Modify Relevance</span></span>

<span data-ttu-id="e0125-141">本節說明如何略過或回復相關性範例。</span><span class="sxs-lookup"><span data-stu-id="e0125-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="e0125-142">在功能表列中，按一下 [ **Cogwheel** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e0125-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e0125-143">在 [**設定與實用\>程式公用程式**] 索引標籤中，選取 [**修改相關性**]。</span><span class="sxs-lookup"><span data-stu-id="e0125-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="e0125-144">從選項中選取：</span><span class="sxs-lookup"><span data-stu-id="e0125-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="e0125-145">**Skip current sample-針對目前的使用者**：這會在開啟案例範例中，標記為**Skip**，所有未標記的檔案都是執行公用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="e0125-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="e0125-146">在標記為**略過**的檔案上不會執行相關性處理。</span><span class="sxs-lookup"><span data-stu-id="e0125-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="e0125-147">**Skip current sample-所有開啟的範例**：這將會標記為**Skip**，所有使用者開啟的範例中的所有未標記檔案。</span><span class="sxs-lookup"><span data-stu-id="e0125-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="e0125-148">如果使用者目前正在標記範例，則不建議使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e0125-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="e0125-149">**回復上一個範例**：不管是在「計算」處理常式之前或之後，都將會回復的最後一個已完成相關性訓練範例。</span><span class="sxs-lookup"><span data-stu-id="e0125-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="e0125-150">不允許復原追趕範例。</span><span class="sxs-lookup"><span data-stu-id="e0125-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="e0125-151">按一下 [**執行**] 執行。</span><span class="sxs-lookup"><span data-stu-id="e0125-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="e0125-152">透明度分析</span><span class="sxs-lookup"><span data-stu-id="e0125-152">Transparency analysis</span></span>

<span data-ttu-id="e0125-153">「透明度分析」公用程式會啟用檔案及其所指派相關性分數的詳細視圖。</span><span class="sxs-lookup"><span data-stu-id="e0125-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="e0125-154">報告可以做為健全檢查，也可以比較人類審校所定義之檔案的相關性，與「高級 eDiscovery」所指派的相關性相較。</span><span class="sxs-lookup"><span data-stu-id="e0125-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="e0125-155">除了相關性分數之外，高級 eDiscovery 還會計算並指派考慮關鍵字內容的關鍵字權重。</span><span class="sxs-lookup"><span data-stu-id="e0125-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="e0125-156">檔案中的同一個字可以指派不同的權重，視內容和位置而定。</span><span class="sxs-lookup"><span data-stu-id="e0125-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="e0125-157">每個關鍵字都會使用增加的色彩濃度（從黃色到深橙色）和不同的灰色陰影來標示。</span><span class="sxs-lookup"><span data-stu-id="e0125-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="e0125-158">色彩編碼是用來以視覺方式指出字詞相對於相關性分數的相對正負號或負數。</span><span class="sxs-lookup"><span data-stu-id="e0125-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="e0125-159">在多重問題案例案例中，可能會針對每個問題產生透明分析報告。</span><span class="sxs-lookup"><span data-stu-id="e0125-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="e0125-160">在功能表列中，按一下 [ **Cogwheel** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e0125-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e0125-161">在 [**設定與實用\>程式公用程式**] 索引標籤中，選取 [**透明度\>分析設定**]。</span><span class="sxs-lookup"><span data-stu-id="e0125-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="e0125-162">在 \* \* 檔識別碼 \* \* 中，輸入要處理之檔案的檔案識別碼。</span><span class="sxs-lookup"><span data-stu-id="e0125-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="e0125-163">在 [**問題**] 清單中，選取相關的問題。</span><span class="sxs-lookup"><span data-stu-id="e0125-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="e0125-164">按一下 [**透明分析**]。</span><span class="sxs-lookup"><span data-stu-id="e0125-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="e0125-165">完成後，會顯示檔案的「透明度分析」報告，其中會顯示標示的關鍵字色彩如何與整體相關性分數相關聯。</span><span class="sxs-lookup"><span data-stu-id="e0125-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e0125-166">請參閱</span><span class="sxs-lookup"><span data-stu-id="e0125-166">See also</span></span>

[<span data-ttu-id="e0125-167">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="e0125-167">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e0125-168">定義案例與租使用者設定</span><span class="sxs-lookup"><span data-stu-id="e0125-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

