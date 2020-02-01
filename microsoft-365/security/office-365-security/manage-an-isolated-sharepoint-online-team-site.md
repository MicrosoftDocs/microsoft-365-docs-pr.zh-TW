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
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 摘要： 管理隔離的 SharePoint Online 小組網站與這些程序。
ms.openlocfilehash: 59c86c869ed38c3e64ff19974660cf96ec4c715e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599000"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ac76c-103">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ac76c-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="ac76c-104">**摘要：** 管理隔離的 SharePoint Online 小組網站與這些程序。</span><span class="sxs-lookup"><span data-stu-id="ac76c-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="ac76c-105">本文說明用於隔離 SharePoint Online 小組網站的一般管理作業。</span><span class="sxs-lookup"><span data-stu-id="ac76c-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="ac76c-106">新增使用者</span><span class="sxs-lookup"><span data-stu-id="ac76c-106">Add a new user</span></span>

<span data-ttu-id="ac76c-107">當新的人員加入網站時，您必須決定其程度站台中的參與：</span><span class="sxs-lookup"><span data-stu-id="ac76c-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="ac76c-108">管理： 將新的使用者帳戶新增至網站系統管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="ac76c-109">作用中的共同作業： 將使用者帳戶新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="ac76c-110">檢視： 將使用者帳戶新增至網站檢視者存取群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="ac76c-111">如果您要管理使用者帳戶和群組透過 Active Directory 網域服務 (AD DS)，將適當的使用者新增至適當的存取群組使用一般的 AD DS 使用者和群組管理程序，並等候與您的 Office 365 同步處理訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="ac76c-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="ac76c-112">如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac76c-112">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="ac76c-113">針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，將適當的使用者新增至適當的存取群組。</span><span class="sxs-lookup"><span data-stu-id="ac76c-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="ac76c-114">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="ac76c-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="ac76c-115">若要將使用者帳戶新增至其使用者主體名稱 (UPN) 存取群組，使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="ac76c-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ac76c-116">若要新增的使用者帳戶來存取群組，其顯示名稱，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="ac76c-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="ac76c-117">新增新群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-117">Add a new group</span></span>

<span data-ttu-id="ac76c-118">若要存取整個群組，您必須決定在站台中的所有群組的成員參與的層級：</span><span class="sxs-lookup"><span data-stu-id="ac76c-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="ac76c-119">管理： 將群組新增至網站系統管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="ac76c-120">作用中的共同作業： 將群組新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="ac76c-121">檢視： 將群組新增至網站檢視者存取群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="ac76c-122">如果您要管理使用者帳戶和透過 AD DS 群組，將適當的群組新增至適當的群組使用一般的 AD DS 使用者和群組管理程序，並等待同步處理您的 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="ac76c-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="ac76c-123">如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac76c-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="ac76c-124">針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，將適當的群組新增至適當的存取群組。</span><span class="sxs-lookup"><span data-stu-id="ac76c-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="ac76c-125">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="ac76c-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="ac76c-126">然後，使用下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="ac76c-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="ac76c-127">移除使用者</span><span class="sxs-lookup"><span data-stu-id="ac76c-127">Remove a user</span></span>

<span data-ttu-id="ac76c-128">必須從網站移除某個人的存取，當您移除這些，他們正在根據他們參與網站成員存取群組：</span><span class="sxs-lookup"><span data-stu-id="ac76c-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="ac76c-129">管理： 移除從網站系統管理員存取群組的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ac76c-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="ac76c-130">作用中的共同作業： 移除從網站成員存取群組的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ac76c-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="ac76c-131">檢視： 移除從網站檢視者存取群組的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="ac76c-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="ac76c-132">如果您要管理使用者帳戶和透過 AD DS 群組，從使用一般的 AD DS 使用者和群組管理程序適當的存取群組中移除適當的使用者，並等待同步處理您的 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="ac76c-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="ac76c-133">如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac76c-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="ac76c-134">針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，從適當的存取群組中移除適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="ac76c-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="ac76c-135">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="ac76c-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="ac76c-136">若要移除其 upn 存取群組的使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="ac76c-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ac76c-137">若要移除其顯示名稱為存取群組的使用者帳戶，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="ac76c-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="ac76c-138">移除群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-138">Remove a group</span></span>

