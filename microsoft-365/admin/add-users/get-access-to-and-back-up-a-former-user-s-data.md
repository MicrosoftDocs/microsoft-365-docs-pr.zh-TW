---
title: 存取及備份離職使用者的資料
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: 瞭解如何在人員離開組織時保留員工的檔案和電子郵件。
ms.openlocfilehash: 32f64efb30acb5438e5add8bcb897200951e6362
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780610"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="3a7e4-103">存取及備份離職使用者的資料</span><span class="sxs-lookup"><span data-stu-id="3a7e4-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="3a7e4-104">當員工離開您的組織時，您可能會想要存取其資料（檔和電子郵件），並對其進行備份，或是將它備份或提供給新員工。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="3a7e4-105">存取先前使用者的 OneDrive 檔</span><span class="sxs-lookup"><span data-stu-id="3a7e4-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="3a7e4-106">如果您移除使用者的授權，但沒有刪除帳戶，您可以讓自己存取使用者 OneDrive 中的內容。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="3a7e4-107">如果您刪除使用者帳戶，則預設會有30天的時間來存取先前使用者的 OneDrive 資料。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="3a7e4-108">[瞭解如何為已刪除的使用者設定 OneDrive 保留](/onedrive/set-retention)。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="3a7e4-109">如果您在這段時間內沒有[還原使用者帳戶](/office365/admin/add-users/restore-user)，其 OneDrive 內容就會被刪除。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="3a7e4-110">若要保留先前使用者的 OneDrive 檔案，請先讓您自行存取 OneDrive，然後移動您想要保留的檔案。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3a7e4-111">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="3a7e4-112">選取使用者。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-112">Select a user.</span></span>

