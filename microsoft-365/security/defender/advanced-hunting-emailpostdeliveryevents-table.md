---
title: Advanced 搜尋架構中的 EmailPostDeliveryEvents 表格
description: 深入瞭解在高級搜尋架構的 EmailPostDeliveryEvents 資料表中 Microsoft 365 電子郵件上採取的傳遞動作
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，欄，資料類型，描述、EmailPostDeliveryEvents、網路郵件識別碼、寄件者、收件者、附件識別碼、連結計數、url 計數
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
ms.openlocfilehash: 444af2441eef5a3720325656f996e6bcdb42937e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935470"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[！附注] `EmailPostDeliveryEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含對 Microsoft 365 所處理之電子郵件傳送投遞動作的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的內建架構參照。

若要取得個別電子郵件訊息的詳細資訊，您也可以使用 [`EmailEvents`](advanced-hunting-emailevents-table.md) 、 [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) 和 [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) 資料表。 如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `NetworkMessageId` | string | 電子郵件的唯一識別碼，由 Microsoft 365 產生 |
| `InternetMessageId` | 字串 | 透過傳送電子郵件系統所設定之電子郵件的公開識別碼 |
| `Action` | 字串 | 對實體採取的動作 |
| `ActionType` | string | 觸發事件的活動類型：手動修復、網路釣魚 ZAP、惡意程式碼 ZAP |
| `ActionTrigger` | string | 會指出管理員是由系統管理員所觸發的動作，還是透過待處理的自動動作) 或某些特殊的機制（例如 ZAP 或動態傳遞）進行核准 ( |
| `ActionResult` | string | 動作的結果 |
| `RecipientEmailAddress` | 字串 | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `DeliveryLocation` | 字串 | 傳送電子郵件的位置：收件匣/資料夾、內部部署/外部、垃圾郵件、隔離、失敗、已中斷、刪除的郵件 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。 |

## <a name="supported-event-types"></a>支援的事件種類
此表格會捕獲具有下列值的事件 `ActionType` ：

- **手動修正** –系統管理員會在電子郵件傳送至使用者信箱後，手動對該電子郵件採取動作。 這包括透過 [威脅瀏覽器](../office-365-security/threat-explorer.md) 手動採取的動作，或核准 [ (AIR) 動作的自動調查和回應](m365d-autoir-actions.md)。
- **網路釣魚 ZAP** – [零小時自動清除 (ZAP)](../office-365-security/zero-hour-auto-purge.md) 會在傳送後對網路釣魚電子郵件採取動作。
- **惡意程式碼 ZAP** –零小時自動清除 (ZAP) 在傳送後，包含惡意程式碼的電子郵件上採取的動作。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
