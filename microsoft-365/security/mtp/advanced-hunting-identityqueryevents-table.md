---
title: 進位搜尋架構中的 IdentityQueryEvents 資料表
description: 瞭解進位搜尋架構之 IdentityQueryEvents 資料表中的 Active Directory 查詢事件
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、IdentityQueryEvents、Azure AD、Active Directory、Azure ATP、identities、LDAP 查詢
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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929811"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進位搜尋架構中的表格包含對 Active Directory 物件執行查詢的資訊，例如使用者、群組、裝置 `IdentityQueryEvents` 和網域。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型。 請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料 |
| `Application` | string | 執行錄製動作的應用程式 |
| `QueryType` | string | 查詢類型，例如查詢組、查詢使用者或列舉使用者 |
| `QueryTarget` | string | 被查詢之使用者、群組、裝置、網域或其他實體類型的名稱 |
| `Query` | string | 用來執行查詢的字串 |
| `Protocol` | string | 通訊期間使用的通訊協定 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountUpn` | string | 帳戶 (UPN) 使用者主體名稱 |
| `AccountSid` | string | 帳戶 (安全性) SID 識別碼 |
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中的帳戶使用者名稱。 通常是指定或名字、中間名、姓氏或名字的組合。 |
| `DeviceName` | string | 端點之 FQDN () 完整功能變數名稱 |
| `IPAddress` | string | 指派給端點的 IP 位址，用於相關網路通訊期間 |
| `DestinationDeviceName` | string | 執行處理錄製動作之伺服器應用程式之裝置的名稱 |
| `DestinationIPAddress` | string | 執行處理錄製動作之伺服器應用程式的裝置 IP 位址 |
| `TargetDeviceName` | string | 所記錄動作 (裝置) FQDN 網域 |
| `TargetAccountUpn` | string | 已記錄 (之) 之帳戶的使用者主體名稱或 UPN 名稱 |
| `TargetAccountDisplayName` | string | 顯示所記錄動作所適用于之帳戶的名稱 |
| `Location` | string | 與活動相關的城市、國家/地區或其他地理位置 |
| `ReportId` | long | 事件的唯一識別碼 |
| `AdditionalFields` | string | 實體或事件的其他相關資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
