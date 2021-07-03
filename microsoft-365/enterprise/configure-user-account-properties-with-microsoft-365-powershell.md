---
title: 使用 PowerShell 設定 Microsoft 365 使用者帳戶屬性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 使用 Microsoft 365 的 PowerShell，設定 Microsoft 365 承租人中個別或多個使用者帳戶的屬性。
ms.openlocfilehash: aeb9b586c42a0bdfb8d69b8d297998fedc1124e6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286006"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="176b9-103">使用 PowerShell 設定 Microsoft 365 使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="176b9-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="176b9-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="176b9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="176b9-105">您可以使用 Microsoft 365 系統管理中心來設定 Microsoft 365 租使用者帳戶的屬性。</span><span class="sxs-lookup"><span data-stu-id="176b9-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="176b9-106">在 PowerShell 中，您也可以執行這項動作，此外還有其他一些無法在系統管理中心中執行的動作。</span><span class="sxs-lookup"><span data-stu-id="176b9-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="176b9-107">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="176b9-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="176b9-108">若要在 Graph 模組的 Azure Active Directory PowerShell 中設定使用者帳戶的屬性，請使用 [**AzureADUser 指令程式**](/powershell/module/azuread/set-azureaduser)，並指定要設定或變更的屬性。</span><span class="sxs-lookup"><span data-stu-id="176b9-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="176b9-109">首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="176b9-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="176b9-110">變更特定使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="176b9-110">Change properties for a specific user account</span></span>

<span data-ttu-id="176b9-111">您可以使用 *-ObjectID* 參數識別帳戶，並使用其他參數設定或變更特定屬性。</span><span class="sxs-lookup"><span data-stu-id="176b9-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="176b9-112">以下是最常見的參數清單：</span><span class="sxs-lookup"><span data-stu-id="176b9-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="176b9-113">-部門 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-113">-Department "\<department name>"</span></span>

- <span data-ttu-id="176b9-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-114">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="176b9-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="176b9-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>

- <span data-ttu-id="176b9-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-116">-GivenName "\<user first name>"</span></span>

- <span data-ttu-id="176b9-117">-姓 " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-117">-Surname "\<user last name>"</span></span>

- <span data-ttu-id="176b9-118">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="176b9-118">-Mobile "\<mobile phone number>"</span></span>

- <span data-ttu-id="176b9-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="176b9-119">-JobTitle "\<job title>"</span></span>

- <span data-ttu-id="176b9-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="176b9-120">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="176b9-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="176b9-121">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="176b9-122">-城市 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-122">-City "\<city name>"</span></span>

- <span data-ttu-id="176b9-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-123">-State "\<state name>"</span></span>

- <span data-ttu-id="176b9-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="176b9-124">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="176b9-125">-國家/地區 " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-125">-Country "\<country name>"</span></span>

- <span data-ttu-id="176b9-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="176b9-126">-TelephoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="176b9-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="176b9-127">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="176b9-128">這是 ISO 3166-1 Alpha-2 (A2) 雙字母國家或地區碼。</span><span class="sxs-lookup"><span data-stu-id="176b9-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="176b9-129">如需其他參數，請參閱 [AzureADUser](/powershell/module/azuread/set-azureaduser)。</span><span class="sxs-lookup"><span data-stu-id="176b9-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser).</span></span>

> [!NOTE]
> <span data-ttu-id="176b9-130">在您指派授權給使用者帳戶之前，您必須指派使用位置。</span><span class="sxs-lookup"><span data-stu-id="176b9-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>

