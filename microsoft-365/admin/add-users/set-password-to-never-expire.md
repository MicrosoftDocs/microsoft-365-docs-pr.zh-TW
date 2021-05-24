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
ms.openlocfilehash: 12c717d8d625b0135f185b1af131db00e9762c73
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635555"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="b4af8-103">設定個別使用者的密碼永不過期</span><span class="sxs-lookup"><span data-stu-id="b4af8-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="b4af8-104">本文說明如何為個別使用者設定密碼，使其不會過期。</span><span class="sxs-lookup"><span data-stu-id="b4af8-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="b4af8-105">您必須使用 PowerShell 來完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="b4af8-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b4af8-106">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="b4af8-106">Before you begin</span></span>

<span data-ttu-id="b4af8-107">本文適用於為公司、學校或非營利組織設定密碼到期原則的人員。</span><span class="sxs-lookup"><span data-stu-id="b4af8-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="b4af8-108">若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b4af8-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="b4af8-109">[何謂系統管理員帳戶?](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b4af8-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="b4af8-110">您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="b4af8-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="b4af8-111">Microsoft cloud service 的全域系統管理員可以使用 Graph 的[Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) ，設定特定使用者不會到期的密碼。</span><span class="sxs-lookup"><span data-stu-id="b4af8-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="b4af8-112">您也可以使用 [AzureAD](/powershell/module/Azuread) Cmdlet 來移除永不過期的設定，或查看哪些使用者密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="b4af8-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="b4af8-113">本指南適用于其他提供者，例如 Intune 和 Microsoft 365，也取決於 Azure AD 的身分識別和目錄服務。</span><span class="sxs-lookup"><span data-stu-id="b4af8-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="b4af8-114">[密碼到期] 是原則中唯一可以變更的部分。</span><span class="sxs-lookup"><span data-stu-id="b4af8-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="b4af8-115">只有未透過目錄同步處理同步處理的使用者帳戶密碼才能設定為不會過期。</span><span class="sxs-lookup"><span data-stu-id="b4af8-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="b4af8-116">如需目錄同步處理的詳細資訊，請參閱[連線 AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="b4af8-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="b4af8-117">如何檢查密碼的到期原則</span><span class="sxs-lookup"><span data-stu-id="b4af8-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="b4af8-118">如需 AzureAD 模組中 Get-AzureADUser 命令的詳細資訊，請參閱參考文章 [AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。</span><span class="sxs-lookup"><span data-stu-id="b4af8-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="b4af8-119">執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="b4af8-119">Run one of the following commands:</span></span>

- <span data-ttu-id="b4af8-120">若要查看單一使用者的密碼是否設為永不過期，請使用 UPN (執行下列 Cmdlet，例如， *user@contoso.onmicrosoft.com*) 或您要檢查之使用者的使用者識別碼：</span><span class="sxs-lookup"><span data-stu-id="b4af8-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="b4af8-121">範例：</span><span class="sxs-lookup"><span data-stu-id="b4af8-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="b4af8-122">若要查看所有使用者的 [ **密碼永不到期** ] 設定，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b4af8-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="b4af8-123">若要在目前使用者名稱為 **ReportPasswordNeverExpires.html** 之電腦上的 Html 中取得所有具有 PasswordNeverExpires 的使用者報告</span><span class="sxs-lookup"><span data-stu-id="b4af8-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="b4af8-124">若要在目前使用者名稱為 **ReportPasswordNeverExpires.csv** 的電腦上，取得 CSV 中具有 PasswordNeverExpires 的所有使用者報告</span><span class="sxs-lookup"><span data-stu-id="b4af8-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="b4af8-125">若要將組織中所有使用者的密碼設為永不過期，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b4af8-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="b4af8-126">設定參數的使用者帳戶 `-PasswordPolicies DisablePasswordExpiration` 仍會以屬性為基礎 `pwdLastSet` 。</span><span class="sxs-lookup"><span data-stu-id="b4af8-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="b4af8-127">根據 `pwdLastSet` 屬性，如果您變更到期 `-PasswordPolicies None` ，所有 pwdLastSet 超過90天的密碼都需要使用者在下次登入時進行變更。</span><span class="sxs-lookup"><span data-stu-id="b4af8-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="b4af8-128">這項變更可能會影響大量的使用者。</span><span class="sxs-lookup"><span data-stu-id="b4af8-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="b4af8-129">設定密碼為到期</span><span class="sxs-lookup"><span data-stu-id="b4af8-129">Set a password to expire</span></span>

<span data-ttu-id="b4af8-130">執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="b4af8-130">Run one of the following commands:</span></span>

- <span data-ttu-id="b4af8-131">若要設定一個使用者的密碼，使密碼到期，請使用 UPN 或使用者的使用者識別碼執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b4af8-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="b4af8-132">若要設定組織中所有使用者的密碼，使其到期，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b4af8-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="b4af8-133">相關內容</span><span class="sxs-lookup"><span data-stu-id="b4af8-133">Related content</span></span>

<span data-ttu-id="b4af8-134">[讓使用者重設自己的密碼](../add-users/let-users-reset-passwords.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="b4af8-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="b4af8-135"> (篇文章) 中[重設密碼](../add-users/reset-passwords.md)</span><span class="sxs-lookup"><span data-stu-id="b4af8-135">[Reset passwords](../add-users/reset-passwords.md) (article)\</span></span>
<span data-ttu-id="b4af8-136">[為您的組織設定密碼到期原則](../manage/set-password-expiration-policy.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="b4af8-136">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>