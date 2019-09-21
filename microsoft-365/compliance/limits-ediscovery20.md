---
title: 進階電子文件限制
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解作用中的 Microsoft 365 進階電子文件解決方案的限制。 這包括大小寫的限制時使用搜尋工具來收集案例資料, 編製索引限制，以及搜尋限制。
ms.openlocfilehash: 622d2669457a2a1e84909aadae9b653ca37684ce
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077116"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="f4788-104">進階電子文件探索的限制</span><span class="sxs-lookup"><span data-stu-id="f4788-104">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="f4788-105">本文說明 Microsoft 365 進階電子文件解決方案中的限制。</span><span class="sxs-lookup"><span data-stu-id="f4788-105">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-limits"></a><span data-ttu-id="f4788-106">區分大小限制</span><span class="sxs-lookup"><span data-stu-id="f4788-106">Case limits</span></span>

<span data-ttu-id="f4788-107">下表列出在進階電子文件中的情況下的限制。</span><span class="sxs-lookup"><span data-stu-id="f4788-107">The following table lists the limits for cases in Advanced eDiscovery.</span></span>

|<span data-ttu-id="f4788-108">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="f4788-108">**Description of limit**</span></span>|<span data-ttu-id="f4788-109">**限制**</span><span class="sxs-lookup"><span data-stu-id="f4788-109">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4788-110">可以新增至案例 （如需所有檢閱都設定案例中） 的文件總數。</span><span class="sxs-lookup"><span data-stu-id="f4788-110">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="f4788-111">1 百萬</span><span class="sxs-lookup"><span data-stu-id="f4788-111">1 million</span></span>  <br/> |
|<span data-ttu-id="f4788-112">設定每負載的總檔案大小。</span><span class="sxs-lookup"><span data-stu-id="f4788-112">Total file size per load set.</span></span>  <br/> |<span data-ttu-id="f4788-113">100 GB</span><span class="sxs-lookup"><span data-stu-id="f4788-113">100 GB</span></span>  <br/> |
|<span data-ttu-id="f4788-114">總資料量載入每日的案例。</span><span class="sxs-lookup"><span data-stu-id="f4788-114">Total amount of data loaded into a case per day.</span></span><br/> |<span data-ttu-id="f4788-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="f4788-115">2 TB</span></span> <br/> |
|<span data-ttu-id="f4788-116">每個案例的載入集的最大數目。</span><span class="sxs-lookup"><span data-stu-id="f4788-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="f4788-117">15 </span><span class="sxs-lookup"><span data-stu-id="f4788-117">15</span></span> <br/> |
|<span data-ttu-id="f4788-118">檢閱的最大數目會設定每個案例。</span><span class="sxs-lookup"><span data-stu-id="f4788-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="f4788-119">20</span><span class="sxs-lookup"><span data-stu-id="f4788-119">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="f4788-120">索引限制</span><span class="sxs-lookup"><span data-stu-id="f4788-120">Indexing limits</span></span>

<span data-ttu-id="f4788-121">下表列出進階電子文件中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="f4788-121">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="f4788-122">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="f4788-122">**Description of limit**</span></span>|<span data-ttu-id="f4788-123">**限制**</span><span class="sxs-lookup"><span data-stu-id="f4788-123">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="f4788-124">從單一檔案解壓縮的字元數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-124">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="f4788-125">10 萬個<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f4788-125">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="f4788-126">單一檔案的大小上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-126">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="f4788-127">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f4788-127">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="f4788-128">最大深度內嵌在文件中的項目。</span><span class="sxs-lookup"><span data-stu-id="f4788-128">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="f4788-129">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f4788-129">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="f4788-130">處理由光學字元辨識 (OCR) 的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-130">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="f4788-131">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f4788-131">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="f4788-132">搜尋限制</span><span class="sxs-lookup"><span data-stu-id="f4788-132">Search limits</span></span>