<span data-ttu-id="176b9-131">若要為您的使用者帳戶顯示使用者主要名稱，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="176b9-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="176b9-132">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="176b9-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="176b9-133"> (**AzureADUser**) 取得使用者帳戶上的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-134">依字母順序排序使用者主體名稱清單， (**排序 UserPrincipalName**) 然後將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-135">只顯示每個帳戶的使用者主體名稱屬性 (**選取 UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="176b9-136"> (**更**) ，一次顯示一屏。</span><span class="sxs-lookup"><span data-stu-id="176b9-136">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="176b9-137">若要根據顯示名稱顯示帳戶的使用者主要名稱)  (first 和 last name，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="176b9-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="176b9-138">填入 *$userName* 變數，並移除 \< and > 下列字元：</span><span class="sxs-lookup"><span data-stu-id="176b9-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="176b9-139">在這個範例中，會顯示具有顯示名稱 *Caleb sills 帳戶* 之使用者帳戶的使用者主要名稱。</span><span class="sxs-lookup"><span data-stu-id="176b9-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="176b9-140">使用 *$upn* 變數，您可以根據其顯示名稱來變更個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="176b9-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="176b9-141">以下範例會將 *Belinda Newman* 的使用位置設定為法國。</span><span class="sxs-lookup"><span data-stu-id="176b9-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="176b9-142">但是它會指定其顯示名稱，而不是使用者主要名稱：</span><span class="sxs-lookup"><span data-stu-id="176b9-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="176b9-143">變更所有使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="176b9-143">Change properties for all user accounts</span></span>

<span data-ttu-id="176b9-144">若要變更所有使用者的屬性，您可以使用 **AzureADUser** 和 **AzureADUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="176b9-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="176b9-145">下列範例會將所有使用者的使用位置變更為 *華北*：</span><span class="sxs-lookup"><span data-stu-id="176b9-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="176b9-146">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="176b9-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="176b9-147"> (**AzureADUser**) 取得使用者帳戶的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-148">將使用者位置設定為法國 (**AzureADUser-UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="176b9-149">變更特定使用者帳戶組的屬性</span><span class="sxs-lookup"><span data-stu-id="176b9-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="176b9-150">若要變更特定使用者帳戶集的屬性，您可以使用 **AzureADUser**、 **Where** 及 **AzureADUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="176b9-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="176b9-151">下列範例會將會計部門中所有使用者的使用量位置變更為 *華北*：</span><span class="sxs-lookup"><span data-stu-id="176b9-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="176b9-152">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="176b9-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="176b9-153"> (**AzureADUser**) 取得使用者帳戶上的所有資訊，然後將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>

1.  <span data-ttu-id="176b9-154">尋找其 *部門* 屬性設定為 "記帳" (的所有使用者帳戶， **其中 {$ _。部門-eq "記帳"}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-155">將使用者位置設定為法國 (**AzureADUser-UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="176b9-156">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="176b9-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="176b9-157">若要使用 Windows PowerShell 的 Microsoft Azure Active Directory 模組設定使用者帳戶的屬性，請使用 **Set-MsolUser** Cmdlet，並指定要設定或變更的屬性。</span><span class="sxs-lookup"><span data-stu-id="176b9-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="176b9-158">首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="176b9-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
> [!NOTE]
> <span data-ttu-id="176b9-159">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="176b9-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="176b9-160">從 PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="176b9-160">Run these cmdlets from Windows PowerShell.</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="176b9-161">變更特定使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="176b9-161">Change properties for a specific user account</span></span>

<span data-ttu-id="176b9-162">若要設定特定使用者帳戶的屬性，請使用 [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) Cmdlet，並指定要設定或變更的屬性。</span><span class="sxs-lookup"><span data-stu-id="176b9-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="176b9-163">您可以使用 *-UserPrincipalName* 參數識別帳戶，並使用其他參數設定或變更特定屬性。</span><span class="sxs-lookup"><span data-stu-id="176b9-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="176b9-164">以下是最常見的參數清單。</span><span class="sxs-lookup"><span data-stu-id="176b9-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="176b9-165">-城市 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-165">-City "\<city name>"</span></span>

- <span data-ttu-id="176b9-166">-國家/地區 " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-166">-Country "\<country name>"</span></span>

- <span data-ttu-id="176b9-167">-部門 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-167">-Department "\<department name>"</span></span>

- <span data-ttu-id="176b9-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-168">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="176b9-169">-傳真 " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="176b9-169">-Fax "\<fax number>"</span></span>

- <span data-ttu-id="176b9-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-170">-FirstName "\<user first name>"</span></span>

- <span data-ttu-id="176b9-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-171">-LastName "\<user last name>"</span></span>

- <span data-ttu-id="176b9-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="176b9-172">-MobilePhone "\<mobile phone number>"</span></span>

- <span data-ttu-id="176b9-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="176b9-173">-Office "\<office location>"</span></span>

- <span data-ttu-id="176b9-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="176b9-174">-PhoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="176b9-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="176b9-175">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="176b9-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="176b9-176">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="176b9-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-177">-State "\<state name>"</span></span>

- <span data-ttu-id="176b9-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="176b9-178">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="176b9-179">-職稱 " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="176b9-179">-Title "\<title name>"</span></span>

- <span data-ttu-id="176b9-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="176b9-180">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="176b9-181">這是 ISO 3166-1 Alpha-2 (A2) 雙字母國家或地區碼。</span><span class="sxs-lookup"><span data-stu-id="176b9-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="176b9-182">如需其他參數，請參閱 [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="176b9-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="176b9-183">若要查看所有使用者的使用者主要名稱，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="176b9-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="176b9-184">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="176b9-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="176b9-185">**Get-MsolUser**) 取得使用者帳戶 (的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-186">依字母順序排序使用者主體名稱清單， (**排序 UserPrincipalName**) 然後將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-187">只顯示每個帳戶的使用者主體名稱屬性 (**選取 UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="176b9-188"> (**更**) ，一次顯示一屏。</span><span class="sxs-lookup"><span data-stu-id="176b9-188">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="176b9-189">若要根據顯示名稱顯示帳戶的使用者主要名稱)  (first 和 last name，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="176b9-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="176b9-190">填入 *$userName* 變數，然後移除 \< and > 字元。</span><span class="sxs-lookup"><span data-stu-id="176b9-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="176b9-191">此範例會顯示名為 Caleb Sills 帳戶之使用者的使用者主要名稱：</span><span class="sxs-lookup"><span data-stu-id="176b9-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="176b9-192">使用 *$upn* 變數，您可以根據其顯示名稱來變更個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="176b9-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="176b9-193">以下範例會將 *Belinda Newman* 的使用位置設定為 *法國*，但是會指定其顯示名稱，而不是其使用者主要名稱：</span><span class="sxs-lookup"><span data-stu-id="176b9-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="176b9-194">變更所有使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="176b9-194">Change properties for all user accounts</span></span>

<span data-ttu-id="176b9-195">若要變更所有使用者的屬性，請使用 **Get-MsolUser** 和 **Set-MsolUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="176b9-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="176b9-196">下列範例會將所有使用者的使用位置變更為 *華北*：</span><span class="sxs-lookup"><span data-stu-id="176b9-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="176b9-197">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="176b9-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="176b9-198">取得使用者帳戶 (**Get-MsolUser**) 的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-199">將使用者位置設定為法國 (**Set-MsolUser UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="176b9-200">變更特定使用者帳戶組的屬性</span><span class="sxs-lookup"><span data-stu-id="176b9-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="176b9-201">若要變更特定使用者帳戶集的屬性，您可以使用 **Get-MsolUser**、 **Where** 及 **Set-MsolUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="176b9-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="176b9-202">下列範例會將會計部門中所有使用者的使用量位置變更為 *華北*：</span><span class="sxs-lookup"><span data-stu-id="176b9-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="176b9-203">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="176b9-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="176b9-204">取得使用者帳戶 (**Get-MsolUser**) 的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-205">尋找其 *部門* 屬性設定為 "記帳" (的所有使用者帳戶，其為 **{$ _。部門-eq "記帳"}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="176b9-206">將使用者位置設定為法國 (**Set-MsolUser UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="176b9-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="176b9-207">另請參閱</span><span class="sxs-lookup"><span data-stu-id="176b9-207">See also</span></span>

[<span data-ttu-id="176b9-208">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="176b9-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="176b9-209">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="176b9-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="176b9-210">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="176b9-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
