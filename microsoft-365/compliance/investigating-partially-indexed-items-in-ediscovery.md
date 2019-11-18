---
title: 調查 Office 365 電子文件探索中已局部編製索引的項目
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 已局部編製索引的項目 （也呼叫未建立索引的項目） 是 Exchange 信箱項目和文件在 SharePoint 和 OneDrive 網站，如某個原因而未完全編製索引的內容搜尋。 在本文中了解為何無法編製索引的搜尋項目，並已局部編製索引的項目所傳回、 識別搜尋錯誤的已局部編製索引的項目，並使用 PowerShell 指令碼來判斷您的組織暴露於已局部編製索引的電子郵件項目。
ms.openlocfilehash: 4e1430fe80c01b1cc9e67777c6955790ea1c6540
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685596"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="f264b-104">調查 Office 365 電子文件探索中已局部編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="f264b-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="f264b-105">當您執行搜尋時，自動從安全性 & 合規性中心執行內容搜尋會包含已局部編製索引的項目預估的搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="f264b-105">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="f264b-106">已局部編製索引的項目是 Exchange 信箱項目和文件 SharePoint 和 OneDrive for Business 網站完全沒有編入搜尋索引，因任何原因。</span><span class="sxs-lookup"><span data-stu-id="f264b-106">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="f264b-107">大部分的電子郵件和網站的文件會成功索引，因為它們會落在[電子郵件訊息的編製索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)內。</span><span class="sxs-lookup"><span data-stu-id="f264b-107">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="f264b-108">不過，某些項目可能會超過這些索引限制，而且會已局部編製索引。</span><span class="sxs-lookup"><span data-stu-id="f264b-108">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="f264b-109">以下是其他原因無法編製索引的搜尋項目，並已局部編製索引的項目時執行內容搜尋所傳回的原因：</span><span class="sxs-lookup"><span data-stu-id="f264b-109">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="f264b-110">電子郵件具有無法建立索引; 檔案類型的附加的檔案在大多數情況下，該檔案類型是[無法辨識或不支援索引編製功能](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="f264b-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="f264b-111">電子郵件有附加的檔案沒有有效的處理常式，圖像檔案; 例如這是最常見原因的已局部編製索引的電子郵件項目</span><span class="sxs-lookup"><span data-stu-id="f264b-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="f264b-112">太多檔案附加到電子郵件</span><span class="sxs-lookup"><span data-stu-id="f264b-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="f264b-113">附加到電子郵件的檔案是太大</span><span class="sxs-lookup"><span data-stu-id="f264b-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="f264b-114">檔案類型支援索引編製，但是特定檔案發生索引錯誤</span><span class="sxs-lookup"><span data-stu-id="f264b-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="f264b-115">雖然可能會有所不同，大部分的 Office 365 組織客戶的內容低於 1%磁碟區，擁有的內容低於 12%的已局部編製索引的大小。</span><span class="sxs-lookup"><span data-stu-id="f264b-115">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="f264b-116">與大小的磁碟區之間的差異的原因是較大的檔案有較高的機率的含有不能完全索引的內容。</span><span class="sxs-lookup"><span data-stu-id="f264b-116">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="f264b-117">已局部編製索引的項目計數為何變更搜尋？</span><span class="sxs-lookup"><span data-stu-id="f264b-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="f264b-118">安全 & 與規範中心執行內容搜尋之後，總數和大小所搜尋的位置中的已局部編製索引項目列出中會顯示在搜尋的詳細統計資料中的搜尋結果統計資料。</span><span class="sxs-lookup"><span data-stu-id="f264b-118">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="f264b-119">請注意這些稱為搜尋統計資料中*未編製索引的項目*。</span><span class="sxs-lookup"><span data-stu-id="f264b-119">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="f264b-120">以下是會影響搜尋結果中傳回的已局部編製索引項目數目的一些事項：</span><span class="sxs-lookup"><span data-stu-id="f264b-120">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="f264b-121">如果項目已局部編製索引，且符合搜尋查詢，它會包含在計數 （和大小） 的搜尋結果項目和已局部編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="f264b-121">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="f264b-122">不過，當匯出該相同結果，項目是搜尋的只包含在搜尋結果; 集它具有不包括為已局部編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="f264b-122">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="f264b-123">如果您指定日期範圍的搜尋查詢 （包括它的關鍵字查詢中） 或使用條件，不會比對的日期範圍的任何已局部編製索引項目不包含已局部編製索引的項目計數。</span><span class="sxs-lookup"><span data-stu-id="f264b-123">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="f264b-124">只有已局部編製索引項目的日期範圍內的隨附中已局部編製索引的項目計數。</span><span class="sxs-lookup"><span data-stu-id="f264b-124">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="f264b-125">**附註：** 已局部編製索引項目位於 SharePoint 和 OneDrive 網站*不*包含在搜尋的詳細統計資料中顯示的已局部編製索引的項目估計值。</span><span class="sxs-lookup"><span data-stu-id="f264b-125">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="f264b-126">不過，當您匯出內容搜尋結果時，可以匯出已局部編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="f264b-126">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="f264b-127">例如，如果您只搜尋網站在內容搜尋的估計數量中已局部編製索引的項目將會是零。</span><span class="sxs-lookup"><span data-stu-id="f264b-127">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="f264b-128">計算已局部編製索引的項目在您的組織中的比率</span><span class="sxs-lookup"><span data-stu-id="f264b-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="f264b-129">若要了解您的組織暴露於已局部編製索引的項目，您可以執行所有內容搜尋所有信箱中 （藉由使用空白的關鍵字查詢）。</span><span class="sxs-lookup"><span data-stu-id="f264b-129">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="f264b-130">在下面的下列範例中，有 56,208 (4,830 MB) 完全編製索引項目和 470 (316 MB) 已局部編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="f264b-130">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![範例搜尋統計資料顯示的已局部編製索引的項目](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="f264b-132">您可以使用下列計算判斷百分比的已局部編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="f264b-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="f264b-133">**若要計算的比例的組織中的已局部編製索引項目：**</span><span class="sxs-lookup"><span data-stu-id="f264b-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="f264b-134">藉由使用上述範例中，從搜尋結果。 84%的所有信箱項目已局部編製索引。</span><span class="sxs-lookup"><span data-stu-id="f264b-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="f264b-135">**若要計算您組織中已局部編製索引項目的大小的百分比：**</span><span class="sxs-lookup"><span data-stu-id="f264b-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="f264b-136">因此在前一個範例中，6.54] %的信箱項目的總大小會從已局部編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="f264b-136">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="f264b-137">如先前所述，大多數的 Office 365 組織的客戶的內容低於 1%磁碟區，擁有的內容低於 12%的已局部編製索引的大小。</span><span class="sxs-lookup"><span data-stu-id="f264b-137">As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="f264b-138">使用已局部編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="f264b-138">Working with partially indexed items</span></span>

<span data-ttu-id="f264b-139">在情況下當您要檢查部分項目來驗證它們不包含的相關資訊，您可以[匯出內容搜尋報告](export-a-content-search-report.md)包含已局部編製索引項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f264b-139">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="f264b-140">當您匯出內容搜尋報告時，請務必選擇其中一個包含已局部編製索引的項目匯出選項。</span><span class="sxs-lookup"><span data-stu-id="f264b-140">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![選擇 [匯出已局部編製索引的項目第二個或第三個選項](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="f264b-142">當您匯出內容搜尋結果] 或 [內容搜尋報告使用其中一個選項時，匯出包含名為未編製索引的 Items.csv 報表。</span><span class="sxs-lookup"><span data-stu-id="f264b-142">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="f264b-143">此報告中包含大部分的 ResultsLog.csv 檔案; 相同的資訊不過，未編製索引的 Items.csv 檔案也包含兩個欄位相關的已局部編製索引的項目：**錯誤標記**與**Error 屬性**。</span><span class="sxs-lookup"><span data-stu-id="f264b-143">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="f264b-144">這些欄位包含每個已局部編製索引項目的索引錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f264b-144">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="f264b-145">使用這兩個欄位中的資訊可協助您判斷針對特定的索引時發生錯誤會影響您調查。</span><span class="sxs-lookup"><span data-stu-id="f264b-145">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="f264b-146">如果是的話，您可以執行已設定目標內容搜尋和擷取及匯出特定的電子郵件與 SharePoint 或 OneDrive 文件，以便您可以檢查它們，以判斷如果它們相關您調查。</span><span class="sxs-lookup"><span data-stu-id="f264b-146">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="f264b-147">如需逐步指示，請參閱[準備 Office 365 中已設定目標內容搜尋的 CSV 檔案](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="f264b-147">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="f264b-148">**附註：** 未編製索引的 Items.csv 檔案也會包含名為**錯誤類型**和**錯誤訊息**的欄位。</span><span class="sxs-lookup"><span data-stu-id="f264b-148">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="f264b-149">這些是舊版欄位中內含的**錯誤標記**和**Error 屬性**欄位中，但具有較少的詳細資訊的資訊類似的資訊。</span><span class="sxs-lookup"><span data-stu-id="f264b-149">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="f264b-150">您可以放心地忽略這些舊版的欄位。</span><span class="sxs-lookup"><span data-stu-id="f264b-150">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="f264b-151">與已局部編製索引的項目相關的錯誤</span><span class="sxs-lookup"><span data-stu-id="f264b-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="f264b-152">錯誤標記所組成的資訊、 錯誤和檔案類型的兩個部分。</span><span class="sxs-lookup"><span data-stu-id="f264b-152">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="f264b-153">例如，在此錯誤/filetype 配對：</span><span class="sxs-lookup"><span data-stu-id="f264b-153">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

   
 <span data-ttu-id="f264b-154">`parseroutputsize`錯誤和`xls`是在發生錯誤的檔案的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f264b-154">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="f264b-155">在情況下所無法辨識該檔案類型或檔案類型不帶不會套用到錯誤，您會看到值`noformat`取代之檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f264b-155">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="f264b-156">以下是錯誤和錯誤的可能原因的描述編製索引的清單。</span><span class="sxs-lookup"><span data-stu-id="f264b-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="f264b-157">**錯誤標記**</span><span class="sxs-lookup"><span data-stu-id="f264b-157">**Error tag**</span></span>|<span data-ttu-id="f264b-158">**描述**</span><span class="sxs-lookup"><span data-stu-id="f264b-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="f264b-159">電子郵件有太多的附件，以及這些附件的一些未處理。</span><span class="sxs-lookup"><span data-stu-id="f264b-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="f264b-160">內容的擷取器和文件剖析器找不到太多層級的巢狀方式置於其他附件的附件。</span><span class="sxs-lookup"><span data-stu-id="f264b-160">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="f264b-161">這些附件的一些不處理。</span><span class="sxs-lookup"><span data-stu-id="f264b-161">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="f264b-162">附件失敗解碼所以 RMS 保護。</span><span class="sxs-lookup"><span data-stu-id="f264b-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="f264b-163">附加到電子郵件的檔案太大，且無法處理。</span><span class="sxs-lookup"><span data-stu-id="f264b-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="f264b-164">當索引寫入已處理的電子郵件訊息，其中一個索引的屬性太大，而且已被截斷。</span><span class="sxs-lookup"><span data-stu-id="f264b-164">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="f264b-165">截斷的屬性會列在 Error 屬性] 欄位。</span><span class="sxs-lookup"><span data-stu-id="f264b-165">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="f264b-166">電子郵件訊息包含無法處理為有效的 Unicode 的文字。</span><span class="sxs-lookup"><span data-stu-id="f264b-166">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="f264b-167">此項目編製索引可能不完整。</span><span class="sxs-lookup"><span data-stu-id="f264b-167">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="f264b-168">加密附件或電子郵件訊息的內容，以及 Office 365 無法解碼內容。</span><span class="sxs-lookup"><span data-stu-id="f264b-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="f264b-169">分析處理時發生未知的錯誤。</span><span class="sxs-lookup"><span data-stu-id="f264b-169">An unknown error occurred during parsing.</span></span> <span data-ttu-id="f264b-170">這通常會造成從軟體錯誤或服務當機。</span><span class="sxs-lookup"><span data-stu-id="f264b-170">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="f264b-171">附件是太大，剖析器處理，且該附件的剖析未發生的事件或未完成。</span><span class="sxs-lookup"><span data-stu-id="f264b-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="f264b-172">附件格式不正確，且無法剖析器處理。</span><span class="sxs-lookup"><span data-stu-id="f264b-172">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="f264b-173">這項結果從可以舊檔案格式，藉由不相容的軟體或有病毒假冒某個項目比其他宣告所建立的檔案。</span><span class="sxs-lookup"><span data-stu-id="f264b-173">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="f264b-174">附件的剖析的輸出是太大，且必須截斷。</span><span class="sxs-lookup"><span data-stu-id="f264b-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="f264b-175">附件具有 Office 365 無法偵測到的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f264b-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="f264b-176">附件具有 Office 365could 偵測，但剖析該檔案類型不支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f264b-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="f264b-177">電子郵件屬性的值在 Exchange 儲存區已太大而無法擷取，並將無法處理的訊息。</span><span class="sxs-lookup"><span data-stu-id="f264b-177">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="f264b-178">這通常只是電子郵件訊息的本文屬性。</span><span class="sxs-lookup"><span data-stu-id="f264b-178">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="f264b-179">內容的擷取器無法解碼受 RMS 保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="f264b-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="f264b-180">太多文字已編製索引期間識別文件中。</span><span class="sxs-lookup"><span data-stu-id="f264b-180">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="f264b-181">當達到此限制時，停止處理屬性的屬性就會被截斷。</span><span class="sxs-lookup"><span data-stu-id="f264b-181">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="f264b-182">錯誤欄位描述哪些欄位受到錯誤標記] 欄位中列出的處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="f264b-182">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="f264b-183">如果您搜尋屬性，例如：`subject`或`participants`，錯誤訊息的內文中不會影響您的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f264b-183">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="f264b-184">決定完全哪些您可能需要進一步調查的已局部編製索引項目時，這可以是很有用。</span><span class="sxs-lookup"><span data-stu-id="f264b-184">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="f264b-185">使用 PowerShell 指令碼來判斷您的組織暴露於已局部編製索引的電子郵件項目</span><span class="sxs-lookup"><span data-stu-id="f264b-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="f264b-186">下列步驟顯示如何執行 PowerShell 指令碼，搜尋所有項目中所有 Exchange 信箱，然後產生報告相關的已局部編製索引的電子郵件項目貴組織的比率，（依計數，以及由大小） 並顯示的項目數 （和其檔案類型） 的每個索引所發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="f264b-186">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="f264b-187">使用在前一節中的錯誤標記描述，來識別索引時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="f264b-187">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="f264b-188">使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `PartiallyIndexedItems.ps1`。</span><span class="sxs-lookup"><span data-stu-id="f264b-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```

2. <span data-ttu-id="f264b-189">[連接到安全性 & 合規性中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="f264b-189">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="f264b-190">在安全性 & 合規性中心 PowerShell，移至您在步驟 1，儲存指令碼的所在資料夾，然後執行指令碼。例如：</span><span class="sxs-lookup"><span data-stu-id="f264b-190">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="f264b-191">以下是範例的指令碼所傳回的輸出。</span><span class="sxs-lookup"><span data-stu-id="f264b-191">Here's an example fo the output returned by the script.</span></span>
  
![輸出會產生報告，以在您的組織暴露於已局部編製索引的電子郵件項目上的指令碼範例](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="f264b-193">注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="f264b-193">Note the following:</span></span>
  
1. <span data-ttu-id="f264b-194">總數和大小的電子郵件項目，貴組織的比率的已局部編製索引的電子郵件項目 （依計數，以及由大小）</span><span class="sxs-lookup"><span data-stu-id="f264b-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="f264b-195">清單錯誤標記與之對應的檔案類型，發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="f264b-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f264b-196">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f264b-196">See also</span></span>

[<span data-ttu-id="f264b-197">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="f264b-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
