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
ms.openlocfilehash: acc515d046b1ebd2ff7c5dd9c52b363fe99f0b9e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087457"
---
# <a name="learn-the-advanced-hunting-query-language"></a>了解進階搜捕查詢語言

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

進階搜捕是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎。 您可以使用 Kusto 語法和運算子來建立查詢，以在特別為進階搜捕而建構的[結構描述](advanced-hunting-schema-tables.md)中尋找的資訊。 若要深入了解這些概念，請執行您的第一個查詢。

## <a name="try-your-first-query"></a>嘗試您的第一個查詢

在 Microsoft 365 安全性中心中，移至 [搜捕]**** 以執行您的第一個查詢。 請使用下列範例：

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

這是它在進階搜捕中看起來的樣子。

![Microsoft Defender ATP 進階搜捕查詢的影像](../../media/advanced-hunting-query-example.png)

查詢會從描述其用途的簡短註解開始。 如果您後來決定要儲存查詢，並與組織中的其他人共用，這會有所幫助。

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

查詢本身通常會以資料表名稱開頭，後面接著管道 (`|`) 開始的一系列元素。 在此範例中，我們首先使用資料表名稱 `DeviceProcessEvents` 來新增，並視需要新增管道元素。

第一個管道元素是範圍在過去七天內的時間篩選條件。 盡可能讓時間範圍越小越好，以確保查詢能順利執行、傳回可管理的結果，且不會逾時。

```kusto
| where Timestamp > ago(7d)
```

在時間範圍之後會緊接著代表 PowerShell 應用程式的檔案搜尋。

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

之後，查詢會尋找通常用於 PowerShell 的命令列來下載檔案。

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

現在您的查詢已清楚識別出您要尋找的資料，您可以新增元素來定義結果。 `project` 會傳回特定資料行，`top` 會限制結果的數目，讓結果的格式正確、數量合理且容易處理。

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

按一下 [執行查詢]**** 以查看結果。 您可以展開畫面檢視，讓您專注在您的搜捕查詢和結果。

## <a name="learn-common-query-operators-for-advanced-hunting"></a>了解適用於進階搜捕的一般查詢運算子

您已執行了第一個查詢，並對其組成元素有一點了解了，現在可以開始追蹤一些基本概念。 進階搜捕所使用的 Kusto 查詢語言支援一系列運算子，包括下列常見運算子。

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

若要查看這些運算子的實際範例，請從進階搜捕的 [開始使用]**** 區段中執行這些運算子。

## <a name="understand-data-types-and-their-query-syntax-implications"></a>了解資料類型及其查詢語法含意

進階搜捕資料表中的資料通常會分類為以下資料類型。

| 資料類型 | 描述與查詢含意 |
|--|--|
| `datetime` | 通常代表事件時間戳記的資料和時間資訊 |
| `string` | 字元字串 |
| `bool` | True 或 False |
| `int` | 32 位元數值  |
| `long` | 64 位元數值 |

## <a name="use-sample-queries"></a>使用範例查詢

[開始使用]**** 區段提供一些使用常用運算子的簡單查詢。 嘗試執行這些查詢，並對它們進行些微修改。

![進階搜捕視窗的影像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>除了基本查詢範例以外，您也可以取得適用於特定威脅搜捕案例的[共用查詢](advanced-hunting-shared-queries.md)。 探索頁面左側或 GitHub 查詢儲存庫的共用查詢。

## <a name="access-query-language-documentation"></a>Access 查詢語言說明文件

如需有關 Kusto 查詢語言和支援運算子的詳細資訊，請參閱 [Kusto 查詢語言說明文件](https://docs.microsoft.com/azure/kusto/query/)。

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
