---
title: Advanced 搜尋架構中的 AlertInfo 表格
description: 深入瞭解高級搜尋架構的 AlertInfo 資料表中的警示產生事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，MITRE，ATT&CK，Microsoft Defender ATP，MDATP，Office 365 ATP，Microsoft Cloud App Security，MCAS，and Azure ATP
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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929513"
---
# <a name="alertinfo"></a>AlertInfo

適用於：****
- Microsoft 威脅防護



[ `AlertInfo` ！附注][高級搜尋](advanced-hunting-overview.md)架構中的表格包含來自 Microsoft Defender ATP、Office 365 Atp、Microsoft Cloud APP Security 和 Azure atp 的提醒資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `AlertId` | string | 警示的唯一識別碼。 |
| `Title` | 字串 | 警示標題 |
| `Category` | 字串 | 輸入由警示所識別的威脅指示器或入侵活動類型 |
| `Severity` | string | 表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低) |
| `ServiceSource` | string | 提供提醒資訊的產品或服務 |
| `DetectionSource` | string | 識別值得注意之元件或活動的偵測技術或感應器 |
| `AttackTechniques` | string | MITRE ATT&與觸發警示之活動相關聯的 CK 技術 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
