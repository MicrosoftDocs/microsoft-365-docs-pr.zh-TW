---
title: 使用 PowerShell 刪除 Microsoft 365 使用者帳戶
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
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: 瞭解如何在 PowerShell 中使用不同的模組，以刪除 Microsoft 365 使用者帳戶。
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754537"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="4bfd7-103">使用 PowerShell 刪除 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="4bfd7-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="4bfd7-104">您可以使用 Microsoft 365 的 PowerShell 來刪除及還原使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="4bfd7-105">瞭解如何使用 Microsoft 365 系統管理中心 [還原使用者帳戶](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) 。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-105">Learn how to [restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="4bfd7-106">如需其他資源的清單，請參閱 [管理使用者和群組](https://docs.microsoft.com/microsoft-365/admin/add-users/)。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4bfd7-107">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bfd7-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4bfd7-108">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="4bfd7-109">連接後，請使用下列語法來移除個別使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="4bfd7-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="4bfd7-110">此範例會移除使用者帳戶 *fabricec \@ litwareinc.com*。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="4bfd7-111">**AzureADUser** Cmdlet 中的 *-ObjectID*參數會接受帳戶的登入名稱，也稱為使用者主要名稱或帳戶的物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="4bfd7-112">若要根據使用者的名稱顯示帳戶名稱，請使用下列命令︰</span><span class="sxs-lookup"><span data-stu-id="4bfd7-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4bfd7-113">本範例會顯示使用者 *Caleb sills 帳戶*的帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4bfd7-114">若要根據使用者的顯示名稱移除帳戶，請使用下列命令︰</span><span class="sxs-lookup"><span data-stu-id="4bfd7-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4bfd7-115">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4bfd7-116">當您透過 Microsoft Azure Active Directory Module for Windows PowerShell 刪除使用者帳戶時，系統不會永久刪除該帳戶。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="4bfd7-117">您可以在 30 天內還原已刪除的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="4bfd7-118">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="4bfd7-119">若要刪除使用者帳戶，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="4bfd7-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="4bfd7-120">PowerShell 核心不支援 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，以及其名稱中含有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="4bfd7-121">從 Windows PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="4bfd7-122">本範例會刪除 *BelindaN@litwareinc.com*的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="4bfd7-123">若要在 30 天的寬限期內還原已刪除的使用者帳戶，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="4bfd7-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="4bfd7-124">本範例會還原刪除的帳戶 *BelindaN \@ litwareinc.com*。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="4bfd7-125">若要查看可以還原的已刪除使用者清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4bfd7-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="4bfd7-126">如果使用者帳戶的原始使用者主要名稱被另一個帳戶使用，當您還原使用者帳戶時，請使用 _NewUserPrincipalName_ 參數 (而不是 _UserPrincipalName_) 來指定不同的使用者主要名稱。</span><span class="sxs-lookup"><span data-stu-id="4bfd7-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="4bfd7-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4bfd7-127">See also</span></span>

[<span data-ttu-id="4bfd7-128">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="4bfd7-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4bfd7-129">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4bfd7-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4bfd7-130">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bfd7-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
