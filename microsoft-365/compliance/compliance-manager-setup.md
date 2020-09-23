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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 設定 Microsoft 合規性管理員使用者許可權和角色，以及設定自動的動作測試。 管理使用者記錄並篩選儀表板視圖。
ms.openlocfilehash: ead4fe60a11bcf78a318601c1de6d72f2490c567
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204346"
---
# <a name="get-started-with-compliance-manager"></a><span data-ttu-id="a099e-104">開始使用合規性管理員</span><span class="sxs-lookup"><span data-stu-id="a099e-104">Get started with Compliance Manager</span></span>

<span data-ttu-id="a099e-105">**本文內容：** 本文可協助您設定合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="a099e-105">**In this article:** This article helps you set up Compliance Manager.</span></span> <span data-ttu-id="a099e-106">瞭解如何 **存取** 合規性管理員、 **設定角色和許可權**，以及設定 **改進動作的自動測試**。</span><span class="sxs-lookup"><span data-stu-id="a099e-106">Learn how to **access** Compliance Manager, **set roles and permissions**, and configure **automatic testing of improvement actions**.</span></span> <span data-ttu-id="a099e-107">逐步流覽 **您的合規性管理員儀表板** ，瞭解主要頁面：「改進動作」頁面、「解決方案」頁面、「評估」頁面及「評估範本」頁面。</span><span class="sxs-lookup"><span data-stu-id="a099e-107">Walk through **your Compliance Manager dashboard** and understand the main pages: the improvement actions page, the solutions page, the assessments page, and the assessment templates page.</span></span>

## <a name="who-can-access-compliance-manager"></a><span data-ttu-id="a099e-108">誰可以存取合規性管理員</span><span class="sxs-lookup"><span data-stu-id="a099e-108">Who can access Compliance Manager</span></span>

