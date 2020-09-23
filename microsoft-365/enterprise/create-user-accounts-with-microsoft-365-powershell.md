---
title: 使用 PowerShell 建立 Microsoft 365 使用者帳戶
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: 在本文中，您將瞭解如何使用 PowerShell 來建立使用者帳戶或多個 Microsoft 365 使用者帳戶。
ms.openlocfilehash: 00ae8806e786eada092704febd65c72c72382788
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235591"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell 建立 Microsoft 365 使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以使用 Microsoft 365 的 PowerShell，有效地建立使用者帳戶，尤其是多個使用者帳戶。 當您在 PowerShell 中建立使用者帳戶時，永遠都必須有特定的帳戶屬性。 其他屬性不一定用於建立帳戶，但卻很重要。 下表說明這些屬性：
  
|**屬性名稱**|**必要？**|**描述**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |是  <br/> |這是 Microsoft 365 服務中使用的顯示名稱。 例如，Caleb Sills。  <br/> |
|**UserPrincipalName** <br/> |是  <br/> |這是用來登入 Microsoft 365 服務的帳戶名稱。 例如，CalebS@contoso.onmicrosoft.com。  <br/> |
|**FirstName** <br/> |否  <br/> ||
|**LastName** <br/> |否  <br/> ||
|**LicenseAssignment** <br/> |否  <br/> |這是授權方案 (也稱為授權計畫或 SKU) ，可將可用的授權指派給使用者帳戶。 授權會定義可供帳戶使用的 Microsoft 365 服務。 當您建立帳戶時，您不需要指派授權給使用者，但是需要授權才能存取 Microsoft 365 服務。 建立使用者帳戶之後，您有 30 天的時間進行使用者帳戶授權。 |
|**Password** <br/> |否  <br/> | 如果您未指定密碼，則會指派隨機密碼給使用者帳戶，並可在命令結果中看見此密碼。如果您指定密碼，該密碼必須是下列任三種類型的 8 到 16 個 ASCII 文字：小寫字母、大寫字母、數字和符號。 <br/> |
|**UsageLocation** <br/> |否  <br/> |這是有效的 ISO 3166-1 alpha-2 國碼。 例如，US 代表美國、FR 代表法國。 提供此值很重要，因為某些國家/地區無法使用某些 Microsoft 365 服務，因此除非該帳戶已設定此值，否則您無法指派授權給使用者帳戶。 如需詳細資訊，請參閱 [關於授許可權制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。  <br/> |

>[!Note]
>瞭解如何使用 Microsoft 365 系統管理中心[建立使用者帳戶](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)。 如需其他資源的清單，請參閱 [管理使用者和群組](https://docs.microsoft.com/microsoft-365/admin/add-users/)。
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

連接之後，使用下列語法來建立個別帳戶：
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

本範例會為名為 Caleb Sills 的美國使用者建立帳戶：
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="create-an-individual-user-account"></a>建立個別使用者帳戶

若要建立個別帳戶，請使用下列語法：
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

若要列出可用的授權方案名稱，請使用此命令：

````powershell
Get-MsolAccountSku
````

本範例會建立一個名為 Caleb Sills 的美國使用者帳戶，並指派 `contoso:ENTERPRISEPACK` (Office 365 企業版 E3) 授權方案的授權。
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>建立多個使用者帳戶

1. 建立包含必要使用者帳戶資訊的逗點分隔值 (CSV) 檔案。例如：
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
>CSV 檔案的第一列中的欄名稱和其順序都是任意的，但是請確定檔案的其餘部分中的資料符合欄名稱的順序，並在 PowerShell for Microsoft 365 命令中使用參數值的欄名。
    
2. 使用下列語法：
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

本範例會從名為 C:\My Documents\NewAccounts.csv 的檔案建立使用者帳戶，並將結果記錄在名為 C:\My Documents\NewAccountResults.csv 的檔案中
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. 檢閱輸出檔以查看結果。 我們未指定密碼，所以在輸出檔中會顯示 Microsoft 365 所產生的隨機密碼。
    
## <a name="see-also"></a>請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
