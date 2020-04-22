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
description: 瞭解如何設定及開始使用 Microsoft 合規性分數，以協助簡化及自動化風險評估。
ms.openlocfilehash: 4ccd89647540aeda8ba6253f6e5eefab1dc81791
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632388"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="edaa1-103">Microsoft 規範分數（預覽）設定</span><span class="sxs-lookup"><span data-stu-id="edaa1-103">Microsoft Compliance Score (preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="edaa1-104">開始之前</span><span class="sxs-lookup"><span data-stu-id="edaa1-104">Before you begin</span></span>

<span data-ttu-id="edaa1-105">您組織的 Microsoft 365 全域管理員可能會是第一個存取合規性分數的使用者。</span><span class="sxs-lookup"><span data-stu-id="edaa1-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="edaa1-106">我們建議全域管理員登入，並設定第一次的訪問合規性分數時所述的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="edaa1-106">We recommend the global admin sign-in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="edaa1-107">登入</span><span class="sxs-lookup"><span data-stu-id="edaa1-107">Sign in</span></span>

1. <span data-ttu-id="edaa1-108">請移至[microsoft 365 規範中心](https://compliance.microsoft.com/)，並使用您的 Microsoft 365 全域管理員帳戶登**入**。</span><span class="sxs-lookup"><span data-stu-id="edaa1-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="edaa1-109">在左導覽窗格上選取 [**合規性分數**]。</span><span class="sxs-lookup"><span data-stu-id="edaa1-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="edaa1-110">您應該會看到您[的評分分數儀表板與您的分數](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="edaa1-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="edaa1-111">存取合規性分數的直接連結為： [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore)。</span><span class="sxs-lookup"><span data-stu-id="edaa1-111">The direct link to access Compliance Score is: [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="edaa1-112">設定使用者權限並指派角色</span><span class="sxs-lookup"><span data-stu-id="edaa1-112">Set user permissions and assign roles</span></span>

<span data-ttu-id="edaa1-113">合規性分數使用以角色為基礎的存取控制（RBAC）許可權模型。</span><span class="sxs-lookup"><span data-stu-id="edaa1-113">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="edaa1-114">只有獲指派角色的使用者才可存取合規性分數，而且每個使用者所允許的動作都會受到角色類型的限制。</span><span class="sxs-lookup"><span data-stu-id="edaa1-114">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="edaa1-115">設定許可權的位置</span><span class="sxs-lookup"><span data-stu-id="edaa1-115">Where to set permissions</span></span>

<span data-ttu-id="edaa1-116">您組織的全域管理員可以設定 Microsoft 365 規範中心或 Azure Active Directory （Azure AD）中的使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="edaa1-116">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="edaa1-117">在這兩個位置中設定角色後，使用者即可存取合規性分數及合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="edaa1-117">Once roles are set in either of these locations, users can access Compliance Score as well as  Compliance Manager.</span></span>

<span data-ttu-id="edaa1-118">請注意，現有的相容性管理員角色**不會**轉移到合規性分數。</span><span class="sxs-lookup"><span data-stu-id="edaa1-118">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span> <span data-ttu-id="edaa1-119">如果您在合規性管理員中擁有角色，且其符合性分數是新的，則您的合規性管理員角色不會授與您對合規性分數的存取。</span><span class="sxs-lookup"><span data-stu-id="edaa1-119">If you have a role in Compliance Manager and are new to Compliance Score, your Compliance Manager role won't grant you access to Compliance Score.</span></span> <span data-ttu-id="edaa1-120">您的全域系統管理員必須在 Microsoft 365 規範中心或 Azure AD 中為您設定許可權和角色，以便您可以存取合規性分數。</span><span class="sxs-lookup"><span data-stu-id="edaa1-120">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="edaa1-121">角色類型</span><span class="sxs-lookup"><span data-stu-id="edaa1-121">Role types</span></span>

<span data-ttu-id="edaa1-122">下表顯示每個 Microsoft 365 規範中心角色如何對應至現有的合規性管理員角色，以及每個角色所允許的功能。</span><span class="sxs-lookup"><span data-stu-id="edaa1-122">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="edaa1-123">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="edaa1-123">User can:</span></span> | <span data-ttu-id="edaa1-124">Microsoft 365 規範中心角色</span><span class="sxs-lookup"><span data-stu-id="edaa1-124">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="edaa1-125">合規性管理員角色</span><span class="sxs-lookup"><span data-stu-id="edaa1-125">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="edaa1-126">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="edaa1-126">**Read but not edit data**</span></span>| <span data-ttu-id="edaa1-127">Azure AD 全域讀取器</span><span class="sxs-lookup"><span data-stu-id="edaa1-127">Azure AD global reader</span></span>  | <span data-ttu-id="edaa1-128">Azure AD 全域讀取器</span><span class="sxs-lookup"><span data-stu-id="edaa1-128">Azure AD global reader</span></span> | 
| <span data-ttu-id="edaa1-129">**讀取但不編輯資料**</span><span class="sxs-lookup"><span data-stu-id="edaa1-129">**Read but not edit data**</span></span>| <span data-ttu-id="edaa1-130">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="edaa1-130">Security reader</span></span> | <span data-ttu-id="edaa1-131">合規性管理員讀者</span><span class="sxs-lookup"><span data-stu-id="edaa1-131">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="edaa1-132">**編輯資料**</span><span class="sxs-lookup"><span data-stu-id="edaa1-132">**Edit data**</span></span>| <span data-ttu-id="edaa1-133">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-133">Compliance administrator</span></span> | <span data-ttu-id="edaa1-134">合規性管理員參與者</span><span class="sxs-lookup"><span data-stu-id="edaa1-134">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="edaa1-135">**編輯測試結果**</span><span class="sxs-lookup"><span data-stu-id="edaa1-135">**Edit test results**</span></span>| <span data-ttu-id="edaa1-136">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-136">Compliance administrator</span></span> | <span data-ttu-id="edaa1-137">合規性管理員 assessor</span><span class="sxs-lookup"><span data-stu-id="edaa1-137">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="edaa1-138">**管理評估、範本及租使用者資料**</span><span class="sxs-lookup"><span data-stu-id="edaa1-138">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="edaa1-139">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-139">Compliance administrator</span></span><br><span data-ttu-id="edaa1-140">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-140">Compliance data administrator</span></span><br><span data-ttu-id="edaa1-141">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-141">Security administrator</span></span> | <span data-ttu-id="edaa1-142">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-142">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="edaa1-143">**指派使用者**</span><span class="sxs-lookup"><span data-stu-id="edaa1-143">**Assign users**</span></span>| <span data-ttu-id="edaa1-144">全域管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-144">Global administrator</span></span> | <span data-ttu-id="edaa1-145">入口網站管理員</span><span class="sxs-lookup"><span data-stu-id="edaa1-145">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="edaa1-146">當您從相容性分數移至合規性管理員以完成工作時（例如，若要管理評估），您的瀏覽器會開啟新的索引標籤，並顯示對話方塊。</span><span class="sxs-lookup"><span data-stu-id="edaa1-146">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="edaa1-147">在標頭為「已是 Microsoft cloud services 客戶」的上方區段中？</span><span class="sxs-lookup"><span data-stu-id="edaa1-147">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="edaa1-148">登入您的帳戶「選取登**入**以存取合規性管理員;您不需要重新輸入您的認證。</span><span class="sxs-lookup"><span data-stu-id="edaa1-148">Sign in to your account," select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="edaa1-149">如何在 Microsoft 365 規範中心設定許可權和角色</span><span class="sxs-lookup"><span data-stu-id="edaa1-149">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="edaa1-150">若要設定 Microsoft 365 規範中心的許可權：</span><span class="sxs-lookup"><span data-stu-id="edaa1-150">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="edaa1-151">請移至[Microsoft 365 規範中心](https://compliance.microsoft.com)，並以您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="edaa1-151">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="edaa1-152">在左功能窗格上選取 [**許可權**]。</span><span class="sxs-lookup"><span data-stu-id="edaa1-152">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="edaa1-153">您可以從這裡查看角色及指派許可權。</span><span class="sxs-lookup"><span data-stu-id="edaa1-153">From here, you can view roles and assign permissions.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="edaa1-154">設定自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="edaa1-154">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="edaa1-155">根據預設，所有新租使用者皆已開啟「[安全分數](../security/mtp/microsoft-secure-score.md)自動更新」。</span><span class="sxs-lookup"><span data-stu-id="edaa1-155">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="edaa1-156">所有由安全評分監控的動作，會自動更新合規性分數中相同動作的狀態。</span><span class="sxs-lookup"><span data-stu-id="edaa1-156">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="edaa1-157">您的全域系統管理員可以管理此設定，以關閉所有動作的自動更新，或個別設定動作的更新。</span><span class="sxs-lookup"><span data-stu-id="edaa1-157">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="edaa1-158">在公開預覽期間，您需要移至 Microsoft 服務信任入口網站（其中的合規性管理員所在）以管理安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="edaa1-158">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="edaa1-159">若要管理自動安全分數更新，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="edaa1-159">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="edaa1-160">使用您的全域系統管理員帳戶登入[服務信任入口網站](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="edaa1-160">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="edaa1-161">在服務信任入口網站頂端功能表列上，按一下 [**其他**] 下的 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="edaa1-161">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="edaa1-162">在 [**安全分數**] 索引標籤中，選取對應的按鈕來**開啟所有動作**、**關閉所有動作**，或**設定每個動作。**</span><span class="sxs-lookup"><span data-stu-id="edaa1-162">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="edaa1-163">如果您選擇 [**依動作設定]，請**採取下列額外步驟，為個別動作開啟安全分數更新：</span><span class="sxs-lookup"><span data-stu-id="edaa1-163">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="edaa1-164">從上方功能表中選取 [**合規性管理員**] （不要選取 [合規性管理員（經典）]，這是一種舊版產品）。</span><span class="sxs-lookup"><span data-stu-id="edaa1-164">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic)," which is a legacy product).</span></span>

5. <span data-ttu-id="edaa1-165">在螢幕的右上角選取 [**租使用者管理**]。</span><span class="sxs-lookup"><span data-stu-id="edaa1-165">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="edaa1-166">在 [**客戶動作**] 窗格上，在 [**受影響的動作**] 欄下，以省略號（**...**）尋找您的預定動作。</span><span class="sxs-lookup"><span data-stu-id="edaa1-166">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="edaa1-167">按一下省略號，然後選取 [**編輯]。**</span><span class="sxs-lookup"><span data-stu-id="edaa1-167">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="edaa1-168">將**安全分數連續更新**切換開關切換為 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="edaa1-168">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="edaa1-169">選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="edaa1-169">Select **Save.**</span></span> <span data-ttu-id="edaa1-170">安全分數連續監控現在已開啟該動作。</span><span class="sxs-lookup"><span data-stu-id="edaa1-170">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="edaa1-171">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="edaa1-171">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="edaa1-172">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="edaa1-172">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="edaa1-173">深入瞭解[管理安全分數更新](compliance-manager-release-notes.md#secure-score)。</span><span class="sxs-lookup"><span data-stu-id="edaa1-173">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="edaa1-174">瞭解規範分數儀表板</span><span class="sxs-lookup"><span data-stu-id="edaa1-174">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="edaa1-175">合規性分數儀表板的設計目的是讓您快速瞭解目前的相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="edaa1-175">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="edaa1-176">![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="edaa1-176">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="edaa1-177">整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="edaa1-177">Overall compliance score</span></span>

<span data-ttu-id="edaa1-178">您的相容性分數主要是在頂端。</span><span class="sxs-lookup"><span data-stu-id="edaa1-178">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="edaa1-179">它會顯示以點為單位的百分比，可完成解決重要資料保護標準及法規的改進動作。</span><span class="sxs-lookup"><span data-stu-id="edaa1-179">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="edaa1-180">當您第一次達成法規遵從性分數時，您的初始分數是以內建的 Microsoft 365 資料保護基準（一組包含常見工業法規和標準的控制項）為基礎。</span><span class="sxs-lookup"><span data-stu-id="edaa1-180">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="edaa1-181">由於合規性分數會掃描現有 Microsoft 365 解決方案的系統，因此它會根據組織目前啟用的隱私權和安全性設定，針對您的相容性狀況，提供初步評估。</span><span class="sxs-lookup"><span data-stu-id="edaa1-181">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="edaa1-182">當您新增與貴組織相關的評估時，您的分數會變得更有意義。</span><span class="sxs-lookup"><span data-stu-id="edaa1-182">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="edaa1-183">深入瞭解[如何計算您的分數](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="edaa1-183">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="edaa1-184">重要改進動作</span><span class="sxs-lookup"><span data-stu-id="edaa1-184">Key improvement actions</span></span>

<span data-ttu-id="edaa1-185">本節列出您現在可以採取的最大改進動作，以對您的整體合規性分數產生最大的積極影響。</span><span class="sxs-lookup"><span data-stu-id="edaa1-185">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="edaa1-186">影響分數的解決方案</span><span class="sxs-lookup"><span data-stu-id="edaa1-186">Solutions that affect your score</span></span>

<span data-ttu-id="edaa1-187">本節顯示的解決方案包含的動作最有積極影響您分數的機會，以及每個解決方案中未完成的改進動作數目。</span><span class="sxs-lookup"><span data-stu-id="edaa1-187">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="edaa1-188">合規性分數細分</span><span class="sxs-lookup"><span data-stu-id="edaa1-188">Compliance Score breakdown</span></span>

<span data-ttu-id="edaa1-189">本節以兩種不同的方式提供更詳細的分數視圖：</span><span class="sxs-lookup"><span data-stu-id="edaa1-189">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="edaa1-190">**類別**：顯示資料保護類別中的整體分數百分比，例如「保護資訊」或「管理裝置」。</span><span class="sxs-lookup"><span data-stu-id="edaa1-190">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="edaa1-191">**評估**：顯示針對特定合規性和資料保護標準、法規或法律（如 GDPR 或 NIST 800-53）進行評估的進度百分比。</span><span class="sxs-lookup"><span data-stu-id="edaa1-191">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="edaa1-192">篩選儀表板視圖</span><span class="sxs-lookup"><span data-stu-id="edaa1-192">Filtering your dashboard view</span></span>

<span data-ttu-id="edaa1-193">您可以篩選儀表板視圖，只查看與特定規章和標準、解決方案、動作類型、[您設定的評估群組](working-with-compliance-manager.md#groups)或資料保護類別相關的專案。</span><span class="sxs-lookup"><span data-stu-id="edaa1-193">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="edaa1-194">以這種方式篩選您的視圖也會篩選您儀表板上的分數，以顯示您已從您的篩選準則中取得的總可能點數的點數。</span><span class="sxs-lookup"><span data-stu-id="edaa1-194">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="edaa1-195">若要套用篩選：</span><span class="sxs-lookup"><span data-stu-id="edaa1-195">To apply filters:</span></span>

1. <span data-ttu-id="edaa1-196">選取儀表板右上方的 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="edaa1-196">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="edaa1-197">從 [**篩選**] 浮出] 窗格**中選取篩選**準則，然後選取 [套用]。</span><span class="sxs-lookup"><span data-stu-id="edaa1-197">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="edaa1-198">套用篩選後，您會看到即時調整您的分數。</span><span class="sxs-lookup"><span data-stu-id="edaa1-198">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="edaa1-199">合規性分數百分比和分解資訊，以及改善動作和解決方案，現在只適用于篩選準則所涵蓋的資料。</span><span class="sxs-lookup"><span data-stu-id="edaa1-199">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="edaa1-200">如果您登出合規性分數，當您登入時，篩選的視圖仍然保留。</span><span class="sxs-lookup"><span data-stu-id="edaa1-200">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="edaa1-201">若要移除篩選：</span><span class="sxs-lookup"><span data-stu-id="edaa1-201">To remove filters:</span></span>

- <span data-ttu-id="edaa1-202">在 [套用的**篩選**] 標題高於您的合規性分數之外，選取您要移除的個別篩選旁邊的**X** 。或</span><span class="sxs-lookup"><span data-stu-id="edaa1-202">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="edaa1-203">選取儀表板右上方的 [**篩選**]，然後選取 [**清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="edaa1-203">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="edaa1-204">下一步</span><span class="sxs-lookup"><span data-stu-id="edaa1-204">Next step</span></span>

<span data-ttu-id="edaa1-205">造訪使用[合規性分數](working-with-compliance-score.md)，以瞭解如何採取行動以提升評分的工作流程。</span><span class="sxs-lookup"><span data-stu-id="edaa1-205">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>