---
title: 在 Office 365 進階電子文件探索中匯出結果
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
description: '了解如何定義從 Office 365 進階電子文件探索，包括指定參數匯出批次的程序中匯出結果的選項。 '
ms.openlocfilehash: ae25c0aac64a437f902ec5533453a05b8bdb5be6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41588313"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="0e669-103">在 Office 365 進階電子文件探索中匯出結果</span><span class="sxs-lookup"><span data-stu-id="0e669-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="0e669-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="0e669-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="0e669-106">本主題說明 [進階電子文件探索匯出設定] 選項。</span><span class="sxs-lookup"><span data-stu-id="0e669-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="0e669-107">**本主題內容：**</span><span class="sxs-lookup"><span data-stu-id="0e669-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="0e669-108">定義匯出批次和工作階段</span><span class="sxs-lookup"><span data-stu-id="0e669-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="0e669-109">增量和其他匯出</span><span class="sxs-lookup"><span data-stu-id="0e669-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="0e669-110">設定批次匯出參數</span><span class="sxs-lookup"><span data-stu-id="0e669-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="0e669-111">匯出報告輸出檔案</span><span class="sxs-lookup"><span data-stu-id="0e669-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="0e669-112">定義匯出批次和工作階段</span><span class="sxs-lookup"><span data-stu-id="0e669-112">Defining export batches and sessions</span></span>
<span data-ttu-id="0e669-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="0e669-113"><a name="BK_Define"> </a></span></span>

<span data-ttu-id="0e669-114">匯出批次允許匯出處理使用一組已定義的參數。</span><span class="sxs-lookup"><span data-stu-id="0e669-114">An export batch allows export processing using a set of defined parameters.</span></span> <span data-ttu-id="0e669-115">進階電子文件可讓您定義自訂每個匯出批次。</span><span class="sxs-lookup"><span data-stu-id="0e669-115">Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="0e669-116">參數會定義每個匯出批次。</span><span class="sxs-lookup"><span data-stu-id="0e669-116">Parameters are defined per export batch.</span></span> <span data-ttu-id="0e669-117">案例的第一個批次的預設會建立名為 「 匯出批次 01 」 批次。</span><span class="sxs-lookup"><span data-stu-id="0e669-117">A batch named "Export batch 01" is created by default for the first batch of a case.</span></span> <span data-ttu-id="0e669-118">您也可以編輯的批次名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="0e669-118">You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="0e669-119">匯出工作階段是進階電子文件探索匯出匯出批次內執行。</span><span class="sxs-lookup"><span data-stu-id="0e669-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="0e669-120">增量和其他匯出</span><span class="sxs-lookup"><span data-stu-id="0e669-120">Incremental and additional exports</span></span>
<span data-ttu-id="0e669-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="0e669-121"><a name="BK_IncrementalReports"> </a></span></span>

