---
title: 進階搜捕結構描述中的 EmailEvents 表格
description: 深入瞭解在高級搜尋架構的 EmailEvents 表格中與 Microsoft 365 電子郵件相關的事件
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、EmailEvents、網路郵件 id、寄件者、收件者、附件識別碼、附件計數、url 計數、url 計數
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
ms.openlocfilehash: 63f12aaa84415b354fd257558612dbbe28e41360
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429452"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用範圍：**
- Microsoft 威脅防護



[進階搜捕](advanced-hunting-overview.md)結構描述中的 `EmailEvents` 表格包含有關在 Office 365 ATP 處理電子郵件的事件相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

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
| `PhishDetectionMethod` | 字串 | 用於將電子郵件偵測為網路釣魚的方法：惡意 URL 信譽、ATP 安全連結 URL 引爆、進階網路釣魚篩選、一般網路釣魚篩選、防詐騙：組織內部、防詐騙：外部網域、網域模擬、使用者模擬、品牌模擬 |
| `MalwareFilterVerdict` | 字串 | 決定電子郵件是否包含惡意程式碼的電子郵件篩選堆疊：惡意程式碼或非惡意程式碼 |
| `MalwareDetectionMethod` | 字串 | 用於偵測電子郵件惡意程式碼的方法：反惡意程式碼引擎、檔案信譽、ATP 安全附件 |
| `FinalEmailAction` | 字串 | 以篩選決策、原則和使用者動作為基礎的最終電子郵件執行動作：將郵件移至垃圾郵件資料夾、新增 X 標頭、修改主旨、重新導向郵件、刪除郵件、傳送至隔離、未採取任何動作、密件副本郵件 |
| `FinalEmailActionPolicy` | 字串 | 生效的動作原則：反垃圾郵件 - 高信賴度、反垃圾郵件、反垃圾郵件 - 大宗郵件、反垃圾郵件 - 網路釣魚、反網路釣魚網域模擬、反網路釣魚使用者模擬、反網路釣魚詐騙、反網路釣魚圖形模擬、反惡意程式碼、安全附件、企業傳輸規則 (ETR) |
| `FinalEmailActionPolicyGuid` | 字串 | 決定最終郵件動作的原則的唯一識別碼 |
| `AttachmentCount` | int | 電子郵件的附件數量 |
| `UrlCount` | int | 電子郵件的內嵌 URL 數量 |
| `EmailLanguage` | 字串 | 偵測到的電子郵件內容語言 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
