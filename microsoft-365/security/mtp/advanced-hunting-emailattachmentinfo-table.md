---
title: 進階搜捕結構描述中的 EmailAttachmentInfo 表格
description: 了解進階搜捕結構描述之 EmailAttachmentInfo 表格中的電子郵件附件資訊
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型，描述] 中，EmailAttachmentInfo，網路郵件 id、 寄件者收件者、 附件識別碼、 附件名稱、 惡意程式碼 verdict
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3bd4c3ed69c53a4520e0e0739801ef4a74b77059
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210368"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**適用範圍：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[進階搜捕](advanced-hunting-overview.md)結構描述中的 `EmailAttachmentInfo` 表格包含有關 Office 365 ATP 所處理的電子郵件附件資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間。 |
| `AttachmentId` | 字串 | 唯一電子郵件附件識別碼 |
| `NetworkMessageId` | 字串 | Office 365 產生的電子郵件唯一識別碼 |
| `SenderFromAddress` | 字串 | 電子郵件用戶端上的電子郵件收件者看得到 [寄件者] 標題中的寄件者電子郵件地址 |
| `RecipientEmailAddress` | 字串 | 收件者的電子郵件地址，或通訊群組清單展開後之收件者的電子郵件地址 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FileType` | 字串 | 副檔名類型 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `MalwareFilterVerdict` | 字串 | 決定電子郵件是否包含惡意程式碼的電子郵件篩選堆疊：惡意程式碼或非惡意程式碼 |
| `MalwareDetectionMethod` | 字串 | 用於偵測電子郵件惡意程式碼的方法：反惡意程式碼引擎、檔案信譽、ATP 安全附件 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)