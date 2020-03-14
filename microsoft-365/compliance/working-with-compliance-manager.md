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
description: Microsoft 合規性管理員是 Microsoft 服務信任入口網站中免費的工作流程型風險評估工具。 合規性管理員可讓您追蹤、指派及驗證 Microsoft 產品相關的規章遵循活動。
ms.openlocfilehash: a0cdabdc37779ee2f7624242eeb177f3d35b87da
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634131"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="75fb2-104">與 Microsoft 合規性管理員合作（預覽）</span><span class="sxs-lookup"><span data-stu-id="75fb2-104">Work with Microsoft Compliance Manager (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75fb2-105">Microsoft 合規性管理員是一種儀表板和管理工具，可提供您的資料保護和合規性 stature 的摘要，以及改善資料保護和合規性的建議。</span><span class="sxs-lookup"><span data-stu-id="75fb2-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="75fb2-106">合規性管理員中提供的客戶動作為建議。在實施之前，您的組織可以評估這些建議在其各項法規環境中的效能。</span><span class="sxs-lookup"><span data-stu-id="75fb2-106">The customer actions provided in Compliance Manager are recommendations; it is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="75fb2-107">在合規性管理員中找到的建議不得加以轉譯以保證法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="75fb2-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="75fb2-108">Access 合規性管理員</span><span class="sxs-lookup"><span data-stu-id="75fb2-108">Access Compliance Manager</span></span>

<span data-ttu-id="75fb2-p103">您可以從服務信任入口網站存取合規性管理員。任何人只要有 Microsoft 帳戶或 Azure Active Directory 組織帳戶都可以存取合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="75fb2-p103">You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>
  
1. <span data-ttu-id="75fb2-111">請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="75fb2-111">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).</span></span>

2. <span data-ttu-id="75fb2-112">使用您的 Microsoft 服務帳戶登入，這是您的 Office 365、Microsoft 365 或 Azure Active Directory （Azure AD）使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="75fb2-112">Sign in with your Microsoft service account, which is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

3. <span data-ttu-id="75fb2-113">在服務信任入口網站中，建議您選取 [**合規性管理員**]，也就是具有最新功能的預覽版本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-113">In the Service Trust Portal, we recommend selecting **Compliance Manager**, which is the preview version with the most current features.</span></span> <span data-ttu-id="75fb2-114">**合規性管理員（經典）** 會帶您前往舊版合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="75fb2-114">**Compliance Manager (Classic)** takes you to the previous version of Compliance Manager.</span></span>

4. <span data-ttu-id="75fb2-115">顯示未披露的合約時，請閱讀並選取 [**同意**]，然後再顯示您的合規性管理員儀表板。</span><span class="sxs-lookup"><span data-stu-id="75fb2-115">When the Non-Disclosure Agreement is displayed, read it and select **Agree**, which then displays your Compliance Manager dashboard.</span></span>

<span data-ttu-id="75fb2-116">為了讓您開始，您的組織預設會出現 Office 365 的 ISO/IEC 27001:2103 評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-116">To get you started, an ISO/IEC 27001:2103 Assessment for Office 365 appears by default for your organization.</span></span>

## <a name="administration"></a><span data-ttu-id="75fb2-117">系統管理</span><span class="sxs-lookup"><span data-stu-id="75fb2-117">Administration</span></span>

