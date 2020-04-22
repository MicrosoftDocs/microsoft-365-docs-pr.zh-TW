---
title: 與 Microsoft 合規性管理員合作（預覽）
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
description: Microsoft 合規性管理員是免費的工作流程型風險評估工具。 使用它來追蹤、指派及驗證 Microsoft 產品相關的規章遵循活動。
ms.openlocfilehash: 2a2c0b9311062da1269f7b56c926ced9e038627f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626229"
---
# <a name="working-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="bd54d-104">使用 Microsoft 合規性管理員（預覽）</span><span class="sxs-lookup"><span data-stu-id="bd54d-104">Working with Microsoft Compliance Manager (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd54d-105">Microsoft 合規性管理員是一種儀表板和管理工具，可提供您的資料保護和合規性 stature 的摘要，以及改善資料保護和合規性的建議。</span><span class="sxs-lookup"><span data-stu-id="bd54d-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="bd54d-106">合規性管理員中提供的客戶動作為建議。</span><span class="sxs-lookup"><span data-stu-id="bd54d-106">The customer actions provided in Compliance Manager are recommendations.</span></span> <span data-ttu-id="bd54d-107">在實施之前，您的組織可以評估這些建議在其各項法規環境中的效能。</span><span class="sxs-lookup"><span data-stu-id="bd54d-107">It is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="bd54d-108">您不應將合規性管理員中找到的建議視為合規性的保證。</span><span class="sxs-lookup"><span data-stu-id="bd54d-108">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="bd54d-109">Access 合規性管理員</span><span class="sxs-lookup"><span data-stu-id="bd54d-109">Access Compliance Manager</span></span>

<span data-ttu-id="bd54d-110">合規性管理員可以從 Microsoft 服務信任入口網站存取。</span><span class="sxs-lookup"><span data-stu-id="bd54d-110">Compliance Manager is accessible from the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="bd54d-111">任何具有 Microsoft 帳戶或 Azure Active Directory 組織帳戶的人都可以存取合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="bd54d-111">Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>

1. <span data-ttu-id="bd54d-112">請移至 [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3)。</span><span class="sxs-lookup"><span data-stu-id="bd54d-112">Go to [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3).</span></span>

2. <span data-ttu-id="bd54d-113">使用您的 Microsoft 服務帳戶登入，這是您的 Office 365、Microsoft 365 或 Azure Active Directory （Azure AD）使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd54d-113">Sign in with your Microsoft service account, which is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

> [!NOTE]
> <span data-ttu-id="bd54d-114">在服務信任入口網站中，選取 [**合規性管理員**]，這是具有最新功能的預覽版本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-114">In the Service Trust Portal, select **Compliance Manager**, which is the preview version with the most current features.</span></span> <span data-ttu-id="bd54d-115">請勿選取 **[合規性管理員（經典）] （** 包含本檔未涵蓋的舊版功能）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-115">Do not select **Compliance Manager (Classic)**, which contains legacy features not covered by this documentation.</span></span>

## <a name="administration"></a><span data-ttu-id="bd54d-116">系統管理</span><span class="sxs-lookup"><span data-stu-id="bd54d-116">Administration</span></span>

