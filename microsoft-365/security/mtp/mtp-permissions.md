---
title: 管理 Microsoft 365 安全性中心的 Microsoft 威脅防護資料的存取權
description: 了解如何在 Microsoft 威脅防護中管理資料的權限
keywords: 存取權, 權限, MTP, Microsoft 威脅防護, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 進階威脅防護, 範圍, 約制, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 0450bf5e37775ed721b307fed1034556ab73a08a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600050"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>管理 Microsoft 威脅防護的存取權

**適用於：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

指派下列 Azure Active Directory (AD) 角色的帳戶可存取 Microsoft 威脅防護功能和資料：
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
存取 Microsoft 威脅防護資料可透過使用 Microsoft Defender ATP 角色型存取控制 (RBAC) 中指派給使用者群組的範圍加以控制。 如果您的存取權並未限定於 Microsoft Defender ATP 中的特定一組裝置，便能在 Microsoft 威脅防護完整存取資料。 不過，一旦您的帳戶限定範圍設定完畢，就只會看到範圍內裝置的相關資料。

例如，如果您只屬於具有一個 Microsoft Defender ATP 角色的單一使用者群組，且該使用者群組僅獲授權存取銷售裝置，您便只會在 Microsoft 威脅防護中看到銷售裝置的相關資料。 [深入了解 Microsoft Defender ATP 中的 RBAC 設定](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security 存取控制
在預覽期間，Microsoft 威脅防護不會根據 Cloud App Security 設定強制執行存取控制。 這些設定不會影響存取 Microsoft 威脅防護資料。

## <a name="related-topics"></a>相關主題

- [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender ATP RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security 角色](https://docs.microsoft.com/cloud-app-security/manage-admins)