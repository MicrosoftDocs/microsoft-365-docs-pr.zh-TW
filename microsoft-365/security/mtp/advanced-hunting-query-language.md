---
title: 瞭解 Microsoft 365 Defender 中的高級搜尋查詢語言
description: 建立您的第一個威脅搜捕查詢，並了解常用的運算子和進階搜捕查詢語言的其他概念
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，語言，學習，第一個查詢，遙測，事件，遙測，自訂偵測，架構，kusto，運算子，資料類型，powershell 下載，查詢範例
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
ms.openlocfilehash: f996cd00cc2f7a1f1de2540f1d6686d26431c4f4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904076"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="1cb91-104">了解進階搜捕查詢語言</span><span class="sxs-lookup"><span data-stu-id="1cb91-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1cb91-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="1cb91-105">**Applies to:**</span></span>
- <span data-ttu-id="1cb91-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1cb91-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1cb91-107">進階搜捕是以 [Kusto 查詢語言](/azure/kusto/query/)為基礎。</span><span class="sxs-lookup"><span data-stu-id="1cb91-107">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="1cb91-108">您可以使用 Kusto 運算子和語句來建立在特定 [架構](advanced-hunting-schema-tables.md)中尋找資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="1cb91-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="1cb91-109">若要深入了解這些概念，請執行您的第一個查詢。</span><span class="sxs-lookup"><span data-stu-id="1cb91-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="1cb91-110">嘗試您的第一個查詢</span><span class="sxs-lookup"><span data-stu-id="1cb91-110">Try your first query</span></span>

<span data-ttu-id="1cb91-111">在 Microsoft 365 的 [安全性中心] 中，移至 **搜尋** 以執行第一個查詢。</span><span class="sxs-lookup"><span data-stu-id="1cb91-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="1cb91-112">請使用下列範例：</span><span class="sxs-lookup"><span data-stu-id="1cb91-112">Use the following example:</span></span>

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

