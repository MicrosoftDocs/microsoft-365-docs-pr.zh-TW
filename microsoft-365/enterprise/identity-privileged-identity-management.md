---
title: 步驟 3：設定隨選全域管理員
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解及設定 Azure AD Privileged Identity Management。
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866310"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>步驟 3：設定隨選全域管理員

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步驟中，您會設定 Azure AD Privileged Identity Management (PIM) 來減少全域系統管理員帳戶容易受到惡意使用者攻擊的時間。PIM 可在需要時提供隨需、即時的全域系統管理員角色指派。  

全域系統管理員帳戶不再是永久管理員，而是變為合格的管理員。全域系統管理員角色在有人需要它之前為無作用狀態。您需要完成啟動程序，在一段特定時間內將全域系統管理員角色新增到全域系統管理員帳戶。時間到期後，PIM 會從全域系統管理員帳戶中移除此全域系統管理員角色。

Microsoft 365 企業版 E5 隨附 Azure Active Directory Premium P2，而 P2 便有 PIM 功能。或者，您可以為您的全域系統管理員帳戶購買單獨的 Azure Active Directory Premium P2 授權。

若要為 Azure AD 租用戶和全域系統管理員帳戶啟用 Azure PIM，請參閱[什麼是 Azure AD Privileged Identity Management？](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

若要開發可保護特殊存取權避免受到網路攻擊的全面性藍圖，請參閱[在 Azure AD 中保護混合式部署和雲端部署的特殊權限存取](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)。

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-pim)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [簡化密碼重設](identity-password-reset.md) |

