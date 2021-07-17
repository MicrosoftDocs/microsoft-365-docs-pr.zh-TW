---
title: 從檢閱集匯出文件
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何從簡報或外部評論的 Advanced eDiscovery 審閱集選取及匯出內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461396"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="d8d0a-103">從 Advanced eDiscovery 中的審閱集匯出檔</span><span class="sxs-lookup"><span data-stu-id="d8d0a-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="d8d0a-104">匯出功能可讓使用者在您從 Advanced eDiscovery 中的審閱集匯出檔時，自訂下載套件所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="d8d0a-105">若要從審閱集匯出檔：</span><span class="sxs-lookup"><span data-stu-id="d8d0a-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="d8d0a-106">在 Microsoft 365 合規性中心中，開啟 Advanced eDiscovery 案例，選取 [**複查集**] 索引標籤，然後選取您要匯出的複查集。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="d8d0a-107">在 [檢查] 集中，按一下 [**動作**  >  **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="d8d0a-108">匯出工具會顯示飛出的頁面，包含設定匯出的設定。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="d8d0a-109">有些選項預設為選取狀態，但您可以變更這些選項。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="d8d0a-110">請參閱下一節，以取得您可以設定的匯出選項的描述。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![從審閱集匯出專案的設定選項](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="d8d0a-112">設定匯出後，按一下 [ **匯出** ] 以啟動匯出程式。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="d8d0a-113">視您在 [**輸出選項**] 區段中選取的選項而定，您可以透過直接下載或組織的 Azure 儲存體帳戶來存取匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="d8d0a-114">匯出工作會在案例週期內保留。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="d8d0a-115">不過，您必須在匯出工作完成後的30天內，從匯出工作下載內容。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="d8d0a-116">匯出選項</span><span class="sxs-lookup"><span data-stu-id="d8d0a-116">Export options</span></span>