<span data-ttu-id="75fb2-118">只有全域系統管理員可以使用特定的管理功能，而且只有當以全域系統管理員帳戶登入時才會顯示。</span><span class="sxs-lookup"><span data-stu-id="75fb2-118">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="75fb2-119">全域管理員可以指派使用者權限，也可以為所有動作開啟自動安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="75fb2-119">The global administrator can assign user permissions, and can turn on automatic Secure Score updates for all actions.</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="75fb2-120">將合規性管理員角色指派給使用者</span><span class="sxs-lookup"><span data-stu-id="75fb2-120">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="75fb2-121">一旦管理員將合規性管理員角色指派給其他使用者，這些使用者便可在合規性管理員中查看資料，並執行其角色所決定的動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-121">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="75fb2-122">管理員也可以在[Azure Active Directory （AZURE AD）中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)指派使用者的全域讀取者角色，授與合規性管理員的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="75fb2-122">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="75fb2-123">每個合規性管理員角色都具有稍有不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="75fb2-123">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="75fb2-124">您可以查看指派給每個角色的許可權、查看哪些使用者屬於哪些角色，以及透過服務信任入口網站新增或移除該角色中的使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-124">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="75fb2-125">選取 [**管理**] 功能表項目目，然後選擇 [要查看的**設定**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-125">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理功能表：已選取設定](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="75fb2-127">若要新增使用者或從合規性管理員角色中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-127">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="75fb2-128">請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="75fb2-128">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="75fb2-129">使用您的 Azure Active Directory 全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="75fb2-129">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="75fb2-130">在服務信任入口網站頂端功能表列上，選取 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-130">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="75fb2-131">在 [**選取角色**] 下拉式清單中，選取您要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="75fb2-131">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="75fb2-132">新增至每個角色的使用者會列在 [選取角色]\*\*\*\* 頁面上。</span><span class="sxs-lookup"><span data-stu-id="75fb2-132">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="75fb2-133">若要將使用者新增至此角色，請選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-133">To add users to this role, select **Add**.</span></span> <span data-ttu-id="75fb2-134">在 [**新增使用者**] 對話方塊中，選取 [使用者] 欄位。</span><span class="sxs-lookup"><span data-stu-id="75fb2-134">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="75fb2-135">您可以在可用的使用者清單中向內移動，或是開始輸入使用者名稱，以根據您的搜尋字詞篩選清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-135">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="75fb2-136">選取要將該帳戶新增至以該角色布建的 [**新增使用者**] 清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-136">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="75fb2-137">如果您想要同時新增多個使用者，請開始輸入使用者名稱以篩選清單，然後選取要新增至清單的使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-137">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="75fb2-138">選取 [**儲存**]，將選取的角色布建給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-138">Select **Save** to provision the selected role to these users.</span></span> 

    ![合規性管理員-新增使用者](../media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="75fb2-140">若要移除此角色中的使用者，請選取使用者，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-140">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合規性管理員-刪除使用者](../media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="75fb2-142">控制自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="75fb2-142">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="75fb2-143">您可以使用下列步驟，針對所有動作，關閉所有動作，關閉所有動作，或透過個別動作設定安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="75fb2-143">Secure Score updates can be turned on automatically for all actions, turned off for all actions, or set by individual action by following these steps.</span></span>

1. <span data-ttu-id="75fb2-144">使用您的全域系統管理員帳戶登入[服務信任入口網站](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="75fb2-144">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="75fb2-145">在服務信任入口網站頂端功能表列上，按一下 [**其他**] 下的 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-145">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="75fb2-146">在 [**安全分數**] 索引標籤中，選取對應的按鈕來**開啟所有動作**、**關閉所有動作**，或**設定每個動作。**</span><span class="sxs-lookup"><span data-stu-id="75fb2-146">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="75fb2-147">如果您選擇 [**依動作設定]，請**採取下列額外步驟，為個別動作開啟安全分數更新：</span><span class="sxs-lookup"><span data-stu-id="75fb2-147">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="75fb2-148">從上方功能表中選取 [**合規性管理員**] （附注：不要選取「合規性管理員（古典）」）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-148">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="75fb2-149">在螢幕的右上角選取 [**租使用者管理**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-149">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="75fb2-150">在 [**客戶動作**] 窗格上，在 [**受影響的動作**] 欄下，以省略號（**...**）尋找您的預定動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-150">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="75fb2-151">按一下省略號，然後選取 [**編輯]。**</span><span class="sxs-lookup"><span data-stu-id="75fb2-151">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="75fb2-152">將**安全分數連續更新**切換開關切換為 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="75fb2-152">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="75fb2-153">選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="75fb2-153">Select **Save.**</span></span> <span data-ttu-id="75fb2-154">安全分數連續監控現在已開啟該動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-154">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="75fb2-155">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="75fb2-155">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="75fb2-156">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-156">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

## <a name="groups"></a><span data-ttu-id="75fb2-157">群組</span><span class="sxs-lookup"><span data-stu-id="75fb2-157">Groups</span></span>

<span data-ttu-id="75fb2-158">群組是容器，可讓您組織評估，並在具有相同或相關客戶管理控制措施的評估之間共用一般資訊和工作流程工作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-158">Groups are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span>

<span data-ttu-id="75fb2-159">您可以根據對您邏輯的方式來群組評估，例如依年、標準、服務或組織的小組、部門或地理區域。</span><span class="sxs-lookup"><span data-stu-id="75fb2-159">You can group Assessments in a way that is logical to you, such as by year, standard, service, or based on your organization's teams, divisions, or geographies.</span></span> <span data-ttu-id="75fb2-160">以下是兩個群組和其基礎評估的範例：</span><span class="sxs-lookup"><span data-stu-id="75fb2-160">Below are examples of two groups and their underlying Assessments:</span></span>
  
- <span data-ttu-id="75fb2-161">**FFIEC 是評估2020**</span><span class="sxs-lookup"><span data-stu-id="75fb2-161">**FFIEC IS Assessments 2020**</span></span>
  - <span data-ttu-id="75fb2-162">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="75fb2-162">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="75fb2-163">Intune + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="75fb2-163">Intune + FFIEC IS</span></span>
- <span data-ttu-id="75fb2-164">**資料安全性與隱私權評估**</span><span class="sxs-lookup"><span data-stu-id="75fb2-164">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="75fb2-165">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="75fb2-165">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="75fb2-166">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="75fb2-166">Office 365 + ISO 27018:2014</span></span>

> [!NOTE]
> <span data-ttu-id="75fb2-167">建議您先判斷貴組織的群群組原則，*然後再*新增新的評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-167">We recommend determining a grouping strategy for your organization *before* adding new Assessments.</span></span> <span data-ttu-id="75fb2-168">根據預設，名為「預設群組」的群組可用於您的初始評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-168">By default, a group named "Default Group" is available for your initial Assessments.</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="75fb2-169">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="75fb2-169">How to create a group</span></span>

<span data-ttu-id="75fb2-170">群組無法建立為獨立實體。</span><span class="sxs-lookup"><span data-stu-id="75fb2-170">Groups cannot be created as standalone entities.</span></span> <span data-ttu-id="75fb2-171">群組必須至少包含一個評估，因此若要建立群組，您必須先建立評估以放置在群組中。</span><span class="sxs-lookup"><span data-stu-id="75fb2-171">A group must always contain at least one Assessment, so in order to create a group, you must first create an Assessment to put in the group.</span></span> <span data-ttu-id="75fb2-172">請遵循下列步驟建立群組：</span><span class="sxs-lookup"><span data-stu-id="75fb2-172">Follow the steps below to create a group:</span></span>

1. <span data-ttu-id="75fb2-173">您可以在儀表板頂端的附近，選取 [新增**評估**]，以建立新的評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-173">Create a new Assessment by selecting **+ Add Assessment** near the top of your dashboard.</span></span>
2. <span data-ttu-id="75fb2-174">在 [**評估**] 快顯視窗中，輸入評估的標題，然後從下拉式功能表中選取範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-174">From the **Assessment** flyout pane, enter a title for your Assessment and select a template from the drop-down menu.</span></span>
3. <span data-ttu-id="75fb2-175">在 [**請選取群組或新增**群組] 中，選取 [**新增群組**]，然後在下欄欄位中輸入您的組名。</span><span class="sxs-lookup"><span data-stu-id="75fb2-175">At **Please select a group or add a new group**, select **Add a new group** and enter your group name in the field below.</span></span>
4. <span data-ttu-id="75fb2-176">若要複製現有群組中的資訊，請切換 [**您想要從現有的群組複製資料嗎？** ] 切換至 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="75fb2-176">To copy information from an existing group, toggle the **Would you like to copy the data from an existing group?** switch to **On.**</span></span> <span data-ttu-id="75fb2-177">從下拉式功能表中選取您要複製的群組，然後選取您想要在新群組中執行新評估的任何欄位核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-177">Select the group you want to copy from the drop-down menu underneath, and select the checkboxes of any fields you want to carry over to the new Assessment in your new group.</span></span>
5. <span data-ttu-id="75fb2-178">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75fb2-178">Select **Save**.</span></span> <span data-ttu-id="75fb2-179">完成後，就會關閉彈出窗格，而且新的群組會自動顯示在您的儀表板上。</span><span class="sxs-lookup"><span data-stu-id="75fb2-179">When completed, the flyout pane closes and your new group automatically displays on your dashboard.</span></span>

<span data-ttu-id="75fb2-180">使用群組時所知道的事項：</span><span class="sxs-lookup"><span data-stu-id="75fb2-180">What to know when working with groups:</span></span>
  
- <span data-ttu-id="75fb2-181">組名（也稱為「*群組 IDs*）在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="75fb2-181">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="75fb2-182">群組沒有任何安全性屬性。</span><span class="sxs-lookup"><span data-stu-id="75fb2-182">Groups do not have any security properties.</span></span> <span data-ttu-id="75fb2-183">擁有權限都與評估相關聯。</span><span class="sxs-lookup"><span data-stu-id="75fb2-183">All permissions are associated with Assessments.</span></span>
- <span data-ttu-id="75fb2-184">將評估新增至群組之後，就無法變更該群組。</span><span class="sxs-lookup"><span data-stu-id="75fb2-184">Once you add an Assessment to a group, the grouping cannot be changed.</span></span> <span data-ttu-id="75fb2-185">您可以重新命名評估群組，這會變更與該群組相關之所有評估的評估群組名稱。</span><span class="sxs-lookup"><span data-stu-id="75fb2-185">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span>
- <span data-ttu-id="75fb2-186">完成時，相同群組內的相關評估控制項會自動更新。</span><span class="sxs-lookup"><span data-stu-id="75fb2-186">Related Assessment controls in different Assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="75fb2-187">如果您將新的評估新增至現有的群組，則會將該群組中評估的一般資訊複製到新的評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-187">If you add a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="75fb2-188">群組可以包含同一個憑證或法規的評估，但是每個群組只能包含特定產品認證組的一個評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-188">Groups can contain Assessments for the same certification or regulation, but each group can only contain one Assessment for a specific product-certification pair.</span></span> <span data-ttu-id="75fb2-189">例如，群組不可包含針對 Office 365 和 NIST CSF 的兩項評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-189">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="75fb2-190">只有在每個群組的對應憑證或法規不同時，群組才可以包含同一個產品的多項評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-190">A group can contain multiple Assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="75fb2-191">隱藏評估會中斷這種評估與群組之間的關係。</span><span class="sxs-lookup"><span data-stu-id="75fb2-191">Hiding an Assessment breaks the relationship between that Assessment and the group.</span></span> <span data-ttu-id="75fb2-192">其他相關評估的任何進一步更新都會不再反映在隱藏評估中。</span><span class="sxs-lookup"><span data-stu-id="75fb2-192">Any further updates to other related Assessments are no longer reflected in the hidden assessment.</span></span> <span data-ttu-id="75fb2-193">（[瞭解如何隱藏評估。](#hide-a-template-or-an-assessment)）</span><span class="sxs-lookup"><span data-stu-id="75fb2-193">([Learn how to hide Assessments.](#hide-a-template-or-an-assessment))</span></span>
- <span data-ttu-id="75fb2-194">無法刪除群組。</span><span class="sxs-lookup"><span data-stu-id="75fb2-194">Groups cannot be deleted.</span></span>

## <a name="tenant-management"></a><span data-ttu-id="75fb2-195">租使用者管理</span><span class="sxs-lookup"><span data-stu-id="75fb2-195">Tenant Management</span></span>

<span data-ttu-id="75fb2-196">合規性管理員（預覽）包含新的介面，用來管理稱為**租使用者管理**的新資料元素。</span><span class="sxs-lookup"><span data-stu-id="75fb2-196">Compliance Manager (Preview) includes a new interface for managing new data elements called **Tenant Management**.</span></span> <span data-ttu-id="75fb2-197">此介面可讓您管理全租使用者的設定：</span><span class="sxs-lookup"><span data-stu-id="75fb2-197">This interface enables you to manage tenant-wide settings:</span></span>

- <span data-ttu-id="75fb2-198">**維度：** View 可讓您建立自訂樞軸篩選的範本、評估及動作專案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-198">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="75fb2-199">**擁有者：** 指定每個即席專案的擁有者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-199">**Owners:** Specify an owner for each Action Item.</span></span>
- <span data-ttu-id="75fb2-200">**客戶動作：** 管理合規性管理員（預覽）中包含的完整動作專案清單，並啟用/停用以安全分數整合之動作的安全評分監控。</span><span class="sxs-lookup"><span data-stu-id="75fb2-200">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="75fb2-201">選取 [**租使用者管理**] 以開啟管理介面，並使用下列步驟來管理**維度**、**擁有**者及**客戶動作**。</span><span class="sxs-lookup"><span data-stu-id="75fb2-201">Select **Tenant Management** to open the management interface, and use the following steps to manage **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="75fb2-202">Dimensions</span><span class="sxs-lookup"><span data-stu-id="75fb2-202">Dimensions</span></span>

<span data-ttu-id="75fb2-203">維度是一組中繼資料，可提供範本、評估或交辦事項的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-203">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="75fb2-204">維度使用索引鍵和值的概念，其中維度索引鍵代表屬性，維度值代表屬性的有效值。</span><span class="sxs-lookup"><span data-stu-id="75fb2-204">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="75fb2-205">例如，在合規性管理員中，有三種類型的動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-205">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="75fb2-206">它們是由**動作類型**的尺寸鍵及**檔**、**運作**及**技術**的維度值所定義。</span><span class="sxs-lookup"><span data-stu-id="75fb2-206">They are defined by a Dimension Key of **Action Type** and Dimension Values of **Documentation**, **Operational**, and **Technical**.</span></span> <span data-ttu-id="75fb2-207">您可以編輯或刪除現有的維度。</span><span class="sxs-lookup"><span data-stu-id="75fb2-207">You can edit or delete existing Dimensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75fb2-208">您可以新增維度，也可以將其指派給您已匯入的範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-208">You can add new dimensions, and they can be assigned to Templates that you have already imported.</span></span> <span data-ttu-id="75fb2-209">您也可以將新的維度新增至您建立的任何新範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-209">You can also add new dimensions to any new Templates you create.</span></span>

### <a name="owners"></a><span data-ttu-id="75fb2-210">擁有者</span><span class="sxs-lookup"><span data-stu-id="75fb2-210">Owners</span></span>

<span data-ttu-id="75fb2-211">擁有者是用來識別每個控制項的負責方。</span><span class="sxs-lookup"><span data-stu-id="75fb2-211">Owners are used to identify the responsible party for each control.</span></span> <span data-ttu-id="75fb2-212">所有內建的控制項都是由 Microsoft、客戶或兩者所擁有。</span><span class="sxs-lookup"><span data-stu-id="75fb2-212">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="75fb2-213">您可以為擁有者建立自訂值，以用於在組織中指定更細微的責任。</span><span class="sxs-lookup"><span data-stu-id="75fb2-213">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="75fb2-214">例如，您可以建立代表組織內特定群組、小組或業務單位的擁有者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-214">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="75fb2-215">新增擁有者</span><span class="sxs-lookup"><span data-stu-id="75fb2-215">Add an Owner</span></span>

1. <span data-ttu-id="75fb2-216">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-216">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="75fb2-217">選取 [ **+ 新增擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-217">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="75fb2-218">提供擁有者的名稱和描述，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-218">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="75fb2-219">描述會顯示在 [擁有者] 欄中。</span><span class="sxs-lookup"><span data-stu-id="75fb2-219">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="75fb2-220">編輯擁有者</span><span class="sxs-lookup"><span data-stu-id="75fb2-220">Edit an Owner</span></span>

<span data-ttu-id="75fb2-221">您無法編輯擁有者名稱，但您可以修改顯示在 [擁有者] 欄中的描述。</span><span class="sxs-lookup"><span data-stu-id="75fb2-221">You can’t edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="75fb2-222">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-222">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="75fb2-223">找到您要編輯的擁有者，選取其旁邊的省略號（...），然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-223">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="75fb2-224">視需要修改描述，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-224">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="75fb2-225">刪除擁有者</span><span class="sxs-lookup"><span data-stu-id="75fb2-225">Delete an Owner</span></span>

1. <span data-ttu-id="75fb2-226">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-226">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="75fb2-227">找到您想要刪除的擁有者，選取其旁邊的省略號（...），然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-227">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="75fb2-228">出現確認訊息時，請選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-228">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="75fb2-229">客戶動作</span><span class="sxs-lookup"><span data-stu-id="75fb2-229">Customer Actions</span></span>

<span data-ttu-id="75fb2-230">[客戶動作] 區域會顯示合規性管理員（預覽）中所有範本及評估的所有客戶動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-230">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

<span data-ttu-id="75fb2-231">![合規性管理員-新增使用者](../media/compliance-manager-customer-actions.png "合規性管理員客戶動作")</span><span class="sxs-lookup"><span data-stu-id="75fb2-231">![Compliance Manager — add users](../media/compliance-manager-customer-actions.png "Compliance Manager Customer Actions")</span></span>

<span data-ttu-id="75fb2-232">您可以快速查看動作的標題、擁有者、類別、強制執行和評分，並判斷是否與安全分數整合。</span><span class="sxs-lookup"><span data-stu-id="75fb2-232">At a glance, you can see an Action’s title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="75fb2-233">您可以展開動作並選取 [**讀取**]，以閱讀動作的描述並存取描述中的任何連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-233">You can expand an Action and select **Read More** to read the Action’s description and access any links in the description.</span></span> <span data-ttu-id="75fb2-234">您也可以使用此介面來啟用及停用以每個動作為基礎的安全分數整合，以及新增自訂動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-234">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="75fb2-235">具有安全計分整合功能的動作旁會有省略號（...）（請注意，自訂動作旁邊也有省略號）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-235">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="75fb2-236">啟用或停用安全分數整合</span><span class="sxs-lookup"><span data-stu-id="75fb2-236">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="75fb2-237">針對您要修改的動作選取省略號（...），然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-237">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="75fb2-238">切換切換參數，以取得安全分數連續更新為開啟或關閉，以啟用或停用透過安全分數的連續監控。</span><span class="sxs-lookup"><span data-stu-id="75fb2-238">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="75fb2-239">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75fb2-239">Select **Save**.</span></span>

<span data-ttu-id="75fb2-240">當組織第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行保護，以完全收集資料，並將其劃分為您的分數。</span><span class="sxs-lookup"><span data-stu-id="75fb2-240">When organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="75fb2-241">在這段時間內，將安全計分連續更新參數設定為**Off** ，並手動設定所要**執行**的動作，就會將該動作計算為您的分數。</span><span class="sxs-lookup"><span data-stu-id="75fb2-241">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="75fb2-242">在最初7天后，開啟安全分數連續更新會啟用從該點繼續進行監視。</span><span class="sxs-lookup"><span data-stu-id="75fb2-242">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>

<span data-ttu-id="75fb2-243">安全分數整合不支援的任何動作都可以手動實施。</span><span class="sxs-lookup"><span data-stu-id="75fb2-243">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="75fb2-244">手動執行將會考慮該動作群組的分數。</span><span class="sxs-lookup"><span data-stu-id="75fb2-244">A manual implementation will factor into the score for that action's group.</span></span>

#### <a name="add-a-customer-action"></a><span data-ttu-id="75fb2-245">新增客戶動作</span><span class="sxs-lookup"><span data-stu-id="75fb2-245">Add a customer action</span></span>

1. <span data-ttu-id="75fb2-246">選取 [ **+ 新增客戶動作**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-246">Select **+ Add Customer Action**.</span></span>
2. <span data-ttu-id="75fb2-247">在 [**標題**] 欄位中為動作提供唯一的標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-247">Provide a unique title for the Action in the **Title** field.</span></span>
3. <span data-ttu-id="75fb2-248">在 [**最大合規性分數**] 欄位中提供動作的合規性分數（可以是1-99 的任何數位）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-248">Provide a Compliance Score for the Action in the **Maximum Compliance Score** field (this can be any number from 1-99).</span></span>
4. <span data-ttu-id="75fb2-249">使用 [**動作類型**] 下拉式清單來指定您要新增的動作類型。</span><span class="sxs-lookup"><span data-stu-id="75fb2-249">Use the **Action Type** dropdown to specify the type of Action you are adding.</span></span> <span data-ttu-id="75fb2-250">如果動作類型不存在，您可以將值新增至動作類型維度金鑰以加以新增。</span><span class="sxs-lookup"><span data-stu-id="75fb2-250">If the Action Type does not exist, you can add it by adding the value to the Action Type dimension key.</span></span>
5. <span data-ttu-id="75fb2-251">使用 [**維度**] 下拉式清單來指定或新增動作的維度鍵和值。</span><span class="sxs-lookup"><span data-stu-id="75fb2-251">Use the **Dimensions** dropdown to specify or add dimension keys and values for the Action.</span></span>
6. <span data-ttu-id="75fb2-252">使用 [**擁有**者] 下拉式清單來指定動作的擁有者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-252">Use the **Owner** dropdown to specify the owner for Action.</span></span>
7. <span data-ttu-id="75fb2-253">選取**+** 以新增動作的描述和描述標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-253">Select **+** to add a description and description title for the Action.</span></span>
8. <span data-ttu-id="75fb2-254">選取 [ **X** ] 以關閉描述 blade。</span><span class="sxs-lookup"><span data-stu-id="75fb2-254">Select the **X** to close the Description blade.</span></span>
9. <span data-ttu-id="75fb2-255">選取 [**儲存**] 以儲存客戶動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-255">Select **Save** to save the Customer Action.</span></span>

#### <a name="delete-a-customer-action"></a><span data-ttu-id="75fb2-256">刪除客戶動作</span><span class="sxs-lookup"><span data-stu-id="75fb2-256">Delete a customer action</span></span>

1. <span data-ttu-id="75fb2-257">針對您要修改的動作選取省略號（...），然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-257">Select the ellipses (…) for the Action you want to modify and select **Delete**.</span></span>
2. <span data-ttu-id="75fb2-258">出現確認訊息時，請選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-258">When the confirmation message appears, select **Delete**.</span></span>

## <a name="assessments"></a><span data-ttu-id="75fb2-259">評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-259">Assessments</span></span>

### <a name="add-an-assessment"></a><span data-ttu-id="75fb2-260">新增評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-260">Add an Assessment</span></span>
  
1. <span data-ttu-id="75fb2-261">在 [評估] 儀表板中，選取 [ **+ Add 評估**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-261">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="75fb2-262">當刀片式伺服器開啟時，請輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="75fb2-262">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="75fb2-263">**職稱（必要）：** 輸入評估的標題</span><span class="sxs-lookup"><span data-stu-id="75fb2-263">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="75fb2-264">**請選取範本（必要）：** 選取標準或自訂範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-264">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="75fb2-265">**請選取群組或新增新的群組（必要）：** 選取現有的群組，或選擇新增群組，並提供唯一的組名</span><span class="sxs-lookup"><span data-stu-id="75fb2-265">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="75fb2-266">**您要複製現有群組中的資料嗎？（選用）：** 切換控制項以啟用群組副本，然後：</span><span class="sxs-lookup"><span data-stu-id="75fb2-266">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="75fb2-267">**選取群組（選用）：** 如果已啟用群組副本，請選取要複製的群組</span><span class="sxs-lookup"><span data-stu-id="75fb2-267">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="75fb2-268">**執行詳細資料（選用）：** 選取以將實現詳細資料複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="75fb2-268">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="75fb2-269">**測試計劃 & 其他資訊（選用）：** 選取以將測試計劃及其他資訊詳細資料複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="75fb2-269">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="75fb2-270">**檔（選用）：** 選取以將檔案複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="75fb2-270">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="75fb2-271">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-271">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="75fb2-272">評估儀表板上會顯示新的評估，並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="75fb2-272">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="75fb2-273">評估的標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-273">The title of the Assessment.</span></span>
- <span data-ttu-id="75fb2-274">評估的維度，包括憑證、環境和套用至評估的產品。</span><span class="sxs-lookup"><span data-stu-id="75fb2-274">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="75fb2-275">其建立日期和上次修改日期的日期。</span><span class="sxs-lookup"><span data-stu-id="75fb2-275">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="75fb2-276">評估分數顯示為百分比。</span><span class="sxs-lookup"><span data-stu-id="75fb2-276">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="75fb2-277">這個分數會自動包含您的分數從 Microsoft 管理的控制項，以及從安全得分。</span><span class="sxs-lookup"><span data-stu-id="75fb2-277">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="75fb2-278">顯示評估的 Microsoft managed 和客戶 manged 控制項數目的進度指示器。</span><span class="sxs-lookup"><span data-stu-id="75fb2-278">Progress indicators that show the number of assessed Microsoft-managed and customer-manged controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="75fb2-279">從現有「評定」複製資訊</span><span class="sxs-lookup"><span data-stu-id="75fb2-279">Copying information from existing Assessments</span></span>

<span data-ttu-id="75fb2-280">當您建立評估時，您可以選擇複製現有群組中的資訊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-280">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="75fb2-281">這可讓您將輸入到所複製評估的資訊套用到新評估中的相同控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-281">This allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="75fb2-282">例如，如果您的組織中有所有 FFIEC 相關評估的群組，您可以從現有評估中複製下列資訊：</span><span class="sxs-lookup"><span data-stu-id="75fb2-282">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="75fb2-283">執行詳細資料</span><span class="sxs-lookup"><span data-stu-id="75fb2-283">Implementation Details</span></span>
- <span data-ttu-id="75fb2-284">測試計劃 & 其他資訊</span><span class="sxs-lookup"><span data-stu-id="75fb2-284">Test Plan & Additional Information</span></span>
- <span data-ttu-id="75fb2-285">文件</span><span class="sxs-lookup"><span data-stu-id="75fb2-285">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="75fb2-286">將現有評估的資訊複製到新的評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-286">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="75fb2-287">在 [評估] 儀表板中，選取 [ **+ Add 評估**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-287">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="75fb2-288">在 [**新增評估**] 視窗中，完成下列資訊：</span><span class="sxs-lookup"><span data-stu-id="75fb2-288">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="75fb2-289">**職稱（必要）：** 輸入評估的標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-289">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="75fb2-290">**請選取範本（必要）：** 選取標準或自訂的範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-290">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="75fb2-291">**請選取群組或新增新的群組（必要）：** 選擇 [新增**群組**]，並提供唯一的組名。</span><span class="sxs-lookup"><span data-stu-id="75fb2-291">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="75fb2-292">**您要複製現有群組中的資料嗎？（選用）：** 將控制項切換至開啟以啟用群組副本，然後：**選取群組（選用）：** 如果已啟用群組副本，請選取要複製的群組。</span><span class="sxs-lookup"><span data-stu-id="75fb2-292">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="75fb2-293">- **執行詳細資料（選用）：** 選取可將實現詳細資料複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="75fb2-293">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="75fb2-294">- **測試計劃 & 其他資訊（選用）：** 選取以將測試計劃及其他資訊詳細資料複製到新群組。</span><span class="sxs-lookup"><span data-stu-id="75fb2-294">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="75fb2-295">- **檔（選用）：** 選取以將檔案複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="75fb2-295">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="75fb2-296">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-296">Select **Save** to create the Assessment.</span></span>

### <a name="view-an-assessment"></a><span data-ttu-id="75fb2-297">查看評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-297">View an Assessment</span></span>
  
1. <span data-ttu-id="75fb2-298">在 [評估] 儀表板中，選取 [評估名稱] 以開啟它，然後查看 [動作專案] 和 [控制項] 資訊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-298">In the Assessments dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="75fb2-299">以下是 Office 365 及 ISO 27001 評估的範例。</span><span class="sxs-lookup"><span data-stu-id="75fb2-299">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="75fb2-300">第一個視圖說明合規性管理員（預覽）中的新動作專案視圖。</span><span class="sxs-lookup"><span data-stu-id="75fb2-300">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合規性管理員動作專案視圖](../media/compliance-manager-action-items.png)

<span data-ttu-id="75fb2-302">動作會以字母順序列出，而且每個動作都會被指派分數和擁有者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-302">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="75fb2-303">選取 [**讀取其他**] 連結，以閱讀每個動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-303">Select  the **Read More** link to read the details of each Action.</span></span> 

![合規性管理員動作專案視圖](../media/compliance-manager-actions-read-more.png)

<span data-ttu-id="75fb2-305">選取 [**檢查**] 連結，以管理、指派、實施及測試動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-305">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="75fb2-306">以下是範例動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-306">Below is an example Action.</span></span>

![合規性管理員動作視圖](../media/compliance-manager-action.png)

<span data-ttu-id="75fb2-308">在舊版合規性管理員中，實現需求的工作流程是在控制項層級執行。</span><span class="sxs-lookup"><span data-stu-id="75fb2-308">In previous versions of Compliance Manager, the workflow for implementing requirements was performed at the Control level.</span></span> <span data-ttu-id="75fb2-309">合規性監察官會指派控制權給某人以執行該控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-309">A compliance officer would assign a control to someone to implement the control.</span></span> <span data-ttu-id="75fb2-310">這有兩個缺點：</span><span class="sxs-lookup"><span data-stu-id="75fb2-310">There were two drawbacks to this:</span></span>

- <span data-ttu-id="75fb2-311">控制項通常會有多個動作與其相關聯，而且指派控制項的使用者可能不是完成執行控制項所需之所有動作的適當人員。</span><span class="sxs-lookup"><span data-stu-id="75fb2-311">Controls often had multiple actions associated with them, and the user to whom a control was assigned, might not be the right person to complete all actions that were required to implement the control</span></span>
- <span data-ttu-id="75fb2-312">將不同的工作組合成單一動作，可防止使用的信號和遙測的集合，在合規性管理員（預覽）中自動記錄租使用者設定變更。</span><span class="sxs-lookup"><span data-stu-id="75fb2-312">Combining separate tasks into a single Action prevented the collection of the signals and telemetry that is used to automatically record tenant configuration changes in Compliance Manager (Preview).</span></span>

<span data-ttu-id="75fb2-313">在 [合規性管理員（預覽）] 中，工作流程會從控制項層級移至動作層級。</span><span class="sxs-lookup"><span data-stu-id="75fb2-313">In Compliance Manager (Preview), the workflow process has moved from the Control level to the Action level.</span></span> <span data-ttu-id="75fb2-314">當您複查動作時，可以使用下欄欄位來管理動作工作流程：</span><span class="sxs-lookup"><span data-stu-id="75fb2-314">When reviewing an Action, the following fields can be used to manage the Action workflow:</span></span>

- <span data-ttu-id="75fb2-315">**指派使用者：** 選取此欄位，以選擇或輸入應指派此動作的使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-315">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="75fb2-316">您可以在清單中滾動，或輸入名稱來尋找，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="75fb2-316">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="75fb2-317">**管理檔：** 您可以以 Office 檔、圖像檔案及螢幕擷取畫面的形式上傳執行證據，在 CSV 或 TXT 中 PowerShell 輸出，以及 Pdf。</span><span class="sxs-lookup"><span data-stu-id="75fb2-317">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="75fb2-318">**實施狀態：** 用來指出動作目前的執行狀態。</span><span class="sxs-lookup"><span data-stu-id="75fb2-318">**Implementation Status:** Used to indicate the Action’s current implementation status.</span></span> <span data-ttu-id="75fb2-319">可能的值尚未實現、已實現、替代的實施、規劃中和不在範圍內。</span><span class="sxs-lookup"><span data-stu-id="75fb2-319">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="75fb2-320">**實施日期：** 採取動作的日期。</span><span class="sxs-lookup"><span data-stu-id="75fb2-320">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="75fb2-321">**測試結果：** 用來指出實施驗證的結果。</span><span class="sxs-lookup"><span data-stu-id="75fb2-321">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="75fb2-322">可能的值不會評估、傳遞、失敗-低風險、失敗-中低風險、失敗-高風險，而且不在範圍內。</span><span class="sxs-lookup"><span data-stu-id="75fb2-322">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="75fb2-323">**測試日期：** 驗證發生的日期。</span><span class="sxs-lookup"><span data-stu-id="75fb2-323">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="75fb2-324">**執行附注：** 輸入組織的執行詳細資料，以及您想要包含的任何附注。</span><span class="sxs-lookup"><span data-stu-id="75fb2-324">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="75fb2-325">**測試方案：** 輸入此動作的測試計劃詳細資料，以及您要包含的任何附注。</span><span class="sxs-lookup"><span data-stu-id="75fb2-325">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="75fb2-326">**其他資訊：** 輸入有關此動作或其在組織中實施方式的任何其他資訊，以及您想要加入的任何附注。</span><span class="sxs-lookup"><span data-stu-id="75fb2-326">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="75fb2-327">合規性管理員（預覽）也包含舊版中所找到的以控制項為基礎的樞紐分析表。</span><span class="sxs-lookup"><span data-stu-id="75fb2-327">Compliance Manager (Preview) also includes the control-based pivot found in previous versions.</span></span> <span data-ttu-id="75fb2-328">選取 [**控制項資訊**] 儀表板加以查看。</span><span class="sxs-lookup"><span data-stu-id="75fb2-328">Select the **Controls Info** dashboard to view it.</span></span> <span data-ttu-id="75fb2-329">您可以在評估與範本層級查看控制項資訊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-329">You can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="75fb2-330">以下是評估的控制項資訊儀表板的範例。</span><span class="sxs-lookup"><span data-stu-id="75fb2-330">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合規性管理員控制資訊視圖](../media/compliance-manager-controls-info.png)

<span data-ttu-id="75fb2-332">針對評估，[控制項資訊] 儀表板會顯示：</span><span class="sxs-lookup"><span data-stu-id="75fb2-332">For Assessments, the Controls Info dashboard displays:</span></span>

- <span data-ttu-id="75fb2-333">**群組**下拉式清單，可選取要查看的群組（使用多個群組時）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-333">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="75fb2-334">**評估**下拉式功能表，以選取要查看的評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-334">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="75fb2-335">所選評估的中繼資料，包括：</span><span class="sxs-lookup"><span data-stu-id="75fb2-335">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="75fb2-336">**評估控制項**的進度指標，顯示超過控制項總數的評估的控制項數目。</span><span class="sxs-lookup"><span data-stu-id="75fb2-336">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="75fb2-337">評估的目前**符合性分數**，顯示為百分數。</span><span class="sxs-lookup"><span data-stu-id="75fb2-337">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="75fb2-338">評估中所用之**憑證及\*\*\*\*產品**的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-338">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="75fb2-339">評估的目前**狀態**和上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="75fb2-339">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="75fb2-340">評估的**範圍服務**清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-340">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="75fb2-341">控制項的詳細資料，依控制項系列分組，包含客戶動作和 Microsoft 執行詳細資料的連結：</span><span class="sxs-lookup"><span data-stu-id="75fb2-341">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="75fb2-342">**您的動作**會顯示您可以執行的客戶動作，以滿足部分或所有控制項的需求。</span><span class="sxs-lookup"><span data-stu-id="75fb2-342">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control’s requirements.</span></span> <span data-ttu-id="75fb2-343">許多控制項具有多個與其相關聯的動作，而且所有與控制項關聯的動作都會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="75fb2-343">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="75fb2-344">這裡的動作與動作儀表板中所列的 UI 相同。</span><span class="sxs-lookup"><span data-stu-id="75fb2-344">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="75fb2-345">**Microsoft 動作**會顯示 Microsoft 內部架構中套用至所選認證控制項的控制項清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-345">**Microsoft Actions** displays the list of controls from Microsoft’s internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="75fb2-346">針對每個內部控制，選取 [已**執行**]，以查看 Microsoft 的執行和測試詳細資料，以及測試結果和測試日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="75fb2-346">For each internal control, select **Implemented** to see Microsoft’s implementation and test details, along with the test result and test date, as shown below.</span></span>

![合規性管理員 Microsoft 動作視圖](../media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a><span data-ttu-id="75fb2-348">匯出評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-348">Export an Assessment</span></span>

<span data-ttu-id="75fb2-349">您可以將評估匯出至您組織中或外部審計員和主管的符合性專案關係人的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="75fb2-349">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="75fb2-350">報表是指報表建立日期和時間的評估快照。</span><span class="sxs-lookup"><span data-stu-id="75fb2-350">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="75fb2-351">報告包含針對評估、控制執行狀態、控制測試日期、測試結果，以及提供上傳的證據檔連結的所有 Microsoft 及客戶管理控制項的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-351">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span> <span data-ttu-id="75fb2-352">您應該在封存評估之前匯出評估報告，因為封存的評估不會保留上載檔的連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-352">You should export the Assessment report prior to archiving an assessment because archived assessments do not retain links to uploaded documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="75fb2-353">匯出評估報告</span><span class="sxs-lookup"><span data-stu-id="75fb2-353">Export an Assessment report</span></span>
  
1. <span data-ttu-id="75fb2-354">在 [合規性管理員] 儀表板上，選取 [**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="75fb2-354">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="75fb2-355">在下拉式功能表中，選取您要匯出之評估的**群組**和**評估**。</span><span class="sxs-lookup"><span data-stu-id="75fb2-355">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="75fb2-356">選取 [**匯出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="75fb2-356">Select the **Export** button.</span></span>

<span data-ttu-id="75fb2-357">在您的瀏覽器會話中，會將評估報告當做 Excel 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="75fb2-357">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="75fb2-358">Excel 檔案的 files 名稱預設為評估的標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-358">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="75fb2-359">隱藏範本或評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-359">Hide a Template or an Assessment</span></span>

<span data-ttu-id="75fb2-360">當您完成範本或評估，但是不再因相容性目的而需要時，您可以將它從您的視圖中隱藏。</span><span class="sxs-lookup"><span data-stu-id="75fb2-360">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="75fb2-361">當範本或評估隱藏時，它會從預設視圖中移除，您必須選取 [**包含隱藏**] 核取方塊加以顯示。</span><span class="sxs-lookup"><span data-stu-id="75fb2-361">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="75fb2-362">![合規性管理員隱藏的範本視圖](../media/compliance-manager-hidden-template.png "合規性管理員隱藏範本")</span><span class="sxs-lookup"><span data-stu-id="75fb2-362">![Compliance Manager Hidden Template View](../media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75fb2-363">隱藏評估不會保留其上傳的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-363">Hidden Assessments do not retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="75fb2-364">強烈建議您先匯出評估，再將其隱藏以保留報告中的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-364">It is highly recommended that you export the Assessment before hiding it to retain links to the evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="75fb2-365">隱藏範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-365">Hiding a Template</span></span>

1. <span data-ttu-id="75fb2-366">開啟 [**範本**] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="75fb2-366">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="75fb2-367">找到您想要隱藏的範本，並在其列的省略號上，選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-367">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="75fb2-368">當您看到確認訊息時，請選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-368">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="75fb2-369">隱藏評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-369">Hide an Assessment</span></span>

1. <span data-ttu-id="75fb2-370">開啟 [**評估**儀表板]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-370">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="75fb2-371">從下拉式清單中，選取包含您想要隱藏之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="75fb2-371">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="75fb2-372">找到您想要隱藏的評估，並選取省略號，選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-372">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="75fb2-373">當您看到確認訊息時，請選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-373">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="75fb2-374">查看隱藏評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-374">View hidden Assessments</span></span>
  
1. <span data-ttu-id="75fb2-375">開啟 [**評估**儀表板] 索引標籤，然後選取 [**包含隱藏**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-375">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="75fb2-376">隱藏評估會顯示在 [**隱藏評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="75fb2-376">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="75fb2-377">取消隱藏評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-377">Unhide an Assessment</span></span>

1. <span data-ttu-id="75fb2-378">在 [**評估**] 索引標籤上，選取 [**包含隱藏**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-378">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="75fb2-379">隱藏評估會顯示在 [**隱藏評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="75fb2-379">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="75fb2-380">找到您想要取消隱藏的評估，並選取省略號，選取 [**取消隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-380">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="75fb2-381">當您看到確認訊息時，請選取 [**取消隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-381">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="75fb2-382">控制項和動作</span><span class="sxs-lookup"><span data-stu-id="75fb2-382">Controls and Actions</span></span>

<span data-ttu-id="75fb2-383">控制項和動作是合規性管理員（預覽）中所使用的主要資料轉動。</span><span class="sxs-lookup"><span data-stu-id="75fb2-383">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="75fb2-384">在舊版本的合規性管理員中，控制項 pivot 已增強，可在相同的控制系列中顯示 Microsoft 和客戶控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-384">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="75fb2-385">這種合併的視圖可讓您更容易查看每個控制項的完整共用責任模型。</span><span class="sxs-lookup"><span data-stu-id="75fb2-385">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="75fb2-386">Action pivot 是合規性管理員（預覽）中的新功能，其設計目的是為了提供 Microsoft 建議的所有動作的簡潔觀點。</span><span class="sxs-lookup"><span data-stu-id="75fb2-386">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="75fb2-387">控制項</span><span class="sxs-lookup"><span data-stu-id="75fb2-387">Controls</span></span>

<span data-ttu-id="75fb2-388">控制項可以從 [控制項資訊] 儀表板中查看。</span><span class="sxs-lookup"><span data-stu-id="75fb2-388">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="75fb2-389">控制項代表標準、認證、法規或架構中的需求。</span><span class="sxs-lookup"><span data-stu-id="75fb2-389">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="75fb2-390">若要將這些需求對應至多個標準、法規等專案，並將這些需求與動作相關聯，請將所有專案視為控制項框架。</span><span class="sxs-lookup"><span data-stu-id="75fb2-390">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="75fb2-391">例如，像是控制架構之外，規章（如 HIPAA）已細分為一節，合規性管理員中的 HIPAA 控制項使用與這些區段相同的編號配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="75fb2-391">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合規性管理員 Microsoft 控制項詳細資料](../media/compliance-manager-control-details.png)

<span data-ttu-id="75fb2-393">控制項有三種類型：</span><span class="sxs-lookup"><span data-stu-id="75fb2-393">There are three types of controls:</span></span>

1. <span data-ttu-id="75fb2-394">**Microsoft 受管理的控制項：** 這些是只有 Microsoft 有責任的控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-394">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="75fb2-395">它們會顯示在 box 範本中，並由 Microsoft 新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="75fb2-395">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="75fb2-396">**客戶管理的控制項：** 這些是只有客戶具有責任的控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-396">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="75fb2-397">它們會顯示在 box 範本中，並由客戶新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="75fb2-397">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="75fb2-398">**共用管理控制措施：** 這些是在 Microsoft 與客戶之間共用責任的控制。</span><span class="sxs-lookup"><span data-stu-id="75fb2-398">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="75fb2-399">這些範本會出現在 box 範本中，並由 Microsoft 新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="75fb2-399">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="75fb2-400">客戶也可以編輯或停用 Microsoft 管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-400">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="75fb2-401">Actions 專案</span><span class="sxs-lookup"><span data-stu-id="75fb2-401">Actions Items</span></span>

<span data-ttu-id="75fb2-402">動作專案是實施標準或法規需求的建議工作，或是用來測試、驗證及記錄組織的執行需求。</span><span class="sxs-lookup"><span data-stu-id="75fb2-402">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="75fb2-403">動作與一個或多個控制項相關聯。</span><span class="sxs-lookup"><span data-stu-id="75fb2-403">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="75fb2-404">每個控制項都有一個或多個與其相關聯的動作，而且每個動作都可以與一個或多個控制項產生關聯。</span><span class="sxs-lookup"><span data-stu-id="75fb2-404">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="75fb2-405">動作是合規性管理員（預覽）中核心工作流程的一部分，因為它們是指派、追蹤及驗證組織的物件。</span><span class="sxs-lookup"><span data-stu-id="75fb2-405">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="75fb2-406">指派動作專案</span><span class="sxs-lookup"><span data-stu-id="75fb2-406">Assign Action Items</span></span>
  
1. <span data-ttu-id="75fb2-407">在 [**動作專案**] 儀表板上，選取包含要指派其動作之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="75fb2-407">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="75fb2-408">在 [**評估**] 下拉式清單中，選取您要指派其動作的評估，或從下拉式清單中選取 [**全部**]，以查看所有可用的動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-408">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="75fb2-409">找到您想要指派的動作，然後在 [**擁有**者] 欄中，選取要**審閱**、已**執行**或**測試**的連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-409">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, **Implemented** or **Test**.</span></span>
4. <span data-ttu-id="75fb2-410">選取 [**指派使用者**] 欄位，並顯示您組織中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-410">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="75fb2-411">滾動清單並選取使用者或篩選清單，以選取使用者的名稱來選取使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-411">Scroll the list and select user or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="75fb2-412">在 [執行附注] 欄位中，輸入您想要傳遞給指派使用者的任何附注。</span><span class="sxs-lookup"><span data-stu-id="75fb2-412">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="75fb2-413">選取 [**儲存**] 以指派動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-413">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="75fb2-414">重新指派動作專案</span><span class="sxs-lookup"><span data-stu-id="75fb2-414">Reassign Action Items</span></span>

<span data-ttu-id="75fb2-415">此功能可讓組織將動作重新指派給新使用者，以移除使用者帳戶上任何使用中或尚未完成的相關性。</span><span class="sxs-lookup"><span data-stu-id="75fb2-415">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="75fb2-416">在 [**動作專案**] 儀表板上，選取包含您想要重新指派其動作之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="75fb2-416">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="75fb2-417">在 [**評估**] 下拉式清單中，選取您要重新指派其動作的評估，或從下拉式清單中選取 [**全部**]，以查看所有可用的動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-417">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="75fb2-418">找到您想要重新指派的動作，然後在 [**擁有**者] 欄中，選取要**複查**、**實施**或**測試**的連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-418">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="75fb2-419">從 [**指派使用者**] 欄位中刪除現有的使用者，並從使用者清單中選擇不同的使用者，或透過輸入使用者的名稱來篩選清單，以選取使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-419">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="75fb2-420">在 [執行附注] 欄位中，輸入您想要傳遞給使用者的任何附注。</span><span class="sxs-lookup"><span data-stu-id="75fb2-420">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="75fb2-421">選取 [**儲存**] 以重新指派動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-421">Select **Save** to reassign the Action.</span></span>

## <a name="templates"></a><span data-ttu-id="75fb2-422">範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-422">Templates</span></span>

<span data-ttu-id="75fb2-423">範本是合規性管理員（預覽）中與產品及認證（例如，standard、管制、控制架構等）相關聯的基礎物件。</span><span class="sxs-lookup"><span data-stu-id="75fb2-423">A Template is the base object in Compliance Manager (Preview) that is associated with a Product and a Certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="75fb2-424">您可以從 [範本] 儀表板中查看及新增範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-424">Templates can be viewed and added from the Templates dashboard.</span></span>

![合規性管理員 Microsoft 範本儀表板](../media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="75fb2-426">儀表板會顯示每個範本，以及與範本相關聯的憑證及產品、建立範本的日期和上次修改的日期、客戶和 Microsoft 管理控制項的數量，以及最大的合規性分數。範本，以及範本的狀態（例如，已核准，待定核准，已匯入）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-426">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

<span data-ttu-id="75fb2-427">內建的範本都有與其相關聯的內建評估，但是您可以根據內建的範本建立其他評估，而且您可以匯入自己的範本，並根據這些範本建立自訂評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-427">The built-in Templates each have a built-in Assessment associated with them, but you can create additional Assessments based on built-in Templates, and you can import your own Templates, and create custom Assessments based off those.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="75fb2-428">建立範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-428">Create a Template</span></span>

<span data-ttu-id="75fb2-429">您可以複製現有的範本或匯入自訂範本，以建立範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-429">You can create a Template by copying an existing Template or by importing a custom Template.</span></span> <span data-ttu-id="75fb2-430">必須使用範本資料的特定格式和架構，否則不會將其匯入合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="75fb2-430">There is a specific format and schema that must be used for Template data or it will not import into Compliance Manager.</span></span> <span data-ttu-id="75fb2-431">您可以從這裡下載具有正確架構和範例資料的檔案。</span><span class="sxs-lookup"><span data-stu-id="75fb2-431">A file with the correct schema and sample data can be downloaded from here.</span></span>
<span data-ttu-id="75fb2-432">每個自訂範本應該位於包含五個索引標籤的個別 Excel 活頁簿（.xls 或 .xlsx 格式）中：</span><span class="sxs-lookup"><span data-stu-id="75fb2-432">Each custom Template should be in a separate Excel workbook (in .xls or .xlsx format) that contains five tabs:</span></span>

1. <span data-ttu-id="75fb2-433">範本-評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-433">Template-Assessment</span></span>
2. <span data-ttu-id="75fb2-434">ControlFamily</span><span class="sxs-lookup"><span data-stu-id="75fb2-434">ControlFamily</span></span>
3. <span data-ttu-id="75fb2-435">動作</span><span class="sxs-lookup"><span data-stu-id="75fb2-435">Actions</span></span>
4. <span data-ttu-id="75fb2-436">擁有權</span><span class="sxs-lookup"><span data-stu-id="75fb2-436">Ownership</span></span>
5. <span data-ttu-id="75fb2-437">Dimensions</span><span class="sxs-lookup"><span data-stu-id="75fb2-437">Dimensions</span></span>

<span data-ttu-id="75fb2-438">每個索引標籤中所用的架構如下所述。</span><span class="sxs-lookup"><span data-stu-id="75fb2-438">The schema used within each tab is detailed below.</span></span>

#### <a name="template-assessment-tab"></a><span data-ttu-id="75fb2-439">範本-[評估] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="75fb2-439">Template-Assessment tab</span></span>

<span data-ttu-id="75fb2-440">此索引標籤具有單一欄：</span><span class="sxs-lookup"><span data-stu-id="75fb2-440">This tab has a single column:</span></span>

- <span data-ttu-id="75fb2-441">**inScopeServices**：以逗號分隔的產品或服務的清單，該清單屬於範本的範圍。</span><span class="sxs-lookup"><span data-stu-id="75fb2-441">**inScopeServices**: Comma-delimited list of products or services that are in-scope for the Template.</span></span>

#### <a name="controlfamily-tab"></a><span data-ttu-id="75fb2-442">ControlFamily] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="75fb2-442">ControlFamily tab</span></span>

<span data-ttu-id="75fb2-443">此索引標籤包含的欄會定義對應至 [動作] 索引標籤上所列動作的控制項，並包含控制項名稱、系列、標題及描述等詳細資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-443">This tab includes columns that define the controls that are mapped to the Actions listed on the Actions tab, and includes details like control name, family, title, and description.</span></span>  <span data-ttu-id="75fb2-444">您必須依下列順序依下列順序在 Excel 中排序的此索引標籤欄如下：</span><span class="sxs-lookup"><span data-stu-id="75fb2-444">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="75fb2-445">**controlName：** 來自憑證/標準/法規等的控制項名稱。</span><span class="sxs-lookup"><span data-stu-id="75fb2-445">**controlName:** Control name from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="75fb2-446">**controlFamily：** 從認證/標準、法規等控制系列。</span><span class="sxs-lookup"><span data-stu-id="75fb2-446">**controlFamily:** Control family from certification/standard, regulation, etc.</span></span>
- <span data-ttu-id="75fb2-447">**controlTitle：** 控制憑證/標準/法規等的標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-447">**controlTitle:** Control title from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="75fb2-448">**controlDescription：** 憑證/標準/法規等的控制描述。</span><span class="sxs-lookup"><span data-stu-id="75fb2-448">**controlDescription:** Control description from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="75fb2-449">**controlVersion：** 選用控制版本資訊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-449">**controlVersion:** Optional control version info.</span></span>  <span data-ttu-id="75fb2-450">範例：針對 NIST 800-53，目前值為 Rev 4，所以 controlVersion 為4。</span><span class="sxs-lookup"><span data-stu-id="75fb2-450">Example: for NIST 800-53, the current value is Rev 4, so the controlVersion is 4.</span></span>  <span data-ttu-id="75fb2-451">針對 CSA CCM，它是3.0.1。</span><span class="sxs-lookup"><span data-stu-id="75fb2-451">For CSA CCM, it is 3.0.1.</span></span>
- <span data-ttu-id="75fb2-452">**isDisabled：** 使用 TRUE 或 FALSE，表示控制項是否已停用。</span><span class="sxs-lookup"><span data-stu-id="75fb2-452">**isDisabled:** Use TRUE or FALSE to indicate whether the control has been disabled.</span></span>
- <span data-ttu-id="75fb2-453">**controlType：** 使用「抄送」表示這些是客戶管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-453">**controlType:** Use CC to indicate these are customer-managed controls.</span></span>
- <span data-ttu-id="75fb2-454">**controlComplianceScore：** 指派給控制項之所有動作分數的總和。</span><span class="sxs-lookup"><span data-stu-id="75fb2-454">**controlComplianceScore:** Sum of the score of all Actions assigned to the Control.</span></span>
- <span data-ttu-id="75fb2-455">**controlActionTitle：** 在 [動作] 索引標籤上，此控制項的所有 actionTitles 的雙分號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-455">**controlActionTitle:** Double semi-colon-delimited list of all actionTitles for this control as listed on the Actions tab.</span></span> 

#### <a name="actions-tab"></a><span data-ttu-id="75fb2-456">動作] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="75fb2-456">Actions tab</span></span>

<span data-ttu-id="75fb2-457">此索引標籤包含定義個別動作的欄，包含動作標題、擁有權及尺寸等詳細資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-457">This tab includes columns that define individual Actions, and it includes details like action title, ownership, and dimensions.</span></span> <span data-ttu-id="75fb2-458">您必須依下列順序依下列順序在 Excel 中排序的此索引標籤欄如下：</span><span class="sxs-lookup"><span data-stu-id="75fb2-458">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="75fb2-459">**actionTitle：** 動作的標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-459">**actionTitle:** Title of the action.</span></span> <span data-ttu-id="75fb2-460">每個標題都必須是唯一的，而且我們建議使用 Pascal 大小寫。</span><span class="sxs-lookup"><span data-stu-id="75fb2-460">Each title must be unique, and we recommend using Pascal case.</span></span>
- <span data-ttu-id="75fb2-461">**actionRelatedODVs：** 兩個以分號分隔的 actionTitles 清單，其為 actionTitle 欄中所列子系的父代。</span><span class="sxs-lookup"><span data-stu-id="75fb2-461">**actionRelatedODVs:** Double semicolon-delimited list of actionTitles that are parents of the child listed in the actionTitle column.</span></span> <span data-ttu-id="75fb2-462">在父/子關聯中，父系代表高水位線。</span><span class="sxs-lookup"><span data-stu-id="75fb2-462">In a parent/child relationship, the parent represents the high watermark.</span></span> <span data-ttu-id="75fb2-463">因此，如果您完成父系動作，也會完成所有子動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-463">Thus, if you complete a parent action, you also complete all child actions.</span></span> <span data-ttu-id="75fb2-464">例如，當您有類似的需求，但有不同的標準定義值，例如密碼長度，其中一個標準/法規至少需要15個字元，另一個則至少需要12或10。</span><span class="sxs-lookup"><span data-stu-id="75fb2-464">For example, when you have similar requirements but different standard-defined values, such as password length, where one standard/regulation requires a minimum of 15 characters, and another requires a minimum of 12 or 10.</span></span> <span data-ttu-id="75fb2-465">15是本範例中的父級，而且如果您至少設定15個字元，也會滿足在其他評估中建議12或10個字元的動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-465">15 would be the parent in this example, and if you configure a minimum of 15 characters, you also satisfy the actions that recommend 12 or 10 characters in other assessments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75fb2-466">ActionRelatedODVs 欄是架構的必要欄;不過，在合規性管理員（預覽）中無法使用該功能（相關的動作）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-466">The actionRelatedODVs column is a required column for the schema; however, the feature (related actions) is not available in Compliance Manager (Preview).</span></span>  <span data-ttu-id="75fb2-467">它會排定在以後的版本中新增。</span><span class="sxs-lookup"><span data-stu-id="75fb2-467">It is scheduled to be added in a later release.</span></span>

- <span data-ttu-id="75fb2-468">**actionDimensionValues：** 使用下列格式，從 [維度] 索引標籤中，以兩個分號分隔的可用維度清單：</span><span class="sxs-lookup"><span data-stu-id="75fb2-468">**actionDimensionValues:** Double semicolon-delimited list of applicable dimensions from the Dimensions tab, using the following format:</span></span>

    ```Markdown
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    <span data-ttu-id="75fb2-469">例如：</span><span class="sxs-lookup"><span data-stu-id="75fb2-469">For example:</span></span>

    ```Markdown
    Product::Office 365;;Certification::NIST CSF
    ```

    <span data-ttu-id="75fb2-470">自訂範本中使用的所有維度，都必須列在匯入檔案的 [維度] 索引標籤上，即使這些維度已列在維度儀表板上也是一樣。</span><span class="sxs-lookup"><span data-stu-id="75fb2-470">All Dimensions that are used in a custom Template must be listed on the Dimensions tab of the import file, even if they are already listed on the Dimensions dashboard.</span></span>
- <span data-ttu-id="75fb2-471">**actionScore：** 每個動作的數值，代表該動作的分數。</span><span class="sxs-lookup"><span data-stu-id="75fb2-471">**actionScore:** Numeric value for each Action, which represents the score for that action.</span></span> <span data-ttu-id="75fb2-472">我們建議遵循內建評估所使用的計分模型，此模型是以每個行動的目的及強制執行為基礎。</span><span class="sxs-lookup"><span data-stu-id="75fb2-472">We recommend following the scoring model used by the built-in assessments, which is based on each Action’s purpose and enforcement.</span></span>
- <span data-ttu-id="75fb2-473">**actionOwnership：** 以兩個分號分隔的擁有者清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-473">**actionOwnership:** Double semicolon-delimited list of Owners.</span></span> <span data-ttu-id="75fb2-474">所有列出的擁有者都必須包含在 [擁有權] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="75fb2-474">All listed Owners must be included on the Ownership tab.</span></span>
- <span data-ttu-id="75fb2-475">**actionDescription：** 每個動作的文字，其必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="75fb2-475">**actionDescription:** Text of each Action, which must be unique.</span></span> <span data-ttu-id="75fb2-476">此欄位支援 Markdown 語言，如下所述。</span><span class="sxs-lookup"><span data-stu-id="75fb2-476">This field supports Markdown Language as described below.</span></span>

#### <a name="ownership-tab"></a><span data-ttu-id="75fb2-477">擁有權] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="75fb2-477">Ownership tab</span></span>

<span data-ttu-id="75fb2-478">此索引標籤包含定義每個動作之擁有者的欄。</span><span class="sxs-lookup"><span data-stu-id="75fb2-478">This tab includes columns that define owners for each action.</span></span>  <span data-ttu-id="75fb2-479">您必須依下列順序依下列順序在 Excel 中排序的此索引標籤欄如下：</span><span class="sxs-lookup"><span data-stu-id="75fb2-479">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="75fb2-480">**ownershipName：** 擁有者/責任方的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="75fb2-480">**ownershipName:** Unique name of owner/responsible party.</span></span>
- <span data-ttu-id="75fb2-481">**ownershipDescription：** 擁有者/責任方的描述。</span><span class="sxs-lookup"><span data-stu-id="75fb2-481">**ownershipDescription:** Description of the owner/responsible party.</span></span>

#### <a name="dimensions-tab"></a><span data-ttu-id="75fb2-482">維度] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="75fb2-482">Dimensions tab</span></span>

<span data-ttu-id="75fb2-483">此索引標籤包含定義可以與動作相關聯之維度的欄。</span><span class="sxs-lookup"><span data-stu-id="75fb2-483">This tab includes columns that define the Dimensions that can be associated with an Action.</span></span>  <span data-ttu-id="75fb2-484">您必須依下列順序依下列順序在 Excel 中排序的此索引標籤欄如下：</span><span class="sxs-lookup"><span data-stu-id="75fb2-484">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="75fb2-485">**dimensionKey：** 維度所用的按鍵清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-485">**dimensionKey:** List of Keys used for Dimensions.</span></span> <span data-ttu-id="75fb2-486">例如，產品、認證等。</span><span class="sxs-lookup"><span data-stu-id="75fb2-486">For example, Product, Certification, etc.</span></span>
- <span data-ttu-id="75fb2-487">**dimensionValue：** 每個維度索引鍵的唯一值。</span><span class="sxs-lookup"><span data-stu-id="75fb2-487">**dimensionValue:** Unique value for each dimension key.</span></span> <span data-ttu-id="75fb2-488">例如，Office 365、Intune、Azure、自訂產品等等。</span><span class="sxs-lookup"><span data-stu-id="75fb2-488">For example, Office 365, Intune, Azure, Custom Product, etc.</span></span>
- <span data-ttu-id="75fb2-489">**allowMultiSelect：** 使用 TRUE 或 FALSE，表示可以為單一維度鍵選取多個維度值。</span><span class="sxs-lookup"><span data-stu-id="75fb2-489">**allowMultiSelect:** Use TRUE or FALSE to indicate that multiple dimension values can be selected for a single dimension key.</span></span>

#### <a name="using-markdown-language-in-description-fields"></a><span data-ttu-id="75fb2-490">在 [描述] 欄位中使用 Markdown 語言</span><span class="sxs-lookup"><span data-stu-id="75fb2-490">Using Markdown Language in Description Fields</span></span>

<span data-ttu-id="75fb2-491">範本與評估支援使用 Markdown 語言做為某些文字元素和格式設定。</span><span class="sxs-lookup"><span data-stu-id="75fb2-491">Templates and Assessments support the use of Markdown language for some text elements and formatting.</span></span>  <span data-ttu-id="75fb2-492">在合規性管理員中使用的 Markdown 語言有三個格式化元件：</span><span class="sxs-lookup"><span data-stu-id="75fb2-492">There are three formatting elements of Markdown language that are used in Compliance Manager:</span></span>

- <span data-ttu-id="75fb2-493">專案符號和編號清單</span><span class="sxs-lookup"><span data-stu-id="75fb2-493">Bullets and Numbered lists</span></span>
- <span data-ttu-id="75fb2-494">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="75fb2-494">Hyperlinks</span></span>
- <span data-ttu-id="75fb2-495">黑體</span><span class="sxs-lookup"><span data-stu-id="75fb2-495">Boldface</span></span>

<span data-ttu-id="75fb2-496">專案符號會以星號代替 Word 或 Excel 專案符號。</span><span class="sxs-lookup"><span data-stu-id="75fb2-496">Bullets are represented as asterisks instead of Word or Excel bullets.</span></span> <span data-ttu-id="75fb2-497">例如：</span><span class="sxs-lookup"><span data-stu-id="75fb2-497">For example:</span></span>

```Markdown
* Item A
* Item B
* Item C
```

<span data-ttu-id="75fb2-498">數位是以數位表示，但有間距表示縮排（三個空格的每個層級），而只是用於所有子等級的數位（例如，沒有字母）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-498">Numbers are represented as numbers, but with spaces for indentation (three spaces per level) and only numbers used for all sublevels (for example, no letters).</span></span>  <span data-ttu-id="75fb2-499">例如：</span><span class="sxs-lookup"><span data-stu-id="75fb2-499">For example:</span></span>
   1. <span data-ttu-id="75fb2-500">專案 A</span><span class="sxs-lookup"><span data-stu-id="75fb2-500">Item A</span></span>
   2. <span data-ttu-id="75fb2-501">專案 B</span><span class="sxs-lookup"><span data-stu-id="75fb2-501">Item B</span></span>
      1. <span data-ttu-id="75fb2-502">子專案 A</span><span class="sxs-lookup"><span data-stu-id="75fb2-502">Sub-item A</span></span>
      2. <span data-ttu-id="75fb2-503">子專案 B</span><span class="sxs-lookup"><span data-stu-id="75fb2-503">Sub-item B</span></span>
   3. <span data-ttu-id="75fb2-504">專案 C</span><span class="sxs-lookup"><span data-stu-id="75fb2-504">Item C</span></span>
   4. <span data-ttu-id="75fb2-505">專案 D</span><span class="sxs-lookup"><span data-stu-id="75fb2-505">Item D</span></span>
      1. <span data-ttu-id="75fb2-506">子專案 A</span><span class="sxs-lookup"><span data-stu-id="75fb2-506">Sub-item A</span></span>
      2. <span data-ttu-id="75fb2-507">子專案 B</span><span class="sxs-lookup"><span data-stu-id="75fb2-507">Sub-item B</span></span>
   5. <span data-ttu-id="75fb2-508">專案 E</span><span class="sxs-lookup"><span data-stu-id="75fb2-508">Item E</span></span>

<span data-ttu-id="75fb2-509">超連結的構造方式是在超連結文字周圍放置方括弧，並在緊鄰右括弧旁的括弧中放置超連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-509">Hyperlinks are constructed by placing brackets around the hyperlink text and the hyperlink itself in parentheses immediately next to the close bracket.</span></span>  <span data-ttu-id="75fb2-510">例如：</span><span class="sxs-lookup"><span data-stu-id="75fb2-510">For example:</span></span>

```Markdown
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
<span data-ttu-id="75fb2-511">此文字的呈現方式如下：按一下[這裡](https://www.microsoft.com)以移至 Microsoft 首頁。</span><span class="sxs-lookup"><span data-stu-id="75fb2-511">This text renders as follows:  Click [here](https://www.microsoft.com) to go to Microsoft’s home page.</span></span>

<span data-ttu-id="75fb2-512">如以上範例中所示，合規性管理員不會呈現帶底線的 URLs。</span><span class="sxs-lookup"><span data-stu-id="75fb2-512">As shown in the above example, Compliance Manager does not render URLs with underlining.</span></span>

<span data-ttu-id="75fb2-513">粗體文字是文字每一側的兩個星號，以粗體顯示。</span><span class="sxs-lookup"><span data-stu-id="75fb2-513">Boldface text is two asterisks on each side of the text to be bolded.</span></span>  <span data-ttu-id="75fb2-514">例如：</span><span class="sxs-lookup"><span data-stu-id="75fb2-514">For example:</span></span>

```Markdown
**This text will render in bold**
```
<span data-ttu-id="75fb2-515">**這個文字會以粗體呈現**</span><span class="sxs-lookup"><span data-stu-id="75fb2-515">**This text renders in bold**</span></span>

### <a name="create-a-template"></a><span data-ttu-id="75fb2-516">建立範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-516">Create a Template</span></span>

<span data-ttu-id="75fb2-517">您可以複製現有範本或從 Excel 匯入範本資料來建立範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-517">You can create a Template by copying an existing Template or by importing Template data from Excel.</span></span> <span data-ttu-id="75fb2-518">從 Excel 匯入資料時，範本需要兩個不同的合規性管理員管理員才能發佈資料（一個發佈，另一個用來核准）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-518">When importing data from Excel, the Template requires two different Compliance Manager Administrators to publish the data (one to publish, and one to approve).</span></span>

#### <a name="create-a-template-by-copying-an-existing-template"></a><span data-ttu-id="75fb2-519">複製現有範本以建立範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-519">Create a Template by copying an existing Template</span></span>

1. <span data-ttu-id="75fb2-520">開啟 [**範本**] 儀表板，然後選取 [ **+ 新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-520">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="75fb2-521">在 [**輸入範本名稱**] 欄位中，提供範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="75fb2-521">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="75fb2-522">選取 [**從現有範本複製**] 核取方塊，然後選取您要從下拉式清單中複製的範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-522">Check the **Copy from an existing template** checkbox and select the template you want to copy from the dropdown.</span></span>
4. <span data-ttu-id="75fb2-523">（選用）新增其他維度。</span><span class="sxs-lookup"><span data-stu-id="75fb2-523">Optionally add any additional Dimensions.</span></span>
5. <span data-ttu-id="75fb2-524">選取 [**新增至儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-524">Select **Add to Dashboard**.</span></span>

#### <a name="create-a-template-by-importing-data"></a><span data-ttu-id="75fb2-525">透過匯入資料建立範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-525">Create a Template by importing data</span></span>

1. <span data-ttu-id="75fb2-526">開啟 [**範本**] 儀表板，然後選取 [ **+ 新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-526">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="75fb2-527">在 [**輸入範本名稱**] 欄位中，提供範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="75fb2-527">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="75fb2-528">從可用清單中至少選取一個維度。</span><span class="sxs-lookup"><span data-stu-id="75fb2-528">Select at least one Dimension from the available list.</span></span>
4. <span data-ttu-id="75fb2-529">選取 **[流覽]** ，流覽至匯入檔案的位置，選取該檔案，然後選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-529">Select **Browse** to navigate to the location of the import file, select it, and select **Open**.</span></span>
5. <span data-ttu-id="75fb2-530">將會驗證匯入檔案，並指出所偵測到的控制項和控制系列數目。</span><span class="sxs-lookup"><span data-stu-id="75fb2-530">The import file will be validated and indicate the number of controls and control families that were detected.</span></span> <span data-ttu-id="75fb2-531">如果發生錯誤，則會在包含錯誤詳細資料的匯入檔案中提供連結至已修改的版本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-531">If there are errors, a link will be provided to a modified version of the import file that includes error details.</span></span> <span data-ttu-id="75fb2-532">您必須先解決所有的錯誤，才可匯入資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-532">All errors must be resolved before the data will be imported.</span></span>
6. <span data-ttu-id="75fb2-533">一旦資料通過驗證，請選取 [**新增至儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-533">Once the data passes validation, select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="75fb2-534">匯入的範本會出現在 [**範本**] 儀表板上，且其狀態為 [已匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-534">The imported Template appears on the **Templates** dashboard and it has a status of **Imported**.</span></span> <span data-ttu-id="75fb2-535">選取省略號（...），然後選取 [**發佈**] 以發佈範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-535">Select the ellipses (…) and select **Publish** to publish the Template.</span></span> <span data-ttu-id="75fb2-536">出現確認訊息時，請選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-536">When the confirmation message appears, select **Publish**.</span></span> <span data-ttu-id="75fb2-537">範本狀態變更為 [**擱置**中的核准]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-537">The Template status changes to **Pending Approval**.</span></span>
8. <span data-ttu-id="75fb2-538">另一個具有合規性管理員系統管理員角色的使用者必須核准範本儀表板中的範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-538">Another user with the Compliance Manager Administrator role must approve the Template in the Templates dashboard.</span></span> <span data-ttu-id="75fb2-539">他們必須選取省略號（...），然後選取 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-539">They must select the ellipses (…) and select **Approve**.</span></span> <span data-ttu-id="75fb2-540">出現確認訊息時，請選取 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-540">When the confirmation message appears, select **Approve**.</span></span> <span data-ttu-id="75fb2-541">現在可以使用範本。</span><span class="sxs-lookup"><span data-stu-id="75fb2-541">The Template is now ready for use.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75fb2-542">建立範本時，您必須同時包含**產品**和憑證的維度 **，以**確保您的範本會以合規性分數顯示。</span><span class="sxs-lookup"><span data-stu-id="75fb2-542">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>

### <a name="customize-a-template"></a><span data-ttu-id="75fb2-543">自訂範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-543">Customize a Template</span></span>

<span data-ttu-id="75fb2-544">範本可透過其他自訂控制項進行自訂。</span><span class="sxs-lookup"><span data-stu-id="75fb2-544">Templates can be customized through the additional of custom controls.</span></span> <span data-ttu-id="75fb2-545">所有自訂控制項都會視為客戶管理控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-545">All custom controls are considered customer-managed Controls.</span></span>

#### <a name="add-a-custom-control-to-a-template"></a><span data-ttu-id="75fb2-546">將自訂控制項新增至範本</span><span class="sxs-lookup"><span data-stu-id="75fb2-546">Add a custom control to a Template</span></span>

1. <span data-ttu-id="75fb2-547">開啟您要修改的**範本**。</span><span class="sxs-lookup"><span data-stu-id="75fb2-547">Open the **Template** you want to modify.</span></span>
2. <span data-ttu-id="75fb2-548">選取 [ **+ 新增**自訂控制項]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-548">Select **+ Add** custom control.</span></span>
3. <span data-ttu-id="75fb2-549">從下拉式清單中選取**控制項族**，如果不存在，則輸入新的控制項系列。</span><span class="sxs-lookup"><span data-stu-id="75fb2-549">Select a **Control Family** from the dropdown or enter a new control family if it does not exist.</span></span>
4. <span data-ttu-id="75fb2-550">在 [**控制項識別碼**] 欄位中提供控制項的唯一名稱或識別碼。</span><span class="sxs-lookup"><span data-stu-id="75fb2-550">Provide a unique name or ID for the control in the **Control ID** field.</span></span>
5. <span data-ttu-id="75fb2-551">在 [**標題**] 欄位中提供控制項標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-551">Provide the control title in the **Title** field.</span></span>
6. <span data-ttu-id="75fb2-552">在 [**描述**] 欄位中提供控制項的需求和其他資訊。</span><span class="sxs-lookup"><span data-stu-id="75fb2-552">Provide the requirements and other information for the control in the **Description** field.</span></span>
7. <span data-ttu-id="75fb2-553">選取 [**指派客戶**動作]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-553">Select **Assign Customer** Action.</span></span>
8. <span data-ttu-id="75fb2-554">找到您想要指派給控制項的動作：</span><span class="sxs-lookup"><span data-stu-id="75fb2-554">Locate the Action(s) you want to assign to the control:</span></span>
    - <span data-ttu-id="75fb2-555">使用 [**依維度篩選**] 來使用指派給動作的維度，以找出並列出它們。</span><span class="sxs-lookup"><span data-stu-id="75fb2-555">Use **Filter by Dimension** to use dimensions assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="75fb2-556">使用 [**依擁有者篩選**]，以使用指派給動作的擁有者，以找出並列出它們。</span><span class="sxs-lookup"><span data-stu-id="75fb2-556">Use **Filter by Owner** to use the owner(s) assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="75fb2-557">從下拉式清單中選取**動作類型**，依類型列出動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-557">Select an **Action Type** from the dropdown to list Actions by type.</span></span>
    - <span data-ttu-id="75fb2-558">輸入要尋找並列出之動作的標題。</span><span class="sxs-lookup"><span data-stu-id="75fb2-558">Enter the title of the Action to locate and list it.</span></span>
9. <span data-ttu-id="75fb2-559">使用步驟8中的準則，將會出現**符合動作**清單。</span><span class="sxs-lookup"><span data-stu-id="75fb2-559">Using the criteria in Step 8, a list of **Matching Action(s)** will appear.</span></span> <span data-ttu-id="75fb2-560">選取您要指派給控制項的第一個動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-560">Select the first Action you want to assign to the control.</span></span>
10. <span data-ttu-id="75fb2-561">隨即會出現動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-561">The details of the Action appear.</span></span> <span data-ttu-id="75fb2-562">選取您要使用的**描述**，然後選取 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-562">Select the **Description** you want to use and select **Done**.</span></span>
11. <span data-ttu-id="75fb2-563">針對每個您想要指派的其他動作，重複步驟9和10。</span><span class="sxs-lookup"><span data-stu-id="75fb2-563">Repeat Steps 9 and 10 for each additional Action you want to assign.</span></span>
12. <span data-ttu-id="75fb2-564">選取所有適用的動作後，請選取 [**指派**]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-564">When all applicable Actions have been selected, select **Assign**.</span></span>
13. <span data-ttu-id="75fb2-565">選取 [**儲存**] 以儲存新的控制項。</span><span class="sxs-lookup"><span data-stu-id="75fb2-565">Select **Save** to save the new control.</span></span>

> [!NOTE]
> <span data-ttu-id="75fb2-566">對範本所做的任何變更，都不會反映在現有評估中。</span><span class="sxs-lookup"><span data-stu-id="75fb2-566">Any changes made to a template will not be reflected in existing assessments.</span></span> <span data-ttu-id="75fb2-567">必須先進行範本更新，然後再套用到新的評估，才能看到所做的變更。</span><span class="sxs-lookup"><span data-stu-id="75fb2-567">Template updates must be made first, and then applied to a new assessment, in order for the changes to be seen.</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="75fb2-568">將範本匯出至 JSON</span><span class="sxs-lookup"><span data-stu-id="75fb2-568">Export a Template to JSON</span></span>

<span data-ttu-id="75fb2-569">合規性管理員（預覽）也支援將範本匯出為 JavaScript 物件標記法（JSON）格式。</span><span class="sxs-lookup"><span data-stu-id="75fb2-569">Compliance Manager (Preview) also supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="75fb2-570">這可讓您將合規性管理員資料與其他支援 JSON 的系統交換。</span><span class="sxs-lookup"><span data-stu-id="75fb2-570">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="75fb2-571">報告</span><span class="sxs-lookup"><span data-stu-id="75fb2-571">Reports</span></span>

<span data-ttu-id="75fb2-572">您可以將評估匯出至您組織中或外部審計員和主管的符合性專案關係人的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="75fb2-572">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="75fb2-573">報表是指匯出之日期和時間為止的評估快照。</span><span class="sxs-lookup"><span data-stu-id="75fb2-573">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="75fb2-574">報告包含 Microsoft 及客戶管理控制項的詳細資料，以供評估、控制執行狀態、控制測試日期、測試結果和上傳的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-574">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="75fb2-575">您應該在封存評估之前將其封存，因為已封存的評估不會保留上載檔的連結。</span><span class="sxs-lookup"><span data-stu-id="75fb2-575">You should export Assessments before archiving them because archived Assessments do not retain links to uploaded documents.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="75fb2-576">匯出評估</span><span class="sxs-lookup"><span data-stu-id="75fb2-576">Export an Assessment</span></span>

1. <span data-ttu-id="75fb2-577">在 [合規性管理員] 儀表板上，選取 [**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="75fb2-577">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="75fb2-578">在下拉式功能表中，選取您要匯出之評估的群組和評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-578">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="75fb2-579">選取 [匯出]。</span><span class="sxs-lookup"><span data-stu-id="75fb2-579">Select Export.</span></span> <span data-ttu-id="75fb2-580">評估匯出會下載成 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="75fb2-580">The Assessment export is downloaded as an Excel file.</span></span>

![合規性管理員評估 Excel 報告](../media/compliance-manager-assessment-report.png)

## <a name="permissions"></a><span data-ttu-id="75fb2-582">權限</span><span class="sxs-lookup"><span data-stu-id="75fb2-582">Permissions</span></span>

<span data-ttu-id="75fb2-583">下表說明每個合規性管理員許可權及其允許使用者執行的動作。</span><span class="sxs-lookup"><span data-stu-id="75fb2-583">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="75fb2-584">該表也會指出指派每個許可權的角色。</span><span class="sxs-lookup"><span data-stu-id="75fb2-584">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="75fb2-585">**Azure AD 全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="75fb2-585">**Azure AD Global Reader**</span></span>|<span data-ttu-id="75fb2-586">**合規性管理員讀取者**</span><span class="sxs-lookup"><span data-stu-id="75fb2-586">**Compliance Manager Reader**</span></span>|<span data-ttu-id="75fb2-587">**合規性參與者**</span><span class="sxs-lookup"><span data-stu-id="75fb2-587">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="75fb2-588">**合規性管理員評估者**</span><span class="sxs-lookup"><span data-stu-id="75fb2-588">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="75fb2-589">**合規性管理員管理者**</span><span class="sxs-lookup"><span data-stu-id="75fb2-589">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="75fb2-590">**入口網站管理員**</span><span class="sxs-lookup"><span data-stu-id="75fb2-590">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75fb2-591">**讀取資料：** 使用者可以讀取但不能編輯資料（範本資料和租使用者管理除外）。</span><span class="sxs-lookup"><span data-stu-id="75fb2-591">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="75fb2-592">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-592">X</span></span> | <span data-ttu-id="75fb2-593">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-593">X</span></span> | <span data-ttu-id="75fb2-594">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-594">X</span></span> | <span data-ttu-id="75fb2-595">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-595">X</span></span> | <span data-ttu-id="75fb2-596">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-596">X</span></span>  | <span data-ttu-id="75fb2-597">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-597">X</span></span> |
|<span data-ttu-id="75fb2-598">**編輯資料：** 除了 [測試結果] 和 [測試日期] 欄位（範本資料和租使用者管理以外）以外，使用者可以編輯所有欄位。</span><span class="sxs-lookup"><span data-stu-id="75fb2-598">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="75fb2-599">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-599">X</span></span> | <span data-ttu-id="75fb2-600">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-600">X</span></span>  | <span data-ttu-id="75fb2-601">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-601">X</span></span> | <span data-ttu-id="75fb2-602">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-602">X</span></span> |
|<span data-ttu-id="75fb2-603">**編輯測試結果：** 使用者可以編輯 [測試結果] 和 [測試日期] 欄位。</span><span class="sxs-lookup"><span data-stu-id="75fb2-603">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="75fb2-604">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-604">X</span></span> | <span data-ttu-id="75fb2-605">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-605">X</span></span> | <span data-ttu-id="75fb2-606">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-606">X</span></span> |
|<span data-ttu-id="75fb2-607">**管理評估：** 使用者可以建立、封存和刪除評估。</span><span class="sxs-lookup"><span data-stu-id="75fb2-607">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="75fb2-608">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-608">X</span></span> | <span data-ttu-id="75fb2-609">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-609">X</span></span> |
|<span data-ttu-id="75fb2-610">**管理主資料：** 使用者可以查看、編輯和刪除範本資料及承租人管理資料。</span><span class="sxs-lookup"><span data-stu-id="75fb2-610">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="75fb2-611">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-611">X</span></span> | <span data-ttu-id="75fb2-612">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-612">X</span></span> |
|<span data-ttu-id="75fb2-613">**管理使用者：** 使用者可以將組織中的其他使用者新增至讀者、投稿人、Assessor 及系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="75fb2-613">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="75fb2-614">只有在您組織中具有全域系統管理員角色的使用者，才可以從入口網站管理員角色新增或移除使用者。</span><span class="sxs-lookup"><span data-stu-id="75fb2-614">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="75fb2-615">X</span><span class="sxs-lookup"><span data-stu-id="75fb2-615">X</span></span> |
