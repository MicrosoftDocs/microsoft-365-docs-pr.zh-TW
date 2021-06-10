---
title: 在 Microsoft 365 Defender 的高級搜尋中處理錯誤
description: 瞭解使用高級搜尋時所顯示的錯誤
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema，kusto，timeout，資源，錯誤，未知錯誤，限制，配額，參數，配置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 32d50103c6476a89f24568edeea75a206e37e227
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952677"
---
# <a name="handle-advanced-hunting-errors"></a><span data-ttu-id="94d37-104">處理高級搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="94d37-104">Handle advanced hunting errors</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="94d37-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="94d37-105">**Applies to:**</span></span>
- <span data-ttu-id="94d37-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94d37-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="94d37-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="94d37-107">Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="94d37-108">「高級搜尋」顯示錯誤，以通知語法錯誤，以及每當查詢命中 [預先定義的配額和使用參數](advanced-hunting-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="94d37-108">Advanced hunting displays errors to notify for syntax mistakes and whenever queries hit [predefined quotas and usage parameters](advanced-hunting-limits.md).</span></span> <span data-ttu-id="94d37-109">請參閱下表，以取得如何解決或避免錯誤的秘訣。</span><span class="sxs-lookup"><span data-stu-id="94d37-109">Refer to the table below for tips on how to resolve or avoid errors.</span></span>

| <span data-ttu-id="94d37-110">錯誤類型</span><span class="sxs-lookup"><span data-stu-id="94d37-110">Error type</span></span> | <span data-ttu-id="94d37-111">原因</span><span class="sxs-lookup"><span data-stu-id="94d37-111">Cause</span></span> | <span data-ttu-id="94d37-112">解決方案</span><span class="sxs-lookup"><span data-stu-id="94d37-112">Resolution</span></span> | <span data-ttu-id="94d37-113">錯誤訊息範例</span><span class="sxs-lookup"><span data-stu-id="94d37-113">Error message examples</span></span> |
|--|--|--|--|
| <span data-ttu-id="94d37-114">語法錯誤</span><span class="sxs-lookup"><span data-stu-id="94d37-114">Syntax errors</span></span> | <span data-ttu-id="94d37-115">查詢包含無法辨識的名稱，包括對不存在運算子、欄、函數或資料表的參照。</span><span class="sxs-lookup"><span data-stu-id="94d37-115">The query contains unrecognized names, including references to nonexistent operators, columns, functions, or tables.</span></span> | <span data-ttu-id="94d37-116">請確定 [Kusto 運算子和函數](/azure/data-explorer/kusto/query/) 的參照正確無誤。</span><span class="sxs-lookup"><span data-stu-id="94d37-116">Ensure references to [Kusto operators and functions](/azure/data-explorer/kusto/query/) are correct.</span></span> <span data-ttu-id="94d37-117">檢查正確的高級搜尋欄、函數及資料表的 [架構](advanced-hunting-schema-tables.md) 。</span><span class="sxs-lookup"><span data-stu-id="94d37-117">Check [the schema](advanced-hunting-schema-tables.md) for the correct advanced hunting columns, functions, and tables.</span></span> <span data-ttu-id="94d37-118">以引號括住變數字串，以便加以識別。</span><span class="sxs-lookup"><span data-stu-id="94d37-118">Enclose variable strings in quotes so they are recognized.</span></span> <span data-ttu-id="94d37-119">撰寫查詢時，請使用來自 IntelliSense 的自動完成建議。</span><span class="sxs-lookup"><span data-stu-id="94d37-119">While writing your queries, use the autocomplete suggestions from IntelliSense.</span></span> | `A recognition error occurred.` |
| <span data-ttu-id="94d37-120">語意錯誤</span><span class="sxs-lookup"><span data-stu-id="94d37-120">Semantic errors</span></span> | <span data-ttu-id="94d37-121">雖然查詢使用有效的運算子、欄、函數或資料表名稱，但其結構及產生的邏輯都有錯誤。</span><span class="sxs-lookup"><span data-stu-id="94d37-121">While the query uses valid operator, column, function, or table names, there are errors in its structure and resulting logic.</span></span> <span data-ttu-id="94d37-122">在某些情況下，高級搜尋會識別導致錯誤的特定運算子。</span><span class="sxs-lookup"><span data-stu-id="94d37-122">In some cases, advanced hunting identifies the specific operator that caused the error.</span></span> | <span data-ttu-id="94d37-123">檢查查詢結構中是否有錯誤。</span><span class="sxs-lookup"><span data-stu-id="94d37-123">Check for errors in the structure of query.</span></span> <span data-ttu-id="94d37-124">如需指引，請參閱 [Kusto 檔](/azure/data-explorer/kusto/query/) 。</span><span class="sxs-lookup"><span data-stu-id="94d37-124">Refer to [Kusto documentation](/azure/data-explorer/kusto/query/) for guidance.</span></span> <span data-ttu-id="94d37-125">撰寫查詢時，請使用來自 IntelliSense 的自動完成建議。</span><span class="sxs-lookup"><span data-stu-id="94d37-125">While writing your queries, use the autocomplete suggestions from IntelliSense.</span></span> |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| <span data-ttu-id="94d37-126">超時</span><span class="sxs-lookup"><span data-stu-id="94d37-126">Timeouts</span></span> | <span data-ttu-id="94d37-127">查詢只能在 [有限的期限](advanced-hunting-limits.md)內執行超時之前。執行複雜查詢時，可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="94d37-127">A query can only run within a [limited period before timing out](advanced-hunting-limits.md). This error can happen more frequently when running complex queries.</span></span> | [<span data-ttu-id="94d37-128">優化查詢</span><span class="sxs-lookup"><span data-stu-id="94d37-128">Optimize the query</span></span>](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| <span data-ttu-id="94d37-129">CPU 節流</span><span class="sxs-lookup"><span data-stu-id="94d37-129">CPU throttling</span></span> | <span data-ttu-id="94d37-130">相同承租人中的查詢已超過根據租使用者規模所分配的 [CPU 資源](advanced-hunting-limits.md) 。</span><span class="sxs-lookup"><span data-stu-id="94d37-130">Queries in the same tenant have exceeded the [CPU resources](advanced-hunting-limits.md) that have been allocated based on tenant size.</span></span> | <span data-ttu-id="94d37-131">服務每隔15分鐘檢查一次 CPU 資源使用狀況，並在使用量超過已分配配額的10% 時，顯示警告。</span><span class="sxs-lookup"><span data-stu-id="94d37-131">The service checks CPU resource usage every 15 minutes and daily and displays warnings after usage exceeds 10% of the allocated quota.</span></span> <span data-ttu-id="94d37-132">如果您達到100% 的使用率，該服務會封鎖查詢，直到下一天或15分鐘週期之後。</span><span class="sxs-lookup"><span data-stu-id="94d37-132">If you reach 100% utilization, the service blocks queries until after the next daily or 15-minute cycle.</span></span> [<span data-ttu-id="94d37-133">優化您的查詢以避免命中 CPU 配額</span><span class="sxs-lookup"><span data-stu-id="94d37-133">Optimize your queries to avoid hitting CPU quotas</span></span>](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| <span data-ttu-id="94d37-134">超過結果大小限制</span><span class="sxs-lookup"><span data-stu-id="94d37-134">Result size limit exceeded</span></span>  | <span data-ttu-id="94d37-135">查詢結果集的匯總大小超過大小上限。</span><span class="sxs-lookup"><span data-stu-id="94d37-135">The aggregate size of the result set for the query has exceeded the maximum size.</span></span> <span data-ttu-id="94d37-136">如果結果集是如此大的錯誤，且在10000記錄的限制下截斷，則可能會發生這個錯誤。</span><span class="sxs-lookup"><span data-stu-id="94d37-136">This error can occur if the result set is so large that truncation at the 10,000-record limit can't reduce it to an acceptable size.</span></span> <span data-ttu-id="94d37-137">具有可調內容之多個欄的結果，可能會受到此錯誤影響。</span><span class="sxs-lookup"><span data-stu-id="94d37-137">Results that have multiple columns with sizable content are more likely to be impacted by this error.</span></span> | [<span data-ttu-id="94d37-138">優化查詢</span><span class="sxs-lookup"><span data-stu-id="94d37-138">Optimize the query</span></span>](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| <span data-ttu-id="94d37-139">過度資源消耗</span><span class="sxs-lookup"><span data-stu-id="94d37-139">Excessive resource consumption</span></span> | <span data-ttu-id="94d37-140">查詢已消耗過大量的資源，且已停止完成。</span><span class="sxs-lookup"><span data-stu-id="94d37-140">The query has consumed excessive amounts of resources and has been stopped from completing.</span></span> <span data-ttu-id="94d37-141">在某些情況下，高級搜尋會識別未優化的特定運算子。</span><span class="sxs-lookup"><span data-stu-id="94d37-141">In some cases, advanced hunting identifies the specific operator that wasn't optimized.</span></span> | [<span data-ttu-id="94d37-142">優化查詢</span><span class="sxs-lookup"><span data-stu-id="94d37-142">Optimize the query</span></span>](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| <span data-ttu-id="94d37-143">未知錯誤</span><span class="sxs-lookup"><span data-stu-id="94d37-143">Unknown errors</span></span> | <span data-ttu-id="94d37-144">因為未知原因，所以查詢失敗。</span><span class="sxs-lookup"><span data-stu-id="94d37-144">The query failed because of an unknown reason.</span></span> | <span data-ttu-id="94d37-145">請嘗試再次執行查詢。</span><span class="sxs-lookup"><span data-stu-id="94d37-145">Try running the query again.</span></span> <span data-ttu-id="94d37-146">如果查詢繼續傳回未知錯誤，請透過入口網站與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="94d37-146">Contact Microsoft through the portal if queries continue to return unknown errors.</span></span> | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a><span data-ttu-id="94d37-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="94d37-147">Related topics</span></span>
- [<span data-ttu-id="94d37-148">高級搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="94d37-148">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="94d37-149">配額和使用量參數</span><span class="sxs-lookup"><span data-stu-id="94d37-149">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="94d37-150">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="94d37-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="94d37-151">Kusto 查詢語言概述</span><span class="sxs-lookup"><span data-stu-id="94d37-151">Kusto Query Language overview</span></span>](/azure/data-explorer/kusto/query/)