---
title: 進位搜尋架構中的 AADSignInEventsBeta 資料表
description: 瞭解進位搜尋架構之 Azure Active Directory 登錄事件資料表的關聯資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、檔案、IP 位址、裝置、電腦、使用者、帳戶、身分識別、AAD
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
ms.openlocfilehash: b574717d0ba5621d85c8e73f36ddc72b062a1494
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931035"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

適用於：

- Microsoft 365 Defender

>[!IMPORTANT]
> 此表格目前為 Beta 版，並且提供短期版本，讓您在 `AADSignInEventsBeta` Azure Active Directory (AAD) 事件搜尋。 我們最終會移動所有登錄架構資訊至 `IdentityLogonEvents` 資料表。<br><br>
> 可透過 Azure 資訊安全中心整合的 Microsoft Defender 端點解決方案存取 Microsoft 365 Defender，但沒有 Microsoft Defender for Office、Microsoft Defender for Identity 或 Microsoft Cloud App 安全性授權的客戶，將無法查看此架構。 

 

進 `AADSignInEventsBeta` 位搜尋架構中的表格包含有關 Azure Active Directory 互動式和非互動式之登錄的資訊。深入瞭解 Azure Active Directory 的登錄 [活動報告 -](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)預覽。

使用這個參考來建立從表格取回之資訊的查詢。
如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。

 

 

| 資料行名稱                 | 資料類型 | 描述          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | 記錄的產生日期和時間                                                                                                                                         |
| `Application`                     | string        | 執行錄製動作的應用程式                                                                                                                                       |
| `ApplicationId`                   | string        | 應用程式的唯一識別碼                                                                                                                                               |
| `LogonType`                       | string        | 登入會話類型，尤其是互動式遠端互動式 (RDP) 、網路、批次和服務                                                                              |
| `ErrorCode`                       | int        | 發生登錄錯誤時，包含錯誤碼。 若要尋找特定錯誤碼的描述，請流覽 <https://aka.ms/AADsigninsErrorCodes> 。                                     |
| `CorrelationId`                   | string        | 此登錄事件的唯一識別碼                                                                                                                                              |
| `SessionId`                       | string        | 網站伺服器在流覽或會話期間指派給使用者的唯一數位                                                                                     |
| `AccountDisplayName`              | string        | 顯示在通訊錄中的帳戶使用者名稱。 通常是指定或名字、中間名縮寫，以及姓氏或名字的組合。                             |
| `AccountObjectId`                 | string        | Azure AD 中帳戶的唯一識別碼                                                                                                                                       |
| `AccountUpn`                      | string        | 帳戶 (UPN) 使用者主體名稱                                                                                                                                            |
| `IsExternalUser`                  | int        | 指出已登錄的使用者為外部使用者。 可能的值：-1 (設定為) ;0 (非) ;1 (外部) 。                                                                   |
| `IsGuestUser`                     | 布林值       | 指出已登錄的使用者是否在租使用者中為來賓                                                                                                                  |
| `AlternateSignInName`             | string        | 內部部署使用者主體名稱 (使用者) Azure AD 的 UPN 使用者名稱                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | 上次簽到的使用者變更密碼的日期和時間                                                                                                              |
| `ResourceDisplayName`             | string        | 顯示已存取資源的名稱                                                                                                                                               |
| `ResourceId`                      | string        | 已存取資源的唯一識別碼                                                                                                                                          |
| `ResourceTenantId`                | string        | 存取資源之租使用者的唯一識別碼                                                                                                                            |
| `DeviceName`                      | string        | 電腦的完整網域名稱 (FQDN)                                                                                                                                   |
| `AadDeviceId`                     | string   |      Azure AD 中裝置的唯一識別碼                                                                                                                                                                               |
| `OSPlatform`                      | string        | 電腦上執行的作業系統平台。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。  |
| `DeviceTrustType`                 | 字串        | 表示已登錄之裝置的信任類型。 僅適用于受管理的裝置案例。 可能的值為 Workplace、AzureAd 和 ServerAd。                                     |
| `IsManaged`                       | int       | 指出初始化該登錄的裝置是受管理的裝置 () 1，或不是 (0)                                                                          |
| `IsCompliant`                     | int       | 指出啟動該登錄的裝置是否符合 (1) 相容性， (0)                                                                                        |
| `AuthenticationProcessingDetails` | string        | 驗證處理器的詳細資訊                                                                                                                                          |
| `AuthenticationRequirement`       | string        | 此登錄所需的驗證類型。 可能的值：需要 multiAuthentication (MFA) singleFactorAuthentication (不需要 MFA) 。                |
| `TokenIssuerType`                 | int        | 指出權杖發行者是 Azure Active Directory (0) 或 Active Directory Federation Services (1)                                                                              |
| `RiskLevelAggregated`                       | int        | 在登錄期間匯總的風險等級。 可能的值：未設定) 的 (匯總風險等級、1 (無) 、10 (低) 、50 (中) 或 100 (高) 。                               |
| `RiskDetails`                      | int        | 已簽署之使用者風險狀態的詳細資訊                                                                                                                            |
| `RiskState`                       | int        | 表示有風險的使用者狀態。 可能的值：0 (無) 、1 (已確認安全) 、2 (修復) 、3 (解除) 、4 (風險) 或 5 (已確認已入侵) 。                                |
| `UserAgent`                       | string        | 網頁瀏覽器或其他用戶端應用程式的使用者代理程式資訊                                                                                                             |
| `ClientAppUsed`                   | string        | 表示使用的用戶端應用程式                                                                                                                                                       |
| `Browser`                         | string        | 用來進行登錄的瀏覽器版本詳細資料                                                                                                                            |
| `ConditionalAccessPolicies`       | string        | 將條件式存取原則新用至此登錄事件的詳細資訊                                                                                                             |
| `ConditionalAccessStatus`         | int        | 已對登錄所適用之條件式存取原則的狀態。 可能的值包括 0 (原則) 、1 (嘗試將原則成功) ，或 2 (原則未) 。      |
| `IPAddress`                       | string        | 指派給端點的 IP 位址，用於相關網路通訊期間                                                                                                  |
| `CountryCode`                     | string        | 兩個字母的代碼，指出用戶端 IP 位址已異地定位的國家/地區                                                                                                    |
| `State`                           | string        | 發生此登錄的州/省 （如果可用）                                                                                                                                      |
| `City`                            | string        | 帳戶使用者所在的城市                                                                                                                                              |
| `Latitude`                        | string        | 簽署位置的北到南座標                                                                                                                              |
| `Longitude`                       | string        | 簽署位置的東部至西座標                                                                                                                                |
| `NetworkLocationDetails`          | string        | 此登錄事件之驗證處理器的網路位置詳細資料                                                                                                       |
| `RequestId`                       | string        |  要求的唯一識別碼                                                                                                                                                   |
|`ReportId` | string | 事件的唯一識別碼 |

 

 

## <a name="related-articles"></a>相關文章

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [進階搜捕概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [了解查詢語言](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [了解結構描述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
