---
title: 進位搜尋架構中的 AADSpnSignInEventsBeta 資料表
description: 瞭解與 Azure Active Directory 服務主體及進位搜尋架構的受管理身分識別登錄事件資料表相關聯的資訊
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料表、資料行、資料類型、描述、警示資訊、警示、實體、證據、檔案、IP 位址、裝置、電腦、使用者、帳戶、身分識別、AAD
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
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928615"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

適用於：

- Microsoft 365 Defender

>[!IMPORTANT]
> 資料表目前為 Beta 版，目前提供短期版本，讓您搜尋 `AADSpnSignInEventsBeta` Azure Active Directory (AAD) 服務主體及受管理的身分識別登錄事件。 我們最終會移動所有登錄架構資訊至 `IdentityLogonEvents` 資料表。<br><br>
> 可透過 Azure 資訊安全中心整合的 Microsoft Defender 端點解決方案存取 Microsoft 365 Defender，但沒有 Microsoft Defender for Office、Microsoft Defender for Identity 或 Microsoft Cloud App 安全性授權的客戶，將無法查看此架構。 



進 `AADSpnSignInEventsBeta` 位搜尋架構中的資料表包含有關 Azure Active Directory 服務主體及受管理身分識別登錄的資訊。您可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)的登錄活動報告中深入瞭解不同類型的登錄 - 預覽。

使用這個參考來建立從表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。





| 資料行名稱     | 資料類型 | 描述   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | 記錄的產生日期和時間                                                                                                     |
| `Application`          | string        | 執行錄製動作的應用程式                                                                                                   |
| `ApplicationId`        | string        | 應用程式的唯一識別碼                                                                                                           |
| `IsManagedIdentity`    | 布林值       | 指出該登錄是否由受管理的身分識別初始化                                                                               |
| `ErrorCode`            | int        | 發生登錄錯誤時，包含錯誤碼。 若要尋找特定錯誤碼的描述，請流覽 <https://aka.ms/AADsigninsErrorCodes> 。 |
| `CorrelationId`        | string        | 此登錄事件的唯一識別碼                                                                                                          |
| `ServicePrincipalName` | string        | 初始化該登錄的服務主體名稱                                                                                        |
| `ServicePrincipalId`   | string        | 初始化登錄的服務主體的唯一識別碼                                                                           |
| `ResourceDisplayName`  | string        | 顯示已存取資源的名稱                                                                                                           |
| `ResourceId`           | string        | 已存取資源的唯一識別碼                                                                                                      |
| `ResourceTenantId`     | string        | 存取資源之租使用者的唯一識別碼                                                                                        |
| `IPAddress`            | string        | 指派給端點的 IP 位址，用於相關網路通訊期間                                                              |
| `CountryCode`          | string        | 兩個字母的代碼，指出用戶端 IP 位址已異地定位的國家/地區                                                                |
| `State`                | string        | 發生此登錄的州/省 （如果可用）                                                                                                  |
| `City`                 | string        | 帳戶使用者所在的城市                                                                                                          |
| `Latitude`             | string        | 簽署位置的北到南座標                                                                                          |
| `Longitude`            | string        | 簽署位置的東部至西座標                                                                                            |
| `RequestId`            | string        | 要求的唯一識別碼                                                                                                                |
|`ReportId` | string | 事件的唯一識別碼 | 

 

## <a name="related-articles"></a>相關文章

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [進階搜捕概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [了解查詢語言](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [了解結構描述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

