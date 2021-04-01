---
title: 在系統管理中心部署增益集
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 瞭解如何使用系統管理中心的集中式部署，將增益集部署至組織中的使用者和群組。
ms.openlocfilehash: 996ef34f1fc8d9663f6fa59f13a56a169b7edd11
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470520"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="9199b-103">在系統管理中心部署增益集</span><span class="sxs-lookup"><span data-stu-id="9199b-103">Deploy add-ins in the admin center</span></span>

<span data-ttu-id="9199b-104">Office 增益集可以協助您將文件個人化，也可以簡化您存取網路資訊的方式 (請參閱[開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="9199b-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="9199b-105">身為系統管理員，您可以使用 Microsoft 365 系統管理中心的 [集中式部署] 功能，為組織中的使用者部署 Office 增益集。</span><span class="sxs-lookup"><span data-stu-id="9199b-105">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9199b-106">若要將增益集部署至組織內的使用者和群組，[集中式部署] 是建議和功能最豐富的方法。</span><span class="sxs-lookup"><span data-stu-id="9199b-106">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span>

<span data-ttu-id="9199b-107">如需如何判斷您的組織是否可支援集中式部署的詳細資訊，請參閱判斷您的組織是否可使用 [集中式部署增益集](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="9199b-107">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="9199b-108">若要深入瞭解如何在部署後管理增益集，請參閱 [在系統管理中心管理增益集](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="9199b-108">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9199b-109">Word、Excel 及 PowerPoint 會使用 [SharePoint 應用程式目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) ，將增益集部署至內部部署環境中的使用者，但不連接至 Microsoft 365 和/或支援所需 SharePoint 增益集。</span><span class="sxs-lookup"><span data-stu-id="9199b-109">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="9199b-110">Outlook 使用 Exchange 控制台在內部部署環境中部署，但不連接至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="9199b-110">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="9199b-111">部署 Office 增益集的建議方式</span><span class="sxs-lookup"><span data-stu-id="9199b-111">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="9199b-112">若要使用逐步式方法來推出增益集，建議您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="9199b-112">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="9199b-113">將增益集推出給一小部分的商務專案關係人和 IT 部門的成員。</span><span class="sxs-lookup"><span data-stu-id="9199b-113">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="9199b-114">如果部署成功，請移至步驟2。</span><span class="sxs-lookup"><span data-stu-id="9199b-114">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="9199b-115">向商務中的更多人員推出增益集。</span><span class="sxs-lookup"><span data-stu-id="9199b-115">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="9199b-116">請再次評估結果，如果成功，則繼續進行完整部署。</span><span class="sxs-lookup"><span data-stu-id="9199b-116">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="9199b-117">對所有使用者執行完整的展示。</span><span class="sxs-lookup"><span data-stu-id="9199b-117">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="9199b-118">視目標物件的大小而定，您可以新增或移除向外展開步驟。</span><span class="sxs-lookup"><span data-stu-id="9199b-118">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="9199b-119">使用系統管理中心部署 Office 增益集</span><span class="sxs-lookup"><span data-stu-id="9199b-119">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="9199b-120">開始之前，請參閱 [判斷集中式部署的增益集是否適用于您的組織](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="9199b-120">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="9199b-121">在系統管理中心中，移至 [ **設定** \> **增益集** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9199b-121">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="9199b-122">如果您看不到 [ **增益集** ] 頁面，請移至 [ **設定** \> **整合型應用程式** \> **增益集** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9199b-122">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>

2. <span data-ttu-id="9199b-123">選取頁面頂端的 [ **部署增益集** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9199b-123">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9199b-124">系統管理中心已更新整合型應用程式的部署經驗。</span><span class="sxs-lookup"><span data-stu-id="9199b-124">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="9199b-125">整合式應用程式只有全域系統管理員才能看見，但其他使用者仍存在舊經驗。</span><span class="sxs-lookup"><span data-stu-id="9199b-125">Integrated Apps is only visible to Global administrators, while for others the old experience still exists.</span></span> <span data-ttu-id="9199b-126">如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 [**設定**  >  **整合型應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="9199b-126">If you don't see the above steps, go to the Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="9199b-127">在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集**]。</span><span class="sxs-lookup"><span data-stu-id="9199b-127">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

3. <span data-ttu-id="9199b-128">選取 [選項]，然後依照指示執行。</span><span class="sxs-lookup"><span data-stu-id="9199b-128">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="9199b-129">如果您選取 [從 Office Store 新增增益集] 選項，請讓增益集成為選取範圍。</span><span class="sxs-lookup"><span data-stu-id="9199b-129">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="9199b-130">您可以依類別來查看可用的增益集： **建議您**、 **評級** 或 **名稱**。</span><span class="sxs-lookup"><span data-stu-id="9199b-130">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="9199b-131">Office Store 只有免費的增益集可供使用。</span><span class="sxs-lookup"><span data-stu-id="9199b-131">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="9199b-132">目前尚不支援付費增益集。</span><span class="sxs-lookup"><span data-stu-id="9199b-132">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="9199b-133">選取增益集之後，請接受條款及條件以繼續。</span><span class="sxs-lookup"><span data-stu-id="9199b-133">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE]
    > <span data-ttu-id="9199b-134">透過 Office Store 選項，更新及增強功能會自動部署至使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-134">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="9199b-135">在下一個頁面上，選取 [ **所有人**]、[ **特定使用者/群組**] 或 [ **僅限我** ]，以指定要部署增益集的人員。</span><span class="sxs-lookup"><span data-stu-id="9199b-135">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="9199b-136">使用 [搜尋] 方塊尋找特定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="9199b-136">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE]
    > <span data-ttu-id="9199b-137">若要瞭解適用于增益集的其他狀態，請參閱 [增益集狀態](./manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="9199b-137">To learn about other states that apply to an add-in, see [Add-in states](./manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="9199b-138">選取 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="9199b-138">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="9199b-139">部署增益集時，會出現綠色的勾選標記。</span><span class="sxs-lookup"><span data-stu-id="9199b-139">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="9199b-140">依照頁面上的指示測試增益集。</span><span class="sxs-lookup"><span data-stu-id="9199b-140">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9199b-141">使用者可能需要重新開機 Office 來查看應用程式功能區上的增益集圖示。</span><span class="sxs-lookup"><span data-stu-id="9199b-141">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="9199b-142">Outlook 增益集最多可能需要24小時才能出現在應用程式功能區上。</span><span class="sxs-lookup"><span data-stu-id="9199b-142">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>

8. <span data-ttu-id="9199b-143">完成時，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9199b-143">When finished, select **Next**.</span></span> <span data-ttu-id="9199b-144">如果您只是自行部署，您可以選取 [ **變更可存取增益集的人員** ]，以部署至其他使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-144">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="9199b-145">如果您已將增益集部署至組織的其他成員，請依照指示宣告增益集的部署。</span><span class="sxs-lookup"><span data-stu-id="9199b-145">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="9199b-146">建議使用已部署增益集的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="9199b-146">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="9199b-147">請考慮傳送描述何時及如何使用增益集的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9199b-147">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="9199b-148">包含或連結，以協助內容或 FAQs 如果增益集發生問題，可能會協助使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-148">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="9199b-149">將增益集指派給使用者和群組時的考慮事項</span><span class="sxs-lookup"><span data-stu-id="9199b-149">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="9199b-150">全域管理員和 Exchange 系統管理員可以將增益集指派給每個人或特定使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="9199b-150">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="9199b-151">每個選項都有其意涵：</span><span class="sxs-lookup"><span data-stu-id="9199b-151">Each option has implications:</span></span>
  
- <span data-ttu-id="9199b-152">**所有人** 此選項會將增益集指派給組織中的每一位使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-152">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="9199b-153">請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。</span><span class="sxs-lookup"><span data-stu-id="9199b-153">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span>

- <span data-ttu-id="9199b-154">**使用者** 如果您將增益集指派給個別使用者，然後將增益集部署至新的使用者，您必須先新增新的使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-154">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>

- <span data-ttu-id="9199b-155">**群組** 如果您將增益集指派給群組，則新增至群組的使用者會自動指派增益集。</span><span class="sxs-lookup"><span data-stu-id="9199b-155">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="9199b-156">當使用者從群組中移除時，使用者將無法存取增益集。</span><span class="sxs-lookup"><span data-stu-id="9199b-156">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="9199b-157">在這兩種情況下，系統管理員不需要其他的動作。</span><span class="sxs-lookup"><span data-stu-id="9199b-157">In either case, no additional action is required from the admin.</span></span>

- <span data-ttu-id="9199b-158">**僅自己** 如果您將增益集指派給您自己，增益集就會指派給您的帳戶，這是測試增益集的理想選擇。</span><span class="sxs-lookup"><span data-stu-id="9199b-158">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>

<span data-ttu-id="9199b-159">組織的右選項視您的設定而定。</span><span class="sxs-lookup"><span data-stu-id="9199b-159">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="9199b-160">不過，我們建議您使用群組來進行工作分派。</span><span class="sxs-lookup"><span data-stu-id="9199b-160">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="9199b-161">身為系統管理員，您可能會發現使用群組來管理增益集及控制這些群組的成員資格，而不是每次指派個別使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-161">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="9199b-162">在某些情況下，您可能會想要限制一小部分使用者的存取，只要手動指派使用者給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-162">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="9199b-163">更多關於 Office 增益集的安全性</span><span class="sxs-lookup"><span data-stu-id="9199b-163">More about Office add-ins security</span></span>

<span data-ttu-id="9199b-p117">Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：</span><span class="sxs-lookup"><span data-stu-id="9199b-p117">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="9199b-167">顯示資料。</span><span class="sxs-lookup"><span data-stu-id="9199b-167">Display data.</span></span>

- <span data-ttu-id="9199b-168">閱讀使用者的文件以提供內容相關服務。</span><span class="sxs-lookup"><span data-stu-id="9199b-168">Read a user's document to provide contextual services.</span></span>

- <span data-ttu-id="9199b-169">從使用者的文件讀取及寫入資料，以提供值給該使用者。</span><span class="sxs-lookup"><span data-stu-id="9199b-169">Read and write data to and from a user's document to provide value to that user.</span></span>

<span data-ttu-id="9199b-170">如需 Office 增益集類型和功能的詳細資訊，請參閱 [Office 增益集平台概觀](/office/dev/add-ins/overview/office-add-ins) (尤其是「分析 Office 增益集」一節)。</span><span class="sxs-lookup"><span data-stu-id="9199b-170">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="9199b-p118">若要與使用者的文件互動，增益集必須在資訊清單中宣告需要的權限。五個層級的 JavaScript API 存取權限模型可為工作窗格增益集使用者提供基本的隱私權和安全性。Office 市集中的大多數增益集為 ReadWriteDocument 層級，且包含至少 ReadDocument 層級的大部分增益集支援功能。如需權限層級的詳細資訊，請參閱[要求取得用於內容和工作窗格增益集之 API 的權限](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9199b-p118">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="9199b-p119">更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。</span><span class="sxs-lookup"><span data-stu-id="9199b-p119">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="9199b-178">增益集的更新會以下列方式進行：</span><span class="sxs-lookup"><span data-stu-id="9199b-178">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="9199b-179">**企業營運增益集：** 在此情況下，管理員明確上傳資訊清單的地方，增益集需要系統管理員上載新的資訊清單檔案，以支援中繼資料變更。</span><span class="sxs-lookup"><span data-stu-id="9199b-179">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="9199b-180">在下次啟動相關的 Office 應用程式時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="9199b-180">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="9199b-181">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="9199b-181">The web application can change at any time.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9199b-182">管理員不需要移除 LOB 增益集進行更新。</span><span class="sxs-lookup"><span data-stu-id="9199b-182">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="9199b-183">在 [增益集] 區段中，系統管理員只要按一下 LOB 增益集，然後選擇右下角的 [ **更新] 按鈕** 即可。</span><span class="sxs-lookup"><span data-stu-id="9199b-183">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="9199b-184">只有當新增益集的版本高於現有增益集的版本時，更新才會運作。</span><span class="sxs-lookup"><span data-stu-id="9199b-184">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>

- <span data-ttu-id="9199b-185">**Office Store 增益集：** 當系統管理員從 Office Store 中選取增益集時，如果 Office Store 中的增益集更新，增益集將在稍後的集中式部署中更新。</span><span class="sxs-lookup"><span data-stu-id="9199b-185">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span></span> <span data-ttu-id="9199b-186">在下次啟動相關的 Office 應用程式時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="9199b-186">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="9199b-187">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="9199b-187">The web application can change at any time.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="9199b-188">深入了解</span><span class="sxs-lookup"><span data-stu-id="9199b-188">Learn more</span></span>

[<span data-ttu-id="9199b-189">在系統管理中心管理增益集</span><span class="sxs-lookup"><span data-stu-id="9199b-189">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="9199b-190">[建立第一個 Word 工作窗格增益集](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)。</span><span class="sxs-lookup"><span data-stu-id="9199b-190">[Build your first Word task pane add-in](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="9199b-191">對存放區中的增益集進行未成年人和取得</span><span class="sxs-lookup"><span data-stu-id="9199b-191">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="9199b-192">使用集中式部署 PowerShell Cmdlet 來管理增益集</span><span class="sxs-lookup"><span data-stu-id="9199b-192">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)
  
[<span data-ttu-id="9199b-193">疑難排解：使用者未看到增益集</span><span class="sxs-lookup"><span data-stu-id="9199b-193">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)