---
title: 瞭解 Microsoft 365 Defender 中的進位搜尋查詢語言
description: 建立您的第一個威脅搜捕查詢，並了解常用的運算子和進階搜捕查詢語言的其他概念
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、語言、學習、第一個查詢、遙測、事件、遙測、自訂偵測、架構、kusto、運算子、資料類型、PowerShell 下載、查詢範例
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
ms.openlocfilehash: 41341a2b5238485fc58021fe4af71cd5c635352c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929799"
---
# <a name="learn-the-advanced-hunting-query-language"></a>了解進階搜捕查詢語言

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進階搜捕是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎。 您可以使用 Kusto 運算子和語句來建構在特殊架構中尋找資訊的 [查詢](advanced-hunting-schema-tables.md)。 若要深入了解這些概念，請執行您的第一個查詢。

## <a name="try-your-first-query"></a>嘗試您的第一個查詢

在 Microsoft 365 資訊安全中心，請前往搜尋 **以** 執行第一個查詢。 請使用下列範例：

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

**[以進位搜尋執行此查詢](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>描述查詢並指定要搜尋的資料表
查詢的開頭已加入簡短的批註，說明查詢的用詞。 如果您稍後決定儲存查詢並與他人共用，此批註會有所説明。 

```kusto
// Finds PowerShell execution events that could involve a download
```

查詢本身一般會從資料表名稱開始，後面接著以 `|` () 。 在此範例中，我們先建立兩個數據表的聯聯，然後，然後根據需要新增  `DeviceProcessEvents` `DeviceNetworkEvents` 管道元素。

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>設定時間範圍
第一個管道元素是限制過去七天的時間篩選。 限制時間範圍可協助確保查詢執行良好、可管理的結果，而且不會浪費時間。

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>檢查特定程式
在時間範圍內，後面緊接著搜尋代表 PowerShell 應用程式的程式檔案名。

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>搜尋特定命令字串
之後，查詢會尋找命令列中的字串，這些字串通常是使用 PowerShell 下載檔案。

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

### <a name="customize-result-columns-and-length"></a>自訂結果欄和長度 
現在您的查詢已清楚地識別出您想要尋找的資料，您可以定義結果的外觀。 `project` 會返回特定欄 `top` ，並限制結果數量。 這些運算子可協助確保結果的格式正確，且相當大且容易處理。

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

選取 **執行查詢** 以查看結果。 使用查詢編輯器右上角的展開圖示來專注于搜尋查詢和結果。 

![進位查詢編輯器中的展開控制項圖像](../../media/advanced-hunting-expand.png)

>[!TIP]
>您可以用圖表來查看查詢結果，並快速調整篩選。 請參閱關於 [使用查詢結果的指南](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>瞭解一般查詢運算子

您只執行第一個查詢，並概觀其元件。 現在該稍微回溯一下，並學習一些基本知識了。 進階搜捕所使用的 Kusto 查詢語言支援一系列運算子，包括下列常見運算子。

| 運算子 | 描述及用法 |
|--|--|
| `where` | 將資料表篩選為符合述詞的資料列子集。 |
| `summarize` | 產生匯總輸入資料表內容的資料表。 |
| `join` | 合併兩個資料表的資料列，並比對每個資料表中的指定資料行的值來建立新的資料表。 |
| `count` | 傳回輸入記錄集中的記錄數目。 |
| `top` | 傳回按指定資料行排序的前 N 筆記錄。 |
| `limit` | 傳回指定的資料列數。 |
| `project` | 選取要包含的資料行、重新命名或捨棄，然後插入新的計算資料行。 |
| `extend` | 建立計算資料行並將它們附加到結果集中。 |
| `makeset` |  傳回 Expr 在群組中取得的獨特值集合的動態 (JSON) 陣列。 |
| `find` | 在一組資料表中尋找符合述詞的資料列。 |

若要查看這些運算子的實際範例，請從進階搜捕的 [開始使用] 區段中執行這些運算子。

## <a name="understand-data-types"></a>瞭解資料類型

進位搜尋支援 Kusto 資料類型，包括下列常見類型：

| 資料類型 | 描述與查詢含意 |
|--|--|
| `datetime` | 資料和時間資訊通常代表事件時間戳記。 [查看支援的日期時間格式](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | UTF-8 中的字元字串會以單引號括 () `'` 或雙引號括 `"` () 。 [閱讀更多有關字串](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | 此資料類型支援 `true` 或 `false` 狀態。 [查看支援文字和運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32 位整數  |
| `long` | 64 位整數 |

若要深入瞭解這些資料類型， [請閱讀 Kusto scalar 資料類型](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)。

## <a name="get-help-as-you-write-queries"></a>編寫查詢時取得協助
運用下列功能更快速地編寫查詢：
- **自動建議**- 當您撰寫查詢時，進位搜尋會提供 IntelliSense 的建議。 
- **架構樹**—包含資料表清單及其資料行的架構標記法，會提供在工作區域旁。 如需詳細資訊，請將游標暫留在某項目上。 按兩下某個項目，將它插入查詢編輯器。
- **[架構參照](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— 包含資料表與資料行描述的入口網站內參照，以及支援的事件種類 (`ActionType` 查詢) 範例查詢

## <a name="work-with-multiple-queries-in-the-editor"></a>在編輯器中使用多個查詢
您可以使用查詢編輯器來嘗試多個查詢。 若要使用多個查詢：

- 以空白行分隔每個查詢。
- 將游標放在查詢的任何部分，以選取該查詢再執行。 這只會執行選取的查詢。 若要執行另一個查詢，請據此移動游標，然後選取執行 **查詢**。

![具有多個查詢的查詢編輯器圖像](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>使用範例查詢

[開始使用] 區段提供一些使用常用運算子的簡單查詢。 嘗試執行這些查詢，並對它們進行些微修改。

![進階搜捕視窗的影像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>除了基本查詢範例以外，您也可以取得適用於特定威脅搜捕案例的[共用查詢](advanced-hunting-shared-queries.md)。 探索頁面左側或 GitHub 查詢存放庫 [左側的共用查詢](https://aka.ms/hunting-queries)。

## <a name="access-query-language-documentation"></a>Access 查詢語言說明文件

如需有關 Kusto 查詢語言和支援運算子的詳細資訊，請參閱 [Kusto 查詢語言說明文件](https://docs.microsoft.com/azure/kusto/query/)。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
