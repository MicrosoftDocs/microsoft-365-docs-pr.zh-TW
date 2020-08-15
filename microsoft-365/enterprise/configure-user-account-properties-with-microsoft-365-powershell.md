---
title: 使用 PowerShell 設定 Microsoft 365 使用者帳戶屬性
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 摘要：使用 Microsoft 365 PowerShell，設定您的 Microsoft 365 租使用者中個別或多個使用者帳戶的屬性。
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688218"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="b66fa-103">使用 PowerShell 設定 Microsoft 365 使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="b66fa-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="b66fa-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="b66fa-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b66fa-105">雖然您可以使用 Microsoft 365 系統管理中心來設定 Microsoft 365 租使用者之使用者帳戶的屬性，但您也可以使用 PowerShell，並執行 Microsoft 365 系統管理中心無法執行的某些動作。</span><span class="sxs-lookup"><span data-stu-id="b66fa-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b66fa-106">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="b66fa-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b66fa-107">若要使用適用于 Graph 模組的 Azure Active Directory PowerShell，設定使用者帳戶的屬性，您可以使用 [AzureADUser 指令程式](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) ，並指定要設定或變更的屬性。</span><span class="sxs-lookup"><span data-stu-id="b66fa-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="b66fa-108">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="b66fa-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="b66fa-109">變更特定使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="b66fa-109">Change properties for a specific user account</span></span>

