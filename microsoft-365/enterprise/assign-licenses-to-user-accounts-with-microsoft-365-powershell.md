---
title: 使用 PowerShell 將 Microsoft 365 授權指派給使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: 在本文中，您將瞭解如何使用 PowerShell 將 Microsoft 365 授權指派給未授權的使用者。
ms.openlocfilehash: 7bd217dfeed762a11161c3f512fb55a8e6c4968e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688299"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>使用 PowerShell 將 Microsoft 365 授權指派給使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

使用者必須先將授權方案的授權指派給他們的帳戶，才可使用任何 Microsoft 365 服務。 您可以使用 PowerShell 快速將授權指派給未授權的帳戶。 

>[!Note]
>必須為使用者帳戶指派位置。 您可以從 Microsoft 365 系統管理中心的使用者帳戶屬性或從 PowerShell 執行此動作。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  

接下來，使用此命令列出租使用者的授權計畫。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下來，取得您想要新增授權的帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。

接下來，確定使用者帳戶已指派使用位置。

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

若未指派任何使用位置，您可以使用下列命令指派其中一個：

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

最後，指定使用者登入名稱和授權方案名稱，並執行這些命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

執行 `Get-MsolAccountSku` 命令，以查看組織中每個計畫可用的授權方案和可用的授權數目。 每個計畫中可用的授權數目**ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**。 如需授權方案、授權及服務的詳細資訊，請參閱 [使用 PowerShell 查看授權和服務](view-licenses-and-services-with-microsoft-365-powershell.md)。

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

若要尋找組織中未授權的帳戶，請執行此命令。

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

您只能將授權指派給 **UsageLocation** 屬性設定為有效的 ISO 3166-1 Alpha-2 國家碼的使用者帳戶。 例如，US 代表美國、FR 代表法國。 某些國家/地區未提供某些 Microsoft 365 服務。 如需詳細資訊，請參閱 [關於授許可權制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。
    
若要尋找沒有 **UsageLocation** 值的帳戶，請執行此命令。

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

若要設定帳戶的 **UsageLocation** 值，請執行下列命令。

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

例如：

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
如果您使用 **Get-MsolUser** Cmdlet，而不使用 **-All**參數，則只會傳回前 500 個帳戶。

### <a name="assigning-licenses-to-user-accounts"></a>指派授權給使用者帳戶
    
若要將授權指派給使用者，請在 PowerShell 中使用下列命令。
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

此範例會將 **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) 授權方案的授權指派給未授權的使用者 **belindan \@ litwareinc.com**：
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

若要將授權指派給所有未授權的使用者，請執行此命令。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>您無法將多個授權指派給使用者，請使用相同的授權計畫。 如果您沒有足夠的可用授權，授權會依照 **Get-MsolUser** Cmdlet 所傳回的順序指派給使用者，直到可用的授權執行完畢為止。
>

此範例會將 Office 365 Enterprise E3) 授權計畫中 **litwareinc:ENTERPRISEPACK** (的授權指派給所有未授權的使用者：
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

本範例會將相同授權指派給美國的銷售部門中未授權的使用者：
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>使用適用于 Graph 模組的 Azure Active Directory PowerShell，將使用者移至不同訂閱 (授權方案) 

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
接下來，取得您要切換訂閱的使用者帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。

接下來，使用此命令列出租使用者 (授權方案) 的訂閱。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下來，列出使用者帳戶目前具有這些命令的訂閱。

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

識別使用者目前已 (FROM 訂閱) 和使用者移至其中的訂閱 (TO 訂閱) 。

最後，指定 TO 及 FROM 訂閱名稱 (SKU 部分編號) 並執行這些命令。

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

您可以使用下列命令來確認使用者帳戶的訂閱變更。

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>請參閱

[使用 PowerShell 管理使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
