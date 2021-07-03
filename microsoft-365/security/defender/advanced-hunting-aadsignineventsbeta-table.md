---
title: Advanced 搜尋架構中的 AADSignInEventsBeta 表格
description: 深入瞭解與高級搜尋架構的 Azure Active Directory 登入事件表格相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，資料類型，描述，檔案，IP 位址，設備，機器，使用者，帳戶，身分識別，AAD
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: edc9a1e40275631752ca1252a16071f4b07f07f9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286330"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**適用於：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 此 `AADSignInEventsBeta` 資料表目前在 Beta 中，並在短期內提供，以供您尋找 Azure Active Directory (AAD) 登入事件。 我們最後會將所有登入架構資訊移至 `IdentityLogonEvents` 表格。

[！附注] `AADSignInEventsBeta` 高級搜尋架構中的表格包含 Azure Active Directory 互動式和非互動式登入的相關資訊。深入瞭解[Azure Active Directory 登入活動報告-預覽](/azure/active-directory/reports-monitoring/concept-all-sign-ins)中的登入。

使用這個參考來建立從表格取回之資訊的查詢。 如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) (部分內容為機器翻譯)。

<br>

****

|資料行名稱|資料類型|描述|
|---|---|---|
|`Timestamp`|datetime|記錄的產生日期和時間|
|`Application`|string|執行錄製動作的應用程式|
|`ApplicationId`|string|應用程式的唯一識別碼|
|`LogonType`|string|登入會話的類型，尤其是互動式、遠端互動 (RDP) 、網路、批次及服務|
|`ErrorCode`|int|如果發生登入錯誤，則會包含錯誤代碼。 若要尋找特定錯誤碼的描述，請造訪 <https://aka.ms/AADsigninsErrorCodes> 。|
|`CorrelationId`|string|登入事件的唯一識別碼|
|`SessionId`|string|網站伺服器在就診或會話期間指派給使用者的唯一號碼|
|`AccountDisplayName`|string|顯示在通訊錄中之帳戶使用者的名稱。 通常是指定的名稱或名字、中間名首字母的組合，以及姓氏或姓的組合。|
|`AccountObjectId`|string|Azure AD 中帳戶的唯一識別碼|
|`AccountUpn`|string|帳戶的使用者主要名稱 (UPN) |
|`IsExternalUser`|int|會指出登入的使用者是否為外部使用者。 可能的值：-1 (未設定) ，0 (非外部) ，1 (外部) 。|
|`IsGuestUser`|布林值|指出登入的使用者是否為承租人中的來賓|
|`AlternateSignInName`|string|內部部署使用者主要名稱 (使用者登入 Azure AD 的 UPN) |
|`LastPasswordChangeTimestamp`|datetime|上次簽署使用者密碼的日期和時間|
|`ResourceDisplayName`|string|存取資源的顯示名稱|
|`ResourceId`|string|存取資源的唯一識別碼|
|`ResourceTenantId`|string|存取資源租使用者的唯一識別碼|
|`DeviceName`|string|電腦的完整網域名稱 (FQDN)|
|`AadDeviceId`|string|Azure AD 中裝置的唯一識別碼|
|`OSPlatform`|string|電腦上執行的作業系統平台。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。|
|`DeviceTrustType`|字串|指出已登入之裝置的信任類型。 僅適用于受管理的裝置案例。 可能的值為 Workplace、AzureAd 及 ServerAd。|
|`IsManaged`|int|會指出發起登入的裝置是否為受管理的裝置 (1) 或不是受管理裝置 (0) |
|`IsCompliant`|int|會指出發起登入的裝置是否符合 (1) 或不相容 (0) |
|`AuthenticationProcessingDetails`|string|驗證處理器的詳細資料|
|`AuthenticationRequirement`|string|登入所需的驗證類型。 可能的值： multiFactorAuthentication (MFA 是必要) 和 singleFactorAuthentication (不需要 MFA) 。|
|`TokenIssuerType`|int|會指出權杖簽發者是否 Azure Active Directory (0) 或 Active Directory Federation Services (1) |
|`RiskLevelAggregated`|int|登入過程中的風險層級匯總。 可能的值： 0 (匯總風險層級未設定) ，1 (none) ，10 (低) ，50 (中) ，或 100 (高) 。|
|`RiskDetails`|int|有關已登入之使用者的危險狀態的詳細資料|
|`RiskState`|int|表示有危險的使用者狀態。 可能的值： 0 (無) 、1 (已確認的安全) 、2 (修正) 、3 () 、4 (風險) 或 5 (已確認已遭破壞) 。|
|`UserAgent`|string|來自網頁瀏覽器或其他用戶端應用程式的使用者代理程式資訊|
|`ClientAppUsed`|string|表示所用的用戶端應用程式|
|`Browser`|string|用於登入之瀏覽器版本的詳細資料|
|`ConditionalAccessPolicies`|string|套用至登入事件之條件式存取原則的詳細資料|
|`ConditionalAccessStatus`|int|套用至登入的條件式存取原則狀態。 可能的值為 0 (套用的原則) 、1 (嘗試套用原則失敗) 或 2 (未套用) 原則。|
|`IPAddress`|string|指派給端點的 IP 位址，並在相關的網路通訊期間使用|
|`Country`|string|兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區|
|`State`|string|發生登入的狀態（若有的話）|
|`City`|string|帳戶使用者所在的城市|
|`Latitude`|string|登入位置的北到南部座標|
|`Longitude`|string|登入位置的東對西座標|
|`NetworkLocationDetails`|string|登錄事件驗證處理器的網路位置詳細資料|
|`RequestId`|string|要求的唯一識別碼|
|`ReportId`|string|事件的唯一識別碼|
|

## <a name="related-articles"></a>相關文章

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [進階搜捕概觀](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [了解查詢語言](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [了解結構描述](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