<span data-ttu-id="b66fa-110">您可以使用 **-ObjectID** 參數識別帳戶，並設定或變更具有其他參數的特定屬性。</span><span class="sxs-lookup"><span data-stu-id="b66fa-110">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="b66fa-111">以下是最常見的參數清單。</span><span class="sxs-lookup"><span data-stu-id="b66fa-111">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="b66fa-112">-部門 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="b66fa-113">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="b66fa-114">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="b66fa-115">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="b66fa-116">-姓 " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="b66fa-117">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="b66fa-118">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="b66fa-119">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="b66fa-120">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="b66fa-121">-城市 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="b66fa-122">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="b66fa-123">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="b66fa-124">-國家/地區 " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="b66fa-125">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="b66fa-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="b66fa-127">這是 ISO 3166-1 Alpha-2 (A2) 雙字母國家或地區碼。</span><span class="sxs-lookup"><span data-stu-id="b66fa-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="b66fa-128">請參閱 [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for 其他參數。</span><span class="sxs-lookup"><span data-stu-id="b66fa-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for additional parameters.</span></span>


<span data-ttu-id="b66fa-129">若要為您的使用者帳戶顯示使用者主要名稱，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b66fa-129">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="b66fa-130">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="b66fa-130">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="b66fa-131"> (**AzureADUser**) 取得使用者帳戶的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-131">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-132">依字母順序排序使用者主體名稱清單， (**排序 UserPrincipalName**) 然後將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-132">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-133">只顯示每個帳戶的使用者主體名稱屬性 (**選取 UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-133">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="b66fa-134"> (**更**) ，一次顯示一屏。</span><span class="sxs-lookup"><span data-stu-id="b66fa-134">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="b66fa-135">這個命令會列出您的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="b66fa-135">This command will list all of your accounts.</span></span> <span data-ttu-id="b66fa-136">如果您想要根據其顯示名稱來顯示帳戶的使用者主要名稱 () ，請填入下列 **$userName** 變數 (移除 \< and >) 的字元，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b66fa-136">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="b66fa-137">本範例會顯示名稱為 Caleb Sills 帳戶的使用者帳戶使用者主要名稱。</span><span class="sxs-lookup"><span data-stu-id="b66fa-137">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="b66fa-138">使用 **$upn** 變數，您可以根據其顯示名稱來變更個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="b66fa-138">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="b66fa-139">以下範例會將 Belinda Newman 的使用位置設定為法國，但指定其顯示名稱，而不是其使用者主要名稱：</span><span class="sxs-lookup"><span data-stu-id="b66fa-139">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="b66fa-140">變更所有使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="b66fa-140">Change properties for all user accounts</span></span>

<span data-ttu-id="b66fa-141">若要變更所有使用者的屬性，您可以使用 **AzureADUser** 和 **AzureADUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="b66fa-141">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="b66fa-142">下列範例會將所有使用者的使用位置變更為華北：</span><span class="sxs-lookup"><span data-stu-id="b66fa-142">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="b66fa-143">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="b66fa-143">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="b66fa-144"> (**AzureADUser**) 取得使用者帳戶的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-144">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-145">將使用者位置設定為法國 (**AzureADUser-UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-145">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="b66fa-146">變更特定使用者帳戶組的屬性</span><span class="sxs-lookup"><span data-stu-id="b66fa-146">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="b66fa-147">若要變更特定使用者帳戶集的屬性，您可以使用 **AzureADUser**、 **Where**及 **AzureADUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="b66fa-147">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="b66fa-148">下列範例會將會計部門中所有使用者的使用量位置變更為華北：</span><span class="sxs-lookup"><span data-stu-id="b66fa-148">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="b66fa-149">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="b66fa-149">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="b66fa-150"> (**AzureADUser**) 取得使用者帳戶的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-150">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-151">尋找其部門屬性設定為 "記帳" (的所有使用者帳戶， **其中 {$ _。部門-eq "記帳"}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-151">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-152">將使用者位置設定為法國 (**AzureADUser-UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-152">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b66fa-153">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="b66fa-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b66fa-154">若要使用 Microsoft Azure Active Directory Module for Windows PowerShell 設定使用者帳戶的屬性，您可以使用 **Set-MsolUser** Cmdlet，並指定要設定或變更的屬性。</span><span class="sxs-lookup"><span data-stu-id="b66fa-154">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="b66fa-155">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b66fa-155">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="b66fa-156">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b66fa-156">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="b66fa-157">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="b66fa-157">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="b66fa-158">變更特定使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="b66fa-158">Change properties for a specific user account</span></span>

<span data-ttu-id="b66fa-159">若要設定特定使用者帳戶的屬性，您可以使用 [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) Cmdlet，並指定要設定或變更的屬性。</span><span class="sxs-lookup"><span data-stu-id="b66fa-159">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="b66fa-160">您可以使用 **-UserPrincipalName** 參數來識別帳戶，並設定或變更具有其他參數的特定屬性。</span><span class="sxs-lookup"><span data-stu-id="b66fa-160">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="b66fa-161">以下是最常見的參數清單。</span><span class="sxs-lookup"><span data-stu-id="b66fa-161">Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="b66fa-162">-城市 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-162">-City "\<city name>"</span></span>
    
- <span data-ttu-id="b66fa-163">-國家/地區 " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-163">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="b66fa-164">-部門 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-164">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="b66fa-165">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-165">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="b66fa-166">-傳真 " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-166">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="b66fa-167">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-167">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="b66fa-168">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-168">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="b66fa-169">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-169">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="b66fa-170">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-170">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="b66fa-171">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-171">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="b66fa-172">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-172">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="b66fa-173">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-173">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="b66fa-174">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-174">-State "\<state name>"</span></span>
    
- <span data-ttu-id="b66fa-175">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-175">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="b66fa-176">-職稱 " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-176">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="b66fa-177">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="b66fa-177">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="b66fa-178">這是 ISO 3166-1 Alpha-2 (A2) 雙字母國家或地區碼。</span><span class="sxs-lookup"><span data-stu-id="b66fa-178">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="b66fa-179">如需其他參數，請參閱 [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-179">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="b66fa-180">若要查看所有使用者的使用者主要名稱，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b66fa-180">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="b66fa-181">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="b66fa-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="b66fa-182">**Get-MsolUser**) 取得使用者帳戶 (的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-182">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-183">依字母順序排序使用者主體名稱清單， (**排序 UserPrincipalName**) 然後將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-183">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-184">只顯示每個帳戶的使用者主體名稱屬性 (**選取 UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-184">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="b66fa-185"> (**更**) ，一次顯示一屏。</span><span class="sxs-lookup"><span data-stu-id="b66fa-185">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="b66fa-186">這個命令會列出您的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="b66fa-186">This command will list all of your accounts.</span></span> <span data-ttu-id="b66fa-187">如果您想要根據其顯示名稱來顯示帳戶的使用者主要名稱 () ，請填入下列 **$userName** 變數 (移除 \< and >) 的字元，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b66fa-187">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="b66fa-188">此範例會顯示名為 Caleb Sills 帳戶之使用者的使用者主要名稱。</span><span class="sxs-lookup"><span data-stu-id="b66fa-188">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="b66fa-189">使用 **$upn** 變數，您可以根據其顯示名稱來變更個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="b66fa-189">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="b66fa-190">以下範例會將 Belinda Newman 的使用位置設定為法國，但指定其顯示名稱，而不是其使用者主要名稱：</span><span class="sxs-lookup"><span data-stu-id="b66fa-190">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="b66fa-191">變更所有使用者帳戶的屬性</span><span class="sxs-lookup"><span data-stu-id="b66fa-191">Change properties for all user accounts</span></span>

<span data-ttu-id="b66fa-192">若要變更所有使用者的屬性，您可以使用 **Get-MsolUser** 和 **Set-MsolUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="b66fa-192">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="b66fa-193">下列範例會將所有使用者的使用位置變更為華北：</span><span class="sxs-lookup"><span data-stu-id="b66fa-193">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="b66fa-194">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="b66fa-194">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="b66fa-195">**Get-MsolUser**) 取得使用者帳戶 (的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-195">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-196">將使用者位置設定為法國 (**Set-MsolUser UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-196">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="b66fa-197">變更特定使用者帳戶組的屬性</span><span class="sxs-lookup"><span data-stu-id="b66fa-197">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="b66fa-198">若要變更特定使用者帳戶集的屬性，您可以使用 **Get-MsolUser**、 **Where**及 **Set-MsolUser** Cmdlet 的組合。</span><span class="sxs-lookup"><span data-stu-id="b66fa-198">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="b66fa-199">下列範例會將會計部門中所有使用者的使用量位置變更為華北：</span><span class="sxs-lookup"><span data-stu-id="b66fa-199">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="b66fa-200">這個命令會指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="b66fa-200">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="b66fa-201">**Get-MsolUser**) 取得使用者帳戶 (的所有資訊，並將其傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-201">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-202">尋找其部門屬性設定為 "記帳" (的所有使用者帳戶， **其中 {$ _。部門-eq "記帳"}**) ，並將產生的資訊傳送至下一個命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-202">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="b66fa-203">將使用者位置設定為法國 (**Set-MsolUser UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="b66fa-203">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    

## <a name="see-also"></a><span data-ttu-id="b66fa-204">請參閱</span><span class="sxs-lookup"><span data-stu-id="b66fa-204">See also</span></span>

[<span data-ttu-id="b66fa-205">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="b66fa-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b66fa-206">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b66fa-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b66fa-207">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b66fa-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
