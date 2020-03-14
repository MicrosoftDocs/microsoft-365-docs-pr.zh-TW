---
title: 步驟2：保護您的密碼
f1.keywords:
- NOCSH
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
description: 您必須在組織中強化且易於管理您的密碼。
ms.openlocfilehash: c0ad9e2ad86cb803484e3d350fe112580610f509
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633091"
---
# <a name="step-2-secure-your-passwords"></a>步驟 2：保護您的密碼

![第 2 階段 - 身分識別](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>防止不正確的密碼

*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*

您所有的使用者都應使用 [Microsoft 密碼指導方針](https://www.microsoft.com/research/publication/password-guidance/)來建立使用者帳戶密碼。

若要防止使用者建立容易猜測的密碼，請使用 Azure AD 密碼保護，此功能會同時使用全域禁止密碼清單和您指定的選用自訂禁止密碼清單。 例如，您可以指定組織的特定字詞，例如：

- 品牌名稱
- 產品名稱
- 位置 (例如公司總部)
- 公司的特定內部條款
- 具有特定公司意義的縮寫

您可以在[雲端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)和[內部部署 Active Directory 網域服務 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) 中禁止使用不正確的密碼。

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-password-prot)。

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>簡化密碼重設

*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*

在這一節中，您會啟用自助密碼重設 (SSPR)，允許使用者重設或解除鎖定其密碼或帳戶。 您可以使用詳細的報告來追蹤使用者何時存取系統，以及使用通知來警示誤用或濫用。 您必須先啟用密碼回寫，才可以部署密碼重設。

請參閱[推出密碼重設的指示](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：密碼重設](password-reset-m365-ent-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-reset)。


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>簡化使用者登入

*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您將會設定 Azure Active Directory 無縫單一登入 (Azure AD 無縫 SSO)，搭配密碼雜湊同步 (PHS)和傳遞驗證 (PTA) 使用，以便使用者可登入使用 Azure AD 使用者帳戶的服務，而不需要輸入密碼，以及在許多情況下不需輸入使用者名稱。 這可讓使用者更容易存取以雲端為基礎的應用程式，例如 Office 365，而不需要任何額外的內部部署元件，例如身分識別同盟伺服器。

您可以使用 Azure AD Connect 工具設定 Azure AD 無縫 SSO。

請參閱[設定 Azure AD 無縫 SSO 的指示](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：Azure AD 無縫單一登入](single-sign-on-m365-ent-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-sso)。


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>自訂 Office 365 登入頁面

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您將會新增公司的名稱、標誌和其他辨識項目，藉此協助使用者辨識組織的登入頁面。 

使用 Microsoft 365 企業版，您可以自訂登入和存取面板頁面的外觀，讓頁面中出現公司的標誌、色彩配置和自訂的使用者資訊。 

如需詳細資訊，請參閱[將公司商標新增至 Office 365 登入頁面](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。

如需設定的指示，請參閱[將公司商標新增至登入和存取面板頁面](https://aka.ms/aadpaddbranding)。

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-custom-sign-in)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 3](../media/stepnumbers/Step3.png)| [保護和管理您的使用者登入](identity-secure-user-sign-ins.md) |
