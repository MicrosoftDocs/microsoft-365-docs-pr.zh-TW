---
title: 管理獨立的 SharePoint Online 小組網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 管理隔離的 SharePoint 線上小組網站、新增使用者和群組、移除使用者和群組，以及使用自訂許可權建立 documents 子資料夾。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 99b773547fa67068d75a79260af14010e456cb01
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059867"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="12d1f-103">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="12d1f-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="12d1f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="12d1f-104">**Applies to**</span></span>
- [<span data-ttu-id="12d1f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="12d1f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="12d1f-106">適用於 Office 365 的 Microsoft Defender 方案 1</span><span class="sxs-lookup"><span data-stu-id="12d1f-106">Microsoft Defender for Office 365 plan 1</span></span>](defender-for-office-365.md)
- <span data-ttu-id="12d1f-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="12d1f-107">SharePoint Online</span></span> 

 <span data-ttu-id="12d1f-108">**摘要：** 使用這些程式來管理您的隔離 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="12d1f-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="12d1f-109">本文說明隔離 SharePoint Online 小組網站的一般管理作業。</span><span class="sxs-lookup"><span data-stu-id="12d1f-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="12d1f-110">新增使用者</span><span class="sxs-lookup"><span data-stu-id="12d1f-110">Add a new user</span></span>

<span data-ttu-id="12d1f-111">當有人新加入網站時，您必須決定其在網站中的參與層級：</span><span class="sxs-lookup"><span data-stu-id="12d1f-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="12d1f-112">管理：將新的使用者帳戶新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="12d1f-113">主動共同作業：將使用者帳戶新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="12d1f-114">查看：將使用者帳戶新增至網站檢視器存取群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="12d1f-115">如果您是透過 Active Directory Domain Services (AD DS) 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將適當的使用者新增至適當的訪問群組，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="12d1f-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="12d1f-116">如果您是透過 Microsoft 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12d1f-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="12d1f-117">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的使用者新增至適當的訪問群組。</span><span class="sxs-lookup"><span data-stu-id="12d1f-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="12d1f-118">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="12d1f-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="12d1f-119">若要將使用者帳戶新增至具有使用者主要名稱 (UPN) 的 access 群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="12d1f-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="12d1f-120">若要將使用者帳戶新增至具有其顯示名稱的 access 群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="12d1f-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="12d1f-121">新增群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-121">Add a new group</span></span>

<span data-ttu-id="12d1f-122">若要將存取權新增至整個群組，您必須決定網站中群組的所有成員的參與層級：</span><span class="sxs-lookup"><span data-stu-id="12d1f-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="12d1f-123">管理：將群組新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="12d1f-124">主動共同作業：將群組新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="12d1f-125">查看：將群組新增至網站檢視器訪問群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="12d1f-126">如果您是透過 AD DS 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將適當的群組新增至適當的群組，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="12d1f-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="12d1f-127">如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12d1f-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="12d1f-128">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的群組新增至適當的訪問群組。</span><span class="sxs-lookup"><span data-stu-id="12d1f-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="12d1f-129">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="12d1f-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="12d1f-130">然後，使用下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="12d1f-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="12d1f-131">移除使用者</span><span class="sxs-lookup"><span data-stu-id="12d1f-131">Remove a user</span></span>

<span data-ttu-id="12d1f-132">當某人的存取權必須從網站中移除時，您可以從存取權組中移除他們目前是其成員的存取權，而不是根據其在網站中的參與權：</span><span class="sxs-lookup"><span data-stu-id="12d1f-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="12d1f-133">管理：從網站管理員存取群組中移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="12d1f-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="12d1f-134">主動共同作業：從網站成員存取群組中移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="12d1f-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="12d1f-135">查看：從網站檢視器存取群組中移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="12d1f-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="12d1f-136">如果您是透過 AD DS 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式從適當的訪問群組中移除適當的使用者，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="12d1f-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="12d1f-137">如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12d1f-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="12d1f-138">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組從適當的訪問群組中移除適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="12d1f-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="12d1f-139">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="12d1f-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="12d1f-140">若要使用 UPN 從存取群組中移除使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="12d1f-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="12d1f-141">若要從具有顯示名稱的 access 群組中移除使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="12d1f-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="12d1f-142">移除群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-142">Remove a group</span></span>

