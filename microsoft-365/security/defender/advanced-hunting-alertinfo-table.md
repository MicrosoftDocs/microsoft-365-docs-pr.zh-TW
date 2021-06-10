---
title: Advanced 搜尋架構中的 AlertInfo 表格
description: 深入瞭解高級搜尋架構的 AlertInfo 資料表中的警示產生事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，MITRE，ATT&CK，microsoft defender for Endpoint，microsoft defender for Office 365，Microsoft Cloud App Security，MCAS，以及 microsoft defender 身分識別
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933694"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender



[！附注] `AlertInfo` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含 microsoft defender for Endpoint、microsoft defender for Office 365、Microsoft Cloud App Security 和 Microsoft defender for Identity 的警示資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `AlertId` | 字串 | 警示的唯一識別碼。 |
| `Title` | 字串 | 警示標題 |
| `Category` | 字串 | 輸入由警示所識別的威脅指示器或入侵活動類型 |
| `Severity` | 字串 | 表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低) |
| `ServiceSource` | 字串 | 提供提醒資訊的產品或服務 |
| `DetectionSource` | string | 識別值得注意之元件或活動的偵測技術或感應器 |
| `AttackTechniques` | string | MITRE ATT&與觸發警示之活動相關聯的 CK 技術 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
