---
title: 步驟 1： 使用 MFA 提升遠端工作者的登入安全性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 您的遠端工作者必須使用多重要素驗證 (MFA) 來登入。
ms.openlocfilehash: aa9b122ca18c4d8a8123914ee2d29d41c9ec789e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681453"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>步驟 1： 使用 MFA 提升遠端工作者的登入安全性

若要提升遠端工作者的登入安全性，請使用多重要素驗證 (MFA)。 MFA 會要求使用者登入程序另外遵守使用者帳戶密碼以外的驗證規定。 惡意使用者即使確定了使用者帳戶的密碼，還必須能夠回應另外的驗證機制 (例如，傳送至智慧型手機的簡訊)，才能獲得存取權。

![正確的密碼加上其他驗證則可導致順利登入](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Microsoft 強烈建議包括遠端工作者 (特別是系統管理員) 在內的所有使用者都使用 MFA。

根據您的 Microsoft 365 方案，您有三種方法可以要求使用者使用 MFA。

|方案  |建議  |
|---------|---------|
|所有的 Microsoft 365 方案（不含 Azure AD Premium P1 或 P2 授權）     |[在 Azure AD 中啟用安全性預設](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性預設包含了適用於使用者和系統管理員的 MFA。   |
|Microsoft 365 E3 （含 Azure AD Premium P1 授權）     | 使用[常見的條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則： <br>- [要求系統管理員使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [要求所有使用者使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 （含 Azure AD Premium P2 授權）     | 利用 Azure AD Identity Protection，藉由建立下列原則來開始實作 Microsoft [建議的一組條件式存取和相關原則](../security/office-365-security/identity-access-policies.md)：<br> - [登入風險為中或高時，需要 MFA](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [封鎖不支援新式驗證的用戶端](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [高風險使用者必須變更密碼](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>安全性預設

安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。 這些訂閱會開啟安全性預設，而***要求所有使用者都必須使用 MFA 與 Microsoft Authenticator 應用程式**_。
 
使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。 14 天過後，使用者就無法登入，除非其完成 MFA 註冊。

安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。 您可以停用安全性預設，改為使用 MFA 與條件式存取原則或改為使用個別帳戶。

如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

## <a name="conditional-access-policies"></a>條件式存取原則

條件式存取原則是一組規則，可指定要在什麼條件下評估和允許登入。 例如，您可以建立敘述如下的條件式存取原則：

- 如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。

此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。

您也可以使用條件式存取原則來執行更進階的功能，例如要求登入必須是來自符合規範的裝置 (例如執行 Windows 10 的膝上型電腦)。

[條件式存取] 需有 Azure AD Premium P1 授權，已附加在 Microsoft 365 E3 和 E5 套裝中。

如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

## <a name="azure-ad-identity-protection-support"></a>Azure AD Identity Protection 支援

使用 Azure AD Identity Protection，您可建立敘述如下的額外條件式存取原則：

- 如果經判斷登入風險屬於中或高風險，則要求 MFA。

Azure AD Identity Protection 需有已附加在 Microsoft 365 E5 中的 Azure AD Premium P2 的授權資料。

如需詳細資訊，請參閱[風險型條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)。

利用 Azure AD Identity Protection，您也可以建立原則，以要求您的使用者註冊使用 MFA。 如需詳細資訊，請參閱[設定 Azure Multi-Factor Authentication 註冊原則](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)


## <a name="using-these-methods-together"></a>共同使用這些方法

請記住下列事項：

- 如果您已啟用任何條件式存取原則，則無法啟用安全性預設。
- 如果您已啟用安全性預設，則無法啟用任何條件式存取原則。

如果已啟用安全性預設，系統會提示所有新使用者註冊 MFA 並使用 Microsoft Authenticator 應用程式。 

下表顯示啟用 MFA 與安全性預設和條件式存取原則的結果。

| Method | 啟用 | 停用 | 額外驗證方法 |
|:-------|:-----|:-------|:-------|
| _*安全性預設**  | 無法使用條件式存取原則 | 可以使用條件式存取原則 | Microsoft Authenticator 應用程式 |
| **條件式存取原則** | 如果已啟用任何原則，則無法啟用安全性預設 | 如果已停用所有原則，則可啟用安全性預設  | 在 MFA 註冊期間由使用者指定  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a>讓您的使用者重設自己的密碼

自助式密碼重設（SSPR）可讓使用者自行重設自己的密碼，而不會影響到 IT 人員的工作。 使用者可隨時隨地快速重設自己的密碼。 如需詳細資訊，請參閱[規劃 Azure AD 自助式密碼重設部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>使用 Azure AD 登入 SaaS 應用程式

除了為使用者提供雲端驗證之外，Azure AD 也可以是您保護所有應用程式 (無論是內部部署、位於 Microsoft 雲端或其他雲端) 的核心方式。 透過[將您的應用程式整合到 Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration)，您可以輕鬆地讓遠端工作者探索所需的應用程式，並安全地登入這些應用程式。

## <a name="admin-technical-resources-for-mfa-and-identity"></a>適用於 MFA 和身分識別的系統管理員技術資源

- [Azure AD 可協助您啟用遠端工作的五大方法](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Microsoft 365 的身分識別藍圖](../enterprise/identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD 訓練影片](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a>步驟 1 的結果

部署 MFA 之後，您的使用者：

- 必須使用 MFA 來登入。
- 已完成 MFA 註冊程序，並使用 MFA 進行所有的登入動作。
- 可使用 SSPR 進行密碼重設。

## <a name="next-step"></a>下一步

[![步驟 2：可遠端存取內部部署應用程式和服務](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

繼續[步驟 2](empower-people-to-work-remotely-remote-access.md)，以為內部部署應用程式和服務提供遠端存取。
