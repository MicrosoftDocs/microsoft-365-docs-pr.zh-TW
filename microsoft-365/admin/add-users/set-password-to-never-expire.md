---
title: 設定個別使用者的密碼永不過期
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 瞭解如何使用 Windows PowerShell 將部分個人的使用者密碼設為永不過期。
ms.openlocfilehash: 04fb2b0c17f695c41df2f8b1277c7918054ae9fe
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240232"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>設定個別使用者的密碼永不過期

## <a name="set-the-password-expiration-policy-for-your-organization"></a>設定組織的密碼到期原則

1. 在系統管理中心中，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全性 & 隱私權</a>] 頁面。
2. 選取 [**密碼原則**] 旁邊的 [**編輯**]。 
3. 如果密碼設為永不過期，請將開關設定為 [**關閉**]。 您可以選擇指定密碼到期前的天數。

## <a name="set-the-password-expiration-policy-for-individual-users"></a>為個別使用者設定密碼到期原則

Microsoft cloud service 的全域系統管理員可以使用 [Azure Active Directory PowerShell for Graph]，將密碼設為不會到期的特定使用者。 您也可以使用 AzureAD Cmdlet 來移除永不過期的設定，或查看哪些使用者密碼設定為永不過期。

本指南適用于其他提供者，例如 Intune 和 Office 365，也就是針對身分識別及目錄服務，也依賴 Azure AD。 [密碼到期] 是原則中唯一可以變更的部分。

如需有關圖形之 Azure AD PowerShell 的詳細資訊，請參閱[Azure Active Directory PowerShell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)。

> [!NOTE]
> 只有未透過目錄同步處理同步處理的使用者帳戶密碼才能設定為不會過期。 如需目錄同步作業的詳細資訊，請參閱[CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>如何檢查密碼的到期原則

如需 AzureAD 模組中 AzureADUser 命令的詳細資訊，請參閱參考文章[AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。

執行下列其中一個命令：

- 若要查看單一使用者的密碼是否設為永不過期，請使用 UPN （例如， *user@contoso.onmicrosoft.com*）或您要檢查之使用者的使用者識別碼，執行下列 Cmdlet：

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

- 若要查看所有使用者的 [**密碼永不到期**] 設定，請執行下列 Cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 若要在目前使用者名稱為**ReportPasswordNeverExpires**的桌上型電腦上，取得所有具有 PasswordNeverExpires Html 的使用者報告

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- 若要在目前使用者名稱為**ReportPasswordNeverExpires**的電腦上使用 CSV 中的所有使用者報告，取得 PasswordNeverExpires

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
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

### <a name="set-a-password-to-never-expire"></a>將密碼設為永不過期

執行下列其中一個命令：

- 若要將某個使用者的密碼設為永不過期，請使用 UPN 或使用者的使用者識別碼執行下列 Cmdlet：

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 若要將組織中所有使用者的密碼設為永不過期，請執行下列 Cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> 根據屬性設定`-PasswordPolicies DisablePasswordExpiration`為 [仍然存在的`pwdLastSet`密碼] 的密碼。 如果您將使用者密碼設為永不過期，而 90 + 天則為 [已移至]，密碼會到期。 根據`pwdLastSet`屬性，如果您變更到期時間`-PasswordPolicies None`，則超過90天的所有密碼`pwdLastSet`都需要使用者在下次登入時變更。 這項變更可能會影響大量的使用者。