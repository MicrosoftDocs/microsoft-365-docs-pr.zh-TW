---
title: 進階搜捕結構描述中的 EmailAttachmentInfo 表格
description: 了解進階搜捕結構描述之 EmailAttachmentInfo 表格中的電子郵件附件資訊
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、EmailAttachmentInfo、網路郵件識別碼、寄件者、收件者、附件識別碼、附件名稱、惡意程式碼判定
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 84d0c1fd256b013291e3df33dc5d7a0524741685
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498921"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用範圍：**
- Microsoft 365 Defender



[！附注] `EmailAttachmentInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含 Microsoft Defender for Office 365 所處理電子郵件附件的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `NetworkMessageId` | string | Microsoft 365 產生之電子郵件的唯一識別碼 |
| `SenderFromAddress` | 字串 | 電子郵件用戶端上的電子郵件收件者看得到 [寄件者] 標題中的寄件者電子郵件地址 |
| `SenderDisplayName` | 字串 | 顯示在通訊錄中之寄件者的名稱，通常是指定或名字、中間名首字母的組合，以及姓氏或姓的組合 |
| `SenderObjectId` | string | Azure AD 中寄件者帳戶的唯一識別碼 |
| `RecipientEmailAddress` | 字串 | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `RecipientObjectId` | 字串 | Azure AD 中電子郵件收件者的唯一識別碼 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FileType` | 字串 | 副檔名類型 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `ThreatTypes` | 字串 | 從電子郵件篩選棧中判定電子郵件是否包含惡意程式碼、網路釣魚或其他威脅 |
| `ThreatNames` | string | 找到惡意程式碼或其他威脅的偵測名稱 |
| `DetectionMethods` | string | 用於偵測電子郵件中所發現之惡意程式碼、網路釣魚或其他威脅的方法 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
