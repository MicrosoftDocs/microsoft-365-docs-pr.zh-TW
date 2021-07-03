---
title: 使用 PowerShell 設定 Microsoft 365 使用者帳戶屬性
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 使用 Microsoft 365 的 PowerShell，設定 Microsoft 365 承租人中個別或多個使用者帳戶的屬性。
ms.openlocfilehash: aeb9b586c42a0bdfb8d69b8d297998fedc1124e6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286006"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>使用 PowerShell 設定 Microsoft 365 使用者帳戶屬性

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以使用 Microsoft 365 系統管理中心來設定 Microsoft 365 租使用者帳戶的屬性。 在 PowerShell 中，您也可以執行這項動作，此外還有其他一些無法在系統管理中心中執行的動作。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

若要在 Graph 模組的 Azure Active Directory PowerShell 中設定使用者帳戶的屬性，請使用 [**AzureADUser 指令程式**](/powershell/module/azuread/set-azureaduser)，並指定要設定或變更的屬性。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="change-properties-for-a-specific-user-account"></a>變更特定使用者帳戶的屬性

您可以使用 *-ObjectID* 參數識別帳戶，並使用其他參數設定或變更特定屬性。 以下是最常見的參數清單：
  
- -部門 " \<department name> "

- -DisplayName " \<full user name> "

- -FacsimilieTelephoneNumber " \<fax number> "

- -GivenName " \<user first name> "

- -姓 " \<user last name> "

- -Mobile " \<mobile phone number> "

- -JobTitle " \<job title> "

- -PreferredLanguage " \<language> "

- -StreetAddress " \<street address> "

- -城市 " \<city name> "

- -State " \<state name> "

- -PostalCode " \<postal code> "

- -國家/地區 " \<country name> "

- -TelephoneNumber " \<office phone number> "

- -UsageLocation " \<2-character country or region code> "

    這是 ISO 3166-1 Alpha-2 (A2) 雙字母國家或地區碼。

如需其他參數，請參閱 [AzureADUser](/powershell/module/azuread/set-azureaduser)。

> [!NOTE]
> 在您指派授權給使用者帳戶之前，您必須指派使用位置。

若要為您的使用者帳戶顯示使用者主要名稱，請執行下列命令。
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

這個命令會指示 PowerShell：
  
1.  (**AzureADUser**) 取得使用者帳戶上的所有資訊，並將其傳送至下一個命令 (**|**) 。

1. 依字母順序排序使用者主體名稱清單， (**排序 UserPrincipalName**) 然後將其傳送至下一個命令 (**|**) 。

1. 只顯示每個帳戶的使用者主體名稱屬性 (**選取 UserPrincipalName**) 。

1.  (**更**) ，一次顯示一屏。

