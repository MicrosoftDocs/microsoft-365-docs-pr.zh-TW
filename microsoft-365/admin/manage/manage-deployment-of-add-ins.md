---
title: 管理系統管理中心內增益集的部署
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用系統管理中心的集中式部署，將增益集部署至組織中的使用者和群組。
ms.openlocfilehash: cb41d02d8075e94c788a9964e0a3ac69d8363ef4
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139706"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a><span data-ttu-id="47509-103">在 Microsoft 365 系統管理中心中管理增益集的部署</span><span class="sxs-lookup"><span data-stu-id="47509-103">Manage deployment of add-ins in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="47509-104">系統管理中心變更。</span><span class="sxs-lookup"><span data-stu-id="47509-104">The admin center is changing.</span></span> <span data-ttu-id="47509-105">[！附注] 如果您的經驗不符合這裡所述的詳細資料，請參閱[關於新的 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="47509-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="47509-106">Office 增益集可以協助您將文件個人化，也可以簡化您存取網路資訊的方式 (請參閱[開始使用 Office 增益集](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx))。</span><span class="sxs-lookup"><span data-stu-id="47509-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)).</span></span> <span data-ttu-id="47509-107">作為系統管理員，您可以為組織中的使用者部署 Office 增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-107">As an admin, you can deploy Office add-ins for the users in your organization.</span></span> <span data-ttu-id="47509-108">您可以使用 Microsoft 365 系統管理中心的 [集中式部署] 功能來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="47509-108">You can do this using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="47509-109">若要將增益集部署至組織內的使用者和群組，[集中式部署] 是建議和功能最豐富的方法。</span><span class="sxs-lookup"><span data-stu-id="47509-109">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> <span data-ttu-id="47509-110">如需如何判斷您的組織是否可支援集中式部署的詳細資訊，請參閱判斷您的組織是否可使用[集中式部署增益集](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="47509-110">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
<span data-ttu-id="47509-111">[集中式部署] 提供下列優點：</span><span class="sxs-lookup"><span data-stu-id="47509-111">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="47509-112">全域管理員可以將增益集直接指派給使用者、透過群組將增益集指派給多位使用者，或租使用者指派給每個人。</span><span class="sxs-lookup"><span data-stu-id="47509-112">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the tenant.</span></span>
    
- <span data-ttu-id="47509-p104">當相關 Office 應用程式啟動時，系統會自動為使用者下載增益集。如果增益集支援增益集命令，增益集會自動顯示在 Office 應用程式的 [功能區] 中。</span><span class="sxs-lookup"><span data-stu-id="47509-p104">When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.</span></span>
    
- <span data-ttu-id="47509-115">如果系統管理員關閉或刪除增益集，或從 Azure Active Directory 或指派給的群組中移除該使用者，就不再顯示使用者的增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-115">Add-ins will no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="47509-116">Word、Excel 及 PowerPoint 會使用[SharePoint 應用程式目錄](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)，將增益集部署至內部部署環境中的使用者，但不連接至 Microsoft 365 和/或支援所需 SharePoint 增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-116">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="47509-117">> Outlook 使用 Exchange 控制台，在內部部署環境中部署，但不連接至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="47509-117">>  For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span> > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="47509-118">部署 Office 增益集的建議方式</span><span class="sxs-lookup"><span data-stu-id="47509-118">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="47509-p106">請考慮採用分階段的方式來推出增益集，這樣有助於確保增益集部署順利進行。我們的建議方案如下：</span><span class="sxs-lookup"><span data-stu-id="47509-p106">Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:</span></span>
  
1. <span data-ttu-id="47509-p107">為一小組商務專案關係人以及 IT 部門的成員推行增益集。評估部署是否成功，如果成功，則請繼續進行步驟 2。</span><span class="sxs-lookup"><span data-stu-id="47509-p107">Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.</span></span>
    
2. <span data-ttu-id="47509-p108">為企業中將需使用增益集的一大組人員推行。同樣地，請評估成果，如果一切順利，則請繼續進行完整部署的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="47509-p108">Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.</span></span>
    
3. <span data-ttu-id="47509-125">為目標對象使用者完全推行。</span><span class="sxs-lookup"><span data-stu-id="47509-125">Full rollout to target audience of users.</span></span>
    
<span data-ttu-id="47509-126">視目標對象的大小規模而定，您可能會想要新增或移除推行步驟。</span><span class="sxs-lookup"><span data-stu-id="47509-126">Depending on the size of the target audience, you may want to add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="47509-127">使用系統管理中心部署 Office 增益集</span><span class="sxs-lookup"><span data-stu-id="47509-127">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="47509-128">開始之前，請參閱[判斷集中式部署的增益集是否適用于您的組織](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="47509-128">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

  
1. <span data-ttu-id="47509-129">在系統管理中心中，移至 [**設定** \> **增益集**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="47509-129">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="47509-130">在頁面頂端，選取 [**部署增益集**]。</span><span class="sxs-lookup"><span data-stu-id="47509-130">Select **Deploy Add-in** at the top of the page.</span></span> <span data-ttu-id="47509-131">在 [概覽] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="47509-131">On the overview page, select **Next**.</span></span>
    
3. <span data-ttu-id="47509-132">選取 [選項]，然後依照指示執行。</span><span class="sxs-lookup"><span data-stu-id="47509-132">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="47509-133">如果您選取 [從 Office 書店新增增益集] 選項，您現在可以將增益集選取範圍。</span><span class="sxs-lookup"><span data-stu-id="47509-133">If you selected the option to add an add-in from the Office Store, you can now make your add-in selection.</span></span> <span data-ttu-id="47509-134">請注意，您可以透過**為您建議的**類別、**評級**或**名稱**來查看可用的增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-134">Notice that you can view available add-ins via categories of **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="47509-135">您只能從 Office 市集新增免費的增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-135">Only free add-ins are available to add from the Office Store.</span></span> <span data-ttu-id="47509-136">目前尚不支援付費增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-136">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="47509-137">在您選取增益集之後，您必須同意一些額外的條款及條件，才能繼續進行。</span><span class="sxs-lookup"><span data-stu-id="47509-137">Once you've selected your add-in, you will need to agree to some additional terms and conditions in order to proceed.</span></span> <br/><br/> <span data-ttu-id="47509-138">附注：使用 Office Store 選項時，系統會自動將增益集的更新及增強功能提供給使用者，而不需要您介入。</span><span class="sxs-lookup"><span data-stu-id="47509-138">NOTE: With the Office Store option, updates and enhancements to the add-in will automatically be made available to users without your intervention.</span></span>

5. <span data-ttu-id="47509-139">在下一個頁面上，選取 [**所有人**]、[**特定使用者/群組**] 或 [**僅限我**]，以指定要部署增益集的人員。</span><span class="sxs-lookup"><span data-stu-id="47509-139">On the next page, select **Everyone**, **Specific users/groups** or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="47509-140">使用 [搜尋] 方塊，尋找您要將增益集部署到哪個使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="47509-140">Use the Search box to find the users or groups who you want to deploy the add-in to.</span></span> <br/><span data-ttu-id="47509-141">附注：瞭解適用于增益集的其他狀態。</span><span class="sxs-lookup"><span data-stu-id="47509-141">NOTE: Learn about the other states that apply to an add-in.</span></span> <span data-ttu-id="47509-142">請參閱本主題稍後介紹的[增益集狀態](#add-in-states)。</span><span class="sxs-lookup"><span data-stu-id="47509-142">See [Add-in states](#add-in-states) later in this topic.</span></span>
  
6. <span data-ttu-id="47509-143">選取 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="47509-143">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="47509-144">部署增益集時，會出現綠色的勾選標記。</span><span class="sxs-lookup"><span data-stu-id="47509-144">A green tick will appear when the add-in has been deployed.</span></span> <span data-ttu-id="47509-145">您可以依照頁面上的指示測試增益集是否已成功部署。</span><span class="sxs-lookup"><span data-stu-id="47509-145">You can follow the on-page instructions to test that the add-in has deployed successfully.</span></span>

> [!NOTE]
> <span data-ttu-id="47509-146">使用者可能需要重新開機 Office，才能看到增益集圖示出現在應用程式的功能區上。</span><span class="sxs-lookup"><span data-stu-id="47509-146">Users may need to relaunch Office to see the add-in icon appear on the ribbon of app.</span></span> <span data-ttu-id="47509-147">在使用者的功能區上顯示 Outlook 增益集時，最多可能需要12小時。</span><span class="sxs-lookup"><span data-stu-id="47509-147">Outlook add-ins can take up to 12 hours to appear on users' ribbons.</span></span>
    
8. <span data-ttu-id="47509-148">完成時，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="47509-148">When finished, select **Next**.</span></span> <span data-ttu-id="47509-149">如果您只是自行部署，您可以選取 [**變更擁有增益集的存取**權]，以部署至其他使用者。</span><span class="sxs-lookup"><span data-stu-id="47509-149">If you've deployed to just yourself, you can select **Change who has access to add-in** in order to deploy to more users.</span></span>



<span data-ttu-id="47509-150">如果您已將增益集部署至組織的成員以外的成員，請遵循顯示的指示，以有效宣告增益集的部署。</span><span class="sxs-lookup"><span data-stu-id="47509-150">If you've deployed the add-in to members of your organization other than yourself, follow the instructions displayed in order to effectively announce the deployment of the add-in.</span></span> <br/><span data-ttu-id="47509-151">現在，您可以在 Microsoft 365 中看到增益集和其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="47509-151">You now see your add-in along with other apps in Microsoft 365.</span></span>
  
<span data-ttu-id="47509-152">將增益集部署到使用者和群組後，建議您告知他們，這樣他們才會知道已經可以使用增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-152">It's a good idea to inform the users and groups who you deployed the add-in to so that they know that it's available.</span></span> <span data-ttu-id="47509-153">請考慮傳送電子郵件給他們，說明使用增益集的時機與方法，並解說增益集對於提升工作效率有何幫助。</span><span class="sxs-lookup"><span data-stu-id="47509-153">Consider sending an email to them that describes when and how to use the add-in and explains how the add-in can help them do their job better.</span></span> <span data-ttu-id="47509-154">包含或連結至相關的說明內容或 FAQs，可協助使用者是否有任何問題增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-154">Include or link to relevant Help content or FAQs that might help if users have any problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="47509-155">將增益集指派給使用者和群組時的考慮事項</span><span class="sxs-lookup"><span data-stu-id="47509-155">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="47509-156">系統管理員可以將增益集指派給所有人或特定的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="47509-156">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="47509-157">每個選項都有其意涵：</span><span class="sxs-lookup"><span data-stu-id="47509-157">Each option has implications:</span></span>
  
- <span data-ttu-id="47509-158">**所有人**：顧名思義，此選項會將增益集指派給租使用者中的每位使用者。</span><span class="sxs-lookup"><span data-stu-id="47509-158">**Everyone**: As the name implies, this option assigns the add-in to every user in the tenant.</span></span> <span data-ttu-id="47509-159">請謹慎使用此選項，並且只有在貴組織需要普遍使用此增益集時才使用此選項。</span><span class="sxs-lookup"><span data-stu-id="47509-159">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="47509-160">**使用者**：如果您將增益集指派給個別使用者，然後若要將增益集部署至新的使用者，您必須先新增該使用者。</span><span class="sxs-lookup"><span data-stu-id="47509-160">**Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user.</span></span> <span data-ttu-id="47509-161">移除使用者時也是如此。</span><span class="sxs-lookup"><span data-stu-id="47509-161">The same goes for removing users.</span></span> 
    
- <span data-ttu-id="47509-162">**群組**：如果您將增益集指派給群組，則新增至群組的使用者會自動被指派增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-162">**Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in.</span></span> <span data-ttu-id="47509-163">此外，移除群組中的使用者後，該使用者就會失去增益集的存取權。</span><span class="sxs-lookup"><span data-stu-id="47509-163">And, when a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="47509-164">在任何一種情況下，身為系統管理員的您都不需要執行額外的動作。</span><span class="sxs-lookup"><span data-stu-id="47509-164">In either case, no additional action is required from you as the admin.</span></span> 

- <span data-ttu-id="47509-165">**僅限我**：如果您將增益集指派給您自己，就會將增益集指派給您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="47509-165">**Just me**: If you assign an add-in to just yourself, this assigns the add-in to only your account.</span></span> <span data-ttu-id="47509-166">如果您想要先測試增益集，這是理想的選擇。</span><span class="sxs-lookup"><span data-stu-id="47509-166">This is ideal if you wish to test out the add-in first.</span></span>
    
<span data-ttu-id="47509-167">您的組織適合的選項取決於您的設定。</span><span class="sxs-lookup"><span data-stu-id="47509-167">The option that is right for your organization depends on your configuration.</span></span> <span data-ttu-id="47509-168">不過，建議透過群組執行指派。</span><span class="sxs-lookup"><span data-stu-id="47509-168">However, we recommend making assignments via groups.</span></span> <span data-ttu-id="47509-169">身為系統管理員，比起每次必須變更指派的使用者，使用群組來管理增益集及控制這些群組的成員資格可能會比較輕鬆。</span><span class="sxs-lookup"><span data-stu-id="47509-169">As an admin, you might find it easier to manage add-ins using groups and control the membership of those groups rather than having to change the users assigned each time.</span></span> <span data-ttu-id="47509-170">另一方面，在某些情況下，您可能會想要將存取權限制於一小組使用者以內，因而指派特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="47509-170">On the other hand, in some situations, you may want to restrict access to a very small set of users and therefore make assignments to specific users.</span></span> <span data-ttu-id="47509-171">因此，您必須以手動方式管理被指派的使用者。</span><span class="sxs-lookup"><span data-stu-id="47509-171">As a result, you will need to manage the assigned users manually.</span></span>
  
### <a name="add-in-states"></a><span data-ttu-id="47509-172">增益集狀態</span><span class="sxs-lookup"><span data-stu-id="47509-172">Add-in states</span></span>

<span data-ttu-id="47509-173">增益集可以處於 [**開啟**] 或 [**關閉**] 狀態。</span><span class="sxs-lookup"><span data-stu-id="47509-173">An add-in can either be in the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="47509-174">**State**</span><span class="sxs-lookup"><span data-stu-id="47509-174">**State**</span></span>|<span data-ttu-id="47509-175">**狀態如何發生**</span><span class="sxs-lookup"><span data-stu-id="47509-175">**How the state occurs**</span></span>|<span data-ttu-id="47509-176">**影響**</span><span class="sxs-lookup"><span data-stu-id="47509-176">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="47509-177">**Active**</span><span class="sxs-lookup"><span data-stu-id="47509-177">**Active**</span></span>  <br/> |<span data-ttu-id="47509-178">系統管理員上載增益集，並將其指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="47509-178">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="47509-179">被指派增益集的使用者和群組會在相關用戶端中看見增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-179">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="47509-180">**已關閉**</span><span class="sxs-lookup"><span data-stu-id="47509-180">**Turned off**</span></span>  <br/> |<span data-ttu-id="47509-181">系統管理員已關閉增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-181">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="47509-182">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-182">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="47509-183">如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-183">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="47509-184">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="47509-184">**Deleted**</span></span>  <br/> |<span data-ttu-id="47509-185">系統管理員已刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-185">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="47509-186">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-186">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="47509-187">如果沒有人再使用增益集，請考慮刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-187">Consider deleting an add-in if no one is using it any more.</span></span> <span data-ttu-id="47509-188">如果只有在一年的某些特殊時段需要使用增益集，關閉增益集可能會是比較合理的做法。</span><span class="sxs-lookup"><span data-stu-id="47509-188">Turning off an add-in may make sense if an add-in is used only during specific times of the year.</span></span>
  
### <a name="security-of-office-add-ins"></a><span data-ttu-id="47509-189">Office 增益集的安全性</span><span class="sxs-lookup"><span data-stu-id="47509-189">Security of Office add-ins</span></span>

<span data-ttu-id="47509-p124">Office 增益集會與內含部分增益集中繼資料的 XML 資訊清單檔案合併，但最重要的是，Office 增益集會與指向包含所有程式碼和邏輯的 Web 應用程式合併。增益集可以有各種不同的功能。例如，增益集可以：</span><span class="sxs-lookup"><span data-stu-id="47509-p124">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="47509-193">顯示資料。</span><span class="sxs-lookup"><span data-stu-id="47509-193">Display data.</span></span>
    
- <span data-ttu-id="47509-194">閱讀使用者的文件以提供內容相關服務。</span><span class="sxs-lookup"><span data-stu-id="47509-194">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="47509-195">從使用者的文件讀取及寫入資料，以提供值給該使用者。</span><span class="sxs-lookup"><span data-stu-id="47509-195">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="47509-196">如需 Office 增益集類型和功能的詳細資訊，請參閱 [Office 增益集平台概觀](https://go.microsoft.com/fwlink/p/?linkid=846362) (尤其是「分析 Office 增益集」一節)。</span><span class="sxs-lookup"><span data-stu-id="47509-196">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="47509-p125">若要與使用者的文件互動，增益集必須在資訊清單中宣告需要的權限。五個層級的 JavaScript API 存取權限模型可為工作窗格增益集使用者提供基本的隱私權和安全性。Office 市集中的大多數增益集為 ReadWriteDocument 層級，且包含至少 ReadDocument 層級的大部分增益集支援功能。如需權限層級的詳細資訊，請參閱[要求取得用於內容和工作窗格增益集之 API 的權限](https://go.microsoft.com/fwlink/p/?linkid=848863) (英文)。</span><span class="sxs-lookup"><span data-stu-id="47509-p125">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).</span></span>
  
<span data-ttu-id="47509-p126">更新資訊清單時，通常是變更增益集的圖示和文字。有時則會變更增益集的命令。不過，增益集的權限不會遭到變更。執行增益集的所有程式碼和邏輯的 Web 應用程式可能隨時變更，這是 Web 應用程式的本質所致。</span><span class="sxs-lookup"><span data-stu-id="47509-p126">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="47509-204">增益集的更新會以下列方式進行：</span><span class="sxs-lookup"><span data-stu-id="47509-204">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="47509-205">**企業營運增益集：** 在此情況下，管理員明確上傳資訊清單的地方，增益集需要系統管理員上載新的資訊清單檔案，以支援中繼資料變更。</span><span class="sxs-lookup"><span data-stu-id="47509-205">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="47509-206">在下次啟動相關的 Office 應用程式時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="47509-206">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="47509-207">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="47509-207">The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="47509-208">管理員不需要移除 LOB 增益集進行更新。</span><span class="sxs-lookup"><span data-stu-id="47509-208">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="47509-209">在 [增益集] 區段中，系統管理員只要按一下 LOB 增益集，然後選擇右下角的 [**更新] 按鈕**即可。</span><span class="sxs-lookup"><span data-stu-id="47509-209">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="47509-210">只有當新增益集的版本高於現有增益集的版本時，更新才會運作。</span><span class="sxs-lookup"><span data-stu-id="47509-210">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="47509-211">**Office Store 增益集：** 當系統管理員從 Office Store 中選取增益集時，如果 Office Store 中的增益集更新，增益集將在稍後的集中式部署中更新。</span><span class="sxs-lookup"><span data-stu-id="47509-211">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span></span> <span data-ttu-id="47509-212">在下次啟動相關的 Office 應用程式時，增益集就會更新。</span><span class="sxs-lookup"><span data-stu-id="47509-212">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="47509-213">Web 應用程式可以隨時變更。</span><span class="sxs-lookup"><span data-stu-id="47509-213">The web application can change at any time.</span></span> 

### <a name="edit-add-in-access"></a><span data-ttu-id="47509-214">編輯增益集存取</span><span class="sxs-lookup"><span data-stu-id="47509-214">Edit Add-in access</span></span>

<span data-ttu-id="47509-215">部署後，系統管理員也可以修改使用者對增益集的存取權。</span><span class="sxs-lookup"><span data-stu-id="47509-215">Post deployment, admins can also modify the user access to add-ins.</span></span>

1. <span data-ttu-id="47509-216">在系統管理中心中，移至 [**設定** > **服務] & 增益集**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="47509-216">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="47509-217">選取部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-217">Select the deployed add-in.</span></span>

3. <span data-ttu-id="47509-218">按一下 [在**誰可以存取**] 底下的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="47509-218">Click on **Edit** under **Who has Access**.</span></span>
4. <span data-ttu-id="47509-219">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="47509-219">Save the changes.</span></span>
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="47509-220">關閉所有用戶端（Outlook 除外）的 Office Store 以避免增益集下載</span><span class="sxs-lookup"><span data-stu-id="47509-220">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="47509-221">Outlook 增益集安裝是由[不同](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)的程式管理。</span><span class="sxs-lookup"><span data-stu-id="47509-221">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="47509-222">做為組織，您可能想要防止從 Office Store 下載新的 Office 增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-222">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="47509-223">這可以與集中式部署搭配使用，以確保只有組織認可的增益集部署至組織內的使用者。</span><span class="sxs-lookup"><span data-stu-id="47509-223">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="47509-224">若要關閉增益集採集：</span><span class="sxs-lookup"><span data-stu-id="47509-224">To turn off add-in acquisition:</span></span>
  
1. <span data-ttu-id="47509-225">在系統管理中心中，移至 **[設定]** \> [[服務與增益集]](https://go.microsoft.com/fwlink/p/?linkid=2053743) 頁面。</span><span class="sxs-lookup"><span data-stu-id="47509-225">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="47509-226">選取 [**使用者擁有的應用程式和服務**]。</span><span class="sxs-lookup"><span data-stu-id="47509-226">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="47509-227">清除 [讓使用者存取 Office store] 選項。</span><span class="sxs-lookup"><span data-stu-id="47509-227">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="47509-228">這會防止所有使用者從存放區中取得下列增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-228">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="47509-229">Word、Excel 及 PowerPoint 2016 的增益集，來自：</span><span class="sxs-lookup"><span data-stu-id="47509-229">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="47509-230">Windows</span><span class="sxs-lookup"><span data-stu-id="47509-230">Windows</span></span>
    
  - <span data-ttu-id="47509-231">Mac</span><span class="sxs-lookup"><span data-stu-id="47509-231">Mac</span></span>
    
  - <span data-ttu-id="47509-232">辦公室</span><span class="sxs-lookup"><span data-stu-id="47509-232">Office</span></span>
    
    
- <span data-ttu-id="47509-233">從**AppSource**中開始的購置</span><span class="sxs-lookup"><span data-stu-id="47509-233">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="47509-234">Microsoft 365 中的增益集</span><span class="sxs-lookup"><span data-stu-id="47509-234">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="47509-235">嘗試存取儲存區的使用者會看到下列訊息：**對不起，Microsoft 365 已設定為防止個別購買 Office store 增益集。**</span><span class="sxs-lookup"><span data-stu-id="47509-235">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="47509-236">下列版本提供支援關閉 Office 書店的功能：</span><span class="sxs-lookup"><span data-stu-id="47509-236">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="47509-237">Windows： 16.0.9001-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="47509-237">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="47509-238">Mac： 16.10.18011401-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="47509-238">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="47509-239">iOS： 2.9.18010804-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="47509-239">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="47509-240">目前可用的 web。</span><span class="sxs-lookup"><span data-stu-id="47509-240">The web - Currently available.</span></span>
    
<span data-ttu-id="47509-241">這不會讓系統管理員使用集中式部署從 Office Store 指派增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-241">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="47509-242">若要防止使用者使用 Microsoft 帳戶登入，您可以限制登入只使用組織帳戶。</span><span class="sxs-lookup"><span data-stu-id="47509-242">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="47509-243">如需詳細資訊，請參閱[此處](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="47509-243">For more information, look [here](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="47509-244">對存放區中的增益集進行未成年人和取得</span><span class="sxs-lookup"><span data-stu-id="47509-244">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="47509-245">一般資料保護規定（GDPR）是一種歐盟法規，它會生效25，2018。</span><span class="sxs-lookup"><span data-stu-id="47509-245">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="47509-246">它可讓使用者具備及保護其資料的權力。</span><span class="sxs-lookup"><span data-stu-id="47509-246">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="47509-247">其中一個 GDPR 的其中一個方面是，所有未成年人都無法將其個人資料傳送給他們的父系或監護人未獲核准的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="47509-247">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="47509-248">定義為次要的特定年齡取決於個人所在的地區。</span><span class="sxs-lookup"><span data-stu-id="47509-248">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="47509-249">法律規定具有「父母同意」規定的地區包括美國、韓國、英國和歐盟。</span><span class="sxs-lookup"><span data-stu-id="47509-249">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="47509-250">對於這些地區，次要會封鎖（透過 Azure Active Directory）從存放區取得任何新的 Office 增益集，並執行先前取得的增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-250">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="47509-251">對於沒有法令規定的國家，將不會有下載限制。</span><span class="sxs-lookup"><span data-stu-id="47509-251">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="47509-252">根據 Azure Active Directory 中所指定的資料，將使用者判斷為次要。</span><span class="sxs-lookup"><span data-stu-id="47509-252">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="47509-253">承租人管理員負責宣告法律年齡群組和該使用者的「父母同意」。</span><span class="sxs-lookup"><span data-stu-id="47509-253">The tenant admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="47509-254">如果父項/監護人 consents 使用特定增益集，則租使用者管理員可以使用集中式部署，將該增益集部署至所有已同意的未成年人。</span><span class="sxs-lookup"><span data-stu-id="47509-254">If the parent/guardian consents to a minor using a specific add-In, then the tenant admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="47509-255">若要 GDPR 相容性，您必須確定在學校/組織中部署下列 Office 組建中的其中一項。</span><span class="sxs-lookup"><span data-stu-id="47509-255">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
  
 <span data-ttu-id="47509-256">**Word、Excel、PowerPoint 及專案**：</span><span class="sxs-lookup"><span data-stu-id="47509-256">**For Word, Excel, PowerPoint, and Project**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="47509-257">**平台**</span><span class="sxs-lookup"><span data-stu-id="47509-257">**Platform**</span></span> <br/> |<span data-ttu-id="47509-258">**組建號碼**</span><span class="sxs-lookup"><span data-stu-id="47509-258">**Build number**</span></span> <br/> |
|<span data-ttu-id="47509-259">適用于企業的 Microsoft 365 應用程式（每月通道）</span><span class="sxs-lookup"><span data-stu-id="47509-259">Microsoft 365 Apps for enterprise (Monthly Channel)</span></span>  <br/> |<span data-ttu-id="47509-260">9001.2138</span><span class="sxs-lookup"><span data-stu-id="47509-260">9001.2138</span></span>   <br/> |
|<span data-ttu-id="47509-261">適用于企業的 Microsoft 365 應用程式（半年通道）</span><span class="sxs-lookup"><span data-stu-id="47509-261">Microsoft 365 Apps for enterprise (Semi-Annual Channel)</span></span>  <br/> |<span data-ttu-id="47509-262">8431.2159</span><span class="sxs-lookup"><span data-stu-id="47509-262">8431.2159</span></span>  <br/> |
|<span data-ttu-id="47509-263">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="47509-263">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="47509-264">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="47509-264">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="47509-265">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="47509-265">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="47509-266">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="47509-266">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="47509-267">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="47509-267">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="47509-268">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="47509-268">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="47509-269">網頁版 Office</span><span class="sxs-lookup"><span data-stu-id="47509-269">Office for the web</span></span>  <br/> |<span data-ttu-id="47509-270">不適用</span><span class="sxs-lookup"><span data-stu-id="47509-270">N/A</span></span>  <br/> |
   
 <span data-ttu-id="47509-271">**Outlook**：</span><span class="sxs-lookup"><span data-stu-id="47509-271">**For Outlook**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="47509-272">**平台**</span><span class="sxs-lookup"><span data-stu-id="47509-272">**Platform**</span></span> <br/> |<span data-ttu-id="47509-273">**組建號碼**</span><span class="sxs-lookup"><span data-stu-id="47509-273">**Build number**</span></span> <br/> |
|<span data-ttu-id="47509-274">Outlook 2016 for Windows （MSI）</span><span class="sxs-lookup"><span data-stu-id="47509-274">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="47509-275">建立無待定</span><span class="sxs-lookup"><span data-stu-id="47509-275">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="47509-276">Outlook 2016 for Windows （C2R）</span><span class="sxs-lookup"><span data-stu-id="47509-276">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="47509-277">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="47509-277">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="47509-278">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="47509-278">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="47509-279">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="47509-279">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="47509-280">iOS 的 Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="47509-280">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="47509-281">2.75.0</span><span class="sxs-lookup"><span data-stu-id="47509-281">2.75.0</span></span>  <br/> |
|<span data-ttu-id="47509-282">適用于 Android 的 Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="47509-282">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="47509-283">2.2.145</span><span class="sxs-lookup"><span data-stu-id="47509-283">2.2.145</span></span>  <br/> |
|<span data-ttu-id="47509-284">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="47509-284">Outlook.com</span></span>  <br/> |<span data-ttu-id="47509-285">不適用</span><span class="sxs-lookup"><span data-stu-id="47509-285">N/A</span></span>  <br/> |
   
 <span data-ttu-id="47509-286">**Office 2013 需求**</span><span class="sxs-lookup"><span data-stu-id="47509-286">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="47509-287">如果已啟用 Active Directory 驗證程式庫（ADAL），Windows 的 Word、Excel 及 PowerPoint 2013 會支援相同的次要檢查。</span><span class="sxs-lookup"><span data-stu-id="47509-287">Word, Excel, and PowerPoint 2013 for Windows will support the same minor checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="47509-288">規範有兩個選項，如接下來所述。</span><span class="sxs-lookup"><span data-stu-id="47509-288">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="47509-289">**啟用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="47509-289">**Enable ADAL**.</span></span> <span data-ttu-id="47509-290">本文說明如何啟用 ADAL for Office 2013：搭配[使用 Microsoft 365 新式驗證與 office 用戶端](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。</span><span class="sxs-lookup"><span data-stu-id="47509-290">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="47509-291">您也需要將登錄機碼設定為啟用 ADAL，如在[Windows 裝置上啟用 Office 2013 新式驗證](../security-and-compliance/enable-modern-authentication.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="47509-291">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="47509-292">此外，您必須安裝下列 Office 2013 的四月更新：</span><span class="sxs-lookup"><span data-stu-id="47509-292">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="47509-293">Office 2013 的安全性更新說明：4月10日（2018）</span><span class="sxs-lookup"><span data-stu-id="47509-293">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="47509-294">2018年4月3日，Office 2013 的更新（KB4018333）</span><span class="sxs-lookup"><span data-stu-id="47509-294">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="47509-295">**不要啟用 ADAL**。</span><span class="sxs-lookup"><span data-stu-id="47509-295">**Don't enable ADAL**.</span></span> <span data-ttu-id="47509-296">如果您無法在 Office 2013 中啟用 ADAL，我們建議使用「群組原則」來關閉 Office 用戶端的存放區。</span><span class="sxs-lookup"><span data-stu-id="47509-296">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the office clients.</span></span> <span data-ttu-id="47509-297">有關如何關閉 Office 相關應用程式設定的資訊位於[這裡](https://technet.microsoft.com/library/cc178992.aspx)。</span><span class="sxs-lookup"><span data-stu-id="47509-297">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>
    
## <a name="end-user-experience-with-add-ins"></a><span data-ttu-id="47509-298">使用者的增益集使用體驗</span><span class="sxs-lookup"><span data-stu-id="47509-298">End user experience with add-ins</span></span>

<span data-ttu-id="47509-p138">既然您已部署增益集，使用者就可以開始在他們的 Office 應用程式中使用 (請參閱[開始使用 Office 增益集](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx))。增益集會顯示在增益集支援的所有平台上。</span><span class="sxs-lookup"><span data-stu-id="47509-p138">Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). The add-in will appear on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="47509-301">如果增益集支援增益集命令，命令會顯示在 Office 功能區上。</span><span class="sxs-lookup"><span data-stu-id="47509-301">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="47509-302">在下列範例中，會出現**引文**增益集的命令**搜尋引文**。</span><span class="sxs-lookup"><span data-stu-id="47509-302">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![具有搜尋引文的 Office 功能區](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="47509-304">如果部署的增益集不支援增益集命令，或是您想要查看所有已部署的增益集，您可以透過**My 增益集**進行查看。</span><span class="sxs-lookup"><span data-stu-id="47509-304">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="47509-305">在 Word 2016、Excel 2016 或 PowerPoint 2016 中</span><span class="sxs-lookup"><span data-stu-id="47509-305">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="47509-306">選取 **[ \>插入我的增益集**]。</span><span class="sxs-lookup"><span data-stu-id="47509-306">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="47509-307">在 [Office 增益集] 視窗中，選取 [**管理受管理**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="47509-307">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="47509-308">按兩下您先前部署的增益集（在此範例中為 [**引文**]）。</span><span class="sxs-lookup"><span data-stu-id="47509-308">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="47509-309">![[Office 增益集] 頁面的 [管理受管理] 索引標籤](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="47509-309">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="47509-310">在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="47509-310">In Outlook</span></span>

1. <span data-ttu-id="47509-311">在 [**首頁**] 功能區上，選取 [**取得增益集**]。</span><span class="sxs-lookup"><span data-stu-id="47509-311">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="47509-312">![Outlook 中的 [市集] 按鈕](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="47509-312">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="47509-313">選取左側導覽中的 [系統**管理管理**]。</span><span class="sxs-lookup"><span data-stu-id="47509-313">Select **Admin-managed** in the left nav.</span></span>

## <a name="delete-the-add-in"></a><span data-ttu-id="47509-314">刪除增益集</span><span class="sxs-lookup"><span data-stu-id="47509-314">Delete the add-in</span></span>

<span data-ttu-id="47509-315">您也可以刪除已部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-315">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="47509-316">在系統管理中心中，移至 [**設定** > **服務] & 增益集**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="47509-316">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="47509-317">選取部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="47509-317">Select the deployed add-in.</span></span>

3. <span data-ttu-id="47509-318">按一下 [**刪除] Add-In**。</span><span class="sxs-lookup"><span data-stu-id="47509-318">Click on **Delete Add-In**.</span></span> <span data-ttu-id="47509-319">移除右下角的增益集按鈕。</span><span class="sxs-lookup"><span data-stu-id="47509-319">Remove the Add-in button on the bottom right corner.</span></span>
4. <span data-ttu-id="47509-320">驗證您的選擇，然後選擇 [**移除增益集**]。</span><span class="sxs-lookup"><span data-stu-id="47509-320">Validate your selections, and choose **Remove add-in**.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="47509-321">深入了解</span><span class="sxs-lookup"><span data-stu-id="47509-321">Learn more</span></span>

<span data-ttu-id="47509-322">深入了解如何建立及建置 [Office 增益集](https://go.microsoft.com/fwlink/p/?linkid=846362)。</span><span class="sxs-lookup"><span data-stu-id="47509-322">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="47509-323">[使用集中式部署 PowerShell Cmdlet 來管理增益集](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="47509-323">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="47509-324">疑難排解：使用者未看到增益集</span><span class="sxs-lookup"><span data-stu-id="47509-324">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
