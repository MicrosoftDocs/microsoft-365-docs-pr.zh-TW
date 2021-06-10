---
title: 使用 PowerShell 管理安全性群組
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 瞭解如何使用 PowerShell 來管理安全性群組。
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909499"
---
# <a name="manage-security-groups-with-powershell"></a>使用 PowerShell 管理安全性群組

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以使用 PowerShell 做為 Microsoft 365 Microsoft 365 系統管理中心的替代，以管理安全性群組。 

本文說明如何列出、建立、變更設定和移除安全性群組。 

當本文中的命令區塊要求您指定變數值時，請使用下列步驟。

1. 將命令區塊複製到 [剪貼簿]，然後將它貼到記事本或 PowerShell 整合式腳本環境 (ISE) 。
2. 填入變數值，並移除 "<" 和 ">" 字元。
3. 在 PowerShell] 視窗或 PowerShell ISE 中執行命令。

請參閱 [維護安全性群組成員資格](maintain-group-membership-with-microsoft-365-powershell.md) 以使用 PowerShell 管理群組成員資格。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="list-your-groups"></a>列出您的群組

使用此命令來列出所有群組。

```powershell
Get-AzureADGroup
```
使用這些命令，依其顯示名稱顯示特定群組的設定。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>建立新的群組

使用此命令來建立新的安全性群組。

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>變更群組上的設定

使用下列命令，顯示群組的設定。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

然後，使用「 [AzureADGroup」一](/powershell/module/azuread/set-azureadgroup) 文來決定如何變更設定。

### <a name="remove-a-security-group"></a>移除安全性群組

使用這些命令移除安全性群組。

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>管理安全性群組的擁有者

使用這些命令來顯示安全性群組目前的擁有者。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
使用這些命令，將使用者帳戶的 **使用者主要名稱 (UPN)** 新增至目前安全性群組的擁有者。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
使用這些命令，透過其 **顯示名稱** 將使用者帳戶新增至目前安全性群組的擁有者。

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
使用這些命令，將使用者帳戶由其 **UPN 的 UPN** 移除，移至目前安全性群組的擁有者。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

使用這些命令，將使用者帳戶的 **顯示名稱** 移除至安全性群組目前的擁有者。

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="list-your-groups"></a>列出您的群組

使用此命令來列出所有群組。

```powershell
Get-MsolGroup
```
使用這些命令，依其顯示名稱顯示特定群組的設定。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>建立新的群組

使用此命令來建立新的安全性群組。

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>變更群組上的設定

使用下列命令，顯示群組的設定。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

然後，使用「 [MsolGroup」一](/powershell/module/msonline/set-msolgroup) 文來決定如何變更設定。

### <a name="remove-a-security-group"></a>移除安全性群組

使用這些命令移除安全性群組。

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)