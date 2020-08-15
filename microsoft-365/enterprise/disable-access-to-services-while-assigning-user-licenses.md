---
title: 在指派使用者授權時停用 Microsoft 365 服務的存取權
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: 瞭解如何使用 Microsoft 365 的 PowerShell，將授權指派給使用者帳戶並同時停用特定服務方案。
ms.openlocfilehash: b027c805638284a78d4e49f4c65518be02e60392
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688476"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="f51ab-103">在指派使用者授權時停用 Microsoft 365 服務的存取權</span><span class="sxs-lookup"><span data-stu-id="f51ab-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="f51ab-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="f51ab-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f51ab-105">Microsoft 365 訂閱隨附個別服務的服務方案。</span><span class="sxs-lookup"><span data-stu-id="f51ab-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="f51ab-106">Microsoft 365 系統管理員經常需要在指派授權給使用者時停用特定的計畫。</span><span class="sxs-lookup"><span data-stu-id="f51ab-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="f51ab-107">透過本文中的指示，您可以在使用個別使用者帳戶或多個使用者帳戶的 PowerShell 停用特定的服務方案時，指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="f51ab-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f51ab-108">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="f51ab-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f51ab-109">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="f51ab-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="f51ab-110">接下來，使用此命令列出租使用者的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="f51ab-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="f51ab-111">接下來，取得您想要新增授權的帳戶登入名稱，也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="f51ab-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="f51ab-112">接下來，編譯要啟用的服務清單。</span><span class="sxs-lookup"><span data-stu-id="f51ab-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="f51ab-113">如需授權方案的完整清單 (也稱為產品名稱) 、其包含的服務方案及其對應的易記名稱，請參閱 [產品名稱和服務方案識別碼取得授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="f51ab-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="f51ab-114">在下列命令區塊中，填入使用者帳戶的使用者主要名稱、SKU 元件編號，以及要啟用及移除解說文字和字元的服務方案清單 \< and > 。</span><span class="sxs-lookup"><span data-stu-id="f51ab-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="f51ab-115">然後，在 PowerShell 命令提示字元中執行產生的命令。</span><span class="sxs-lookup"><span data-stu-id="f51ab-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f51ab-116">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="f51ab-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f51ab-117">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f51ab-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="f51ab-118">接下來，執行下列命令以查看您目前的訂閱：</span><span class="sxs-lookup"><span data-stu-id="f51ab-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="f51ab-119">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f51ab-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f51ab-120">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="f51ab-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="f51ab-121">在 [顯示]  `Get-MsolAccountSku` 命令中：</span><span class="sxs-lookup"><span data-stu-id="f51ab-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="f51ab-122">**AccountSkuId** 為您組織的訂閱 \<OrganizationName> ： \<Subscription> format。</span><span class="sxs-lookup"><span data-stu-id="f51ab-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="f51ab-123">是您在 \<OrganizationName> Microsoft 365 中註冊時所提供的值，且對您的組織而言是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f51ab-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="f51ab-124">\<Subscription>值是針對特定訂閱。</span><span class="sxs-lookup"><span data-stu-id="f51ab-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="f51ab-125">例如，針對 litwareinc:ENTERPRISEPACK，組織名稱是 litwareinc，訂閱名稱是 ENTERPRISEPACK (Office 365 Enterprise E3) 。</span><span class="sxs-lookup"><span data-stu-id="f51ab-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="f51ab-126">**ActiveUnits** 為您為訂閱購買的授權數目。</span><span class="sxs-lookup"><span data-stu-id="f51ab-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="f51ab-127">**WarningUnits** 是尚未更新之訂閱中的授權數目，在30天的寬限期後會到期。</span><span class="sxs-lookup"><span data-stu-id="f51ab-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="f51ab-128">**ConsumedUnits** 是您為訂閱指派給使用者的授權數目。</span><span class="sxs-lookup"><span data-stu-id="f51ab-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="f51ab-129">請注意包含您要授權之使用者的 Microsoft 365 訂閱 AccountSkuId。</span><span class="sxs-lookup"><span data-stu-id="f51ab-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="f51ab-130">此外，請確定有足夠的授權，可從**ActiveUnits** ) 指派 (減去**ConsumedUnits** 。</span><span class="sxs-lookup"><span data-stu-id="f51ab-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="f51ab-131">接下來，執行此命令，以查看您所有訂閱中可用之 Microsoft 365 服務方案的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="f51ab-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="f51ab-132">在此命令顯示時，決定當您指派授權給使用者時，您想要停用的服務方案。</span><span class="sxs-lookup"><span data-stu-id="f51ab-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="f51ab-133">以下是服務方案及其對應的 Microsoft 365 服務的部分清單。</span><span class="sxs-lookup"><span data-stu-id="f51ab-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="f51ab-134">下表顯示 Microsoft 365 服務方案及其最常見服務的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="f51ab-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="f51ab-135">您的服務方案清單可能不同。</span><span class="sxs-lookup"><span data-stu-id="f51ab-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="f51ab-136">**服務計劃**</span><span class="sxs-lookup"><span data-stu-id="f51ab-136">**Service plan**</span></span>|<span data-ttu-id="f51ab-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="f51ab-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="f51ab-138">Sway</span><span class="sxs-lookup"><span data-stu-id="f51ab-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="f51ab-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f51ab-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="f51ab-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="f51ab-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="f51ab-141">Azure 版權管理 (RMS)</span><span class="sxs-lookup"><span data-stu-id="f51ab-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="f51ab-142">*先前命名為 Office 365 ProPlus*的 Microsoft 365 應用程式 enterprise () </span><span class="sxs-lookup"><span data-stu-id="f51ab-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="f51ab-143">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="f51ab-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="f51ab-144">辦公室</span><span class="sxs-lookup"><span data-stu-id="f51ab-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="f51ab-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f51ab-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="f51ab-146">Exchange Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="f51ab-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="f51ab-147">如需授權方案的完整清單 (也稱為產品名稱) 、其包含的服務方案及其對應的易記名稱，請參閱 [產品名稱和服務方案識別碼取得授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="f51ab-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="f51ab-148">現在，您已具備要停用的 AccountSkuId 和服務方案，您可以將授權指派給個別使用者或多位使用者。</span><span class="sxs-lookup"><span data-stu-id="f51ab-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="f51ab-149">針對單一使用者</span><span class="sxs-lookup"><span data-stu-id="f51ab-149">For a single user</span></span>

<span data-ttu-id="f51ab-150">若為單一使用者，請填入使用者帳戶的使用者主要名稱、AccountSkuId，以及要停用的服務方案清單，並移除解說文字和 \< and > 字元。</span><span class="sxs-lookup"><span data-stu-id="f51ab-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="f51ab-151">然後，在 PowerShell 命令提示字元中執行產生的命令。</span><span class="sxs-lookup"><span data-stu-id="f51ab-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="f51ab-152">以下是名為 belindan@contoso.com 之帳戶的範例命令區塊，供 contoso:ENTERPRISEPACK 授權使用，且要停用的服務方案 RMS_S_ENTERPRISE、SWAY、INTUNE_O365 和 YAMMER_ENTERPRISE：</span><span class="sxs-lookup"><span data-stu-id="f51ab-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="f51ab-153">針對多個使用者</span><span class="sxs-lookup"><span data-stu-id="f51ab-153">For multiple users</span></span>

<span data-ttu-id="f51ab-154">若要對多位使用者執行這項管理工作，請建立一個以逗號分隔的值 (包含 UserPrincipalName 和 UsageLocation 欄位的 CSV) 文字檔。</span><span class="sxs-lookup"><span data-stu-id="f51ab-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="f51ab-155">範例如下：</span><span class="sxs-lookup"><span data-stu-id="f51ab-155">Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="f51ab-156">接下來，填入輸入和輸出 CSV 檔案的位置、帳戶 SKU 識別碼，以及要停用的服務方案清單，然後在 PowerShell 命令提示字元中執行產生的命令。</span><span class="sxs-lookup"><span data-stu-id="f51ab-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

<span data-ttu-id="f51ab-157">此 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="f51ab-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="f51ab-158">顯示每位使用者的使用者主要名稱。</span><span class="sxs-lookup"><span data-stu-id="f51ab-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="f51ab-159">將自訂的授權指派給每個使用者。</span><span class="sxs-lookup"><span data-stu-id="f51ab-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="f51ab-160">會建立 CSV 檔案，其中包含所有已處理的使用者，並顯示其授權狀態。</span><span class="sxs-lookup"><span data-stu-id="f51ab-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f51ab-161">請參閱</span><span class="sxs-lookup"><span data-stu-id="f51ab-161">See also</span></span>

[<span data-ttu-id="f51ab-162">使用 PowerShell 停用 Microsoft 365 服務的存取權</span><span class="sxs-lookup"><span data-stu-id="f51ab-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f51ab-163">使用 PowerShell 停用 Sway 的存取權</span><span class="sxs-lookup"><span data-stu-id="f51ab-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f51ab-164">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="f51ab-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f51ab-165">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f51ab-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
