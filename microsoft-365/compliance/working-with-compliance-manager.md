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
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用合規性管理員來追蹤、指派及驗證 Microsoft 產品相關的法規遵從性活動。
ms.openlocfilehash: e12250c6f78759b2298bfb5ebba6ae79918a0fd9
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023390"
---
# <a name="working-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="d75ed-103">使用 Microsoft 合規性管理員（預覽）</span><span class="sxs-lookup"><span data-stu-id="d75ed-103">Working with Microsoft Compliance Manager (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d75ed-104">Microsoft 合規性管理員是一種儀表板和管理工具，可提供您的資料保護和合規性 stature 的摘要，以及改善資料保護和合規性的建議。</span><span class="sxs-lookup"><span data-stu-id="d75ed-104">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="d75ed-105">合規性管理員中提供的客戶動作為建議。</span><span class="sxs-lookup"><span data-stu-id="d75ed-105">The customer actions provided in Compliance Manager are recommendations.</span></span> <span data-ttu-id="d75ed-106">在實施之前，您的組織可以評估這些建議在其各項法規環境中的效能。</span><span class="sxs-lookup"><span data-stu-id="d75ed-106">It is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="d75ed-107">您不應將合規性管理員中找到的建議視為合規性的保證。</span><span class="sxs-lookup"><span data-stu-id="d75ed-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="d75ed-108">Access 合規性管理員</span><span class="sxs-lookup"><span data-stu-id="d75ed-108">Access Compliance Manager</span></span>

<span data-ttu-id="d75ed-109">合規性管理員可以從 Microsoft 服務信任入口網站存取。</span><span class="sxs-lookup"><span data-stu-id="d75ed-109">Compliance Manager is accessible from the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="d75ed-110">任何具有 Microsoft 帳戶或 Azure Active Directory 組織帳戶的人都可以存取合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="d75ed-110">Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>

1. <span data-ttu-id="d75ed-111">請移至 [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3)。</span><span class="sxs-lookup"><span data-stu-id="d75ed-111">Go to [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3).</span></span>

2. <span data-ttu-id="d75ed-112">使用您的 Microsoft 服務帳戶登入，這是您的 Office 365、Microsoft 365 或 Azure Active Directory （Azure AD）使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d75ed-112">Sign in with your Microsoft service account, which is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-113">在服務信任入口網站中，選取 [**合規性管理員**]，這是具有最新功能的預覽版本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-113">In the Service Trust Portal, select **Compliance Manager**, which is the preview version with the most current features.</span></span> <span data-ttu-id="d75ed-114">請勿選取 **[合規性管理員（經典）**]，其中包含本檔尚未涵蓋的早期版本功能。</span><span class="sxs-lookup"><span data-stu-id="d75ed-114">Do not select **Compliance Manager (classic)**, which contains early-release features not covered by this documentation.</span></span>

## <a name="administration"></a><span data-ttu-id="d75ed-115">系統管理</span><span class="sxs-lookup"><span data-stu-id="d75ed-115">Administration</span></span>

