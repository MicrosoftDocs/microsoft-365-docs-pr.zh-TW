---
title: 設計獨立的 SharePoint Online 小組網站
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
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 摘要： 逐步執行獨立的 SharePoint Online 小組網站的設計程序。
ms.openlocfilehash: f03df1f99650f458dd9df2c9e561decf491c3011
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083203"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="7cb81-103">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="7cb81-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="7cb81-104">**摘要：** 獨立的 SharePoint Online 小組網站的設計程序步驟。</span><span class="sxs-lookup"><span data-stu-id="7cb81-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="7cb81-105">本文會引導您完成建立隔離的 SharePoint Online 小組網站之前，您必須進行的關鍵設計決策。</span><span class="sxs-lookup"><span data-stu-id="7cb81-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="7cb81-106">階段 1： 判斷您的 SharePoint 群組和權限等級</span><span class="sxs-lookup"><span data-stu-id="7cb81-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="7cb81-107">使用下列 SharePoint 群組建立預設每個 SharePoint Online 小組網站：</span><span class="sxs-lookup"><span data-stu-id="7cb81-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="7cb81-108">\<站台名稱 # C0 成員</span><span class="sxs-lookup"><span data-stu-id="7cb81-108">\<site name> Members</span></span>
    
- <span data-ttu-id="7cb81-109">\<站台名稱 # C0 訪客</span><span class="sxs-lookup"><span data-stu-id="7cb81-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="7cb81-110">\<站台名稱 # C0 擁有者</span><span class="sxs-lookup"><span data-stu-id="7cb81-110">\<site name> Owners</span></span>
    
