---
title: 了解進階搜捕查詢語言
description: 建立您的第一個威脅搜捕查詢，並了解常用的運算子和進階搜捕查詢語言的其他概念
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，mdatp，microsoft defender atp，wdatp 搜尋，查詢，語言，學習，第一個查詢，遙測，事件，遙測，自訂偵測，schema，kusto，運算子，資料類型
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
ms.openlocfilehash: 21cea1f661de294aea41ea2c4db21b1aca8a0eec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058824"
---
# <a name="learn-the-advanced-hunting-query-language"></a>了解進階搜捕查詢語言

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

適用於：
- [適用於端點的 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

進階搜捕是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎。 您可以使用 Kusto 運算子和語句來建立在特定 [架構](advanced-hunting-schema-reference.md)中尋找資訊的查詢。 若要深入了解這些概念，請執行您的第一個查詢。

## <a name="try-your-first-query"></a>嘗試您的第一個查詢

在 Microsoft Defender Security Center 中，移至 [ **高級搜尋** ] 以執行第一個查詢。 請使用下列範例：

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
**[在高級搜尋中執行此查詢](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>描述查詢，並指定要搜尋的表格
已將簡短批註新增至查詢的開頭，以描述其用途。 此批註可協助您稍後決定要儲存查詢，並與組織中的其他人共用。

```kusto
// Finds PowerShell execution events that could involve a download
```
查詢本身通常會從資料表名稱開始，並以管道 () 開始數個元素 `|` 。 在此範例中，我們會從建立兩個表格的同盟開始，並  `DeviceProcessEvents` `DeviceNetworkEvents` 視需要新增管線元素。

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>設定時間範圍
第一個輸送的元素是一種範圍設定為前七天的時間篩選器。 限制時間範圍可協助確保查詢順利執行、傳回可管理的結果，而且不會超時。

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>檢查特定進程
時間範圍後緊接著搜尋代表 PowerShell 應用程式的處理常式檔案名。

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>搜尋特定的命令字串
之後，查詢會在命令列中尋找通常用來透過 PowerShell 下載檔案的字串。

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

### <a name="customize-result-columns-and-length"></a>自訂結果欄及長度 
現在，您的查詢會明確識別您想要尋找的資料，您可以定義結果的外觀。 `project` 會傳回特定的欄，並 `top` 限制結果的數目。 這些運算子可協助確保結果具有適當的格式，且易於處理。

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

選取 [ **執行查詢** ] 以查看結果。 使用查詢編輯器右上角的展開圖示，以著重于搜尋查詢和結果。 

![高級搜尋查詢編輯器中的展開控制項影像](images/advanced-hunting-expand.png)

>[!TIP]
>您可以以圖表形式查看查詢結果，並快速調整篩選。 如需相關指導，請 [參閱使用查詢結果](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>了解適用於進階搜捕的一般查詢運算子

您剛剛執行第一個查詢，並大致瞭解其元件。 請稍微進行回溯，並瞭解一些基礎知識。 進階搜捕所使用的 Kusto 查詢語言支援一系列運算子，包括下列常見運算子。

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

若要查看這些操作員的實際範例，請從 [高級搜尋] 頁面的 [ **開始** 使用] 區段中執行。

## <a name="understand-data-types"></a>瞭解資料類型

「高級搜尋」支援 Kusto 資料類型，包括下列通用類型：

| 資料類型 | 描述與查詢含意 |
|--|--|
| `datetime` | 通常代表事件時間戳記的資料和時間資訊。 [請參閱支援的 datetime 格式](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | UTF-8 以單引號括住的字元字串 (`'`) 或雙引號 (`"`) 。 [閱讀更多關於字串的資訊](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | 這種資料類型支援 `true` 或 `false` 狀態。 [請參閱支援的文字及運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32位整數  |
| `long` | 64位整數 |

若要深入瞭解這些資料類型，請 [參閱 Kusto 純量資料型別](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)。

## <a name="get-help-as-you-write-queries"></a>編寫查詢時取得協助
運用下列功能更快速地編寫查詢：

- **Autosuggest**--當您撰寫查詢時，高級搜尋會提供 IntelliSense 的建議。
- **架構樹** 系-您的工作區域旁會提供包含資料表清單和其欄的架構標記法。 如需詳細資訊，請將游標暫留在某項目上。 按兩下某個項目，將它插入查詢編輯器。
- **[架構參考（Schema](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**）包含資料表和欄描述的入口網站內參照，以及支援的事件種類 (`ActionType` 值) 和範例查詢

## <a name="work-with-multiple-queries-in-the-editor"></a>在編輯器中使用多個查詢
您可以使用查詢編輯器來試驗多個查詢。 若要使用多個查詢：

- 以空行分隔每個查詢。
- 將游標放在查詢的任何部分，以選取該查詢，然後再執行它。 這只會執行選取的查詢。 若要執行另一個查詢，請據以移動游標，然後選取 [ **執行查詢**]。

![具有多個查詢的高級搜尋查詢編輯器的影像 ](images/ah-multi-query.png)
 _查詢編輯器_

## <a name="use-sample-queries"></a>使用範例查詢

[開始使用] 區段提供一些使用常用運算子的簡單查詢。 嘗試執行這些查詢，並對它們進行些微修改。

![[高級搜尋入門] 索引標籤的影像](images/atp-advanced-hunting.png)

> [!NOTE]
> 除了基本查詢範例以外，您也可以取得適用於特定威脅搜捕案例的[共用查詢](advanced-hunting-shared-queries.md)。 流覽頁面左側的共用查詢或 [GitHub 查詢存放庫](https://aka.ms/hunting-queries)。

## <a name="access-comprehensive-query-language-reference"></a>存取綜合查詢語言參考

如需查詢語言的詳細資訊，請參閱 [Kusto 查詢語言檔](https://docs.microsoft.com/azure/kusto/query/)。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
