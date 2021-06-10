---
title: 維護具有 PowerShell 的安全性群組成員資格
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: 瞭解如何使用 PowerShell 維護 Microsoft 365 群組的成員資格。
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909571"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="71363-103">維護具有 PowerShell 的安全性群組成員資格</span><span class="sxs-lookup"><span data-stu-id="71363-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="71363-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="71363-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="71363-105">您可以使用 PowerShell Microsoft 365 Microsoft 365 系統管理中心，以維護 Microsoft 365 中的安全性群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="71363-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="71363-106">瞭解如何使用 Microsoft 365 系統管理中心[維護 Microsoft 365 群組成員資格](../admin/create-groups/add-or-remove-members-from-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="71363-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="71363-107">如需其他資源的清單，請參閱 [管理使用者和群組](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="71363-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="71363-108">針對 Graph 模組，請使用 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="71363-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="71363-109">首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="71363-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="71363-110">新增或移除使用者帳戶為群組的成員</span><span class="sxs-lookup"><span data-stu-id="71363-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="71363-111">**若要依其 UPN 新增使用者帳戶**，請將使用者帳戶使用者主要名稱填入 (UPN) 中 (範例： belindan@contoso.com) 及安全性群組顯示名稱、移除「<」和「>」字元，並在 PowerShell 視窗或 PowerShell 的整合式腳本環境中執行這些命令 (ISE) 。</span><span class="sxs-lookup"><span data-stu-id="71363-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="71363-112">**若要新增使用者帳戶的顯示名稱**，請填入使用者帳戶顯示名稱 (例如： Belinda Newman) 和群組顯示名稱，並在 [PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="71363-113">**若要依其 UPN 移除使用者帳戶**，請填入使用者帳戶 UPN (範例： belindan@contoso.com) 和群組顯示名稱，並在 [PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="71363-114">**若要依其顯示名稱移除使用者帳戶**，請填入使用者帳戶顯示名稱 (範例： Belinda Newman) 和 group 顯示名稱，並在 [PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="71363-115">新增或移除群組為群組的成員</span><span class="sxs-lookup"><span data-stu-id="71363-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="71363-116">安全性群組可以包含其他群組做為成員。</span><span class="sxs-lookup"><span data-stu-id="71363-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="71363-117">不過，Microsoft 365 群組卻無法。</span><span class="sxs-lookup"><span data-stu-id="71363-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="71363-118">本節包含的 PowerShell 命令可以新增或移除安全性群組的群組。</span><span class="sxs-lookup"><span data-stu-id="71363-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="71363-119">**若要以其顯示名稱來新增群組**，請填入要新增之群組的顯示名稱，以及將包含成員群組的群組的顯示名稱，並在 PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="71363-120">**若要依其顯示名稱移除群組**，請填入您要移除之群組的顯示名稱，以及會包含成員群組的群組的顯示名稱，並在 PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="71363-121">使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="71363-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="71363-122">首先，連線[至您的 Microsoft 365 租使用者](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="71363-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="71363-123">新增或移除使用者帳戶為群組的成員</span><span class="sxs-lookup"><span data-stu-id="71363-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="71363-124">**若要依其 UPN 新增使用者帳戶**，請將使用者帳戶使用者主要名稱填入 (UPN) 中 (範例： belindan@contoso.com) 和群組顯示名稱、移除 "<" 和 ">" 字元，並在 PowerShell 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="71363-125">**若要新增使用者帳戶的顯示名稱**，請填入使用者帳戶顯示名稱 (例如： Belinda Newman) 和群組顯示名稱，並在 [PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="71363-126">**若要依其 UPN 移除使用者帳戶**，請填入使用者帳戶 UPN (範例： belindan@contoso.com) 和群組顯示名稱，並在 [PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="71363-127">**若要依其顯示名稱移除使用者帳戶**，請填入使用者帳戶顯示名稱 (範例： Belinda Newman) 和 group 顯示名稱，並在 [PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="71363-128">新增或移除群組為群組的成員</span><span class="sxs-lookup"><span data-stu-id="71363-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="71363-129">安全性群組可以包含其他群組做為成員。</span><span class="sxs-lookup"><span data-stu-id="71363-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="71363-130">不過，Microsoft 365 群組卻無法。</span><span class="sxs-lookup"><span data-stu-id="71363-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="71363-131">本節包含的 PowerShell 命令可以新增或移除安全性群組的群組。</span><span class="sxs-lookup"><span data-stu-id="71363-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="71363-132">**若要以其顯示名稱來新增群組**，請填入要新增之群組的顯示名稱，以及將包含成員群組的群組的顯示名稱，並在 PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="71363-133">**若要依其顯示名稱移除群組**，請填入您要移除之群組的顯示名稱，以及會包含成員群組的群組的顯示名稱，並在 PowerShell] 視窗或 PowerShell ISE 中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="71363-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="71363-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="71363-134">See also</span></span>

[<span data-ttu-id="71363-135">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="71363-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="71363-136">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71363-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="71363-137">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="71363-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)