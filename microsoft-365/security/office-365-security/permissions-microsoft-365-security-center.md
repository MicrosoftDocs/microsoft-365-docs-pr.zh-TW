---
title: Microsoft 365 安全性中心的權限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 系統管理員可以了解如何在 Microsoft 365 安全性中心管理與安全性相關的所有工作的權限。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c2d28510c25290921084e6a238fa8c781c35624
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772464"
---
# <a name="permissions-in-the-microsoft-365-security-center"></a><span data-ttu-id="915eb-103">Microsoft 365 安全性中心的權限</span><span class="sxs-lookup"><span data-stu-id="915eb-103">Permissions in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="915eb-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="915eb-104">**Applies to**</span></span>
- [<span data-ttu-id="915eb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="915eb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="915eb-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="915eb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="915eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="915eb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="915eb-108">您需要管理橫跨所有 Microsoft 365 服務的安全性案例。</span><span class="sxs-lookup"><span data-stu-id="915eb-108">You need to manage security scenarios that span all the Microsoft 365 services.</span></span> <span data-ttu-id="915eb-109">而且您需要靈活地為組織中的合適人員提供正確的管理員權限。</span><span class="sxs-lookup"><span data-stu-id="915eb-109">And you need the flexibility to give the right admin permissions to the right people in your organization.</span></span>

<span data-ttu-id="915eb-110"><https://security.microsoft.com> 的 Microsoft 365 安全性中心支援直接管理在 Microsoft 365 中執行安全性工作的使用者的權限。</span><span class="sxs-lookup"><span data-stu-id="915eb-110">The Microsoft 365 security center at <https://security.microsoft.com> supports directly managing permissions for users who perform security tasks in Microsoft 365.</span></span> <span data-ttu-id="915eb-111">透過使用安全性中心管理權限，您可以集中管理與安全性相關的所有工作權限。</span><span class="sxs-lookup"><span data-stu-id="915eb-111">By using the security center to manage permissions, you can manage permissions centrally for all tasks related to security.</span></span>

<span data-ttu-id="915eb-112">要在安全性中心内管理權限，移至 **[權限和角色]** 或 <https://security.microsoft.com/securitypermissions>。</span><span class="sxs-lookup"><span data-stu-id="915eb-112">To manage permissions in the security center, go to **Permissions & roles** or <https://security.microsoft.com/securitypermissions>.</span></span> <span data-ttu-id="915eb-113">您需要是 **全域系統管理員** 或安全性中心中 **組織管理** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="915eb-113">You need to be a **global administrator** or a member of the **Organization Management** role group in the security center.</span></span> <span data-ttu-id="915eb-114">具體來說，**角色管理** 角色允許使用者在安全性中心檢視、建立和修改角色群組，預設情況下，該角色僅分配給 **組織管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="915eb-114">Specifically, the **Role Management** role allows users to view, create, and modify role groups in the security center, and by default, that role is assigned only to the **Organization Management** role group.</span></span>

## <a name="relationship-of-members-roles-and-role-groups"></a><span data-ttu-id="915eb-115">成員、角色和角色群組的關係</span><span class="sxs-lookup"><span data-stu-id="915eb-115">Relationship of members, roles, and role groups</span></span>

<span data-ttu-id="915eb-116">安全性中心的權限是根據角色型存取控制 (RBAC) 權限模型。</span><span class="sxs-lookup"><span data-stu-id="915eb-116">Permissions in the security center are based on the role-based access control (RBAC) permissions model.</span></span> <span data-ttu-id="915eb-117">RBAC 與大多數 Microsoft 365 服務使用的權限模型相同，因此如果您熟悉這些服務中的權限結構，那麼就會非常熟悉如何在安全性中心授予權限。</span><span class="sxs-lookup"><span data-stu-id="915eb-117">RBAC is the same permissions model that's used by most Microsoft 365 services, so if you're familiar with the permission structure in these services, granting permissions in the security center will be very familiar.</span></span>

<span data-ttu-id="915eb-118">**角色** 會授予執行工作集的權限。</span><span class="sxs-lookup"><span data-stu-id="915eb-118">A **role** grants the permissions to do a set of tasks.</span></span>

<span data-ttu-id="915eb-119">**角色群組** 是一組讓人員在安全性中心完成工作的角色。</span><span class="sxs-lookup"><span data-stu-id="915eb-119">A **role group** is a set of roles that lets people do their jobs in the security center.</span></span> <span data-ttu-id="915eb-120">例如，攻擊模擬器管理員角色群組包含攻擊模擬器管理員角色，以建立和管理攻擊模擬培訓的所有方面。</span><span class="sxs-lookup"><span data-stu-id="915eb-120">For example, the Attack Simulator Administrators role group includes the Attack Simulator Admin role to create and manage all aspects of attack simulation training.</span></span>

<span data-ttu-id="915eb-121">安全性中心的預設角色群組包含必須指派給人員的最常見工作和功能。</span><span class="sxs-lookup"><span data-stu-id="915eb-121">The security center includes default role groups for the most common tasks and functions that you'll need to assign.</span></span> <span data-ttu-id="915eb-122">通常，我們建議您只要將個別使用者新增為預設角色群組的 **成員**。</span><span class="sxs-lookup"><span data-stu-id="915eb-122">Generally, we recommend simply adding individual users as **members** to the default role groups.</span></span>

![圖表顯示角色群組和角色及成員的關係](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-security-center"></a><span data-ttu-id="915eb-124">安全性中心的角色和角色群組</span><span class="sxs-lookup"><span data-stu-id="915eb-124">Roles and role groups in the security center</span></span>

<span data-ttu-id="915eb-125">安全性中心的 **權限和角色** 中提供以下類型的角色和角色群組:</span><span class="sxs-lookup"><span data-stu-id="915eb-125">The following types of roles and role groups are available in **Permissions & roles** in the security center:</span></span>

- <span data-ttu-id="915eb-126">**Azure AD 角色**: 可以檢視角色和指派使用者，但不能直接在安全性中心進行管理。</span><span class="sxs-lookup"><span data-stu-id="915eb-126">**Azure AD roles**: You can view the roles and assigned users, but you can't manage them directly in the security center.</span></span> <span data-ttu-id="915eb-127">Azure AD 角色是為 **所有** Microsoft 365 服務指派權限的中心角色。</span><span class="sxs-lookup"><span data-stu-id="915eb-127">Azure AD roles are central roles that assign permissions for **all** Microsoft 365 services.</span></span>

- <span data-ttu-id="915eb-128">**電子郵件和共同作業角色**: 這些角色群組與安全性和合規性中心中可用的角色群組相同，但您可以直接在安全性中心管理它們。</span><span class="sxs-lookup"><span data-stu-id="915eb-128">**Email & collaboration roles**: These are the same role groups that are available in the Security & Compliance Center, but you can manage them directly in the security center.</span></span> <span data-ttu-id="915eb-129">你在此處指派的權限僅用於 Microsoft 365 安全性中心、Microsoft 365 合規性中心和安全性與合規性中心，並不涵蓋其他 Microsoft 365 工作負載所需的所有權限。</span><span class="sxs-lookup"><span data-stu-id="915eb-129">The permissions that you assign here are specific to the Microsoft 365 security center, the Microsoft 365 compliance center, and the Security & Compliance Center, and don't cover all of the permissions that are needed in other Microsoft 365 workloads.</span></span>

![Microsoft 365 安全性中心的權限和角色頁面](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-security-center"></a><span data-ttu-id="915eb-131">安全性中心的 Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="915eb-131">Azure AD roles in the security center</span></span>

<span data-ttu-id="915eb-132">當您移至 **電子郵件和共同作業角色** \> **權限和角色** \> **Azure AD 角色** \> **角色**（或直接轉到 <https://security.microsoft.com/aadpermissions>）時，您將看到本章節中描述的 Azure AD 角色。</span><span class="sxs-lookup"><span data-stu-id="915eb-132">When you go **Email & collaboration roles** \> **Permissions & roles** \> **Azure AD roles** \> **Roles** (or directly to <https://security.microsoft.com/aadpermissions>) you'll see the Azure AD roles that are described in this section.</span></span>

<span data-ttu-id="915eb-133">選取角色時，會出現一個包含角色描述和使用者作業的詳細資料飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="915eb-133">When you select a role, a details flyout that contains the description of the role and the user assignments appears.</span></span> <span data-ttu-id="915eb-134">但是要管理這些作業，您需要在詳細資料飛出視窗中點擊 **[管理 Azure AD 中的成員]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-134">But to manage those assignments, you need to click **Manage members in Azure AD** in the details flyout.</span></span>

![在 Azure Active Directory 中管理權限的連結](../../media/permissions-manage-in-azure-ad-link.png)

<span data-ttu-id="915eb-136">如需詳細資訊，請參閱 [在 Azure Active Directory 中檢視和指派系統管理員角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="915eb-136">For more information, see [View and assign administrator roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<br>

****

|<span data-ttu-id="915eb-137">角色</span><span class="sxs-lookup"><span data-stu-id="915eb-137">Role</span></span>|<span data-ttu-id="915eb-138">描述</span><span class="sxs-lookup"><span data-stu-id="915eb-138">Description</span></span>|
|---|---|
|<span data-ttu-id="915eb-139">**全域管理員**</span><span class="sxs-lookup"><span data-stu-id="915eb-139">**Global administrator**</span></span>|<span data-ttu-id="915eb-140">可以存取所有 Microsoft 365 服務中的所有系統管理功能。</span><span class="sxs-lookup"><span data-stu-id="915eb-140">Access to all administrative features in all Microsoft 365 services.</span></span> <span data-ttu-id="915eb-141">只有全域管理員才能指派其他系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="915eb-141">Only global administrators can assign other administrator roles.</span></span> <span data-ttu-id="915eb-142">如需詳細資訊，請參閱[全域系統管理員／公司系統管理員](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)。</span><span class="sxs-lookup"><span data-stu-id="915eb-142">For more information, see [Global Administrator / Company Administrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).</span></span>|
|<span data-ttu-id="915eb-143">**合規性資料管理員**</span><span class="sxs-lookup"><span data-stu-id="915eb-143">**Compliance data administrator**</span></span>|<span data-ttu-id="915eb-144">可以追蹤 Microsoft 365 中的組織資料，確保其受到保護，並深入了解任何問題以協助降低風險。</span><span class="sxs-lookup"><span data-stu-id="915eb-144">Keep track of your organization's data across Microsoft 365, make sure it's protected, and get insights into any issues to help mitigate risks.</span></span> <span data-ttu-id="915eb-145">如需詳細資訊，請參閱[合規性資料系統管理員](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)。</span><span class="sxs-lookup"><span data-stu-id="915eb-145">For more information, see [Compliance Data Administrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).</span></span>|
|<span data-ttu-id="915eb-146">**合規性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="915eb-146">**Compliance administrator**</span></span>|<span data-ttu-id="915eb-147">可幫助您的組織遵守任何法規要求、管理電子文件探索案例，並維護 Microsoft 365 各個位置、身分和應用程式的資料監管原則。</span><span class="sxs-lookup"><span data-stu-id="915eb-147">Help your organization stay compliant with any regulatory requirements, manage eDiscovery cases, and maintain data governance policies across Microsoft 365 locations, identities, and apps.</span></span> <span data-ttu-id="915eb-148">如需詳細資訊，請參閱 [合規性系統管理員](/azure/active-directory/roles/permissions-reference#compliance-administrator)。</span><span class="sxs-lookup"><span data-stu-id="915eb-148">For more information, see [Compliance Administrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).</span></span>|
|<span data-ttu-id="915eb-149">**安全性操作員**</span><span class="sxs-lookup"><span data-stu-id="915eb-149">**Security operator**</span></span>|<span data-ttu-id="915eb-150">可檢視、調查和回應 Microsoft 365 使用者、裝置和內容所受的主動威脅。</span><span class="sxs-lookup"><span data-stu-id="915eb-150">View, investigate, and respond to active threats to your Microsoft 365 users, devices, and content.</span></span> <span data-ttu-id="915eb-151">如需詳細資訊，請參閱 [安全性運算子](/azure/active-directory/roles/permissions-reference#security-operator)。</span><span class="sxs-lookup"><span data-stu-id="915eb-151">For more information, see [Security Operator](/azure/active-directory/roles/permissions-reference#security-operator).</span></span>|
|<span data-ttu-id="915eb-152">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="915eb-152">**Security reader**</span></span>|<span data-ttu-id="915eb-153">可檢視和調查 Microsoft 365 使用者、裝置和內容所受的主動威脅，但是 (與安全性運算子不同) 他們沒有透過採取行動而回應的權限。</span><span class="sxs-lookup"><span data-stu-id="915eb-153">View and investigate active threats to your Microsoft 365 users, devices, and content, but (unlike the Security operator) they do not have permissions to respond by taking action.</span></span> <span data-ttu-id="915eb-154">如需詳細資訊，請參閱 [安全性讀取者](/azure/active-directory/roles/permissions-reference#security-reader)。</span><span class="sxs-lookup"><span data-stu-id="915eb-154">For more information, see [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).</span></span>|
|<span data-ttu-id="915eb-155">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="915eb-155">**Security administrator**</span></span>|<span data-ttu-id="915eb-156">可透過管理安全性原則、檢視 Microsoft 365 各項產品的安全性分析和報告，以及在威脅環境中保持最新速度，來控制組織的整體安全性。</span><span class="sxs-lookup"><span data-stu-id="915eb-156">Control your organization's overall security by managing security policies, reviewing security analytics and reports across Microsoft 365 products, and staying up-to-speed on the threat landscape.</span></span> <span data-ttu-id="915eb-157">如需詳細資訊，請參閱 [安全性系統管理員](/azure/active-directory/roles/permissions-reference#security-administrator)。</span><span class="sxs-lookup"><span data-stu-id="915eb-157">For more information, see [Security Administrator](/azure/active-directory/roles/permissions-reference#security-administrator).</span></span>|
|<span data-ttu-id="915eb-158">**全域讀取者**</span><span class="sxs-lookup"><span data-stu-id="915eb-158">**Global reader**</span></span>|<span data-ttu-id="915eb-159">**全域系統管理員** 角色的唯讀版本。</span><span class="sxs-lookup"><span data-stu-id="915eb-159">The read-only version of the **Global administrator** role.</span></span> <span data-ttu-id="915eb-160">在 Microsoft 365 中檢視所有設定和管理資訊。</span><span class="sxs-lookup"><span data-stu-id="915eb-160">View all settings and administrative information across Microsoft 365.</span></span> <span data-ttu-id="915eb-161">如需詳細資訊，請參閱 [全域讀取者](/azure/active-directory/roles/permissions-reference#global-reader)。</span><span class="sxs-lookup"><span data-stu-id="915eb-161">For more information, see [Global Reader](/azure/active-directory/roles/permissions-reference#global-reader).</span></span>|
|<span data-ttu-id="915eb-162">**攻擊模擬系統管理員**</span><span class="sxs-lookup"><span data-stu-id="915eb-162">**Attack simulation administrator**</span></span>|<span data-ttu-id="915eb-163">建立和管理 [攻擊模擬系統](attack-simulation-training.md) 創建、模擬的啟動/排程，以及模擬結果審查的所有方面。</span><span class="sxs-lookup"><span data-stu-id="915eb-163">Create and manage all aspects of [attack simulation](attack-simulation-training.md) creation, launch/scheduling of a simulation, and the review of simulation results.</span></span> <span data-ttu-id="915eb-164">詳細資訊，請參閲 [攻擊模擬系統管理員](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)。</span><span class="sxs-lookup"><span data-stu-id="915eb-164">For more information, see [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).</span></span>|
|<span data-ttu-id="915eb-165">**攻擊承載作者**</span><span class="sxs-lookup"><span data-stu-id="915eb-165">**Attack payload author**</span></span>|<span data-ttu-id="915eb-166">建立攻擊承載，但不實際啟動或排程它們。</span><span class="sxs-lookup"><span data-stu-id="915eb-166">Create attack payloads but not actually launch or schedule them.</span></span> <span data-ttu-id="915eb-167">如需詳細資訊，請參閱 [攻擊承載作者](/azure/active-directory/roles/permissions-reference#attack-payload-author)。</span><span class="sxs-lookup"><span data-stu-id="915eb-167">For more information, see [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).</span></span>|
|

### <a name="email--collaboration-roles-in-the-security-center"></a><span data-ttu-id="915eb-168">安全性中心中的電子郵件和共同作業角色</span><span class="sxs-lookup"><span data-stu-id="915eb-168">Email & collaboration roles in the security center</span></span>

<span data-ttu-id="915eb-169">當您移至 **電子郵件和共同作業角色** \> **權限和角色** \> **電子郵件和共同作業角色** \> **角色**（或直接轉到 <https://security.microsoft.com/emailandcollabpermissions>）時，您將看到安全性與合規性中心中可用的相同角色群組。</span><span class="sxs-lookup"><span data-stu-id="915eb-169">When you go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles** (or directly to <https://security.microsoft.com/emailandcollabpermissions>) you'll see the same role groups that are available in the Security & Compliance Center.</span></span>

<span data-ttu-id="915eb-170">如需有關這些角色群組的詳細資訊，請參閱 [安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="915eb-170">For complete information about these role groups, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

#### <a name="modify-email--collaboration-role-membership-in-the-security-center"></a><span data-ttu-id="915eb-171">修改安全性中心中的電子郵件和共同作業角色成員資格</span><span class="sxs-lookup"><span data-stu-id="915eb-171">Modify Email & collaboration role membership in the security center</span></span>

1. <span data-ttu-id="915eb-172">在安全性中心，移至 **電子郵件和共同作業角色** \> **權限和角色** \> **電子郵件和共同作業角色** \> **角色**。</span><span class="sxs-lookup"><span data-stu-id="915eb-172">In the security center, go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles**.</span></span>

2. <span data-ttu-id="915eb-173">在 **權限** 頁面中，從清單中開啟和選取要修改的角色群組。</span><span class="sxs-lookup"><span data-stu-id="915eb-173">In the **Permissions** page that opens, select the role group that you want to modify from the list.</span></span> <span data-ttu-id="915eb-174">您可以點擊 **[名稱]** 資料行標題，以按名稱進行排序，也可以點擊 **[搜尋]** ![[搜尋圖示]](../../media/m365-cc-sc-search-icon.png) 來查找角色群組。</span><span class="sxs-lookup"><span data-stu-id="915eb-174">You can click on the **Name** column header to sort the list by name, or you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find the role group.</span></span>

3. <span data-ttu-id="915eb-175">在顯示角色群組詳細資料的飛出視窗中，按一下 **[成員]** 章節中的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-175">In the role group details flyout that appears, click **Edit** in the **Members** section.</span></span>

4. <span data-ttu-id="915eb-176">在出現的 **[正在編輯選擇成員]** 頁面執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="915eb-176">In the **Editing choose members** page that appears, do one of the following steps:</span></span>
   - <span data-ttu-id="915eb-177">如果沒有角色群組成員，請點擊 **[選擇成員]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-177">If there are no role group members, click **Choose members**.</span></span>
   - <span data-ttu-id="915eb-178">如果有現有的角色群組成員，請點擊 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-178">If there are existing role group members, click **Edit**</span></span>

5. <span data-ttu-id="915eb-179">在出現的 **[選擇成員]** 飛出視窗執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="915eb-179">In the **Choose members** flyout that appears, do one of the following steps:</span></span>

   - <span data-ttu-id="915eb-180">點擊 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-180">Click **Add**.</span></span> <span data-ttu-id="915eb-181">在出現的使用者清單中，選取一個或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="915eb-181">In the list of users that appears, select one or more users.</span></span> <span data-ttu-id="915eb-182">或者，您可以點擊 **[搜尋]** ![[搜尋圖示]](../../media/m365-cc-sc-search-icon.png) 以找出和選取使用者。</span><span class="sxs-lookup"><span data-stu-id="915eb-182">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select users.</span></span>

     <span data-ttu-id="915eb-183">選好要新增的使用者後，點擊 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-183">When you've selected the users that you want to add, click **Add**.</span></span>

   - <span data-ttu-id="915eb-184">點擊 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-184">Click **Remove**.</span></span> <span data-ttu-id="915eb-185">選取下列一個或多個現有的成員。</span><span class="sxs-lookup"><span data-stu-id="915eb-185">Select one or more of the existing members.</span></span> <span data-ttu-id="915eb-186">或者，您可以點擊 **[搜尋]** ![[搜尋圖示]](../../media/m365-cc-sc-search-icon.png) 以找出和選取成員。</span><span class="sxs-lookup"><span data-stu-id="915eb-186">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select members.</span></span>

     <span data-ttu-id="915eb-187">選好要移除的使用者後，點擊 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-187">When you've selected the users that you want to remove, click **Remove**.</span></span>

6. <span data-ttu-id="915eb-188">返回 **[選擇成員]** 飛出視窗，點擊 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-188">Back on the **Choose members** flyout, click **Done**.</span></span>

7. <span data-ttu-id="915eb-189">返回 **[正在編輯選擇成員]** 頁面，點擊 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-189">Back on the **Editing choose members** page, click **Save**.</span></span>

8. <span data-ttu-id="915eb-190">返回角色群組詳細資料飛出視窗，點擊 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="915eb-190">Back on the role group details flyout, click **Done**.</span></span>
