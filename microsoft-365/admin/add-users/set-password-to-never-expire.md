---
title: 設定個別使用者的密碼永不過期
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 瞭解如何使用 Windows PowerShell 將部分個人的使用者密碼設為永不過期。
ms.openlocfilehash: e778ad8a020a6767934d51f8bc227bfc39b13a9b
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580913"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>設定個別使用者的密碼永不過期

本文說明如何為個別使用者設定密碼，使其不會過期。 您必須使用 PowerShell 來完成這些步驟。

## <a name="before-you-begin"></a>在您開始之前

本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。 若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。 [何謂系統管理員帳戶?](../admin-overview/admin-overview.md) 

您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。

Microsoft cloud service 的全域系統管理員可以使用 [ [Azure Active Directory PowerShell For Graph]](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) ，將密碼設為不會到期的特定使用者。 您也可以使用 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) Cmdlet 來移除永不過期的設定，或查看哪些使用者密碼設定為永不過期。

本指南適用于其他提供者，例如 Intune 和 Microsoft 365，也就是針對身分識別及目錄服務，也依賴 Azure AD。 [密碼到期] 是原則中唯一可以變更的部分。

> [!NOTE]
> 只有未透過目錄同步處理同步處理的使用者帳戶密碼才能設定為不會過期。 如需目錄同步作業的詳細資訊，請參閱 [CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>如何檢查密碼的到期原則

如需 AzureAD 模組中 Get-AzureADUser 命令的詳細資訊，請參閱參考文章 [AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。

執行下列其中一個命令：

- 若要查看單一使用者的密碼是否設為永不過期，請使用 UPN (執行下列 Cmdlet，例如， *user@contoso.onmicrosoft.com*) 或您要檢查之使用者的使用者識別碼：

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    範例：

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- 若要查看所有使用者的 [ **密碼永不到期** ] 設定，請執行下列 Cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 若要在目前使用者名稱為**ReportPasswordNeverExpires.html**之電腦上的 Html 中取得所有具有 PasswordNeverExpires 的使用者報告

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- 若要在目前使用者名稱為**ReportPasswordNeverExpires.csv**的電腦上，取得 CSV 中具有 PasswordNeverExpires 的所有使用者報告

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 若要將組織中所有使用者的密碼設為永不過期，請執行下列 Cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a>設定密碼為到期

執行下列其中一個命令：

- 若要設定一個使用者的密碼，使密碼到期，請使用 UPN 或使用者的使用者識別碼執行下列 Cmdlet：

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 若要設定組織中所有使用者的密碼，使其到期，請使用下列 Cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> 根據使用者帳戶屬性，以參數設定的使用者帳戶 `-PasswordPolicies DisablePasswordExpiration` 仍會保留天數 `pwdLastSet` 。 例如，如果您將使用者密碼設為永不到期，但90或更多的天數，密碼仍然會到期。 根據 `pwdLastSet` 使用者帳戶屬性，針對使用參數設定的使用者帳戶 `-PasswordPolicies None` ，所有超過90天的密碼都 `pwdLastSet` 需要使用者在下次登入時變更。這項變更可能會影響大量的使用者。

## <a name="related-content"></a>相關內容

[讓使用者重設自己的密碼](../add-users/let-users-reset-passwords.md)

[重設密碼](../add-users/reset-passwords.md)