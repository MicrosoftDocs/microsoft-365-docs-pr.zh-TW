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
description: 瞭解如何在簡報或外部評論的高級 eDiscovery 檢查集中，選取及匯出內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581014"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="f0428-103">從高級 eDiscovery 的審閱集中匯出檔</span><span class="sxs-lookup"><span data-stu-id="f0428-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="f0428-104">匯出功能可讓使用者在您從 Advanced eDiscovery 的審閱集中匯出檔時，自訂下載套件所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="f0428-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="f0428-105">若要從審閱集匯出檔：</span><span class="sxs-lookup"><span data-stu-id="f0428-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="f0428-106">在 Microsoft 365 規範中心，開啟 [高級 eDiscovery] 案例，選取 [ **複查集** ] 索引標籤，然後選取您要匯出的複查集。</span><span class="sxs-lookup"><span data-stu-id="f0428-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="f0428-107">在 [檢查] 集中，按一下 [**動作**  >  **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="f0428-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="f0428-108">匯出工具會顯示飛出的頁面，包含設定匯出的設定。</span><span class="sxs-lookup"><span data-stu-id="f0428-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="f0428-109">有些選項預設為選取狀態，但您可以變更這些選項。</span><span class="sxs-lookup"><span data-stu-id="f0428-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="f0428-110">請參閱下一節，以取得您可以設定的匯出選項的描述。</span><span class="sxs-lookup"><span data-stu-id="f0428-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![從審閱集匯出專案的設定選項](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="f0428-112">設定匯出後，按一下 [ **匯出** ] 以啟動匯出程式。</span><span class="sxs-lookup"><span data-stu-id="f0428-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="f0428-113">根據您在 [ **輸出選項** ] 區段中選取的選項，您可以透過直接下載或組織的 Azure 儲存體帳戶來存取匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="f0428-114">匯出工作會在案例週期內保留。</span><span class="sxs-lookup"><span data-stu-id="f0428-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="f0428-115">不過，您必須在匯出工作完成後的30天內，從匯出工作下載內容。</span><span class="sxs-lookup"><span data-stu-id="f0428-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="f0428-116">匯出選項</span><span class="sxs-lookup"><span data-stu-id="f0428-116">Export options</span></span>

