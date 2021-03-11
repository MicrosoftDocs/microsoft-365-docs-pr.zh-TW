---
title: Advanced 搜尋架構中的 IdentityDirectoryEvents 表格
description: 深入瞭解高級搜尋架構的 IdentityDirectoryEvents 資料表中的網域控制站和 Active Directory 事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityDirectoryEvents，網域控制站，Active Directory，Azure ATP，身分識別
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
ms.openlocfilehash: d4e119bc0a2e600d5203231eb196cf201469bfd2
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712363"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

`IdentityDirectoryEvents` [Advanced 搜尋](advanced-hunting-overview.md)架構中的表格包含的事件包括內部部署網域控制站執行 ACTIVE Directory (AD) 。 此表格會捕獲各種身分識別相關的事件，例如密碼變更、密碼到期和使用者主要名稱 (UPN) 變更。 它也會在網域控制站上捕獲系統事件，例如排程任務和 PowerShell 活動。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的內建架構參照。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型。 如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | string | 執行錄製動作的應用程式 |
| `TargetAccountUpn` | string | 套用錄製動作之帳戶的使用者主要名稱 (UPN)  |
| `TargetAccountDisplayName` | string | 套用錄製的動作所套用之帳戶的顯示名稱 |
| `TargetDeviceName` | string | 套用錄製動作之裝置的完整功能變數名稱 (FQDN)  |
| `DestinationDeviceName` | string | 執行伺服器應用程式（處理錄製的動作）的裝置名稱 |
| `DestinationIPAddress` | string | 執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址 |
| `DestinationPort` | string | 活動的目的地埠 |
| `Protocol` | string | 通訊期間使用的通訊協定 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountUpn` | string | 帳戶的使用者主要名稱 (UPN)  |
| `AccountSid` | string | 帳戶的安全性識別碼 (SID)  |
| `AccountObjectId` | string | Azure Active Directory 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中之帳戶使用者的名稱。 通常是指定的名稱或名字、中間初始名稱或姓氏的組合。 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `IPAddress` | string | 通訊期間指派給裝置的 IP 位址 |
| `Port` | string | 通訊期間使用的 TCP 埠 |
| `Location` | string | 與事件關聯的城市、國家或其他地理位置 |
| `ISP` | string | 與 IP 位址相關聯的網際網路服務提供者 |
| `ReportId` | long | 事件的唯一識別碼 |
| `AdditionalFields` | string | 實體或事件的其他資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
