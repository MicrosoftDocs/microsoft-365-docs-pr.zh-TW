---
title: 進位搜尋架構中的 CloudAppEvents 資料表
description: 瞭解來自雲端應用程式與服務的事件，包括進位搜尋架構的 CloudAppEvents 資料表
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料表、資料行、資料類型、描述、CloudAppEvents、雲端 App 安全性、MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928447"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

目前提供預覽版，進位搜尋架構中的表格包含各種雲端應用程式和服務中活動的資訊，特別是 `CloudAppEvents` Microsoft Teams 和 Exchange Online。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

此表格將展開以納入 Microsoft Cloud App 安全性所監視的更多活動。 最後，此表格會包含目前儲存在 [AppFileEvents](advanced-hunting-appfileevents-table.md) 資料表中的檔案活動。 當更多資料移至此表格時，Microsoft 會提供額外的指引。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型 |
| `Application` | string | 執行錄製動作的應用程式 |
| `ApplicationId` | string | 應用程式的唯一識別碼 |
| `AccountObjectId` | string | Azure Active Directory 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中的帳戶使用者名稱。 通常是指定或名字、中間名、姓氏或名字的組合。 |
| `IsAdminOperation` | string | 指出活動是否由系統管理員執行 |
| `DeviceType` | string | 根據用途和功能所根據的裝置類型，例如「網路裝置」、「工作站」、「伺服器」、「行動裝置」、「遊戲主機」或「印表機」 | 
| `OSPlatform` | string | 在裝置上作業系統平臺。 此欄會指出特定的作業系統，包括同一家庭內的變化，例如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 指派給端點的 IP 位址，用於相關網路通訊期間 |
| `IsAnonymousProxy` | string | 指出 IP 位址是否屬於已知的匿名 Proxy |
| `CountryCode` | string | 兩個字母的代碼，指出用戶端 IP 位址已異地定位的國家/地區 |
| `City` | string | 用戶端 IP 位址地理位置的城市 |
| `Isp` | string | 與 IP 位址 (ISP) 網際網路服務提供者 |
| `UserAgent` | string | 網頁瀏覽器或其他用戶端應用程式的使用者代理程式資訊 |
| `ActivityType` | string | 觸發事件的活動類型 |
| `ActivityObjects` | string | 包含錄製活動的物件清單，例如檔案或資料夾 |
| `ObjectName` | string | 錄製動作所使用之物件的名稱 |
| `ObjectType` | string | 所記錄動作所針對的物件類型，例如檔案或資料夾 |
| `ObjectId` | string | 所記錄動作所使用之物件的唯一識別碼 |
| `ReportId` | string | 事件的唯一識別碼 |
| `RawEventData` | string | 從 JSON 格式的來源應用程式或服務原始事件資訊 |
| `AdditionalFields` | string | 實體或事件的其他相關資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
