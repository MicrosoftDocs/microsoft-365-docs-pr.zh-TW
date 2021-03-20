---
title: 使用 PowerShell 將 Microsoft 365 授權指派給使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905461"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="7b394-103">使用 PowerShell 將 Microsoft 365 授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7b394-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="7b394-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="7b394-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7b394-105">使用者必須先將授權方案的授權指派給他們的帳戶，才可使用任何 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="7b394-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="7b394-106">您可以使用 PowerShell 快速將授權指派給未授權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7b394-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="7b394-107">使用者帳戶必須先指派位置。</span><span class="sxs-lookup"><span data-stu-id="7b394-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="7b394-108">若要在 [Microsoft 365 系統管理中心](../admin/add-users/add-users.md)中建立新的使用者帳戶，必須指定位置。</span><span class="sxs-lookup"><span data-stu-id="7b394-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="7b394-109">從您的內部部署 Active Directory 網域服務同步處理的帳戶預設不會有指定的位置。</span><span class="sxs-lookup"><span data-stu-id="7b394-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="7b394-110">您可以從下列位置設定這些帳戶的位置：</span><span class="sxs-lookup"><span data-stu-id="7b394-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="7b394-111">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="7b394-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="7b394-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b394-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="7b394-113">[Azure 入口網站](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory**  >  **使用者**> 使用者帳戶 >**設定檔**  >  **連絡人資訊**  > ) 的 **國家或地區**。</span><span class="sxs-lookup"><span data-stu-id="7b394-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="7b394-114">瞭解如何使用 Microsoft 365 系統管理中心[指派授權給使用者帳戶](../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="7b394-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="7b394-115">如需其他資源的清單，請參閱 [管理使用者和群組](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="7b394-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="7b394-116">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b394-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="7b394-117">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="7b394-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="7b394-118">接下來，使用此命令列出租使用者的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="7b394-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="7b394-119">接下來，取得您想要新增授權的帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="7b394-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="7b394-120">接下來，確定使用者帳戶已指派使用位置。</span><span class="sxs-lookup"><span data-stu-id="7b394-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="7b394-121">若未指派任何使用位置，您可以使用下列命令指派其中一個：</span><span class="sxs-lookup"><span data-stu-id="7b394-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="7b394-122">最後，指定使用者登入名稱和授權方案名稱，並執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="7b394-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="7b394-123">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="7b394-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="7b394-124">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7b394-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="7b394-125">執行 `Get-MsolAccountSku` 命令，以查看組織中每個計畫可用的授權方案和可用的授權數目。</span><span class="sxs-lookup"><span data-stu-id="7b394-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="7b394-126">每個計畫中可用的授權數目 **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**。</span><span class="sxs-lookup"><span data-stu-id="7b394-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="7b394-127">如需授權方案、授權及服務的詳細資訊，請參閱 [使用 PowerShell 查看授權和服務](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="7b394-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="7b394-128">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b394-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="7b394-129">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="7b394-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="7b394-130">若要尋找組織中未授權的帳戶，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="7b394-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="7b394-131">您只能將授權指派給 **UsageLocation** 屬性設定為有效的 ISO 3166-1 Alpha-2 國家碼的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7b394-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="7b394-132">例如，US 代表美國、FR 代表法國。</span><span class="sxs-lookup"><span data-stu-id="7b394-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="7b394-133">某些國家/地區未提供某些 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="7b394-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="7b394-134">如需詳細資訊，請參閱 [關於授許可權制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。</span><span class="sxs-lookup"><span data-stu-id="7b394-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="7b394-135">若要尋找沒有 **UsageLocation** 值的帳戶，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="7b394-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="7b394-136">若要設定帳戶的 **UsageLocation** 值，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7b394-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="7b394-137">例如：</span><span class="sxs-lookup"><span data-stu-id="7b394-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="7b394-138">如果您使用 **Get-MsolUser** Cmdlet，而不使用 **-All** 參數，則只會傳回前 500 個帳戶。</span><span class="sxs-lookup"><span data-stu-id="7b394-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="7b394-139">指派授權給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7b394-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="7b394-140">若要將授權指派給使用者，請在 PowerShell 中使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="7b394-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="7b394-141">此範例會將 **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) 授權方案的授權指派給未授權的使用者 **belindan \@ litwareinc.com**：</span><span class="sxs-lookup"><span data-stu-id="7b394-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="7b394-142">若要將授權指派給所有未授權的使用者，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="7b394-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="7b394-143">您無法將多個授權指派給使用者，請使用相同的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="7b394-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="7b394-144">如果您沒有足夠的可用授權，授權會依照 **Get-MsolUser** Cmdlet 所傳回的順序指派給使用者，直到可用的授權執行完畢為止。</span><span class="sxs-lookup"><span data-stu-id="7b394-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="7b394-145">此範例會將 Office 365 Enterprise E3) 授權計畫中 **litwareinc:ENTERPRISEPACK** (的授權指派給所有未授權的使用者：</span><span class="sxs-lookup"><span data-stu-id="7b394-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="7b394-146">本範例會將相同授權指派給美國的銷售部門中未授權的使用者：</span><span class="sxs-lookup"><span data-stu-id="7b394-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="7b394-147">使用適用于 Graph 模組的 Azure Active Directory PowerShell，將使用者移至不同訂閱 (授權方案) </span><span class="sxs-lookup"><span data-stu-id="7b394-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="7b394-148">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="7b394-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="7b394-149">接下來，取得您要切換訂閱的使用者帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="7b394-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="7b394-150">接下來，使用此命令列出租使用者 (授權方案) 的訂閱。</span><span class="sxs-lookup"><span data-stu-id="7b394-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="7b394-151">接下來，列出使用者帳戶目前具有這些命令的訂閱。</span><span class="sxs-lookup"><span data-stu-id="7b394-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="7b394-152">識別使用者目前已 (FROM 訂閱) 和使用者移至其中的訂閱 (TO 訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="7b394-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="7b394-153">最後，指定 TO 及 FROM 訂閱名稱 (SKU 部分編號) 並執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="7b394-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="7b394-154">您可以使用下列命令來確認使用者帳戶的訂閱變更。</span><span class="sxs-lookup"><span data-stu-id="7b394-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="7b394-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b394-155">See also</span></span>

[<span data-ttu-id="7b394-156">以 PowerShell 管理使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="7b394-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7b394-157">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b394-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7b394-158">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b394-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)