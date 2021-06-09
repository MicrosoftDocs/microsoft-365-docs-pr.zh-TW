---
title: 使用 PowerShell 停用 Microsoft 365 服務的存取權
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: 在本文中，您將瞭解如何使用 PowerShell 來停用使用者 Microsoft 365 服務的存取權。
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688478"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>使用 PowerShell 停用 Microsoft 365 服務的存取權

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 帳戶指派授權方案的授權時，使用者就可以從該授權取得 Microsoft 365 服務。 不過，您可以控制使用者可以存取的 Microsoft 365 服務。 例如，即使授權允許存取 SharePoint 線上服務，您還是可以停用存取權。 您可以使用 PowerShell 針對特定授權方案停用任何數目的服務存取權：

- 個別帳戶。
- 一組帳戶。
- 您組織中的所有帳戶。

>[!Note]
>有 Microsoft 365 服務相依性，可防止當其他服務依賴于指定的服務時停用此服務。
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

接下來，使用此命令來查看可用的授權方案，也稱為 AccountSkuIds：

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

如需詳細資訊，請參閱 [使用 PowerShell 查看授權和服務](view-licenses-and-services-with-microsoft-365-powershell.md)。
    
若要查看本主題中程式的 before 和 after 結果，請參閱 [使用 PowerShell 查看帳戶授權和服務詳細資料](view-account-license-and-service-details-with-microsoft-365-powershell.md)。
    
PowerShell 指令碼可供使用，會自動執行本主題中所述的程序。 具體說來，此腳本可讓您查看及停用 Microsoft 365 組織中的服務，包括 Sway。 如需詳細資訊，請參閱 [使用 PowerShell 停用 Sway 的存取權](disable-access-to-sway-with-microsoft-365-powershell.md)。
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>針對特定授權方案停用特定使用者的特定 Microsoft 365 服務
  
若要針對特定授權方案停用特定的一組 Microsoft 365 服務，請執行下列步驟：
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>步驟1：使用下列語法識別授權方案中不想要的服務：
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

下列範例會建立一個 **LicenseOptions** 物件，該物件會停用名為 (的授權計畫中的 Office 和 SharePoint 線上服務 `litwareinc:ENTERPRISEPACK` Office 365 企業版 E3) 。
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>步驟2：在一或多個使用者上使用步驟1中的 **LicenseOptions** 物件。
    
若要建立已停用服務的新帳戶，請使用下列語法：
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

下列範例會為 Allie Bellew 建立新的帳戶，以指派授權並停用步驟1中所述的服務。
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

如需在 Microsoft 365 中為 PowerShell 建立使用者帳戶的詳細資訊，請參閱[使用 PowerShell 建立使用者帳戶](create-user-accounts-with-microsoft-365-powershell.md)。
    
若要停用現有授權使用者的服務，請使用下列語法：
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

本範例會停用使用者 BelindaN@litwareinc.com 的服務。
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

若要停用步驟1中所述的所有現有授權使用者的服務，請從 **Get-MsolAccountSku** (Cmdlet 的顯示（如 **litwareinc:ENTERPRISEPACK**) ）中指定 Microsoft 365 計畫的名稱，然後執行下列命令：
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 如果您使用 **Get-MsolUser** Cmdlet 但未使用 _All_ 參數，則只會傳回第一個500使用者帳戶。

若要為一組現有的使用者停用服務，請使用下列其中一種方法來識別使用者：
    
**方法1。根據現有的帳戶屬性來篩選帳戶** 

若要這麼做，使用下列語法：
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

下列範例會停用美國地區的銷售部門中的使用者服務。
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**方法2：使用特定帳戶的清單** 

若要這樣做，請執行下列步驟：
    
1. 建立一個文字檔，其中每一行上都包含一個帳戶，如下所示：
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   在此範例中，文字檔為 C： \\ 我的檔 \\Accounts.txt。
    
2. 執行下列命令：
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

如果您想要針對多個授權方案停用服務存取權，請針對每個授權方案重複上述指示，以確保：

- 已指派授權方案的使用者帳戶。
- 授權方案提供要停用的服務。

若要在指派使用者給授權計畫時為使用者停用 Microsoft 365 服務，請參閱在[指派使用者授權時停用服務存取權](disable-access-to-services-while-assigning-user-licenses.md)。

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>將授權方案中的所有服務指派給使用者帳戶

針對已停用服務的使用者帳戶，您可以使用下列命令來啟用特定授權方案的所有服務：

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>相關主題

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
