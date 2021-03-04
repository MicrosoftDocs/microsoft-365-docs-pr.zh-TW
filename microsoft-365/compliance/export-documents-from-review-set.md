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
description: 瞭解如何選取及匯出簡報或外部評論的審閱集合中的內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423644"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="6a12d-103">從高級 eDiscovery 的審閱集中匯出檔</span><span class="sxs-lookup"><span data-stu-id="6a12d-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="6a12d-104">匯出功能可讓使用者自訂下載套件所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="6a12d-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="6a12d-105">匯出工具提供具有下列設定的設定頁面：</span><span class="sxs-lookup"><span data-stu-id="6a12d-105">The Export tool provides a configuration page with the following settings:</span></span>

![從審閱集匯出專案的選項](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="6a12d-107">匯出選項</span><span class="sxs-lookup"><span data-stu-id="6a12d-107">Export options</span></span>

- <span data-ttu-id="6a12d-108">匯出名稱：匯出工作的名稱。</span><span class="sxs-lookup"><span data-stu-id="6a12d-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="6a12d-109">描述：可讓您新增描述的自由文字欄位。</span><span class="sxs-lookup"><span data-stu-id="6a12d-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="6a12d-110">匯出下列檔：</span><span class="sxs-lookup"><span data-stu-id="6a12d-110">Export these documents:</span></span>

  - <span data-ttu-id="6a12d-111">僅限選取的檔-只匯出目前選取的檔。</span><span class="sxs-lookup"><span data-stu-id="6a12d-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="6a12d-112">審閱集合中的所有檔-匯出審閱集中的所有檔</span><span class="sxs-lookup"><span data-stu-id="6a12d-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="6a12d-113">中繼資料</span><span class="sxs-lookup"><span data-stu-id="6a12d-113">Metadata</span></span>
  
  - <span data-ttu-id="6a12d-114">載入檔-此檔案包含每個檔案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="6a12d-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="6a12d-115">如需包含哪些欄位的詳細資訊，請參閱 [Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="6a12d-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="6a12d-116">這個檔案通常可由協力廠商的 eDiscovery 工具來 ingested。</span><span class="sxs-lookup"><span data-stu-id="6a12d-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="6a12d-117">標記-選取時，標籤資訊將會包含在載入檔中。</span><span class="sxs-lookup"><span data-stu-id="6a12d-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="6a12d-118">內容</span><span class="sxs-lookup"><span data-stu-id="6a12d-118">Content</span></span>
  
  - <span data-ttu-id="6a12d-119">原生檔案-選取此核取方塊以包含原生檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="6a12d-120">交談選項</span><span class="sxs-lookup"><span data-stu-id="6a12d-120">Conversation options</span></span>
    
    - <span data-ttu-id="6a12d-121">交談檔案-匯出會重新構建聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="6a12d-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="6a12d-122">這種格式會顯示與使用者在原生應用程式中看到的外觀類似的對話。</span><span class="sxs-lookup"><span data-stu-id="6a12d-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="6a12d-123">個別聊天訊息-當原始交談檔案儲存在 Microsoft 365 中時，將其匯出。</span><span class="sxs-lookup"><span data-stu-id="6a12d-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="6a12d-124">選項</span><span class="sxs-lookup"><span data-stu-id="6a12d-124">Options</span></span>

  - <span data-ttu-id="6a12d-125">文字檔-包括解壓縮的原生文字檔版本。</span><span class="sxs-lookup"><span data-stu-id="6a12d-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="6a12d-126">Replace redacted natives with 已轉換的 Pdf-如果審閱時產生 redacted PDF 檔案，這些檔案可供匯出。</span><span class="sxs-lookup"><span data-stu-id="6a12d-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="6a12d-127">您可以選擇只匯出 redacted (的原生檔案，但不要選取此選項) 或選取此選項，即可匯出包含實際密文的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="6a12d-128"> (匯出內容的輸出選項可透過網頁瀏覽器直接下載，或是可以傳送至 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="6a12d-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="6a12d-129">前兩個選項可讓您直接下載。 ) </span><span class="sxs-lookup"><span data-stu-id="6a12d-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="6a12d-130">鬆散檔案和 Pst (電子郵件會在可能的情況) 中，以類似使用者在原生應用程式中所看到之原始目錄結構的格式來匯出時，新增至 Pst。</span><span class="sxs-lookup"><span data-stu-id="6a12d-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="6a12d-131">如需詳細資訊，請參閱 [鬆散檔案及 PST 匯出結構](#loose-files-and-pst-export-structure) 一節。</span><span class="sxs-lookup"><span data-stu-id="6a12d-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="6a12d-132">緊縮的目錄結構-檔會匯出並包含在下載中。</span><span class="sxs-lookup"><span data-stu-id="6a12d-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="6a12d-133">匯出至您的 Azure 儲存體帳戶的壓縮目錄結構-檔案會匯出至您組織的 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="6a12d-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="6a12d-134">鬆散檔與 PST 匯出結構</span><span class="sxs-lookup"><span data-stu-id="6a12d-134">Loose files and PST export structure</span></span>

<span data-ttu-id="6a12d-135">如果您選取此匯出選項，匯出的內容會以下列結構組織：</span><span class="sxs-lookup"><span data-stu-id="6a12d-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="6a12d-136">根資料夾–此資料夾命名為 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="6a12d-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="6a12d-137">Export_load_file.csv 元資料檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="6a12d-138">Summary.csv-也包含匯出統計資料的摘要檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="6a12d-139">Exchange-此資料夾包含所有來自 Exchange 的內容，以原生檔案格式。</span><span class="sxs-lookup"><span data-stu-id="6a12d-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="6a12d-140">如果您選取 [ **以轉換的 Pdf 取代 redacted Natives** ] 選項，則 Natives 檔案會取代為 redacted pdf。</span><span class="sxs-lookup"><span data-stu-id="6a12d-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="6a12d-141">SharePoint = 此資料夾包含以原生檔案格式 SharePoint 的所有本機內容。</span><span class="sxs-lookup"><span data-stu-id="6a12d-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="6a12d-142">如果您選取 [ **以轉換的 Pdf 取代 redacted Natives** ] 選項，則 Natives 檔案會取代為 redacted pdf。</span><span class="sxs-lookup"><span data-stu-id="6a12d-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="6a12d-143">緊縮目錄結構</span><span class="sxs-lookup"><span data-stu-id="6a12d-143">Condensed directory structure</span></span>

- <span data-ttu-id="6a12d-144">根資料夾-此資料夾命名為 ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="6a12d-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="6a12d-145">Export_load_file.csv 元資料檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="6a12d-146">Summary.txt-也包含匯出統計資料的摘要檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="6a12d-147">Input_or_native_files-此資料夾包含所有已匯出的原生檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="6a12d-148">如果您匯出的是 redacted PDF 檔案，則不會放入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="6a12d-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="6a12d-149">相反地，它們會新增至分開的資料夾。</span><span class="sxs-lookup"><span data-stu-id="6a12d-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="6a12d-150">Error_files-此資料夾包含下列錯誤檔案（如果它們包含在匯出中）：</span><span class="sxs-lookup"><span data-stu-id="6a12d-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="6a12d-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="6a12d-151">ExtractionError.</span></span> <span data-ttu-id="6a12d-152">CSV 檔案，其中包含未從父系檔案正確提取之任何可用之檔案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="6a12d-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="6a12d-153">ProcessingError –此檔案包含含處理錯誤的檔案清單。</span><span class="sxs-lookup"><span data-stu-id="6a12d-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="6a12d-154">此內容屬於專案層級，也就是說，如果附件導致處理錯誤，則包含附件的電子郵件會包含在此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="6a12d-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="6a12d-155">Extracted_text_files-此資料夾包含在處理時所產生的所有解壓縮文字檔。</span><span class="sxs-lookup"><span data-stu-id="6a12d-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="6a12d-156">匯出工作會在案例週期內保留。</span><span class="sxs-lookup"><span data-stu-id="6a12d-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="6a12d-157">不過，您必須在匯出工作完成後的30天內，從匯出工作下載內容。</span><span class="sxs-lookup"><span data-stu-id="6a12d-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
