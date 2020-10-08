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
ms.openlocfilehash: 5adf57c2397c4de3c5ea8622a2a9be7207ebf152
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379298"
---
# <a name="access-the-admin-portal"></a>存取管理員入口網站

您的 Microsoft Managed 桌面服務閘道是 Microsoft [Azure 入口網站](https://portal.azure.com)。 如需更多有關使用和自訂 Azure 入口網站體驗的詳細資訊，請參閱 [azure 入口網站檔](https://docs.microsoft.com/azure/azure-portal/)。 可用於預覽現在，您也可以在 [Microsoft 端點管理員](https://endpoint.microsoft.com/)中找到 Microsoft 受管理的桌面。 如果您不熟悉此入口網站的裝置管理功能，請參閱 [Microsoft 端點管理員的檔](https://docs.microsoft.com/mem/)。

> [!NOTE]
> 不過，您可以選擇 accesss Microsoft 受管理的電腦，在 [Microsoft 端點管理員](https://endpoint.microsoft.com/) 或 [Azure 入口網站](https://portal.azure.com)中，支援下列瀏覽器：
> - Microsoft Edge (最新版本) 
> - Microsoft Internet Explorer 11
> - Safari (最新版本，僅限 Mac) 
> - Chrome (最新版本) 
> - Firefox (最新版本) 

您的管理帳戶需要特定許可權，才能存取 Azure 入口網站或 Microsoft 端點管理員中的 Microsoft 受管理桌面系統管理功能。 您可以使用以角色為基礎的存取控制 (RBAC) ，管理組織內這些功能的系統管理員存取權。 有幾個 Azure Active Directory (Azure AD) 系統管理員角色和內建自訂角色，可為 Microsoft Managed Desktop Admin 入口網站中的不同功能提供更細微的控制。 如需 Azure Active Directory 角色的詳細資訊，請參閱 [在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 與適用于各種 Microsoft 產品和服務的 Azure AD 系統管理員角色不同，自訂角色是 Microsoft 受管理的桌面所特有，且只會保證此服務的系統管理功能存取權。 管理員可以個別或搭配使用 Azure AD 系統管理員角色，將自訂角色指派給使用者，以將 Microsoft 管理的桌面許可權新增至現有的系統管理員帳戶。

您可以指派下列每個角色，以提供不同的存取層級：

|Azure AD 角色  |Microsoft 受管理的桌面許可權  |
|---------|---------|
|全域系統管理員     | 具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中 **所有功能的讀取和寫入權限** 。         |
|全域讀取者     | 具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的 **所有功能具有唯讀許可權** 。         |
|Intune 服務系統管理員     |  具有此角色的系統管理員具有與 Microsoft Managed Desktop Admin 入口網站中的 **安全性無關的功能的讀取和寫入權限** 。       |
|服務支援系統管理員     | 具有此角色的系統管理員具有與 Microsoft Managed Desktop Admin 入口網站中的 **安全性無關的功能的讀取和寫入權限** 。         |
|安全性系統管理員 | 具有此角色的系統管理員對管理員入口網站中 Microsoft 受管理的電腦具有**安全性相關功能的**所有功能和寫入權限，具有**唯讀許可權**。 |
|安全性讀取者 |具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的 **所有功能具有唯讀許可權** 。|

> [!IMPORTANT]
> 只有全域系統管理員角色具有在 Microsoft Managed Desktop 中 *註冊* 您的組織所需的許可權。 請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶的許可權。 在 Microsoft 受管理的桌面完成註冊後，您應該永遠使用該角色，以完成其他工作所需的 *最低* 許可權。

 
|自訂角色  |Microsoft 受管理的桌面許可權  |
|---------|---------|
|Microsoft 受管理的桌面服務管理員  | 指派給使用者時，此角色可讓系統管理員 **讀取和寫入權限給** 與 Microsoft Managed Desktop admin 入口網站中的安全性無關的功能。  |
|Microsoft 受管理的桌面服務讀取器 | 指派給使用者時，此角色可讓系統管理員對與 Microsoft Managed Desktop Admin 入口網站中的安全性無關的 **功能具有唯讀許可權** 。 |
|Microsoft 受管理的桌面安全性管理員 |指派給使用者時，此角色只會讓系統管理員 **讀取和寫入權限，只會針對** Microsoft Managed Desktop admin 入口網站中的安全性相關功能。   |

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
