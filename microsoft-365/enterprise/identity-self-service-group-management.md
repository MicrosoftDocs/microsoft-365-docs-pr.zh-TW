---
title: 步驟 14：允許使用者建立及管理自己的群組
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
description: 了解及設定 Azure AD 自助式群組管理
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866448"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>步驟 14：允許使用者建立及管理自己的群組

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步驟中，您將識別由群組擁有者而不是 IT 系統管理員管理的 Azure Active Directory (AD) 群組。這個功能又稱為「自助式群組管理」**，可以讓沒有系統管理角色的群組擁有者建立及管理安全性群組。 

使用者可要求安全性群組的成員資格，該要求會傳送給群組擁有者，而不是 IT 系統管理員。這可將群組成員資格的每日控制委派給小組、專案或業務擁有者，他們了解群組的業務使用，可以管理成員資格。

>[!Note]
>自助式群組管理僅限用於 Azure AD 安全性和 Office 365 群組。它不適用於擁有郵件功能的群組、通訊群組清單或任何從內部部署 Windows Server Active Directory (AD) 同步處理的群組。
>

如需詳細資訊，請參閱[設定 Azure AD 群組自助式管理的指示](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-self-service-groups)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [設定動態群組成員資格](identity-automatic-group-membership.md) |
