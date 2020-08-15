---
title: 將 Microsoft 365 授權指派給使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
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
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688301"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>將 Microsoft 365 授權指派給使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

針對僅限雲端的身分識別模型，您可以根據建立的方式，將 Microsoft 365 授權指派給使用者帳戶。

針對混合式身分識別模型，當第一次同步處理 Active Directory 網域服務 (AD DS) 使用者帳戶時，系統不會自動將其指派給 Microsoft 365 授權。 您必須先設定使用者位置的每個使用者帳戶。

在這兩種情況下，您必須指派授權給使用者帳戶，讓您的使用者能夠存取 Microsoft 365 服務，例如電子郵件和 Microsoft 團隊。

您可以透過群組成員資格個別或自動將授權指派給使用者帳戶。

若要將 Microsoft 365 授權指派給個別使用者帳戶，您可以使用：

- [Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [適用於 Microsoft 365 的 PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

若要進行自動授權指派，請參閱 [在 AZURE AD 中以群組為基礎的授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

## <a name="next-steps"></a>後續步驟

透過已獲指派授權的完整使用者帳戶，您現在可以：

- [實施安全性](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [部署用戶端軟體，例如 Microsoft 365 應用程式](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [在 Microsoft 365 中設定行動裝置管理](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [設定服務和應用程式](configure-services-and-applications.md)
