---
title: Microsoft 威脅防護中進階搜捕的最佳做法
description: 了解如何在使用進階搜捕時建構快速、有效率且無錯誤的威脅搜捕查詢
keywords: 進階搜捕,威脅搜捕,網路威脅搜捕,搜尋,查詢,遙測,自訂偵測,結構描述,kusto,避免逾時,命令列,程序識別碼
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 871f659074c4f8386746e341db4d3500c5e80a31
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807002"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="9928d-104">進階搜捕查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="9928d-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="9928d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9928d-105">**Applies to:**</span></span>
- <span data-ttu-id="9928d-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="9928d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a><span data-ttu-id="9928d-107">最佳化查詢效能</span><span class="sxs-lookup"><span data-stu-id="9928d-107">Optimize query performance</span></span>
<span data-ttu-id="9928d-108">套用這些建議來加快取得結果，並避免在執行複雜查詢時發生逾時：</span><span class="sxs-lookup"><span data-stu-id="9928d-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="9928d-109">嘗試新的查詢時，一律使用 `limit` 來避免極度龐大的結果集。</span><span class="sxs-lookup"><span data-stu-id="9928d-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="9928d-110">您也可以一開始使用 `count` 來評估結果集的大小。</span><span class="sxs-lookup"><span data-stu-id="9928d-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="9928d-111">首先使用時間篩選。</span><span class="sxs-lookup"><span data-stu-id="9928d-111">Use time filters first.</span></span> <span data-ttu-id="9928d-112">在理想情況下，將查詢限制為偶數日。</span><span class="sxs-lookup"><span data-stu-id="9928d-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="9928d-113">將預期會刪除大多數資料的篩選放在時間篩選之後的查詢開頭。</span><span class="sxs-lookup"><span data-stu-id="9928d-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="9928d-114">尋找完整標記時，請在 `contains`上使用 `has`運算子。</span><span class="sxs-lookup"><span data-stu-id="9928d-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="9928d-115">尋找特定欄位，而不是在所有欄位執行全文搜尋。</span><span class="sxs-lookup"><span data-stu-id="9928d-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="9928d-116">結合表格時，先指定含有較少列的表格。</span><span class="sxs-lookup"><span data-stu-id="9928d-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="9928d-117">`project` 僅限已結合的表格所需的欄位。</span><span class="sxs-lookup"><span data-stu-id="9928d-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="9928d-118">如需提高查詢效能的更多指導方針，請參閱 [Kusto 查詢最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="9928d-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="9928d-119">查詢祕訣與陷阱</span><span class="sxs-lookup"><span data-stu-id="9928d-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="9928d-120">含有程序識別碼的查詢</span><span class="sxs-lookup"><span data-stu-id="9928d-120">Queries with process IDs</span></span>
<span data-ttu-id="9928d-121">程序識別碼 (PID) 會在 Windows 中回收，並針對新程序重複使用。</span><span class="sxs-lookup"><span data-stu-id="9928d-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="9928d-122">它們本身不能充當特定程序的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="9928d-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="9928d-123">若要為特定電腦上的程序取得唯一識別碼，請使用程序識別碼與程序建立時間。</span><span class="sxs-lookup"><span data-stu-id="9928d-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="9928d-124">結合或摘要處理程序中的資料時，需包含電腦識別碼的欄位 (`DeviceId` 或 `DeviceName`)、程序識別碼 (`ProcessId` 或 `InitiatingProcessId`) 以及程序建立時間 (`ProcessCreationTime` 或 `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="9928d-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="9928d-125">下列範例查詢發現透過連接埠 445 (SMB) 存取 10 個以上 IP 位址的程序，可能是因為掃描檔案共用。</span><span class="sxs-lookup"><span data-stu-id="9928d-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="9928d-126">例如查詢：</span><span class="sxs-lookup"><span data-stu-id="9928d-126">Example query:</span></span>
```
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="9928d-127">查詢會以 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 進行彙總，因此它會檢查單一程序，而不會將多個具有相同程序識別碼的程序混合在一起。</span><span class="sxs-lookup"><span data-stu-id="9928d-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="9928d-128">含有命令列的查詢</span><span class="sxs-lookup"><span data-stu-id="9928d-128">Queries with command lines</span></span>

<span data-ttu-id="9928d-129">命令列可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="9928d-129">Command lines can vary.</span></span> <span data-ttu-id="9928d-130">若適用，請篩選檔案名稱並執行模糊比對。</span><span class="sxs-lookup"><span data-stu-id="9928d-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="9928d-131">有許多方法可以建構命令列來完成工作。</span><span class="sxs-lookup"><span data-stu-id="9928d-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="9928d-132">例如，攻擊者會參照影像檔 (無論是否有路徑、無附檔名、使用環境變數或使用引號)。</span><span class="sxs-lookup"><span data-stu-id="9928d-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="9928d-133">此外，攻擊者也會變更參數順序，或新增多個引號和空格。</span><span class="sxs-lookup"><span data-stu-id="9928d-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="9928d-134">若要使用命令列建立更持久的查詢，請套用做法下列做法：</span><span class="sxs-lookup"><span data-stu-id="9928d-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="9928d-135">藉由按照檔案名稱欄位比對，而非在命令列欄位中進行篩選，以識別已知的程序 (例如 *net.ext* 或 *psexec.exe*)。</span><span class="sxs-lookup"><span data-stu-id="9928d-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="9928d-136">查詢命令列引數時，請勿以特定順序尋找多個不相關引數上完全相符的內容。</span><span class="sxs-lookup"><span data-stu-id="9928d-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="9928d-137">請改用規則運算式或使用多個不同的包含運算子。</span><span class="sxs-lookup"><span data-stu-id="9928d-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="9928d-138">使用不區分大小寫對比。</span><span class="sxs-lookup"><span data-stu-id="9928d-138">Use case insensitive matches.</span></span> <span data-ttu-id="9928d-139">例如，使用 `=~`、`in~` 和 `contains` 而不是 `==`、`in` 和 `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="9928d-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="9928d-140">若要降低 DOS 命令列混淆技術，請考慮移除引號、使用空格代替逗號，以及使用單一空格取代多個連續的空格。</span><span class="sxs-lookup"><span data-stu-id="9928d-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="9928d-141">請注意，有更複雜的 DOS 混淆技術需要其他降低方法，但這些方法可協助處理最常見的問題。</span><span class="sxs-lookup"><span data-stu-id="9928d-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="9928d-142">下列範例說明建構查詢的幾種方法，可尋找 *net.exe* 檔案以停止 Windows Defender 防火牆服務：</span><span class="sxs-lookup"><span data-stu-id="9928d-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="9928d-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="9928d-143">Related topics</span></span>
- [<span data-ttu-id="9928d-144">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="9928d-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9928d-145">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="9928d-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9928d-146">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="9928d-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9928d-147">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="9928d-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9928d-148">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="9928d-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