3. <span data-ttu-id="3a7e4-113">在右窗格中，選取 [ **OneDrive**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-113">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="3a7e4-114">在 [**存取**檔案] 底下，選取 [**建立檔的連結**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-114">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="3a7e4-115">選取連結以開啟檔案位置。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-115">Select the link to open the file location.</span></span> <span data-ttu-id="3a7e4-116">將檔案下載至您的電腦，或選取 [**移至**] 或 [**複製至**] 以移動或複製至您自己的 OneDrive 或共用文件庫。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-116">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="3a7e4-117">您一次最多可以移動或複製 500 MB 的檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-117">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="3a7e4-118">當您移動或複製具有版本記錄的檔時，只會移動最新的版本。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-118">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3a7e4-119">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="3a7e4-120">選取使用者。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-120">Select a user.</span></span>

3. <span data-ttu-id="3a7e4-121">在右窗格中，展開 [ **OneDrive 設定**]，然後按一下 [**存取**] 旁的 [**存取**檔案]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-121">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="3a7e4-122">選取連結以開啟檔案位置。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-122">Select the link to open the file location.</span></span> <span data-ttu-id="3a7e4-123">將檔案下載至您的電腦，或選取 [**移至**] 或 [**複製至**] 以移動或複製至您自己的 OneDrive 或共用文件庫。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-123">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="3a7e4-124">您一次最多可以移動或複製 500 MB 的檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-124">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="3a7e4-125">當您移動或複製具有版本記錄的檔時，只會移動最新的版本。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-125">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3a7e4-126">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="3a7e4-127">選取使用者。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-127">Select a user.</span></span>

3. <span data-ttu-id="3a7e4-128">在右窗格中，展開 [ **OneDrive 設定**]，然後按一下 [**存取**] 旁的 [**存取**檔案]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-128">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="3a7e4-129">選取連結以開啟檔案位置。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-129">Select the link to open the file location.</span></span> <span data-ttu-id="3a7e4-130">將檔案下載至您的電腦，或選取 [**移至**] 或 [**複製至**] 以移動或複製至您自己的 OneDrive 或共用文件庫。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-130">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="3a7e4-131">您一次最多可以移動或複製 500 MB 的檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-131">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="3a7e4-132">當您移動或複製具有版本記錄的檔時，只會移動最新的版本。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-132">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="3a7e4-133">撤銷使用者 OneDrive 的系統管理員存取權</span><span class="sxs-lookup"><span data-stu-id="3a7e4-133">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="3a7e4-134">如同全域系統管理員，您可以在使用者的 OneDrive 中存取內容，但您可能想要在不再需要時移除存取權。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-134">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3a7e4-135"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">以全域</a>系統管理員身分登入系統管理員或 SharePoint 管理員。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-135">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="3a7e4-136">如果您收到的訊息您沒有存取系統管理中心的許可權，則您的組織不具備系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-136">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3a7e4-137"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">以全域</a>系統管理員身分登入系統管理員或 SharePoint 管理員。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-137">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="3a7e4-138">如果您收到的訊息您沒有存取系統管理中心的許可權，則您的組織不具備系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-138">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3a7e4-139"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">以全域</a>系統管理員身分登入系統管理員或 SharePoint 管理員。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-139">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="3a7e4-140">如果您收到的訊息您沒有存取系統管理中心的許可權，則您的組織不具備系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-140">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="3a7e4-141">在左窗格中，選取 [系統**管理中心**] \> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-141">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="3a7e4-142">(您可能需要選取 [全部顯示]\*\*\*\* 才能查看系統管理中心的清單。)</span><span class="sxs-lookup"><span data-stu-id="3a7e4-142">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="3a7e4-143">如果出現 [傳統 SharePoint 系統管理中心]，請選取 [立即在頁面頂端開啟]，以開啟 SharePoint**系統**管理中心。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-143">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="3a7e4-144">在左窗格中，選取 [**其他功能**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-144">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="3a7e4-145">在 [**使用者設定檔**] 下，選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-145">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="3a7e4-146">在 [**人員**] 底下，選取 [**管理使用者設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-146">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="3a7e4-147">輸入使用者的名稱，然後選取 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-147">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="3a7e4-148">以滑鼠右鍵按一下使用者，然後選擇 [**管理網站集合擁有**者]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-148">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="3a7e4-149">移除不再需要存取使用者資料的人員，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-149">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="3a7e4-150">存取先前使用者的 Outlook 資料</span><span class="sxs-lookup"><span data-stu-id="3a7e4-150">Access the Outlook data of a former user</span></span>

<span data-ttu-id="3a7e4-151">若要儲存先前員工的電子郵件、行事曆、工作和連絡人，請將資訊匯出至 Outlook 資料檔案（.pst）。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-151">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="3a7e4-152">[將離職員工的電子郵件新增](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)至您的 Outlook （如果您[重設使用者的密碼](reset-passwords.md)，您可以將它設定為您知道的內容）。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-152">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="3a7e4-153">在 Outlook 中，**選取 [** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-153">In Outlook, select **File**.</span></span>
    
    ![這是功能區在 Outlook 2016 中的外觀。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="3a7e4-155">選取 [**開啟 &amp; 匯出**匯 \> **入/匯出**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-155">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Backstage 檢視中的匯入/匯出命令](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="3a7e4-157">選取 [**匯出至**檔案]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-157">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![匯出至 [匯入及匯出] 嚮導中的 [檔案] 選項](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="3a7e4-159">選取 [ **Outlook 資料檔案（.pst）**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-159">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="3a7e4-160">選取您要匯出的帳戶，方法是選取其名稱或電子郵件地址，例如信箱-Anne Weiler 或 anne@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-160">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="3a7e4-161">如果您想要匯出帳戶中的所有內容，包括郵件、行事曆、連絡人、工作和附注，請確定已選取 [**包含子資料夾**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-161">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3a7e4-162">您一次可以匯出一個帳戶。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-162">You can export one account at a time.</span></span> <span data-ttu-id="3a7e4-163">如果您想要匯出多個帳戶，請在匯出一個帳戶後，重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-163">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![選取上方資料夾並包含檢查子資料夾的 [匯出 Outlook 資料檔案] 對話方塊](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="3a7e4-165">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-165">Select **Next**.</span></span>
    
8. <span data-ttu-id="3a7e4-166">選取 **[流覽]** 以選取要儲存 Outlook 資料檔案（.pst）的位置。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-166">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="3a7e4-167">輸入檔案名 *，然後*選取 **[確定]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-167">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3a7e4-168">如果您以前已使用 export，就會出現上一個資料夾位置和檔案名。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-168">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="3a7e4-169">請輸入*其他*的檔案名，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-169">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="3a7e4-170">若要匯出至現有的 Outlook 資料檔（.pst），請在 [**選項**] 下，指定匯出檔案中已存在的專案時要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-170">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="3a7e4-171">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="3a7e4-171">Select **Finish**.</span></span>
    
<span data-ttu-id="3a7e4-172">Outlook 會立即開始匯出，除非已建立新的 Outlook 資料檔（.pst）或使用密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-172">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="3a7e4-173">如果您正在建立 Outlook 資料檔案（.pst），選用密碼可協助保護檔案。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-173">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="3a7e4-174">當 [**建立 Outlook 資料檔案**] 對話方塊出現時，在 [**密碼**] 和 [**確認密碼**] 方塊中輸入*密碼*，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-174">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="3a7e4-175">在 [ **Outlook 資料檔案密碼**] 對話方塊中，輸入*密碼*，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-175">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="3a7e4-176">如果您要匯出的現有 Outlook 資料檔案（.pst）是受密碼保護，請在 [ **Outlook 資料檔案密碼**] 對話方塊中，輸入*密碼*，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-176">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="3a7e4-177">請參閱如何[將電子郵件、連絡人及行事曆匯出或備份至 outlook 2010 中的 outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)檔案。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-177">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="3a7e4-178">根據預設，您的電子郵件在12個月內可供離線使用。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-178">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="3a7e4-179">如有需要，請參閱 how to[增加可離線使用的資料](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-179">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="3a7e4-180">讓另一位使用者能夠存取先前使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="3a7e4-180">Give another user access to a former user's email</span></span> 

<span data-ttu-id="3a7e4-181">若要將離職員工的電子郵件、行事曆、工作和連絡人的存取權授與另一個員工，請將此資訊匯入另一個員工的 Outlook 收件匣。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-181">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="3a7e4-182">您也可以[將先前使用者的信箱轉換成共用信箱，或將](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox)[離職員工的電子郵件轉寄給另一個員工](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-182">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="3a7e4-183">在 Outlook 中，移**至 [** 檔案] [ \> **開啟 &amp; 匯出**] [匯 \> **入/匯出**]。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-183">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="3a7e4-184">這會啟動 [匯入及匯出] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-184">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="3a7e4-185">選取 [**從其他程式或**檔案匯入]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-185">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![匯入及匯出嚮導](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="3a7e4-187">選取 [ **Outlook 資料檔案（.pst）**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-187">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="3a7e4-188">流覽至您要匯入的 .pst 檔案。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-188">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="3a7e4-189">在 [**選項**] 底下，選擇您要處理重複專案的方式</span><span class="sxs-lookup"><span data-stu-id="3a7e4-189">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="3a7e4-190">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-190">Select **Next**.</span></span>
    
7. <span data-ttu-id="3a7e4-191">如果已指派密碼給 Outlook 資料檔案（.pst），請輸入密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-191">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="3a7e4-192">設定匯入專案的選項。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-192">Set the options for importing items.</span></span> <span data-ttu-id="3a7e4-193">通常不需要變更預設設定。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-193">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="3a7e4-194">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="3a7e4-194">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="3a7e4-195">存取現有使用者的 OneDrive 和電子郵件資料時，這些步驟會保持不變。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-195">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="3a7e4-196">如果您只想匯入或還原 Outlook 資料檔（.pst）中的幾個專案，您可以開啟 Outlook 資料檔案。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-196">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="3a7e4-197">然後，在功能窗格中，將 [Outlook 資料檔案資料夾] 中的專案拖曳到現有的 Outlook 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="3a7e4-197">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="3a7e4-198">相關文章</span><span class="sxs-lookup"><span data-stu-id="3a7e4-198">Related articles</span></span>
[<span data-ttu-id="3a7e4-199">從 Office 365 中移除前任員工</span><span class="sxs-lookup"><span data-stu-id="3a7e4-199">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="3a7e4-200">在 OneDrive 帳戶上新增及移除系統管理員</span><span class="sxs-lookup"><span data-stu-id="3a7e4-200">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="3a7e4-201">還原已刪除的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="3a7e4-201">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="3a7e4-202">OneDrive 保留與刪除</span><span class="sxs-lookup"><span data-stu-id="3a7e4-202">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
