---
title: 在 Microsoft 365 Defender 中處理進位搜尋查詢結果
description: 充分利用 Microsoft 365 Defender 中的進一步搜尋所返回的查詢結果
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、自訂偵測、架構、kusto、microsoft 365、Microsoft 威脅防護、視覺效果、圖表、篩選、向下切入
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932301"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="535c6-104">使用進位搜尋查詢結果</span><span class="sxs-lookup"><span data-stu-id="535c6-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="535c6-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="535c6-105">**Applies to:**</span></span>
- <span data-ttu-id="535c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="535c6-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="535c6-107">雖然您可以建構 [進位](advanced-hunting-overview.md) 的搜尋查詢來返回非常精確的資訊，您也可以使用查詢結果來取得進一步的深入見解，並調查特定活動和標記。</span><span class="sxs-lookup"><span data-stu-id="535c6-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="535c6-108">您可以對查詢結果採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="535c6-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="535c6-109">以表格或圖表查看結果</span><span class="sxs-lookup"><span data-stu-id="535c6-109">View results as a table or chart</span></span>
- <span data-ttu-id="535c6-110">匯出表格和圖表</span><span class="sxs-lookup"><span data-stu-id="535c6-110">Export tables and charts</span></span>
- <span data-ttu-id="535c6-111">向下切入至詳細的實體資訊</span><span class="sxs-lookup"><span data-stu-id="535c6-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="535c6-112">直接從結果調整查詢或篩選</span><span class="sxs-lookup"><span data-stu-id="535c6-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="535c6-113">以表格或圖表查看查詢結果</span><span class="sxs-lookup"><span data-stu-id="535c6-113">View query results as a table or chart</span></span>
<span data-ttu-id="535c6-114">根據預設，進位搜尋會以表格式資料顯示查詢結果。</span><span class="sxs-lookup"><span data-stu-id="535c6-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="535c6-115">您也可以顯示與圖表相同的資料。</span><span class="sxs-lookup"><span data-stu-id="535c6-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="535c6-116">進位搜尋支援下列視圖：</span><span class="sxs-lookup"><span data-stu-id="535c6-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="535c6-117">檢視類型</span><span class="sxs-lookup"><span data-stu-id="535c6-117">View type</span></span> | <span data-ttu-id="535c6-118">說明</span><span class="sxs-lookup"><span data-stu-id="535c6-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="535c6-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="535c6-119">**Table**</span></span> | <span data-ttu-id="535c6-120">以表格式格式顯示查詢結果</span><span class="sxs-lookup"><span data-stu-id="535c6-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="535c6-121">**直條圖**</span><span class="sxs-lookup"><span data-stu-id="535c6-121">**Column chart**</span></span> | <span data-ttu-id="535c6-122">將 X 軸上的一系列唯一專案轉成垂直軸，其高度代表另一個欄位的數值</span><span class="sxs-lookup"><span data-stu-id="535c6-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="535c6-123">**堆疊直條圖**</span><span class="sxs-lookup"><span data-stu-id="535c6-123">**Stacked column chart**</span></span> | <span data-ttu-id="535c6-124">將 X 軸上的一系列唯一專案轉成堆疊的垂直軸，其高度代表來自一或多個其他欄位的數值</span><span class="sxs-lookup"><span data-stu-id="535c6-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="535c6-125">**圓形圖**</span><span class="sxs-lookup"><span data-stu-id="535c6-125">**Pie chart**</span></span> | <span data-ttu-id="535c6-126">呈現代表唯一專案的區段圓形圖。</span><span class="sxs-lookup"><span data-stu-id="535c6-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="535c6-127">每個圓形圖的大小代表來自另一個欄位的數值。</span><span class="sxs-lookup"><span data-stu-id="535c6-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="535c6-128">**環圈圖**</span><span class="sxs-lookup"><span data-stu-id="535c6-128">**Donut chart**</span></span> | <span data-ttu-id="535c6-129">呈現代表唯一專案的分節弧線。</span><span class="sxs-lookup"><span data-stu-id="535c6-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="535c6-130">每個弧線的長度代表來自另一個欄位的數值。</span><span class="sxs-lookup"><span data-stu-id="535c6-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="535c6-131">**折線圖**</span><span class="sxs-lookup"><span data-stu-id="535c6-131">**Line chart**</span></span> | <span data-ttu-id="535c6-132">繪製一系列唯一專案的數值，並連接繪製的值</span><span class="sxs-lookup"><span data-stu-id="535c6-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="535c6-133">**散佈圖**</span><span class="sxs-lookup"><span data-stu-id="535c6-133">**Scatter chart**</span></span> | <span data-ttu-id="535c6-134">繪製一系列唯一專案的數值</span><span class="sxs-lookup"><span data-stu-id="535c6-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="535c6-135">**面積圖**</span><span class="sxs-lookup"><span data-stu-id="535c6-135">**Area chart**</span></span> | <span data-ttu-id="535c6-136">繪製一系列唯一專案的數值，並填滿繪製值下方的區段</span><span class="sxs-lookup"><span data-stu-id="535c6-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="535c6-137">建構有效圖表的查詢</span><span class="sxs-lookup"><span data-stu-id="535c6-137">Construct queries for effective charts</span></span>
<span data-ttu-id="535c6-138">當呈現圖表時，進位搜尋會自動識別感興趣的欄和要匯總的數值。</span><span class="sxs-lookup"><span data-stu-id="535c6-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="535c6-139">若要取得有意義的圖表，請建構查詢以視覺化方式返回您想要查看的特定值。</span><span class="sxs-lookup"><span data-stu-id="535c6-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="535c6-140">以下是一些範例查詢和產生的圖表。</span><span class="sxs-lookup"><span data-stu-id="535c6-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="535c6-141">按嚴重性顯示警示</span><span class="sxs-lookup"><span data-stu-id="535c6-141">Alerts by severity</span></span>
<span data-ttu-id="535c6-142">使用 `summarize` 運算子取得您想要繪製圖表之值的數值計數。</span><span class="sxs-lookup"><span data-stu-id="535c6-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="535c6-143">下列查詢使用 `summarize` 運算子來按嚴重性取得警示數目。</span><span class="sxs-lookup"><span data-stu-id="535c6-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="535c6-144">呈現結果時，直條圖會以個別的欄顯示每個嚴重性值：</span><span class="sxs-lookup"><span data-stu-id="535c6-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="535c6-145">![進一步搜尋查詢結果顯示為直條圖查詢結果的圖像，查詢結果會以嚴重性顯示為 ](../../media/advanced-hunting-column-chart.jpg)
 *直條圖*</span><span class="sxs-lookup"><span data-stu-id="535c6-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="535c6-146">根據作業系統警示嚴重性</span><span class="sxs-lookup"><span data-stu-id="535c6-146">Alert severity by operating system</span></span>
