---
title: 使用 PowerShell 將 Microsoft 365 授權指派給使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: 在本文中，您將瞭解如何使用 PowerShell 將 Microsoft 365 授權指派給未授權的使用者。
ms.openlocfilehash: 7bd217dfeed762a11161c3f512fb55a8e6c4968e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688299"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="2215e-103">使用 PowerShell 將 Microsoft 365 授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="2215e-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="2215e-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="2215e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2215e-105">使用者必須先將授權方案的授權指派給他們的帳戶，才可使用任何 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="2215e-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="2215e-106">您可以使用 PowerShell 快速將授權指派給未授權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2215e-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

>[!Note]
><span data-ttu-id="2215e-107">必須為使用者帳戶指派位置。</span><span class="sxs-lookup"><span data-stu-id="2215e-107">User accounts must be assigned a location.</span></span> <span data-ttu-id="2215e-108">您可以從 Microsoft 365 系統管理中心的使用者帳戶屬性或從 PowerShell 執行此動作。</span><span class="sxs-lookup"><span data-stu-id="2215e-108">You can do this from the properties of a user account in the Microsoft 365 admin center or from PowerShell.</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2215e-109">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="2215e-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2215e-110">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="2215e-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="2215e-111">接下來，使用此命令列出租使用者的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="2215e-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="2215e-112">接下來，取得您想要新增授權的帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="2215e-112">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="2215e-113">接下來，確定使用者帳戶已指派使用位置。</span><span class="sxs-lookup"><span data-stu-id="2215e-113">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="2215e-114">若未指派任何使用位置，您可以使用下列命令指派其中一個：</span><span class="sxs-lookup"><span data-stu-id="2215e-114">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="2215e-115">最後，指定使用者登入名稱和授權方案名稱，並執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="2215e-115">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="2215e-116">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="2215e-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="2215e-117">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2215e-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="2215e-118">執行 `Get-MsolAccountSku` 命令，以查看組織中每個計畫可用的授權方案和可用的授權數目。</span><span class="sxs-lookup"><span data-stu-id="2215e-118">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="2215e-119">每個計畫中可用的授權數目**ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**。</span><span class="sxs-lookup"><span data-stu-id="2215e-119">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="2215e-120">如需授權方案、授權及服務的詳細資訊，請參閱 [使用 PowerShell 查看授權和服務](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="2215e-120">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="2215e-121">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2215e-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="2215e-122">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="2215e-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="2215e-123">若要尋找組織中未授權的帳戶，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="2215e-123">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="2215e-124">您只能將授權指派給 **UsageLocation** 屬性設定為有效的 ISO 3166-1 Alpha-2 國家碼的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2215e-124">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="2215e-125">例如，US 代表美國、FR 代表法國。</span><span class="sxs-lookup"><span data-stu-id="2215e-125">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="2215e-126">某些國家/地區未提供某些 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="2215e-126">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="2215e-127">如需詳細資訊，請參閱 [關於授許可權制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。</span><span class="sxs-lookup"><span data-stu-id="2215e-127">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="2215e-128">若要尋找沒有 **UsageLocation** 值的帳戶，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="2215e-128">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="2215e-129">若要設定帳戶的 **UsageLocation** 值，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="2215e-129">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="2215e-130">例如：</span><span class="sxs-lookup"><span data-stu-id="2215e-130">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="2215e-131">如果您使用 **Get-MsolUser** Cmdlet，而不使用 **-All**參數，則只會傳回前 500 個帳戶。</span><span class="sxs-lookup"><span data-stu-id="2215e-131">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="2215e-132">指派授權給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="2215e-132">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="2215e-133">若要將授權指派給使用者，請在 PowerShell 中使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="2215e-133">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="2215e-134">此範例會將 **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) 授權方案的授權指派給未授權的使用者 **belindan \@ litwareinc.com**：</span><span class="sxs-lookup"><span data-stu-id="2215e-134">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="2215e-135">若要將授權指派給所有未授權的使用者，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="2215e-135">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="2215e-136">您無法將多個授權指派給使用者，請使用相同的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="2215e-136">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="2215e-137">如果您沒有足夠的可用授權，授權會依照 **Get-MsolUser** Cmdlet 所傳回的順序指派給使用者，直到可用的授權執行完畢為止。</span><span class="sxs-lookup"><span data-stu-id="2215e-137">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="2215e-138">此範例會將 Office 365 Enterprise E3) 授權計畫中 **litwareinc:ENTERPRISEPACK** (的授權指派給所有未授權的使用者：</span><span class="sxs-lookup"><span data-stu-id="2215e-138">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="2215e-139">本範例會將相同授權指派給美國的銷售部門中未授權的使用者：</span><span class="sxs-lookup"><span data-stu-id="2215e-139">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2215e-140">使用適用于 Graph 模組的 Azure Active Directory PowerShell，將使用者移至不同訂閱 (授權方案) </span><span class="sxs-lookup"><span data-stu-id="2215e-140">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2215e-141">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="2215e-141">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="2215e-142">接下來，取得您要切換訂閱的使用者帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="2215e-142">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="2215e-143">接下來，使用此命令列出租使用者 (授權方案) 的訂閱。</span><span class="sxs-lookup"><span data-stu-id="2215e-143">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="2215e-144">接下來，列出使用者帳戶目前具有這些命令的訂閱。</span><span class="sxs-lookup"><span data-stu-id="2215e-144">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="2215e-145">識別使用者目前已 (FROM 訂閱) 和使用者移至其中的訂閱 (TO 訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="2215e-145">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="2215e-146">最後，指定 TO 及 FROM 訂閱名稱 (SKU 部分編號) 並執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="2215e-146">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="2215e-147">您可以使用下列命令來確認使用者帳戶的訂閱變更。</span><span class="sxs-lookup"><span data-stu-id="2215e-147">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="2215e-148">請參閱</span><span class="sxs-lookup"><span data-stu-id="2215e-148">See also</span></span>

[<span data-ttu-id="2215e-149">使用 PowerShell 管理使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="2215e-149">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2215e-150">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2215e-150">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2215e-151">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2215e-151">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
