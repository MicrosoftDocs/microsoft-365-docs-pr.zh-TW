---
title: 進階搜捕結構描述中的 EmailUrlInfo 表格
description: 了解進階搜捕結構描述之 EmailUrlInfo 表格中的 URL 或連結資訊
keywords: 進階搜捕, 威脅搜捕, 網路威脅搜捕, 搜尋, 查詢, 遙測, 結構描述參考, kusto, 表格, 欄, 資料類型, 描述, EmailUrlInfo, 網路訊息識別碼, URL, 連結
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
ms.openlocfilehash: da9712d1f3465c28d2ba880997a52434723a297d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808668"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**適用於：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[進階搜捕](advanced-hunting-overview.md)結構描述中的 `EmailUrlInfo` 表格包含有關 Office 365 ATP 所處理的電子郵件和附件 URL 資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `UrlId` | string | 電子郵件主旨、內文或附件中 URL 的唯一識別碼 |
| `NetworkMessageId` | string | Office 365 產生的電子郵件唯一識別碼 |
| `Url` | string | 電子郵件主旨、內文或附件中的完整 URL |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)