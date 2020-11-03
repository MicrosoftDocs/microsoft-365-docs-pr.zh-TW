---
title: Advanced 搜尋架構中的 AppFileEvents 表格
description: 深入瞭解在高級搜尋架構的 AppFileEvents 資料表中，與雲端 app 和服務相關聯的檔案相關事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，AppFileEvents，Cloud App Security，MCAS
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
ms.openlocfilehash: 1a7f523e96c0a46c29098f7e5bb2fbb83a4db4bb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847653"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[！附注] `AppFileEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含雲端 app 和服務中由 Microsoft cloud App Security 監控之檔案相關活動的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型。 如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | string | 執行錄製動作的應用程式 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FolderPath` | 字串 | 包含錄製的動作所套用之檔案的資料夾 |
| `PreviousFileName` | string | 重新命名為動作結果之檔案的原始名稱 |
| `PreviousFolderPath` | string | 在套用錄製的動作之前包含檔的原始檔案夾 |
| `Protocol` | string | 使用的網路通訊協定 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountUpn` | string | 帳戶的使用者主要名稱 (UPN)  |
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中之帳戶使用者的名稱。 通常是指定的名稱或名字、中間初始名稱或姓氏的組合。 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `DeviceType` | string | 裝置類型 | 
| `OSPlatform` | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。 |
| `IPAddress` | 字串 | 指派給端點的 IP 位址，並在相關的網路通訊期間使用 |
| `DestinationDeviceName` | string | 執行伺服器應用程式（處理錄製的動作）的裝置名稱 |
| `DestinationIPAddress` | string | 執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址 |
| `Location` | string | 與事件關聯的城市、國家或其他地理位置 |
| `Isp` | string | 網際網路服務提供者 (與端點 IP 位址相關聯的 ISP)  |
| `ReportId` | long | 事件的唯一識別碼 |
| `AdditionalFields` | string | 實體或事件的其他資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