<span data-ttu-id="d75ed-116">只有全域系統管理員可以使用特定的管理功能，而且只有當以全域系統管理員帳戶登入時才會顯示。</span><span class="sxs-lookup"><span data-stu-id="d75ed-116">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="d75ed-117">全域管理員可以：</span><span class="sxs-lookup"><span data-stu-id="d75ed-117">The global administrator can:</span></span>
- [<span data-ttu-id="d75ed-118">指派使用者角色</span><span class="sxs-lookup"><span data-stu-id="d75ed-118">Assign user roles</span></span>](#assigning-compliance-manager-roles-to-users)
- [<span data-ttu-id="d75ed-119">開啟和關閉自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="d75ed-119">Turn on and off automatic Secure Score updates</span></span>](#controlling-automatic-secure-score-updates)
- [<span data-ttu-id="d75ed-120">設定使用者隱私權設定</span><span class="sxs-lookup"><span data-stu-id="d75ed-120">Configure user privacy settings</span></span>](#configuring-user-privacy-settings)
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="d75ed-121">將合規性管理員角色指派給使用者</span><span class="sxs-lookup"><span data-stu-id="d75ed-121">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="d75ed-122">一旦管理員將合規性管理員角色指派給其他使用者，這些使用者便可在合規性管理員中查看資料，並執行其角色所決定的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-122">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="d75ed-123">管理員也可以在[Azure Active Directory （AZURE AD）中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)指派使用者的全域讀取者角色，授與合規性管理員的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="d75ed-123">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="d75ed-124">每個合規性管理員角色都具有稍有不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="d75ed-124">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="d75ed-125">您可以查看指派給每個角色的許可權、查看哪些使用者屬於哪些角色，以及透過服務信任入口網站新增或移除該角色中的使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-125">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="d75ed-126">選取 [**管理**] 功能表項目目，然後選擇 [要查看的**設定**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-126">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理功能表：已選取設定](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="d75ed-128">若要新增使用者或從合規性管理員角色中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-128">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="d75ed-129">請移至 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="d75ed-129">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="d75ed-130">使用您的 Azure Active Directory 全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="d75ed-130">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="d75ed-131">在服務信任入口網站頂端功能表列上，選取 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-131">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="d75ed-132">在 [**選取角色**] 下拉式清單中，選取您要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="d75ed-132">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="d75ed-133">新增至每個角色的使用者會列在 [選取角色]\*\*\*\* 頁面上。</span><span class="sxs-lookup"><span data-stu-id="d75ed-133">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="d75ed-134">若要將使用者新增至此角色，請選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-134">To add users to this role, select **Add**.</span></span> <span data-ttu-id="d75ed-135">在 [**新增使用者**] 對話方塊中，選取 [使用者] 欄位。</span><span class="sxs-lookup"><span data-stu-id="d75ed-135">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="d75ed-136">您可以在可用的使用者清單中向內移動，或是開始輸入使用者名稱，以根據您的搜尋字詞篩選清單。</span><span class="sxs-lookup"><span data-stu-id="d75ed-136">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="d75ed-137">選取要將該帳戶新增至以該角色布建的 [**新增使用者**] 清單中的使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-137">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="d75ed-138">如果您想要同時新增多個使用者，請開始輸入使用者名稱以篩選清單，然後選取要新增至清單的使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-138">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="d75ed-139">選取 [**儲存**]，將選取的角色布建給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-139">Select **Save** to provision the selected role to these users.</span></span> 

    ![合規性管理員-新增使用者](../media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="d75ed-141">若要移除此角色中的使用者，請選取使用者，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-141">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合規性管理員-刪除使用者](../media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="d75ed-143">控制自動安全分數更新</span><span class="sxs-lookup"><span data-stu-id="d75ed-143">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="d75ed-144">您可以使用下列步驟，針對所有動作，關閉所有動作，關閉所有動作，或透過個別動作設定安全分數更新。</span><span class="sxs-lookup"><span data-stu-id="d75ed-144">Secure Score updates can be turned on automatically for all actions, turned off for all actions, or set by individual action by following these steps.</span></span>

1. <span data-ttu-id="d75ed-145">使用您的全域系統管理員帳戶登入[服務信任入口網站](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="d75ed-145">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="d75ed-146">在服務信任入口網站頂端功能表列上，按一下 [**其他**] 下的 [系統**管理員**]，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-146">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="d75ed-147">在 [**安全分數**] 索引標籤中，選取對應的按鈕來**開啟所有動作**、**關閉所有動作**，或**設定每個動作。**</span><span class="sxs-lookup"><span data-stu-id="d75ed-147">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="d75ed-148">如果您選擇 [**依動作設定]，請**採取下列額外步驟，為個別動作開啟安全分數更新：</span><span class="sxs-lookup"><span data-stu-id="d75ed-148">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="d75ed-149">從上方功能表中選取 [**合規性管理員**] （附注：不要選取「合規性管理員（古典）」）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-149">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="d75ed-150">在螢幕的右上角選取 [**租使用者管理**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-150">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="d75ed-151">在 [**客戶動作**] 窗格上，在 [**受影響的動作**] 欄下，以省略號（**...**）尋找您的預定動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-151">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="d75ed-152">按一下省略號，然後選取 [**編輯]。**</span><span class="sxs-lookup"><span data-stu-id="d75ed-152">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="d75ed-153">將**安全分數連續更新**切換開關切換為 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="d75ed-153">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="d75ed-154">選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="d75ed-154">Select **Save.**</span></span> <span data-ttu-id="d75ed-155">安全分數連續監控現在已開啟該動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-155">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="d75ed-156">**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。</span><span class="sxs-lookup"><span data-stu-id="d75ed-156">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="d75ed-157">合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-157">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

### <a name="configuring-user-privacy-settings"></a><span data-ttu-id="d75ed-158">設定使用者隱私權設定</span><span class="sxs-lookup"><span data-stu-id="d75ed-158">Configuring user privacy settings</span></span>

<span data-ttu-id="d75ed-159">某些法規要求組織能夠刪除使用者的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-159">Certain regulations require an organization to be able to delete user history data.</span></span> <span data-ttu-id="d75ed-160">若要啟用此功能，**使用者隱私權設定**功能可讓系統管理員：</span><span class="sxs-lookup"><span data-stu-id="d75ed-160">To enable this, the **User Privacy Settings** functions allow administrators to:</span></span>
  
- [<span data-ttu-id="d75ed-161">使用者搜尋</span><span class="sxs-lookup"><span data-stu-id="d75ed-161">Search for a user</span></span>](#search-for-a-user)

- [<span data-ttu-id="d75ed-162">匯出帳戶資料歷程記錄的報告</span><span class="sxs-lookup"><span data-stu-id="d75ed-162">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)

- [<span data-ttu-id="d75ed-163">重新指派動作項目</span><span class="sxs-lookup"><span data-stu-id="d75ed-163">Reassign action items</span></span>](#reassign-action-items)

- [<span data-ttu-id="d75ed-164">刪除使用者資料歷程記錄</span><span class="sxs-lookup"><span data-stu-id="d75ed-164">Delete user data history</span></span>](#delete-user-data-history)
    
![合規性管理員管理 - 使用者隱私權設定功能](../media/067d6c6a-712a-4dc2-9b99-de2fa4417dc3.png)
  
#### <a name="search-for-a-user"></a><span data-ttu-id="d75ed-166">搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="d75ed-166">Search for a user</span></span>

<span data-ttu-id="d75ed-167">若要搜尋使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="d75ed-167">To search for a user account:</span></span>
  
1. <span data-ttu-id="d75ed-168">輸入使用者電子郵件地址的別名 (位在 @ 符號左邊的資訊)，然後按一下右邊的網域尾碼清單以選擇網域名稱。</span><span class="sxs-lookup"><span data-stu-id="d75ed-168">Enter the user email address by typing in the alias (the information to the left of the @ symbol) and choosing the domain name by clicking the domain suffix list on the right.</span></span> <span data-ttu-id="d75ed-169">如果您的組織有多個註冊的網域，您可以加倍檢查電子郵件地址功能變數名稱尾碼，以確定其是否正確。</span><span class="sxs-lookup"><span data-stu-id="d75ed-169">If your organization has multiple registered domains, you can double check the email address domain name suffix to ensure that it is correct.</span></span>
    
2. <span data-ttu-id="d75ed-170">當您輸入正確的使用者名稱時，請選取 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-170">When you have the username correctly entered, select **Search**.</span></span>
    
3. <span data-ttu-id="d75ed-171">如果找不到使用者帳戶，將會在頁面上顯示「找不到使用者」錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="d75ed-171">If the user account is not found, the error message 'User not found' will be displayed on the page.</span></span> <span data-ttu-id="d75ed-172">請檢查使用者的電子郵件地址資訊，必要時進行修正，然後選取 [**搜尋**] 再試一次。</span><span class="sxs-lookup"><span data-stu-id="d75ed-172">Check the user's email address information, make corrections as necessary and select **Search** to try again.</span></span>
    
4. <span data-ttu-id="d75ed-173">找到使用者帳戶時，按鈕的文字會從 [搜尋]\*\*\*\* 變更為 [清除]\*\*\*\*，這表示傳回的使用者帳戶是額外功能的作業內容，將會顯示在下面，且執行這些功能將會套用到這個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d75ed-173">If user account is found, the text of the button changes from **Search** to **Clear**, which indicates that the returned user account is the operating context for the additional functions that will be displayed below, that running those functions will apply to this user account.</span></span>
    
5. <span data-ttu-id="d75ed-174">若要清除搜尋結果並搜尋不同的使用者，請選取 [**清除**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-174">To clear search results and search for a different user, select **Clear**.</span></span>
    
#### <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="d75ed-175">匯出帳戶資料歷程記錄的報告</span><span class="sxs-lookup"><span data-stu-id="d75ed-175">Export a report of account data history</span></span>

<span data-ttu-id="d75ed-176">識別使用者帳戶之後，您可能會想要產生一份與此帳戶相關的相依性報告。</span><span class="sxs-lookup"><span data-stu-id="d75ed-176">Once the user account has been identified, you may wish to generate a report of dependencies that exist linked to this account.</span></span> <span data-ttu-id="d75ed-177">這個資訊可以讓您重新指派開放的動作項目，或是確保存取先前上傳的證明。</span><span class="sxs-lookup"><span data-stu-id="d75ed-177">This information allows you to reassign open action items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="d75ed-178">若要產生並匯出報告：</span><span class="sxs-lookup"><span data-stu-id="d75ed-178">To generate and export a report:</span></span>
  
1. <span data-ttu-id="d75ed-179">選取 [**匯出**]，以產生及下載目前指派給傳回之使用者帳戶的合規性管理員控制項動作專案，以及該使用者上傳的檔案清單。</span><span class="sxs-lookup"><span data-stu-id="d75ed-179">select **Export** to generate and download a report of the Compliance Manager control action items currently assigned to the returned user account and the list of documents uploaded by that user.</span></span> <span data-ttu-id="d75ed-180">如果沒有任何指派的動作或上傳的檔，錯誤訊息就會顯示「沒有此使用者的資料」。</span><span class="sxs-lookup"><span data-stu-id="d75ed-180">If there are no assigned actions or uploaded documents, an error message displays "No data for this user."</span></span>

2. <span data-ttu-id="d75ed-181">報告會在使用中瀏覽器視窗的背景下載。</span><span class="sxs-lookup"><span data-stu-id="d75ed-181">The report downloads in the background of the active browser window.</span></span> <span data-ttu-id="d75ed-182">如果您看不到下載快顯視窗，請檢查您的瀏覽器下載歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="d75ed-182">If you don't see a download pop up, check your browser download history.</span></span>

3. <span data-ttu-id="d75ed-183">開啟文件以檢視報告資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-183">Open the document to review the report data.</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-p117">這並不是歷程記錄報告，會保留並顯示動作項目作業歷程記錄的狀態變更。所產生的報告是報告執行時所指派項目的控制項動作項目 (寫入報表的日期和時間戳記) 的快照。例如，如果針對相同的使用者重新產生此報告，動作項目的任何後續重新指派都將會導致不同的快照報告資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-p117">This is not a historical report that retains and displays state changes to action item assignment history. The generated report is a snapshot of the control action items assigned at the time that the report is run (date and time stamp written into the report). For instance, any subsequent reassignment of action items will result in different snapshot report data if this report is generated again for the same user.</span></span>
  
#### <a name="reassign-action-items"></a><span data-ttu-id="d75ed-187">重新指派動作項目</span><span class="sxs-lookup"><span data-stu-id="d75ed-187">Reassign action items</span></span>

<span data-ttu-id="d75ed-p118">這項功能可讓組織移除使用者帳戶上任何使用中或未完成的相依性，方法是將所傳回使用者帳戶的所有動作項目擁有權 (其中同時包含作用中和已完成的動作項目) 重新指派給下面選取的新使用者。此動作不會變更已傳回使用者帳戶的文件上傳歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="d75ed-p118">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning all action item ownership (which includes both active and completed action items) from the returned user account to a new user selected below. This action does not change document upload history for the returned user account.</span></span>
  
 <span data-ttu-id="d75ed-190">若要將動作項目重新指派給其他使用者：</span><span class="sxs-lookup"><span data-stu-id="d75ed-190">To reassign action items to another user:</span></span>
  
1. <span data-ttu-id="d75ed-191">按一下輸入方塊以瀏覽並選取所傳回使用者的動作項目應被指派的組織中的另一位使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-191">Click the input box to browse for and select another user within the organization to whom the returned user's action items should be assigned.</span></span>
    
2. <span data-ttu-id="d75ed-192">選取 [取代]\*\*\*\* 以將所傳回使用者的所有控制項動作項目重新指派給新選取的使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-192">Select **Replace** to reassign all control action items from the returned user to the newly selected user.</span></span>
    
3. <span data-ttu-id="d75ed-193">隨即會顯示確認對話方塊，「這會將目前使用者的所有控制動作專案重新指派給選取的使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-193">A confirmation dialog box appears stating, "This will reassign all control action items from the current user to the selected user.</span></span> <span data-ttu-id="d75ed-194">這個動作無法復原。</span><span class="sxs-lookup"><span data-stu-id="d75ed-194">This action cannot be undone.</span></span> <span data-ttu-id="d75ed-195">您確定要繼續？」</span><span class="sxs-lookup"><span data-stu-id="d75ed-195">Are you sure you want to continue?"</span></span>
    
4. <span data-ttu-id="d75ed-196">若要繼續，請選取 **[確定]**，否則請選取 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-196">To continue, select **OK**, otherwise select **Cancel**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d75ed-p120">所有的動作項目 (作用中及已完成) 將會指派給新選取的使用者。不過，此動作不會影響文件上傳歷程記；先前指派使用者所上傳的任何文件仍會顯示日期/時間和先前指派使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="d75ed-p120">All action items (both active and completed) will be assigned to the newly selected user. However, this action does not affect the document upload history; any documents uploaded by the previously assigned user will still show the date/time and name of the previously assigned user.</span></span> 
  
<span data-ttu-id="d75ed-p121">變更文件上傳歷程記錄以移除先前指派的使用者必須以手動程序執行。在這種情況下，系統管理員必須：</span><span class="sxs-lookup"><span data-stu-id="d75ed-p121">Changing the document upload history to remove the previously assigned user will have to be done as a manual process. In that case, the administrator will need to:</span></span>
  
1. <span data-ttu-id="d75ed-201">開啟先前已下載的 [匯出] 報告。</span><span class="sxs-lookup"><span data-stu-id="d75ed-201">Open the previously downloaded Export report.</span></span>
  
2. <span data-ttu-id="d75ed-202">找出並瀏覽至所需的控制項動作項目。</span><span class="sxs-lookup"><span data-stu-id="d75ed-202">Identify and navigate to the desired control action item.</span></span>
  
3. <span data-ttu-id="d75ed-203">選取 [**管理檔**] 以流覽至該控制項的證據存放庫。</span><span class="sxs-lookup"><span data-stu-id="d75ed-203">Select **Manage Documents** to navigate to the evidence repository for that control.</span></span>
  
4. <span data-ttu-id="d75ed-204">下載文件。</span><span class="sxs-lookup"><span data-stu-id="d75ed-204">Download the document.</span></span>
  
5. <span data-ttu-id="d75ed-205">刪除辨識存放庫中的文件。</span><span class="sxs-lookup"><span data-stu-id="d75ed-205">Delete the document in the evidence repository.</span></span>
  
6. <span data-ttu-id="d75ed-206">重新上傳檔。</span><span class="sxs-lookup"><span data-stu-id="d75ed-206">Re-upload the document.</span></span> <span data-ttu-id="d75ed-207">現在檔會有新的上傳日期、時間及「上傳者」的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d75ed-207">The document will now have a new upload date, time, and "Uploaded by" username.</span></span>
  
#### <a name="delete-user-data-history"></a><span data-ttu-id="d75ed-208">刪除使用者資料歷程記錄</span><span class="sxs-lookup"><span data-stu-id="d75ed-208">Delete user data history</span></span>

<span data-ttu-id="d75ed-p123">這會將指派給所傳回使用者之所有動作項目的控制項動作項目設為「未指派」。這也會將所傳回使用者上傳的任何文件的上傳者值設為 [已移除使用者]</span><span class="sxs-lookup"><span data-stu-id="d75ed-p123">This sets control action items to 'unassigned' for all action items assigned to the returned user. This also sets uploaded by value to 'user removed' for any documents uploaded by the returned user</span></span>
  
 <span data-ttu-id="d75ed-211">若要刪除使用者帳戶動作項目和文件上傳記錄：</span><span class="sxs-lookup"><span data-stu-id="d75ed-211">To delete the user account action item and document upload history:</span></span>
  
1. <span data-ttu-id="d75ed-212">選取 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d75ed-212">Select **Delete**.</span></span>

2. <span data-ttu-id="d75ed-213">確認對話方塊隨即顯示：「這會移除所有控制項動作專案指派，以及所選使用者的檔上傳記錄。</span><span class="sxs-lookup"><span data-stu-id="d75ed-213">A confirmation dialog displays: "This will remove all control action item assignments and the document upload history for the selected user.</span></span> <span data-ttu-id="d75ed-214">這個動作無法復原。</span><span class="sxs-lookup"><span data-stu-id="d75ed-214">This action cannot be undone.</span></span> <span data-ttu-id="d75ed-215">您確定要繼續？」</span><span class="sxs-lookup"><span data-stu-id="d75ed-215">Are you sure you want to continue?"</span></span>
    
3. <span data-ttu-id="d75ed-216">若要繼續，請選取 **[確定]**，否則請選取 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-216">To continue, select **OK**, otherwise select **Cancel**.</span></span>

## <a name="groups"></a><span data-ttu-id="d75ed-217">群組</span><span class="sxs-lookup"><span data-stu-id="d75ed-217">Groups</span></span>

<span data-ttu-id="d75ed-218">群組是容器，可讓您組織評估，並在具有相同或相關客戶管理控制措施的評估之間共用一般資訊和工作流程工作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-218">Groups are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span>

<span data-ttu-id="d75ed-219">您可以根據對您邏輯的方式來群組評估，例如依年、標準、服務或組織的小組、部門或地理區域。</span><span class="sxs-lookup"><span data-stu-id="d75ed-219">You can group Assessments in a way that is logical to you, such as by year, standard, service, or based on your organization's teams, divisions, or geographies.</span></span> <span data-ttu-id="d75ed-220">以下是兩個群組和其基礎評估的範例：</span><span class="sxs-lookup"><span data-stu-id="d75ed-220">Below are examples of two groups and their underlying Assessments:</span></span>
  
- <span data-ttu-id="d75ed-221">**FFIEC 是評估2020**</span><span class="sxs-lookup"><span data-stu-id="d75ed-221">**FFIEC IS Assessments 2020**</span></span>
  - <span data-ttu-id="d75ed-222">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="d75ed-222">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="d75ed-223">Intune + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="d75ed-223">Intune + FFIEC IS</span></span>
- <span data-ttu-id="d75ed-224">**資料安全性與隱私權評估**</span><span class="sxs-lookup"><span data-stu-id="d75ed-224">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="d75ed-225">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="d75ed-225">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="d75ed-226">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="d75ed-226">Office 365 + ISO 27018:2014</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-227">建議您先判斷貴組織的群群組原則，*然後再*新增新的評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-227">We recommend determining a grouping strategy for your organization *before* adding new Assessments.</span></span>

<span data-ttu-id="d75ed-228">為了讓您開始，您會為您設定一個包含資料保護基準的**預設**群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-228">To get you started, a **Default** group is set up for you that contains the Data Protection Baseline.</span></span> <span data-ttu-id="d75ed-229">此基準是一組包含常見工業法規和標準的控制項（[深入瞭解](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-229">This baseline is a set of controls that includes common industry regulations and standards ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="d75ed-230">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="d75ed-230">How to create a group</span></span>

<span data-ttu-id="d75ed-231">群組無法建立為獨立實體。</span><span class="sxs-lookup"><span data-stu-id="d75ed-231">Groups cannot be created as standalone entities.</span></span> <span data-ttu-id="d75ed-232">群組必須至少包含一個評估，因此若要建立群組，您必須先建立評估以放置在群組中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-232">A group must always contain at least one Assessment, so in order to create a group, you must first create an Assessment to put in the group.</span></span>

<span data-ttu-id="d75ed-233">請遵循下列步驟建立群組：</span><span class="sxs-lookup"><span data-stu-id="d75ed-233">Follow the steps below to create a group:</span></span>

1. <span data-ttu-id="d75ed-234">您可以在儀表板頂端的附近，選取 [新增**評估**]，以建立新的評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-234">Create a new Assessment by selecting **+ Add Assessment** near the top of your dashboard.</span></span>
2. <span data-ttu-id="d75ed-235">在 [**評估**] 快顯視窗中，輸入評估的標題，然後從下拉式功能表中選取範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-235">From the **Assessment** flyout pane, enter a title for your Assessment and select a template from the drop-down menu.</span></span>
3. <span data-ttu-id="d75ed-236">在 [**請選取群組或新增**群組] 中，選取 [**新增群組**]，然後在下欄欄位中輸入您的組名。</span><span class="sxs-lookup"><span data-stu-id="d75ed-236">At **Please select a group or add a new group**, select **Add a new group** and enter your group name in the field below.</span></span>
4. <span data-ttu-id="d75ed-237">若要複製現有群組中的資訊，請切換 [**您想要從現有的群組複製資料嗎？** ] 切換至 [**開啟]。**</span><span class="sxs-lookup"><span data-stu-id="d75ed-237">To copy information from an existing group, toggle the **Would you like to copy the data from an existing group?** switch to **On.**</span></span> <span data-ttu-id="d75ed-238">從下拉式功能表中選取您要複製的群組，然後選取您想要在新群組中執行新評估的任何欄位核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-238">Select the group you want to copy from the drop-down menu underneath, and select the checkboxes of any fields you want to carry over to the new Assessment in your new group.</span></span>
5. <span data-ttu-id="d75ed-239">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-239">Select **Save**.</span></span> <span data-ttu-id="d75ed-240">完成後，就會關閉彈出窗格，您會在儀表板上看到您的新群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-240">When completed, the flyout pane closes and you'll see your new group on your dashboard.</span></span>

<span data-ttu-id="d75ed-241">使用群組時所知道的事項：</span><span class="sxs-lookup"><span data-stu-id="d75ed-241">What to know when working with groups:</span></span>
  
- <span data-ttu-id="d75ed-242">組名（也稱為「*群組 IDs*）在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-242">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="d75ed-243">群組沒有任何安全性屬性。</span><span class="sxs-lookup"><span data-stu-id="d75ed-243">Groups do not have any security properties.</span></span> <span data-ttu-id="d75ed-244">擁有權限都與評估相關聯。</span><span class="sxs-lookup"><span data-stu-id="d75ed-244">All permissions are associated with Assessments.</span></span>
- <span data-ttu-id="d75ed-245">將評估新增至群組之後，就無法變更該群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-245">Once you add an Assessment to a group, the grouping cannot be changed.</span></span> <span data-ttu-id="d75ed-246">您可以重新命名評估群組，這會變更與該群組相關之所有評估的評估群組名稱。</span><span class="sxs-lookup"><span data-stu-id="d75ed-246">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span>
- <span data-ttu-id="d75ed-247">完成時，相同群組內的相關評估控制項會自動更新。</span><span class="sxs-lookup"><span data-stu-id="d75ed-247">Related Assessment controls in different Assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="d75ed-248">如果您將新的評估新增至現有的群組，則會將該群組中評估的一般資訊複製到新的評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-248">If you add a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="d75ed-249">群組可以包含同一個憑證或法規的評估，但是每個群組只能包含特定產品認證組的一個評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-249">Groups can contain Assessments for the same certification or regulation, but each group can only contain one Assessment for a specific product-certification pair.</span></span> <span data-ttu-id="d75ed-250">例如，群組不可包含針對 Office 365 和 NIST CSF 的兩項評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-250">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="d75ed-251">只有在每個群組的對應憑證或法規不同時，群組才可以包含同一個產品的多項評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-251">A group can contain multiple Assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="d75ed-252">隱藏評估會中斷這種評估與群組之間的關係。</span><span class="sxs-lookup"><span data-stu-id="d75ed-252">Hiding an Assessment breaks the relationship between that Assessment and the group.</span></span> <span data-ttu-id="d75ed-253">其他相關評估的任何進一步更新都會不再反映在隱藏評估中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-253">Any further updates to other related Assessments are no longer reflected in the hidden assessment.</span></span> <span data-ttu-id="d75ed-254">（[瞭解如何隱藏評估。](#hide-a-template-or-an-assessment)）</span><span class="sxs-lookup"><span data-stu-id="d75ed-254">([Learn how to hide Assessments.](#hide-a-template-or-an-assessment))</span></span>
- <span data-ttu-id="d75ed-255">無法刪除群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-255">Groups cannot be deleted.</span></span>
- <span data-ttu-id="d75ed-256">當對出現于多個群組中的動作專案進行變更時，該變更會反映在該動作專案的所有實例中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-256">When a change is made to an Action Item that appears in multiple Groups, that change is reflected in all instances of that Action Item.</span></span>

## <a name="tenant-management-of-dimensions-owners--customer-actions"></a><span data-ttu-id="d75ed-257">對維度、擁有者、& 客戶動作的承租人管理</span><span class="sxs-lookup"><span data-stu-id="d75ed-257">Tenant management of dimensions, owners, & customer actions</span></span>

<span data-ttu-id="d75ed-258">**承租人管理**介面可讓您管理這些組織範圍的設定：</span><span class="sxs-lookup"><span data-stu-id="d75ed-258">The **Tenant Management** interface enables you to manage these organization-wide settings:</span></span>

- <span data-ttu-id="d75ed-259">**維度：** View 可讓您建立自訂樞軸篩選的範本、評估及動作專案的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-259">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="d75ed-260">**擁有者：** 填入可與動作相關聯的責任方清單。</span><span class="sxs-lookup"><span data-stu-id="d75ed-260">**Owners:** Populate a list of responsible parties that can be associated with actions.</span></span>
- <span data-ttu-id="d75ed-261">**客戶動作：** 管理合規性管理員（預覽）中包含的完整動作專案清單，並啟用/停用以安全分數整合之動作的安全評分監控。</span><span class="sxs-lookup"><span data-stu-id="d75ed-261">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="d75ed-262">從畫面的右上角選取 [**租使用者管理**] 以開啟管理介面，並使用下列步驟來管理**維度**、**擁有**者及**客戶動作**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-262">Select **Tenant Management** from the upper-right corner of your screen to open the management interface, and use the steps below to manage  **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="d75ed-263">Dimensions</span><span class="sxs-lookup"><span data-stu-id="d75ed-263">Dimensions</span></span>

<span data-ttu-id="d75ed-264">維度是一組中繼資料，可提供範本、評估或交辦事項的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-264">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="d75ed-265">維度使用索引鍵和值的概念，其中維度索引鍵代表屬性，維度值代表屬性的有效值。</span><span class="sxs-lookup"><span data-stu-id="d75ed-265">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="d75ed-266">例如，在合規性管理員中，有三種類型的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-266">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="d75ed-267">它們是由**動作目的**的維度鍵和**預防**、**偵探**和**修正**的維度值所定義。</span><span class="sxs-lookup"><span data-stu-id="d75ed-267">They are defined by a Dimension Key of **Action Purpose** and Dimension Values of **Preventative**, **Detective**, and **Corrective**.</span></span>

### <a name="owners"></a><span data-ttu-id="d75ed-268">擁有者</span><span class="sxs-lookup"><span data-stu-id="d75ed-268">Owners</span></span>

<span data-ttu-id="d75ed-269">擁有者可用於識別每個控制項的負責人。</span><span class="sxs-lookup"><span data-stu-id="d75ed-269">Owners are used to identify the person responsible for each control.</span></span> <span data-ttu-id="d75ed-270">所有內建的控制項都是由 Microsoft、客戶或兩者所擁有。</span><span class="sxs-lookup"><span data-stu-id="d75ed-270">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="d75ed-271">您可以為擁有者建立自訂值，以用於在組織中指定更細微的責任。</span><span class="sxs-lookup"><span data-stu-id="d75ed-271">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="d75ed-272">例如，您可以建立代表組織內特定群組、小組或業務單位的擁有者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-272">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="d75ed-273">新增擁有者</span><span class="sxs-lookup"><span data-stu-id="d75ed-273">Add an Owner</span></span>

1. <span data-ttu-id="d75ed-274">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-274">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="d75ed-275">選取 [ **+ 新增擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-275">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="d75ed-276">提供擁有者的名稱和描述，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-276">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="d75ed-277">描述會顯示在 [擁有者] 欄中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-277">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="d75ed-278">編輯擁有者</span><span class="sxs-lookup"><span data-stu-id="d75ed-278">Edit an Owner</span></span>

<span data-ttu-id="d75ed-279">您無法編輯擁有者名稱，但您可以修改顯示在 [擁有者] 欄中的描述。</span><span class="sxs-lookup"><span data-stu-id="d75ed-279">You can't edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="d75ed-280">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-280">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="d75ed-281">找到您要編輯的擁有者，選取其旁邊的省略號（...），然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-281">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="d75ed-282">視需要修改描述，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-282">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="d75ed-283">刪除擁有者</span><span class="sxs-lookup"><span data-stu-id="d75ed-283">Delete an Owner</span></span>

1. <span data-ttu-id="d75ed-284">開啟**租使用者管理**，然後選取 [**擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-284">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="d75ed-285">找到您想要刪除的擁有者，選取其旁邊的省略號（...），然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-285">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="d75ed-286">出現確認訊息時，請選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-286">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="d75ed-287">客戶動作</span><span class="sxs-lookup"><span data-stu-id="d75ed-287">Customer Actions</span></span>

<span data-ttu-id="d75ed-288">[客戶動作] 區域會顯示合規性管理員（預覽）中所有範本及評估的所有客戶動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-288">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

<span data-ttu-id="d75ed-289">![合規性管理員-新增使用者](../media/compliance-manager-customer-actions.png "合規性管理員客戶動作")</span><span class="sxs-lookup"><span data-stu-id="d75ed-289">![Compliance Manager — add users](../media/compliance-manager-customer-actions.png "Compliance Manager Customer Actions")</span></span>

<span data-ttu-id="d75ed-290">您可以快速查看動作的標題、擁有者、類別、強制執行和評分，並判斷是否與安全分數整合。</span><span class="sxs-lookup"><span data-stu-id="d75ed-290">At a glance, you can see an Action's title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="d75ed-291">您可以展開動作並選取 [**讀取**]，以閱讀動作的描述並存取描述中的任何連結。</span><span class="sxs-lookup"><span data-stu-id="d75ed-291">You can expand an Action and select **Read More** to read the Action's description and access any links in the description.</span></span> <span data-ttu-id="d75ed-292">您也可以使用此介面來啟用及停用以每個動作為基礎的安全分數整合，以及新增自訂動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-292">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="d75ed-293">具有安全計分整合功能的動作旁會有省略號（...）（請注意，自訂動作旁邊也有省略號）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-293">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="d75ed-294">啟用或停用安全分數整合</span><span class="sxs-lookup"><span data-stu-id="d75ed-294">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="d75ed-295">針對您要修改的動作選取省略號（...），然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-295">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="d75ed-296">切換切換參數，以取得安全分數連續更新為開啟或關閉，以啟用或停用透過安全分數的連續監控。</span><span class="sxs-lookup"><span data-stu-id="d75ed-296">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="d75ed-297">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-297">Select **Save**.</span></span>

<span data-ttu-id="d75ed-298">當組織第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行保護，以完全收集資料，並將其劃分為您的分數。</span><span class="sxs-lookup"><span data-stu-id="d75ed-298">When organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="d75ed-299">在這段時間內，將安全計分連續更新參數設定為**Off** ，並手動設定所要**執行**的動作，就會將該動作計算為您的分數。</span><span class="sxs-lookup"><span data-stu-id="d75ed-299">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="d75ed-300">在最初7天后，開啟安全分數連續更新會啟用從該點繼續進行監視。</span><span class="sxs-lookup"><span data-stu-id="d75ed-300">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>

<span data-ttu-id="d75ed-301">安全分數整合不支援的任何動作都可以手動實施。</span><span class="sxs-lookup"><span data-stu-id="d75ed-301">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="d75ed-302">手動執行將會考慮該動作群組的分數。</span><span class="sxs-lookup"><span data-stu-id="d75ed-302">A manual implementation will factor into the score for that action's group.</span></span>

## <a name="assessments"></a><span data-ttu-id="d75ed-303">評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-303">Assessments</span></span>

<span data-ttu-id="d75ed-304">本節說明如何查看和使用評估，包括如何新增、匯出、複製現有評估中的資訊，以及透過版本設定將其更新。</span><span class="sxs-lookup"><span data-stu-id="d75ed-304">This section explains how to view and work with your Assessments, including how to add new ones, export them, copy information from existing Assessments, and keep them updated through versioning.</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-305">您現在可以在合規性分數中建立評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-305">You can now create assessments in Compliance Score.</span></span> <span data-ttu-id="d75ed-306">[查看指導方針和指示](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="d75ed-306">[View guidance and instructions](compliance-score-assessments.md).</span></span>

### <a name="view-an-assessment-and-action-details"></a><span data-ttu-id="d75ed-307">查看評估和動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="d75ed-307">View an Assessment and Action details</span></span>
  
<span data-ttu-id="d75ed-308">在 [**評估**] 儀表板中，選取 [評估名稱] 以開啟它，然後查看 [動作專案] 和 [控制項] 資訊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-308">In the **Assessments** dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="d75ed-309">以下是 Office 365 及 ISO 27001 評估的範例。</span><span class="sxs-lookup"><span data-stu-id="d75ed-309">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="d75ed-310">第一個視圖說明合規性管理員（預覽）中的新動作專案視圖。</span><span class="sxs-lookup"><span data-stu-id="d75ed-310">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合規性管理員動作專案視圖](../media/compliance-manager-action-items.png)

<span data-ttu-id="d75ed-312">動作會以字母順序列出，而且每個動作都會被指派分數和擁有者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-312">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="d75ed-313">選取 [**讀取其他**] 連結，以閱讀每個動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-313">Select  the **Read More** link to read the details of each Action.</span></span>

![合規性管理員動作專案視圖](../media/compliance-manager-actions-read-more.png)

<span data-ttu-id="d75ed-315">選取 [**檢查**] 連結，以管理、指派、實施及測試動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-315">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="d75ed-316">以下是範例動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-316">Below is an example Action.</span></span>

![合規性管理員動作視圖](../media/compliance-manager-action.png)

<span data-ttu-id="d75ed-318">使用下欄欄位來管理動作工作流程：</span><span class="sxs-lookup"><span data-stu-id="d75ed-318">Use the following fields to manage the Action workflow:</span></span>

- <span data-ttu-id="d75ed-319">**指派使用者：** 選取此欄位，以選擇或輸入應指派此動作的使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-319">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="d75ed-320">您可以在清單中滾動，或輸入名稱來尋找，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="d75ed-320">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="d75ed-321">**管理檔：** 您可以以 Office 檔、圖像檔案及螢幕擷取畫面的形式上傳執行證據，在 CSV 或 TXT 中 PowerShell 輸出，以及 Pdf。</span><span class="sxs-lookup"><span data-stu-id="d75ed-321">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="d75ed-322">**實施狀態：** 用來指出動作目前的執行狀態。</span><span class="sxs-lookup"><span data-stu-id="d75ed-322">**Implementation Status:** Used to indicate the Action's current implementation status.</span></span> <span data-ttu-id="d75ed-323">可能的值尚未實現、已實現、替代的實施、規劃中和不在範圍內。</span><span class="sxs-lookup"><span data-stu-id="d75ed-323">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="d75ed-324">**實施日期：** 採取動作的日期。</span><span class="sxs-lookup"><span data-stu-id="d75ed-324">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="d75ed-325">**測試結果：** 用來指出實施驗證的結果。</span><span class="sxs-lookup"><span data-stu-id="d75ed-325">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="d75ed-326">可能的值不會評估、傳遞、失敗-低風險、失敗-中低風險、失敗-高風險，而且不在範圍內。</span><span class="sxs-lookup"><span data-stu-id="d75ed-326">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="d75ed-327">**測試日期：** 驗證發生的日期。</span><span class="sxs-lookup"><span data-stu-id="d75ed-327">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="d75ed-328">**執行附注：** 輸入組織的執行詳細資料，以及您想要包含的任何附注。</span><span class="sxs-lookup"><span data-stu-id="d75ed-328">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="d75ed-329">**測試方案：** 輸入此動作的測試計劃詳細資料，以及您要包含的任何附注。</span><span class="sxs-lookup"><span data-stu-id="d75ed-329">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="d75ed-330">**其他資訊：** 輸入有關此動作或其在組織中實施方式的任何其他資訊，以及您想要加入的任何附注。</span><span class="sxs-lookup"><span data-stu-id="d75ed-330">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="d75ed-331">在 [**控制項資訊**] 儀表板上，您可以在評估與範本層級查看控制項資訊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-331">On the **Controls Info** dashboard, you can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="d75ed-332">以下是評估的控制項資訊儀表板的範例。</span><span class="sxs-lookup"><span data-stu-id="d75ed-332">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合規性管理員控制資訊視圖](../media/compliance-manager-controls-info.png)

<span data-ttu-id="d75ed-334">針對評估，[控制項資訊] 儀表板會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d75ed-334">For Assessments, the Controls Info dashboard displays the following information:</span></span>

- <span data-ttu-id="d75ed-335">**群組**下拉式清單，可選取要查看的群組（使用多個群組時）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-335">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="d75ed-336">**評估**下拉式功能表，以選取要查看的評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-336">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="d75ed-337">所選評估的中繼資料，包括：</span><span class="sxs-lookup"><span data-stu-id="d75ed-337">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="d75ed-338">**評估控制項**的進度指標，顯示超過控制項總數的評估的控制項數目。</span><span class="sxs-lookup"><span data-stu-id="d75ed-338">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="d75ed-339">評估的目前**符合性分數**，顯示為百分數。</span><span class="sxs-lookup"><span data-stu-id="d75ed-339">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="d75ed-340">評估中所用之**憑證及\*\*\*\*產品**的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-340">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="d75ed-341">評估的目前**狀態**和上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="d75ed-341">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="d75ed-342">評估的**範圍服務**清單。</span><span class="sxs-lookup"><span data-stu-id="d75ed-342">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="d75ed-343">控制項的詳細資料，依控制項系列分組，包含客戶動作和 Microsoft 執行詳細資料的連結：</span><span class="sxs-lookup"><span data-stu-id="d75ed-343">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="d75ed-344">**您的動作**會顯示您可以執行的客戶動作，以滿足部分或所有控制項的需求。</span><span class="sxs-lookup"><span data-stu-id="d75ed-344">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control's requirements.</span></span> <span data-ttu-id="d75ed-345">許多控制項具有多個與其相關聯的動作，而且所有與控制項關聯的動作都會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="d75ed-345">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="d75ed-346">這裡的動作與動作儀表板中所列的 UI 相同。</span><span class="sxs-lookup"><span data-stu-id="d75ed-346">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="d75ed-347">**Microsoft 動作**會顯示 Microsoft 內部架構中套用至所選認證控制項的控制項清單。</span><span class="sxs-lookup"><span data-stu-id="d75ed-347">**Microsoft Actions** displays the list of controls from Microsoft's internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="d75ed-348">針對每個內部控制，選取 [已**執行**]，以查看 Microsoft 的執行和測試詳細資料，以及測試結果和測試日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="d75ed-348">For each internal control, select **Implemented** to see Microsoft's implementation and test details, along with the test result and test date, as shown below.</span></span>

![合規性管理員 Microsoft 動作視圖](../media/compliance-manager-microsoft-action.png)

### <a name="add-an-assessment"></a><span data-ttu-id="d75ed-350">新增評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-350">Add an Assessment</span></span>
  
1. <span data-ttu-id="d75ed-351">在 [評估] 儀表板中，選取 [ **+ Add 評估**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-351">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="d75ed-352">當刀片式伺服器開啟時，請輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d75ed-352">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="d75ed-353">**職稱（必要）：** 輸入評估的標題</span><span class="sxs-lookup"><span data-stu-id="d75ed-353">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="d75ed-354">**請選取範本（必要）：** 選取標準或自訂範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-354">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="d75ed-355">**請選取群組或新增新的群組（必要）：** 選取現有的群組，或選擇新增群組，並提供唯一的組名</span><span class="sxs-lookup"><span data-stu-id="d75ed-355">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="d75ed-356">**您要複製現有群組中的資料嗎？（選用）：** 切換控制項以啟用群組副本，然後：</span><span class="sxs-lookup"><span data-stu-id="d75ed-356">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="d75ed-357">**選取群組（選用）：** 如果已啟用群組副本，請選取要複製的群組</span><span class="sxs-lookup"><span data-stu-id="d75ed-357">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="d75ed-358">**執行詳細資料（選用）：** 選取以將實現詳細資料複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="d75ed-358">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="d75ed-359">**測試計劃 & 其他資訊（選用）：** 選取以將測試計劃及其他資訊詳細資料複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="d75ed-359">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="d75ed-360">**檔（選用）：** 選取以將檔案複製到新的群組</span><span class="sxs-lookup"><span data-stu-id="d75ed-360">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="d75ed-361">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-361">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="d75ed-362">評估儀表板上會顯示新的評估，並顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d75ed-362">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="d75ed-363">評估的標題。</span><span class="sxs-lookup"><span data-stu-id="d75ed-363">The title of the Assessment.</span></span>
- <span data-ttu-id="d75ed-364">評估的維度，包括憑證、環境和套用至評估的產品。</span><span class="sxs-lookup"><span data-stu-id="d75ed-364">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="d75ed-365">其建立日期和上次修改日期的日期。</span><span class="sxs-lookup"><span data-stu-id="d75ed-365">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="d75ed-366">評估分數顯示為百分比。</span><span class="sxs-lookup"><span data-stu-id="d75ed-366">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="d75ed-367">這個分數會自動包含您的分數從 Microsoft 管理的控制項，以及從安全得分。</span><span class="sxs-lookup"><span data-stu-id="d75ed-367">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="d75ed-368">顯示已評估的 Microsoft 管理和客戶管理控制措施數目的進度指標。</span><span class="sxs-lookup"><span data-stu-id="d75ed-368">Progress indicators that show the number of assessed Microsoft-managed and customer-managed controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="d75ed-369">從現有「評定」複製資訊</span><span class="sxs-lookup"><span data-stu-id="d75ed-369">Copying information from existing Assessments</span></span>

<span data-ttu-id="d75ed-370">當您建立評估時，您可以選擇複製現有群組中的資訊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-370">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="d75ed-371">複製功能可讓您將輸入到複製評估中的資訊套用到新評估中的相同控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-371">Copying allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="d75ed-372">例如，如果您的組織中有所有 FFIEC 相關評估的群組，您可以從現有評估中複製下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d75ed-372">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="d75ed-373">執行詳細資料</span><span class="sxs-lookup"><span data-stu-id="d75ed-373">Implementation Details</span></span>
- <span data-ttu-id="d75ed-374">測試計劃 & 其他資訊</span><span class="sxs-lookup"><span data-stu-id="d75ed-374">Test Plan & Additional Information</span></span>
- <span data-ttu-id="d75ed-375">文件</span><span class="sxs-lookup"><span data-stu-id="d75ed-375">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="d75ed-376">將現有評估的資訊複製到新的評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-376">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="d75ed-377">在 [評估] 儀表板中，選取 [ **+ Add 評估**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-377">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="d75ed-378">在 [**新增評估**] 視窗中，完成下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d75ed-378">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="d75ed-379">**職稱（必要）：** 輸入評估的標題。</span><span class="sxs-lookup"><span data-stu-id="d75ed-379">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="d75ed-380">**請選取範本（必要）：** 選取標準或自訂的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-380">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="d75ed-381">**請選取群組或新增新的群組（必要）：** 選擇 [新增**群組**]，並提供唯一的組名。</span><span class="sxs-lookup"><span data-stu-id="d75ed-381">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="d75ed-382">**您要複製現有群組中的資料嗎？（選用）：** 將控制項切換至開啟以啟用群組副本，然後：**選取群組（選用）：** 如果已啟用群組副本，請選取要複製的群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-382">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="d75ed-383">- **執行詳細資料（選用）：** 選取可將實現詳細資料複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-383">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="d75ed-384">- **測試計劃 & 其他資訊（選用）：** 選取以將測試計劃及其他資訊詳細資料複製到新群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-384">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="d75ed-385">- **檔（選用）：** 選取以將檔案複製到新的群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-385">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="d75ed-386">選取 [**儲存**] 以建立評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-386">Select **Save** to create the Assessment.</span></span>

### <a name="versioning-alerts-for-assessment-updates"></a><span data-ttu-id="d75ed-387">評估更新的版本設定警示</span><span class="sxs-lookup"><span data-stu-id="d75ed-387">Versioning alerts for Assessment updates</span></span>

<span data-ttu-id="d75ed-388">當評估有可用的更新時，提醒圖示會通知您有更新準備就緒。</span><span class="sxs-lookup"><span data-stu-id="d75ed-388">When an update is available for an Assessment, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="d75ed-389">當您按一下該圖示時，會快顯視窗來說明更新，並提示您接受。</span><span class="sxs-lookup"><span data-stu-id="d75ed-389">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="d75ed-390">以下是評估的版本設定警示範例：</span><span class="sxs-lookup"><span data-stu-id="d75ed-390">Below is an example of the versioning alert for an Assessment:</span></span>

<span data-ttu-id="d75ed-391">![合規性分數-版本設定警示](../media/compliance-score-assessment-version.png "評估版本更新警示")</span><span class="sxs-lookup"><span data-stu-id="d75ed-391">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="d75ed-392">選取警示圖示會顯示彈出窗格，說明更新並提示您接受：</span><span class="sxs-lookup"><span data-stu-id="d75ed-392">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="d75ed-393">![合規性分數-版本快顯視窗](../media/compliance-score-assessment-version-accept.png "評估更新確認窗格")</span><span class="sxs-lookup"><span data-stu-id="d75ed-393">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

<span data-ttu-id="d75ed-394">我們強烈建議您在收到更新通知時接受所有更新。</span><span class="sxs-lookup"><span data-stu-id="d75ed-394">We strongly recommend accepting all updates when you receive update notifications.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="d75ed-395">匯出評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-395">Export an Assessment</span></span>

<span data-ttu-id="d75ed-396">您可以將評估匯出至您組織中或外部審計員和主管的符合性專案關係人的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="d75ed-396">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="d75ed-397">報表是指報表建立日期和時間的評估快照。</span><span class="sxs-lookup"><span data-stu-id="d75ed-397">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="d75ed-398">報告包含針對評估、控制執行狀態、控制測試日期、測試結果，以及提供上傳的證據檔連結的所有 Microsoft 及客戶管理控制項的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-398">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="d75ed-399">匯出評估報告</span><span class="sxs-lookup"><span data-stu-id="d75ed-399">Export an Assessment report</span></span>
  
1. <span data-ttu-id="d75ed-400">在 [合規性管理員] 儀表板上，選取 [**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d75ed-400">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="d75ed-401">在下拉式功能表中，選取您要匯出之評估的**群組**和**評估**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-401">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="d75ed-402">選取 [**匯出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d75ed-402">Select the **Export** button.</span></span>

<span data-ttu-id="d75ed-403">在您的瀏覽器會話中，會將評估報告當做 Excel 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="d75ed-403">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="d75ed-404">Excel 檔案的 files 名稱預設為評估的標題。</span><span class="sxs-lookup"><span data-stu-id="d75ed-404">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="d75ed-405">隱藏範本或評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-405">Hide a Template or an Assessment</span></span>

<span data-ttu-id="d75ed-406">當您完成範本或評估，但是不再因相容性目的而需要時，您可以將它從您的視圖中隱藏。</span><span class="sxs-lookup"><span data-stu-id="d75ed-406">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="d75ed-407">當範本或評估隱藏時，它會從預設視圖中移除，您必須選取 [**包含隱藏**] 核取方塊加以顯示。</span><span class="sxs-lookup"><span data-stu-id="d75ed-407">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="d75ed-408">![合規性管理員隱藏的範本視圖](../media/compliance-manager-hidden-template.png "合規性管理員隱藏範本")</span><span class="sxs-lookup"><span data-stu-id="d75ed-408">![Compliance Manager Hidden Template View](../media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d75ed-409">隱藏評估不會保留其上傳的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="d75ed-409">Hidden Assessments don't retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="d75ed-410">強烈建議您在隱藏評估之前先將其匯出，以保留報告中的證據檔連結。</span><span class="sxs-lookup"><span data-stu-id="d75ed-410">We highly recommended that you export an Assessment before hiding it to retain links to evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="d75ed-411">隱藏範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-411">Hiding a Template</span></span>

1. <span data-ttu-id="d75ed-412">開啟 [**範本**] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="d75ed-412">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="d75ed-413">找到您想要隱藏的範本，並在其列的省略號上，選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-413">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="d75ed-414">當您看到確認訊息時，請選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-414">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="d75ed-415">隱藏評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-415">Hide an Assessment</span></span>

1. <span data-ttu-id="d75ed-416">開啟 [**評估**儀表板]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-416">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="d75ed-417">從下拉式清單中，選取包含您想要隱藏之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-417">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="d75ed-418">找到您想要隱藏的評估，並選取省略號，選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-418">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="d75ed-419">當您看到確認訊息時，請選取 [**隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-419">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="d75ed-420">查看隱藏評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-420">View hidden Assessments</span></span>
  
1. <span data-ttu-id="d75ed-421">開啟 [**評估**儀表板] 索引標籤，然後選取 [**包含隱藏**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-421">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="d75ed-422">隱藏評估會顯示在 [**隱藏評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-422">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="d75ed-423">取消隱藏評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-423">Unhide an Assessment</span></span>

1. <span data-ttu-id="d75ed-424">在 [**評估**] 索引標籤上，選取 [**包含隱藏**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-424">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="d75ed-425">隱藏評估會顯示在 [**隱藏評估**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-425">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="d75ed-426">找到您想要取消隱藏的評估，並選取省略號，選取 [**取消隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-426">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="d75ed-427">當您看到確認訊息時，請選取 [**取消隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-427">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="d75ed-428">控制項和動作</span><span class="sxs-lookup"><span data-stu-id="d75ed-428">Controls and Actions</span></span>

<span data-ttu-id="d75ed-429">控制項和動作是合規性管理員（預覽）中所使用的主要資料轉動。</span><span class="sxs-lookup"><span data-stu-id="d75ed-429">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="d75ed-430">在舊版本的合規性管理員中，控制項 pivot 已增強，可在相同的控制系列中顯示 Microsoft 和客戶控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-430">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="d75ed-431">這種合併的視圖可讓您更容易查看每個控制項的完整共用責任模型。</span><span class="sxs-lookup"><span data-stu-id="d75ed-431">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="d75ed-432">Action pivot 是合規性管理員（預覽）中的新功能，其設計目的是為了提供 Microsoft 建議的所有動作的簡潔觀點。</span><span class="sxs-lookup"><span data-stu-id="d75ed-432">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="d75ed-433">控制項</span><span class="sxs-lookup"><span data-stu-id="d75ed-433">Controls</span></span>

<span data-ttu-id="d75ed-434">控制項可以從 [控制項資訊] 儀表板中查看。</span><span class="sxs-lookup"><span data-stu-id="d75ed-434">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="d75ed-435">控制項代表標準、認證、法規或架構中的需求。</span><span class="sxs-lookup"><span data-stu-id="d75ed-435">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="d75ed-436">若要將這些需求對應至多個標準、法規等專案，並將這些需求與動作相關聯，請將所有專案視為控制項框架。</span><span class="sxs-lookup"><span data-stu-id="d75ed-436">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="d75ed-437">例如，像是控制架構之外，規章（如 HIPAA）已細分為一節，合規性管理員中的 HIPAA 控制項使用與這些區段相同的編號配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d75ed-437">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合規性管理員 Microsoft 控制項詳細資料](../media/compliance-manager-control-details.png)

<span data-ttu-id="d75ed-439">控制項有三種類型：</span><span class="sxs-lookup"><span data-stu-id="d75ed-439">There are three types of controls:</span></span>

1. <span data-ttu-id="d75ed-440">**Microsoft 受管理的控制項：** 這些是只有 Microsoft 有責任的控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-440">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="d75ed-441">它們會顯示在 box 範本中，並由 Microsoft 新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="d75ed-441">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="d75ed-442">**客戶管理的控制項：** 這些是只有客戶具有責任的控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-442">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="d75ed-443">它們會顯示在 box 範本中，並由客戶新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="d75ed-443">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="d75ed-444">**共用管理控制措施：** 這些是在 Microsoft 與客戶之間共用責任的控制。</span><span class="sxs-lookup"><span data-stu-id="d75ed-444">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="d75ed-445">這些範本會出現在 box 範本中，並由 Microsoft 新增至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="d75ed-445">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="d75ed-446">客戶也可以編輯或停用 Microsoft 管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-446">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="d75ed-447">Actions 專案</span><span class="sxs-lookup"><span data-stu-id="d75ed-447">Actions Items</span></span>

<span data-ttu-id="d75ed-448">動作專案是實施標準或法規需求的建議工作，或是用來測試、驗證及記錄組織的執行需求。</span><span class="sxs-lookup"><span data-stu-id="d75ed-448">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="d75ed-449">動作與一個或多個控制項相關聯。</span><span class="sxs-lookup"><span data-stu-id="d75ed-449">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="d75ed-450">每個控制項都有一個或多個與其相關聯的動作，而且每個動作都可以與一個或多個控制項產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d75ed-450">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="d75ed-451">動作是合規性管理員（預覽）中核心工作流程的一部分，因為它們是指派、追蹤及驗證組織的物件。</span><span class="sxs-lookup"><span data-stu-id="d75ed-451">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="d75ed-452">指派動作專案</span><span class="sxs-lookup"><span data-stu-id="d75ed-452">Assign Action Items</span></span>
  
1. <span data-ttu-id="d75ed-453">在 [**動作專案**] 儀表板上，選取包含要指派其動作之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-453">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="d75ed-454">在 [**評估**] 下拉式清單中，選取您要指派其動作的評估，或從下拉式清單中選取 [**全部**]，以查看所有可用的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-454">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="d75ed-455">找到您要指派的動作，然後在 [**擁有**者] 欄位中，選取要**複查**的連結、\* \* 已執行或**測試**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-455">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, \*\*Implemented, or **Test**.</span></span>
4. <span data-ttu-id="d75ed-456">選取 [**指派使用者**] 欄位，並顯示您組織中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="d75ed-456">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="d75ed-457">滾動清單並選取使用者或篩選清單，以選取使用者的名稱來選取使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-457">Scroll the list and select user or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="d75ed-458">在 [執行附注] 欄位中，輸入您想要傳遞給指派使用者的任何附注。</span><span class="sxs-lookup"><span data-stu-id="d75ed-458">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="d75ed-459">選取 [**儲存**] 以指派動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-459">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="d75ed-460">重新指派動作專案</span><span class="sxs-lookup"><span data-stu-id="d75ed-460">Reassign Action Items</span></span>

<span data-ttu-id="d75ed-461">此功能可讓組織將動作重新指派給新使用者，以移除使用者帳戶上任何使用中或尚未完成的相關性。</span><span class="sxs-lookup"><span data-stu-id="d75ed-461">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="d75ed-462">在 [**動作專案**] 儀表板上，選取包含您想要重新指派其動作之評估的**群組**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-462">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="d75ed-463">在 [**評估**] 下拉式清單中，選取您要重新指派其動作的評估，或從下拉式清單中選取 [**全部**]，以查看所有可用的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-463">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="d75ed-464">找到您想要重新指派的動作，然後在 [**擁有**者] 欄中，選取要**複查**、**實施**或**測試**的連結。</span><span class="sxs-lookup"><span data-stu-id="d75ed-464">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="d75ed-465">從 [**指派使用者**] 欄位中刪除現有的使用者，並從使用者清單中選擇不同的使用者，或透過輸入使用者的名稱來篩選清單，以選取使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-465">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="d75ed-466">在 [執行附注] 欄位中，輸入您想要傳遞給使用者的任何附注。</span><span class="sxs-lookup"><span data-stu-id="d75ed-466">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="d75ed-467">選取 [**儲存**] 以重新指派動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-467">Select **Save** to reassign the Action.</span></span>

#### <a name="common-action-items-synch-status-across-groups"></a><span data-ttu-id="d75ed-468">不同群組的常見動作專案同步狀態</span><span class="sxs-lookup"><span data-stu-id="d75ed-468">Common Action Items synch status across Groups</span></span>

<span data-ttu-id="d75ed-469">如果您的組織有多個評估群組，則會有技術動作（也就是影響整個組織的動作）的行為。</span><span class="sxs-lookup"><span data-stu-id="d75ed-469">If your organization has multiple groups of assessments, there is a behavior of Technical actions (that is, actions affecting your entire organization).</span></span> <span data-ttu-id="d75ed-470">群組間的任何重複動作現在會合並成一個單一動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-470">Any duplicate actions across groups are now combined into one single action.</span></span> <span data-ttu-id="d75ed-471">單一巨集指令包含先前重複的版本中所有上傳的記事及證據。</span><span class="sxs-lookup"><span data-stu-id="d75ed-471">That single action contains all uploaded notes and evidence from previously duplicate versions.</span></span> <span data-ttu-id="d75ed-472">在一個群組或評估中對動作所做的任何變更，都會反映在該動作的所有實例中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-472">Any change made to the action in one group or assessment will be reflected in all instances of that action.</span></span> <span data-ttu-id="d75ed-473">「**實施狀態**」、「**實施日期**」、「**測試狀態**」及「**測試日期**」欄位會反映最新的更新。</span><span class="sxs-lookup"><span data-stu-id="d75ed-473">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** fields reflect the most recent updates.</span></span>

## <a name="templates"></a><span data-ttu-id="d75ed-474">範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-474">Templates</span></span>

<span data-ttu-id="d75ed-475">範本是合規性管理員（預覽）中與產品及認證（例如，standard、管制、控制架構等）相關聯的基礎物件。</span><span class="sxs-lookup"><span data-stu-id="d75ed-475">A Template is the base object in Compliance Manager (Preview) that is associated with a product and a certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="d75ed-476">您可以從 [**範本**] 儀表板中查看及新增範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-476">Templates can be viewed and added from the **Templates** dashboard.</span></span>

![合規性管理員 Microsoft 範本儀表板](../media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="d75ed-478">儀表板會顯示每個範本，以及與範本相關聯的憑證及產品、客戶的範本建立和上次修改的日期、客戶和 Microsoft 管理的控制項數目、範本的最大合規性分數，以及範本的狀態（例如，已核准、待定核准、匯入）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-478">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

### <a name="create-a-template"></a><span data-ttu-id="d75ed-479">建立範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-479">Create a Template</span></span>

<span data-ttu-id="d75ed-480">使用範本來建立評估的方法有三種：</span><span class="sxs-lookup"><span data-stu-id="d75ed-480">There are three ways to work with Templates to create Assessments:</span></span>

1. <span data-ttu-id="d75ed-481">使用其中一種準備使用 Microsoft 提供的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-481">Use one of the ready to use Templates provided by Microsoft.</span></span>
2. <span data-ttu-id="d75ed-482">透過擴充程式，自訂現成的動作和控制項的可使用範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-482">Customize a ready to use Template with your own actions and controls through the extension process.</span></span>
3. <span data-ttu-id="d75ed-483">建立您自己的範本，並將其匯入合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="d75ed-483">Create your own Template and import it into Compliance Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-484">當您將範本上傳到合規性管理員時，必須透過保留系統管理員角色的兩位使用者核准它，然後才可使用。</span><span class="sxs-lookup"><span data-stu-id="d75ed-484">When you upload a template into Compliance Manager, it must be approved by two users who hold an admin role before it is published and available for use.</span></span>

#### <a name="use-a-ready-to-use-template"></a><span data-ttu-id="d75ed-485">使用準備使用的範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-485">Use a ready to use Template</span></span>

<span data-ttu-id="d75ed-486">您可以在**範本**儀表板上使用範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-486">Ready to use templates are available on your **Templates** dashboard.</span></span> <span data-ttu-id="d75ed-487">查看目前的[範本清單](compliance-score-templates.md)，該清單會在每次新的範本可用時更新。</span><span class="sxs-lookup"><span data-stu-id="d75ed-487">View the current [list of templates](compliance-score-templates.md), which is updated each time a new template is available.</span></span>

#### <a name="customize-a-template-through-the-extension-process"></a><span data-ttu-id="d75ed-488">透過擴充處理常式自訂範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-488">Customize a Template through the extension process</span></span>

1. <span data-ttu-id="d75ed-489">開啟 [**範本**] 儀表板，然後選取 [ **+ 新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-489">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="d75ed-490">在 [範本] 飛入窗格上，選取 [**從通用範本建立副檔名**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-490">On the Template flyout pane, select the **Create extension from global template** checkbox.</span></span>
3. <span data-ttu-id="d75ed-491">從下拉式功能表中選取您要擴充的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-491">Select the template you want to extend from the drop-down menu.</span></span>
4. <span data-ttu-id="d75ed-492">若尚未在 Excel 中格式化範本資料，請選取彈出窗格中的連結，以下載 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="d75ed-492">If you have not already formatted your template data in Excel, select the link in the flyout pane to download an Excel file.</span></span> <span data-ttu-id="d75ed-493">請根據下列[Excel](#import-template-data-with-excel)指示填寫試算表，並將其儲存至您的本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="d75ed-493">Fill out the spreadsheet according to the [Import Template data with Excel](#import-template-data-with-excel) instructions below and save it to your local drive.</span></span>
5. <span data-ttu-id="d75ed-494">選取 **[流覽]** 以上傳您的 Excel 檔案，以匯入自訂的範本資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-494">Import your customized template data by selecting **Browse** to upload your Excel file.</span></span>
6. <span data-ttu-id="d75ed-495">選取 [**新增至儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-495">Select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="d75ed-496">對範本所做的變更需要有兩個擁有系統管理員角色的使用者核准。</span><span class="sxs-lookup"><span data-stu-id="d75ed-496">The changes to the template require approval of two users who hold an admin role.</span></span> <span data-ttu-id="d75ed-497">這些使用者會收到範本更新的通知。</span><span class="sxs-lookup"><span data-stu-id="d75ed-497">Those users receive a notification of the template updates.</span></span> <span data-ttu-id="d75ed-498">有兩個系統管理員核准變更，您會在 [**範本**] 儀表板上看到更新的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-498">One the changes are approved by two admins, you'll see your updated template on your **Templates** dashboard.</span></span>

#### <a name="create-your-own-template-and-import-it-into-compliance-manager"></a><span data-ttu-id="d75ed-499">建立您自己的範本，並將其匯入合規性管理員</span><span class="sxs-lookup"><span data-stu-id="d75ed-499">Create your own Template and import it into Compliance Manager</span></span>

1. <span data-ttu-id="d75ed-500">開啟 [**範本**] 儀表板，然後選取 [ **+ 新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-500">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="d75ed-501">在 [範本] 飛入窗格上，選取 [**建立新的範本**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-501">On the Template flyout pane, select **Create a new template**.</span></span>
3. <span data-ttu-id="d75ed-502">選取 **[流覽]** 以上傳包含資料的 Excel 檔案（請參閱下列[Excel 的匯入範本資料](#import-template-data-with-excel)），以匯入範本資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-502">Import your template data by selecting **Browse** to upload your Excel file containing the data (see [Import Template data with Excel](#import-template-data-with-excel) below).</span></span>
4. <span data-ttu-id="d75ed-503">選取 [**新增至儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-503">Select **Add to Dashboard**.</span></span>
5. <span data-ttu-id="d75ed-504">新的範本需要有兩個擁有系統管理員角色的使用者核准。</span><span class="sxs-lookup"><span data-stu-id="d75ed-504">The new template requires approval of two users who hold an admin role.</span></span> <span data-ttu-id="d75ed-505">這些使用者接收新範本可供核准的通知。</span><span class="sxs-lookup"><span data-stu-id="d75ed-505">Those users receive a notification that a new template is ready for approval.</span></span> <span data-ttu-id="d75ed-506">一個範本已由兩個系統管理員核准，您會在 [**範本**] 儀表板上看到新的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-506">One the template is approved by two admins, you'll see your new template on your **Templates** dashboard.</span></span>

#### <a name="import-template-data-with-excel"></a><span data-ttu-id="d75ed-507">使用 Excel 匯入範本資料</span><span class="sxs-lookup"><span data-stu-id="d75ed-507">Import Template data with Excel</span></span>

<span data-ttu-id="d75ed-508">若要修改範本或建立您自己的範本，您會使用[Excel 試算表](https://go.microsoft.com/fwlink/?linkid=2124865)來捕獲必要的資料，並將其上傳到合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="d75ed-508">To modify a template or create your own template, you'll use an [Excel spreadsheet](https://go.microsoft.com/fwlink/?linkid=2124865) to capture the necessary data and upload it to Compliance Manager.</span></span> <span data-ttu-id="d75ed-509">這個試算表範本具有必須使用的特定格式和架構，否則將不會匯入至合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="d75ed-509">This spreadsheet template has a specific format and schema that must be used or it will not import into Compliance Manager.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d75ed-510">如果您先前已在合規性管理員中建立或自訂範本，則**此程式最近已更新。請仔細閱讀本節。**</span><span class="sxs-lookup"><span data-stu-id="d75ed-510">If you've created or customized templates in Compliance Manager before, **this process has been recently updated. Please review this section carefully.**</span></span>

<span data-ttu-id="d75ed-511">試算表包含四個選項卡，其中三個是必要的：</span><span class="sxs-lookup"><span data-stu-id="d75ed-511">The spreadsheet contains four tabs, three of which are required:</span></span>

1. <span data-ttu-id="d75ed-512">範本（必要）</span><span class="sxs-lookup"><span data-stu-id="d75ed-512">Template (required)</span></span>
2. <span data-ttu-id="d75ed-513">ControlFamily （必要）</span><span class="sxs-lookup"><span data-stu-id="d75ed-513">ControlFamily (required)</span></span>
3. <span data-ttu-id="d75ed-514">動作（必要）</span><span class="sxs-lookup"><span data-stu-id="d75ed-514">Actions (required)</span></span>
4. <span data-ttu-id="d75ed-515">維度（選用）</span><span class="sxs-lookup"><span data-stu-id="d75ed-515">Dimensions (optional)</span></span>

<span data-ttu-id="d75ed-516">您的試算表**必須依此順序包含**索引標籤，否則您的資料將無法成功匯入至範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-516">Your spreadsheet **must include the tabs in this order**, otherwise your data won't successfully import to a template.</span></span>

##### <a name="template-tab"></a><span data-ttu-id="d75ed-517">範本] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="d75ed-517">Template tab</span></span>

<span data-ttu-id="d75ed-518">[**範本**] 索引標籤是必要的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-518">The **Template** tab is required.</span></span> <span data-ttu-id="d75ed-519">此索引標籤中的資訊提供範本的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-519">The information in this tab provides metadata about the template.</span></span> <span data-ttu-id="d75ed-520">有四個必要的欄。</span><span class="sxs-lookup"><span data-stu-id="d75ed-520">There are four required columns.</span></span> <span data-ttu-id="d75ed-521">欄必須保留在 Excel 工作表上如下所列的順序。</span><span class="sxs-lookup"><span data-stu-id="d75ed-521">The columns must retain the order on the Excel sheet as listed below.</span></span> <span data-ttu-id="d75ed-522">您可以在四欄**後**新增您自己的欄，以提供您自己的維度。</span><span class="sxs-lookup"><span data-stu-id="d75ed-522">You can add your own column **after** the four columns to provide your own dimensions.</span></span> <span data-ttu-id="d75ed-523">如果您這麼做，請務必使用[下列指示](#dimensions-tab)將其新增至 [**維度**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d75ed-523">If you do this, be sure to add them to the **Dimensions** tab using the [instructions below](#dimensions-tab).</span></span>

- <span data-ttu-id="d75ed-524">**職稱**：這是範本的標題，必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-524">**title**: This is the title for your template, which must be unique.</span></span> <span data-ttu-id="d75ed-525">您可以在合規性管理員中與其他範本共用名稱稱，不論它是您已建立的範本，還是由 Microsoft 提供的預先設定的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-525">It can't share a name with another template you have in Compliance Manager, whether it's a template you already created, or a pre-configured template provided by Microsoft.</span></span>

- <span data-ttu-id="d75ed-526">**產品**：這是必要的維度。</span><span class="sxs-lookup"><span data-stu-id="d75ed-526">**product**: This is a required dimension.</span></span> <span data-ttu-id="d75ed-527">列出與範本相關聯的產品。</span><span class="sxs-lookup"><span data-stu-id="d75ed-527">List the product associated with the template.</span></span>

- <span data-ttu-id="d75ed-528">**認證**：這是您用來做為範本的規章。</span><span class="sxs-lookup"><span data-stu-id="d75ed-528">**certification**: This is the regulation you're using for the template.</span></span>

- <span data-ttu-id="d75ed-529">**inScopeServices**：這些是此項評估所定址之產品中的服務（例如，如果您列為 Office 365 做為產品，則 Microsoft 團隊可能是一個範圍內的服務）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-529">**inScopeServices**: These are the services within the product that this assessment addresses (for example, if you listed Office 365 as the product, Microsoft Teams could be an in-scope service).</span></span> <span data-ttu-id="d75ed-530">您可以列出多個以兩個分號分隔的服務。</span><span class="sxs-lookup"><span data-stu-id="d75ed-530">You can list multiple services separated by two semi-colons.</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-531">關於產品和憑證：在您匯入試算表以建立或自訂範本之後，您在 [**產品**] 和 [憑證 **] 儲存格中**插入的資料將無法編輯。</span><span class="sxs-lookup"><span data-stu-id="d75ed-531">Regarding product and certification: The data you insert in the **product** and **certification** cells cannot be edited after you import the spreadsheet to create or customize a template.</span></span> <span data-ttu-id="d75ed-532">此外，群組不能包含兩個具有相同**產品/認證**組合的評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-532">Also, a group cannot contain two assessments that have the same **product/certification** combination.</span></span> <span data-ttu-id="d75ed-533">您可以有多個範本具有相同的產品/認證組合。</span><span class="sxs-lookup"><span data-stu-id="d75ed-533">You can have multiple templates that have the same product/certification combination.</span></span>

##### <a name="controlfamily-tab"></a><span data-ttu-id="d75ed-534">ControlFamily] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="d75ed-534">ControlFamily tab</span></span>

<span data-ttu-id="d75ed-535">[ **ControlFamily** ] 索引標籤是必要的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-535">The **ControlFamily** tab is required.</span></span>  <span data-ttu-id="d75ed-536">此索引標籤中的必要欄（必須遵循範例試算表中提供的順序）為：</span><span class="sxs-lookup"><span data-stu-id="d75ed-536">The required columns in this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="d75ed-537">**controlName**：這是來自憑證、標準或法規（通常是某些類型的 ID）的控制項名稱。</span><span class="sxs-lookup"><span data-stu-id="d75ed-537">**controlName**: This is the control name from the certification, standard, or regulation, which is typically some type of ID.</span></span> <span data-ttu-id="d75ed-538">控制項名稱在範本內必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-538">Control names must be unique within a template.</span></span> <span data-ttu-id="d75ed-539">試算表中不可以有多個具有相同名稱的控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-539">You can't have multiple controls with the same name in the spreadsheet.</span></span>

- <span data-ttu-id="d75ed-540">**controlFamily**：提供 controlFamily 的單字或片語，它會識別控制項的廣泛群組。</span><span class="sxs-lookup"><span data-stu-id="d75ed-540">**controlFamily**: Provide a word or phrase for the controlFamily, which identifies a broad grouping of controls.</span></span> <span data-ttu-id="d75ed-541">ControlFamily 不必是唯一的;它可以在試算表中列出一次以上。</span><span class="sxs-lookup"><span data-stu-id="d75ed-541">A controlFamily doesn't have to be unique; it can be listed more than once in a spreadsheet.</span></span> <span data-ttu-id="d75ed-542">同一個 controlFamily 也可以列于多個範本中，但彼此之間彼此沒有關系。</span><span class="sxs-lookup"><span data-stu-id="d75ed-542">The same controlFamily can also be listed in multiple templates, though they have no relation to each other.</span></span> <span data-ttu-id="d75ed-543">每個 controlFamily 都必須對應至至少一個控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-543">Every controlFamily must be mapped to at least one control.</span></span>

- <span data-ttu-id="d75ed-544">**controlTitle**：提供控制項的標題。</span><span class="sxs-lookup"><span data-stu-id="d75ed-544">**controlTitle**: Provide a title for the control.</span></span> <span data-ttu-id="d75ed-545">雖然 controlName 是參考碼，但標題是一般會出現在規章中的 rtf 文字格式。</span><span class="sxs-lookup"><span data-stu-id="d75ed-545">Whereas the controlName is a reference code, the title is a rich text format typically seen in the regulations.</span></span>

- <span data-ttu-id="d75ed-546">**controlDescription**：提供控制項的描述。</span><span class="sxs-lookup"><span data-stu-id="d75ed-546">**controlDescription**: Provide a description of the control.</span></span>

- <span data-ttu-id="d75ed-547">**controlActionTitle**：這是您想要與此控制項相關之動作的標題。</span><span class="sxs-lookup"><span data-stu-id="d75ed-547">**controlActionTitle**: This is the title of an action that you want to relate to this control.</span></span> <span data-ttu-id="d75ed-548">您可以新增多個分號，並以兩個分號隔開，中間沒有空格。</span><span class="sxs-lookup"><span data-stu-id="d75ed-548">You can add multiple actions by separating by two semi-colons with no space in between.</span></span> <span data-ttu-id="d75ed-549">您清單中的每個控制項都必須至少包含一個動作，且該動作必須存在（這表示您可以在相同試算表的 [**動作**] 索引標籤上列出的動作，也就是 Microsoft 所建立的動作）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-549">Every control you list must include at least one action, and the action must exist (which means you can list an action that you list on the **Actions** tab of the same spreadsheet, an action that exists in a different template, or an action created by Microsoft).</span></span> <span data-ttu-id="d75ed-550">不同的控制項可以參照相同的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-550">Different controls can reference the same action.</span></span>

##### <a name="actions-tab"></a><span data-ttu-id="d75ed-551">動作] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="d75ed-551">Actions tab</span></span>

<span data-ttu-id="d75ed-552">[**動作**] 索引標籤是必要的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-552">The **Actions** tab is required.</span></span>  <span data-ttu-id="d75ed-553">它會指定您組織的動作，而不是 Microsoft 的動作，該動作已存在於合規性管理員中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-553">It designates actions of your organization and not the actions of Microsoft, which already exist in Compliance Manager.</span></span> <span data-ttu-id="d75ed-554">此索引標籤的必要欄（必須遵循範例試算表中提供的順序）為：</span><span class="sxs-lookup"><span data-stu-id="d75ed-554">The required columns for this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="d75ed-555">**actionTitle**：這是您動作的標題，而且是必要的欄位。</span><span class="sxs-lookup"><span data-stu-id="d75ed-555">**actionTitle**: This is the title for your action and is a required field.</span></span> <span data-ttu-id="d75ed-556">您提供的標題必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-556">The title you provide must be unique.</span></span> <span data-ttu-id="d75ed-557">**重要**：如果您參考的是已存在的動作（例如另一個範本），並在後續欄中修改其任何元素，這些變更將會傳播至其他範本中的相同動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-557">**Important**: if you reference an action you own that already exists (such as in another template) and you modify any of its elements in the subsequent columns, those changes will propagate to the same action in other templates.</span></span>

- <span data-ttu-id="d75ed-558">**implementationType**：在此必要欄位中，列出下列三種實施類型之一：</span><span class="sxs-lookup"><span data-stu-id="d75ed-558">**implementationType**: In this required field, list one of the three implementation types below:</span></span>
    - <span data-ttu-id="d75ed-559">**操作**-由人員和程式所執行的動作，以保護組織系統、資產、資料和人員的機密性、完整性和可用性（範例：安全性意識和訓練）</span><span class="sxs-lookup"><span data-stu-id="d75ed-559">**Operational** - actions implemented by people and processes to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: security awareness and training)</span></span>
    - <span data-ttu-id="d75ed-560">**技術**-透過使用資訊系統的硬體、軟體或固件元件所包含的技術和機制完成的動作，以保護組織系統和資料的機密性、完整性和可用性（範例：多重要素驗證）</span><span class="sxs-lookup"><span data-stu-id="d75ed-560">**Technical** - actions completed through the use of technology and mechanisms contained in the hardware, software, or firmware components of the information system to protect the confidentiality, integrity, and availability of organizational systems and data (example: multi-factor authentication)</span></span>
    - <span data-ttu-id="d75ed-561">**檔**-透過記錄的原則及程式所實施的動作，建立及定義保護組織系統、資產、資料和人員的機密性、完整性和可用性所需的控制項（範例：資訊安全性原則）</span><span class="sxs-lookup"><span data-stu-id="d75ed-561">**Documentation** - actions implemented through documented policies and procedures establishing and defining the controls required to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: an information security policy)</span></span>

- <span data-ttu-id="d75ed-562">**actionScore**：在這個必要的欄位中，為您的動作提供數值分數值。</span><span class="sxs-lookup"><span data-stu-id="d75ed-562">**actionScore**: In this required field, provide a numeric score value for your action.</span></span> <span data-ttu-id="d75ed-563">它必須是介於1到99的整數。它不得為0、null 或空白。</span><span class="sxs-lookup"><span data-stu-id="d75ed-563">It must be a whole number ranging from 1 to 99; it cannot be 0, null, or blank.</span></span> <span data-ttu-id="d75ed-564">數位越高，其價值越高，以改善您的相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="d75ed-564">The higher the number, the greater its value toward improving your compliance posture.</span></span> <span data-ttu-id="d75ed-565">如需相關指引，請參閱 Microsoft 如何評分其控制項：</span><span class="sxs-lookup"><span data-stu-id="d75ed-565">For guidance, see below how Microsoft scores its controls:</span></span>

<span data-ttu-id="d75ed-566">![合規性管理員控制點值](../media/compliance-score-controls-scoring.png "合規性管理員控制點值")</span><span class="sxs-lookup"><span data-stu-id="d75ed-566">![Compliance Manager controls point values](../media/compliance-score-controls-scoring.png "Compliance Manager controls point values")</span></span>

- <span data-ttu-id="d75ed-567">**actionDescriptionTitle**：這是描述的標題，而且是必要專案。</span><span class="sxs-lookup"><span data-stu-id="d75ed-567">**actionDescriptionTitle**: This is the title of the description and is required.</span></span> <span data-ttu-id="d75ed-568">此描述標題可讓您在多個範本中使用相同的動作，並在每個範本中呈現不同的描述。</span><span class="sxs-lookup"><span data-stu-id="d75ed-568">This description title allows you to have the same action in multiple templates and surface a different description in each template.</span></span>  <span data-ttu-id="d75ed-569">此欄位可協助您澄清描述所參照的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-569">This field helps you clarify what template the description is referencing.</span></span> <span data-ttu-id="d75ed-570">在大多數情況下，您可以在此欄位中放置您建立的範本名稱。</span><span class="sxs-lookup"><span data-stu-id="d75ed-570">In most cases, you can put the name of the template you're creating in this field.</span></span>

- <span data-ttu-id="d75ed-571">**actionDescription**：提供動作的描述。</span><span class="sxs-lookup"><span data-stu-id="d75ed-571">**actionDescription**: Provide a description of the action.</span></span> <span data-ttu-id="d75ed-572">您可以套用粗體文字和超連結等格式。</span><span class="sxs-lookup"><span data-stu-id="d75ed-572">You can apply formatting such as bold text and hyperlinks.</span></span> <span data-ttu-id="d75ed-573">這是必要欄位。</span><span class="sxs-lookup"><span data-stu-id="d75ed-573">This is required field.</span></span>

- <span data-ttu-id="d75ed-574">**維度-動作目的**：這是選用的欄位。</span><span class="sxs-lookup"><span data-stu-id="d75ed-574">**dimension-Action Purpose**: This is an optional field.</span></span> <span data-ttu-id="d75ed-575">如果包含此標頭，則標頭必須包含 "dimension" 前置詞。</span><span class="sxs-lookup"><span data-stu-id="d75ed-575">If you include it, the header must include the "dimension-" prefix.</span></span> <span data-ttu-id="d75ed-576">您將在此處包含的任何維度，都將做為[符合性分數中的篩選器](compliance-score-setup.md#filtering-your-dashboard-view)，並顯示在合規性分數的「改進動作詳細資料」頁面</span><span class="sxs-lookup"><span data-stu-id="d75ed-576">Any dimensions you include here will be used as [filters in Compliance Score](compliance-score-setup.md#filtering-your-dashboard-view) and appear on the improvement actions details page in Compliance Score.</span></span>

##### <a name="dimensions-tab"></a><span data-ttu-id="d75ed-577">維度] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="d75ed-577">Dimensions tab</span></span>

<span data-ttu-id="d75ed-578">[**維度**] 索引標籤是選用的。</span><span class="sxs-lookup"><span data-stu-id="d75ed-578">The **Dimensions** tab is optional.</span></span> <span data-ttu-id="d75ed-579">不過，如果您在其他位置參照維度，但如果它不存在於您已建立的範本或在 Microsoft 範本中，則需要在這裡加以指定。</span><span class="sxs-lookup"><span data-stu-id="d75ed-579">However, if you reference a dimension elsewhere, you need to specify it here if it does not exist in a template you've already created or in a Microsoft template.</span></span> <span data-ttu-id="d75ed-580">此索引標籤的欄如下所示：</span><span class="sxs-lookup"><span data-stu-id="d75ed-580">The columns for this tab are listed below:</span></span>

- <span data-ttu-id="d75ed-581">**dimensionKey**：清單為 "product"，"認證，" 「動作目的」</span><span class="sxs-lookup"><span data-stu-id="d75ed-581">**dimensionKey**: list as "product", "certifications," "action purpose"</span></span>
- <span data-ttu-id="d75ed-582">**dimensionValue**：範例： Office 365、HIPPA、預防性、偵探</span><span class="sxs-lookup"><span data-stu-id="d75ed-582">**dimensionValue**: examples: Office 365, HIPPA, Preventative, Detective</span></span>

<span data-ttu-id="d75ed-583">您可以前往**租使用者管理**，然後選取 [**維度**] 索引標籤，以查看現有的維度。此外，當您匯出現有的範本時，匯出的試算表會有 [**維度**] 索引標籤，該索引標籤會列出範本中所用的所有維度。</span><span class="sxs-lookup"><span data-stu-id="d75ed-583">You can view your existing dimensions by going to **Tenant Management** and selecting the **Dimensions** tab. Also, anytime you export an existing template, the exported spreadsheet will have the **Dimensions** tab, which lists all the dimensions used in the template.</span></span>

### <a name="modify-an-existing-template"></a><span data-ttu-id="d75ed-584">修改現有範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-584">Modify an existing Template</span></span>

<span data-ttu-id="d75ed-585">若要使用以上所述的匯入程式，對您建立或自訂的範本進行變更，您可以使用相同的程式，將這些變更匯入至您的範本。</span><span class="sxs-lookup"><span data-stu-id="d75ed-585">To make changes to a Template you created or customized using the import process outlined above, you use the same process to import those changes into your Template.</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-586">編輯範本元件時，請注意許多重要因素，因此請仔細閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="d75ed-586">There are several important factors to be aware of as you edit template components, so please review this section carefully.</span></span>

#### <a name="general-process-for-modifying-a-template"></a><span data-ttu-id="d75ed-587">修改範本的一般程式</span><span class="sxs-lookup"><span data-stu-id="d75ed-587">General process for modifying a Template</span></span>

<span data-ttu-id="d75ed-588">若要變更組織的現有範本之一，一般處理常式如下：</span><span class="sxs-lookup"><span data-stu-id="d75ed-588">To make changes to one of your organization's existing templates, the general process is:</span></span>

1. <span data-ttu-id="d75ed-589">從您的**範本**儀表板中，選取您要修改的範本，它會彈出您的 [**控制項資訊**] 儀表板，顯示**範本**索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d75ed-589">From your **Templates** dashboard, select the Template you want to modify, which brings up your **Controls Info** dashboard showing your **Template** tab.</span></span>
2. <span data-ttu-id="d75ed-590">從這裡，選取 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-590">From here, select **Export**.</span></span> <span data-ttu-id="d75ed-591">將下載所有範本資料的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="d75ed-591">An Excel sheet with all your template data will download.</span></span>
3. <span data-ttu-id="d75ed-592">若要編輯、新增或移除動作，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="d75ed-592">To edit, add, or remove an action, see the sections below.</span></span>
4. <span data-ttu-id="d75ed-593">當您完成 Excel 檔案的變更後，請從儀表板選取範本，然後選取 [匯入]，將檔案匯入**範本。**</span><span class="sxs-lookup"><span data-stu-id="d75ed-593">When you're done making changes to your Excel file, import the file back into the template by selecting the template from your dashboard and selecting **Import**.</span></span> <span data-ttu-id="d75ed-594">您的範本現在會包含您所做的變更。</span><span class="sxs-lookup"><span data-stu-id="d75ed-594">Your template will now include the changes you made.</span></span>

#### <a name="to-edit-template-attributes"></a><span data-ttu-id="d75ed-595">編輯範本屬性</span><span class="sxs-lookup"><span data-stu-id="d75ed-595">To edit Template attributes</span></span>

<span data-ttu-id="d75ed-596">在 [**範本**] 索引標籤上，您可以編輯 [**標題**] 欄中的任何專案、[ **inScopeServices** ] 欄，以及您可能新增的任何其他欄位。</span><span class="sxs-lookup"><span data-stu-id="d75ed-596">On the **Templates** tab, you can edit anything in the **title** column, the **inScopeServices** column, and in any other column you may have added.</span></span> <span data-ttu-id="d75ed-597">不過，您無法在 [**產品**] 或 [**認證**] 欄中編輯任何專案。</span><span class="sxs-lookup"><span data-stu-id="d75ed-597">However, you can't edit anything in the **product** or **certification** columns.</span></span>

#### <a name="to-add-an-action-to-a-template"></a><span data-ttu-id="d75ed-598">若要將動作新增至範本</span><span class="sxs-lookup"><span data-stu-id="d75ed-598">To add an action to a Template</span></span>

1. <span data-ttu-id="d75ed-599">移至 [**動作**] 索引標籤，並將您的資訊新增至現有動作下方第一個空白列的必要欄位中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-599">Go to the **Actions** tab and add your information in the required fields in the first empty row underneath your existing actions.</span></span>
2. <span data-ttu-id="d75ed-600">移至 [ **ControlFamily** ] 索引標籤。找到包含您動作所對應之控制項的列。</span><span class="sxs-lookup"><span data-stu-id="d75ed-600">Go to your **ControlFamily** tab. Find the row containing the control your action maps to.</span></span> <span data-ttu-id="d75ed-601">將您的新動作新增至該資料列中的 [ **controlActionTitle** ] 欄（請記得在此欄位中分隔多個動作，並使用兩個分號，其間沒有間距）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-601">Add your new action to the **controlActionTitle** column in that row (remember to separate multiple actions in this field with two semi-colons, no space in between).</span></span>
3. <span data-ttu-id="d75ed-602">將試算表儲存至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d75ed-602">Save your spreadsheet to your local machine.</span></span>

#### <a name="to-edit-an-actions-information"></a><span data-ttu-id="d75ed-603">編輯動作的資訊</span><span class="sxs-lookup"><span data-stu-id="d75ed-603">To edit an action's information</span></span>

<span data-ttu-id="d75ed-604">您可以變更*其標題以外*的任何動作的資訊。</span><span class="sxs-lookup"><span data-stu-id="d75ed-604">You can change any action's information *except for its title*.</span></span> <span data-ttu-id="d75ed-605">您可以編輯來自 B + + 的任何儲存格，當您將檔案重新匯入範本時，該範本中的動作現在會包含更新的資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-605">You can edit any cell from columns B onward, and when you import the file back into the template, the actions in that template will now contain the updated data.</span></span>

<span data-ttu-id="d75ed-606">您無法編輯**actionTitle** （A 欄），因為如果您這麼做，合規性管理員會將此項視為新的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-606">You cannot edit the **actionTitle** (column A) because if you do, Compliance Manager considers this to be a new action.</span></span> <span data-ttu-id="d75ed-607">如果您想要變更動作的名稱，請參閱下列直接的指示。</span><span class="sxs-lookup"><span data-stu-id="d75ed-607">If you want to change an action's name, see the instructions immediately below.</span></span>

#### <a name="to-change-the-name-of-an-action"></a><span data-ttu-id="d75ed-608">變更動作名稱</span><span class="sxs-lookup"><span data-stu-id="d75ed-608">To change the name of an action</span></span>

<span data-ttu-id="d75ed-609">如果您想要變更動作名稱，您必須在試算表中明確指定您要以新名稱取代現有名稱。</span><span class="sxs-lookup"><span data-stu-id="d75ed-609">If you want to change the name of an action, you have to explicitly designate in the spreadsheet that you are replacing an existing name with a new name.</span></span> <span data-ttu-id="d75ed-610">若要變更動作的名稱，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d75ed-610">To change an action's name, follow these steps:</span></span>

1. <span data-ttu-id="d75ed-611">在試算表的 [**動作**] 索引標籤中，將新欄新增至 a 欄後的試算表中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-611">In the **Actions** tab of your spreadsheet, add a new column to the spreadsheet after column A.</span></span>
2. <span data-ttu-id="d75ed-612">在這個新欄中（現在是 B 欄），置於第1列： **oldActionTitle**中的標題。</span><span class="sxs-lookup"><span data-stu-id="d75ed-612">In this new column, which is now column B, put as its header in row 1: **oldActionTitle**.</span></span>
3. <span data-ttu-id="d75ed-613">複製欄 A 的內容，並將其貼到 B 欄中。這會將您現有的動作標題（即您想變更的專案）放入 B 欄中。</span><span class="sxs-lookup"><span data-stu-id="d75ed-613">Copy the contents of column A and paste them into column B. This puts your existing action titles, which are what you want to change, into column B.</span></span>
4. <span data-ttu-id="d75ed-614">在 [欄位 A] 中， **actionTitle**] 刪除舊名稱，並以新名稱取代為您的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-614">In column A, **actionTitle**, delete the old name and replace it with the new name for your action.</span></span>

#### <a name="to-remove-an-action-from-a-template"></a><span data-ttu-id="d75ed-615">移除範本中的動作</span><span class="sxs-lookup"><span data-stu-id="d75ed-615">To remove an action from a Template</span></span>

<span data-ttu-id="d75ed-616">從試算表中刪除某列的動作，**並不會**從您正在編輯的範本中移除動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-616">Deleting an action from a row in a spreadsheet **does not** remove the action from the template you're editing.</span></span> <span data-ttu-id="d75ed-617">相反地，請遵循下列程式移除動作：</span><span class="sxs-lookup"><span data-stu-id="d75ed-617">Instead, follow the process below to remove an action:</span></span>

1. <span data-ttu-id="d75ed-618">在 [**動作**] 索引標籤上，插入新欄做為 a 欄位，並將**作業放在**標題列中，也就是第一個資料行。</span><span class="sxs-lookup"><span data-stu-id="d75ed-618">On the **Actions** tab, insert a new column as column A and put **Operation** in the header row, which is row number one.</span></span>
2. <span data-ttu-id="d75ed-619">在您要移除之動作的列上，在該列的 A 欄中將**Delete**放入該資料行。</span><span class="sxs-lookup"><span data-stu-id="d75ed-619">On the row for the action you want to remove, put **Delete** in column A for that row.</span></span>
3. <span data-ttu-id="d75ed-620">請確定此巨集指令不再是控制項的參照。</span><span class="sxs-lookup"><span data-stu-id="d75ed-620">Ensure that this action is no longer referenced by a control.</span></span> <span data-ttu-id="d75ed-621">移至 [ **ControlFamily** ] 索引標籤，並在 F 欄中尋找動作的標題，也就是**controlActionTitle**。</span><span class="sxs-lookup"><span data-stu-id="d75ed-621">Go to the **ControlFamily** tab and look for your action's title in column F, which is **controlActionTitle**.</span></span>
4. <span data-ttu-id="d75ed-622">當您找到您列在 [ **controlActionTitle** ] 欄中的動作時，請加以刪除。</span><span class="sxs-lookup"><span data-stu-id="d75ed-622">When you find your action listed in the **controlActionTitle** column, delete it.</span></span>
5. <span data-ttu-id="d75ed-623">將試算表儲存至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d75ed-623">Save your spreadsheet to your local machine.</span></span>

<span data-ttu-id="d75ed-624">當您將試算表重新匯入範本時，您的動作將會從範本移除。</span><span class="sxs-lookup"><span data-stu-id="d75ed-624">When you import your spreadsheet back into the template, your action will be removed from the template.</span></span> <span data-ttu-id="d75ed-625">從範本移除動作不會完全移除動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-625">Removing an action from a template does not completely remove the action.</span></span> <span data-ttu-id="d75ed-626">該動作仍可由另一個範本參照。</span><span class="sxs-lookup"><span data-stu-id="d75ed-626">That action can still be referenced by another template.</span></span>

<span data-ttu-id="d75ed-627">如果您要移除控制項所參照的最後一個動作，您必須移除該控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-627">If you are removing the last action that a control references, then you need to remove the control.</span></span>

> [!NOTE]
> <span data-ttu-id="d75ed-628">若要移除控制項：請遵循相同的程式移除如上所述的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-628">To remove a control: Follow the same process for removing an action as outlined above.</span></span> <span data-ttu-id="d75ed-629">在 [ **ControlFamily** ] 索引標籤中，新增 [作業 **] 欄，** 並將 [**刪除**] 放在您要移除的控制項旁。</span><span class="sxs-lookup"><span data-stu-id="d75ed-629">In the **ControlFamily** tab, add an **Operation** column and put **Delete** next to the control you want to remove.</span></span>

### <a name="updates-to-templates"></a><span data-ttu-id="d75ed-630">範本的更新</span><span class="sxs-lookup"><span data-stu-id="d75ed-630">Updates to Templates</span></span>

<span data-ttu-id="d75ed-631">每次透過版本設定程式更新評估時，您的自訂評估會繼承這些更新，並保留您的自訂控制項。</span><span class="sxs-lookup"><span data-stu-id="d75ed-631">Each time an Assessment is updated through the versioning process, your customized Assessment will inherit those updates and keep your custom controls.</span></span> <span data-ttu-id="d75ed-632">請參閱「[評估更新的版本設定警示](#versioning-alerts-for-assessment-updates)」。</span><span class="sxs-lookup"><span data-stu-id="d75ed-632">See [Versioning alerts for Assessment updates](#versioning-alerts-for-assessment-updates).</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="d75ed-633">將範本匯出至 JSON</span><span class="sxs-lookup"><span data-stu-id="d75ed-633">Export a Template to JSON</span></span>

<span data-ttu-id="d75ed-634">合規性管理員（預覽）支援將範本匯出為 JavaScript 物件標記法（JSON）格式。</span><span class="sxs-lookup"><span data-stu-id="d75ed-634">Compliance Manager (Preview) supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="d75ed-635">這可讓您將合規性管理員資料與其他支援 JSON 的系統交換。</span><span class="sxs-lookup"><span data-stu-id="d75ed-635">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="d75ed-636">報告</span><span class="sxs-lookup"><span data-stu-id="d75ed-636">Reports</span></span>

<span data-ttu-id="d75ed-637">您可以將評估匯出至您組織中或外部審計員和主管的符合性專案關係人的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="d75ed-637">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="d75ed-638">報表是指匯出之日期和時間為止的評估快照。</span><span class="sxs-lookup"><span data-stu-id="d75ed-638">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="d75ed-639">報告包含 Microsoft 及客戶管理控制項的詳細資料，以供評估、控制執行狀態、控制測試日期、測試結果和上傳的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="d75ed-639">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="d75ed-640">因為隱藏評估未保留上載檔的連結，所以您應該先匯出評估，再將其隱藏。</span><span class="sxs-lookup"><span data-stu-id="d75ed-640">Because hidden Assessments don't retain links to uploaded documents, you should export the Assessment before you hide it.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="d75ed-641">匯出評估</span><span class="sxs-lookup"><span data-stu-id="d75ed-641">Export an Assessment</span></span>

1. <span data-ttu-id="d75ed-642">在 [合規性管理員] 儀表板上，選取 [**控制項資訊**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d75ed-642">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="d75ed-643">在下拉式功能表中，選取您要匯出之評估的群組和評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-643">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="d75ed-644">選取 [匯出]。</span><span class="sxs-lookup"><span data-stu-id="d75ed-644">Select Export.</span></span> <span data-ttu-id="d75ed-645">評估匯出會下載成 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="d75ed-645">The Assessment export is downloaded as an Excel file.</span></span>

<span data-ttu-id="d75ed-646">![合規性管理員評估 Excel 報告](../media/compliance-manager-assessment-report.png "合規性管理員評估 Excel 報告")</span><span class="sxs-lookup"><span data-stu-id="d75ed-646">![Compliance Manager Assessment Excel Report](../media/compliance-manager-assessment-report.png "Compliance Manager assessment Excel report")</span></span>

## <a name="permissions"></a><span data-ttu-id="d75ed-647">權限</span><span class="sxs-lookup"><span data-stu-id="d75ed-647">Permissions</span></span>

<span data-ttu-id="d75ed-648">下表說明每個合規性管理員許可權及其允許使用者執行的動作。</span><span class="sxs-lookup"><span data-stu-id="d75ed-648">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="d75ed-649">該表也會指出指派每個許可權的角色。</span><span class="sxs-lookup"><span data-stu-id="d75ed-649">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="d75ed-650">**Azure AD 全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="d75ed-650">**Azure AD Global Reader**</span></span>|<span data-ttu-id="d75ed-651">**合規性管理員讀取者**</span><span class="sxs-lookup"><span data-stu-id="d75ed-651">**Compliance Manager Reader**</span></span>|<span data-ttu-id="d75ed-652">**合規性參與者**</span><span class="sxs-lookup"><span data-stu-id="d75ed-652">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="d75ed-653">**合規性管理員評估者**</span><span class="sxs-lookup"><span data-stu-id="d75ed-653">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="d75ed-654">**合規性管理員管理者**</span><span class="sxs-lookup"><span data-stu-id="d75ed-654">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="d75ed-655">**入口網站管理員**</span><span class="sxs-lookup"><span data-stu-id="d75ed-655">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d75ed-656">**讀取資料：** 使用者可以讀取但不能編輯資料（範本資料和租使用者管理除外）。</span><span class="sxs-lookup"><span data-stu-id="d75ed-656">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="d75ed-657">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-657">X</span></span> | <span data-ttu-id="d75ed-658">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-658">X</span></span> | <span data-ttu-id="d75ed-659">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-659">X</span></span> | <span data-ttu-id="d75ed-660">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-660">X</span></span> | <span data-ttu-id="d75ed-661">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-661">X</span></span>  | <span data-ttu-id="d75ed-662">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-662">X</span></span> |
|<span data-ttu-id="d75ed-663">**編輯資料：** 除了 [測試結果] 和 [測試日期] 欄位（範本資料和租使用者管理以外）以外，使用者可以編輯所有欄位。</span><span class="sxs-lookup"><span data-stu-id="d75ed-663">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="d75ed-664">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-664">X</span></span> | <span data-ttu-id="d75ed-665">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-665">X</span></span>  | <span data-ttu-id="d75ed-666">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-666">X</span></span> | <span data-ttu-id="d75ed-667">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-667">X</span></span> |
|<span data-ttu-id="d75ed-668">**編輯測試結果：** 使用者可以編輯 [測試結果] 和 [測試日期] 欄位。</span><span class="sxs-lookup"><span data-stu-id="d75ed-668">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="d75ed-669">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-669">X</span></span> | <span data-ttu-id="d75ed-670">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-670">X</span></span> | <span data-ttu-id="d75ed-671">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-671">X</span></span> |
|<span data-ttu-id="d75ed-672">**管理評估：** 使用者可以建立、封存和刪除評估。</span><span class="sxs-lookup"><span data-stu-id="d75ed-672">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="d75ed-673">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-673">X</span></span> | <span data-ttu-id="d75ed-674">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-674">X</span></span> |
|<span data-ttu-id="d75ed-675">**管理主資料：** 使用者可以查看、編輯和刪除範本資料及承租人管理資料。</span><span class="sxs-lookup"><span data-stu-id="d75ed-675">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="d75ed-676">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-676">X</span></span> | <span data-ttu-id="d75ed-677">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-677">X</span></span> |
|<span data-ttu-id="d75ed-678">**管理使用者：** 使用者可以將組織中的其他使用者新增至讀者、投稿人、Assessor 及系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="d75ed-678">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="d75ed-679">只有在您組織中具有全域系統管理員角色的使用者，才可以從入口網站管理員角色新增或移除使用者。</span><span class="sxs-lookup"><span data-stu-id="d75ed-679">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="d75ed-680">X</span><span class="sxs-lookup"><span data-stu-id="d75ed-680">X</span></span> |