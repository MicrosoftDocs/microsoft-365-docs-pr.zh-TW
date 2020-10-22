---
title: 使用 PowerShell 將角色指派給 Microsoft 365 使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: 在本文中，瞭解如何將系統管理員角色指派給使用者帳戶，以快速輕鬆地使用 PowerShell Microsoft 365。
ms.openlocfilehash: 1486c86172cd34e6e88f8cd02d003967518bcdb7
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655944"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="23fce-103">使用 PowerShell 將系統管理員角色指派給 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="23fce-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="23fce-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="23fce-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="23fce-105">您可以使用 Microsoft 365 的 PowerShell，快速且輕鬆地將系統管理員角色指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="23fce-105">You can quickly and easily assign admin roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="23fce-106">瞭解如何使用 Microsoft 365 系統管理中心，[將系統管理員角色指派給使用者帳戶](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="23fce-106">[Learn how to assign admin roles to user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="23fce-107">如需其他資源的清單，請參閱 [管理使用者和群組](https://docs.microsoft.com/microsoft-365/admin/add-users/)。</span><span class="sxs-lookup"><span data-stu-id="23fce-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="23fce-108">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="23fce-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="23fce-109">首先，使用全域系統管理員帳戶 [連接至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) 。</span><span class="sxs-lookup"><span data-stu-id="23fce-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="23fce-110">接下來，決定要新增至角色的使用者帳戶登入名稱 (例如： fredsm@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="23fce-110">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com).</span></span> <span data-ttu-id="23fce-111">這也稱為使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="23fce-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="23fce-112">接下來，決定系統管理員角色的名稱。</span><span class="sxs-lookup"><span data-stu-id="23fce-112">Next, determine the name of the admin role.</span></span> <span data-ttu-id="23fce-113">使用 [Azure Active Directory 中的系統管理員角色許可權清單](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="23fce-113">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="23fce-114">請注意本文中的記事。</span><span class="sxs-lookup"><span data-stu-id="23fce-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="23fce-115">Azure AD PowerShell 的某些角色名稱是不同的。</span><span class="sxs-lookup"><span data-stu-id="23fce-115">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="23fce-116">例如，Microsoft 365 系統管理中心的「SharePoint 系統管理員」角色稱為「SharePoint 服務管理員」，以供 Azure AD PowerShell。</span><span class="sxs-lookup"><span data-stu-id="23fce-116">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="23fce-117">接下來，填入登入和角色名稱，並執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="23fce-117">Next, fill in the sign-in and role names and run these commands.</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="23fce-118">以下是將 SharePoint 服務管理員系統管理員角色指派給 belindan@contoso.com 帳戶的已完成命令集範例：</span><span class="sxs-lookup"><span data-stu-id="23fce-118">Here is an example of a completed command set that assigns the SharePoint Service Administrator admin role to the belindan@contoso.com account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="23fce-119">若要顯示特定系統管理員角色的使用者名稱清單，請使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="23fce-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="23fce-120">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="23fce-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="23fce-121">首先，使用全域系統管理員帳戶 [連接至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="23fce-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="23fce-122">針對單一角色變更</span><span class="sxs-lookup"><span data-stu-id="23fce-122">For a single role change</span></span>

<span data-ttu-id="23fce-123">特定使用者帳戶最常見的方式是顯示名稱或其電子郵件名稱，也就是知道其登入名稱或使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="23fce-123">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="23fce-124">使用者帳戶的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="23fce-124">Display names of user accounts</span></span>

<span data-ttu-id="23fce-125">如果您用來處理使用者帳戶的顯示名稱，請決定下列專案：</span><span class="sxs-lookup"><span data-stu-id="23fce-125">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="23fce-126">您要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="23fce-126">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="23fce-127">若要指定使用者帳戶，您必須決定其顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="23fce-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="23fce-128">若要取得完整清單帳戶，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="23fce-128">To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="23fce-129">這個命令會列出您的使用者帳戶顯示名稱，依顯示名稱排序，一次一屏。</span><span class="sxs-lookup"><span data-stu-id="23fce-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="23fce-130">您可以使用 **Where** Cmdlet，將清單篩選為較小的集合。</span><span class="sxs-lookup"><span data-stu-id="23fce-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="23fce-131">範例如下：</span><span class="sxs-lookup"><span data-stu-id="23fce-131">Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="23fce-132">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23fce-132">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="23fce-133">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="23fce-133">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="23fce-134">這個命令只會列出顯示名稱開頭為 "John" 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="23fce-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="23fce-135">您要指派的角色。</span><span class="sxs-lookup"><span data-stu-id="23fce-135">The role you want to assign.</span></span>
    
    <span data-ttu-id="23fce-136">若要顯示可指派給使用者帳戶的可用系統管理員角色清單，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="23fce-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="23fce-137">一旦您決定帳戶的顯示名稱和系統管理員角色的名稱，請使用下列命令將角色指派給帳戶：</span><span class="sxs-lookup"><span data-stu-id="23fce-137">Once you have determined the Display Name of the account and the Name of the admin role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="23fce-138">複製命令，並將其貼到 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="23fce-138">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="23fce-139">針對 **$dispName** 和 **$roleName** 變數，以其值取代描述文字、移除 \< and > 字元，並留下引號。</span><span class="sxs-lookup"><span data-stu-id="23fce-139">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="23fce-140">複製已修改的列，並將其貼到 windows 的 Windows Azure Active Directory 模組中 PowerShell] 視窗以執行。</span><span class="sxs-lookup"><span data-stu-id="23fce-140">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="23fce-141">或者，您也可以使用 Windows PowerShell 整合型腳本環境 (ISE) 。</span><span class="sxs-lookup"><span data-stu-id="23fce-141">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="23fce-142">以下是已完成命令集的範例：</span><span class="sxs-lookup"><span data-stu-id="23fce-142">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="23fce-143">使用者帳戶的登入名稱</span><span class="sxs-lookup"><span data-stu-id="23fce-143">Sign-in names of user accounts</span></span>

<span data-ttu-id="23fce-144">如果您用來使用登入名稱或使用者帳戶的 Upn，請決定下列專案：</span><span class="sxs-lookup"><span data-stu-id="23fce-144">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="23fce-145">使用者帳戶的 UPN。</span><span class="sxs-lookup"><span data-stu-id="23fce-145">The user account's UPN.</span></span>
    
    <span data-ttu-id="23fce-146">如果您還沒有知道 UPN，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="23fce-146">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="23fce-147">這個命令會列出您的使用者帳戶的 UPN，依 UPN 排序，一次一個畫面。</span><span class="sxs-lookup"><span data-stu-id="23fce-147">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="23fce-148">您可以使用 **Where** Cmdlet，將清單篩選為較小的集合。</span><span class="sxs-lookup"><span data-stu-id="23fce-148">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="23fce-149">範例如下：</span><span class="sxs-lookup"><span data-stu-id="23fce-149">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="23fce-150">這個命令只會列出顯示名稱開頭為 "John" 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="23fce-150">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="23fce-151">您要指派的角色。</span><span class="sxs-lookup"><span data-stu-id="23fce-151">The role you want to assign.</span></span>
    
    <span data-ttu-id="23fce-152">若要顯示可指派給使用者帳戶的可用角色清單，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="23fce-152">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="23fce-153">一旦您擁有帳戶的 UPN 和角色名稱，請使用下列命令將角色指派給帳戶：</span><span class="sxs-lookup"><span data-stu-id="23fce-153">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="23fce-154">複製命令，並將其貼到 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="23fce-154">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="23fce-155">針對 **$upnName** 和 **$roleName** 變數，以其值取代描述文字、移除 \< and > 字元，並留下引號。</span><span class="sxs-lookup"><span data-stu-id="23fce-155">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="23fce-156">複製已修改的列，並將其貼到 windows 的 Windows Azure Active Directory 模組中 PowerShell] 視窗以執行。</span><span class="sxs-lookup"><span data-stu-id="23fce-156">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="23fce-157">或者，您也可以使用 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="23fce-157">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="23fce-158">以下是已完成命令集的範例：</span><span class="sxs-lookup"><span data-stu-id="23fce-158">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="23fce-159">多重角色變更</span><span class="sxs-lookup"><span data-stu-id="23fce-159">Multiple role changes</span></span>

<span data-ttu-id="23fce-160">若有多個角色變更，請決定下列專案：</span><span class="sxs-lookup"><span data-stu-id="23fce-160">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="23fce-161">您要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="23fce-161">Which user accounts that you want to configure.</span></span> <span data-ttu-id="23fce-162">您可以使用上一節中的方法來收集顯示名稱或 Upn 的集合。</span><span class="sxs-lookup"><span data-stu-id="23fce-162">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="23fce-163">您想要指派給每個使用者帳戶的角色。</span><span class="sxs-lookup"><span data-stu-id="23fce-163">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="23fce-164">若要顯示可指派給使用者帳戶的可用角色清單，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="23fce-164">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="23fce-165">接下來，建立一個逗號分隔值 (CSV) 文字檔，該文字檔具有顯示名稱或 UPN 及角色名稱欄位。</span><span class="sxs-lookup"><span data-stu-id="23fce-165">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="23fce-166">您可以使用 Microsoft Excel 輕鬆做到這一點。</span><span class="sxs-lookup"><span data-stu-id="23fce-166">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="23fce-167">以下是顯示名稱的範例：</span><span class="sxs-lookup"><span data-stu-id="23fce-167">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="23fce-168">接下來，填入 CSV 檔案的位置，並在 PowerShell 命令提示字元中執行產生的命令。</span><span class="sxs-lookup"><span data-stu-id="23fce-168">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="23fce-169">以下是 Upn 的範例：</span><span class="sxs-lookup"><span data-stu-id="23fce-169">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="23fce-170">接下來，填入 CSV 檔案的位置，並在 PowerShell 命令提示字元中執行產生的命令。</span><span class="sxs-lookup"><span data-stu-id="23fce-170">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="23fce-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="23fce-171">See also</span></span>

- [<span data-ttu-id="23fce-172">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="23fce-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="23fce-173">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="23fce-173">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="23fce-174">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="23fce-174">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
