---
title: 進階電子文件探索限制
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Microsoft 365 中的高級 eDiscovery 解決方案的大小寫限制、索引限制和搜尋限制。
ms.openlocfilehash: 4f8222abaea0e8920e48f2f7b506d9477e93bc84
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126866"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="61344-103">進階電子文件探索的限制</span><span class="sxs-lookup"><span data-stu-id="61344-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="61344-104">本文說明 Microsoft 365 中的高級 eDiscovery 解決方案的限制。</span><span class="sxs-lookup"><span data-stu-id="61344-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="61344-105">案例與複查集限制</span><span class="sxs-lookup"><span data-stu-id="61344-105">Case and review set limits</span></span>

<span data-ttu-id="61344-106">下表列出高級 eDiscovery 中案例和審閱集的限制。</span><span class="sxs-lookup"><span data-stu-id="61344-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="61344-107">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61344-107">**Description of limit**</span></span>|<span data-ttu-id="61344-108">**限制**</span><span class="sxs-lookup"><span data-stu-id="61344-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61344-109">可以新增至案例的檔總數（案例中的所有審閱集）。</span><span class="sxs-lookup"><span data-stu-id="61344-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="61344-110">3 百萬</span><span class="sxs-lookup"><span data-stu-id="61344-110">3 million</span></span> <br/> |
|<span data-ttu-id="61344-111">每個負載集的檔案大小總計。</span><span class="sxs-lookup"><span data-stu-id="61344-111">Total file size per load set.</span></span> <span data-ttu-id="61344-112">這包括將非 Office 365 載入至審閱集。</span><span class="sxs-lookup"><span data-stu-id="61344-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="61344-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="61344-113">300 GB</span></span> <br/> |
|<span data-ttu-id="61344-114">每天組織中的所有審閱集合中載入的資料總量。</span><span class="sxs-lookup"><span data-stu-id="61344-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="61344-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="61344-115">2 TB</span></span> <br/> |
|<span data-ttu-id="61344-116">每個案例的載入集數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="61344-117">15 </span><span class="sxs-lookup"><span data-stu-id="61344-117">15</span></span> <br/> |
|<span data-ttu-id="61344-118">每個案例的審閱集數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="61344-119">共</span><span class="sxs-lookup"><span data-stu-id="61344-119">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="61344-120">索引限制</span><span class="sxs-lookup"><span data-stu-id="61344-120">Indexing limits</span></span>

<span data-ttu-id="61344-121">下表列出高級 eDiscovery 中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="61344-121">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="61344-122">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61344-122">**Description of limit**</span></span>|<span data-ttu-id="61344-123">**限制**</span><span class="sxs-lookup"><span data-stu-id="61344-123">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="61344-124">從單一檔案解壓縮的字元數上限。</span><span class="sxs-lookup"><span data-stu-id="61344-124">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="61344-125">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61344-125">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="61344-126">單一檔案的大小上限。</span><span class="sxs-lookup"><span data-stu-id="61344-126">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="61344-127">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61344-127">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="61344-128">檔中內嵌專案的最大深度。</span><span class="sxs-lookup"><span data-stu-id="61344-128">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="61344-129">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61344-129">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="61344-130">光學字元辨識（OCR）所處理的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="61344-130">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="61344-131">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61344-131">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="61344-132">搜尋限制</span><span class="sxs-lookup"><span data-stu-id="61344-132">Search limits</span></span>

