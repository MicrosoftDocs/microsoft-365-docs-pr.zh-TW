---
title: 步驟 3：保護和管理您的使用者登入
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 您可以將使用者登入 Windows 裝置和 Microsoft 365 變得更安全。
ms.openlocfilehash: c1379cfdd65204a27c8147ade8c8c8704e441f1f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801728"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>步驟 3：保護和管理您的使用者登入

![階段 2 - 身分識別](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>使用 Windows Hello 企業版

*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*

Windows 10 企業版的 Windows Hello 企業版在登入 Windows 裝置時，會使用加強雙因素驗證取代密碼。 雙因素是一種新的使用者認證類型，可與裝置和生物特徵或 PIN 相繫結。

如需詳細資訊，請參閱 [ Windows Hello 企業版概觀](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>設定 Azure Multi-Factor Authentication

*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*

在這個步驟，您將設定 Azure Multi-Factor Authentication (MFA)，為使用者登入和交易添加第二層安全性。 MFA 在使用者正確輸入其密碼之後，還會需要其他驗證方法。 沒有 MFA，密碼就是唯一的驗證方法。 但密碼的問題在於，許多密碼很容易被攻擊者猜測，或在不知情的情況下分享給不受信任的一方。

透過 MFA，第二層安全性可以是：

- 不容易遭到偽造或重複的個人和受信任裝置 (例如智慧型手機)。
- 生物識別屬性 (例如指紋)。

您將啟用 MFA 並使用[條件式存取原則](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)來設定次要驗證方法，這會允許您使用 Azure Active Directory (Azure AD) 群組來將 MFA 向指定的一組使用者 (例如試驗使用者、地理位置或部門) 推出。 請務必讓使用者知道即將啟用 MFA，使得他們了解需求 (例如強制使用智慧型手機登入) 並能順利登入。 

如需更多資訊，請參閱 [規劃雲端式 Azure Multi-Factor Authentication 部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：Azure Multi-Factor Authentication](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-mfa)。

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>防護認證洩露

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*

在這一節中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。 Azure AD 身分識別保護提供多種方法，可協助防止攻擊者危及使用者帳戶的認證。

使用 Azure AD Identity Protection，您可以：

|||
|:---------|:---------|
|判斷並處理組織身分識別中潛在的弱點|Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。 Azure AD Identity Protection 可使用此資料來產生報告和警示，協助您評估問題及採取行動。|
|偵測與組織身分識別相關的可疑活動，並自動進行回應處理|您可以設定以風險為基礎的原則，當達到指定風險層級時自動回應偵測到的問題。 除了由 Azure AD 和 Microsoft Intune 提供的其他條件式存取控制項之外，這些原則還可以自動封鎖存取權，或採取更正動作，包括密碼重設以及對後續登入要求 Azure Multi-Factor Authentication。|
|調查可疑事件，並使用系統管理動作加以解決|您可以使用安全性事件的相關資訊來調查風險事件。基本工作流程可用於追蹤調查及啟動修復動作，例如密碼重設。|

請參閱 [Azure AD Identity Protection 的相關詳細資訊](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。

請參閱[啟用 Azure AD Identity Protection 的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。

此步驟的結果會是您已啟用 Azure AD Identity Protection，並將其用於：

- 解決潛在的身分識別弱點。
- 偵測可能的認證洩露嘗試。
- 調查並解決持續的可疑身分識別事件。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-ident-prot)。

|||
|:-------|:-----|
|![步驟 4](./media/stepnumbers/Step4.png)| [新增使用者帳戶](identity-add-user-accounts.md) |
