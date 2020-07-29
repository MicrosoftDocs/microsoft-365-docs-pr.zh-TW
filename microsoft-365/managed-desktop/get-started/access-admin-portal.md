---
title: 存取系統管理入口網站
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 17696b18b4109b568bb1d616813ba40e2a9dccdc
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430468"
---
# <a name="access-the-admin-portal"></a>存取管理員入口網站

您的 Microsoft Managed 桌面服務閘道是 Microsoft [Azure 入口網站](https://portal.azure.com)。 如需更多有關使用和自訂 Azure 入口網站體驗的詳細資訊，請參閱[azure 入口網站檔](https://docs.microsoft.com/azure/azure-portal/)。 可用於預覽現在，您也可以在[Microsoft 端點管理員](https://endpoint.microsoft.com/)中找到 Microsoft 受管理的桌面。 如果您不熟悉此入口網站的裝置管理功能，請參閱[Microsoft 端點管理員的檔](https://docs.microsoft.com/mem/)。

您的管理帳戶需要特定許可權，才能存取 Microsoft 受管理的桌面系統管理入口網站。 您可以使用角色型存取控制（RBAC）管理組織內這些功能的系統管理員存取權。 如需 Azure Active Directory 角色的詳細資訊，請參閱[在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

指派系統管理員使用者帳戶下列任何角色，以確保存取權：

|Azure AD 角色  |Microsoft 受管理的桌面許可權  |
|---------|---------|
|全域系統管理員     | 具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。         |
|全域讀取者     | 具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的所有功能具有**唯讀許可權**。         |
|Intune 服務系統管理員     |  具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。       |
|服務支援系統管理員     | 具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。         |

> [!IMPORTANT]
> 只有全域系統管理員角色具有在 Microsoft Managed Desktop 中*註冊*您的組織所需的許可權。 請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶的許可權。 在 Microsoft 受管理的桌面完成註冊後，您應該永遠使用該角色，以完成其他工作所需的*最低*許可權。

## <a name="assigning-roles-to-administrators"></a>將角色指派給系統管理員

如果您需要協助指派 Azure Active Directory 角色，請參閱[在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。
