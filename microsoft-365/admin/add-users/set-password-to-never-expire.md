---
title: 設定個別使用者的密碼永不過期
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: 登入您的 Microsoft 365 系統管理員帳戶，將某些個別使用者密碼設定為永不到期，使用 Windows PowerShell。
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571922"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>設定個別使用者的密碼永不過期

本文說明如何為個別使用者設定密碼，使其不會過期。 您必須使用 PowerShell 來完成這些步驟。

## <a name="before-you-begin"></a>在您開始之前

本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。 若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。 [何謂系統管理員帳戶?](../../business-video/admin-center-overview.md) 

您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。

Microsoft cloud service 的全域系統管理員可以使用 Graph 的[Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) ，設定特定使用者不會到期的密碼。 您也可以使用 [AzureAD](/powershell/module/Azuread) Cmdlet 來移除永不過期的設定，或查看哪些使用者密碼設定為永不過期。

本指南適用于其他提供者，例如 Intune 和 Microsoft 365，也取決於 Azure AD 的身分識別和目錄服務。 [密碼到期] 是原則中唯一可以變更的部分。

> [!NOTE]
> 只有未透過目錄同步處理同步處理的使用者帳戶密碼才能設定為不會過期。 如需目錄同步處理的詳細資訊，請參閱[連線 AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect)。

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>如何檢查密碼的到期原則

如需 AzureAD 模組中 Get-AzureADUser 命令的詳細資訊，請參閱參考文章 [AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。

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

- 若要在目前使用者名稱為 **ReportPasswordNeverExpires.html** 之電腦上的 Html 中取得所有具有 PasswordNeverExpires 的使用者報告

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- 若要在目前使用者名稱為 **ReportPasswordNeverExpires.csv** 的電腦上，取得 CSV 中具有 PasswordNeverExpires 的所有使用者報告

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

> [!WARNING]
> 設定參數的使用者帳戶 `-PasswordPolicies DisablePasswordExpiration` 仍會以屬性為基礎 `pwdLastSet` 。 根據 `pwdLastSet` 屬性，如果您變更到期 `-PasswordPolicies None` ，所有 pwdLastSet 超過90天的密碼都需要使用者在下次登入時進行變更。 這項變更可能會影響大量的使用者。

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

## <a name="related-content"></a>相關內容

[讓使用者重設自己的密碼](../add-users/let-users-reset-passwords.md) (文章)

[重設密碼](../add-users/reset-passwords.md) (文章)