---
title: 使用 PowerShell 刪除 Microsoft 365 使用者帳戶
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: 在本文中，您將瞭解如何在 PowerShell 中使用不同的模組，以刪除 Microsoft 365 使用者帳戶。
ms.openlocfilehash: 6da2d83b3f305db09f8c1d02f54e643a0ad1978b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688622"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="ad796-103">使用 PowerShell 刪除 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ad796-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="ad796-104">您可以使用 Microsoft 365 的 PowerShell 刪除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ad796-104">You can use PowerShell for Microsoft 365 to delete a user account.</span></span>
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ad796-105">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad796-105">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ad796-106">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="ad796-106">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="ad796-107">連接之後，使用下列語法來移除個別使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="ad796-107">After you have connected, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="ad796-108">此範例會移除使用者帳戶 fabricec@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ad796-108">This example removes the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="ad796-109">**AzureADUser 指令程式**中的 **-ObjectID**參數會接受帳戶的登入名稱，也稱為使用者主要名稱，或帳戶的物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="ad796-109">The **-ObjectID** parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="ad796-110">若要根據使用者的名稱顯示帳戶名稱，請使用下列命令︰</span><span class="sxs-lookup"><span data-stu-id="ad796-110">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ad796-111">本範例針對名為 Caleb Sills 的使用者顯示帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="ad796-111">This example displays the account name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ad796-112">若要根據使用者的顯示名稱移除帳戶，請使用下列命令︰</span><span class="sxs-lookup"><span data-stu-id="ad796-112">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ad796-113">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="ad796-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ad796-p101">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組來刪除使用者帳戶時，該帳戶並不會永久刪除。您可以在 30 天內還原已刪除的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ad796-p101">When you delete a user account with the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted. You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="ad796-116">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ad796-116">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="ad796-117">若要刪除使用者帳戶，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad796-117">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="ad796-118">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad796-118">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="ad796-119">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="ad796-119">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="ad796-120">此範例會刪除使用者帳戶 BelindaN@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ad796-120">This example deletes the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="ad796-121">若要在 30 天的寬限期內還原已刪除的使用者帳戶，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad796-121">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="ad796-122">此範例會還原已刪除的帳戶 BelindaN@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ad796-122">This example restores the deleted account BelindaN@litwareinc.com.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 <span data-ttu-id="ad796-123">**附註：**</span><span class="sxs-lookup"><span data-stu-id="ad796-123">**Notes:**</span></span>
  
- <span data-ttu-id="ad796-124">若要查看可以還原的已刪除使用者清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ad796-124">To see the list of deleted users that can be restored, run the following command:</span></span>
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- <span data-ttu-id="ad796-125">如果使用者帳戶的原始使用者主要名稱被另一個帳戶使用，當您還原使用者帳戶時，請使用 _NewUserPrincipalName_ 參數 (而不是 _UserPrincipalName_) 來指定不同的使用者主要名稱。</span><span class="sxs-lookup"><span data-stu-id="ad796-125">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="ad796-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ad796-126">See also</span></span>

[<span data-ttu-id="ad796-127">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="ad796-127">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ad796-128">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad796-128">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ad796-129">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad796-129">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
