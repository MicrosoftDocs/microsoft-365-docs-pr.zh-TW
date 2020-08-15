---
title: 使用 PowerShell 來查看 Microsoft 365 帳戶授權與服務詳細資料
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
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: 說明如何使用 PowerShell 來判斷已指派給使用者的 Microsoft 365 服務。
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688847"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="5bd66-103">使用 PowerShell 來查看 Microsoft 365 帳戶授權與服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="5bd66-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="5bd66-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="5bd66-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5bd66-105">在 Microsoft 365 中，授權計畫中的授權 (也稱為 SKUs 或 Microsoft 365 方案) 讓使用者能夠存取為這些計畫定義的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="5bd66-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="5bd66-106">不過，使用者可能無法存取目前指派給他們的授權中可用的所有服務。</span><span class="sxs-lookup"><span data-stu-id="5bd66-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="5bd66-107">您可以使用 Microsoft 365 的 PowerShell，以查看使用者帳戶上的服務狀態。</span><span class="sxs-lookup"><span data-stu-id="5bd66-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="5bd66-108">如需授權方案、授權及服務的詳細資訊，請參閱 [使用 PowerShell 查看授權和服務](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd66-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5bd66-109">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bd66-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5bd66-110">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="5bd66-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="5bd66-111">接下來，使用此命令列出租使用者的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="5bd66-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="5bd66-112">使用這些命令，列出每個授權方案中可用的服務。</span><span class="sxs-lookup"><span data-stu-id="5bd66-112">Use these commands to list the services that are available in each licensing plan.</span></span>

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

<span data-ttu-id="5bd66-113">使用這些命令列出指派給使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="5bd66-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5bd66-114">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="5bd66-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5bd66-115">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5bd66-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="5bd66-116">接下來，執行此命令，列出您組織中可用的授權計畫。</span><span class="sxs-lookup"><span data-stu-id="5bd66-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="5bd66-117">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5bd66-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5bd66-118">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="5bd66-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="5bd66-119">接下來，執行此命令以列出每個授權方案中可用的服務，以及這些服務的列出順序 (索引編號) 中。</span><span class="sxs-lookup"><span data-stu-id="5bd66-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="5bd66-120">使用此命令來列出指派給使用者的授權，以及列出 (索引編號) 中的順序。</span><span class="sxs-lookup"><span data-stu-id="5bd66-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="5bd66-121">若要為使用者帳戶查看服務</span><span class="sxs-lookup"><span data-stu-id="5bd66-121">To view services for a user account</span></span>

<span data-ttu-id="5bd66-122">若要查看使用者有權存取的所有 Microsoft 365 服務，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="5bd66-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="5bd66-123">此範例會顯示使用者 BelindaN@litwareinc.com 可以存取的服務。</span><span class="sxs-lookup"><span data-stu-id="5bd66-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="5bd66-124">這會顯示與指派給其帳戶之所有授權相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="5bd66-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="5bd66-125">此範例會顯示使用者 BelindaN@litwareinc.com 可以從指派給其帳戶的第一個授權存取 (索引編號為 0) 的服務。</span><span class="sxs-lookup"><span data-stu-id="5bd66-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="5bd66-126">若要查看已指派 *多個授權*之使用者的所有服務，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="5bd66-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a><span data-ttu-id="5bd66-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="5bd66-127">See also</span></span>

[<span data-ttu-id="5bd66-128">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="5bd66-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5bd66-129">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5bd66-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5bd66-130">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bd66-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
