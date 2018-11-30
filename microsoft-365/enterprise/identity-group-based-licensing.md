---
title: 步驟 12：設定自動授權
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定 Azure AD 群組之以群組為基礎的授權。
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866101"
---
# <a name="step-12-set-up-automatic-licensing"></a>步驟 12：設定自動授權

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步驟中，您會在 Azure AD 中設定安全性群組，以自動將授權從一組訂閱中指派給該群組的所有成員。這稱為*以群組為基礎的授權*。若使用者帳戶已新增至該群組或從其中移除，該群組訂閱的授權將會自動從使用者帳戶指派或移除。

針對 Microsoft 365 企業版，您將會設定 Azure AD 安全性群組來指派這些授權：

- Office 365 企業版 E3 或 E5
- Enterprise Mobility + Security (EMS) E3 或 E5

使用您在步驟 2 中找出的群組，尋找包含帳戶清單的群組，其中該群組中的所有使用者必須同時擁有 Office 365 和 EMS 授權。請確定您擁有有足夠的授權可供所有群組成員使用。如果您的授權已用完，在授權可供使用前將不會指派新使用者。

>[!Note]
>您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定*以群組為基礎的授權*。
>

查看 [Azure Active Directory 中以群組為基礎之授權基本概念](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)的其他資訊。

請參閱「[為 Azure 安全性群組設定以群組為基礎之授權的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」。

此步驟的結果如下：

- 您已識別出哪些安全性群組適用於以群組為基礎的授權。
- 您已為以群組為基礎的授權設定這些群組。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-group-license)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [監控租用戶和登入活動](identity-azure-ad-access-usage-reporting.md) |

