---
title: 進階搜捕結構描述中的 EmailAttachmentInfo 表格
description: 了解進階搜捕結構描述之 EmailAttachmentInfo 表格中的電子郵件附件資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、EmailAttachmentInfo、網路訊息識別碼、寄件者、收件者、附件識別碼、附件名稱、惡意程式碼惡意程式碼
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c6cab4d813eba79e298d0082072888e3ef1ad1cd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926999"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用範圍：**
- Microsoft 365 Defender



進 `EmailAttachmentInfo` 位搜尋架構 [中的](advanced-hunting-overview.md) 表格包含由 Microsoft Defender for Office 365 處理之電子郵件之附件的資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間。 |
| `AttachmentId` | 字串 | 唯一電子郵件附件識別碼 |
| `NetworkMessageId` | 字串 | Microsoft 365 產生之電子郵件的唯一識別碼 |
| `SenderFromAddress` | 字串 | 電子郵件用戶端上的電子郵件收件者看得到 [寄件者] 標題中的寄件者電子郵件地址 |
| `RecipientEmailAddress` | 字串 | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FileType` | 字串 | 副檔名類型 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `MalwareFilterVerdict` | 字串 | 決定電子郵件是否包含惡意程式碼的電子郵件篩選堆疊：惡意程式碼或非惡意程式碼 |
| `MalwareDetectionMethod` | 字串 | 用來偵測電子郵件中的惡意攻擊的方法：反惡意軟體引擎、檔案品質、安全附件 |
| `SenderDisplayName` | string | 顯示在通訊錄中的寄件者名稱，通常是指定或名字、中間名縮寫，以及姓氏或名字的組合 |
| `SenderObjectId` | string | 在 Azure AD 中寄件者帳戶的唯一識別碼 |
| `ThreatTypes` | string | 電子郵件篩選堆疊的詐騙者會檢查電子郵件是否包含惡意攻擊、網路釣魚或其他威脅 |
| `ThreatNames` | string | 找到的惡意攻擊或其他威脅的偵測名稱 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
