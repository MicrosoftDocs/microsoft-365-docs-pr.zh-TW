---
title: 步驟 1： 使用 MFA 提升遠端工作者的登入安全性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 您的遠端工作者必須使用多重要素驗證 (MFA) 來登入。
ms.openlocfilehash: a0350be5cf75024fbefadb21ae56017bf64ca0d8
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213469"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>步驟 1： 使用 MFA 提升遠端工作者的登入安全性

若要提升遠端工作者的登入安全性，請使用多重要素驗證 (MFA)。 MFA 會要求使用者登入程序另外遵守使用者帳戶密碼以外的驗證規定。 惡意使用者即使確定了使用者帳戶的密碼，還必須能夠回應另外的驗證機制 (例如，傳送至智慧型手機的簡訊)，才能獲得存取權。

![正確的密碼加上其他驗證則可導致順利登入](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Microsoft 強烈建議包括遠端工作者 (特別是系統管理員) 在內的所有使用者都使用 MFA。

根據您的 Microsoft 365 方案，您有三種方法可以要求使用者使用 MFA。

|方案  |建議  |
|---------|---------|
|Microsoft 365 方案 (不含 Azure AD Premium P1 或 P2)     |[在 Azure AD 中啟用安全性預設](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性預設包含了適用於使用者和系統管理員的 MFA。   |
|Microsoft 365 E3 (含 Azure AD Premium P1)     | 使用[常見的條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則： <br>- [要求系統管理員使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [要求所有使用者使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (含 Azure AD Premium P2)     | 利用 Azure AD Identity Protection，藉由建立下列兩種原則來開始實作 Microsoft [建議的一組條件式存取和相關原則](../enterprise/identity-access-policies.md)：<br> - [登入風險為中或高時，需要 MFA](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [封鎖不支援新式驗證的用戶端](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [高風險使用者必須變更密碼](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>安全性預設

安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。 這些訂用帳戶會開啟安全性預設，而***要求所有使用者都必須使用 MFA 與 Microsoft Authenticator 應用程式***。
 
使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。 14 天過後，使用者就無法登入，除非其完成 MFA 註冊。

安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。 您可以停用安全性預設，改為使用 MFA 與條件式存取原則或改為使用個別帳戶。

如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

## <a name="conditional-access-policies"></a>條件式存取原則

條件式存取原則是一組規則，可指定要在什麼條件下評估和允許登入。 例如，您可以建立敘述如下的條件式存取原則：

- 如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。

此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。

您也可以使用條件式存取原則來執行更進階的功能，例如要求登入必須是來自符合規範的裝置 (例如執行 Windows 10 的膝上型電腦)。

條件式存取需要 Azure AD Premium P1，此方案隨附於 Microsoft 365 E3 和 E5。

如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

## <a name="azure-ad-identity-protection-support"></a>Azure AD Identity Protection 支援

使用 Azure AD Identity Protection，您可建立敘述如下的額外條件式存取原則：

- 如果經判斷登入風險屬於中或高風險，則要求 MFA。

Azure AD Identity Protection 需要 Azure AD Premium P2，此方案隨附於 Microsoft 365 E5。

如需詳細資訊，請參閱[風險型條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)。

## <a name="using-these-methods-together"></a>共同使用這些方法

請記住下列事項：

- 如果您已啟用任何條件式存取原則，則無法啟用安全性預設。
- 如果您已啟用安全性預設，則無法啟用任何條件式存取原則。

如果已啟用安全性預設，系統會提示所有新使用者註冊 MFA 並使用 Microsoft Authenticator 應用程式。 

下表顯示啟用 MFA 與安全性預設和條件式存取原則的結果。

|| 啟用 | 停用 | 額外驗證方法 |
|:-------|:-----|:-------|:-------|
| **安全性預設**  | 無法使用條件式存取原則 | 可以使用條件式存取原則 | Microsoft Authenticator 應用程式 |
| **條件式存取原則** | 如果已啟用任何原則，則無法啟用安全性預設 | 如果已停用所有原則，則可啟用安全性預設  | 在 MFA 註冊期間由使用者指定  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>適用於 MFA 和身分識別的系統管理員訓練與技術資源

- [Microsoft 365 的 MFA 規劃](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [Azure AD 可協助您啟用遠端工作的五大方法](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [規劃及部署 Microsoft 365 的身分識別基礎結構](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Azure Academy Azure AD 訓練影片](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [設定 Azure Multi-Factor Authentication 註冊原則](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>步驟 1 的結果

部署 MFA 之後，您的使用者：

- 必須使用 MFA 來登入。
- 已完成 MFA 註冊程序，且會使用 MFA 來進行所有登入。

## <a name="next-step"></a>後續步驟

繼續[步驟 2](empower-people-to-work-remotely-remote-access.md)，以為內部部署應用程式和服務提供遠端存取。
