---
title: 讓使用者能夠存取安全性與合規性中心
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須先獲指派 Microsoft 365 Security & 合規性中心的許可權，才能管理任何安全性或規範功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 19358e3cca0c4d47338fe5fc72b671e36477ce7e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351948"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>讓使用者能夠存取安全性與合規性中心

在安全性 & 規範中心內，必須將許可權指派給使用者，才能管理任何安全性或規範功能。 在安全性 & 規範中心內，以全域管理員或 OrganizationManagement 角色群組成員的身分，您可以將這些許可權授與使用者。 使用者只能管理您授予權利給他們的安全性或符合性功能。

如需您可以授與安全性 & 規範中心使用者之不同許可權的詳細資訊，請參閱[安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須是全域系統管理員或安全性 & 規範中心的 OrganizationManagement 角色群組成員，才可完成本文中的步驟。

- 安全性 & 合規性中心的角色群組可能會具有與 Exchange Online 中的角色群組類似的名稱，但它們不是相同的。

- 角色群組成員資格不會在 Exchange Online 與安全性 & 合規性中心共用。

- 委派存取許可權（結合）具有「管理者代表」（AOBO）許可權的合作夥伴無法存取安全性 & 規範中心。

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用系統管理中心，讓另一位使用者能夠存取安全性 & 規範中心

1. 登[入並移](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)至系統管理中心。

2. 在 Microsoft 365 系統管理中心中，開啟 [系統**管理中心**]，然後按一下 [**安全性 & 合規性**]。

3. 在 [安全性 & 規範中心] 中，移至 [**許可權**]。

4. 從清單中，選擇您要新增使用者的角色群組，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

5. 在 [**成員**] 底下的角色群組的 [內容] 頁面中，按一下 [**新增** ![ 新增圖示] ](../../media/ITPro-EAC-AddIcon.gif) ，然後選取您要新增的使用者名稱（或使用者）。

6. 當您選取要新增至角色群組的所有使用者時，請按一下 [**新增- \> ** ]，然後按一下 **[確定]**。

7. 按一下 [儲存]，將變更儲存到角色群組。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

1. 在 [安全性 & 規範中心] 中，移至 [**許可權**]。

2. 從清單中，選取要查看成員的角色群組。

3. 在右側的角色群組詳細資料中，您可以查看角色群組的成員。

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用 PowerShell 授予另一個使用者存取安全性 & 規範中心的許可權

1. [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

2. 使用 **Add-RoleGroupMember** 命令，以將使用者新增至組織管理角色，如下列範例所示。

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **參數**：

   - _Identity_是要新增成員的角色群組。

   - _Member_是信箱、通用安全性群組（USG），或要新增至角色群組的電腦。 您一次只能指定一個成員。

如需語法及參數的詳細資訊，請參閱[Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您是否已授予使用者對安全性 & 合規性中心的存取權，請使用**Get-RoleGroupMember** Cmdlet 來查看「組織管理」角色群組中的成員，如下列範例所示。

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

如需語法及參數的詳細資訊，請參閱[Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。
