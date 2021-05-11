---
title: 匯出內容搜尋報告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 您可以匯出搜尋結果報告，而不是在 Office 365 中的安全性 & 合規性中心匯出內容搜尋的實際結果。 報告包含搜尋結果摘要及檔，其中包含每個要匯出之專案的詳細資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311567"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="89ae1-104">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="89ae1-104">Export a Content search report</span></span>

<span data-ttu-id="89ae1-105">您可以匯出實際搜尋結果時所產生的報表，而不是從 Microsoft 365 合規性中心的內容搜尋中匯出完整的搜尋結果集合 (或從與核心 eDiscovery 案例) 相關聯的搜尋中匯出。</span><span class="sxs-lookup"><span data-stu-id="89ae1-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="89ae1-106">當您匯出報告時，報告檔案會下載至本機電腦上與內容搜尋同名的資料夾，但附加 *_ReportsOnly*。</span><span class="sxs-lookup"><span data-stu-id="89ae1-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="89ae1-107">例如，如果內容搜尋命名為  *ContosoCase0815*，則會將報告下載至名為 *ContosoCase0815_ReportsOnly* 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="89ae1-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="89ae1-108">如需報告中所包含檔的清單，請參閱 [報告的內容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="89ae1-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="89ae1-109">匯出搜尋報告之前</span><span class="sxs-lookup"><span data-stu-id="89ae1-109">Before you export a search report</span></span>

