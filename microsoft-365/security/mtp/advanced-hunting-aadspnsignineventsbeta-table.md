---
title: Advanced 搜尋架構中的 AADSpnSignInEventsBeta 表格
description: 深入瞭解與 Azure Active Directory 服務主體及高級搜尋架構之 managed identity 登入事件表格相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，，device，machine，使用者，帳戶，身分識別，AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3eba2459fd9a0af1963ca8d1446b22fc0b1bdb93
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145400"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

適用於：

- Microsoft 365 Defender

>[!IMPORTANT]
> 此 `AADSpnSignInEventsBeta` 表格目前在 Beta 中，並在短期內提供，可讓您透過 Azure Active Directory (AAD) 服務主體和受管理身分識別登入事件進行搜尋。 我們最後會將所有登入架構資訊移至 `IdentityLogonEvents` 表格。<br><br>
> 可透過 Azure Security Center 的整合 Microsoft Defender for Endpoint 方案存取 Microsoft 365 Defender 的客戶，但沒有 Microsoft Defender for Office、Microsoft Defender 身分識別或 Microsoft Cloud App Security 的授權，將無法查看此架構。 



[！附注] `AADSpnSignInEventsBeta` 高級搜尋架構中的表格包含 Azure Active Directory 服務主體和受管理身分識別登入的相關資訊。您可以在 [Azure Active Directory 登入活動報告-預覽](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)中深入瞭解不同類型的登入。

使用這個參考來建立從表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。





| 資料行名稱     | 資料類型 | 描述   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | 記錄的產生日期和時間                                                                                                     |
| `Application`          | string        | 執行錄製動作的應用程式                                                                                                   |
| `ApplicationId`        | string        | 應用程式的唯一識別碼                                                                                                           |
| `IsManagedIdentity`    | 布林值       | 指出登入是否是由受管理身分識別所啟動                                                                               |
| `ErrorCode`            | int        | 如果發生登入錯誤，則會包含錯誤代碼。 若要尋找特定錯誤碼的描述，請造訪 <https://aka.ms/AADsigninsErrorCodes> 。 |
| `CorrelationId`        | string        | 登入事件的唯一識別碼                                                                                                          |
| `ServicePrincipalName` | string        | 啟動登入的服務主體名稱                                                                                        |
| `ServicePrincipalId`   | string        | 啟動登入之服務主體的唯一識別碼                                                                           |
| `ResourceDisplayName`  | string        | 存取資源的顯示名稱                                                                                                           |
| `ResourceId`           | string        | 存取資源的唯一識別碼                                                                                                      |
| `ResourceTenantId`     | string        | 存取資源租使用者的唯一識別碼                                                                                        |
| `IPAddress`            | string        | 指派給端點的 IP 位址，並在相關的網路通訊期間使用                                                              |
| `Country`          | string        | 兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區                                                                |
| `State`                | string        | 發生登入的狀態（若有的話）                                                                                                  |
| `City`                 | string        | 帳戶使用者所在的城市                                                                                                          |
| `Latitude`             | string        | 登入位置的北到南部座標                                                                                          |
| `Longitude`            | string        | 登入位置的東對西座標                                                                                            |
| `RequestId`            | string        | 要求的唯一識別碼                                                                                                                |
|`ReportId` | string | 事件的唯一識別碼 | 

 

## <a name="related-articles"></a>相關文章

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [進階搜捕概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [了解查詢語言](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [了解結構描述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

