---
title: 使用 PowerShell View Microsoft 365 使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: 瞭解如何使用 PowerShell 以不同方式來查看、列出或顯示 Microsoft 365 使用者帳戶。
ms.openlocfilehash: 77219fb89430ed257ef2a68a7b24bf9ebac715b2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290168"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell View Microsoft 365 使用者帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以使用 Microsoft 365 系統管理中心來查看 Microsoft 365 租使用者的帳戶。 Microsoft 365 的 PowerShell 啟用此功能，但也提供其他功能。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>針對 Graph 模組，請使用 Azure Active Directory PowerShell

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
### <a name="view-all-accounts"></a>查看所有帳戶

若要顯示完整的使用者帳戶清單，請執行下列命令：
  
```powershell
Get-AzureADUser
```

您應該會收到類似以下的資訊：
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>查看特定帳戶

若要顯示特定的使用者帳戶，請執行下列命令。 填寫使用者帳戶的登入帳戶名稱，也稱為使用者主要名稱 (UPN) 。 移除 "<" 和 ">" 字元。
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

以下為範例：
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>查看特定帳戶的其他屬性值

根據預設， **AzureADUser** Cmdlet 只會顯示帳戶的 *ObjectID*、 *DisplayName* 及 *UserPrincipalName* 屬性。

若要更選擇要顯示的內容，請搭配使用 **Select** Cmdlet 搭配 **AzureADUser 指令程式** 。 若要組合這兩個 Cmdlet，請使用 "管道" 字元 ( "|") ，它會告訴 Azure Active Directory PowerShell Graph 以取得一個命令的結果，並將其傳送至下一個命令。 以下是一個範例命令，會顯示每個使用者帳戶的 *DisplayName*、 *部門* 和 *UsageLocation* ：
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

這個命令會指示 PowerShell：
  
1.  (**AzureADUser**) 取得使用者帳戶上的所有資訊，並將其傳送至下一個命令 (**|**) 。
    
1.  只顯示使用者帳戶名稱、部門和使用位置， (**選取 DisplayName、部門、UsageLocation**) 。
  
若要查看特定使用者帳戶的所有屬性，請使用 **Select** Cmdlet 及萬用字元 ( * ) 。 以下為範例：
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

在另一個範例中，執行下列命令以檢查特定使用者帳戶的啟用狀態：
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>查看帳戶同步處理狀態

使用者帳戶有兩個來源： 

- Windows Server Active Directory (AD) ，也就是從內部部署 AD 同步處理至雲端的帳戶。

- Azure Active Directory (Azure ad) 在雲端中直接建立的 ad 帳戶。


下列命令會指示 PowerShell 取得屬性 *DirSyncEnabled* 設定為 *True* 的所有使用者。 您可以使用它來尋找與內部部署 AD 同步處理的帳戶。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

下列命令會指示 PowerShell 取得屬性 *DirSyncEnabled* 設定為 *False* 的所有使用者。 您可以使用它來尋找僅雲端帳戶。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>根據共同屬性來查看帳戶

若要更選擇要顯示的帳戶清單，您可以使用 **Where** Cmdlet 搭配 **AzureADUser** Cmdlet。 若要組合這兩個 Cmdlet，請使用 "管道" 字元 ( "|") ，它會告訴 Azure Active Directory PowerShell Graph 以取得一個命令的結果，並將其傳送至下一個命令。 以下範例命令只會顯示具有未指定使用位置的使用者帳戶：
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

這個命令會指示 Azure Active Directory PowerShell Graph：
  
1.  (**AzureADUser**) 取得使用者帳戶上的所有資訊，並將其傳送至下一個命令 (**|**) 。
    
1. 尋找所有未指定使用位置的使用者帳戶， (**其中 {$ \_ 。UsageLocation-eq $Null}**) 。 在大括弧內，此命令會指示 PowerShell 只找出 UsageLocation 使用者帳戶屬性 (的帳戶集 **$ \_ 。** 未指定 UsageLocation)  (**-eq $Null**) 。
    
**UsageLocation** 屬性只是與使用者帳戶相關聯的眾多屬性之一。 若要顯示特定使用者帳戶的所有屬性，請使用 **Select** Cmdlet 及萬用字元 ( * ) 。 以下為範例：
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

例如，「 **城市** 」是使用者帳戶屬性的名稱。 您可以使用下列命令列出居住在倫敦的所有使用者帳戶：
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> 在這些範例中， **where** Cmdlet 的語法是 **{$ \_ 。** [user account property name][比較運算子]值 **}**。 > [comparison 運算子] 是 **-eq** for equals，- **ne** 代表不等於，- **lt** 代表小於， **-gt** 代表大於，其他。  [value] 通常是一個字串， (字母、數位及其他字元的順序) 、數值或未指定的 **$Null** 。 如需詳細資訊，請參閱 [Where](/powershell/module/microsoft.powershell.core/where-object)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。

首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="view-all-accounts"></a>查看所有帳戶

若要顯示完整的使用者帳戶清單，請執行下列命令：
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。 從 PowerShell 執行這些 Cmdlet。
>

您應該會收到類似以下的資訊：
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