<span data-ttu-id="ac76c-139">若要移除整個群組存取，您移除群組，他們正在根據他們參與網站成員存取群組：</span><span class="sxs-lookup"><span data-stu-id="ac76c-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="ac76c-140">管理： 移除從網站系統管理員存取群組的群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="ac76c-141">作用中的共同作業： 移除從網站成員存取群組的群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="ac76c-142">檢視： 移除從網站檢視者存取群組的群組</span><span class="sxs-lookup"><span data-stu-id="ac76c-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="ac76c-143">如果您要管理使用者帳戶和透過 Windows Server Active Directory 群組，從使用一般的 AD DS 使用者和群組管理程序的適當的存取群組中移除適當的群組，並等候與您的 Office 365 進行同步處理訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="ac76c-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="ac76c-144">如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac76c-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="ac76c-145">針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，從適當的存取群組中移除適當的群組。</span><span class="sxs-lookup"><span data-stu-id="ac76c-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="ac76c-146">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="ac76c-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="ac76c-147">若要使用他們的顯示名稱存取群組中移除群組，請使用下列 PowerShell 命令區塊：</span><span class="sxs-lookup"><span data-stu-id="ac76c-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="ac76c-148">建立文件的子資料夾有自訂權限</span><span class="sxs-lookup"><span data-stu-id="ac76c-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="ac76c-149">在某些情況下，使用獨立的站台內的人員子集需要更多私人理想的共同作業。</span><span class="sxs-lookup"><span data-stu-id="ac76c-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="ac76c-150">SharePoint Online 網站，您可以在網站的文件資料夾中建立子資料夾，並指派自訂權限。</span><span class="sxs-lookup"><span data-stu-id="ac76c-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="ac76c-151">這些權限而不會看到子資料夾。</span><span class="sxs-lookup"><span data-stu-id="ac76c-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="ac76c-152">若要建立自訂的權限文件的子資料夾，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ac76c-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="ac76c-153">是網站的系統管理員存取群組的成員帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ac76c-153">Sign in to Office 365 with an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="ac76c-154">如需說明，請參閱[在何處登入 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="ac76c-154">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="ac76c-155">移至隔離的小組網站，然後按一下 [**文件**。</span><span class="sxs-lookup"><span data-stu-id="ac76c-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="ac76c-156">瀏覽至資料夾中的文件資料夾，將會包含子資料夾中使用的自訂權限、 建立資料夾，然後再開啟它。</span><span class="sxs-lookup"><span data-stu-id="ac76c-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="ac76c-157">按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac76c-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="ac76c-158">按一下 [**與 > 進階共用**]。</span><span class="sxs-lookup"><span data-stu-id="ac76c-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="ac76c-159">按一下 [**停止繼承權限**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="ac76c-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="ac76c-160">按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac76c-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="ac76c-161">按一下 [**與 > 進階共用**]。</span><span class="sxs-lookup"><span data-stu-id="ac76c-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="ac76c-162">按一下 [**授與權限 > 與 > 進階共用**]。</span><span class="sxs-lookup"><span data-stu-id="ac76c-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="ac76c-163">在 [權限] 頁面上，按一下 [**\<網站清單中的名稱> 成員**。</span><span class="sxs-lookup"><span data-stu-id="ac76c-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="ac76c-164">在**\<網站名稱> 成員**] 頁面上，選取之網站成員存取群組旁的核取記號、 按一下 [**動作]**、 按一下 [**移除使用者群組**]，然後按一下 [ **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ac76c-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="ac76c-165">若要將特定成員新增至這個子資料夾，按一下 [**新 > 新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="ac76c-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="ac76c-166">在 [**共用**] 對話方塊中，輸入使用者帳戶，可以在子資料夾中的檔案上共同作業，然後按一下 [**共用**的名稱。</span><span class="sxs-lookup"><span data-stu-id="ac76c-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="ac76c-167">重新整理 [web] 頁面上，以查看新的結果。</span><span class="sxs-lookup"><span data-stu-id="ac76c-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="ac76c-168">在左導覽中的**群組**] 底下按一下 [**\<網站名稱> 訪客**群組，並使用步驟 11-14 指定 （視需要），可以檢視檔案的子資料夾中的使用者帳戶的集合。</span><span class="sxs-lookup"><span data-stu-id="ac76c-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="ac76c-169">在左導覽中的**群組**] 底下按一下 [**\<網站名稱> 擁有者**群組，並使用步驟 11-14 指定 （視需要） 可以管理的子資料夾中的權限的使用者帳戶的集合。</span><span class="sxs-lookup"><span data-stu-id="ac76c-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="ac76c-170">關閉瀏覽器中的 [**人員與群組**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ac76c-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac76c-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ac76c-171">See Also</span></span>

[<span data-ttu-id="ac76c-172">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ac76c-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="ac76c-173">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ac76c-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="ac76c-174">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ac76c-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



