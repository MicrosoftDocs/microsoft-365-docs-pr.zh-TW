---
title: 使用 PowerShell 移除使用者帳戶中的 Microsoft 365 授權
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: 說明如何使用 PowerShell 來移除先前指派給使用者的 Microsoft 365 授權。
ms.openlocfilehash: 815b2290ca3b5ac4ee3cfec87383161ea70f3dca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688340"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="da55b-103">使用 PowerShell 移除使用者帳戶中的 Microsoft 365 授權</span><span class="sxs-lookup"><span data-stu-id="da55b-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="da55b-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="da55b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="da55b-105">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="da55b-105">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="da55b-106">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="da55b-106">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="da55b-107">接下來，使用此命令列出租使用者的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="da55b-107">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="da55b-108">接下來，取得您要移除授權的帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="da55b-108">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="da55b-109">最後，指定使用者登入和授權方案名稱、移除「<」和「>」字元，然後執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="da55b-109">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="da55b-110">若要移除特定使用者帳戶的所有授權，請指定使用者登入名稱、移除「<」和「>」字元，然後執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="da55b-110">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="da55b-111">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="da55b-111">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="da55b-112">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="da55b-112">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="da55b-113">若要查看授權方案 (**AccountSkuID** 組織中的) 資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="da55b-113">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="da55b-114">使用 PowerShell 來查看授權和服務</span><span class="sxs-lookup"><span data-stu-id="da55b-114">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="da55b-115">使用 PowerShell 來查看帳戶授權與服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="da55b-115">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="da55b-116">如果您使用 **Get-MsolUser** Cmdlet，而不使用 _-All_參數，則只會傳回前 500 個帳戶。</span><span class="sxs-lookup"><span data-stu-id="da55b-116">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="da55b-117">移除使用者帳戶中的授權</span><span class="sxs-lookup"><span data-stu-id="da55b-117">Removing licenses from user accounts</span></span>

<span data-ttu-id="da55b-118">若要從現有的使用者帳戶中移除授權，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="da55b-118">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="da55b-119">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da55b-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="da55b-120">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="da55b-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="da55b-121">本範例會從使用者帳戶 BelindaN@litwareinc.com 中移除 (Office 365 Enterprise E3) 授權的 **litwareinc:ENTERPRISEPACK** 。</span><span class="sxs-lookup"><span data-stu-id="da55b-121">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="da55b-122">您無法使用 `Set-MsolUserLicense` Cmdlet 將使用者取消指派為 *取消* 的授權。</span><span class="sxs-lookup"><span data-stu-id="da55b-122">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="da55b-123">您必須為 Microsoft 365 系統管理中心中的每個使用者帳戶個別執行此動作。</span><span class="sxs-lookup"><span data-stu-id="da55b-123">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="da55b-124">若要從現有授權使用者的群組中移除所有授權，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="da55b-124">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="da55b-125">根據**現有的帳戶屬性來篩選帳戶**若要這麼做，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="da55b-125">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="da55b-126">這則範例會移除美國的銷售部門中所有使用者帳戶的所有授權。</span><span class="sxs-lookup"><span data-stu-id="da55b-126">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="da55b-127">**針對特定授權使用特定帳戶的清單** 若要這麼做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="da55b-127">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="da55b-128">在每一行上建立及儲存包含一個帳戶的文字檔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da55b-128">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="da55b-129">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="da55b-129">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="da55b-130">本範例會從文字檔 C:\My Documents\Accounts.txt 中所定義的使用者帳戶移除 **litwareinc:ENTERPRISEPACK** (Office 365 企業版 E3) 授權。</span><span class="sxs-lookup"><span data-stu-id="da55b-130">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="da55b-131">若要從所有現有的使用者帳戶中移除所有授權，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="da55b-131">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="da55b-132">若要釋放授權，另一種方法是刪除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="da55b-132">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="da55b-133">如需詳細資訊，請參閱 [使用 PowerShell 刪除及還原使用者帳戶](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="da55b-133">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da55b-134">請參閱</span><span class="sxs-lookup"><span data-stu-id="da55b-134">See also</span></span>

[<span data-ttu-id="da55b-135">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="da55b-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da55b-136">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da55b-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da55b-137">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="da55b-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
