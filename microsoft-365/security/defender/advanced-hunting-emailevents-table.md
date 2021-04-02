---
title: 進階搜捕結構描述中的 EmailEvents 表格
description: 深入瞭解在高級搜尋架構的 EmailEvents 表格中與 Microsoft 365 電子郵件相關的事件
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、EmailEvents、網路郵件 id、寄件者、收件者、附件識別碼、附件計數、url 計數、url 計數
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
ms.openlocfilehash: 460668c281dff378867a721f4e3635a36cb590e2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498901"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用範圍：**

- Microsoft 365 Defender

[！附注] `EmailEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含有關在 Microsoft Defender for Office 365 上處理電子郵件之事件的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的內建架構參照。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `NetworkMessageId` | string | Microsoft 365 產生之電子郵件的唯一識別碼 |
| `InternetMessageId` | 字串 | 透過傳送電子郵件系統所設定之電子郵件的公開識別碼 |
| `SenderMailFromAddress` | 字串 | [郵件寄件者] 標頭中的寄件者電子郵件地址，又稱為信封寄件者或退回路徑位址 |
| `SenderFromAddress` | 字串 | 電子郵件用戶端上的電子郵件收件者看得到 [寄件者] 標題中的寄件者電子郵件地址 |
| `SenderDisplayName` | 字串 | 顯示在通訊錄中之寄件者的名稱，通常是指定或名字、中間名首字母的組合，以及姓氏或姓的組合 |
| `SenderObjectId` | string |Azure AD 中寄件者帳戶的唯一識別碼 |
| `SenderMailFromDomain` | 字串 | [郵件寄件者] 標頭中的寄件者網域，也稱為信封寄件者或退回路徑位址 |
| `SenderFromDomain` | 字串 | [寄件者] 標頭中的寄件者網域，可對電子郵件用戶端上的電子郵件收件者顯示 |
| `SenderIPv4` | 字串 | 轉送郵件的最後偵測郵件伺服器的 IPv4 位址 |
| `SenderIPv6` | 字串 | 轉送郵件的最後偵測郵件伺服器的 IPv6 位址 |
| `RecipientEmailAddress` | 字串 | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `RecipientObjectId` | 字串 | Azure AD 中電子郵件收件者的唯一識別碼 |
| `Subject` | 字串 | 電子郵件的主旨 |
| `EmailClusterId` | 字串 | 根據內容啟發式分析叢集的類似電子郵件群組識別碼 |
| `EmailDirection` | 字串 | 相對於您的網路的電子郵件方向：內送、外寄、組織內部 |
| `DeliveryAction` | 字串 | 電子郵件的傳遞動作：已傳送、已標示為垃圾郵件、已封鎖或已取代 |
| `DeliveryLocation` | 字串 | 傳送電子郵件的位置：收件匣/資料夾、內部部署/外部、垃圾郵件、隔離、失敗、已中斷、刪除的郵件 |
| `ThreatTypes` | 字串 | 從電子郵件篩選棧中判定電子郵件是否包含惡意程式碼、網路釣魚或其他威脅 |
| `ThreatNames` | string |找到惡意程式碼或其他威脅的偵測名稱 |
| `DetectionMethods` | string | 用於偵測電子郵件中所發現之惡意程式碼、網路釣魚或其他威脅的方法 |
| `ConfidenceLevel` | string | 任何垃圾郵件或網路釣魚 verdicts 的信賴層級清單。 若為垃圾郵件，此欄會顯示「垃圾郵件信賴等級」 (SCL) ，指出是否已略過電子郵件 (-1) ，發現不是垃圾郵件 (0，1) ，發現是具有適中信心的垃圾郵件， (5、6) ，或發現是具有高可信度的垃圾郵件 (9) 。 若為網路釣魚，此欄會顯示信賴等級為 "High" 或 "Low"。 |
| `EmailAction` | 字串 | 以篩選決策、原則和使用者動作為基礎的最終電子郵件執行動作：將郵件移至垃圾郵件資料夾、新增 X 標頭、修改主旨、重新導向郵件、刪除郵件、傳送至隔離、未採取任何動作、密件副本郵件 |
| `EmailActionPolicy` | 字串 | 生效的動作原則：反垃圾郵件 - 高信賴度、反垃圾郵件、反垃圾郵件 - 大宗郵件、反垃圾郵件 - 網路釣魚、反網路釣魚網域模擬、反網路釣魚使用者模擬、反網路釣魚詐騙、反網路釣魚圖形模擬、反惡意程式碼、安全附件、企業傳輸規則 (ETR) |
| `EmailActionPolicyGuid` | 字串 | 決定最終郵件動作的原則的唯一識別碼 |
| `AttachmentCount` | int | 電子郵件的附件數量 |
| `UrlCount` | int | 電子郵件的內嵌 URL 數量 |
| `EmailLanguage` | 字串 | 偵測到的電子郵件內容語言 |
| `Connectors` | string | 定義組織郵件流程的自訂指示，以及如何路由傳送電子郵件 |
| `OrgLevelAction` | string | 對電子郵件採取的動作，以回應組織層級定義的原則的符合專案 |
| `OrgLevelPolicy` | string | 觸發對電子郵件採取之動作的組織原則 |
| `UserLevelAction` | string | 對電子郵件採取的動作，以回應由收件者所定義的信箱原則的相符專案 |
| `UserLevelPolicy` | string | 觸發對電子郵件採取之動作的使用者信箱原則 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。 |

## <a name="related-topics"></a>相關主題

- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
