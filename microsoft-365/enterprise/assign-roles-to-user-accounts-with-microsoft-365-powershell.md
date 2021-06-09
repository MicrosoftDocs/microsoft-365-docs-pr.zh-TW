---
title: 使用 PowerShell 將角色指派給 Microsoft 365 使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: 在本文中，瞭解如何使用 PowerShell Microsoft 365 將系統管理員角色指派給使用者帳戶的快捷方式。
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905377"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell 指派系統管理員角色以 Microsoft 365 使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以使用 Microsoft 365 的 PowerShell 輕易指派角色給使用者帳戶。

>[!Note]
>瞭解如何使用 Microsoft 365 系統管理中心，[將系統管理員角色指派](../admin/add-users/assign-admin-roles.md)給使用者帳戶。
>
>如需其他資源的清單，請參閱 [管理使用者和群組](../admin/add-users/index.yml)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，使用全域管理員帳戶來連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
接下來，識別您想要新增至角色的使用者帳戶登入名稱 (例如： fredsm \@ contoso.com) 。 這也稱為使用者主要名稱 (UPN) 。

接下來，決定角色的名稱。 請參閱[Azure Active Directory 中的系統管理員角色許可權](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。

>[!Note]
>請注意本文中的記事。  (Azure AD) PowerShell 的某些角色名稱是不同的 Azure Active Directory。 例如，在 Microsoft 365 *系統管理中心的 SharePoint 系統管理員* 角色是在 Azure AD PowerShell 中 *SharePoint 服務管理員*。
>

接下來，填入登入和角色名稱，並執行下列命令：
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

以下是將「SharePoint 服務管理員」角色指派給 *belindan \@ contoso.com* 帳戶的完整命令集範例：
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

若要顯示特定系統管理員角色的使用者名稱清單，請使用下列命令。

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，使用全域管理員帳戶來連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
### <a name="for-a-single-role-change"></a>針對單一角色變更

指定使用者帳戶最常見的方式是使用其顯示名稱或其電子郵件名稱，也稱為其登入名稱或使用者主要名稱 (UPN) 。

#### <a name="display-names-of-user-accounts"></a>使用者帳戶的顯示名稱

如果您是用來處理使用者帳戶的顯示名稱，請決定下列資訊：
  
- 您要設定的使用者帳戶
    
    若要指定使用者帳戶，您必須決定其顯示名稱。 若要取得完整的帳戶清單，請使用此命令：
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    這個命令會列出您的使用者帳戶顯示名稱，依顯示名稱排序，一次一屏。 您可以使用 **Where** Cmdlet，將清單篩選為較小的集合。 請參閱下列的範例。

   >[!Note]
   >PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。 從 PowerShell 執行這些 Cmdlet。
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    這個命令只會列出顯示名稱開頭為 "John" 的使用者帳戶。
    
- 您要指派的角色
    
    若要顯示可指派給使用者帳戶的可用系統管理員角色清單，請使用下列命令：
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

決定帳戶的顯示名稱和角色名稱之後，請使用下列命令將角色指派給帳戶：
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

將命令貼到記事本。 針對 *$dispName* 和 *$roleName* 變數，以其值取代描述文字。 移除 \< and > 字元，但保留引號。 將修改過的列貼到 Microsoft Azure Active Directory 模組中，以執行 Windows PowerShell 視窗。 或者，您也可以使用 Windows PowerShell 的整合式腳本環境 (ISE) 。
  
以下是已完成命令集的範例：
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>使用者帳戶的登入名稱

如果您是用來使用登入名稱或使用者帳戶的 Upn，請決定下列資訊：
  
- 使用者帳戶的 UPN
    
    如果您不知道 UPN，請使用此命令：
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    這個命令會列出您的使用者帳戶的 UPN，依 UPN 排序，一次一個畫面。 您可以使用 **Where** Cmdlet 篩選清單。 以下為範例：
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    這個命令只會列出顯示名稱開頭為 "John" 的使用者帳戶。
    
- 您要指派的角色
    
    若要顯示可指派給使用者帳戶的可用角色清單，請使用下列命令：
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

當您擁有帳戶的 UPN 和角色名稱之後，請使用下列命令將角色指派給帳戶：
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

複製命令，並將其貼到記事本。 用於 **$upnName** 和 **$roleName** 變數。 以其值取代描述文字。 移除 \< and > 字元，但保留引號。 將修改過的列貼到 Microsoft Azure Active Directory 模組中，以執行 Windows PowerShell 視窗。 或者，您也可以使用 Windows PowerShell ISE。
  
以下是已完成命令集的範例：
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>多重角色變更

若有多個角色變更，請決定下列資訊：
  
- 您想要設定的使用者帳戶。 您可以使用上一節中的方法來收集顯示名稱或 Upn 的集合。
    
- 您想要指派給每個使用者帳戶的角色。 若要顯示可指派給使用者帳戶的可用角色清單，請使用下列命令：
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

接下來，建立一個逗號分隔值 (CSV) 文字檔，該文字檔具有顯示名稱或 UPN 及角色名稱欄位。 您可以在 Microsoft Excel 中輕鬆這麼做。

以下是顯示名稱的範例：
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

接下來，填入 CSV 檔案的位置，並在 PowerShell 命令提示字元中執行產生的命令。
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

以下是 Upn 的範例：
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

接下來，填入 CSV 檔案的位置，並在 PowerShell 命令提示字元中執行產生的命令。
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>另請參閱

- [以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
- [開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)