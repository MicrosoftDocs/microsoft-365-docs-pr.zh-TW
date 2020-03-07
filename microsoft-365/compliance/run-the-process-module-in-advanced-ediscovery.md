---
title: 在 Office 365 進階電子文件探索中執行處理序模組
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
description: '了解做準備案例的 Office 365 資料的檔案與 Office 365 進階電子文件探索分析的準則。  '
ms.openlocfilehash: eb608eeac33e0d5d06dce9d0c35cd86f4e0bc280
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557813"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="abe72-103">執行進階電子文件中的處理序模組 （傳統）</span><span class="sxs-lookup"><span data-stu-id="abe72-103">Run the Process module in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="abe72-104">Case 檔案載入至進階電子文件**準備**期間\>**程序**。</span><span class="sxs-lookup"><span data-stu-id="abe72-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="abe72-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="abe72-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="abe72-107">指導方針： 準備進階電子文件中的資料</span><span class="sxs-lookup"><span data-stu-id="abe72-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="abe72-108">**品質**： 清楚識別案例檔案母體相關的大小寫。</span><span class="sxs-lookup"><span data-stu-id="abe72-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="abe72-109">**載入**： 將檔案載入至進階電子文件存取的位置。</span><span class="sxs-lookup"><span data-stu-id="abe72-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="abe72-110">**檔案識別碼**： 進階電子文件中的唯一檔案識別碼。</span><span class="sxs-lookup"><span data-stu-id="abe72-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="abe72-111">如果沒有檔案識別碼匯入，進階電子文件會自動產生的識別碼。</span><span class="sxs-lookup"><span data-stu-id="abe72-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="abe72-112">如果您將對應的識別碼在後續的程序負載，並將對應比初始的程序負載中不同的路徑，進階電子文件將會取代路徑 （而非新增新的檔案項目）。</span><span class="sxs-lookup"><span data-stu-id="abe72-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="abe72-113">識別碼可用以匯出程序中的參照。</span><span class="sxs-lookup"><span data-stu-id="abe72-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="abe72-114">識別碼值不應該 」-1 」。</span><span class="sxs-lookup"><span data-stu-id="abe72-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="abe72-115">**MD5**： 此簽章用來區分 （兩個檔案均不予以考量完全重複除非他們擁有相同 MD5） 的檔案。</span><span class="sxs-lookup"><span data-stu-id="abe72-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="abe72-116">根據預設，進階電子文件會計算 MD5 的檔案。</span><span class="sxs-lookup"><span data-stu-id="abe72-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="abe72-117">文字檔案載入的檔案時，建議您載入，並將對應原始 MD5 值，而不是計算進階電子文件中。</span><span class="sxs-lookup"><span data-stu-id="abe72-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="abe72-118">**檔案類型和名稱**：</span><span class="sxs-lookup"><span data-stu-id="abe72-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="abe72-119">進階電子文件可以處理的各種格式的檔案，例如載入的原生檔案解壓縮到某標準格式， \*。TXT、 HTML 或。XML。</span><span class="sxs-lookup"><span data-stu-id="abe72-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="abe72-120">處理的文字檔案是比原生檔案。</span><span class="sxs-lookup"><span data-stu-id="abe72-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="abe72-121">擷取的文字檔案會儲存在案例的資料夾。</span><span class="sxs-lookup"><span data-stu-id="abe72-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="abe72-122">不會載入無法擷取，例如系統檔案或圖形影像的檔案。</span><span class="sxs-lookup"><span data-stu-id="abe72-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="abe72-123">這些檔案可能會延遲處理。</span><span class="sxs-lookup"><span data-stu-id="abe72-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="abe72-124">確認大幅名為檔案名稱和路徑正確。</span><span class="sxs-lookup"><span data-stu-id="abe72-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="abe72-125">**檔案路徑**： 進階電子文件可以載入檔案與路徑的長度最多 400 個字元。</span><span class="sxs-lookup"><span data-stu-id="abe72-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="abe72-126">**文字擷取**： 擷取文字從原生檔案，除了一般文字，當下列也解壓縮： 隱藏文字 （Excel 和.doc）、 隱藏資料行 (Excel)，追蹤修訂 (.doc) 演講者備忘 (.ppt)、 內嵌物件 （例如，在.ppt 中的 Excel 物件）。</span><span class="sxs-lookup"><span data-stu-id="abe72-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="abe72-127">這些可以在文字編輯器中檢視。</span><span class="sxs-lookup"><span data-stu-id="abe72-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="abe72-128">**略過文字**： 執行程序之後，再分析定義此選用功能。</span><span class="sxs-lookup"><span data-stu-id="abe72-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="abe72-129">忽略文字應該使用時請小心謹慎，因為其使用，可能會降低檔案分析的效能。</span><span class="sxs-lookup"><span data-stu-id="abe72-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="abe72-130">**多國語系文字**： 進階電子文件目前未處理的標記、 custodian 和問題的多國語言名稱。</span><span class="sxs-lookup"><span data-stu-id="abe72-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="abe72-131">**中繼資料**： 決定是否要儲存供日後參考，例如日期範圍、 檔案大小、 檔案類型的案例資料庫中 custodian，和主旨的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="abe72-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="abe72-132">檔案已經已載入，不會重新執行庫存或新增額外負荷重新處理之後，可以載入中繼資料。</span><span class="sxs-lookup"><span data-stu-id="abe72-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="abe72-133">如果檔案原本已載入的路徑，對應的路徑] 欄，稍後再匯入中繼資料時。</span><span class="sxs-lookup"><span data-stu-id="abe72-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="abe72-134">很可能參照到依識別碼的檔案，並將對應的不同的路徑。</span><span class="sxs-lookup"><span data-stu-id="abe72-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="abe72-135">檔案路徑變更時，這是很有用的案例。</span><span class="sxs-lookup"><span data-stu-id="abe72-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="abe72-136">如果檔案原本已載入的檔案識別碼，對應識別碼] 欄中，當載入中繼資料。</span><span class="sxs-lookup"><span data-stu-id="abe72-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="abe72-137">（而不是 ID) 的路徑來參照該檔案會導致檔案重新載入與不同的識別碼。</span><span class="sxs-lookup"><span data-stu-id="abe72-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="abe72-138">進階電子文件建立檔案的複本而，載入的中繼資料的現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="abe72-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="abe72-139">**系列**： 即無法再載入系列沒有其父系 （標頭的家庭）。</span><span class="sxs-lookup"><span data-stu-id="abe72-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="abe72-140">**檔案大小**： 在大小上的檔案載入至進階電子文件沒有限制。</span><span class="sxs-lookup"><span data-stu-id="abe72-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="abe72-141">進行分析 （分析、 相關性等），限制為 5,242,880 擷取文字的字元。</span><span class="sxs-lookup"><span data-stu-id="abe72-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="abe72-142">較大的檔案會略過 （例如，在 [相關性，檔案不會參與相關性訓練程序而不會收到相關性分數批次計算後）。</span><span class="sxs-lookup"><span data-stu-id="abe72-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="abe72-143">**檔案數量**： 可以在單一的案例中處理的檔案數目沒有建議的限制。</span><span class="sxs-lookup"><span data-stu-id="abe72-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="abe72-144">效能取決於您的系統資源。</span><span class="sxs-lookup"><span data-stu-id="abe72-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="abe72-145">篩選檔案</span><span class="sxs-lookup"><span data-stu-id="abe72-145">Filtering files</span></span>

<span data-ttu-id="abe72-146">使用者定義的標籤可以是一組檔案以排除處理程序或其他工作相關聯。</span><span class="sxs-lookup"><span data-stu-id="abe72-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="abe72-147">每個程序工作階段相關聯的批次識別碼。</span><span class="sxs-lookup"><span data-stu-id="abe72-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="abe72-148">雖然批次識別碼是看不到最高]，在 [相關性，如此可以使用搜尋公用程式，藉由將目前的批次的篩選器，標記所有適當的檔案有使用者定義的標籤。</span><span class="sxs-lookup"><span data-stu-id="abe72-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="abe72-149">請參閱</span><span class="sxs-lookup"><span data-stu-id="abe72-149">See also</span></span>

[<span data-ttu-id="abe72-150">進階電子文件 （傳統）</span><span class="sxs-lookup"><span data-stu-id="abe72-150">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="abe72-151">執行處理序模組及載入資料</span><span class="sxs-lookup"><span data-stu-id="abe72-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="abe72-152">檢視處理序模組結果</span><span class="sxs-lookup"><span data-stu-id="abe72-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

