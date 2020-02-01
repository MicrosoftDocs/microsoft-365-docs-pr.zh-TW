---
title: Microsoft 合規性分數安裝程式
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
description: 了解如何登入，設定權限，以及了解 Microsoft 合規性分數，可協助簡化和自動化風險評定儀表板。
ms.openlocfilehash: a97fa1c0598fcab1660d71581fed2be8dafe8911
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595750"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="83692-103">Microsoft 合規性分數 （預覽） 安裝程式</span><span class="sxs-lookup"><span data-stu-id="83692-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="83692-104">開始之前</span><span class="sxs-lookup"><span data-stu-id="83692-104">Before you begin</span></span>

<span data-ttu-id="83692-105">Microsoft 365 全域系統管理員為您的組織可能會存取合規性分數第一位使用者。</span><span class="sxs-lookup"><span data-stu-id="83692-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="83692-106">建議的全域管理員身分登入和設定使用者權限，如下所示時第一次造訪合規性分數。</span><span class="sxs-lookup"><span data-stu-id="83692-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="83692-107">登入</span><span class="sxs-lookup"><span data-stu-id="83692-107">Sign in</span></span>

1. <span data-ttu-id="83692-108">移至[Microsoft 365 合規性中心](https://compliance.microsoft.com/)及以 Microsoft 365 全域系統管理員帳戶**登入**。</span><span class="sxs-lookup"><span data-stu-id="83692-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="83692-109">左側的導覽窗格上，選取 [**合規性分數**。</span><span class="sxs-lookup"><span data-stu-id="83692-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="83692-110">您應該會看到您的[合規性分數儀表板與您的分數](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="83692-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="83692-111">設定使用者權限，並將角色指派</span><span class="sxs-lookup"><span data-stu-id="83692-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="83692-112">合規性分數使用角色型存取控制 (RBAC) 權限模型。</span><span class="sxs-lookup"><span data-stu-id="83692-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="83692-113">只有獲指派角色的使用者可以存取合規性分數，以及每位使用者所允許的動作會受到角色類型。</span><span class="sxs-lookup"><span data-stu-id="83692-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="83692-114">若要設定權限的位置</span><span class="sxs-lookup"><span data-stu-id="83692-114">Where to set permissions</span></span>

<span data-ttu-id="83692-115">在 Microsoft 365 合規性中心或 Azure Active Directory (Azure AD) 中，您組織的全域系統管理員可以設定使用者權限。</span><span class="sxs-lookup"><span data-stu-id="83692-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="83692-116">一旦角色在這些位置的設定，使用者將能夠存取合規性分數 （以及合規性管理員）。</span><span class="sxs-lookup"><span data-stu-id="83692-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="83692-117">收件者的現有合規性管理員角色**不**傳輸透過合規性分數。</span><span class="sxs-lookup"><span data-stu-id="83692-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="83692-118">這表示，如果您先前指派的角色合規性管理員中，該角色會授與您存取合規性分數。</span><span class="sxs-lookup"><span data-stu-id="83692-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="83692-119">您的全域系統管理員將需要設定權限及角色為您的 Microsoft 365 合規性中心或 Azure AD 中，讓您可以存取合規性分數。</span><span class="sxs-lookup"><span data-stu-id="83692-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="83692-120">角色類型</span><span class="sxs-lookup"><span data-stu-id="83692-120">Role types</span></span>

<span data-ttu-id="83692-121">下表顯示每個 Microsoft 365 合規性中心角色如何對應至現有的合規性管理員角色及每個角色所允許的函數。</span><span class="sxs-lookup"><span data-stu-id="83692-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="83692-122">使用者可以：</span><span class="sxs-lookup"><span data-stu-id="83692-122">User can:</span></span> | <span data-ttu-id="83692-123">Microsoft 365 合規性中心角色</span><span class="sxs-lookup"><span data-stu-id="83692-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="83692-124">合規性管理員角色</span><span class="sxs-lookup"><span data-stu-id="83692-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="83692-125">**讀取但無法編輯資料**</span><span class="sxs-lookup"><span data-stu-id="83692-125">**Read but not edit data**</span></span>| <span data-ttu-id="83692-126">Azure AD 全域讀者</span><span class="sxs-lookup"><span data-stu-id="83692-126">Azure AD global reader</span></span>  | <span data-ttu-id="83692-127">Azure AD 全域讀者</span><span class="sxs-lookup"><span data-stu-id="83692-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="83692-128">**讀取但無法編輯資料**</span><span class="sxs-lookup"><span data-stu-id="83692-128">**Read but not edit data**</span></span>| <span data-ttu-id="83692-129">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="83692-129">Security reader</span></span> | <span data-ttu-id="83692-130">合規性管理員讀取者</span><span class="sxs-lookup"><span data-stu-id="83692-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="83692-131">**編輯資料**</span><span class="sxs-lookup"><span data-stu-id="83692-131">**Edit data**</span></span>| <span data-ttu-id="83692-132">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="83692-132">Compliance administrator</span></span> | <span data-ttu-id="83692-133">合規性參與者</span><span class="sxs-lookup"><span data-stu-id="83692-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="83692-134">**編輯測試結果**</span><span class="sxs-lookup"><span data-stu-id="83692-134">**Edit test results**</span></span>| <span data-ttu-id="83692-135">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="83692-135">Compliance administrator</span></span> | <span data-ttu-id="83692-136">合規性管理員評估者</span><span class="sxs-lookup"><span data-stu-id="83692-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="83692-137">**管理評估以及範本和租用戶資料**</span><span class="sxs-lookup"><span data-stu-id="83692-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="83692-138">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="83692-138">Compliance administrator</span></span><br><span data-ttu-id="83692-139">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="83692-139">Compliance data administrator</span></span><br><span data-ttu-id="83692-140">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="83692-140">Security administrator</span></span> | <span data-ttu-id="83692-141">合規性管理員的系統管理員</span><span class="sxs-lookup"><span data-stu-id="83692-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="83692-142">**指派給使用者**</span><span class="sxs-lookup"><span data-stu-id="83692-142">**Assign users**</span></span>| <span data-ttu-id="83692-143">全域管理員</span><span class="sxs-lookup"><span data-stu-id="83692-143">Global administrator</span></span> | <span data-ttu-id="83692-144">入口網站管理員</span><span class="sxs-lookup"><span data-stu-id="83692-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="83692-145">從合規性分數移至合規性管理員完成工作時 （例如，若要管理 「 評估 」），您的瀏覽器會開啟新的索引標籤，會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="83692-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="83692-146">在 [使用標頭 [top] 區段中，「 已 Microsoft 雲端服務客戶嗎？</span><span class="sxs-lookup"><span data-stu-id="83692-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="83692-147">您的帳戶，登入] 選取 [**登入**存取合規性管理員;您將不需要重新輸入您的認證。</span><span class="sxs-lookup"><span data-stu-id="83692-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="83692-148">如何設定 Microsoft 365 合規性中心中的權限和角色</span><span class="sxs-lookup"><span data-stu-id="83692-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="83692-149">若要在 Microsoft 365 合規性中心設定權限：</span><span class="sxs-lookup"><span data-stu-id="83692-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="83692-150">移至[Microsoft 365 合規性中心](https://compliance.microsoft.com)，並使用您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="83692-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="83692-151">在左側的導覽窗格上，選取 [**權限**。</span><span class="sxs-lookup"><span data-stu-id="83692-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="83692-152">從這裡開始，您可以檢視角色及指派權限。</span><span class="sxs-lookup"><span data-stu-id="83692-152">From here, you can view roles and assign permissions.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="83692-153">設定自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="83692-153">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="83692-154">根據預設，所有新租用戶具有自動更新開啟[安全分數](../security/mtp/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="83692-154">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="83692-155">這表示安全分數會監視的所有動作將會自動都更新中合規性分數的相同動作的狀態。</span><span class="sxs-lookup"><span data-stu-id="83692-155">This means that all actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="83692-156">您的全域管理員可以管理此設定設為關閉自動更新的所有動作，或個別地設定更新的動作。</span><span class="sxs-lookup"><span data-stu-id="83692-156">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="83692-157">期間公開預覽，您必須移至 Microsoft 服務信任入口網站 （合規性管理員所在） 來管理安全分數會更新。</span><span class="sxs-lookup"><span data-stu-id="83692-157">During public preview, you will need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="83692-158">若要管理自動安全分數更新，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="83692-158">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="83692-159">[服務信任入口網站](https://servicetrust.microsoft.com)以全域管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="83692-159">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="83692-160">在服務信任入口網站上方的功能表列中，[**更多**，選取 [**系統管理員**，然後選擇**設定**。</span><span class="sxs-lookup"><span data-stu-id="83692-160">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="83692-161">在 [**安全分數**] 索引標籤中，選取 [對應] 按鈕，任一**開啟的所有動作**，請**關閉的所有動作**，或**設定每個動作。**</span><span class="sxs-lookup"><span data-stu-id="83692-161">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="83692-162">如果您選擇**設定每個動作，** 採取下列額外的步驟，將開啟安全分數更新個別的動作：</span><span class="sxs-lookup"><span data-stu-id="83692-162">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="83692-163">從上方的功能表選取 [**合規性管理員**(附註： 請勿選取 「 合規性管理員 （傳統） 」)。</span><span class="sxs-lookup"><span data-stu-id="83692-163">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="83692-164">在您的畫面右上角中，選取 [**租用戶管理**。</span><span class="sxs-lookup"><span data-stu-id="83692-164">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="83692-165">在 [**客戶動作**] 窗格中，尋找您預定的動作，以在**受影響的動作**] 欄下省略符號 （**...**）。</span><span class="sxs-lookup"><span data-stu-id="83692-165">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="83692-166">按一下省略符號，然後選取 [**編輯]。**</span><span class="sxs-lookup"><span data-stu-id="83692-166">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="83692-167">切換**連續安全分數更新**切換切換至**上。**</span><span class="sxs-lookup"><span data-stu-id="83692-167">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="83692-168">選取 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="83692-168">Select **Save.**</span></span> <span data-ttu-id="83692-169">安全分數持續監視現在已為該動作。</span><span class="sxs-lookup"><span data-stu-id="83692-169">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="83692-170">**附註：** 只有全域系統管理員可以開啟或關閉自動更新的所有動作。</span><span class="sxs-lookup"><span data-stu-id="83692-170">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="83692-171">合規性管理員中系統管理員可以全域開啟 [自動更新的個別的動作，但不適用於所有動作。</span><span class="sxs-lookup"><span data-stu-id="83692-171">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="83692-172">讀取更多關於[管理安全分數更新](compliance-manager-release-notes.md#secure-score)。</span><span class="sxs-lookup"><span data-stu-id="83692-172">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="83692-173">了解合規性分數儀表板</span><span class="sxs-lookup"><span data-stu-id="83692-173">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="83692-174">合規性分數儀表板旨在提供您目前的合規性狀態在快速檢視。</span><span class="sxs-lookup"><span data-stu-id="83692-174">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="83692-175">![合規性分數-儀表板](media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="83692-175">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="83692-176">整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="83692-176">Overall compliance score</span></span>

<span data-ttu-id="83692-177">合規性分數，顯著精選頂端，顯示根據點可達成的完成處理索引鍵的資料保護標準與法規的改進動作的百分比。</span><span class="sxs-lookup"><span data-stu-id="83692-177">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span>

<span data-ttu-id="83692-178">當您第一次回到合規性分數時，您的初始分數根據內建的 Microsoft 365 的資料保護基準-一組控制項包含一般產業法規及標準。</span><span class="sxs-lookup"><span data-stu-id="83692-178">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="83692-179">合規性分數會掃描您的系統的現有的 Microsoft 365 解決方案，因為它可讓您根據隱私權和安全性設定目前已啟用組織的合規性狀態初始評估。</span><span class="sxs-lookup"><span data-stu-id="83692-179">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="83692-180">當您新增至您的組織相關的評估，您的分數變得更有意義。</span><span class="sxs-lookup"><span data-stu-id="83692-180">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="83692-181">深入了解[您的分數的計算方式](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="83692-181">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="83692-182">關鍵的改進動作</span><span class="sxs-lookup"><span data-stu-id="83692-182">Key improvement actions</span></span>

<span data-ttu-id="83692-183">此章節將列出上方改進您可以的採取來說，使上整體合規性分數的最大的正面影響。</span><span class="sxs-lookup"><span data-stu-id="83692-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="83692-184">它會列出未完成或失敗，具有高風險評定的動作。</span><span class="sxs-lookup"><span data-stu-id="83692-184">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="83692-185">會影響您的分數的解決方案</span><span class="sxs-lookup"><span data-stu-id="83692-185">Solutions that affect your score</span></span>

<span data-ttu-id="83692-186">您必須在每個方案中的解決方案包含動作與最大有機會帶來正面影響您的分數，以及多少未完成的改進動作此區段顯示。</span><span class="sxs-lookup"><span data-stu-id="83692-186">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="83692-187">合規性分數分解</span><span class="sxs-lookup"><span data-stu-id="83692-187">Compliance Score breakdown</span></span>

<span data-ttu-id="83692-188">本節提供詳細的檢視您分數中兩個不同的方式：</span><span class="sxs-lookup"><span data-stu-id="83692-188">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="83692-189">**類別**： 顯示內的資料保護類別，例如 「 保護資訊 」 或 「 管理裝置 」。 您整體分數的百分比</span><span class="sxs-lookup"><span data-stu-id="83692-189">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="83692-190">**「 評估 」**: 管理特定的合規性和資料保護標準、 法令或法律，例如 GDPR 或 NIST 800-53 評定顯示進度百分比。</span><span class="sxs-lookup"><span data-stu-id="83692-190">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="83692-191">篩選您的儀表板檢視</span><span class="sxs-lookup"><span data-stu-id="83692-191">Filtering your dashboard view</span></span>

<span data-ttu-id="83692-192">您可以篩選您的儀表板檢視，以查看只項目關聯至特定法規與標準、 解決方案、 巨集指令、[評估您所設定的群組](working-with-compliance-manager.md#groups)或資料保護類別類型。</span><span class="sxs-lookup"><span data-stu-id="83692-192">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="83692-193">篩選以這種方式檢視也將篩選在儀表板，顯示已達到超出根據篩選準則的總可能點多少點數的分數。</span><span class="sxs-lookup"><span data-stu-id="83692-193">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="83692-194">若要套用的篩選器：</span><span class="sxs-lookup"><span data-stu-id="83692-194">To apply filters:</span></span>

1. <span data-ttu-id="83692-195">選取 [儀表板右上方**篩選器**]。</span><span class="sxs-lookup"><span data-stu-id="83692-195">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="83692-196">從彈出式**篩選**] 窗格中，選取您的篩選條件，然後選取 [**套用**]。</span><span class="sxs-lookup"><span data-stu-id="83692-196">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="83692-197">一旦套用的篩選，您會看到您調整即時的分數。</span><span class="sxs-lookup"><span data-stu-id="83692-197">Once a filter is applied, you will see your score adjusted in real-time.</span></span> <span data-ttu-id="83692-198">合規性分數百分比分解的詳細資訊，以及改進動作與解決方案，現在只適用於所涵蓋的篩選準則的資料。</span><span class="sxs-lookup"><span data-stu-id="83692-198">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="83692-199">如果您登出合規性分數時您登入,，也會維持您篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="83692-199">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="83692-200">若要移除的篩選器：</span><span class="sxs-lookup"><span data-stu-id="83692-200">To remove filters:</span></span>

- <span data-ttu-id="83692-201">在上方合規性分數**套用篩選器**] 標題下，選取您想要移除; 個別篩選器旁邊的**X**或</span><span class="sxs-lookup"><span data-stu-id="83692-201">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="83692-202">選取**篩選**右上一邊的儀表板，然後選取 [**清除篩選**。</span><span class="sxs-lookup"><span data-stu-id="83692-202">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="83692-203">下一步</span><span class="sxs-lookup"><span data-stu-id="83692-203">Next step</span></span>

<span data-ttu-id="83692-204">請造訪以了解如何採取動作，以改善您的分數的工作流程[使用合規性分數](working-with-compliance-score.md)。</span><span class="sxs-lookup"><span data-stu-id="83692-204">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>