<span data-ttu-id="1cb91-113">**[在高級搜尋中執行此查詢](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="1cb91-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="1cb91-114">描述查詢，並指定要搜尋的表格</span><span class="sxs-lookup"><span data-stu-id="1cb91-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="1cb91-115">已將簡短批註新增至查詢的開頭，以描述其用途。</span><span class="sxs-lookup"><span data-stu-id="1cb91-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="1cb91-116">此批註可協助您稍後決定要儲存查詢，並與組織中的其他人共用。</span><span class="sxs-lookup"><span data-stu-id="1cb91-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="1cb91-117">查詢本身通常會從資料表名稱開始，並以管道 () 開始數個元素 `|` 。</span><span class="sxs-lookup"><span data-stu-id="1cb91-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="1cb91-118">在此範例中，我們會從建立兩個表格的同盟開始，並  `DeviceProcessEvents` `DeviceNetworkEvents` 視需要新增管線元素。</span><span class="sxs-lookup"><span data-stu-id="1cb91-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="1cb91-119">設定時間範圍</span><span class="sxs-lookup"><span data-stu-id="1cb91-119">Set the time range</span></span>
<span data-ttu-id="1cb91-120">第一個輸送的元素是一種範圍設定為前七天的時間篩選器。</span><span class="sxs-lookup"><span data-stu-id="1cb91-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="1cb91-121">限制時間範圍可協助確保查詢順利執行、傳回可管理的結果，而且不會超時。</span><span class="sxs-lookup"><span data-stu-id="1cb91-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="1cb91-122">檢查特定進程</span><span class="sxs-lookup"><span data-stu-id="1cb91-122">Check specific processes</span></span>
<span data-ttu-id="1cb91-123">時間範圍後緊接著搜尋代表 PowerShell 應用程式的處理常式檔案名。</span><span class="sxs-lookup"><span data-stu-id="1cb91-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="1cb91-124">搜尋特定的命令字串</span><span class="sxs-lookup"><span data-stu-id="1cb91-124">Search for specific command strings</span></span>
<span data-ttu-id="1cb91-125">之後，查詢會在命令列中尋找通常用來透過 PowerShell 下載檔案的字串。</span><span class="sxs-lookup"><span data-stu-id="1cb91-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="1cb91-126">自訂結果欄及長度</span><span class="sxs-lookup"><span data-stu-id="1cb91-126">Customize result columns and length</span></span> 
<span data-ttu-id="1cb91-127">現在，您的查詢會明確識別您想要尋找的資料，您可以定義結果的外觀。</span><span class="sxs-lookup"><span data-stu-id="1cb91-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="1cb91-128">`project` 會傳回特定的欄，並 `top` 限制結果的數目。</span><span class="sxs-lookup"><span data-stu-id="1cb91-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="1cb91-129">這些運算子可協助確保結果具有適當的格式，且易於處理。</span><span class="sxs-lookup"><span data-stu-id="1cb91-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="1cb91-130">選取 [ **執行查詢** ] 以查看結果。</span><span class="sxs-lookup"><span data-stu-id="1cb91-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="1cb91-131">使用查詢編輯器右上角的展開圖示，以著重于搜尋查詢和結果。</span><span class="sxs-lookup"><span data-stu-id="1cb91-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高級搜尋查詢編輯器中的展開控制項影像](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="1cb91-133">您可以以圖表形式查看查詢結果，並快速調整篩選。</span><span class="sxs-lookup"><span data-stu-id="1cb91-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="1cb91-134">如需相關指導，請 [參閱使用查詢結果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="1cb91-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="1cb91-135">瞭解一般查詢運算子</span><span class="sxs-lookup"><span data-stu-id="1cb91-135">Learn common query operators</span></span>

<span data-ttu-id="1cb91-136">您剛剛執行第一個查詢，並大致瞭解其元件。</span><span class="sxs-lookup"><span data-stu-id="1cb91-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="1cb91-137">請稍微進行回溯，並瞭解一些基礎知識。</span><span class="sxs-lookup"><span data-stu-id="1cb91-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="1cb91-138">進階搜捕所使用的 Kusto 查詢語言支援一系列運算子，包括下列常見運算子。</span><span class="sxs-lookup"><span data-stu-id="1cb91-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="1cb91-139">運算子</span><span class="sxs-lookup"><span data-stu-id="1cb91-139">Operator</span></span> | <span data-ttu-id="1cb91-140">描述及用法</span><span class="sxs-lookup"><span data-stu-id="1cb91-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="1cb91-141">將資料表篩選為符合述詞的資料列子集。</span><span class="sxs-lookup"><span data-stu-id="1cb91-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="1cb91-142">產生匯總輸入資料表內容的資料表。</span><span class="sxs-lookup"><span data-stu-id="1cb91-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="1cb91-143">合併兩個資料表的資料列，並比對每個資料表中的指定資料行的值來建立新的資料表。</span><span class="sxs-lookup"><span data-stu-id="1cb91-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="1cb91-144">傳回輸入記錄集中的記錄數目。</span><span class="sxs-lookup"><span data-stu-id="1cb91-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="1cb91-145">傳回按指定資料行排序的前 N 筆記錄。</span><span class="sxs-lookup"><span data-stu-id="1cb91-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="1cb91-146">傳回指定的資料列數。</span><span class="sxs-lookup"><span data-stu-id="1cb91-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="1cb91-147">選取要包含的資料行、重新命名或捨棄，然後插入新的計算資料行。</span><span class="sxs-lookup"><span data-stu-id="1cb91-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="1cb91-148">建立計算資料行並將它們附加到結果集中。</span><span class="sxs-lookup"><span data-stu-id="1cb91-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="1cb91-149">傳回 Expr 在群組中取得的獨特值集合的動態 (JSON) 陣列。</span><span class="sxs-lookup"><span data-stu-id="1cb91-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="1cb91-150">在一組資料表中尋找符合述詞的資料列。</span><span class="sxs-lookup"><span data-stu-id="1cb91-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="1cb91-151">若要查看這些運算子的實際範例，請從進階搜捕的 [開始使用] 區段中執行這些運算子。</span><span class="sxs-lookup"><span data-stu-id="1cb91-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="1cb91-152">瞭解資料類型</span><span class="sxs-lookup"><span data-stu-id="1cb91-152">Understand data types</span></span>

<span data-ttu-id="1cb91-153">「高級搜尋」支援 Kusto 資料類型，包括下列通用類型：</span><span class="sxs-lookup"><span data-stu-id="1cb91-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="1cb91-154">資料類型</span><span class="sxs-lookup"><span data-stu-id="1cb91-154">Data type</span></span> | <span data-ttu-id="1cb91-155">描述與查詢含意</span><span class="sxs-lookup"><span data-stu-id="1cb91-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="1cb91-156">通常代表事件時間戳記的資料和時間資訊。</span><span class="sxs-lookup"><span data-stu-id="1cb91-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="1cb91-157">請參閱支援的 datetime 格式</span><span class="sxs-lookup"><span data-stu-id="1cb91-157">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="1cb91-158">UTF-8 以單引號括住的字元字串 (`'`) 或雙引號 (`"`) 。</span><span class="sxs-lookup"><span data-stu-id="1cb91-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="1cb91-159">閱讀更多關於字串的資訊</span><span class="sxs-lookup"><span data-stu-id="1cb91-159">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="1cb91-160">這種資料類型支援 `true` 或 `false` 狀態。</span><span class="sxs-lookup"><span data-stu-id="1cb91-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="1cb91-161">請參閱支援的文字及運算子</span><span class="sxs-lookup"><span data-stu-id="1cb91-161">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="1cb91-162">32位整數</span><span class="sxs-lookup"><span data-stu-id="1cb91-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="1cb91-163">64位整數</span><span class="sxs-lookup"><span data-stu-id="1cb91-163">64-bit integer</span></span> |

<span data-ttu-id="1cb91-164">若要深入瞭解這些資料類型，請 [參閱 Kusto 純量資料型別](/azure/data-explorer/kusto/query/scalar-data-types/)。</span><span class="sxs-lookup"><span data-stu-id="1cb91-164">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="1cb91-165">編寫查詢時取得協助</span><span class="sxs-lookup"><span data-stu-id="1cb91-165">Get help as you write queries</span></span>
<span data-ttu-id="1cb91-166">運用下列功能更快速地編寫查詢：</span><span class="sxs-lookup"><span data-stu-id="1cb91-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="1cb91-167">**Autosuggest**--當您撰寫查詢時，高級搜尋會提供 IntelliSense 的建議。</span><span class="sxs-lookup"><span data-stu-id="1cb91-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="1cb91-168">**架構樹** 系-您的工作區域旁會提供包含資料表清單和其欄的架構標記法。</span><span class="sxs-lookup"><span data-stu-id="1cb91-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="1cb91-169">如需詳細資訊，請將游標暫留在某項目上。</span><span class="sxs-lookup"><span data-stu-id="1cb91-169">For more information, hover over an item.</span></span> <span data-ttu-id="1cb91-170">按兩下某個項目，將它插入查詢編輯器。</span><span class="sxs-lookup"><span data-stu-id="1cb91-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="1cb91-171">**[架構參考（Schema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**）包含資料表和欄描述的入口網站內參照，以及支援的事件種類 (`ActionType` 值) 和範例查詢</span><span class="sxs-lookup"><span data-stu-id="1cb91-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="1cb91-172">在編輯器中使用多個查詢</span><span class="sxs-lookup"><span data-stu-id="1cb91-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="1cb91-173">您可以使用查詢編輯器來試驗多個查詢。</span><span class="sxs-lookup"><span data-stu-id="1cb91-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="1cb91-174">若要使用多個查詢：</span><span class="sxs-lookup"><span data-stu-id="1cb91-174">To use multiple queries:</span></span>

- <span data-ttu-id="1cb91-175">以空行分隔每個查詢。</span><span class="sxs-lookup"><span data-stu-id="1cb91-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="1cb91-176">將游標放在查詢的任何部分，以選取該查詢，然後再執行它。</span><span class="sxs-lookup"><span data-stu-id="1cb91-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="1cb91-177">這只會執行選取的查詢。</span><span class="sxs-lookup"><span data-stu-id="1cb91-177">This will run only the selected query.</span></span> <span data-ttu-id="1cb91-178">若要執行另一個查詢，請據以移動游標，然後選取 [ **執行查詢**]。</span><span class="sxs-lookup"><span data-stu-id="1cb91-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![具有多個查詢的查詢編輯器影像](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="1cb91-180">使用範例查詢</span><span class="sxs-lookup"><span data-stu-id="1cb91-180">Use sample queries</span></span>

<span data-ttu-id="1cb91-181">[開始使用] 區段提供一些使用常用運算子的簡單查詢。</span><span class="sxs-lookup"><span data-stu-id="1cb91-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="1cb91-182">嘗試執行這些查詢，並對它們進行些微修改。</span><span class="sxs-lookup"><span data-stu-id="1cb91-182">Try running these queries and making small modifications to them.</span></span>

![進階搜捕視窗的影像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="1cb91-184">除了基本查詢範例以外，您也可以取得適用於特定威脅搜捕案例的[共用查詢](advanced-hunting-shared-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb91-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="1cb91-185">流覽頁面左側的共用查詢或 [GitHub 查詢存放庫](https://aka.ms/hunting-queries)。</span><span class="sxs-lookup"><span data-stu-id="1cb91-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="1cb91-186">Access 查詢語言說明文件</span><span class="sxs-lookup"><span data-stu-id="1cb91-186">Access query language documentation</span></span>

<span data-ttu-id="1cb91-187">如需有關 Kusto 查詢語言和支援運算子的詳細資訊，請參閱 [Kusto 查詢語言說明文件](/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="1cb91-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1cb91-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="1cb91-188">Related topics</span></span>
- [<span data-ttu-id="1cb91-189">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="1cb91-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1cb91-190">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="1cb91-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="1cb91-191">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="1cb91-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1cb91-192">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="1cb91-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1cb91-193">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="1cb91-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1cb91-194">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="1cb91-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)