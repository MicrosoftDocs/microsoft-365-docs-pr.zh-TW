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
description: 瞭解如何選取及匯出或下載簡報或外部評論的審閱集合中的內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 29c2224a1ce0a92bca3b2057352f6f82fdc7afde
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034091"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="a19ec-103">從檢閱集匯出文件</span><span class="sxs-lookup"><span data-stu-id="a19ec-103">Export documents from a review set</span></span>

<span data-ttu-id="a19ec-104">您可以透過下列其中一種方法，從審閱集中匯出簡報或外部審閱內容：</span><span class="sxs-lookup"><span data-stu-id="a19ec-104">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="a19ec-105">下載檔案</span><span class="sxs-lookup"><span data-stu-id="a19ec-105">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="a19ec-106">匯出檔</span><span class="sxs-lookup"><span data-stu-id="a19ec-106">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="a19ec-107">從審閱集下載檔案</span><span class="sxs-lookup"><span data-stu-id="a19ec-107">Download documents from a review set</span></span>

<span data-ttu-id="a19ec-108">下載提供一種簡單的方式，可從原生格式的審閱集下載內容。</span><span class="sxs-lookup"><span data-stu-id="a19ec-108">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="a19ec-109">它會利用瀏覽器的資料傳輸功能，讓下載做好準備時出現瀏覽器提示。</span><span class="sxs-lookup"><span data-stu-id="a19ec-109">It leverages the browser's data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="a19ec-110">使用此方法下載的檔案會壓縮成容器檔案，並將成為專案層級檔案。</span><span class="sxs-lookup"><span data-stu-id="a19ec-110">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="a19ec-111">這表示如果您選取附件，將會自動收到包含附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a19ec-111">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="a19ec-112">同樣地，如果您選取嵌入在 word 檔中的 excel 試算表，您會收到 word 檔，並嵌入 excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="a19ec-112">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="a19ec-113">已下載的專案會保留最後一個修改的日期，該日期可以看作是檔案屬性。</span><span class="sxs-lookup"><span data-stu-id="a19ec-113">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="a19ec-114">若要從審閱集下載內容，請先選取您想要下載的檔案，然後選取 [動作] 功能表中的 [下載]。</span><span class="sxs-lookup"><span data-stu-id="a19ec-114">To download content from a review set, start by selecting the files you want to download then select "Download" under the Actions menu.</span></span>

![自動產生電腦描述的螢幕擷取畫面](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="a19ec-116">從檢閱集匯出文件</span><span class="sxs-lookup"><span data-stu-id="a19ec-116">Export documents from a review set</span></span>

<span data-ttu-id="a19ec-117">匯出功能可讓使用者自訂下載套件所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="a19ec-117">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="a19ec-118">它會提供具有下列設定的設定頁面：</span><span class="sxs-lookup"><span data-stu-id="a19ec-118">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="a19ec-119">元資料檔案</span><span class="sxs-lookup"><span data-stu-id="a19ec-119">Metadata file</span></span>

<span data-ttu-id="a19ec-120">這可以視為您的「載入檔案」，該檔案包含與匯出之檔案相關聯的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="a19ec-120">This can be considered your "load file" that contains metadata associated with the files you export.</span></span> <span data-ttu-id="a19ec-121">如需元資料檔案中可用的匯出欄位清單，請參閱[Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="a19ec-121">For a list of exported fields available in the metadata file, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="a19ec-122">這個檔案通常可由協力廠商工具來 ingested。</span><span class="sxs-lookup"><span data-stu-id="a19ec-122">This file can typically be ingested by third-party tools.</span></span>

### <a name="tag-data"></a><span data-ttu-id="a19ec-123">標記資料</span><span class="sxs-lookup"><span data-stu-id="a19ec-123">Tag data</span></span>

<span data-ttu-id="a19ec-124">此內容會新增為元資料檔案中的欄位。</span><span class="sxs-lookup"><span data-stu-id="a19ec-124">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="a19ec-125">包含所有套用至審查集的標記資訊。</span><span class="sxs-lookup"><span data-stu-id="a19ec-125">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="a19ec-126">文字檔</span><span class="sxs-lookup"><span data-stu-id="a19ec-126">Text files</span></span>

<span data-ttu-id="a19ec-127">可為從審閱集匯出的每個檔案產生文字檔。</span><span class="sxs-lookup"><span data-stu-id="a19ec-127">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="a19ec-128">這些檔案通常是服務合作夥伴在 ingesting 資料到協力廠商工具的一部分時所需的時間。</span><span class="sxs-lookup"><span data-stu-id="a19ec-128">Often times these files are required by service partners as part of ingesting data into third-party tools.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="a19ec-129">Redacted 檔案</span><span class="sxs-lookup"><span data-stu-id="a19ec-129">Redacted files</span></span>

<span data-ttu-id="a19ec-130">如果審閱時產生 redacted PDF 檔案，則在匯出期間可使用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a19ec-130">If redacted PDF files are generated during review, these files are available during export.</span></span> <span data-ttu-id="a19ec-131">您可以決定是否只匯出原生檔案，或將需要密文的原生檔案取代成包含實際密文的 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="a19ec-131">You can decide whether to export native files only or to replace the native files that required redaction with the PDF files that contain the actual redactions.</span></span>

### <a name="export-location"></a><span data-ttu-id="a19ec-132">匯出位置</span><span class="sxs-lookup"><span data-stu-id="a19ec-132">Export location</span></span>

<span data-ttu-id="a19ec-133">匯出的內容會傳送至 Microsoft 提供的 Azure blob 或客戶的 blob，如果在匯出時提供詳細資料，即可使用。</span><span class="sxs-lookup"><span data-stu-id="a19ec-133">Exported content is delivered to either a Microsoft provided Azure blob or a customer's blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="a19ec-134">匯出結構</span><span class="sxs-lookup"><span data-stu-id="a19ec-134">Export structure</span></span>

<span data-ttu-id="a19ec-135">從審閱集匯出內容時，會以下列結構組織內容。</span><span class="sxs-lookup"><span data-stu-id="a19ec-135">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="a19ec-136">根資料夾–下載識別碼</span><span class="sxs-lookup"><span data-stu-id="a19ec-136">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="a19ec-137">Export\_load\_file .csv = metadata file</span><span class="sxs-lookup"><span data-stu-id="a19ec-137">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="a19ec-138">摘要 .txt = 具有匯出統計資料的摘要檔案</span><span class="sxs-lookup"><span data-stu-id="a19ec-138">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="a19ec-139">輸入\_或原\_生檔案 = 包含所有的原生檔案</span><span class="sxs-lookup"><span data-stu-id="a19ec-139">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="a19ec-140">錯誤\_檔案 = 包含匯出中包含的任何錯誤檔案</span><span class="sxs-lookup"><span data-stu-id="a19ec-140">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="a19ec-141">ExtractionError –包含未從父系檔案正確提取之任何可用檔案中繼資料的 csv</span><span class="sxs-lookup"><span data-stu-id="a19ec-141">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="a19ec-142">ProcessingError –具有處理錯誤的內容。</span><span class="sxs-lookup"><span data-stu-id="a19ec-142">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="a19ec-143">此內容是專案層級的意義。如果附件發生處理錯誤，包含附件的電子郵件將會包含在此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a19ec-143">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="a19ec-144">解壓縮\_的\_文字檔 = 包含處理時所產生的所有解壓縮文字檔。</span><span class="sxs-lookup"><span data-stu-id="a19ec-144">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>
