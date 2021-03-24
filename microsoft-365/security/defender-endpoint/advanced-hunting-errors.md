---
title: 在 Microsoft Defender ATP 的高級搜尋中處理錯誤
description: 瞭解使用高級搜尋時所顯示的錯誤
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp、m365、搜尋、查詢、遙測、架構、kusto、timeout、資源、錯誤、不明錯誤
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 64c8a13ba9e8110d761245315969b9e1882b3448
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059999"
---
# <a name="handle-advanced-hunting-errors"></a>處理高級搜尋錯誤

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

「高級搜尋」顯示錯誤，以通知語法錯誤，以及每當查詢命中 [預先定義的限制](advanced-hunting-limits.md)。 請參閱下表，以取得如何解決或避免錯誤的秘訣。 

| 錯誤類型 | 原因 | 解決方案 | 錯誤訊息範例 |
|--|--|--|--|
| 語法錯誤 | 查詢包含無法辨識的名稱，包括對不存在運算子、欄、函數或資料表的參照。 | 請確定 [Kusto 運算子和函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 的參照正確無誤。 檢查正確的高級搜尋欄、函數及資料表的 [架構](advanced-hunting-schema-reference.md) 。 以引號括住變數字串，以便加以識別。 撰寫查詢時，請使用來自 IntelliSense 的自動完成建議。 | `A recognition error occurred.` |
| 語意錯誤 | 雖然查詢使用有效的運算子、欄、函數或資料表名稱，但其結構及產生的邏輯都有錯誤。 在某些情況下，高級搜尋會識別導致錯誤的特定運算子。 | 檢查查詢結構中是否有錯誤。 如需指引，請參閱 [Kusto 檔](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 。 撰寫查詢時，請使用來自 IntelliSense 的自動完成建議。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| 超時 | 查詢只能在 [有限的期限](advanced-hunting-limits.md)內執行超時之前。執行複雜查詢時，可能會發生此錯誤。 | [優化查詢](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 節流 | 相同承租人中的查詢已超過根據租使用者規模所分配的 [CPU 資源](advanced-hunting-limits.md) 。 | 服務每隔15分鐘檢查一次 CPU 資源使用狀況，並在使用量超過所分配之限制的10% 時顯示警告。 如果您達到100% 的使用率，該服務會封鎖查詢，直到下一天或15分鐘週期之後。 [優化您的查詢以避免命中 CPU 限制](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 超過結果大小限制  | 查詢結果集的匯總大小已超過上限。 如果結果集是如此大的錯誤，且在10000記錄的限制下截斷，則可能會發生這個錯誤。 具有可調內容之多個欄的結果，可能會受到此錯誤影響。 | [優化查詢](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 過度資源消耗 | 查詢已消耗過大量的資源，且已停止完成。 在某些情況下，高級搜尋會識別未優化的特定運算子。 | [優化查詢](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 未知錯誤 | 因為未知原因，所以查詢失敗。 | 請嘗試再次執行查詢。 如果查詢繼續傳回未知錯誤，請透過入口網站與 Microsoft 聯繫。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>相關主題
- [高級搜尋最佳作法](advanced-hunting-best-practices.md)
- [服務限制](advanced-hunting-limits.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [Kusto 查詢語言概述](https://docs.microsoft.com/azure/data-explorer/kusto/query/)