<span data-ttu-id="bd54d-117">只有全域系統管理員可以使用特定的管理功能，而且只有當以全域系統管理員帳戶登入時才會顯示。</span><span class="sxs-lookup"><span data-stu-id="bd54d-117">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="bd54d-118">全域管理員可以指派使用者權限並開啟自動安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-118">The global administrator can assign user permissions and turn on automatic Secure Score updates.</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="bd54d-119">將合規性管理員角色指派給使用者</span><span class="sxs-lookup"><span data-stu-id="bd54d-119">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="bd54d-120">一旦管理員將合規性管理員角色指派給其他使用者，這些使用者便可在合規性管理員中查看資料，並執行其角色所決定的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-120">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="bd54d-121">管理員也可以在[Azure Active Directory （AZURE AD）中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)指派使用者的全域讀取者角色，授與合規性管理員的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="bd54d-121">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="bd54d-122">每個合規性管理員角色都具有稍有不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="bd54d-122">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="bd54d-123">您可以查看指派給每個角色的許可權、查看哪些使用者屬於哪些角色，以及透過服務信任入口網站新增或移除該角色中的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-123">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="bd54d-124">選取 [**管理**] 功能表項目目，然後選擇 [要查看的**設定**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-124">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理功能表：已選取設定](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="bd54d-126">若要新增使用者或從合規性管理員角色中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-126">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="bd54d-127">請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bd54d-127">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="bd54d-128">使用您的 Azure Active Directory 全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="bd54d-128">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="bd54d-129">在服務信任入口網站頂端功能表列上，選取 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-129">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="bd54d-130">在 [**選取角色**] 下拉式清單中，選取您要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="bd54d-130">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="bd54d-131">新增至每個角色的使用者會列在 [選取角色]\*\*\*\* 頁面上。</span><span class="sxs-lookup"><span data-stu-id="bd54d-131">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="bd54d-132">若要將使用者新增至此角色，請選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-132">To add users to this role, select **Add**.</span></span> <span data-ttu-id="bd54d-133">在 [**新增使用者**] 對話方塊中，選取 [使用者] 欄位。</span><span class="sxs-lookup"><span data-stu-id="bd54d-133">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="bd54d-134">您可以在可用的使用者清單中向內移動，或是開始輸入使用者名稱，以根據您的搜尋字詞篩選清單。</span><span class="sxs-lookup"><span data-stu-id="bd54d-134">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="bd54d-135">選取要將該帳戶新增至以該角色布建的 [**新增使用者**] 清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-135">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="bd54d-136">如果您想要同時新增多個使用者，請開始輸入使用者名稱以篩選清單，然後選取要新增至清單的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-136">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="bd54d-137">選取 [**儲存**]，將選取的角色布建給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-137">Select **Save** to provision the selected role to these users.</span></span> 

    ![合規性管理員-新增使用者](../media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="bd54d-139">若要移除此角色中的使用者，請選取使用者，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-139">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合規性管理員-刪除使用者](../media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="bd54d-141">控制自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="bd54d-141">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="bd54d-142">您可以使用下列步驟，針對所有動作，關閉所有動作，關閉所有動作，或透過個別動作設定安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-142">Secure Score updates can be turned on automatically for all actions, turned off for all actions, or set by individual action by following these steps.</span></span>

1. <span data-ttu-id="bd54d-143">使用您的全域系統管理員帳戶登入[服務信任入口網站](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bd54d-143">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="bd54d-144">在服務信任入口網站頂端功能表列上，按一下 [**其他**] 下的 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-144">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="bd54d-145">在 [**安全分數**] 索引標籤中，選取對應的按鈕來**開啟所有動作**、**關閉所有動作**，或**設定每個動作。**</span><span class="sxs-lookup"><span data-stu-id="bd54d-145">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="bd54d-146">如果您選擇 [**依動作設定]，請**採取下列額外步驟，為個別動作開啟安全分數更新：</span><span class="sxs-lookup"><span data-stu-id="bd54d-146">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="bd54d-147">從上方功能表中選取 [**合規性管理員**] （附注：不要選取「合規性管理員（古典）」）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-147">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="bd54d-148">在螢幕的右上角選取 [**租使用者管理**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-148">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="bd54d-149">在 [**客戶動作**] 窗格上，在 [**受影響的動作**] 欄下，以省略號（**...**）尋找您的預定動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-149">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="bd54d-150">按一下省略號，然後選取 [**編輯]。**</span><span class="sxs-lookup"><span data-stu-id="bd54d-150">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="bd54d-151">將**安全分數連續更新**切換開關切換為 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="bd54d-151">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="bd54d-152">選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="bd54d-152">Select **Save.**</span></span> <span data-ttu-id="bd54d-153">安全分數連續監控現在已開啟該動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-153">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="bd54d-154">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-154">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="bd54d-155">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-155">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

## <a name="groups"></a><span data-ttu-id="bd54d-156">群組</span><span class="sxs-lookup"><span data-stu-id="bd54d-156">Groups</span></span>

<span data-ttu-id="bd54d-157">群組是容器，可讓您組織評估，並在具有相同或相關客戶管理控制措施的評估之間共用一般資訊和工作流程工作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-157">Groups are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span>

<span data-ttu-id="bd54d-158">您可以根據對您邏輯的方式來群組評估，例如依年、標準、服務或組織的小組、部門或地理區域。</span><span class="sxs-lookup"><span data-stu-id="bd54d-158">You can group Assessments in a way that is logical to you, such as by year, standard, service, or based on your organization's teams, divisions, or geographies.</span></span> <span data-ttu-id="bd54d-159">以下是兩個群組和其基礎評估的範例：</span><span class="sxs-lookup"><span data-stu-id="bd54d-159">Below are examples of two groups and their underlying Assessments:</span></span>
  
- <span data-ttu-id="bd54d-160">**FFIEC 是評估2020**</span><span class="sxs-lookup"><span data-stu-id="bd54d-160">**FFIEC IS Assessments 2020**</span></span>
  - <span data-ttu-id="bd54d-161">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="bd54d-161">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="bd54d-162">Intune + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="bd54d-162">Intune + FFIEC IS</span></span>
- <span data-ttu-id="bd54d-163">**資料安全性與隱私權評估**</span><span class="sxs-lookup"><span data-stu-id="bd54d-163">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="bd54d-164">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="bd54d-164">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="bd54d-165">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="bd54d-165">Office 365 + ISO 27018:2014</span></span>

> [!NOTE]
> <span data-ttu-id="bd54d-166">建議您先判斷貴組織的群群組原則，*然後再*新增新的評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-166">We recommend determining a grouping strategy for your organization *before* adding new Assessments.</span></span>

<span data-ttu-id="bd54d-167">為了讓您開始，您會為您設定一個包含資料保護基準的**預設**群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-167">To get you started, a **Default** group is set up for you that contains the Data Protection Baseline.</span></span> <span data-ttu-id="bd54d-168">此基準是一組包含常見工業法規和標準的控制項（[深入瞭解](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-168">This baseline is a set of controls that includes common industry regulations and standards ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="bd54d-169">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="bd54d-169">How to create a group</span></span>

<span data-ttu-id="bd54d-170">群組無法建立為獨立實體。</span><span class="sxs-lookup"><span data-stu-id="bd54d-170">Groups cannot be created as standalone entities.</span></span> <span data-ttu-id="bd54d-171">群組必須至少包含一個評估，因此若要建立群組，您必須先建立評估以放置在群組中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-171">A group must always contain at least one Assessment, so in order to create a group, you must first create an Assessment to put in the group.</span></span>

<span data-ttu-id="bd54d-172">請遵循下列步驟建立群組：</span><span class="sxs-lookup"><span data-stu-id="bd54d-172">Follow the steps below to create a group:</span></span>

1. <span data-ttu-id="bd54d-173">您可以在儀表板頂端的附近，選取 [新增**評估**]，以建立新的評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-173">Create a new Assessment by selecting **+ Add Assessment** near the top of your dashboard.</span></span>
2. <span data-ttu-id="bd54d-174">在 [**評估**] 快顯視窗中，輸入評估的標題，然後從下拉式功能表中選取範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-174">From the **Assessment** flyout pane, enter a title for your Assessment and select a template from the drop-down menu.</span></span>
3. <span data-ttu-id="bd54d-175">在 [**請選取群組或新增**群組] 中，選取 [**新增群組**]，然後在下欄欄位中輸入您的組名。</span><span class="sxs-lookup"><span data-stu-id="bd54d-175">At **Please select a group or add a new group**, select **Add a new group** and enter your group name in the field below.</span></span>
4. <span data-ttu-id="bd54d-176">若要複製現有群組中的資訊，請切換 [**您想要從現有的群組複製資料嗎？** ] 切換至 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="bd54d-176">To copy information from an existing group, toggle the **Would you like to copy the data from an existing group?** switch to **On.**</span></span> <span data-ttu-id="bd54d-177">從下拉式功能表中選取您要複製的群組，然後選取您想要在新群組中執行新評估的任何欄位核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-177">Select the group you want to copy from the drop-down menu underneath, and select the checkboxes of any fields you want to carry over to the new Assessment in your new group.</span></span>
5. <span data-ttu-id="bd54d-178">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-178">Select **Save**.</span></span> <span data-ttu-id="bd54d-179">完成後，就會關閉彈出窗格，您會在儀表板上看到您的新群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-179">When completed, the flyout pane closes and you'll see your new group on your dashboard.</span></span>

<span data-ttu-id="bd54d-180">使用群組時所知道的事項：</span><span class="sxs-lookup"><span data-stu-id="bd54d-180">What to know when working with groups:</span></span>
  
- <span data-ttu-id="bd54d-181">組名（也稱為「*群組 IDs*）在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-181">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="bd54d-182">群組沒有任何安全性屬性。</span><span class="sxs-lookup"><span data-stu-id="bd54d-182">Groups do not have any security properties.</span></span> <span data-ttu-id="bd54d-183">擁有權限都與評估相關聯。</span><span class="sxs-lookup"><span data-stu-id="bd54d-183">All permissions are associated with Assessments.</span></span>
- <span data-ttu-id="bd54d-184">將評估新增至群組之後，就無法變更該群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-184">Once you add an Assessment to a group, the grouping cannot be changed.</span></span> <span data-ttu-id="bd54d-185">您可以重新命名評估群組，這會變更與該群組相關之所有評估的評估群組名稱。</span><span class="sxs-lookup"><span data-stu-id="bd54d-185">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span>
- <span data-ttu-id="bd54d-186">完成時，相同群組內的相關評估控制項會自動更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-186">Related Assessment controls in different Assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="bd54d-187">如果您將新的評估新增至現有的群組，則會將該群組中評估的一般資訊複製到新的評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-187">If you add a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="bd54d-188">群組可以包含同一個憑證或法規的評估，但是每個群組只能包含特定產品認證組的一個評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-188">Groups can contain Assessments for the same certification or regulation, but each group can only contain one Assessment for a specific product-certification pair.</span></span> <span data-ttu-id="bd54d-189">例如，群組不可包含針對 Office 365 和 NIST CSF 的兩項評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-189">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="bd54d-190">只有在每個群組的對應憑證或法規不同時，群組才可以包含同一個產品的多項評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-190">A group can contain multiple Assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="bd54d-191">隱藏評估會中斷這種評估與群組之間的關係。</span><span class="sxs-lookup"><span data-stu-id="bd54d-191">Hiding an Assessment breaks the relationship between that Assessment and the group.</span></span> <span data-ttu-id="bd54d-192">其他相關評估的任何進一步更新都會不再反映在隱藏評估中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-192">Any further updates to other related Assessments are no longer reflected in the hidden assessment.</span></span> <span data-ttu-id="bd54d-193">（[瞭解如何隱藏評估。](#hide-a-template-or-an-assessment)）</span><span class="sxs-lookup"><span data-stu-id="bd54d-193">([Learn how to hide Assessments.](#hide-a-template-or-an-assessment))</span></span>
- <span data-ttu-id="bd54d-194">無法刪除群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-194">Groups cannot be deleted.</span></span>
- <span data-ttu-id="bd54d-195">當對出現于多個群組中的動作專案進行變更時，該變更會反映在該動作專案的所有實例中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-195">When a change is made to an Action Item that appears in multiple Groups, that change is reflected in all instances of that Action Item.</span></span>

## <a name="tenant-management-of-dimensions-owners--customer-actions"></a><span data-ttu-id="bd54d-196">對維度、擁有者、& 客戶動作的承租人管理</span><span class="sxs-lookup"><span data-stu-id="bd54d-196">Tenant management of dimensions, owners, & customer actions</span></span>

<span data-ttu-id="bd54d-197">**承租人管理**介面可讓您管理這些組織範圍的設定：</span><span class="sxs-lookup"><span data-stu-id="bd54d-197">The **Tenant Management** interface enables you to manage these organization-wide settings:</span></span>

- <span data-ttu-id="bd54d-198">**維度：** View 可讓您建立自訂樞軸篩選的範本、評估及動作專案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-198">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="bd54d-199">**擁有者：** 填入可與動作相關聯的責任方清單。</span><span class="sxs-lookup"><span data-stu-id="bd54d-199">**Owners:** Populate a list of responsible parties that can be associated with actions.</span></span>
- <span data-ttu-id="bd54d-200">**客戶動作：** 管理合規性管理員（預覽）中包含的完整動作專案清單，並啟用/停用以安全分數整合之動作的安全評分監控。</span><span class="sxs-lookup"><span data-stu-id="bd54d-200">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="bd54d-201">從畫面的右上角選取 [**租使用者管理**] 以開啟管理介面，並使用下列步驟來管理**維度**、**擁有**者及**客戶動作**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-201">Select **Tenant Management** from the upper-right corner of your screen to open the management interface, and use the steps below to manage  **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="bd54d-202">Dimensions</span><span class="sxs-lookup"><span data-stu-id="bd54d-202">Dimensions</span></span>

<span data-ttu-id="bd54d-203">維度是一組中繼資料，可提供範本、評估或交辦事項的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-203">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="bd54d-204">維度使用索引鍵和值的概念，其中維度索引鍵代表屬性，維度值代表屬性的有效值。</span><span class="sxs-lookup"><span data-stu-id="bd54d-204">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="bd54d-205">例如，在合規性管理員中，有三種類型的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-205">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="bd54d-206">它們是由**動作目的**的維度鍵和**預防**、**偵探**和**修正**的維度值所定義。</span><span class="sxs-lookup"><span data-stu-id="bd54d-206">They are defined by a Dimension Key of **Action Purpose** and Dimension Values of **Preventative**, **Detective**, and **Corrective**.</span></span>

### <a name="owners"></a><span data-ttu-id="bd54d-207">擁有者</span><span class="sxs-lookup"><span data-stu-id="bd54d-207">Owners</span></span>

<span data-ttu-id="bd54d-208">擁有者可用於識別每個控制項的負責人。</span><span class="sxs-lookup"><span data-stu-id="bd54d-208">Owners are used to identify the person responsible for each control.</span></span> <span data-ttu-id="bd54d-209">所有內建的控制項都是由 Microsoft、客戶或兩者所擁有。</span><span class="sxs-lookup"><span data-stu-id="bd54d-209">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="bd54d-210">您可以為擁有者建立自訂值，以用於在組織中指定更細微的責任。</span><span class="sxs-lookup"><span data-stu-id="bd54d-210">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="bd54d-211">例如，您可以建立代表組織內特定群組、小組或業務單位的擁有者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-211">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="bd54d-212">新增擁有者</span><span class="sxs-lookup"><span data-stu-id="bd54d-212">Add an Owner</span></span>

1. <span data-ttu-id="bd54d-213">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-213">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="bd54d-214">選取 [ **+ 新增擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-214">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="bd54d-215">提供擁有者的名稱和描述，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-215">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="bd54d-216">描述會顯示在 [擁有者] 欄中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-216">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="bd54d-217">編輯擁有者</span><span class="sxs-lookup"><span data-stu-id="bd54d-217">Edit an Owner</span></span>

<span data-ttu-id="bd54d-218">您無法編輯擁有者名稱，但您可以修改顯示在 [擁有者] 欄中的描述。</span><span class="sxs-lookup"><span data-stu-id="bd54d-218">You can't edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="bd54d-219">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-219">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="bd54d-220">找到您要編輯的擁有者，選取其旁邊的省略號（...），然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-220">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="bd54d-221">視需要修改描述，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-221">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="bd54d-222">刪除擁有者</span><span class="sxs-lookup"><span data-stu-id="bd54d-222">Delete an Owner</span></span>

1. <span data-ttu-id="bd54d-223">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-223">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="bd54d-224">找到您想要刪除的擁有者，選取其旁邊的省略號（...），然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-224">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="bd54d-225">出現確認訊息時，請選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-225">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="bd54d-226">客戶動作</span><span class="sxs-lookup"><span data-stu-id="bd54d-226">Customer Actions</span></span>

<span data-ttu-id="bd54d-227">[客戶動作] 區域會顯示合規性管理員（預覽）中所有範本及評估的所有客戶動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-227">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

<span data-ttu-id="bd54d-228">![合規性管理員-新增使用者](../media/compliance-manager-customer-actions.png "合規性管理員客戶動作")</span><span class="sxs-lookup"><span data-stu-id="bd54d-228">![Compliance Manager — add users](../media/compliance-manager-customer-actions.png "Compliance Manager Customer Actions")</span></span>

<span data-ttu-id="bd54d-229">您可以快速查看動作的標題、擁有者、類別、強制執行和評分，並判斷是否與安全分數整合。</span><span class="sxs-lookup"><span data-stu-id="bd54d-229">At a glance, you can see an Action's title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="bd54d-230">您可以展開動作並選取 [**讀取**]，以閱讀動作的描述並存取描述中的任何連結。</span><span class="sxs-lookup"><span data-stu-id="bd54d-230">You can expand an Action and select **Read More** to read the Action's description and access any links in the description.</span></span> <span data-ttu-id="bd54d-231">您也可以使用此介面來啟用及停用以每個動作為基礎的安全分數整合，以及新增自訂動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-231">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="bd54d-232">具有安全計分整合功能的動作旁會有省略號（...）（請注意，自訂動作旁邊也有省略號）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-232">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="bd54d-233">啟用或停用安全分數整合</span><span class="sxs-lookup"><span data-stu-id="bd54d-233">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="bd54d-234">針對您要修改的動作選取省略號（...），然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-234">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="bd54d-235">切換切換參數，以取得安全分數連續更新為開啟或關閉，以啟用或停用透過安全分數的連續監控。</span><span class="sxs-lookup"><span data-stu-id="bd54d-235">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="bd54d-236">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-236">Select **Save**.</span></span>

<span data-ttu-id="bd54d-237">當組織第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行保護，以完全收集資料，並將其劃分為您的分數。</span><span class="sxs-lookup"><span data-stu-id="bd54d-237">When organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="bd54d-238">在這段時間內，將安全計分連續更新參數設定為**Off** ，並手動設定所要**執行**的動作，就會將該動作計算為您的分數。</span><span class="sxs-lookup"><span data-stu-id="bd54d-238">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="bd54d-239">在最初7天后，開啟安全分數連續更新會啟用從該點繼續進行監視。</span><span class="sxs-lookup"><span data-stu-id="bd54d-239">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>

<span data-ttu-id="bd54d-240">安全分數整合不支援的任何動作都可以手動實施。</span><span class="sxs-lookup"><span data-stu-id="bd54d-240">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="bd54d-241">手動執行將會考慮該動作群組的分數。</span><span class="sxs-lookup"><span data-stu-id="bd54d-241">A manual implementation will factor into the score for that action's group.</span></span>

## <a name="assessments"></a><span data-ttu-id="bd54d-242">評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-242">Assessments</span></span>

<span data-ttu-id="bd54d-243">本節說明如何查看和使用評估，包括如何新增、匯出、複製現有評估中的資訊，以及透過版本設定將其更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-243">This section explains how to view and work with your Assessments, including how to add new ones, export them, copy information from existing Assessments, and keep them updated through versioning.</span></span>

### <a name="view-an-assessment-and-action-details"></a><span data-ttu-id="bd54d-244">查看評估和動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="bd54d-244">View an Assessment and Action details</span></span>
  
<span data-ttu-id="bd54d-245">在 [**評估**] 儀表板中，選取 [評估名稱] 以開啟它，然後查看 [動作專案] 和 [控制項] 資訊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-245">In the **Assessments** dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="bd54d-246">以下是 Office 365 及 ISO 27001 評估的範例。</span><span class="sxs-lookup"><span data-stu-id="bd54d-246">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="bd54d-247">第一個視圖說明合規性管理員（預覽）中的新動作專案視圖。</span><span class="sxs-lookup"><span data-stu-id="bd54d-247">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合規性管理員動作專案視圖](../media/compliance-manager-action-items.png)

<span data-ttu-id="bd54d-249">動作會以字母順序列出，而且每個動作都會被指派分數和擁有者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-249">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="bd54d-250">選取 [**讀取其他**] 連結，以閱讀每個動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-250">Select  the **Read More** link to read the details of each Action.</span></span>

![合規性管理員動作專案視圖](../media/compliance-manager-actions-read-more.png)

<span data-ttu-id="bd54d-252">選取 [**檢查**] 連結，以管理、指派、實施及測試動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-252">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="bd54d-253">以下是範例動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-253">Below is an example Action.</span></span>

![合規性管理員動作視圖](../media/compliance-manager-action.png)

<span data-ttu-id="bd54d-255">使用下欄欄位來管理動作工作流程：</span><span class="sxs-lookup"><span data-stu-id="bd54d-255">Use the following fields to manage the Action workflow:</span></span>

- <span data-ttu-id="bd54d-256">**指派使用者：** 選取此欄位，以選擇或輸入應指派此動作的使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-256">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="bd54d-257">您可以在清單中滾動，或輸入名稱來尋找，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="bd54d-257">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="bd54d-258">**管理檔：** 您可以以 Office 檔、圖像檔案及螢幕擷取畫面的形式上傳執行證據，在 CSV 或 TXT 中 PowerShell 輸出，以及 Pdf。</span><span class="sxs-lookup"><span data-stu-id="bd54d-258">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="bd54d-259">**實施狀態：** 用來指出動作目前的執行狀態。</span><span class="sxs-lookup"><span data-stu-id="bd54d-259">**Implementation Status:** Used to indicate the Action's current implementation status.</span></span> <span data-ttu-id="bd54d-260">可能的值尚未實現、已實現、替代的實施、規劃中和不在範圍內。</span><span class="sxs-lookup"><span data-stu-id="bd54d-260">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="bd54d-261">**實施日期：** 採取動作的日期。</span><span class="sxs-lookup"><span data-stu-id="bd54d-261">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="bd54d-262">**測試結果：** 用來指出實施驗證的結果。</span><span class="sxs-lookup"><span data-stu-id="bd54d-262">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="bd54d-263">可能的值不會評估、傳遞、失敗-低風險、失敗-中低風險、失敗-高風險，而且不在範圍內。</span><span class="sxs-lookup"><span data-stu-id="bd54d-263">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="bd54d-264">**測試日期：** 驗證發生的日期。</span><span class="sxs-lookup"><span data-stu-id="bd54d-264">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="bd54d-265">**執行附注：** 輸入組織的執行詳細資料，以及您想要包含的任何附注。</span><span class="sxs-lookup"><span data-stu-id="bd54d-265">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="bd54d-266">**測試方案：** 輸入此動作的測試計劃詳細資料，以及您要包含的任何附注。</span><span class="sxs-lookup"><span data-stu-id="bd54d-266">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="bd54d-267">**其他資訊：** 輸入有關此動作或其在組織中實施方式的任何其他資訊，以及您想要加入的任何附注。</span><span class="sxs-lookup"><span data-stu-id="bd54d-267">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="bd54d-268">在 [**控制項資訊**] 儀表板上，您可以在評估與範本層級查看控制項資訊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-268">On the **Controls Info** dashboard, you can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="bd54d-269">以下是評估的控制項資訊儀表板的範例。</span><span class="sxs-lookup"><span data-stu-id="bd54d-269">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合規性管理員控制資訊視圖](../media/compliance-manager-controls-info.png)

<span data-ttu-id="bd54d-271">針對評估，[控制項資訊] 儀表板會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="bd54d-271">For Assessments, the Controls Info dashboard displays the following information:</span></span>

- <span data-ttu-id="bd54d-272">**群組**下拉式清單，可選取要查看的群組（使用多個群組時）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-272">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="bd54d-273">**評估**下拉式功能表，以選取要查看的評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-273">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="bd54d-274">所選評估的中繼資料，包括：</span><span class="sxs-lookup"><span data-stu-id="bd54d-274">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="bd54d-275">**評估控制項**的進度指標，顯示超過控制項總數的評估的控制項數目。</span><span class="sxs-lookup"><span data-stu-id="bd54d-275">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="bd54d-276">評估的目前**符合性分數**，顯示為百分數。</span><span class="sxs-lookup"><span data-stu-id="bd54d-276">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="bd54d-277">評估中所用之**憑證及\*\*\*\*產品**的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-277">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="bd54d-278">評估的目前**狀態**和上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="bd54d-278">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="bd54d-279">評估的**範圍服務**清單。</span><span class="sxs-lookup"><span data-stu-id="bd54d-279">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="bd54d-280">控制項的詳細資料，依控制項系列分組，包含客戶動作和 Microsoft 執行詳細資料的連結：</span><span class="sxs-lookup"><span data-stu-id="bd54d-280">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="bd54d-281">**您的動作**會顯示您可以執行的客戶動作，以滿足部分或所有控制項的需求。</span><span class="sxs-lookup"><span data-stu-id="bd54d-281">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control's requirements.</span></span> <span data-ttu-id="bd54d-282">許多控制項具有多個與其相關聯的動作，而且所有與控制項關聯的動作都會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="bd54d-282">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="bd54d-283">這裡的動作與動作儀表板中所列的 UI 相同。</span><span class="sxs-lookup"><span data-stu-id="bd54d-283">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="bd54d-284">**Microsoft 動作**會顯示 Microsoft 內部架構中套用至所選認證控制項的控制項清單。</span><span class="sxs-lookup"><span data-stu-id="bd54d-284">**Microsoft Actions** displays the list of controls from Microsoft's internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="bd54d-285">針對每個內部控制，選取 [已**執行**]，以查看 Microsoft 的執行和測試詳細資料，以及測試結果和測試日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="bd54d-285">For each internal control, select **Implemented** to see Microsoft's implementation and test details, along with the test result and test date, as shown below.</span></span>

![合規性管理員 Microsoft 動作視圖](../media/compliance-manager-microsoft-action.png)

### <a name="add-an-assessment"></a><span data-ttu-id="bd54d-287">新增評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-287">Add an Assessment</span></span>
  
1. <span data-ttu-id="bd54d-288">在 [評估] 儀表板中，選取 [ **+ Add 評估**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-288">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="bd54d-289">當刀片式伺服器開啟時，請輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="bd54d-289">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="bd54d-290">**職稱（必要）：** 輸入評估的標題</span><span class="sxs-lookup"><span data-stu-id="bd54d-290">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="bd54d-291">**請選取範本（必要）：** 選取標準或自訂範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-291">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="bd54d-292">**請選取群組或新增新的群組（必要）：** 選取現有的群組，或選擇新增群組，並提供唯一的組名</span><span class="sxs-lookup"><span data-stu-id="bd54d-292">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="bd54d-293">**您要複製現有群組中的資料嗎？（選用）：** 切換控制項以啟用群組副本，然後：</span><span class="sxs-lookup"><span data-stu-id="bd54d-293">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="bd54d-294">**選取群組（選用）：** 如果已啟用群組副本，請選取要複製的群組</span><span class="sxs-lookup"><span data-stu-id="bd54d-294">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="bd54d-295">**執行詳細資料（選用）：** 選取以將實現詳細資料複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="bd54d-295">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="bd54d-296">**測試計劃 & 其他資訊（選用）：** 選取以將測試計劃及其他資訊詳細資料複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="bd54d-296">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="bd54d-297">**檔（選用）：** 選取以將檔案複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="bd54d-297">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="bd54d-298">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-298">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="bd54d-299">評估儀表板上會顯示新的評估，並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="bd54d-299">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="bd54d-300">評估的標題。</span><span class="sxs-lookup"><span data-stu-id="bd54d-300">The title of the Assessment.</span></span>
- <span data-ttu-id="bd54d-301">評估的維度，包括憑證、環境和套用至評估的產品。</span><span class="sxs-lookup"><span data-stu-id="bd54d-301">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="bd54d-302">其建立日期和上次修改日期的日期。</span><span class="sxs-lookup"><span data-stu-id="bd54d-302">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="bd54d-303">評估分數顯示為百分比。</span><span class="sxs-lookup"><span data-stu-id="bd54d-303">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="bd54d-304">這個分數會自動包含您的分數從 Microsoft 管理的控制項，以及從安全得分。</span><span class="sxs-lookup"><span data-stu-id="bd54d-304">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="bd54d-305">顯示已評估的 Microsoft 管理和客戶管理控制措施數目的進度指標。</span><span class="sxs-lookup"><span data-stu-id="bd54d-305">Progress indicators that show the number of assessed Microsoft-managed and customer-managed controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="bd54d-306">從現有「評定」複製資訊</span><span class="sxs-lookup"><span data-stu-id="bd54d-306">Copying information from existing Assessments</span></span>

<span data-ttu-id="bd54d-307">當您建立評估時，您可以選擇複製現有群組中的資訊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-307">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="bd54d-308">複製功能可讓您將輸入到複製評估中的資訊套用到新評估中的相同控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-308">Copying allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="bd54d-309">例如，如果您的組織中有所有 FFIEC 相關評估的群組，您可以從現有評估中複製下列資訊：</span><span class="sxs-lookup"><span data-stu-id="bd54d-309">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="bd54d-310">執行詳細資料</span><span class="sxs-lookup"><span data-stu-id="bd54d-310">Implementation Details</span></span>
- <span data-ttu-id="bd54d-311">測試計劃 & 其他資訊</span><span class="sxs-lookup"><span data-stu-id="bd54d-311">Test Plan & Additional Information</span></span>
- <span data-ttu-id="bd54d-312">文件</span><span class="sxs-lookup"><span data-stu-id="bd54d-312">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="bd54d-313">將現有評估的資訊複製到新的評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-313">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="bd54d-314">在 [評估] 儀表板中，選取 [ **+ Add 評估**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-314">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="bd54d-315">在 [**新增評估**] 視窗中，完成下列資訊：</span><span class="sxs-lookup"><span data-stu-id="bd54d-315">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="bd54d-316">**職稱（必要）：** 輸入評估的標題。</span><span class="sxs-lookup"><span data-stu-id="bd54d-316">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="bd54d-317">**請選取範本（必要）：** 選取標準或自訂的範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-317">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="bd54d-318">**請選取群組或新增新的群組（必要）：** 選擇 [新增**群組**]，並提供唯一的組名。</span><span class="sxs-lookup"><span data-stu-id="bd54d-318">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="bd54d-319">**您要複製現有群組中的資料嗎？（選用）：** 將控制項切換至開啟以啟用群組副本，然後：**選取群組（選用）：** 如果已啟用群組副本，請選取要複製的群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-319">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="bd54d-320">- **執行詳細資料（選用）：** 選取可將實現詳細資料複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-320">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="bd54d-321">- **測試計劃 & 其他資訊（選用）：** 選取以將測試計劃及其他資訊詳細資料複製到新群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-321">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="bd54d-322">- **檔（選用）：** 選取以將檔案複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-322">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="bd54d-323">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-323">Select **Save** to create the Assessment.</span></span>

### <a name="versioning-alerts-for-assessment-updates"></a><span data-ttu-id="bd54d-324">評估更新的版本設定警示</span><span class="sxs-lookup"><span data-stu-id="bd54d-324">Versioning alerts for Assessment updates</span></span>

<span data-ttu-id="bd54d-325">當評估有可用的更新時，提醒圖示會通知您有更新準備就緒。</span><span class="sxs-lookup"><span data-stu-id="bd54d-325">When an update is available for an Assessment, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="bd54d-326">當您按一下該圖示時，會快顯視窗來說明更新，並提示您接受。</span><span class="sxs-lookup"><span data-stu-id="bd54d-326">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="bd54d-327">以下是評估的版本設定警示範例：</span><span class="sxs-lookup"><span data-stu-id="bd54d-327">Below is an example of the versioning alert for an Assessment:</span></span>

<span data-ttu-id="bd54d-328">![合規性分數-版本設定警示](../media/compliance-score-assessment-version.png "評估版本更新警示")</span><span class="sxs-lookup"><span data-stu-id="bd54d-328">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="bd54d-329">選取警示圖示會顯示彈出窗格，說明更新並提示您接受：</span><span class="sxs-lookup"><span data-stu-id="bd54d-329">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="bd54d-330">![合規性分數-版本快顯視窗](../media/compliance-score-assessment-version-accept.png "評估更新確認窗格")</span><span class="sxs-lookup"><span data-stu-id="bd54d-330">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

<span data-ttu-id="bd54d-331">我們強烈建議您在收到更新通知時接受所有更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-331">We strongly recommend accepting all updates when you receive update notifications.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="bd54d-332">匯出評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-332">Export an Assessment</span></span>

<span data-ttu-id="bd54d-333">您可以將評估匯出至您組織中或外部審計員和主管的符合性專案關係人的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="bd54d-333">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="bd54d-334">報表是指報表建立日期和時間的評估快照。</span><span class="sxs-lookup"><span data-stu-id="bd54d-334">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="bd54d-335">報告包含針對評估、控制執行狀態、控制測試日期、測試結果，以及提供上傳的證據檔連結的所有 Microsoft 及客戶管理控制項的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-335">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="bd54d-336">匯出評估報告</span><span class="sxs-lookup"><span data-stu-id="bd54d-336">Export an Assessment report</span></span>
  
1. <span data-ttu-id="bd54d-337">在 [合規性管理員] 儀表板上，選取 [**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bd54d-337">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="bd54d-338">在下拉式功能表中，選取您要匯出之評估的**群組**和**評估**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-338">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="bd54d-339">選取 [**匯出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bd54d-339">Select the **Export** button.</span></span>

<span data-ttu-id="bd54d-340">在您的瀏覽器會話中，會將評估報告當做 Excel 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="bd54d-340">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="bd54d-341">Excel 檔案的 files 名稱預設為評估的標題。</span><span class="sxs-lookup"><span data-stu-id="bd54d-341">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="bd54d-342">隱藏範本或評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-342">Hide a Template or an Assessment</span></span>

<span data-ttu-id="bd54d-343">當您完成範本或評估，但是不再因相容性目的而需要時，您可以將它從您的視圖中隱藏。</span><span class="sxs-lookup"><span data-stu-id="bd54d-343">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="bd54d-344">當範本或評估隱藏時，它會從預設視圖中移除，您必須選取 [**包含隱藏**] 核取方塊加以顯示。</span><span class="sxs-lookup"><span data-stu-id="bd54d-344">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="bd54d-345">![合規性管理員隱藏的範本視圖](../media/compliance-manager-hidden-template.png "合規性管理員隱藏範本")</span><span class="sxs-lookup"><span data-stu-id="bd54d-345">![Compliance Manager Hidden Template View](../media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd54d-346">隱藏評估不會保留其上傳的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="bd54d-346">Hidden Assessments don't retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="bd54d-347">強烈建議您在隱藏評估之前先將其匯出，以保留報告中的證據檔連結。</span><span class="sxs-lookup"><span data-stu-id="bd54d-347">We highly recommended that you export an Assessment before hiding it to retain links to evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="bd54d-348">隱藏範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-348">Hiding a Template</span></span>

1. <span data-ttu-id="bd54d-349">開啟 [**範本**] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="bd54d-349">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="bd54d-350">找到您想要隱藏的範本，並在其列的省略號上，選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-350">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="bd54d-351">當您看到確認訊息時，請選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-351">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="bd54d-352">隱藏評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-352">Hide an Assessment</span></span>

1. <span data-ttu-id="bd54d-353">開啟 [**評估**儀表板]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-353">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="bd54d-354">從下拉式清單中，選取包含您想要隱藏之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-354">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="bd54d-355">找到您想要隱藏的評估，並選取省略號，選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-355">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="bd54d-356">當您看到確認訊息時，請選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-356">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="bd54d-357">查看隱藏評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-357">View hidden Assessments</span></span>
  
1. <span data-ttu-id="bd54d-358">開啟 [**評估**儀表板] 索引標籤，然後選取 [**包含隱藏**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-358">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="bd54d-359">隱藏評估會顯示在 [**隱藏評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-359">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="bd54d-360">取消隱藏評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-360">Unhide an Assessment</span></span>

1. <span data-ttu-id="bd54d-361">在 [**評估**] 索引標籤上，選取 [**包含隱藏**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-361">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="bd54d-362">隱藏評估會顯示在 [**隱藏評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-362">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="bd54d-363">找到您想要取消隱藏的評估，並選取省略號，選取 [**取消隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-363">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="bd54d-364">當您看到確認訊息時，請選取 [**取消隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-364">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="bd54d-365">控制項和動作</span><span class="sxs-lookup"><span data-stu-id="bd54d-365">Controls and Actions</span></span>

<span data-ttu-id="bd54d-366">控制項和動作是合規性管理員（預覽）中所使用的主要資料轉動。</span><span class="sxs-lookup"><span data-stu-id="bd54d-366">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="bd54d-367">在舊版本的合規性管理員中，控制項 pivot 已增強，可在相同的控制系列中顯示 Microsoft 和客戶控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-367">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="bd54d-368">這種合併的視圖可讓您更容易查看每個控制項的完整共用責任模型。</span><span class="sxs-lookup"><span data-stu-id="bd54d-368">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="bd54d-369">Action pivot 是合規性管理員（預覽）中的新功能，其設計目的是為了提供 Microsoft 建議的所有動作的簡潔觀點。</span><span class="sxs-lookup"><span data-stu-id="bd54d-369">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="bd54d-370">控制項</span><span class="sxs-lookup"><span data-stu-id="bd54d-370">Controls</span></span>

<span data-ttu-id="bd54d-371">控制項可以從 [控制項資訊] 儀表板中查看。</span><span class="sxs-lookup"><span data-stu-id="bd54d-371">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="bd54d-372">控制項代表標準、認證、法規或架構中的需求。</span><span class="sxs-lookup"><span data-stu-id="bd54d-372">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="bd54d-373">若要將這些需求對應至多個標準、法規等專案，並將這些需求與動作相關聯，請將所有專案視為控制項框架。</span><span class="sxs-lookup"><span data-stu-id="bd54d-373">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="bd54d-374">例如，像是控制架構之外，規章（如 HIPAA）已細分為一節，合規性管理員中的 HIPAA 控制項使用與這些區段相同的編號配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd54d-374">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合規性管理員 Microsoft 控制項詳細資料](../media/compliance-manager-control-details.png)

<span data-ttu-id="bd54d-376">控制項有三種類型：</span><span class="sxs-lookup"><span data-stu-id="bd54d-376">There are three types of controls:</span></span>

1. <span data-ttu-id="bd54d-377">**Microsoft 受管理的控制項：** 這些是只有 Microsoft 有責任的控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-377">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="bd54d-378">它們會顯示在 box 範本中，並由 Microsoft 新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="bd54d-378">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="bd54d-379">**客戶管理的控制項：** 這些是只有客戶具有責任的控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-379">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="bd54d-380">它們會顯示在 box 範本中，並由客戶新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="bd54d-380">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="bd54d-381">**共用管理控制措施：** 這些是在 Microsoft 與客戶之間共用責任的控制。</span><span class="sxs-lookup"><span data-stu-id="bd54d-381">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="bd54d-382">這些範本會出現在 box 範本中，並由 Microsoft 新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="bd54d-382">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="bd54d-383">客戶也可以編輯或停用 Microsoft 管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-383">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="bd54d-384">Actions 專案</span><span class="sxs-lookup"><span data-stu-id="bd54d-384">Actions Items</span></span>

<span data-ttu-id="bd54d-385">動作專案是實施標準或法規需求的建議工作，或是用來測試、驗證及記錄組織的執行需求。</span><span class="sxs-lookup"><span data-stu-id="bd54d-385">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="bd54d-386">動作與一個或多個控制項相關聯。</span><span class="sxs-lookup"><span data-stu-id="bd54d-386">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="bd54d-387">每個控制項都有一個或多個與其相關聯的動作，而且每個動作都可以與一個或多個控制項產生關聯。</span><span class="sxs-lookup"><span data-stu-id="bd54d-387">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="bd54d-388">動作是合規性管理員（預覽）中核心工作流程的一部分，因為它們是指派、追蹤及驗證組織的物件。</span><span class="sxs-lookup"><span data-stu-id="bd54d-388">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="bd54d-389">指派動作專案</span><span class="sxs-lookup"><span data-stu-id="bd54d-389">Assign Action Items</span></span>
  
1. <span data-ttu-id="bd54d-390">在 [**動作專案**] 儀表板上，選取包含要指派其動作之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-390">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="bd54d-391">在 [**評估**] 下拉式清單中，選取您要指派其動作的評估，或從下拉式清單中選取 [**全部**]，以查看所有可用的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-391">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="bd54d-392">找到您要指派的動作，然後在 [**擁有**者] 欄位中，選取要**複查**的連結、\* \* 已執行或**測試**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-392">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, \*\*Implemented, or **Test**.</span></span>
4. <span data-ttu-id="bd54d-393">選取 [**指派使用者**] 欄位，並顯示您組織中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="bd54d-393">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="bd54d-394">滾動清單並選取使用者或篩選清單，以選取使用者的名稱來選取使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-394">Scroll the list and select user or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="bd54d-395">在 [執行附注] 欄位中，輸入您想要傳遞給指派使用者的任何附注。</span><span class="sxs-lookup"><span data-stu-id="bd54d-395">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="bd54d-396">選取 [**儲存**] 以指派動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-396">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="bd54d-397">重新指派動作專案</span><span class="sxs-lookup"><span data-stu-id="bd54d-397">Reassign Action Items</span></span>

<span data-ttu-id="bd54d-398">此功能可讓組織將動作重新指派給新使用者，以移除使用者帳戶上任何使用中或尚未完成的相關性。</span><span class="sxs-lookup"><span data-stu-id="bd54d-398">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="bd54d-399">在 [**動作專案**] 儀表板上，選取包含您想要重新指派其動作之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-399">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="bd54d-400">在 [**評估**] 下拉式清單中，選取您要重新指派其動作的評估，或從下拉式清單中選取 [**全部**]，以查看所有可用的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-400">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="bd54d-401">找到您想要重新指派的動作，然後在 [**擁有**者] 欄中，選取要**複查**、**實施**或**測試**的連結。</span><span class="sxs-lookup"><span data-stu-id="bd54d-401">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="bd54d-402">從 [**指派使用者**] 欄位中刪除現有的使用者，並從使用者清單中選擇不同的使用者，或透過輸入使用者的名稱來篩選清單，以選取使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-402">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="bd54d-403">在 [執行附注] 欄位中，輸入您想要傳遞給使用者的任何附注。</span><span class="sxs-lookup"><span data-stu-id="bd54d-403">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="bd54d-404">選取 [**儲存**] 以重新指派動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-404">Select **Save** to reassign the Action.</span></span>

#### <a name="common-action-items-synch-status-across-groups"></a><span data-ttu-id="bd54d-405">不同群組的常見動作專案同步狀態</span><span class="sxs-lookup"><span data-stu-id="bd54d-405">Common Action Items synch status across Groups</span></span>

<span data-ttu-id="bd54d-406">如果您的組織有多個評估群組，則會有技術動作（也就是影響整個組織的動作）的行為。</span><span class="sxs-lookup"><span data-stu-id="bd54d-406">If your organization has multiple groups of assessments, there is a behavior of Technical actions (that is, actions affecting your entire organization).</span></span> <span data-ttu-id="bd54d-407">群組間的任何重複動作現在會合並成一個單一動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-407">Any duplicate actions across groups are now combined into one single action.</span></span> <span data-ttu-id="bd54d-408">單一巨集指令包含先前重複的版本中所有上傳的記事及證據。</span><span class="sxs-lookup"><span data-stu-id="bd54d-408">That single action contains all uploaded notes and evidence from previously duplicate versions.</span></span> <span data-ttu-id="bd54d-409">在一個群組或評估中對動作所做的任何變更，都會反映在該動作的所有實例中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-409">Any change made to the action in one group or assessment will be reflected in all instances of that action.</span></span> <span data-ttu-id="bd54d-410">「**實施狀態**」、「**實施日期**」、「**測試狀態**」及「**測試日期**」欄位會反映最新的更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-410">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** fields reflect the most recent updates.</span></span>

## <a name="templates"></a><span data-ttu-id="bd54d-411">範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-411">Templates</span></span>

<span data-ttu-id="bd54d-412">範本是合規性管理員（預覽）中與產品及認證（例如，standard、管制、控制架構等）相關聯的基礎物件。</span><span class="sxs-lookup"><span data-stu-id="bd54d-412">A Template is the base object in Compliance Manager (Preview) that is associated with a product and a certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="bd54d-413">您可以從 [**範本**] 儀表板中查看及新增範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-413">Templates can be viewed and added from the **Templates** dashboard.</span></span>

![合規性管理員 Microsoft 範本儀表板](../media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="bd54d-415">儀表板會顯示每個範本，以及與範本相關聯的憑證及產品、客戶的範本建立和上次修改的日期、客戶和 Microsoft 管理的控制項數目、範本的最大合規性分數，以及範本的狀態（例如，已核准、待定核准、匯入）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-415">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

### <a name="create-a-template"></a><span data-ttu-id="bd54d-416">建立範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-416">Create a Template</span></span>

<span data-ttu-id="bd54d-417">使用範本來建立評估的方法有三種：</span><span class="sxs-lookup"><span data-stu-id="bd54d-417">There are three ways to work with Templates to create Assessments:</span></span>

1. <span data-ttu-id="bd54d-418">使用 Microsoft 提供的預先設定的範本之一。</span><span class="sxs-lookup"><span data-stu-id="bd54d-418">Use one of the pre-configured Templates provided by Microsoft.</span></span>
2. <span data-ttu-id="bd54d-419">透過擴充程式，自訂預先設定的範本和您自己的動作和控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-419">Customize a pre-configured Template with your own actions and controls through the extension process.</span></span>
3. <span data-ttu-id="bd54d-420">建立您自己的範本，並將其匯入合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="bd54d-420">Create your own Template and import it into Compliance Manager.</span></span>

#### <a name="use-a-microsoft-pre-configured-template"></a><span data-ttu-id="bd54d-421">使用 Microsoft 預先設定的範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-421">Use a Microsoft pre-configured Template</span></span>

<span data-ttu-id="bd54d-422">預先設定的範本可在您的**範本**儀表板上使用。</span><span class="sxs-lookup"><span data-stu-id="bd54d-422">The pre-configured templates are available on your **Templates** dashboard.</span></span> <span data-ttu-id="bd54d-423">查看目前的[範本清單](compliance-manager-overview.md#templates)，該清單會在每次新的範本可用時更新。</span><span class="sxs-lookup"><span data-stu-id="bd54d-423">View the current [list of templates](compliance-manager-overview.md#templates), which is updated each time a new template is available.</span></span>

#### <a name="customize-a-template-through-the-extension-process"></a><span data-ttu-id="bd54d-424">透過擴充處理常式自訂範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-424">Customize a Template through the extension process</span></span>

1. <span data-ttu-id="bd54d-425">開啟 [**範本**] 儀表板，然後選取 [ **+ 新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-425">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="bd54d-426">在 [範本] 飛入窗格上，選取 [**從通用範本建立副檔名**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-426">On the Template flyout pane, select the **Create extension from global template** checkbox.</span></span>
3. <span data-ttu-id="bd54d-427">從下拉式功能表中選取您要擴充的範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-427">Select the template you want to extend from the drop-down menu.</span></span>
4. <span data-ttu-id="bd54d-428">若尚未在 Excel 中格式化範本資料，請選取彈出窗格中的連結，以下載 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="bd54d-428">If you have not already formatted your template data in Excel, select the link in the flyout pane to download an Excel file.</span></span> <span data-ttu-id="bd54d-429">請根據下列[Excel](#import-template-data-with-excel)指示填寫試算表，並將其儲存至您的本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="bd54d-429">Fill out the spreadsheet according to the [Import Template data with Excel](#import-template-data-with-excel) instructions below and save it to your local drive.</span></span>
5. <span data-ttu-id="bd54d-430">選取 **[流覽]** 以上傳您的 Excel 檔案，以匯入自訂的範本資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-430">Import your customized template data by selecting **Browse** to upload your Excel file.</span></span>
6. <span data-ttu-id="bd54d-431">選取 [**新增至儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-431">Select **Add to Dashboard**.</span></span> <span data-ttu-id="bd54d-432">然後您會看到新的範本新增至您的**範本**儀表板。</span><span class="sxs-lookup"><span data-stu-id="bd54d-432">You will then see your new template added to your **Templates** dashboard.</span></span>

#### <a name="create-your-own-template-and-import-it-into-compliance-manager"></a><span data-ttu-id="bd54d-433">建立您自己的範本，並將其匯入合規性管理員</span><span class="sxs-lookup"><span data-stu-id="bd54d-433">Create your own Template and import it into Compliance Manager</span></span>

1. <span data-ttu-id="bd54d-434">開啟 [**範本**] 儀表板，然後選取 [ **+ 新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-434">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="bd54d-435">在 [範本] 飛入窗格上，選取 [**建立新的範本**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-435">On the Template flyout pane, select **Create a new template**.</span></span>
3. <span data-ttu-id="bd54d-436">選取 **[流覽]** 以上傳包含資料的 Excel 檔案（請參閱下列[Excel 的匯入範本資料](#import-template-data-with-excel)），以匯入範本資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-436">Import your template data by selecting **Browse** to upload your Excel file containing the data (see [Import Template data with Excel](#import-template-data-with-excel) below).</span></span>
4. <span data-ttu-id="bd54d-437">選取 [**新增至儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-437">Select **Add to Dashboard**.</span></span> <span data-ttu-id="bd54d-438">然後您會看到新的範本新增至您的**範本**儀表板。</span><span class="sxs-lookup"><span data-stu-id="bd54d-438">You will then see your new template added to your **Templates** dashboard.</span></span>

#### <a name="import-template-data-with-excel"></a><span data-ttu-id="bd54d-439">使用 Excel 匯入範本資料</span><span class="sxs-lookup"><span data-stu-id="bd54d-439">Import Template data with Excel</span></span>

<span data-ttu-id="bd54d-440">若要修改範本或建立您自己的範本，您會使用[Excel 試算表](https://go.microsoft.com/fwlink/?linkid=2124865)來捕獲必要的資料，並將其上傳到合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="bd54d-440">To modify a template or create your own template, you'll use an [Excel spreadsheet](https://go.microsoft.com/fwlink/?linkid=2124865) to capture the necessary data and upload it to Compliance Manager.</span></span> <span data-ttu-id="bd54d-441">這個試算表範本具有必須使用的特定格式和架構，否則將不會匯入至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="bd54d-441">This spreadsheet template has a specific format and schema that must be used or it will not import into Compliance Manager.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd54d-442">如果您先前已在合規性管理員中建立或自訂範本，此程式會在2020年4月的合規性管理員（預覽）版本中**更新**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-442">If you've created or customized templates in Compliance Manager before, **this process has been updated** as part of the April 2020 release of Compliance Manager (Preview).</span></span> <span data-ttu-id="bd54d-443">**請仔細閱讀本節。**</span><span class="sxs-lookup"><span data-stu-id="bd54d-443">**Please review this section carefully.**</span></span>

<span data-ttu-id="bd54d-444">試算表包含四個選項卡，其中三個是必要的：</span><span class="sxs-lookup"><span data-stu-id="bd54d-444">The spreadsheet contains four tabs, three of which are required:</span></span>

1. <span data-ttu-id="bd54d-445">範本（必要）</span><span class="sxs-lookup"><span data-stu-id="bd54d-445">Template (required)</span></span>
2. <span data-ttu-id="bd54d-446">ControlFamily （必要）</span><span class="sxs-lookup"><span data-stu-id="bd54d-446">ControlFamily (required)</span></span>
3. <span data-ttu-id="bd54d-447">動作（必要）</span><span class="sxs-lookup"><span data-stu-id="bd54d-447">Actions (required)</span></span>
4. <span data-ttu-id="bd54d-448">維度（選用）</span><span class="sxs-lookup"><span data-stu-id="bd54d-448">Dimensions (optional)</span></span>

<span data-ttu-id="bd54d-449">您的試算表**必須依此順序包含**索引標籤，否則您的資料將無法成功匯入至範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-449">Your spreadsheet **must include the tabs in this order**, otherwise your data won't successfully import to a template.</span></span>

##### <a name="template-tab"></a><span data-ttu-id="bd54d-450">範本] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="bd54d-450">Template tab</span></span>

<span data-ttu-id="bd54d-451">[**範本**] 索引標籤是必要的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-451">The **Template** tab is required.</span></span> <span data-ttu-id="bd54d-452">此索引標籤中的資訊提供範本的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-452">The information in this tab provides metadata about the template.</span></span> <span data-ttu-id="bd54d-453">有四個必要的欄。</span><span class="sxs-lookup"><span data-stu-id="bd54d-453">There are four required columns.</span></span> <span data-ttu-id="bd54d-454">欄必須保留在 Excel 工作表上如下所列的順序。</span><span class="sxs-lookup"><span data-stu-id="bd54d-454">The columns must retain the order on the Excel sheet as listed below.</span></span> <span data-ttu-id="bd54d-455">您可以在四欄**後**新增您自己的欄，以提供您自己的維度。</span><span class="sxs-lookup"><span data-stu-id="bd54d-455">You can add your own column **after** the four columns to provide your own dimensions.</span></span> <span data-ttu-id="bd54d-456">如果您這麼做，請務必使用[下列指示](#dimensions-tab)將其新增至 [**維度**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bd54d-456">If you do this, be sure to add them to the **Dimensions** tab using the [instructions below](#dimensions-tab).</span></span>

- <span data-ttu-id="bd54d-457">**職稱**：這是範本的標題，必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-457">**title**: This is the title for your template, which must be unique.</span></span> <span data-ttu-id="bd54d-458">您可以在合規性管理員中與其他範本共用名稱稱，不論它是您已建立的範本，還是由 Microsoft 提供的預先設定的範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-458">It can't share a name with another template you have in Compliance Manager, whether it's a template you already created, or a pre-configured template provided by Microsoft.</span></span>

- <span data-ttu-id="bd54d-459">**產品**：這是必要的維度。</span><span class="sxs-lookup"><span data-stu-id="bd54d-459">**product**: This is a required dimension.</span></span> <span data-ttu-id="bd54d-460">列出與範本相關聯的產品。</span><span class="sxs-lookup"><span data-stu-id="bd54d-460">List the product associated with the template.</span></span>

- <span data-ttu-id="bd54d-461">**認證**：這是您用來做為範本的規章。</span><span class="sxs-lookup"><span data-stu-id="bd54d-461">**certification**: This is the regulation you're using for the template.</span></span>

- <span data-ttu-id="bd54d-462">**inScopeServices**：這些是此項評估所定址之產品中的服務（例如，如果您列為 Office 365 做為產品，則 Microsoft 團隊可能是一個範圍內的服務）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-462">**inScopeServices**: These are the services within the product that this assessment addresses (for example, if you listed Office 365 as the product, Microsoft Teams could be an in-scope service).</span></span> <span data-ttu-id="bd54d-463">您可以列出多個以兩個分號分隔的服務。</span><span class="sxs-lookup"><span data-stu-id="bd54d-463">You can list multiple services separated by two semi-colons.</span></span>

> [!NOTE]
> <span data-ttu-id="bd54d-464">關於產品和憑證：在您匯入試算表以建立或自訂範本之後，您在 [**產品**] 和 [憑證 **] 儲存格中**插入的資料將無法編輯。</span><span class="sxs-lookup"><span data-stu-id="bd54d-464">Regarding product and certification: The data you insert in the **product** and **certification** cells cannot be edited after you import the spreadsheet to create or customize a template.</span></span> <span data-ttu-id="bd54d-465">此外，群組不能包含兩個具有相同**產品/認證**組合的評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-465">Also, a group cannot contain two assessments that have the same **product/certification** combination.</span></span> <span data-ttu-id="bd54d-466">您可以有多個範本具有相同的產品/認證組合。</span><span class="sxs-lookup"><span data-stu-id="bd54d-466">You can have multiple templates that have the same product/certification combination.</span></span>

##### <a name="controlfamily-tab"></a><span data-ttu-id="bd54d-467">ControlFamily] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="bd54d-467">ControlFamily tab</span></span>

<span data-ttu-id="bd54d-468">[ **ControlFamily** ] 索引標籤是必要的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-468">The **ControlFamily** tab is required.</span></span>  <span data-ttu-id="bd54d-469">此索引標籤中的必要欄（必須遵循範例試算表中提供的順序）為：</span><span class="sxs-lookup"><span data-stu-id="bd54d-469">The required columns in this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="bd54d-470">**controlName**：這是來自憑證、標準或法規（通常是某些類型的 ID）的控制項名稱。</span><span class="sxs-lookup"><span data-stu-id="bd54d-470">**controlName**: This is the control name from the certification, standard, or regulation, which is typically some type of ID.</span></span> <span data-ttu-id="bd54d-471">控制項名稱在範本內必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-471">Control names must be unique within a template.</span></span> <span data-ttu-id="bd54d-472">試算表中不可以有多個具有相同名稱的控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-472">You can't have multiple controls with the same name in the spreadsheet.</span></span>

- <span data-ttu-id="bd54d-473">**controlFamily**：提供 controlFamily 的單字或片語，它會識別控制項的廣泛群組。</span><span class="sxs-lookup"><span data-stu-id="bd54d-473">**controlFamily**: Provide a word or phrase for the controlFamily, which identifies a broad grouping of controls.</span></span> <span data-ttu-id="bd54d-474">ControlFamily 不必是唯一的;它可以在試算表中列出一次以上。</span><span class="sxs-lookup"><span data-stu-id="bd54d-474">A controlFamily doesn't have to be unique; it can be listed more than once in a spreadsheet.</span></span> <span data-ttu-id="bd54d-475">同一個 controlFamily 也可以列于多個範本中，但彼此之間彼此沒有關系。</span><span class="sxs-lookup"><span data-stu-id="bd54d-475">The same controlFamily can also be listed in multiple templates, though they have no relation to each other.</span></span> <span data-ttu-id="bd54d-476">每個 controlFamily 都必須對應至至少一個控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-476">Every controlFamily must be mapped to at least one control.</span></span>

- <span data-ttu-id="bd54d-477">**controlTitle**：提供控制項的標題。</span><span class="sxs-lookup"><span data-stu-id="bd54d-477">**controlTitle**: Provide a title for the control.</span></span> <span data-ttu-id="bd54d-478">雖然 controlName 是參考碼，但標題是一般會出現在規章中的 rtf 文字格式。</span><span class="sxs-lookup"><span data-stu-id="bd54d-478">Whereas the controlName is a reference code, the title is a rich text format typically seen in the regulations.</span></span>

- <span data-ttu-id="bd54d-479">**controlDescription**：提供控制項的描述。</span><span class="sxs-lookup"><span data-stu-id="bd54d-479">**controlDescription**: Provide a description of the control.</span></span>

- <span data-ttu-id="bd54d-480">**controlActionTitle**：這是您想要與此控制項相關之動作的標題。</span><span class="sxs-lookup"><span data-stu-id="bd54d-480">**controlActionTitle**: This is the title of an action that you want to relate to this control.</span></span> <span data-ttu-id="bd54d-481">您可以新增多個分號，並以兩個分號隔開，中間沒有空格。</span><span class="sxs-lookup"><span data-stu-id="bd54d-481">You can add multiple actions by separating by two semi-colons with no space in between.</span></span> <span data-ttu-id="bd54d-482">您清單中的每個控制項都必須至少包含一個動作，且該動作必須存在（這表示您可以在相同試算表的 [**動作**] 索引標籤上列出的動作，也就是 Microsoft 所建立的動作）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-482">Every control you list must include at least one action, and the action must exist (which means you can list an action that you list on the **Actions** tab of the same spreadsheet, an action that exists in a different template, or an action created by Microsoft).</span></span> <span data-ttu-id="bd54d-483">不同的控制項可以參照相同的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-483">Different controls can reference the same action.</span></span>

##### <a name="actions-tab"></a><span data-ttu-id="bd54d-484">動作] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="bd54d-484">Actions tab</span></span>

<span data-ttu-id="bd54d-485">[**動作**] 索引標籤是必要的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-485">The **Actions** tab is required.</span></span>  <span data-ttu-id="bd54d-486">它會指定您組織的動作，而不是 Microsoft 的動作，該動作已存在於合規性管理員中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-486">It designates actions of your organization and not the actions of Microsoft, which already exist in Compliance Manager.</span></span> <span data-ttu-id="bd54d-487">此索引標籤的必要欄（必須遵循範例試算表中提供的順序）為：</span><span class="sxs-lookup"><span data-stu-id="bd54d-487">The required columns for this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="bd54d-488">**actionTitle**：這是您動作的標題，而且是必要的欄位。</span><span class="sxs-lookup"><span data-stu-id="bd54d-488">**actionTitle**: This is the title for your action and is a required field.</span></span> <span data-ttu-id="bd54d-489">您提供的標題必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-489">The title you provide must be unique.</span></span> <span data-ttu-id="bd54d-490">**重要**：如果您參考的是已存在的動作（例如另一個範本），並在後續欄中修改其任何元素，這些變更將會傳播至其他範本中的相同動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-490">**Important**: if you reference an action you own that already exists (such as in another template) and you modify any of its elements in the subsequent columns, those changes will propagate to the same action in other templates.</span></span>

- <span data-ttu-id="bd54d-491">**implementationType**：在此必要欄位中，列出下列三種實施類型之一：</span><span class="sxs-lookup"><span data-stu-id="bd54d-491">**implementationType**: In this required field, list one of the three implementation types below:</span></span>
    - <span data-ttu-id="bd54d-492">**操作**-由人員和程式所執行的動作，以保護組織系統、資產、資料和人員的機密性、完整性和可用性（範例：安全性意識和訓練）</span><span class="sxs-lookup"><span data-stu-id="bd54d-492">**Operational** - actions implemented by people and processes to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: security awareness and training)</span></span>
    - <span data-ttu-id="bd54d-493">**技術**-透過使用資訊系統的硬體、軟體或固件元件所包含的技術和機制完成的動作，以保護組織系統和資料的機密性、完整性和可用性（範例：多重要素驗證）</span><span class="sxs-lookup"><span data-stu-id="bd54d-493">**Technical** - actions completed through the use of technology and mechanisms contained in the hardware, software, or firmware components of the information system to protect the confidentiality, integrity, and availability of organizational systems and data (example: multi-factor authentication)</span></span>
    - <span data-ttu-id="bd54d-494">**檔**-透過記錄的原則及程式所實施的動作，建立及定義保護組織系統、資產、資料和人員的機密性、完整性和可用性所需的控制項（範例：資訊安全性原則）</span><span class="sxs-lookup"><span data-stu-id="bd54d-494">**Documentation** - actions implemented through documented policies and procedures establishing and defining the controls required to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: an information security policy)</span></span>

- <span data-ttu-id="bd54d-495">**actionScore**：在這個必要的欄位中，為您的動作提供數值分數值。</span><span class="sxs-lookup"><span data-stu-id="bd54d-495">**actionScore**: In this required field, provide a numeric score value for your action.</span></span> <span data-ttu-id="bd54d-496">它必須是介於1到99的整數。它不得為0、null 或空白。</span><span class="sxs-lookup"><span data-stu-id="bd54d-496">It must be a whole number ranging from 1 to 99; it cannot be 0, null, or blank.</span></span> <span data-ttu-id="bd54d-497">數位越高，其價值越高，以改善您的相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="bd54d-497">The higher the number, the greater its value toward improving your compliance posture.</span></span> <span data-ttu-id="bd54d-498">如需相關指引，請參閱 Microsoft 如何評分其控制項：</span><span class="sxs-lookup"><span data-stu-id="bd54d-498">For guidance, see below how Microsoft scores its controls:</span></span>

<span data-ttu-id="bd54d-499">![合規性管理員控制點值](../media/compliance-score-controls-scoring.png "合規性管理員控制點值")</span><span class="sxs-lookup"><span data-stu-id="bd54d-499">![Compliance Manager controls point values](../media/compliance-score-controls-scoring.png "Compliance Manager controls point values")</span></span>

- <span data-ttu-id="bd54d-500">**actionDescriptionTitle**：這是描述的標題，而且是必要專案。</span><span class="sxs-lookup"><span data-stu-id="bd54d-500">**actionDescriptionTitle**: This is the title of the description and is required.</span></span> <span data-ttu-id="bd54d-501">此描述標題可讓您在多個範本中使用相同的動作，並在每個範本中呈現不同的描述。</span><span class="sxs-lookup"><span data-stu-id="bd54d-501">This description title allows you to have the same action in multiple templates and surface a different description in each template.</span></span>  <span data-ttu-id="bd54d-502">此欄位可協助您澄清描述所參照的範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-502">This field helps you clarify what template the description is referencing.</span></span> <span data-ttu-id="bd54d-503">在大多數情況下，您可以在此欄位中放置您建立的範本名稱。</span><span class="sxs-lookup"><span data-stu-id="bd54d-503">In most cases, you can put the name of the template you're creating in this field.</span></span>

- <span data-ttu-id="bd54d-504">**actionDescription**：提供動作的描述。</span><span class="sxs-lookup"><span data-stu-id="bd54d-504">**actionDescription**: Provide a description of the action.</span></span> <span data-ttu-id="bd54d-505">您可以套用粗體文字和超連結等格式。</span><span class="sxs-lookup"><span data-stu-id="bd54d-505">You can apply formatting such as bold text and hyperlinks.</span></span> <span data-ttu-id="bd54d-506">這是必要欄位。</span><span class="sxs-lookup"><span data-stu-id="bd54d-506">This is required field.</span></span>

- <span data-ttu-id="bd54d-507">**維度-動作目的**：這是選用的欄位。</span><span class="sxs-lookup"><span data-stu-id="bd54d-507">**dimension-Action Purpose**: This is an optional field.</span></span> <span data-ttu-id="bd54d-508">如果包含此標頭，則標頭必須包含 "dimension" 前置詞。</span><span class="sxs-lookup"><span data-stu-id="bd54d-508">If you include it, the header must include the "dimension-" prefix.</span></span> <span data-ttu-id="bd54d-509">您將在此處包含的任何維度，都將做為[符合性分數中的篩選器](compliance-score-setup.md#filtering-your-dashboard-view)，並顯示在[合規性分數的「改進動作詳細資料」頁面](working-with-compliance-score.md#view-your-improvement-actions)</span><span class="sxs-lookup"><span data-stu-id="bd54d-509">Any dimensions you include here will be used as [filters in Compliance Score](compliance-score-setup.md#filtering-your-dashboard-view) and appear on the [improvement actions details page in Compliance Score](working-with-compliance-score.md#view-your-improvement-actions).</span></span>

##### <a name="dimensions-tab"></a><span data-ttu-id="bd54d-510">維度] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="bd54d-510">Dimensions tab</span></span>

<span data-ttu-id="bd54d-511">[**維度**] 索引標籤是選用的。</span><span class="sxs-lookup"><span data-stu-id="bd54d-511">The **Dimensions** tab is optional.</span></span> <span data-ttu-id="bd54d-512">不過，如果您在其他位置參照維度，但如果它不存在於您已建立的範本或在 Microsoft 範本中，則需要在這裡加以指定。</span><span class="sxs-lookup"><span data-stu-id="bd54d-512">However, if you reference a dimension elsewhere, you need to specify it here if it does not exist in a template you've already created or in a Microsoft template.</span></span> <span data-ttu-id="bd54d-513">此索引標籤的欄如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd54d-513">The columns for this tab are listed below:</span></span>

- <span data-ttu-id="bd54d-514">**dimensionKey**：清單為 "product"，"認證，" 「動作目的」</span><span class="sxs-lookup"><span data-stu-id="bd54d-514">**dimensionKey**: list as "product", "certifications," "action purpose"</span></span>
- <span data-ttu-id="bd54d-515">**dimensionValue**：範例： Office 365、HIPPA、預防性、偵探</span><span class="sxs-lookup"><span data-stu-id="bd54d-515">**dimensionValue**: examples: Office 365, HIPPA, Preventative, Detective</span></span>

<span data-ttu-id="bd54d-516">您可以前往**租使用者管理**，然後選取 [**維度**] 索引標籤，以查看現有的維度。此外，當您匯出現有的範本時，匯出的試算表會有 [**維度**] 索引標籤，該索引標籤會列出範本中所用的所有維度。</span><span class="sxs-lookup"><span data-stu-id="bd54d-516">You can view your existing dimensions by going to **Tenant Management** and selecting the **Dimensions** tab. Also, anytime you export an existing template, the exported spreadsheet will have the **Dimensions** tab, which lists all the dimensions used in the template.</span></span>

### <a name="modify-an-existing-template"></a><span data-ttu-id="bd54d-517">修改現有範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-517">Modify an existing Template</span></span>

<span data-ttu-id="bd54d-518">若要使用以上所述的匯入程式，對您建立或自訂的範本進行變更，您可以使用相同的程式，將這些變更匯入至您的範本。</span><span class="sxs-lookup"><span data-stu-id="bd54d-518">To make changes to a Template you created or customized using the import process outlined above, you use the same process to import those changes into your Template.</span></span>

> [!NOTE]
> <span data-ttu-id="bd54d-519">編輯範本元件時，請注意許多重要因素，因此請仔細閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="bd54d-519">There are several important factors to be aware of as you edit template components, so please review this section carefully.</span></span>

#### <a name="general-process-for-modifying-a-template"></a><span data-ttu-id="bd54d-520">修改範本的一般程式</span><span class="sxs-lookup"><span data-stu-id="bd54d-520">General process for modifying a Template</span></span>

<span data-ttu-id="bd54d-521">若要變更組織的現有範本之一，一般處理常式如下：</span><span class="sxs-lookup"><span data-stu-id="bd54d-521">To make changes to one of your organization's existing templates, the general process is:</span></span>

1. <span data-ttu-id="bd54d-522">從您的**範本**儀表板中，選取您要修改的範本，它會彈出您的 [**控制項資訊**] 儀表板，顯示**範本**索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bd54d-522">From your **Templates** dashboard, select the Template you want to modify, which brings up your **Controls Info** dashboard showing your **Template** tab.</span></span>
2. <span data-ttu-id="bd54d-523">從這裡，選取 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-523">From here, select **Export**.</span></span> <span data-ttu-id="bd54d-524">將下載所有範本資料的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="bd54d-524">An Excel sheet with all your template data will download.</span></span>
3. <span data-ttu-id="bd54d-525">若要編輯、新增或移除動作，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="bd54d-525">To edit, add, or remove an action, see the sections below.</span></span>
4. <span data-ttu-id="bd54d-526">當您完成 Excel 檔案的變更後，請從儀表板選取範本，然後選取 [匯入]，將檔案匯入**範本。**</span><span class="sxs-lookup"><span data-stu-id="bd54d-526">When you're done making changes to your Excel file, import the file back into the template by selecting the template from your dashboard and selecting **Import**.</span></span> <span data-ttu-id="bd54d-527">您的範本現在會包含您所做的變更。</span><span class="sxs-lookup"><span data-stu-id="bd54d-527">Your template will now include the changes you made.</span></span>

#### <a name="to-edit-template-attributes"></a><span data-ttu-id="bd54d-528">編輯範本屬性</span><span class="sxs-lookup"><span data-stu-id="bd54d-528">To edit Template attributes</span></span>

<span data-ttu-id="bd54d-529">在 [**範本**] 索引標籤上，您可以編輯 [**標題**] 欄中的任何專案、[ **inScopeServices** ] 欄，以及您可能新增的任何其他欄位。</span><span class="sxs-lookup"><span data-stu-id="bd54d-529">On the **Templates** tab, you can edit anything in the **title** column, the **inScopeServices** column, and in any other column you may have added.</span></span> <span data-ttu-id="bd54d-530">不過，您無法在 [**產品**] 或 [**認證**] 欄中編輯任何專案。</span><span class="sxs-lookup"><span data-stu-id="bd54d-530">However, you can't edit anything in the **product** or **certification** columns.</span></span>

#### <a name="to-add-an-action-to-a-template"></a><span data-ttu-id="bd54d-531">若要將動作新增至範本</span><span class="sxs-lookup"><span data-stu-id="bd54d-531">To add an action to a Template</span></span>

1. <span data-ttu-id="bd54d-532">移至 [**動作**] 索引標籤，並將您的資訊新增至現有動作下方第一個空白列的必要欄位中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-532">Go to the **Actions** tab and add your information in the required fields in the first empty row underneath your existing actions.</span></span>
2. <span data-ttu-id="bd54d-533">移至 [ **ControlFamily** ] 索引標籤。找到包含您動作所對應之控制項的列。</span><span class="sxs-lookup"><span data-stu-id="bd54d-533">Go to your **ControlFamily** tab. Find the row containing the control your action maps to.</span></span> <span data-ttu-id="bd54d-534">將您的新動作新增至該資料列中的 [ **controlActionTitle** ] 欄（請記得在此欄位中分隔多個動作，並使用兩個分號，其間沒有間距）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-534">Add your new action to the **controlActionTitle** column in that row (remember to separate multiple actions in this field with two semi-colons, no space in between).</span></span>
3. <span data-ttu-id="bd54d-535">將試算表儲存至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="bd54d-535">Save your spreadsheet to your local machine.</span></span>

#### <a name="to-edit-an-actions-information"></a><span data-ttu-id="bd54d-536">編輯動作的資訊</span><span class="sxs-lookup"><span data-stu-id="bd54d-536">To edit an action's information</span></span>

<span data-ttu-id="bd54d-537">您可以變更*其標題以外*的任何動作的資訊。</span><span class="sxs-lookup"><span data-stu-id="bd54d-537">You can change any action's information *except for its title*.</span></span> <span data-ttu-id="bd54d-538">您可以編輯來自 B + + 的任何儲存格，當您將檔案重新匯入範本時，該範本中的動作現在會包含更新的資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-538">You can edit any cell from columns B onward, and when you import the file back into the template, the actions in that template will now contain the updated data.</span></span>

<span data-ttu-id="bd54d-539">您無法編輯**actionTitle** （A 欄），因為如果您這麼做，合規性管理員會將此項視為新的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-539">You cannot edit the **actionTitle** (column A) because if you do, Compliance Manager considers this to be a new action.</span></span> <span data-ttu-id="bd54d-540">如果您想要變更動作的名稱，請參閱下列直接的指示。</span><span class="sxs-lookup"><span data-stu-id="bd54d-540">If you want to change an action's name, see the instructions immediately below.</span></span>

#### <a name="to-change-the-name-of-an-action"></a><span data-ttu-id="bd54d-541">變更動作名稱</span><span class="sxs-lookup"><span data-stu-id="bd54d-541">To change the name of an action</span></span>

<span data-ttu-id="bd54d-542">如果您想要變更動作名稱，您必須在試算表中明確指定您要以新名稱取代現有名稱。</span><span class="sxs-lookup"><span data-stu-id="bd54d-542">If you want to change the name of an action, you have to explicitly designate in the spreadsheet that you are replacing an existing name with a new name.</span></span> <span data-ttu-id="bd54d-543">若要變更動作的名稱，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bd54d-543">To change an action's name, follow these steps:</span></span>

1. <span data-ttu-id="bd54d-544">在試算表的 [**動作**] 索引標籤中，將新欄新增至 a 欄後的試算表中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-544">In the **Actions** tab of your spreadsheet, add a new column to the spreadsheet after column A.</span></span>
2. <span data-ttu-id="bd54d-545">在這個新欄中（現在是 B 欄），置於第1列： **oldActionTitle**中的標題。</span><span class="sxs-lookup"><span data-stu-id="bd54d-545">In this new column, which is now column B, put as its header in row 1: **oldActionTitle**.</span></span>
3. <span data-ttu-id="bd54d-546">複製欄 A 的內容，並將其貼到 B 欄中。這會將您現有的動作標題（即您想變更的專案）放入 B 欄中。</span><span class="sxs-lookup"><span data-stu-id="bd54d-546">Copy the contents of column A and paste them into column B. This puts your existing action titles, which are what you want to change, into column B.</span></span>
4. <span data-ttu-id="bd54d-547">在 [欄位 A] 中， **actionTitle**] 刪除舊名稱，並以新名稱取代為您的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-547">In column A, **actionTitle**, delete the old name and replace it with the new name for your action.</span></span>

#### <a name="to-remove-an-action-from-a-template"></a><span data-ttu-id="bd54d-548">移除範本中的動作</span><span class="sxs-lookup"><span data-stu-id="bd54d-548">To remove an action from a Template</span></span>

<span data-ttu-id="bd54d-549">從試算表中刪除某列的動作，**並不會**從您正在編輯的範本中移除動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-549">Deleting an action from a row in a spreadsheet **does not** remove the action from the template you're editing.</span></span> <span data-ttu-id="bd54d-550">相反地，請遵循下列程式移除動作：</span><span class="sxs-lookup"><span data-stu-id="bd54d-550">Instead, follow the process below to remove an action:</span></span>

1. <span data-ttu-id="bd54d-551">在 [**動作**] 索引標籤上，插入新欄做為 a 欄位，並將**作業放在**標題列中，也就是第一個資料行。</span><span class="sxs-lookup"><span data-stu-id="bd54d-551">On the **Actions** tab, insert a new column as column A and put **Operation** in the header row, which is row number one.</span></span>
2. <span data-ttu-id="bd54d-552">在您要移除之動作的列上，在該列的 A 欄中將**Delete**放入該資料行。</span><span class="sxs-lookup"><span data-stu-id="bd54d-552">On the row for the action you want to remove, put **Delete** in column A for that row.</span></span>
3. <span data-ttu-id="bd54d-553">請確定此巨集指令不再是控制項的參照。</span><span class="sxs-lookup"><span data-stu-id="bd54d-553">Ensure that this action is no longer referenced by a control.</span></span> <span data-ttu-id="bd54d-554">移至 [ **ControlFamily** ] 索引標籤，並在 F 欄中尋找動作的標題，也就是**controlActionTitle**。</span><span class="sxs-lookup"><span data-stu-id="bd54d-554">Go to the **ControlFamily** tab and look for your action's title in column F, which is **controlActionTitle**.</span></span>
4. <span data-ttu-id="bd54d-555">當您找到您列在 [ **controlActionTitle** ] 欄中的動作時，請加以刪除。</span><span class="sxs-lookup"><span data-stu-id="bd54d-555">When you find your action listed in the **controlActionTitle** column, delete it.</span></span>
5. <span data-ttu-id="bd54d-556">將試算表儲存至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="bd54d-556">Save your spreadsheet to your local machine.</span></span>

<span data-ttu-id="bd54d-557">當您將試算表重新匯入範本時，您的動作將會從範本移除。</span><span class="sxs-lookup"><span data-stu-id="bd54d-557">When you import your spreadsheet back into the template, your action will be removed from the template.</span></span> <span data-ttu-id="bd54d-558">從範本移除動作不會完全移除動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-558">Removing an action from a template does not completely remove the action.</span></span> <span data-ttu-id="bd54d-559">該動作仍可由另一個範本參照。</span><span class="sxs-lookup"><span data-stu-id="bd54d-559">That action can still be referenced by another template.</span></span>

<span data-ttu-id="bd54d-560">如果您要移除控制項所參照的最後一個動作，您必須移除該控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-560">If you are removing the last action that a control references, then you need to remove the control.</span></span>

> [!NOTE]
> <span data-ttu-id="bd54d-561">若要移除控制項：請遵循相同的程式移除如上所述的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-561">To remove a control: Follow the same process for removing an action as outlined above.</span></span> <span data-ttu-id="bd54d-562">在 [ **ControlFamily** ] 索引標籤中，新增 [作業 **] 欄，** 並將 [**刪除**] 放在您要移除的控制項旁。</span><span class="sxs-lookup"><span data-stu-id="bd54d-562">In the **ControlFamily** tab, add an **Operation** column and put **Delete** next to the control you want to remove.</span></span>

### <a name="updates-to-templates"></a><span data-ttu-id="bd54d-563">範本的更新</span><span class="sxs-lookup"><span data-stu-id="bd54d-563">Updates to Templates</span></span>

<span data-ttu-id="bd54d-564">每次透過版本設定程式更新評估時，您的自訂評估會繼承這些更新，並保留您的自訂控制項。</span><span class="sxs-lookup"><span data-stu-id="bd54d-564">Each time an Assessment is updated through the versioning process, your customized Assessment will inherit those updates and keep your custom controls.</span></span> <span data-ttu-id="bd54d-565">請參閱「[評估更新的版本設定警示](#versioning-alerts-for-assessment-updates)」。</span><span class="sxs-lookup"><span data-stu-id="bd54d-565">See [Versioning alerts for Assessment updates](#versioning-alerts-for-assessment-updates).</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="bd54d-566">將範本匯出至 JSON</span><span class="sxs-lookup"><span data-stu-id="bd54d-566">Export a Template to JSON</span></span>

<span data-ttu-id="bd54d-567">合規性管理員（預覽）支援將範本匯出為 JavaScript 物件標記法（JSON）格式。</span><span class="sxs-lookup"><span data-stu-id="bd54d-567">Compliance Manager (Preview) supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="bd54d-568">這可讓您將合規性管理員資料與其他支援 JSON 的系統交換。</span><span class="sxs-lookup"><span data-stu-id="bd54d-568">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="bd54d-569">報告</span><span class="sxs-lookup"><span data-stu-id="bd54d-569">Reports</span></span>

<span data-ttu-id="bd54d-570">您可以將評估匯出至您組織中或外部審計員和主管的符合性專案關係人的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="bd54d-570">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="bd54d-571">報表是指匯出之日期和時間為止的評估快照。</span><span class="sxs-lookup"><span data-stu-id="bd54d-571">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="bd54d-572">報告包含 Microsoft 及客戶管理控制項的詳細資料，以供評估、控制執行狀態、控制測試日期、測試結果和上傳的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="bd54d-572">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="bd54d-573">因為隱藏評估未保留上載檔的連結，所以您應該先匯出評估，再將其隱藏。</span><span class="sxs-lookup"><span data-stu-id="bd54d-573">Because hidden Assessments don't retain links to uploaded documents, you should export the Assessment before you hide it.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="bd54d-574">匯出評估</span><span class="sxs-lookup"><span data-stu-id="bd54d-574">Export an Assessment</span></span>

1. <span data-ttu-id="bd54d-575">在 [合規性管理員] 儀表板上，選取 [**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bd54d-575">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="bd54d-576">在下拉式功能表中，選取您要匯出之評估的群組和評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-576">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="bd54d-577">選取 [匯出]。</span><span class="sxs-lookup"><span data-stu-id="bd54d-577">Select Export.</span></span> <span data-ttu-id="bd54d-578">評估匯出會下載成 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="bd54d-578">The Assessment export is downloaded as an Excel file.</span></span>

<span data-ttu-id="bd54d-579">![合規性管理員評估 Excel 報告](../media/compliance-manager-assessment-report.png "合規性管理員評估 Excel 報告")</span><span class="sxs-lookup"><span data-stu-id="bd54d-579">![Compliance Manager Assessment Excel Report](../media/compliance-manager-assessment-report.png "Compliance Manager assessment Excel report")</span></span>

## <a name="permissions"></a><span data-ttu-id="bd54d-580">權限</span><span class="sxs-lookup"><span data-stu-id="bd54d-580">Permissions</span></span>

<span data-ttu-id="bd54d-581">下表說明每個合規性管理員許可權及其允許使用者執行的動作。</span><span class="sxs-lookup"><span data-stu-id="bd54d-581">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="bd54d-582">該表也會指出指派每個許可權的角色。</span><span class="sxs-lookup"><span data-stu-id="bd54d-582">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="bd54d-583">**Azure AD 全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="bd54d-583">**Azure AD Global Reader**</span></span>|<span data-ttu-id="bd54d-584">**合規性管理員讀取者**</span><span class="sxs-lookup"><span data-stu-id="bd54d-584">**Compliance Manager Reader**</span></span>|<span data-ttu-id="bd54d-585">**合規性參與者**</span><span class="sxs-lookup"><span data-stu-id="bd54d-585">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="bd54d-586">**合規性管理員評估者**</span><span class="sxs-lookup"><span data-stu-id="bd54d-586">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="bd54d-587">**合規性管理員管理者**</span><span class="sxs-lookup"><span data-stu-id="bd54d-587">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="bd54d-588">**入口網站管理員**</span><span class="sxs-lookup"><span data-stu-id="bd54d-588">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd54d-589">**讀取資料：** 使用者可以讀取但不能編輯資料（範本資料和租使用者管理除外）。</span><span class="sxs-lookup"><span data-stu-id="bd54d-589">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="bd54d-590">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-590">X</span></span> | <span data-ttu-id="bd54d-591">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-591">X</span></span> | <span data-ttu-id="bd54d-592">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-592">X</span></span> | <span data-ttu-id="bd54d-593">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-593">X</span></span> | <span data-ttu-id="bd54d-594">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-594">X</span></span>  | <span data-ttu-id="bd54d-595">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-595">X</span></span> |
|<span data-ttu-id="bd54d-596">**編輯資料：** 除了 [測試結果] 和 [測試日期] 欄位（範本資料和租使用者管理以外）以外，使用者可以編輯所有欄位。</span><span class="sxs-lookup"><span data-stu-id="bd54d-596">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="bd54d-597">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-597">X</span></span> | <span data-ttu-id="bd54d-598">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-598">X</span></span>  | <span data-ttu-id="bd54d-599">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-599">X</span></span> | <span data-ttu-id="bd54d-600">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-600">X</span></span> |
|<span data-ttu-id="bd54d-601">**編輯測試結果：** 使用者可以編輯 [測試結果] 和 [測試日期] 欄位。</span><span class="sxs-lookup"><span data-stu-id="bd54d-601">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="bd54d-602">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-602">X</span></span> | <span data-ttu-id="bd54d-603">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-603">X</span></span> | <span data-ttu-id="bd54d-604">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-604">X</span></span> |
|<span data-ttu-id="bd54d-605">**管理評估：** 使用者可以建立、封存和刪除評估。</span><span class="sxs-lookup"><span data-stu-id="bd54d-605">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="bd54d-606">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-606">X</span></span> | <span data-ttu-id="bd54d-607">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-607">X</span></span> |
|<span data-ttu-id="bd54d-608">**管理主資料：** 使用者可以查看、編輯和刪除範本資料及承租人管理資料。</span><span class="sxs-lookup"><span data-stu-id="bd54d-608">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="bd54d-609">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-609">X</span></span> | <span data-ttu-id="bd54d-610">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-610">X</span></span> |
|<span data-ttu-id="bd54d-611">**管理使用者：** 使用者可以將組織中的其他使用者新增至讀者、投稿人、Assessor 及系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="bd54d-611">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="bd54d-612">只有在您組織中具有全域系統管理員角色的使用者，才可以從入口網站管理員角色新增或移除使用者。</span><span class="sxs-lookup"><span data-stu-id="bd54d-612">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="bd54d-613">X</span><span class="sxs-lookup"><span data-stu-id="bd54d-613">X</span></span> |