<span data-ttu-id="7cb81-111">這些群組不同 Office 365 和 Azure Active Directory (AD) 群組，並會指派的資源之網站的權限的基準。</span><span class="sxs-lookup"><span data-stu-id="7cb81-111">These groups are separate from Office 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="7cb81-112">會決定 SharePoint 群組的成員可以執行網站中的特定權限集合是權限等級。</span><span class="sxs-lookup"><span data-stu-id="7cb81-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="7cb81-113">根據預設，適用於 SharePoint Online 小組網站有三個權限層級： 編輯 」、 「 讀取和 「 完全控制。</span><span class="sxs-lookup"><span data-stu-id="7cb81-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="7cb81-114">下表顯示預設相互關聯的 SharePoint 群組和指派的權限等級：</span><span class="sxs-lookup"><span data-stu-id="7cb81-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="7cb81-115">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="7cb81-115">**SharePoint group**</span></span>|<span data-ttu-id="7cb81-116">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="7cb81-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7cb81-117">\<站台名稱 # C0 成員</span><span class="sxs-lookup"><span data-stu-id="7cb81-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="7cb81-118">編輯</span><span class="sxs-lookup"><span data-stu-id="7cb81-118">Edit</span></span>  <br/> |
|<span data-ttu-id="7cb81-119">\<站台名稱 # C0 訪客</span><span class="sxs-lookup"><span data-stu-id="7cb81-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="7cb81-120">讀取</span><span class="sxs-lookup"><span data-stu-id="7cb81-120">Read</span></span>  <br/> |
|<span data-ttu-id="7cb81-121">\<站台名稱 # C0 擁有者</span><span class="sxs-lookup"><span data-stu-id="7cb81-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="7cb81-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="7cb81-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="7cb81-123">**最佳作法：** 您可以建立其他的 SharePoint 群組和權限等級。</span><span class="sxs-lookup"><span data-stu-id="7cb81-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="7cb81-124">不過，建議使用的預設 SharePoint 群組和權限層級的隔離 SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="7cb81-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="7cb81-125">以下是預設 SharePoint 群組和權限等級。</span><span class="sxs-lookup"><span data-stu-id="7cb81-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![預設 SharePoint 群組和權限層級的 SharePoint Online 網站。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="7cb81-127">階段 2： 使用存取群組將權限指派給使用者</span><span class="sxs-lookup"><span data-stu-id="7cb81-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="7cb81-128">您可以藉由新增使用者帳戶或使用者帳戶為 SharePoint 群組的成員的 Office 365 或 Azure AD 群組來指派給使用者的權限。</span><span class="sxs-lookup"><span data-stu-id="7cb81-128">You can assign permissions to users by adding their user account, or an Office 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="7cb81-129">新增後，Office 365 使用者帳戶，或是直接或間接透過 Office 365 或 Azure AD 群組的成員資格，指派相關聯的 SharePoint 群組的權限等級。</span><span class="sxs-lookup"><span data-stu-id="7cb81-129">Once added, the Office 365 user accounts, either directly or indirectly via membership in an Office 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="7cb81-130">使用預設 SharePoint 群組做為範例：</span><span class="sxs-lookup"><span data-stu-id="7cb81-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="7cb81-131">屬於**\<網站名稱> 成員**SharePoint 群組，其中可以包含使用者帳戶和群組、 指派的**編輯**權限層級</span><span class="sxs-lookup"><span data-stu-id="7cb81-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="7cb81-132">屬於**\<網站名稱> 訪客**SharePoint 群組，其中可以包含使用者帳戶和群組、 指派**讀取**權限等級</span><span class="sxs-lookup"><span data-stu-id="7cb81-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="7cb81-133">屬於**\<網站名稱> 擁有者**SharePoint 群組，其中可以包含使用者帳戶和群組、 指派 [**完全控制**」 權限等級</span><span class="sxs-lookup"><span data-stu-id="7cb81-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="7cb81-134">**最佳作法：** 雖然您可以管理透過個別使用者帳戶的權限，我們建議您使用單一 Azure AD 群組，而是稱為存取群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="7cb81-135">這可簡化透過在 [存取] 群組的成員資格的權限管理，而不是管理清單中的使用者帳戶為每個 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="7cb81-136">Azure AD 群組的 Office 365 是不同於 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-136">Azure AD groups for Office 365 are different than Office 365 groups.</span></span> <span data-ttu-id="7cb81-137">Azure AD 群組出現在其**類型**設為 [**安全性**與 Microsoft 365 系統管理中心中，而且不具有電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7cb81-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="7cb81-138">您可以管理 azure AD 群組內：</span><span class="sxs-lookup"><span data-stu-id="7cb81-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="7cb81-139">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="7cb81-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="7cb81-140">這些是您內部部署中已建立的群組 AD DS 基礎結構和同步處理至 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7cb81-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Office 365 subscription.</span></span> <span data-ttu-id="7cb81-141">在 Microsoft 365 系統管理中心中，這些群組會有**與 active directory Synched\*\*\*\*狀態**。</span><span class="sxs-lookup"><span data-stu-id="7cb81-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="7cb81-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="7cb81-142">Office 365</span></span>
    
    <span data-ttu-id="7cb81-143">以下是使用 Microsoft 365 系統管理中心，在 Azure 入口網站或 Microsoft PowerShell 已建立的群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="7cb81-144">在 Microsoft 365 系統管理中心中，這些群組會有**雲端**的**狀態**。</span><span class="sxs-lookup"><span data-stu-id="7cb81-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="7cb81-145">**最佳作法：** 如果您是使用 AD DS 內部，並且同步處理與您的 Office 365 訂閱，執行您的使用者和群組管理與 AD DS。</span><span class="sxs-lookup"><span data-stu-id="7cb81-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Office 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="7cb81-146">隔離的 SharePoint Online 小組網站，建議的群組結構看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="7cb81-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="7cb81-147">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="7cb81-147">**SharePoint group**</span></span>|<span data-ttu-id="7cb81-148">**Azure AD 為基礎的存取群組**</span><span class="sxs-lookup"><span data-stu-id="7cb81-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="7cb81-149">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="7cb81-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7cb81-150">\<站台名稱 # C0 成員</span><span class="sxs-lookup"><span data-stu-id="7cb81-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="7cb81-151">\<站台名稱 # C0 成員</span><span class="sxs-lookup"><span data-stu-id="7cb81-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="7cb81-152">編輯</span><span class="sxs-lookup"><span data-stu-id="7cb81-152">Edit</span></span>  <br/> |
