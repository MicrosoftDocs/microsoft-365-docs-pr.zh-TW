---
title: 進階搜捕結構描述中的 EmailEvents 表格
description: 在進位搜尋架構的 EmailEvents 資料表中瞭解與 Microsoft 365 電子郵件相關聯的事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、EmailEvents、網路訊息識別碼、寄件者、收件者、附件識別碼、附件名稱、惡意程式碼攻擊、網路釣魚網路釣魚者、附件計數、連結計數、URL 計數
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
ms.openlocfilehash: 48a0fe53cb92214d616887741c0c260edf1653c2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928983"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用範圍：**
- Microsoft 365 Defender



進 `EmailEvents` 位搜尋架構 [中的](advanced-hunting-overview.md) 表格包含有關在 Microsoft Defender for Office 365 上處理電子郵件之事件的資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `EmailId` | 字串 | 唯一電子郵件和收件者識別碼 |
| `NetworkMessageId` | 字串 | Microsoft 365 產生之電子郵件的唯一識別碼 |
| `InternetMessageId` | 字串 | 透過傳送電子郵件系統所設定之電子郵件的公開識別碼 |
| `SenderMailFromAddress` | 字串 | [郵件寄件者] 標頭中的寄件者電子郵件地址，又稱為信封寄件者或退回路徑位址 |
| `SenderFromAddress` | 字串 | 電子郵件用戶端上的電子郵件收件者看得到 [寄件者] 標題中的寄件者電子郵件地址 |
| `SenderMailFromDomain` | 字串 | [郵件寄件者] 標頭中的寄件者網域，也稱為信封寄件者或退回路徑位址 |
| `SenderFromDomain` | 字串 | [寄件者] 標頭中的寄件者網域，可對電子郵件用戶端上的電子郵件收件者顯示 |
| `SenderIPv4` | 字串 | 轉送郵件的最後偵測郵件伺服器的 IPv4 位址 |
| `SenderIPv6` | 字串 | 轉送郵件的最後偵測郵件伺服器的 IPv6 位址 |
| `RecipientEmailAddress` | 字串 | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `Subject` | 字串 | 電子郵件的主旨 |
| `EmailClusterId` | 字串 | 根據內容啟發式分析叢集的類似電子郵件群組識別碼 |
| `EmailDirection` | 字串 | 相對於您的網路的電子郵件方向：內送、外寄、組織內部 |
| `DeliveryAction` | 字串 | 電子郵件的傳遞動作：已傳送、已標示為垃圾郵件、已封鎖或已取代 |
| `DeliveryLocation` | 字串 | 傳送電子郵件的位置：收件匣/資料夾、內部部署/外部、垃圾郵件、隔離、失敗、已中斷、刪除的郵件 |
| `PhishFilterVerdict` | 字串 | 決定電子郵件是否為網路釣魚的電子郵件篩選堆疊：網路釣魚或非網路釣魚 |
| `PhishDetectionMethod` | 字串 | 用來偵測電子郵件為網路釣魚的方法：惡意 URL 信譽、安全連結 URL 代理、進紙篩選、一般網路釣魚篩選、反詐騙：Intra-org、反詐騙：外部網域、網域假冒、使用者假冒、品牌假冒 |
| `MalwareFilterVerdict` | 字串 | 決定電子郵件是否包含惡意程式碼的電子郵件篩選堆疊：惡意程式碼或非惡意程式碼 |
| `MalwareDetectionMethod` | 字串 | 用來偵測電子郵件中的惡意攻擊的方法：反惡意軟體引擎、檔案品質、安全附件 |
| `EmailAction` | 字串 | 以篩選決策、原則和使用者動作為基礎的最終電子郵件執行動作：將郵件移至垃圾郵件資料夾、新增 X 標頭、修改主旨、重新導向郵件、刪除郵件、傳送至隔離、未採取任何動作、密件副本郵件 |
| `EmailActionPolicy` | 字串 | 生效的動作原則：反垃圾郵件 - 高信賴度、反垃圾郵件、反垃圾郵件 - 大宗郵件、反垃圾郵件 - 網路釣魚、反網路釣魚網域模擬、反網路釣魚使用者模擬、反網路釣魚詐騙、反網路釣魚圖形模擬、反惡意程式碼、安全附件、企業傳輸規則 (ETR) |
| `EmailActionPolicyGuid` | 字串 | 決定最終郵件動作的原則的唯一識別碼 |
| `AttachmentCount` | int | 電子郵件的附件數量 |
| `UrlCount` | int | 電子郵件的內嵌 URL 數量 |
| `EmailLanguage` | 字串 | 偵測到的電子郵件內容語言 |
| `OrgLevelAction` | string | 針對與組織層級所定義之政策比對的電子郵件採取的動作 |
| `OrgLevelPolicy` | string | 觸發對電子郵件採取動作的組織政策 |
| `UserLevelAction` | string | 針對符合收件者定義的信箱策略對電子郵件採取的動作 |
| `UserLevelPolicy` | string | 觸發對電子郵件採取動作的使用者信箱政策 |
| `Connectors` | string | 定義組織郵件流程與電子郵件傳送方式的自訂指示 |
| `SenderDisplayName` | string | 顯示在通訊錄中的寄件者名稱，通常是指定或名字、中間名縮寫，以及姓氏或名字的組合 |
| `SenderObjectId` | string |在 Azure AD 中寄件者帳戶的唯一識別碼 |
| `ThreatTypes` | string | 電子郵件篩選堆疊的詐騙者會檢查電子郵件是否包含惡意攻擊、網路釣魚或其他威脅 |
| `ThreatNames` | string |找到的惡意攻擊或其他威脅的偵測名稱 |
| `DetectionMethods` | string | 用來偵測電子郵件中的惡意攻擊、網路釣魚或其他威脅的方法 |


## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