<span data-ttu-id="d8d0a-117">使用下列選項來設定匯出。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-117">Use the following options to configure the export.</span></span> <span data-ttu-id="d8d0a-118">並非所有選項都允許某些輸出選項，尤其是匯出至 PST 格式時不允許匯出文字檔和 redacted Pdf。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="d8d0a-119">**匯出名稱**：匯出工作的名稱。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="d8d0a-120">這將用來命名將下載的 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="d8d0a-121">**描述**：可讓您新增描述的自由文字欄位。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="d8d0a-122">**匯出這些檔**</span><span class="sxs-lookup"><span data-stu-id="d8d0a-122">**Export these documents**</span></span>

  - <span data-ttu-id="d8d0a-123">僅限選取的檔：此選項只會匯出目前選取的檔。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="d8d0a-124">只有在審閱集中選取專案時，才可使用此選項。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-124">This option is only available when items are selected in a review set.</span></span>
  
  - <span data-ttu-id="d8d0a-125">所有已篩選的檔：此選項會匯出使用中篩選器中的檔。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="d8d0a-126">只有在對複查集套用篩選時，才可使用此選項。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-126">This option is only available when a filter is applied to the review set.</span></span>
  
  - <span data-ttu-id="d8d0a-127">審閱集中的所有檔：此選項會匯出審閱集中的所有檔。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="d8d0a-128">**輸出選項**：匯出的內容可透過網頁瀏覽器直接下載，或是可以傳送至 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="d8d0a-129">前兩個選項可讓您直接下載。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="d8d0a-130">僅限報告：只會建立摘要和載入檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-130">Reports only: Only the summary and load file are created.</span></span>
  
  - <span data-ttu-id="d8d0a-131">鬆散檔案與 Pst (電子郵件會在可能) 時新增至 Pst：以類似使用者在原生應用程式中所看到之原始目錄結構的格式匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="d8d0a-132">如需詳細資訊，請參閱 [鬆散檔案及 PST 匯出結構](#loose-files-and-pst-export-structure) 一節。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="d8d0a-133">緊縮的目錄結構：檔案會匯出並包含在下載檔案中。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="d8d0a-134">匯出至 Azure 儲存體帳戶的緊縮目錄結構：檔案會匯出到您組織的 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="d8d0a-135">針對此選項，您必須提供 Azure 儲存體帳戶中容器的 URL，才能將檔案匯出至。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="d8d0a-136">您也必須為您的 Azure 儲存體帳戶提供共用存取簽名 (SAS) token。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="d8d0a-137">如需詳細資訊，請參閱[將檔匯出為審閱集中的 Azure 儲存體帳戶](download-export-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="d8d0a-138">**Include**</span><span class="sxs-lookup"><span data-stu-id="d8d0a-138">**Include**</span></span>
  
  - <span data-ttu-id="d8d0a-139">標記：選取此選項時，會將標記資訊包含在載入檔案中。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-139">Tags: When selected, tagging information is included in the load file.</span></span>
  
  - <span data-ttu-id="d8d0a-140">文字檔：此選項包含匯出中原生檔案的解壓縮文字版本。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="d8d0a-141">以轉換的 Pdf 取代 redacted natives：如果在審核期間產生 redacted PDF 檔案，這些檔案可供匯出。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="d8d0a-142">您可以選擇只匯出 redacted (的原生檔案，但不要選取此選項) 或選取此選項，即可匯出包含實際密文的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

<span data-ttu-id="d8d0a-143">下列各節說明鬆散檔案和緊縮目錄結構選項的資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-143">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span> <span data-ttu-id="d8d0a-144">匯出會分割成 ZIP 檔案，其大小上限為 75 GB 的解壓縮內容。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="d8d0a-145">如果匯出大小小於 75 GB，則匯出會包含摘要檔和單一 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="d8d0a-146">若匯出的壓縮資料大於 75 GB，將會建立多個 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-146">For exports larger than 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="d8d0a-147">下載後，可將 ZIP 檔案解壓縮到單一位置，以重新建立完整匯出。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="d8d0a-148">鬆散檔與 PST 匯出結構</span><span class="sxs-lookup"><span data-stu-id="d8d0a-148">Loose files and PST export structure</span></span>

<span data-ttu-id="d8d0a-149">如果您選取此匯出選項，匯出的內容會以下列結構組織：</span><span class="sxs-lookup"><span data-stu-id="d8d0a-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="d8d0a-150">Summary.csv：包括從審閱集匯出的內容摘要</span><span class="sxs-lookup"><span data-stu-id="d8d0a-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="d8d0a-151">根資料夾：此資料夾命名為 [匯出名稱] x 的 z.zip，將會針對每個 ZIP 檔分割區重複此資料夾。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="d8d0a-152">z.csv 的 Export_load_file_x：元資料檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="d8d0a-153">警告與錯誤 z.csv：此檔案包含嘗試從審閱集匯出時，發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  
  - <span data-ttu-id="d8d0a-154">Exchange：此資料夾包含 Exchange 儲存于 PST 檔案中的所有內容。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="d8d0a-155">Redacted PDF 檔案不能包含在此選項中。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="d8d0a-156">如果在審閱集中選取了附件，將會使用附加的附件匯出上層電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  
  - <span data-ttu-id="d8d0a-157">SharePoint：此資料夾包含以原生檔案格式 SharePoint 的所有本機內容。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="d8d0a-158">Redacted PDF 檔案不能包含在此選項中。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="d8d0a-159">緊縮目錄結構</span><span class="sxs-lookup"><span data-stu-id="d8d0a-159">Condensed directory structure</span></span>

- <span data-ttu-id="d8d0a-160">Summary.csv：包括從審閱集匯出的內容摘要</span><span class="sxs-lookup"><span data-stu-id="d8d0a-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="d8d0a-161">根資料夾：此資料夾命名為 [匯出名稱] x 的 z.zip，將會針對每個 ZIP 檔分割區重複此資料夾。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="d8d0a-162">z.csv 的 Export_load_file_x：元資料檔案，也包含儲存在 ZIP 檔案中的每個檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  
  - <span data-ttu-id="d8d0a-163">警告與錯誤 z.csv：此檔案包含嘗試從審閱集匯出時，發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>

  - <span data-ttu-id="d8d0a-164">NativeFiles：此資料夾包含所有已匯出的原生檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="d8d0a-165">如果您選取 [ *以轉換的 Pdf 取代 redacted Natives* ] 選項，則 Natives 檔案會取代為 redacted pdf。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  
  - <span data-ttu-id="d8d0a-166">Error_files：此資料夾包含提取或其他處理錯誤的檔案。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="d8d0a-167">檔案會放在不同的資料夾中，ExtractionError 或 ProcessingError。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="d8d0a-168">這些檔案會列于載入檔案中。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-168">These files are listed in the load file.</span></span>

  - <span data-ttu-id="d8d0a-169">Extracted_text_files：此資料夾包含在處理時所產生的所有解壓縮文字檔。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="d8d0a-170">匯出至 Azure 儲存體帳戶的緊縮目錄結構</span><span class="sxs-lookup"><span data-stu-id="d8d0a-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="d8d0a-171">此選項使用與 *緊縮目錄結構* 相同的一般結構，但是不會壓縮內容，而且會將資料儲存至您的 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="d8d0a-172">使用協力廠商 eDiscovery 提供者時，通常會使用此選項。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="d8d0a-173">如需如何使用此選項的詳細資訊，請參閱[將檔匯出為審閱集中的 Azure 儲存體帳戶](download-export-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="d8d0a-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
