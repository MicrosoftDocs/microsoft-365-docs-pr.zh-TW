---
title: 步驟6：使用群組更輕鬆地進行管理
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
description: 了解及設定 Azure AD 自助群組管理。
ms.openlocfilehash: 97077f5e047f55ea6bf6e532d25d25f4682ff179
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981774"
---
# <a name="step-6-use-groups-for-easier-management"></a>步驟6：使用群組更輕鬆地進行管理

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>允許使用者建立及管理自己的群組

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在本節中，您將識別可由群組擁有者而非 IT 系統管理員管理的Azure Active Directory (Azure AD) 群組。 此功能也稱為*自助服務群組管理*，允許未獲指派系統管理角色的群組擁有者建立和管理安全群組。 

使用者可要求安全性群組的成員資格，該要求會傳送給群組擁有者，而不是 IT 系統管理員。這可將群組成員資格的每日控制委派給小組、專案或業務擁有者，他們了解群組的業務使用，可以管理成員資格。

>[!Note]
>自助群組管理功能僅適用於 Azure AD 安全性和 Office 365 群組。 它不適用於已啟用郵件功能的群組、通訊群組清單或已從內部部署 Active Directory 網域服務 (AD DS) 同步處理的任何群組。
>

如需詳細資訊，請參閱[設定 Azure AD 群組自助管理的指示](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-self-service-groups)。

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>設定動態群組成員資格

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您將建立一系列規則，來自動新增或移除作為 Azure AD 群組成員的使用者帳戶。 這稱為*動態群組成員資格*。 規則會以使用者帳戶屬性為基礎，例如部門或國家/地區。

以下是規則適用的方式：

- 如果新的使用者帳戶與群組的所有規則相符，就會成為成員。
- 如果某個使用者帳戶不是群組的成員，但其屬性變更，使其符合該群組的所有規則，該帳戶就會成為該群組的成員。
- 若某個使用者帳戶與該群組的所有規則不相符，就不會將該帳戶新增至該群組。
- 如果某個使用者帳戶是群組的成員，但其屬性變更，使其不再符合該群組的所有規則，就會移除該帳戶身為該群組成員的身分。

若要使用動態成員資格，您必須先決定群組集合都有一組常見的使用者帳戶屬性。比方說，根據使用者帳戶屬性「部門」的設定為「銷售」，銷售部門的所有成員都應屬於 Azure AD 群組。

請參閱[指示以建立及設定動態 Azure AD 群組的規則](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。

這一節的結果如下：

- 可針對動態成員資格而設定的一組 Azure AD 群組
- 針對每個動態群組的一組規則

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-dyn-groups)。

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>設定自動授權

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您將在 Azure AD 中設定安全性群組，以自動將一組訂閱中的授權指派給該群組的所有成員。 這稱為*群組型授權*。 如果在群組中新增或移除使用者帳戶，則將自動指派或從使用者帳戶中取消指派群組訂閱的授權。

針對 Microsoft 365 企業版，您將設定 Azure AD 安全性群組，以指派適當的 Microsoft 365 企業版授權。

請確定您有足夠的授權可供所有群組成員使用。 如果您用完了授權，除非有授權可供使用，否則將不會對新使用者指派授權。

>[!Note]
>您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定*以群組為基礎的授權*。
>

查看 [Azure Active Directory 中以群組為基礎之授權基本概念](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)的其他資訊。

請參閱「[為 Azure 安全性群組設定以群組為基礎之授權的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」。

這一節的結果如下：

- 您已識別出哪些安全性群組適用於以群組為基礎的授權。
- 您已為以群組為基礎的授權設定這些群組。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-group-license)。

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [設定身分識別治理](identity-governance.md) |