<span data-ttu-id="535c6-147">您也可以使用運算子 `summarize` 來準備多個欄位的值圖表結果。</span><span class="sxs-lookup"><span data-stu-id="535c6-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="535c6-148">例如，您可能會想要瞭解警示嚴重性如何分散在作業系統或作業系統 () 。</span><span class="sxs-lookup"><span data-stu-id="535c6-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="535c6-149">下列查詢使用運算子從資料表提取作業系統資訊，然後用來計算 `join` `DeviceInfo` `summarize` 資料行 `OSPlatform` 與資料行 `Severity` 中的值：</span><span class="sxs-lookup"><span data-stu-id="535c6-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="535c6-150">使用堆疊直條圖以視覺化方式呈現的結果最佳：</span><span class="sxs-lookup"><span data-stu-id="535c6-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="535c6-151">![以堆疊圖表顯示進位搜尋查詢結果的圖像，查詢結果顯示由作業系統和嚴重性顯示為堆疊 ](../../media/advanced-hunting-stacked-chart.jpg)
 *圖表的警示*</span><span class="sxs-lookup"><span data-stu-id="535c6-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="535c6-152">橫跨十大寄件者網域的網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="535c6-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="535c6-153">如果您要處理的值清單並非有限，可以使用運算子只繪製實例數 `Top` 最多的值圖表。</span><span class="sxs-lookup"><span data-stu-id="535c6-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="535c6-154">例如，若要取得網路釣魚電子郵件數最多的十大寄件者網域，請使用下列查詢：</span><span class="sxs-lookup"><span data-stu-id="535c6-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="535c6-155">使用圓形圖視圖，有效顯示上方網域的分佈：</span><span class="sxs-lookup"><span data-stu-id="535c6-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="535c6-156">![進位搜尋查詢結果的影像會顯示為圓形圖圓形圖，顯示跨頂端寄件者網域的網路釣魚 ](../../media/advanced-hunting-pie-chart.jpg)
 *電子郵件分佈*</span><span class="sxs-lookup"><span data-stu-id="535c6-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="535c6-157">一段時間的檔案活動</span><span class="sxs-lookup"><span data-stu-id="535c6-157">File activities over time</span></span>
<span data-ttu-id="535c6-158">您可以將 `summarize` 運算子與 `bin()` 函數一起使用，檢查一段時間是否與特定標記有關的事件。</span><span class="sxs-lookup"><span data-stu-id="535c6-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="535c6-159">以下查詢會以時間間隔 30 分鐘計算涉及檔案的事件，以顯示與檔案相關的 `invoice.doc` 活動尖峰：</span><span class="sxs-lookup"><span data-stu-id="535c6-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="535c6-160">下方的線條圖會清楚突顯包含更多涉及活動的時段 `invoice.doc` ：</span><span class="sxs-lookup"><span data-stu-id="535c6-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="535c6-161">![進位搜尋查詢結果的影像會顯示為線條圖的線條圖，顯示一段時間與檔案 ](../../media/advanced-hunting-line-chart.jpg)
 *有關之事件的數量*</span><span class="sxs-lookup"><span data-stu-id="535c6-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="535c6-162">匯出表格和圖表</span><span class="sxs-lookup"><span data-stu-id="535c6-162">Export tables and charts</span></span>
