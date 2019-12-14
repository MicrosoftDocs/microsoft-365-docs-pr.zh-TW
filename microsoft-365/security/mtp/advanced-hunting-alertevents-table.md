---
title: 進階搜捕結構描述中的 AlertEvents 表格
description: 了解進階搜捕結構描述之 AlertEvents 表格中的警示產生事件
keywords: 進階搜捕、威脅搜捕、網路威脅搜捕、搜尋、查詢、遙測、結構描述參考、kusto、表格、欄、資料類型、描述、alertevents、警示、嚴重性、類別
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
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910921"
---
# <a name="alertevents"></a>AlertEvents

**適用範圍：**
- Microsoft 威脅防護

[!include[Prerelease information](prerelease.md)]

[進階搜捕](advanced-hunting-overview.md)結構描述中的 `AlertEvents` 表格包含有關 Microsoft Defender ATP 警示的資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `AlertId` | 字串 | 警示的唯一識別碼。 |
| `EventTime` | datetime | 事件記錄的日期和時間。 |
| `MachineId` | 字串 | 服務中電腦的唯一識別碼 |
| `ComputerName` | 字串 | 電腦的完整網域名稱 (FQDN) |
| `Severity` | 字串 | 表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低) |
| `Category` | 字串 | 輸入由警示所識別的威脅指示器或入侵活動類型 |
| `Title` | 字串 | 警示標題 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一事件，此欄必須與 ComputerName 和 EventTime 欄搭配使用 |
| `Table` | 字串 | 含有事件詳細資料的表格 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
