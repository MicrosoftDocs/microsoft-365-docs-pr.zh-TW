---
title: 使用 PowerShell 查看已授權和未經許可的 Microsoft 365 使用者
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: 本文說明如何使用 PowerShell 來查看已授權和未經許可的 Microsoft 365 使用者帳戶。
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651381"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="e5b74-103">使用 PowerShell 查看已授權和未經許可的 Microsoft 365 使用者</span><span class="sxs-lookup"><span data-stu-id="e5b74-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="e5b74-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="e5b74-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e5b74-105">您的 Microsoft 365 組織中的使用者帳戶可能會從您組織中提供的授權方案中，為他們指派一些、全部或沒有的可用授權。</span><span class="sxs-lookup"><span data-stu-id="e5b74-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="e5b74-106">您可以使用 Microsoft 365 的 PowerShell，在您的組織中快速尋找授權與未經授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="e5b74-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e5b74-107">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5b74-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e5b74-108">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e5b74-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="e5b74-109">若要查看組織中所有尚未指派任何授權方案的使用者帳戶清單 (未經許可的使用者) ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e5b74-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="e5b74-110">若要查看組織中已指派任何授權方案 (授權使用者的所有使用者帳戶清單) ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e5b74-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="e5b74-111">若要列出您訂閱中的所有使用者，請使用 `Get-AzureAdUser -All $true` 命令。</span><span class="sxs-lookup"><span data-stu-id="e5b74-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e5b74-112">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="e5b74-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e5b74-113">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e5b74-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="e5b74-114">若要查看組織中所有使用者帳戶及其授權狀態的清單，請在 PowerShell: 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e5b74-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="e5b74-115">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e5b74-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e5b74-116">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="e5b74-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="e5b74-117">若要檢視您組織中所有未經授權使用者帳戶的清單，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e5b74-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="e5b74-118">若要檢視您組織中所有經授權使用者帳戶的清單，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e5b74-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="e5b74-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e5b74-119">See also</span></span>

[<span data-ttu-id="e5b74-120">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="e5b74-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e5b74-121">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5b74-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e5b74-122">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5b74-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
