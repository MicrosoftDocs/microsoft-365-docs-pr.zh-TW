---
title: 步驟 15：設定動態群組成員資格
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
description: 了解自動群組成員資格並根據帳戶屬性進行設定。
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866635"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>步驟 15：設定動態群組成員資格

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在本步驟中，您將建立一系列的規則，這些規則會自動新增或移除使用者帳戶作為 Azure AD 群組成員的身分。這稱為*動態群組成員資格*。這些規則根據使用者帳戶屬性 (例如部門或國家/地區) 而定。

以下是規則適用的方式：

- 如果新的使用者帳戶與群組的所有規則相符，就會成為成員。
- 如果某個使用者帳戶不是群組的成員，但其屬性變更，使其符合該群組的所有規則，該帳戶就會成為該群組的成員。
- 若某個使用者帳戶與該群組的所有規則不相符，就不會將該帳戶新增至該群組。
- 如果某個使用者帳戶是群組的成員，但其屬性變更，使其不再符合該群組的所有規則，就會移除該帳戶身為該群組成員的身分。

若要使用動態成員資格，您必須先決定群組集合都有一組常見的使用者帳戶屬性。比方說，根據使用者帳戶屬性「部門」的設定為「銷售」，銷售部門的所有成員都應屬於 Azure AD 群組。

請參閱[指示以建立及設定動態 Azure AD 群組的規則](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。

此步驟的結果如下：

- 可針對動態成員資格而設定的一組 Azure AD 群組
- 針對每個動態群組的一組規則

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：自動化 Microsoft 365 企業版測試環境的授權與群組成員資格](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-dyn-groups)。

## <a name="next-step"></a>下一步

[識別基礎結構允出準則](identity-exit-criteria.md)
