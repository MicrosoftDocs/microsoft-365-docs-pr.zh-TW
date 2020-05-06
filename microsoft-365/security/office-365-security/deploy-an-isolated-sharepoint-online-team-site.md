---
title: 部署獨立的 SharePoint Online 小組網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 使用此逐步部署指南，在 Microsoft Office 365 中建立和設定隔離的 SharePoint Online 小組網站。
ms.openlocfilehash: 772a9e5ea08871857a70cc840e377046d459a314
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036448"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="4e91d-103">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="4e91d-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="4e91d-104">**摘要：** 使用下列逐步指示來部署新的獨立 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="4e91d-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="4e91d-105">本文屬於逐步部署指南，說明如何在 Microsoft Office 365 中建立及設定獨立的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="4e91d-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="4e91d-106">下列步驟假設使用三個預設 SharePoint 群組和對應的權限等級，其中每個存取層級都有一個 Azure Active Directory (AD) 型存取群組。</span><span class="sxs-lookup"><span data-stu-id="4e91d-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="4e91d-107">階段1：建立並填入小組網站存取群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="4e91d-108">在這個階段中，您會針對三個預設 SharePoint 群組建立三個 Azure AD 型存取群組，並填入適當的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4e91d-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e91d-109">下列步驟假設所有必要的使用者帳戶都已經存在，並已獲派適當的授權。</span><span class="sxs-lookup"><span data-stu-id="4e91d-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="4e91d-110">如果沒有，請先新增並指派授權，再繼續進行步驟1。</span><span class="sxs-lookup"><span data-stu-id="4e91d-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="4e91d-111">步驟1：列出網站的 SharePoint Online 系統管理員</span><span class="sxs-lookup"><span data-stu-id="4e91d-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="4e91d-112">決定與獨立小組網站的 SharePoint Online 系統管理員對應的一組使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4e91d-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="4e91d-113">如果您是透過 Microsoft 365 管理使用者帳戶和群組，且想要使用 Windows PowerShell，請建立使用者主要名稱（Upn）清單（例如 UPN： belindan@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="4e91d-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="4e91d-114">步驟2：列出網站的成員</span><span class="sxs-lookup"><span data-stu-id="4e91d-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="4e91d-115">決定與獨立小組網站成員對應的一組使用者帳戶，其會在網站中所儲存的資源上共同作業。</span><span class="sxs-lookup"><span data-stu-id="4e91d-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="4e91d-116">如果您是透過 Microsoft 365 管理使用者帳戶和群組，且想要使用 PowerShell，請建立其 Upn 的清單。</span><span class="sxs-lookup"><span data-stu-id="4e91d-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="4e91d-117">如果有大量網站成員，您可以將 UPN 清單儲存在文字檔中，並使用單一 PowerShell 命令全部新增。</span><span class="sxs-lookup"><span data-stu-id="4e91d-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="4e91d-118">步驟3：列出網站的檢視者</span><span class="sxs-lookup"><span data-stu-id="4e91d-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="4e91d-119">決定與獨立小組網站檢視者對應的一組使用者帳戶，其可檢視網站中儲存的資源，但不能加以修改或直接在其內容上共同作業。</span><span class="sxs-lookup"><span data-stu-id="4e91d-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="4e91d-120">如果您是透過 Microsoft 365 管理使用者帳戶和群組，且想要使用 PowerShell，請建立其 Upn 的清單。</span><span class="sxs-lookup"><span data-stu-id="4e91d-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="4e91d-121">如果有大量網站成員，您可以將 UPN 清單儲存在文字檔中，並使用單一 PowerShell 命令全部新增。</span><span class="sxs-lookup"><span data-stu-id="4e91d-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="4e91d-122">網站的檢視者可能包括管理階層、法律顧問或各部門的專案關係人。</span><span class="sxs-lookup"><span data-stu-id="4e91d-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="4e91d-123">步驟4：在 Azure AD 中建立網站的三個存取群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="4e91d-124">您需要在 Azure AD 中建立下列存取群組：</span><span class="sxs-lookup"><span data-stu-id="4e91d-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="4e91d-125">網站管理員 (其中包含步驟 1 的清單)</span><span class="sxs-lookup"><span data-stu-id="4e91d-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="4e91d-126">網站成員 (其中包含步驟 2 的清單)</span><span class="sxs-lookup"><span data-stu-id="4e91d-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="4e91d-127">網站檢視者 (其中包含步驟 3 的清單)</span><span class="sxs-lookup"><span data-stu-id="4e91d-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="4e91d-128">在您的瀏覽器中，移至 Azure 入口網站 ([https://portal.azure.com](https://portal.azure.com))，並以已獲派使用者管理管理員或公司系統管理員角色的帳戶認證登入。</span><span class="sxs-lookup"><span data-stu-id="4e91d-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="4e91d-129">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="4e91d-130">在 [群組 - 所有群組]\*\*\*\* 刀鋒視窗中，按一下 [+ 新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="4e91d-131">在 [新增群組]\*\*\*\* 刀鋒視窗中：</span><span class="sxs-lookup"><span data-stu-id="4e91d-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="4e91d-132">在 [群組類型]\*\*\*\* 中選取 [安全性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="4e91d-133">在 [名稱]\*\*\*\* 中鍵入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="4e91d-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="4e91d-134">在 [群組描述]\*\*\*\* 中鍵入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="4e91d-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="4e91d-135">在 [成員資格類型]\*\*\*\* 中選取 [已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="4e91d-136">按一下 [建立]\*\*\*\*，然後關閉 [群組]\*\*\*\* 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="4e91d-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="4e91d-137">針對其他群組重複步驟 3 至 5。</span><span class="sxs-lookup"><span data-stu-id="4e91d-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4e91d-138">您需要使用 Azure 入口網站來建立群組，以便其啟用 Office 功能。</span><span class="sxs-lookup"><span data-stu-id="4e91d-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="4e91d-139">如果您後來將 SharePoint Online 獨立網站設定為高度機密網站，其使用「Azure 資訊保護」標籤來加密檔案並將權限指派給特定群組，則必須在啟用 Office 功能的情況下建立允許的群組。</span><span class="sxs-lookup"><span data-stu-id="4e91d-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="4e91d-140">建立 Azure AD 群組之後，您就無法變更其 Office 功能設定。</span><span class="sxs-lookup"><span data-stu-id="4e91d-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="4e91d-141">以下是您的最終設定，其具有三個網站存取群組。</span><span class="sxs-lookup"><span data-stu-id="4e91d-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![用於部署獨立 SharePoint Online 網站的三個存取群組。](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="4e91d-143">步驟 5。</span><span class="sxs-lookup"><span data-stu-id="4e91d-143">Step 5.</span></span> <span data-ttu-id="4e91d-144">將使用者帳戶新增至存取群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="4e91d-145">在此步驟中進行以下動作：</span><span class="sxs-lookup"><span data-stu-id="4e91d-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="4e91d-146">將步驟 1 的使用者清單新增至網站管理員存取群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="4e91d-147">將步驟 2 的使用者清單新增至網站成員存取群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="4e91d-148">將步驟 3 的使用者清單新增至網站檢視者存取群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="4e91d-149">如果您是透過 Active Directory 網域服務（AD DS）來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將使用者新增至適當的訪問群組，並等候 Microsoft 365 訂閱同步處理。</span><span class="sxs-lookup"><span data-stu-id="4e91d-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="4e91d-150">如果您是透過 Office 365 管理使用者帳戶和群組，您可使用 Microsoft 365 系統管理中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4e91d-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="4e91d-151">如果任何存取群組有重複的群組名稱，您應該使用 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="4e91d-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="4e91d-152">在 Microsoft 365 系統管理中心，使用已指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的使用者帳戶和群組新增至適當的存取群組。</span><span class="sxs-lookup"><span data-stu-id="4e91d-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="4e91d-153">在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4e91d-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="4e91d-154">接下來，使用下列命令區塊將個別的使用者帳戶新增到存取群組：</span><span class="sxs-lookup"><span data-stu-id="4e91d-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="4e91d-155">如果您將任何存取群組的使用者帳戶 UPN 儲存在文字檔中，即可使用下列 PowerShell 命令區塊一次新增所有 UPN：</span><span class="sxs-lookup"><span data-stu-id="4e91d-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="4e91d-156">在 PowerShell 中，使用下列命令區塊將個別的群組新增至存取群組：</span><span class="sxs-lookup"><span data-stu-id="4e91d-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="4e91d-157">結果應該如下所述︰</span><span class="sxs-lookup"><span data-stu-id="4e91d-157">The results should be the following:</span></span>
  
- <span data-ttu-id="4e91d-158">網站管理員 Azure AD 群組包含網站管理員使用者帳戶或群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="4e91d-159">網站成員 Azure AD 群組包含網站成員使用者帳戶或群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="4e91d-160">網站檢視者 Azure AD 群組包含只能檢視網站內容的使用者帳戶或群組</span><span class="sxs-lookup"><span data-stu-id="4e91d-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="4e91d-161">使用 Microsoft 365 系統管理中心或下列 PowerShell 命令區塊來驗證每個存取群組的群組成員清單：</span><span class="sxs-lookup"><span data-stu-id="4e91d-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="4e91d-162">以下是您的最終設定，其中有三個網站存取群組填入了使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="4e91d-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![三個存取群組填入了使用者帳戶。](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="4e91d-164">第 2 階段：建立及設定獨立的小組網站</span><span class="sxs-lookup"><span data-stu-id="4e91d-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="4e91d-165">在這個階段中，您會建立獨立的 SharePoint Online 網站，並設定預設 SharePoint Online 權限等級的權限，以使用新的 Azure AD 型存取群組。</span><span class="sxs-lookup"><span data-stu-id="4e91d-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="4e91d-166">依預設，新的小組網站包含 Microsoft 365 群組和其他相關資源，但在此情況下，我們會建立沒有 Microsoft 365 群組的小組網站。</span><span class="sxs-lookup"><span data-stu-id="4e91d-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="4e91d-167">這可讓您完全透過 SharePoint 維護許可權。</span><span class="sxs-lookup"><span data-stu-id="4e91d-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="4e91d-168">首先，使用下列步驟建立 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="4e91d-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="4e91d-169">使用也用來管理 SharePoint Online 小組網站（SharePoint Online 系統管理員）的帳戶登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="4e91d-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="4e91d-170">如需說明，請參閱[在何處登入 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="4e91d-170">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4e91d-171">在 Microsoft 365 系統管理中心的 [系統**管理中心**] 下，按一下 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="4e91d-172">在 SharePoint 系統管理中心中，展開 [**網站**]，然後按一下 [**即時網頁**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="4e91d-173">按一下 [**建立**]，然後選擇 [**其他選項**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="4e91d-174">在 [**選擇範本**] 清單中，選擇 [**小組網站**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="4e91d-175">在 [網站名稱]\*\*\*\* 中，鍵入小組網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="4e91d-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="4e91d-176">在 [**主要管理員**] 中，輸入您用來登入的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4e91d-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="4e91d-177">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-177">Click **Finish**.</span></span>
    
<span data-ttu-id="4e91d-178">接下來，從新的 SharePoint Online 小組網站，設定權限。</span><span class="sxs-lookup"><span data-stu-id="4e91d-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="4e91d-179">在工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="4e91d-180">在 [**網站共用**] 底下，按一下 [**變更成員可以共用的方式**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="4e91d-181">選擇 [**唯一的網站擁有者可以共用檔案、資料夾及網站**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="4e91d-182">將 [**允許存取要求**關閉] 設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="4e91d-183">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="4e91d-184">在 [**許可權**] 窗格中，按一下 [**高級許可權設定**]。</span><span class="sxs-lookup"><span data-stu-id="4e91d-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="4e91d-185">在 [權限]\*\*\*\* 瀏覽器索引標籤中，按一下清單中的 [\<網站名稱> 成員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="4e91d-186">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="4e91d-187">在 [共用]\*\*\*\* 對話方塊中，鍵入網站成員存取群組的名稱並加以選取，然後按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="4e91d-188">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4e91d-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="4e91d-189">按一下清單中 [\<網站名稱> 擁有者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="4e91d-190">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="4e91d-191">在 [共用]\*\*\*\* 對話方塊中，鍵入網站管理員存取群組的名稱並加以選取，然後按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="4e91d-192">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4e91d-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="4e91d-193">按一下清單中 [\<網站名稱> 訪客]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="4e91d-194">在 [人員與群組]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="4e91d-195">在 [共用]\*\*\*\* 對話方塊中，鍵入網站檢視者存取群組的名稱並加以選取，然後按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e91d-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="4e91d-196">關閉 [權限]\*\*\*\* 瀏覽器索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4e91d-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="4e91d-197">這些使用權限設定的結果是：</span><span class="sxs-lookup"><span data-stu-id="4e91d-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="4e91d-198">[\<網站名稱> 擁有者]\*\*\*\* SharePoint 群組包含網站管理員存取群組，其中的所有成員都具有 [完全控制]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="4e91d-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="4e91d-199">[\<網站名稱> 成員]\*\*\*\* SharePoint 群組包含網站成員存取群組，其中的所有成員都具有 [編輯]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="4e91d-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="4e91d-200">[\<網站名稱> 訪客]\*\*\*\* SharePoint 群組包含網站檢視者存取群組，其中的所有成員都具有 [讀取]\*\*\*\* 權限等級。</span><span class="sxs-lookup"><span data-stu-id="4e91d-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="4e91d-201">已停用成員邀請其他成員或非成員要求存取權的功能。</span><span class="sxs-lookup"><span data-stu-id="4e91d-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="4e91d-202">以下是您的最終設定，其中網站有三個 SharePoint 群組設定為使用三個存取群組，而這三個存取群組填入了使用者帳戶或 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="4e91d-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![具有存取群組與使用者帳戶的獨立 SharePoint Online 網站最終設定。](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="4e91d-204">您和網站成員現在可以透過其中一個存取群組的群組成員資格，使用網站的資源來共同作業。</span><span class="sxs-lookup"><span data-stu-id="4e91d-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="4e91d-205">下一步</span><span class="sxs-lookup"><span data-stu-id="4e91d-205">Next step</span></span>

<span data-ttu-id="4e91d-206">當您需要變更網站存取群組成員資格或建立具有自訂權限的文件資料夾時，請參閱[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="4e91d-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4e91d-207">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4e91d-207">See Also</span></span>

[<span data-ttu-id="4e91d-208">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="4e91d-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="4e91d-209">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="4e91d-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="4e91d-210">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="4e91d-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



