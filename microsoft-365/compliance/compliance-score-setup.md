---
title: Microsoft 規範分數（預覽）設定
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
description: 瞭解如何設定及開始使用 Microsoft 合規性分數，以協助簡化及自動化風險評估。
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016188"
---
# <a name="compliance-score-preview-setup"></a><span data-ttu-id="5d774-103">合規性分數（預覽）設定</span><span class="sxs-lookup"><span data-stu-id="5d774-103">Compliance Score (preview) setup</span></span>

<span data-ttu-id="5d774-104">**本文內容：** 瞭解如何**存取**合規性分數、設定**角色和許可權**，以及設定**自動安全分數更新**。</span><span class="sxs-lookup"><span data-stu-id="5d774-104">**In this article:** Understand how to **access** Compliance Score, set **roles and permissions**, and configure **automatic Secure Score updates**.</span></span> <span data-ttu-id="5d774-105">本文也說明主要合規性分數頁面：**您的儀表板**、[改進動作] 頁面、[解決方案] 頁面及 [評估] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5d774-105">This article also explains the main Compliance Score pages: **your dashboard**, the improvement actions page, the solutions page, and the assessments page.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5d774-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="5d774-106">Before you begin</span></span>

<span data-ttu-id="5d774-107">您組織的 Microsoft 365 全域管理員可能會是第一個存取合規性分數的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d774-107">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="5d774-108">建議全域管理員登入，並設定第一次的訪問合規性分數時所述的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="5d774-108">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="5d774-109">登入</span><span class="sxs-lookup"><span data-stu-id="5d774-109">Sign in</span></span>