<span data-ttu-id="f0428-117">使用下列選項來設定匯出。</span><span class="sxs-lookup"><span data-stu-id="f0428-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="f0428-118">**匯出名稱**：匯出工作的名稱。</span><span class="sxs-lookup"><span data-stu-id="f0428-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="f0428-119">**描述**：可讓您新增描述的自由文字欄位。</span><span class="sxs-lookup"><span data-stu-id="f0428-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="f0428-120">**匯出這些檔**</span><span class="sxs-lookup"><span data-stu-id="f0428-120">**Export these documents**</span></span>

  - <span data-ttu-id="f0428-121">**僅限選取的檔**：此選項只會匯出目前選取的檔。</span><span class="sxs-lookup"><span data-stu-id="f0428-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="f0428-122">**審閱集中的所有檔**：此選項會匯出審閱集中的所有檔。</span><span class="sxs-lookup"><span data-stu-id="f0428-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="f0428-123">**中繼資料**</span><span class="sxs-lookup"><span data-stu-id="f0428-123">**Metadata**</span></span>
  
  - <span data-ttu-id="f0428-124">**Load file**：此檔案包含每個檔案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="f0428-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="f0428-125">這個檔案通常可由協力廠商的 eDiscovery 工具來 ingested。</span><span class="sxs-lookup"><span data-stu-id="f0428-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="f0428-126">如需包含哪些欄位的詳細資訊，請參閱 [Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f0428-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="f0428-127">**標記**：選取此選項時，會將標記資訊包含在載入檔案中。</span><span class="sxs-lookup"><span data-stu-id="f0428-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="f0428-128">**內容**</span><span class="sxs-lookup"><span data-stu-id="f0428-128">**Content**</span></span>
  
  - <span data-ttu-id="f0428-129">**原生** 檔案：選取此核取方塊，以在審閱集中包含檔的原生檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="f0428-130">如果您選擇匯出原生檔案，您可以使用下列選項來瞭解如何匯出聊天交談。</span><span class="sxs-lookup"><span data-stu-id="f0428-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="f0428-131">**交談選項**</span><span class="sxs-lookup"><span data-stu-id="f0428-131">**Conversation options**</span></span>

    - <span data-ttu-id="f0428-132">**交談** 檔案：此選項會匯出重新構建的交談交談。</span><span class="sxs-lookup"><span data-stu-id="f0428-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="f0428-133">這種格式會顯示與使用者在原生應用程式中看到的外觀類似的對話。</span><span class="sxs-lookup"><span data-stu-id="f0428-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="f0428-134">**個別聊天訊息**：此選項會在原始交談檔案儲存在 Microsoft 365 中時，將其匯出。</span><span class="sxs-lookup"><span data-stu-id="f0428-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="f0428-135">**選項**</span><span class="sxs-lookup"><span data-stu-id="f0428-135">**Options**</span></span>

  - <span data-ttu-id="f0428-136">**文字檔**：-此選項包含匯出中的原生檔案的解壓縮文字版本。</span><span class="sxs-lookup"><span data-stu-id="f0428-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="f0428-137">**以轉換的 Pdf 取代 redacted natives**：如果在審核期間產生 redacted PDF 檔案，這些檔案可供匯出。</span><span class="sxs-lookup"><span data-stu-id="f0428-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="f0428-138">您可以選擇只匯出 redacted (的原生檔案，但不要選取此選項) 或選取此選項，即可匯出包含實際密文的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="f0428-139">**輸出選項**：匯出的內容可透過網頁瀏覽器直接下載，或是可以傳送至 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="f0428-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="f0428-140">前兩個選項可讓您直接下載。</span><span class="sxs-lookup"><span data-stu-id="f0428-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="f0428-141">**鬆散檔案與 pst (電子郵件會在可能) 時新增至 pst**：以類似使用者在原生應用程式中所看到之原始目錄結構的格式匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="f0428-142">如需詳細資訊，請參閱 [鬆散檔案及 PST 匯出結構](#loose-files-and-pst-export-structure) 一節。</span><span class="sxs-lookup"><span data-stu-id="f0428-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="f0428-143">**緊縮的目錄結構**：檔案會匯出並包含在下載檔案中。</span><span class="sxs-lookup"><span data-stu-id="f0428-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="f0428-144">已 **匯出至您的 Azure 儲存體帳戶的緊縮目錄結構**：檔案會匯出至您組織的 azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="f0428-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="f0428-145">針對此選項，您必須提供 Azure 儲存體帳戶中容器的 URL，才能將檔案匯出至。</span><span class="sxs-lookup"><span data-stu-id="f0428-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="f0428-146">您也必須為您的 Azure 儲存體帳戶提供共用存取簽名 (SAS) token。</span><span class="sxs-lookup"><span data-stu-id="f0428-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="f0428-147">如需詳細資訊，請參閱 [將檔匯出為審閱集合中的 Azure 儲存體帳戶](download-export-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="f0428-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="f0428-148">下列各節說明鬆散檔案和緊縮目錄結構選項的資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="f0428-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="f0428-149">鬆散檔與 PST 匯出結構</span><span class="sxs-lookup"><span data-stu-id="f0428-149">Loose files and PST export structure</span></span>

<span data-ttu-id="f0428-150">如果您選取此匯出選項，匯出的內容會以下列結構組織：</span><span class="sxs-lookup"><span data-stu-id="f0428-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="f0428-151">根資料夾：此資料夾命名為 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="f0428-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="f0428-152">Export_load_file.csv：元資料檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="f0428-153">Summary.csv：也包含匯出統計資料的摘要檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="f0428-154">Exchange：此資料夾包含所有來自 Exchange 的內容，以原生檔案格式。</span><span class="sxs-lookup"><span data-stu-id="f0428-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="f0428-155">如果您選取 [ **以轉換的 Pdf 取代 redacted Natives** ] 選項，則 Natives 檔案會取代為 redacted pdf。</span><span class="sxs-lookup"><span data-stu-id="f0428-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="f0428-156">SharePoint：此資料夾包含以原生檔案格式 SharePoint 的所有本機內容。</span><span class="sxs-lookup"><span data-stu-id="f0428-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="f0428-157">如果您選取 [ **以轉換的 Pdf 取代 redacted Natives** ] 選項，則 Natives 檔案會取代為 redacted pdf。</span><span class="sxs-lookup"><span data-stu-id="f0428-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="f0428-158">緊縮目錄結構</span><span class="sxs-lookup"><span data-stu-id="f0428-158">Condensed directory structure</span></span>

- <span data-ttu-id="f0428-159">根資料夾：此資料夾命名為 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="f0428-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="f0428-160">Export_load_file.csv：元資料檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="f0428-161">Summary.txt：也包含匯出統計資料的摘要檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="f0428-162">NativeFiles：此資料夾包含所有已匯出的原生檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="f0428-163">如果您匯出的是 redacted PDF 檔案，則不會放入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="f0428-164">相反地，它們會新增至分開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f0428-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="f0428-165">Error_files：此資料夾包含下列錯誤檔案（如果它們包含在匯出中）：</span><span class="sxs-lookup"><span data-stu-id="f0428-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="f0428-166">ExtractionError：包含未從父系檔案正確提取之任何可用檔案中繼資料的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="f0428-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="f0428-167">ProcessingError：此檔案包含含處理錯誤的檔案清單。</span><span class="sxs-lookup"><span data-stu-id="f0428-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="f0428-168">此內容屬於專案層級，也就是說，如果附件導致處理錯誤，則包含附件的電子郵件會包含在此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f0428-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="f0428-169">Extracted_text_files：此資料夾包含在處理時所產生的所有解壓縮文字檔。</span><span class="sxs-lookup"><span data-stu-id="f0428-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
