---
title: 讓使用者能夠存取 Office 365 安全規範中心
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
description: 使用者必須獲指派 Office 365 安全性 & 合規性中心的權限，他們可以管理其安全性或規範功能的任何之前。
ms.openlocfilehash: c64991fa4ad847381cb00e38473aefc848015ff0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076863"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a>讓使用者能夠存取 Office 365 安全規範中心

使用者必須獲指派 Office 365 安全性 & 合規性中心的權限，他們可以管理其安全性或規範功能的任何之前。 為 Office 365 全域系統管理員或 OrganizationManagement 角色群組的安全性 & 合規性中心中的成員，您可以授與這些權限的使用者。 使用者只能管理您授予權利給他們的安全性或符合性功能。 
  
如需詳細資訊的不同的權限您可以授與安全性 & 合規性中心中的使用者，請參閱[Office 365 安全性 & 合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須是 Office 365 全域系統管理員或若要完成本文中的步驟安全性 & 合規性中心，OrganizationManagement 角色群組的成員。

- 安全性 & 合規性中心的角色群組可能會有類似的角色群組的名稱在 Exchange Online，但是兩者並不相同。

- Exchange Online 和安全性 & 合規性中心之間不會共用角色群組成員資格。

- 使用管理代理者 」 (AOBO) 權限的委派的存取權限 (DAP) 合作夥伴無法存取安全性 & 合規性中心。

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用管理中心將另一個使用者存取權授與安全性 & 合規性中心

1. [登入 Office 365 並移至系統管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。

2. 在 Microsoft 365 系統管理中心中，開啟 [**系統管理中心**，然後按一下 [**安全性 & 合規性**。

3. 在安全性 & 合規性中心，前往 [**權限**。

4. 從清單中，選擇 [角色群組，您想要新增使用者並按一下 [**編輯**![編輯圖示](../media/O365-MDM-CreatePolicy-EditIcon.gif)。

5. 在角色群組的 [屬性] 頁面 [**成員**] 底下，按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)選取名稱您想要新增的使用者 （或使用者）。

6. 當您已選取的所有使用者想要新增至角色群組，請按一下 [**新增-\> ** ]，然後 **[確定]**。

7. 按一下 [儲存]，將變更儲存到角色群組。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

1. 在安全性 & 合規性中心，前往 [**權限**。

2. 從清單中，選取要檢視的成員的角色群組。

3. 在右側，在 [角色群組的詳細資訊，您可以檢視角色群組的成員。

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用 PowerShell 將另一個使用者存取權授與安全性 & 合規性中心

1. [連線至 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

2. 使用 **Add-RoleGroupMember** 命令，以將使用者新增至組織管理角色，如下列範例所示。

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **參數**：
  
   - _身分識別_是要新增成員的角色群組。

   - _成員_是要新增至角色群組的信箱、 萬用安全性群組 (USG) 或電腦。 您一次只能指定一個成員。

如需詳細的語法及參數的詳細資訊，請參閱[Add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。
  
### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已給予使用者存取安全性 & 合規性中心，使用**Get-rolegroupmember**指令程式檢視成員中 「 組織管理 」 角色群組，如下列範例所示。
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

如需詳細的語法及參數的詳細資訊，請參閱[Get-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。
