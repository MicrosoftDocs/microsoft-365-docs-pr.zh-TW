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
description: 深入瞭解 Microsoft 365 中 Advanced eDiscovery 解決方案的實際案例限制、索引限制和搜尋限制。
ms.openlocfilehash: 335e40c6918fc33acc12082546b98f28c319c814
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244573"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="abef3-103">進階電子文件探索的限制</span><span class="sxs-lookup"><span data-stu-id="abef3-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="abef3-104">本文說明 Microsoft 365 中 Advanced eDiscovery 解決方案的限制。</span><span class="sxs-lookup"><span data-stu-id="abef3-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="abef3-105">案例與複查集限制</span><span class="sxs-lookup"><span data-stu-id="abef3-105">Case and review set limits</span></span>

<span data-ttu-id="abef3-106">下表列出 Advanced eDiscovery 中案例和審閱集的限制。</span><span class="sxs-lookup"><span data-stu-id="abef3-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

| <span data-ttu-id="abef3-107">限制的描述</span><span class="sxs-lookup"><span data-stu-id="abef3-107">Description of limit</span></span> | <span data-ttu-id="abef3-108">限制</span><span class="sxs-lookup"><span data-stu-id="abef3-108">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="abef3-109">在案例) 中，所有審閱集可以新增到案例中的檔總數目 (。</span><span class="sxs-lookup"><span data-stu-id="abef3-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="abef3-110">3 百萬</span><span class="sxs-lookup"><span data-stu-id="abef3-110">3 million</span></span> <br/> |
|<span data-ttu-id="abef3-111">每個負載集的檔案大小總計。</span><span class="sxs-lookup"><span data-stu-id="abef3-111">Total file size per load set.</span></span> <span data-ttu-id="abef3-112">這包括將非 Office 365 載入至審閱集。</span><span class="sxs-lookup"><span data-stu-id="abef3-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="abef3-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="abef3-113">300 GB</span></span> <br/> |
|<span data-ttu-id="abef3-114">每天組織中的所有審閱集合中載入的資料總量。</span><span class="sxs-lookup"><span data-stu-id="abef3-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="abef3-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="abef3-115">2 TB</span></span> <br/> |
|<span data-ttu-id="abef3-116">每個案例的負載集數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-116">Maximum number of load sets per case.</span></span>  <br/> |<span data-ttu-id="abef3-117">200</span><span class="sxs-lookup"><span data-stu-id="abef3-117">200</span></span> <br/> |
|<span data-ttu-id="abef3-118">每個案例的審閱集數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="abef3-119">共</span><span class="sxs-lookup"><span data-stu-id="abef3-119">20</span></span> <br/> |
|<span data-ttu-id="abef3-120">每個案例的標記群組數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="abef3-121">1000</span><span class="sxs-lookup"><span data-stu-id="abef3-121">1000</span></span> <br/> |
|<span data-ttu-id="abef3-122">每個案例的標記數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="abef3-123">1000</span><span class="sxs-lookup"><span data-stu-id="abef3-123">1000</span></span> <br/> |
|<span data-ttu-id="abef3-124">您的組織中可將內容新增至審閱集的最大並行工作。</span><span class="sxs-lookup"><span data-stu-id="abef3-124">Maximum concurrent jobs in your organization to add content to a review set.</span></span> <span data-ttu-id="abef3-125">這些工作稱為 **將資料新增至審閱集** ，並顯示在 [ **工作** ] 索引標籤的案例中。</span><span class="sxs-lookup"><span data-stu-id="abef3-125">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span>| <span data-ttu-id="abef3-126">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-126">10 <sup>4</sup></span></span> |
|<span data-ttu-id="abef3-127">將內容新增至每位使用者之審閱集的最大並行工作。</span><span class="sxs-lookup"><span data-stu-id="abef3-127">Maximum concurrent jobs to add content to a review set per user.</span></span> <span data-ttu-id="abef3-128">這些工作稱為 **將資料新增至審閱集** ，並顯示在 [ **工作** ] 索引標籤的案例中。</span><span class="sxs-lookup"><span data-stu-id="abef3-128">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span> | <span data-ttu-id="abef3-129">個</span><span class="sxs-lookup"><span data-stu-id="abef3-129">3</span></span> |
|||

## <a name="hold-limits"></a><span data-ttu-id="abef3-130">保留限制</span><span class="sxs-lookup"><span data-stu-id="abef3-130">Hold limits</span></span>

<span data-ttu-id="abef3-131">下表列出與 Advanced eDiscovery 案例相關聯的保留限制。</span><span class="sxs-lookup"><span data-stu-id="abef3-131">The following table lists the limits for holds associated with an Advanced eDiscovery case.</span></span>

| <span data-ttu-id="abef3-132">限制的描述</span><span class="sxs-lookup"><span data-stu-id="abef3-132">Description of limit</span></span> | <span data-ttu-id="abef3-133">限制</span><span class="sxs-lookup"><span data-stu-id="abef3-133">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="abef3-134">單一案例保留中的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-134">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="abef3-135">此限制包括使用者信箱的組合總數，以及與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="abef3-135">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span> <br/> |<span data-ttu-id="abef3-136">1,000</span><span class="sxs-lookup"><span data-stu-id="abef3-136">1,000</span></span>  <br/> |
|<span data-ttu-id="abef3-137">單一案例保留中的網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-137">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="abef3-138">此限制包括與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的商務用 OneDrive 網站、SharePoint 網站和網站的綜合總數。</span><span class="sxs-lookup"><span data-stu-id="abef3-138">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="abef3-139">100</span><span class="sxs-lookup"><span data-stu-id="abef3-139">100</span></span>  <br/> |

## <a name="indexing-limits"></a><span data-ttu-id="abef3-140">索引限制</span><span class="sxs-lookup"><span data-stu-id="abef3-140">Indexing limits</span></span>

<span data-ttu-id="abef3-141">下表列出 Advanced eDiscovery 中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="abef3-141">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

| <span data-ttu-id="abef3-142">限制的描述</span><span class="sxs-lookup"><span data-stu-id="abef3-142">Description of limit</span></span> | <span data-ttu-id="abef3-143">限制</span><span class="sxs-lookup"><span data-stu-id="abef3-143">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="abef3-144">從單一檔案解壓縮的字元數上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-144">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="abef3-145">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-145">10 million<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="abef3-146">單一檔案的大小上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-146">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="abef3-147">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-147">100 MB<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="abef3-148">檔中內嵌專案的最大深度。</span><span class="sxs-lookup"><span data-stu-id="abef3-148">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="abef3-149">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-149">25<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="abef3-150">光學字元辨識 (OCR) 所處理的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-150">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="abef3-151">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-151">24 MB<sup>1</sup></span></span> <br/> 
|<span data-ttu-id="abef3-152">每天每個組織的索引工作數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-152">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="abef3-153">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-153">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="abef3-154">搜尋限制</span><span class="sxs-lookup"><span data-stu-id="abef3-154">Search limits</span></span>

<span data-ttu-id="abef3-155">本節所述的限制與使用 [ **搜尋** ] 索引標籤上的 [搜尋] 工具收集案例的資料有關。</span><span class="sxs-lookup"><span data-stu-id="abef3-155">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="abef3-156">如需詳細資訊，請參閱[在 Advanced eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="abef3-156">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

| <span data-ttu-id="abef3-157">限制的描述</span><span class="sxs-lookup"><span data-stu-id="abef3-157">Description of limit</span></span> | <span data-ttu-id="abef3-158">限制</span><span class="sxs-lookup"><span data-stu-id="abef3-158">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="abef3-159">可在單一搜尋中搜尋的信箱或網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-159">Maximum number of mailboxes or sites that can be searched in a single search.</span></span> |<span data-ttu-id="abef3-160">無限制</span><span class="sxs-lookup"><span data-stu-id="abef3-160">No limit</span></span>|
|<span data-ttu-id="abef3-161">可以同時執行的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-161">Maximum number of searches that can run at the same time.</span></span> |<span data-ttu-id="abef3-162">無限制</span><span class="sxs-lookup"><span data-stu-id="abef3-162">No limit</span></span> |
|<span data-ttu-id="abef3-163">單一使用者可以同時開始的搜尋數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-163">Maximum number of searches that a single user can start at the same time.</span></span> |<span data-ttu-id="abef3-164">10 </span><span class="sxs-lookup"><span data-stu-id="abef3-164">10</span></span> | 
|<span data-ttu-id="abef3-165">搜尋查詢 (包含運算子和條件) 的最大字元數。</span><span class="sxs-lookup"><span data-stu-id="abef3-165">Maximum number of characters for a search query (including operators and conditions).</span></span> |<span data-ttu-id="abef3-166">10000 &nbsp; <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-166">10,000 &nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="abef3-167">SharePoint 和商務用 OneDrive 網站的搜尋查詢的最大字元數 (包括運算子和條件) 。</span><span class="sxs-lookup"><span data-stu-id="abef3-167">Maximum number of characters for a search query for SharePoint and OneDrive for Business sites (including operators and conditions).</span></span> |<span data-ttu-id="abef3-168">10,000</span><span class="sxs-lookup"><span data-stu-id="abef3-168">10,000</span></span><br><span data-ttu-id="abef3-169">4000，使用萬用字元 &nbsp; <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-169">4,000 with Wildcards&nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="abef3-170">首碼萬用字元的最小字母字元數目;例如，**一個 \* *_ 或 _* 集 \***。</span><span class="sxs-lookup"><span data-stu-id="abef3-170">Minimum number of alpha characters for prefix wildcards; for example, \**one\**_ or _\* set\*\*\*.</span></span>|<span data-ttu-id="abef3-171">個</span><span class="sxs-lookup"><span data-stu-id="abef3-171">3</span></span> |  
|<span data-ttu-id="abef3-172">使用首碼萬用字元來搜尋確切的字詞，或是使用前置詞萬用字元及 **接近** 的布林運算子時，所傳回的最大變種。</span><span class="sxs-lookup"><span data-stu-id="abef3-172">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span> |<span data-ttu-id="abef3-173">10000 &nbsp; <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-173">10,000&nbsp;<sup>3</sup></span></span>|
|<span data-ttu-id="abef3-174">搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-174">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="abef3-175">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="abef3-175">The newest items are displayed.</span></span> |<span data-ttu-id="abef3-176">100</span><span class="sxs-lookup"><span data-stu-id="abef3-176">100</span></span>|
|<span data-ttu-id="abef3-177">搜尋時，預覽頁面上顯示的所有信箱中的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-177">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>|<span data-ttu-id="abef3-178">1,000</span><span class="sxs-lookup"><span data-stu-id="abef3-178">1,000</span></span>|
|<span data-ttu-id="abef3-179">可針對搜尋結果預覽的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-179">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="abef3-180">如果有超過1000個信箱包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前1000個信箱。</span><span class="sxs-lookup"><span data-stu-id="abef3-180">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="abef3-181">1,000</span><span class="sxs-lookup"><span data-stu-id="abef3-181">1,000</span></span>|
|<span data-ttu-id="abef3-182">在 [預覽] 頁面上搜尋的 SharePoint 和商務用 OneDrive 網站中顯示的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-182">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="abef3-183">隨即顯示最新的專案。</span><span class="sxs-lookup"><span data-stu-id="abef3-183">The newest items are displayed.</span></span> |<span data-ttu-id="abef3-184">200</span><span class="sxs-lookup"><span data-stu-id="abef3-184">200</span></span>|
|<span data-ttu-id="abef3-185">可預覽搜尋結果的 SharePoint 和商務用 OneDrive 網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-185">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="abef3-186">如果有超過200個網站包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前200網站。</span><span class="sxs-lookup"><span data-stu-id="abef3-186">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>|<span data-ttu-id="abef3-187">200</span><span class="sxs-lookup"><span data-stu-id="abef3-187">200</span></span>|
|<span data-ttu-id="abef3-188">搜尋時預覽頁面上顯示的每個公用資料夾信箱的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-188">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span> |<span data-ttu-id="abef3-189">100</span><span class="sxs-lookup"><span data-stu-id="abef3-189">100</span></span>|
|<span data-ttu-id="abef3-190">在 [預覽] 頁面上顯示的所有公用資料夾信箱專案中找到的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-190">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span> |<span data-ttu-id="abef3-191">200</span><span class="sxs-lookup"><span data-stu-id="abef3-191">200</span></span>|
|<span data-ttu-id="abef3-192">可預覽搜尋結果的公用資料夾信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-192">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="abef3-193">如果有超過500的公用資料夾信箱包含符合搜尋查詢的專案，則預覽中只可使用具有最多結果的前500個信箱。</span><span class="sxs-lookup"><span data-stu-id="abef3-193">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="abef3-194">500</span><span class="sxs-lookup"><span data-stu-id="abef3-194">500</span></span>|
|||

## <a name="search-times"></a><span data-ttu-id="abef3-195">搜尋時間</span><span class="sxs-lookup"><span data-stu-id="abef3-195">Search times</span></span>

<span data-ttu-id="abef3-196">Microsoft 會收集所有組織執行之搜尋的效能資訊。</span><span class="sxs-lookup"><span data-stu-id="abef3-196">Microsoft collects performance information for searches run by all organizations.</span></span> <span data-ttu-id="abef3-197">雖然搜尋查詢的複雜性可能會影響搜尋時間，會影響搜尋所需時間的最大因素是搜尋的信箱數量。</span><span class="sxs-lookup"><span data-stu-id="abef3-197">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="abef3-198">雖然 Microsoft 不會提供搜尋時間的服務等級協定，但下表會根據搜尋中包含的信箱數目，列出收集搜尋的平均搜尋時間。</span><span class="sxs-lookup"><span data-stu-id="abef3-198">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for collection searches based on the number of mailboxes included in the search.</span></span>
  
  | <span data-ttu-id="abef3-199">信箱數目</span><span class="sxs-lookup"><span data-stu-id="abef3-199">Number of mailboxes</span></span> | <span data-ttu-id="abef3-200">平均搜尋時間</span><span class="sxs-lookup"><span data-stu-id="abef3-200">Average search time</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="abef3-201">100</span><span class="sxs-lookup"><span data-stu-id="abef3-201">100</span></span>  <br/> |<span data-ttu-id="abef3-202">30 秒</span><span class="sxs-lookup"><span data-stu-id="abef3-202">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="abef3-203">1,000</span><span class="sxs-lookup"><span data-stu-id="abef3-203">1,000</span></span>  <br/> |<span data-ttu-id="abef3-204">45 秒</span><span class="sxs-lookup"><span data-stu-id="abef3-204">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="abef3-205">10,000</span><span class="sxs-lookup"><span data-stu-id="abef3-205">10,000</span></span>  <br/> |<span data-ttu-id="abef3-206">4 分鐘</span><span class="sxs-lookup"><span data-stu-id="abef3-206">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="abef3-207">25,000</span><span class="sxs-lookup"><span data-stu-id="abef3-207">25,000</span></span>  <br/> |<span data-ttu-id="abef3-208">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="abef3-208">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="abef3-209">50,000</span><span class="sxs-lookup"><span data-stu-id="abef3-209">50,000</span></span>  <br/> |<span data-ttu-id="abef3-210">20 分鐘</span><span class="sxs-lookup"><span data-stu-id="abef3-210">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="abef3-211">100,000</span><span class="sxs-lookup"><span data-stu-id="abef3-211">100,000</span></span>  <br/> |<span data-ttu-id="abef3-212">25 分鐘</span><span class="sxs-lookup"><span data-stu-id="abef3-212">25 minutes</span></span>  <br/> |
  |||

## <a name="viewer-limits"></a><span data-ttu-id="abef3-213">檢視器限制</span><span class="sxs-lookup"><span data-stu-id="abef3-213">Viewer limits</span></span>

| <span data-ttu-id="abef3-214">限制的描述</span><span class="sxs-lookup"><span data-stu-id="abef3-214">Description of limit</span></span> | <span data-ttu-id="abef3-215">限制</span><span class="sxs-lookup"><span data-stu-id="abef3-215">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="abef3-216">可在原生檢視器中查看的 Excel 檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-216">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="abef3-217">4 MB</span><span class="sxs-lookup"><span data-stu-id="abef3-217">4 MB</span></span>  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a><span data-ttu-id="abef3-218">匯出限制-最終匯出缺考核集</span><span class="sxs-lookup"><span data-stu-id="abef3-218">Export limits - Final export out of Review Set</span></span>

<span data-ttu-id="abef3-219">本節所述的限制與從審閱集匯出檔相關。</span><span class="sxs-lookup"><span data-stu-id="abef3-219">The limits described in this section are related to exporting documents out of a review set.</span></span>

| <span data-ttu-id="abef3-220">限制的描述</span><span class="sxs-lookup"><span data-stu-id="abef3-220">Description of limit</span></span> | <span data-ttu-id="abef3-221">限制</span><span class="sxs-lookup"><span data-stu-id="abef3-221">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="abef3-222">單一匯出的大小上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-222">Maximum size of a single export.</span></span>|<span data-ttu-id="abef3-223">5000000檔或 500 GB （以較少者為准）</span><span class="sxs-lookup"><span data-stu-id="abef3-223">5 million documents or 500 GB, whichever is smaller</span></span>|
|<span data-ttu-id="abef3-224">每個審閱集的併發匯出上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-224">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="abef3-225">1</span><span class="sxs-lookup"><span data-stu-id="abef3-225">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="abef3-226">複查設定的下載限制</span><span class="sxs-lookup"><span data-stu-id="abef3-226">Review set download limits</span></span>

| <span data-ttu-id="abef3-227">限制的描述</span><span class="sxs-lookup"><span data-stu-id="abef3-227">Description of limit</span></span> | <span data-ttu-id="abef3-228">限制</span><span class="sxs-lookup"><span data-stu-id="abef3-228">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="abef3-229">從審閱集下載的檔總大小或檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-229">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="abef3-230">3 MB 或50檔 <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="abef3-230">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="abef3-231"><sup>1</sup> 任何超出單一檔限制的專案會顯示為處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="abef3-231"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span>
>
> <span data-ttu-id="abef3-232"><sup>2</sup>搜尋 SharePoint 和商務用 OneDrive 位置時，搜尋的網站 URLs 中的字元會根據此限制計算。</span><span class="sxs-lookup"><span data-stu-id="abef3-232"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span> <span data-ttu-id="abef3-233">字元總數包括：</span><span class="sxs-lookup"><span data-stu-id="abef3-233">The total number of characters consists of:</span></span><br>
> - <span data-ttu-id="abef3-234">[使用者] 和 [篩選] 欄位中的所有字元。</span><span class="sxs-lookup"><span data-stu-id="abef3-234">All characters in both the Users and Filters fields.</span></span>
> - <span data-ttu-id="abef3-235">適用于使用者的所有搜尋許可權篩選。</span><span class="sxs-lookup"><span data-stu-id="abef3-235">All search permissions filters that apply to the user.</span></span>
> - <span data-ttu-id="abef3-236">搜尋中任何位置屬性的字元;這包括 ExchangeLocation、PublicFolderLocation、SharPointLocation、ExchangeLocationExclusion、PublicFolderLocationExclusion、SharePointLocationExclusion、OneDriveLocationExclusion。</span><span class="sxs-lookup"><span data-stu-id="abef3-236">The characters from any location properties in the search; this includes ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion.</span></span>
>   <span data-ttu-id="abef3-237">例如，包含搜尋中的所有 SharePoint 網站和 OneDrive 帳戶會算作六個字元，因為會同時顯示 SharePointLocation 和 OneDriveLocation 欄位的 "all" 一詞。</span><span class="sxs-lookup"><span data-stu-id="abef3-237">For example, including all SharePoint sites and OneDrive accounts in the search will count as six characters, as the word "ALL" will appear for both the SharePointLocation and OneDriveLocation field.</span></span>
>
> <span data-ttu-id="abef3-238"><sup>3</sup> ：非片語查詢 (關鍵字值，但不使用雙引號) 我們使用特殊的前置詞索引。</span><span class="sxs-lookup"><span data-stu-id="abef3-238"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="abef3-239">這會告訴我們檔中的字詞，但不會出現在檔中。</span><span class="sxs-lookup"><span data-stu-id="abef3-239">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="abef3-240">若要執行片語查詢 (關鍵字值使用雙引號) ，我們需要比較檔內的字詞中的文字的位置。</span><span class="sxs-lookup"><span data-stu-id="abef3-240">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="abef3-241">這表示我們無法使用關鍵字查詢的首碼索引。</span><span class="sxs-lookup"><span data-stu-id="abef3-241">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="abef3-242">在此情況下，我們會以內部首碼擴充的任何可能的字來內部展開查詢;例如， **time \* *_ 可以展開為 _*"time 或 timer OR time 或 timex or timeboxed or ..."**。</span><span class="sxs-lookup"><span data-stu-id="abef3-242">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="abef3-243">10000的限制是 word 可以擴充的變種數目上限，而不是符合查詢的檔數目上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-243">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="abef3-244">非片語字詞沒有上限。</span><span class="sxs-lookup"><span data-stu-id="abef3-244">There is no upper limit for non-phrase terms.</span></span>
>
> <span data-ttu-id="abef3-245"><sup>4</sup> 在其他 eDiscovery 工具中匯出內容時，會共用此限制。</span><span class="sxs-lookup"><span data-stu-id="abef3-245"><sup>4</sup> This limit is shared with exporting content in other eDiscovery tools.</span></span> <span data-ttu-id="abef3-246">這表示內容搜尋與核心 eDiscovery (中的併發匯出及新增內容至 Advanced eDiscovery) 中的審閱集，都是針對此限制套用。</span><span class="sxs-lookup"><span data-stu-id="abef3-246">This means that concurrent exports in Content search and Core eDiscovery (and adding content to review sets in Advanced eDiscovery) are all applied against this limit.</span></span>
>
> <span data-ttu-id="abef3-247"><sup>5</sup> 此限制適用于從審閱集下載選取的檔。</span><span class="sxs-lookup"><span data-stu-id="abef3-247"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="abef3-248">它不會套用到從審閱集匯出檔。</span><span class="sxs-lookup"><span data-stu-id="abef3-248">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="abef3-249">如需下載及匯出檔的詳細資訊，請參閱[Export case data in Advanced eDiscovery](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="abef3-249">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>
>
> <span data-ttu-id="abef3-250">每個組織每天有<sup>6</sup>個索引限制。</span><span class="sxs-lookup"><span data-stu-id="abef3-250"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="abef3-251">例如，您可以在案例中的 [ **資料來源** ] 索引標籤上選取多個保管人，然後按一下 [ **更新索引** ]，避免為每個保管人建立個別的索引工作。</span><span class="sxs-lookup"><span data-stu-id="abef3-251">As a workaround, you can select multiple custodians on the **Data sources** tab in a case and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> 
