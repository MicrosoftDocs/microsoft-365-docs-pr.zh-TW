---
title: 移除具有 PowerShell 之使用者帳戶的 Microsoft 365 授權
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: 說明如何使用 PowerShell 移除先前指派給使用者的 Microsoft 365 授權。
ms.openlocfilehash: 9944d1ab056d109b6bf71a44fe01acef78ce1f14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920665"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>移除具有 PowerShell 之使用者帳戶的 Microsoft 365 授權

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

>[!Note]
>瞭解如何使用 Microsoft 365 系統管理中心[移除使用者帳戶中的授權](../admin/manage/remove-licenses-from-users.md)。 如需其他資源的清單，請參閱 [管理使用者和群組](../admin/add-users/index.yml)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

接下來，使用此命令列出租使用者的授權計畫。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下來，取得您要移除授權的帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。

最後，指定使用者登入和授權方案名稱、移除「<」和「>」字元，然後執行這些命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

若要移除特定使用者帳戶的所有授權，請指定使用者登入名稱、移除「<」和「>」字元，然後執行這些命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
   
若要查看授權方案 (**AccountSkuID** 組織中的) 資訊，請參閱下列主題：
    
  - [使用 PowerShell 來查看授權和服務](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [使用 PowerShell 來查看帳戶授權與服務詳細資料](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
如果您使用 **Get-MsolUser** Cmdlet，而不使用 _-All_ 參數，則只會傳回前 500 個帳戶。
    
### <a name="removing-licenses-from-user-accounts"></a>移除使用者帳戶中的授權

若要從現有的使用者帳戶中移除授權，請使用下列語法：
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

本範例會從使用者帳戶 BelindaN@litwareinc.com 移除 Office 365 企業版 E3) 授權的 **litwareinc:ENTERPRISEPACK** (。
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>您無法使用 `Set-MsolUserLicense` Cmdlet 將使用者取消指派為 *取消* 的授權。 您必須為 Microsoft 365 系統管理中心中的每個使用者帳戶個別執行此動作。
>

若要從現有授權使用者的群組中移除所有授權，請使用下列其中一種方法：
  
- 根據 **現有的帳戶屬性來篩選帳戶** 若要這麼做，請使用下列語法：
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

這則範例會移除美國的銷售部門中所有使用者帳戶的所有授權。
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **針對特定授權使用特定帳戶的清單** 若要這麼做，請執行下列步驟：
    
1. 在每一行上建立及儲存包含一個帳戶的文字檔，如下所示：
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. 使用下列語法：
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
本範例會從在文字檔 C:\My Documents\Accounts.txt 中所定義的使用者帳戶中，移除 **litwareinc:ENTERPRISEPACK** (Office 365 企業版 E3) 授權。
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

若要從所有現有的使用者帳戶中移除所有授權，請使用下列語法：
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

若要釋放授權，另一種方法是刪除使用者帳戶。 如需詳細資訊，請參閱 [使用 PowerShell 刪除及還原使用者帳戶](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。
  
## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)