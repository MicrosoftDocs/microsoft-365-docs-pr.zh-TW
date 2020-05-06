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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 設計獨立 SharePoint Online 小組網站，包括決定許可權等級、將許可權指派給具有存取群組的使用者，以及嵌套的 Azure AD 群組。
ms.openlocfilehash: 4663a0b9710fc05d0b063a3100d3b5ac223a2161
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034837"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="fdada-103">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="fdada-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="fdada-104">**摘要：** 逐步執行獨立 SharePoint Online 小組網站的設計程式。</span><span class="sxs-lookup"><span data-stu-id="fdada-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="fdada-105">本文將引導您完成建立隔離的 SharePoint Online 小組網站之前必須進行的主要設計決策。</span><span class="sxs-lookup"><span data-stu-id="fdada-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="fdada-106">階段1：判斷您的 SharePoint 群組和許可權等級</span><span class="sxs-lookup"><span data-stu-id="fdada-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="fdada-107">預設會使用下列 SharePoint 群組建立每個 SharePoint Online 小組網站：</span><span class="sxs-lookup"><span data-stu-id="fdada-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="fdada-108">\<網站名稱> 成員</span><span class="sxs-lookup"><span data-stu-id="fdada-108">\<site name> Members</span></span>
    
- <span data-ttu-id="fdada-109">\<網站名稱> 訪客</span><span class="sxs-lookup"><span data-stu-id="fdada-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="fdada-110">\<網站名稱> 擁有者</span><span class="sxs-lookup"><span data-stu-id="fdada-110">\<site name> Owners</span></span>
    
