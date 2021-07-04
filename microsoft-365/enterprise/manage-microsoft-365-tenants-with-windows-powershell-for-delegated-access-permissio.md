---
title: 使用合作協力廠商的 Windows PowerShell 管理 Microsoft 365 承租人
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: 在本文中，您將瞭解如何使用 PowerShell 進行 Microsoft 365，以管理客戶租用。
ms.openlocfilehash: 96c2c148b64d638ea977922f6a0ae3d5e23a8ace
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289100"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>使用委派存取許可權的 Windows PowerShell 管理 Microsoft 365 承租人 (結合) 夥伴

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Windows PowerShell 允許合作和雲端解決方案提供者 (CSP) 協力廠商可輕鬆管理及報告 Microsoft 365 系統管理中心中無法使用的客戶租使用者設定。 請注意，合作夥伴系統管理員帳戶須有管理代表 (AOBO) 權限才能連接其客戶租用。

委派的存取權限 (DAP) 合作夥伴就是新聞訂閱方式和雲端解決方案提供者 (CSP) 合作夥伴。 他們通常是其他公司的網路或電信服務提供者。 他們會將 Microsoft 365 訂閱捆綁到其客戶的服務產品中。 當他們銷售 Microsoft 365 訂閱時，系統會自動授與租用 AOBO) 許可權的 (管理，讓他們能管理及報告客戶租用。
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

本主題中的程式需要連接至[連線，才能與 PowerShell Microsoft 365](connect-to-microsoft-365-powershell.md)。

您也需要合作夥伴租用戶系統管理員認證。

## <a name="what-do-you-want-to-do"></a>您要執行的工作

### <a name="list-all-tenant-ids"></a>列出所有租用戶識別碼

> [!NOTE]
> 如果您有擁有 500 個以上的租用戶，請使用  _-All_ 或 _-MaxResultsParameter_ 來設定 Cmdlet 語法的範圍。這適用於其他提供大量輸出的 Cmdlet (如 **Get-MsolUser** )。

若要列出所有可存取的客戶租用戶識別碼，請執行此命令。

```powershell
Get-MsolPartnerContract -All | Select-Object TenantId
```

這會顯示按照 **TenantId** 排列的所有客戶租用戶清單。

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。 若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。
>

### <a name="get-a-tenant-id-by-using-the-domain-name"></a>使用網域名稱來取得租用戶識別碼

若要依據網域名稱來取得特定客戶租用戶的 **TenantId** ，請執行此命令。將 _<domainname.onmicrosoft.com>_ 取代為所需的實際客戶租用戶網域名稱。

```powershell
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>列出租用戶的所有網域

若要取得任一客戶租用戶的所有網域，請執行此命令。將 _<customer TenantId value>_ 取代為實際值。

```powershell
Get-MsolDomain -TenantId <customer TenantId value>
```

如果您已經註冊其他網域，這會傳回與客戶 **TenantId** 相關聯的所有網域。

### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>取得所有租用戶和註冊網域的對應

Microsoft 365 命令的先前 PowerShell 會向您說明如何在承租人 IDs 或網域中檢索，但不能同時在兩者之間取得任何明確的對應。 此命令會產生所有客戶租用戶識別碼和網域的清單。

```powershell
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>取得租用戶的所有使用者

這會顯示特定租用戶之所有使用者的 **UserPrincipalName**、**DisplayName** 和 **isLicensed** 狀態。將 _<customer TenantId value>_ 取代為實際值。

```powershell
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>取得有關使用者的所有詳細資料

如果您想要查看特定使用者的所有內容，請執行此命令。將 _<customer TenantId value>_ 和 _<user principal name value>_ 取代為實際值。

```powershell
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>新增使用者、設定選項及指派授權

Microsoft 365 使用者的大量建立、設定及授權，對 Microsoft 365 使用 PowerShell 特別有效。 在這兩個步驟的程式中，您會先以逗號分隔的值 (CSV) 檔案建立所有使用者的專案，然後使用 Microsoft 365 的 PowerShell 匯入該檔案。

#### <a name="create-a-csv-file"></a>建立 CSV 檔案

使用此格式來建立 CSV 檔案：

`UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`

其中：

- **UsageLocation** ：此項目的值是由兩個字母組成的使用者 ISO 國家/地區碼。您可以在 [ISO 線上瀏覽平台](https://go.microsoft.com/fwlink/p/?LinkId=532703)查詢國家/地區碼。例如，美國的代碼是 US，而巴西的代碼則是 BR。

- **LicenseAssignment** ：此項目的值使用格式： `syndication-account:<PROVISIONING_ID>`. 例如，如果您要將 O365_Business_Premium 授權指派給客戶租用戶使用者， **LicenseAssignment** 值看起來會像： **syndication-account:O365_Business_Premium** 。在新聞訂閱方式合作夥伴入口網站中，您可以找到能以新聞訂閱方式或 CSP 合作夥伴身分存取的 PROVISIONING_ID。

#### <a name="import-the-csv-file-and-create-the-users"></a>匯入 CSV 檔案及建立使用者

建立 CSV 檔案之後，請執行此命令以利用使用者在第一次登入時必須變更的不會到期密碼建立使用者帳戶，以及指派您指定的授權。請務必替代正確的 CSV 檔案名稱。

```powershell
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>另請參閱

[合作夥伴說明](https://go.microsoft.com/fwlink/p/?LinkId=533477)
