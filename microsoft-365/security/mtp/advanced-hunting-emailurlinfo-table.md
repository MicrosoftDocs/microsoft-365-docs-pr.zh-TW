---
title: 進階搜捕結構描述中的 EmailUrlInfo 表格
description: 了解進階搜捕結構描述之 EmailUrlInfo 表格中的 URL 或連結資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，EmailUrlInfo，網路郵件識別碼，url，連結
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2d37868af5c582512b543c1e2ca859e63b190425
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430832"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 威脅防護

[進階搜捕](advanced-hunting-overview.md)結構描述中的 `EmailUrlInfo` 表格包含有關 Office 365 ATP 所處理的電子郵件和附件 URL 資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `UrlId` | string | 電子郵件主旨、內文或附件中 URL 的唯一識別碼 |
| `NetworkMessageId` | string | Microsoft 365 產生之電子郵件的唯一識別碼 |
| `Url` | string | 電子郵件主旨、內文或附件中的完整 URL |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
