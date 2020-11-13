---
title: 在系統管理中心管理增益集
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用集中式增益集，將增益集部署至組織中的使用者和群組。
ms.openlocfilehash: 5521b01e059ca8ae4a97ecb094f9aa1198263701
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071474"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="0fdf2-103">在系統管理中心管理增益集</span><span class="sxs-lookup"><span data-stu-id="0fdf2-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0fdf2-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-104">The admin center is changing.</span></span> <span data-ttu-id="0fdf2-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="0fdf2-106">Office 增益集可協助您個人化檔，並簡化存取網頁上資訊的方式 (請參閱 [開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="0fdf2-107">在管理員為組織中的使用者部署增益集後，系統管理員可以關閉或開啟增益集、編輯、刪除及管理增益集的存取。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="0fdf2-108">如需從系統管理中心安裝增益集的詳細資訊，請參閱 [在系統管理中心部署增益集](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="0fdf2-109">增益集狀態</span><span class="sxs-lookup"><span data-stu-id="0fdf2-109">Add-in states</span></span>

<span data-ttu-id="0fdf2-110">增益集可以處於 [ **開啟** ] 或 [ **關閉** ] 狀態。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="0fdf2-111">**State**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-111">**State**</span></span>|<span data-ttu-id="0fdf2-112">**狀態如何發生**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-112">**How the state occurs**</span></span>|<span data-ttu-id="0fdf2-113">**影響**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0fdf2-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-114">**Active**</span></span>  <br/> |<span data-ttu-id="0fdf2-115">系統管理員上載增益集，並將其指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="0fdf2-116">被指派增益集的使用者和群組會在相關用戶端中看見增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="0fdf2-117">**已關閉**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="0fdf2-118">系統管理員已關閉增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="0fdf2-119">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="0fdf2-120">如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="0fdf2-121">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="0fdf2-122">系統管理員已刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="0fdf2-123">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="0fdf2-124">如果沒有人再使用增益集，請考慮刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="0fdf2-125">例如，如果增益集只會在一年的特定時間內使用，則關閉增益集可能會有意義。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="0fdf2-126">刪除增益集</span><span class="sxs-lookup"><span data-stu-id="0fdf2-126">Delete an add-in</span></span>

<span data-ttu-id="0fdf2-127">您也可以刪除已部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="0fdf2-128">在系統管理中心中，移至 [ **設定**  >  **服務] & 增益集** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0fdf2-129">系統管理中心已更新整合型應用程式的部署經驗。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0fdf2-130">如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 [ **設定** ] [  >  **整合式應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0fdf2-131">在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="0fdf2-132">選取部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="0fdf2-133">按一下 [ **刪除] Add-In** 。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="0fdf2-134">移除右下角的增益集按鈕。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="0fdf2-135">驗證您的選擇，然後選擇 [ **移除增益集** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="0fdf2-136">編輯增益集存取</span><span class="sxs-lookup"><span data-stu-id="0fdf2-136">Edit add-in access</span></span>

<span data-ttu-id="0fdf2-137">部署後，系統管理員也可以管理使用者對增益集的存取。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="0fdf2-138">在系統管理中心中，移至 [ **設定**  >  **服務] & 增益集** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0fdf2-139">系統管理中心已更新整合型應用程式的部署經驗。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0fdf2-140">如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 [ **設定** ] [  >  **整合式應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0fdf2-141">在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="0fdf2-142">選取部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="0fdf2-143">按一下 [在 **誰可以存取** ] 底下的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="0fdf2-144">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="0fdf2-145">在 Outlook) 以外的所有用戶端上關閉 Office 存放區，以防止增益集下載 (</span><span class="sxs-lookup"><span data-stu-id="0fdf2-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="0fdf2-146">Outlook 增益集安裝是由 [不同](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)的程式管理。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="0fdf2-147">做為組織，您可能想要防止從 Office Store 下載新的 Office 增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="0fdf2-148">這可以與集中式部署搭配使用，以確保只有組織認可的增益集部署至組織內的使用者。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="0fdf2-149">**若要關閉增益集採集**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="0fdf2-150">在系統管理中心中，移至 **[設定]** \> [[服務與增益集]](https://go.microsoft.com/fwlink/p/?linkid=2053743) 頁面。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0fdf2-151">系統管理中心已更新整合型應用程式的部署經驗。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0fdf2-152">如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 [ **設定** ] [  >  **整合式應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0fdf2-153">在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="0fdf2-154">選取 [ **使用者擁有的應用程式和服務** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="0fdf2-155">清除 [讓使用者存取 Office store] 選項。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="0fdf2-156">這會防止所有使用者從存放區中取得下列增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="0fdf2-157">Word、Excel 及 PowerPoint 2016 的增益集，來自：</span><span class="sxs-lookup"><span data-stu-id="0fdf2-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="0fdf2-158">Windows</span><span class="sxs-lookup"><span data-stu-id="0fdf2-158">Windows</span></span>
    
  - <span data-ttu-id="0fdf2-159">Mac</span><span class="sxs-lookup"><span data-stu-id="0fdf2-159">Mac</span></span>
    
  - <span data-ttu-id="0fdf2-160">辦公室</span><span class="sxs-lookup"><span data-stu-id="0fdf2-160">Office</span></span>
    
    
- <span data-ttu-id="0fdf2-161">從 **AppSource** 中開始的購置</span><span class="sxs-lookup"><span data-stu-id="0fdf2-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="0fdf2-162">Microsoft 365 中的增益集</span><span class="sxs-lookup"><span data-stu-id="0fdf2-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="0fdf2-163">嘗試存取儲存區的使用者會看到下列訊息： **對不起，Microsoft 365 已設定為防止個別購買 Office store 增益集。**</span><span class="sxs-lookup"><span data-stu-id="0fdf2-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="0fdf2-164">下列版本提供支援關閉 Office 書店的功能：</span><span class="sxs-lookup"><span data-stu-id="0fdf2-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="0fdf2-165">Windows： 16.0.9001-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="0fdf2-166">Mac： 16.10.18011401-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="0fdf2-167">iOS： 2.9.18010804-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="0fdf2-168">目前可用的 web。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-168">The web - Currently available.</span></span>
    
<span data-ttu-id="0fdf2-169">這不會讓系統管理員使用集中式部署從 Office Store 指派增益集。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="0fdf2-170">若要防止使用者使用 Microsoft 帳戶登入，您可以限制登入只使用組織帳戶。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="0fdf2-171">如需詳細資訊，請參閱 [Office 2016 的身分識別、驗證及授權](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="0fdf2-172">防止使用者存取 office 書店也會防止使用者在 [進行測試時旁載 Office 增益集](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="0fdf2-173">更多關於使用者使用增益集的體驗</span><span class="sxs-lookup"><span data-stu-id="0fdf2-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="0fdf2-174">部署增益集之後，您的使用者就可以開始在 Office 應用程式中使用它 (請參閱 [開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="0fdf2-175">增益集會出現在增益集所支援的所有平臺上。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="0fdf2-176">如果增益集支援增益集命令，命令會顯示在 Office 功能區上。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-176">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="0fdf2-177">在下列範例中，會出現 **引文** 增益集的命令 **搜尋引文** 。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-177">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![具有搜尋引文的 Office 功能區](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="0fdf2-179">如果部署的增益集不支援增益集命令，或是您想要查看所有已部署的增益集，您可以透過 **My 增益集** 進行查看。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="0fdf2-180">在 Word 2016、Excel 2016 或 PowerPoint 2016 中</span><span class="sxs-lookup"><span data-stu-id="0fdf2-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="0fdf2-181">選取 [ **插入 \> 我的增益集** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="0fdf2-182">在 [Office 增益集] 視窗中，選取 [ **管理受管理** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="0fdf2-183">在此範例中，按兩下您先前部署的增益集 (中的 **引文** ) 。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="0fdf2-184">![[Office 增益集] 頁面的 [管理受管理] 索引標籤](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="0fdf2-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="0fdf2-185">在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="0fdf2-185">In Outlook</span></span>

1. <span data-ttu-id="0fdf2-186">在 [ **首頁** ] 功能區上，選取 [ **取得增益集** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="0fdf2-187">![Outlook 中的 [市集] 按鈕](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="0fdf2-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="0fdf2-188">選取左側導覽中的 [系統 **管理管理** ]。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="0fdf2-189">深入了解</span><span class="sxs-lookup"><span data-stu-id="0fdf2-189">Learn more</span></span>

[<span data-ttu-id="0fdf2-190">在系統管理中心部署增益集</span><span class="sxs-lookup"><span data-stu-id="0fdf2-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="0fdf2-191">深入了解如何建立及建置 [Office 增益集](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="0fdf2-192">[使用集中式部署 PowerShell Cmdlet 來管理增益集](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="0fdf2-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="0fdf2-193">疑難排解：使用者未看到增益集</span><span class="sxs-lookup"><span data-stu-id="0fdf2-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="0fdf2-194">Microsoft Store 中的未成年人和取得增益集</span><span class="sxs-lookup"><span data-stu-id="0fdf2-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
