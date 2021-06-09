---
title: 開始使用 Microsoft 合規性管理員
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 設定 Microsoft 合規性管理員使用者許可權和角色，以及設定自動的動作測試。 管理使用者記錄並篩選儀表板視圖。
ms.openlocfilehash: 8877a9a1e65a624708646c17a2517647c8a72f6a
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570555"
---
# <a name="get-started-with-compliance-manager"></a><span data-ttu-id="be1f4-104">開始使用 [合規性管理員]</span><span class="sxs-lookup"><span data-stu-id="be1f4-104">Get started with Compliance Manager</span></span>

<span data-ttu-id="be1f4-105">**本文內容：** 本文可協助您設定合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="be1f4-105">**In this article:** This article helps you set up Compliance Manager.</span></span> <span data-ttu-id="be1f4-106">瞭解如何 **存取** 合規性管理員、 **設定角色和許可權**，以及設定 **改進動作的自動測試**。</span><span class="sxs-lookup"><span data-stu-id="be1f4-106">Learn how to **access** Compliance Manager, **set roles and permissions**, and configure **automatic testing of improvement actions**.</span></span> <span data-ttu-id="be1f4-107">逐步流覽 **您的合規性管理員儀表板** ，瞭解主要頁面：「改進動作」頁面、「解決方案」頁面、「評估」頁面及「評估範本」頁面。</span><span class="sxs-lookup"><span data-stu-id="be1f4-107">Walk through **your Compliance Manager dashboard** and understand the main pages: the improvement actions page, the solutions page, the assessments page, and the assessment templates page.</span></span>

## <a name="who-can-access-compliance-manager"></a><span data-ttu-id="be1f4-108">神秘可以存取合規性管理員</span><span class="sxs-lookup"><span data-stu-id="be1f4-108">Who can access Compliance Manager</span></span>

