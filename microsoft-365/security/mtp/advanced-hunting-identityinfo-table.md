---
title: 進位搜尋架構中的 IdentityInfo 資料表
description: 瞭解進位搜尋架構之 IdentityInfo 資料表中的使用者帳戶資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、資料行、資料類型、描述、AccountInfo、IdentityInfo、account
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929907"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進 `IdentityInfo` 位搜尋架構 [中的](advanced-hunting-overview.md) 表格包含從各種服務取得之使用者帳戶的資訊，包括 Azure Active Directory。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!NOTE]
>此資料表已 `AccountInfo` 重新命名。 重新命名期間，所有儲存于入口網站中的查詢都會自動更新。 檢查您儲存于其他位置的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountUpn` | string | 帳戶 (UPN) 使用者主體名稱 |
| `OnPremSid` | string | 帳戶的 SID () 內部部署安全性識別碼 |
| `CloudSid` | string | 帳戶的雲端安全性識別碼 |
| `GivenName` | string | 帳戶使用者的指定名稱或名字 |
| `Surname` | string | 帳戶使用者的姓氏、家人姓名或名字 |
| `AccountDisplayName` | string | 顯示在通訊錄中的帳戶使用者名稱。 通常是指定或名字、中間名、姓氏或名字的組合。 |
| `Department` | string | 帳戶使用者所屬的部門名稱 |
| `JobTitle` | string | 帳戶使用者職稱 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `EmailAddress` | string | 帳戶的 SMTP 位址 |
| `SipProxyAddress` | string | VOIP (VOIP) 會話初始通訊協定 (SIP) 位址 |
| `City` | string | 帳戶使用者所在的城市 |
| `Country` | string | 帳戶使用者所在的國家/地區 |
| `IsAccountEnabled` | 布林值 | 指出帳戶是否已啟用 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
