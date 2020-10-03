---
title: 保護 Microsoft 365 租用戶的使用者登入
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 規定使用者以多重要素驗證 (MFA) 和其他功能安全登入。
ms.openlocfilehash: 2e6c564e3179d0847710e2bef071dcc9e1cdbdaf
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327423"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>保護 Microsoft 365 租用戶的使用者登入

若要加強使用者登入的安全性：

- 使用 Windows Hello 企業版
- 使用 Azure Active Directory (Azure AD) 密碼保護
- 使用多重要素驗證 (MFA)
- 部署身分識別與裝置存取設定
- 使用 Azure AD Identity Protection 來防止認證洩露

## <a name="windows-hello-for-business"></a>Windows Hello 企業版

Windows 10 企業版的 Windows Hello 企業版在登入 Windows 裝置時，會使用加強雙因素驗證取代密碼。 雙因素是一種新的使用者認證類型，可與裝置和生物特徵或 PIN 相繫結。

如需詳細資訊，請參閱 [ Windows Hello 企業版概觀](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。


## <a name="azure-ad-password-protection"></a>Azure AD 密碼保護

Azure AD 密碼保護可偵測並封鎖已知的弱式密碼及其變體，也會封鎖貴組織特有的額外弱式詞彙。 預設全域禁用密碼清單會自動套用至 Azure AD 租用戶中的所有使用者。 您可以在自訂禁用密碼清單中定義其他條目。 使用者變更或重設密碼時，系統會檢查這些禁用密碼清單，以強制使用強式密碼。

如需詳細資訊，請參閱[設定 Azure AD 密碼保護](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)。

## <a name="mfa"></a>MFA

MFA 會要求使用者登入程序另外遵守使用者帳戶密碼以外的驗證規定。 惡意使用者即使確定了使用者帳戶的密碼，還必須能夠回應另外的驗證機制 (例如，傳送至智慧型手機的簡訊)，才能獲得存取權。

![正確的密碼加上其他驗證則可導致順利登入](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

使用 MFA 的第一步是***要求所有系統管理員帳戶 (亦即授權帳戶) 都使用 MFA***。

除了這個第一步，Microsoft 建議要求所有使用者都使用 MFA。

根據您的 Microsoft 365 方案，有三種方法可以要求系統管理員或使用者使用 MFA。

| 方案 | 建議 |
|---------|---------|
|所有的 Microsoft 365 方案（不含 Azure AD Premium P1 或 P2 授權）     |[在 Azure AD 中啟用安全性預設](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性預設包含了適用於使用者和系統管理員的 MFA。   |
|Microsoft 365 E3 （含 Azure AD Premium P1 授權）     | 使用[常見的條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則： <br>- [要求系統管理員使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [要求所有使用者使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 （含 Azure AD Premium P2 授權）     | 利用 Azure AD Identity Protection，藉由建立下列兩種原則來開始實作 Microsoft [建議的一組條件式存取和相關原則](../enterprise/identity-access-policies.md)：<br> - [登入風險為中或高時，需要 MFA](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [高風險使用者必須變更密碼](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>安全性預設

安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。 這些訂用帳戶會開啟安全性預設，而***要求所有使用者都必須使用 MFA 與 Microsoft Authenticator 應用程式***。
 
使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。 14 天過後，使用者就無法登入，除非其完成 MFA 註冊。

安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。 您可以停用安全性預設，改為使用 MFA 與條件式存取原則或改為使用個別帳戶。

如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

### <a name="conditional-access-policies"></a>條件式存取原則

條件式存取原則是一組規則，可指定要在什麼條件下評估登入以及授予存取權。 例如，您可以建立敘述如下的條件式存取原則：

- 如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。

此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。

您也可以使用條件式存取原則來執行更進階的功能，例如要求登入必須是來自符合規範的裝置 (例如執行 Windows 10 的膝上型電腦)。

[條件式存取] 需有 Azure AD Premium P1 授權，已附加在 Microsoft 365 E3 和 E5 套裝中。

如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

### <a name="using-these-methods-together"></a>共同使用這些方法

請記住下列事項：

- 如果您已啟用任何條件式存取原則，則無法啟用安全性預設。
- 如果您已啟用安全性預設，則無法啟用任何條件式存取原則。

如果已啟用安全性預設，系統會提示所有新使用者註冊 MFA 並使用 Microsoft Authenticator 應用程式。 

下表顯示啟用 MFA 與安全性預設和條件式存取原則的結果。

| Method | 啟用 | 停用 | 額外驗證方法 |
|:-------|:-----|:-------|:-------|
| **安全性預設**  | 無法使用條件式存取原則 | 可以使用條件式存取原則 | Microsoft Authenticator 應用程式 |
| **條件式存取原則** | 如果已啟用任何原則，則無法啟用安全性預設 | 如果已停用所有原則，則可啟用安全性預設  | 在 MFA 註冊期間由使用者指定  |
||||

## <a name="identity-and-device-access-configurations"></a>身分識別與裝置存取設定

建議採用身分識別和裝置存取設定和原則這類先決條件功能，其設定結合了條件式存取、Intune 和 Azure Active Directory Identity Protection 原則，決定是否應授予特定存取權要求及其授予條件。 這項決定的依據是登入的使用者帳戶、使用的裝置、使用者存取時使用的應用程式、建立存取要求的位置，以及對要求的風險評估。 這項功能有助於確保，只有經核准的使用者與裝置才可存取重要的資源。

>[!Note]
>Azure AD Identity Protection 需要 Microsoft 365 E5 隨附的 Azure AD Premium P2 授權。
>

身分識別與裝置存取原則的定義為分三層使用： 

- 對於存取您的應用程式和資料的身分識別和裝置，基準保護是安全性等級下限。
- 敏感性保護可為特定資料提供額外的安全性。 身分識別和裝置的安全性層級與裝置健康情況需求較高。
- 包含高度管制或保密資料環境的防護，適合通常屬於高度保密、包含營業，或是受資料法規約束的少量資料。 身分識別和裝置的安全性層級與裝置健康情況需求高出許多。 

這些層級及其對應的設定，可針對所有資料、身分識別和裝置，提供一致的保護層級。

Microsoft 強烈建議您在組織設定並推出身分識別和裝置存取原則，包括 Microsoft Teams、Exchange Online 和 SharePoint 專有的設定。 如需詳細資訊，請參閱[身分識別與裝置存取設定](microsoft-365-policies-configurations.md)。

## <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

在這一節中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。 Azure AD 身分識別保護提供多種方法，可協助防止攻擊者危及使用者帳戶的認證。

使用 Azure AD Identity Protection，您可以：

|功能|描述|
|:---------|:---------|
| 判斷並處理組織身分識別中潛在的弱點 | Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。 Azure AD Identity Protection 可使用此資料來產生報告和警示，協助您評估問題及採取行動。|
|偵測與組織身分識別相關的可疑活動，並自動進行回應處理|您可以設定以風險為基礎的原則，當達到指定風險層級時自動回應偵測到的問題。 除了由 Azure AD 和 Microsoft Intune 提供的其他條件式存取控制項之外，這些原則還可以自動封鎖存取權，或採取更正動作，包括密碼重設以及對後續登入要求 Azure Multi-Factor Authentication。 |
| 調查可疑事件，並使用系統管理動作加以解決 | 您可以使用安全性事件的相關資訊來調查風險事件。基本工作流程可用於追蹤調查及啟動修復動作，例如密碼重設。 |
|||

請參閱 [Azure AD Identity Protection 的相關詳細資訊](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。

請參閱[啟用 Azure AD Identity Protection 的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>適用於 MFA 和身分識別登入的系統管理員技術資源

- [Microsoft 365 適用的 MFA](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Microsoft 365 的身分識別藍圖](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD 訓練影片](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [設定 Azure Multi-Factor Authentication 註冊原則](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [身分識別與裝置存取設定](microsoft-365-policies-configurations.md)

## <a name="next-step"></a>下一步

[管理您的使用者帳戶](manage-microsoft-365-accounts.md)