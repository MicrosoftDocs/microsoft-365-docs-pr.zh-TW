---
title: 將 Microsoft 365 授權指派給使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 說明如何將 Microsoft 365 授權指派給使用者帳戶（個別或根據群組成員資格）。
ms.openlocfilehash: 6bba3cd767787f450840c5cae6c30f2be21bed1b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905437"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>將 Microsoft 365 授權指派給使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

針對僅限雲端的身分識別模型，您可以根據建立的方式，將 Microsoft 365 授權指派給使用者帳戶。

針對混合式識別模型，當第一次同步處理 Active Directory 網域服務 (AD DS) 使用者帳戶時，系統不會自動指派位置或 Microsoft 365 授權。 **您必須在指派授權之前或之前，設定每個使用者帳戶的使用者位置。**

在這兩種情況下，您必須指派授權給使用者帳戶，讓您的使用者能夠存取 Microsoft 365 服務，例如電子郵件和 Microsoft 團隊。

您可以透過群組成員資格個別或自動將授權指派給使用者帳戶。

若要將 Microsoft 365 授權指派給個別使用者帳戶，您可以使用：

- [Microsoft 365 系統管理中心](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD 系統管理中心

## <a name="group-based-licensing"></a>群組型授權

您可以在 Azure AD 中設定安全性群組，以自動將一組訂閱的授權指派給群組的所有成員。 這稱為 *群組型授權*。 如果在群組中新增或移除使用者帳戶，則將自動指派或從使用者帳戶中取消指派群組訂閱的授權。

請確定您有足夠的授權可供所有群組成員使用。 如果您用完了授權，除非有授權可供使用，否則將不會對新使用者指派授權。

>[!Note]
>您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定以群組為基礎的授權。
>

如需更多 informaion，請參閱 [在 AZURE AD 中以群組為基礎的授權](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

## <a name="next-steps"></a>後續步驟

使用已獲指派授權的適當使用者帳戶集，您現在可以：

- [實施安全性](../security/office-365-security/security-roadmap.md)
- [部署用戶端軟體，例如 Microsoft 365 應用程式](/DeployOffice/deployment-guide-microsoft-365-apps)
- [設定裝置管理](device-management-roadmap-microsoft-365.md)
- [設定服務和應用程式](configure-services-and-applications.md)