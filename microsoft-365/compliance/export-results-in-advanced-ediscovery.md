---
title: 在高級電子檔探索中匯出結果
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: '瞭解如何定義從 Advanced eDiscovery 匯出結果的選項，包括指定匯出批次參數的程式。 '
ms.openlocfilehash: 4d94b7d1f1d475916e7b0b44a98dd878a1bd5fde
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615997"
---
# <a name="export-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="c2fdf-103">在高級 eDiscovery （古典）中匯出結果</span><span class="sxs-lookup"><span data-stu-id="c2fdf-103">Export results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="c2fdf-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c2fdf-106">本主題說明高級 eDiscovery 匯出設定選項。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="c2fdf-107">**本主題內容：**</span><span class="sxs-lookup"><span data-stu-id="c2fdf-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="c2fdf-108">定義匯出批次和會話</span><span class="sxs-lookup"><span data-stu-id="c2fdf-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="c2fdf-109">增量和其他匯出</span><span class="sxs-lookup"><span data-stu-id="c2fdf-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="c2fdf-110">設定批次匯出參數</span><span class="sxs-lookup"><span data-stu-id="c2fdf-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="c2fdf-111">匯出報表輸出檔案</span><span class="sxs-lookup"><span data-stu-id="c2fdf-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="c2fdf-112">定義匯出批次和會話</span><span class="sxs-lookup"><span data-stu-id="c2fdf-112">Defining export batches and sessions</span></span>
<span data-ttu-id="c2fdf-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="c2fdf-113"><a name="BK_Define"> </a></span></span>

<span data-ttu-id="c2fdf-114">匯出批次允許使用一組定義的參數進行匯出處理。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-114">An export batch allows export processing using a set of defined parameters.</span></span> <span data-ttu-id="c2fdf-115">「高級 eDiscovery」可讓您定義批次，以自訂每個匯出。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-115">Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="c2fdf-116">每個匯出批次定義參數。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-116">Parameters are defined per export batch.</span></span> <span data-ttu-id="c2fdf-117">預設會為案例的第一個批次建立名為 "Export batch 1" 的批次。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-117">A batch named "Export batch 01" is created by default for the first batch of a case.</span></span> <span data-ttu-id="c2fdf-118">您也可以編輯批次名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-118">You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="c2fdf-119">匯出會話是在匯出批次中執行高級 eDiscovery 匯出。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="c2fdf-120">增量和其他匯出</span><span class="sxs-lookup"><span data-stu-id="c2fdf-120">Incremental and additional exports</span></span>
<span data-ttu-id="c2fdf-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="c2fdf-121"><a name="BK_IncrementalReports"> </a></span></span>

<span data-ttu-id="c2fdf-122">您可以在匯出批次中執行多個匯出會話，以根據相同的匯出範本和參數，確保結果一致。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-122">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters.</span></span> <span data-ttu-id="c2fdf-123">針對批次中的每個會話，您可以針對每個「增量」，匯出新處理案例資料的分析和處理。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-123">For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="c2fdf-124">若要使用不同的參數組匯出，您必須先建立新的批次。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-124">In order to export using a different set of parameters, you first need to create a new batch.</span></span> <span data-ttu-id="c2fdf-125">新批次中的第一個會話會產生目前為止處理的檔案的結果，不論這些檔案是透過一或多個匯入，還是進行處理。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-125">The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports.</span></span> <span data-ttu-id="c2fdf-126">每個批次重新計算透視、相似性、inclusives 等。會話使用為批次定義的參數，而不重新計算透視、相似性、inclusives 等每個會話執行的參數。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-126">Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="c2fdf-127">例如，假設已匯入案例，並分析其資料。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-127">For example, assume a case was imported and its data analyzed.</span></span> <span data-ttu-id="c2fdf-128">若要針對累加的資料取得近乎重複的電子郵件串接結果，請按一下 [在先前用於匯出資料的相同批次中**建立匯出會話**]。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-128">In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="c2fdf-129">設定批次匯出參數</span><span class="sxs-lookup"><span data-stu-id="c2fdf-129">Set up batch export parameters</span></span>
<span data-ttu-id="c2fdf-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="c2fdf-130"><a name="BK_SetUpExport"> </a></span></span>

