---
title: 進位搜尋架構中的 EmailPostDeliveryEvents 資料表
description: 瞭解在進位搜尋架構的 EmailPostDeliveryEvents 資料表中對 Microsoft 365 電子郵件採取的動作
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、資料表、資料行、資料類型、描述、EmailPostiveryEvents、網路訊息識別碼、寄件者、收件者、附件識別碼、附件名稱、惡意程式碼攻擊、網路釣魚網路釣魚、附件計數、連結計數、URL 計數
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
ms.openlocfilehash: d7920be05156320411f3907cbcdae88d315b5136
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929703"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進 `EmailPostDeliveryEvents` 位搜尋架構 [中的](advanced-hunting-overview.md) 表格包含 Microsoft 365 處理之電子郵件訊息的傳遞後動作相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

若要取得個別電子郵件訊息詳細資訊，您也可以使用 [`EmailEvents`](advanced-hunting-emailevents-table.md) ， [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) 及 [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) 表格。 如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `EventId` | string | 事件的唯一識別碼 |
| `NetworkMessageId` | string | Microsoft 365 產生之電子郵件的唯一識別碼 |
| `InternetMessageId` | 字串 | 透過傳送電子郵件系統所設定之電子郵件的公開識別碼 |
| `Action` | 字串 | 對實體採取的動作 |
| `ActionType` | string | 觸發事件的活動類型：手動修復、Phish ZAP、Malware ZAP |
| `ActionTrigger` | string | 指出由系統管理員手動或 (或透過核准擱置的自動化動作) 觸發的動作，或由一些特殊機制觸發，例如 ZAP 或動態傳遞 |
| `ActionResult` | string | 動作的結果 |
| `RecipientEmailAddress` | 字串 | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `DeliveryLocation` | 字串 | 傳送電子郵件的位置：收件匣/資料夾、內部部署/外部、垃圾郵件、隔離、失敗、已中斷、刪除的郵件 |

## <a name="supported-event-types"></a>支援的事件種類
下表會使用下列值來捕捉 `ActionType` 事件：

- **手動修復** – 系統管理員在電子郵件訊息傳遞到使用者信箱之後，手動執行動作。 這包括透過威脅庫手動採取的動作[](../office-365-security/threat-explorer.md)，或經過 AIR ([自動化調查與) 核准](mtp-autoir-actions.md)。
- **網路釣魚 ZAP** [：ZAP](../office-365-security/zero-hour-auto-purge.md) (0 小時自動清除) 在傳送後對網路釣魚電子郵件執行動作。
- **Malware ZAP** – ZAP (0 小時自動清除) 對在傳遞後發現含有惡意攻擊的電子郵件執行動作。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
