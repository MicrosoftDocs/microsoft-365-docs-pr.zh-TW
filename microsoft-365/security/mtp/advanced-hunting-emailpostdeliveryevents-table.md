---
title: Advanced 搜尋架構中的 EmailPostDeliveryEvents 表格
description: 深入瞭解在 Microsoft 365 電子郵件的高級搜尋架構 EmailPostDeliveryEvents 表格中所進行的傳遞動作
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、EmailPostDeliveryEvents、網路郵件 id、寄件者、收件者、附件識別碼、附件計數、url 計數、url 計數
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
ms.openlocfilehash: f4b34abdbfcbd6c3a2f142001a3d486485c86fcd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515912"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[！附注] `EmailPostDeliveryEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含對 Microsoft 365 所處理之電子郵件所採取之投遞後動作的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

若要取得個別電子郵件訊息的詳細資訊，您也可以使用 [`EmailEvents`](advanced-hunting-emailevents-table.md) 、 [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) 和 [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) 資料表。 如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `EventId` | string | 事件的唯一識別碼 |
| `NetworkMessageId` | string | Microsoft 365 產生之電子郵件的唯一識別碼 |
| `InternetMessageId` | string | 透過傳送電子郵件系統所設定之電子郵件的公開識別碼 |
| `Action` | string | 對實體採取的動作 |
| `ActionType` | string | 觸發事件的活動類型：手動修復、網路釣魚 ZAP、惡意程式碼 ZAP |
| `ActionTrigger` | string | 會指出是由系統管理員觸發動作（手動或透過待處理的自動動作進行核准），還是由某些特殊的機制（如 ZAP 或動態傳遞） |
| `ActionResult` | string | 動作的結果 |
| `RecipientEmailAddress` | string | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `DeliveryLocation` | 字串 | 傳送電子郵件的位置：收件匣/資料夾、內部部署/外部、垃圾郵件、隔離、失敗、已中斷、刪除的郵件 |

## <a name="supported-event-types"></a>支援的事件種類
此表格會捕獲具有下列值的事件 `ActionType` ：

- **手動修正**–系統管理員會在電子郵件傳送至使用者信箱後，手動對該電子郵件採取動作。 這包括透過[威脅瀏覽器](../office-365-security/threat-explorer.md)手動採取的動作[，或自動調查和回應（AIR）動作](mtp-autoir-actions.md)的核准。
- **網路釣魚 ZAP** –[零小時自動清除（ZAP）](../office-365-security/zero-hour-auto-purge.md)在傳送後採取網路釣魚電子郵件的動作。
- **惡意程式碼 ZAP** –零小時自動清除（ZAP）採取的方式是在傳送後包含惡意程式碼的電子郵件上採取的動作。

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)