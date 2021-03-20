---
title: 使用 PowerShell 管理安全性群組
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: 瞭解如何使用 PowerShell 來管理安全性群組。
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909499"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="a9d8e-103">使用 PowerShell 管理安全性群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="a9d8e-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="a9d8e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a9d8e-105">您可以使用 Microsoft 365 的 PowerShell 作為 Microsoft 365 系統管理中心的替代方案，以管理安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="a9d8e-106">本文說明如何列出、建立、變更設定和移除安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="a9d8e-107">當本文中的命令區塊要求您指定變數值時，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="a9d8e-108">將命令區塊複製到 [剪貼簿]，然後將它貼到 [記事本] 或 PowerShell 整合型腳本環境 (ISE) 。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="a9d8e-109">填入變數值，並移除 "<" 和 ">" 字元。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="a9d8e-110">在 PowerShell] 視窗或 PowerShell ISE 中執行命令。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="a9d8e-111">請參閱 [維護安全性群組成員資格](maintain-group-membership-with-microsoft-365-powershell.md) 以使用 PowerShell 管理群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a9d8e-112">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9d8e-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a9d8e-113">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="a9d8e-114">列出您的群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-114">List your groups</span></span>

<span data-ttu-id="a9d8e-115">使用此命令來列出所有群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="a9d8e-116">使用這些命令，依其顯示名稱顯示特定群組的設定。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="a9d8e-117">建立新的群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-117">Create a new group</span></span>

<span data-ttu-id="a9d8e-118">使用此命令來建立新的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="a9d8e-119">變更群組上的設定</span><span class="sxs-lookup"><span data-stu-id="a9d8e-119">Change the settings on a group</span></span>

<span data-ttu-id="a9d8e-120">使用下列命令，顯示群組的設定。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="a9d8e-121">然後，使用「 [AzureADGroup」一](/powershell/module/azuread/set-azureadgroup) 文來決定如何變更設定。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="a9d8e-122">移除安全性群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-122">Remove a security group</span></span>

<span data-ttu-id="a9d8e-123">使用這些命令移除安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="a9d8e-124">管理安全性群組的擁有者</span><span class="sxs-lookup"><span data-stu-id="a9d8e-124">Manage the owners of a security group</span></span>

<span data-ttu-id="a9d8e-125">使用這些命令來顯示安全性群組目前的擁有者。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="a9d8e-126">使用這些命令，將使用者帳戶的 **使用者主要名稱 (UPN)** 新增至目前安全性群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="a9d8e-127">使用這些命令，透過其 **顯示名稱** 將使用者帳戶新增至目前安全性群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="a9d8e-128">使用這些命令，將使用者帳戶由其 **UPN 的 UPN** 移除，移至目前安全性群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="a9d8e-129">使用這些命令，將使用者帳戶的 **顯示名稱** 移除至安全性群組目前的擁有者。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a9d8e-130">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a9d8e-131">首先，連線 [至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="a9d8e-132">列出您的群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-132">List your groups</span></span>

<span data-ttu-id="a9d8e-133">使用此命令來列出所有群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="a9d8e-134">使用這些命令，依其顯示名稱顯示特定群組的設定。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="a9d8e-135">建立新的群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-135">Create a new group</span></span>

<span data-ttu-id="a9d8e-136">使用此命令來建立新的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="a9d8e-137">變更群組上的設定</span><span class="sxs-lookup"><span data-stu-id="a9d8e-137">Change the settings on a group</span></span>

<span data-ttu-id="a9d8e-138">使用下列命令，顯示群組的設定。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="a9d8e-139">然後，使用「 [MsolGroup」一](/powershell/module/msonline/set-msolgroup) 文來決定如何變更設定。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="a9d8e-140">移除安全性群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-140">Remove a security group</span></span>

<span data-ttu-id="a9d8e-141">使用這些命令移除安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a9d8e-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="a9d8e-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a9d8e-142">See also</span></span>

[<span data-ttu-id="a9d8e-143">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="a9d8e-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a9d8e-144">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9d8e-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a9d8e-145">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9d8e-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)