<span data-ttu-id="c2fdf-131">EDiscovery 匯出工具是用來將搜尋結果從 Advanced eDiscovery 匯出至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-131">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer.</span></span> <span data-ttu-id="c2fdf-132">若要增加資料傳輸輸送量並加速匯出程式，您可以在用來匯出搜尋結果的電腦上設定 Windows 登錄設定。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-132">To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results.</span></span> <span data-ttu-id="c2fdf-133">如果您想要增加下載速度，請先設定登錄設定，再設定匯出參數。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-133">If you'd like to increase the download speed, configure the registry setting before you set up the export parameters.</span></span> <span data-ttu-id="c2fdf-134">如需詳細資訊，請參閱[在從 Office 365 匯出 eDiscovery 搜尋結果時，提高下載速度](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-134">For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="c2fdf-135">在 [Advanced eDiscovery] 中，選取案例，然後按一下 [**匯出** \> **設定**]。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="c2fdf-136">從 [**匯出批次**] 清單中，選取批次名稱或匯出結果以匯出批次01（預設批次）。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="c2fdf-137">若要匯出您新增至現有案例的新檔案的結果，請繼續使用目前的批次。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-137">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="c2fdf-138">若要在批次中建立會話，請選取相同的批次號碼，然後按一下 [**建立匯出會話**] 您可以使用此選項，以增量方式匯出與上一個批次相同的參數。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-138">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="c2fdf-139">若要匯出至新的批次**Add** ![，請按一下](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)[add add icon]，並以**批次名稱**輸入新名稱（或接受預設值），並在 [**批次描述**] 中輸入描述。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-139">To export to a new batch, click **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="c2fdf-140">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-140">Click **OK**.</span></span>
    
    - <span data-ttu-id="c2fdf-141">若要編輯批次名稱或描述，請選取 [**匯出批次**] 中的名稱](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，然後按一下 [**編輯** ![編輯圖示]，然後修改欄位。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="c2fdf-142">在您執行匯出批次的會話後，便無法將其刪除。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-142">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="c2fdf-143">此外，在執行第一個會話後，只可編輯部分參數。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-143">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="c2fdf-144">若要建立重複的匯出批次，請選擇 [**重複匯出批次** ![建立](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg)重複的匯出批次圖示]，然後在 [面板] 中輸入重複批次的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-144">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="c2fdf-145">若要刪除匯出批次，請選擇 [**刪除** ![] [](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)刪除匯出批次圖示]。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-145">To delete an export batch, choose **Delete** ![Delete an export batch icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="c2fdf-146">若要查看批次的記錄，請選擇 [**批次記錄** ![] view 病史 history 圖示](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-146">To view the history of a batch, choose **Batch history** ![View history icon](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="c2fdf-147">在 [**人口**] 底下，選取 [**僅包含相關性切出分數**和/或**調整輸出批次**以上的檔案] （如果您要微調匯出批次的設定）。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-147">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="c2fdf-148">如果您選取 [**只包含相關性的僅限**]，則會啟用**問題**。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-148">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled.</span></span> <span data-ttu-id="c2fdf-149">如果檔案的相關性分數高於所選取問題的切削分數，將會匯出檔案，除非它是由「做為審閱」篩選排除。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-149">If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="c2fdf-150">如果您選取 [**調整匯出批次**]，就會啟用 [**取消重復資料**刪除] 和 [依審閱篩選] 欄位選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-150">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled.</span></span> <span data-ttu-id="c2fdf-151">如果您選擇 [**重復資料**刪除]，則會根據定義的原則來篩選掉重複的檔案（預設值）：從整個案例中的每一組重複檔案，除了一個檔案之外，還會取消 duped 所有檔。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-151">If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="c2fdf-152">保管人層級：從同一保管人的每一組重複的檔案，除了一個檔案之外，還會解除 duped。匯出輸出包含所有重複檔案的記錄。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-152">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files.</span></span> <span data-ttu-id="c2fdf-153">如果您選擇 [**依審閱篩選**] 欄位，請選取 [**中繼資料**] 底下的 [修改]，以輸入您的「做**為審閱**」欄位設定。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-153">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="c2fdf-154">選取 [**包含輸入檔**]，以在套件內容中包含來源檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-154">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="c2fdf-155">您可以清除此設定，以加速匯出程式。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-155">You can clear this setting to speed up the export process.</span></span> <span data-ttu-id="c2fdf-156">請注意，在任何情況下都會匯出原生檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-156">Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="c2fdf-157">在 [**中繼資料**] 底下，選取 [**匯出範本**] 清單中的下列選項（每次會話一次）。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="c2fdf-158">**Standard**：一組基本的資料項目目、中繼資料和屬性。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-158">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="c2fdf-159">當匯入資料已在高級 eDiscovery 中處理，並將匯出資料上傳至已包含檔案的系統時，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-159">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="c2fdf-160">[匯出範本] 欄預設會建立並填滿。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-160">By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="c2fdf-161">**All**：完整的標準元資料集（包括所有的處理資料），以及分析與相關性分數。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-161">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="c2fdf-162">當 Advanced eDiscovery 執行第一次上傳至外部系統的處理及檔資料時，此範本是必要的。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-162">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="c2fdf-163">**問題**：請選取**所有問題**，或選取您建立的特定問題。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="c2fdf-164">在 [**目的地**：] 下</span><span class="sxs-lookup"><span data-stu-id="c2fdf-164">Under **Destination**:</span></span>
    
    - <span data-ttu-id="c2fdf-165">**下載到本機電腦**</span><span class="sxs-lookup"><span data-stu-id="c2fdf-165">**Download to local machine**</span></span>
    
    - <span data-ttu-id="c2fdf-166">**匯出至使用者定義的 Azure blob**：若已勾選此專案，您可以指定容器 URL 和 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="c2fdf-167">匯出套件儲存至使用者定義的 Azure blob 之後，就不會再透過「高級 eDiscovery」管理該資料。它是由 Azure blob 所管理。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-167">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob.</span></span> <span data-ttu-id="c2fdf-168">這表示如果您刪除此案例，匯出的檔案仍會保留在 Azure blob 上。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-168">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="c2fdf-169">**儲存 sas token 以供未來匯出會話**：如果檢查，則會在高級 eDiscovery 的內部資料庫中加密 sas 權杖，以供日後使用。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="c2fdf-170">目前的 SAS 權杖會在每月後到期。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-170">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="c2fdf-171">如果您嘗試在數個月後下載，您必須撤銷上一個會話，然後再匯出一次。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-171">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="c2fdf-172">按一下 [**修改**] 以設定「審閱」欄位設定。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-172">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![設定審閱匯出批次的欄位設定](../media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="c2fdf-174">在 [**審閱欄位設定**] 底下的 [**選取案例**] 下拉式清單中，選取案例及檢查範圍。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-174">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review.</span></span> <span data-ttu-id="c2fdf-175">設定會根據您的選取範圍來顯示。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-175">The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="c2fdf-176">**全部檢查**（預設值）：預設會選取所有電子郵件、附件及檔。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-176">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="c2fdf-177">**檢查集合中的所有唯一內容**： Inclusives 及唯一包含副本，電子郵件集合層級中的唯一附件，包含每一組完全相同的專案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-177">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="c2fdf-178">**檢查集合中所有的唯一內容**： Inclusives，電子郵件集合階層中的唯一附件，包含每一組完全相同的副本。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-178">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="c2fdf-179">**檢查所有的唯一內容和相關的系列**檔案： Inclusives、電子郵件集合層級中的唯一附件、每一組完全重複的代表，展開以包含 [家人] 檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-179">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="c2fdf-180">**自訂**（可讓您定義對話方塊中的選項）：預設值是保留目前的選取範圍並啟用所有的對話方塊選項，以允許其選取範圍。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-180">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection.</span></span> <span data-ttu-id="c2fdf-181">如果您選取此選項，則可以自訂電子郵件、檔、附件及其他的設定。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-181">If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="c2fdf-182">在 [**電子郵件**] 底下，選取您要匯出的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-182">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="c2fdf-183">**所有電子郵件**：（預設值）會選取所有電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-183">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="c2fdf-184">**Inclusives**：包含電子郵件是指執行緒的最後一封電子郵件，其中包含來自該執行緒的所有其他電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-184">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="c2fdf-185">**Inclusives 和唯一包含副本**：包含相同主體、內文和附件的副本和 Inclusives;唯一包含的副本是這些電子郵件的獨特副本。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-185">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="c2fdf-186">在 [**檔**] 底下，選取您要匯出的檔。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-186">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="c2fdf-187">**所有檔**：（預設值）已選取所有檔。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-187">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="c2fdf-188">「**旋轉**：」會選擇為代表臨近重複設定的檔案，通常會在審閱集時用作基準。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-188">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="c2fdf-189">**每一組完全相同的代表**：唯一接近重複的檔案（包括 pivot）。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-189">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="c2fdf-190">在 [**附件**] 底下，選取您要匯出的附件。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-190">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="c2fdf-191">**所有附件**：（預設值）會選取所有附件。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-191">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="c2fdf-192">**案例層級的唯一附件**：指定之案例內的唯一附件檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-192">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="c2fdf-193">**電子郵件集層級中的唯一附件**：指定的電子郵件案例內的唯一附件檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-193">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="c2fdf-194">在 [**Micellaneous**] 底下，您可以選擇將**附件當做檔對待**、將**電子郵件視為檔**，或**展開以包含系列**檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-194">Under**Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**.</span></span> <span data-ttu-id="c2fdf-195">當您選擇 [**展開] 以包含系列**檔案時，會針對每個已標記為要檢查的檔案，也會標記同一系列的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-195">When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="c2fdf-196">選擇 [**儲存**] 以儲存設定。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-196">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="c2fdf-197">指定匯出參數之後，請按一下 [建立匯出的**會話**] 以開始匯出批次。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-197">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="c2fdf-198">在匯出期間，狀態會顯示在 [**任務狀態**] 中。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-198">During export, the status is displayed in **Task status**.</span></span> <span data-ttu-id="c2fdf-199">結果會顯示在 [**匯出摘要**] 中。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-199">The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="c2fdf-200">在 [**下載**檔案] 視窗中，按一下 [**複製到剪貼簿**] 以複製匯出機碼。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-200">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![下載檔案](../media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="c2fdf-202">按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-202">Click **Close**.</span></span> 
    
    <span data-ttu-id="c2fdf-203">電子檔探索匯出工具已啟動。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-203">The eDiscovery Export Tool is started.</span></span>
    
    ![eDiscovery 匯出工具](../media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="c2fdf-205">在 [ **EDiscovery 匯出工具**] 中：</span><span class="sxs-lookup"><span data-stu-id="c2fdf-205">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="c2fdf-206">在 [**貼上用來連線至來源的共用存取簽名]** 中，將 youcopied 至剪貼簿的匯出金鑰貼到步驟7中。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-206">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="c2fdf-207">按一下 **[流覽]** ，以選取在本機電腦上儲存已下載之匯出檔案的目標位置。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-207">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="c2fdf-208">按一下 [**開始**]。匯出檔案會下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-208">Click **Start**.The export files are downloaded to the local machine.</span></span> <span data-ttu-id="c2fdf-209">如果您在步驟4中選擇 [**匯出至使用者定義的 Azure blob** ]，則會話會匯出至您所選擇的 BLOB 儲存 URL 目的地。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-209">If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="c2fdf-210">如需匯出報告中欄位的完整描述，請參閱[匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-210">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="c2fdf-211">匯出報表輸出檔案</span><span class="sxs-lookup"><span data-stu-id="c2fdf-211">Export report output files</span></span>
<span data-ttu-id="c2fdf-212"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="c2fdf-212"><a name="BK_ExportOutputFIles"> </a></span></span>

<span data-ttu-id="c2fdf-213">下表列出當您執行匯出批次時所產生的輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-213">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="c2fdf-214">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="c2fdf-214">**File name**</span></span>|<span data-ttu-id="c2fdf-215">**檔案類型**</span><span class="sxs-lookup"><span data-stu-id="c2fdf-215">**File type**</span></span>|<span data-ttu-id="c2fdf-216">**描述**</span><span class="sxs-lookup"><span data-stu-id="c2fdf-216">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2fdf-217">匯出摘要</span><span class="sxs-lookup"><span data-stu-id="c2fdf-217">Export summary</span></span>  <br/> |<span data-ttu-id="c2fdf-218">Csv</span><span class="sxs-lookup"><span data-stu-id="c2fdf-218">csv</span></span>  <br/> |<span data-ttu-id="c2fdf-219">電子檔探索匯出工具所產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="c2fdf-220">跟蹤</span><span class="sxs-lookup"><span data-stu-id="c2fdf-220">Trace</span></span>  <br/> |<span data-ttu-id="c2fdf-221">Txt</span><span class="sxs-lookup"><span data-stu-id="c2fdf-221">txt</span></span>  <br/> |<span data-ttu-id="c2fdf-222">電子檔探索匯出工具所產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-222">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="c2fdf-223">解壓縮的文字檔</span><span class="sxs-lookup"><span data-stu-id="c2fdf-223">Extracted text files</span></span>  <br/> |<span data-ttu-id="c2fdf-224">檔資料夾</span><span class="sxs-lookup"><span data-stu-id="c2fdf-224">File folder</span></span>  <br/> |<span data-ttu-id="c2fdf-225">包含匯出檔案的解壓縮文字檔的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-225">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="c2fdf-226">輸入或本機檔</span><span class="sxs-lookup"><span data-stu-id="c2fdf-226">Input or native files</span></span>  <br/> |<span data-ttu-id="c2fdf-227">檔資料夾</span><span class="sxs-lookup"><span data-stu-id="c2fdf-227">File folder</span></span>  <br/> |<span data-ttu-id="c2fdf-228">包含匯出檔案的原生和輸入檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-228">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="c2fdf-229">匯出清單</span><span class="sxs-lookup"><span data-stu-id="c2fdf-229">Export list</span></span>  <br/> |<span data-ttu-id="c2fdf-230">.xlsx</span><span class="sxs-lookup"><span data-stu-id="c2fdf-230">xlsx</span></span>  <br/> |<span data-ttu-id="c2fdf-231">以 .xlsx 格式匯出的檔中繼資料。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-231">Exported files metadata in xlsx format.</span></span> <span data-ttu-id="c2fdf-232">檔案中的欄位是根據範本使用者選取匯出。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-232">Fields in files are according to template user selects to export.</span></span> <span data-ttu-id="c2fdf-233">如有需要，會建立數個檔案，每個檔案會包含 100-150K 列。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-233">If needed, several files are created, each contains 100-150K rows.</span></span> <span data-ttu-id="c2fdf-234">如果特定值包含的字元數超過 Excel 儲存格可以包含的字元數（目前的限制為32767個字元），則會將此值修整為允許的最大長度。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-234">If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed.</span></span> <span data-ttu-id="c2fdf-235">如果值已被裁去，該儲存格的背景色彩是紅色，表示這是使用者。電子郵件參與者 "是一種可能超出長度限制的欄位範例（如果電子郵件傳送到大型分配）。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-235">If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution.</span></span> <span data-ttu-id="c2fdf-236">如需輸出欄位的詳細資訊，請參閱[匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-236">See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.</span></span>  <br/> |
|<span data-ttu-id="c2fdf-237">載入檔</span><span class="sxs-lookup"><span data-stu-id="c2fdf-237">Load file</span></span>  <br/> |<span data-ttu-id="c2fdf-238">Csv</span><span class="sxs-lookup"><span data-stu-id="c2fdf-238">csv</span></span>  <br/> |<span data-ttu-id="c2fdf-239">匯出的檔中繼資料（csv 格式），以用於載入至不同的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-239">Exported files metadata in csv format for loading into a different application.</span></span> <span data-ttu-id="c2fdf-240">檔案中的欄位是根據範本使用者選取匯出。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-240">Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="c2fdf-241">成功指示器</span><span class="sxs-lookup"><span data-stu-id="c2fdf-241">Success indicator</span></span>  <br/> |<span data-ttu-id="c2fdf-242">Txt</span><span class="sxs-lookup"><span data-stu-id="c2fdf-242">txt</span></span>  <br/> |<span data-ttu-id="c2fdf-243">僅在匯出至協力廠商 Azure blob 時建立。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-243">Only created when exporting to a 3rd party Azure blob.</span></span> <span data-ttu-id="c2fdf-244">如果匯出完全成功，將會建立檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-244">If export succeed completely, the file will be created.</span></span> <span data-ttu-id="c2fdf-245">當失敗或部分成功時，將不會建立檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-245">In case of failure, or partial success the file will not be created.</span></span> <span data-ttu-id="c2fdf-246">將會在根資料夾中建立檔案，允許在不同的匯出批次/會話狀態上進行自動追蹤。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-246">File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses.</span></span> <span data-ttu-id="c2fdf-247">這是空白的檔案。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-247">This is an empty file.</span></span> <span data-ttu-id="c2fdf-248">其名稱為： TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime .txt。</span><span class="sxs-lookup"><span data-stu-id="c2fdf-248">Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c2fdf-249">請參閱</span><span class="sxs-lookup"><span data-stu-id="c2fdf-249">See also</span></span>

[<span data-ttu-id="c2fdf-250">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="c2fdf-250">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c2fdf-251">查看批次歷史記錄及匯出過去的結果</span><span class="sxs-lookup"><span data-stu-id="c2fdf-251">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="c2fdf-252">高級電子檔探索的快速設定</span><span class="sxs-lookup"><span data-stu-id="c2fdf-252">Quick setup for Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="c2fdf-253">匯出報告欄位</span><span class="sxs-lookup"><span data-stu-id="c2fdf-253">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c2fdf-254">提高從 Office 365 匯出 eDiscovery 搜尋結果時的下載速度</span><span class="sxs-lookup"><span data-stu-id="c2fdf-254">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)