<span data-ttu-id="fdada-111">這些群組是與 Microsoft 365 和 Azure Active Directory （AD）群組分開的，也是指派網站資源之許可權的基礎。</span><span class="sxs-lookup"><span data-stu-id="fdada-111">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="fdada-112">一組特定許可權，可決定 SharePoint 群組的成員可在網站中執行的動作為許可權等級。</span><span class="sxs-lookup"><span data-stu-id="fdada-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="fdada-113">SharePoint Online 小組網站的預設許可權等級有三個： Edit、Read 及 Full control。</span><span class="sxs-lookup"><span data-stu-id="fdada-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="fdada-114">下表顯示 SharePoint 群組的預設關聯，以及指派的許可權等級：</span><span class="sxs-lookup"><span data-stu-id="fdada-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="fdada-115">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="fdada-115">**SharePoint group**</span></span>|<span data-ttu-id="fdada-116">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="fdada-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fdada-117">\<網站名稱> 成員</span><span class="sxs-lookup"><span data-stu-id="fdada-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="fdada-118">編輯</span><span class="sxs-lookup"><span data-stu-id="fdada-118">Edit</span></span>  <br/> |
|<span data-ttu-id="fdada-119">\<網站名稱> 訪客</span><span class="sxs-lookup"><span data-stu-id="fdada-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="fdada-120">讀取</span><span class="sxs-lookup"><span data-stu-id="fdada-120">Read</span></span>  <br/> |
|<span data-ttu-id="fdada-121">\<網站名稱> 擁有者</span><span class="sxs-lookup"><span data-stu-id="fdada-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="fdada-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="fdada-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="fdada-123">**最佳作法：** 您可以建立額外的 SharePoint 群組和許可權層級。</span><span class="sxs-lookup"><span data-stu-id="fdada-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="fdada-124">不過，我們建議您針對隔離的 SharePoint Online 網站使用預設的 SharePoint 群組和許可權層級。</span><span class="sxs-lookup"><span data-stu-id="fdada-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="fdada-125">以下是預設的 SharePoint 群組和許可權層級。</span><span class="sxs-lookup"><span data-stu-id="fdada-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![SharePoint Online 網站的預設 SharePoint 群組和許可權層級。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="fdada-127">階段2：將許可權指派給具有存取群組的使用者</span><span class="sxs-lookup"><span data-stu-id="fdada-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="fdada-128">您可以將許可權指派給使用者，方法是將其使用者帳戶（或使用者帳戶所屬的 Microsoft 365 或 Azure AD 群組）新增至 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-128">You can assign permissions to users by adding their user account, or an Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="fdada-129">一旦新增，使用者帳戶（透過 Microsoft 365 或 Azure AD 群組中的成員資格直接或間接）會被指派與 SharePoint 群組相關聯的許可權等級。</span><span class="sxs-lookup"><span data-stu-id="fdada-129">Once added, the user accounts, either directly or indirectly via membership in an Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="fdada-130">使用預設的 SharePoint 群組為範例：</span><span class="sxs-lookup"><span data-stu-id="fdada-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="fdada-131">可包含使用者帳戶和群組的\*\* \<網站名稱> 成員**SharePoint 群組的成員會被指派 [**編輯\*\*] 許可權等級。</span><span class="sxs-lookup"><span data-stu-id="fdada-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="fdada-132">\*\*網站名稱的成員> 訪客 SharePoint 群組，其中可以包含使用者帳戶和群組，都已獲指派「讀取」許可權等級。 \< \*\* **Read**</span><span class="sxs-lookup"><span data-stu-id="fdada-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="fdada-133">網站名稱> 擁有者 SharePoint 群組的成員，可包含使用者帳戶和群組，都已獲指派「**完全控制**」許可權層級。 \*\* \< \*\*</span><span class="sxs-lookup"><span data-stu-id="fdada-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="fdada-134">**最佳作法：** 雖然您可以透過個別使用者帳戶管理許可權，但建議您改用單一 Azure AD 群組（稱為存取群組）。</span><span class="sxs-lookup"><span data-stu-id="fdada-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="fdada-135">這可簡化透過存取群組成員資格的版權管理，而不是管理每個 SharePoint 群組的使用者帳戶清單。</span><span class="sxs-lookup"><span data-stu-id="fdada-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="fdada-136">Microsoft 365 的 Azure AD 群組不同于 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-136">Azure AD groups for Microsoft 365 are different than Microsoft 365 groups.</span></span> <span data-ttu-id="fdada-137">Azure AD 群組會顯示在 Microsoft 365 系統管理中心中，其**類型**設為 [**安全性**]，而且沒有電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fdada-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="fdada-138">Azure AD 群組可在下列專案中管理：</span><span class="sxs-lookup"><span data-stu-id="fdada-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="fdada-139">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="fdada-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="fdada-140">這些是在您的內部部署 AD DS 基礎結構中建立並同步處理至您的 Microsoft 365 訂閱的群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="fdada-141">在 Microsoft 365 系統管理中心中，這些群組的**狀態**為 [已**與 active directory 同步處理**]。</span><span class="sxs-lookup"><span data-stu-id="fdada-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="fdada-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="fdada-142">Office 365</span></span>
    
    <span data-ttu-id="fdada-143">這些是使用 Microsoft 365 系統管理中心、Azure 入口網站或 Microsoft PowerShell 建立的群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="fdada-144">在 Microsoft 365 系統管理中心中，這些群組的**狀態**為**雲端**。</span><span class="sxs-lookup"><span data-stu-id="fdada-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="fdada-145">**最佳作法：** 如果您使用的是 AD DS 內部部署並與 Microsoft 365 訂閱進行同步處理，請使用 AD DS 執行您的使用者和群組管理。</span><span class="sxs-lookup"><span data-stu-id="fdada-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="fdada-146">針對隔離 SharePoint 線上小組網站，建議的群組結構如下所示：</span><span class="sxs-lookup"><span data-stu-id="fdada-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="fdada-147">**SharePoint 群組**</span><span class="sxs-lookup"><span data-stu-id="fdada-147">**SharePoint group**</span></span>|<span data-ttu-id="fdada-148">**Azure AD 型訪問群組**</span><span class="sxs-lookup"><span data-stu-id="fdada-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="fdada-149">**權限等級**</span><span class="sxs-lookup"><span data-stu-id="fdada-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fdada-150">\<網站名稱> 成員</span><span class="sxs-lookup"><span data-stu-id="fdada-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="fdada-151">\<網站名稱> 成員</span><span class="sxs-lookup"><span data-stu-id="fdada-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="fdada-152">編輯</span><span class="sxs-lookup"><span data-stu-id="fdada-152">Edit</span></span>  <br/> |
|<span data-ttu-id="fdada-153">\<網站名稱> 訪客</span><span class="sxs-lookup"><span data-stu-id="fdada-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="fdada-154">\<網站名稱> 檢視器</span><span class="sxs-lookup"><span data-stu-id="fdada-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="fdada-155">讀取</span><span class="sxs-lookup"><span data-stu-id="fdada-155">Read</span></span>  <br/> |
|<span data-ttu-id="fdada-156">\<網站名稱> 擁有者</span><span class="sxs-lookup"><span data-stu-id="fdada-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="fdada-157">\<網站名稱> 系統管理員</span><span class="sxs-lookup"><span data-stu-id="fdada-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="fdada-158">完全控制</span><span class="sxs-lookup"><span data-stu-id="fdada-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="fdada-159">**最佳作法：** 雖然您可以使用 Microsoft 365 或 Azure AD 群組做為 SharePoint 群組的成員，我們還是建議您使用 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-159">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="fdada-160">Azure AD 群組（透過 AD DS 或 Microsoft 365 管理）可讓您更靈活地使用嵌套群組來指派許可權。</span><span class="sxs-lookup"><span data-stu-id="fdada-160">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="fdada-161">以下是設定為使用 Azure AD 型存取群組的預設 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![使用訪問群組做為預設 SharePoint 線上網站群組的成員。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="fdada-163">當您設計三個訪問群組時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="fdada-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="fdada-164">在 [ \*\* \<網站名稱]> Admins\*\* access 群組中應該只有少數幾個成員，對應于管理小組網站的少數 SharePoint Online 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="fdada-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="fdada-165">您的網站成員大部分位於\*\* \<網站名稱> 成員**或** \<網站名稱> 查看\*\*器存取群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="fdada-166">因為\*\* \<網站名稱> 成員\*\*存取群組中的網站成員具備刪除或修改網站中資源的能力，所以請謹慎考慮其成員資格。</span><span class="sxs-lookup"><span data-stu-id="fdada-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="fdada-167">若有疑問，請將網站成員新增至\*\* \<網站名稱> 查看\*\*器存取群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="fdada-168">以下是名為 ProjectX 之隔離網站的 SharePoint 群組和存取群組的範例。</span><span class="sxs-lookup"><span data-stu-id="fdada-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![使用名為 ProjectX SharePoint Online 網站的存取群組的範例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="fdada-170">階段3：使用嵌套 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="fdada-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="fdada-171">對於僅限少數人員的專案，新增至網站 SharePoint 群組的單一層級 Azure AD 訪問群組會適合大多數案例。</span><span class="sxs-lookup"><span data-stu-id="fdada-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="fdada-172">不過，如果您有大量人員，而這些人已經是已建立的 Azure AD 群組的成員，您可以使用嵌套群組或包含其他群組的群組做為成員，更輕鬆地指派 SharePoint 許可權。</span><span class="sxs-lookup"><span data-stu-id="fdada-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="fdada-173">例如，您想要建立一個隔離的 SharePoint 線上小組網站，以共同共同作業的銷售、行銷、工程、法律和支援部門的主管，以及那些部門已經擁有 executive 使用者帳戶成員資格的群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="fdada-174">不需要為新的網站成員建立新的群組，並將所有個人的執行使用者帳戶放在新的群組中，將每個部門的現有 executive 群組放在新群組中。</span><span class="sxs-lookup"><span data-stu-id="fdada-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="fdada-175">如果您在多個組織之間共用 Microsoft 365 訂閱，則組織的隔離網站的單一群組成員資格可能會因為使用者帳戶的數量非常困難而難於管理。</span><span class="sxs-lookup"><span data-stu-id="fdada-175">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="fdada-176">在此情況下，您可以針對包含組織內群組的每個組織，使用嵌套 Azure AD 群組來管理許可權。</span><span class="sxs-lookup"><span data-stu-id="fdada-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="fdada-177">若要使用嵌套 Azure AD 群組：</span><span class="sxs-lookup"><span data-stu-id="fdada-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="fdada-178">識別或建立 Azure AD 群組，其中會包含使用者帳戶，並將適當的使用者帳戶新增為成員。</span><span class="sxs-lookup"><span data-stu-id="fdada-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="fdada-179">建立將包含其他 Azure AD 群組的容器 Azure AD 型訪問群組，並將這些群組新增為成員。</span><span class="sxs-lookup"><span data-stu-id="fdada-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="fdada-180">若要取得容器存取群組的適當存取層級，請找出 SharePoint 群組和對應的許可權等級。</span><span class="sxs-lookup"><span data-stu-id="fdada-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fdada-181">您無法使用嵌套的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="fdada-181">You cannot use nested Microsoft 365 groups.</span></span> 
  
<span data-ttu-id="fdada-182">以下是 ProjectX 成員存取群組的嵌套 Azure AD 群組範例。</span><span class="sxs-lookup"><span data-stu-id="fdada-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![在 ProjectX 網站的成員存取群組中使用嵌套存取群組的範例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="fdada-184">因為「調研」、「工程」和「專案負責人」小組中的所有使用者帳戶都是網站成員，所以將其 Azure AD 群組新增至 ProjectX 成員存取群組會比較容易。</span><span class="sxs-lookup"><span data-stu-id="fdada-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="fdada-185">後續步驟</span><span class="sxs-lookup"><span data-stu-id="fdada-185">Next step</span></span>

<span data-ttu-id="fdada-186">當您準備好在實際執行中建立和設定隔離的網站時，請參閱[部署隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="fdada-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fdada-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fdada-187">See Also</span></span>

[<span data-ttu-id="fdada-188">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="fdada-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="fdada-189">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="fdada-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="fdada-190">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="fdada-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