- <span data-ttu-id="89ae1-110">若要匯出搜尋報告，您必須在安全性 & 合規性中心內指派符合性搜尋管理角色。</span><span class="sxs-lookup"><span data-stu-id="89ae1-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="89ae1-111">此角色預設會指派給內建的 eDiscovery 管理員和組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="89ae1-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="89ae1-112">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="89ae1-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="89ae1-113">當您匯出報告時，資料會暫時儲存在 Microsoft 雲端的 Azure 儲存體位置，然後再下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="89ae1-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="89ae1-114">確定您的組織可以連線到 Azure 中的端點，也就是 **\* blob.core.windows.net** (此萬用字元代表匯出) 的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="89ae1-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="89ae1-115">搜尋結果資料會在建立後的兩周內從 Azure 儲存體位置刪除。</span><span class="sxs-lookup"><span data-stu-id="89ae1-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="89ae1-116">您用來匯出搜尋結果的電腦必須符合下列系統需求：</span><span class="sxs-lookup"><span data-stu-id="89ae1-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="89ae1-117">最新版本的 Windows (32 位或 64-位) </span><span class="sxs-lookup"><span data-stu-id="89ae1-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="89ae1-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="89ae1-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="89ae1-119">您必須使用下列其中一種支援的瀏覽器執行 eDiscovery 匯出工具<sup>1</sup>：</span><span class="sxs-lookup"><span data-stu-id="89ae1-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="89ae1-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="89ae1-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="89ae1-121">或</span><span class="sxs-lookup"><span data-stu-id="89ae1-121">OR</span></span>

  - <span data-ttu-id="89ae1-122">Microsoft Internet Explorer 10 和更新版本</span><span class="sxs-lookup"><span data-stu-id="89ae1-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="89ae1-123"><sup>1</sup> Microsoft 不會製造協力廠商擴充模組或 ClickOnce 應用程式的附加元件。</span><span class="sxs-lookup"><span data-stu-id="89ae1-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="89ae1-124">使用不受支援的瀏覽器匯出搜尋結果時，不支援協力廠商分機或附加元件。</span><span class="sxs-lookup"><span data-stu-id="89ae1-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="89ae1-125"><sup>2</sup>因為 Microsoft Edge 的最近變更，所以預設不再啟用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="89ae1-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="89ae1-126">如需在 Edge 中啟用 ClickOnce 支援的相關指示，請參閱[使用 Microsoft Edge 中的 eDiscovery 匯出工具](configure-edge-to-export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="89ae1-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="89ae1-127">如果搜尋傳回的結果總大小超過 2 TB，則匯出報告會失敗。</span><span class="sxs-lookup"><span data-stu-id="89ae1-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="89ae1-128">若要順利匯出報告，請嘗試縮小範圍並重新執行搜尋，使結果的預估大小小於 2 TB。</span><span class="sxs-lookup"><span data-stu-id="89ae1-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="89ae1-129">如果搜尋結果超過7天，且提交匯出報告工作，則會顯示錯誤訊息，提示您重新執行搜尋以更新搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="89ae1-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="89ae1-130">如果發生這種情況，請取消匯出，然後重新執行搜尋，然後再次開始匯出。</span><span class="sxs-lookup"><span data-stu-id="89ae1-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="89ae1-131">匯出搜尋報告時，會依據同時執行的匯出數目上限，以及單一使用者可執行檔匯出數目上限而進行計數。</span><span class="sxs-lookup"><span data-stu-id="89ae1-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="89ae1-132">如需匯出限制的相關資訊，請參閱 [匯出內容搜尋結果](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="89ae1-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="89ae1-133">步驟1：產生要匯出的報告</span><span class="sxs-lookup"><span data-stu-id="89ae1-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="89ae1-134">第一步是準備報表，以下載至電腦匯出。</span><span class="sxs-lookup"><span data-stu-id="89ae1-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="89ae1-135">當您匯出報告時，報表檔會上傳至 Microsoft 雲端的 Azure 儲存體區域。</span><span class="sxs-lookup"><span data-stu-id="89ae1-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="89ae1-136">在 [Microsoft 365 規範中心] 中，選取您要從中匯出報告的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="89ae1-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="89ae1-137">在 [搜尋飛出] 頁面底部的 [ **動作** ] 功能表上，按一下 [ **匯出報告**]。</span><span class="sxs-lookup"><span data-stu-id="89ae1-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![[動作] 功能表中的匯出報表選項](../media/ActionMenuExportReport.png)

   <span data-ttu-id="89ae1-139">[ **匯出報告** 飛出] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="89ae1-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="89ae1-140">可用於匯出搜尋資訊的匯出報告選項，取決於搜尋結果是位於信箱或網站中，或是兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="89ae1-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="89ae1-141">在 [ **輸出選項**] 底下，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="89ae1-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![匯出輸出選項](../media/ExportOutputOptions.png)

    - <span data-ttu-id="89ae1-143">**所有專案（不包括具有無法辨識格式的專案）都會加密，或是未以其他原因為索引**。</span><span class="sxs-lookup"><span data-stu-id="89ae1-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="89ae1-144">此選項只會匯出索引項目目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="89ae1-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="89ae1-145">**所有專案（包括具有無法辨識格式的專案）都會加密，或是未以其他原因為索引**。</span><span class="sxs-lookup"><span data-stu-id="89ae1-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="89ae1-146">這個選項會匯出有關索引及未編制索引之專案的資訊。</span><span class="sxs-lookup"><span data-stu-id="89ae1-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="89ae1-147">**僅限未辨識格式的專案、已加密或尚未為其他原因編制索引**。</span><span class="sxs-lookup"><span data-stu-id="89ae1-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="89ae1-148">此選項只會匯出未編制索引項目目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="89ae1-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="89ae1-149">設定 [**啟用 Exchange 內容的重復資料** 刪除] 選項。</span><span class="sxs-lookup"><span data-stu-id="89ae1-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="89ae1-150">如果您選取此選項，則會在 [匯出摘要報告] 中包含重復資料刪除之前 (的重複郵件計數和重復資料消除) 。</span><span class="sxs-lookup"><span data-stu-id="89ae1-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="89ae1-151">此外，只有一份郵件副本會包含在 manifest.xml 檔中。</span><span class="sxs-lookup"><span data-stu-id="89ae1-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="89ae1-152">但「匯出結果報告」會包含重複郵件之每個副本的資料列，以便您識別包含重複郵件複本的信箱。</span><span class="sxs-lookup"><span data-stu-id="89ae1-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="89ae1-153">如需有關匯出報告的詳細資訊，請參閱 [報告中包含的內容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="89ae1-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="89ae1-154">如果您未選取此選項，則匯出報告將會包含有關搜尋傳回之所有郵件的資訊，包含重複專案。</span><span class="sxs-lookup"><span data-stu-id="89ae1-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="89ae1-155">如需有關重復資料刪除以及如何識別重複專案的詳細資訊，請參閱 [eDiscovery 搜尋結果中的重復資料](de-duplication-in-ediscovery-search-results.md)刪除。</span><span class="sxs-lookup"><span data-stu-id="89ae1-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="89ae1-156">按一下 [ **產生報告**]。</span><span class="sxs-lookup"><span data-stu-id="89ae1-156">Click **Generate report**.</span></span>

   <span data-ttu-id="89ae1-157">搜尋報告已準備好下載，這表示會將報告檔上傳至 Microsoft 雲端的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="89ae1-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="89ae1-158">可能會花幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="89ae1-158">This may take several minutes.</span></span>

<span data-ttu-id="89ae1-159">如需下載匯出之搜尋報告的指示，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="89ae1-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="89ae1-160">步驟2：下載報表</span><span class="sxs-lookup"><span data-stu-id="89ae1-160">Step 2: Download the report</span></span>

<span data-ttu-id="89ae1-161">下一步是將報表從 Azure 儲存體區域下載到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="89ae1-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="89ae1-162">在 Microsoft 365 規範中心的 [**內容搜尋**] 頁面上，選取 [**匯出**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="89ae1-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="89ae1-163">您可能 **需要按一下 [** 重新整理] 以更新匯出工作清單，使其顯示您建立的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="89ae1-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="89ae1-164">匯出報告工作與對應的搜尋同名，但 **_ReportsOnly** 附加至搜尋名稱。</span><span class="sxs-lookup"><span data-stu-id="89ae1-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="89ae1-165">選取您在步驟1中建立的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="89ae1-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="89ae1-166">按一下 [**匯出索引鍵**] 底下的 [**匯出報告**] 頁面上的 [**複製到剪貼** 簿]。</span><span class="sxs-lookup"><span data-stu-id="89ae1-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="89ae1-167">您可以在步驟6中使用此機碼下載搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="89ae1-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="89ae1-168">由於任何人都可以安裝並啟動 eDiscovery 匯出工具，然後使用此機碼來下載搜尋報告，請務必採取預防措施來保護此機碼，就像您保護密碼或其他安全性相關的資訊一樣。</span><span class="sxs-lookup"><span data-stu-id="89ae1-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="89ae1-169">按一下彈出頁面頂端的 [ **下載結果**]。</span><span class="sxs-lookup"><span data-stu-id="89ae1-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="89ae1-170">如果系統提示您安裝 **EDiscovery 匯出工具**，請按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="89ae1-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="89ae1-171">在 [ **EDiscovery 匯出工具**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="89ae1-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![eDiscovery 匯出工具](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="89ae1-173">在適當的方塊中貼上您在步驟3中複製的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="89ae1-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="89ae1-174">按一下 **[流覽]** 以指定您要下載搜尋報告檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="89ae1-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="89ae1-175">按一下 [開始] 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="89ae1-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="89ae1-176">**EDiscovery 匯出工具** 會顯示匯出程式的狀態資訊，包括估計要下載之其餘專案的數位 (和大小) 。</span><span class="sxs-lookup"><span data-stu-id="89ae1-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="89ae1-177">匯出程式完成後，您可以在下載檔案的位置存取檔案。</span><span class="sxs-lookup"><span data-stu-id="89ae1-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="89ae1-178">報告中包含的內容</span><span class="sxs-lookup"><span data-stu-id="89ae1-178">What's included in the report</span></span>

<span data-ttu-id="89ae1-179">當您產生及匯出內容搜尋結果的報告時，會下載下列檔：</span><span class="sxs-lookup"><span data-stu-id="89ae1-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="89ae1-180">**匯出摘要：** 包含匯出摘要的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="89ae1-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="89ae1-181">這包括下列資訊：搜尋的內容來源數目、每個內容位置的搜尋結果數目、預估的專案數、要匯出的實際專案數，以及所要匯出之專案的預估和實際大小。</span><span class="sxs-lookup"><span data-stu-id="89ae1-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="89ae1-182">如果您在匯出報告時包含未編制索引的專案，則未編制索引的專案數會包含在預估的搜尋結果總數和下載之搜尋結果的總數中，如果您要匯出的搜尋結果) 所列于 [匯出摘要] 報告中的結果 (。</span><span class="sxs-lookup"><span data-stu-id="89ae1-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="89ae1-183">換句話說，將下載的專案總數等於估計的結果總數和未編制索引的專案總數。</span><span class="sxs-lookup"><span data-stu-id="89ae1-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="89ae1-184">**資訊清單：** 包含搜尋結果中所包含之每個專案相關資訊的資訊清單檔案 (以 XML 格式) 。</span><span class="sxs-lookup"><span data-stu-id="89ae1-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="89ae1-185">如果您已啟用 [重復資料刪除] 選項，則不會在資訊清單檔案中包含重複的郵件。</span><span class="sxs-lookup"><span data-stu-id="89ae1-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="89ae1-186">**結果：** 包含一列的 Excel 檔，其中包含每個要連同搜尋結果一起匯出之索引項目目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="89ae1-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="89ae1-187">針對電子郵件，結果記錄檔包含每封郵件的相關資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="89ae1-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="89ae1-188">來源信箱中郵件的位置 (，包含郵件是在主要或封存信箱) 中。</span><span class="sxs-lookup"><span data-stu-id="89ae1-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="89ae1-189">傳送或接收郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="89ae1-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="89ae1-190">郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="89ae1-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="89ae1-191">郵件的寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="89ae1-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="89ae1-192">針對來自 SharePoint 和商務用 OneDrive 網站的檔，結果記錄檔包含每個檔的相關資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="89ae1-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="89ae1-193">檔的 URL。</span><span class="sxs-lookup"><span data-stu-id="89ae1-193">The URL for the document.</span></span>

  - <span data-ttu-id="89ae1-194">檔所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="89ae1-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="89ae1-195">上次修改檔的日期。</span><span class="sxs-lookup"><span data-stu-id="89ae1-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="89ae1-196">位於結果記錄檔的 [主旨] 欄中的檔 (名稱) 。</span><span class="sxs-lookup"><span data-stu-id="89ae1-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="89ae1-197">**結果** 報告中的列數應該等於搜尋結果的總數減去 [未 **編制索引的專案**] 報告中所列的總專案數。</span><span class="sxs-lookup"><span data-stu-id="89ae1-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="89ae1-198">**蹤跡：記錄** 檔，包含匯出程式的詳細記錄資訊，可協助您在匯出期間發現問題。</span><span class="sxs-lookup"><span data-stu-id="89ae1-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="89ae1-199">如果您使用 Microsoft 支援部門開啟與匯出搜尋報告相關的問題，可能會要求您提供此追蹤記錄檔。</span><span class="sxs-lookup"><span data-stu-id="89ae1-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="89ae1-200">未 **編制索引的專案：** Excel 檔，包含搜尋結果中所包含之任何未編制索引項目目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="89ae1-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="89ae1-201">如果您在產生搜尋結果報告時未包含未編制索引的專案，則此報告仍會下載，但會是空的。</span><span class="sxs-lookup"><span data-stu-id="89ae1-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
