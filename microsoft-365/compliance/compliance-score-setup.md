---
title: Microsoft 合規性分數安裝程式
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
description: 了解如何登入，設定權限，以及了解 Microsoft 合規性分數，可協助簡化和自動化風險評定儀表板。
ms.openlocfilehash: 03bcc5663e3b57728eb4ba791bbcba9593e5afc7
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831176"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="b9e0d-103">Microsoft 合規性分數 （預覽） 安裝程式</span><span class="sxs-lookup"><span data-stu-id="b9e0d-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b9e0d-104">開始之前</span><span class="sxs-lookup"><span data-stu-id="b9e0d-104">Before you begin</span></span>

<span data-ttu-id="b9e0d-105">Microsoft 365 全域系統管理員為您的組織可能會存取合規性分數第一位使用者。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="b9e0d-106">建議的全域管理員身分登入和設定使用者權限，如下所示時第一次造訪合規性分數。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="b9e0d-107">登入</span><span class="sxs-lookup"><span data-stu-id="b9e0d-107">Sign in</span></span>

1. <span data-ttu-id="b9e0d-108">移至[Microsoft 365 合規性中心](https://compliance.microsoft.com/)及以 Microsoft 365 全域系統管理員帳戶**登入**。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="b9e0d-109">左側的導覽窗格上，選取 [**合規性分數**。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="b9e0d-110">您應該會看到您的[合規性分數儀表板與您的分數](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="b9e0d-111">設定使用者權限，並將角色指派</span><span class="sxs-lookup"><span data-stu-id="b9e0d-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="b9e0d-112">合規性分數使用角色型存取控制 (RBAC) 權限模型。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="b9e0d-113">只有獲指派角色的使用者可以存取合規性分數，以及每位使用者所允許的動作會受到角色類型。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="b9e0d-114">若要設定權限的位置</span><span class="sxs-lookup"><span data-stu-id="b9e0d-114">Where to set permissions</span></span>

<span data-ttu-id="b9e0d-115">在 Microsoft 365 合規性中心或 Azure Active Directory (Azure AD) 中，您組織的全域系統管理員可以設定使用者權限。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b9e0d-116">一旦角色在這些位置的設定，使用者將能夠存取合規性分數 （以及合規性管理員）。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="b9e0d-117">收件者的現有合規性管理員角色**不**傳輸透過合規性分數。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="b9e0d-118">這表示，如果您先前指派的角色合規性管理員中，該角色會授與您存取合規性分數。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="b9e0d-119">您的全域系統管理員將需要設定權限及角色為您的 Microsoft 365 合規性中心或 Azure AD 中，讓您可以存取合規性分數。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="b9e0d-120">角色類型</span><span class="sxs-lookup"><span data-stu-id="b9e0d-120">Role types</span></span>

<span data-ttu-id="b9e0d-121">下表顯示每個 Microsoft 365 合規性中心角色如何對應至現有的合規性管理員角色及每個角色所允許的函數。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="b9e0d-122">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="b9e0d-122">User can:</span></span> | <span data-ttu-id="b9e0d-123">Microsoft 365 合規性中心角色</span><span class="sxs-lookup"><span data-stu-id="b9e0d-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="b9e0d-124">合規性管理員角色</span><span class="sxs-lookup"><span data-stu-id="b9e0d-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="b9e0d-125">**讀取但無法編輯資料**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-125">**Read but not edit data**</span></span>| <span data-ttu-id="b9e0d-126">Azure AD 全域讀者</span><span class="sxs-lookup"><span data-stu-id="b9e0d-126">Azure AD global reader</span></span>  | <span data-ttu-id="b9e0d-127">Azure AD 全域讀者</span><span class="sxs-lookup"><span data-stu-id="b9e0d-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="b9e0d-128">**讀取但無法編輯資料**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-128">**Read but not edit data**</span></span>| <span data-ttu-id="b9e0d-129">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="b9e0d-129">Security reader</span></span> | <span data-ttu-id="b9e0d-130">合規性管理員讀取者</span><span class="sxs-lookup"><span data-stu-id="b9e0d-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="b9e0d-131">**編輯資料**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-131">**Edit data**</span></span>| <span data-ttu-id="b9e0d-132">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-132">Compliance administrator</span></span> | <span data-ttu-id="b9e0d-133">合規性參與者</span><span class="sxs-lookup"><span data-stu-id="b9e0d-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="b9e0d-134">**編輯測試結果**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-134">**Edit test results**</span></span>| <span data-ttu-id="b9e0d-135">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-135">Compliance administrator</span></span> | <span data-ttu-id="b9e0d-136">合規性管理員評估者</span><span class="sxs-lookup"><span data-stu-id="b9e0d-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="b9e0d-137">**管理評估以及範本和租用戶資料**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="b9e0d-138">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-138">Compliance administrator</span></span><br><span data-ttu-id="b9e0d-139">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-139">Compliance data administrator</span></span><br><span data-ttu-id="b9e0d-140">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-140">Security administrator</span></span> | <span data-ttu-id="b9e0d-141">合規性管理員的系統管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="b9e0d-142">**指派給使用者**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-142">**Assign users**</span></span>| <span data-ttu-id="b9e0d-143">全域管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-143">Global administrator</span></span> | <span data-ttu-id="b9e0d-144">入口網站管理員</span><span class="sxs-lookup"><span data-stu-id="b9e0d-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="b9e0d-145">從合規性分數移至合規性管理員完成工作時 （例如，若要管理 「 評估 」），您的瀏覽器會開啟新的索引標籤，會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="b9e0d-146">在 [使用標頭 [top] 區段中，「 已 Microsoft 雲端服務客戶嗎？</span><span class="sxs-lookup"><span data-stu-id="b9e0d-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="b9e0d-147">您的帳戶，登入] 選取 [**登入**存取合規性管理員;您將不需要重新輸入您的認證。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="b9e0d-148">如何設定 Microsoft 365 合規性中心中的權限和角色</span><span class="sxs-lookup"><span data-stu-id="b9e0d-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="b9e0d-149">若要在 Microsoft 365 合規性中心設定權限：</span><span class="sxs-lookup"><span data-stu-id="b9e0d-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="b9e0d-150">移至[Microsoft 365 合規性中心](https://compliance.microsoft.com)，並使用您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="b9e0d-151">在左側的導覽窗格上，選取 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="b9e0d-152">從這裡開始，您可以檢視角色及指派權限。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-152">From here, you can view roles and assign permissions.</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="b9e0d-153">了解合規性分數儀表板</span><span class="sxs-lookup"><span data-stu-id="b9e0d-153">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="b9e0d-154">合規性分數儀表板旨在提供您目前的合規性狀態在快速檢視。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-154">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="b9e0d-155">![合規性分數-儀表板](media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="b9e0d-155">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="b9e0d-156">整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="b9e0d-156">Overall compliance score</span></span>

<span data-ttu-id="b9e0d-157">合規性分數，顯著精選頂端，顯示根據點可達成的完成處理索引鍵的資料保護標準與法規的改進動作的百分比。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-157">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span> 

<span data-ttu-id="b9e0d-158">當您第一次回到合規性分數時，您的初始分數根據內建的 Microsoft 365 的資料保護基準-一組控制項包含一般產業法規及標準。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-158">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="b9e0d-159">合規性分數會掃描您的系統的現有的 Microsoft 365 解決方案，因為它可讓您根據隱私權和安全性設定目前已啟用組織的合規性狀態初始評估。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-159">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="b9e0d-160">當您新增至您的組織相關的評估，您的分數變得更有意義。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-160">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="b9e0d-161">深入了解[您的分數的計算方式](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-161">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="b9e0d-162">關鍵的改進動作</span><span class="sxs-lookup"><span data-stu-id="b9e0d-162">Key improvement actions</span></span>

<span data-ttu-id="b9e0d-163">此章節將列出上方改進您可以的採取來說，使上整體合規性分數的最大的正面影響。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-163">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="b9e0d-164">它會列出未完成或失敗，具有高風險評定的動作。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-164">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="b9e0d-165">會影響您的分數的解決方案</span><span class="sxs-lookup"><span data-stu-id="b9e0d-165">Solutions that affect your score</span></span>

<span data-ttu-id="b9e0d-166">您必須在每個方案中的解決方案包含動作與最大有機會帶來正面影響您的分數，以及多少未完成的改進動作此區段顯示。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-166">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="b9e0d-167">合規性分數分解</span><span class="sxs-lookup"><span data-stu-id="b9e0d-167">Compliance Score breakdown</span></span>

<span data-ttu-id="b9e0d-168">本節提供詳細的檢視您分數中兩個不同的方式：</span><span class="sxs-lookup"><span data-stu-id="b9e0d-168">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="b9e0d-169">**類別**： 顯示內的資料保護類別，例如 「 保護資訊 」 或 「 管理裝置 」。 您整體分數的百分比</span><span class="sxs-lookup"><span data-stu-id="b9e0d-169">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="b9e0d-170">**「 評估 」**: 管理特定的合規性和資料保護標準、 法令或法律，例如 GDPR 或 NIST 800-53 評定顯示進度百分比。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-170">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="b9e0d-171">篩選您的儀表板檢視</span><span class="sxs-lookup"><span data-stu-id="b9e0d-171">Filtering your dashboard view</span></span>

<span data-ttu-id="b9e0d-172">您可以篩選您的儀表板檢視，以查看只項目關聯至特定法規與標準、 解決方案、 的動作、 群組或資料保護類別類型。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-172">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, groups, or data protection categories.</span></span> <span data-ttu-id="b9e0d-173">篩選以這種方式檢視也將篩選在儀表板，顯示已達到超出根據篩選準則的總可能點多少點數的分數。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-173">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="b9e0d-174">若要套用的篩選器：</span><span class="sxs-lookup"><span data-stu-id="b9e0d-174">To apply filters:</span></span>

1. <span data-ttu-id="b9e0d-175">選取 [儀表板右上方**篩選器**]。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-175">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="b9e0d-176">從彈出式**篩選**] 窗格中，選取您的篩選條件，然後選取 [**套用**]。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-176">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="b9e0d-177">您會看到您在調整的分數即時，與您將只能看到改進動作、 解決方案，以及分數分解資訊對應至您的篩選準則。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-177">You will see your score adjusted in real-time, and you will only see improvement actions, solutions, and score breakdown information that correspond to your filter criteria.</span></span> <span data-ttu-id="b9e0d-178">如果您登出合規性分數時您登入,，也會維持您篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-178">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="b9e0d-179">若要移除的篩選器：</span><span class="sxs-lookup"><span data-stu-id="b9e0d-179">To remove filters:</span></span>

- <span data-ttu-id="b9e0d-180">在上方合規性分數**套用篩選器**] 標題下，選取您想要移除; 個別篩選器旁邊的**X**或</span><span class="sxs-lookup"><span data-stu-id="b9e0d-180">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="b9e0d-181">選取**篩選**右上一邊的儀表板，然後選取 [**清除篩選**。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-181">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="b9e0d-182">下一步</span><span class="sxs-lookup"><span data-stu-id="b9e0d-182">Next step</span></span>

<span data-ttu-id="b9e0d-183">請造訪以了解如何採取動作，以改善您的分數的工作流程[使用合規性分數](working-with-compliance-score.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e0d-183">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>