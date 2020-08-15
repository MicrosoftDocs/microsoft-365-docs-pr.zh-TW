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
description: 本文說明如何使用 PowerShell 來封鎖和取消封鎖 Microsoft 365 帳戶的存取。
ms.openlocfilehash: a9ade2f41fb601da00ca1c2d1905ca0cb003dcb3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688497"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="26b53-103">使用 PowerShell 封鎖 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="26b53-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="26b53-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="26b53-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="26b53-105">封鎖存取 Microsoft 365 帳戶，可防止任何人使用該帳戶登入，並存取您的 Microsoft 365 組織中的服務和資料。</span><span class="sxs-lookup"><span data-stu-id="26b53-105">Blocking access to a Microsoft 365 account prevents anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="26b53-106">您可以使用 PowerShell 來封鎖個別和多個使用者帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="26b53-106">You can use PowerShell to block access to individual and multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="26b53-107">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b53-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="26b53-108">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="26b53-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="26b53-109">封鎖個別使用者帳戶的存取</span><span class="sxs-lookup"><span data-stu-id="26b53-109">Block access to individual user accounts</span></span>

<span data-ttu-id="26b53-110">使用下列語法來封鎖個別使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="26b53-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="26b53-111">Set-AzureAD 指令程式中的-ObjectID 參數會接受帳戶登入名稱，也稱為使用者主要名稱，或者是帳戶的物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="26b53-111">The -ObjectID parameter in the Set-AzureAD cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span> 
  
<span data-ttu-id="26b53-112">此範例會封鎖對使用者帳戶 fabricec@litwareinc.com 的存取。</span><span class="sxs-lookup"><span data-stu-id="26b53-112">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="26b53-113">若要將使用者帳戶解除封鎖，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="26b53-114">若要根據使用者的顯示名稱來顯示使用者帳戶 UPN，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="26b53-115">此範例會顯示名為 Caleb Sills 帳戶之使用者的使用者帳戶 UPN。</span><span class="sxs-lookup"><span data-stu-id="26b53-115">This example displays the user account UPN for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="26b53-116">若要根據使用者的顯示名稱封鎖帳戶，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="26b53-117">您可以隨時使用下列命令來檢查使用者帳戶的封鎖狀態：</span><span class="sxs-lookup"><span data-stu-id="26b53-117">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="26b53-118">封鎖對多個使用者帳戶的存取</span><span class="sxs-lookup"><span data-stu-id="26b53-118">Block access to multiple user accounts</span></span>

<span data-ttu-id="26b53-119">若要封鎖對多個使用者帳戶的存取，請建立一個文字檔，其中每一行上都包含一個帳戶登入名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="26b53-119">To block access to multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="26b53-120">在下列命令中，範例文字檔會 C:\My Documents\Accounts.txt 中。</span><span class="sxs-lookup"><span data-stu-id="26b53-120">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="26b53-121">以您的文字檔的路徑和檔案名取代。</span><span class="sxs-lookup"><span data-stu-id="26b53-121">Replace this with the path and file name of your text file.</span></span>
  
<span data-ttu-id="26b53-122">若要封鎖對文字檔中所列帳戶的存取，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="26b53-123">若要解除封鎖對文字檔中所列帳戶的存取，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-123">To unblock the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="26b53-124">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="26b53-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="26b53-125">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="26b53-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="26b53-126">封鎖個別使用者帳戶的存取</span><span class="sxs-lookup"><span data-stu-id="26b53-126">Block access to individual user accounts</span></span>

<span data-ttu-id="26b53-127">使用下列語法來封鎖對個別使用者帳戶的存取：</span><span class="sxs-lookup"><span data-stu-id="26b53-127">Use the following syntax to block access to an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="26b53-128">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="26b53-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="26b53-129">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="26b53-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="26b53-130">此範例會封鎖對使用者帳戶 fabricec@litwareinc.com 的存取。</span><span class="sxs-lookup"><span data-stu-id="26b53-130">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="26b53-131">若要將使用者帳戶解除封鎖，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="26b53-132">您可以隨時使用下列命令來檢查使用者帳戶的封鎖狀態：</span><span class="sxs-lookup"><span data-stu-id="26b53-132">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="26b53-133">封鎖對多個使用者帳戶的存取</span><span class="sxs-lookup"><span data-stu-id="26b53-133">Block access to multiple user accounts</span></span>

<span data-ttu-id="26b53-134">首先，建立一個文字檔，其中每一行上都包含一個帳戶，如下所示：</span><span class="sxs-lookup"><span data-stu-id="26b53-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="26b53-135">在下列命令中，範例文字檔會 C:\My Documents\Accounts.txt 中。</span><span class="sxs-lookup"><span data-stu-id="26b53-135">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="26b53-136">以您的文字檔的路徑和檔案名取代。</span><span class="sxs-lookup"><span data-stu-id="26b53-136">Replace this with the path and file name of your text file.</span></span>
    
<span data-ttu-id="26b53-137">若要封鎖對文字檔中所列帳戶的存取，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-137">To block access to the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="26b53-138">若要解除封鎖對文字檔中所列帳戶的存取，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="26b53-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="26b53-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="26b53-139">See also</span></span>

[<span data-ttu-id="26b53-140">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="26b53-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="26b53-141">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26b53-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="26b53-142">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b53-142">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
