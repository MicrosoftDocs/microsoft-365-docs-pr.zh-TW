---
title: Advanced 搜尋架構中的 IdentityInfo 表格
description: 深入瞭解高級搜尋架構的 IdentityInfo 資料表中的使用者帳戶資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，AccountInfo，IdentityInfo，account
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898954"
---
# <a name="identityinfo"></a>IdentityInfo

適用於：****
- Microsoft 威脅防護

[！附注] `IdentityInfo` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含從各種服務（包含 Azure Active Directory）取得之使用者帳戶的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!NOTE]
>此資料表已重新命名 `AccountInfo` 。 重新命名時，儲存在入口網站中的所有查詢都會自動更新。 檢查您已儲存在其他位置的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountUpn` | string | 帳戶的使用者主要名稱（UPN） |
| `OnPremSid` | string | 帳戶的內部部署安全性識別碼（SID） |
| `CloudSid` | string | 帳戶的雲端安全性識別碼 |
| `GivenName` | string | 帳戶使用者的指定名稱或名字 |
| `Surname` | string | 帳戶使用者的姓氏、系列名稱或姓氏 |
| `AccountDisplayName` | string | 顯示在通訊錄中之帳戶使用者的名稱。 通常是指定的名稱或名字、中間初始名稱或姓氏的組合。 |
| `Department` | string | 帳戶使用者所屬的部門名稱 |
| `JobTitle` | string | 帳戶使用者的職稱 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `EmailAddress` | string | 帳戶的 SMTP 位址 |
| `SipProxyAddress` | string | 客戶的 over IP （VOIP）會話初始通訊協定（SIP）位址的語音 |
| `City` | string | 帳戶使用者所在的城市 |
| `Country` | string | 帳戶使用者所在的國家/地區 |
| `IsAccountEnabled` | 布林值 | 指出帳戶是否已啟用 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
