---
title: 管理 Microsoft 365 身分識別管理
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
description: 深入瞭解如何使用 Microsoft 365 身分識別管理功能。
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910951"
---
# <a name="manage-microsoft-365-identity-governance"></a>管理 Microsoft 365 身分識別管理

身分識別治理就是保護、監控及稽核對關鍵資產的存取權，同時確保員工生產力。 例如，您可以使用身分識別治理來確保適當的使用者具有適當資源的存取權，並隨著時間判斷該存取權是否有所變更。

如需詳細資訊，請參閱 [Azure Active Directory (AZURE AD) 的身分識別管理 ](/azure/active-directory/governance/identity-governance-overview)。

## <a name="set-up-azure-ad-access-reviews"></a>設定 Azure AD 存取權檢閱

Azure AD access 評論可讓您複查使用者的存取權，以確保只有正確的人員繼續存取。 例如：

- 當組織加入新員工時，您必須確保他們具有適當的存取權，以具有生產力。
- 當該員工轉移至其他小組、位置或部門時，您必須確保在必要時移除其對先前小組、位置或部門的存取權。
- 當該員工或來賓離開組織時，您必須確保會移除其存取權。

若您的組織受限於安全性稽核來判斷使用者帳戶是否擁有太大的存取權 (如果違反產業或地區法規，則可能會受到處罰)，則這一點特別重要。

如需詳細資訊，請參閱 [存取權考核的概述](/azure/active-directory/governance/access-reviews-overview)。

請參閱下列文章來設定不同類型的存取權檢閱：

- [群組和應用程式](/azure/active-directory/governance/create-access-review)
- [Azure AD 角色](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 資源角色](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>設定 Azure AD 的權利管理

Wiht Azure AD 權利管理，您可以自動化存取要求工作流程、存取指派、評論和到期，以管理身分識別和存取生命週期。

您的員工需要存取各種群組、應用程式和網站，以執行其工作。 管理此存取可能具有挑戰性，因為需要變更、新增新的應用程式，或使用者需要其他存取權。 當您與其他組織共同作業時，可能不知道其他組織中的誰需要存取組織的資源，而外部使用者則不會知道組織所使用的應用程式、群組或網站。

Azure AD 權利管理可協助您更有效率地管理內部及外部使用者對群組、應用程式和 SharePoint 網站的存取。
 
如需詳細資訊，請參閱 [AZURE AD 權利管理的概述](/azure/active-directory/governance/entitlement-management-overview)。