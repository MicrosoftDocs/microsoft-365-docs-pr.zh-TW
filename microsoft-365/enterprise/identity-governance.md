---
title: 步驟 7：設定身分識別治理
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
description: 了解並設定 Azure AD 租用戶的身分識別治理。
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047356"
---
# <a name="step-7-configure-identity-governance"></a>步驟 7：設定身分識別治理

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

身分識別治理就是保護、監控及稽核對關鍵資產的存取權，同時確保員工生產力。 例如，您可以使用身分識別治理來確保適當的使用者具有適當資源的存取權，並隨著時間判斷該存取權是否有所變更。

如需 Azure Active Directory (Azure AD) 身分識別治理的詳細資訊，請參閱[此文章](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>設定 Azure AD 存取權檢閱

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*

在此步驟中，您將設定 Azure AD 存取權檢閱，這可讓您檢閱使用者的存取權，以確保只有適當的人員可以持續存取。 例如：

- 當組織加入新員工時，您必須確保他們具有適當的存取權，以具有生產力。
- 當該員工轉移至其他小組、位置或部門時，您必須確保在必要時移除其對先前小組、位置或部門的存取權。
- 當該員工或來賓離開組織時，您必須確保會移除其存取權。

若您的組織受限於安全性稽核來判斷使用者帳戶是否擁有太大的存取權 (如果違反產業或地區法規，則可能會受到處罰)，則這一點特別重要。

如需 Azure AD 存取權檢閱的詳細資訊，請參閱[此文章](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。

請參閱下列文章來設定不同類型的存取權檢閱：

- [群組和應用程式](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 資源角色](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-access-reviews)。

## <a name="next-step"></a>下一步

[識別基礎結構允出準則](identity-exit-criteria.md)

