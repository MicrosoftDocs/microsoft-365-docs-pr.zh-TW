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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 瞭解如何使用 Windows PowerShell 將部分個人的使用者密碼設為永不過期。
ms.openlocfilehash: f85eb2d3aaf5b19779ea8f293e2cbdc28c1535aa
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804205"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="02a23-103">設定個別使用者的密碼永不過期</span><span class="sxs-lookup"><span data-stu-id="02a23-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="02a23-104">設定組織的密碼到期原則</span><span class="sxs-lookup"><span data-stu-id="02a23-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="02a23-105">在系統管理中心中，移至 [**設定**] [設定] \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="02a23-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="02a23-106">在 [設定] 頁面的頂端，選取 [ **安全性 & 隱私權**]。</span><span class="sxs-lookup"><span data-stu-id="02a23-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="02a23-107">選取 [密碼到期原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02a23-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="02a23-108">如果密碼設為永不過期，請按一下 [ **將使用者密碼設為在數天后到期**] 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="02a23-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="02a23-109">您可以選擇指定密碼到期前的天數。</span><span class="sxs-lookup"><span data-stu-id="02a23-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="02a23-110">為個別使用者設定密碼到期原則</span><span class="sxs-lookup"><span data-stu-id="02a23-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="02a23-111">Microsoft cloud service 的全域系統管理員可以使用 [ [Azure Active Directory PowerShell For Graph]](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) ，將密碼設為不會到期的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="02a23-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="02a23-112">您也可以使用 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) Cmdlet 來移除永不過期的設定，或查看哪些使用者密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="02a23-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="02a23-113">本指南適用于其他提供者，例如 Intune 和 Microsoft 365，也就是針對身分識別及目錄服務，也依賴 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="02a23-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="02a23-114">[密碼到期] 是原則中唯一可以變更的部分。</span><span class="sxs-lookup"><span data-stu-id="02a23-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="02a23-115">如需有關圖形之 Azure AD PowerShell 的詳細資訊，請參閱 [Azure Active Directory PowerShell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)。</span><span class="sxs-lookup"><span data-stu-id="02a23-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="02a23-116">只有未透過目錄同步處理同步處理的使用者帳戶密碼才能設定為不會過期。</span><span class="sxs-lookup"><span data-stu-id="02a23-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="02a23-117">如需目錄同步作業的詳細資訊，請參閱 [CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="02a23-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="02a23-118">如何檢查密碼的到期原則</span><span class="sxs-lookup"><span data-stu-id="02a23-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="02a23-119">如需 AzureAD 模組中 AzureADUser 命令的詳細資訊，請參閱參考文章 [AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。</span><span class="sxs-lookup"><span data-stu-id="02a23-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="02a23-120">執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="02a23-120">Run one of the following commands:</span></span>

- <span data-ttu-id="02a23-121">若要查看單一使用者的密碼是否設為永不過期，請使用 UPN (執行下列 Cmdlet，例如， *user@contoso.onmicrosoft.com*) 或您要檢查之使用者的使用者識別碼：</span><span class="sxs-lookup"><span data-stu-id="02a23-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="02a23-122">範例：</span><span class="sxs-lookup"><span data-stu-id="02a23-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="02a23-123">若要查看所有使用者的 [ **密碼永不到期** ] 設定，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02a23-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="02a23-124">若要在目前使用者名稱為**ReportPasswordNeverExpires.html**之電腦上的 Html 中取得所有具有 PasswordNeverExpires 的使用者報告</span><span class="sxs-lookup"><span data-stu-id="02a23-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="02a23-125">若要在目前使用者名稱為**ReportPasswordNeverExpires.csv**的電腦上，取得 CSV 中具有 PasswordNeverExpires 的所有使用者報告</span><span class="sxs-lookup"><span data-stu-id="02a23-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="02a23-126">設定密碼為到期</span><span class="sxs-lookup"><span data-stu-id="02a23-126">Set a password to expire</span></span>

<span data-ttu-id="02a23-127">執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="02a23-127">Run one of the following commands:</span></span>

- <span data-ttu-id="02a23-128">若要設定一個使用者的密碼，使密碼到期，請使用 UPN 或使用者的使用者識別碼執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02a23-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="02a23-129">若要設定組織中所有使用者的密碼，使其到期，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02a23-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="02a23-130">將密碼設為永不過期</span><span class="sxs-lookup"><span data-stu-id="02a23-130">Set a password to never expire</span></span>

<span data-ttu-id="02a23-131">執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="02a23-131">Run one of the following commands:</span></span>

- <span data-ttu-id="02a23-132">若要將某個使用者的密碼設為永不過期，請使用 UPN 或使用者的使用者識別碼執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02a23-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="02a23-133">若要將組織中所有使用者的密碼設為永不過期，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02a23-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="02a23-134">根據使用者帳戶屬性，以參數設定的使用者帳戶 `-PasswordPolicies DisablePasswordExpiration` 仍會保留天數 `pwdLastSet` 。</span><span class="sxs-lookup"><span data-stu-id="02a23-134">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="02a23-135">例如，如果您將使用者密碼設為永不到期，但90或更多的天數，密碼仍然會到期。</span><span class="sxs-lookup"><span data-stu-id="02a23-135">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="02a23-136">根據 `pwdLastSet` 使用者帳戶屬性，針對使用參數設定的使用者帳戶 `-PasswordPolicies None` ，所有超過90天的密碼都 `pwdLastSet` 需要使用者在下次登入時變更。這項變更可能會影響大量的使用者。</span><span class="sxs-lookup"><span data-stu-id="02a23-136">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>
