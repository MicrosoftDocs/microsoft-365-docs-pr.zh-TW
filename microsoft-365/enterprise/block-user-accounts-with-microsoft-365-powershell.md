---
title: 使用 PowerShell 封鎖 Microsoft 365 使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: 如何使用 PowerShell 來封鎖和取消封鎖 Microsoft 365 帳戶的存取權。
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754677"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="e951a-103">使用 PowerShell 封鎖 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e951a-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="e951a-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="e951a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e951a-105">當您封鎖 Microsoft 365 帳戶的存取權時，可防止任何人使用該帳戶登入，並存取您 Microsoft 365 組織中的服務和資料。</span><span class="sxs-lookup"><span data-stu-id="e951a-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="e951a-106">您可以使用 PowerShell 來封鎖個別或多個使用者帳戶的存取權。</span><span class="sxs-lookup"><span data-stu-id="e951a-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e951a-107">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="e951a-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e951a-108">首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e951a-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="e951a-109">封鎖個別使用者帳戶的存取</span><span class="sxs-lookup"><span data-stu-id="e951a-109">Block access to individual user accounts</span></span>

<span data-ttu-id="e951a-110">使用下列語法來封鎖個別使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="e951a-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="e951a-111">**Set-AzureAD** 指令程式中的 *-ObjectID* 參數會接受帳戶登入名稱，也稱為使用者主要名稱，或者是帳戶的物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="e951a-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="e951a-112">本範例會封鎖存取 *fabricec@litwareinc.com* 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e951a-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="e951a-113">若要將使用者帳戶解除封鎖，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="e951a-114">若要根據使用者的顯示名稱來顯示使用者帳戶 UPN，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="e951a-115">此範例會顯示使用者  *Caleb sills 帳戶* 的使用者帳戶 UPN。</span><span class="sxs-lookup"><span data-stu-id="e951a-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e951a-116">若要根據使用者的顯示名稱封鎖帳戶，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="e951a-117">若要檢查使用者帳戶的封鎖狀態，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="e951a-118">封鎖多個使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e951a-118">Block multiple user accounts</span></span>

<span data-ttu-id="e951a-119">若要封鎖多個使用者帳戶的存取權，請建立一個文字檔，其中每一行上都包含一個帳戶登入名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e951a-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="e951a-120">在下列命令中，範例文字檔會 *C:\My Documents\Accounts.txt* 中。</span><span class="sxs-lookup"><span data-stu-id="e951a-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="e951a-121">請將此檔案名取代為您的文字檔的路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="e951a-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="e951a-122">若要封鎖對文字檔中所列帳戶的存取，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="e951a-123">若要解除封鎖文字檔中所列的帳戶，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e951a-124">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="e951a-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e951a-125">首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e951a-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="e951a-126">封鎖個別的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e951a-126">Block individual user accounts</span></span>

<span data-ttu-id="e951a-127">使用下列語法來封鎖個別使用者帳戶的存取權：</span><span class="sxs-lookup"><span data-stu-id="e951a-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="e951a-128">PowerShell 核心不支援 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，以及其名稱中具有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e951a-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="e951a-129">您必須從 Windows PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e951a-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="e951a-130">本範例會封鎖存取使用者帳戶 *fabricec \@ litwareinc.com*。</span><span class="sxs-lookup"><span data-stu-id="e951a-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="e951a-131">若要將使用者帳戶解除封鎖，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="e951a-132">若要檢查使用者帳戶的封鎖狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="e951a-133">封鎖多個使用者帳戶的存取權</span><span class="sxs-lookup"><span data-stu-id="e951a-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="e951a-134">首先，建立一個文字檔，其中每一行上都包含一個帳戶，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e951a-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="e951a-135">在下列命令中，範例文字檔會 *C:\My Documents\Accounts.txt* 中。</span><span class="sxs-lookup"><span data-stu-id="e951a-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="e951a-136">請將此檔案名取代為您的文字檔的路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="e951a-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="e951a-137">若要封鎖對文字檔中所列帳戶的存取，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="e951a-138">若要解除封鎖對文字檔中所列帳戶的存取，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e951a-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="e951a-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e951a-139">See also</span></span>

[<span data-ttu-id="e951a-140">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="e951a-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e951a-141">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e951a-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e951a-142">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e951a-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
