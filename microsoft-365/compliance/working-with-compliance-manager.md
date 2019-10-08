---
title: 搭配使用 Microsoft Compliance Manager （預覽）
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
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: d15899b994e4169c7362144623bc726f3825245d
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417582"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="dac3c-104">搭配使用 Microsoft Compliance Manager （預覽）</span><span class="sxs-lookup"><span data-stu-id="dac3c-104">Work with Microsoft Compliance Manager (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dac3c-105">Microsoft Compliance Manager 是提供資料保護和合規性成長與建議，以提升資料保護和合規性的摘要儀表板和管理工具。</span><span class="sxs-lookup"><span data-stu-id="dac3c-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="dac3c-106">提供合規性管理員中的客戶動作是建議;它是由您的組織來評估在其各自的法規環境之前實作這些建議的有效性。</span><span class="sxs-lookup"><span data-stu-id="dac3c-106">The customer actions provided in Compliance Manager are recommendations; it is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="dac3c-107">找到合規性管理員中的建議不應該解譯成保證郵件可以合規性。</span><span class="sxs-lookup"><span data-stu-id="dac3c-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="dac3c-108">存取合規性管理員</span><span class="sxs-lookup"><span data-stu-id="dac3c-108">Access Compliance Manager</span></span>

<span data-ttu-id="dac3c-p103">您可以從服務信任入口網站存取合規性管理員。任何人只要有 Microsoft 帳戶或 Azure Active Directory 組織帳戶都可以存取合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="dac3c-p103">You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>
  
1. <span data-ttu-id="dac3c-111">請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="dac3c-111">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).</span></span>

2. <span data-ttu-id="dac3c-112">使用您的 Microsoft 服務帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="dac3c-112">Sign in with your Microsoft service account.</span></span> <span data-ttu-id="dac3c-113">這是您 Office 365、 Microsoft 365 或 Azure Active Directory (Azure AD) 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="dac3c-113">This is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

