---
title: 在 Microsoft 365 資訊安全中心管理 Microsoft 365 Defender 資料的存取權
description: 瞭解如何在 Microsoft 365 Defender 中管理資料的許可權
keywords: 存取權, 權限, MTP, Microsoft 威脅防護, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 進階威脅防護, 範圍, 約制, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930135"
---
# <a name="manage-access-to-microsoft-365-defender"></a>管理 Microsoft 365 Defender 的存取權

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

指派有下列 Azure Active Directory 帳戶 (AD) 角色可以存取 Microsoft 365 Defender 功能和資料：
- 全域管理員
- 安全性系統管理員
- 安全性操作員
- 全域讀取者
- 安全性讀取者

若要檢閱具有這些角色的帳戶，請[在 Microsoft 365 安全性中心檢視權限](https://security.microsoft.com/permissions)。

## <a name="access-to-functionality"></a>存取功能
特定功能的存取權由您的 [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)決定。 如果您得存取需要為您或使用者群組指派新角色的特定功能，請與全域管理員連絡。

### <a name="approve-pending-automated-tasks"></a>核准擱置的自動化工作
[自動化調查和補救](mtp-autoir-actions.md)可針對電子郵件、轉寄規則、檔案、持續性機制和調查期間找到的其他成品採取動作。 若要核准或拒絕需要明確核准的擱置中動作，您必須在 Microsoft 365 中指派特定角色。 若要深入瞭解，請參閱[重要訊息中心權限](mtp-action-center.md#required-permissions-for-action-center-tasks)。

## <a name="access-to-data"></a>資料存取權
Microsoft 365 Defender 資料的存取權可以使用在 Microsoft Defender 中指派給使用者群組的範圍控制端點角色型存取控制 (RBAC) 。 如果您的存取範圍尚未設定為端點的 Defender 中一組特定裝置，您將擁有 Microsoft 365 Defender 資料的完整存取權。 不過，一旦您的帳戶限定範圍設定完畢，就只會看到範圍內裝置的相關資料。

例如，如果您只屬於具有 Microsoft Defender 端點角色的一個使用者群組，而且該使用者群組僅取得銷售裝置的存取權限，您只會在 Microsoft 365 Defender 中看見銷售裝置的資料。 [深入瞭解 Microsoft Defender for Endpoint 中的 RBAC 設定](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security 存取控制
在預覽期間，Microsoft 365 Defender 不會根據雲端 App 安全性設定強制執行存取控制。 存取 Microsoft 365 Defender 資料不受這些設定影響。

## <a name="related-topics"></a>相關主題

- [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [端點 RBAC 的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security 角色](https://docs.microsoft.com/cloud-app-security/manage-admins)