**Get-MsolUser** 指令程式也有一組參數，用來篩選顯示的使用者帳戶集。 例如，針對未經許可的使用者清單 (已新增至 Microsoft 365，但尚未授權使用任何服務) 的使用者，請執行下列命令：
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

您應該會收到類似以下的資訊：
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

如需其他參數以篩選顯示的使用者帳戶集合的詳細資訊，請參閱 [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100))。
  
### <a name="view-a-specific-account"></a>查看特定帳戶

若要顯示特定的使用者帳戶，請執行下列命令。 填寫使用者帳戶的登入名稱，也稱為使用者主要名稱 (UPN) 。 移除 "<" 和 ">" 字元。
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>根據共同屬性來查看帳戶

若要更選擇要顯示的帳戶清單，您可以使用 **Where** Cmdlet 與 **Get-MsolUser** Cmdlet 結合使用。 若要組合這兩個 Cmdlet，請使用 "管道" 字元 ( "|") ，告知 PowerShell 取得一個命令的結果，並將它傳送至下一個命令。 以下範例只會顯示具有未指定使用位置的使用者帳戶：
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

這個命令會指示 PowerShell：
  
1. **Get-MsolUser**) 取得使用者帳戶 (的所有資訊，並將其傳送至下一個命令 (**|**) 。
    
1. 尋找所有未指定使用位置的使用者帳戶， (**其中 {$ \_ 。UsageLocation-eq $Null}**) 。 在大括弧內，此命令會指示 PowerShell 只尋找 UsageLocation 使用者帳戶屬性 (的帳戶集 **$ \_ 。** 未指定 UsageLocation)  (**-eq $Null**) 。
    
您應該會收到類似以下的資訊：
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation* 屬性只是與使用者帳戶相關聯的眾多屬性之一。 若要查看使用者帳戶的所有屬性，請使用 **Select** Cmdlet 及萬用字元 ( * ) 以顯示特定使用者帳戶的所有屬性。 以下為範例：
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

例如，「 *城市* 」是使用者帳戶屬性的名稱。 您可以使用下列命令來列出居住在倫敦的使用者的所有使用者帳戶：
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> 在這些範例中， **where** Cmdlet 的語法是 **{$ \_ 。** [user account property name][比較運算子]值 **}**.  [比較運算子] 的 **-eq** 代表 equals，- **ne** 代表不等於， **-lt** 代表小於， **-gt** 代表大於，其他。  [value] 通常是一個字串， (字母、數位及其他字元的順序) 、數值或未指定的 **$Null** 。 如需詳細資訊，請參閱 [Where](/powershell/module/microsoft.powershell.core/where-object)。
  
若要檢查使用者帳戶的封鎖狀態，請使用下列命令：
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>查看帳戶的其他屬性值

根據預設， **Get-MsolUser** Cmdlet 會顯示使用者帳戶的三個屬性：
  
- UserPrincipalName

- DisplayName

- Islicensed 內容

如果您需要其他屬性（例如，使用者在其中運作的部門，以及他們使用 Microsoft 365 服務的國家/地區），您可以搭配 **Select** 資訊清單執行 **Get-MsolUser** ，以指定使用者帳戶屬性的清單。 以下為範例：
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

這個命令會指示 PowerShell：
  
1. 取得 (**Get-MsolUser**) 的使用者帳戶資訊，並將其傳送至下一個命令 (**|**) 。
    
1. 只顯示使用者帳戶名稱、部門和使用位置， (**選取 DisplayName、部門、UsageLocation**) 。
    
您應該會收到類似以下的資訊：
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

**Select** Cmdlet 可讓您選擇要顯示的屬性。 若要顯示特定使用者帳戶的所有屬性，請使用通配字元 ( * ) 。 以下為範例：
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

若要更選擇要顯示的帳戶清單，您也可以使用 **Where** Cmdlet。 以下範例命令只會顯示具有未指定使用位置的使用者帳戶：
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

這個命令會指示 PowerShell：
  
1. 取得 (**Get-MsolUser**) 的使用者帳戶資訊，並將其傳送至下一個命令 (**|**) 。
    
1. 尋找所有未指定使用位置的使用者帳戶， (**其中 {$ \_ 。UsageLocation-eq $Null}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。 在大括弧內，此命令會指示 PowerShell 只找出 UsageLocation 使用者帳戶屬性 (的帳戶集 **$ \_ 。** 未指定 UsageLocation)  (**-eq $Null**) 。
    
1. 只顯示使用者帳戶名稱、部門和使用位置， (**選取 DisplayName、部門、UsageLocation**) 。
    
您應該會收到類似以下的資訊：
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

如果您是使用目錄同步處理來建立及管理 Microsoft 365 使用者，您可以顯示 Microsoft 365 使用者已計畫的本機帳戶。 下列範例假設：

- Azure AD 連線設定為使用 ObjectGUID 的預設來源錨點。  (如需設定來源錨點的詳細資訊，請參閱[AZURE AD 連線：設計概念](/azure/active-directory/hybrid/plan-connect-design-concepts)) 。
- 已安裝 PowerShell 的 Active Directory 網域服務模組 (請參閱 [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)) 。

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>另請參閱

[以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)