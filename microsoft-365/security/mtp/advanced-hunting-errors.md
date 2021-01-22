---
title: 處理 Microsoft 365 Defender 進位搜尋中的錯誤
description: 瞭解使用進位搜尋時顯示的錯誤
keywords: 進位搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構、kusto、timeout、資源、錯誤、未知錯誤、限制、配額、參數、配置
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
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929643"
---
# <a name="handle-advanced-hunting-errors"></a>處理進位搜尋錯誤

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


進位搜尋會顯示錯誤，以通知語法錯誤，每當查詢達到[預先定義的配額和使用量參數時。](advanced-hunting-limits.md) 請參閱下表，以瞭解如何解決或避免錯誤的秘訣。

| 錯誤類型 | 原因 | 解決方案 | 錯誤訊息範例 |
|--|--|--|--|
| 語法錯誤 | 查詢包含無法辨識的名稱，包括參照非運算子、資料行、函數或資料表。 | 確保 [參照到 Kusto 運算子和](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 函數正確無誤。 檢查 [正確進](advanced-hunting-schema-tables.md) 位搜尋欄、函數和表格的架構。 以引號括住變數字串，以便識別這些字串。 撰寫查詢時，請使用 IntelliSense 的自動完成建議。 | `A recognition error occurred.` |
| 語式錯誤 | 當查詢使用有效的運算子、資料行、函數或資料表名稱時，其結構及產生的邏輯會發生錯誤。 在某些情況下，進位搜尋會識別導致錯誤的特定運算子。 | 檢查查詢結構的錯誤。 請參閱 [Kusto 檔以](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 尋求指引。 撰寫查詢時，請使用 IntelliSense 的自動完成建議。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| 超時 | 查詢只能在限定時間內 [執行，才能在計時之前執行](advanced-hunting-limits.md)。執行複雜的查詢時，可能會更頻繁地發生此錯誤。 | [優化查詢](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 節流 | 同一租使用者中的查詢已超過根據租[](advanced-hunting-limits.md)使用者大小配置 CPU 資源。 | 此服務每 15 分鐘和每天檢查 CPU 資源使用量，並且會在使用量超過已配置配額的 10% 時顯示警告。 如果您達到 100% 的使用率，服務會進行查詢，直到下一個每天或 15 分鐘迴圈之後。 [優化您的查詢以避免達到 CPU 配額](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 超出結果大小限制  | 查詢的結果集匯總大小已超過上限。 如果結果集太大，以 10，000 記錄限制截斷，但無法將結果集縮減到可接受的大小，就可能會發生此錯誤。 具有大量內容之多個欄的結果較容易受此錯誤影響。 | [優化查詢](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 過度資源耗用 | 查詢已耗用過多資源，而且已停止完成。 在某些情況下，進一步搜尋會識別未優化的特定運算子。 | [優化查詢](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 未知的錯誤 | 查詢失敗的原因不明。 | 再次嘗試執行查詢。 如果查詢繼續傳回未知的錯誤，請透過入口網站與 Microsoft 聯繫。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>相關主題
- [進位搜尋最佳作法](advanced-hunting-best-practices.md)
- [配額和使用量參數](advanced-hunting-limits.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [Kusto Query 語言概觀](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
