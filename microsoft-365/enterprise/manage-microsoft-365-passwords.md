---
title: 管理 Microsoft 365 使用者帳戶密碼
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 瞭解如何管理 Microsoft 365 使用者帳戶密碼。
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328492"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>管理 Microsoft 365 使用者帳戶密碼

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以根據您的身分識別設定，以數種不同的方式管理 Microsoft 365 使用者帳戶密碼。 您可以在 [Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)、Active Directory 網域服務 (AD DS) 或 Azure Active Directory (azure AD) 系統管理中心中管理使用者帳戶。

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>規劃管理使用者帳戶密碼的位置和方式

您可以管理使用者帳戶的位置和方式，取決於您要用於 Microsoft 365 的身分識別模型。 這兩種模型是僅限雲端和混合式的模型。
  
### <a name="cloud-only"></a>僅雲端

您可以在下列情況中管理使用者帳戶密碼：

- [Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- Azure AD 系統管理中心
    
### <a name="hybrid"></a>混合式

使用混合式身分識別時，密碼會儲存在 AD DS 中，因此您必須使用內部部署 AD DS 工具來管理使用者帳戶密碼。 即使使用密碼雜湊同步處理 (PHS) ，在此中，Azure AD 會在 AD DS 中儲存已雜湊版本的已雜湊版本，您和使用者必須在 AD DS 中管理其密碼。

透過 [密碼寫回](#pw_writeback)，您的使用者可以透過 Azure AD 變更其 AD DS 密碼。

## <a name="prevent-bad-passwords"></a>防止不正確的密碼

您所有的使用者都應使用 [Microsoft 密碼指導方針](https://www.microsoft.com/research/publication/password-guidance)來建立使用者帳戶密碼。

若要防止使用者建立容易猜測的密碼，請使用 Azure AD 密碼保護，此功能會同時使用全域禁止密碼清單和您指定的選用自訂禁止密碼清單。 例如，您可以指定組織的特定字詞，例如：

- 品牌名稱
- 產品名稱
- 位置 (例如公司總部)
- 公司的特定內部條款
- 具有特定公司意義的縮寫

您可以在雲端和您的[內部部署 AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)[中](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)，禁止不良密碼。

## <a name="simplify-user-sign-in"></a>簡化使用者登入

Azure AD 無縫單一 Sign-On (Azure AD 無縫 SSO) 可搭配 PHS 及透過驗證 (PTA) ，以允許使用者登入使用 Azure AD 使用者帳戶的服務，而不必輸入密碼，而在許多情況下，他們的使用者名稱。 這可讓使用者更容易存取以雲端為基礎的應用程式，例如 Office 365，而不需要任何額外的內部部署元件，例如身分識別同盟伺服器。

您可以使用 Azure AD Connect 工具設定 Azure AD 無縫 SSO。 請參閱[設定 Azure AD 無縫 SSO 的指示](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>簡化 AD DS 的密碼更新

透過密碼寫回，您可以允許使用者透過 Azure AD 重設其密碼，然後再將其複寫到 AD DS。 使用者不需要存取其內部部署 AD DS 來更新其密碼。 對於沒有內部部署網路遠端存取連線的漫遊或遠端使用者而言，這非常有用。

為了充分利用 Azure AD Identity Protection 功能 (例如當偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，需要密碼回寫。

如需詳細資訊和設定指示，請參閱 [Azure AD SSPR 密碼回寫](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。

>[!Note]
>升級至最新版的 Azure AD Connect，以確保在新版本發行後能夠使用新功能並獲得最佳體驗。如需詳細資訊，請參閱 [Azure AD Connect 的自訂安裝](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。
>

## <a name="simplify-password-resets"></a>簡化密碼重設

自助密碼重設 (SSPR) 可讓使用者重設或解除鎖定密碼或帳戶。 您可以使用詳細的報告來追蹤使用者何時存取系統，以及使用通知來警示誤用或濫用。 您必須啟用 [密碼回寫](#pw_writeback) ，才能部署密碼重設。

請參閱[推出密碼重設的指示](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。

