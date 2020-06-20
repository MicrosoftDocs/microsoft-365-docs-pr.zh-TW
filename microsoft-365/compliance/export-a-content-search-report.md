---
title: 匯出內容搜尋報告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: 您可以匯出搜尋結果報告，而不是在 Office 365 的安全性 & 規範中心中匯出內容搜尋的實際結果。 報告包含搜尋結果摘要及檔，其中包含每個要匯出之專案的詳細資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25525a0670f31a7e962fb72f6d1559381e8b33cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817772"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="a94d5-104">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="a94d5-104">Export a Content Search report</span></span>

<span data-ttu-id="a94d5-105">在 [安全性 & 規範中心] （以及從與 eDiscovery 案例相關聯的內容搜尋）中匯出搜尋結果的完整集合時，您可以匯出在匯出搜尋結果時所產生的相同報告。</span><span class="sxs-lookup"><span data-stu-id="a94d5-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="a94d5-106">當您匯出報表時，它會下載到與內容搜尋同名的資料夾，但附加 *_ReportsOnly*。</span><span class="sxs-lookup"><span data-stu-id="a94d5-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="a94d5-107">例如，如果內容搜尋命名為*ContosoCase0815*，則會將報告下載至名為*ContosoCase0815_ReportsOnly*的資料夾。</span><span class="sxs-lookup"><span data-stu-id="a94d5-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="a94d5-108">如需報告中所包含檔的清單，請參閱[報告的內容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="a94d5-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="a94d5-109">指派角色及檢查系統需求</span><span class="sxs-lookup"><span data-stu-id="a94d5-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="a94d5-110">若要匯出內容搜尋報告，您必須在安全性 & 規範中心內指派符合性搜尋管理角色。</span><span class="sxs-lookup"><span data-stu-id="a94d5-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="a94d5-111">此角色預設會指派給內建的 eDiscovery 管理員和組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="a94d5-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="a94d5-112">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a94d5-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="a94d5-113">當您匯出報告時，資料會暫時儲存在 Microsoft 雲端的唯一 Azure 存放區中，然後再下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="a94d5-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="a94d5-114">請確定您的組織可以連線到 Azure 中的端點，也就是\*\* \* blob.core.windows.net\*\* （萬用字元代表匯出的唯一識別碼）。</span><span class="sxs-lookup"><span data-stu-id="a94d5-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="a94d5-115">搜尋結果資料會在建立後的兩周從 Azure 存放區刪除。</span><span class="sxs-lookup"><span data-stu-id="a94d5-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="a94d5-116">您用來匯出搜尋結果的電腦必須符合下列系統需求：</span><span class="sxs-lookup"><span data-stu-id="a94d5-116">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="a94d5-117">32位或64位版本的 Windows 7 和更新版本</span><span class="sxs-lookup"><span data-stu-id="a94d5-117">32-bit or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="a94d5-118">Microsoft .NET Framework 4。7</span><span class="sxs-lookup"><span data-stu-id="a94d5-118">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="a94d5-119">您必須使用下列其中一種支援的瀏覽器執行 eDiscovery 匯出工具<sup>1</sup>：</span><span class="sxs-lookup"><span data-stu-id="a94d5-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="a94d5-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a94d5-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="a94d5-121">OR</span><span class="sxs-lookup"><span data-stu-id="a94d5-121">OR</span></span>

  - <span data-ttu-id="a94d5-122">Microsoft Internet Explorer 10 和更新版本</span><span class="sxs-lookup"><span data-stu-id="a94d5-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="a94d5-123"><sup>1</sup> Microsoft 不會製造協力廠商擴充模組或 ClickOnce 應用程式的附加元件。</span><span class="sxs-lookup"><span data-stu-id="a94d5-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="a94d5-124">使用不受支援的瀏覽器匯出搜尋結果時，不支援協力廠商分機或附加元件。</span><span class="sxs-lookup"><span data-stu-id="a94d5-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="a94d5-125"><sup>2</sup>由於 Microsoft Edge 的最近變更，因此預設不再啟用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="a94d5-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="a94d5-126">如需在 Edge 中啟用 ClickOnce 支援的相關指示，請參閱[使用 Microsoft Edge 中的 EDiscovery 匯出工具](configure-edge-to-export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="a94d5-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="a94d5-127">如果預估內容搜尋所傳回的結果總大小超過 2 TB，則匯出報表失敗。</span><span class="sxs-lookup"><span data-stu-id="a94d5-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="a94d5-128">若要順利匯出報告，請嘗試縮小範圍並重新執行搜尋，使結果的預估大小小於 2 TB。</span><span class="sxs-lookup"><span data-stu-id="a94d5-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="a94d5-129">匯出內容搜尋報告時，會依據同時執行的匯出數目上限及單一使用者可執行檔匯出數目上限而產生計數。</span><span class="sxs-lookup"><span data-stu-id="a94d5-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="a94d5-130">如需匯出限制的相關資訊，請參閱[匯出內容搜尋結果](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="a94d5-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="a94d5-131">產生及下載內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="a94d5-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="a94d5-132">產生及下載內容搜尋報告的步驟，與實際匯出搜尋結果類似。</span><span class="sxs-lookup"><span data-stu-id="a94d5-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="a94d5-133">步驟1：產生要匯出的報告</span><span class="sxs-lookup"><span data-stu-id="a94d5-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="a94d5-134">第一步是準備報表，以下載至電腦匯出。</span><span class="sxs-lookup"><span data-stu-id="a94d5-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="a94d5-135">當您報告時，報表檔會上傳至 Microsoft 雲端中的 Azure 存放區。</span><span class="sxs-lookup"><span data-stu-id="a94d5-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="a94d5-136">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="a94d5-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="a94d5-137">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a94d5-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="a94d5-138">在安全性 & 規範中心的左窗格中，按一下 [**搜尋** \> **內容搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="a94d5-139">在 [**內容搜尋**] 頁面上，選取搜尋。</span><span class="sxs-lookup"><span data-stu-id="a94d5-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="a94d5-140">在詳細資料窗格中，在 [**將報告匯出至電腦**] 底下，按一下 [**產生報告**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a94d5-141">如果搜尋的結果超過7天，系統會提示您更新搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="a94d5-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="a94d5-142">如果發生這種情況，請取消匯出，按一下 [詳細資料] 窗格中所選搜尋的 [**更新搜尋結果**]，然後在結果更新後再次啟動報告匯出。</span><span class="sxs-lookup"><span data-stu-id="a94d5-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="a94d5-143">在 [**匯出報告**] 頁面的 [**包含搜尋中的這些專案**] 底下，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a94d5-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="a94d5-144">只匯出已編制索引的專案</span><span class="sxs-lookup"><span data-stu-id="a94d5-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="a94d5-145">匯出已編制索引及未編制索引的專案</span><span class="sxs-lookup"><span data-stu-id="a94d5-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="a94d5-146">只匯出未編制索引的專案</span><span class="sxs-lookup"><span data-stu-id="a94d5-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="a94d5-147">如需未編制索引之專案的詳細資訊，請參閱[內容搜尋中已部分索引的專案](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="a94d5-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="a94d5-148">選擇包含所有 SharePoint 檔版本的搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="a94d5-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="a94d5-149">只有在搜尋的內容來源包含 SharePoint 或 OneDrive 商務網站時，才會顯示此選項。</span><span class="sxs-lookup"><span data-stu-id="a94d5-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="a94d5-150">按一下 [**產生報告**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="a94d5-151">搜尋結果報告已準備好下載，這表示會將報告檔上傳至 Microsoft 雲端中的 Azure 儲存體區域。</span><span class="sxs-lookup"><span data-stu-id="a94d5-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="a94d5-152">當報告可供下載時，[**下載報告**] 連結會顯示在 [詳細資料] 窗格中的 [**匯出報告至電腦**] 底下。</span><span class="sxs-lookup"><span data-stu-id="a94d5-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a94d5-153">您也可以匯出與 eDiscovery 案例相關聯之內容搜尋的報告。</span><span class="sxs-lookup"><span data-stu-id="a94d5-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="a94d5-154">若要執行此動作，請移至**ediscovery** \> **ediscovery**，選取案例，然後按一下 [**編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="a94d5-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="a94d5-155">在 [**搜尋**] 頁面上，選取搜尋，然後按一下 [**匯出** ![ 匯出搜尋結果圖示] [ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **匯出報告**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="a94d5-156">步驟2：下載報表</span><span class="sxs-lookup"><span data-stu-id="a94d5-156">Step 2: Download the report</span></span>

<span data-ttu-id="a94d5-157">下一步是將報告從 Azure 存放區下載到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="a94d5-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="a94d5-158">在您產生報告之搜尋的 [詳細資料] 窗格中，在 [**將報告匯出至電腦**] 底下，按一下 [**下載報告**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="a94d5-159">[**下載報告**] 頁面隨即顯示，並包含下列有關下載至電腦之報告的資訊。</span><span class="sxs-lookup"><span data-stu-id="a94d5-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="a94d5-160">將下載的專案數。</span><span class="sxs-lookup"><span data-stu-id="a94d5-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="a94d5-161">預估將要下載之專案的總大小。</span><span class="sxs-lookup"><span data-stu-id="a94d5-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="a94d5-162">是否要匯出索引或未編制索引的索引。</span><span class="sxs-lookup"><span data-stu-id="a94d5-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="a94d5-163">未編制索引的專案是指具有可識別格式的專案、已加密的專案，或因其他原因而未建立索引的專案。</span><span class="sxs-lookup"><span data-stu-id="a94d5-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="a94d5-164">SharePoint 檔的版本是否會下載。</span><span class="sxs-lookup"><span data-stu-id="a94d5-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="a94d5-165">報表匯出程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="a94d5-165">The status of the report export process.</span></span> <span data-ttu-id="a94d5-166">即使報表準備未完成，也可以開始下載報表。</span><span class="sxs-lookup"><span data-stu-id="a94d5-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="a94d5-167">在 [**匯出金鑰**] 底下，按一下 [**複製到剪貼**簿]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="a94d5-168">您可以在步驟5中使用此機碼下載報告。</span><span class="sxs-lookup"><span data-stu-id="a94d5-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a94d5-169">由於任何人都可以安裝並啟動 eDiscovery 匯出工具，然後使用此機碼來下載搜尋報告，請務必採取預防措施來保護此機碼，就像您保護密碼或其他安全性相關的資訊一樣。</span><span class="sxs-lookup"><span data-stu-id="a94d5-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="a94d5-170">按一下 [**下載報告**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="a94d5-171">如果系統提示您安裝**EDiscovery 匯出工具**，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="a94d5-172">在 [ **EDiscovery 匯出工具**] 中，在適當的方塊中貼上您在步驟2中複製的匯出金鑰。</span><span class="sxs-lookup"><span data-stu-id="a94d5-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="a94d5-173">按一下 **[流覽]** 以指定您要下載報表的位置。</span><span class="sxs-lookup"><span data-stu-id="a94d5-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="a94d5-174">按一下 [開始]\*\*\*\* 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="a94d5-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="a94d5-175">**EDiscovery 匯出工具**會顯示匯出程式的狀態資訊，包括要下載之其餘專案的數位（和大小）的預估。</span><span class="sxs-lookup"><span data-stu-id="a94d5-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="a94d5-176">匯出程式完成後，您可以在下載檔案的位置存取檔案。</span><span class="sxs-lookup"><span data-stu-id="a94d5-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a94d5-177">您可以下載與 eDiscovery 案例相關聯的內容搜尋報告。</span><span class="sxs-lookup"><span data-stu-id="a94d5-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="a94d5-178">若要執行此動作，請移至**ediscovery** \> **ediscovery**，選取案例，然後按一下 [**編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="a94d5-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="a94d5-179">在 [**匯出**] 頁面上，選取報告匯出，然後按一下 [詳細資料] 窗格中的 [**下載報告**]。</span><span class="sxs-lookup"><span data-stu-id="a94d5-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="a94d5-180">報告中包含的內容</span><span class="sxs-lookup"><span data-stu-id="a94d5-180">What's included in the report</span></span>

<span data-ttu-id="a94d5-181">當您產生及匯出內容搜尋結果的報告時，會下載下列檔：</span><span class="sxs-lookup"><span data-stu-id="a94d5-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="a94d5-182">**匯出摘要：** 包含匯出摘要的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="a94d5-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="a94d5-183">這包括下列資訊：搜尋的內容來源數目、每個內容位置的搜尋結果數目、預估的專案數、要匯出的實際專案數，以及所要匯出之專案的預估和實際大小。</span><span class="sxs-lookup"><span data-stu-id="a94d5-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a94d5-184">如果您在匯出報告時包含未編制索引的專案，未編制索引的專案數目會包含在已預計的搜尋結果總數和下載之搜尋結果的總數（如果您要匯出搜尋結果，則是在 [匯出摘要] 報告中列出）。</span><span class="sxs-lookup"><span data-stu-id="a94d5-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="a94d5-185">換句話說，將下載的專案總數等於估計的結果總數和未編制索引的專案總數。</span><span class="sxs-lookup"><span data-stu-id="a94d5-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="a94d5-186">**資訊清單：** 包含在搜尋結果中的每個專案相關資訊的資訊清單檔案（XML 格式）。</span><span class="sxs-lookup"><span data-stu-id="a94d5-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="a94d5-187">**結果：** 包含每一列的 Excel 檔，其中包含每個要連同搜尋結果一起匯出之索引項目目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a94d5-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="a94d5-188">針對電子郵件，結果記錄檔包含每封郵件的相關資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="a94d5-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="a94d5-189">來源信箱中郵件的位置（包括郵件是在主要或封存信箱中）。</span><span class="sxs-lookup"><span data-stu-id="a94d5-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="a94d5-190">傳送或接收郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="a94d5-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="a94d5-191">郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="a94d5-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="a94d5-192">郵件的寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="a94d5-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="a94d5-193">針對來自 SharePoint 和 OneDrive 商務網站的檔，結果記錄檔包含每個檔的相關資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="a94d5-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="a94d5-194">檔的 URL。</span><span class="sxs-lookup"><span data-stu-id="a94d5-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="a94d5-195">檔所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="a94d5-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="a94d5-196">上次修改檔的日期。</span><span class="sxs-lookup"><span data-stu-id="a94d5-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="a94d5-197">檔的名稱（位於結果記錄檔的 [主旨] 欄中）。</span><span class="sxs-lookup"><span data-stu-id="a94d5-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a94d5-198">**結果**報告中的列數應該等於搜尋結果的總數減去 [未**編制索引的專案**] 報告中所列的總專案數。</span><span class="sxs-lookup"><span data-stu-id="a94d5-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="a94d5-199">未**編制索引的專案：** Excel 檔，包含搜尋結果中所包含之任何未編制索引項目目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a94d5-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="a94d5-200">如果您在產生搜尋結果報告時未包含未編制索引的專案，則此報告仍會下載，但會是空的。</span><span class="sxs-lookup"><span data-stu-id="a94d5-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
