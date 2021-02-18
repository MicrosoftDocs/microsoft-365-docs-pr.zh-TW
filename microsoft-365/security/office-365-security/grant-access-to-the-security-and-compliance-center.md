---
title: 讓使用者能夠存取安全性與合規性中心
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 使用者必須先獲指派 Microsoft 365 Security & 合規性中心的許可權，才能管理任何安全性或規範功能。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289874"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>讓使用者能夠存取安全性與合規性中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在安全性 & 規範中心內，必須將許可權指派給使用者，才能管理任何安全性或規範功能。 在安全性 & 規範中心內，以全域管理員或 OrganizationManagement 角色群組成員的身分，您可以將這些許可權授與使用者。 使用者只能管理您授予權利給他們的安全性或符合性功能。

如需您可以授與安全性 & 規範中心使用者之不同許可權的詳細資訊，請參閱 [安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須是全域系統管理員或安全性 & 規範中心的 OrganizationManagement 角色群組成員，才可完成本文中的步驟。

- 安全性 & 合規性中心的角色群組可能會具有與 Exchange Online 中的角色群組類似的名稱，但它們不是相同的。

- 角色群組成員資格不會在 Exchange Online 與安全性 & 合規性中心共用。

- 委派存取許可權 () 協力廠商使用管理代表 (AOBO) 許可權無法存取安全性 & 規範中心。

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用安全性 & 合規性中心，讓另一個使用者能夠存取安全性 & 規範中心

1. 開啟安全性 & 合規性中心 <https://protection.office.com> ，然後移至 [ **許可權**]。 若要直接移至 [ **許可權** ] 索引標籤，請開啟 <https://protection.office.com/permissions> 。

2. 從角色群組的清單中，選擇角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

3. 在 [**成員**] 底下的角色群組的 [內容] 頁面中，按一下 [**新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.gif) ，然後選取您要新增的使用者 (名稱或使用者) 。

4. 當您選取要新增至角色群組的所有使用者時，請按一下 [**新增- \>** ]，然後按一下 **[確定]**。

5. 完成後，按一下 **[儲存]**。

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用安全性 & 規範中心 PowerShell 授予另一個使用者存取安全性 & 規範中心的許可權

1. [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 使用下列語法：

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

如需詳細的語法及參數問題，請參閱 [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您是否已成功授與安全性 & 規範中心的存取權，請執行下列其中一個步驟：

- 在 [安全性 & 規範中心] 中，移至 [ **許可權** ]，然後選取角色群組。 在開啟的 [詳細資料] 浮出控制項中，驗證角色群組的成員。

- 在 [安全性 & 規範中心] PowerShell 中， \<RoleGroupName\> 以角色群組的名稱取代，並執行下列命令：

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  如需詳細的語法及參數資訊，請參閱 [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。
