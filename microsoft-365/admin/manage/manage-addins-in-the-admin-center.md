---
title: 在系統管理中心管理增益集
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 瞭解如何使用集中式增益集，將增益集部署至組織中的使用者和群組。
ms.openlocfilehash: aad68d37fb23c26ef1a1ca1ba7dfc5d4e2a40bfe
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392860"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="90894-103">在系統管理中心管理增益集</span><span class="sxs-lookup"><span data-stu-id="90894-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="90894-104">Office 增益集可協助您個人化檔，並簡化存取網頁上資訊的方式 (請參閱[開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。</span><span class="sxs-lookup"><span data-stu-id="90894-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="90894-105">在管理員為組織中的使用者部署增益集後，系統管理員可以關閉或開啟增益集、編輯、刪除及管理增益集的存取。</span><span class="sxs-lookup"><span data-stu-id="90894-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="90894-106">如需從系統管理中心安裝增益集的詳細資訊，請參閱 [在系統管理中心部署增益集](./manage-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="90894-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="90894-107">增益集狀態</span><span class="sxs-lookup"><span data-stu-id="90894-107">Add-in states</span></span>

<span data-ttu-id="90894-108">增益集可以處於 [ **開啟** ] 或 [ **關閉** ] 狀態。</span><span class="sxs-lookup"><span data-stu-id="90894-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="90894-109">狀態</span><span class="sxs-lookup"><span data-stu-id="90894-109">State</span></span> | <span data-ttu-id="90894-110">狀態如何發生</span><span class="sxs-lookup"><span data-stu-id="90894-110">How the state occurs</span></span> | <span data-ttu-id="90894-111">影響</span><span class="sxs-lookup"><span data-stu-id="90894-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="90894-112">**Active**</span><span class="sxs-lookup"><span data-stu-id="90894-112">**Active**</span></span>  <br/> |<span data-ttu-id="90894-113">系統管理員上載增益集，並將其指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="90894-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="90894-114">被指派增益集的使用者和群組會在相關用戶端中看見增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="90894-115">**已關閉**</span><span class="sxs-lookup"><span data-stu-id="90894-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="90894-116">系統管理員已關閉增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="90894-117">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="90894-118">如果增益集狀態已變更為 [使用中]，使用者和群組將可再次存取增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="90894-119">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="90894-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="90894-120">系統管理員已刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="90894-121">被指派增益集的使用者和群組無法再存取增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="90894-122">如果沒有人再使用增益集，請考慮刪除增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="90894-123">例如，如果增益集只會在一年的特定時間內使用，則關閉增益集可能會有意義。</span><span class="sxs-lookup"><span data-stu-id="90894-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="90894-124">刪除增益集</span><span class="sxs-lookup"><span data-stu-id="90894-124">Delete an add-in</span></span>

<span data-ttu-id="90894-125">您也可以刪除已部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="90894-126">在系統管理中心中，移至 **設定**  >  **服務 & 增益集**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="90894-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90894-127">系統管理中心已更新整合型應用程式的部署經驗。</span><span class="sxs-lookup"><span data-stu-id="90894-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="90894-128">如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 **設定** 的  >  **整合式應用程式**。</span><span class="sxs-lookup"><span data-stu-id="90894-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="90894-129">在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集**]。</span><span class="sxs-lookup"><span data-stu-id="90894-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="90894-130">選取部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="90894-131">按一下 [ **刪除] Add-In**。</span><span class="sxs-lookup"><span data-stu-id="90894-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="90894-132">移除右下角的增益集按鈕。</span><span class="sxs-lookup"><span data-stu-id="90894-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="90894-133">驗證您的選項，然後選擇 [移除增益集 **]**。</span><span class="sxs-lookup"><span data-stu-id="90894-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="90894-134">編輯增益集存取權</span><span class="sxs-lookup"><span data-stu-id="90894-134">Edit add-in access</span></span>

<span data-ttu-id="90894-135">部署後，系統管理員也可以管理使用者對增益集的存取。</span><span class="sxs-lookup"><span data-stu-id="90894-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="90894-136">在系統管理中心中，移至 **設定**  >  **服務 & 增益集**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="90894-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90894-137">系統管理中心已更新整合型應用程式的部署經驗。</span><span class="sxs-lookup"><span data-stu-id="90894-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="90894-138">如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 **設定** 的  >  **整合式應用程式**。</span><span class="sxs-lookup"><span data-stu-id="90894-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="90894-139">在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集**]。</span><span class="sxs-lookup"><span data-stu-id="90894-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="90894-140">選取部署的增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="90894-141">按一下 [**神秘具有存取權**] 底下的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="90894-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="90894-142">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="90894-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="90894-143">在所有用戶端上關閉 Office 儲存區，以避免增益集下載 (但 Outlook) </span><span class="sxs-lookup"><span data-stu-id="90894-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="90894-144">Outlook 增益集安裝是由[不同](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)的程式所管理。</span><span class="sxs-lookup"><span data-stu-id="90894-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="90894-145">做為組織，您可能想要防止從 Office 存放區下載新 Office 增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="90894-146">這可以與集中式部署搭配使用，以確保只有組織認可的增益集部署至組織內的使用者。</span><span class="sxs-lookup"><span data-stu-id="90894-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="90894-147">**若要關閉增益集採集**</span><span class="sxs-lookup"><span data-stu-id="90894-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="90894-148">在系統管理中心中，移至 **[設定]** \> [[服務與增益集]](https://go.microsoft.com/fwlink/p/?linkid=2053743) 頁面。</span><span class="sxs-lookup"><span data-stu-id="90894-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90894-149">系統管理中心已更新整合型應用程式的部署經驗。</span><span class="sxs-lookup"><span data-stu-id="90894-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="90894-150">如果您未看到上述步驟，請移至 [集中式部署] 區段，移至 **設定** 的  >  **整合式應用程式**。</span><span class="sxs-lookup"><span data-stu-id="90894-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="90894-151">在 [ **整合式應用程式** ] 頁面的頂端，選擇 [ **增益集**]。</span><span class="sxs-lookup"><span data-stu-id="90894-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="90894-152">選取 [使用者所擁有的應用程式與服務 **]**。</span><span class="sxs-lookup"><span data-stu-id="90894-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="90894-153">清除讓使用者存取 Office 市集的選項。</span><span class="sxs-lookup"><span data-stu-id="90894-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="90894-154">這會防止所有使用者從存放區中取得下列增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="90894-155">Word、Excel 及 PowerPoint 2016 的增益集：</span><span class="sxs-lookup"><span data-stu-id="90894-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="90894-156">Windows</span><span class="sxs-lookup"><span data-stu-id="90894-156">Windows</span></span>
      - <span data-ttu-id="90894-157">Mac</span><span class="sxs-lookup"><span data-stu-id="90894-157">Mac</span></span>
      - <span data-ttu-id="90894-158">辦公室</span><span class="sxs-lookup"><span data-stu-id="90894-158">Office</span></span>
        
        
    - <span data-ttu-id="90894-159">從 **AppSource** 中開始的購置</span><span class="sxs-lookup"><span data-stu-id="90894-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="90894-160">Microsoft 365 內的增益集</span><span class="sxs-lookup"><span data-stu-id="90894-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="90894-161">嘗試存取儲存區的使用者會看到下列訊息：**對不起，Microsoft 365 已設定為防止個別購買 Office 儲存區增益集。**</span><span class="sxs-lookup"><span data-stu-id="90894-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="90894-162">下列版本提供支援關閉 Office 儲存區：</span><span class="sxs-lookup"><span data-stu-id="90894-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="90894-163">Windows： 16.0.9001-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="90894-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="90894-164">Mac： 16.10.18011401-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="90894-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="90894-165">iOS： 2.9.18010804-目前可供使用。</span><span class="sxs-lookup"><span data-stu-id="90894-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="90894-166">目前可用的 web。</span><span class="sxs-lookup"><span data-stu-id="90894-166">The web - Currently available.</span></span>
    
<span data-ttu-id="90894-167">這不會讓系統管理員使用集中式部署從 Office 儲存區指派增益集。</span><span class="sxs-lookup"><span data-stu-id="90894-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>

> [!NOTE] 
> <span data-ttu-id="90894-168">例如，即使系統管理員已停用存放區，增益集（例如 Visio 資料視覺化檢視、Bing 地圖服務和 Graph 人員）仍會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="90894-168">Add-ins such as Visio Data Visualizer, Bing Maps, and People Graph will still show up in the ribbon, even if an admin has disabled the Store.</span></span> <span data-ttu-id="90894-169">若要移除這些連結，管理員必須透過「群組原則」物件停用存放區 (GPO) 。</span><span class="sxs-lookup"><span data-stu-id="90894-169">To remove these links, administrators must disable the Store through Group Policy Object (GPO).</span></span>
  
<span data-ttu-id="90894-170">若要防止使用者使用 Microsoft 帳戶登入，您可以限制登入只使用組織帳戶。</span><span class="sxs-lookup"><span data-stu-id="90894-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="90894-171">如需詳細資訊，請參閱[Office 2016 的身分識別、驗證及授權](/DeployOffice/security/identity-authentication-and-authorization-in-office)。</span><span class="sxs-lookup"><span data-stu-id="90894-171">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="90894-172">防止使用者存取 office 書店也會防止使用者從[旁載 Office 增益集，以便從網路共用進行測試](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="90894-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="90894-173">有關使用增益集的使用者經驗的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="90894-173">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="90894-174">部署增益集之後，您的使用者可以在其 Office 應用程式中開始使用它 (請參閱[開始使用 Office 增益集](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。</span><span class="sxs-lookup"><span data-stu-id="90894-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="90894-175">增益集會出現在增益集所支援的所有平臺上。</span><span class="sxs-lookup"><span data-stu-id="90894-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="90894-176">如果增益集支援增益集命令，命令會顯示在 Office 功能區上。</span><span class="sxs-lookup"><span data-stu-id="90894-176">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="90894-177">在下列範例中，會出現 **引文** 增益集的命令 **搜尋引文**。</span><span class="sxs-lookup"><span data-stu-id="90894-177">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office 帶搜尋引文的功能區](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="90894-179">如果部署的增益集不支援增益集命令，或是您想要查看所有已部署的增益集，您可以透過 **My 增益集** 進行查看。</span><span class="sxs-lookup"><span data-stu-id="90894-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="90894-180">在 Word 2016、Excel 2016 或 PowerPoint 2016 中</span><span class="sxs-lookup"><span data-stu-id="90894-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="90894-181">選取 [ **插入 \> 我的增益集**]。</span><span class="sxs-lookup"><span data-stu-id="90894-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="90894-182">在 [Office 增益集] 視窗中，選取 [**管理受管理**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90894-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="90894-183">在此範例中，按兩下您先前部署的增益集 (中的 **引文**) 。</span><span class="sxs-lookup"><span data-stu-id="90894-183">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![[Office 增益集] 頁面的 [管理受管理] 索引標籤](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="90894-185">在 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="90894-185">In Outlook</span></span>

1. <span data-ttu-id="90894-186">在 [ **首頁** ] 功能區上，選取 [ **取得增益集**]。</span><span class="sxs-lookup"><span data-stu-id="90894-186">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Outlook 中的 [市集] 按鈕](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="90894-188">選取左側瀏覽列中的 [受系統管理員管理 **]**。</span><span class="sxs-lookup"><span data-stu-id="90894-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="90894-189">相關內容</span><span class="sxs-lookup"><span data-stu-id="90894-189">Related content</span></span>

<span data-ttu-id="90894-190">[在系統管理中心中部署增益集](./manage-deployment-of-add-ins.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="90894-190">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="90894-191">深入瞭解建立及建立[Office 增益集](/office/dev/add-ins/overview/office-add-ins) (文章) </span><span class="sxs-lookup"><span data-stu-id="90894-191">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="90894-192">[使用集中式部署 PowerShell Cmdlet 來管理增益集](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="90894-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="90894-193">[疑難排解：使用者未看到增益集](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (文章) </span><span class="sxs-lookup"><span data-stu-id="90894-193">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="90894-194">[從 Microsoft Store (文章中的未成年人和取得增益集](./minors-and-acquiring-addins-from-the-store.md)) </span><span class="sxs-lookup"><span data-stu-id="90894-194">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>