<span data-ttu-id="0e669-122">您可以執行匯出批次，以確保結果一致根據相同的匯出範本和參數中的多個匯出工作階段。</span><span class="sxs-lookup"><span data-stu-id="0e669-122">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters.</span></span> <span data-ttu-id="0e669-123">為一個批次中每個工作階段，您可以匯出分析的新處理案例資料，並且處理每個 「 逐漸 」。</span><span class="sxs-lookup"><span data-stu-id="0e669-123">For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="0e669-124">若要匯出使用一組不同的參數，必須先建立新的批次。</span><span class="sxs-lookup"><span data-stu-id="0e669-124">In order to export using a different set of parameters, you first need to create a new batch.</span></span> <span data-ttu-id="0e669-125">在新的批次中的第一個工作階段會產生檔案的情況下到目前為止，處理，不論這些檔案所匯入，並透過一或多個匯入處理的結果。</span><span class="sxs-lookup"><span data-stu-id="0e669-125">The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports.</span></span> <span data-ttu-id="0e669-126">樞紐分析表、 相似性、 inclusives 等，會重新計算每個批次。工作階段使用批次所定義的參數，並不會計算樞紐分析表、 相似性、 inclusives 等針對每個工作階段執行。</span><span class="sxs-lookup"><span data-stu-id="0e669-126">Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="0e669-127">例如，假設情況已匯入且其資料分析。</span><span class="sxs-lookup"><span data-stu-id="0e669-127">For example, assume a case was imported and its data analyzed.</span></span> <span data-ttu-id="0e669-128">若要擷取接近重複項目和電子郵件執行緒增量資料的結果，請按一下 [先前用來將資料匯出同一個批次中的 [**建立匯出工作階段**]。</span><span class="sxs-lookup"><span data-stu-id="0e669-128">In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="0e669-129">設定批次匯出參數</span><span class="sxs-lookup"><span data-stu-id="0e669-129">Set up batch export parameters</span></span>
<span data-ttu-id="0e669-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="0e669-130"><a name="BK_SetUpExport"> </a></span></span>

<span data-ttu-id="0e669-131">EDiscovery 匯出工具用來從進階電子文件的搜尋結果匯出到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="0e669-131">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer.</span></span> <span data-ttu-id="0e669-132">若要增加資料傳輸輸送量並提升並匯出程序，您可以用來匯出搜尋結果的電腦上設定 Windows 登錄設定。</span><span class="sxs-lookup"><span data-stu-id="0e669-132">To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results.</span></span> <span data-ttu-id="0e669-133">如果您想要增加的下載速度，設定為登錄設定的設定匯出參數之前。</span><span class="sxs-lookup"><span data-stu-id="0e669-133">If you'd like to increase the download speed, configure the registry setting before you set up the export parameters.</span></span> <span data-ttu-id="0e669-134">如需詳細資訊，請參閱[增加匯出 eDiscovery 搜尋結果從 Office 365 時的下載速度](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="0e669-134">For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="0e669-135">在 [進階電子文件，select Case，按一下 [**匯出** \> **安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="0e669-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="0e669-136">從**匯出批次**] 清單中，選取批次名稱，或將結果匯出至匯出批次 01、 （預設批次）。</span><span class="sxs-lookup"><span data-stu-id="0e669-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="0e669-137">若要匯出結果的新檔案新增至現有的情況下，繼續執行您目前的批次。</span><span class="sxs-lookup"><span data-stu-id="0e669-137">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="0e669-138">批次中建立工作階段、 選取相同的批次數目，並按一下 [**建立匯出工作階段**中，您可以使用此選項為前一個批次，匯出相同的參數，以累加方式。</span><span class="sxs-lookup"><span data-stu-id="0e669-138">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="0e669-139">若要匯出至新的批次時，按一下 [**新增**![新增圖示](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)和**批次名稱**輸入新名稱 （或接受預設值） 和 [描述] 中**批次描述**。</span><span class="sxs-lookup"><span data-stu-id="0e669-139">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="0e669-140">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e669-140">Click **OK**.</span></span>
    
    - <span data-ttu-id="0e669-141">若要編輯的批次名稱或描述，請選取中**匯出批次**的名稱，請按一下 [**編輯**![編輯圖示](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，然後再修改欄位。</span><span class="sxs-lookup"><span data-stu-id="0e669-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="0e669-142">您已執行匯出批次的工作階段之後，他們無法刪除。</span><span class="sxs-lookup"><span data-stu-id="0e669-142">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="0e669-143">此外，一旦執行第一個工作階段後，可以編輯只有一些參數。</span><span class="sxs-lookup"><span data-stu-id="0e669-143">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="0e669-144">若要建立的重複匯出批次，請選擇 [**重複匯出批次**![建立重複的匯出批次圖示](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)和在 [資訊] 面板中輸入名稱和描述重複的批次。</span><span class="sxs-lookup"><span data-stu-id="0e669-144">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="0e669-145">若要刪除匯出批次，請選擇 [**刪除**![刪除匯出批次圖示](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="0e669-145">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="0e669-146">若要檢視的批次歷程記錄，請選擇 [**批次歷程記錄**![檢視歷程記錄圖示](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="0e669-146">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="0e669-147">[**母體**，選取**包含上述相關性截止分數的檔案**及/或**精簡匯出批次**如果您想要微調您匯出批次的設定。</span><span class="sxs-lookup"><span data-stu-id="0e669-147">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="0e669-148">如果您選取**包含上述相關性截止分數的檔案**，然後會啟用**問題**。</span><span class="sxs-lookup"><span data-stu-id="0e669-148">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled.</span></span> <span data-ttu-id="0e669-149">如果檔案的相關性分數是高於所選問題的截止分數，除非它排除 '進行檢閱' 篩選器，將會匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-149">If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="0e669-150">如果您選取 [**精簡匯出批次**，**取消 dupe**及篩選由 '的檢閱' 欄位選項按鈕隨即啟用。</span><span class="sxs-lookup"><span data-stu-id="0e669-150">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled.</span></span> <span data-ttu-id="0e669-151">如果您選擇**取消 dupe**，然後重複的檔案會根據定義的原則篩選出 [案件層級 （預設值）： 每個一組重複檔案在整個的情況下，從所有但一個檔案將會被取消 duped。</span><span class="sxs-lookup"><span data-stu-id="0e669-151">If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="0e669-152">Custodian 層級： 每個一組重複檔案的相同 custodian，從所有但一個檔案將會被取消 duped。]匯出輸出中包含重複的所有檔案的記錄。</span><span class="sxs-lookup"><span data-stu-id="0e669-152">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files.</span></span> <span data-ttu-id="0e669-153">如果您選擇**的 '進行檢閱' 的篩選器**] 欄位，選取 [**修改] 底下的中繼資料**]，輸入您 **'進行檢閱'** 的欄位設定]。</span><span class="sxs-lookup"><span data-stu-id="0e669-153">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="0e669-154">選取要包含封裝內容中的來源檔案**包含的輸入的檔**。</span><span class="sxs-lookup"><span data-stu-id="0e669-154">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="0e669-155">您可以清除此設定可加速在匯出程序。</span><span class="sxs-lookup"><span data-stu-id="0e669-155">You can clear this setting to speed up the export process.</span></span> <span data-ttu-id="0e669-156">請注意的原生檔案將會在任何情況下匯出。</span><span class="sxs-lookup"><span data-stu-id="0e669-156">Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="0e669-157">[**中繼資料**，選取 [從下列選項中**匯出範本**] 清單中 （一次每個工作階段）。</span><span class="sxs-lookup"><span data-stu-id="0e669-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="0e669-158">**標準**： 基本組資料的項目、 中繼資料，以及屬性。</span><span class="sxs-lookup"><span data-stu-id="0e669-158">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="0e669-159">進階 eDiscovery 中已經處理匯入資料，並將資料匯出至已經含有檔案系統上傳時，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="0e669-159">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="0e669-160">根據預設，匯出的範本建立並填入資料行。</span><span class="sxs-lookup"><span data-stu-id="0e669-160">By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="0e669-161">**全部**： 包括所有處理資料，以及分析與相關性分數的標準中繼資料的完整集合。</span><span class="sxs-lookup"><span data-stu-id="0e669-161">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="0e669-162">此範本時，需要進階電子文件會執行的處理和檔案資料上載到外部系統的第一次。</span><span class="sxs-lookup"><span data-stu-id="0e669-162">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="0e669-163">**問題**： 選取 [**所有問題**，或都選取您已建立的特定問題。</span><span class="sxs-lookup"><span data-stu-id="0e669-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="0e669-164">在 [**目的地**]:</span><span class="sxs-lookup"><span data-stu-id="0e669-164">Under **Destination**:</span></span>
    
    - <span data-ttu-id="0e669-165">**下載到本機電腦**</span><span class="sxs-lookup"><span data-stu-id="0e669-165">**Download to local machine**</span></span>
    
    - <span data-ttu-id="0e669-166">**匯出至使用者定義的 Azure blob**： 如果選取此項，您可以指定容器 URL 和 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="0e669-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="0e669-167">一旦匯出套件儲存至使用者定義的 Azure blob、 資料不會再由進階電子文件;它是由 Azure blob 中的管理。</span><span class="sxs-lookup"><span data-stu-id="0e669-167">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob.</span></span> <span data-ttu-id="0e669-168">這表示如果您刪除這種情況，匯出的檔案都會仍保留在 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="0e669-168">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="0e669-169">**儲存 SAS 語彙基元未來匯出工作階段**： 如果選取這個選項，會被 SAS 語彙基元加密供日後使用的進階電子文件內部資料庫中。</span><span class="sxs-lookup"><span data-stu-id="0e669-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="0e669-170">目前 SAS 語彙基元，會在一個月後到期。</span><span class="sxs-lookup"><span data-stu-id="0e669-170">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="0e669-171">如果您嘗試下載您需要復原最後一個工作階段多個月份之後，然後再次匯出。</span><span class="sxs-lookup"><span data-stu-id="0e669-171">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="0e669-172">按一下 [**修改]** 若要設定的 '進行檢閱'] 欄位。</span><span class="sxs-lookup"><span data-stu-id="0e669-172">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![匯出批次的檢閱欄位設定為設定](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="0e669-174">在**檢閱欄位設定**，在 [**選取案例**] 下拉式清單中，選取案例和檢閱的範圍。</span><span class="sxs-lookup"><span data-stu-id="0e669-174">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review.</span></span> <span data-ttu-id="0e669-175">根據您的選取範圍所顯示的設定。</span><span class="sxs-lookup"><span data-stu-id="0e669-175">The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="0e669-176">**檢閱所有**（預設值）： 依預設已選取所有的電子郵件、 附件和文件。</span><span class="sxs-lookup"><span data-stu-id="0e669-176">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="0e669-177">**檢閱一組中的所有唯一內容**： 電子郵件中的唯一附件 Inclusives 和唯一的內含副本，設定層級，從每個一組完全重複的代表性。</span><span class="sxs-lookup"><span data-stu-id="0e669-177">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="0e669-178">**檢閱一組-無 （含） 的副本中的所有唯一內容**： Inclusives，電子郵件中的唯一附件設定層級，從每個一組完全重複的代表性。</span><span class="sxs-lookup"><span data-stu-id="0e669-178">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="0e669-179">**檢閱所有唯一內容及相關的家長監護檔案**： Inclusives，電子郵件設定層級，代表從完全重複的項目，每組中的唯一附件展開到包含系列的檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-179">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="0e669-180">**自訂**（可讓您定義的選項] 對話方塊中）： 預設值是以保留目前的選取項目，並啟用所有的對話方塊選項，允許其選取項目。</span><span class="sxs-lookup"><span data-stu-id="0e669-180">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection.</span></span> <span data-ttu-id="0e669-181">如果您選取此選項，您可以再自訂電子郵件、 文件、 附件的設定及其他。</span><span class="sxs-lookup"><span data-stu-id="0e669-181">If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="0e669-182">在 [**電子郵件**，選取您想要匯出之電子的郵件。</span><span class="sxs-lookup"><span data-stu-id="0e669-182">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="0e669-183">**所有的電子郵件**: （預設值） 會選取所有的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0e669-183">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="0e669-184">**Inclusives**: （含） 的電子郵件是否在執行緒中，最後一個電子郵件，並且包含所有其他電子郵件從執行緒。</span><span class="sxs-lookup"><span data-stu-id="0e669-184">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="0e669-185">**Inclusives 和唯一的內含副本**: （含） 的複本，並具有相同的主旨、 內文和附件; inclusives唯一內含副本是唯一的複本這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0e669-185">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="0e669-186">在 [**文件**，選取您想要匯出的文件。</span><span class="sxs-lookup"><span data-stu-id="0e669-186">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="0e669-187">**所有文件**: （預設值） 會選取所有文件。</span><span class="sxs-lookup"><span data-stu-id="0e669-187">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="0e669-188">**樞紐分析表**： 選擇作為近似重複項目組，通常用於作為基準檢閱設定的具有代表性的檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-188">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="0e669-189">**從完全重複的每一組代表性**： 唯一的近似重複檔案 （包含樞紐分析表）。</span><span class="sxs-lookup"><span data-stu-id="0e669-189">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="0e669-190">在 [**附件**]，選取您想要匯出的附件。</span><span class="sxs-lookup"><span data-stu-id="0e669-190">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="0e669-191">**所有附件**: （預設值） 會選取所有附件。</span><span class="sxs-lookup"><span data-stu-id="0e669-191">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="0e669-192">**附件案例層級的唯一方式**： 指定案例中的唯一的附件檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-192">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="0e669-193">**電子郵件中的唯一附件設定層級**： 中指定的電子郵件案例的唯一的附件檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-193">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="0e669-194">下**Micellaneous**，您可以選擇**將視為附件為文件**、**將視為作為文件的電子郵件**，或**展開並包括系列的檔案**。</span><span class="sxs-lookup"><span data-stu-id="0e669-194">Under**Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**.</span></span> <span data-ttu-id="0e669-195">當您選擇**展開並包括家庭檔案**，會加上旗標供檢閱每個檔案時，也被標示所有檔案的相同的家庭。</span><span class="sxs-lookup"><span data-stu-id="0e669-195">When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="0e669-196">選擇 [**儲存**] 以儲存設定。</span><span class="sxs-lookup"><span data-stu-id="0e669-196">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="0e669-197">指定匯出參數之後，若要啟動匯出批次，請按一下 [**建立匯出工作階段**]。</span><span class="sxs-lookup"><span data-stu-id="0e669-197">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="0e669-198">在匯出期間，狀態會顯示在 [**工作狀態**。</span><span class="sxs-lookup"><span data-stu-id="0e669-198">During export, the status is displayed in **Task status**.</span></span> <span data-ttu-id="0e669-199">結果會顯示在**匯出摘要**。</span><span class="sxs-lookup"><span data-stu-id="0e669-199">The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="0e669-200">在 [**檔案下載**] 視窗中，按一下 [**複製到剪貼簿**複製的匯出金鑰]。</span><span class="sxs-lookup"><span data-stu-id="0e669-200">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![下載檔案](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="0e669-202">按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e669-202">Click **Close**.</span></span> 
    
    <span data-ttu-id="0e669-203">啟動 eDiscovery 匯出工具。</span><span class="sxs-lookup"><span data-stu-id="0e669-203">The eDiscovery Export Tool is started.</span></span>
    
    ![eDiscovery 匯出工具](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="0e669-205">在**eDiscovery 匯出工具**中：</span><span class="sxs-lookup"><span data-stu-id="0e669-205">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="0e669-206">中**貼上共用的存取簽章，將會用來連線至來源**，請在步驟 7 中該 youcopied 到剪貼簿貼的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="0e669-206">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="0e669-207">按一下 [**瀏覽]** 以選取用來儲存在本機電腦上的下載的匯出檔案的目標位置。</span><span class="sxs-lookup"><span data-stu-id="0e669-207">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="0e669-208">按一下 [**啟動**]。匯出的檔案下載至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="0e669-208">Click **Start**.The export files are downloaded to the local machine.</span></span> <span data-ttu-id="0e669-209">如果您在步驟 4 中所選擇**匯出至使用者定義的 Azure blob** ，工作階段會匯出到您所選擇的 Blob 儲存體 URL 目的地。</span><span class="sxs-lookup"><span data-stu-id="0e669-209">If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="0e669-210">在 [匯出] 報告中的欄位的完整說明，請參閱[匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0e669-210">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="0e669-211">匯出報告輸出檔案</span><span class="sxs-lookup"><span data-stu-id="0e669-211">Export report output files</span></span>
<span data-ttu-id="0e669-212"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="0e669-212"><a name="BK_ExportOutputFIles"> </a></span></span>

<span data-ttu-id="0e669-213">下表列出當您執行匯出批次時所產生的輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-213">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="0e669-214">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="0e669-214">**File name**</span></span>|<span data-ttu-id="0e669-215">**檔案類型**</span><span class="sxs-lookup"><span data-stu-id="0e669-215">**File type**</span></span>|<span data-ttu-id="0e669-216">**描述**</span><span class="sxs-lookup"><span data-stu-id="0e669-216">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e669-217">匯出摘要</span><span class="sxs-lookup"><span data-stu-id="0e669-217">Export summary</span></span>  <br/> |<span data-ttu-id="0e669-218">csv</span><span class="sxs-lookup"><span data-stu-id="0e669-218">csv</span></span>  <br/> |<span data-ttu-id="0e669-219">EDiscovery 匯出工具所產生記錄檔。</span><span class="sxs-lookup"><span data-stu-id="0e669-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="0e669-220">追蹤</span><span class="sxs-lookup"><span data-stu-id="0e669-220">Trace</span></span>  <br/> |<span data-ttu-id="0e669-221">txt</span><span class="sxs-lookup"><span data-stu-id="0e669-221">txt</span></span>  <br/> |<span data-ttu-id="0e669-222">EDiscovery 匯出工具所產生記錄檔。</span><span class="sxs-lookup"><span data-stu-id="0e669-222">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="0e669-223">擷取的文字檔案</span><span class="sxs-lookup"><span data-stu-id="0e669-223">Extracted text files</span></span>  <br/> |<span data-ttu-id="0e669-224">檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="0e669-224">File folder</span></span>  <br/> |<span data-ttu-id="0e669-225">包含匯出的檔案解壓縮的文字檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e669-225">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="0e669-226">輸入] 或 [原生檔案</span><span class="sxs-lookup"><span data-stu-id="0e669-226">Input or native files</span></span>  <br/> |<span data-ttu-id="0e669-227">檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="0e669-227">File folder</span></span>  <br/> |<span data-ttu-id="0e669-228">包含的原生和輸入檔案的匯出檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e669-228">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="0e669-229">匯出清單</span><span class="sxs-lookup"><span data-stu-id="0e669-229">Export list</span></span>  <br/> |<span data-ttu-id="0e669-230">xlsx</span><span class="sxs-lookup"><span data-stu-id="0e669-230">xlsx</span></span>  <br/> |<span data-ttu-id="0e669-231">Xlsx 格式匯出的檔案中繼資料。</span><span class="sxs-lookup"><span data-stu-id="0e669-231">Exported files metadata in xlsx format.</span></span> <span data-ttu-id="0e669-232">若要匯出的範本使用者選取會根據檔案中的欄位。</span><span class="sxs-lookup"><span data-stu-id="0e669-232">Fields in files are according to template user selects to export.</span></span> <span data-ttu-id="0e669-233">如有需要建立一些檔案、 每個包含 100-150 K 資料列。</span><span class="sxs-lookup"><span data-stu-id="0e669-233">If needed, several files are created, each contains 100-150K rows.</span></span> <span data-ttu-id="0e669-234">如果特定值會包含非 Excel 儲存格可以包含多個字元 （目前限制為 32767 個字元），然後將修剪允許的最大長度的值。</span><span class="sxs-lookup"><span data-stu-id="0e669-234">If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed.</span></span> <span data-ttu-id="0e669-235">如果調整值，此儲存格的背景色彩是紅色，這表示使用者 」。電子郵件參與者 」 是可以超過此長度限制，欄位的範例，如果電子郵件已傳送至大型通訊群組。</span><span class="sxs-lookup"><span data-stu-id="0e669-235">If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution.</span></span> <span data-ttu-id="0e669-236">如需詳細資訊輸出欄位，請參閱[匯出報告欄位](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0e669-236">See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.</span></span>  <br/> |
|<span data-ttu-id="0e669-237">載入檔案</span><span class="sxs-lookup"><span data-stu-id="0e669-237">Load file</span></span>  <br/> |<span data-ttu-id="0e669-238">csv</span><span class="sxs-lookup"><span data-stu-id="0e669-238">csv</span></span>  <br/> |<span data-ttu-id="0e669-239">其他應用程式中載入的 csv 格式匯出的檔案中繼資料。</span><span class="sxs-lookup"><span data-stu-id="0e669-239">Exported files metadata in csv format for loading into a different application.</span></span> <span data-ttu-id="0e669-240">若要匯出的範本使用者選取會根據檔案中的欄位。</span><span class="sxs-lookup"><span data-stu-id="0e669-240">Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="0e669-241">成功指示器</span><span class="sxs-lookup"><span data-stu-id="0e669-241">Success indicator</span></span>  <br/> |<span data-ttu-id="0e669-242">txt</span><span class="sxs-lookup"><span data-stu-id="0e669-242">txt</span></span>  <br/> |<span data-ttu-id="0e669-243">匯出至第 3 方 Azure blob 時，才建立。</span><span class="sxs-lookup"><span data-stu-id="0e669-243">Only created when exporting to a 3rd party Azure blob.</span></span> <span data-ttu-id="0e669-244">如果完全成功匯出，將會建立檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-244">If export succeed completely, the file will be created.</span></span> <span data-ttu-id="0e669-245">如果失敗，或部分將不會建立成功檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-245">In case of failure, or partial success the file will not be created.</span></span> <span data-ttu-id="0e669-246">會在根資料夾中，讓上不同匯出批次/工作階段狀態的自動化的追蹤建立檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-246">File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses.</span></span> <span data-ttu-id="0e669-247">這是空的檔案。</span><span class="sxs-lookup"><span data-stu-id="0e669-247">This is an empty file.</span></span> <span data-ttu-id="0e669-248">它的名稱： TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。</span><span class="sxs-lookup"><span data-stu-id="0e669-248">Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0e669-249">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0e669-249">See also</span></span>

[<span data-ttu-id="0e669-250">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="0e669-250">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0e669-251">檢視批次歷程記錄及匯出過去的結果</span><span class="sxs-lookup"><span data-stu-id="0e669-251">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="0e669-252">快速設定 Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="0e669-252">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="0e669-253">匯出報告欄位</span><span class="sxs-lookup"><span data-stu-id="0e669-253">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="0e669-254">匯出 eDiscovery 搜尋結果從 Office 365 時，增加的下載速度</span><span class="sxs-lookup"><span data-stu-id="0e669-254">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)

