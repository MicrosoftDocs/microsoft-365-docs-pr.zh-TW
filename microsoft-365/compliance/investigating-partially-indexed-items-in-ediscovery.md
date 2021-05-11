---
title: 調查 eDiscovery 中已部分索引的專案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何從組織內的 Exchange、SharePoint 及商務用 OneDrive 中，管理部分索引項目目 (也稱為未編制索引的專案) 。
ms.openlocfilehash: 539fd2687735a5ee14be543750becca8c6c3154c
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311449"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="b350f-103">調查 eDiscovery 中已部分索引的專案</span><span class="sxs-lookup"><span data-stu-id="b350f-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="b350f-104">您從 Microsoft 365 合規性中心執行的 eDiscovery 搜尋，會在您執行搜尋時，自動將部分索引項目目納入估計的搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="b350f-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="b350f-105">部分編制索引的專案 Exchange SharePoint 上的信箱專案和檔，以及商務用 OneDrive 的網站，因為某些原因並未完全編制搜尋的索引。</span><span class="sxs-lookup"><span data-stu-id="b350f-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="b350f-106">大部分電子郵件訊息和網站檔都已成功編制索引，因為它們在電子郵件的 [索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)內。</span><span class="sxs-lookup"><span data-stu-id="b350f-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="b350f-107">不過，有些專案可能會超出這些索引限制，而且會進行部分編制索引。</span><span class="sxs-lookup"><span data-stu-id="b350f-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="b350f-108">以下是在執行 eDiscovery 搜尋時，無法將專案編制索引以進行搜尋的其他原因，而且會傳回成部分索引項目目：</span><span class="sxs-lookup"><span data-stu-id="b350f-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="b350f-109">電子郵件的附加檔案沒有有效的處理常式，例如映射檔;這是部分索引電子郵件專案最常見的原因。</span><span class="sxs-lookup"><span data-stu-id="b350f-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="b350f-110">附加至電子郵件的檔案太多。</span><span class="sxs-lookup"><span data-stu-id="b350f-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="b350f-111">附加到電子郵件的檔案太大。</span><span class="sxs-lookup"><span data-stu-id="b350f-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="b350f-112">檔案類型支援索引編製，但在編製特定檔案的索引時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="b350f-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="b350f-113">雖然這種方式不同，但大多陣列織客戶的內容少於磁片容量的1%，而不是以部分索引的大小小於12% 的內容。</span><span class="sxs-lookup"><span data-stu-id="b350f-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="b350f-114">磁片區與大小之間差異的原因是，較大的檔案包含無法完全編制索引之內容的可能性較高。</span><span class="sxs-lookup"><span data-stu-id="b350f-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="b350f-115">為何搜尋的部分索引項目目計數變更？</span><span class="sxs-lookup"><span data-stu-id="b350f-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="b350f-116">在您執行 eDiscovery 搜尋之後，搜尋位置中已部分索引項目目的總數和大小會列在搜尋結果統計資料中，顯示在搜尋的詳細統計資料中。</span><span class="sxs-lookup"><span data-stu-id="b350f-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="b350f-117">請注意，這些是在搜尋統計資料中稱為未  *編制索引的專案*  。</span><span class="sxs-lookup"><span data-stu-id="b350f-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="b350f-118">以下是會影響搜尋結果中傳回的部分索引項目目數目的一些事項：</span><span class="sxs-lookup"><span data-stu-id="b350f-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="b350f-119">如果專案已部分編制索引，且符合搜尋查詢，則會同時包含搜尋結果專案的計數 (和) 大小，以及部分編制索引的專案。</span><span class="sxs-lookup"><span data-stu-id="b350f-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="b350f-120">不過，當匯出相同搜尋的結果時，此專案會包含在一組搜尋結果中;它不會包含在部分索引項目目中。</span><span class="sxs-lookup"><span data-stu-id="b350f-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="b350f-121">位於 SharePoint 和 OneDrive 網站中的部分索引項目目 *不會* 包含在搜尋的詳細統計資料中顯示的部分索引項目目估計內。</span><span class="sxs-lookup"><span data-stu-id="b350f-121">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="b350f-122">不過，當您匯出 eDiscovery 搜尋的結果時，可以匯出部分索引的專案。</span><span class="sxs-lookup"><span data-stu-id="b350f-122">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="b350f-123">例如，如果您只有搜尋網站，估計數目的部分索引項目目會是零。</span><span class="sxs-lookup"><span data-stu-id="b350f-123">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="b350f-124">計算組織中已部分索引的專案比率</span><span class="sxs-lookup"><span data-stu-id="b350f-124">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="b350f-125">若要瞭解組織在部分索引項目目中的危險性，您可以使用空白的關鍵字查詢) ，在所有信箱中執行所有內容的搜尋 (。</span><span class="sxs-lookup"><span data-stu-id="b350f-125">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="b350f-126">在下列範例中，有 1629904 (146.46 GB) 完整編制索引的專案，以及 10025 (10.27 GB) 部分索引的專案。</span><span class="sxs-lookup"><span data-stu-id="b350f-126">In the following example, there are 1,629,904 (146.46 GB) fully indexed items and 10,025 (10.27 GB) partially indexed items.</span></span>
  
