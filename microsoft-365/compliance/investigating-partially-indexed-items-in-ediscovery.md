---
title: 調查 eDiscovery 中已部分索引的專案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何從組織內的 Exchange、SharePoint 和 OneDrive 管理部分索引（或未編制索引）專案。
ms.openlocfilehash: ed85a9351aad340c5840b6b9b9ea6e55833ed527
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817522"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="c4224-103">調查 eDiscovery 中已部分索引的專案</span><span class="sxs-lookup"><span data-stu-id="c4224-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="c4224-104">您從安全性 & 合規性中心執行的內容搜尋，會在您執行搜尋時，自動在預估搜尋結果中包含一部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="c4224-104">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="c4224-105">已部分編制索引的專案是 Exchange 信箱專案和檔，其上的 SharePoint 和 OneDrive 出於某些原因尚未完全編制搜尋索引的商務網站。</span><span class="sxs-lookup"><span data-stu-id="c4224-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="c4224-106">大部分電子郵件訊息和網站檔都已成功編制索引，因為它們在電子郵件的[索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)內。</span><span class="sxs-lookup"><span data-stu-id="c4224-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="c4224-107">不過，有些專案可能會超出這些索引限制，而且會進行部分編制索引。</span><span class="sxs-lookup"><span data-stu-id="c4224-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="c4224-108">以下是無法將專案編制索引以進行搜尋的其他原因，當您執行內容搜尋時，會傳回成部分索引項目目：</span><span class="sxs-lookup"><span data-stu-id="c4224-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="c4224-109">電子郵件的附件檔案類型無法建立索引;在大多數情況下，無法辨識檔案類型，[也不支援編制索引。](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="c4224-109">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="c4224-110">電子郵件的附加檔案沒有有效的處理常式，例如映射檔;這是部分索引電子郵件專案最常見的原因</span><span class="sxs-lookup"><span data-stu-id="c4224-110">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="c4224-111">附加到電子郵件的檔案太多</span><span class="sxs-lookup"><span data-stu-id="c4224-111">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="c4224-112">附加到電子郵件的檔案太大</span><span class="sxs-lookup"><span data-stu-id="c4224-112">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="c4224-113">檔案類型支援索引編制，但特定檔案發生索引錯誤</span><span class="sxs-lookup"><span data-stu-id="c4224-113">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="c4224-114">雖然這種方式不同，但大多陣列織客戶的內容少於磁片容量的1%，而不是以部分索引的大小小於12% 的內容。</span><span class="sxs-lookup"><span data-stu-id="c4224-114">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="c4224-115">磁片區與大小之間差異的原因是，較大的檔案包含無法完全編制索引之內容的可能性較高。</span><span class="sxs-lookup"><span data-stu-id="c4224-115">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="c4224-116">為何搜尋的部分索引項目目計數變更？</span><span class="sxs-lookup"><span data-stu-id="c4224-116">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="c4224-117">在安全性 & 規範中心執行內容搜尋之後，搜尋位置中已部分索引項目目的總數和大小會列在搜尋結果的搜尋結果統計資料中。</span><span class="sxs-lookup"><span data-stu-id="c4224-117">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="c4224-118">請注意，這些是在搜尋統計資料中稱為未*編制索引的專案*。</span><span class="sxs-lookup"><span data-stu-id="c4224-118">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="c4224-119">以下是會影響搜尋結果中傳回的部分索引項目目數目的一些事項：</span><span class="sxs-lookup"><span data-stu-id="c4224-119">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="c4224-120">如果專案已部分編制索引且符合搜尋查詢，則會包含在搜尋結果專案和部分索引項目目的計數（和大小）。</span><span class="sxs-lookup"><span data-stu-id="c4224-120">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="c4224-121">不過，當匯出相同搜尋的結果時，此專案會包含在一組搜尋結果中;它不會包含在部分索引項目目中。</span><span class="sxs-lookup"><span data-stu-id="c4224-121">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="c4224-122">如果您指定搜尋查詢的日期範圍（在關鍵字查詢中包含它或使用條件），則不符合日期範圍的任何部分索引項目目都不會包含在部分索引項目目計數中。</span><span class="sxs-lookup"><span data-stu-id="c4224-122">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="c4224-123">只有位於日期範圍內的部分索引項目目會包含在部分索引項目目的計數中。</span><span class="sxs-lookup"><span data-stu-id="c4224-123">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="c4224-124">**附注：** 位於 SharePoint 和 OneDrive 網站中的部分索引項目目*不會*包含在搜尋的詳細統計資料中顯示的部分索引項目目估計內。</span><span class="sxs-lookup"><span data-stu-id="c4224-124">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="c4224-125">不過，當您匯出內容搜尋的結果時，可以匯出部分索引的專案。</span><span class="sxs-lookup"><span data-stu-id="c4224-125">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="c4224-126">例如，如果您只搜尋內容搜尋中的網站，估計數目的部分索引項目目會是零。</span><span class="sxs-lookup"><span data-stu-id="c4224-126">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="c4224-127">計算組織中已部分索引的專案比率</span><span class="sxs-lookup"><span data-stu-id="c4224-127">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="c4224-128">若要瞭解您的組織對部分索引項目目的危險性，您可以針對所有信箱中的所有內容執行搜尋（使用空白關鍵字查詢）。</span><span class="sxs-lookup"><span data-stu-id="c4224-128">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="c4224-129">在下列範例中，有56208（4830 MB）已完全索引的專案和470（316 MB）部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="c4224-129">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![顯示部分索引項目目之搜尋統計資料的範例](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="c4224-131">您可以使用下列計算來判斷部分索引項目目的百分比。</span><span class="sxs-lookup"><span data-stu-id="c4224-131">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="c4224-132">**若要計算組織中已部分索引的專案比率：**</span><span class="sxs-lookup"><span data-stu-id="c4224-132">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="c4224-133">使用上述範例中的搜尋結果，就會以部分索引的方式列出所有信箱專案的84%。</span><span class="sxs-lookup"><span data-stu-id="c4224-133">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="c4224-134">**若要計算組織中部分索引項目目大小的百分比：**</span><span class="sxs-lookup"><span data-stu-id="c4224-134">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="c4224-135">在上一個範例中，信箱專案總大小的6.54% 是從部分索引的專案。</span><span class="sxs-lookup"><span data-stu-id="c4224-135">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="c4224-136">如先前所述，大多陣列織客戶的內容少於1% 的內容，而不是以部分索引的大小小於12% 的內容。</span><span class="sxs-lookup"><span data-stu-id="c4224-136">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="c4224-137">使用部分編制索引的專案</span><span class="sxs-lookup"><span data-stu-id="c4224-137">Working with partially indexed items</span></span>

<span data-ttu-id="c4224-138">在需要檢查部分專案以驗證它們不包含相關資訊的情況下，您可以匯出包含部分索引項目目相關資訊的[內容搜尋報告](export-a-content-search-report.md)。</span><span class="sxs-lookup"><span data-stu-id="c4224-138">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="c4224-139">當您匯出內容搜尋報告時，請務必選擇其中一個包含部分索引項目目的匯出選項。</span><span class="sxs-lookup"><span data-stu-id="c4224-139">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![選擇第二個或第三個選項，匯出已部分索引的專案](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="c4224-141">當您使用其中一個選項匯出內容搜尋結果或內容搜尋報告時，匯出會包含一個名為「未編制索引」 Items.csv 的報表。</span><span class="sxs-lookup"><span data-stu-id="c4224-141">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="c4224-142">這個報告包含的資訊大部分與 ResultsLog.csv 檔案相同;不過，未編制索引的 Items.csv 檔案中也包含與部分索引項目目相關的兩個欄位：**錯誤標記**和**錯誤屬性**。</span><span class="sxs-lookup"><span data-stu-id="c4224-142">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="c4224-143">這些欄位包含每個部分索引項目目之索引錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c4224-143">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="c4224-144">使用這兩個欄位中的資訊可協助您判斷是否有特定影響調查的索引錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4224-144">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="c4224-145">如果是的話，您可以執行目標內容搜尋，並取回和匯出特定的電子郵件訊息，並 SharePoint 或 OneDrive 檔，以便進行檢查，以判斷是否與您的調查相關。</span><span class="sxs-lookup"><span data-stu-id="c4224-145">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="c4224-146">如需逐步指示，請參閱[在 Office 365 中準備用來進行目標內容搜尋的 CSV](csv-file-for-an-id-list-content-search.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="c4224-146">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="c4224-147">**附注：** 未編制索引的 Items.csv 檔案也包含名為「**錯誤類型**」和「**錯誤訊息**」的欄位。</span><span class="sxs-lookup"><span data-stu-id="c4224-147">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="c4224-148">這些是舊版欄位，包含類似于 [**錯誤標記**] 和 [**錯誤屬性**] 欄位中的資訊，但詳細資訊更少的資訊。</span><span class="sxs-lookup"><span data-stu-id="c4224-148">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="c4224-149">您可以放心忽略這些舊版欄位。</span><span class="sxs-lookup"><span data-stu-id="c4224-149">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="c4224-150">與部分索引項目目相關的錯誤</span><span class="sxs-lookup"><span data-stu-id="c4224-150">Errors related to partially indexed items</span></span>

<span data-ttu-id="c4224-151">錯誤標記是由兩部分資訊組成，錯誤和檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c4224-151">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="c4224-152">例如，在此錯誤/類型的對中：</span><span class="sxs-lookup"><span data-stu-id="c4224-152">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

   
 <span data-ttu-id="c4224-153">`parseroutputsize`為錯誤， `xls` 是發生錯誤之檔案的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c4224-153">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="c4224-154">在此情況下，無法辨識檔案類型或檔案類型未套用至錯誤，您將會看到 [！注意事項] 此值 `noformat` 取代檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c4224-154">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="c4224-155">下列是索引錯誤的清單，以及錯誤可能原因的描述。</span><span class="sxs-lookup"><span data-stu-id="c4224-155">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="c4224-156">**錯誤標記**</span><span class="sxs-lookup"><span data-stu-id="c4224-156">**Error tag**</span></span>|<span data-ttu-id="c4224-157">**描述**</span><span class="sxs-lookup"><span data-stu-id="c4224-157">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="c4224-158">電子郵件中有太多附件，但未處理某些附件。</span><span class="sxs-lookup"><span data-stu-id="c4224-158">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="c4224-159">內容檢索程式和檔剖析器發現嵌套在其他附件中的附件太多層級。</span><span class="sxs-lookup"><span data-stu-id="c4224-159">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="c4224-160">部分附件未處理。</span><span class="sxs-lookup"><span data-stu-id="c4224-160">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="c4224-161">因為郵件是受 RMS 保護，所以附件的解碼失敗。</span><span class="sxs-lookup"><span data-stu-id="c4224-161">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="c4224-162">附加到電子郵件的檔案太大，無法處理。</span><span class="sxs-lookup"><span data-stu-id="c4224-162">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="c4224-163">當寫入已處理的電子郵件給索引時，其中一個可編制索引的屬性太大，已被截斷。</span><span class="sxs-lookup"><span data-stu-id="c4224-163">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="c4224-164">截斷的屬性會列在 [錯誤屬性] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="c4224-164">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="c4224-165">電子郵件包含無法當作有效的 Unicode 處理的文字。</span><span class="sxs-lookup"><span data-stu-id="c4224-165">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="c4224-166">此專案的索引可能不完整。</span><span class="sxs-lookup"><span data-stu-id="c4224-166">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="c4224-167">附件或電子郵件訊息的內容已加密，但 Microsoft 365 無法解碼內容。</span><span class="sxs-lookup"><span data-stu-id="c4224-167">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="c4224-168">剖析時發生未知的錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4224-168">An unknown error occurred during parsing.</span></span> <span data-ttu-id="c4224-169">這通常是軟體錯誤或服務損毀的結果。</span><span class="sxs-lookup"><span data-stu-id="c4224-169">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="c4224-170">附件太大，分析器無法處理，且該附件的分析並未發生或未完成。</span><span class="sxs-lookup"><span data-stu-id="c4224-170">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="c4224-171">附件格式不正確，無法由分析程式處理。</span><span class="sxs-lookup"><span data-stu-id="c4224-171">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="c4224-172">這是因為舊的檔案格式、由不相容的軟體所建立的檔案，或假裝為非所聲稱之專案的結果。</span><span class="sxs-lookup"><span data-stu-id="c4224-172">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="c4224-173">對附件剖析的輸出過大，必須加以截斷。</span><span class="sxs-lookup"><span data-stu-id="c4224-173">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="c4224-174">附件的檔案類型無法偵測到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c4224-174">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="c4224-175">附件的檔案類型為 Office 365could 偵測，但不支援剖析該檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c4224-175">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="c4224-176">Exchange 存放區中的電子郵件屬性值過大，無法進行找回，無法處理郵件。</span><span class="sxs-lookup"><span data-stu-id="c4224-176">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="c4224-177">這通常只會在電子郵件的 body 屬性時發生。</span><span class="sxs-lookup"><span data-stu-id="c4224-177">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="c4224-178">內容檢索程式無法解碼受 RMS 保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="c4224-178">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="c4224-179">在編制索引期間檔中識別過多的字。</span><span class="sxs-lookup"><span data-stu-id="c4224-179">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="c4224-180">當達到此限制時，處理屬性已停止，而且會截斷屬性。</span><span class="sxs-lookup"><span data-stu-id="c4224-180">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="c4224-181">[錯誤] 欄位描述 [錯誤標記] 欄位中所列的處理錯誤所影響的欄位。</span><span class="sxs-lookup"><span data-stu-id="c4224-181">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="c4224-182">如果您正在搜尋諸如或的屬性 `subject` `participants` ，則郵件本文中的錯誤不會影響搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="c4224-182">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="c4224-183">這對判斷可能需要進一步調查的部分索引項目目是很有用的。</span><span class="sxs-lookup"><span data-stu-id="c4224-183">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="c4224-184">使用 PowerShell 腳本，判斷組織的部分索引電子郵件專案的危險性</span><span class="sxs-lookup"><span data-stu-id="c4224-184">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="c4224-185">下列步驟說明如何執行 PowerShell 腳本，搜尋所有 Exchange 信箱中的所有專案，然後產生有關組織的部分索引電子郵件專案（按計數和大小）的比例的報告，並顯示每個索引錯誤的專案數（及其檔案類型）。</span><span class="sxs-lookup"><span data-stu-id="c4224-185">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="c4224-186">使用上一節中的錯誤標記描述來識別索引錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4224-186">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="c4224-187">使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `PartiallyIndexedItems.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="c4224-187">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="c4224-188">[連線到安全性與合規性中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="c4224-188">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="c4224-189">在 [安全性 & 規範中心] PowerShell 中，移至您在步驟1中用來儲存腳本的資料夾，然後執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="c4224-189">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="c4224-190">以下是腳本傳回的輸出範例。</span><span class="sxs-lookup"><span data-stu-id="c4224-190">Here's an example fo the output returned by the script.</span></span>
  
![從腳本輸出的範例，產生您組織對部分索引電子郵件專案的公開報告](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="c4224-192">注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="c4224-192">Note the following:</span></span>
  
1. <span data-ttu-id="c4224-193">電子郵件專案的總數和大小，以及組織的部分索引電子郵件專案（依計數和大小）的比例</span><span class="sxs-lookup"><span data-stu-id="c4224-193">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="c4224-194">清單錯誤標記，以及發生錯誤的對應檔案類型。</span><span class="sxs-lookup"><span data-stu-id="c4224-194">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4224-195">請參閱</span><span class="sxs-lookup"><span data-stu-id="c4224-195">See also</span></span>

[<span data-ttu-id="c4224-196">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="c4224-196">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
