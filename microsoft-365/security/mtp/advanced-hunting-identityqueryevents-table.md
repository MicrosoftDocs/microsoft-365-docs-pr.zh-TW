---
title: Advanced 搜尋架構中的 IdentityQueryEvents 表格
description: 深入瞭解高級搜尋架構的 IdentityQueryEvents 資料表中的 Active Directory 查詢事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityQueryEvents，Azure AD，Active Directory，Azure ATP，identity，LDAP 查詢
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
ms.openlocfilehash: bf1c57ee93c6f0e007c1b58e73fb9371799e75c6
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431120"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

[！附注] `IdentityQueryEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含針對 Active Directory 物件（如使用者、群組、裝置和網域）所執行之查詢的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型。 如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | string | 執行錄製動作的應用程式 |
| `QueryType` | string | 查詢類型，例如 QueryGroup、QueryUser 或 EnumerateUsers |
| `QueryTarget` | string | 所查詢的使用者、群組、裝置、網域或任何其他實體類型的名稱 |
| `Query` | string | 用來執行查詢的字串 |
| `Protocol` | string | 通訊期間使用的通訊協定 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountUpn` | string | 帳戶的使用者主要名稱 (UPN)  |
| `AccountSid` | string | 帳戶的安全性識別碼 (SID)  |
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中之帳戶使用者的名稱。 通常是指定的名稱或名字、中間初始名稱或姓氏的組合。 |
| `DeviceName` | string | 端點 (FQDN) 的完整功能變數名稱 |
| `IPAddress` | string | 指派給端點的 IP 位址，並在相關的網路通訊期間使用 |
| `DestinationDeviceName` | string | 執行伺服器應用程式（處理錄製的動作）的裝置名稱 |
| `DestinationIPAddress` | string | 執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址 |
| `TargetDeviceName` | string | 套用錄製動作之裝置的完整功能變數名稱 (FQDN)  |
| `TargetAccountUpn` | string | 套用錄製動作之帳戶的使用者主要名稱 (UPN)  |
| `TargetAccountDisplayName` | string | 套用錄製的動作所套用之帳戶的顯示名稱 |
| `Location` | string | 與事件關聯的城市、國家或其他地理位置 |
| `ReportId` | long | 事件的唯一識別碼 |
| `AdditionalFields` | string | 實體或事件的其他資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