<span data-ttu-id="f4788-133">在 [**搜尋**] 索引標籤上使用搜尋工具來收集資料的大小寫與相關本節所述的限制。</span><span class="sxs-lookup"><span data-stu-id="f4788-133">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="f4788-134">如需詳細資訊，請參閱[收集資料的進階電子文件中的案例](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f4788-134">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="f4788-135">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="f4788-135">**Description of limit**</span></span>|<span data-ttu-id="f4788-136">**限制**</span><span class="sxs-lookup"><span data-stu-id="f4788-136">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4788-137">最大數目的信箱或網站，可以在單一搜尋中搜尋的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f4788-137">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="f4788-138">無限制</span><span class="sxs-lookup"><span data-stu-id="f4788-138">No limit</span></span>  <br/> |
|<span data-ttu-id="f4788-139">可以在同一時間執行的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-139">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="f4788-140">無限制</span><span class="sxs-lookup"><span data-stu-id="f4788-140">No limit</span></span>  <br/> | 
|<span data-ttu-id="f4788-141">最大數目的單一使用者可以在同一時間開始搜尋的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f4788-141">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="f4788-142">10 </span><span class="sxs-lookup"><span data-stu-id="f4788-142">10</span></span>  <br/> | 
|<span data-ttu-id="f4788-143">搜尋查詢 （包括運算子和條件） 的字元數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-143">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="f4788-144">**信箱**： 10000</span><span class="sxs-lookup"><span data-stu-id="f4788-144">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="f4788-145">**網站**： 4000 搜尋最多 20 個網站<sup>2</sup>時，搜尋所有的網站] 或 [2000</span><span class="sxs-lookup"><span data-stu-id="f4788-145">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="f4788-146">前置詞萬用字元; alpha 字元數目下限例如**一個\*** 或**設定\***。</span><span class="sxs-lookup"><span data-stu-id="f4788-146">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="f4788-147">3</span><span class="sxs-lookup"><span data-stu-id="f4788-147">3</span></span>  <br/> |  
|<span data-ttu-id="f4788-148">傳回時所要搜尋的精準字詞或使用前置詞萬用字元和**NEAR**或**ONEAR**布林運算子使用前置詞萬用字元時最大的變化。</span><span class="sxs-lookup"><span data-stu-id="f4788-148">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** or **ONEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="f4788-149">10000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f4788-149">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="f4788-150">每個使用者信箱搜尋的預覽頁面顯示的項目數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-150">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="f4788-151">顯示最新的項目。</span><span class="sxs-lookup"><span data-stu-id="f4788-151">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="f4788-152">100</span><span class="sxs-lookup"><span data-stu-id="f4788-152">100</span></span>  <br/> |
|<span data-ttu-id="f4788-153">來自所有信箱搜尋的預覽頁面上顯示的項目數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-153">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="f4788-154">1,000</span><span class="sxs-lookup"><span data-stu-id="f4788-154">1,000</span></span>  <br/> |
|<span data-ttu-id="f4788-155">可以預覽搜尋結果中的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-155">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="f4788-156">如果有超過 1000 個信箱包含符合搜尋查詢的項目，僅上方 1000 個信箱與最多結果可供預覽。</span><span class="sxs-lookup"><span data-stu-id="f4788-156">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="f4788-157">1,000</span><span class="sxs-lookup"><span data-stu-id="f4788-157">1,000</span></span>  <br/> |
|<span data-ttu-id="f4788-158">從 SharePoint 和 OneDrive for Business 網站的搜尋的預覽頁面上顯示的項目數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-158">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="f4788-159">顯示最新的項目。</span><span class="sxs-lookup"><span data-stu-id="f4788-159">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="f4788-160">200</span><span class="sxs-lookup"><span data-stu-id="f4788-160">200</span></span>  <br/> |
|<span data-ttu-id="f4788-161">最大數目 SharePoint 和 OneDrive for Business 網站可預覽搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f4788-161">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="f4788-162">如果有 200 個以上的網站包含符合搜尋查詢的項目，只有前的 200 網站與最多結果可供預覽。</span><span class="sxs-lookup"><span data-stu-id="f4788-162">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="f4788-163">200</span><span class="sxs-lookup"><span data-stu-id="f4788-163">200</span></span>  <br/> |
|<span data-ttu-id="f4788-164">每個公用資料夾信箱搜尋的預覽頁面上顯示的項目數目上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-164">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="f4788-165">100</span><span class="sxs-lookup"><span data-stu-id="f4788-165">100</span></span>  <br/> |
|<span data-ttu-id="f4788-166">搜尋的預覽頁面上顯示的所有公用資料夾信箱項目中找到的項目數上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-166">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="f4788-167">200</span><span class="sxs-lookup"><span data-stu-id="f4788-167">200</span></span>  <br/> |
|<span data-ttu-id="f4788-168">最大數目可以預覽搜尋結果中的公用資料夾信箱的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f4788-168">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="f4788-169">如果有超過 500 個公用資料夾信箱包含符合搜尋查詢的項目，僅上方 500 個信箱與最多結果可供預覽。</span><span class="sxs-lookup"><span data-stu-id="f4788-169">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="f4788-170">500</span><span class="sxs-lookup"><span data-stu-id="f4788-170">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="f4788-171">檢視器] 限制</span><span class="sxs-lookup"><span data-stu-id="f4788-171">Viewer limits</span></span>

|<span data-ttu-id="f4788-172">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="f4788-172">**Description of limit**</span></span>|<span data-ttu-id="f4788-173">**限制**</span><span class="sxs-lookup"><span data-stu-id="f4788-173">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="f4788-174">可檢視的原生檢視器中的 Excel 檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-174">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="f4788-175">4 MB</span><span class="sxs-lookup"><span data-stu-id="f4788-175">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="f4788-176">檢閱設定下載限制</span><span class="sxs-lookup"><span data-stu-id="f4788-176">Review set download limits</span></span>

|<span data-ttu-id="f4788-177">**限制說明**</span><span class="sxs-lookup"><span data-stu-id="f4788-177">**Description of limit**</span></span>|<span data-ttu-id="f4788-178">**限制**</span><span class="sxs-lookup"><span data-stu-id="f4788-178">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4788-179">檔案大小總計或文件的最大數目下載來自檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="f4788-179">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="f4788-180">3 MB 或 50 的文件<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f4788-180">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="f4788-181"><sup>1</sup>超過單一檔案限制的任何項目會顯示為處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="f4788-181"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="f4788-182"><sup>2</sup>搜尋 SharePoint 和 OneDrive for Business 位置] 中，網站的 Url 中的字元時要搜尋比對這個限制的計數。</span><span class="sxs-lookup"><span data-stu-id="f4788-182"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="f4788-183"><sup>3</sup>非片語查詢 （不會使用雙引號關鍵字值） 我們會使用特殊的前置字元索引。</span><span class="sxs-lookup"><span data-stu-id="f4788-183"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="f4788-184">這會告知我們，word 就會發生在文件，但不是其中它就會發生在文件。</span><span class="sxs-lookup"><span data-stu-id="f4788-184">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="f4788-185">若要執行的片語查詢 （雙引號的關鍵字值），我們需要比較內文件中的字片語中的位置。</span><span class="sxs-lookup"><span data-stu-id="f4788-185">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="f4788-186">這表示，我們不能使用的前置字元索引片語查詢。</span><span class="sxs-lookup"><span data-stu-id="f4788-186">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="f4788-187">在此情況下，我們在內部依序展開 [與所有可能的字前置詞會展開成; 查詢例如，**時間\*** 可以展開至 **「 時間 OR 計時器時間 OR timex OR OR timeboxed 或...」**。</span><span class="sxs-lookup"><span data-stu-id="f4788-187">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="f4788-188">10000 的限制是變體 word 可以展開至不符合查詢的文件數目的最大數目。</span><span class="sxs-lookup"><span data-stu-id="f4788-188">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="f4788-189">非片語字詞沒有上限。</span><span class="sxs-lookup"><span data-stu-id="f4788-189">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="f4788-190"><sup>4</sup>此限制適用於從檢閱集下載選取文件。</span><span class="sxs-lookup"><span data-stu-id="f4788-190"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="f4788-191">它不會套用至來自檢閱設定匯出文件。</span><span class="sxs-lookup"><span data-stu-id="f4788-191">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="f4788-192">如需下載和匯出文件的詳細資訊，請參閱[匯出案例資料進階電子文件中](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="f4788-192">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

