---
title: 存取系統管理入口網站
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
description: 如何尋找及使用管理員入口網站，包括控制對它的存取。
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 2facd506497cbdab42f2d8b051fbd50f82432927
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770598"
---
# <a name="access-the-admin-portal"></a>存取管理員入口網站

您的 Microsoft 受管理的電腦服務閘道是[Microsoft 端點管理員](https://endpoint.microsoft.com/)。 如果您不熟悉此入口網站的裝置管理功能，請參閱[Microsoft 端點管理員檔](/mem/)。

> [!NOTE]
> 在[Microsoft 端點管理員](https://endpoint.microsoft.com/)支援下列瀏覽器：
> - Microsoft Edge (最新版本) 
> - Safari (最新版本，僅限 Mac) 
> - Chrome (最新版本) 
> - Firefox (最新版本) 

您的系統管理帳戶需要特定許可權，才能存取 Microsoft 端點管理員中的 Microsoft 受管理的電腦管理功能。 您可以使用以角色為基礎的存取控制，管理組織內這些功能的系統管理員存取權。 有幾個 Azure Active Directory (Azure AD) 系統管理員角色和內建 Microsoft 受管理的電腦角色，可提供更細微的控制，可對 Microsoft 受管理的電腦管理入口網站內的不同功能提供更細微的控制。 如需 Azure Active Directory 角色的詳細資訊，請參閱[Azure Active Directory 中的系統管理員角色許可權](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 與適用于各種 Microsoft 產品和服務的 Azure AD 系統管理員角色不同，內建角色是 Microsoft 受管理的電腦特有的角色，且只會保證可存取此項服務的系統管理功能。 系統管理員可以個別指派內建角色給使用者，或搭配 Azure AD 系統管理員角色一起指派，以將 Microsoft 受管理的電腦許可權新增至現有的系統管理員帳戶。

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory 具有 Microsoft 受管理的電腦存取權的角色

|Azure AD 角色  |Microsoft 受管理的電腦許可權  |
|---------|---------|
|全域系統管理員     | 具有此角色的系統管理員具有 Microsoft 受管理的電腦系統管理員入口網站中 **所有功能的讀取和寫入權限**。         |
|全域讀取者     | 具有此角色的系統管理員對 Microsoft 受管理的電腦系統管理員入口網站中的 **所有功能具有唯讀許可權**。         |
|Intune 服務系統管理員     |  具有此角色的系統管理員會具有與 Microsoft 受管理的電腦系統管理員入口網站中的 **安全性無關的功能的讀取和寫入權限**。       |
|服務支援系統管理員     | 具有此角色的系統管理員對與安全性和寫入權限 **不相關的功能** 具有「唯讀」許可權，以在 Microsoft 受管理的電腦系統管理入口網站中 **管理支援要求**。         |
|安全性系統管理員 | 具有此角色的系統管理員對管理員入口網站中 Microsoft 受管理的電腦的 **安全性相關功能**，具有「**唯讀」許可權**。 |
|安全性讀取者 |具有此角色的系統管理員對 Microsoft 受管理的電腦系統管理員入口網站中的 **所有功能具有唯讀許可權**。|

如果您需要協助指派 Azure Active Directory 角色，請參閱[Azure Active Directory 中的系統管理員角色許可權](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

> [!IMPORTANT]
> 只有全域系統管理員角色具備 Microsoft 受管理的電腦中的 *註冊* 組織所需的許可權。 請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶許可權。 在完成 Microsoft 受管理的電腦的註冊後，您應該一直使用具有完成其他工作所需的 *最低* 許可權的角色。

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Microsoft 受管理的電腦所提供的內建角色


|內建角色  |Microsoft 受管理的電腦許可權  |
|---------|---------|
|Microsoft 受管理的電腦服務管理員  | 指派給使用者時，此角色可讓系統管理員 **讀取和寫入權限給** 與 Microsoft 受管理的電腦系統管理入口網站中的安全性無關的功能。  |
|Microsoft 受管理的電腦服務讀取器 | 指派給使用者時，此角色會授與 Microsoft 受管理的電腦系統管理入口網站中與安全性無關的功能的管理員 **唯讀許可權**。 |
|Microsoft 受管理的電腦安全性管理員 |指派給使用者時，此角色只會讓系統管理員 **讀取和寫入權限，只對** Microsoft 受管理的電腦系統管理入口網站中的安全性相關功能。   |

> [!NOTE]
> 安全性功能包括安全性相關的通訊、安全性連絡人的管理、安全性相關支援要求的管理，以及與安全性相關的報表存取。 

### <a name="assigning-built-in-roles-to-user"></a>將內建角色指派給使用者

為了便於管理內建角色，每個自訂角色的安全性群組都有名稱為「新式工作區角色- _角色名稱_」 (例如，「新式工作區角色–安全性管理員」 ) 。 若要將使用者指派給其中一個安全性群組，請遵循下列步驟：
1.  移 Microsoft 端點管理員入口網站。
2.  選取左側的 [ **群組** ]。
3.  搜尋 **新式的工作區角色**，然後選取與您要指派之角色相關聯的群組。 
4.  選取左側的 [ **成員** ]，然後選取 [+ 在命令列 **新增成員** ]。
5.  輸入要新增之人員的電子郵件。 若為來賓，您必須先將其邀請，才能指派群組。
6.  選取底部的 [ **選取** ]。

> [!NOTE]
> 目前不支援角色指派的嵌套安全性群組。 

### <a name="assigning-built-in-roles-to-groups"></a>將內建角色指派給群組

如果您需要將一個或多個內建角色指派給現有的群組，請遵循下列步驟：
1. 移至 [portal.azure.com](https://portal.azure.com/)。
2. 搜尋並開啟 **Enterprise 的應用程式**。
3. 將 **應用程式類型** 篩選變更為 _Microsoft 應用程式_ ，然後 **選取 [** 套用]。
4. 搜尋並選取 _新式的 Workplace 客戶 APIs_。
5. 從左側窗格中選取 [ **使用者和群組** ]，然後選取 [ **+ 新增使用者/群組**]。
6. 從 **使用者和群組** 搜尋您想要的群組。
7. 在 [ **選取角色**] 中搜尋適用的角色，然後選取該角色。
8. 選取 [ **指派**]。