<span data-ttu-id="be1f4-109">合規性管理員可供具有 Office 365 和 Microsoft 365 授權的組織使用，並可政府社群雲端 (GCC) 中等、GCC 高及國防 (DoD) 客戶。</span><span class="sxs-lookup"><span data-stu-id="be1f4-109">Compliance Manager is available to organizations with Office 365 and Microsoft 365 licenses, and to US Government Community Cloud (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span> <span data-ttu-id="be1f4-110">評估可用性和管理功能取決於您的授權合約。</span><span class="sxs-lookup"><span data-stu-id="be1f4-110">Assessment availability and management capabilities depend on your licensing agreement.</span></span>  <span data-ttu-id="be1f4-111">[查看服務說明的詳細資料](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-111">[View service description details](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="be1f4-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="be1f4-112">Before you begin</span></span>

<span data-ttu-id="be1f4-113">組織的 Microsoft 365 全域管理員可能會是第一個存取合規性管理員的使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-113">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Manager.</span></span> <span data-ttu-id="be1f4-114">我們建議全域管理員登入，並設定第一次造訪合規性管理員時所述的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="be1f4-114">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Manager for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="be1f4-115">登入</span><span class="sxs-lookup"><span data-stu-id="be1f4-115">Sign in</span></span>

1. <span data-ttu-id="be1f4-116">請移至「 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)」，並以您的 Microsoft 365 全域管理員帳戶登 **入**。</span><span class="sxs-lookup"><span data-stu-id="be1f4-116">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global administrator account.</span></span>
2. <span data-ttu-id="be1f4-117">在左功能窗格上選取 [ **合規性管理員** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-117">Select **Compliance Manager** on the left navigation pane.</span></span> <span data-ttu-id="be1f4-118">您將會收到您的 [合規性管理員儀表板](#understand-the-compliance-manager-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-118">You'll arrive at your [Compliance Manager dashboard](#understand-the-compliance-manager-dashboard).</span></span>

<span data-ttu-id="be1f4-119">Access 合規性管理員的直接連結為 [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-119">The direct link to access Compliance Manager is [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="be1f4-120">設定使用者權限並指派角色</span><span class="sxs-lookup"><span data-stu-id="be1f4-120">Set user permissions and assign roles</span></span>

<span data-ttu-id="be1f4-121">合規性管理員使用以角色為基礎的存取控制 (RBAC) 許可權模型。</span><span class="sxs-lookup"><span data-stu-id="be1f4-121">Compliance Manager uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="be1f4-122">只有獲指派角色的使用者可以存取合規性管理員，且每個使用者所允許的動作受到 [角色類型](#role-types)的限制。</span><span class="sxs-lookup"><span data-stu-id="be1f4-122">Only users who are assigned a role may access Compliance Manager, and the actions allowed by each user are restricted by [role type](#role-types).</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="be1f4-123">設定許可權的位置</span><span class="sxs-lookup"><span data-stu-id="be1f4-123">Where to set permissions</span></span>

<span data-ttu-id="be1f4-124">擁有組織之全域系統管理員角色的人員可以設定合規性管理員的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="be1f4-124">The person holding the global admin role for your organization can set user permissions for Compliance Manager.</span></span> <span data-ttu-id="be1f4-125">您可以在 Office 365 安全性 & 規範中心以及 Azure Active Directory (Azure AD) 中設定許可權。</span><span class="sxs-lookup"><span data-stu-id="be1f4-125">Permissions can be set in the Office 365 Security & Compliance center as well as in Azure Active Directory (Azure AD).</span></span>

> [!NOTE]
> <span data-ttu-id="be1f4-126">美國政府 Community 中的客戶 (GCC) 高和最的防禦權 (DoD) 環境只能在 Azure AD 中為合規性管理員設定使用者權限和角色。</span><span class="sxs-lookup"><span data-stu-id="be1f4-126">Customers in US Government Community (GCC) High and Department of Defense (DoD) environments can only set user permissions and roles for Compliance Manager in Azure AD.</span></span> <span data-ttu-id="be1f4-127">請參閱下列 Azure AD 指示和角色類型定義。</span><span class="sxs-lookup"><span data-stu-id="be1f4-127">See below for Azure AD instructions and role type definitions.</span></span>

<span data-ttu-id="be1f4-128">若要在 Office 365 安全性 & 規範中心設定許可權並指派角色，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="be1f4-128">To set permissions and assign roles in the Office 365 Security & Compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="be1f4-129">移至 [ [Office 365 安全性 & 規範中心](https://protection.office.com/)]，然後選取左側導覽的 **許可權**。</span><span class="sxs-lookup"><span data-stu-id="be1f4-129">Go to the [Office 365 Security & Compliance Center](https://protection.office.com/) and select **Permissions** on the left navigation.</span></span>

2. <span data-ttu-id="be1f4-130">尋找您要新增一或多個使用者的角色群組，然後選取 [組名] 左側的方塊。</span><span class="sxs-lookup"><span data-stu-id="be1f4-130">Find the role group to which you want to add one or more users, and check the box to the left of the group name.</span></span> <span data-ttu-id="be1f4-131"> (請參閱 [下列角色和相關功能的清單](#role-types)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-131">(See the [list of roles and related functions below](#role-types).</span></span> <span data-ttu-id="be1f4-132">會模仿角色名稱的角色群組名稱。 ) </span><span class="sxs-lookup"><span data-stu-id="be1f4-132">The role group names mimic the role name.)</span></span>

3. <span data-ttu-id="be1f4-133">在該群組的彈出窗格上，選取 [**成員**] 標題底下的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-133">On the flyout pane for that group, select **Edit** under the **Members** header.</span></span>

4. <span data-ttu-id="be1f4-134">選取 **[選擇成員**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-134">Select **Choose members**.</span></span> <span data-ttu-id="be1f4-135">會出現另一個快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="be1f4-135">Another flyout window will appear.</span></span>

5. <span data-ttu-id="be1f4-136">選取 [ **+ 新增** ] 選擇一或多個要新增至群組的使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-136">Select **+ Add** to choose one or more users to add to the group.</span></span>

6. <span data-ttu-id="be1f4-137">選取您要新增之名稱旁邊的核取方塊，然後選取底部的 [ **新增** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="be1f4-137">Select the checkbox next to the names you want to add, then select the **Add** button at the bottom.</span></span>

7. <span data-ttu-id="be1f4-138">當您完成指派使用者時，請選取 [ **完成**]，然後選取 [ **儲存**]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-138">When you’re done assigning users, select **Done**, then select **Save**, then **Close**.</span></span>

##### <a name="more-about-the-office-365-security--compliance-center"></a><span data-ttu-id="be1f4-139">Office 365 安全性 & 規範中心的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="be1f4-139">More about the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="be1f4-140">深入瞭解[Office 365 安全性 & 規範中心的許可權](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-140">Learn more about [permissions in the Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="be1f4-141">如果您沒有 Office 365 安全性與合規性中心的存取權，或者您需要在 Microsoft 服務信任入口網站中存取傳統版本的合規性管理員，則服務信任入口網站中的系統管理員設定會提供另一種方法，來指派角色 ([view 指示](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-141">If you don't have access to the Office 365 Security and Compliance Center, or if you need to access the classic version of Compliance Manager in the Microsoft Service Trust Portal,  the Admin settings in the Service Trust Portal provides another way to assign roles ([view instructions](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)).</span></span> <span data-ttu-id="be1f4-142">請注意，這些角色在其功能上的限制更為有限。</span><span class="sxs-lookup"><span data-stu-id="be1f4-142">Be aware that such roles are more limited in their functionality.</span></span>

##### <a name="more-about-azure-ad"></a><span data-ttu-id="be1f4-143">有關 Azure AD 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="be1f4-143">More about Azure AD</span></span>

<span data-ttu-id="be1f4-144">若要在 Azure AD 中指派角色和設定許可權，請參閱[使用 Azure Active Directory 指派系統管理員和非系統管理員角色給使用者](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-144">To assign roles and set permissions in Azure AD, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

<span data-ttu-id="be1f4-145">使用 Azure AD 身分識別但未 Office 365 或 Microsoft 365 訂閱的使用者，將無法存取 Microsoft 365 規範中心內的合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="be1f4-145">Users with Azure AD identities who don't have Office 365 or Microsoft 365 subscriptions won't be able to access Compliance Manager in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="be1f4-146">若要在存取合規性管理員中尋求協助，請與 [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com)聯繫。</span><span class="sxs-lookup"><span data-stu-id="be1f4-146">To seek assistance in accessing Compliance Manager, contact [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).</span></span>

### <a name="role-types"></a><span data-ttu-id="be1f4-147">角色類型</span><span class="sxs-lookup"><span data-stu-id="be1f4-147">Role types</span></span>

<span data-ttu-id="be1f4-148">下表顯示合規性管理員中每個角色所允許的功能。</span><span class="sxs-lookup"><span data-stu-id="be1f4-148">The table below shows the functions allowed by each role in Compliance Manager.</span></span> <span data-ttu-id="be1f4-149">該表也顯示每個 [AZURE AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 如何對應至合規性管理員角色。</span><span class="sxs-lookup"><span data-stu-id="be1f4-149">The table also shows how each [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to Compliance Manager roles.</span></span> <span data-ttu-id="be1f4-150">使用者必須至少要有合規性管理員讀者角色或 Azure AD 全域讀卡機角色，才可存取合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="be1f4-150">Users will need at least the Compliance Manager reader role, or Azure AD global reader role, to access Compliance Manager.</span></span>


| <span data-ttu-id="be1f4-151">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="be1f4-151">User can:</span></span> | <span data-ttu-id="be1f4-152">合規性管理員角色</span><span class="sxs-lookup"><span data-stu-id="be1f4-152">Compliance Manager role</span></span> | <span data-ttu-id="be1f4-153">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="be1f4-153">Azure AD role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="be1f4-154">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="be1f4-154">**Read but not edit data**</span></span>| <span data-ttu-id="be1f4-155">合規性管理員讀取者</span><span class="sxs-lookup"><span data-stu-id="be1f4-155">Compliance Manager Reader</span></span>  | <span data-ttu-id="be1f4-156">Azure AD 全域讀取器，安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="be1f4-156">Azure AD Global reader, Security reader</span></span> | 
| <span data-ttu-id="be1f4-157">**編輯資料**</span><span class="sxs-lookup"><span data-stu-id="be1f4-157">**Edit data**</span></span>| <span data-ttu-id="be1f4-158">合規性管理員貢獻</span><span class="sxs-lookup"><span data-stu-id="be1f4-158">Compliance Manager Contribution</span></span> | <span data-ttu-id="be1f4-159">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="be1f4-159">Compliance Administrator</span></span> | 
| <span data-ttu-id="be1f4-160">**編輯測試結果**</span><span class="sxs-lookup"><span data-stu-id="be1f4-160">**Edit test results**</span></span>| <span data-ttu-id="be1f4-161">合規性管理員評定員</span><span class="sxs-lookup"><span data-stu-id="be1f4-161">Compliance Manager Assessor</span></span> | <span data-ttu-id="be1f4-162">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="be1f4-162">Compliance Administrator</span></span> | 
| <span data-ttu-id="be1f4-163">**管理評估、範本及租使用者資料**</span><span class="sxs-lookup"><span data-stu-id="be1f4-163">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="be1f4-164">合規性管理員管理</span><span class="sxs-lookup"><span data-stu-id="be1f4-164">Compliance Manager Administration</span></span> | <span data-ttu-id="be1f4-165">合規性管理員、規範資料管理員、安全性管理員</span><span class="sxs-lookup"><span data-stu-id="be1f4-165">Compliance Administrator, Compliance Data Administrator, Security Administrator</span></span>  | 
| <span data-ttu-id="be1f4-166">**指派使用者**</span><span class="sxs-lookup"><span data-stu-id="be1f4-166">**Assign users**</span></span>| <span data-ttu-id="be1f4-167">全域管理員</span><span class="sxs-lookup"><span data-stu-id="be1f4-167">Global Administrator</span></span> | <span data-ttu-id="be1f4-168">全域管理員</span><span class="sxs-lookup"><span data-stu-id="be1f4-168">Global Administrator</span></span> | 

## <a name="settings-for-automated-testing-and-user-history"></a><span data-ttu-id="be1f4-169">自動測試和使用者歷程記錄的設定</span><span class="sxs-lookup"><span data-stu-id="be1f4-169">Settings for automated testing and user history</span></span>

<span data-ttu-id="be1f4-170">Microsoft 365 規範中心的合規性管理員設定可讓您啟用及停用自動執行改進動作的測試。</span><span class="sxs-lookup"><span data-stu-id="be1f4-170">The Compliance Manager settings in the Microsoft 365 compliance center allow you to enable and disable automatic testing of improvement actions.</span></span> <span data-ttu-id="be1f4-171">這些設定也可讓您管理與改進動作相關聯之使用者的資料，包括將「改進」動作重新指派給其他使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="be1f4-171">The settings also allow you to manage the data of users associated to improvement actions, including the ability to reassign improvement actions to a different user.</span></span>  <span data-ttu-id="be1f4-172">只有具有全域系統管理員或合規性管理員角色的人員才能存取合規性管理員設定。</span><span class="sxs-lookup"><span data-stu-id="be1f4-172">Only people with a global administrator or Compliance Manager Administrator role can access the Compliance Manager settings.</span></span>

> [!NOTE]
> <span data-ttu-id="be1f4-173">GCC 高和 DoD 環境中的客戶無法使用自動測試功能，因為在這些環境中無法使用安全分數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-173">The automated testing feature is not available to customers in GCC High and DoD environments because Secure Score isn't available in these environments.</span></span> <span data-ttu-id="be1f4-174">GCC高和 DoD 客戶必須手動實施及測試其改進動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-174">GCC High and DoD customers will need to manually implement and test their improvement actions.</span></span>

### <a name="set-up-automated-testing"></a><span data-ttu-id="be1f4-175">設定自動測試</span><span class="sxs-lookup"><span data-stu-id="be1f4-175">Set up automated testing</span></span>

<span data-ttu-id="be1f4-176">合規性管理員中的某些改進動作也是由 [Microsoft 安全分數](../security/defender/microsoft-secure-score.md)所監控。</span><span class="sxs-lookup"><span data-stu-id="be1f4-176">Some improvement actions in Compliance Manager are also monitored by [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="be1f4-177">您可以設定進行自動監控的動作自動測試，這表示在安全的分數中測試並更新動作時，這些結果會與合規性管理員中的相同動作同步處理，並在合規性分數中計數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-177">You can set up automated testing of actions that are jointly monitored, which means that when an action is tested and updated in Secure Score, those results synch with the same actions in Compliance Manager and count toward your compliance score.</span></span>

<span data-ttu-id="be1f4-178">預設會針對合規性管理員的新組織開啟自動測試。</span><span class="sxs-lookup"><span data-stu-id="be1f4-178">Automatic testing is turned on by default for organizations new to Compliance Manager.</span></span> <span data-ttu-id="be1f4-179">當您第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行安全的評分，以完全收集資料，並將其考慮為您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-179">When you first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your compliance score.</span></span>  <span data-ttu-id="be1f4-180">開啟自動測試時，不會更新動作的測試日期，但會更新其測試狀態。</span><span class="sxs-lookup"><span data-stu-id="be1f4-180">When automated testing is turned on, the action’s test date won’t be updated, but its test status will update.</span></span> <span data-ttu-id="be1f4-181">當建立新的評估時，會自動包含 Microsoft control 得分和安全評分整合。</span><span class="sxs-lookup"><span data-stu-id="be1f4-181">When new assessments are created, scores automatically include Microsoft control scores and Secure Score integration.</span></span>

<span data-ttu-id="be1f4-182">組織的全域管理員可以隨時變更自動測試的設定。</span><span class="sxs-lookup"><span data-stu-id="be1f4-182">The global administrator for your organization can change the settings for automated testing at any time.</span></span> <span data-ttu-id="be1f4-183">您可以關閉常見改進動作的自動測試，或為個別動作開啟自動測試。</span><span class="sxs-lookup"><span data-stu-id="be1f4-183">You can turn off automated testing for common improvement actions, or turn it on for individual actions.</span></span> <span data-ttu-id="be1f4-184">遵循下列指示變更您的自動測試設定。</span><span class="sxs-lookup"><span data-stu-id="be1f4-184">Follow the instructions below to change your automated testing settings.</span></span>

#### <a name="to-manage-your-automated-testing-settings"></a><span data-ttu-id="be1f4-185">若要管理您的自動測試設定：</span><span class="sxs-lookup"><span data-stu-id="be1f4-185">To manage your automated testing settings:</span></span>

1. <span data-ttu-id="be1f4-186">從 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽 **設定**。</span><span class="sxs-lookup"><span data-stu-id="be1f4-186">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="be1f4-187">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-187">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="be1f4-188">從左側導覽選取 [ **自動測試** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-188">Select **Automated testing** from the left navigation.</span></span>

4. <span data-ttu-id="be1f4-189">選取 [適用] 按鈕，針對所有改進動作開啟自動測試、關閉所有動作的 [關閉] 或 [依個別動作開啟]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-189">Select the applicable button to turn on automatic testing for all improvement actions, turn it off for all actions, or turn on by individual action.</span></span>

5. <span data-ttu-id="be1f4-190">如果您選取 [ **每次改進動作開啟**]，清單會顯示所有可用的改善動作，以供選擇。</span><span class="sxs-lookup"><span data-stu-id="be1f4-190">If you select **Turn on per improvement action**, a list will show all the available improvement actions to choose from.</span></span>  <span data-ttu-id="be1f4-191">選取您想要自動測試的任何動作旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="be1f4-191">Check the box next to any action you want automatically tested.</span></span>

6. <span data-ttu-id="be1f4-192">選取 [ **儲存** ] 以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="be1f4-192">Select **Save** to save your settings.</span></span> <span data-ttu-id="be1f4-193">您會在螢幕頂端看到您的選取專案已儲存的確認訊息。</span><span class="sxs-lookup"><span data-stu-id="be1f4-193">You’ll receive a confirmation message at the top of your screen that your selection was saved.</span></span> <span data-ttu-id="be1f4-194">如果您收到失敗通知，請再試一次。</span><span class="sxs-lookup"><span data-stu-id="be1f4-194">If you receive a failure notice, try again.</span></span>

<span data-ttu-id="be1f4-195">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="be1f4-195">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="be1f4-196">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-196">The Compliance Manager Administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

### <a name="manage-user-history"></a><span data-ttu-id="be1f4-197">管理使用者歷程記錄</span><span class="sxs-lookup"><span data-stu-id="be1f4-197">Manage user history</span></span>

<span data-ttu-id="be1f4-198">「 **管理使用者記錄** 」設定可協助您快速識別在合規性管理員中使用「改進」動作的使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-198">The **Manage user history** settings help you quickly identify which users have worked with improvement actions in Compliance Manager.</span></span> <span data-ttu-id="be1f4-199">與改進動作相關聯的身分識別使用者資料包括任何執行和測試工作已完成、檔上傳的檔，以及所輸入的任何附注。</span><span class="sxs-lookup"><span data-stu-id="be1f4-199">The identifiable user data associated with improvement actions includes any implementation and testing work done, documents they uploaded, and any notes they entered.</span></span> <span data-ttu-id="be1f4-200">若要瞭解和檢索此類型的資料，您的組織本身的合規性需求可能是必要的。</span><span class="sxs-lookup"><span data-stu-id="be1f4-200">Understanding and retrieving this type of data may be necessary for your organization’s own compliance needs.</span></span>

<span data-ttu-id="be1f4-201">使用者記錄設定也可讓您將所有的「改進動作」從一個使用者重新指派給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-201">The user history settings also allow you to reassign all improvement actions from one user to another.</span></span>

<span data-ttu-id="be1f4-202">**若要尋找使用者記錄設定：**</span><span class="sxs-lookup"><span data-stu-id="be1f4-202">**To find the user history settings:**</span></span>

1. <span data-ttu-id="be1f4-203">從[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽設定。</span><span class="sxs-lookup"><span data-stu-id="be1f4-203">Select Settings on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="be1f4-204">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-204">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="be1f4-205">從左側導覽中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-205">Select **Manage user history** from the left navigation.</span></span>

<span data-ttu-id="be1f4-206">「 **管理使用者歷程記錄** 」頁面會顯示所有使用者的清單，其郵寄地址會指派給「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-206">The **manage user history** page shows a list of all users by email address who are assigned to an improvement action.</span></span> <span data-ttu-id="be1f4-207">使用 [ **搜尋** ] 按鈕，透過輸入電子郵件地址來快速尋找特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-207">Use the **Search** button to quickly find a specific user by typing in their email address.</span></span>

<span data-ttu-id="be1f4-208">在每個使用者的電子郵件地址右側，[ **選取** ] 下拉式功能表提供匯出報告、重新指派改進動作或刪除歷程記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="be1f4-208">To the right of each user’s email address, the **Select** drop-down menu provides options to  export a report, reassign improvement actions, or delete history.</span></span> <span data-ttu-id="be1f4-209">請參閱下列各節，以取得每個選項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="be1f4-209">See each section below for details about each option.</span></span>

#### <a name="export-a-report-of-user-history-data"></a><span data-ttu-id="be1f4-210">匯出使用者記錄資料的報告</span><span class="sxs-lookup"><span data-stu-id="be1f4-210">Export a report of user history data</span></span>

<span data-ttu-id="be1f4-211">您可以匯出包含目前指派給使用者之改進動作清單的 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="be1f4-211">You can export an Excel file containing a list of improvement actions currently assigned to a user.</span></span>  <span data-ttu-id="be1f4-212">報告也會列出該使用者上傳的任何證據檔案。</span><span class="sxs-lookup"><span data-stu-id="be1f4-212">The report also lists any evidence files uploaded by that user.</span></span> <span data-ttu-id="be1f4-213">此資訊可協助您重新指派開啟的「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-213">This information can help you reassign open improvement actions.</span></span>

<span data-ttu-id="be1f4-214">報表反映的是在建立日期後的「改進」動作狀態。</span><span class="sxs-lookup"><span data-stu-id="be1f4-214">The report reflects the improvement action’s status as of its creation date.</span></span> <span data-ttu-id="be1f4-215">這不是所有先前對其狀態或工作 (分派所做變更的歷史報告。瞭解如何 [從 [改進動作] 頁面匯出報告](compliance-manager-improvement-actions.md#export-a-report)) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-215">It’s not a historical report of all previous changes to its status or assignment (learn how to [export a report from your improvement actions page](compliance-manager-improvement-actions.md#export-a-report)).</span></span>

<span data-ttu-id="be1f4-216">**請遵循下列步驟，依使用者匯出報告：**</span><span class="sxs-lookup"><span data-stu-id="be1f4-216">**Follow the steps below to export a report by user:**</span></span>

1. <span data-ttu-id="be1f4-217">從 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽 **設定**。</span><span class="sxs-lookup"><span data-stu-id="be1f4-217">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="be1f4-218">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-218">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="be1f4-219">從左邊的流覽窗格中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-219">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="be1f4-220">搜尋清單電子郵件地址，或選取 [ **搜尋** ] 並輸入使用者的電子郵件地址，以尋找預定的使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-220">Find your intended user by searching the list email addresses, or by selecting **Search** and entering the user’s email address.</span></span>

5. <span data-ttu-id="be1f4-221">從 [ **選取** ] 下拉式功能表中，選擇 [ **匯出報告**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-221">From the **Select** drop-down menu, choose **Export report**.</span></span>

6. <span data-ttu-id="be1f4-222">在報告的 Excel 檔產生後，您就可以開啟它，並將它儲存到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="be1f4-222">Once the Excel file of your report is generated, you can open it and save it to your local machine.</span></span>

#### <a name="reassign-improvement-actions-to-another-user"></a><span data-ttu-id="be1f4-223">將改進動作重新指派給另一位使用者</span><span class="sxs-lookup"><span data-stu-id="be1f4-223">Reassign improvement actions to another user</span></span>

<span data-ttu-id="be1f4-224">您可以從某個使用者重新指派改進動作給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-224">You can reassign improvement actions from one user to another.</span></span> <span data-ttu-id="be1f4-225">當您重新指派動作時，檔上傳的歷程記錄不會變更，但原來上傳檔的使用者名稱將不再出現在 [改進] 動作內。</span><span class="sxs-lookup"><span data-stu-id="be1f4-225">When you reassign an action, the document upload history doesn't change, but the name of the user who originally uploaded the documentation no longer appears within the improvement action.</span></span>

<span data-ttu-id="be1f4-226">**請遵循下列步驟，將改進動作重新指派給其他使用者：**</span><span class="sxs-lookup"><span data-stu-id="be1f4-226">**Follow the steps below to reassign improvement actions to another user:**</span></span>

1. <span data-ttu-id="be1f4-227">從 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽 **設定**。</span><span class="sxs-lookup"><span data-stu-id="be1f4-227">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="be1f4-228">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-228">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="be1f4-229">從左邊的流覽窗格中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-229">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="be1f4-230">搜尋清單電子郵件地址，或選取 [ **搜尋** ] 並輸入該使用者的電子郵件地址，以尋找使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-230">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="be1f4-231">從 [ **選取** ] 下拉式功能表中，選擇 [ **重新指派改進動作**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-231">From the **Select** drop-down menu, choose **Reassign improvement actions**.</span></span> <span data-ttu-id="be1f4-232">隨即會出現 [ **重新指派改進動作** ] 彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="be1f4-232">The **Reassign improvement actions** flyout pane will appear.</span></span>

6. <span data-ttu-id="be1f4-233">在 [ **搜尋使用者** ] 欄位中，輸入 *您要指派「改進動作」* 之使用者的名稱或電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="be1f4-233">In the **Search users** field, enter the name or email address of the user you want assign the improvement actions *to*.</span></span>

7. <span data-ttu-id="be1f4-234">當您看到 [ **改進動作將指派** 給您的預定使用者名稱] 時，請選取使用者，然後選取 [ **指派動作**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-234">When you see the name of your intended user under **Improvement actions will be assigned to**, select the user, then select **Assign actions**.</span></span>

8. <span data-ttu-id="be1f4-235">當重新指派完成時，您會在飛入窗格中看到一則確認訊息，以確認先前使用者的所有改進動作都已重新指派給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-235">When the reassignment is complete, you’ll see a confirmation message in the flyout pane confirming that all improvement actions from the previous user have been reassigned to the new user.</span></span> <span data-ttu-id="be1f4-236">如果您收到重新指派失敗通知，請關閉視窗，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="be1f4-236">If you receive a reassignment failure notice, close the window and try again.</span></span> <span data-ttu-id="be1f4-237">若要關閉彈出窗格，請選取 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-237">To close the flyout pane, select **Done**.</span></span>

<span data-ttu-id="be1f4-238">新的受託人會收到已獲指派給改進動作的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="be1f4-238">The new assignee receives an email that they've been assigned to an improvement action.</span></span> <span data-ttu-id="be1f4-239">電子郵件包含 [改進動作的詳細資料] 頁面的直接連結。</span><span class="sxs-lookup"><span data-stu-id="be1f4-239">The email contains a direct link into the improvement action's details page.</span></span>
 
 > [!NOTE]
> <span data-ttu-id="be1f4-240">如果您重新指派具有暫止更新的動作，當重新指派後接受更新時，就會中斷重新分派電子郵件中動作的直接連結。</span><span class="sxs-lookup"><span data-stu-id="be1f4-240">If you reassign an action that has a pending update, the direct link to the action in the reassignment email will break if the update is accepted after reassignment.</span></span> <span data-ttu-id="be1f4-241">您可以在接受更新後，將動作重新指派給使用者，以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="be1f4-241">You can fix this by re-assigning the action to the user after the update is accepted.</span></span> <span data-ttu-id="be1f4-242">深入瞭解 [改進動作的更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-242">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

#### <a name="delete-user-history"></a><span data-ttu-id="be1f4-243">刪除使用者歷程記錄</span><span class="sxs-lookup"><span data-stu-id="be1f4-243">Delete user history</span></span>

<span data-ttu-id="be1f4-244">刪除使用者的歷程記錄會將其當作改進動作的擁有者移除，並且會從合規性管理員中的所有其他欄位移除其名稱。</span><span class="sxs-lookup"><span data-stu-id="be1f4-244">Deleting a user’s history will remove them as an owner of improvement actions, and will remove their name from all other fields in Compliance Manager.</span></span> <span data-ttu-id="be1f4-245">當您刪除使用者的記錄時，他們所擁有的「提升」動作將不會顯示 **指定** 的值，直到指派新的使用者為止。</span><span class="sxs-lookup"><span data-stu-id="be1f4-245">When you delete a user’s history, the improvement actions they owned will not display an **Assigned to** value until a new user is assigned.</span></span> <span data-ttu-id="be1f4-246">任何上傳至 [提升] 動作的檔都會顯示 **使用者移除** 的位置，取代刪除的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="be1f4-246">Any documents uploaded to the improvement action will show **User removed** in place of the deleted user’s name.</span></span> <span data-ttu-id="be1f4-247">刪除使用者歷程記錄是永久的。</span><span class="sxs-lookup"><span data-stu-id="be1f4-247">Deleting user history is permanent.</span></span>

<span data-ttu-id="be1f4-248">若要刪除使用者的歷程記錄，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="be1f4-248">To delete a user’s history, follow the steps below:</span></span>

1. <span data-ttu-id="be1f4-249">從 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽 **設定**。</span><span class="sxs-lookup"><span data-stu-id="be1f4-249">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="be1f4-250">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-250">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="be1f4-251">從左邊的流覽窗格中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-251">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="be1f4-252">搜尋清單電子郵件地址，或選取 [ **搜尋** ] 並輸入該使用者的電子郵件地址，以尋找使用者。</span><span class="sxs-lookup"><span data-stu-id="be1f4-252">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="be1f4-253">從 [ **選取** ] 下拉式功能表中，選擇 [ **刪除歷程記錄**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-253">From the **Select** drop-down menu, choose **Delete history**.</span></span>

6. <span data-ttu-id="be1f4-254">隨即會出現一個視窗，要求您確認永久刪除使用者的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="be1f4-254">A window appears asking you to confirm the permanent deletion of the user’s history.</span></span> <span data-ttu-id="be1f4-255">若要繼續刪除，請選取 [ **刪除歷程記錄**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-255">To continue with deletion, select **Delete history**.</span></span> <span data-ttu-id="be1f4-256">若要離開但不刪除記錄，請選取 [ **取消**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-256">To leave without deleting the history, select **Cancel**.</span></span>

7. <span data-ttu-id="be1f4-257">您將會在 [ **管理使用者歷程記錄** ] 頁面上，收到使用者已刪除之記錄的上方的確認訊息。</span><span class="sxs-lookup"><span data-stu-id="be1f4-257">You’ll arrive back at the **Manage user history** page with a confirmation message at the top that the history for the user was deleted.</span></span>

## <a name="understand-the-compliance-manager-dashboard"></a><span data-ttu-id="be1f4-258">瞭解合規性管理員儀表板</span><span class="sxs-lookup"><span data-stu-id="be1f4-258">Understand the Compliance Manager dashboard</span></span>

<span data-ttu-id="be1f4-259">合規性管理員儀表板專為您提供目前符合性狀況的一覽式視圖。</span><span class="sxs-lookup"><span data-stu-id="be1f4-259">The Compliance Manager dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="be1f4-260">![合規性管理員-儀表板](../media/compliance-manager-dashboard.png "合規性管理員儀表板")</span><span class="sxs-lookup"><span data-stu-id="be1f4-260">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="be1f4-261">整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="be1f4-261">Overall compliance score</span></span>

<span data-ttu-id="be1f4-262">您的相容性分數主要是在頂端。</span><span class="sxs-lookup"><span data-stu-id="be1f4-262">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="be1f4-263">它會顯示以點為單位的百分比，可完成解決重要資料保護標準及法規的改進動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-263">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span> <span data-ttu-id="be1f4-264">[Microsoft 動作](compliance-manager-assessments.md#microsoft-actions-tab)中的點數，其為 microsoft 的管理，也是針對您的合規性分數計數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-264">Points from [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab), which are managed my Microsoft, also count toward your compliance score.</span></span>

<span data-ttu-id="be1f4-265">當您第一次進入合規性管理員時，您的初始分數是以[Microsoft 365 資料保護基準](compliance-manager-assessments.md#data-protection-baseline-default-assessment)為基礎。</span><span class="sxs-lookup"><span data-stu-id="be1f4-265">When you come to Compliance Manager for the first time, your initial score is based on the [Microsoft 365 data protection baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment).</span></span> <span data-ttu-id="be1f4-266">這項可供所有組織使用的基準評估是一組包含常見工業法規和標準的控制項。</span><span class="sxs-lookup"><span data-stu-id="be1f4-266">This baseline assessment, which is available to all organizations, is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="be1f4-267">合規性管理員會掃描現有的 Microsoft 365 解決方案，並根據您目前的隱私權和安全性設定，為您提供初步評估。</span><span class="sxs-lookup"><span data-stu-id="be1f4-267">Compliance Manager scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="be1f4-268">當您新增與貴組織相關的評估時，您的分數會變得更有意義。</span><span class="sxs-lookup"><span data-stu-id="be1f4-268">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

<span data-ttu-id="be1f4-269">**深入瞭解：** [瞭解如何計算您的合規性分數](compliance-score-calculation.md)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-269">**Learn more:** [Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="be1f4-270">關鍵改進動作</span><span class="sxs-lookup"><span data-stu-id="be1f4-270">Key improvement actions</span></span>

<span data-ttu-id="be1f4-271">本節列出您現在可以採取的最大改進動作，以對您的整體合規性分數產生最大的積極影響。</span><span class="sxs-lookup"><span data-stu-id="be1f4-271">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="be1f4-272">選取 [ **查看所有改進動作** ]，以移至您的 [改進動作] 頁面。</span><span class="sxs-lookup"><span data-stu-id="be1f4-272">Select **View all improvement actions** to go to your improvement actions page.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="be1f4-273">影響您分數的解決方案</span><span class="sxs-lookup"><span data-stu-id="be1f4-273">Solutions that affect your score</span></span>

<span data-ttu-id="be1f4-274">本節著重強調包含改進動作的解決方案，該動作可對您的分數產生積極影響，以及這些解決方案中未完成的改進動作數目。</span><span class="sxs-lookup"><span data-stu-id="be1f4-274">This section highlights solutions containing improvement actions that can positively impact your score, and the number of outstanding improvement actions in those solutions.</span></span> <span data-ttu-id="be1f4-275">選取 [ **查看所有解決方案** 以流覽您的解決方案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="be1f4-275">Select **View all solutions** to visit your solutions page.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="be1f4-276">合規性分數分解</span><span class="sxs-lookup"><span data-stu-id="be1f4-276">Compliance score breakdown</span></span>

<span data-ttu-id="be1f4-277">本節以兩種不同的方式提供更詳細的分數視圖：</span><span class="sxs-lookup"><span data-stu-id="be1f4-277">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="be1f4-278">**類別**：顯示資料保護類別中的整體分數百分比，例如「保護資訊」或「管理裝置」。</span><span class="sxs-lookup"><span data-stu-id="be1f4-278">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="be1f4-279">**評估**：顯示針對特定合規性和資料保護標準、法規或法律（如 GDPR 或 NIST 800-53）進行評估的進度百分比。</span><span class="sxs-lookup"><span data-stu-id="be1f4-279">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="be1f4-280">篩選儀表板視圖</span><span class="sxs-lookup"><span data-stu-id="be1f4-280">Filtering your dashboard view</span></span>

<span data-ttu-id="be1f4-281">您可以篩選儀表板視圖，只查看與特定規章和標準、解決方案、動作類型、評估群組或資料保護類別相關的專案。</span><span class="sxs-lookup"><span data-stu-id="be1f4-281">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="be1f4-282">以這種方式篩選您的視圖也會篩選您儀表板上的分數，以顯示您已從您的篩選準則中取得的總可能點數的點數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-282">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="be1f4-283">若要套用篩選：</span><span class="sxs-lookup"><span data-stu-id="be1f4-283">To apply filters:</span></span>

1. <span data-ttu-id="be1f4-284">選取儀表板右上方的 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-284">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="be1f4-285">從 [ **篩選** ] 浮出] 窗格 **中選取篩選** 準則，然後選取 [套用]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-285">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="be1f4-286">套用篩選後，您會看到即時調整您的分數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-286">After you apply a filter, you’ll see your score adjusted in real time.</span></span> <span data-ttu-id="be1f4-287">合規性分數百分比和分解資訊，以及改善動作和解決方案，現在只適用于篩選準則所涵蓋的資料。</span><span class="sxs-lookup"><span data-stu-id="be1f4-287">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="be1f4-288">如果您登出合規性管理員，當您重新登入時，您的篩選視圖仍會保留。</span><span class="sxs-lookup"><span data-stu-id="be1f4-288">If you sign out of Compliance Manager, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="be1f4-289">若要移除篩選：</span><span class="sxs-lookup"><span data-stu-id="be1f4-289">To remove filters:</span></span>

- <span data-ttu-id="be1f4-290">在 [套用的 **篩選** ] 標題高於您的合規性分數之外，選取您要移除的個別篩選旁邊的 **X** 。或</span><span class="sxs-lookup"><span data-stu-id="be1f4-290">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="be1f4-291">選取儀表板右上方的 [ **篩選** ]，然後在 [ **篩選** ] 飛入窗格上，選取 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-291">Select **Filter** on the upper-right side of your dashboard, then on the **Filters** flyout pane, select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="be1f4-292">改進動作頁面</span><span class="sxs-lookup"><span data-stu-id="be1f4-292">Improvement actions page</span></span>

<span data-ttu-id="be1f4-293">[改進動作](compliance-manager-improvement-actions.md) 是由您的組織管理的動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-293">[Improvement actions](compliance-manager-improvement-actions.md) are actions managed by your organization.</span></span> <span data-ttu-id="be1f4-294">使用改善動作有助於集中執行您的合規性活動，並與資料保護法規和標準相符。</span><span class="sxs-lookup"><span data-stu-id="be1f4-294">Working with improvement actions helps to centralize your compliance activities and align with data protection regulations and standards.</span></span> <span data-ttu-id="be1f4-295">每個改進動作都提供詳細的執行指導，以及將您帶入適當解決方案的連結。</span><span class="sxs-lookup"><span data-stu-id="be1f4-295">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="be1f4-296">您可以將改進動作指派給組織中的使用者，以執行實施和測試工作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-296">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="be1f4-297">您也可以在改進動作中儲存檔、記事及記錄狀態更新。</span><span class="sxs-lookup"><span data-stu-id="be1f4-297">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="be1f4-298">查看您的改善動作</span><span class="sxs-lookup"><span data-stu-id="be1f4-298">View your improvement actions</span></span>

<span data-ttu-id="be1f4-299">「合規性管理員」儀表板會顯示您的 **重要改進動作。**</span><span class="sxs-lookup"><span data-stu-id="be1f4-299">The Compliance Manager dashboard shows your **key improvement actions.**</span></span> <span data-ttu-id="be1f4-300">若要查看您的所有改進動作，請選取儀表板上的 [改進動作] 索引標籤，這會將您帶入 [改進動作] 頁面。</span><span class="sxs-lookup"><span data-stu-id="be1f4-300">To view all of your improvement actions, select the Improvement actions tab on your dashboard, which brings you to your improvement actions page.</span></span> <span data-ttu-id="be1f4-301">您也可以選取 [View the 儀表板上的重要改進動作] 下的 [所有改進動作]，以取得您的 [改進動作] 頁面。</span><span class="sxs-lookup"><span data-stu-id="be1f4-301">You can also select View all improvement actions underneath the list of key improvement actions on your dashboard to get to your improvement actions page.</span></span>

<span data-ttu-id="be1f4-302">[改進動作] 頁面會顯示組織所管理的所有改進動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-302">The improvement actions page shows all of the improvement actions that are managed by your organization.</span></span> <span data-ttu-id="be1f4-303">您可以在每個評估中查看 Microsoft 所管理的動作 (深入瞭解 [Microsoft 動作](compliance-manager-assessments.md#microsoft-actions-tab)) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-303">Actions that are managed by Microsoft can be viewed within each assessment (learn more about [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab)).</span></span>

<span data-ttu-id="be1f4-304">如果您在 [改進動作] 頁面上有很長的動作清單，篩選您的視圖可能會很有説明。</span><span class="sxs-lookup"><span data-stu-id="be1f4-304">If you have a long list of actions on your improvement actions page, it may be helpful to filter your view.</span></span> <span data-ttu-id="be1f4-305">在 [動作] 清單的右上角選取 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-305">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="be1f4-306">當 [ **篩選** ] 飛入窗格出現時，根據規定和標準、解決方案和群組選取您的準則。</span><span class="sxs-lookup"><span data-stu-id="be1f4-306">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="be1f4-307">您也可以選取右上角的 [ **群組** ]，以自訂您的視圖。</span><span class="sxs-lookup"><span data-stu-id="be1f4-307">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="be1f4-308">從下拉式功能表中，選取 [按群組、解決方案、類別、動作類型或狀態來查看]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-308">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="be1f4-309">此頁面的預設視圖不會顯示已 **通過** 測試狀態的改善動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-309">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="be1f4-310">若要查看已通過測試的動作，請檢查 [篩選] 飛入窗格中的 [已 **傳遞** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="be1f4-310">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="be1f4-311">僅限具有 **超過** 您分數之測試狀態的動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-311">Only actions with a test status of **Passed** count toward your score.</span></span> <span data-ttu-id="be1f4-312">有些動作可能會顯示「暫止的 **更新」標籤。**</span><span class="sxs-lookup"><span data-stu-id="be1f4-312">Some actions may show a **pending update label.**</span></span> <span data-ttu-id="be1f4-313">深入瞭解 [改進動作的更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-313">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

<span data-ttu-id="be1f4-314">[改進動作] 頁面會顯示每個改進動作的下列資料點：</span><span class="sxs-lookup"><span data-stu-id="be1f4-314">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="be1f4-315">**達到的點數**：完成動作可供總可用點數的點數</span><span class="sxs-lookup"><span data-stu-id="be1f4-315">**Points achieved**: the number of points achieved out of the total available by completing the action</span></span>
- <span data-ttu-id="be1f4-316">**規章**：動作相關的規章或標準</span><span class="sxs-lookup"><span data-stu-id="be1f4-316">**Regulations**: the regulations or standards pertaining to the action</span></span>
- <span data-ttu-id="be1f4-317">**群組**：您指派動作的群組</span><span class="sxs-lookup"><span data-stu-id="be1f4-317">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="be1f4-318">**解決方案**：您可以用來執行動作的解決方案</span><span class="sxs-lookup"><span data-stu-id="be1f4-318">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="be1f4-319">**評估**：包含動作的評估</span><span class="sxs-lookup"><span data-stu-id="be1f4-319">**Assessments**: the assessments that contain the action</span></span>
- <span data-ttu-id="be1f4-320">**類別**：相關的資料保護類別 (例如，保護資訊、管理裝置等等 ) </span><span class="sxs-lookup"><span data-stu-id="be1f4-320">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="be1f4-321">**測試狀態**：</span><span class="sxs-lookup"><span data-stu-id="be1f4-321">**Test status**:</span></span>
    - <span data-ttu-id="be1f4-322">**無** –未記錄任何狀態更新</span><span class="sxs-lookup"><span data-stu-id="be1f4-322">**None** – no status update recorded</span></span>
    - <span data-ttu-id="be1f4-323">**未評估** -尚未開始測試</span><span class="sxs-lookup"><span data-stu-id="be1f4-323">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="be1f4-324">已成功測試 **傳遞** 的執行</span><span class="sxs-lookup"><span data-stu-id="be1f4-324">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="be1f4-325">**失敗的低風險** -測試失敗、低風險</span><span class="sxs-lookup"><span data-stu-id="be1f4-325">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="be1f4-326">**失敗之中度風險** -測試失敗，中度風險</span><span class="sxs-lookup"><span data-stu-id="be1f4-326">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="be1f4-327">**失敗的高風險** -測試失敗，高風險</span><span class="sxs-lookup"><span data-stu-id="be1f4-327">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="be1f4-328">**超出範圍** –動作不在評估範圍內，也不會影響您的分數</span><span class="sxs-lookup"><span data-stu-id="be1f4-328">**Out of scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="be1f4-329">**若要偵測-若要** 進行手動測試，表示已執行動作但未測試;若為自動測試，表示動作正等候自動化結果</span><span class="sxs-lookup"><span data-stu-id="be1f4-329">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="be1f4-330">**無法檢測** -無法判斷自動狀態</span><span class="sxs-lookup"><span data-stu-id="be1f4-330">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="be1f4-331">**部分測試** –對部分點獎勵的自動化計分</span><span class="sxs-lookup"><span data-stu-id="be1f4-331">**Partially tested** – automated scoring that awards partial points</span></span>

<span data-ttu-id="be1f4-332">**深入瞭解：** [查看如何指派及執行有關改進動作的工作](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-332">**Learn more:** [See how to assign and perform work on improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="be1f4-333">解決方案頁面</span><span class="sxs-lookup"><span data-stu-id="be1f4-333">Solutions page</span></span>

<span data-ttu-id="be1f4-334">[解決方案] 頁面會顯示以方案組織的盈餘分析和潛在點數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-334">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="be1f4-335">從這個視圖中查看剩下的點數和改善動作，可協助您瞭解哪些解決方案需要更立即關注。</span><span class="sxs-lookup"><span data-stu-id="be1f4-335">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="be1f4-336">選取 [合規性管理員] 儀表板上的 [ **解決方案** ] 索引標籤，尋找 [解決方案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="be1f4-336">Find the solutions page by selecting the **Solutions** tab on your Compliance Manager dashboard.</span></span> <span data-ttu-id="be1f4-337">您也可以選取 [ **查看所有** 在您的儀表板右上方] 區段中 **，影響您分數** 的解決方案。</span><span class="sxs-lookup"><span data-stu-id="be1f4-337">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="be1f4-338">篩選您的解決方案視圖</span><span class="sxs-lookup"><span data-stu-id="be1f4-338">Filtering your solutions view</span></span>

<span data-ttu-id="be1f4-339">若要篩選您的解決方案視圖：</span><span class="sxs-lookup"><span data-stu-id="be1f4-339">To filter your view of solutions:</span></span>

1. <span data-ttu-id="be1f4-340">從評估清單的左上角選取 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-340">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="be1f4-341">在 [ **篩選器** ] 飛入窗格上，勾選所需準則的旁邊， (標準和規章、解決方案、動作類型、合規性管理員群組、類別) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-341">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="be1f4-342">選取 [ **套用** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="be1f4-342">Select the **Apply** button.</span></span> <span data-ttu-id="be1f4-343">篩選窗格會關閉，您會看到篩選的視圖。</span><span class="sxs-lookup"><span data-stu-id="be1f4-343">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="be1f4-344">您也可以將您的視圖修改成按群組、產品或法規來查看評估，方法是從評估清單上方的 [ **群組** ] 下拉式功能表中選取群組的類型。</span><span class="sxs-lookup"><span data-stu-id="be1f4-344">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-action-from-the-solution-page"></a><span data-ttu-id="be1f4-345">從解決方案頁面採取動作</span><span class="sxs-lookup"><span data-stu-id="be1f4-345">Taking action from the solution page</span></span>

<span data-ttu-id="be1f4-346">[解決方案] 頁面會顯示您組織中已連接至 [改進動作] 的解決方案。</span><span class="sxs-lookup"><span data-stu-id="be1f4-346">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="be1f4-347">該表列出每個方案對您的整體分數、在該方案中取得及可能的點數，以及在該解決方案中群組的其餘改進動作數目，可增加您的分數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-347">The table lists each solution’s contribution to your overall score, the points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="be1f4-348">您可以使用下列兩種方式從這個畫面採取動作：</span><span class="sxs-lookup"><span data-stu-id="be1f4-348">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="be1f4-349">在您預定方案的列上，選取 [ **其他動作** ] 欄底下的超連結號碼。</span><span class="sxs-lookup"><span data-stu-id="be1f4-349">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="be1f4-350">您會看到 [改進動作] 畫面的篩選視圖，顯示該解決方案的未測試改進動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-350">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="be1f4-351">在您預定方案的列上，選取 [ **開啟方案** ] 欄下的 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-351">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="be1f4-352">您會在 Microsoft 365 中看到方案或位置，並 Office 365 安全性與合規性中心，您可以採取建議的動作。</span><span class="sxs-lookup"><span data-stu-id="be1f4-352">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="be1f4-353">評估頁面</span><span class="sxs-lookup"><span data-stu-id="be1f4-353">Assessments page</span></span>

<span data-ttu-id="be1f4-354">「評估」頁面會列出您為組織設定的所有 [評估](compliance-manager-assessments.md) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-354">The assessments page lists all the [assessments](compliance-manager-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="be1f4-355">您的相容性分數分母是由所有追蹤的評估所決定。</span><span class="sxs-lookup"><span data-stu-id="be1f4-355">Your compliance score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="be1f4-356">當您新增更多評估時，您將會看到 [改進動作] 頁面上列出的更多改進動作，以及您的相容性分數分母增加。</span><span class="sxs-lookup"><span data-stu-id="be1f4-356">As you add more assessments, you'll see more improvement actions listed on your improvement actions page, and your compliance score denominator increases.</span></span>

<span data-ttu-id="be1f4-357">靠近頁面頂端的 [已啟動 **範本** ] 計數器會顯示目前使用中的評估範本數目，以供您的組織使用的範本總數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-357">The **activated templates** counter near the top of the page shows the number of active assessment templates currently in use out of the total number of templates available for your organization to use.</span></span> <span data-ttu-id="be1f4-358">如需詳細資訊，請參閱 [範本類型](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-358">See [Template type](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) for more information.</span></span>

<span data-ttu-id="be1f4-359">評估頁面摘要列出每項評估的重要資訊：</span><span class="sxs-lookup"><span data-stu-id="be1f4-359">The assessments page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="be1f4-360">**評估**：評估的名稱</span><span class="sxs-lookup"><span data-stu-id="be1f4-360">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="be1f4-361">**狀態**：</span><span class="sxs-lookup"><span data-stu-id="be1f4-361">**Status**:</span></span>
    - <span data-ttu-id="be1f4-362">**完成** -所有控制項的狀態皆為「已傳遞」，或是至少有一個已傳遞，其餘部分則為「範圍外」</span><span class="sxs-lookup"><span data-stu-id="be1f4-362">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="be1f4-363">**不完整** –至少有一個控制項的狀態為 "failed"</span><span class="sxs-lookup"><span data-stu-id="be1f4-363">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="be1f4-364">**None** -尚未測試所有控制項</span><span class="sxs-lookup"><span data-stu-id="be1f4-364">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="be1f4-365">**進行中** 的改進動作具有任何其他狀態，包括「進行中」、「部分信用」或「未檢查」</span><span class="sxs-lookup"><span data-stu-id="be1f4-365">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="be1f4-366">**評估進度**：完成工作的百分比（以成功測試的控制項數目衡量）</span><span class="sxs-lookup"><span data-stu-id="be1f4-366">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="be1f4-367">**您的改進動作**：已完成的動作數目，可滿足您的控制項的實現</span><span class="sxs-lookup"><span data-stu-id="be1f4-367">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="be1f4-368">**Microsoft 動作**：已完成的動作數目，可滿足 Microsoft 控制項的實現</span><span class="sxs-lookup"><span data-stu-id="be1f4-368">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="be1f4-369">**群組**：評估所屬之群組的名稱</span><span class="sxs-lookup"><span data-stu-id="be1f4-369">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="be1f4-370">**產品**：相關聯的 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="be1f4-370">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="be1f4-371">**規章**：套用至評估的規章標準、原則或法律</span><span class="sxs-lookup"><span data-stu-id="be1f4-371">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="be1f4-372">篩選評估視圖</span><span class="sxs-lookup"><span data-stu-id="be1f4-372">Filtering your assessments view</span></span>

<span data-ttu-id="be1f4-373">篩選您的評估：</span><span class="sxs-lookup"><span data-stu-id="be1f4-373">To filter you view of assessments:</span></span>

1. <span data-ttu-id="be1f4-374">從評估清單的左上角選取 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="be1f4-374">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="be1f4-375">在 [ **篩選** ] 浮出控制項窗格上，檢查所需的準則。</span><span class="sxs-lookup"><span data-stu-id="be1f4-375">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="be1f4-376">選取 [ **套用** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="be1f4-376">Select the **Apply** button.</span></span> <span data-ttu-id="be1f4-377">篩選窗格會關閉，您會看到篩選的視圖。</span><span class="sxs-lookup"><span data-stu-id="be1f4-377">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="be1f4-378">您也可以將您的視圖修改成按群組、產品或法規來查看評估，方法是從評估清單上方的 [ **群組** ] 下拉式功能表中選取群組的類型。</span><span class="sxs-lookup"><span data-stu-id="be1f4-378">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="be1f4-379">預設評估</span><span class="sxs-lookup"><span data-stu-id="be1f4-379">Default assessment</span></span>

<span data-ttu-id="be1f4-380">根據預設，您會在 [評估] 頁面上看到 [資料保護基準](compliance-manager-assessments.md#data-protection-baseline-default-assessment) 評估。</span><span class="sxs-lookup"><span data-stu-id="be1f4-380">By default, you'll see the [Data Protection Baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment) assessment on the assessments page.</span></span> <span data-ttu-id="be1f4-381">合規性管理員也會提供數個預先建立的 [範本](compliance-manager-templates-list.md) 來建立評估。</span><span class="sxs-lookup"><span data-stu-id="be1f4-381">Compliance Manager also provides several pre-built [templates](compliance-manager-templates-list.md) for building assessments.</span></span>

## <a name="assessment-templates-page"></a><span data-ttu-id="be1f4-382">評定範本頁面</span><span class="sxs-lookup"><span data-stu-id="be1f4-382">Assessment templates page</span></span>

<span data-ttu-id="be1f4-383">範本是在合規性管理員中建立評定的架構。</span><span class="sxs-lookup"><span data-stu-id="be1f4-383">A template is a framework for creating an assessment in Compliance Manager.</span></span> <span data-ttu-id="be1f4-384">評定範本頁面會顯示範本清單和重要詳細資料。</span><span class="sxs-lookup"><span data-stu-id="be1f4-384">The assessment templates page displays a list of templates and key details.</span></span> <span data-ttu-id="be1f4-385">此清單包含合規性管理員所提供的範本，以及您的組織已修改或建立的任何範本。</span><span class="sxs-lookup"><span data-stu-id="be1f4-385">The list includes templates provided by Compliance Manager as well as any templates your organization has modified or created.</span></span> <span data-ttu-id="be1f4-386">您可以套用篩選器，以根據憑證、產品範圍、國家、行業及建立者，尋找範本。</span><span class="sxs-lookup"><span data-stu-id="be1f4-386">You can apply filters to find a template based on certification, product scope, country, industry, and who created it.</span></span>

<span data-ttu-id="be1f4-387">靠近頁面頂端的 [已啟動 **範本** ] 計數器會顯示目前使用中的評估範本數目，以供您的組織使用的範本總數。</span><span class="sxs-lookup"><span data-stu-id="be1f4-387">The **activated templates** counter near the top of the page shows the number of active assessment templates currently in use out of the total number of templates available for your organization to use.</span></span> <span data-ttu-id="be1f4-388">如需詳細資訊，請參閱 [範本類型](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) 。</span><span class="sxs-lookup"><span data-stu-id="be1f4-388">See [Template type](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) for more information.</span></span>

<span data-ttu-id="be1f4-389">從其列中選取範本以顯示其 [詳細資料] 頁面，其中包含範本的描述，以及憑證、範圍和控制項詳細資料的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="be1f4-389">Select a template from its row to bring up its details page, which contains a description of the template and further information about certification, scope, and controls details.</span></span> <span data-ttu-id="be1f4-390">您可以從這個頁面選取適當的按鈕來建立評估、將範本資料匯出至 Excel，或修改範本。</span><span class="sxs-lookup"><span data-stu-id="be1f4-390">From this page you can select the appropriate buttons to create an assessment, export the template data to Excel, or modify the template.</span></span>

<span data-ttu-id="be1f4-391">**深入瞭解：** 請 [參閱如何使用評估範本](compliance-manager-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="be1f4-391">**Learn more:** [Read how to work with assessment templates](compliance-manager-templates.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="be1f4-392">下一步</span><span class="sxs-lookup"><span data-stu-id="be1f4-392">Next step</span></span>
<span data-ttu-id="be1f4-393">[設定評估](compliance-manager-assessments.md)，以自訂合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="be1f4-393">Customize Compliance Manager by [setting up assessments](compliance-manager-assessments.md).</span></span>