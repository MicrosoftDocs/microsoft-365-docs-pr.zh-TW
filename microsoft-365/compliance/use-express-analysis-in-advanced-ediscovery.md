---
title: 在 Office 365 進階電子文件探索中使用快速分析
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: 了解如何執行 Office 365 進階電子文件探索的快速分析模式
ms.openlocfilehash: 41de4b0c4e4e57501fb2a0774c556e2556c3d496
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597310"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="bb754-103">在 Office 365 進階電子文件探索中使用快速分析</span><span class="sxs-lookup"><span data-stu-id="bb754-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="bb754-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="bb754-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="bb754-106">您可以使用**Express 分析**，以快速分析案例，並將結果匯出。</span><span class="sxs-lookup"><span data-stu-id="bb754-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="bb754-107">您可以使用快速分析來計算近似重複項目和電子郵件執行緒及計算佈景主題。</span><span class="sxs-lookup"><span data-stu-id="bb754-107">You can use express analysis to calculate near-duplicates and email threads and calculate themes.</span></span> <span data-ttu-id="bb754-108">您也可以設定特定參數的佈景主題、 文件相似性和匯出檔案[的快速分析進階的設定](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)] 中。</span><span class="sxs-lookup"><span data-stu-id="bb754-108">You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="bb754-109">執行快速分析</span><span class="sxs-lookup"><span data-stu-id="bb754-109">Run Express analysis</span></span>