|<span data-ttu-id="7cb81-153">\<站台名稱 # C0 訪客</span><span class="sxs-lookup"><span data-stu-id="7cb81-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="7cb81-154">\<站台名稱 # C0 檢視者</span><span class="sxs-lookup"><span data-stu-id="7cb81-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="7cb81-155">讀取</span><span class="sxs-lookup"><span data-stu-id="7cb81-155">Read</span></span>  <br/> |
|<span data-ttu-id="7cb81-156">\<站台名稱 # C0 擁有者</span><span class="sxs-lookup"><span data-stu-id="7cb81-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="7cb81-157">\<站台名稱 # C0 系統管理員</span><span class="sxs-lookup"><span data-stu-id="7cb81-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="7cb81-158">完全控制</span><span class="sxs-lookup"><span data-stu-id="7cb81-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="7cb81-159">**最佳作法：** 雖然您可以使用 Office 365 或 Azure AD 群組作為 SharePoint 群組的成員，我們建議您使用 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-159">**Best practice:** Although you can use either Office 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="7cb81-160">Azure AD 群組、 管理透過 AD DS 或 Office 365，讓您更多彈性，可使用巢狀的群組指派權限。</span><span class="sxs-lookup"><span data-stu-id="7cb81-160">Azure AD groups, managed either through AD DS or Office 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="7cb81-161">以下是預設設定為使用 Azure AD 為基礎的存取群組的 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![使用存取群組作為預設 SharePoint Online 網站群組的成員。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="7cb81-163">在設計時三個存取群組，請謹記下列事項：</span><span class="sxs-lookup"><span data-stu-id="7cb81-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="7cb81-164">應該只有幾個成員中的**\<網站名稱> Admins**存取群組，對應至數目更少的 SharePoint Online 系統管理員負責管理小組網站。</span><span class="sxs-lookup"><span data-stu-id="7cb81-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="7cb81-165">大部分的網站成員位於**\<網站名稱> 成員**或**\<網站名稱> Viewer**存取群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="7cb81-166">因為網站中的成員**\<網站名稱> 成員**存取群組已刪除或修改網站中的資源，請仔細考慮其成員資格的能力。</span><span class="sxs-lookup"><span data-stu-id="7cb81-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="7cb81-167">有疑問，新增至網站成員**\<網站名稱> Viewer**存取群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="7cb81-168">以下是範例為名為 ProjectX 隔離網站的存取群組與 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![SharePoint Online 網站使用存取群組的範例會為名為 ProjectX。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="7cb81-170">階段 3： 使用巢狀 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="7cb81-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="7cb81-171">受限於數目更少的人員的專案，Azure AD 為基礎的存取群組新增至 SharePoint 群組網站的單一層級可容納大部分的案例。</span><span class="sxs-lookup"><span data-stu-id="7cb81-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="7cb81-172">不過，如果您有大量的人員和那些人員已經成員建立 Azure AD 群組，您可以更輕鬆地指派 SharePoint 權限使用巢狀的群組或包含其他群組作為成員的群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="7cb81-173">例如，您要建立隔離的 SharePoint online 小組網站的高階主管的銷售、 行銷、 工程、 法律的共同作業與支援部門與那些部門已經自己的群組，以高階主管的使用者帳戶成員資格。</span><span class="sxs-lookup"><span data-stu-id="7cb81-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="7cb81-174">而不是新的網站成員建立新的群組，並將放中，所有的個別高階主管的使用者帳戶會置於新群組中每個部門的現有高階主管群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="7cb81-175">如果您要共用的多個組織之間的 Office 365 訂用帳戶，單一層級的隔離的網站，為組織的群組成員資格可能變得很難管理由於使用者帳戶的真正數目。</span><span class="sxs-lookup"><span data-stu-id="7cb81-175">If you are sharing an Office 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="7cb81-176">在此情況下，您可以使用每個組織的 Azure AD 群組包含要管理權限的群組在其組織內的巢狀。</span><span class="sxs-lookup"><span data-stu-id="7cb81-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="7cb81-177">若要使用巢狀 Azure AD 群組：</span><span class="sxs-lookup"><span data-stu-id="7cb81-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="7cb81-178">識別或建立 Azure AD 群組，包含使用者帳戶，並將適當的使用者帳戶新增為成員。</span><span class="sxs-lookup"><span data-stu-id="7cb81-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="7cb81-179">建立容器 Azure AD 為基礎的存取群組，包含其他 Azure AD 群組，並將這些群組新增為成員。</span><span class="sxs-lookup"><span data-stu-id="7cb81-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="7cb81-180">適當層級的存取容器存取群組，找出對應的權限等級與 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7cb81-181">您無法使用巢狀的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-181">You cannot use nested Office 365 groups.</span></span> 
  
<span data-ttu-id="7cb81-182">以下是 [ProjectX 成員存取群組的範例中的巢狀的 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![針對 ProjectX 網站成員存取群組使用巢狀的存取群組的範例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="7cb81-184">因為所有的參考資料、 工程和專案中的使用者帳戶時會導致 teams 旨在為網站成員，很容易將其 Azure AD 群組新增至 ProjectX 成員存取群組。</span><span class="sxs-lookup"><span data-stu-id="7cb81-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="7cb81-185">下一步</span><span class="sxs-lookup"><span data-stu-id="7cb81-185">Next step</span></span>

<span data-ttu-id="7cb81-186">當您準備好要建立及設定隔離的網站在生產環境中時，請參閱[部署隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="7cb81-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7cb81-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7cb81-187">See Also</span></span>

[<span data-ttu-id="7cb81-188">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="7cb81-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="7cb81-189">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="7cb81-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="7cb81-190">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="7cb81-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



