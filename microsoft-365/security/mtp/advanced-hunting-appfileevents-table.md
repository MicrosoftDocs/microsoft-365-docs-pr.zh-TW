---
title: 進位搜尋架構中的 AppFileEvents 資料表
description: 在進位搜尋架構的 AppFileEvents 資料表中，瞭解與雲端應用程式和服務相關聯的檔案相關事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、資料行、資料類型、描述、AppFileEvents、雲端 App 安全性、MCAS
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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932871"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進位搜尋架構中的表格包含 Microsoft Cloud App 安全性所監控之雲端應用程式和服務中的檔案 `AppFileEvents` 相關活動相關資訊。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參照。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型。 請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料 |
| `Application` | string | 執行錄製動作的應用程式 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FolderPath` | 字串 | 包含已記錄動作所使用之檔案的資料夾 |
| `PreviousFileName` | string | 因動作而重新命名之檔案的原始名稱 |
| `PreviousFolderPath` | string | 在已記錄的動作之前包含檔案的原始檔案夾 |
| `Protocol` | string | 已使用網路通訊協定 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountUpn` | string | 帳戶 (UPN) 使用者主體名稱 |
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中的帳戶使用者名稱。 通常是指定或名字、中間名、姓氏或名字的組合。 |
| `DeviceName` | string | 裝置 FQDN (完整) 功能變數名稱 |
| `DeviceType` | string | 裝置類型 | 
| `OSPlatform` | string | 在裝置上作業系統平臺。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。 |
| `IPAddress` | 字串 | 指派給端點的 IP 位址，用於相關網路通訊期間 |
| `DestinationDeviceName` | string | 執行處理錄製動作之伺服器應用程式之裝置的名稱 |
| `DestinationIPAddress` | string | 執行處理錄製動作之伺服器應用程式的裝置 IP 位址 |
| `Location` | string | 與活動相關的城市、國家/地區或其他地理位置 |
| `Isp` | string | 與端點 IP 位址 (ISP) 網際網路服務提供者 |
| `ReportId` | long | 事件的唯一識別碼 |
| `AdditionalFields` | string | 實體或事件的其他相關資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