1. <span data-ttu-id="5d774-110">請移至[microsoft 365 規範中心](https://compliance.microsoft.com/)，並使用您的 Microsoft 365 全域管理員帳戶登**入**。</span><span class="sxs-lookup"><span data-stu-id="5d774-110">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="5d774-111">在左導覽窗格上選取 [**合規性分數**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-111">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="5d774-112">您應該會看到您[的評分分數儀表板與您的分數](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="5d774-112">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="5d774-113">存取合規性分數的直接連結 [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) 。</span><span class="sxs-lookup"><span data-stu-id="5d774-113">The direct link to access Compliance Score is [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="5d774-114">設定使用者權限並指派角色</span><span class="sxs-lookup"><span data-stu-id="5d774-114">Set user permissions and assign roles</span></span>

<span data-ttu-id="5d774-115">合規性分數使用以角色為基礎的存取控制（RBAC）許可權模型。</span><span class="sxs-lookup"><span data-stu-id="5d774-115">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="5d774-116">只有獲指派角色的使用者才可存取合規性分數，而且每個使用者所允許的動作都會受到角色類型的限制。</span><span class="sxs-lookup"><span data-stu-id="5d774-116">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="5d774-117">設定許可權的位置</span><span class="sxs-lookup"><span data-stu-id="5d774-117">Where to set permissions</span></span>

<span data-ttu-id="5d774-118">擁有組織之全域系統管理員角色的人員可以在[Azure Active Directory （AZURE AD）](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)或[合規性管理員](compliance-manager-overview.md#permissions)中設定使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="5d774-118">The person holding the global admin role for your organization can set user permissions in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) or in [Compliance Manager](compliance-manager-overview.md#permissions).</span></span> <span data-ttu-id="5d774-119">在這兩個位置中設定角色後，使用者即可存取合規性分數及合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="5d774-119">Once roles are set in either of these locations, users can access Compliance Score as well as Compliance Manager.</span></span>

### <a name="role-types"></a><span data-ttu-id="5d774-120">角色類型</span><span class="sxs-lookup"><span data-stu-id="5d774-120">Role types</span></span>

<span data-ttu-id="5d774-121">下表顯示每個[AZURE AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)如何對應至現有的合規性管理員角色，以及每個角色所允許的功能。</span><span class="sxs-lookup"><span data-stu-id="5d774-121">The table below shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span> <span data-ttu-id="5d774-122">使用者至少需要 Azure AD 全域讀卡機角色，才能存取合規性分數。</span><span class="sxs-lookup"><span data-stu-id="5d774-122">Users will need at least the Azure AD global reader role to access Compliance Score.</span></span>


| <span data-ttu-id="5d774-123">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="5d774-123">User can:</span></span> | <span data-ttu-id="5d774-124">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="5d774-124">Azure AD role</span></span> | <span data-ttu-id="5d774-125">合規性管理員角色</span><span class="sxs-lookup"><span data-stu-id="5d774-125">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="5d774-126">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="5d774-126">**Read but not edit data**</span></span>| <span data-ttu-id="5d774-127">Azure AD 全域讀取器</span><span class="sxs-lookup"><span data-stu-id="5d774-127">Azure AD global reader</span></span>  | <span data-ttu-id="5d774-128">Azure AD 全域讀取器</span><span class="sxs-lookup"><span data-stu-id="5d774-128">Azure AD global reader</span></span> | 
| <span data-ttu-id="5d774-129">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="5d774-129">**Read but not edit data**</span></span>| <span data-ttu-id="5d774-130">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="5d774-130">Security reader</span></span> | <span data-ttu-id="5d774-131">合規性管理員讀者</span><span class="sxs-lookup"><span data-stu-id="5d774-131">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="5d774-132">**編輯資料**</span><span class="sxs-lookup"><span data-stu-id="5d774-132">**Edit data**</span></span>| <span data-ttu-id="5d774-133">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-133">Compliance administrator</span></span> | <span data-ttu-id="5d774-134">合規性管理員參與者</span><span class="sxs-lookup"><span data-stu-id="5d774-134">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="5d774-135">**編輯測試結果**</span><span class="sxs-lookup"><span data-stu-id="5d774-135">**Edit test results**</span></span>| <span data-ttu-id="5d774-136">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-136">Compliance administrator</span></span> | <span data-ttu-id="5d774-137">合規性管理員 assessor</span><span class="sxs-lookup"><span data-stu-id="5d774-137">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="5d774-138">**管理評估、範本及租使用者資料**</span><span class="sxs-lookup"><span data-stu-id="5d774-138">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="5d774-139">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-139">Compliance administrator</span></span><br><span data-ttu-id="5d774-140">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-140">Compliance data administrator</span></span><br><span data-ttu-id="5d774-141">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-141">Security administrator</span></span> | <span data-ttu-id="5d774-142">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-142">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="5d774-143">**指派使用者**</span><span class="sxs-lookup"><span data-stu-id="5d774-143">**Assign users**</span></span>| <span data-ttu-id="5d774-144">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-144">Global administrator</span></span> | <span data-ttu-id="5d774-145">入口網站管理員</span><span class="sxs-lookup"><span data-stu-id="5d774-145">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="5d774-146">當您從相容性分數移至合規性管理員以在公開預覽期間完成工作時，您的瀏覽器會開啟新的索引標籤，並會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="5d774-146">When you go from Compliance Score to Compliance Manager to complete a task during public preview, your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="5d774-147">在標頭為「已是 Microsoft cloud services 客戶」的上方區段中？</span><span class="sxs-lookup"><span data-stu-id="5d774-147">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="5d774-148">登入您的帳戶，請選取 [登**入**Access 合規性管理員]。</span><span class="sxs-lookup"><span data-stu-id="5d774-148">Sign in to your account," select **Sign In** to access Compliance Manager.</span></span> <span data-ttu-id="5d774-149">您不需要重新輸入您的認證。</span><span class="sxs-lookup"><span data-stu-id="5d774-149">You won't need to re-enter your credentials.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="5d774-150">設定自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="5d774-150">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="5d774-151">根據預設，所有新租使用者皆已開啟「[安全分數](../security/mtp/microsoft-secure-score-new.md)自動更新」。</span><span class="sxs-lookup"><span data-stu-id="5d774-151">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score-new.md) automatic updates turned on.</span></span> <span data-ttu-id="5d774-152">所有由安全評分監控的動作，會自動更新合規性分數中相同動作的狀態。</span><span class="sxs-lookup"><span data-stu-id="5d774-152">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="5d774-153">您的全域系統管理員可以管理此設定，以關閉所有動作的自動更新，或個別設定動作的更新。</span><span class="sxs-lookup"><span data-stu-id="5d774-153">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="5d774-154">在公開預覽期間，您需要移至 Microsoft 服務信任入口網站（其中的合規性管理員所在）以管理安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="5d774-154">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="5d774-155">若要管理自動安全分數更新，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5d774-155">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="5d774-156">使用您的全域系統管理員帳戶登入[服務信任入口網站](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="5d774-156">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="5d774-157">在服務信任入口網站頂端功能表列上，按一下 [**其他**] 下的 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-157">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="5d774-158">在 [**安全分數**] 索引標籤中，選取對應的按鈕來**開啟所有動作**、**關閉所有動作**，或**設定每個動作。**</span><span class="sxs-lookup"><span data-stu-id="5d774-158">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="5d774-159">如果您選擇 [**依動作設定]，請**採取下列額外步驟，為個別動作開啟安全分數更新：</span><span class="sxs-lookup"><span data-stu-id="5d774-159">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="5d774-160">從上方功能表中選取 [**合規性管理員**] （不要選取 [合規性管理員（經典）]）。</span><span class="sxs-lookup"><span data-stu-id="5d774-160">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic),").</span></span>

5. <span data-ttu-id="5d774-161">在螢幕的右上角選取 [**租使用者管理**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-161">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="5d774-162">在 [**客戶動作**] 窗格上，在 [**受影響的動作**] 欄下，以省略號（**...**）尋找您的預定動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-162">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="5d774-163">按一下省略號，然後選取 [**編輯]。**</span><span class="sxs-lookup"><span data-stu-id="5d774-163">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="5d774-164">將**安全分數連續更新**切換開關切換為 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="5d774-164">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="5d774-165">選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="5d774-165">Select **Save.**</span></span> <span data-ttu-id="5d774-166">安全分數連續監控現在已開啟該動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-166">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="5d774-167">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="5d774-167">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="5d774-168">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-168">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="5d774-169">深入了解</span><span class="sxs-lookup"><span data-stu-id="5d774-169">Learn more</span></span>

<span data-ttu-id="5d774-170">[閱讀有關管理安全分數更新的資訊](compliance-manager-release-notes.md#secure-score)。</span><span class="sxs-lookup"><span data-stu-id="5d774-170">[Read about managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="5d774-171">瞭解規範分數儀表板</span><span class="sxs-lookup"><span data-stu-id="5d774-171">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="5d774-172">合規性分數儀表板的設計目的是讓您快速瞭解目前的相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="5d774-172">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="5d774-173">![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="5d774-173">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="5d774-174">整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="5d774-174">Overall compliance score</span></span>

<span data-ttu-id="5d774-175">您的相容性分數主要是在頂端。</span><span class="sxs-lookup"><span data-stu-id="5d774-175">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="5d774-176">它會顯示以點為單位的百分比，可完成解決重要資料保護標準及法規的改進動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-176">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="5d774-177">當您第一次達成法規遵從性分數時，您的初始分數是以內建的[Microsoft 365 資料保護基準](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)（一組包含常見工業法規和標準的控制項）為基礎。</span><span class="sxs-lookup"><span data-stu-id="5d774-177">When you come to Compliance Score for the first time, your initial score is based on the built-in [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="5d774-178">合規性分數會掃描現有的 Microsoft 365 解決方案，並根據您目前的隱私權和安全性設定，為您提供初步評估。</span><span class="sxs-lookup"><span data-stu-id="5d774-178">Compliance Score scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="5d774-179">當您新增與貴組織相關的評估時，您的分數會變得更有意義。</span><span class="sxs-lookup"><span data-stu-id="5d774-179">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="5d774-180">深入了解</span><span class="sxs-lookup"><span data-stu-id="5d774-180">Learn more</span></span>
<span data-ttu-id="5d774-181">[瞭解如何計算您的合規性分數](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="5d774-181">[Understand how your compliance score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="5d774-182">重要改進動作</span><span class="sxs-lookup"><span data-stu-id="5d774-182">Key improvement actions</span></span>

<span data-ttu-id="5d774-183">本節列出您現在可以採取的最大改進動作，以對您的整體合規性分數產生最大的積極影響。</span><span class="sxs-lookup"><span data-stu-id="5d774-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="5d774-184">影響分數的解決方案</span><span class="sxs-lookup"><span data-stu-id="5d774-184">Solutions that affect your score</span></span>

<span data-ttu-id="5d774-185">本節顯示的解決方案包含的動作最有積極影響您分數的機會，以及每個解決方案中未完成的改進動作數目。</span><span class="sxs-lookup"><span data-stu-id="5d774-185">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="5d774-186">合規性分數細分</span><span class="sxs-lookup"><span data-stu-id="5d774-186">Compliance Score breakdown</span></span>

<span data-ttu-id="5d774-187">本節以兩種不同的方式提供更詳細的分數視圖：</span><span class="sxs-lookup"><span data-stu-id="5d774-187">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="5d774-188">**類別**：顯示資料保護類別中的整體分數百分比，例如「保護資訊」或「管理裝置」。</span><span class="sxs-lookup"><span data-stu-id="5d774-188">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="5d774-189">**評估**：顯示針對特定合規性和資料保護標準、法規或法律（如 GDPR 或 NIST 800-53）進行評估的進度百分比。</span><span class="sxs-lookup"><span data-stu-id="5d774-189">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="5d774-190">篩選儀表板視圖</span><span class="sxs-lookup"><span data-stu-id="5d774-190">Filtering your dashboard view</span></span>

<span data-ttu-id="5d774-191">您可以篩選儀表板視圖，只查看與特定規章和標準、解決方案、動作類型、評估群組或資料保護類別相關的專案。</span><span class="sxs-lookup"><span data-stu-id="5d774-191">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="5d774-192">以這種方式篩選您的視圖也會篩選您儀表板上的分數，以顯示您已從您的篩選準則中取得的總可能點數的點數。</span><span class="sxs-lookup"><span data-stu-id="5d774-192">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="5d774-193">若要套用篩選：</span><span class="sxs-lookup"><span data-stu-id="5d774-193">To apply filters:</span></span>

1. <span data-ttu-id="5d774-194">選取儀表板右上方的 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-194">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="5d774-195">從 [**篩選**] 浮出] 窗格**中選取篩選**準則，然後選取 [套用]。</span><span class="sxs-lookup"><span data-stu-id="5d774-195">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="5d774-196">套用篩選後，您會看到即時調整您的分數。</span><span class="sxs-lookup"><span data-stu-id="5d774-196">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="5d774-197">合規性分數百分比和分解資訊，以及改善動作和解決方案，現在只適用于篩選準則所涵蓋的資料。</span><span class="sxs-lookup"><span data-stu-id="5d774-197">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="5d774-198">如果您登出合規性分數，當您登入時，篩選的視圖仍然保留。</span><span class="sxs-lookup"><span data-stu-id="5d774-198">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="5d774-199">若要移除篩選：</span><span class="sxs-lookup"><span data-stu-id="5d774-199">To remove filters:</span></span>

- <span data-ttu-id="5d774-200">在 [套用的**篩選**] 標題高於您的合規性分數之外，選取您要移除的個別篩選旁邊的**X** 。或</span><span class="sxs-lookup"><span data-stu-id="5d774-200">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="5d774-201">選取儀表板右上方的 [**篩選**]，然後選取 [**清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-201">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="5d774-202">改進動作頁面</span><span class="sxs-lookup"><span data-stu-id="5d774-202">Improvement actions page</span></span>

<span data-ttu-id="5d774-203">[改進的動作](compliance-score-improvement-actions.md)會集中在您的相容性活動，並協助您與資料保護法規和標準相符。</span><span class="sxs-lookup"><span data-stu-id="5d774-203">[Improvement actions](compliance-score-improvement-actions.md) centralize your compliance activities and help you align with data protection regulations and standards.</span></span> <span data-ttu-id="5d774-204">每個改進動作都提供詳細的執行指導，以及將您帶入適當解決方案的連結。</span><span class="sxs-lookup"><span data-stu-id="5d774-204">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="5d774-205">動作可指派給組織中的使用者，以執行實施和測試工作。</span><span class="sxs-lookup"><span data-stu-id="5d774-205">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="5d774-206">您也可以在改進動作中儲存檔、記事及記錄狀態更新。</span><span class="sxs-lookup"><span data-stu-id="5d774-206">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="5d774-207">查看您的改善動作</span><span class="sxs-lookup"><span data-stu-id="5d774-207">View your improvement actions</span></span>

<span data-ttu-id="5d774-208">合規性分數儀表板會顯示您的**重要改進動作**，也就是最重要的問題，也就是具有最重要問題的最可用點。</span><span class="sxs-lookup"><span data-stu-id="5d774-208">The Compliance Score dashboard shows your **key improvement actions**, which are the ones with the most available points that address the most important issues.</span></span>

<span data-ttu-id="5d774-209">若要查看您的所有改進動作，請選取儀表板上的 [**改進動作**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5d774-209">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard.</span></span> <span data-ttu-id="5d774-210">或者，選取 [在您的儀表板上的主要改進動作清單下，**查看所有改進動作**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-210">Or, select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span>

<span data-ttu-id="5d774-211">如果您有很長的動作清單，篩選您的視圖可能會很有説明。</span><span class="sxs-lookup"><span data-stu-id="5d774-211">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="5d774-212">在 [動作] 清單的右上角選取 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-212">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="5d774-213">當 [**篩選**] 飛入窗格出現時，根據規定和標準、解決方案和群組選取您的準則。</span><span class="sxs-lookup"><span data-stu-id="5d774-213">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="5d774-214">您也可以選取右上角的 [**群組**]，以自訂您的視圖。</span><span class="sxs-lookup"><span data-stu-id="5d774-214">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="5d774-215">從下拉式功能表中，選取 [按群組、解決方案、類別、動作類型或狀態來查看]。</span><span class="sxs-lookup"><span data-stu-id="5d774-215">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="5d774-216">此頁面的預設視圖不會顯示已**通過**測試狀態的改善動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-216">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="5d774-217">若要查看已通過測試的動作，請檢查 [篩選] 飛入窗格中的 [已**傳遞**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="5d774-217">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="5d774-218">僅限具有**超過**您分數之測試狀態的動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-218">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="5d774-219">[改進動作] 頁面會顯示每個改進動作的下列資料點：</span><span class="sxs-lookup"><span data-stu-id="5d774-219">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="5d774-220">**分數影響**：完成動作時，整體得分會增加的點數</span><span class="sxs-lookup"><span data-stu-id="5d774-220">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="5d774-221">**規章**：動作相關的規章或標準</span><span class="sxs-lookup"><span data-stu-id="5d774-221">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="5d774-222">**群組**：您指派動作的群組</span><span class="sxs-lookup"><span data-stu-id="5d774-222">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="5d774-223">**解決方案**：您可以用來執行動作的解決方案</span><span class="sxs-lookup"><span data-stu-id="5d774-223">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="5d774-224">**評估**：針對動作所在的評估（組織控制以符合特定符合性目標）</span><span class="sxs-lookup"><span data-stu-id="5d774-224">**Assessments**: the assessment (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="5d774-225">**類別**：相關的資料保護類別（例如，保護資訊、管理裝置等等）</span><span class="sxs-lookup"><span data-stu-id="5d774-225">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="5d774-226">**測試狀態**：</span><span class="sxs-lookup"><span data-stu-id="5d774-226">**Test status**:</span></span>
    - <span data-ttu-id="5d774-227">**無**–未記錄任何狀態更新</span><span class="sxs-lookup"><span data-stu-id="5d774-227">**None** – no status update recorded</span></span>
    - <span data-ttu-id="5d774-228">**未評估**-尚未開始測試</span><span class="sxs-lookup"><span data-stu-id="5d774-228">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="5d774-229">已成功測試**傳遞**的執行</span><span class="sxs-lookup"><span data-stu-id="5d774-229">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="5d774-230">**失敗的低風險**-測試失敗、低風險</span><span class="sxs-lookup"><span data-stu-id="5d774-230">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="5d774-231">**失敗之中度風險**-測試失敗，中度風險</span><span class="sxs-lookup"><span data-stu-id="5d774-231">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="5d774-232">**失敗的高風險**-測試失敗，高風險</span><span class="sxs-lookup"><span data-stu-id="5d774-232">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="5d774-233">**不在範圍**內–動作不在評估範圍內，也不會影響您的分數</span><span class="sxs-lookup"><span data-stu-id="5d774-233">**Not in scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="5d774-234">**若要偵測-若要**進行手動測試，表示已執行動作但未測試;若為自動測試，表示動作正等候自動化結果</span><span class="sxs-lookup"><span data-stu-id="5d774-234">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="5d774-235">**無法檢測**-無法判斷自動狀態</span><span class="sxs-lookup"><span data-stu-id="5d774-235">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="5d774-236">**部分測試**–對部分點獎勵的自動化計分</span><span class="sxs-lookup"><span data-stu-id="5d774-236">**Partially tested** – automated scoring that awards partial points</span></span>
- <span data-ttu-id="5d774-237">**達到的點數**：允許的最大點數（以點為單位）</span><span class="sxs-lookup"><span data-stu-id="5d774-237">**Points achieved**: number of points earned out of the maximum possible</span></span>

#### <a name="learn-more"></a><span data-ttu-id="5d774-238">深入了解</span><span class="sxs-lookup"><span data-stu-id="5d774-238">Learn more</span></span>
<span data-ttu-id="5d774-239">[請參閱如何指派及執行有關改進動作的工作](compliance-score-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="5d774-239">[See how to assign and perform work on improvement actions](compliance-score-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="5d774-240">解決方案頁面</span><span class="sxs-lookup"><span data-stu-id="5d774-240">Solutions page</span></span>

<span data-ttu-id="5d774-241">[解決方案] 頁面會顯示以方案組織的盈餘分析和潛在點數。</span><span class="sxs-lookup"><span data-stu-id="5d774-241">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="5d774-242">從這個視圖中查看剩下的點數和改善動作，可協助您瞭解哪些解決方案需要更立即關注。</span><span class="sxs-lookup"><span data-stu-id="5d774-242">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="5d774-243">在 [規範分數] 儀表板上，選取 [**解決方案**] 索引標籤，尋找 [解決方案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5d774-243">Find the solutions page by selecting the **Solutions** tab on your Compliance Score dashboard.</span></span> <span data-ttu-id="5d774-244">您也可以選取 [**查看所有**在您的儀表板右上方] 區段中 **，影響您分數**的解決方案。</span><span class="sxs-lookup"><span data-stu-id="5d774-244">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="5d774-245">篩選您的解決方案視圖</span><span class="sxs-lookup"><span data-stu-id="5d774-245">Filtering your solutions view</span></span>

<span data-ttu-id="5d774-246">若要篩選您的解決方案視圖：</span><span class="sxs-lookup"><span data-stu-id="5d774-246">To filter your view of solutions:</span></span>

1. <span data-ttu-id="5d774-247">從評估清單的左上角選取 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-247">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="5d774-248">在 [**篩選器**] 飛入窗格上，勾選所需準則（標準及規章、解決方案、動作類型、合規性管理員群組、類別）旁的複選。</span><span class="sxs-lookup"><span data-stu-id="5d774-248">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="5d774-249">選取 [**套用**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d774-249">Select the **Apply** button.</span></span> <span data-ttu-id="5d774-250">篩選窗格會關閉，您會看到篩選的視圖。</span><span class="sxs-lookup"><span data-stu-id="5d774-250">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="5d774-251">您也可以將您的視圖修改成按群組、產品或法規來查看評估，方法是從評估清單上方的 [**群組**] 下拉式功能表中選取群組的類型。</span><span class="sxs-lookup"><span data-stu-id="5d774-251">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solution-page"></a><span data-ttu-id="5d774-252">從解決方案頁面採取動作</span><span class="sxs-lookup"><span data-stu-id="5d774-252">Taking actions from the solution page</span></span>

<span data-ttu-id="5d774-253">[解決方案] 頁面會顯示您組織中已連接至 [改進動作] 的解決方案。</span><span class="sxs-lookup"><span data-stu-id="5d774-253">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="5d774-254">該表列出每個方案對您整體分數的貢獻，在該解決方案中取得的分數提升點，以及在該解決方案中群組的其餘改進動作數目，也會增加您的分數。</span><span class="sxs-lookup"><span data-stu-id="5d774-254">The table lists each solution’s contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="5d774-255">您可以使用下列兩種方式從這個畫面採取動作：</span><span class="sxs-lookup"><span data-stu-id="5d774-255">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="5d774-256">在您預定方案的列上，選取 [**其他動作**] 欄底下的超連結號碼。</span><span class="sxs-lookup"><span data-stu-id="5d774-256">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="5d774-257">您會看到 [改進動作] 畫面的篩選視圖，顯示該解決方案的未測試改進動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-257">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="5d774-258">在您預定方案的列上，選取 [**開啟方案**] 欄下的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-258">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="5d774-259">您會在 Microsoft 365 和 Office 365 安全性與合規性中心中看到解決方案或位置，您可以採取建議的動作。</span><span class="sxs-lookup"><span data-stu-id="5d774-259">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="5d774-260">評估頁面</span><span class="sxs-lookup"><span data-stu-id="5d774-260">Assessments page</span></span>

<span data-ttu-id="5d774-261">「評估」頁面會列出您為組織設定的所有[評估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="5d774-261">The assessments page lists all the [assessments](compliance-score-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="5d774-262">您的相容性分數分母是由所有追蹤的評估所決定。</span><span class="sxs-lookup"><span data-stu-id="5d774-262">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="5d774-263">您新增的評估程度越高，您在 [改進動作] 頁面上看到的改善動作越多，而得分分母的越高。</span><span class="sxs-lookup"><span data-stu-id="5d774-263">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="5d774-264">此頁面摘要列出每項評估的重要資訊：</span><span class="sxs-lookup"><span data-stu-id="5d774-264">This page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="5d774-265">**評估**：評估的名稱</span><span class="sxs-lookup"><span data-stu-id="5d774-265">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="5d774-266">**狀態**：</span><span class="sxs-lookup"><span data-stu-id="5d774-266">**Status**:</span></span>
    - <span data-ttu-id="5d774-267">**完成**-所有控制項的狀態皆為「已傳遞」，或是至少有一個已傳遞，其餘部分則為「範圍外」</span><span class="sxs-lookup"><span data-stu-id="5d774-267">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="5d774-268">**不完整**–至少有一個控制項的狀態為 "failed"</span><span class="sxs-lookup"><span data-stu-id="5d774-268">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="5d774-269">**None** -尚未測試所有控制項</span><span class="sxs-lookup"><span data-stu-id="5d774-269">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="5d774-270">**進行中**的改進動作具有任何其他狀態，包括「進行中」、「部分信用」或「未檢查」</span><span class="sxs-lookup"><span data-stu-id="5d774-270">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="5d774-271">**評估進度**：完成工作的百分比（以成功測試的控制項數目衡量）</span><span class="sxs-lookup"><span data-stu-id="5d774-271">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="5d774-272">**您的改進動作**：已完成的動作數目，可滿足您的控制項的實現</span><span class="sxs-lookup"><span data-stu-id="5d774-272">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="5d774-273">**Microsoft 動作**：已完成的動作數目，可滿足 Microsoft 控制項的實現</span><span class="sxs-lookup"><span data-stu-id="5d774-273">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="5d774-274">**群組**：評估所屬之群組的名稱</span><span class="sxs-lookup"><span data-stu-id="5d774-274">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="5d774-275">**產品**：相關的 Microsoft 365 服務</span><span class="sxs-lookup"><span data-stu-id="5d774-275">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="5d774-276">**規章**：套用至評估的規章標準、原則或法律</span><span class="sxs-lookup"><span data-stu-id="5d774-276">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="5d774-277">篩選評估視圖</span><span class="sxs-lookup"><span data-stu-id="5d774-277">Filtering your assessments view</span></span>

<span data-ttu-id="5d774-278">篩選您的評估：</span><span class="sxs-lookup"><span data-stu-id="5d774-278">To filter you view of assessments:</span></span>

1. <span data-ttu-id="5d774-279">從評估清單的左上角選取 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5d774-279">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="5d774-280">在 [**篩選**] 浮出控制項窗格上，檢查所需的準則。</span><span class="sxs-lookup"><span data-stu-id="5d774-280">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="5d774-281">選取 [套用] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5d774-281">Select the Apply button.</span></span> <span data-ttu-id="5d774-282">篩選窗格會關閉，您會看到篩選的視圖。</span><span class="sxs-lookup"><span data-stu-id="5d774-282">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="5d774-283">您也可以將您的視圖修改成按群組、產品或法規來查看評估，方法是從評估清單上方的 [**群組**] 下拉式功能表中選取群組的類型。</span><span class="sxs-lookup"><span data-stu-id="5d774-283">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="5d774-284">預設評估</span><span class="sxs-lookup"><span data-stu-id="5d774-284">Default assessment</span></span>

<span data-ttu-id="5d774-285">根據預設，您會在 [評估] 頁面上看到[Microsoft 365 資料保護基準](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)評估。</span><span class="sxs-lookup"><span data-stu-id="5d774-285">By default, you'll see the [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) assessment on the assessments page.</span></span> <span data-ttu-id="5d774-286">合規性分數也提供數種可供使用的[範本](compliance-score-templates.md)，可供您用來建立評估。</span><span class="sxs-lookup"><span data-stu-id="5d774-286">Compliance Score also provides several ready to use [templates](compliance-score-templates.md) from which to build assessments.</span></span>

## <a name="next-step"></a><span data-ttu-id="5d774-287">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5d774-287">Next step</span></span>
<span data-ttu-id="5d774-288">[設定評估](compliance-score-assessments.md)，以自訂合規性分數。</span><span class="sxs-lookup"><span data-stu-id="5d774-288">Customize Compliance Score by [setting up assessments](compliance-score-assessments.md).</span></span>