<span data-ttu-id="a099e-109">合規性管理員可供使用 Office 365 和 Microsoft 365 授權的組織使用。</span><span class="sxs-lookup"><span data-stu-id="a099e-109">Compliance Manager is available to organizations with Office 365 and Microsoft 365 licenses.</span></span> <span data-ttu-id="a099e-110">評估可用性和管理功能取決於您的授權合約。</span><span class="sxs-lookup"><span data-stu-id="a099e-110">Assessment availability and management capabilities depend on your licensing agreement.</span></span>  <span data-ttu-id="a099e-111">[查看服務說明的詳細資料](https://go.microsoft.com/fwlink/?linkid=2132371)。</span><span class="sxs-lookup"><span data-stu-id="a099e-111">[View service description details](https://go.microsoft.com/fwlink/?linkid=2132371).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a099e-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="a099e-112">Before you begin</span></span>

<span data-ttu-id="a099e-113">您組織的 Microsoft 365 全域管理員可能是第一個存取合規性管理員的使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-113">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Manager.</span></span> <span data-ttu-id="a099e-114">我們建議全域管理員登入，並設定第一次造訪合規性管理員時所述的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="a099e-114">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Manager for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="a099e-115">登入</span><span class="sxs-lookup"><span data-stu-id="a099e-115">Sign in</span></span>

1. <span data-ttu-id="a099e-116">請移至 [microsoft 365 規範中心](https://compliance.microsoft.com/) ，並使用您的 Microsoft 365 全域管理員帳戶登 **入** 。</span><span class="sxs-lookup"><span data-stu-id="a099e-116">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global administrator account.</span></span>
2. <span data-ttu-id="a099e-117">在左功能窗格上選取 [ **合規性管理員** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-117">Select **Compliance Manager** on the left navigation pane.</span></span> <span data-ttu-id="a099e-118">您將會收到您的 [合規性管理員儀表板](#understand-the-compliance-manger-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="a099e-118">You'll arrive at your [Compliance Manager dashboard](#understand-the-compliance-manger-dashboard).</span></span>

<span data-ttu-id="a099e-119">Access 合規性管理員的直接連結為 [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) 。</span><span class="sxs-lookup"><span data-stu-id="a099e-119">The direct link to access Compliance Manager is [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="a099e-120">設定使用者權限並指派角色</span><span class="sxs-lookup"><span data-stu-id="a099e-120">Set user permissions and assign roles</span></span>

<span data-ttu-id="a099e-121">合規性管理員使用以角色為基礎的存取控制 (RBAC) 許可權模型。</span><span class="sxs-lookup"><span data-stu-id="a099e-121">Compliance Manager uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="a099e-122">只有獲指派角色的使用者可以存取合規性管理員，且每個使用者所允許的動作受到 [角色類型](#role-types)的限制。</span><span class="sxs-lookup"><span data-stu-id="a099e-122">Only users who are assigned a role may access Compliance Manager, and the actions allowed by each user are restricted by [role type](#role-types).</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="a099e-123">設定許可權的位置</span><span class="sxs-lookup"><span data-stu-id="a099e-123">Where to set permissions</span></span>

<span data-ttu-id="a099e-124">擁有組織全域系統管理員角色的人員可以在 Microsoft 365 規範中心以及 Azure Active Directory (Azure AD) 中設定使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="a099e-124">The person holding the global admin role for your organization can set user permissions in the Microsoft 365 compliance center, as well as in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="a099e-125">若要在 Microsoft 365 規範中心內設定許可權並指派角色，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a099e-125">To set permissions and assign roles from within the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="a099e-126">從[Microsoft 365 規範中心](https://compliance.microsoft.com/)的任何地方，選取左側導覽的**許可權**。</span><span class="sxs-lookup"><span data-stu-id="a099e-126">Select **Permissions** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a099e-127">在最上方的位置，請在 [ **Office 365 中選取要查看及管理角色的連結]，請移至這裡。**</span><span class="sxs-lookup"><span data-stu-id="a099e-127">Near the top, select the link at **“To view and manage roles in Office 365, please go here.”**</span></span> <span data-ttu-id="a099e-128">新的索引標籤會以 Office 365 安全性 & 規範中心開啟 ([瞭解您](microsoft-365-compliance-center.md#frequently-asked-questions) 已重新導向) 的原因。</span><span class="sxs-lookup"><span data-stu-id="a099e-128">A new tab will open to the Office 365 Security & Compliance Center ([learn why you’re redirected](microsoft-365-compliance-center.md#frequently-asked-questions)).</span></span>

3. <span data-ttu-id="a099e-129">尋找您要新增一或多個使用者的角色群組，然後選取 [組名] 左側的方塊。</span><span class="sxs-lookup"><span data-stu-id="a099e-129">Find the role group to which you want to add one or more users, and check the box to the left of the group name.</span></span> <span data-ttu-id="a099e-130"> (請參閱 [下列角色和相關功能的清單](#role-types)。</span><span class="sxs-lookup"><span data-stu-id="a099e-130">(See the [list of roles and related functions below](#role-types).</span></span> <span data-ttu-id="a099e-131">會模仿角色名稱的角色群組名稱。 ) </span><span class="sxs-lookup"><span data-stu-id="a099e-131">The role group names mimic the role name.)</span></span>

4. <span data-ttu-id="a099e-132">在該群組的彈出窗格上，選取 [**成員**] 標題底下的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-132">On the flyout pane for that group, select **Edit** under the **Members** header.</span></span>

5. <span data-ttu-id="a099e-133">選取 **[選擇成員**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-133">Select **Choose members**.</span></span> <span data-ttu-id="a099e-134">會出現另一個快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="a099e-134">Another flyout window will appear.</span></span>

6. <span data-ttu-id="a099e-135">選取 [ **+ 新增** ] 選擇一或多個要新增至群組的使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-135">Select **+ Add** to choose one or more users to add to the group.</span></span>

7. <span data-ttu-id="a099e-136">選取您要新增之名稱旁邊的核取方塊，然後選取底部的 [ **新增** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a099e-136">Select the checkbox next to the names you want to add, then select the **Add** button at the bottom.</span></span>

8. <span data-ttu-id="a099e-137">當您完成指派使用者時，請選取 [ **完成**]，然後選取 [ **儲存**]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-137">When you’re done assigning users, select **Done**, then select **Save**, then **Close**.</span></span>

##### <a name="more-about-the-office-365-secruity--compliance-center"></a><span data-ttu-id="a099e-138">有關 Office 365 Secruity 的詳細資訊 & 規範中心</span><span class="sxs-lookup"><span data-stu-id="a099e-138">More about the Office 365 Secruity & Compliance Center</span></span>

<span data-ttu-id="a099e-139">深入瞭解 [Office 365 安全性 & 合規性中心的許可權](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="a099e-139">Learn more about [permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

<span data-ttu-id="a099e-140">如果您沒有 Office 365 安全性與合規性中心的存取權，或者您需要在 Microsoft 服務信任入口網站中存取經典版本的合規性管理員，則服務信任入口網站中的系統管理員設定會提供另一種方法， ([view 說明](/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud?view=o365-worldwide.md#assigning-compliance-manager-roles-to-users)) 中指派角色。</span><span class="sxs-lookup"><span data-stu-id="a099e-140">If you don't have access to the Office 365 Security and Compliance Center, or if you need to access the classic version of Compliance Manager in the Microsoft Service Trust Portal,  the Admin settings in the Service Trust Portal provides another way to assign roles ([view instructions](/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud?view=o365-worldwide.md#assigning-compliance-manager-roles-to-users)).</span></span> <span data-ttu-id="a099e-141">請注意，這些角色在其功能上的限制更為有限。</span><span class="sxs-lookup"><span data-stu-id="a099e-141">Be aware that such roles are more limited in their functionality.</span></span>

##### <a name="more-about-azure-ad"></a><span data-ttu-id="a099e-142">有關 Azure AD 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a099e-142">More about Azure AD</span></span>

<span data-ttu-id="a099e-143">若要在 Azure AD 中指派角色和設定許可權，請參閱 [使用 Azure Active Directory 指派系統管理員和非系統管理員角色給使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="a099e-143">To assign roles and set permissions in Azure AD, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

<span data-ttu-id="a099e-144">使用 Azure AD 身分識別但未安裝 Office 365 或 Microsoft 365 訂閱的使用者，將無法存取 Microsoft 365 規範中心內的合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="a099e-144">Users with Azure AD identities who don't have Office 365 or Microsoft 365 subscriptions won't be able to access Compliance Manager in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a099e-145">若要在存取合規性管理員中尋求協助，請與 [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com)聯繫。</span><span class="sxs-lookup"><span data-stu-id="a099e-145">To seek assistance in accessing Compliance Manager, contact [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).</span></span>

### <a name="role-types"></a><span data-ttu-id="a099e-146">角色類型</span><span class="sxs-lookup"><span data-stu-id="a099e-146">Role types</span></span>

<span data-ttu-id="a099e-147">下表顯示合規性管理員中每個角色所允許的功能。</span><span class="sxs-lookup"><span data-stu-id="a099e-147">The table below shows the functions allowed by each role in Compliance Manager.</span></span> <span data-ttu-id="a099e-148">該表也顯示每個 [AZURE AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 如何對應至符合性管理員角色。</span><span class="sxs-lookup"><span data-stu-id="a099e-148">The table also shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to Compliance Manger roles.</span></span> <span data-ttu-id="a099e-149">使用者必須至少要有合規性管理員讀者角色或 Azure AD 全域讀卡機角色，才可存取合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="a099e-149">Users will need at least the Compliance Manager reader role, or Azure AD global reader role, to access Compliance Manager.</span></span>


| <span data-ttu-id="a099e-150">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="a099e-150">User can:</span></span> | <span data-ttu-id="a099e-151">合規性管理員角色</span><span class="sxs-lookup"><span data-stu-id="a099e-151">Compliance Manager role</span></span> | <span data-ttu-id="a099e-152">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="a099e-152">Azure AD role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="a099e-153">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="a099e-153">**Read but not edit data**</span></span>| <span data-ttu-id="a099e-154">合規性管理員讀取者</span><span class="sxs-lookup"><span data-stu-id="a099e-154">Compliance Manager Reader</span></span>  | <span data-ttu-id="a099e-155">Azure AD 全域讀取器，安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="a099e-155">Azure AD Global reader, Security reader</span></span> | 
| <span data-ttu-id="a099e-156">**編輯資料**</span><span class="sxs-lookup"><span data-stu-id="a099e-156">**Edit data**</span></span>| <span data-ttu-id="a099e-157">合規性管理員貢獻</span><span class="sxs-lookup"><span data-stu-id="a099e-157">Compliance Manager Contribution</span></span> | <span data-ttu-id="a099e-158">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="a099e-158">Compliance Administrator</span></span> | 
| <span data-ttu-id="a099e-159">**編輯測試結果**</span><span class="sxs-lookup"><span data-stu-id="a099e-159">**Edit test results**</span></span>| <span data-ttu-id="a099e-160">合規性管理員評估</span><span class="sxs-lookup"><span data-stu-id="a099e-160">Compliance Manager Assessment</span></span> | <span data-ttu-id="a099e-161">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="a099e-161">Compliance Administrator</span></span> | 
| <span data-ttu-id="a099e-162">**管理評估、範本及租使用者資料**</span><span class="sxs-lookup"><span data-stu-id="a099e-162">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="a099e-163">合規性管理員管理</span><span class="sxs-lookup"><span data-stu-id="a099e-163">Compliance Manager Administration</span></span> | <span data-ttu-id="a099e-164">合規性管理員、規範資料管理員、安全性管理員</span><span class="sxs-lookup"><span data-stu-id="a099e-164">Compliance Administrator, Compliance Data Administrator, Security Administrator</span></span>  | 
| <span data-ttu-id="a099e-165">**指派使用者**</span><span class="sxs-lookup"><span data-stu-id="a099e-165">**Assign users**</span></span>| <span data-ttu-id="a099e-166">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="a099e-166">Global Administrator</span></span> | <span data-ttu-id="a099e-167">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="a099e-167">Global Administrator</span></span> | 

## <a name="settings-for-automated-testing-and-user-history"></a><span data-ttu-id="a099e-168">自動測試和使用者歷程記錄的設定</span><span class="sxs-lookup"><span data-stu-id="a099e-168">Settings for automated testing and user history</span></span>

<span data-ttu-id="a099e-169">Microsoft 365 合規性中心的合規性管理員設定可讓您啟用及停用自動改進動作的測試。</span><span class="sxs-lookup"><span data-stu-id="a099e-169">The Compliance Manager settings in the Microsoft 365 compliance center allow you to enable and disable automatic testing of improvement actions.</span></span> <span data-ttu-id="a099e-170">這些設定也可讓您管理與改進動作相關聯之使用者的資料，包括將「改進」動作重新指派給其他使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="a099e-170">The settings also allow you to manage the data of users associated to improvement actions, including the ability to reassign improvement actions to a different user.</span></span>  <span data-ttu-id="a099e-171">只有具有全域系統管理員或合規性管理員角色的人員才能存取合規性管理員設定。</span><span class="sxs-lookup"><span data-stu-id="a099e-171">Only people with a global administrator or Compliance Manager Administrator role can access the Compliance Manager settings.</span></span>

### <a name="set-up-automated-testing"></a><span data-ttu-id="a099e-172">設定自動測試</span><span class="sxs-lookup"><span data-stu-id="a099e-172">Set up automated testing</span></span>

<span data-ttu-id="a099e-173">合規性管理員中的某些改進動作也是由 [Microsoft 安全分數](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)所監控。</span><span class="sxs-lookup"><span data-stu-id="a099e-173">Some improvement actions in Compliance Manager are also monitored by [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="a099e-174">您可以設定進行自動監控的動作自動測試，這表示在安全的分數中測試並更新動作時，這些結果會與合規性管理員中的相同動作同步處理，並在合規性分數中計數。</span><span class="sxs-lookup"><span data-stu-id="a099e-174">You can set up automated testing of actions that are jointly monitored, which means that when an action is tested and updated in Secure Score, those results synch with the same actions in Compliance Manager and count toward your compliance score.</span></span>

<span data-ttu-id="a099e-175">預設會針對合規性管理員的新組織開啟自動測試。</span><span class="sxs-lookup"><span data-stu-id="a099e-175">Automatic testing is turned on by default for organizations new to Compliance Manger.</span></span> <span data-ttu-id="a099e-176">當您第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間來完全收集資料，並將其劃分為您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="a099e-176">When you first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your compliance score.</span></span>  <span data-ttu-id="a099e-177">開啟自動測試時，不會更新動作的測試日期，但會更新其測試狀態。</span><span class="sxs-lookup"><span data-stu-id="a099e-177">When automated testing is turned on, the action’s test date won’t be updated, but its test status will update.</span></span> <span data-ttu-id="a099e-178">當建立新的評估時，會自動包含 Microsoft control 得分和安全評分整合。</span><span class="sxs-lookup"><span data-stu-id="a099e-178">When new assessments are created, scores automatically include Microsoft control scores and Secure Score integration.</span></span>

<span data-ttu-id="a099e-179">組織的全域管理員可以隨時變更自動測試的設定。</span><span class="sxs-lookup"><span data-stu-id="a099e-179">The global administrator for your organization can change the settings for automated testing at any time.</span></span> <span data-ttu-id="a099e-180">您可以關閉常見改進動作的自動測試，或為個別動作開啟自動測試。</span><span class="sxs-lookup"><span data-stu-id="a099e-180">You can turn off automated testing for common improvement actions, or turn it on for individual actions.</span></span> <span data-ttu-id="a099e-181">遵循下列指示變更您的自動測試設定。</span><span class="sxs-lookup"><span data-stu-id="a099e-181">Follow the instructions below to change your automated testing settings.</span></span>

#### <a name="to-manage-your-automated-testing-settings"></a><span data-ttu-id="a099e-182">若要管理您的自動測試設定：</span><span class="sxs-lookup"><span data-stu-id="a099e-182">To manage your automated testing settings:</span></span>

1. <span data-ttu-id="a099e-183">從[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽的**設定**。</span><span class="sxs-lookup"><span data-stu-id="a099e-183">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a099e-184">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-184">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="a099e-185">從左側導覽選取 [ **自動測試** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-185">Select **Automated testing** from the left navigation.</span></span>

4. <span data-ttu-id="a099e-186">選取 [適用] 按鈕，針對所有改進動作開啟自動測試、關閉所有動作的 [關閉] 或 [依個別動作開啟]。</span><span class="sxs-lookup"><span data-stu-id="a099e-186">Select the applicable button to turn on automatic testing for all improvement actions, turn it off for all actions, or turn on by individual action.</span></span>

5. <span data-ttu-id="a099e-187">如果您選取 [ **每次改進動作開啟**]，清單會顯示所有可用的改善動作，以供選擇。</span><span class="sxs-lookup"><span data-stu-id="a099e-187">If you select **Turn on per improvement action**, a list will show all the available improvement actions to choose from.</span></span>  <span data-ttu-id="a099e-188">選取您想要自動測試的任何動作旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="a099e-188">Check the box next to any action you want automatically tested.</span></span>

6. <span data-ttu-id="a099e-189">選取 [ **儲存** ] 以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="a099e-189">Select **Save** to save your settings.</span></span> <span data-ttu-id="a099e-190">您會在螢幕頂端看到您的選取專案已儲存的確認訊息。</span><span class="sxs-lookup"><span data-stu-id="a099e-190">You’ll receive a confirmation message at the top of your screen that your selection was saved.</span></span> <span data-ttu-id="a099e-191">如果您收到失敗通知，請再試一次。</span><span class="sxs-lookup"><span data-stu-id="a099e-191">If you receive a failure notice, try again.</span></span>

<span data-ttu-id="a099e-192">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="a099e-192">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="a099e-193">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-193">The Compliance Manager Administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

### <a name="manage-user-history"></a><span data-ttu-id="a099e-194">管理使用者歷程記錄</span><span class="sxs-lookup"><span data-stu-id="a099e-194">Manage user history</span></span>

<span data-ttu-id="a099e-195">「 **管理使用者記錄** 」設定可協助您快速識別在合規性管理員中使用「改進」動作的使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-195">The **Manage user history** settings help you quickly identify which users have worked with improvement actions in Compliance Manger.</span></span> <span data-ttu-id="a099e-196">與改進動作相關聯的身分識別使用者資料包括任何執行和測試工作已完成、檔上傳的檔，以及所輸入的任何附注。</span><span class="sxs-lookup"><span data-stu-id="a099e-196">The identifiable user data associated with improvement actions includes any implementation and testing work done, documents they uploaded, and any notes they entered.</span></span> <span data-ttu-id="a099e-197">若要瞭解和檢索此類型的資料，您的組織本身的合規性需求可能是必要的。</span><span class="sxs-lookup"><span data-stu-id="a099e-197">Understanding and retrieving this type of data may be necessary for your organization’s own compliance needs.</span></span>

<span data-ttu-id="a099e-198">使用者記錄設定也可讓您將所有的「改進動作」從一個使用者重新指派給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-198">The user history settings also allow you to reassign all improvement actions from one user to another.</span></span>

<span data-ttu-id="a099e-199">**若要尋找使用者記錄設定：**</span><span class="sxs-lookup"><span data-stu-id="a099e-199">**To find the user history settings:**</span></span>

1. <span data-ttu-id="a099e-200">從 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽的設定。</span><span class="sxs-lookup"><span data-stu-id="a099e-200">Select Settings on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a099e-201">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-201">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="a099e-202">從左側導覽中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-202">Select **Manage user history** from the left navigation.</span></span>

<span data-ttu-id="a099e-203">「 **管理使用者歷程記錄** 」頁面會顯示所有使用者的清單，其郵寄地址會指派給「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-203">The **manage user history** page shows a list of all users by email address who are assigned to an improvement action.</span></span> <span data-ttu-id="a099e-204">使用 [ **搜尋** ] 按鈕，透過輸入電子郵件地址來快速尋找特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-204">Use the **Search** button to quickly find a specific user by typing in their email address.</span></span>

<span data-ttu-id="a099e-205">在每個使用者的電子郵件地址右側，[ **選取** ] 下拉式功能表提供匯出報告、重新指派改進動作或刪除歷程記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="a099e-205">To the right of each user’s email address, the **Select** drop-down menu provides options to  export a report, reassign improvement actions, or delete history.</span></span> <span data-ttu-id="a099e-206">請參閱下列各節，以取得每個選項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a099e-206">See each section below for details about each option.</span></span>

#### <a name="export-a-report-of-user-history-data"></a><span data-ttu-id="a099e-207">匯出使用者記錄資料的報告</span><span class="sxs-lookup"><span data-stu-id="a099e-207">Export a report of user history data</span></span>

<span data-ttu-id="a099e-208">您可以匯出包含目前指派給使用者之改進動作清單的 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="a099e-208">You can export an Excel file containing a list of improvement actions currently assigned to a user.</span></span>  <span data-ttu-id="a099e-209">報告也會列出該使用者上傳的任何證據檔案。</span><span class="sxs-lookup"><span data-stu-id="a099e-209">The report also lists any evidence files uploaded by that user.</span></span> <span data-ttu-id="a099e-210">此資訊可協助您重新指派開啟的「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-210">This information can help you reassign open improvement actions.</span></span>

<span data-ttu-id="a099e-211">報表反映的是在建立日期後的「改進」動作狀態。</span><span class="sxs-lookup"><span data-stu-id="a099e-211">The report reflects the improvement action’s status as of its creation date.</span></span> <span data-ttu-id="a099e-212">這不是所有先前對其狀態或工作 (分派所做變更的歷史報告。瞭解如何 [從 [改進動作] 頁面匯出報告](compliance-manager-improvement-actions.md#export-a-report)) 。</span><span class="sxs-lookup"><span data-stu-id="a099e-212">It’s not a historical report of all previous changes to its status or assignment (learn how to [export a report from your improvement actions page](compliance-manager-improvement-actions.md#export-a-report)).</span></span>

<span data-ttu-id="a099e-213">**請遵循下列步驟，依使用者匯出報告：**</span><span class="sxs-lookup"><span data-stu-id="a099e-213">**Follow the steps below to export a report by user:**</span></span>

1. <span data-ttu-id="a099e-214">從[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽的**設定**。</span><span class="sxs-lookup"><span data-stu-id="a099e-214">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a099e-215">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-215">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="a099e-216">從左邊的流覽窗格中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-216">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="a099e-217">搜尋清單電子郵件地址，或選取 [ **搜尋** ] 並輸入使用者的電子郵件地址，以尋找預定的使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-217">Find your intended user by searching the list email addresses, or by selecting **Search** and entering the user’s email address.</span></span>

5. <span data-ttu-id="a099e-218">從 [ **選取** ] 下拉式功能表中，選擇 [ **匯出報告**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-218">From the **Select** drop-down menu, choose **Export report**.</span></span>

6. <span data-ttu-id="a099e-219">在報告的 Excel 檔案產生後，您就可以開啟它，並將它儲存到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="a099e-219">Once the Excel file of your report is generated, you can open it and save it to your local machine.</span></span>

#### <a name="reassign-improvement-actions-to-another-user"></a><span data-ttu-id="a099e-220">將改進動作重新指派給另一位使用者</span><span class="sxs-lookup"><span data-stu-id="a099e-220">Reassign improvement actions to another user</span></span>

<span data-ttu-id="a099e-221">您可以從某個使用者重新指派改進動作給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-221">You can reassign improvement actions from one user to another.</span></span> <span data-ttu-id="a099e-222">當您重新指派動作時，檔上傳的歷程記錄不會變更，但原來上傳檔的使用者名稱將不再出現在 [改進] 動作內。</span><span class="sxs-lookup"><span data-stu-id="a099e-222">When you reassign an action, the document upload history doesn't change, but the name of the user who originally uploaded the documentation no longer appears within the improvement action.</span></span>

<span data-ttu-id="a099e-223">**請遵循下列步驟，將改進動作重新指派給其他使用者：**</span><span class="sxs-lookup"><span data-stu-id="a099e-223">**Follow the steps below to reassign improvement actions to another user:**</span></span>

1. <span data-ttu-id="a099e-224">從[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽的**設定**。</span><span class="sxs-lookup"><span data-stu-id="a099e-224">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a099e-225">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-225">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="a099e-226">從左邊的流覽窗格中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-226">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="a099e-227">搜尋清單電子郵件地址，或選取 [ **搜尋** ] 並輸入該使用者的電子郵件地址，以尋找使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-227">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="a099e-228">從 [ **選取** ] 下拉式功能表中，選擇 [ **重新指派改進動作**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-228">From the **Select** drop-down menu, choose **Reassign improvement actions**.</span></span> <span data-ttu-id="a099e-229">隨即會出現 [ **重新指派改進動作** ] 彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="a099e-229">The **Reassign improvement actions** flyout pane will appear.</span></span>

6. <span data-ttu-id="a099e-230">在 [ **搜尋使用者** ] 欄位中，輸入 *您要指派「改進動作」* 之使用者的名稱或電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a099e-230">In the **Search users** field, enter the name or email address of the user you want assign the improvement actions *to*.</span></span>

7. <span data-ttu-id="a099e-231">當您看到 [ **改進動作將指派**給您的預定使用者名稱] 時，請選取使用者，然後選取 [ **指派動作**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-231">When you see the name of your intended user under **Improvement actions will be assigned to**, select the user, then select **Assign actions**.</span></span>

8. <span data-ttu-id="a099e-232">當重新指派完成時，您會在飛入窗格中看到一則確認訊息，以確認先前使用者的所有改進動作都已重新指派給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-232">When the reassignment is complete, you’ll see a confirmation message in the flyout pane confirming that all improvement actions from the previous user have been reassigned to the new user.</span></span> <span data-ttu-id="a099e-233">如果您收到重新指派失敗通知，請關閉視窗，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="a099e-233">If you receive a reassignment failure notice, close the window and try again.</span></span> <span data-ttu-id="a099e-234">若要關閉彈出窗格，請選取 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-234">To close the flyout pane, select **Done**.</span></span>

<span data-ttu-id="a099e-235">新的受託人會收到已獲指派給改進動作的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a099e-235">The new assignee receives an email that they've been assigned to an improvement action.</span></span> <span data-ttu-id="a099e-236">電子郵件包含 [改進動作的詳細資料] 頁面的直接連結。</span><span class="sxs-lookup"><span data-stu-id="a099e-236">The email contains a direct link into the improvement action's details page.</span></span>
 
 > [!NOTE]
> <span data-ttu-id="a099e-237">如果您重新指派具有暫止更新的動作，當重新指派後接受更新時，就會中斷重新分派電子郵件中動作的直接連結。</span><span class="sxs-lookup"><span data-stu-id="a099e-237">If you reassign an action that has a pending update, the direct link to the action in the reassignment email will break if the update is accepted after reassignment.</span></span> <span data-ttu-id="a099e-238">您可以在接受更新後，將動作重新指派給使用者，以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="a099e-238">You can fix this by re-assigning the action to the user after the update is accepted.</span></span> <span data-ttu-id="a099e-239">深入瞭解 [改進動作的更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。</span><span class="sxs-lookup"><span data-stu-id="a099e-239">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

#### <a name="delete-user-history"></a><span data-ttu-id="a099e-240">刪除使用者歷程記錄</span><span class="sxs-lookup"><span data-stu-id="a099e-240">Delete user history</span></span>

<span data-ttu-id="a099e-241">刪除使用者的歷程記錄會將其當作改進動作的擁有者移除，並且會從合規性管理員中的所有其他欄位移除其名稱。</span><span class="sxs-lookup"><span data-stu-id="a099e-241">Deleting a user’s history will remove them as an owner of improvement actions, and will remove their name from all other fields in Compliance Manger.</span></span> <span data-ttu-id="a099e-242">當您刪除使用者的記錄時，他們所擁有的「提升」動作將不會顯示 **指定** 的值，直到指派新的使用者為止。</span><span class="sxs-lookup"><span data-stu-id="a099e-242">When you delete a user’s history, the improvement actions they owned will not display an **Assigned to** value until a new user is assigned.</span></span> <span data-ttu-id="a099e-243">任何上傳至 [提升] 動作的檔都會顯示 **使用者移除** 的位置，取代刪除的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="a099e-243">Any documents uploaded to the improvement action will show **User removed** in place of the deleted user’s name.</span></span> <span data-ttu-id="a099e-244">刪除使用者歷程記錄是永久的。</span><span class="sxs-lookup"><span data-stu-id="a099e-244">Deleting user history is permanent.</span></span>

<span data-ttu-id="a099e-245">若要刪除使用者的歷程記錄，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a099e-245">To delete a user’s history, follow the steps below:</span></span>

1. <span data-ttu-id="a099e-246">從[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的任何地方，選取左側導覽的**設定**。</span><span class="sxs-lookup"><span data-stu-id="a099e-246">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="a099e-247">在 [設定] 頁面上，選取 [ **合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-247">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="a099e-248">從左邊的流覽窗格中，選取 [ **管理使用者歷程記錄** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-248">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="a099e-249">搜尋清單電子郵件地址，或選取 [ **搜尋** ] 並輸入該使用者的電子郵件地址，以尋找使用者。</span><span class="sxs-lookup"><span data-stu-id="a099e-249">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="a099e-250">從 [ **選取** ] 下拉式功能表中，選擇 [ **刪除歷程記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-250">From the **Select** drop-down menu, choose **Delete history**.</span></span>

6. <span data-ttu-id="a099e-251">隨即會出現一個視窗，要求您確認永久刪除使用者的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="a099e-251">A window appears asking you to confirm the permanent deletion of the user’s history.</span></span> <span data-ttu-id="a099e-252">若要繼續刪除，請選取 [ **刪除歷程記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-252">To continue with deletion, select **Delete history**.</span></span> <span data-ttu-id="a099e-253">若要離開但不刪除記錄，請選取 [ **取消**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-253">To leave without deleting the history, select **Cancel**.</span></span>

7. <span data-ttu-id="a099e-254">您將會在 [ **管理使用者歷程記錄** ] 頁面上，收到使用者已刪除之記錄的上方的確認訊息。</span><span class="sxs-lookup"><span data-stu-id="a099e-254">You’ll arrive back at the **Manage user history** page with a confirmation message at the top that the history for the user was deleted.</span></span>

## <a name="understand-the-compliance-manger-dashboard"></a><span data-ttu-id="a099e-255">瞭解合規性管理員儀表板</span><span class="sxs-lookup"><span data-stu-id="a099e-255">Understand the Compliance Manger dashboard</span></span>

<span data-ttu-id="a099e-256">合規性管理員儀表板專為您提供目前符合性狀況的一覽式視圖。</span><span class="sxs-lookup"><span data-stu-id="a099e-256">The Compliance Manager dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="a099e-257">![合規性管理員-儀表板](../media/compliance-manager-dashboard.png "合規性管理員儀表板")</span><span class="sxs-lookup"><span data-stu-id="a099e-257">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="a099e-258">整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="a099e-258">Overall compliance score</span></span>

<span data-ttu-id="a099e-259">您的相容性分數主要是在頂端。</span><span class="sxs-lookup"><span data-stu-id="a099e-259">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="a099e-260">它會顯示以點為單位的百分比，可完成解決重要資料保護標準及法規的改進動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-260">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span> <span data-ttu-id="a099e-261">[Microsoft 動作](compliance-manager-assessments.md#microsoft-actions-tab)中的點數，其為 microsoft 的管理，也是針對您的合規性分數計數。</span><span class="sxs-lookup"><span data-stu-id="a099e-261">Points from [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab), which are managed my Microsoft, also count toward your compliance score.</span></span>

<span data-ttu-id="a099e-262">當您第一次進入合規性管理員時，您的初始分數是以 [Microsoft 365 資料保護基準](compliance-manager-assessments.md#data-protection-baseline-default-assessment)為基礎。</span><span class="sxs-lookup"><span data-stu-id="a099e-262">When you come to Compliance Manager for the first time, your initial score is based on the [Microsoft 365 data protection baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment).</span></span> <span data-ttu-id="a099e-263">這項可供所有組織使用的基準評估是一組包含常見工業法規和標準的控制項。</span><span class="sxs-lookup"><span data-stu-id="a099e-263">This baseline assessment, which is available to all organizations, is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="a099e-264">合規性管理員會掃描現有的 Microsoft 365 解決方案，並根據您目前的隱私權和安全性設定，為您提供初步評估。</span><span class="sxs-lookup"><span data-stu-id="a099e-264">Compliance Manager scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="a099e-265">當您新增與貴組織相關的評估時，您的分數會變得更有意義。</span><span class="sxs-lookup"><span data-stu-id="a099e-265">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

<span data-ttu-id="a099e-266">**深入瞭解：** [瞭解如何計算您的合規性分數](compliance-score-calculation.md)。</span><span class="sxs-lookup"><span data-stu-id="a099e-266">**Learn more:** [Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="a099e-267">重要改進動作</span><span class="sxs-lookup"><span data-stu-id="a099e-267">Key improvement actions</span></span>

<span data-ttu-id="a099e-268">本節列出您現在可以採取的最大改進動作，以對您的整體合規性分數產生最大的積極影響。</span><span class="sxs-lookup"><span data-stu-id="a099e-268">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="a099e-269">選取 [ **查看所有改進動作** ]，以移至您的 [改進動作] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a099e-269">Select **View all improvement actions** to go to your improvement actions page.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="a099e-270">影響分數的解決方案</span><span class="sxs-lookup"><span data-stu-id="a099e-270">Solutions that affect your score</span></span>

<span data-ttu-id="a099e-271">本節著重強調包含改進動作的解決方案，該動作可對您的分數產生積極影響，以及這些解決方案中未完成的改進動作數目。</span><span class="sxs-lookup"><span data-stu-id="a099e-271">This section highlights solutions containing improvement actions that can positively impact your score, and the number of outstanding improvement actions in those solutions.</span></span> <span data-ttu-id="a099e-272">選取 [ **查看所有解決方案** 以流覽您的解決方案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a099e-272">Select **View all solutions** to visit your solutions page.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="a099e-273">合規性分數細分</span><span class="sxs-lookup"><span data-stu-id="a099e-273">Compliance score breakdown</span></span>

<span data-ttu-id="a099e-274">本節以兩種不同的方式提供更詳細的分數視圖：</span><span class="sxs-lookup"><span data-stu-id="a099e-274">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="a099e-275">**類別**：顯示資料保護類別中的整體分數百分比，例如「保護資訊」或「管理裝置」。</span><span class="sxs-lookup"><span data-stu-id="a099e-275">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="a099e-276">**評估**：顯示針對特定合規性和資料保護標準、法規或法律（如 GDPR 或 NIST 800-53）進行評估的進度百分比。</span><span class="sxs-lookup"><span data-stu-id="a099e-276">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="a099e-277">篩選儀表板視圖</span><span class="sxs-lookup"><span data-stu-id="a099e-277">Filtering your dashboard view</span></span>

<span data-ttu-id="a099e-278">您可以篩選儀表板視圖，只查看與特定規章和標準、解決方案、動作類型、評估群組或資料保護類別相關的專案。</span><span class="sxs-lookup"><span data-stu-id="a099e-278">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="a099e-279">以這種方式篩選您的視圖也會篩選您儀表板上的分數，以顯示您已從您的篩選準則中取得的總可能點數的點數。</span><span class="sxs-lookup"><span data-stu-id="a099e-279">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="a099e-280">若要套用篩選：</span><span class="sxs-lookup"><span data-stu-id="a099e-280">To apply filters:</span></span>

1. <span data-ttu-id="a099e-281">選取儀表板右上方的 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-281">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="a099e-282">從 [ **篩選** ] 浮出] 窗格 **中選取篩選**準則，然後選取 [套用]。</span><span class="sxs-lookup"><span data-stu-id="a099e-282">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="a099e-283">套用篩選後，您會看到即時調整您的分數。</span><span class="sxs-lookup"><span data-stu-id="a099e-283">After you apply a filter, you’ll see your score adjusted in real time.</span></span> <span data-ttu-id="a099e-284">合規性分數百分比和分解資訊，以及改善動作和解決方案，現在只適用于篩選準則所涵蓋的資料。</span><span class="sxs-lookup"><span data-stu-id="a099e-284">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="a099e-285">如果您登出合規性管理員，當您重新登入時，您的篩選視圖仍會保留。</span><span class="sxs-lookup"><span data-stu-id="a099e-285">If you sign out of Compliance Manager, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="a099e-286">若要移除篩選：</span><span class="sxs-lookup"><span data-stu-id="a099e-286">To remove filters:</span></span>

- <span data-ttu-id="a099e-287">在 [套用的 **篩選** ] 標題高於您的合規性分數之外，選取您要移除的個別篩選旁邊的 **X** 。或</span><span class="sxs-lookup"><span data-stu-id="a099e-287">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="a099e-288">選取儀表板右上方的 [ **篩選** ]，然後在 [ **篩選** ] 飛入窗格上，選取 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-288">Select **Filter** on the upper-right side of your dashboard, then on the **Filters** flyout pane, select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="a099e-289">改進動作頁面</span><span class="sxs-lookup"><span data-stu-id="a099e-289">Improvement actions page</span></span>

<span data-ttu-id="a099e-290">[改進動作](compliance-manager-improvement-actions.md) 是由您的組織管理的動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-290">[Improvement actions](compliance-manager-improvement-actions.md) are actions managed by your organization.</span></span> <span data-ttu-id="a099e-291">使用改善動作有助於集中執行您的合規性活動，並與資料保護法規和標準相符。</span><span class="sxs-lookup"><span data-stu-id="a099e-291">Working with improvement actions helps to centralize your compliance activities and align with data protection regulations and standards.</span></span> <span data-ttu-id="a099e-292">每個改進動作都提供詳細的執行指導，以及將您帶入適當解決方案的連結。</span><span class="sxs-lookup"><span data-stu-id="a099e-292">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="a099e-293">您可以將改進動作指派給組織中的使用者，以執行實施和測試工作。</span><span class="sxs-lookup"><span data-stu-id="a099e-293">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="a099e-294">您也可以在改進動作中儲存檔、記事及記錄狀態更新。</span><span class="sxs-lookup"><span data-stu-id="a099e-294">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="a099e-295">查看您的改善動作</span><span class="sxs-lookup"><span data-stu-id="a099e-295">View your improvement actions</span></span>

<span data-ttu-id="a099e-296">「合規性管理員」儀表板會顯示您的 **重要改進動作。**</span><span class="sxs-lookup"><span data-stu-id="a099e-296">The Compliance Manager dashboard shows your **key improvement actions.**</span></span> <span data-ttu-id="a099e-297">若要查看您的所有改進動作，請選取儀表板上的 [改進動作] 索引標籤，這會將您帶入 [改進動作] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a099e-297">To view all of your improvement actions, select the Improvement actions tab on your dashboard, which brings you to your improvement actions page.</span></span> <span data-ttu-id="a099e-298">您也可以選取 [View the 儀表板上的重要改進動作] 下的 [所有改進動作]，以取得您的 [改進動作] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a099e-298">You can also select View all improvement actions underneath the list of key improvement actions on your dashboard to get to your improvement actions page.</span></span>

<span data-ttu-id="a099e-299">[改進動作] 頁面會顯示組織所管理的所有改進動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-299">The improvement actions page shows all of the improvement actions that are managed by your organization.</span></span> <span data-ttu-id="a099e-300">您可以在每個評估中查看 Microsoft 所管理的動作 (深入瞭解 [Microsoft 動作](compliance-manager-assessments.md#microsoft-actions-tab)) 。</span><span class="sxs-lookup"><span data-stu-id="a099e-300">Actions that are managed by Microsoft can be viewed within each assessment (learn more about [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab)).</span></span>

<span data-ttu-id="a099e-301">如果您在 [改進動作] 頁面上有很長的動作清單，篩選您的視圖可能會很有説明。</span><span class="sxs-lookup"><span data-stu-id="a099e-301">If you have a long list of actions on your improvement actions page, it may be helpful to filter your view.</span></span> <span data-ttu-id="a099e-302">在 [動作] 清單的右上角選取 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-302">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="a099e-303">當 [ **篩選** ] 飛入窗格出現時，根據規定和標準、解決方案和群組選取您的準則。</span><span class="sxs-lookup"><span data-stu-id="a099e-303">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="a099e-304">您也可以選取右上角的 [ **群組** ]，以自訂您的視圖。</span><span class="sxs-lookup"><span data-stu-id="a099e-304">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="a099e-305">從下拉式功能表中，選取 [按群組、解決方案、類別、動作類型或狀態來查看]。</span><span class="sxs-lookup"><span data-stu-id="a099e-305">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="a099e-306">此頁面的預設視圖不會顯示已 **通過**測試狀態的改善動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-306">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="a099e-307">若要查看已通過測試的動作，請檢查 [篩選] 飛入窗格中的 [已 **傳遞** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="a099e-307">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="a099e-308">僅限具有 **超過** 您分數之測試狀態的動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-308">Only actions with a test status of **Passed** count toward your score.</span></span> <span data-ttu-id="a099e-309">有些動作可能會顯示「暫止的 **更新」標籤。**</span><span class="sxs-lookup"><span data-stu-id="a099e-309">Some actions may show a **pending update label.**</span></span> <span data-ttu-id="a099e-310">深入瞭解 [改進動作的更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。</span><span class="sxs-lookup"><span data-stu-id="a099e-310">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

<span data-ttu-id="a099e-311">[改進動作] 頁面會顯示每個改進動作的下列資料點：</span><span class="sxs-lookup"><span data-stu-id="a099e-311">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="a099e-312">**達到的點數**：完成動作可供總可用點數的點數</span><span class="sxs-lookup"><span data-stu-id="a099e-312">**Points achieved**: the number of points achieved out of the total available by completing the action</span></span>
- <span data-ttu-id="a099e-313">**規章**：動作相關的規章或標準</span><span class="sxs-lookup"><span data-stu-id="a099e-313">**Regulations**: the regulations or standards pertaining to the action</span></span>
- <span data-ttu-id="a099e-314">**群組**：您指派動作的群組</span><span class="sxs-lookup"><span data-stu-id="a099e-314">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="a099e-315">**解決方案**：您可以用來執行動作的解決方案</span><span class="sxs-lookup"><span data-stu-id="a099e-315">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="a099e-316">**評估**：包含動作的評估</span><span class="sxs-lookup"><span data-stu-id="a099e-316">**Assessments**: the assessments that contain the action</span></span>
- <span data-ttu-id="a099e-317">**類別**：相關的資料保護類別 (例如，保護資訊、管理裝置等等 ) </span><span class="sxs-lookup"><span data-stu-id="a099e-317">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="a099e-318">**測試狀態**：</span><span class="sxs-lookup"><span data-stu-id="a099e-318">**Test status**:</span></span>
    - <span data-ttu-id="a099e-319">**無** –未記錄任何狀態更新</span><span class="sxs-lookup"><span data-stu-id="a099e-319">**None** – no status update recorded</span></span>
    - <span data-ttu-id="a099e-320">**未評估** -尚未開始測試</span><span class="sxs-lookup"><span data-stu-id="a099e-320">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="a099e-321">已成功測試**傳遞**的執行</span><span class="sxs-lookup"><span data-stu-id="a099e-321">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="a099e-322">**失敗的低風險** -測試失敗、低風險</span><span class="sxs-lookup"><span data-stu-id="a099e-322">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="a099e-323">**失敗之中度風險** -測試失敗，中度風險</span><span class="sxs-lookup"><span data-stu-id="a099e-323">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="a099e-324">**失敗的高風險** -測試失敗，高風險</span><span class="sxs-lookup"><span data-stu-id="a099e-324">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="a099e-325">**超出範圍** –動作不在評估範圍內，也不會影響您的分數</span><span class="sxs-lookup"><span data-stu-id="a099e-325">**Out of scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="a099e-326">**若要偵測-若要** 進行手動測試，表示已執行動作但未測試;若為自動測試，表示動作正等候自動化結果</span><span class="sxs-lookup"><span data-stu-id="a099e-326">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="a099e-327">**無法檢測** -無法判斷自動狀態</span><span class="sxs-lookup"><span data-stu-id="a099e-327">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="a099e-328">**部分測試** –對部分點獎勵的自動化計分</span><span class="sxs-lookup"><span data-stu-id="a099e-328">**Partially tested** – automated scoring that awards partial points</span></span>

<span data-ttu-id="a099e-329">**深入瞭解：** [查看如何指派及執行有關改進動作的工作](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="a099e-329">**Learn more:** [See how to assign and perform work on improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="a099e-330">解決方案頁面</span><span class="sxs-lookup"><span data-stu-id="a099e-330">Solutions page</span></span>

<span data-ttu-id="a099e-331">[解決方案] 頁面會顯示以方案組織的盈餘分析和潛在點數。</span><span class="sxs-lookup"><span data-stu-id="a099e-331">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="a099e-332">從這個視圖中查看剩下的點數和改善動作，可協助您瞭解哪些解決方案需要更立即關注。</span><span class="sxs-lookup"><span data-stu-id="a099e-332">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="a099e-333">選取 [合規性管理員] 儀表板上的 [ **解決方案** ] 索引標籤，尋找 [解決方案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a099e-333">Find the solutions page by selecting the **Solutions** tab on your Compliance Manager dashboard.</span></span> <span data-ttu-id="a099e-334">您也可以選取 [ **查看所有** 在您的儀表板右上方] 區段中 **，影響您分數** 的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a099e-334">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="a099e-335">篩選您的解決方案視圖</span><span class="sxs-lookup"><span data-stu-id="a099e-335">Filtering your solutions view</span></span>

<span data-ttu-id="a099e-336">若要篩選您的解決方案視圖：</span><span class="sxs-lookup"><span data-stu-id="a099e-336">To filter your view of solutions:</span></span>

1. <span data-ttu-id="a099e-337">從評估清單的左上角選取 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-337">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="a099e-338">在 [ **篩選器** ] 飛入窗格上，勾選所需準則的旁邊， (標準和規章、解決方案、動作類型、合規性管理員群組、類別) 。</span><span class="sxs-lookup"><span data-stu-id="a099e-338">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="a099e-339">選取 [ **套用** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a099e-339">Select the **Apply** button.</span></span> <span data-ttu-id="a099e-340">篩選窗格會關閉，您會看到篩選的視圖。</span><span class="sxs-lookup"><span data-stu-id="a099e-340">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="a099e-341">您也可以將您的視圖修改成按群組、產品或法規來查看評估，方法是從評估清單上方的 [ **群組** ] 下拉式功能表中選取群組的類型。</span><span class="sxs-lookup"><span data-stu-id="a099e-341">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-action-from-the-solution-page"></a><span data-ttu-id="a099e-342">從解決方案頁面採取動作</span><span class="sxs-lookup"><span data-stu-id="a099e-342">Taking action from the solution page</span></span>

<span data-ttu-id="a099e-343">[解決方案] 頁面會顯示您組織中已連接至 [改進動作] 的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a099e-343">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="a099e-344">該表列出每個方案對您的整體分數、在該方案中取得及可能的點數，以及在該解決方案中群組的其餘改進動作數目，可增加您的分數。</span><span class="sxs-lookup"><span data-stu-id="a099e-344">The table lists each solution’s contribution to your overall score, the points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="a099e-345">您可以使用下列兩種方式從這個畫面採取動作：</span><span class="sxs-lookup"><span data-stu-id="a099e-345">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="a099e-346">在您預定方案的列上，選取 [ **其他動作** ] 欄底下的超連結號碼。</span><span class="sxs-lookup"><span data-stu-id="a099e-346">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="a099e-347">您會看到 [改進動作] 畫面的篩選視圖，顯示該解決方案的未測試改進動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-347">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="a099e-348">在您預定方案的列上，選取 [ **開啟方案** ] 欄下的 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="a099e-348">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="a099e-349">您會在 Microsoft 365 和 Office 365 安全性與合規性中心中看到解決方案或位置，您可以採取建議的動作。</span><span class="sxs-lookup"><span data-stu-id="a099e-349">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="a099e-350">評估頁面</span><span class="sxs-lookup"><span data-stu-id="a099e-350">Assessments page</span></span>

<span data-ttu-id="a099e-351">「評估」頁面會列出您為組織設定的所有 [評估](compliance-manager-assessments.md) 。</span><span class="sxs-lookup"><span data-stu-id="a099e-351">The assessments page lists all the [assessments](compliance-manager-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="a099e-352">您的相容性分數分母是由所有追蹤的評估所決定。</span><span class="sxs-lookup"><span data-stu-id="a099e-352">Your compliance score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="a099e-353">當您新增更多評估時，您將會看到 [改進動作] 頁面上列出的更多改進動作，以及您的相容性分數分母增加。</span><span class="sxs-lookup"><span data-stu-id="a099e-353">As you add more assessments, you'll see more improvement actions listed on your improvement actions page, and your compliance score denominator increases.</span></span>

<span data-ttu-id="a099e-354">評估頁面摘要列出每項評估的重要資訊：</span><span class="sxs-lookup"><span data-stu-id="a099e-354">The assessments page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="a099e-355">**評估**：評估的名稱</span><span class="sxs-lookup"><span data-stu-id="a099e-355">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="a099e-356">**狀態**：</span><span class="sxs-lookup"><span data-stu-id="a099e-356">**Status**:</span></span>
    - <span data-ttu-id="a099e-357">**完成** -所有控制項的狀態皆為「已傳遞」，或是至少有一個已傳遞，其餘部分則為「範圍外」</span><span class="sxs-lookup"><span data-stu-id="a099e-357">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="a099e-358">**不完整** –至少有一個控制項的狀態為 "failed"</span><span class="sxs-lookup"><span data-stu-id="a099e-358">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="a099e-359">**None** -尚未測試所有控制項</span><span class="sxs-lookup"><span data-stu-id="a099e-359">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="a099e-360">**進行中** 的改進動作具有任何其他狀態，包括「進行中」、「部分信用」或「未檢查」</span><span class="sxs-lookup"><span data-stu-id="a099e-360">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="a099e-361">**評估進度**：完成工作的百分比（以成功測試的控制項數目衡量）</span><span class="sxs-lookup"><span data-stu-id="a099e-361">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="a099e-362">**您的改進動作**：已完成的動作數目，可滿足您的控制項的實現</span><span class="sxs-lookup"><span data-stu-id="a099e-362">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="a099e-363">**Microsoft 動作**：已完成的動作數目，可滿足 Microsoft 控制項的實現</span><span class="sxs-lookup"><span data-stu-id="a099e-363">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="a099e-364">**群組**：評估所屬之群組的名稱</span><span class="sxs-lookup"><span data-stu-id="a099e-364">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="a099e-365">**產品**：相關的 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="a099e-365">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="a099e-366">**規章**：套用至評估的規章標準、原則或法律</span><span class="sxs-lookup"><span data-stu-id="a099e-366">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="a099e-367">篩選評估視圖</span><span class="sxs-lookup"><span data-stu-id="a099e-367">Filtering your assessments view</span></span>

<span data-ttu-id="a099e-368">篩選您的評估：</span><span class="sxs-lookup"><span data-stu-id="a099e-368">To filter you view of assessments:</span></span>

1. <span data-ttu-id="a099e-369">從評估清單的左上角選取 [ **篩選** ]。</span><span class="sxs-lookup"><span data-stu-id="a099e-369">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="a099e-370">在 [ **篩選** ] 浮出控制項窗格上，檢查所需的準則。</span><span class="sxs-lookup"><span data-stu-id="a099e-370">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="a099e-371">選取 [ **套用** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a099e-371">Select the **Apply** button.</span></span> <span data-ttu-id="a099e-372">篩選窗格會關閉，您會看到篩選的視圖。</span><span class="sxs-lookup"><span data-stu-id="a099e-372">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="a099e-373">您也可以將您的視圖修改成按群組、產品或法規來查看評估，方法是從評估清單上方的 [ **群組** ] 下拉式功能表中選取群組的類型。</span><span class="sxs-lookup"><span data-stu-id="a099e-373">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="a099e-374">預設評估</span><span class="sxs-lookup"><span data-stu-id="a099e-374">Default assessment</span></span>

<span data-ttu-id="a099e-375">根據預設，您會在 [評估] 頁面上看到 [資料保護基準](compliance-manager-assessments.md#data-protection-baseline-default-assessment) 評估。</span><span class="sxs-lookup"><span data-stu-id="a099e-375">By default, you'll see the [Data Protection Baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment) assessment on the assessments page.</span></span> <span data-ttu-id="a099e-376">合規性管理員也會提供數個預先建立的 [範本](compliance-manager-templates-list.md) 來建立評估。</span><span class="sxs-lookup"><span data-stu-id="a099e-376">Compliance Manager also provides several pre-built [templates](compliance-manager-templates-list.md) for building assessments.</span></span>

## <a name="assessment-templates-page"></a><span data-ttu-id="a099e-377">評估範本頁面</span><span class="sxs-lookup"><span data-stu-id="a099e-377">Assessment templates page</span></span>

<span data-ttu-id="a099e-378">範本是在合規性管理員中建立評估的架構。</span><span class="sxs-lookup"><span data-stu-id="a099e-378">A template is a framework for creating an assessment in Compliance Manager.</span></span> <span data-ttu-id="a099e-379">「評估範本」頁面會顯示範本及主要詳細資料的清單。</span><span class="sxs-lookup"><span data-stu-id="a099e-379">The assessment templates page displays a list of templates and key details.</span></span> <span data-ttu-id="a099e-380">此清單包含合規性管理員所提供的範本，以及您的組織已修改或建立的任何範本。</span><span class="sxs-lookup"><span data-stu-id="a099e-380">The list includes templates provided by Compliance Manager as well as any templates your organization has modified or created.</span></span> <span data-ttu-id="a099e-381">您可以套用篩選器，以根據憑證、產品範圍、國家、行業及建立者，尋找範本。</span><span class="sxs-lookup"><span data-stu-id="a099e-381">You can apply filters to find a template based on certification, product scope, country, industry, and who created it.</span></span>

<span data-ttu-id="a099e-382">從其列中選取範本以顯示其 [詳細資料] 頁面，其中包含範本的描述，以及憑證、範圍和控制項詳細資料的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a099e-382">Select a template from its row to bring up its details page, which contains a description of the template and further information about certification, scope, and controls details.</span></span> <span data-ttu-id="a099e-383">您可以從這個頁面選取適當的按鈕來建立評估、將範本資料匯出至 Excel 或修改範本。</span><span class="sxs-lookup"><span data-stu-id="a099e-383">From this page you can select the appropriate buttons to create an assessment, export the template data to Excel, or modify the template.</span></span>

<span data-ttu-id="a099e-384">**深入瞭解：** 請 [參閱如何使用評估範本](compliance-manager-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="a099e-384">**Learn more:** [Read how to work with assessment templates](compliance-manager-templates.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="a099e-385">下一步</span><span class="sxs-lookup"><span data-stu-id="a099e-385">Next step</span></span>
<span data-ttu-id="a099e-386">[設定評估](compliance-manager-assessments.md)，以自訂合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="a099e-386">Customize Compliance Manager by [setting up assessments](compliance-manager-assessments.md).</span></span>