---
title: 步驟 4：設定安全的使用者驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定使用者帳戶的多重要素驗證。
ms.openlocfilehash: 44d878a347e7b01263f9ba3a82f6443f5710dc43
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285462"
---
# <a name="step-4-configure-secure-user-authentication"></a>步驟 4：設定安全的使用者驗證

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>設定多重要素驗證

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在本步驟中，您將設定多重要素驗證 (MFA)，以將第二層安全性新增至使用者登入和交易。在使用者已正確地輸入密碼後，MFA 需要額外的驗證方法。少了 MFA，密碼是唯一的驗證方式。密碼的問題是攻擊者容易猜測許多密碼或在不知情的情況下與未受信任的對象共用密碼。

透過 MFA，第二層安全性可以是：

- 不容易遭到偽造或重複的個人和受信任裝置 (例如智慧型手機)。
- 生物識別屬性 (例如指紋)。

您將啟用 MFA，並以每個使用者帳戶為基礎設定次要驗證方法。請務必讓使用者知道 MFA 已啟用，他們就了解要求 (例如強制使用智慧型手機登入) 並能順利登入。

如需詳細資訊，請參閱[規劃多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。

>[!Note]
>在部分應用程式中 (例如 Microsoft Office 2010 或更舊版本和 Apple Mail) 您無法使用 MFA。若要使用這些應用程式，您將需要使用「應用程式密碼」取代您的傳統密碼。應用程式密碼允許應用程式略過 MFA 並繼續執行。若需應用程式密碼的更多資訊，請參閱[建立 Office 365 的應用程式密碼](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：多重要素驗證](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-mfa)。



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>防護認證洩露

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*

在這一節中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。 Azure AD Identity Protection 提供許多方法，協助防止攻擊者透過您的帳戶和群組而入侵，以及協助保護您最寶貴的資料。

使用 Azure AD Identity Protection，您可以：

|||
|:---------|:---------|
|判斷並處理組織身分識別中潛在的弱點|Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。Identity Protection 可使用此資料產生報告和警訊，協助您評估問題及採取行動。|
|偵測與組織身分識別相關的可疑活動，並自動進行回應處理|您可以設定風險原則，在達到指定的風險層級時，會自動回應偵測到的問題。由 Azure Active Directory 和 Enterprise Mobility + Security (EMS) 提供的這些原則，以及其他條件式存取控制，可自動封鎖存取或採取修正動作，包括密碼重設和要求後續登入的多重要素驗證。|
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

## <a name="monitor-tenant-and-sign-in-activity"></a>監控租用戶和登入活動

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在此步驟中，您將會使用 Azure AD 報告檢視稽核記錄和登入活動。兩種類型的報告皆可供使用。

**稽核記錄活動報告**會報告 Azure AD 租用戶中執行的每項工作歷程記錄。這份報告會回答如以下的問題：

- 哪個人員已將某人新增至系統管理群組？
- 哪個使用者正在登入特定的應用程式？
- 密碼重設的發生次數？

**登入活動報告**會報告哪個人員執行稽核記錄報告所報告的工作。這份報告會回答如以下的問題：

- 針對調查中的特定使用者，他們的登入模式是什麼？
- 一天、週或月的登入活動量為何？
- 這些登入嘗試不成功的次數有多少，且是針對哪一個帳戶？

如需報告以及如何存取他們的詳細資訊，請參閱 [Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。

在此步驟的結果中，您將了解這些報告以及如何使用這些報告來深入了解用於規劃與安全性目的之 Azure AD 事件與活動。



## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [簡化使用者的存取權](identity-password-reset.md) |

