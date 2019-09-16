---
title: 步驟 5：簡化使用者的存取權
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解及設定 Azure AD 的自助密碼重設 (SSPR)。
ms.openlocfilehash: ec81b2931fd4ad599ffcf983ea8a7d764c56404a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981794"
---
# <a name="step-5-simplify-access-for-users"></a>步驟 5：簡化使用者的存取權

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>簡化密碼更新

*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您會允許使用者透過 Azure Active Directory (Azure AD) 重設其密碼，然後複製到本機 Active Directory 網域服務 (AD DS)。 這個程序也稱為密碼回寫。 使用密碼回寫，使用者不需要透過使用者帳戶與其屬性儲存在其中的內部部署 AD DS 來更新其密碼。 對於沒有內部部署網路遠端存取連線的漫遊或遠端使用者而言，這非常有用。

為了充分利用 Azure AD Identity Protection 功能 (例如當偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，需要密碼回寫。

如需詳細資訊和設定指示，請參閱 [Azure AD SSPR 密碼回寫](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。

>[!Note]
>升級至最新版的 Azure AD Connect，以確保在新版本發行後能夠使用新功能並獲得最佳體驗。如需詳細資訊，請參閱 [Azure AD Connect 的自訂安裝](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：密碼回寫](password-writeback-m365-ent-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-writeback)。

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>簡化密碼重設

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您會啟用自助密碼重設 (SSPR)，允許使用者重設或解除鎖定其密碼或帳戶。 您可以使用詳細的報告來追蹤使用者何時存取系統，以及使用通知來警示誤用或濫用。 您必須先啟用密碼回寫，才可以部署密碼重設。

請參閱[推出密碼重設的指示](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：密碼重設](password-reset-m365-ent-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-reset)。


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>簡化使用者登入

*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您將會設定 Azure Active Directory 無縫單一登入 (Azure AD 無縫 SSO)，讓使用者可登入使用 Azure AD 使用者帳戶的服務，而不需要輸入密碼，以及在許多情況下不需輸入使用者名稱。 這可讓使用者更容易存取以雲端為基礎的應用程式，例如 Office 365，而不需要任何額外的內部部署元件，例如身分識別同盟伺服器。

您可以使用 Azure AD Connect 工具設定 Azure AD 無縫 SSO。

請參閱[設定 Azure AD 無縫 SSO 的指示](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：Azure AD 無縫單一登入](single-sign-on-m365-ent-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-sso)。


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>自訂 Office 365 登入頁面

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您將會新增公司的名稱、標誌和其他辨識項目，藉此協助使用者辨識組織的登入頁面。 

使用 Microsoft 365 企業版，您可以自訂登入和存取面板頁面的外觀，讓頁面中出現公司的標誌、色彩配置和自訂的使用者資訊。 

如需詳細資訊，請參閱[將公司商標新增至 Office 365 登入頁面](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。

如需設定的指示，請參閱[將公司商標新增至登入和存取面板頁面](http://aka.ms/aadpaddbranding)。

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-custom-sign-in)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [使用群組更輕鬆地進行管理](identity-self-service-group-management.md) |