<span data-ttu-id="12d1f-143">若要移除整個群組的存取權，您可以從存取權群組中移除群組，而其目前是根據其在網站中參與的成員：</span><span class="sxs-lookup"><span data-stu-id="12d1f-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="12d1f-144">管理：從網站管理員存取群組中移除群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="12d1f-145">使用中共同作業：從網站成員存取群組中移除群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="12d1f-146">查看：從網站檢視器存取群組中移除群組</span><span class="sxs-lookup"><span data-stu-id="12d1f-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="12d1f-147">如果您是透過 Windows Server Active Directory 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式從適當的訪問群組中移除適當的群組，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="12d1f-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="12d1f-148">如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12d1f-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="12d1f-149">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組從適當的訪問群組中移除適當的群組。</span><span class="sxs-lookup"><span data-stu-id="12d1f-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="12d1f-150">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="12d1f-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="12d1f-151">若要使用使用者的顯示名稱從存取群組中移除群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="12d1f-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="12d1f-152">使用自訂許可權建立 documents 子資料夾</span><span class="sxs-lookup"><span data-stu-id="12d1f-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="12d1f-153">在某些情況下，隔離網站中的人員子集需要更多私人位置才能進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="12d1f-153">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="12d1f-154">針對 SharePoint 線上網站，您可以在網站的 [檔] 資料夾中建立子資料夾，並指派自訂許可權。</span><span class="sxs-lookup"><span data-stu-id="12d1f-154">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="12d1f-155">沒有許可權的人員將不會看到子資料夾。</span><span class="sxs-lookup"><span data-stu-id="12d1f-155">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="12d1f-156">若要建立具有自訂許可權的 documents 子資料夾，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="12d1f-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="12d1f-157">登入屬於網站管理員存取群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="12d1f-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="12d1f-158">如需說明，請參閱[在何處登入 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="12d1f-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="12d1f-159">移至隔離的小組網站，然後按一下 [ **檔**]。</span><span class="sxs-lookup"><span data-stu-id="12d1f-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="12d1f-160">流覽至 documents 資料夾中的資料夾，該資料夾將包含具有自訂許可權的子資料夾、建立資料夾，然後開啟該資料夾。</span><span class="sxs-lookup"><span data-stu-id="12d1f-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="12d1f-161">按一下 [共用 **]**。</span><span class="sxs-lookup"><span data-stu-id="12d1f-161">Click **Share**.</span></span>

5. <span data-ttu-id="12d1f-162">按一下 [ **與 > Advanced**] [共用]。</span><span class="sxs-lookup"><span data-stu-id="12d1f-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="12d1f-163">按一下 [ **停止繼承許可權**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="12d1f-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="12d1f-164">按一下 [共用 **]**。</span><span class="sxs-lookup"><span data-stu-id="12d1f-164">Click **Share**.</span></span>

8. <span data-ttu-id="12d1f-165">按一下 [ **與 > Advanced**] [共用]。</span><span class="sxs-lookup"><span data-stu-id="12d1f-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="12d1f-166">按一下 **[授與許可權] > 與 > 高級] 共用**。</span><span class="sxs-lookup"><span data-stu-id="12d1f-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="12d1f-167">在 [許可權] 頁面上，按一下 **\<site name> 清單中的 [成員**]。</span><span class="sxs-lookup"><span data-stu-id="12d1f-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="12d1f-168">在 [ **\<site name> 成員**] 頁面上，選取 [網站成員存取] 群組旁的勾選標記，按一下 [**動作**]，按一下 [**從群組移除使用者**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="12d1f-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="12d1f-169">若要將特定成員新增至這個子資料夾，請按一下 [ **新增 > 新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="12d1f-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="12d1f-170">在 [ **共用** ] 對話方塊中，輸入可共同處理子資料夾中檔案之使用者帳戶的名稱，然後按一下 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="12d1f-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="12d1f-171">請重新整理網頁以查看新的結果。</span><span class="sxs-lookup"><span data-stu-id="12d1f-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="12d1f-172">在左側導覽中的 [**群組**] 底下，按一下 [ **\<site name> 訪客**] 群組，並使用步驟11-14，根據需要在子資料夾中視需要查看檔案 (，以指定使用者帳戶的集合) 。</span><span class="sxs-lookup"><span data-stu-id="12d1f-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="12d1f-173">在左側導覽中的 [**群組**] 底下，按一下 [ **\<site name> 擁有** 者] 群組，並使用步驟11-14，根據需要在子資料夾中指定許可權，以指定使用者帳戶的組 () 。</span><span class="sxs-lookup"><span data-stu-id="12d1f-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="12d1f-174">關閉瀏覽器中的 [ **人員與群組** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="12d1f-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="12d1f-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="12d1f-175">See Also</span></span>

[<span data-ttu-id="12d1f-176">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="12d1f-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="12d1f-177">為團隊設定安全性隔離</span><span class="sxs-lookup"><span data-stu-id="12d1f-177">Configure a team with security isolation</span></span>](/microsoft-365/solutions/secure-teams-security-isolation)
