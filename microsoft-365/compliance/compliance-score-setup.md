---
title: Microsoft 規範分數設定
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
description: 瞭解如何登入、設定許可權，以及瞭解 Microsoft 合規性分數的儀表板，以協助簡化及自動化風險評估。
ms.openlocfilehash: 8233fb3174d822e4f71115cab2a1a174c1749810
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635121"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="20dbf-103">Microsoft 規範分數（預覽）設定</span><span class="sxs-lookup"><span data-stu-id="20dbf-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="20dbf-104">開始之前</span><span class="sxs-lookup"><span data-stu-id="20dbf-104">Before you begin</span></span>

<span data-ttu-id="20dbf-105">您組織的 Microsoft 365 全域管理員可能會是第一個存取合規性分數的使用者。</span><span class="sxs-lookup"><span data-stu-id="20dbf-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="20dbf-106">建議全域管理員登入，並設定第一次的訪問合規性分數時所述的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="20dbf-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="20dbf-107">登入</span><span class="sxs-lookup"><span data-stu-id="20dbf-107">Sign in</span></span>

1. <span data-ttu-id="20dbf-108">請移至[microsoft 365 規範中心](https://compliance.microsoft.com/)，並使用您的 Microsoft 365 全域管理員帳戶登**入**。</span><span class="sxs-lookup"><span data-stu-id="20dbf-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="20dbf-109">在左導覽窗格上選取 [**合規性分數**]。</span><span class="sxs-lookup"><span data-stu-id="20dbf-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="20dbf-110">您應該會看到您[的評分分數儀表板與您的分數](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="20dbf-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="20dbf-111">設定使用者權限並指派角色</span><span class="sxs-lookup"><span data-stu-id="20dbf-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="20dbf-112">合規性分數使用以角色為基礎的存取控制（RBAC）許可權模型。</span><span class="sxs-lookup"><span data-stu-id="20dbf-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="20dbf-113">只有獲指派角色的使用者才可存取合規性分數，而且每個使用者所允許的動作都會受到角色類型的限制。</span><span class="sxs-lookup"><span data-stu-id="20dbf-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="20dbf-114">設定許可權的位置</span><span class="sxs-lookup"><span data-stu-id="20dbf-114">Where to set permissions</span></span>

<span data-ttu-id="20dbf-115">您組織的全域管理員可以設定 Microsoft 365 規範中心或 Azure Active Directory （Azure AD）中的使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="20dbf-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="20dbf-116">在這兩個位置中設定角色後，使用者就能夠存取合規性分數（以及合規性管理員）。</span><span class="sxs-lookup"><span data-stu-id="20dbf-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="20dbf-117">請注意，現有的相容性管理員角色**不會**轉移到合規性分數。</span><span class="sxs-lookup"><span data-stu-id="20dbf-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="20dbf-118">這表示如果您先前已在合規性管理員中指派角色，該角色將不會授與您對合規性分數的存取權。</span><span class="sxs-lookup"><span data-stu-id="20dbf-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="20dbf-119">您的全域系統管理員必須在 Microsoft 365 規範中心或 Azure AD 中為您設定許可權和角色，以便您可以存取合規性分數。</span><span class="sxs-lookup"><span data-stu-id="20dbf-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="20dbf-120">角色類型</span><span class="sxs-lookup"><span data-stu-id="20dbf-120">Role types</span></span>

<span data-ttu-id="20dbf-121">下表顯示每個 Microsoft 365 規範中心角色如何對應至現有的合規性管理員角色，以及每個角色所允許的功能。</span><span class="sxs-lookup"><span data-stu-id="20dbf-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="20dbf-122">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="20dbf-122">User can:</span></span> | <span data-ttu-id="20dbf-123">Microsoft 365 規範中心角色</span><span class="sxs-lookup"><span data-stu-id="20dbf-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="20dbf-124">合規性管理員角色</span><span class="sxs-lookup"><span data-stu-id="20dbf-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="20dbf-125">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="20dbf-125">**Read but not edit data**</span></span>| <span data-ttu-id="20dbf-126">Azure AD 全域讀取器</span><span class="sxs-lookup"><span data-stu-id="20dbf-126">Azure AD global reader</span></span>  | <span data-ttu-id="20dbf-127">Azure AD 全域讀取器</span><span class="sxs-lookup"><span data-stu-id="20dbf-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="20dbf-128">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="20dbf-128">**Read but not edit data**</span></span>| <span data-ttu-id="20dbf-129">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="20dbf-129">Security reader</span></span> | <span data-ttu-id="20dbf-130">合規性管理員讀者</span><span class="sxs-lookup"><span data-stu-id="20dbf-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="20dbf-131">**編輯資料**</span><span class="sxs-lookup"><span data-stu-id="20dbf-131">**Edit data**</span></span>| <span data-ttu-id="20dbf-132">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-132">Compliance administrator</span></span> | <span data-ttu-id="20dbf-133">合規性管理員參與者</span><span class="sxs-lookup"><span data-stu-id="20dbf-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="20dbf-134">**編輯測試結果**</span><span class="sxs-lookup"><span data-stu-id="20dbf-134">**Edit test results**</span></span>| <span data-ttu-id="20dbf-135">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-135">Compliance administrator</span></span> | <span data-ttu-id="20dbf-136">合規性管理員 assessor</span><span class="sxs-lookup"><span data-stu-id="20dbf-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="20dbf-137">**管理評估、範本及租使用者資料**</span><span class="sxs-lookup"><span data-stu-id="20dbf-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="20dbf-138">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-138">Compliance administrator</span></span><br><span data-ttu-id="20dbf-139">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-139">Compliance data administrator</span></span><br><span data-ttu-id="20dbf-140">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-140">Security administrator</span></span> | <span data-ttu-id="20dbf-141">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="20dbf-142">**指派使用者**</span><span class="sxs-lookup"><span data-stu-id="20dbf-142">**Assign users**</span></span>| <span data-ttu-id="20dbf-143">全域管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-143">Global administrator</span></span> | <span data-ttu-id="20dbf-144">入口網站管理員</span><span class="sxs-lookup"><span data-stu-id="20dbf-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="20dbf-145">當您從相容性分數移至合規性管理員以完成工作時（例如，若要管理評估），您的瀏覽器會開啟新的索引標籤，並顯示對話方塊。</span><span class="sxs-lookup"><span data-stu-id="20dbf-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="20dbf-146">在標頭為「已是 Microsoft cloud services 客戶」的上方區段中？</span><span class="sxs-lookup"><span data-stu-id="20dbf-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="20dbf-147">登入您的帳戶「選取登**入**以存取合規性管理員;您不需要重新輸入您的認證。</span><span class="sxs-lookup"><span data-stu-id="20dbf-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="20dbf-148">如何在 Microsoft 365 規範中心設定許可權和角色</span><span class="sxs-lookup"><span data-stu-id="20dbf-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="20dbf-149">若要設定 Microsoft 365 規範中心的許可權：</span><span class="sxs-lookup"><span data-stu-id="20dbf-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="20dbf-150">請移至[Microsoft 365 規範中心](https://compliance.microsoft.com)，並以您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="20dbf-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="20dbf-151">在左功能窗格上選取 [**許可權**]。</span><span class="sxs-lookup"><span data-stu-id="20dbf-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="20dbf-152">您可以從這裡查看角色及指派許可權。</span><span class="sxs-lookup"><span data-stu-id="20dbf-152">From here, you can view roles and assign permissions.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="20dbf-153">設定自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="20dbf-153">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="20dbf-154">根據預設，所有新租使用者皆已開啟「[安全分數](../security/mtp/microsoft-secure-score.md)自動更新」。</span><span class="sxs-lookup"><span data-stu-id="20dbf-154">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="20dbf-155">這表示所有以安全分數監控的動作，會自動更新合規性分數中相同動作的狀態。</span><span class="sxs-lookup"><span data-stu-id="20dbf-155">This means that all actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="20dbf-156">您的全域系統管理員可以管理此設定，以關閉所有動作的自動更新，或個別設定動作的更新。</span><span class="sxs-lookup"><span data-stu-id="20dbf-156">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="20dbf-157">在公開預覽期間，您需要移至 Microsoft 服務信任入口網站（其中的合規性管理員所在）以管理安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="20dbf-157">During public preview, you will need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="20dbf-158">若要管理自動安全分數更新，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="20dbf-158">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="20dbf-159">使用您的全域系統管理員帳戶登入[服務信任入口網站](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="20dbf-159">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="20dbf-160">在服務信任入口網站頂端功能表列上，按一下 [**其他**] 下的 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="20dbf-160">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="20dbf-161">在 [**安全分數**] 索引標籤中，選取對應的按鈕來**開啟所有動作**、**關閉所有動作**，或**設定每個動作。**</span><span class="sxs-lookup"><span data-stu-id="20dbf-161">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="20dbf-162">如果您選擇 [**依動作設定]，請**採取下列額外步驟，為個別動作開啟安全分數更新：</span><span class="sxs-lookup"><span data-stu-id="20dbf-162">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="20dbf-163">從上方功能表中選取 [**合規性管理員**] （附注：不要選取「合規性管理員（古典）」）。</span><span class="sxs-lookup"><span data-stu-id="20dbf-163">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="20dbf-164">在螢幕的右上角選取 [**租使用者管理**]。</span><span class="sxs-lookup"><span data-stu-id="20dbf-164">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="20dbf-165">在 [**客戶動作**] 窗格上，在 [**受影響的動作**] 欄下，以省略號（**...**）尋找您的預定動作。</span><span class="sxs-lookup"><span data-stu-id="20dbf-165">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="20dbf-166">按一下省略號，然後選取 [**編輯]。**</span><span class="sxs-lookup"><span data-stu-id="20dbf-166">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="20dbf-167">將**安全分數連續更新**切換開關切換為 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="20dbf-167">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="20dbf-168">選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="20dbf-168">Select **Save.**</span></span> <span data-ttu-id="20dbf-169">安全分數連續監控現在已開啟該動作。</span><span class="sxs-lookup"><span data-stu-id="20dbf-169">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="20dbf-170">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="20dbf-170">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="20dbf-171">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="20dbf-171">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="20dbf-172">深入瞭解[管理安全分數更新](compliance-manager-release-notes.md#secure-score)。</span><span class="sxs-lookup"><span data-stu-id="20dbf-172">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="20dbf-173">瞭解規範分數儀表板</span><span class="sxs-lookup"><span data-stu-id="20dbf-173">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="20dbf-174">合規性分數儀表板的設計目的是讓您快速瞭解目前的相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="20dbf-174">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="20dbf-175">![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="20dbf-175">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="20dbf-176">整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="20dbf-176">Overall compliance score</span></span>

<span data-ttu-id="20dbf-177">您的相容性分數，主要重點是以點數為基礎，以完成改進動作以解決重要的資料保護標準和法規，顯示以點數為基礎的百分比。</span><span class="sxs-lookup"><span data-stu-id="20dbf-177">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span>

<span data-ttu-id="20dbf-178">當您第一次達成法規遵從性分數時，您的初始分數是以內建的 Microsoft 365 資料保護基準（一組包含常見工業法規和標準的控制項）為基礎。</span><span class="sxs-lookup"><span data-stu-id="20dbf-178">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="20dbf-179">由於合規性分數會掃描現有 Microsoft 365 解決方案的系統，因此它會根據組織目前啟用的隱私權和安全性設定，針對您的相容性狀況，提供初步評估。</span><span class="sxs-lookup"><span data-stu-id="20dbf-179">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="20dbf-180">當您新增與貴組織相關的評估時，您的分數會變得更有意義。</span><span class="sxs-lookup"><span data-stu-id="20dbf-180">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="20dbf-181">深入瞭解[如何計算您的分數](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="20dbf-181">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="20dbf-182">重要改進動作</span><span class="sxs-lookup"><span data-stu-id="20dbf-182">Key improvement actions</span></span>

<span data-ttu-id="20dbf-183">本節列出您現在可以採取的最大改進動作，以對您的整體合規性分數產生最大的積極影響。</span><span class="sxs-lookup"><span data-stu-id="20dbf-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="20dbf-184">它會列出具有高風險之評估未完成或失敗的動作。</span><span class="sxs-lookup"><span data-stu-id="20dbf-184">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="20dbf-185">影響分數的解決方案</span><span class="sxs-lookup"><span data-stu-id="20dbf-185">Solutions that affect your score</span></span>

<span data-ttu-id="20dbf-186">本節顯示哪些方案包含的動作最有可能會對您的分數產生積極影響，以及您在每個解決方案中有多少未完成的改進動作。</span><span class="sxs-lookup"><span data-stu-id="20dbf-186">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="20dbf-187">合規性分數細分</span><span class="sxs-lookup"><span data-stu-id="20dbf-187">Compliance Score breakdown</span></span>

<span data-ttu-id="20dbf-188">本節以兩種不同的方式提供更詳細的分數視圖：</span><span class="sxs-lookup"><span data-stu-id="20dbf-188">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="20dbf-189">**類別**：顯示資料保護類別中的整體分數百分比，例如「保護資訊」或「管理裝置」。</span><span class="sxs-lookup"><span data-stu-id="20dbf-189">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="20dbf-190">**評估**：顯示針對特定合規性和資料保護標準、法規或法律（如 GDPR 或 NIST 800-53）進行評估的進度百分比。</span><span class="sxs-lookup"><span data-stu-id="20dbf-190">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="20dbf-191">篩選儀表板視圖</span><span class="sxs-lookup"><span data-stu-id="20dbf-191">Filtering your dashboard view</span></span>

<span data-ttu-id="20dbf-192">您可以篩選儀表板視圖，只查看與特定規章和標準、解決方案、動作類型、[您設定的評估群組](working-with-compliance-manager.md#groups)或資料保護類別相關的專案。</span><span class="sxs-lookup"><span data-stu-id="20dbf-192">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="20dbf-193">以這種方式篩選您的視圖也會篩選您儀表板上的分數，以顯示您已從您的篩選準則中取得的總可能點數的點數。</span><span class="sxs-lookup"><span data-stu-id="20dbf-193">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="20dbf-194">若要套用篩選：</span><span class="sxs-lookup"><span data-stu-id="20dbf-194">To apply filters:</span></span>

1. <span data-ttu-id="20dbf-195">選取儀表板右上方的 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="20dbf-195">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="20dbf-196">從 [飛出**篩選**] 窗格中選取您的篩選準則，然後選取 [ **Apply**]。</span><span class="sxs-lookup"><span data-stu-id="20dbf-196">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="20dbf-197">套用篩選後，您會看到即時調整您的分數。</span><span class="sxs-lookup"><span data-stu-id="20dbf-197">Once a filter is applied, you will see your score adjusted in real-time.</span></span> <span data-ttu-id="20dbf-198">合規性分數百分比和分解資訊，以及改善動作和解決方案，現在只適用于篩選準則所涵蓋的資料。</span><span class="sxs-lookup"><span data-stu-id="20dbf-198">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="20dbf-199">如果您登出合規性分數，當您登入時，篩選的視圖仍然保留。</span><span class="sxs-lookup"><span data-stu-id="20dbf-199">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="20dbf-200">若要移除篩選：</span><span class="sxs-lookup"><span data-stu-id="20dbf-200">To remove filters:</span></span>

- <span data-ttu-id="20dbf-201">在 [套用的**篩選**] 標題高於您的合規性分數之外，選取您要移除的個別篩選旁邊的**X** 。或</span><span class="sxs-lookup"><span data-stu-id="20dbf-201">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="20dbf-202">選取儀表板右上方的 [**篩選**]，然後選取 [**清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="20dbf-202">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="20dbf-203">下一步</span><span class="sxs-lookup"><span data-stu-id="20dbf-203">Next step</span></span>

<span data-ttu-id="20dbf-204">造訪使用[合規性分數](working-with-compliance-score.md)，以瞭解如何採取行動以提升評分的工作流程。</span><span class="sxs-lookup"><span data-stu-id="20dbf-204">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>