若要根據顯示名稱顯示帳戶的使用者主要名稱)  (first 和 last name，請執行下列命令。 填入 *$userName* 變數，並移除 \< and > 下列字元：
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

在這個範例中，會顯示具有顯示名稱 *Caleb sills 帳戶* 之使用者帳戶的使用者主要名稱。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

使用 *$upn* 變數，您可以根據其顯示名稱來變更個別帳戶。 以下範例會將 *Belinda Newman* 的使用位置設定為法國。 但是它會指定其顯示名稱，而不是使用者主要名稱：
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>變更所有使用者帳戶的屬性

若要變更所有使用者的屬性，您可以使用 **AzureADUser** 和 **AzureADUser** Cmdlet 的組合。 下列範例會將所有使用者的使用位置變更為 *華北*：
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

這個命令會指示 PowerShell：
  
1.  (**AzureADUser**) 取得使用者帳戶的所有資訊，並將其傳送至下一個命令 (**|**) 。

1. 將使用者位置設定為法國 (**AzureADUser-UsageLocation "FR"**) 。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>變更特定使用者帳戶組的屬性

若要變更特定使用者帳戶集的屬性，您可以使用 **AzureADUser**、 **Where** 及 **AzureADUser** Cmdlet 的組合。 下列範例會將會計部門中所有使用者的使用量位置變更為 *華北*：
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

這個命令會指示 PowerShell：
  
1.  (**AzureADUser**) 取得使用者帳戶上的所有資訊，然後將其傳送至下一個命令 (**|**) 。

1.  尋找其 *部門* 屬性設定為 "記帳" (的所有使用者帳戶， **其中 {$ _。部門-eq "記帳"}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。

1. 將使用者位置設定為法國 (**AzureADUser-UsageLocation "FR"**) 。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

若要使用 Windows PowerShell 的 Microsoft Azure Active Directory 模組設定使用者帳戶的屬性，請使用 **Set-MsolUser** Cmdlet，並指定要設定或變更的屬性。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
> [!NOTE]
> PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。 從 PowerShell 執行這些 Cmdlet。

### <a name="change-properties-for-a-specific-user-account"></a>變更特定使用者帳戶的屬性

若要設定特定使用者帳戶的屬性，請使用 [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) Cmdlet，並指定要設定或變更的屬性。 

您可以使用 *-UserPrincipalName* 參數識別帳戶，並使用其他參數設定或變更特定屬性。 以下是最常見的參數清單。
  
- -城市 " \<city name> "

- -國家/地區 " \<country name> "

- -部門 " \<department name> "

- -DisplayName " \<full user name> "

- -傳真 " \<fax number> "

- -FirstName " \<user first name> "

- -LastName " \<user last name> "

- -MobilePhone " \<mobile phone number> "

- -Office " \<office location> "

- -PhoneNumber " \<office phone number> "

- -PostalCode " \<postal code> "

- -PreferredLanguage " \<language> "

- -State " \<state name> "

- -StreetAddress " \<street address> "

- -職稱 " \<title name> "

- -UsageLocation " \<2-character country or region code> "

    這是 ISO 3166-1 Alpha-2 (A2) 雙字母國家或地區碼。

如需其他參數，請參閱 [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100))。

若要查看所有使用者的使用者主要名稱，請執行下列命令：
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

這個命令會指示 PowerShell：
  
1. **Get-MsolUser**) 取得使用者帳戶 (的所有資訊，並將其傳送至下一個命令 (**|**) 。

1. 依字母順序排序使用者主體名稱清單， (**排序 UserPrincipalName**) 然後將其傳送至下一個命令 (**|**) 。

1. 只顯示每個帳戶的使用者主體名稱屬性 (**選取 UserPrincipalName**) 。

1.  (**更**) ，一次顯示一屏。

若要根據顯示名稱顯示帳戶的使用者主要名稱)  (first 和 last name，請執行下列命令。 填入 *$userName* 變數，然後移除 \< and > 字元。
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

此範例會顯示名為 Caleb Sills 帳戶之使用者的使用者主要名稱：
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

使用 *$upn* 變數，您可以根據其顯示名稱來變更個別帳戶。 以下範例會將 *Belinda Newman* 的使用位置設定為 *法國*，但是會指定其顯示名稱，而不是其使用者主要名稱：
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>變更所有使用者帳戶的屬性

若要變更所有使用者的屬性，請使用 **Get-MsolUser** 和 **Set-MsolUser** Cmdlet 的組合。 下列範例會將所有使用者的使用位置變更為 *華北*：
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

這個命令會指示 PowerShell：
  
1. 取得使用者帳戶 (**Get-MsolUser**) 的所有資訊，並將其傳送至下一個命令 (**|**) 。

1. 將使用者位置設定為法國 (**Set-MsolUser UsageLocation "FR"**) 。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>變更特定使用者帳戶組的屬性

若要變更特定使用者帳戶集的屬性，您可以使用 **Get-MsolUser**、 **Where** 及 **Set-MsolUser** Cmdlet 的組合。 下列範例會將會計部門中所有使用者的使用量位置變更為 *華北*：
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

這個命令會指示 PowerShell：
  
1. 取得使用者帳戶 (**Get-MsolUser**) 的所有資訊，並將其傳送至下一個命令 (**|**) 。

1. 尋找其 *部門* 屬性設定為 "記帳" (的所有使用者帳戶，其為 **{$ _。部門-eq "記帳"}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。

1. 將使用者位置設定為法國 (**Set-MsolUser UsageLocation "FR"**) 。

## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
