---
title: 僅限 Microsoft 365 雲端身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
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
description: 說明當您的 Microsoft 365 訂閱使用僅限雲端身分識別時，如何建立使用者和群組。
ms.openlocfilehash: 6ec727ea3648f1daa3af42763e5f497715b987a2
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547755"
---
# <a name="microsoft-365-cloud-only-identity"></a>僅限 Microsoft 365 雲端身分識別

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

使用僅限雲端身分識別，所有的使用者、群組和連絡人都儲存在 Microsoft 365 訂閱的 Azure Active Directory (Azure AD) 租使用者中。 以下是僅限雲端身分識別的基本元件。
 
![僅限雲端身分識別的基本元件](../media/about-microsoft-365-identity/cloud-only-identity.png)

組織中的使用者和他們的使用者帳戶可以多種方式分類。 例如，有些員工是員工，且具有永久狀態。 有些是具有暫存檔狀態的廠商、合同工或合作夥伴。 有些外部使用者沒有使用者帳戶，但仍然必須授與特定服務和資源的存取權，以支援互動和協同作業。 例如：

- 租用戶帳戶代表您為雲端服務授權之組織內的使用者

- 企業對企業 (B2B) 帳戶代表不屬於您邀請參與共同作業之組織的使用者

在您的組織中製作使用者類型的股份。 分組的群組為何？ 例如，您可以將高層次的功能或目的群組的使用者群組為您的組織。

此外，某些雲端服務可以與組織外的使用者共用，而不需使用任何使用者帳戶。您也必須識別使用者的這些群組。

您可以針對多種目的使用 Azure AD 中的群組，以簡化雲端環境的管理。 例如，使用 Azure AD 群組時，您可以：

- 使用以群組為基礎的授權，可在新增為成員時，自動將 Microsoft 365 的授權指派給您的使用者帳戶。
- 根據使用者帳戶屬性（例如部門名稱），以動態方式將使用者帳戶新增至特定群組。
- 自動將軟體的使用者布建為服務 (SaaS) 的應用程式，並使用多重要素驗證 (MFA) 和其他條件式存取原則，來保護這些應用程式的存取權。
- 為 SharePoint Online 小組網站提供許可權和存取層級。

您可以使用下列方式建立新的 ***使用者*** ：

- [Microsoft 365 系統管理中心](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [適用於 Microsoft 365 的 PowerShell](create-user-accounts-with-microsoft-365-powershell.md)

您可以使用下列方式建立新的 ***群組*** ：

- [Microsoft 365 系統管理中心](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [適用於 Microsoft 365 的 PowerShell](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a>僅限雲端身分識別的下一個步驟

[將授權指派給使用者帳戶](assign-licenses-to-user-accounts.md)
