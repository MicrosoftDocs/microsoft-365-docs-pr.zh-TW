---
title: 存取系統管理入口網站
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 2ac0bb01c1a941d460e92c7e75e765ceb85b2bc0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546571"
---
# <a name="access-the-admin-portal"></a>存取管理員入口網站

您的 Microsoft Managed 桌面服務閘道是 Microsoft [Azure 入口網站](https://portal.azure.com)。 如需更多有關使用和自訂 Azure 入口網站體驗的詳細資訊，請參閱 [azure 入口網站檔](https://docs.microsoft.com/azure/azure-portal/)。 可用於預覽現在，您也可以在 [Microsoft 端點管理員](https://endpoint.microsoft.com/)中找到 Microsoft 受管理的桌面。 如果您不熟悉此入口網站的裝置管理功能，請參閱 [Microsoft 端點管理員的檔](https://docs.microsoft.com/mem/)。

您的管理帳戶需要特定許可權，才能存取 Azure 入口網站或 Microsoft 端點管理員中的 Microsoft 受管理桌面系統管理功能。 您可以使用以角色為基礎的存取控制 (RBAC) ，管理組織內這些功能的系統管理員存取權。 您可以使用數種 Azure AD 系統管理員角色和內建自訂角色，為 Microsoft Managed Desktop Admin 入口網站中的不同功能提供更精細的控制。 如需 Azure Active Directory 角色的詳細資訊，請參閱 [在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 與適用于各種 Microsoft 產品和服務的 AAD 系統管理員角色不同，自訂角色是針對 Microsoft 受管理的桌面所特有，且只會保證可存取此服務的系統管理功能。 系統管理員可以個別或結合 AAD 系統管理員角色，將自訂角色指派給使用者，以將 Microsoft 管理的桌面許可權新增至現有的系統管理員帳戶。

您可以指派下列每個角色，以提供不同的存取層級：

|Azure AD 角色  |Microsoft 受管理的桌面許可權  |
|---------|---------|
|全域系統管理員     | 具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的 **讀取和寫入權限** 。         |
|全域讀取者     | 具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的所有功能具有 **唯讀許可權** 。         |
|Intune 服務系統管理員     |  具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的 **讀取和寫入權限** 。 **變更：** 在9月2020日的系統管理員中，此角色將無法存取 Microsoft 受管理的桌面安全性功能。       |
|服務支援系統管理員     | 具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的 **讀取和寫入權限** 。 **變更：** 在9月2020日的系統管理員中，此角色將無法存取 Microsoft 受管理的桌面安全性功能。         |
|安全性系統管理員 | ** 預覽2020年9月 () ** 具有此角色的系統管理員對管理員入口網站中 Microsoft 受管理的電腦具有安全性相關功能的所有功能和寫入權限，具有唯讀許可權。 |
|安全性讀取者 | ** 預覽2020年9月 () **  具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的所有功能具有唯讀許可權。|

> [!IMPORTANT]
> 只有全域系統管理員角色具有在 Microsoft Managed Desktop 中 *註冊* 您的組織所需的許可權。 請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶的許可權。 在 Microsoft 受管理的桌面完成註冊後，您應該永遠使用該角色，以完成其他工作所需的 *最低* 許可權。

 
|自訂角色  |Microsoft 受管理的桌面許可權  |
|---------|---------|
|Microsoft 受管理的桌面服務管理員  | ** 預覽2020年9月 () ** 指派給使用者時，此角色可讓系統管理員讀取與 Microsoft Managed Desktop Admin 入口網站中的安全性無關的 **功能 & 寫入權限** 。  |
|Microsoft 受管理的桌面服務讀取器 | ** 預覽2020年9月 () ** 指派給使用者時，此角色會將「管理員唯讀」許可權授與 Microsoft Managed Desktop Admin 入口網站中 **與安全性** 無關的功能。 |
|Microsoft 受管理的桌面安全性管理員 | ** 預覽2020年9月 () ** 指派給使用者時，此角色可讓系統管理員讀取權限，只對 Microsoft Managed Desktop Admin 入口網站中的 **安全性相關功能 & 寫入權限** 。   |

> [!NOTE]
> 安全性功能包括安全性相關的通訊、安全性連絡人的管理、安全性相關支援要求的管理，以及與安全性相關的報表存取。 

## <a name="assigning-roles-to-administrators"></a>將角色指派給系統管理員

如果您需要協助指派 Azure Active Directory 角色，請參閱 [在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

為便於管理內建角色，已為每個自訂角色建立安全性群組 (例如「新式工作場所角色–安全性管理員」 ) 。 若要將使用者指派給其中一個安全性群組，請遵循下列步驟：
1.  移至 Azure 入口網站，並流覽至 Azure Active Directory blade。
2.  在左側選取 [群組]。
3.  搜尋新式的工作區角色，然後選取與您要指派之角色相關聯的群組。 
4.  選取左側的 [成員]，然後選取 [+ 在命令列上新增成員]。
5.  輸入要新增之人員的電子郵件。 如果是外部使用者，您必須先邀請他們，才可指派群組。
6.  選取底部的 [選取]。

> [!NOTE]
> 目前不支援角色指派的嵌套安全性群組。 
