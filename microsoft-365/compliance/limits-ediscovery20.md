---
title: 進階電子文件探索限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Microsoft 365 中的高級 eDiscovery 解決方案的大小寫限制、索引限制和搜尋限制。
ms.openlocfilehash: 7d676b568c7e4cddedeff02c62b4645619d53357
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446250"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="61222-103">進階電子文件探索的限制</span><span class="sxs-lookup"><span data-stu-id="61222-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="61222-104">本文說明 Microsoft 365 中的高級 eDiscovery 解決方案的限制。</span><span class="sxs-lookup"><span data-stu-id="61222-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="61222-105">案例與複查集限制</span><span class="sxs-lookup"><span data-stu-id="61222-105">Case and review set limits</span></span>

<span data-ttu-id="61222-106">下表列出高級 eDiscovery 中案例和審閱集的限制。</span><span class="sxs-lookup"><span data-stu-id="61222-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="61222-107">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61222-107">**Description of limit**</span></span>|<span data-ttu-id="61222-108">**限制**</span><span class="sxs-lookup"><span data-stu-id="61222-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61222-109">在案例) 中，所有審閱集可以新增到案例中的檔總數目 (。</span><span class="sxs-lookup"><span data-stu-id="61222-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="61222-110">3 百萬</span><span class="sxs-lookup"><span data-stu-id="61222-110">3 million</span></span> <br/> |
|<span data-ttu-id="61222-111">每個負載集的檔案大小總計。</span><span class="sxs-lookup"><span data-stu-id="61222-111">Total file size per load set.</span></span> <span data-ttu-id="61222-112">這包括將非 Office 365 載入至審閱集。</span><span class="sxs-lookup"><span data-stu-id="61222-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="61222-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="61222-113">300 GB</span></span> <br/> |
|<span data-ttu-id="61222-114">每天組織中的所有審閱集合中載入的資料總量。</span><span class="sxs-lookup"><span data-stu-id="61222-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="61222-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="61222-115">2 TB</span></span> <br/> |
|<span data-ttu-id="61222-116">每個案例的載入集數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="61222-117">200</span><span class="sxs-lookup"><span data-stu-id="61222-117">200</span></span> <br/> |
|<span data-ttu-id="61222-118">每個案例的審閱集數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="61222-119">共</span><span class="sxs-lookup"><span data-stu-id="61222-119">20</span></span> <br/> |
|<span data-ttu-id="61222-120">每個案例的標記群組數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="61222-121">1000</span><span class="sxs-lookup"><span data-stu-id="61222-121">1000</span></span> <br/> |
|<span data-ttu-id="61222-122">每個案例的標記數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="61222-123">1000</span><span class="sxs-lookup"><span data-stu-id="61222-123">1000</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="61222-124">索引限制</span><span class="sxs-lookup"><span data-stu-id="61222-124">Indexing limits</span></span>

<span data-ttu-id="61222-125">下表列出高級 eDiscovery 中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="61222-125">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="61222-126">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61222-126">**Description of limit**</span></span>|<span data-ttu-id="61222-127">**限制**</span><span class="sxs-lookup"><span data-stu-id="61222-127">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="61222-128">從單一檔案解壓縮的字元數上限。</span><span class="sxs-lookup"><span data-stu-id="61222-128">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="61222-129">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61222-129">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="61222-130">單一檔案的大小上限。</span><span class="sxs-lookup"><span data-stu-id="61222-130">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="61222-131">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61222-131">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="61222-132">檔中內嵌專案的最大深度。</span><span class="sxs-lookup"><span data-stu-id="61222-132">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="61222-133">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61222-133">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="61222-134">光學字元辨識 (OCR) 所處理的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="61222-134">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="61222-135">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="61222-135">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="61222-136">搜尋限制</span><span class="sxs-lookup"><span data-stu-id="61222-136">Search limits</span></span>

<span data-ttu-id="61222-137">本節所述的限制與使用 [ **搜尋** ] 索引標籤上的 [搜尋] 工具收集案例的資料有關。</span><span class="sxs-lookup"><span data-stu-id="61222-137">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="61222-138">如需詳細資訊，請參閱 [在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="61222-138">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="61222-139">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61222-139">**Description of limit**</span></span>|<span data-ttu-id="61222-140">**限制**</span><span class="sxs-lookup"><span data-stu-id="61222-140">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61222-141">可在單一搜尋中搜尋的信箱或網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-141">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="61222-142">無限制</span><span class="sxs-lookup"><span data-stu-id="61222-142">No limit</span></span>  <br/> |
|<span data-ttu-id="61222-143">可以同時執行的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-143">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="61222-144">無限制</span><span class="sxs-lookup"><span data-stu-id="61222-144">No limit</span></span>  <br/> | 
|<span data-ttu-id="61222-145">單一使用者可以同時開始的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-145">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="61222-146">10 </span><span class="sxs-lookup"><span data-stu-id="61222-146">10</span></span>  <br/> | 
|<span data-ttu-id="61222-147">搜尋查詢 (包含運算子和條件) 的最大字元數。</span><span class="sxs-lookup"><span data-stu-id="61222-147">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="61222-148">**信箱**：10000</span><span class="sxs-lookup"><span data-stu-id="61222-148">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="61222-149">**網站**：4000搜尋所有網站或2000時搜尋最多20個網站時 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="61222-149">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="61222-150">首碼萬用字元的最小字母字元數目;例如\*\*一個 \* **或**設定 \* \*\*。</span><span class="sxs-lookup"><span data-stu-id="61222-150">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="61222-151">3 </span><span class="sxs-lookup"><span data-stu-id="61222-151">3</span></span>  <br/> |  
|<span data-ttu-id="61222-152">使用首碼萬用字元來搜尋確切的字詞，或是使用前置詞萬用字元及 **接近** 的布林運算子時，所傳回的最大變種。</span><span class="sxs-lookup"><span data-stu-id="61222-152">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="61222-153">10000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="61222-153">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="61222-154">搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61222-154">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="61222-155">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="61222-155">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="61222-156">100</span><span class="sxs-lookup"><span data-stu-id="61222-156">100</span></span>  <br/> |
|<span data-ttu-id="61222-157">搜尋時，預覽頁面上顯示的所有信箱中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61222-157">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="61222-158">1,000</span><span class="sxs-lookup"><span data-stu-id="61222-158">1,000</span></span>  <br/> |
|<span data-ttu-id="61222-159">可針對搜尋結果預覽的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-159">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="61222-160">如果有超過1000個信箱包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前1000個信箱。</span><span class="sxs-lookup"><span data-stu-id="61222-160">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="61222-161">1,000</span><span class="sxs-lookup"><span data-stu-id="61222-161">1,000</span></span>  <br/> |
|<span data-ttu-id="61222-162">在 [預覽] 頁面上，針對搜尋顯示之商務網站 SharePoint 和 OneDrive 的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61222-162">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="61222-163">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="61222-163">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="61222-164">200</span><span class="sxs-lookup"><span data-stu-id="61222-164">200</span></span>  <br/> |
|<span data-ttu-id="61222-165">可用於預覽搜尋結果的商務網站 SharePoint 和 OneDrive 數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-165">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="61222-166">如果有超過200個網站包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前200網站。</span><span class="sxs-lookup"><span data-stu-id="61222-166">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="61222-167">200</span><span class="sxs-lookup"><span data-stu-id="61222-167">200</span></span>  <br/> |
|<span data-ttu-id="61222-168">搜尋時預覽頁面上顯示的每個公用資料夾信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61222-168">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="61222-169">100</span><span class="sxs-lookup"><span data-stu-id="61222-169">100</span></span>  <br/> |
|<span data-ttu-id="61222-170">在 [預覽] 頁面上顯示的所有公用資料夾信箱專案中找到的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="61222-170">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="61222-171">200</span><span class="sxs-lookup"><span data-stu-id="61222-171">200</span></span>  <br/> |
|<span data-ttu-id="61222-172">可預覽搜尋結果的公用資料夾信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-172">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="61222-173">如果有超過500的公用資料夾信箱包含符合搜尋查詢的專案，則預覽中只可使用具有最多結果的前500個信箱。</span><span class="sxs-lookup"><span data-stu-id="61222-173">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="61222-174">500</span><span class="sxs-lookup"><span data-stu-id="61222-174">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="61222-175">檢視器限制</span><span class="sxs-lookup"><span data-stu-id="61222-175">Viewer limits</span></span>

|<span data-ttu-id="61222-176">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61222-176">**Description of limit**</span></span>|<span data-ttu-id="61222-177">**限制**</span><span class="sxs-lookup"><span data-stu-id="61222-177">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="61222-178">可在原生檢視器中查看的 Excel 檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="61222-178">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="61222-179">4 MB</span><span class="sxs-lookup"><span data-stu-id="61222-179">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="61222-180">複查設定的下載限制</span><span class="sxs-lookup"><span data-stu-id="61222-180">Review set download limits</span></span>

|<span data-ttu-id="61222-181">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="61222-181">**Description of limit**</span></span>|<span data-ttu-id="61222-182">**限制**</span><span class="sxs-lookup"><span data-stu-id="61222-182">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61222-183">從審閱集下載的檔總大小或檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-183">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="61222-184">3 MB 或50檔 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="61222-184">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="61222-185"><sup>1</sup> 任何超出單一檔限制的專案會顯示為處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="61222-185"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="61222-186"><sup>2</sup> 搜尋商務位置的 SharePoint 和 OneDrive 時，所搜尋之網站 URLs 中的字元會因此限制而計數。</span><span class="sxs-lookup"><span data-stu-id="61222-186"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="61222-187"><sup>3</sup> ：非片語查詢 (關鍵字值，但不使用雙引號) 我們使用特殊的前置詞索引。</span><span class="sxs-lookup"><span data-stu-id="61222-187"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="61222-188">這會告訴我們檔中的字詞，但不會出現在檔中。</span><span class="sxs-lookup"><span data-stu-id="61222-188">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="61222-189">若要執行片語查詢 (關鍵字值使用雙引號) ，我們需要比較檔內的字詞中的文字的位置。</span><span class="sxs-lookup"><span data-stu-id="61222-189">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="61222-190">這表示我們無法使用關鍵字查詢的首碼索引。</span><span class="sxs-lookup"><span data-stu-id="61222-190">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="61222-191">在此情況下，我們會以內部首碼擴充的任何可能的字來內部展開查詢;例如， \*\*time \* \*\*可以展開為 **"time 或 timer OR time 或 timex or timeboxed or ..."**。</span><span class="sxs-lookup"><span data-stu-id="61222-191">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="61222-192">10000的限制是 word 可以擴充的變種數目上限，而不是符合查詢的檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="61222-192">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="61222-193">非片語字詞沒有上限。</span><span class="sxs-lookup"><span data-stu-id="61222-193">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="61222-194"><sup>4</sup> 此限制適用于從審閱集下載選取的檔。</span><span class="sxs-lookup"><span data-stu-id="61222-194"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="61222-195">它不會套用到從審閱集匯出檔。</span><span class="sxs-lookup"><span data-stu-id="61222-195">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="61222-196">如需下載及匯出檔的詳細資訊，請參閱 [在高級 eDiscovery 中匯出案例資料](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="61222-196">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