![顯示部分索引項目目之搜尋統計資料的範例](../media/PartiallyIndexedItemsTest.png)
  
<span data-ttu-id="b350f-128">您可以使用下列計算來判斷部分索引項目目的百分比。</span><span class="sxs-lookup"><span data-stu-id="b350f-128">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="b350f-129">**若要計算組織中已部分索引的專案比率：**</span><span class="sxs-lookup"><span data-stu-id="b350f-129">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

<span data-ttu-id="b350f-130">透過上述範例中的搜尋結果，所有信箱專案的0.62% 都會部分編制索引。</span><span class="sxs-lookup"><span data-stu-id="b350f-130">By using the search results from the previous example, 0.62% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="b350f-131">**若要計算組織中部分索引項目目大小的百分比：**</span><span class="sxs-lookup"><span data-stu-id="b350f-131">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 MB) x 100 = 7.0%`

<span data-ttu-id="b350f-132">在上一個範例中，信箱專案總大小的7% 是來自部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="b350f-132">So in the previous example, 7% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="b350f-133">如先前所述，大多陣列織客戶的內容少於1% 的內容，而不是以部分索引的大小小於12% 的內容。</span><span class="sxs-lookup"><span data-stu-id="b350f-133">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="b350f-134">使用部分編制索引的專案</span><span class="sxs-lookup"><span data-stu-id="b350f-134">Working with partially indexed items</span></span>

<span data-ttu-id="b350f-135">在需要檢查部分專案以驗證它們不包含相關資訊的情況下，您可以匯出包含部分索引項目目相關資訊的 [內容搜尋報告](export-a-content-search-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="b350f-135">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="b350f-136">當您匯出內容搜尋報告時，請務必選擇其中一個包含部分索引項目目的匯出選項。</span><span class="sxs-lookup"><span data-stu-id="b350f-136">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![選擇第二個或第三個選項，匯出已部分索引的專案](../media/PartiallyIndexedItemsExportOptions.png)
  
<span data-ttu-id="b350f-138">當您使用其中一個選項匯出 eDiscovery 搜尋結果或搜尋報告時，匯出會包含一個名為「未編制索引」 Items.csv 的報表。</span><span class="sxs-lookup"><span data-stu-id="b350f-138">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="b350f-139">這個報告包含的資訊大部分與 ResultsLog.csv 檔案相同;不過，未編制索引的 Items.csv 檔案中也包含與部分索引項目目相關的兩個欄位： **錯誤標記** 和 **錯誤屬性**。</span><span class="sxs-lookup"><span data-stu-id="b350f-139">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="b350f-140">這些欄位包含每個部分索引項目目之索引錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b350f-140">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="b350f-141">使用這兩個欄位中的資訊可協助您判斷是否有特定影響調查的索引錯誤。</span><span class="sxs-lookup"><span data-stu-id="b350f-141">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="b350f-142">如果是的話，您可以執行目標搜尋，並取得及匯出特定的電子郵件訊息，並 SharePoint 或 OneDrive 檔，以便進行檢查，以判斷是否與您的調查相關。</span><span class="sxs-lookup"><span data-stu-id="b350f-142">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="b350f-143">如需逐步指示，請參閱[在 Office 365 中準備目標搜尋的 CSV](csv-file-for-an-id-list-content-search.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="b350f-143">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b350f-144">未編制索引的 Items.csv 檔案也包含名為「 **錯誤類型** 」和「 **錯誤訊息**」的欄位。</span><span class="sxs-lookup"><span data-stu-id="b350f-144">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="b350f-145">這些是舊版欄位，包含類似于 [ **錯誤標記** ] 和 [ **錯誤屬性** ] 欄位中的資訊，但詳細資訊更少的資訊。</span><span class="sxs-lookup"><span data-stu-id="b350f-145">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="b350f-146">您可以放心忽略這些舊版欄位。</span><span class="sxs-lookup"><span data-stu-id="b350f-146">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="b350f-147">與部分索引項目目相關的錯誤</span><span class="sxs-lookup"><span data-stu-id="b350f-147">Errors related to partially indexed items</span></span>

<span data-ttu-id="b350f-148">錯誤標記是由兩部分資訊組成，錯誤和檔案類型。</span><span class="sxs-lookup"><span data-stu-id="b350f-148">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="b350f-149">例如，在此錯誤/檔案類型對中：</span><span class="sxs-lookup"><span data-stu-id="b350f-149">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="b350f-150">`parseroutputsize` 為錯誤， `xls` 是發生錯誤之檔案的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="b350f-150">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="b350f-151">在無法辨識檔案類型或檔案類型未套用至錯誤的情況下，您會看到 [！注意事項] 此值會顯示 `noformat` 在 [檔案類型] 的位置。</span><span class="sxs-lookup"><span data-stu-id="b350f-151">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="b350f-152">下列是索引錯誤的清單，以及錯誤可能原因的描述。</span><span class="sxs-lookup"><span data-stu-id="b350f-152">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="b350f-153">錯誤標記</span><span class="sxs-lookup"><span data-stu-id="b350f-153">Error tag</span></span> | <span data-ttu-id="b350f-154">描述</span><span class="sxs-lookup"><span data-stu-id="b350f-154">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="b350f-155">電子郵件中有太多附件，但未處理某些附件。</span><span class="sxs-lookup"><span data-stu-id="b350f-155">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="b350f-156">內容檢索程式和檔剖析器發現嵌套在其他附件中的附件太多層級。</span><span class="sxs-lookup"><span data-stu-id="b350f-156">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="b350f-157">部分附件未處理。</span><span class="sxs-lookup"><span data-stu-id="b350f-157">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="b350f-158">因為郵件是受 RMS 保護，所以附件的解碼失敗。</span><span class="sxs-lookup"><span data-stu-id="b350f-158">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="b350f-159">附加到電子郵件的檔案太大，無法處理。</span><span class="sxs-lookup"><span data-stu-id="b350f-159">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="b350f-160">當寫入已處理的電子郵件給索引時，其中一個可編制索引的屬性太大，已被截斷。</span><span class="sxs-lookup"><span data-stu-id="b350f-160">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="b350f-161">截斷的屬性會列在 [錯誤屬性] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="b350f-161">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="b350f-162">電子郵件包含無法當作有效的 Unicode 處理的文字。</span><span class="sxs-lookup"><span data-stu-id="b350f-162">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="b350f-163">此專案的索引可能不完整。</span><span class="sxs-lookup"><span data-stu-id="b350f-163">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="b350f-164">附件或電子郵件的內容已加密，而且 Microsoft 365 無法解碼內容。</span><span class="sxs-lookup"><span data-stu-id="b350f-164">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="b350f-165">剖析時發生未知的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b350f-165">An unknown error occurred during parsing.</span></span> <span data-ttu-id="b350f-166">這通常是軟體錯誤或服務損毀的結果。</span><span class="sxs-lookup"><span data-stu-id="b350f-166">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="b350f-167">附件太大，分析器無法處理，且該附件的分析並未發生或未完成。</span><span class="sxs-lookup"><span data-stu-id="b350f-167">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="b350f-168">附件格式不正確，無法由分析程式處理。</span><span class="sxs-lookup"><span data-stu-id="b350f-168">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="b350f-169">這項結果可能是舊的檔案格式、不相容的軟體所建立的檔案，或偽裝成非宣告專案的病毒。</span><span class="sxs-lookup"><span data-stu-id="b350f-169">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="b350f-170">對附件剖析的輸出過大，必須加以截斷。</span><span class="sxs-lookup"><span data-stu-id="b350f-170">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="b350f-171">附件的檔案類型 Microsoft 365 無法偵測。</span><span class="sxs-lookup"><span data-stu-id="b350f-171">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="b350f-172">附件的檔案類型 Office 365 可以偵測，但不支援分析該檔案類型。</span><span class="sxs-lookup"><span data-stu-id="b350f-172">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="b350f-173">Exchange 儲存區中的電子郵件屬性值過大，無法進行找回，無法處理郵件。</span><span class="sxs-lookup"><span data-stu-id="b350f-173">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="b350f-174">這通常只會在電子郵件的 body 屬性時發生。</span><span class="sxs-lookup"><span data-stu-id="b350f-174">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="b350f-175">內容檢索程式無法解碼受 RMS 保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="b350f-175">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="b350f-176">在編制索引期間檔中識別過多的字。</span><span class="sxs-lookup"><span data-stu-id="b350f-176">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="b350f-177">當達到此限制時，處理屬性已停止，而且會截斷屬性。</span><span class="sxs-lookup"><span data-stu-id="b350f-177">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="b350f-178">[錯誤] 欄位描述 [錯誤標記] 欄位中所列的處理錯誤所影響的欄位。</span><span class="sxs-lookup"><span data-stu-id="b350f-178">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="b350f-179">如果您正在搜尋諸如或的屬性  `subject`  `participants` ，則郵件本文中的錯誤不會影響搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="b350f-179">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="b350f-180">這對判斷可能需要進一步調查的部分索引項目目是很有用的。</span><span class="sxs-lookup"><span data-stu-id="b350f-180">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="b350f-181">使用 PowerShell 腳本，判斷組織的部分索引電子郵件專案的危險性</span><span class="sxs-lookup"><span data-stu-id="b350f-181">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="b350f-182">下列步驟說明如何執行 PowerShell 腳本，搜尋所有 Exchange 信箱中的所有專案，然後產生有關組織的部分索引電子郵件專案 (依計數和大小) 之比率的報告，並顯示每個索引錯誤的專案數目 (及其檔案類型) 。</span><span class="sxs-lookup"><span data-stu-id="b350f-182">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="b350f-183">使用上一節中的錯誤標記描述來識別索引錯誤。</span><span class="sxs-lookup"><span data-stu-id="b350f-183">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="b350f-184">使用 .ps1 的檔案名尾碼，將下列文字儲存至 Windows PowerShell 腳本檔案;例如， `PartiallyIndexedItems.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="b350f-184">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="b350f-185">[連線到安全性與合規性中心 PowerShell](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b350f-185">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="b350f-186">在 [安全性 & 規範中心] PowerShell 中，移至您在步驟1中用來儲存腳本的資料夾，然後執行腳本;例如：</span><span class="sxs-lookup"><span data-stu-id="b350f-186">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="b350f-187">以下是腳本傳回的輸出範例。</span><span class="sxs-lookup"><span data-stu-id="b350f-187">Here's an example fo the output returned by the script.</span></span>
  
![從腳本輸出的範例，產生您組織對部分索引電子郵件專案的公開報告](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="b350f-189">注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="b350f-189">Note the following:</span></span>
>  
> - <span data-ttu-id="b350f-190">電子郵件專案的總數和大小，以及您組織的部分索引電子郵件專案 (依計數和大小) 所進行的比例。</span><span class="sxs-lookup"><span data-stu-id="b350f-190">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="b350f-191">清單錯誤標記，以及發生錯誤的對應檔案類型。</span><span class="sxs-lookup"><span data-stu-id="b350f-191">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b350f-192">請參閱</span><span class="sxs-lookup"><span data-stu-id="b350f-192">See also</span></span>

[<span data-ttu-id="b350f-193">EDiscovery 中已部分索引的專案</span><span class="sxs-lookup"><span data-stu-id="b350f-193">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)