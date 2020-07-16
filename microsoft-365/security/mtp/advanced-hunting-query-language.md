---
title: 了解 Microsoft 威脅防護中的進階搜捕查詢語言
description: 建立您的第一個威脅搜捕查詢，並了解常用的運算子和進階搜捕查詢語言的其他概念
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，語言，學習，第一個查詢，遙測，事件，遙測，自訂偵測，架構，kusto，運算子，資料類型，powershell 下載，查詢範例
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 26b376fe3e804a3ebaa478e484807bea4c33d38b
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049689"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="8f2bc-104">了解進階搜捕查詢語言</span><span class="sxs-lookup"><span data-stu-id="8f2bc-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="8f2bc-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8f2bc-105">**Applies to:**</span></span>
- <span data-ttu-id="8f2bc-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="8f2bc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8f2bc-107">進階搜捕是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="8f2bc-108">您可以使用 Kusto 語法和運算子來建立查詢，以在特別為進階搜捕而建構的[結構描述](advanced-hunting-schema-tables.md)中尋找的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="8f2bc-109">若要深入了解這些概念，請執行您的第一個查詢。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="8f2bc-110">嘗試您的第一個查詢</span><span class="sxs-lookup"><span data-stu-id="8f2bc-110">Try your first query</span></span>

<span data-ttu-id="8f2bc-111">在 Microsoft 365 的 [安全性中心] 中，移至**搜尋**以執行第一個查詢。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="8f2bc-112">請使用下列範例：</span><span class="sxs-lookup"><span data-stu-id="8f2bc-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="8f2bc-113">這是它在進階搜捕中看起來的樣子。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft 威脅防護高級搜尋查詢的影像](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="8f2bc-115">描述查詢，並指定要搜尋的表格</span><span class="sxs-lookup"><span data-stu-id="8f2bc-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="8f2bc-116">已將簡短批註新增至查詢的開頭，以描述其用途。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="8f2bc-117">這可協助您稍後決定要儲存查詢，並與組織中的其他人共用。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="8f2bc-118">查詢本身通常會以資料表名稱開頭，後面接著管道 (`|`) 開始的一系列元素。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="8f2bc-119">在此範例中，我們會從建立兩個表格的同盟開始，並 `DeviceProcessEvents` `DeviceNetworkEvents` 視需要新增管線元素。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="8f2bc-120">設定時間範圍</span><span class="sxs-lookup"><span data-stu-id="8f2bc-120">Set the time range</span></span>
<span data-ttu-id="8f2bc-121">第一個輸送的元素是一種範圍設定為前七天的時間篩選器。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="8f2bc-122">盡可能讓時間範圍越小越好，以確保查詢能順利執行、傳回可管理的結果，且不會逾時。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="8f2bc-123">檢查特定進程</span><span class="sxs-lookup"><span data-stu-id="8f2bc-123">Check specific processes</span></span>
<span data-ttu-id="8f2bc-124">時間範圍後緊接著搜尋代表 PowerShell 應用程式的處理常式檔案名。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="8f2bc-125">搜尋特定的命令字串</span><span class="sxs-lookup"><span data-stu-id="8f2bc-125">Search for specific command strings</span></span>
<span data-ttu-id="8f2bc-126">之後，查詢會在命令列中尋找通常用來透過 PowerShell 下載檔案的字串。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="8f2bc-127">自訂結果欄及長度</span><span class="sxs-lookup"><span data-stu-id="8f2bc-127">Customize result columns and length</span></span> 
<span data-ttu-id="8f2bc-128">現在您的查詢已清楚識別出您要尋找的資料，您可以新增元素來定義結果。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="8f2bc-129">`project`會傳回特定的欄，並 `top` 限制結果的數目。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="8f2bc-130">這些運算子可協助確保結果具有適當的格式，且易於處理。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="8f2bc-131">按一下 [執行查詢]\*\*\*\* 以查看結果。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="8f2bc-132">選取查詢編輯器右上角的展開圖示，以著重于搜尋查詢和結果。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高級搜尋查詢編輯器中的展開控制項影像](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="8f2bc-134">您可以以圖表形式查看查詢結果，並快速調整篩選。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="8f2bc-135">如需相關指導，請[參閱使用查詢結果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="8f2bc-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="8f2bc-136">了解適用於進階搜捕的一般查詢運算子</span><span class="sxs-lookup"><span data-stu-id="8f2bc-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="8f2bc-137">您已執行了第一個查詢，並對其組成元素有一點了解了，現在可以開始追蹤一些基本概念。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="8f2bc-138">進階搜捕所使用的 Kusto 查詢語言支援一系列運算子，包括下列常見運算子。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="8f2bc-139">運算子</span><span class="sxs-lookup"><span data-stu-id="8f2bc-139">Operator</span></span> | <span data-ttu-id="8f2bc-140">描述及用法</span><span class="sxs-lookup"><span data-stu-id="8f2bc-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="8f2bc-141">將資料表篩選為符合述詞的資料列子集。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="8f2bc-142">產生匯總輸入資料表內容的資料表。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="8f2bc-143">合併兩個資料表的資料列，並比對每個資料表中的指定資料行的值來建立新的資料表。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="8f2bc-144">傳回輸入記錄集中的記錄數目。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="8f2bc-145">傳回按指定資料行排序的前 N 筆記錄。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="8f2bc-146">傳回指定的資料列數。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="8f2bc-147">選取要包含的資料行、重新命名或捨棄，然後插入新的計算資料行。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="8f2bc-148">建立計算資料行並將它們附加到結果集中。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="8f2bc-149">傳回 Expr 在群組中取得的獨特值集合的動態 (JSON) 陣列。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="8f2bc-150">在一組資料表中尋找符合述詞的資料列。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="8f2bc-151">若要查看這些運算子的實際範例，請從進階搜捕的 [開始使用]\*\*\*\* 區段中執行這些運算子。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="8f2bc-152">了解資料類型及其查詢語法含意</span><span class="sxs-lookup"><span data-stu-id="8f2bc-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="8f2bc-153">進階搜捕資料表中的資料通常會分類為以下資料類型。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="8f2bc-154">資料類型</span><span class="sxs-lookup"><span data-stu-id="8f2bc-154">Data type</span></span> | <span data-ttu-id="8f2bc-155">描述與查詢含意</span><span class="sxs-lookup"><span data-stu-id="8f2bc-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="8f2bc-156">通常代表事件時間戳記的資料和時間資訊</span><span class="sxs-lookup"><span data-stu-id="8f2bc-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="8f2bc-157">字元字串</span><span class="sxs-lookup"><span data-stu-id="8f2bc-157">Character string</span></span> |
| `bool` | <span data-ttu-id="8f2bc-158">True 或 False</span><span class="sxs-lookup"><span data-stu-id="8f2bc-158">True or false</span></span> |
| `int` | <span data-ttu-id="8f2bc-159">32 位元數值</span><span class="sxs-lookup"><span data-stu-id="8f2bc-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="8f2bc-160">64 位元數值</span><span class="sxs-lookup"><span data-stu-id="8f2bc-160">64-bit numeric value</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="8f2bc-161">編寫查詢時取得協助</span><span class="sxs-lookup"><span data-stu-id="8f2bc-161">Get help as you write queries</span></span>
<span data-ttu-id="8f2bc-162">運用下列功能更快速地編寫查詢：</span><span class="sxs-lookup"><span data-stu-id="8f2bc-162">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="8f2bc-163">**Autosuggest** --當您撰寫查詢時，高級搜尋會提供 IntelliSense 的建議。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-163">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="8f2bc-164">**架構樹**系-您的工作區域旁會提供包含資料表清單和其欄的架構標記法。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-164">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="8f2bc-165">如需詳細資訊，請將游標暫留在某項目上。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-165">For more information, hover over an item.</span></span> <span data-ttu-id="8f2bc-166">按兩下某個項目，將它插入查詢編輯器。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-166">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="8f2bc-167">**[架構參考（Schema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** ）包含資料表和欄描述的入口網站參照，以及支援的事件種類（ `ActionType` 值）和範例查詢</span><span class="sxs-lookup"><span data-stu-id="8f2bc-167">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="8f2bc-168">在編輯器中使用多個查詢</span><span class="sxs-lookup"><span data-stu-id="8f2bc-168">Work with multiple queries in the editor</span></span>
<span data-ttu-id="8f2bc-169">查詢編輯器可以做為您用來試驗多個查詢的草稿墊。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-169">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="8f2bc-170">若要使用多個查詢：</span><span class="sxs-lookup"><span data-stu-id="8f2bc-170">To use multiple queries:</span></span>

- <span data-ttu-id="8f2bc-171">以空行分隔每個查詢。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-171">Separate each query with an empty line.</span></span>
- <span data-ttu-id="8f2bc-172">將游標放在查詢的任何部分，以選取該查詢，然後再執行它。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-172">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="8f2bc-173">這只會執行選取的查詢。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-173">This will run only the selected query.</span></span> <span data-ttu-id="8f2bc-174">若要執行另一個查詢，請據以移動游標，然後選取 [**執行查詢**]。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-174">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![具有多個查詢的查詢編輯器影像](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="8f2bc-176">使用範例查詢</span><span class="sxs-lookup"><span data-stu-id="8f2bc-176">Use sample queries</span></span>

<span data-ttu-id="8f2bc-177">[開始使用]\*\*\*\* 區段提供一些使用常用運算子的簡單查詢。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-177">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="8f2bc-178">嘗試執行這些查詢，並對它們進行些微修改。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-178">Try running these queries and making small modifications to them.</span></span>

![進階搜捕視窗的影像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="8f2bc-180">除了基本查詢範例以外，您也可以取得適用於特定威脅搜捕案例的[共用查詢](advanced-hunting-shared-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-180">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="8f2bc-181">探索頁面左側或 GitHub 查詢儲存庫的共用查詢。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-181">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="8f2bc-182">Access 查詢語言說明文件</span><span class="sxs-lookup"><span data-stu-id="8f2bc-182">Access query language documentation</span></span>

<span data-ttu-id="8f2bc-183">如需有關 Kusto 查詢語言和支援運算子的詳細資訊，請參閱 [Kusto 查詢語言說明文件](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="8f2bc-183">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f2bc-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f2bc-184">Related topics</span></span>
- [<span data-ttu-id="8f2bc-185">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="8f2bc-185">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8f2bc-186">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="8f2bc-186">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8f2bc-187">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="8f2bc-187">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8f2bc-188">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="8f2bc-188">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8f2bc-189">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="8f2bc-189">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8f2bc-190">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="8f2bc-190">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
