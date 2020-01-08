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
ms.openlocfilehash: 97c5f5541e1c3293346a53d87b950121e85e6eae
ms.sourcegitcommit: 72d0280c2481250cf9114d32317ad2be59ab6789
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40966863"
---
# <a name="advanced-hunting-query-best-practices"></a>進階搜捕查詢最佳做法

**適用於：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a>最佳化查詢效能
套用這些建議來加快取得結果，並避免在執行複雜查詢時發生逾時：
- 嘗試新的查詢時，一律使用 `limit` 來避免極度龐大的結果集。 您也可以一開始使用 `count` 來評估結果集的大小。
- 首先使用時間篩選。 在理想情況下，將查詢限制為偶數日。
- 將預期會刪除大多數資料的篩選放在時間篩選之後的查詢開頭。
- 尋找完整標記時，請在 `contains`上使用 `has`運算子。
- 尋找特定欄位，而不是在所有欄位執行全文搜尋。
- 結合表格時，先指定含有較少列的表格。
- `project` 僅限已結合的表格所需的欄位。

>[!Tip]
>如需提高查詢效能的更多指導方針，請參閱 [Kusto 查詢最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。

## <a name="query-tips-and-pitfalls"></a>查詢祕訣與陷阱

### <a name="queries-with-process-ids"></a>含有程序識別碼的查詢
程序識別碼 (PID) 會在 Windows 中回收，並針對新程序重複使用。 它們本身不能充當特定程序的唯一識別碼。

若要為特定電腦上的程序取得唯一識別碼，請使用程序識別碼與程序建立時間。 結合或摘要處理程序中的資料時，需包含電腦識別碼的欄位 (`DeviceId` 或 `DeviceName`)、程序識別碼 (`ProcessId` 或 `InitiatingProcessId`) 以及程序建立時間 (`ProcessCreationTime` 或 `InitiatingProcessCreationTime`)

下列範例查詢發現透過連接埠 445 (SMB) 存取 10 個以上 IP 位址的程序，可能是因為掃描檔案共用。

例如查詢：
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

查詢會以 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 進行彙總，因此它會檢查單一程序，而不會將多個具有相同程序識別碼的程序混合在一起。

### <a name="queries-with-command-lines"></a>含有命令列的查詢

命令列可能會有所不同。 若適用，請篩選檔案名稱並執行模糊比對。

有許多方法可以建構命令列來完成工作。 例如，攻擊者會參照影像檔 (無論是否有路徑、無附檔名、使用環境變數或使用引號)。 此外，攻擊者也會變更參數順序，或新增多個引號和空格。

若要使用命令列建立更持久的查詢，請套用做法下列做法：

- 藉由按照檔案名稱欄位比對，而非在命令列欄位中進行篩選，以識別已知的程序 (例如 *net.ext* 或 *psexec.exe*)。
- 查詢命令列引數時，請勿以特定順序尋找多個不相關引數上完全相符的內容。 請改用規則運算式或使用多個不同的包含運算子。
- 使用不區分大小寫對比。 例如，使用 `=~`、`in~` 和 `contains` 而不是 `==`、`in` 和 `contains_cs`
- 若要降低 DOS 命令列混淆技術，請考慮移除引號、使用空格代替逗號，以及使用單一空格取代多個連續的空格。 請注意，有更複雜的 DOS 混淆技術需要其他降低方法，但這些方法可協助處理最常見的問題。

下列範例說明建構查詢的幾種方法，可尋找 *net.exe* 檔案以停止 Windows Defender 防火牆服務：

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
## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
