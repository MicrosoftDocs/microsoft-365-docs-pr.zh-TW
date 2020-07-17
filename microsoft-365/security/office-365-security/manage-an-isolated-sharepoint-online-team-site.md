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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 管理隔離的 SharePoint 線上小組網站、新增使用者和群組、移除使用者和群組，以及使用自訂許可權建立 documents 子資料夾。
ms.openlocfilehash: 43329aa72b3729200007441ce73838a7d6a60f55
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755375"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="5535f-103">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5535f-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="5535f-104">**摘要：** 使用這些程式來管理您的隔離 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="5535f-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="5535f-105">本文說明隔離 SharePoint Online 小組網站的一般管理作業。</span><span class="sxs-lookup"><span data-stu-id="5535f-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="5535f-106">新增使用者</span><span class="sxs-lookup"><span data-stu-id="5535f-106">Add a new user</span></span>

<span data-ttu-id="5535f-107">當有人新加入網站時，您必須決定其在網站中的參與層級：</span><span class="sxs-lookup"><span data-stu-id="5535f-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="5535f-108">管理：將新的使用者帳戶新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="5535f-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="5535f-109">主動共同作業：將使用者帳戶新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="5535f-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="5535f-110">查看：將使用者帳戶新增至網站檢視器存取群組</span><span class="sxs-lookup"><span data-stu-id="5535f-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="5535f-111">如果您是透過 Active Directory 網域服務（AD DS）來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將適當的使用者新增至適當的訪問群組，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="5535f-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="5535f-112">如果您是透過 Microsoft 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5535f-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="5535f-113">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的使用者新增至適當的訪問群組。</span><span class="sxs-lookup"><span data-stu-id="5535f-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="5535f-114">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="5535f-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="5535f-115">若要使用使用者主要名稱（UPN）將使用者帳戶新增至 access 群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="5535f-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="5535f-116">若要將使用者帳戶新增至具有其顯示名稱的 access 群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="5535f-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="5535f-117">新增群組</span><span class="sxs-lookup"><span data-stu-id="5535f-117">Add a new group</span></span>

<span data-ttu-id="5535f-118">若要將存取權新增至整個群組，您必須決定網站中群組的所有成員的參與層級：</span><span class="sxs-lookup"><span data-stu-id="5535f-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="5535f-119">管理：將群組新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="5535f-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="5535f-120">主動共同作業：將群組新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="5535f-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="5535f-121">查看：將群組新增至網站檢視器訪問群組</span><span class="sxs-lookup"><span data-stu-id="5535f-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="5535f-122">如果您是透過 AD DS 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將適當的群組新增至適當的群組，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="5535f-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="5535f-123">如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5535f-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="5535f-124">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的群組新增至適當的訪問群組。</span><span class="sxs-lookup"><span data-stu-id="5535f-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="5535f-125">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="5535f-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="5535f-126">然後，使用下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="5535f-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="5535f-127">移除使用者</span><span class="sxs-lookup"><span data-stu-id="5535f-127">Remove a user</span></span>

<span data-ttu-id="5535f-128">當某人的存取權必須從網站中移除時，您可以從存取權組中移除他們目前是其成員的存取權，而不是根據其在網站中的參與權：</span><span class="sxs-lookup"><span data-stu-id="5535f-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="5535f-129">管理：從網站管理員存取群組中移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5535f-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="5535f-130">主動共同作業：從網站成員存取群組中移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5535f-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="5535f-131">查看：從網站檢視器存取群組中移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5535f-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="5535f-132">如果您是透過 AD DS 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式從適當的訪問群組中移除適當的使用者，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="5535f-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="5535f-133">如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5535f-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="5535f-134">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組從適當的訪問群組中移除適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="5535f-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="5535f-135">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="5535f-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="5535f-136">若要使用 UPN 從存取群組中移除使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="5535f-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="5535f-137">若要從具有顯示名稱的 access 群組中移除使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="5535f-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="5535f-138">移除群組</span><span class="sxs-lookup"><span data-stu-id="5535f-138">Remove a group</span></span>