<span data-ttu-id="61344-133">本節所述的限制與使用 [**搜尋**] 索引標籤上的 [搜尋] 工具收集案例的資料有關。</span><span class="sxs-lookup"><span data-stu-id="61344-133">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="61344-134">如需詳細資訊，請參閱[在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="61344-134">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="61344-135">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61344-135">**Description of limit**</span></span>|<span data-ttu-id="61344-136">**限制**</span><span class="sxs-lookup"><span data-stu-id="61344-136">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61344-137">可在單一搜尋中搜尋的信箱或網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-137">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="61344-138">無限制</span><span class="sxs-lookup"><span data-stu-id="61344-138">No limit</span></span>  <br/> |
|<span data-ttu-id="61344-139">可以同時執行的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-139">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="61344-140">無限制</span><span class="sxs-lookup"><span data-stu-id="61344-140">No limit</span></span>  <br/> | 
|<span data-ttu-id="61344-141">單一使用者可以同時開始的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-141">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="61344-142">10 </span><span class="sxs-lookup"><span data-stu-id="61344-142">10</span></span>  <br/> | 
|<span data-ttu-id="61344-143">搜尋查詢的最大字元數（包括運算子和條件）。</span><span class="sxs-lookup"><span data-stu-id="61344-143">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="61344-144">**信箱**：10000</span><span class="sxs-lookup"><span data-stu-id="61344-144">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="61344-145">**網站**：4000搜尋所有網站或2000時搜尋最多20個網站時<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="61344-145">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="61344-146">首碼萬用字元的最小字母字元數目;例如\*\*一個 \* **或**設定 \* \*\*。</span><span class="sxs-lookup"><span data-stu-id="61344-146">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="61344-147">3 </span><span class="sxs-lookup"><span data-stu-id="61344-147">3</span></span>  <br/> |  
|<span data-ttu-id="61344-148">使用首碼萬用字元來搜尋確切的字詞，或是使用前置詞萬用字元及**接近**的布林運算子時，所傳回的最大變種。</span><span class="sxs-lookup"><span data-stu-id="61344-148">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="61344-149">10000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="61344-149">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="61344-150">搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61344-150">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="61344-151">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="61344-151">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="61344-152">100</span><span class="sxs-lookup"><span data-stu-id="61344-152">100</span></span>  <br/> |
|<span data-ttu-id="61344-153">搜尋時，預覽頁面上顯示的所有信箱中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61344-153">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="61344-154">1,000</span><span class="sxs-lookup"><span data-stu-id="61344-154">1,000</span></span>  <br/> |
|<span data-ttu-id="61344-155">可針對搜尋結果預覽的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-155">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="61344-156">如果有超過1000個信箱包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前1000個信箱。</span><span class="sxs-lookup"><span data-stu-id="61344-156">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="61344-157">1,000</span><span class="sxs-lookup"><span data-stu-id="61344-157">1,000</span></span>  <br/> |
|<span data-ttu-id="61344-158">在 [預覽] 頁面上，針對搜尋顯示之商務網站 SharePoint 和 OneDrive 的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61344-158">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="61344-159">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="61344-159">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="61344-160">200</span><span class="sxs-lookup"><span data-stu-id="61344-160">200</span></span>  <br/> |
|<span data-ttu-id="61344-161">可用於預覽搜尋結果的商務網站 SharePoint 和 OneDrive 數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-161">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="61344-162">如果有超過200個網站包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前200網站。</span><span class="sxs-lookup"><span data-stu-id="61344-162">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="61344-163">200</span><span class="sxs-lookup"><span data-stu-id="61344-163">200</span></span>  <br/> |
|<span data-ttu-id="61344-164">搜尋時預覽頁面上顯示的每個公用資料夾信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61344-164">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="61344-165">100</span><span class="sxs-lookup"><span data-stu-id="61344-165">100</span></span>  <br/> |
|<span data-ttu-id="61344-166">在 [預覽] 頁面上顯示的所有公用資料夾信箱專案中找到的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61344-166">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="61344-167">200</span><span class="sxs-lookup"><span data-stu-id="61344-167">200</span></span>  <br/> |
|<span data-ttu-id="61344-168">可預覽搜尋結果的公用資料夾信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-168">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="61344-169">如果有超過500的公用資料夾信箱包含符合搜尋查詢的專案，則預覽中只可使用具有最多結果的前500個信箱。</span><span class="sxs-lookup"><span data-stu-id="61344-169">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="61344-170">500</span><span class="sxs-lookup"><span data-stu-id="61344-170">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="61344-171">檢視器限制</span><span class="sxs-lookup"><span data-stu-id="61344-171">Viewer limits</span></span>

|<span data-ttu-id="61344-172">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61344-172">**Description of limit**</span></span>|<span data-ttu-id="61344-173">**限制**</span><span class="sxs-lookup"><span data-stu-id="61344-173">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="61344-174">可在原生檢視器中查看的 Excel 檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="61344-174">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="61344-175">4 MB</span><span class="sxs-lookup"><span data-stu-id="61344-175">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="61344-176">複查設定的下載限制</span><span class="sxs-lookup"><span data-stu-id="61344-176">Review set download limits</span></span>

|<span data-ttu-id="61344-177">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61344-177">**Description of limit**</span></span>|<span data-ttu-id="61344-178">**限制**</span><span class="sxs-lookup"><span data-stu-id="61344-178">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61344-179">從審閱集下載的檔總大小或檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-179">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="61344-180">3 MB 或50檔<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="61344-180">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="61344-181"><sup>1</sup>任何超出單一檔限制的專案會顯示為處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="61344-181"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="61344-182"><sup>2</sup>搜尋商務位置的 SharePoint 和 OneDrive 時，所搜尋之網站 URLs 中的字元會因此限制而計數。</span><span class="sxs-lookup"><span data-stu-id="61344-182"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="61344-183"><sup>3</sup>若非片語查詢（不使用雙引號的關鍵字值），我們會使用特殊的首碼索引。</span><span class="sxs-lookup"><span data-stu-id="61344-183"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="61344-184">這會告訴我們檔中的字詞，但不會出現在檔中。</span><span class="sxs-lookup"><span data-stu-id="61344-184">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="61344-185">若要執行片語查詢（包含雙引號的關鍵字值），我們需要比較檔內的字詞中的文字的位置。</span><span class="sxs-lookup"><span data-stu-id="61344-185">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="61344-186">這表示我們無法使用關鍵字查詢的首碼索引。</span><span class="sxs-lookup"><span data-stu-id="61344-186">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="61344-187">在此情況下，我們會以內部首碼擴充的任何可能的字來內部展開查詢;例如， \*\*time \* \*\*可以展開為 **"time 或 timer OR time 或 timex or timeboxed or ..."**。</span><span class="sxs-lookup"><span data-stu-id="61344-187">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="61344-188">10000的限制是 word 可以擴充的變種數目上限，而不是符合查詢的檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="61344-188">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="61344-189">非片語字詞沒有上限。</span><span class="sxs-lookup"><span data-stu-id="61344-189">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="61344-190"><sup>4</sup>此限制適用于從審閱集下載選取的檔。</span><span class="sxs-lookup"><span data-stu-id="61344-190"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="61344-191">它不會套用到從審閱集匯出檔。</span><span class="sxs-lookup"><span data-stu-id="61344-191">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="61344-192">如需下載及匯出檔的詳細資訊，請參閱[在高級 eDiscovery 中匯出案例資料](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="61344-192">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