1. <span data-ttu-id="bb754-110">在**Express 分析**(1)] 索引標籤上，選取 [啟用容器 \* \* Express 分析 \* \* (2)，和 [**進階設定**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bb754-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![快速分析] 頁面的螢幕擷取畫面](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="bb754-112">在 [**分析參數**：</span><span class="sxs-lookup"><span data-stu-id="bb754-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="bb754-113">如果您想要執行分析，請檢查**計算近似重複項目和電子郵件執行緒**。</span><span class="sxs-lookup"><span data-stu-id="bb754-113">Check **Calculate near-duplicates and email threads** if you want to run the analysis.</span></span> <span data-ttu-id="bb754-114">此為預設選取的選項。</span><span class="sxs-lookup"><span data-stu-id="bb754-114">It is selected by default.</span></span> 
    
  - <span data-ttu-id="bb754-115">請檢查**計算的佈景主題**處理所有檔案，並將佈景主題指派給他們。</span><span class="sxs-lookup"><span data-stu-id="bb754-115">Check **Calculate Themes** to process all files and assign themes to them.</span></span> <span data-ttu-id="bb754-116">此為預設選取的選項。</span><span class="sxs-lookup"><span data-stu-id="bb754-116">It is selected by default.</span></span> 
    
3. <span data-ttu-id="bb754-117">在 [**匯出目的地**： 之下</span><span class="sxs-lookup"><span data-stu-id="bb754-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="bb754-118">檢查下載到您本機電腦的 [**下載到本機電腦**。</span><span class="sxs-lookup"><span data-stu-id="bb754-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="bb754-119">如果您檢查**匯出至使用者定義的 Azure blob**然後您也可以指定容器 URL 和 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="bb754-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bb754-120">一旦匯出套件儲存至使用者定義的 Azure blob，資料不會再由進階電子文件。</span><span class="sxs-lookup"><span data-stu-id="bb754-120">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery.</span></span> <span data-ttu-id="bb754-121">它是由 Azure blob 中的管理。</span><span class="sxs-lookup"><span data-stu-id="bb754-121">it is managed by the Azure blob.</span></span> <span data-ttu-id="bb754-122">這表示如果您刪除這種情況，匯出的檔案都會仍保留在 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="bb754-122">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="bb754-123">**儲存 SAS 語彙基元未來匯出工作階段**： 如果選取這個選項，會被 SAS 語彙基元加密供日後使用的進階電子文件內部資料庫中。</span><span class="sxs-lookup"><span data-stu-id="bb754-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb754-124">目前 SAS 語彙基元，會在一個月後到期。</span><span class="sxs-lookup"><span data-stu-id="bb754-124">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="bb754-125">如果您嘗試下載您需要復原最後一個工作階段多個月份之後，然後再次匯出。</span><span class="sxs-lookup"><span data-stu-id="bb754-125">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="bb754-126">若要啟動快速分析與預設設定，選擇 [ **Express 分析**，並會顯示 [**工作狀態**] 頁面</span><span class="sxs-lookup"><span data-stu-id="bb754-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="bb754-127">**工作狀態**] 頁面上，您可以展開顯示快速執行的詳細**程序**、**分析**及**匯出**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bb754-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![螢幕擷取畫面的進階電子文件探索 Express 分析工作狀態] 頁面](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="bb754-129">選擇 [ **Express 分析摘要**] 頁面上列出執行的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="bb754-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="bb754-130">在 [ **Express 分析摘要**] 頁面底部，選擇 [下載分析檔案 tp 本機電腦的 [**下載前次工作階段**。</span><span class="sxs-lookup"><span data-stu-id="bb754-130">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer.</span></span> <span data-ttu-id="bb754-131">您可以下載 eDiscovery 匯出工具，並將貼到 eDiscovery 匯出工具的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="bb754-131">You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="bb754-132">快速分析進階的設定</span><span class="sxs-lookup"><span data-stu-id="bb754-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="bb754-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="bb754-133"><a name="BK_AdvancedSettings"> </a></span></span>

<span data-ttu-id="bb754-134">您可以選擇性地設定若要變更預設 Express 分析參數的 [**進階設定]** 。</span><span class="sxs-lookup"><span data-stu-id="bb754-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="bb754-135">在 [**分析**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="bb754-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="bb754-136">在**接近重複項目和電子郵件執行緒**，輸入**文件相似性**的值，或接受預設值是 65%。</span><span class="sxs-lookup"><span data-stu-id="bb754-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="bb754-137">**佈景主題的最大數目**中輸入或選取值來建立佈景主題數目。</span><span class="sxs-lookup"><span data-stu-id="bb754-137">In the **Max number of themes** enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="bb754-138">預設值為 200。</span><span class="sxs-lookup"><span data-stu-id="bb754-138">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bb754-139">增加的佈景主題數目會影響效能，以及佈景主題一般化的能力。</span><span class="sxs-lookup"><span data-stu-id="bb754-139">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="bb754-140">佈景主題數目愈高，更細微它們是。</span><span class="sxs-lookup"><span data-stu-id="bb754-140">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="bb754-141">例如，如果 50 個佈景主題的一組包括 「 籃球、 Spurs、 Clippers，Lakers 」; 例如佈景主題300 佈景主題可能會包含不同的佈景主題: 「 Spurs 」、 「 Clippers 」、 「 Lakers 」。</span><span class="sxs-lookup"><span data-stu-id="bb754-141">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="bb754-142">如果您不有任何認知佈景主題的 「 籃球 」，並使用 ECA 這項功能，看到佈景主題 」 籃球 」 可能是很有用。</span><span class="sxs-lookup"><span data-stu-id="bb754-142">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="bb754-143">但是，如果處理有太多的佈景主題，您可能永遠不會看到 「 籃球 」 這個字後，可能不知道，Spurs 和 Clippers 是很好的籃球佈景主題，若要檢閱，而非移入的項目會開機並用於字形。</span><span class="sxs-lookup"><span data-stu-id="bb754-143">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="bb754-144">**建議的佈景主題**中選擇 [**修改**]，可提供建議來控制處理的佈景主題的佈景主題文字。</span><span class="sxs-lookup"><span data-stu-id="bb754-144">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing.</span></span> <span data-ttu-id="bb754-145">進階電子文件探索會專注於這些建議的字詞，並嘗試建立一或多個相關的佈景主題，根據 「 最大的佈景主題的數字 」 的設定。</span><span class="sxs-lookup"><span data-stu-id="bb754-145">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="bb754-146">例如，如果建議的單字"computer"，且您指定作為 」 主題數目上限 「"2"，進階電子文件會嘗試產生關聯到 「 電腦 」 這個字的兩個佈景主題。</span><span class="sxs-lookup"><span data-stu-id="bb754-146">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="bb754-147">佈景主題的兩個可能會 「 電腦軟體 」 和 「 電腦硬體 」，例如。</span><span class="sxs-lookup"><span data-stu-id="bb754-147">The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![新增建議的佈景主題](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="bb754-149">**模式**從下拉式清單中選取**佈景主題**選項：</span><span class="sxs-lookup"><span data-stu-id="bb754-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="bb754-150">**建立並套用模型**： 計算的模型檔案的線段的佈景主題，並再將它們之間的檔案。</span><span class="sxs-lookup"><span data-stu-id="bb754-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="bb754-151">**建立模型**： 計算從檔案的線段的佈景主題模型。</span><span class="sxs-lookup"><span data-stu-id="bb754-151">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="bb754-152">在其他時候分別完成的分割檔案套用程序。</span><span class="sxs-lookup"><span data-stu-id="bb754-152">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="bb754-153">**套用模型**： 是否先前建立及尚未套用模型，僅會顯示此選項。</span><span class="sxs-lookup"><span data-stu-id="bb754-153">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="bb754-154">這會將佈景主題為基礎的檔案。</span><span class="sxs-lookup"><span data-stu-id="bb754-154">This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="bb754-155">在 [**匯出**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="bb754-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="bb754-156">在 [**選取匯出批次**中：</span><span class="sxs-lookup"><span data-stu-id="bb754-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="bb754-157">從**匯出批次**] 清單中，選取批次名稱，或將結果匯出至匯出批次 01、 （預設批次）。</span><span class="sxs-lookup"><span data-stu-id="bb754-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="bb754-158">若要匯出結果的新檔案新增至現有的情況下，繼續執行您目前的批次。</span><span class="sxs-lookup"><span data-stu-id="bb754-158">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="bb754-159">批次中建立工作階段、 選取相同的批次數目，並按一下 [**建立匯出工作階段**中，您可以使用此選項為前一個批次，匯出相同的參數，以累加方式。</span><span class="sxs-lookup"><span data-stu-id="bb754-159">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="bb754-160">若要匯出至新的批次時，按一下 [**新增**![新增圖示](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)和**批次名稱**輸入新名稱 （或接受預設值） 和 [描述] 中**批次描述**。</span><span class="sxs-lookup"><span data-stu-id="bb754-160">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="bb754-161">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb754-161">Click **OK**.</span></span>
    
  - <span data-ttu-id="bb754-162">若要編輯的批次名稱或描述，請選取中**匯出批次**的名稱，請按一下 [**編輯**![編輯圖示](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，然後再修改欄位。</span><span class="sxs-lookup"><span data-stu-id="bb754-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb754-163">您已執行匯出批次的工作階段之後，他們無法刪除。</span><span class="sxs-lookup"><span data-stu-id="bb754-163">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="bb754-164">此外，一旦執行第一個工作階段後，可以編輯只有一些參數。</span><span class="sxs-lookup"><span data-stu-id="bb754-164">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="bb754-165">若要建立的重複匯出批次，請選擇 [**重複匯出批次**![建立重複的匯出批次圖示](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)和在 [資訊] 面板中輸入名稱和描述重複的批次。</span><span class="sxs-lookup"><span data-stu-id="bb754-165">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="bb754-166">若要刪除匯出批次，請選擇 [**刪除**![刪除匯出批次圖示](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="bb754-166">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="bb754-167">若要檢視的批次歷程記錄，請選擇 [**批次歷程記錄**![檢視歷程記錄圖示](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="bb754-167">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="bb754-168">在 [定義 p 下**opulation:** 選取**包括上方相關性截止分數的檔案**及/或**精簡匯出批次**，如果您想要微調您匯出批次的設定。</span><span class="sxs-lookup"><span data-stu-id="bb754-168">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> <span data-ttu-id="bb754-169">如果您選取**包含上述相關性截止分數的檔案**，然後已啟用**問題**，且如果檔案的相關性分數是高於所選問題的截止分數，然後將檔案匯出。</span><span class="sxs-lookup"><span data-stu-id="bb754-169">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported.</span></span> <span data-ttu-id="bb754-170">將匯出的檔案，除非已由排除 '**檢閱**篩選器。</span><span class="sxs-lookup"><span data-stu-id="bb754-170">The file will be exported unless it's excluded by the ' **For review** filter.</span></span> <span data-ttu-id="bb754-171">如果您選取 [**精簡匯出批次**，然後**取消 dupe**和 **'的檢閱' 的篩選器] 欄位**選項] 按鈕隨即啟用。</span><span class="sxs-lookup"><span data-stu-id="bb754-171">If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled.</span></span> <span data-ttu-id="bb754-172">如果您選擇**取消 dupe**，然後重複檔案將會篩選出根據定義的原則: [案件層級 （預設值）： 每個一組重複檔案在整個的情況下，從所有但一個檔案將會被取消 duped。</span><span class="sxs-lookup"><span data-stu-id="bb754-172">If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="bb754-173">Custodian 層級： 每個一組重複檔案的相同 custodian，從所有但一個檔案將會被取消 duped。</span><span class="sxs-lookup"><span data-stu-id="bb754-173">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.</span></span> <span data-ttu-id="bb754-174">使用匯出輸出中重複的所有檔案的記錄。</span><span class="sxs-lookup"><span data-stu-id="bb754-174">A record of all duplicate files is available in export output.</span></span> <span data-ttu-id="bb754-175">如果您選擇**的 '進行檢閱' 的篩選器**] 欄位，選取 [**修改] 底下的中繼資料**]，輸入您 **'進行檢閱'** 的欄位設定]。</span><span class="sxs-lookup"><span data-stu-id="bb754-175">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="bb754-176">選取要包含封裝內容中的來源檔案**包含的輸入的檔**。</span><span class="sxs-lookup"><span data-stu-id="bb754-176">Select **Include input files**to include source files in the package content.</span></span> <span data-ttu-id="bb754-177">您可以清除此選項可加速在匯出程序。</span><span class="sxs-lookup"><span data-stu-id="bb754-177">You can clear this option to speed up the export process.</span></span> <span data-ttu-id="bb754-178">請注意的原生檔案將會在任何情況下匯出。</span><span class="sxs-lookup"><span data-stu-id="bb754-178">Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="bb754-179">底下**定義中繼資料**，選取 [從下列選項中**匯出範本**] 清單中 （一次每個工作階段）。</span><span class="sxs-lookup"><span data-stu-id="bb754-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="bb754-180">**標準**： 基本組資料的項目、 中繼資料，以及屬性。</span><span class="sxs-lookup"><span data-stu-id="bb754-180">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="bb754-181">進階 eDiscovery 中已經處理匯入資料，並將資料匯出至已經含有檔案系統上傳時，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb754-181">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="bb754-182">根據預設，匯出的範本建立並填入資料行。</span><span class="sxs-lookup"><span data-stu-id="bb754-182">By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="bb754-183">**全部**： 包括所有處理資料，以及分析與相關性分數的標準中繼資料的完整集合。</span><span class="sxs-lookup"><span data-stu-id="bb754-183">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="bb754-184">此範本時，需要進階電子文件會執行的處理和檔案資料上載到外部系統的第一次。</span><span class="sxs-lookup"><span data-stu-id="bb754-184">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="bb754-185">**問題**： 選取 [**所有問題**，或都選取您已建立的特定問題。</span><span class="sxs-lookup"><span data-stu-id="bb754-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="bb754-186">選擇 **[確定]** 以儲存 [進階] 設定，**還原成預設值**使用預設值，或 [**取消**] 取消 [設定進階的設定。</span><span class="sxs-lookup"><span data-stu-id="bb754-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bb754-187">請參閱</span><span class="sxs-lookup"><span data-stu-id="bb754-187">See also</span></span>
<span data-ttu-id="bb754-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="bb754-188"><a name="BK_AdvancedSettings"> </a></span></span>

[<span data-ttu-id="bb754-189">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="bb754-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

