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
ms.openlocfilehash: 145d5de5027a9d6171215c0602a733ced5265657
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445319"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="a6b98-103">進階電子文件探索的限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="a6b98-104">本文說明 Microsoft 365 中的高級 eDiscovery 解決方案的限制。</span><span class="sxs-lookup"><span data-stu-id="a6b98-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="a6b98-105">案例與複查集限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-105">Case and review set limits</span></span>

<span data-ttu-id="a6b98-106">下表列出高級 eDiscovery 中案例和審閱集的限制。</span><span class="sxs-lookup"><span data-stu-id="a6b98-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

| <span data-ttu-id="a6b98-107">限制的描述</span><span class="sxs-lookup"><span data-stu-id="a6b98-107">Description of limit</span></span> | <span data-ttu-id="a6b98-108">限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-108">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6b98-109">在案例) 中，所有審閱集可以新增到案例中的檔總數目 (。</span><span class="sxs-lookup"><span data-stu-id="a6b98-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="a6b98-110">3 百萬</span><span class="sxs-lookup"><span data-stu-id="a6b98-110">3 million</span></span> <br/> |
|<span data-ttu-id="a6b98-111">每個負載集的檔案大小總計。</span><span class="sxs-lookup"><span data-stu-id="a6b98-111">Total file size per load set.</span></span> <span data-ttu-id="a6b98-112">這包括將非 Office 365 載入至審閱集。</span><span class="sxs-lookup"><span data-stu-id="a6b98-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="a6b98-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="a6b98-113">300 GB</span></span> <br/> |
|<span data-ttu-id="a6b98-114">每天組織中的所有審閱集合中載入的資料總量。</span><span class="sxs-lookup"><span data-stu-id="a6b98-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="a6b98-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="a6b98-115">2 TB</span></span> <br/> |
|<span data-ttu-id="a6b98-116">每個案例的負載集數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-116">Maximum number of load sets per case.</span></span>  <br/> |<span data-ttu-id="a6b98-117">200</span><span class="sxs-lookup"><span data-stu-id="a6b98-117">200</span></span> <br/> |
|<span data-ttu-id="a6b98-118">每個案例的審閱集數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="a6b98-119">共</span><span class="sxs-lookup"><span data-stu-id="a6b98-119">20</span></span> <br/> |
|<span data-ttu-id="a6b98-120">每個案例的標記群組數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="a6b98-121">1000</span><span class="sxs-lookup"><span data-stu-id="a6b98-121">1000</span></span> <br/> |
|<span data-ttu-id="a6b98-122">每個案例的標記數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="a6b98-123">1000</span><span class="sxs-lookup"><span data-stu-id="a6b98-123">1000</span></span> <br/> |
|<span data-ttu-id="a6b98-124">您的組織中可將內容新增至審閱集的最大並行工作。</span><span class="sxs-lookup"><span data-stu-id="a6b98-124">Maximum concurrent jobs in your organization to add content to a review set.</span></span> <span data-ttu-id="a6b98-125">這些工作稱為 **將資料新增至審閱集** ，並顯示在 [ **工作** ] 索引標籤的案例中。</span><span class="sxs-lookup"><span data-stu-id="a6b98-125">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span>| <span data-ttu-id="a6b98-126">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-126">10 <sup>4</sup></span></span> |
|<span data-ttu-id="a6b98-127">將內容新增至每位使用者之審閱集的最大並行工作。</span><span class="sxs-lookup"><span data-stu-id="a6b98-127">Maximum concurrent jobs to add content to a review set per user.</span></span> <span data-ttu-id="a6b98-128">這些工作稱為 **將資料新增至審閱集** ，並顯示在 [ **工作** ] 索引標籤的案例中。</span><span class="sxs-lookup"><span data-stu-id="a6b98-128">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span> | <span data-ttu-id="a6b98-129">3 </span><span class="sxs-lookup"><span data-stu-id="a6b98-129">3</span></span> |
|||

## <a name="hold-limits"></a><span data-ttu-id="a6b98-130">保留限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-130">Hold limits</span></span>

<span data-ttu-id="a6b98-131">下表列出與高級 eDiscovery 案例相關聯的保留限制。</span><span class="sxs-lookup"><span data-stu-id="a6b98-131">The following table lists the limits for holds associated with an Advanced eDiscovery case.</span></span>

| <span data-ttu-id="a6b98-132">限制的描述</span><span class="sxs-lookup"><span data-stu-id="a6b98-132">Description of limit</span></span> | <span data-ttu-id="a6b98-133">限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-133">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6b98-134">單一案例保留中的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-134">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="a6b98-135">此限制包括使用者信箱的合併總數，以及與 Microsoft 365 群組、Microsoft 團隊和 Yammer 群組相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="a6b98-135">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span> <br/> |<span data-ttu-id="a6b98-136">1,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-136">1,000</span></span>  <br/> |
|<span data-ttu-id="a6b98-137">單一案例保留中的網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-137">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="a6b98-138">此限制包括商務網站、SharePoint 網站與 Microsoft 365 群組、Microsoft 團隊和 Yammer 群組相關聯的 OneDrive 總數。</span><span class="sxs-lookup"><span data-stu-id="a6b98-138">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="a6b98-139">100</span><span class="sxs-lookup"><span data-stu-id="a6b98-139">100</span></span>  <br/> |

## <a name="indexing-limits"></a><span data-ttu-id="a6b98-140">索引限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-140">Indexing limits</span></span>

<span data-ttu-id="a6b98-141">下表列出高級 eDiscovery 中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="a6b98-141">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

| <span data-ttu-id="a6b98-142">限制的描述</span><span class="sxs-lookup"><span data-stu-id="a6b98-142">Description of limit</span></span> | <span data-ttu-id="a6b98-143">限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-143">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6b98-144">從單一檔案解壓縮的字元數上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-144">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="a6b98-145">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-145">10 million<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="a6b98-146">單一檔案的大小上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-146">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="a6b98-147">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-147">100 MB<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="a6b98-148">檔中內嵌專案的最大深度。</span><span class="sxs-lookup"><span data-stu-id="a6b98-148">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="a6b98-149">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-149">25<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="a6b98-150">光學字元辨識 (OCR) 所處理的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-150">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="a6b98-151">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-151">24 MB<sup>1</sup></span></span> <br/> 
|<span data-ttu-id="a6b98-152">每天每個組織的索引工作數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-152">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="a6b98-153">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-153">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="a6b98-154">搜尋限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-154">Search limits</span></span>

<span data-ttu-id="a6b98-155">本節所述的限制與使用 [ **搜尋** ] 索引標籤上的 [搜尋] 工具收集案例的資料有關。</span><span class="sxs-lookup"><span data-stu-id="a6b98-155">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="a6b98-156">如需詳細資訊，請參閱 [在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="a6b98-156">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

| <span data-ttu-id="a6b98-157">限制的描述</span><span class="sxs-lookup"><span data-stu-id="a6b98-157">Description of limit</span></span> | <span data-ttu-id="a6b98-158">限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-158">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6b98-159">可在單一搜尋中搜尋的信箱或網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-159">Maximum number of mailboxes or sites that can be searched in a single search.</span></span> |<span data-ttu-id="a6b98-160">無限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-160">No limit</span></span>|
|<span data-ttu-id="a6b98-161">可以同時執行的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-161">Maximum number of searches that can run at the same time.</span></span> |<span data-ttu-id="a6b98-162">無限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-162">No limit</span></span> |
|<span data-ttu-id="a6b98-163">單一使用者可以同時開始的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-163">Maximum number of searches that a single user can start at the same time.</span></span> |<span data-ttu-id="a6b98-164">10 </span><span class="sxs-lookup"><span data-stu-id="a6b98-164">10</span></span> | 
|<span data-ttu-id="a6b98-165">搜尋查詢 (包含運算子和條件) 的最大字元數。</span><span class="sxs-lookup"><span data-stu-id="a6b98-165">Maximum number of characters for a search query (including operators and conditions).</span></span> |<span data-ttu-id="a6b98-166">10000 &nbsp; <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-166">10,000&nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="a6b98-167">首碼萬用字元的最小字母字元數目;例如，**一個 \* *_ 或 _* 集 \***。</span><span class="sxs-lookup"><span data-stu-id="a6b98-167">Minimum number of alpha characters for prefix wildcards; for example, \**one\**_ or _\* set\*\*\*.</span></span>|<span data-ttu-id="a6b98-168">3 </span><span class="sxs-lookup"><span data-stu-id="a6b98-168">3</span></span> |  
|<span data-ttu-id="a6b98-169">使用首碼萬用字元來搜尋確切的字詞，或是使用前置詞萬用字元及 **接近** 的布林運算子時，所傳回的最大變種。</span><span class="sxs-lookup"><span data-stu-id="a6b98-169">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span> |<span data-ttu-id="a6b98-170">10000 &nbsp; <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-170">10,000&nbsp;<sup>3</sup></span></span>|
|<span data-ttu-id="a6b98-171">搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-171">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="a6b98-172">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="a6b98-172">The newest items are displayed.</span></span> |<span data-ttu-id="a6b98-173">100</span><span class="sxs-lookup"><span data-stu-id="a6b98-173">100</span></span>|
|<span data-ttu-id="a6b98-174">搜尋時，預覽頁面上顯示的所有信箱中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-174">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>|<span data-ttu-id="a6b98-175">1,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-175">1,000</span></span>|
|<span data-ttu-id="a6b98-176">可針對搜尋結果預覽的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-176">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="a6b98-177">如果有超過1000個信箱包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前1000個信箱。</span><span class="sxs-lookup"><span data-stu-id="a6b98-177">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="a6b98-178">1,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-178">1,000</span></span>|
|<span data-ttu-id="a6b98-179">在 [預覽] 頁面上，針對搜尋顯示之商務網站 SharePoint 和 OneDrive 的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-179">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="a6b98-180">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="a6b98-180">The newest items are displayed.</span></span> |<span data-ttu-id="a6b98-181">200</span><span class="sxs-lookup"><span data-stu-id="a6b98-181">200</span></span>|
|<span data-ttu-id="a6b98-182">可用於預覽搜尋結果的商務網站 SharePoint 和 OneDrive 數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-182">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="a6b98-183">如果有超過200個網站包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前200網站。</span><span class="sxs-lookup"><span data-stu-id="a6b98-183">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>|<span data-ttu-id="a6b98-184">200</span><span class="sxs-lookup"><span data-stu-id="a6b98-184">200</span></span>|
|<span data-ttu-id="a6b98-185">搜尋時預覽頁面上顯示的每個公用資料夾信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-185">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span> |<span data-ttu-id="a6b98-186">100</span><span class="sxs-lookup"><span data-stu-id="a6b98-186">100</span></span>|
|<span data-ttu-id="a6b98-187">在 [預覽] 頁面上顯示的所有公用資料夾信箱專案中找到的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-187">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span> |<span data-ttu-id="a6b98-188">200</span><span class="sxs-lookup"><span data-stu-id="a6b98-188">200</span></span>|
|<span data-ttu-id="a6b98-189">可預覽搜尋結果的公用資料夾信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-189">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="a6b98-190">如果有超過500的公用資料夾信箱包含符合搜尋查詢的專案，則預覽中只可使用具有最多結果的前500個信箱。</span><span class="sxs-lookup"><span data-stu-id="a6b98-190">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="a6b98-191">500</span><span class="sxs-lookup"><span data-stu-id="a6b98-191">500</span></span>|
|||

## <a name="search-times"></a><span data-ttu-id="a6b98-192">搜尋時間</span><span class="sxs-lookup"><span data-stu-id="a6b98-192">Search times</span></span>

<span data-ttu-id="a6b98-193">Microsoft 會收集所有組織執行之搜尋的效能資訊。</span><span class="sxs-lookup"><span data-stu-id="a6b98-193">Microsoft collects performance information for searches run by all organizations.</span></span> <span data-ttu-id="a6b98-194">雖然搜尋查詢的複雜性可能會影響搜尋時間，會影響搜尋所需時間的最大因素是搜尋的信箱數量。</span><span class="sxs-lookup"><span data-stu-id="a6b98-194">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="a6b98-195">雖然 Microsoft 不會提供搜尋時間的服務等級協定，但下表會根據搜尋中包含的信箱數目，列出收集搜尋的平均搜尋時間。</span><span class="sxs-lookup"><span data-stu-id="a6b98-195">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for collection searches based on the number of mailboxes included in the search.</span></span>
  
  |<span data-ttu-id="a6b98-196">**信箱數目**</span><span class="sxs-lookup"><span data-stu-id="a6b98-196">**Number of mailboxes**</span></span>|<span data-ttu-id="a6b98-197">**平均搜尋時間**</span><span class="sxs-lookup"><span data-stu-id="a6b98-197">**Average search time**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="a6b98-198">100</span><span class="sxs-lookup"><span data-stu-id="a6b98-198">100</span></span>  <br/> |<span data-ttu-id="a6b98-199">30 秒</span><span class="sxs-lookup"><span data-stu-id="a6b98-199">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="a6b98-200">1,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-200">1,000</span></span>  <br/> |<span data-ttu-id="a6b98-201">45 秒</span><span class="sxs-lookup"><span data-stu-id="a6b98-201">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="a6b98-202">10,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-202">10,000</span></span>  <br/> |<span data-ttu-id="a6b98-203">4 分鐘</span><span class="sxs-lookup"><span data-stu-id="a6b98-203">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="a6b98-204">25,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-204">25,000</span></span>  <br/> |<span data-ttu-id="a6b98-205">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="a6b98-205">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="a6b98-206">50,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-206">50,000</span></span>  <br/> |<span data-ttu-id="a6b98-207">20 分鐘</span><span class="sxs-lookup"><span data-stu-id="a6b98-207">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="a6b98-208">100,000</span><span class="sxs-lookup"><span data-stu-id="a6b98-208">100,000</span></span>  <br/> |<span data-ttu-id="a6b98-209">25 分鐘</span><span class="sxs-lookup"><span data-stu-id="a6b98-209">25 minutes</span></span>  <br/> |
  |||

## <a name="viewer-limits"></a><span data-ttu-id="a6b98-210">檢視器限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-210">Viewer limits</span></span>

| <span data-ttu-id="a6b98-211">限制的描述</span><span class="sxs-lookup"><span data-stu-id="a6b98-211">Description of limit</span></span> | <span data-ttu-id="a6b98-212">限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-212">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6b98-213">可在原生檢視器中查看的 Excel 檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-213">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="a6b98-214">4 MB</span><span class="sxs-lookup"><span data-stu-id="a6b98-214">4 MB</span></span>  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a><span data-ttu-id="a6b98-215">匯出限制-最終匯出缺考核集</span><span class="sxs-lookup"><span data-stu-id="a6b98-215">Export limits - Final export out of Review Set</span></span>

<span data-ttu-id="a6b98-216">本節所述的限制與從審閱集匯出檔相關。</span><span class="sxs-lookup"><span data-stu-id="a6b98-216">The limits described in this section are related to exporting documents out of a review set.</span></span>

| <span data-ttu-id="a6b98-217">限制的描述</span><span class="sxs-lookup"><span data-stu-id="a6b98-217">Description of limit</span></span> | <span data-ttu-id="a6b98-218">限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-218">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6b98-219">單一匯出的大小上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-219">Maximum size of a single export.</span></span>|<span data-ttu-id="a6b98-220">3000000檔或 100 GB （以較少者為准）</span><span class="sxs-lookup"><span data-stu-id="a6b98-220">3 million documents or 100 GB, whichever is smaller</span></span>|
|<span data-ttu-id="a6b98-221">每個審閱集的併發匯出上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-221">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="a6b98-222">1</span><span class="sxs-lookup"><span data-stu-id="a6b98-222">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="a6b98-223">複查設定的下載限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-223">Review set download limits</span></span>

| <span data-ttu-id="a6b98-224">限制的描述</span><span class="sxs-lookup"><span data-stu-id="a6b98-224">Description of limit</span></span> | <span data-ttu-id="a6b98-225">限制</span><span class="sxs-lookup"><span data-stu-id="a6b98-225">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6b98-226">從審閱集下載的檔總大小或檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-226">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="a6b98-227">3 MB 或50檔 <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a6b98-227">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="a6b98-228"><sup>1</sup> 任何超出單一檔限制的專案會顯示為處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="a6b98-228"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span>
>
> <span data-ttu-id="a6b98-229"><sup>2</sup> 搜尋商務位置的 SharePoint 和 OneDrive 時，所搜尋之網站 URLs 中的字元會因此限制而計數。</span><span class="sxs-lookup"><span data-stu-id="a6b98-229"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span>
>
> <span data-ttu-id="a6b98-230"><sup>3</sup> ：非片語查詢 (關鍵字值，但不使用雙引號) 我們使用特殊的前置詞索引。</span><span class="sxs-lookup"><span data-stu-id="a6b98-230"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="a6b98-231">這會告訴我們檔中的字詞，但不會出現在檔中。</span><span class="sxs-lookup"><span data-stu-id="a6b98-231">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="a6b98-232">若要執行片語查詢 (關鍵字值使用雙引號) ，我們需要比較檔內的字詞中的文字的位置。</span><span class="sxs-lookup"><span data-stu-id="a6b98-232">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="a6b98-233">這表示我們無法使用關鍵字查詢的首碼索引。</span><span class="sxs-lookup"><span data-stu-id="a6b98-233">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="a6b98-234">在此情況下，我們會以內部首碼擴充的任何可能的字來內部展開查詢;例如， **time \* *_ 可以展開為 _*"time 或 timer OR time 或 timex or timeboxed or ..."**。</span><span class="sxs-lookup"><span data-stu-id="a6b98-234">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="a6b98-235">10000的限制是 word 可以擴充的變種數目上限，而不是符合查詢的檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-235">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="a6b98-236">非片語字詞沒有上限。</span><span class="sxs-lookup"><span data-stu-id="a6b98-236">There is no upper limit for non-phrase terms.</span></span>
>
> <span data-ttu-id="a6b98-237"><sup>4</sup> 在其他 eDiscovery 工具中匯出內容時，會共用此限制。</span><span class="sxs-lookup"><span data-stu-id="a6b98-237"><sup>4</sup> This limit is shared with exporting content in other eDiscovery tools.</span></span> <span data-ttu-id="a6b98-238">這表示在 [內容搜尋] 和 [核心 eDiscovery] 中的併發匯出 (，並將內容新增至「高級 eDiscovery) 中的審閱集，都是針對此限制套用。</span><span class="sxs-lookup"><span data-stu-id="a6b98-238">This means that concurrent exports in Content search and Core eDiscovery (and adding content to review sets in Advanced eDiscovery) are all applied against this limit.</span></span>
>
> <span data-ttu-id="a6b98-239"><sup>5</sup> 此限制適用于從審閱集下載選取的檔。</span><span class="sxs-lookup"><span data-stu-id="a6b98-239"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="a6b98-240">它不會套用到從審閱集匯出檔。</span><span class="sxs-lookup"><span data-stu-id="a6b98-240">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="a6b98-241">如需下載及匯出檔的詳細資訊，請參閱 [在高級 eDiscovery 中匯出案例資料](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="a6b98-241">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>
>
> <span data-ttu-id="a6b98-242">每個組織每天有<sup>6</sup>個索引限制。</span><span class="sxs-lookup"><span data-stu-id="a6b98-242"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="a6b98-243">例如，您可以在案例中的 [ **資料來源** ] 索引標籤上選取多個保管人，然後按一下 [ **更新索引** ]，避免為每個保管人建立個別的索引工作。</span><span class="sxs-lookup"><span data-stu-id="a6b98-243">As a workaround, you can select multiple custodians on the **Data sources** tab in a case and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> 
