---
title: 使用 PowerShell 封鎖 Microsoft 365 使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: 如何使用 PowerShell 來封鎖和取消封鎖 Microsoft 365 帳戶的存取。
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754677"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell 封鎖 Microsoft 365 使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

當您封鎖存取 Microsoft 365 帳戶時，可防止任何人使用該帳戶登入，並存取您的 Microsoft 365 組織中的服務和資料。 您可以使用 PowerShell 來封鎖個別或多個使用者帳戶的存取權。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
### <a name="block-access-to-individual-user-accounts"></a>封鎖個別使用者帳戶的存取

使用下列語法來封鎖個別使用者帳戶：
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> **Set-AzureAD**指令程式中的 *-ObjectID*參數會接受帳戶登入名稱，也稱為使用者主要名稱，或者是帳戶的物件識別碼。
  
本範例會封鎖存取 *fabricec@litwareinc.com*的使用者帳戶。
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

若要將使用者帳戶解除封鎖，請執行下列命令：
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

若要根據使用者的顯示名稱來顯示使用者帳戶 UPN，請使用下列命令：
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

此範例會顯示使用者  *Caleb sills 帳戶*的使用者帳戶 UPN。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

若要根據使用者的顯示名稱封鎖帳戶，請使用下列命令：
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

若要檢查使用者帳戶的封鎖狀態，請使用下列命令：
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>封鎖多個使用者帳戶

若要封鎖多個使用者帳戶的存取權，請建立一個文字檔，其中每一行上都包含一個帳戶登入名稱，如下所示：
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

在下列命令中，範例文字檔會 *C:\My Documents\Accounts.txt*中。 請將此檔案名取代為您的文字檔的路徑和檔案名。
  
若要封鎖對文字檔中所列帳戶的存取，請執行下列命令：
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

若要解除封鎖文字檔中所列的帳戶，請執行下列命令：
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
    
### <a name="block-individual-user-accounts"></a>封鎖個別的使用者帳戶

使用下列語法來封鎖個別使用者帳戶的存取權：
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell 核心不支援 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，以及其名稱中具有 *Msol* 的 Cmdlet。 您必須從 [Windows PowerShell 執行這些 Cmdlet。

本範例會封鎖存取使用者帳戶 *fabricec \@ litwareinc.com*。
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

若要將使用者帳戶解除封鎖，請執行下列命令：
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

若要檢查使用者帳戶的封鎖狀態，請執行下列命令：
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>封鎖多個使用者帳戶的存取權

首先，建立一個文字檔，其中每一行上都包含一個帳戶，如下所示：
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

在下列命令中，範例文字檔會 *C:\My Documents\Accounts.txt*中。 請將此檔案名取代為您的文字檔的路徑和檔案名。
    
若要封鎖對文字檔中所列帳戶的存取，請執行下列命令：
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
若要解除封鎖對文字檔中所列帳戶的存取，請執行下列命令：
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
