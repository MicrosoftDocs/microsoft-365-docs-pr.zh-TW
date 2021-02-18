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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 設計獨立 SharePoint Online 小組網站，包括決定許可權等級、將許可權指派給具有存取群組的使用者，以及嵌套的 Azure AD 群組。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288332"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="6eea3-103">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="6eea3-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6eea3-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="6eea3-104">**Applies to**</span></span>
- [<span data-ttu-id="6eea3-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="6eea3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6eea3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6eea3-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="6eea3-107">**摘要：** 逐步執行獨立 SharePoint Online 小組網站的設計程式。</span><span class="sxs-lookup"><span data-stu-id="6eea3-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="6eea3-108">本文將引導您完成建立隔離的 SharePoint Online 小組網站之前必須進行的主要設計決策。</span><span class="sxs-lookup"><span data-stu-id="6eea3-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="6eea3-109">階段1：判斷您的 SharePoint 群組和許可權等級</span><span class="sxs-lookup"><span data-stu-id="6eea3-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="6eea3-110">預設會使用下列 SharePoint 群組建立每個 SharePoint Online 小組網站：</span><span class="sxs-lookup"><span data-stu-id="6eea3-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="6eea3-111">\<site name> 成員</span><span class="sxs-lookup"><span data-stu-id="6eea3-111">\<site name> Members</span></span>

- <span data-ttu-id="6eea3-112">\<site name> 遊客</span><span class="sxs-lookup"><span data-stu-id="6eea3-112">\<site name> Visitors</span></span>

- <span data-ttu-id="6eea3-113">\<site name> 業主</span><span class="sxs-lookup"><span data-stu-id="6eea3-113">\<site name> Owners</span></span>

<span data-ttu-id="6eea3-114">這些群組與 Microsoft 365 和 Azure Active Directory (AD) 群組不同，也是指派網站資源之許可權的基礎。</span><span class="sxs-lookup"><span data-stu-id="6eea3-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="6eea3-115">一組特定許可權，可決定 SharePoint 群組的成員可在網站中執行的動作為許可權等級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-115">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="6eea3-116">SharePoint Online 小組網站的預設許可權等級有三個： Edit、Read 及 Full control。</span><span class="sxs-lookup"><span data-stu-id="6eea3-116">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="6eea3-117">下表顯示 SharePoint 群組的預設關聯，以及指派的許可權等級：</span><span class="sxs-lookup"><span data-stu-id="6eea3-117">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="6eea3-118">SharePoint 群組</span><span class="sxs-lookup"><span data-stu-id="6eea3-118">SharePoint group</span></span>|<span data-ttu-id="6eea3-119">權限層級</span><span class="sxs-lookup"><span data-stu-id="6eea3-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="6eea3-120">\<site name> 成員</span><span class="sxs-lookup"><span data-stu-id="6eea3-120">\<site name> Members</span></span>|<span data-ttu-id="6eea3-121">編輯</span><span class="sxs-lookup"><span data-stu-id="6eea3-121">Edit</span></span>|
|<span data-ttu-id="6eea3-122">\<site name> 遊客</span><span class="sxs-lookup"><span data-stu-id="6eea3-122">\<site name> Visitors</span></span>|<span data-ttu-id="6eea3-123">讀取</span><span class="sxs-lookup"><span data-stu-id="6eea3-123">Read</span></span>|
|<span data-ttu-id="6eea3-124">\<site name> 業主</span><span class="sxs-lookup"><span data-stu-id="6eea3-124">\<site name> Owners</span></span>|<span data-ttu-id="6eea3-125">完全控制</span><span class="sxs-lookup"><span data-stu-id="6eea3-125">Full control</span></span>|
|

 <span data-ttu-id="6eea3-126">**最佳作法：** 您可以建立額外的 SharePoint 群組和許可權層級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-126">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="6eea3-127">不過，我們建議您針對隔離的 SharePoint Online 網站使用預設的 SharePoint 群組和許可權層級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-127">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="6eea3-128">以下是預設的 SharePoint 群組和許可權層級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-128">Here are the default SharePoint groups and permission levels.</span></span>

![SharePoint Online 網站的預設 SharePoint 群組和許可權層級。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="6eea3-130">階段2：將許可權指派給具有存取群組的使用者</span><span class="sxs-lookup"><span data-stu-id="6eea3-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="6eea3-131">您可以將許可權指派給使用者，方法是將其使用者帳戶或使用者帳戶所屬的 Microsoft 365 或 Azure AD 群組新增至 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="6eea3-132">一旦新增，使用者帳戶（透過 Microsoft 365 或 Azure AD 群組中的成員資格直接或間接）會被指派與 SharePoint 群組相關聯的許可權等級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="6eea3-133">使用預設的 SharePoint 群組為範例：</span><span class="sxs-lookup"><span data-stu-id="6eea3-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="6eea3-134">**\<site name> 成員** SharePoint 群組（可以包含使用者帳戶和群組）的成員會被指派「**編輯**」許可權等級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="6eea3-135">**\<site name> 訪客** SharePoint 群組的成員（可以包含使用者帳戶和群組）會獲指派「**讀取**」許可權等級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="6eea3-136">**\<site name> 擁有** 者 SharePoint 群組的成員（可以包含使用者帳戶和群組）會獲指派「**完全控制**」許可權層級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="6eea3-137">**最佳作法：** 雖然您可以透過個別使用者帳戶管理許可權，但建議您改用單一 Azure AD 群組（稱為存取群組）。</span><span class="sxs-lookup"><span data-stu-id="6eea3-137">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="6eea3-138">這可簡化透過存取群組成員資格的版權管理，而不是管理每個 SharePoint 群組的使用者帳戶清單。</span><span class="sxs-lookup"><span data-stu-id="6eea3-138">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="6eea3-139">Microsoft 365 的 Azure AD 群組不同于 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="6eea3-140">Azure AD 群組會顯示在 Microsoft 365 系統管理中心中，其 **類型** 設為 [ **安全性** ]，而且沒有電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6eea3-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="6eea3-141">Azure AD 群組可在下列專案中管理：</span><span class="sxs-lookup"><span data-stu-id="6eea3-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="6eea3-142">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="6eea3-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="6eea3-143">這些是在您的內部部署 AD DS 基礎結構中建立並同步處理至您的 Microsoft 365 訂閱的群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="6eea3-144">在 Microsoft 365 系統管理中心中，這些群組的 **狀態** 為 [已 **與 active directory 同步處理**]。</span><span class="sxs-lookup"><span data-stu-id="6eea3-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="6eea3-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="6eea3-145">Office 365</span></span>

    <span data-ttu-id="6eea3-146">這些是使用 Microsoft 365 系統管理中心、Azure 入口網站或 Microsoft PowerShell 建立的群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="6eea3-147">在 Microsoft 365 系統管理中心中，這些群組的 **狀態** 為 **雲端**。</span><span class="sxs-lookup"><span data-stu-id="6eea3-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="6eea3-148">**最佳作法：** 如果您使用的是 AD DS 內部部署並與 Microsoft 365 訂閱進行同步處理，請使用 AD DS 執行您的使用者和群組管理。</span><span class="sxs-lookup"><span data-stu-id="6eea3-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="6eea3-149">針對隔離 SharePoint 線上小組網站，建議的群組結構如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eea3-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="6eea3-150">SharePoint 群組</span><span class="sxs-lookup"><span data-stu-id="6eea3-150">SharePoint group</span></span>|<span data-ttu-id="6eea3-151">Azure AD 型訪問群組</span><span class="sxs-lookup"><span data-stu-id="6eea3-151">Azure AD-based access group</span></span>|<span data-ttu-id="6eea3-152">權限層級</span><span class="sxs-lookup"><span data-stu-id="6eea3-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="6eea3-153">\<site name> 成員</span><span class="sxs-lookup"><span data-stu-id="6eea3-153">\<site name> Members</span></span>|<span data-ttu-id="6eea3-154">\<site name> 成員</span><span class="sxs-lookup"><span data-stu-id="6eea3-154">\<site name> Members</span></span>|<span data-ttu-id="6eea3-155">編輯</span><span class="sxs-lookup"><span data-stu-id="6eea3-155">Edit</span></span>|
|<span data-ttu-id="6eea3-156">\<site name> 遊客</span><span class="sxs-lookup"><span data-stu-id="6eea3-156">\<site name> Visitors</span></span>|<span data-ttu-id="6eea3-157">\<site name> 觀眾</span><span class="sxs-lookup"><span data-stu-id="6eea3-157">\<site name> Viewers</span></span>|<span data-ttu-id="6eea3-158">讀取</span><span class="sxs-lookup"><span data-stu-id="6eea3-158">Read</span></span>|
|<span data-ttu-id="6eea3-159">\<site name> 業主</span><span class="sxs-lookup"><span data-stu-id="6eea3-159">\<site name> Owners</span></span>|<span data-ttu-id="6eea3-160">\<site name> 管理員</span><span class="sxs-lookup"><span data-stu-id="6eea3-160">\<site name> Admins</span></span>|<span data-ttu-id="6eea3-161">完全控制</span><span class="sxs-lookup"><span data-stu-id="6eea3-161">Full control</span></span>|
|

 <span data-ttu-id="6eea3-162">**最佳作法：** 雖然您可以使用 Microsoft 365 或 Azure AD 群組做為 SharePoint 群組的成員，我們還是建議您使用 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="6eea3-163">Azure AD 群組（透過 AD DS 或 Microsoft 365 管理）可讓您更靈活地使用嵌套群組來指派許可權。</span><span class="sxs-lookup"><span data-stu-id="6eea3-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="6eea3-164">以下是設定為使用 Azure AD 型存取群組的預設 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![使用訪問群組做為預設 SharePoint 線上網站群組的成員。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="6eea3-166">當您設計三個訪問群組時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="6eea3-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="6eea3-167">**\<site name> 管理員** 存取群組中應該只有少數幾個成員，對應于管理小組網站的少量 SharePoint Online 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="6eea3-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="6eea3-168">您的網站成員大部分都位於 **\<site name> members** 或 **\<site name> 查看** 器訪問群組中。</span><span class="sxs-lookup"><span data-stu-id="6eea3-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="6eea3-169">因為 **\<site name> 成員** 存取群組中的網站成員具有刪除或修改網站中資源的能力，所以請謹慎考慮其成員資格。</span><span class="sxs-lookup"><span data-stu-id="6eea3-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="6eea3-170">若有疑問，請將網站成員新增至 **\<site name> 查看** 器存取群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="6eea3-171">以下是名為 ProjectX 之隔離網站的 SharePoint 群組和存取群組的範例。</span><span class="sxs-lookup"><span data-stu-id="6eea3-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![使用名為 ProjectX SharePoint Online 網站的存取群組的範例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="6eea3-173">階段3：使用嵌套 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="6eea3-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="6eea3-174">對於僅限少數人員的專案，新增至網站 SharePoint 群組的單一層級 Azure AD 訪問群組會適合大多數案例。</span><span class="sxs-lookup"><span data-stu-id="6eea3-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="6eea3-175">不過，如果您有大量人員，而這些人已經是已建立的 Azure AD 群組的成員，您可以使用嵌套群組或包含其他群組的群組做為成員，更輕鬆地指派 SharePoint 許可權。</span><span class="sxs-lookup"><span data-stu-id="6eea3-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="6eea3-176">例如，您想要建立一個隔離的 SharePoint 線上小組網站，以共同共同作業的銷售、行銷、工程、法律和支援部門的主管，以及那些部門已經擁有 executive 使用者帳戶成員資格的群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-176">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="6eea3-177">不需要為新的網站成員建立新的群組，並將所有個人的執行使用者帳戶放在新的群組中，將每個部門的現有 executive 群組放在新群組中。</span><span class="sxs-lookup"><span data-stu-id="6eea3-177">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="6eea3-178">如果您在多個組織之間共用 Microsoft 365 訂閱，則組織的隔離網站的單一群組成員資格可能會因為使用者帳戶的數量非常困難而難於管理。</span><span class="sxs-lookup"><span data-stu-id="6eea3-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="6eea3-179">在此情況下，您可以針對包含組織內群組的每個組織，使用嵌套 Azure AD 群組來管理許可權。</span><span class="sxs-lookup"><span data-stu-id="6eea3-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="6eea3-180">若要使用嵌套 Azure AD 群組：</span><span class="sxs-lookup"><span data-stu-id="6eea3-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="6eea3-181">識別或建立 Azure AD 群組，其中會包含使用者帳戶，並將適當的使用者帳戶新增為成員。</span><span class="sxs-lookup"><span data-stu-id="6eea3-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="6eea3-182">建立將包含其他 Azure AD 群組的容器 Azure AD 型訪問群組，並將這些群組新增為成員。</span><span class="sxs-lookup"><span data-stu-id="6eea3-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="6eea3-183">若要取得容器存取群組的適當存取層級，請找出 SharePoint 群組和對應的許可權等級。</span><span class="sxs-lookup"><span data-stu-id="6eea3-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="6eea3-184">您無法使用嵌套的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="6eea3-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="6eea3-185">以下是 ProjectX 成員存取群組的嵌套 Azure AD 群組範例。</span><span class="sxs-lookup"><span data-stu-id="6eea3-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![在 ProjectX 網站的成員存取群組中使用嵌套存取群組的範例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="6eea3-187">因為「調研」、「工程」和「專案負責人」小組中的所有使用者帳戶都是網站成員，所以將其 Azure AD 群組新增至 ProjectX 成員存取群組會比較容易。</span><span class="sxs-lookup"><span data-stu-id="6eea3-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="6eea3-188">下一步</span><span class="sxs-lookup"><span data-stu-id="6eea3-188">Next step</span></span>

<span data-ttu-id="6eea3-189">當您準備好在實際執行中建立和設定隔離的網站時，請參閱 [部署隔離的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="6eea3-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6eea3-190">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6eea3-190">See Also</span></span>

[<span data-ttu-id="6eea3-191">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="6eea3-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="6eea3-192">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="6eea3-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6eea3-193">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="6eea3-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
