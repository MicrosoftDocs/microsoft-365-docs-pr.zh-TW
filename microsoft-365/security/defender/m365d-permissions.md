---
title: 管理 Microsoft 365 security center 中 Microsoft 365 Defender 資料的存取權
description: 瞭解如何在 Microsoft 365 Defender 中管理資料的許可權
keywords: access、許可權、Microsoft 365 Defender、M365、security、MCAS、雲端 App 安全性、Microsoft Defender for 端點、範圍、範圍、RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 738315c446fd57d4cd027de92eb77b0029f84323
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177522"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>使用 Azure Active Directory 通用角色管理 Microsoft 365 Defender 存取權

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

有兩種方式可管理 Microsoft 365 Defender 的存取
- **全域 Azure Active Directory (AD) 角色**
- **自訂角色存取**

指派下列 **全域 Azure Active Directory 的帳戶 (AD) 角色** 可以存取 Microsoft 365 Defender 功能和資料：
- 全域管理員
- 安全性系統管理員
- 安全性操作員
- 全域讀取者
- 安全性讀取者

若要檢閱具有這些角色的帳戶，請[在 Microsoft 365 安全性中心檢視權限](https://security.microsoft.com/permissions)。

**自訂角色** 存取是 Microsoft 365 Defender 中的新功能，可讓您管理 Microsoft Defender 365 中特定資料、工作及功能的存取權。 自訂角色比全域 Azure AD 角色提供更多的控制權，只為使用者提供必要的存取權最低的角色。  除了全域 Azure AD 角色之外，還可以建立自訂角色。 [深入瞭解自訂角色](custom-roles.md)。

> [!NOTE]
> 本文僅適用于管理全域 Azure Active Directory 角色。 如需使用自訂角色型存取控制的詳細資訊，請參閱 [自訂角色的自訂角色的存取控制](custom-roles.md)

## <a name="access-to-functionality"></a>存取功能
特定功能的存取權由您的 [Azure AD 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)決定。 如果您得存取需要為您或使用者群組指派新角色的特定功能，請與全域管理員連絡。

### <a name="approve-pending-automated-tasks"></a>核准擱置的自動化工作
[自動化調查和補救](m365d-autoir-actions.md)可針對電子郵件、轉寄規則、檔案、持續性機制和調查期間找到的其他成品採取動作。 若要核准或拒絕需要明確核准的擱置中動作，您必須在 Microsoft 365 中指派特定角色。 若要深入瞭解，請參閱[重要訊息中心權限](m365d-action-center.md#required-permissions-for-action-center-tasks)。

## <a name="access-to-data"></a>資料存取權
您可以使用指派給 Microsoft Defender 中使用者群組的範圍來控制存取 Microsoft 365 Defender 資料，以用於以端點角色為基礎的存取控制 (RBAC) 。 如果您的存取未限定在 Defender for Endpoint 中的特定裝置集，您就可以在 Microsoft 365 Defender 中取得資料的完整存取權。 不過，一旦您的帳戶限定範圍設定完畢，就只會看到範圍內裝置的相關資料。

例如，如果您只隸屬于一個具有 Microsoft Defender for Endpoint role 的使用者群組，且該使用者群組已獲得對銷售裝置的存取權，您只會看到 Microsoft 365 Defender 中的銷售裝置相關資料。 [深入瞭解 Microsoft Defender for Endpoint 中的 RBAC 設定](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security 存取控制
在預覽期間，Microsoft 365 Defender 不會根據雲端 App 安全性設定來強制進行存取控制。 這些設定不會影響 Microsoft 365 Defender 資料的存取。

## <a name="related-topics"></a>相關主題
- [Microsoft 365 Defender 的角色型存取控制中的自訂角色](custom-roles.md)
- [Azure AD 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender for Endpoint RBAC](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security 角色](/cloud-app-security/manage-admins)
