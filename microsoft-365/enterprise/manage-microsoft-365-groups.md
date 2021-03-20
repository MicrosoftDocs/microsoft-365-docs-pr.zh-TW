---
title: 管理 Microsoft 365 群組
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
description: 瞭解如何管理 Microsoft 365 群組。
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911004"
---
# <a name="manage-microsoft-365-groups"></a>管理 Microsoft 365 群組

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以根據您的設定，以數種不同的方式管理 Microsoft 365 群組。 您可以在 [Microsoft 365 系統管理中心](../admin/add-users/index.yml)、PowerShell、Active Directory 網域服務 (AD DS) 或 [azure Active DIRECTORY (azure AD) admin center](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)中管理使用者帳戶。 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>規劃管理群組的位置和方式

您可以管理使用者帳戶的位置和方式，取決於您要用於 Microsoft 365 的身分識別模型。 這兩個整體模型為雲端且混合式。
  
### <a name="cloud-only"></a>僅雲端

您可以使用下列方式建立及管理群組：

- [Microsoft 365 系統管理中心](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 系統管理中心](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>混合式

AD DS 群組與 Microsoft 365 從 AD DS 同步處理，因此您必須使用內部部署 AD DS 工具來管理這些群組。

您也可以建立和管理獨立于 AD DS 群組的 Azure AD 群組，但可包含 AD DS 中的使用者和群組。 在此情況下，您可以使用：

- [Microsoft 365 系統管理中心](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 系統管理中心](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>允許使用者建立及管理自己的群組

Azure AD 允許群組擁有者管理的群組，而不是由 IT 系統管理員來管理。 此功能也稱為 *自助服務群組管理*，允許未獲指派系統管理角色的群組擁有者建立和管理安全群組。 

使用者可要求安全性群組的成員資格，該要求會傳送給群組擁有者，而不是 IT 系統管理員。這可將群組成員資格的每日控制委派給小組、專案或業務擁有者，他們了解群組的業務使用，可以管理成員資格。

>[!Note]
>自助群組管理功能僅適用於 Azure AD 安全性和 Microsoft 365 群組。 這不適用於已啟用郵件功能的群組、通訊群組清單或任何已從 AD DS 同步處理的群組。
>

如需詳細資訊，請參閱[設定 Azure AD 群組自助管理的指示](/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

## <a name="set-up-dynamic-group-membership"></a>設定動態群組成員資格

Azure AD 支援設定一系列規則，自動將使用者帳戶新增或移除為 Azure AD 群組的成員。 這稱為 *動態群組成員資格*。 規則會以使用者帳戶屬性為基礎，例如部門或國家/地區。

以下是規則適用的方式：

- 如果新的使用者帳戶與群組的所有規則相符，就會成為成員。
- 如果某個使用者帳戶不是群組的成員，但其屬性變更，使其符合該群組的所有規則，該帳戶就會成為該群組的成員。
- 若某個使用者帳戶與該群組的所有規則不相符，就不會將該帳戶新增至該群組。
- 如果某個使用者帳戶是群組的成員，但其屬性變更，使其不再符合該群組的所有規則，就會移除該帳戶身為該群組成員的身分。

若要使用動態成員資格，您必須先決定群組集合都有一組常見的使用者帳戶屬性。比方說，根據使用者帳戶屬性「部門」的設定為「銷售」，銷售部門的所有成員都應屬於 Azure AD 群組。

請參閱[指示以建立及設定動態 Azure AD 群組的規則](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。

## <a name="set-up-automatic-licensing"></a>設定自動授權

您可以在 Azure AD 中設定安全性群組，以自動將一組訂閱的授權指派給群組的所有成員。 這稱為 *群組型授權*。 如果在群組中新增或移除使用者帳戶，則將自動指派或從使用者帳戶中取消指派群組訂閱的授權。

針對 Microsoft 365 企業版，您將設定 Azure AD 安全性群組，以指派適當的 Microsoft 365 企業版授權。

請確定您有足夠的授權可供所有群組成員使用。 如果您用完了授權，除非有授權可供使用，否則將不會對新使用者指派授權。

>[!Note]
>您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定以群組為基礎的授權。
>

如需詳細資訊，請參閱 [在 AZURE AD 中以群組為基礎的授權基礎](/azure/active-directory/active-directory-licensing-whatis-azure-portal)。

請參閱 [指示，設定 Azure 安全性群組的群組型授權](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。