---
title: 在系統管理中心部署增益集
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用系統管理中心的集中式部署，將外掛程式部署到貴組織的使用者和群組。
ms.openlocfilehash: ef7237f20780cb67bc84561ad8617dd8da6f8b82
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926351"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="28347-103">在系統管理中心部署增益集</span><span class="sxs-lookup"><span data-stu-id="28347-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="28347-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="28347-104">The admin center is changing.</span></span> <span data-ttu-id="28347-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="28347-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="28347-106">Office 增益集可以協助您將文件個人化，也可以簡化您存取網路資訊的方式 (請參閱[開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="28347-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="28347-107">系統管理員可以使用 Microsoft 365 系統管理中心的集中式部署功能，為貴組織的使用者部署 Office 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="28347-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="28347-108">若要將外掛程式部署到組織內部的使用者和群組，集中式部署是建議大多數系統管理員採用且功能最豐富的方法。</span><span class="sxs-lookup"><span data-stu-id="28347-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="28347-109">若要瞭解如何判斷貴組織是否可支援集中式部署，請參閱判斷貴組織是否適合使用集中式部署來 [部署附加元件](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="28347-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="28347-110">若要深入瞭解在部署後管理附加元件，請參閱在系統管理中心管理 [外掛程式](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="28347-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="28347-111">針對 Word，Excel 和 PowerPoint 會使用 [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 應用程式目錄，在內部部署環境中將外掛程式部署到使用者，而不需要連至 Microsoft 365 和/或 SharePoint 需要之支援。</span><span class="sxs-lookup"><span data-stu-id="28347-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="28347-112">針對 Outlook，請使用 Exchange 控制台在內部部署環境中部署，而不需要連至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="28347-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="28347-113">部署 Office 增益集的建議方式</span><span class="sxs-lookup"><span data-stu-id="28347-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="28347-114">若要使用階段方法推出附加元件，建議您進行下列操作：</span><span class="sxs-lookup"><span data-stu-id="28347-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="28347-115">向一小組商務專案關係人以及 IT 部門的成員推出此附加元件。</span><span class="sxs-lookup"><span data-stu-id="28347-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="28347-116">如果部署成功，請移至步驟 2。</span><span class="sxs-lookup"><span data-stu-id="28347-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="28347-117">為更多企業內部人員推出此附加元件。</span><span class="sxs-lookup"><span data-stu-id="28347-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="28347-118">再次評估結果，如果成功，請繼續進行完整部署。</span><span class="sxs-lookup"><span data-stu-id="28347-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="28347-119">對所有使用者執行完整推出。</span><span class="sxs-lookup"><span data-stu-id="28347-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="28347-120">視目標物件的大小不同，您可以新增或移除推出步驟。</span><span class="sxs-lookup"><span data-stu-id="28347-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="28347-121">使用系統管理中心部署 Office 外掛程式</span><span class="sxs-lookup"><span data-stu-id="28347-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="28347-122">開始之前，請參閱判斷貴組織是否適合使用集中式部署 [來部署附加元件](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="28347-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="28347-123">在系統管理中心中，前往設定 \> **載入碼** 頁面。</span><span class="sxs-lookup"><span data-stu-id="28347-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="28347-124">如果您沒看到載入 **元件頁面，** 請前往設定整合式應用程式 \>  \> **載入元件** 頁面。</span><span class="sxs-lookup"><span data-stu-id="28347-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="28347-125">選取 **頁面頂端的部署** 載入元件，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="28347-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="28347-126">系統管理中心已更新為整合式應用程式的部署體驗。</span><span class="sxs-lookup"><span data-stu-id="28347-126">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="28347-127">如果您沒看到上述步驟，請前往設定整合式應用程式，以前往集中式部署  >  **區段**。</span><span class="sxs-lookup"><span data-stu-id="28347-127">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="28347-128">在整合式應用程式 **頁面的頂端** ，選擇 **載入元件**。</span><span class="sxs-lookup"><span data-stu-id="28347-128">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="28347-129">選取一個選項，然後按照指示進行。</span><span class="sxs-lookup"><span data-stu-id="28347-129">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="28347-130">如果您選取了從 Office 市儲存新增附加元件的選項，請選取您的附加元件。</span><span class="sxs-lookup"><span data-stu-id="28347-130">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="28347-131">您可以按類別來查看可用的附加元件：**針對** 您建議、**評分或\*\*\*\*名稱**。</span><span class="sxs-lookup"><span data-stu-id="28347-131">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="28347-132">Office 市儲存僅提供免費的附加元件。</span><span class="sxs-lookup"><span data-stu-id="28347-132">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="28347-133">目前尚不支援付費增益集。</span><span class="sxs-lookup"><span data-stu-id="28347-133">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="28347-134">選取某個附加元件之後，請接受條款與條件以繼續進行。</span><span class="sxs-lookup"><span data-stu-id="28347-134">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="28347-135">使用 Office 市儲存區選項時，更新和增強功能會自動部署至使用者。</span><span class="sxs-lookup"><span data-stu-id="28347-135">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="28347-136">在下一頁中，選取所有人、特定使用者 **/** 群組，或只選取我來指定要將載入元件部署到哪些人員。</span><span class="sxs-lookup"><span data-stu-id="28347-136">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="28347-137">使用搜尋方塊尋找特定使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="28347-137">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="28347-138">若要瞭解適用于附加元件的其他狀態，請參閱 [In-in 狀態](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="28347-138">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="28347-139">選取 **部署**。</span><span class="sxs-lookup"><span data-stu-id="28347-139">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="28347-140">部署該附加元件時，會出現綠色刻度。</span><span class="sxs-lookup"><span data-stu-id="28347-140">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="28347-141">請遵循頁面上的指示測試載入元件。</span><span class="sxs-lookup"><span data-stu-id="28347-141">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28347-142">使用者可能需要重新開機 Office，以在 App 功能區上查看此附加元件圖示。</span><span class="sxs-lookup"><span data-stu-id="28347-142">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="28347-143">Outlook 外掛程式最多可能需要 24 小時才能顯示在 App 功能區上。</span><span class="sxs-lookup"><span data-stu-id="28347-143">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="28347-144">完成後，選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="28347-144">When finished, select **Next**.</span></span> <span data-ttu-id="28347-145">如果您只為自己部署，您可以選取變更誰具有 **該附加** 元件的存取權限，以部署到更多使用者。</span><span class="sxs-lookup"><span data-stu-id="28347-145">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="28347-146">如果您已經將該附加元件部署到組織的其他成員，請按照指示宣告該附加元件部署。</span><span class="sxs-lookup"><span data-stu-id="28347-146">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="28347-147">建議告知使用者和群組已部署之附加元件可供使用。</span><span class="sxs-lookup"><span data-stu-id="28347-147">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="28347-148">請考慮傳送一封電子郵件，說明何時及如何使用該附加元件。</span><span class="sxs-lookup"><span data-stu-id="28347-148">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="28347-149">包含或連結至協助使用者解決此附加元件問題的內容或常見問題。</span><span class="sxs-lookup"><span data-stu-id="28347-149">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="28347-150">將增益集指派給使用者和群組時的考慮事項</span><span class="sxs-lookup"><span data-stu-id="28347-150">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="28347-151">系統管理員可以將增益集指派給所有人或特定的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="28347-151">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="28347-152">每個選項都有其意涵：</span><span class="sxs-lookup"><span data-stu-id="28347-152">Each option has implications:</span></span>
  
- <span data-ttu-id="28347-153">**所有人** 此選項會指派此外掛程式給組織每個使用者。</span><span class="sxs-lookup"><span data-stu-id="28347-153">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="28347-154">請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。</span><span class="sxs-lookup"><span data-stu-id="28347-154">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="28347-155">**使用者** 如果您將一個附加元件指派給個別使用者，然後將該附加元件部署到新的使用者，您必須先新增使用者。</span><span class="sxs-lookup"><span data-stu-id="28347-155">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="28347-156">**群組** 如果您將一個附加元件指派給群組，則新加入群組的使用者會自動被指派該附加元件。</span><span class="sxs-lookup"><span data-stu-id="28347-156">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="28347-157">當使用者從群組移除時，該使用者會失去該附加元件的存取權限。</span><span class="sxs-lookup"><span data-stu-id="28347-157">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="28347-158">任一種情況下，管理員都不需要執行額外的動作。</span><span class="sxs-lookup"><span data-stu-id="28347-158">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="28347-159">**僅自己** 如果您只將一個附加元件指派給自己，則只會將這個附加元件指派給您的帳戶，這是測試該附加元件的理想方法。</span><span class="sxs-lookup"><span data-stu-id="28347-159">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="28347-160">適用于貴組織的正確選項取決於您的組選。</span><span class="sxs-lookup"><span data-stu-id="28347-160">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="28347-161">不過，我們建議您使用群組進行指派。</span><span class="sxs-lookup"><span data-stu-id="28347-161">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="28347-162">系統管理員可能會發現，使用群組及控制這些群組的成員資格，而非每次指派個別使用者，以輕鬆管理附加元件。</span><span class="sxs-lookup"><span data-stu-id="28347-162">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="28347-163">在某些情況下，您可能會想要手動指派使用者給特定使用者，以限制一小組使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="28347-163">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="28347-164">Office 附加元件安全性的更多資訊</span><span class="sxs-lookup"><span data-stu-id="28347-164">More about Office add-ins security</span></span>

<span data-ttu-id="28347-p118">Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：</span><span class="sxs-lookup"><span data-stu-id="28347-p118">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="28347-168">顯示資料。</span><span class="sxs-lookup"><span data-stu-id="28347-168">Display data.</span></span>
    
- <span data-ttu-id="28347-169">閱讀使用者的文件以提供內容相關服務。</span><span class="sxs-lookup"><span data-stu-id="28347-169">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="28347-170">從使用者的文件讀取及寫入資料，以提供值給該使用者。</span><span class="sxs-lookup"><span data-stu-id="28347-170">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="28347-171">如需 Office 增益集類型和功能的詳細資訊，請參閱 [Office 增益集平台概觀](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) (尤其是「分析 Office 增益集」一節)。</span><span class="sxs-lookup"><span data-stu-id="28347-171">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="28347-p119">若要與使用者的文件互動，增益集必須在資訊清單中宣告需要的權限。五個層級的 JavaScript API 存取權限模型可為工作窗格增益集使用者提供基本的隱私權和安全性。Office 市集中的大多數增益集為 ReadWriteDocument 層級，且包含至少 ReadDocument 層級的大部分增益集支援功能。如需權限層級的詳細資訊，請參閱[要求取得用於內容和工作窗格增益集之 API 的權限](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) (英文)。</span><span class="sxs-lookup"><span data-stu-id="28347-p119">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="28347-p120">更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。</span><span class="sxs-lookup"><span data-stu-id="28347-p120">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="28347-179">增益集的更新會以下列方式進行：</span><span class="sxs-lookup"><span data-stu-id="28347-179">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="28347-180">**企業經營型附加元件：** 在此案例中，當系統管理員明確上傳的顯示清單時，需要系統管理員上傳新的清單檔案以支援中繼資料變更。</span><span class="sxs-lookup"><span data-stu-id="28347-180">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="28347-181">在下次啟動相關的 Office 應用程式時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="28347-181">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="28347-182">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="28347-182">The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="28347-183">系統管理員不需要移除 LOB 外掛程式，也不需要執行更新。</span><span class="sxs-lookup"><span data-stu-id="28347-183">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="28347-184">在 [附加元件> 區段，系統管理員只要按一下 LOB Add-in，然後選擇右下角的更新按鈕即可。</span><span class="sxs-lookup"><span data-stu-id="28347-184">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="28347-185">只有當新附加元件的版本大於現有附加元件版本時，更新才能作用。</span><span class="sxs-lookup"><span data-stu-id="28347-185">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="28347-186">**Office 市商店的附加元件：** 當系統管理員從 Office 市集選取一個附加元件時，如果 Office 市集中有附加元件更新，該附加元件稍後將會于集中式部署中更新。</span><span class="sxs-lookup"><span data-stu-id="28347-186">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span></span> <span data-ttu-id="28347-187">在下次啟動相關的 Office 應用程式時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="28347-187">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="28347-188">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="28347-188">The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="28347-189">深入了解</span><span class="sxs-lookup"><span data-stu-id="28347-189">Learn more</span></span>

[<span data-ttu-id="28347-190">在系統管理中心管理增益集</span><span class="sxs-lookup"><span data-stu-id="28347-190">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="28347-191">[建立您的第一個 Word 工作窗格附加元件](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)。</span><span class="sxs-lookup"><span data-stu-id="28347-191">[Build your first Word task pane add-in](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="28347-192">從商店取得次要和取得外掛程式</span><span class="sxs-lookup"><span data-stu-id="28347-192">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="28347-193">使用集中式部署 PowerShell Cmdlet 來管理外掛程式</span><span class="sxs-lookup"><span data-stu-id="28347-193">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="28347-194">疑難排解：使用者看不到外掛程式</span><span class="sxs-lookup"><span data-stu-id="28347-194">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
