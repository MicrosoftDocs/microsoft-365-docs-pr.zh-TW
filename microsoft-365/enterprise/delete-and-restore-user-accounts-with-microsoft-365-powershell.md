---
title: 使用 PowerShell 刪除 Microsoft 365 使用者帳戶
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: 瞭解如何在 PowerShell 中使用不同的模組，以刪除 Microsoft 365 使用者帳戶。
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919137"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell 刪除 Microsoft 365 使用者帳戶

您可以針對 Microsoft 365 使用 PowerShell，以刪除及還原使用者帳戶。

>[!Note]
>瞭解如何使用 Microsoft 365 系統管理中心[還原使用者帳戶](../admin/add-users/restore-user.md)。
>
>如需其他資源的清單，請參閱 [管理使用者和群組](../admin/add-users/index.yml)。
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

連接後，請使用下列語法來移除個別使用者帳戶：
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

此範例會移除使用者帳戶 *fabricec \@ litwareinc.com*。
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> **AzureADUser** Cmdlet 中的 *-ObjectID* 參數會接受帳戶的登入名稱，也稱為使用者主要名稱或帳戶的物件識別碼。
  
若要根據使用者的名稱顯示帳戶名稱，請使用下列命令︰
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

本範例會顯示使用者 *Caleb sills 帳戶* 的帳戶名稱。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

若要根據使用者的顯示名稱移除帳戶，請使用下列命令︰
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

當您透過 Windows PowerShell 的 Microsoft Azure Active Directory 模組刪除使用者帳戶時，不會永久刪除該帳戶。 您可以在 30 天內還原已刪除的使用者帳戶。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

若要刪除使用者帳戶，請使用下列語法：
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。 從 PowerShell 執行這些 Cmdlet。
>

本範例會刪除 *BelindaN@litwareinc.com* 的使用者帳戶。
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

若要在 30 天的寬限期內還原已刪除的使用者帳戶，請使用下列語法：
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

本範例會還原刪除的帳戶 *BelindaN \@ litwareinc.com*。
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> 若要查看可以還原的已刪除使用者清單，請執行下列命令：
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> 如果使用者帳戶的原始使用者主要名稱被另一個帳戶使用，當您還原使用者帳戶時，請使用 _NewUserPrincipalName_ 參數 (而不是 _UserPrincipalName_) 來指定不同的使用者主要名稱。


## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)