<span data-ttu-id="535c6-163">執行查詢之後，選取 **匯出以** 將結果儲存到本地檔案。</span><span class="sxs-lookup"><span data-stu-id="535c6-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="535c6-164">您所選擇的視圖會決定匯出結果的方式：</span><span class="sxs-lookup"><span data-stu-id="535c6-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="535c6-165">**表格視圖** - 查詢結果會以清單方式匯出為 Microsoft Excel 活頁簿</span><span class="sxs-lookup"><span data-stu-id="535c6-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="535c6-166">**任何圖表** — 查詢結果會匯出為所呈現圖表的 JPEG 影像</span><span class="sxs-lookup"><span data-stu-id="535c6-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="535c6-167">從查詢結果向下切入</span><span class="sxs-lookup"><span data-stu-id="535c6-167">Drill down from query results</span></span>
<span data-ttu-id="535c6-168">若要快速檢查查詢結果中的記錄，請選取對應的資料列以開啟檢查 **記錄** 面板。</span><span class="sxs-lookup"><span data-stu-id="535c6-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="535c6-169">面板會依據選取的記錄提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="535c6-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="535c6-170">**資產** — 在記錄中 (信箱、裝置和使用者之) 摘要視圖，豐富的可用資訊，例如風險與曝光層級</span><span class="sxs-lookup"><span data-stu-id="535c6-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="535c6-171">**程式樹** — 產生包含程式資訊的記錄，並且使用可用的內容相關資訊豐富;一般而言，會返回更多資料行的查詢可能會導致更豐富的程式樹狀結構。</span><span class="sxs-lookup"><span data-stu-id="535c6-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="535c6-172">**所有詳細** 資料 — 記錄中資料行的所有值</span><span class="sxs-lookup"><span data-stu-id="535c6-172">**All details** — all the values from the columns in the record</span></span>  

![選取的記錄影像，以及用於檢查記錄的面板](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="535c6-174">若要在查詢結果中查看特定實體的詳細資訊 ，例如電腦、檔案、使用者、IP 位址或 URL，請選取實體識別碼以開啟該實體的詳細設定檔頁面面。</span><span class="sxs-lookup"><span data-stu-id="535c6-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="535c6-175">從結果調整您的查詢</span><span class="sxs-lookup"><span data-stu-id="535c6-175">Tweak your queries from the results</span></span>
<span data-ttu-id="535c6-176">以滑鼠右鍵按一下結果集中的值，以快速強化您的查詢。</span><span class="sxs-lookup"><span data-stu-id="535c6-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="535c6-177">您可以使用下列選項來執行這些動作：</span><span class="sxs-lookup"><span data-stu-id="535c6-177">You can use the options to:</span></span>

- <span data-ttu-id="535c6-178">明確尋找選取的值 (`==`)</span><span class="sxs-lookup"><span data-stu-id="535c6-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="535c6-179">從查詢排除選取的值 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="535c6-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="535c6-180">取得更多可將值新增至查詢的進階運算子，例如 `contains`、`starts with` 和 `ends with`</span><span class="sxs-lookup"><span data-stu-id="535c6-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![進位搜尋結果集的影像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="535c6-182">篩選查詢結果</span><span class="sxs-lookup"><span data-stu-id="535c6-182">Filter the query results</span></span>
<span data-ttu-id="535c6-183">顯示在右側的篩選器可提供結果集的摘要。</span><span class="sxs-lookup"><span data-stu-id="535c6-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="535c6-184">每個資料行都有各自的區段，列出針對該資料行找到的獨特值和執行個體數量。</span><span class="sxs-lookup"><span data-stu-id="535c6-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="535c6-185">針對您想要包含或排除的值選取一或兩個按鈕，然後選取執行查詢，以 `+` `-` **精簡查詢**。</span><span class="sxs-lookup"><span data-stu-id="535c6-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![進階搜捕篩選的影像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="535c6-187">一旦套用篩選來修改查詢，然後執行查詢，結果就會相應更新。</span><span class="sxs-lookup"><span data-stu-id="535c6-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="535c6-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="535c6-188">Related topics</span></span>
- [<span data-ttu-id="535c6-189">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="535c6-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="535c6-190">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="535c6-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="535c6-191">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="535c6-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="535c6-192">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="535c6-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="535c6-193">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="535c6-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="535c6-194">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="535c6-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="535c6-195">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="535c6-195">Custom detections overview</span></span>](custom-detections-overview.md)