3. <span data-ttu-id="dac3c-114">在服務信任入口網站中，選取 [**合規性管理員**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-114">In the Service Trust Portal, select **Compliance Manager**.</span></span> <span data-ttu-id="dac3c-115">這是合規性管理員的預覽版本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-115">This is the preview version of Compliance Manager.</span></span> <span data-ttu-id="dac3c-116">**合規性管理員 （傳統）** 是舊版合規性管理員的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-116">**Compliance Manager (Classic)** is the link to the previous version of Compliance Manager.</span></span>

4. <span data-ttu-id="dac3c-117">顯示非洩漏合約時，讀取它，然後選取 [**同意**才能繼續。</span><span class="sxs-lookup"><span data-stu-id="dac3c-117">When the Non-Disclosure Agreement is displayed, read it, and select **Agree** to continue.</span></span> <span data-ttu-id="dac3c-118">您必須同意一次，則會顯示在合規性管理員儀表板。</span><span class="sxs-lookup"><span data-stu-id="dac3c-118">You must agree once, and then the Compliance Manager dashboard is displayed.</span></span>

<span data-ttu-id="dac3c-119">若要取得您快速上手，ISO/IEC 27001:2103 運作的 Office 365 評定，預設會出現為您的組織。</span><span class="sxs-lookup"><span data-stu-id="dac3c-119">To get you started, an ISO/IEC 27001:2103 Assessment for Office 365 appears by default for your organization.</span></span>

## <a name="administration"></a><span data-ttu-id="dac3c-120">系統管理</span><span class="sxs-lookup"><span data-stu-id="dac3c-120">Administration</span></span>

<span data-ttu-id="dac3c-121">有特定的系統管理功能，且僅供全域系統管理員時全域系統管理員帳戶登入時，只顯示。</span><span class="sxs-lookup"><span data-stu-id="dac3c-121">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="dac3c-122">一旦系統管理員將合規性管理員角色指派給其他使用者，這些使用者可以檢視資料合規性管理員中，並執行動作取決於其角色。</span><span class="sxs-lookup"><span data-stu-id="dac3c-122">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="dac3c-123">系統管理員可以也提供的唯讀權限到合規性管理員藉由指定使用者[在 Azure Active Directory (Azure AD) 中的全域讀者角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)。</span><span class="sxs-lookup"><span data-stu-id="dac3c-123">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="dac3c-124">將合規性管理員角色指派給使用者</span><span class="sxs-lookup"><span data-stu-id="dac3c-124">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="dac3c-125">每個合規性管理員角色具有稍有不同的權限。</span><span class="sxs-lookup"><span data-stu-id="dac3c-125">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="dac3c-126">您可以檢視指派給每個角色的權限，請參閱哪些使用者位於哪些角色，並從新增或移除使用者在服務信任入口網站透過該角色。</span><span class="sxs-lookup"><span data-stu-id="dac3c-126">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="dac3c-127">選取 [**系統管理**功能表項目，然後選擇 [**設定**]，以檢視。</span><span class="sxs-lookup"><span data-stu-id="dac3c-127">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 系統功能表： 選取的設定](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="dac3c-129">若要新增使用者或從合規性管理員角色中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-129">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="dac3c-130">請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="dac3c-130">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="dac3c-131">使用您的 Azure Active Directory 全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="dac3c-131">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="dac3c-132">在服務信任入口網站上方的功能表列中，選取 [**系統管理員**，然後選擇**設定**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-132">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="dac3c-133">在 [**選取角色**] 下拉式清單中，選取您想要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="dac3c-133">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="dac3c-134">新增至每個角色的使用者會列在 [**選取角色**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="dac3c-134">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="dac3c-135">將使用者新增至這個角色，選取 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-135">To add users to this role, select **Add**.</span></span> <span data-ttu-id="dac3c-136">在 [**新增使用者**] 對話方塊中，選取 [使用者] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dac3c-136">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="dac3c-137">您可以逐一捲動查看可用的使用者清單，或開始輸入使用者名稱來篩選清單，根據您的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="dac3c-137">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="dac3c-138">選取使用者，將該帳戶新增至該角色使用佈建的 [**新增使用者**] 清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-138">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="dac3c-139">如果您想要新增多個使用者同時，開始輸入使用者名稱，以篩選] 清單中，，，然後選取要新增至清單的使用者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-139">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="dac3c-140">選取 [**儲存**] 以佈建到這些使用者選取的角色。</span><span class="sxs-lookup"><span data-stu-id="dac3c-140">Select **Save** to provision the selected role to these users.</span></span> 

    ![合規性管理員-新增使用者](media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="dac3c-142">若要移除此角色的使用者，請選取的使用者，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-142">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合規性管理員-刪除使用者](media/compliance-manager-delete-users.png)

## <a name="groups"></a><span data-ttu-id="dac3c-144">群組</span><span class="sxs-lookup"><span data-stu-id="dac3c-144">Groups</span></span>

<span data-ttu-id="dac3c-145">群組可讓您以邏輯方式組織評估以及該共用一般資訊及工作流程工作之間具有相同或相關客戶管理控制項的評定。</span><span class="sxs-lookup"><span data-stu-id="dac3c-145">Groups allow you to logically organize Assessments and that share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="dac3c-146">若要協助降低客戶管理動作組織內，您可以藉由年、 標準、 服務、 小組、 部門或行政機關群組評估：</span><span class="sxs-lookup"><span data-stu-id="dac3c-146">You can group Assessments by year, standard, service, team, division, or agencies within your organization to help minimize customer-managed Actions:</span></span>
  
- <span data-ttu-id="dac3c-147">**FFIEC 是評估 2019**</span><span class="sxs-lookup"><span data-stu-id="dac3c-147">**FFIEC IS Assessments 2019**</span></span>
  - <span data-ttu-id="dac3c-148">Office 365 + FFIEC IS</span><span class="sxs-lookup"><span data-stu-id="dac3c-148">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="dac3c-149">Intune + FFIEC IS</span><span class="sxs-lookup"><span data-stu-id="dac3c-149">Intune + FFIEC IS</span></span>
- <span data-ttu-id="dac3c-150">**資料安全性與隱私權評估**</span><span class="sxs-lookup"><span data-stu-id="dac3c-150">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="dac3c-151">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="dac3c-151">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="dac3c-152">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="dac3c-152">Office 365 + ISO 27018:2014</span></span>

<span data-ttu-id="dac3c-153">當您建立新的 「 評估時，您必須建立新的群組評估或指派給現有群組的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-153">When you create a new Assessment, you must create a new group for the Assessment or assign the Assessment to an existing group.</span></span> <span data-ttu-id="dac3c-154">群組無法被建立為獨立的實體。</span><span class="sxs-lookup"><span data-stu-id="dac3c-154">Groups cannot be created as stand-alone entities.</span></span> <span data-ttu-id="dac3c-155">建議您判斷的群組策略，針對您的組織*之前*新增新的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-155">It's recommended that you determine a grouping strategy for your organization *before* adding new assessments.</span></span> <span data-ttu-id="dac3c-156">根據預設，名為 「 預設群組 」 的群組是供您初始評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-156">By default, a Group named "Default Group" is available for your initial Assessments.</span></span> <span data-ttu-id="dac3c-157">群組沒有任何安全性屬性。</span><span class="sxs-lookup"><span data-stu-id="dac3c-157">Groups do not have any security properties.</span></span> <span data-ttu-id="dac3c-158">評估與所有的權限相關聯。</span><span class="sxs-lookup"><span data-stu-id="dac3c-158">All permissions are associated with Assessments.</span></span>

<span data-ttu-id="dac3c-159">當您使用的群組時，請記得：</span><span class="sxs-lookup"><span data-stu-id="dac3c-159">When you work with groups, remember:</span></span>
  
- <span data-ttu-id="dac3c-160">當完成時，自動更新中相同群組中的不同評估相關的評估控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-160">Related assessment controls in different assessments within the same Group automatically update when completed.</span></span>
- <span data-ttu-id="dac3c-161">當您建立新的 「 評估新的群組可以從現存的 group 複製資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-161">New groups can copy information from an existing group when you create a new Assessment.</span></span> <span data-ttu-id="dac3c-162">在新從 「 評估 」 新增至實作詳細資料和客戶管理控制措施的測試計劃和管理回應] 欄位中的群組，您要複製的任何資訊複製到相同 （或相關） 客戶管理控制評量。</span><span class="sxs-lookup"><span data-stu-id="dac3c-162">Any information added to the Implementation Details and Test Plan and Management Response fields of customer-managed controls from Assessments in the group that you're copying from are copied to the same (or related) customer-managed controls in the new Assessment.</span></span> <span data-ttu-id="dac3c-163">如果您正在加入新的 「 評估至現有的群組，請從評估中該群組的一般資訊複製到新的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-163">If you're adding a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="dac3c-164">群組名稱 （也稱為 「*群組 Id*」） 必須是唯一組織內。</span><span class="sxs-lookup"><span data-stu-id="dac3c-164">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="dac3c-165">群組可以為相同的憑證/規定，包含 「 評估 」，但每個群組僅能包含一個評估為特定的雲端服務/憑證配對。</span><span class="sxs-lookup"><span data-stu-id="dac3c-165">Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair.</span></span> <span data-ttu-id="dac3c-166">例如，群組不能包含兩個 Office 365 和 NIST CSF 評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-166">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="dac3c-167">只有在相對應的每一個憑證/規定為不同的群組可以包含多個評定之相同雲端服務。</span><span class="sxs-lookup"><span data-stu-id="dac3c-167">A group can contain multiple Assessments for the same cloud service only if the corresponding certification/regulation for each one is different.</span></span>
- <span data-ttu-id="dac3c-168">一旦評估已新增至評估群組中，無法變更群組。</span><span class="sxs-lookup"><span data-stu-id="dac3c-168">Once an assessment has been added to an assessment group, the grouping cannot be changed.</span></span> <span data-ttu-id="dac3c-169">您可以重新命名評估群組，將變更的群組該群組相關聯的所有 「 評估 」 的 「 評估名稱。</span><span class="sxs-lookup"><span data-stu-id="dac3c-169">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span> <span data-ttu-id="dac3c-170">您可以建立評估及新的評估群組並複製資訊從現有的評估，有效地暗該評定的不同評估群組中。</span><span class="sxs-lookup"><span data-stu-id="dac3c-170">You can create an assessment and a new assessment group and copy information from an existing assessment, which effectively creates a duplicate of that assessment in a different assessment group.</span></span>
- <span data-ttu-id="dac3c-171">封存評估會中斷該評估及群組之間的關係。</span><span class="sxs-lookup"><span data-stu-id="dac3c-171">Archiving an assessment breaks the relationship between that assessment and the group.</span></span> <span data-ttu-id="dac3c-172">其他相關的 「 評估 」 的任何進一步更新不再會反映在封存的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-172">Any further updates to other related assessments are no longer reflected in the archived assessment.</span></span>

## <a name="tenant-management"></a><span data-ttu-id="dac3c-173">租用戶管理</span><span class="sxs-lookup"><span data-stu-id="dac3c-173">Tenant Management</span></span>

<span data-ttu-id="dac3c-174">合規性管理員 （預覽） 包含管理呼叫**租用戶管理**新的資料元素的新介面。</span><span class="sxs-lookup"><span data-stu-id="dac3c-174">Compliance Manager (Preview) includes a new interface for managing new data elements called **Tenant Management**.</span></span> <span data-ttu-id="dac3c-175">此介面可讓您管理租用戶整體設定：</span><span class="sxs-lookup"><span data-stu-id="dac3c-175">This interface enables you to manage tenant-wide settings:</span></span>

- <span data-ttu-id="dac3c-176">**維度：** 檢視範本、 評估以及動作項目，可讓您建立自訂的樞紐分析表的篩選器的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-176">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="dac3c-177">**擁有者：** 指定每個動作項目擁有者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-177">**Owners:** Specify an owner for each Action Item.</span></span>
- <span data-ttu-id="dac3c-178">**客戶動作：** 管理動作項目包含在合規性管理員 （預覽） 的完整清單，並啟用/停用安全分數監視整合在一起安全分數的動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-178">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="dac3c-179">選取**租用戶管理**]，以開啟管理介面，並使用下列步驟來管理**維度**、**擁有者**，以及**客戶動作**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-179">Select **Tenant Management** to open the management interface, and use the following steps to manage **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="dac3c-180">Dimensions</span><span class="sxs-lookup"><span data-stu-id="dac3c-180">Dimensions</span></span>

<span data-ttu-id="dac3c-181">維度都是中繼資料集提供範本、 評估或動作項目相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-181">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="dac3c-182">維度使用機碼和值，其中維度索引鍵代表屬性，而維度值代表屬性的有效值的概念。</span><span class="sxs-lookup"><span data-stu-id="dac3c-182">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="dac3c-183">例如，合規性管理員中有三種類型的動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-183">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="dac3c-184">這些是由維度按鍵的**動作類型**和**文件**、**操作**，以及**技術**的維度值定義。</span><span class="sxs-lookup"><span data-stu-id="dac3c-184">They are defined by a Dimension Key of **Action Type** and Dimension Values of **Documentation**, **Operational**, and **Technical**.</span></span> <span data-ttu-id="dac3c-185">您可以編輯或刪除現有的維度。</span><span class="sxs-lookup"><span data-stu-id="dac3c-185">You can edit or delete existing Dimensions.</span></span>

### <a name="owners"></a><span data-ttu-id="dac3c-186">擁有者</span><span class="sxs-lookup"><span data-stu-id="dac3c-186">Owners</span></span>

<span data-ttu-id="dac3c-187">擁有者用來識別每個控制項負責合作對象。</span><span class="sxs-lookup"><span data-stu-id="dac3c-187">Owners are used to identify the responsible party for each control.</span></span> <span data-ttu-id="dac3c-188">Microsoft、 客戶，或是兩者都擁有所有內建的控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-188">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="dac3c-189">您可以建立自訂值的擁有者可以用來指定組織內更細微的責任。</span><span class="sxs-lookup"><span data-stu-id="dac3c-189">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="dac3c-190">例如，您可以建立代表特定群組、 小組或組織內的業務單位的擁有者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-190">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="dac3c-191">新增擁有者</span><span class="sxs-lookup"><span data-stu-id="dac3c-191">Add an Owner</span></span>

1. <span data-ttu-id="dac3c-192">開啟 [**租用戶管理**]，然後選取 [**擁有者**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-192">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="dac3c-193">選取 [ **+ 新增擁有者**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-193">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="dac3c-194">提供的名稱和描述的擁有者，並選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-194">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="dac3c-195">描述會顯示在 [擁有者] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dac3c-195">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="dac3c-196">編輯擁有者</span><span class="sxs-lookup"><span data-stu-id="dac3c-196">Edit an Owner</span></span>

<span data-ttu-id="dac3c-197">您無法編輯擁有者名稱，但您可以修改 [擁有者] 欄中顯示的描述。</span><span class="sxs-lookup"><span data-stu-id="dac3c-197">You can’t edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="dac3c-198">開啟 [**租用戶管理**]，然後選取 [**擁有者**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-198">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="dac3c-199">找出您想要編輯、 選取它旁的省略符號 （...），選取 [**編輯**擁有的者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-199">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="dac3c-200">視需要修改描述，並選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-200">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="dac3c-201">刪除擁有者</span><span class="sxs-lookup"><span data-stu-id="dac3c-201">Delete an Owner</span></span>

1. <span data-ttu-id="dac3c-202">開啟 [**租用戶管理**]，然後選取 [**擁有者**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-202">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="dac3c-203">找出您想要刪除，請選取其，旁邊的省略符號 （...），然後選取 [**刪除**的擁有者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-203">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="dac3c-204">出現確認訊息時，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-204">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="dac3c-205">客戶動作</span><span class="sxs-lookup"><span data-stu-id="dac3c-205">Customer Actions</span></span>

<span data-ttu-id="dac3c-206">客戶動作區域顯示所有客戶的所有範本及評估動作合規性管理員中 （預覽）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-206">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

![合規性管理員-新增使用者](media/compliance-manager-customer-actions.png)

<span data-ttu-id="dac3c-208">在快速，您可以請參閱巨集指令的標題、 擁有者、 類別、 強制執行 >，以及分數，並判斷是否它整合安全分數。</span><span class="sxs-lookup"><span data-stu-id="dac3c-208">At-a-glance, you can see an Action’s title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="dac3c-209">您可以依序展開 [巨集指令，然後選取 [**更多讀取**閱讀動作的描述，並存取任何說明中的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-209">You can expand an Action and select **Read More** to read the Action’s description and access any links in the description.</span></span> <span data-ttu-id="dac3c-210">啟用及停用安全分數整合，根據每個巨集指令，以及新增自訂動作，您也可以使用此介面。</span><span class="sxs-lookup"><span data-stu-id="dac3c-210">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="dac3c-211">具有安全分數整合功能的動作有這些 （請注意，自訂動作也會有旁邊的省略符號） 旁的省略符號 （...）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-211">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="dac3c-212">啟用或停用安全分數整合</span><span class="sxs-lookup"><span data-stu-id="dac3c-212">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="dac3c-213">選取您要修改，然後選取 [**編輯**巨集的指令的省略符號 （...）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-213">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="dac3c-214">切換開啟或關閉安全分數連續更新的參數來啟用或停用連續監視透過安全分數。</span><span class="sxs-lookup"><span data-stu-id="dac3c-214">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="dac3c-215">選取**儲存**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-215">Select **Save**.</span></span>

#### <a name="add-a-customer-action"></a><span data-ttu-id="dac3c-216">新增客戶巨集指令</span><span class="sxs-lookup"><span data-stu-id="dac3c-216">Add a customer action</span></span>

1. <span data-ttu-id="dac3c-217">選取 [ **+ 新增客戶巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-217">Select **+ Add Customer Action**.</span></span>
2. <span data-ttu-id="dac3c-218">提供在 [**標題**] 欄位中的巨集指令重複的標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-218">Provide a unique title for the Action in the **Title** field.</span></span>
3. <span data-ttu-id="dac3c-219">提供 「 合規性分數 （這可以是任何介於 1-99） 的**最大的合規性分數**欄位中的巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-219">Provide a Compliance Score for the Action in the **Maximum Compliance Score** field (this can be any number from 1-99).</span></span>
4. <span data-ttu-id="dac3c-220">使用 [**巨集指令類型**] 下拉式清單來指定您要新增的動作類型。</span><span class="sxs-lookup"><span data-stu-id="dac3c-220">Use the **Action Type** dropdown to specify the type of Action you are adding.</span></span> <span data-ttu-id="dac3c-221">如果不存在的動作類型，您可以將它新增將值新增至的動作類型維度索引鍵。</span><span class="sxs-lookup"><span data-stu-id="dac3c-221">If the Action Type does not exist, you can add it by adding the value to the Action Type dimension key.</span></span>
5. <span data-ttu-id="dac3c-222">使用 [**維度**] 下拉式清單來指定或巨集指令新增維度機碼和值。</span><span class="sxs-lookup"><span data-stu-id="dac3c-222">Use the **Dimensions** dropdown to specify or add dimension keys and values for the Action.</span></span>
6. <span data-ttu-id="dac3c-223">使用 [**擁有者**] 下拉式清單來指定巨集指令的擁有者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-223">Use the **Owner** dropdown to specify the owner for Action.</span></span>
7. <span data-ttu-id="dac3c-224">選取 [**+** 新增描述和說明，標題巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-224">Select **+** to add a description and description title for the Action.</span></span>
8. <span data-ttu-id="dac3c-225">選取**X** ] 來關閉 [說明] 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="dac3c-225">Select the **X** to close the Description blade.</span></span>
9. <span data-ttu-id="dac3c-226">選取 [**儲存**] 以儲存客戶巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-226">Select **Save** to save the Customer Action.</span></span>

#### <a name="edit-a-customer-action"></a><span data-ttu-id="dac3c-227">編輯客戶巨集指令</span><span class="sxs-lookup"><span data-stu-id="dac3c-227">Edit a customer action</span></span>

1. <span data-ttu-id="dac3c-228">選取您要修改，然後選取 [**編輯**巨集的指令的省略符號 （...）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-228">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="dac3c-229">編輯視，巨集指令，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-229">Edit the Action as desired, and select **Save**.</span></span>

#### <a name="delete-a-customer-action"></a><span data-ttu-id="dac3c-230">刪除客戶巨集指令</span><span class="sxs-lookup"><span data-stu-id="dac3c-230">Delete a customer action</span></span>

1. <span data-ttu-id="dac3c-231">選取您要修改，然後選取 [**刪除**的巨集指令的省略符號 （...）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-231">Select the ellipses (…) for the Action you want to modify and select **Delete**.</span></span>
2. <span data-ttu-id="dac3c-232">出現確認訊息時，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-232">When the confirmation message appears, select **Delete**.</span></span>

## <a name="assessments"></a><span data-ttu-id="dac3c-233">「 評估 」</span><span class="sxs-lookup"><span data-stu-id="dac3c-233">Assessments</span></span>

### <a name="add-an-assessment"></a><span data-ttu-id="dac3c-234">新增評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-234">Add an Assessment</span></span>
  
1. <span data-ttu-id="dac3c-235">在評估儀表板中，選取 [ **+ 新增評估**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-235">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="dac3c-236">[] 刀鋒視窗開啟時，請輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="dac3c-236">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="dac3c-237">**標題 （必要）：** 輸入您的評估的標題</span><span class="sxs-lookup"><span data-stu-id="dac3c-237">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="dac3c-238">**請選取範本 （必要）：** 選取標準或自訂範本</span><span class="sxs-lookup"><span data-stu-id="dac3c-238">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="dac3c-239">**請選取群組或加入新的群組 （必要）：** 選取現有的群組，或選擇新增新的群組，並提供唯一的群組名稱</span><span class="sxs-lookup"><span data-stu-id="dac3c-239">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="dac3c-240">**您想要將資料複製從現有的群組？（選用）：** 切換要啟用群組複本的控制項，然後：</span><span class="sxs-lookup"><span data-stu-id="dac3c-240">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="dac3c-241">**選取群組 （選用）：** 如果啟用群組複本時，選取要複製之群組</span><span class="sxs-lookup"><span data-stu-id="dac3c-241">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="dac3c-242">**實作詳細資料 （選用）：** 選取 [將實作詳細資料複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="dac3c-242">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="dac3c-243">**測試計劃 & 其他資訊 （選用）：** 選取 [複製測試計劃及其他資訊詳細資料] 以新的群組</span><span class="sxs-lookup"><span data-stu-id="dac3c-243">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="dac3c-244">**文件 （選用）：** 選取 [將文件複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="dac3c-244">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="dac3c-245">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-245">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="dac3c-246">新的評估會出現在評估儀表板上，並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="dac3c-246">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="dac3c-247">評估的標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-247">The title of the Assessment.</span></span>
- <span data-ttu-id="dac3c-248">評估，包括憑證、 環境及用於評估產品的尺寸。</span><span class="sxs-lookup"><span data-stu-id="dac3c-248">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="dac3c-249">上次修改的日期和它的建立的日期。</span><span class="sxs-lookup"><span data-stu-id="dac3c-249">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="dac3c-250">顯示百分比評估分數。</span><span class="sxs-lookup"><span data-stu-id="dac3c-250">The Assessment Score shown as a percentage.</span></span>
- <span data-ttu-id="dac3c-251">顯示 Microsoft 受管理] 和 [客戶所管理的評估控制項的數字的進度指標。</span><span class="sxs-lookup"><span data-stu-id="dac3c-251">Progress indicators that show the number of assessed Microsoft-managed and customer-manged controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="dac3c-252">從現有「評估」複製資訊</span><span class="sxs-lookup"><span data-stu-id="dac3c-252">Copying information from existing Assessments</span></span>

<span data-ttu-id="dac3c-253">當您建立評估時，您必須從現存的 group 複製資訊的選項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-253">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="dac3c-254">這可讓您可以套用至相同的控制項中新的 「 評估複製評估輸入的資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-254">This allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="dac3c-255">例如，如果您有一組所有 FFIEC 相關評估貴組織中，您可以從現有 「 評估 」 複製下列資訊：</span><span class="sxs-lookup"><span data-stu-id="dac3c-255">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="dac3c-256">實作詳細資料</span><span class="sxs-lookup"><span data-stu-id="dac3c-256">Implementation Details</span></span>
- <span data-ttu-id="dac3c-257">測試計劃 & 其他資訊</span><span class="sxs-lookup"><span data-stu-id="dac3c-257">Test Plan & Additional Information</span></span>
- <span data-ttu-id="dac3c-258">文件</span><span class="sxs-lookup"><span data-stu-id="dac3c-258">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="dac3c-259">將資訊從現有評估複製到新的 「 評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-259">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="dac3c-260">在評估儀表板中，選取 [ **+ 新增評估**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-260">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="dac3c-261">在 [**新增評估**] 視窗中，完成下列的資訊</span><span class="sxs-lookup"><span data-stu-id="dac3c-261">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="dac3c-262">**標題 （必要）：** 輸入您的評估的標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-262">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="dac3c-263">**請選取範本 （必要）：** 選取一個標準或自訂的範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-263">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="dac3c-264">**請選取群組或加入新的群組 （必要）：** 選擇 [**加入新的群組**，並提供唯一的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="dac3c-264">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="dac3c-265">**您想要將資料複製從現有的群組？（選用）：** 切換入啟用群組複製到控制項，然後:-**選取群組 （選用）：** 如果啟用群組複本時，選取要複製之群組。</span><span class="sxs-lookup"><span data-stu-id="dac3c-265">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="dac3c-266">- **實作詳細資料 （選用）：** 選取 [將實作詳細資料複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="dac3c-266">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="dac3c-267">- **測試計劃 & 其他資訊 （選用）：** 選取 [複製測試計劃及其他資訊詳細資料] 以新的群組。</span><span class="sxs-lookup"><span data-stu-id="dac3c-267">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="dac3c-268">- **文件 （選用）：** 選取 [將文件複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="dac3c-268">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="dac3c-269">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-269">Select **Save** to create the Assessment.</span></span>

### <a name="viewing-assessments"></a><span data-ttu-id="dac3c-270">檢視評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-270">Viewing Assessments</span></span>

#### <a name="view-an-assessment"></a><span data-ttu-id="dac3c-271">檢視評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-271">View an Assessment</span></span>
  
1. <span data-ttu-id="dac3c-272">在評估儀表板中，選取評估名稱以開啟它，檢視動作項目和控制項資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-272">In the Assessments dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="dac3c-273">以下是 Office 365 和 ISO 27001 評估的範例。</span><span class="sxs-lookup"><span data-stu-id="dac3c-273">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="dac3c-274">第一個檢視說明新的動作項目檢視合規性管理員中 （預覽）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-274">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合規性管理員中的動作項目檢視](media/compliance-manager-action-items.png)

<span data-ttu-id="dac3c-276">動作會依字母順序列出和每個巨集指令會指派分數以及擁有者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-276">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="dac3c-277">選取**更多讀取**連結至讀取每個動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-277">Select  the **Read More** link to read the details of each Action.</span></span> 

![合規性管理員中的動作項目檢視](media/compliance-manager-actions-read-more.png)

<span data-ttu-id="dac3c-279">選取來管理、 指派、 實作和測試巨集指令的 [**檢閱**] 連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-279">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="dac3c-280">以下是範例巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-280">Below is an example Action.</span></span>

![合規性管理員動作檢視](media/compliance-manager-action.png)

<span data-ttu-id="dac3c-282">在舊版的合規性管理員中，實作需求的工作流程執行控制層級。</span><span class="sxs-lookup"><span data-stu-id="dac3c-282">In previous versions of Compliance Manager, the workflow for implementing requirements was performed at the Control level.</span></span> <span data-ttu-id="dac3c-283">法務人員會指派給某人實作控制項的控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-283">A compliance officer would assign a control to someone to implement the control.</span></span> <span data-ttu-id="dac3c-284">有了這兩個缺點：</span><span class="sxs-lookup"><span data-stu-id="dac3c-284">There were two drawbacks to this:</span></span>

- <span data-ttu-id="dac3c-285">控制項通常有多個動作，以及向誰控制項已指派，可能無法適當人員來完成實作控制項所需的所有動作的使用者相關聯</span><span class="sxs-lookup"><span data-stu-id="dac3c-285">Controls often had multiple actions associated with them, and the user to whom a control was assigned, might not be the right person to complete all actions that were required to implement the control</span></span>
- <span data-ttu-id="dac3c-286">將個別工作結合成單一動作禁止的訊號和遙測用來自動記錄在合規性管理員 （預覽） 租用戶組態變更的集合。</span><span class="sxs-lookup"><span data-stu-id="dac3c-286">Combining separate tasks into a single Action prevented the collection of the signals and telemetry that is used to automatically record tenant configuration changes in Compliance Manager (Preview).</span></span>

<span data-ttu-id="dac3c-287">合規性管理員中 （預覽），工作流程程序已經從 「 控制層級的巨集指令層級。</span><span class="sxs-lookup"><span data-stu-id="dac3c-287">In Compliance Manager (Preview), the workflow process has moved from the Control level to the Action level.</span></span> <span data-ttu-id="dac3c-288">當檢閱巨集指令，下列欄位可用於管理巨集指令的工作流程：</span><span class="sxs-lookup"><span data-stu-id="dac3c-288">When reviewing an Action, the following fields can be used to manage the Action workflow:</span></span>

- <span data-ttu-id="dac3c-289">**指派給使用者：** 選取 [選擇或輸入應該要指派此巨集指令的使用者名稱此欄位。</span><span class="sxs-lookup"><span data-stu-id="dac3c-289">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="dac3c-290">您可以捲動清單，或輸入要尋找它的名稱，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="dac3c-290">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="dac3c-291">**管理文件：** 您可以上傳 Office 文件、 影像檔和螢幕擷取畫面，在 CSV 或 TXT，與 Pdf PowerShell 輸出的表單中實作的證據。</span><span class="sxs-lookup"><span data-stu-id="dac3c-291">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="dac3c-292">**實作狀態：** 用來指出目前實作狀態的巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-292">**Implementation Status:** Used to indicate the Action’s current implementation status.</span></span> <span data-ttu-id="dac3c-293">可能的值為不實作、 Implemented、 替代實作、 計劃，而不是在範圍。</span><span class="sxs-lookup"><span data-stu-id="dac3c-293">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="dac3c-294">**實作日期：** 採取動作時的日期。</span><span class="sxs-lookup"><span data-stu-id="dac3c-294">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="dac3c-295">**測試結果：** 用來表示實作驗證的結果。</span><span class="sxs-lookup"><span data-stu-id="dac3c-295">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="dac3c-296">可能的值為不評估、 Passed、 失敗低風險、 失敗中度風險、 失敗高風險，而不是在範圍。</span><span class="sxs-lookup"><span data-stu-id="dac3c-296">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="dac3c-297">**測試日期：** 發生驗證日期。</span><span class="sxs-lookup"><span data-stu-id="dac3c-297">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="dac3c-298">**實作附註：** 輸入您的組織，以及您想要包含任何備忘稿實作詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-298">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="dac3c-299">**測試計劃：** 輸入此巨集指令，以及您想要包含任何備忘稿的測試計劃詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-299">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="dac3c-300">**的其他資訊：** 輸入此巨集指令或如何實作您的組織，以及任何您想要包含的附註中的任何其他資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-300">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="dac3c-301">合規性管理員 （預覽） 也會包含在舊版中找到控制項為基礎的樞紐分析表。</span><span class="sxs-lookup"><span data-stu-id="dac3c-301">Compliance Manager (Preview) also includes the control-based pivot found in previous versions.</span></span> <span data-ttu-id="dac3c-302">選取 [檢視它的**控制項資訊**儀表板]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-302">Select the **Controls Info** dashboard to view it.</span></span> <span data-ttu-id="dac3c-303">您可以檢視在評估與範本的層級的控制項的資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-303">You can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="dac3c-304">以下是範例控制項資訊儀表板的 「 評估 」。</span><span class="sxs-lookup"><span data-stu-id="dac3c-304">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合規性管理員控制項資訊檢視](media/compliance-manager-controls-info.png)

<span data-ttu-id="dac3c-306">針對評估，會顯示在控制項資訊儀表板：</span><span class="sxs-lookup"><span data-stu-id="dac3c-306">For Assessments, the Controls Info dashboard displays:</span></span>

- <span data-ttu-id="dac3c-307">若要選取的群組，以檢視 （當使用多個群組） 的 [**群組**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-307">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="dac3c-308">選取要檢視哪些評估**評估**] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="dac3c-308">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="dac3c-309">有關所選的評估、 中繼資料包括：</span><span class="sxs-lookup"><span data-stu-id="dac3c-309">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="dac3c-310">**評估控制項**顯示控制項的總數透過評估控制項數目進度列指示器。</span><span class="sxs-lookup"><span data-stu-id="dac3c-310">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="dac3c-311">評估，以百分比來顯示目前**合規性分數**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-311">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="dac3c-312">**憑證**和用於評估**產品**詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-312">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="dac3c-313">目前**狀態**和評估的上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="dac3c-313">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="dac3c-314">評估**範圍 Services 中**的清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-314">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="dac3c-315">依據控制項系列，客戶動作和 Microsoft 實作詳細資料的連結，將控制項的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="dac3c-315">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="dac3c-316">**您的動作**會顯示您可以執行以滿足某些或所有控制項的需求的客戶動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-316">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control’s requirements.</span></span> <span data-ttu-id="dac3c-317">多個控制項都有與其，相關聯的多個動作和控制項相關聯的所有動作都顯示在此處。</span><span class="sxs-lookup"><span data-stu-id="dac3c-317">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="dac3c-318">以下的動作有相同 UI 中的以動作儀表板中所列。</span><span class="sxs-lookup"><span data-stu-id="dac3c-318">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="dac3c-319">**Microsoft 動作**會顯示來自 Microsoft 的內部架構套用至選取的憑證控制項的控制項的清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-319">**Microsoft Actions** displays the list of controls from Microsoft’s internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="dac3c-320">針對每個內部的控制項，選取 [ **Implemented**查看 Microsoft 的實作和測試詳細資料，以及測試結果和測試的日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dac3c-320">For each internal control, select **Implemented** to see Microsoft’s implementation and test details, along with the test result and test date, as shown below.</span></span>

![合規性管理員 Microsoft 巨集指令檢視](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a><span data-ttu-id="dac3c-322">匯出評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-322">Export an Assessment</span></span>

<span data-ttu-id="dac3c-323">您的組織中的符合性專案關係人或外部稽核者及管理者，您可以評估匯出至 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="dac3c-323">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="dac3c-324">報表會建立報告的時間與日期起評估的快照集。</span><span class="sxs-lookup"><span data-stu-id="dac3c-324">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="dac3c-325">報表包含所有的 Microsoft 和客戶管理控制措施詳細資料，評估，控制項實作狀態] 控制項測試日期、 測試結果，並提供連結上傳的辨識項的文件。</span><span class="sxs-lookup"><span data-stu-id="dac3c-325">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span> <span data-ttu-id="dac3c-326">您應該匯出評估報告之前封存評估，因為封存的評估不會保留上傳的文件的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-326">You should export the Assessment report prior to archiving an assessment because archived assessments do not retain links to uploaded documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="dac3c-327">匯出評估報告</span><span class="sxs-lookup"><span data-stu-id="dac3c-327">Export an Assessment report</span></span>
  
1. <span data-ttu-id="dac3c-328">合規性管理員儀表板上選取**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dac3c-328">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="dac3c-329">**群組**及**評估**在下拉式功能表中選取您想要匯出的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-329">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="dac3c-330">選取 [**匯出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="dac3c-330">Select the **Export** button.</span></span>

<span data-ttu-id="dac3c-331">評估報告是在您的瀏覽器工作階段中下載為 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="dac3c-331">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="dac3c-332">Excel 檔案的檔案名稱預設為評估的標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-332">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="archive-a-template-or-an-assessment"></a><span data-ttu-id="dac3c-333">封存的範本或評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-333">Archive a Template or an Assessment</span></span>

<span data-ttu-id="dac3c-334">當您完成與範本或評估，不再需要以便符合規範時，您就可以進行封存。</span><span class="sxs-lookup"><span data-stu-id="dac3c-334">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can archive it.</span></span> <span data-ttu-id="dac3c-335">保存的範本或評估時，則會從預設檢視，移除，您必須檢查顯示已封存] 核取方塊以顯示它。</span><span class="sxs-lookup"><span data-stu-id="dac3c-335">When a Template or Assessment is archived, it is removed from the default view, and you must check the Show Archived checkbox to display it.</span></span>

![合規性管理員 Microsoft 巨集指令檢視](media/compliance-manager-archive-assessment-view.png)
  
> [!IMPORTANT]
> <span data-ttu-id="dac3c-337">封存的評估不會保留其上傳的辨識項文件的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-337">Archived Assessments do not retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="dac3c-338">強烈建議您將匯出的評估封存之前保留在報表中的辨識項文件的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-338">It is highly recommended that you export the Assessment before archiving to retain links to the evidence documents in the report.</span></span>
  
#### <a name="archive-a-template"></a><span data-ttu-id="dac3c-339">封存的範本</span><span class="sxs-lookup"><span data-stu-id="dac3c-339">Archive a Template</span></span>

1. <span data-ttu-id="dac3c-340">開啟**範本**儀表板。</span><span class="sxs-lookup"><span data-stu-id="dac3c-340">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="dac3c-341">找出您想要選取 [封存] 圖示與封存的範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-341">Locate the Template you want to archive and select the archive icon.</span></span>
3. <span data-ttu-id="dac3c-342">當您看到確認訊息時，選取 [**封存**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-342">When you see the confirmation message, select **Archive**.</span></span>

#### <a name="archive-an-assessment"></a><span data-ttu-id="dac3c-343">封存評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-343">Archive an Assessment</span></span>

1. <span data-ttu-id="dac3c-344">開啟 [**評估**儀表板]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-344">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="dac3c-345">從包含您想要封存評估] 下拉式清單中選取的**群組**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-345">Select the **Group** from the dropdown that contains the Assessment you want to archive.</span></span>
3. <span data-ttu-id="dac3c-346">找出您想要選取 [封存] 圖示與封存的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-346">Locate the Assessment you want to archive and select the archive icon.</span></span>
4. <span data-ttu-id="dac3c-347">當您看到確認訊息時，選取 [**封存**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-347">When you see the confirmation message, select **Archive**.</span></span>

#### <a name="view-archived-assessments"></a><span data-ttu-id="dac3c-348">檢視封存的評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-348">View archived Assessments</span></span>
  
1. <span data-ttu-id="dac3c-349">開啟 [**評估**儀表板] 索引標籤，然後檢查**顯示已封存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-349">Open the **Assessments** dashboard tab and check the **Show Archived** checkbox.</span></span>
2. <span data-ttu-id="dac3c-350">封存的評估會出現在 [**封存評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="dac3c-350">The archived assessments appear in the **Archived Assessments** section.</span></span>
3. <span data-ttu-id="dac3c-351">選取要開啟並檢視評估的評估名稱。</span><span class="sxs-lookup"><span data-stu-id="dac3c-351">Select the Assessment name to open and view the Assessment.</span></span>

#### <a name="activate-an-archived-assessment"></a><span data-ttu-id="dac3c-352">啟用封存的評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-352">Activate an archived Assessment</span></span>

1. <span data-ttu-id="dac3c-353">在**評估**] 索引標籤，然後選取 [**顯示已封存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-353">On the **Assessments** tab and select the **Show Archived** checkbox.</span></span>
2. <span data-ttu-id="dac3c-354">封存的評估會出現在 [**封存評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="dac3c-354">The archived assessments appear in the **Archived Assessments** section.</span></span>
3. <span data-ttu-id="dac3c-355">找出您想要啟動，然後選取 [啟動] 圖示的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-355">Locate the Assessment you want to activate and select the activate icon.</span></span>
4. <span data-ttu-id="dac3c-356">當您看到確認訊息時，選取 [**啟動**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-356">When you see the confirmation message, select **Activate**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="dac3c-357">控制項和動作</span><span class="sxs-lookup"><span data-stu-id="dac3c-357">Controls and Actions</span></span>

<span data-ttu-id="dac3c-358">控制項和動作都是使用合規性管理員中 （預覽） 主要資料樞紐分析表。</span><span class="sxs-lookup"><span data-stu-id="dac3c-358">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="dac3c-359">控制項樞紐分析表，存在於舊版合規性管理員中，已增強，可以在相同的控制項系列中顯示 [Microsoft] 和 [客戶控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-359">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="dac3c-360">此合併的檢視讓您更容易查看完整共同分擔每個控制項為基礎。</span><span class="sxs-lookup"><span data-stu-id="dac3c-360">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="dac3c-361">巨集指令樞紐分析表的新合規性管理員中 （預覽），其設計旨在提供簡化的檢視所有 Microsoft 建議的動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-361">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="dac3c-362">控制項</span><span class="sxs-lookup"><span data-stu-id="dac3c-362">Controls</span></span>

<span data-ttu-id="dac3c-363">控制項可以從控制項資訊儀表板檢視。</span><span class="sxs-lookup"><span data-stu-id="dac3c-363">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="dac3c-364">控制項代表從標準、 憑證、 規定或架構的需求。</span><span class="sxs-lookup"><span data-stu-id="dac3c-364">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="dac3c-365">若要將這些需求對應跨多個標準、 法規等等，並關聯動作，每個項目都會被視為是控制項架構。</span><span class="sxs-lookup"><span data-stu-id="dac3c-365">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="dac3c-366">例如，控制架構，例如] 區段中，由已細分規定，例如 HIPAA，並用 HIPAA 控制項合規性管理員中相同的編號配置為那些] 區段中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dac3c-366">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合規性管理員 Microsoft 控制項詳細資料](media/compliance-manager-control-details.png)

<span data-ttu-id="dac3c-368">有三種類型的控制項：</span><span class="sxs-lookup"><span data-stu-id="dac3c-368">There are three types of controls:</span></span>

1. <span data-ttu-id="dac3c-369">**Microsoft 管理控制措施：** 這些都是控制項，只有 Microsoft 具有責任。</span><span class="sxs-lookup"><span data-stu-id="dac3c-369">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="dac3c-370">它們會出現在方塊中的範本，並由 Microsoft 所加入到合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="dac3c-370">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="dac3c-371">**客戶管理控制措施：** 這些都是控制項，僅客戶有責任。</span><span class="sxs-lookup"><span data-stu-id="dac3c-371">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="dac3c-372">它們會出現在方塊中的範本，並會新增到合規性管理員的客戶。</span><span class="sxs-lookup"><span data-stu-id="dac3c-372">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="dac3c-373">**共用管理控制：** 這些是控制項責任 Microsoft 與客戶之間的共用位置。</span><span class="sxs-lookup"><span data-stu-id="dac3c-373">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="dac3c-374">這些會出現在方塊中的範本，並由 Microsoft 新增到合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="dac3c-374">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="dac3c-375">客戶也可以編輯或停用 Microsoft 管理控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-375">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="dac3c-376">動作項目</span><span class="sxs-lookup"><span data-stu-id="dac3c-376">Actions Items</span></span>

<span data-ttu-id="dac3c-377">動作項目是建議的工作的實作需求的標準或法規，或若要測試，確認，請確定並記錄貴組織的實作需求。</span><span class="sxs-lookup"><span data-stu-id="dac3c-377">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="dac3c-378">一或多個控制項與動作相關聯。</span><span class="sxs-lookup"><span data-stu-id="dac3c-378">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="dac3c-379">每個控制項都有一或多個動作相關聯，以及每個動作可與一或多個控制項相關聯。</span><span class="sxs-lookup"><span data-stu-id="dac3c-379">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="dac3c-380">動作是核心工作流程在合規性管理員 （預覽） 的一部分，因為它們是已指派、 追蹤，並驗證您的組織的物件。</span><span class="sxs-lookup"><span data-stu-id="dac3c-380">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="dac3c-381">指派動作項目</span><span class="sxs-lookup"><span data-stu-id="dac3c-381">Assign Action Items</span></span>
  
1. <span data-ttu-id="dac3c-382">在**動作項目**儀表板中，選取包含您想要指派其動作評估工作的**群組**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-382">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="dac3c-383">在 [**評估**] 下拉式清單中，選取您想要指派，其巨集指令的評估或從若要查看所有可用的動作] 下拉式清單中選取 [**全部]** 。</span><span class="sxs-lookup"><span data-stu-id="dac3c-383">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="dac3c-384">找出您想要指派，巨集的指令，在 [**擁有者**] 欄中，選取 [**檢閱**、 **Implemented**或**測試**的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-384">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, **Implemented** or **Test**.</span></span>
4. <span data-ttu-id="dac3c-385">選取 [**指派的使用者**] 欄位中，並會出現在組織中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-385">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="dac3c-386">捲動清單，並選取使用者或篩選來選取使用者所輸入的使用者名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-386">Scroll the list and select user or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="dac3c-387">在實作附註] 欄位中，輸入您想要傳達指派的使用者任何附註。</span><span class="sxs-lookup"><span data-stu-id="dac3c-387">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="dac3c-388">選取 [**儲存**] 以指派巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-388">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="dac3c-389">重新指派動作項目</span><span class="sxs-lookup"><span data-stu-id="dac3c-389">Reassign Action Items</span></span>

<span data-ttu-id="dac3c-390">此函數可讓組織能夠移除任何使用中或未完成相依性的使用者帳戶，只要重新指派給新的使用者動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-390">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="dac3c-391">在**動作項目**儀表板中，選取包含您想要重新指派其動作評估工作的**群組**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-391">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="dac3c-392">在 [**評估**] 下拉式清單中，選取您想要重新指派，其巨集指令的評估或從 [若要查看所有可用的動作] 下拉式清單中選取 [**所有**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-392">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="dac3c-393">找出您想要重新指派，巨集的指令，在 [**擁有者**] 欄中，選取 [**檢閱**、 **Implemented**，或**測試**的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-393">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="dac3c-394">從**指派的使用者**] 欄位中，刪除現有的使用者與 [從使用者的清單中選擇不同的使用者或篩選來選取使用者所輸入的使用者名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-394">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="dac3c-395">在實作附註] 欄位中，輸入您要向使用者傳達任何附註。</span><span class="sxs-lookup"><span data-stu-id="dac3c-395">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="dac3c-396">選取 [**儲存**] 以重新指派動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-396">Select **Save** to reassign the Action.</span></span>

## <a name="templates"></a><span data-ttu-id="dac3c-397">範本</span><span class="sxs-lookup"><span data-stu-id="dac3c-397">Templates</span></span>

<span data-ttu-id="dac3c-398">範本為基礎物件合規性管理員中 （預覽） 相關聯的產品與憑證 （例如標準、 法規、 控制項 framework 等等）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-398">A Template is the base object in Compliance Manager (Preview) that is associated with a Product and a Certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="dac3c-399">範本可檢視及新增範本儀表板。</span><span class="sxs-lookup"><span data-stu-id="dac3c-399">Templates can be viewed and added from the Templates dashboard.</span></span>

![合規性管理員 Microsoft 範本儀表板](media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="dac3c-401">儀表板會顯示每個範本，以及憑證並產品與相關聯範本，的日期所在範本建立以及上次修改日期，客戶及 Microsoft 管理的控制措施，最大合規性分數的數目範本，以及範本 （例如，已核准擱置核准、 匯入） 的狀態。</span><span class="sxs-lookup"><span data-stu-id="dac3c-401">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

<span data-ttu-id="dac3c-402">內建的範本每個具有內建評估與其相關聯，但您可以建立其他內建範本為基礎的 「 評估 」 和您可以匯入您自己的範本，並建立自訂關閉這些基礎的 「 評估 」。</span><span class="sxs-lookup"><span data-stu-id="dac3c-402">The built-in Templates each have a built-in Assessment associated with them, but you can create additional Assessments based on built-in Templates, and you can import your own Templates, and create custom Assessments based off those.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="dac3c-403">建立範本</span><span class="sxs-lookup"><span data-stu-id="dac3c-403">Create a Template</span></span>

<span data-ttu-id="dac3c-404">藉由複製現有的範本或匯入自訂的範本，您可以建立範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-404">You can create a Template by copying an existing Template or by importing a custom Template.</span></span> <span data-ttu-id="dac3c-405">沒有特定的格式和範本的資料，必須使用的結構描述或其不會匯入到合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="dac3c-405">There is a specific format and schema that must be used for Template data or it will not import into Compliance Manager.</span></span> <span data-ttu-id="dac3c-406">可以在此處下載與正確的結構描述及資料範例檔案。</span><span class="sxs-lookup"><span data-stu-id="dac3c-406">A file with the correct schema and sample data can be downloaded from here.</span></span>
<span data-ttu-id="dac3c-407">每個自訂的範本應為個別 Excel 中的活頁簿 （.xls 或.xlsx 格式），其中包含五個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="dac3c-407">Each custom Template should be in a separate Excel workbook (in .xls or .xlsx format) that contains five tabs:</span></span>

1. <span data-ttu-id="dac3c-408">範本評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-408">Template-Assessment</span></span>
2. <span data-ttu-id="dac3c-409">ControlFamily</span><span class="sxs-lookup"><span data-stu-id="dac3c-409">ControlFamily</span></span>
3. <span data-ttu-id="dac3c-410">動作</span><span class="sxs-lookup"><span data-stu-id="dac3c-410">Actions</span></span>
4. <span data-ttu-id="dac3c-411">擁有權</span><span class="sxs-lookup"><span data-stu-id="dac3c-411">Ownership</span></span>
5. <span data-ttu-id="dac3c-412">Dimensions</span><span class="sxs-lookup"><span data-stu-id="dac3c-412">Dimensions</span></span>

<span data-ttu-id="dac3c-413">下面會使用每個索引標籤內的結構描述。</span><span class="sxs-lookup"><span data-stu-id="dac3c-413">The schema used within each tab is detailed below.</span></span>

#### <a name="template-assessment-tab"></a><span data-ttu-id="dac3c-414">範本評估] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="dac3c-414">Template-Assessment tab</span></span>

<span data-ttu-id="dac3c-415">此索引標籤具有單一資料行：</span><span class="sxs-lookup"><span data-stu-id="dac3c-415">This tab has a single column:</span></span>

- <span data-ttu-id="dac3c-416">**inScopeServices**： 產品或服務範圍內的逗號分隔的清單範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-416">**inScopeServices**: Comma-delimited list of products or services that are in-scope for the Template.</span></span>

#### <a name="controlfamily-tab"></a><span data-ttu-id="dac3c-417">ControlFamily] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="dac3c-417">ControlFamily tab</span></span>

<span data-ttu-id="dac3c-418">此索引標籤包含定義對應至列在 [動作] 索引標籤上的動作控制項的資料行，並包含像是控制項名稱、 系列、 標題和描述的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-418">This tab includes columns that define the controls that are mapped to the Actions listed on the Actions tab, and includes details like control name, family, title, and description.</span></span>  <span data-ttu-id="dac3c-419">此索引標籤的順序必須 Excel 內下方所列順序，資料行是：</span><span class="sxs-lookup"><span data-stu-id="dac3c-419">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="dac3c-420">**controlName:** 從憑證/標準/規定] 等的控制項名稱。</span><span class="sxs-lookup"><span data-stu-id="dac3c-420">**controlName:** Control name from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="dac3c-421">**controlFamily:** 從憑證/標準、 規定等控制項系列。</span><span class="sxs-lookup"><span data-stu-id="dac3c-421">**controlFamily:** Control family from certification/standard, regulation, etc.</span></span>
- <span data-ttu-id="dac3c-422">**controlTitle:** 從憑證/標準/規定等控制項標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-422">**controlTitle:** Control title from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="dac3c-423">**controlDescription:** 控制從憑證/標準/規定等等的描述。</span><span class="sxs-lookup"><span data-stu-id="dac3c-423">**controlDescription:** Control description from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="dac3c-424">**controlVersion:** 選用的控制項的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-424">**controlVersion:** Optional control version info.</span></span>  <span data-ttu-id="dac3c-425">範例： NIST 800-53 的目前值是反轉 4，因此 controlVersion 為 4。</span><span class="sxs-lookup"><span data-stu-id="dac3c-425">Example: for NIST 800-53, the current value is Rev 4, so the controlVersion is 4.</span></span>  <span data-ttu-id="dac3c-426">對於 CSA CCM，通常是 3.0.1。</span><span class="sxs-lookup"><span data-stu-id="dac3c-426">For CSA CCM, it is 3.0.1.</span></span>
- <span data-ttu-id="dac3c-427">**isDisabled:** 使用 TRUE 或 FALSE，指出是否已停用控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-427">**isDisabled:** Use TRUE or FALSE to indicate whether the control has been disabled.</span></span>
- <span data-ttu-id="dac3c-428">**controlType:** 使用 [副本] 表示這些是客戶管理控制措施。</span><span class="sxs-lookup"><span data-stu-id="dac3c-428">**controlType:** Use CC to indicate these are customer-managed controls.</span></span>
- <span data-ttu-id="dac3c-429">**controlComplianceScore:** 指派給控制項的所有動作的分數的總和。</span><span class="sxs-lookup"><span data-stu-id="dac3c-429">**controlComplianceScore:** Sum of the score of all Actions assigned to the Control.</span></span>
- <span data-ttu-id="dac3c-430">**controlActionTitle:** 雙 semi colon 分隔清單的所有 actionTitles 此所列在 [動作] 索引標籤上的控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-430">**controlActionTitle:** Double semi-colon-delimited list of all actionTitles for this control as listed on the Actions tab.</span></span> 

#### <a name="actions-tab"></a><span data-ttu-id="dac3c-431">動作] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="dac3c-431">Actions tab</span></span>

<span data-ttu-id="dac3c-432">此索引標籤包含定義個別的動作，資料行，其包含巨集指令標題、 擁有權和維度等的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-432">This tab includes columns that define individual Actions, and it includes details like action title, ownership, and dimensions.</span></span> <span data-ttu-id="dac3c-433">此索引標籤的順序必須 Excel 內下方所列順序，資料行是：</span><span class="sxs-lookup"><span data-stu-id="dac3c-433">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="dac3c-434">**actionTitle:** 巨集指令的標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-434">**actionTitle:** Title of the action.</span></span> <span data-ttu-id="dac3c-435">每個標題必須是唯一的並建議使用 Pascal 案例。</span><span class="sxs-lookup"><span data-stu-id="dac3c-435">Each title must be unique, and we recommend using Pascal case.</span></span>
- <span data-ttu-id="dac3c-436">**actionRelatedODVs:** 雙以分號分隔的清單是父項 actionTitle] 欄中列出的子系的 actionTitles。</span><span class="sxs-lookup"><span data-stu-id="dac3c-436">**actionRelatedODVs:** Double semicolon-delimited list of actionTitles that are parents of the child listed in the actionTitle column.</span></span> <span data-ttu-id="dac3c-437">在父/子關聯性，父項會代表高浮水印。</span><span class="sxs-lookup"><span data-stu-id="dac3c-437">In a parent/child relationship, the parent represents the high watermark.</span></span> <span data-ttu-id="dac3c-438">因此，如果您完成父巨集指令時，您也完成所有的子系動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-438">Thus, if you complete a parent action, you also complete all child actions.</span></span> <span data-ttu-id="dac3c-439">例如，當您有類似的需求，但不同標準定義的值，例如密碼長度] 中，其中的 15 個字元，至少需要一個標準/規定，而另一個需要至少要有 12 或 10。</span><span class="sxs-lookup"><span data-stu-id="dac3c-439">For example, when you have similar requirements but different standard-defined values, such as password length, where one standard/regulation requires a minimum of 15 characters, and another requires a minimum of 12 or 10.</span></span> <span data-ttu-id="dac3c-440">15 是在這個範例中，父，如果您設定最少的 15 個字元，您也可以滿足建議中其他評估 12 或 10 個字元的動作。</span><span class="sxs-lookup"><span data-stu-id="dac3c-440">15 would be the parent in this example, and if you configure a minimum of 15 characters, you also satisfy the actions that recommend 12 or 10 characters in other assessments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dac3c-441">ActionRelatedODVs 欄是必要的資料行結構描述。不過，不提供在合規性管理員 （預覽） 功能 （相關動作）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-441">The actionRelatedODVs column is a required column for the schema; however, the feature (related actions) is not available in Compliance Manager (Preview).</span></span>  <span data-ttu-id="dac3c-442">它已排定在後續版本中新增。</span><span class="sxs-lookup"><span data-stu-id="dac3c-442">It is scheduled to be added in a later release.</span></span>

- <span data-ttu-id="dac3c-443">**actionDimensionValues:** 雙以分號分隔的清單適用維度的維度] 索引標籤上，使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="dac3c-443">**actionDimensionValues:** Double semicolon-delimited list of applicable dimensions from the Dimensions tab, using the following format:</span></span>

    ```
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    <span data-ttu-id="dac3c-444">例如：</span><span class="sxs-lookup"><span data-stu-id="dac3c-444">For example:</span></span>

    ```
    Product::Office 365;;Certification::NIST CSF
    ```

    <span data-ttu-id="dac3c-445">即使已列出維度儀表板上，必須匯入檔案中，[維度] 索引標籤上列出所有的自訂範本中所使用的維度。</span><span class="sxs-lookup"><span data-stu-id="dac3c-445">All Dimensions that are used in a custom Template must be listed on the Dimensions tab of the import file, even if they are already listed on the Dimensions dashboard.</span></span>
- <span data-ttu-id="dac3c-446">**actionScore:** 每個巨集指令，代表該動作的分數的數值。</span><span class="sxs-lookup"><span data-stu-id="dac3c-446">**actionScore:** Numeric value for each Action, which represents the score for that action.</span></span> <span data-ttu-id="dac3c-447">我們建議的下列計分模型使用內建的評估，根據每個巨集指令的用途和強制執行。</span><span class="sxs-lookup"><span data-stu-id="dac3c-447">We recommend following the scoring model used by the built-in assessments, which is based on each Action’s purpose and enforcement.</span></span>
- <span data-ttu-id="dac3c-448">**actionOwnership:** 雙以分號分隔的清單擁有人。</span><span class="sxs-lookup"><span data-stu-id="dac3c-448">**actionOwnership:** Double semicolon-delimited list of Owners.</span></span> <span data-ttu-id="dac3c-449">在 [擁有權] 索引標籤上都必須包含所有列出的擁有者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-449">All listed Owners must be included on the Ownership tab.</span></span>
- <span data-ttu-id="dac3c-450">**actionDescription:** 每個動作，這必須是唯一的文字。</span><span class="sxs-lookup"><span data-stu-id="dac3c-450">**actionDescription:** Text of each Action, which must be unique.</span></span> <span data-ttu-id="dac3c-451">此欄位支援 Markdown 語言，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dac3c-451">This field supports Markdown Language as described below.</span></span>

#### <a name="ownership-tab"></a><span data-ttu-id="dac3c-452">擁有權] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="dac3c-452">Ownership tab</span></span>

<span data-ttu-id="dac3c-453">此索引標籤包含定義每個動作的擁有者的欄。</span><span class="sxs-lookup"><span data-stu-id="dac3c-453">This tab includes columns that define owners for each action.</span></span>  <span data-ttu-id="dac3c-454">此索引標籤的順序必須 Excel 內下方所列順序，資料行是：</span><span class="sxs-lookup"><span data-stu-id="dac3c-454">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="dac3c-455">**ownershipName:** 擁有者/負責廠商唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="dac3c-455">**ownershipName:** Unique name of owner/responsible party.</span></span>
- <span data-ttu-id="dac3c-456">**ownershipDescription:** 擁有者/負責廠商的描述。</span><span class="sxs-lookup"><span data-stu-id="dac3c-456">**ownershipDescription:** Description of the owner/responsible party.</span></span>

#### <a name="dimensions-tab"></a><span data-ttu-id="dac3c-457">維度] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="dac3c-457">Dimensions tab</span></span>

<span data-ttu-id="dac3c-458">此索引標籤包含定義可與動作相關聯的維度的欄。</span><span class="sxs-lookup"><span data-stu-id="dac3c-458">This tab includes columns that define the Dimensions that can be associated with an Action.</span></span>  <span data-ttu-id="dac3c-459">此索引標籤的順序必須 Excel 內下方所列順序，資料行是：</span><span class="sxs-lookup"><span data-stu-id="dac3c-459">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="dac3c-460">**dimensionKey:** 用於維度的金鑰的清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-460">**dimensionKey:** List of Keys used for Dimensions.</span></span> <span data-ttu-id="dac3c-461">例如，產品，憑證，等等。</span><span class="sxs-lookup"><span data-stu-id="dac3c-461">For example, Product, Certification, etc.</span></span>
- <span data-ttu-id="dac3c-462">**dimensionValue:** 每個維度機碼的唯一值。</span><span class="sxs-lookup"><span data-stu-id="dac3c-462">**dimensionValue:** Unique value for each dimension key.</span></span> <span data-ttu-id="dac3c-463">例如，Office 365、 Intune、 Azure、 自訂的產品，等等。</span><span class="sxs-lookup"><span data-stu-id="dac3c-463">For example, Office 365, Intune, Azure, Custom Product, etc.</span></span>
- <span data-ttu-id="dac3c-464">**allowMultiSelect:** 多個維度值表示可以選取單一維度機碼中使用 TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="dac3c-464">**allowMultiSelect:** Use TRUE or FALSE to indicate that multiple dimension values can be selected for a single dimension key.</span></span>

#### <a name="using-markdown-language-in-description-fields"></a><span data-ttu-id="dac3c-465">描述欄位中使用 Markdown 語言</span><span class="sxs-lookup"><span data-stu-id="dac3c-465">Using Markdown Language in Description Fields</span></span>

<span data-ttu-id="dac3c-466">範本和評估支援 Markdown 語言使用的一些文字項目和格式設定。</span><span class="sxs-lookup"><span data-stu-id="dac3c-466">Templates and Assessments support the use of Markdown language for some text elements and formatting.</span></span>  <span data-ttu-id="dac3c-467">有三種格式的項目 Markdown 語言使用合規性管理員中：</span><span class="sxs-lookup"><span data-stu-id="dac3c-467">There are three formatting elements of Markdown language that are used in Compliance Manager:</span></span>

- <span data-ttu-id="dac3c-468">項目符號及編號清單</span><span class="sxs-lookup"><span data-stu-id="dac3c-468">Bullets and Numbered lists</span></span>
- <span data-ttu-id="dac3c-469">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="dac3c-469">Hyperlinks</span></span>
- <span data-ttu-id="dac3c-470">粗體</span><span class="sxs-lookup"><span data-stu-id="dac3c-470">Boldface</span></span>

<span data-ttu-id="dac3c-471">項目符號被當成星號，而不是 Word 或 Excel 項目符號。</span><span class="sxs-lookup"><span data-stu-id="dac3c-471">Bullets are represented as asterisks instead of Word or Excel bullets.</span></span> <span data-ttu-id="dac3c-472">例如：</span><span class="sxs-lookup"><span data-stu-id="dac3c-472">For example:</span></span>

```
* Item A
* Item B
* Item C
```

<span data-ttu-id="dac3c-473">以數字，但有空格的縮排 （每層級的三個空格） 及僅用於所有子層級 （例如，沒有字母） 的數字表示數字。</span><span class="sxs-lookup"><span data-stu-id="dac3c-473">Numbers are represented as numbers, but with spaces for indentation (three spaces per level) and only numbers used for all sublevels (for example, no letters).</span></span>  <span data-ttu-id="dac3c-474">例如：</span><span class="sxs-lookup"><span data-stu-id="dac3c-474">For example:</span></span>
   1. <span data-ttu-id="dac3c-475">項目 A</span><span class="sxs-lookup"><span data-stu-id="dac3c-475">Item A</span></span>
   2. <span data-ttu-id="dac3c-476">項目 B</span><span class="sxs-lookup"><span data-stu-id="dac3c-476">Item B</span></span>
      1. <span data-ttu-id="dac3c-477">子項目 A</span><span class="sxs-lookup"><span data-stu-id="dac3c-477">Sub-item A</span></span>
      2. <span data-ttu-id="dac3c-478">子項目 B</span><span class="sxs-lookup"><span data-stu-id="dac3c-478">Sub-item B</span></span>
   3. <span data-ttu-id="dac3c-479">項目 C</span><span class="sxs-lookup"><span data-stu-id="dac3c-479">Item C</span></span>
   4. <span data-ttu-id="dac3c-480">項目 D</span><span class="sxs-lookup"><span data-stu-id="dac3c-480">Item D</span></span>
      1. <span data-ttu-id="dac3c-481">子項目 A</span><span class="sxs-lookup"><span data-stu-id="dac3c-481">Sub-item A</span></span>
      2. <span data-ttu-id="dac3c-482">子項目 B</span><span class="sxs-lookup"><span data-stu-id="dac3c-482">Sub-item B</span></span>
   5. <span data-ttu-id="dac3c-483">項目 E</span><span class="sxs-lookup"><span data-stu-id="dac3c-483">Item E</span></span>

<span data-ttu-id="dac3c-484">超連結所建構方式置於立即旁 close 括號括號括住的超連結文字和本身的超連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-484">Hyperlinks are constructed by placing brackets around the hyperlink text and the hyperlink itself in parentheses immediately next to the close bracket.</span></span>  <span data-ttu-id="dac3c-485">例如：</span><span class="sxs-lookup"><span data-stu-id="dac3c-485">For example:</span></span>

```
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
<span data-ttu-id="dac3c-486">這段文字轉譯，如下所示： 按一下[這裡](https://www.microsoft.com)以移至 Microsoft 的首頁。</span><span class="sxs-lookup"><span data-stu-id="dac3c-486">This text renders as follows:  Click [here](https://www.microsoft.com) to go to Microsoft’s home page.</span></span>
<span data-ttu-id="dac3c-487">在上述範例所示，合規性管理員中不會呈現 Url 與底線。</span><span class="sxs-lookup"><span data-stu-id="dac3c-487">As shown in the above example, Compliance Manager does not render URLs with underlining.</span></span>

<span data-ttu-id="dac3c-488">粗體文字是設為粗體文字的每一邊僅由兩個星號。</span><span class="sxs-lookup"><span data-stu-id="dac3c-488">Boldface text is just two asterisks on each side of the text to be bolded.</span></span>  <span data-ttu-id="dac3c-489">例如：</span><span class="sxs-lookup"><span data-stu-id="dac3c-489">For example:</span></span>

```
**This text will render in bold**
```
<span data-ttu-id="dac3c-490">**此文字會以粗體顯示呈現**</span><span class="sxs-lookup"><span data-stu-id="dac3c-490">**This text renders in bold**</span></span>

### <a name="create-a-template"></a><span data-ttu-id="dac3c-491">建立範本</span><span class="sxs-lookup"><span data-stu-id="dac3c-491">Create a Template</span></span>

<span data-ttu-id="dac3c-492">藉由複製現有的範本，或藉由從 Excel 匯入範本資料，您可以建立範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-492">You can create a Template by copying an existing Template or by importing Template data from Excel.</span></span> <span data-ttu-id="dac3c-493">當從 Excel 匯入資料，範本會需要兩個不同的合規性管理員中系統管理員，若要發佈的資料 （若要發行，其中並核准一個）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-493">When importing data from Excel, the Template requires two different Compliance Manager Administrators to publish the data (one to publish, and one to approve).</span></span>

#### <a name="create-a-template-by-copying-an-existing-template"></a><span data-ttu-id="dac3c-494">藉由複製現有的範本建立範本</span><span class="sxs-lookup"><span data-stu-id="dac3c-494">Create a Template by copying an existing Template</span></span>

1. <span data-ttu-id="dac3c-495">開啟**範本**儀表板，然後選取 [ **+ 新增範本**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-495">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="dac3c-496">在 [**輸入範本名稱**] 欄位中，提供範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="dac3c-496">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="dac3c-497">檢查**複製從現有的範本**] 核取方塊，然後選取您想要複製從下拉式清單的範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-497">Check the **Copy from an existing template** checkbox and select the template you want to copy from the dropdown.</span></span>
4. <span data-ttu-id="dac3c-498">選擇性地新增任何其他的維度。</span><span class="sxs-lookup"><span data-stu-id="dac3c-498">Optionally add any additional Dimensions.</span></span>
5. <span data-ttu-id="dac3c-499">選取 [**新增至儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-499">Select **Add to Dashboard**.</span></span>

#### <a name="create-a-template-by-importing-data"></a><span data-ttu-id="dac3c-500">建立範本匯入資料</span><span class="sxs-lookup"><span data-stu-id="dac3c-500">Create a Template by importing data</span></span>

1. <span data-ttu-id="dac3c-501">開啟**範本**儀表板，然後選取 [ **+ 新增範本**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-501">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="dac3c-502">在 [**輸入範本名稱**] 欄位中，提供範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="dac3c-502">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="dac3c-503">從可用清單中選取至少一個維度。</span><span class="sxs-lookup"><span data-stu-id="dac3c-503">Select at least one Dimension from the available list.</span></span>
4. <span data-ttu-id="dac3c-504">選取 [**瀏覽]** 以瀏覽至匯入檔案的位置，加以選取，然後選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-504">Select **Browse** to navigate to the location of the import file, select it, and select **Open**.</span></span>
5. <span data-ttu-id="dac3c-505">匯入檔案將會進行驗證，並指出控制項和已偵測到的控制項系列的數目。</span><span class="sxs-lookup"><span data-stu-id="dac3c-505">The import file will be validated and indicate the number of controls and control families that were detected.</span></span> <span data-ttu-id="dac3c-506">如果沒有錯誤，連結會提供給已修改的舊版匯入檔案，其中包含錯誤的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-506">If there are errors, a link will be provided to a modified version of the import file that includes error details.</span></span> <span data-ttu-id="dac3c-507">將匯入資料之前，必須先解決所有錯誤。</span><span class="sxs-lookup"><span data-stu-id="dac3c-507">All errors must be resolved before the data will be imported.</span></span>
6. <span data-ttu-id="dac3c-508">一旦資料會通過驗證，請選取 [**新增至儀表板**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-508">Once the data passes validation, select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="dac3c-509">匯入的範本會出現在 [**範本**儀表板上，且其具有**匯入**的狀態。</span><span class="sxs-lookup"><span data-stu-id="dac3c-509">The imported Template appears on the **Templates** dashboard and it has a status of **Imported**.</span></span> <span data-ttu-id="dac3c-510">選取的省略符號 （...），然後選取 [**發佈**到發佈範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-510">Select the ellipses (…) and select **Publish** to publish the Template.</span></span> <span data-ttu-id="dac3c-511">出現確認訊息時，選取 [**發行**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-511">When the confirmation message appears, select **Publish**.</span></span> <span data-ttu-id="dac3c-512">**等待核准**範本狀態變更。</span><span class="sxs-lookup"><span data-stu-id="dac3c-512">The Template status changes to **Pending Approval**.</span></span>
8. <span data-ttu-id="dac3c-513">合規性管理員中系統管理員角色與另一位使用者必須核准的範本儀表板中的範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-513">Another user with the Compliance Manager Administrator role must approve the Template in the Templates dashboard.</span></span> <span data-ttu-id="dac3c-514">他們必須選取省略符號 （...），然後選取 [**核准**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-514">They must select the ellipses (…) and select **Approve**.</span></span> <span data-ttu-id="dac3c-515">出現確認訊息時，選取 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-515">When the confirmation message appears, select **Approve**.</span></span> <span data-ttu-id="dac3c-516">範本現已可供使用。</span><span class="sxs-lookup"><span data-stu-id="dac3c-516">The Template is now ready for use.</span></span>

### <a name="customize-a-template"></a><span data-ttu-id="dac3c-517">自訂範本</span><span class="sxs-lookup"><span data-stu-id="dac3c-517">Customize a Template</span></span>

<span data-ttu-id="dac3c-518">可透過其他自訂控制項的自訂範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-518">Templates can be customized through the additional of custom controls.</span></span> <span data-ttu-id="dac3c-519">所有自訂控制項視為客戶管理控制措施。</span><span class="sxs-lookup"><span data-stu-id="dac3c-519">All custom controls are considered customer-managed Controls.</span></span>

#### <a name="add-a-custom-control-to-a-template"></a><span data-ttu-id="dac3c-520">將自訂控制項新增至範本。</span><span class="sxs-lookup"><span data-stu-id="dac3c-520">Add a custom control to a Template</span></span>

1. <span data-ttu-id="dac3c-521">開啟您要修改的**範本**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-521">Open the **Template** you want to modify.</span></span>
2. <span data-ttu-id="dac3c-522">選取 [ **+ 新增**自訂控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-522">Select **+ Add** custom control.</span></span>
3. <span data-ttu-id="dac3c-523">從下拉式清單選取**控制項系列**，或如果它不存在，請輸入新的控制項系列。</span><span class="sxs-lookup"><span data-stu-id="dac3c-523">Select a **Control Family** from the dropdown or enter a new control family if it does not exist.</span></span>
4. <span data-ttu-id="dac3c-524">提供唯一的名稱或 ID 的**控制項識別碼**] 欄位中的控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-524">Provide a unique name or ID for the control in the **Control ID** field.</span></span>
5. <span data-ttu-id="dac3c-525">提供在 [**標題**] 欄位中的控制項標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-525">Provide the control title in the **Title** field.</span></span>
6. <span data-ttu-id="dac3c-526">提供需求和在 [**描述**] 欄位中的控制項的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="dac3c-526">Provide the requirements and other information for the control in the **Description** field.</span></span>
7. <span data-ttu-id="dac3c-527">選取 [**指派客戶**巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-527">Select **Assign Customer** Action.</span></span>
8. <span data-ttu-id="dac3c-528">找出您想要指派給控制項的動作：</span><span class="sxs-lookup"><span data-stu-id="dac3c-528">Locate the Action(s) you want to assign to the control:</span></span>
    - <span data-ttu-id="dac3c-529">使用**篩選維度**可使用指派給動作的維度，找出，並列出。</span><span class="sxs-lookup"><span data-stu-id="dac3c-529">Use **Filter by Dimension** to use dimensions assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="dac3c-530">使用**篩選擁有者**可使用指派給動作而後，找出，並列出。</span><span class="sxs-lookup"><span data-stu-id="dac3c-530">Use **Filter by Owner** to use the owner(s) assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="dac3c-531">清單類型的動作，從下拉式清單選取**動作類型**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-531">Select an **Action Type** from the dropdown to list Actions by type.</span></span>
    - <span data-ttu-id="dac3c-532">輸入動作來找出，並將它的標題。</span><span class="sxs-lookup"><span data-stu-id="dac3c-532">Enter the title of the Action to locate and list it.</span></span>
9. <span data-ttu-id="dac3c-533">步驟 8 中使用的準則，會出現的**比對的動作**清單。</span><span class="sxs-lookup"><span data-stu-id="dac3c-533">Using the criteria in Step 8, a list of **Matching Action(s)** will appear.</span></span> <span data-ttu-id="dac3c-534">選取您想要指派給控制項的第一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dac3c-534">Select the first Action you want to assign to the control.</span></span>
10. <span data-ttu-id="dac3c-535">動作的詳細資料會出現。</span><span class="sxs-lookup"><span data-stu-id="dac3c-535">The details of the Action appear.</span></span> <span data-ttu-id="dac3c-536">選取您想要使用並選取 [**完成**] 的**描述**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-536">Select the **Description** you want to use and select **Done**.</span></span>
11. <span data-ttu-id="dac3c-537">針對您想要指派每個額外動作重複步驟 9 到 10。</span><span class="sxs-lookup"><span data-stu-id="dac3c-537">Repeat Steps 9 and 10 for each additional Action you want to assign.</span></span>
12. <span data-ttu-id="dac3c-538">當已選取所有適用的動作，請選取 [**指派**。</span><span class="sxs-lookup"><span data-stu-id="dac3c-538">When all applicable Actions have been selected, select **Assign**.</span></span>
13. <span data-ttu-id="dac3c-539">選取 [**儲存**] 以儲存新的控制項。</span><span class="sxs-lookup"><span data-stu-id="dac3c-539">Select **Save** to save the new control.</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="dac3c-540">將範本匯出至 JSON</span><span class="sxs-lookup"><span data-stu-id="dac3c-540">Export a Template to JSON</span></span>

<span data-ttu-id="dac3c-541">合規性管理員 （預覽） 也支援將範本匯出至 JavaScript Object Notation (JSON) 格式。</span><span class="sxs-lookup"><span data-stu-id="dac3c-541">Compliance Manager (Preview) also supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="dac3c-542">這可讓您的 exchange 支援 JSON 其他系統的合規性管理員資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-542">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="dac3c-543">報表</span><span class="sxs-lookup"><span data-stu-id="dac3c-543">Reports</span></span>

<span data-ttu-id="dac3c-544">您的組織中的符合性專案關係人或外部稽核者及管理者，您可以評估匯出至 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="dac3c-544">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="dac3c-545">報表是日期起評估的快照集與匯出的時間。</span><span class="sxs-lookup"><span data-stu-id="dac3c-545">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="dac3c-546">報表會包含 Microsoft 和客戶管理控制措施詳細資料，如評估、 控制項實作狀態、 日期控制項測試、 測試結果與上傳的辨識項文件的連結。</span><span class="sxs-lookup"><span data-stu-id="dac3c-546">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="dac3c-547">封存它們，因為封存的評估不會保留到連結上傳文件之前，您應將匯出的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-547">You should export Assessments before archiving them because archived Assessments do not retain links to uploaded documents.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="dac3c-548">匯出評估</span><span class="sxs-lookup"><span data-stu-id="dac3c-548">Export an Assessment</span></span>

1. <span data-ttu-id="dac3c-549">合規性管理員儀表板上選取**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dac3c-549">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="dac3c-550">評估與群組] 下拉式清單功能表中選取您想要匯出的評估。</span><span class="sxs-lookup"><span data-stu-id="dac3c-550">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="dac3c-551">選取 [匯出]。</span><span class="sxs-lookup"><span data-stu-id="dac3c-551">Select Export.</span></span> <span data-ttu-id="dac3c-552">評估匯出為 Excel 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="dac3c-552">The Assessment export is downloaded as an Excel file.</span></span>

![合規性管理員評估 Excel 報表](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a><span data-ttu-id="dac3c-554">權限</span><span class="sxs-lookup"><span data-stu-id="dac3c-554">Permissions</span></span>

<span data-ttu-id="dac3c-555">下表說明每個合規性管理員權限，並可讓使用者執行。</span><span class="sxs-lookup"><span data-stu-id="dac3c-555">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="dac3c-556">表也會指出每個權限指派的角色。</span><span class="sxs-lookup"><span data-stu-id="dac3c-556">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="dac3c-557">**Azure AD 全域讀者**</span><span class="sxs-lookup"><span data-stu-id="dac3c-557">**Azure AD Global Reader**</span></span>|<span data-ttu-id="dac3c-558">**合規性管理員讀取者**</span><span class="sxs-lookup"><span data-stu-id="dac3c-558">**Compliance Manager Reader**</span></span>|<span data-ttu-id="dac3c-559">**合規性參與者**</span><span class="sxs-lookup"><span data-stu-id="dac3c-559">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="dac3c-560">**合規性管理員評估者**</span><span class="sxs-lookup"><span data-stu-id="dac3c-560">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="dac3c-561">**合規性管理員管理者**</span><span class="sxs-lookup"><span data-stu-id="dac3c-561">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="dac3c-562">**入口網站管理員**</span><span class="sxs-lookup"><span data-stu-id="dac3c-562">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dac3c-563">**讀取資料：** 使用者可以讀取但無法編輯資料 （但不包括範本資料和租用戶管理）。</span><span class="sxs-lookup"><span data-stu-id="dac3c-563">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="dac3c-564">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-564">X</span></span> | <span data-ttu-id="dac3c-565">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-565">X</span></span> | <span data-ttu-id="dac3c-566">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-566">X</span></span> | <span data-ttu-id="dac3c-567">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-567">X</span></span> | <span data-ttu-id="dac3c-568">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-568">X</span></span>  | <span data-ttu-id="dac3c-569">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-569">X</span></span>  |<span data-ttu-id="dac3c-570">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-570">X</span></span> |
|<span data-ttu-id="dac3c-571">**編輯資料：** 使用者可以編輯除了 （但不包括範本資料和租用戶管理） 的測試結果] 和 [測試日期欄位以外的所有欄位。</span><span class="sxs-lookup"><span data-stu-id="dac3c-571">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="dac3c-572">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-572">X</span></span> | <span data-ttu-id="dac3c-573">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-573">X</span></span>  | <span data-ttu-id="dac3c-574">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-574">X</span></span> | <span data-ttu-id="dac3c-575">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-575">X</span></span> |
|<span data-ttu-id="dac3c-576">**編輯測試結果：** 使用者可以編輯 [測試結果和測試日期] 欄位。</span><span class="sxs-lookup"><span data-stu-id="dac3c-576">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="dac3c-577">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-577">X</span></span> | <span data-ttu-id="dac3c-578">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-578">X</span></span> | <span data-ttu-id="dac3c-579">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-579">X</span></span> |
|<span data-ttu-id="dac3c-580">**管理評估：** 使用者可以建立、 封存和刪除 「 評估 」。</span><span class="sxs-lookup"><span data-stu-id="dac3c-580">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="dac3c-581">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-581">X</span></span> | <span data-ttu-id="dac3c-582">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-582">X</span></span> |
|<span data-ttu-id="dac3c-583">**管理主要資料：** 使用者可以檢視、 編輯和刪除範本資料和承租人管理資料。</span><span class="sxs-lookup"><span data-stu-id="dac3c-583">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="dac3c-584">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-584">X</span></span> | <span data-ttu-id="dac3c-585">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-585">X</span></span> |
|<span data-ttu-id="dac3c-586">**管理使用者：** 使用者可以將其他使用者新增至 「 助讀程式、 參與者、 評估者，與系統管理員角色其組織中。</span><span class="sxs-lookup"><span data-stu-id="dac3c-586">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="dac3c-587">只有那些與您的組織中的全域系統管理員角色的使用者可以新增或移除入口網站系統管理員角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="dac3c-587">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="dac3c-588">X</span><span class="sxs-lookup"><span data-stu-id="dac3c-588">X</span></span> |