<span data-ttu-id="5535f-139">若要移除整個群組的存取權，您可以從存取權群組中移除群組，而其目前是根據其在網站中參與的成員：</span><span class="sxs-lookup"><span data-stu-id="5535f-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="5535f-140">管理：從網站管理員存取群組中移除群組</span><span class="sxs-lookup"><span data-stu-id="5535f-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="5535f-141">使用中共同作業：從網站成員存取群組中移除群組</span><span class="sxs-lookup"><span data-stu-id="5535f-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="5535f-142">查看：從網站檢視器存取群組中移除群組</span><span class="sxs-lookup"><span data-stu-id="5535f-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="5535f-143">如果您是透過 Windows Server Active Directory 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式從適當的訪問群組中移除適當的群組，並等待與您的訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="5535f-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="5535f-144">如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5535f-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="5535f-145">針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組從適當的訪問群組中移除適當的群組。</span><span class="sxs-lookup"><span data-stu-id="5535f-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="5535f-146">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="5535f-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="5535f-147">若要使用使用者的顯示名稱從存取群組中移除群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="5535f-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="5535f-148">使用自訂許可權建立 documents 子資料夾</span><span class="sxs-lookup"><span data-stu-id="5535f-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="5535f-149">在某些情況下，隔離網站中的人員子集需要更多私人位置才能進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="5535f-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="5535f-150">針對 SharePoint 線上網站，您可以在網站的 [檔] 資料夾中建立子資料夾，並指派自訂許可權。</span><span class="sxs-lookup"><span data-stu-id="5535f-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="5535f-151">沒有許可權的人員將不會看到子資料夾。</span><span class="sxs-lookup"><span data-stu-id="5535f-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="5535f-152">若要建立具有自訂許可權的 documents 子資料夾，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5535f-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="5535f-153">登入屬於網站管理員存取群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="5535f-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="5535f-154">如需說明，請參閱[在何處登入 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="5535f-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5535f-155">移至隔離的小組網站，然後按一下 [**檔**]。</span><span class="sxs-lookup"><span data-stu-id="5535f-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="5535f-156">流覽至 documents 資料夾中的資料夾，該資料夾將包含具有自訂許可權的子資料夾、建立資料夾，然後開啟該資料夾。</span><span class="sxs-lookup"><span data-stu-id="5535f-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="5535f-157">按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5535f-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="5535f-158">按一下 [**與 > Advanced**] [共用]。</span><span class="sxs-lookup"><span data-stu-id="5535f-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="5535f-159">按一下 [**停止繼承許可權**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5535f-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="5535f-160">按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5535f-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="5535f-161">按一下 [**與 > Advanced**] [共用]。</span><span class="sxs-lookup"><span data-stu-id="5535f-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="5535f-162">按一下 **[授與許可權] > 與 > 高級] 共用**。</span><span class="sxs-lookup"><span data-stu-id="5535f-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="5535f-163">在 [許可權] 頁面上，按一下\*\* \<site name> 清單中的 [成員\*\*]。</span><span class="sxs-lookup"><span data-stu-id="5535f-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="5535f-164">在 [ \*\* \<site name> 成員**] 頁面上，選取 [網站成員存取] 群組旁的勾選標記，按一下 [**動作**]，按一下 [**從群組移除使用者\*\*]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5535f-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="5535f-165">若要將特定成員新增至這個子資料夾，請按一下 [**新增 > 新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="5535f-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="5535f-166">在 [**共用**] 對話方塊中，輸入可共同處理子資料夾中檔案之使用者帳戶的名稱，然後按一下 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="5535f-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="5535f-167">請重新整理網頁以查看新的結果。</span><span class="sxs-lookup"><span data-stu-id="5535f-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="5535f-168">在左側導覽中的 [**群組**] 底下，按一下 [ \*\* \<site name> 訪客\*\*] 群組，並使用步驟11-14，指定可在子資料夾中查看檔案的使用者帳戶集（視需要）。</span><span class="sxs-lookup"><span data-stu-id="5535f-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="5535f-169">在左側導覽中的 [**群組**] 底下，按一下 [ \*\* \<site name> 擁有\*\*者] 群組，並使用步驟11-14，指定一組可在子資料夾中管理許可權的使用者帳戶（視需要）。</span><span class="sxs-lookup"><span data-stu-id="5535f-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="5535f-170">關閉瀏覽器中的 [**人員與群組**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5535f-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5535f-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5535f-171">See Also</span></span>

[<span data-ttu-id="5535f-172">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5535f-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="5535f-173">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5535f-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="5535f-174">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5535f-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



