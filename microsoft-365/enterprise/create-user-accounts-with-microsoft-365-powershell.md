---
title: 使用 PowerShell 建立 Microsoft 365 使用者帳戶
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
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: 如何使用 PowerShell 建立個別或多個 Microsoft 365 使用者帳戶。
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907561"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell 建立 Microsoft 365 使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以使用 PowerShell 進行 Microsoft 365，以有效地建立使用者帳戶，包括多個帳戶。

當您在 PowerShell 中建立使用者帳戶時，永遠都必須有特定的帳戶屬性。 不需要其他屬性，但很重要。 請參閱以下表格。
  
|**屬性名稱**|**必要？**|**描述**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |是  <br/> |這是 Microsoft 365 服務所使用的顯示名稱。 例如， *Caleb sills 帳戶*。 <br/> |
|**UserPrincipalName** <br/> |是  <br/> |這是用來登入 Microsoft 365 服務的帳戶名稱。 例如， *CalebS \@ contoso.onmicrosoft.com*。  <br/> |
|**FirstName** <br/> |否  <br/> ||
|**LastName** <br/> |否  <br/> ||
|**LicenseAssignment** <br/> |否  <br/> |這是授權方案 (也稱為授權計畫或 SKU) ，可將可用的授權指派給使用者帳戶。 授權會定義帳戶可用的 Microsoft 365 服務。 當您建立帳戶時，您不需要指派授權給使用者，但是該帳戶必須具有授權才能存取 Microsoft 365 服務。 建立使用者帳戶之後，您有 30 天的時間進行使用者帳戶授權。 |
|**Password** <br/> |否  <br/> | 如果您未指定密碼，則會指派隨機密碼給使用者帳戶，並可在命令結果中看見此密碼。 如果您指定密碼，必須是下列類型的8到16個 ASCII 文字字元：小寫字母、大寫字母、數位和符號。<br/> |
|**UsageLocation** <br/> |否  <br/> |這是有效的 ISO 3166-1 alpha-2 國碼。 例如，美國 *為美國，法國為* *FR* 。 提供此值很重要，因為某些國家/地區沒有提供一些 Microsoft 365 服務。 除非帳戶已設定此值，否則您無法將授權指派給使用者帳戶。 如需詳細資訊，請參閱 [關於授許可權制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。<br/> |

>[!Note]
>瞭解如何使用 Microsoft 365 系統管理中心[建立使用者帳戶](../admin/add-users/add-users.md)。
> 
> 如需其他資源的清單，請參閱 [管理使用者和群組](../admin/add-users/index.yml)。
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

連接後，請使用下列語法來建立個別帳戶：
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

本範例會為 US user *Caleb sills 帳戶* 建立帳戶：
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="create-an-individual-user-account"></a>建立個別使用者帳戶

若要建立個別帳戶，請使用下列語法：
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell 核心不支援 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，以及其名稱中具有 *Msol* 的 Cmdlet。 從 PowerShell 執行這些 Cmdlet。
>

若要列出可用的授權方案名稱，請使用此命令：

````powershell
Get-MsolAccountSku
````

此範例會為 US user *Caleb sills 帳戶* 建立帳戶，並從 `contoso:ENTERPRISEPACK` (Office 365 企業版 E3) 授權計畫指派授權。
  
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

   >[!NOTE]
   >CSV 檔案的第一列中的欄名稱和其順序都是任意的。 不過，請確定檔案的其餘部分中的資料順序符合欄名稱的順序。 並在 PowerShell 中為 Microsoft 365 命令使用參數值的資料行名稱。
    
2. 使用下列語法：
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   本範例會從檔案 *C:\My Documents\NewAccounts.csv* 中建立使用者帳戶，並將結果記錄在名為 *C:\My Documents\NewAccountResults.csv* 檔案中。
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. 檢閱輸出檔以查看結果。 我們未指定密碼，所以輸出檔中會顯示 Microsoft 365 產生之隨機密碼。
    
## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)