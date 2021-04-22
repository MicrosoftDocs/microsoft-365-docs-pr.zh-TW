---
title: Advanced 搜尋架構中的 DeviceAlertEvents 表格
description: 深入瞭解高級搜尋架構的 DeviceAlertEvents 資料表中的警示產生事件
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、Microsoft Defender for Endpoint、search、query、遙測、schema reference、kusto、table、column、data type、description、DeviceAlertEvents、警示、嚴重性、類別
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: bb2350fed5fadee359695743989e02a3b3e44fb2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935338"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[！附注] `DeviceAlertEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含 Microsoft Defender Security Center 中警示的相關資訊。 使用這個參考來建立從表格取回之資訊的查詢。

如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `AlertId` | 字串 | 警示的唯一識別碼。 |
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `Severity` | 字串 | 表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低) |
| `Category` | 字串 | 輸入由警示所識別的威脅指示器或入侵活動類型 |
| `Title` | 字串 | 警示標題 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `AttackTechniques` | string | MITRE ATT&與觸發警示之活動相關聯的 CK 技術 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用 |
| `Table` | 字串 | 含有事件詳細資料的表格 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
