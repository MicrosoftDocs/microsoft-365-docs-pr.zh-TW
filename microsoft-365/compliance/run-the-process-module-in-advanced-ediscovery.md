---
title: 在高級電子檔探索中執行進程模組
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 瞭解使用高級電子檔探索來準備資料大小的案例檔案的指導方針。
ms.openlocfilehash: 5130bea7da8922fd7e98d07696ffde3930d2ce41
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936196"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="f31ce-103">在 [Advanced eDiscovery （古典）] 中執行進程模組</span><span class="sxs-lookup"><span data-stu-id="f31ce-103">Run the Process module in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="f31ce-104">在**準備**過程中，案例檔案會載入至高級 eDiscovery \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="f31ce-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f31ce-105">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="f31ce-105">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="f31ce-106">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f31ce-106">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="f31ce-107">指導方針：準備用於高級電子檔探索的資料</span><span class="sxs-lookup"><span data-stu-id="f31ce-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="f31ce-108">**Quality**：明確識別案例的相關案例檔。</span><span class="sxs-lookup"><span data-stu-id="f31ce-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="f31ce-109">**載入**：將檔案載入至可供高級 eDiscovery 存取的位置。</span><span class="sxs-lookup"><span data-stu-id="f31ce-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="f31ce-110">檔案**識別碼：「** 高級 eDiscovery」中的唯一檔識別碼。</span><span class="sxs-lookup"><span data-stu-id="f31ce-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="f31ce-111">如果沒有匯入的檔案識別碼，高級 eDiscovery 便會自動產生識別碼。</span><span class="sxs-lookup"><span data-stu-id="f31ce-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="f31ce-112">如果您在後續的處理常式載入中對應識別碼，並且對應的路徑與初始程式負載中的不同，則 Advanced eDiscovery 將取代路徑（而不是新增新的檔案專案）。</span><span class="sxs-lookup"><span data-stu-id="f31ce-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="f31ce-113">在匯出程式中，可以使用識別碼做為參考。</span><span class="sxs-lookup"><span data-stu-id="f31ce-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="f31ce-114">識別碼值不應該是 "-1"。</span><span class="sxs-lookup"><span data-stu-id="f31ce-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="f31ce-115">**MD5**：此簽章是用來區分檔案（兩個檔案不會被視為完全重複，除非有相同的 MD5）。</span><span class="sxs-lookup"><span data-stu-id="f31ce-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="f31ce-116">根據預設，「高級 eDiscovery」會計算檔的 MD5。</span><span class="sxs-lookup"><span data-stu-id="f31ce-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="f31ce-117">當載入的檔案為文字檔時，建議您在 [高級 eDiscovery] 中載入和對應原始的 MD5 值，而不是計算它。</span><span class="sxs-lookup"><span data-stu-id="f31ce-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="f31ce-118">**檔案類型和名稱**：</span><span class="sxs-lookup"><span data-stu-id="f31ce-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="f31ce-119">「高級 eDiscovery」可以處理各種格式的檔，並將載入的原生檔案解壓縮成標準格式，例如 \* 。TXT、HTML 或。Xml。</span><span class="sxs-lookup"><span data-stu-id="f31ce-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="f31ce-120">文字檔的處理速度比原生檔案更快。</span><span class="sxs-lookup"><span data-stu-id="f31ce-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="f31ce-121">解壓縮的文字檔會儲存在 case 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f31ce-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="f31ce-122">請勿載入無法解壓縮的檔案，例如系統檔案或圖形影像。</span><span class="sxs-lookup"><span data-stu-id="f31ce-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="f31ce-123">這些檔案可能會延遲處理。</span><span class="sxs-lookup"><span data-stu-id="f31ce-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="f31ce-124">請確認檔案名具有極大的名稱和路徑是否正確。</span><span class="sxs-lookup"><span data-stu-id="f31ce-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="f31ce-125">檔案**路徑**：「高級 eDiscovery」可以載入路徑長度最長為400個字元的檔案。</span><span class="sxs-lookup"><span data-stu-id="f31ce-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="f31ce-126">**文字提取**：從原生檔案提取文字時，除了一般文字之外，還會提取下列專案：隱藏的文字（excel 及 .doc）、隱藏的欄（excel）、追蹤變更（.doc）、喇叭附注（.ppt）、內嵌的物件（例如，.ppt 中的 Excel 物件）。</span><span class="sxs-lookup"><span data-stu-id="f31ce-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="f31ce-127">這些可以在文字編輯器中查看。</span><span class="sxs-lookup"><span data-stu-id="f31ce-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="f31ce-128">**Ignore Text**：此選用功能是在程式執行之後及分析之前定義。</span><span class="sxs-lookup"><span data-stu-id="f31ce-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="f31ce-129">忽略文字應謹慎使用，因為其使用可能會降低檔分析的效能。</span><span class="sxs-lookup"><span data-stu-id="f31ce-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="f31ce-130">**多語系文字**：「高級 eDiscovery」目前並未處理標記、保管人及問題的多語系名稱。</span><span class="sxs-lookup"><span data-stu-id="f31ce-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="f31ce-131">**中繼資料**：判斷是否要在案例資料庫中儲存以供日後參考的中繼資料，例如日期範圍、檔案大小、檔案類型、擁有者和主旨。</span><span class="sxs-lookup"><span data-stu-id="f31ce-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="f31ce-132">在不重新執行清查或重新處理重新處理的開銷的情況下，載入檔之後，即可載入中繼資料。</span><span class="sxs-lookup"><span data-stu-id="f31ce-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="f31ce-133">如果檔案最初是以 path 載入，請在以後匯入中繼資料時對應 [路徑] 欄位。</span><span class="sxs-lookup"><span data-stu-id="f31ce-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="f31ce-134">您可以依識別碼參照檔案，並對應不同的路徑。</span><span class="sxs-lookup"><span data-stu-id="f31ce-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="f31ce-135">當檔案路徑變更時，這是一個有用的案例。</span><span class="sxs-lookup"><span data-stu-id="f31ce-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="f31ce-136">如果檔案最初是以檔識別碼載入，請在載入中繼資料時對應 [識別碼] 欄。</span><span class="sxs-lookup"><span data-stu-id="f31ce-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="f31ce-137">依路徑參照檔案（而不是識別碼）將會以不同的識別碼重新載入檔案。</span><span class="sxs-lookup"><span data-stu-id="f31ce-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="f31ce-138">「高級 eDiscovery」會建立檔案的複本，而不是載入現有檔案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="f31ce-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="f31ce-139">**系列**：無法載入沒有其上級（族的頭部）的系列。</span><span class="sxs-lookup"><span data-stu-id="f31ce-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="f31ce-140">檔案**大小**：載入至 [Advanced eDiscovery] 的檔案大小不會有任何限制。</span><span class="sxs-lookup"><span data-stu-id="f31ce-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="f31ce-141">為了進行分析（分析、相關性等等），限制為解壓縮文字的5242880個字元。</span><span class="sxs-lookup"><span data-stu-id="f31ce-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="f31ce-142">會略過較大的檔案（例如，在相關性中，檔案不會參與相關性訓練程式，也不會在批次計算後接收相關性分數）。</span><span class="sxs-lookup"><span data-stu-id="f31ce-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="f31ce-143">檔案**數量**：在單一案例中，可以處理的檔案數目不建議使用限制。</span><span class="sxs-lookup"><span data-stu-id="f31ce-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="f31ce-144">效能取決於您系統的資源。</span><span class="sxs-lookup"><span data-stu-id="f31ce-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="f31ce-145">篩選檔案</span><span class="sxs-lookup"><span data-stu-id="f31ce-145">Filtering files</span></span>

<span data-ttu-id="f31ce-146">使用者定義的標籤可以與一組檔案相關聯，使其不會從處理常式或其他任務中排除。</span><span class="sxs-lookup"><span data-stu-id="f31ce-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="f31ce-147">每個處理常式會話都與批次識別碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="f31ce-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="f31ce-148">雖然相關聯的專家看不到 [批次識別碼]，但您可以使用搜尋公用程式，為目前的批次新增篩選，並使用使用者定義的標籤來標示所有適當的檔案，以完成此動作。</span><span class="sxs-lookup"><span data-stu-id="f31ce-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f31ce-149">請參閱</span><span class="sxs-lookup"><span data-stu-id="f31ce-149">See also</span></span>

[<span data-ttu-id="f31ce-150">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="f31ce-150">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f31ce-151">執行處理模組及載入資料</span><span class="sxs-lookup"><span data-stu-id="f31ce-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f31ce-152">查看進程模組結果</span><span class="sxs-lookup"><span data-stu-id="f31ce-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

