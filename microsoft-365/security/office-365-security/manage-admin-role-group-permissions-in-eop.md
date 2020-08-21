---
title: 管理 EOP 中的角色群組
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 系統管理員可以瞭解如何在 exchange Online Protection 中指派或移除 Exchange 系統管理中心 (EAC) 中的許可權。
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825686"
---
# <a name="manage-role-groups-in-standalone-eop"></a>在獨立版 EOP 中管理角色群組

在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，您可以使用 Exchange 系統管理中心 (EAC) 將使用者新增至角色群組。 將使用者新增至角色群組，可讓使用者執行特定系統管理員工作的許可權。 您也可以從角色群組中移除使用者。

如需角色和角色群組的詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要 (EAC) 開啟 Exchange 系統管理中心，請參閱 [exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要開啟獨立 EOP PowerShell，請參閱 [Connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 具體說來，您需要角色管理角色，其預設會指派給 OrganizationManagement (全域系統管理員) 角色群組。 如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="use-the-eac-to-manage-role-groups"></a>使用 EAC 來管理角色群組

### <a name="use-the-eac-to-view-role-groups"></a>使用 EAC 來查看角色群組

1. 在 EAC 中，移至 [ **許可權**] [ \> **管理員角色**]。 您組織中的所有角色群組都會列在這裡。

2. 選取角色群組。 [詳細資料] 窗格會顯示 **名稱**、 **描述**、 **指派的角色**，並由角色群組 **進行管理** 。 您也可以按一下 [ **編輯**編輯圖示] 來查看此資訊 ![ ](../../media/ITPro-EAC-EditIcon.png) 。

### <a name="use-the-eac-to-create-role-groups"></a>使用 EAC 來建立角色群組

當您建立新的角色群組時，您可以在建立群組或) 之後，自行設定所有設定 (。 或者，您可以複製現有的角色群組並加以修改。

1. 在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，然後執行下列其中一個步驟：

   - **手動建立新的角色群組** **：按一下 [新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。

   - **複製現有的角色群組**：選取您要複製的角色群組，然後按一下 [ **複製** ![ 複製圖示] ](../../media/ITPro-EAC-CopyIcon.png) 。

2. 在出現的 [ **新增角色群組** ] 視窗中，設定下列設定：

    - **名稱**：輸入角色群組的唯一名稱。

    - **描述**：輸入角色群組的選用描述。

    - **角色**：按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 或 [ **移除** ![ITPro-EAC-RemoveIcon.gif] ](../../media/ITPro-EAC-RemoveIcon.gif) ，以選取或修改指派給角色群組的角色。

    - **成員**：按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 或 [ **移除** ![ITPro-EAC-RemoveIcon.gif] ](../../media/ITPro-EAC-RemoveIcon.gif) ，修改角色群組成員資格。

3. 完成作業後，按一下 [ **儲存** ] 以建立角色群組。

### <a name="use-the-eac-to-modify-role-groups"></a>使用 EAC 修改角色群組

在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，選取您要修改的角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。

當您修改角色群組時，當您建立角色群組時，可以使用相同的選項。 您可以：

- 變更名稱和描述。

- 新增或移除管理角色 (建立或移除角色指派) 。

- 新增及移除成員。

**附注**：有些角色群組 (例如，「組織管理」) 會限制您可以從群組中移除的角色。

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>使用 EAC 修改角色群組中的成員清單

1. 在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，選取您要修改的角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。

2. 在開啟的角色群組屬性頁面的 [ **成員** ] 區段中，執行下列其中一個步驟：

   - 按一下 [ **新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.png) 。 在出現的頁面中，尋找 wou 想要加入的使用者，然後按一下 [ **載入 >**]。 選取 [使用者]，然後視需要按一下 [ **增加->** ] 多次。 完成後，按一下 [確定]****。

   - 選取您要移除的使用者，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。

3. 完成後，按一下 [儲存]****。

   > [!NOTE]
   > 使用者可能必須先登出再登入，才能在您於角色群組中新增或移除成員後，看到其系統管理權限的變更。

### <a name="use-the-eac-to-remove-role-groups"></a>使用 EAC 移除角色群組

您無法移除內建的角色群組，但是您可以移除您已建立的自訂角色群組。

1. 在 EAC 中，移至 [ **許可權**] [ \> **管理員角色**]。

2. 選取您要移除的角色群組，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。

3. 在出現的確認視窗中，按一下 [ **是]** 。

## <a name="use-powershell-to-manage-role-groups"></a>使用 PowerShell 管理角色群組

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>使用獨立 EOP PowerShell 來查看角色群組

若要查看角色群組，請使用下列語法：

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

此範例會傳回所有角色群組的摘要清單。

```PowerShell
Get-RoleGroup
```

此範例會傳回名為 [收件者管理員] 之角色群組的詳細資訊。

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

此範例會傳回使用者 Julia 為成員的所有角色群組。 您需要針對 Julia 使用 DistinguishedName (DN) 值，您可以透過執行下列命令來找到： `Get-User -Identity Julia | Format-List DistinguishedName` 。

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

如需詳細的語法及參數資訊，請參閱 [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)。

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>使用獨立 EOP PowerShell 建立角色群組

當您建立新的角色群組時，您可以在建立群組或) 後，以手動方式 (設定所有設定。 或者，您可以複製現有的角色群組並加以修改。

- 若要手動建立新的角色群組，請使用下列語法：

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Roles_參數會使用下列語法，指定要指派給角色群組的管理角色 `"Role1","Role1",..."RoleN"` 。 您可以使用 **Get-ManagementRole** Cmdlet 來查看可用的角色。

  - _Members_參數會使用下列語法來指定角色群組的成員： `"Member1","Member2",..."MemberN"` 。 您可以指定使用者、擁有郵件功能的通用安全性群組 (Usg) 或其他角色群組 (安全性主體) 。

  此範例會使用下列設定建立名為「限制收件者管理」的新角色群組：

  - 「郵件收件者」角色會指派給角色群組。

  - 使用者 Kim 和聖馬丁會新增為成員。

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 若要複製現有的角色群組，請執行下列步驟：

  1. 使用下列語法，將您要複製的角色群組儲存在變數中：

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 使用下列語法建立新的角色群組：

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Members_參數會使用下列語法來指定角色群組的成員： `"Member1","Member2",..."MemberN"` 。 您可以指定使用者、擁有郵件功能的通用安全性群組 (Usg) 或其他角色群組 (安全性主體) 。

     此範例會將組織管理角色群組複製到名為 "有限的組織管理" 的新角色群組。 角色群組成員為 Isabelle、Carter 及 Lukas。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

如需詳細的語法及參數資訊，請 [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)。

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>使用獨立 EOP PowerShell 修改角色群組中的成員清單

- **Add-RoleGroupMember**和**Remove-RoleGroupMember** Cmdlet 會一次新增或移除個別成員。 **Update-RoleGroupMember**資訊清單可以取代或修改現有的成員清單。

- 角色群組的成員可以是使用者、擁有郵件功能的通用安全性群組 (Usg) 或其他角色群組 (安全性主體) 。

若要修改角色群組的成員，請使用下列語法：

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 若要以您指定的值 _取代_ 現有的現有成員清單，請使用下列語法： `"Member1","Member2",..."MemberN"` 。

- 若要 _選擇性地修改_ 現有的成員清單，請使用下列語法： `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。

此範例會將「服務台」角色群組的所有目前成員，取代為指定的使用者。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

本範例會從服務台角色群組上的成員清單中新增 Daigoro Akai 並移除 Valeria Barrio。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

如需詳細的語法及參數資訊，請參閱 [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>使用獨立 EOP PowerShell 移除角色群組

您無法移除內建的角色群組，但是您可以移除您已建立的自訂角色群組。

若要移除自訂角色群組，請使用下列語法：

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

本範例移除「訓練系統管理員」角色群組。

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

如需詳細的語法及參數資訊，請參閱 [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)。

### <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功複製角色群組，請執行下列其中一個步驟：

- 在 EAC 中，移至 [ **許可權**] [系統 \> **管理員角色**]，然後確認角色群組 (列出] 或 [未列出]) 。 選取角色群組，並確認詳細資料窗格中的設定，或按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 以驗證設定。

- 在 Exchange Online PowerShell 中， \<Role Group Name\> 以角色群組的名稱取代，並執行下列命令，以確認角色群組存在 (或不存在) 並確認設定：

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
