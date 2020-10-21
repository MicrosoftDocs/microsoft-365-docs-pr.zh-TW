---
title: 使用 PowerShell 查看已授權和未經許可的 Microsoft 365 使用者
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: 本文說明如何使用 PowerShell 來查看已授權和未經許可的 Microsoft 365 使用者帳戶。
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651381"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>使用 PowerShell 查看已授權和未經許可的 Microsoft 365 使用者

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您的 Microsoft 365 組織中的使用者帳戶可能會從您組織中提供的授權方案中，為他們指派一些、全部或沒有的可用授權。 您可以使用 Microsoft 365 的 PowerShell，在您的組織中快速尋找授權與未經授權的使用者。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
若要查看組織中所有尚未指派任何授權方案的使用者帳戶清單 (未經許可的使用者) ，請執行下列命令：
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

若要查看組織中已指派任何授權方案 (授權使用者的所有使用者帳戶清單) ，請執行下列命令：
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>若要列出您訂閱中的所有使用者，請使用 `Get-AzureAdUser -All $true` 命令。
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

若要查看組織中所有使用者帳戶及其授權狀態的清單，請在 PowerShell: 中執行下列命令：
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

若要檢視您組織中所有未經授權使用者帳戶的清單，執行下列命令：
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

若要檢視您組織中所有經授權使用者帳戶的清單，執行下列命令：
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
