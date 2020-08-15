---
title: 使用 PowerShell 停用 Microsoft 365 服務的存取權
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: 在本文中，您將瞭解如何使用 PowerShell 來停用使用者的 Microsoft 365 服務存取權。
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688478"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="445d7-103">使用 PowerShell 停用 Microsoft 365 服務的存取權</span><span class="sxs-lookup"><span data-stu-id="445d7-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="445d7-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="445d7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="445d7-105">將授權方案的授權指派給 Microsoft 365 帳戶時，使用者就可以從該授權取得 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="445d7-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="445d7-106">不過，您可以控制使用者可以存取的 Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="445d7-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="445d7-107">例如，即使授權允許存取 SharePoint 線上服務，您還是可以停用存取權。</span><span class="sxs-lookup"><span data-stu-id="445d7-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="445d7-108">您可以使用 PowerShell 針對特定授權方案停用任何數目的服務存取權：</span><span class="sxs-lookup"><span data-stu-id="445d7-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="445d7-109">個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="445d7-109">An individual account.</span></span>
- <span data-ttu-id="445d7-110">一組帳戶。</span><span class="sxs-lookup"><span data-stu-id="445d7-110">A group of accounts.</span></span>
- <span data-ttu-id="445d7-111">您組織中的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="445d7-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="445d7-112">當其他服務依賴于指定的服務時，Microsoft 365 服務相依性會使您無法停用。</span><span class="sxs-lookup"><span data-stu-id="445d7-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="445d7-113">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="445d7-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="445d7-114">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="445d7-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="445d7-115">接下來，使用此命令來查看可用的授權方案，也稱為 AccountSkuIds：</span><span class="sxs-lookup"><span data-stu-id="445d7-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="445d7-116">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="445d7-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="445d7-117">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="445d7-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="445d7-118">如需詳細資訊，請參閱 [使用 PowerShell 查看授權和服務](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="445d7-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="445d7-119">若要查看本主題中程式的 before 和 after 結果，請參閱 [使用 PowerShell 查看帳戶授權和服務詳細資料](view-account-license-and-service-details-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="445d7-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="445d7-120">PowerShell 指令碼可供使用，會自動執行本主題中所述的程序。</span><span class="sxs-lookup"><span data-stu-id="445d7-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="445d7-121">具體說來，此腳本可讓您查看及停用 Microsoft 365 組織中的服務，包括 Sway。</span><span class="sxs-lookup"><span data-stu-id="445d7-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="445d7-122">如需詳細資訊，請參閱 [使用 PowerShell 停用 Sway 的存取權](disable-access-to-sway-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="445d7-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="445d7-123">針對特定授權方案停用特定使用者的特定 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="445d7-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="445d7-124">若要針對特定授權方案停用一組特定的 Microsoft 365 服務，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="445d7-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="445d7-125">步驟1：使用下列語法識別授權方案中不想要的服務：</span><span class="sxs-lookup"><span data-stu-id="445d7-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="445d7-126">下列範例會建立 **LicenseOptions** 物件，以停用名為 `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3) 之授權方案中的 Office 和 SharePoint Online 服務。</span><span class="sxs-lookup"><span data-stu-id="445d7-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="445d7-127">步驟2：在一或多個使用者上使用步驟1中的 **LicenseOptions** 物件。</span><span class="sxs-lookup"><span data-stu-id="445d7-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="445d7-128">若要建立已停用服務的新帳戶，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="445d7-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="445d7-129">下列範例會為 Allie Bellew 建立新的帳戶，以指派授權並停用步驟1中所述的服務。</span><span class="sxs-lookup"><span data-stu-id="445d7-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="445d7-130">如需在 Microsoft 365 的 PowerShell 中建立使用者帳戶的詳細資訊，請參閱 [使用 PowerShell 建立使用者帳戶](create-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="445d7-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="445d7-131">若要停用現有授權使用者的服務，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="445d7-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="445d7-132">本範例會停用使用者 BelindaN@litwareinc.com 的服務。</span><span class="sxs-lookup"><span data-stu-id="445d7-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="445d7-133">若要停用步驟1中所述的所有現有授權使用者的服務，請從 **Get-MsolAccountSku** Cmdlet (（例如 **litwareinc:ENTERPRISEPACK**) ）中指定您的 Microsoft 365 方案名稱，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="445d7-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="445d7-134">如果您使用 **Get-MsolUser** Cmdlet 但未使用 _All_ 參數，則只會傳回第一個500使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="445d7-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="445d7-135">若要為一組現有的使用者停用服務，請使用下列其中一種方法來識別使用者：</span><span class="sxs-lookup"><span data-stu-id="445d7-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="445d7-136">**方法1。根據現有的帳戶屬性來篩選帳戶**</span><span class="sxs-lookup"><span data-stu-id="445d7-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="445d7-137">若要這麼做，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="445d7-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="445d7-138">下列範例會停用美國地區的銷售部門中的使用者服務。</span><span class="sxs-lookup"><span data-stu-id="445d7-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="445d7-139">**方法2：使用特定帳戶的清單**</span><span class="sxs-lookup"><span data-stu-id="445d7-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="445d7-140">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="445d7-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="445d7-141">建立一個文字檔，其中每一行上都包含一個帳戶，如下所示：</span><span class="sxs-lookup"><span data-stu-id="445d7-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="445d7-142">在此範例中，文字檔為 C： \\ 我的檔 \\Accounts.txt。</span><span class="sxs-lookup"><span data-stu-id="445d7-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="445d7-143">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="445d7-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="445d7-144">如果您想要針對多個授權方案停用服務存取權，請針對每個授權方案重複上述指示，以確保：</span><span class="sxs-lookup"><span data-stu-id="445d7-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="445d7-145">已指派授權方案的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="445d7-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="445d7-146">授權方案提供要停用的服務。</span><span class="sxs-lookup"><span data-stu-id="445d7-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="445d7-147">若要在將使用者指派給授權方案時，為他們停用 Microsoft 365 服務，請參閱在 [指派使用者授權時停用服務的存取權](disable-access-to-services-while-assigning-user-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="445d7-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="445d7-148">將授權方案中的所有服務指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="445d7-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="445d7-149">針對已停用服務的使用者帳戶，您可以使用下列命令來啟用特定授權方案的所有服務：</span><span class="sxs-lookup"><span data-stu-id="445d7-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="445d7-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="445d7-150">Related topic</span></span>

[<span data-ttu-id="445d7-151">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="445d7-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="445d7-152">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="445d7-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="445d7-153">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="445d7-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
