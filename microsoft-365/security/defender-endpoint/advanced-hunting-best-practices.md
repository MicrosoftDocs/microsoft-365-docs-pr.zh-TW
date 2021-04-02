---
title: 查詢高級搜尋的最佳作法
description: 了解如何在使用進階搜捕時建構快速、有效率且無錯誤的威脅搜捕查詢
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、自訂偵測、架構、kusto、避免超時、命令列、進程識別碼
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499264"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="dcf7b-104">進階搜捕查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="dcf7b-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dcf7b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="dcf7b-105">**Applies to:**</span></span>
- [<span data-ttu-id="dcf7b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dcf7b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="dcf7b-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="dcf7b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dcf7b-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="dcf7b-109">最佳化查詢效能</span><span class="sxs-lookup"><span data-stu-id="dcf7b-109">Optimize query performance</span></span>

<span data-ttu-id="dcf7b-110">套用這些建議以快速取得結果，並避免執行複雜的查詢時發生超時。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="dcf7b-111">嘗試新的查詢時，一律使用 `limit` 來避免極度龐大的結果集。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="dcf7b-112">您也可以一開始使用 `count` 來評估結果集的大小。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="dcf7b-113">首先使用時間篩選。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-113">Use time filters first.</span></span> <span data-ttu-id="dcf7b-114">理想狀況下，將您的查詢限制為七天。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="dcf7b-115">將預期會刪除大多數資料的篩選放在時間篩選之後的查詢開頭。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="dcf7b-116">尋找完整標記時，請在 `contains`上使用 `has`運算子。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="dcf7b-117">尋找特定欄位，而不是在所有欄位執行全文搜尋。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="dcf7b-118">結合表格時，先指定含有較少列的表格。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="dcf7b-119">`project` 僅限已結合的表格所需的欄位。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="dcf7b-120">如需提高查詢效能的更多指導方針，請參閱 [Kusto 查詢最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="dcf7b-121">查詢祕訣與陷阱</span><span class="sxs-lookup"><span data-stu-id="dcf7b-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="dcf7b-122">含有程序識別碼的查詢</span><span class="sxs-lookup"><span data-stu-id="dcf7b-122">Queries with process IDs</span></span>

<span data-ttu-id="dcf7b-123">程序識別碼 (PID) 會在 Windows 中回收，並針對新程序重複使用。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="dcf7b-124">它們本身不能充當特定程序的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="dcf7b-125">若要取得特定裝置上之程式的唯一識別碼，請使用進程識別碼及程式建立時間。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="dcf7b-126">當您在程式中聯接或摘要資料時，包含裝置識別碼的欄 (`DeviceId` 或 `DeviceName`) ，處理常式識別碼 (`ProcessId` 或 `InitiatingProcessId`) ，以及程式建立時間 (`ProcessCreationTime` 或 `InitiatingProcessCreationTime`) 。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="dcf7b-127">下列範例查詢發現透過連接埠 445 (SMB) 存取 10 個以上 IP 位址的程序，可能是因為掃描檔案共用。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="dcf7b-128">查詢會以 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 進行彙總，因此它會檢查單一程序，而不會將多個具有相同程序識別碼的程序混合在一起。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="dcf7b-129">含有命令列的查詢</span><span class="sxs-lookup"><span data-stu-id="dcf7b-129">Queries with command lines</span></span>

<span data-ttu-id="dcf7b-130">命令列可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-130">Command lines can vary.</span></span> <span data-ttu-id="dcf7b-131">若適用，請篩選檔案名稱並執行模糊比對。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="dcf7b-132">有許多方法可以建構命令列來完成工作。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="dcf7b-133">例如，攻擊者會參照影像檔 (無論是否有路徑、無附檔名、使用環境變數或使用引號)。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="dcf7b-134">此外，攻擊者也會變更參數順序，或新增多個引號和空格。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="dcf7b-135">若要使用命令列建立更持久的查詢，請套用做法下列做法：</span><span class="sxs-lookup"><span data-stu-id="dcf7b-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="dcf7b-136">藉由按照檔案名稱欄位比對，而非在命令列欄位中進行篩選，以識別已知的程序 (例如 *net.ext* 或 *psexec.exe*)。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="dcf7b-137">查詢命令列引數時，請勿以特定順序尋找多個不相關引數上完全相符的內容。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="dcf7b-138">請改用規則運算式或使用多個不同的包含運算子。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="dcf7b-139">使用不區分大小寫對比。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-139">Use case insensitive matches.</span></span> <span data-ttu-id="dcf7b-140">例如，使用 `=~` 、 `in~` 和， `contains` 而不是 `==` ， `in` 及 `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="dcf7b-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="dcf7b-141">若要降低 DOS 命令列混淆技術，請考慮移除引號、使用空格代替逗號，以及使用單一空格取代多個連續的空格。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="dcf7b-142">請注意，有更複雜的 DOS 混淆技術需要其他降低方法，但這些方法可協助處理最常見的問題。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="dcf7b-143">下列範例說明建構查詢的幾種方法，可尋找 *net.exe* 檔案以停止 Windows Defender 防火牆服務：</span><span class="sxs-lookup"><span data-stu-id="dcf7b-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
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

> <span data-ttu-id="dcf7b-144">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="dcf7b-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dcf7b-145">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="dcf7b-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="dcf7b-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="dcf7b-146">Related topics</span></span>

- [<span data-ttu-id="dcf7b-147">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="dcf7b-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dcf7b-148">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="dcf7b-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dcf7b-149">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="dcf7b-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="dcf7b-150">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="dcf7b-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="dcf7b-151">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="dcf7b-151">Custom detections overview</span></span>](overview-custom-detections.md)
