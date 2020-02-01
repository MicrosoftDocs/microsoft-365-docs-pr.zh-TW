---
title: 了解 Microsoft 威脅防護中的進階搜捕查詢語言
description: 建立您的第一個威脅搜捕查詢，並了解常用的運算子和進階搜捕查詢語言的其他概念
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 語言，了解，第一個查詢、 遙測、 活動、 遙測、 自訂偵測、 結構描述、 kusto、 運算子、 資料類型
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
ms.openlocfilehash: 586b887c9c5c1e4c19623c89dd08ed62ba0d4bb2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600340"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="d0ce5-104">了解進階搜捕查詢語言</span><span class="sxs-lookup"><span data-stu-id="d0ce5-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="d0ce5-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d0ce5-105">**Applies to:**</span></span>
- <span data-ttu-id="d0ce5-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="d0ce5-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d0ce5-107">進階搜捕是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="d0ce5-108">您可以使用 Kusto 語法和運算子來建立查詢，以在特別為進階搜捕而建構的[結構描述](advanced-hunting-schema-tables.md)中尋找的資訊。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="d0ce5-109">若要深入了解這些概念，請執行您的第一個查詢。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="d0ce5-110">嘗試您的第一個查詢</span><span class="sxs-lookup"><span data-stu-id="d0ce5-110">Try your first query</span></span>

<span data-ttu-id="d0ce5-111">在 Microsoft 365 安全性中心中，移至 [搜捕]\*\*\*\* 以執行您的第一個查詢。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="d0ce5-112">請使用下列範例：</span><span class="sxs-lookup"><span data-stu-id="d0ce5-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="d0ce5-113">這是它在進階搜捕中看起來的樣子。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Defender ATP 進階搜捕查詢的影像](../images/advanced-hunting-query-example.png)

<span data-ttu-id="d0ce5-115">查詢會從描述其用途的簡短註解開始。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="d0ce5-116">如果您後來決定要儲存查詢，並與組織中的其他人共用，這會有所幫助。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

<span data-ttu-id="d0ce5-117">查詢本身通常會以資料表名稱開頭，後面接著管道 (`|`) 開始的一系列元素。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="d0ce5-118">在此範例中，我們首先使用資料表名稱 `DeviceProcessEvents` 來新增，並視需要新增管道元素。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-118">In this example, we start by adding  with the table name `DeviceProcessEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="d0ce5-119">第一個管道元素是範圍在過去七天內的時間篩選條件。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="d0ce5-120">盡可能讓時間範圍越小越好，以確保查詢能順利執行、傳回可管理的結果，且不會逾時。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="d0ce5-121">在時間範圍之後會緊接著代表 PowerShell 應用程式的檔案搜尋。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="d0ce5-122">之後，查詢會尋找通常用於 PowerShell 的命令列來下載檔案。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="d0ce5-123">現在您的查詢已清楚識別出您要尋找的資料，您可以新增元素來定義結果。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="d0ce5-124">`project` 會傳回特定資料行，`top` 會限制結果的數目，讓結果的格式正確、數量合理且容易處理。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="d0ce5-125">按一下 [執行查詢]\*\*\*\* 以查看結果。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="d0ce5-126">您可以展開畫面檢視，讓您專注在您的搜捕查詢和結果。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="d0ce5-127">了解適用於進階搜捕的一般查詢運算子</span><span class="sxs-lookup"><span data-stu-id="d0ce5-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="d0ce5-128">您已執行了第一個查詢，並對其組成元素有一點了解了，現在可以開始追蹤一些基本概念。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="d0ce5-129">進階搜捕所使用的 Kusto 查詢語言支援一系列運算子，包括下列常見運算子。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="d0ce5-130">運算子</span><span class="sxs-lookup"><span data-stu-id="d0ce5-130">Operator</span></span> | <span data-ttu-id="d0ce5-131">描述及用法</span><span class="sxs-lookup"><span data-stu-id="d0ce5-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="d0ce5-132">將資料表篩選為符合述詞的資料列子集。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="d0ce5-133">產生匯總輸入資料表內容的資料表。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="d0ce5-134">合併兩個資料表的資料列，並比對每個資料表中的指定資料行的值來建立新的資料表。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="d0ce5-135">傳回輸入記錄集中的記錄數目。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="d0ce5-136">傳回按指定資料行排序的前 N 筆記錄。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="d0ce5-137">傳回指定的資料列數。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="d0ce5-138">選取要包含的資料行、重新命名或捨棄，然後插入新的計算資料行。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="d0ce5-139">建立計算資料行並將它們附加到結果集中。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="d0ce5-140">傳回 Expr 在群組中取得的獨特值集合的動態 (JSON) 陣列。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="d0ce5-141">在一組資料表中尋找符合述詞的資料列。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="d0ce5-142">若要查看這些運算子的實際範例，請從進階搜捕的 [開始使用]\*\*\*\* 區段中執行這些運算子。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="d0ce5-143">了解資料類型及其查詢語法含意</span><span class="sxs-lookup"><span data-stu-id="d0ce5-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="d0ce5-144">進階搜捕資料表中的資料通常會分類為以下資料類型。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="d0ce5-145">資料類型</span><span class="sxs-lookup"><span data-stu-id="d0ce5-145">Data type</span></span> | <span data-ttu-id="d0ce5-146">描述與查詢含意</span><span class="sxs-lookup"><span data-stu-id="d0ce5-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="d0ce5-147">通常代表事件時間戳記的資料和時間資訊</span><span class="sxs-lookup"><span data-stu-id="d0ce5-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="d0ce5-148">字元字串</span><span class="sxs-lookup"><span data-stu-id="d0ce5-148">Character string</span></span> |
| `bool` | <span data-ttu-id="d0ce5-149">True 或 False</span><span class="sxs-lookup"><span data-stu-id="d0ce5-149">True or false</span></span> |
| `int` | <span data-ttu-id="d0ce5-150">32 位元數值</span><span class="sxs-lookup"><span data-stu-id="d0ce5-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="d0ce5-151">64 位元數值</span><span class="sxs-lookup"><span data-stu-id="d0ce5-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="d0ce5-152">使用範例查詢</span><span class="sxs-lookup"><span data-stu-id="d0ce5-152">Use sample queries</span></span>

<span data-ttu-id="d0ce5-153">[開始使用]\*\*\*\* 區段提供一些使用常用運算子的簡單查詢。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="d0ce5-154">嘗試執行這些查詢，並對它們進行些微修改。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-154">Try running these queries and making small modifications to them.</span></span>

![進階搜捕視窗的影像](../images/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="d0ce5-156">除了基本查詢範例以外，您也可以取得適用於特定威脅搜捕案例的[共用查詢](advanced-hunting-shared-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="d0ce5-157">探索頁面左側或 GitHub 查詢儲存庫的共用查詢。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="d0ce5-158">Access 查詢語言說明文件</span><span class="sxs-lookup"><span data-stu-id="d0ce5-158">Access query language documentation</span></span>

<span data-ttu-id="d0ce5-159">如需有關 Kusto 查詢語言和支援運算子的詳細資訊，請參閱 [Kusto 查詢語言說明文件](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0ce5-160">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0ce5-160">Related topics</span></span>
- [<span data-ttu-id="d0ce5-161">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="d0ce5-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0ce5-162">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="d0ce5-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d0ce5-163">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="d0ce5-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d0ce5-164">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="d0ce5-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d0ce5-165">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="d0ce5-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)