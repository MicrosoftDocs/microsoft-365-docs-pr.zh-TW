---
title: 設定 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: 在 Project Cortex 中設定內容瞭解
ms.openlocfilehash: 2f9fd4e035152a127f9f1c254f4c489a6ca4c976
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994698"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="4ef90-103">設定 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4ef90-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="4ef90-104">系統管理員可以使用 Microsoft 365 系統管理中心來設定 [Microsoft SharePoint Syntex](index.md)。</span><span class="sxs-lookup"><span data-stu-id="4ef90-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="4ef90-105">開始之前，請先考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="4ef90-105">Consider the following before you start:</span></span>

- <span data-ttu-id="4ef90-106">其中哪些 SharePoint 網站您將會啟用表單處理？</span><span class="sxs-lookup"><span data-stu-id="4ef90-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="4ef90-107">所有網站、部分或選取的網站嗎？</span><span class="sxs-lookup"><span data-stu-id="4ef90-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="4ef90-108">您的預設內容中心名稱為何？</span><span class="sxs-lookup"><span data-stu-id="4ef90-108">What will you name your default content center?</span></span>

<span data-ttu-id="4ef90-109">您可以在 Microsoft 365 系統管理中心初次設定之後變更您的設定。</span><span class="sxs-lookup"><span data-stu-id="4ef90-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="4ef90-110">設定之前，請務必針對您環境中的設定和設定內容理解的最佳方式進行規劃。</span><span class="sxs-lookup"><span data-stu-id="4ef90-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="4ef90-111">例如，您需要做出下列決定：</span><span class="sxs-lookup"><span data-stu-id="4ef90-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="4ef90-112">您想要啟用表單處理的 SharePoint 網站 - 所有網站、部分或選取的網站</span><span class="sxs-lookup"><span data-stu-id="4ef90-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="4ef90-113">內容中心的名稱和系統管理員</span><span class="sxs-lookup"><span data-stu-id="4ef90-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="4ef90-114">需求</span><span class="sxs-lookup"><span data-stu-id="4ef90-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="4ef90-115">您必須具備全域系統管理員或 SharePoint 系統管理員權限才能存取 Microsoft 365 系統管理中心，並設定 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="4ef90-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="4ef90-116">如果您是系統管理員，您也可以在設定之後隨時變更所選的設定，以及在 Microsoft 365 系統管理中心中的所有內容瞭解管理設定。</span><span class="sxs-lookup"><span data-stu-id="4ef90-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="4ef90-117">授權</span><span class="sxs-lookup"><span data-stu-id="4ef90-117">Licensing</span></span>

<span data-ttu-id="4ef90-118">若要使用 SharePoint Syntex，您的組織必須有 SharePoint Syntex 的訂閱，且每個使用者都必須獲指派下列授權：</span><span class="sxs-lookup"><span data-stu-id="4ef90-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="4ef90-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4ef90-119">SharePoint Syntex</span></span>
- <span data-ttu-id="4ef90-120">SharePoint Syntex - SPO 類型</span><span class="sxs-lookup"><span data-stu-id="4ef90-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="4ef90-121">Common Data Service for SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4ef90-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="4ef90-122">如果您在日後 (或您的試用版到期) 取消 SharePoint Syntex 訂閱，使用者將不再可建立或執行文件瞭解模型或表單處理模型，且內容中心範本將不再可用。</span><span class="sxs-lookup"><span data-stu-id="4ef90-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="4ef90-123">此外，字詞庫報告、SKOS 分類法匯入和內容類型推送將不再可用。</span><span class="sxs-lookup"><span data-stu-id="4ef90-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="4ef90-124">不會刪除任何內容，且不會變更網站權限。</span><span class="sxs-lookup"><span data-stu-id="4ef90-124">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="4ef90-125">AI Builder 點數</span><span class="sxs-lookup"><span data-stu-id="4ef90-125">AI Builder credits</span></span>

<span data-ttu-id="4ef90-126">如果貴組織中的 SharePoint Syntex 有 300 個或更多 SharePoint Syntex 授權，您將會獲一百萬的 AI Builder 點數。</span><span class="sxs-lookup"><span data-stu-id="4ef90-126">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="4ef90-127">如果您的授權少於 300 個，您必須購買 AI Builder 點數，才能使用表單處理。</span><span class="sxs-lookup"><span data-stu-id="4ef90-127">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="4ef90-128">您可以使用 [AI Builder  計算機](https://powerapps.microsoft.com/ai-builder-calculator)，來估計最適合您的 AI Builder 容量。</span><span class="sxs-lookup"><span data-stu-id="4ef90-128">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="4ef90-129">如果您計劃使用自訂的 Power Platform 環境，您必須 [配置該環境的點數](/power-platform/admin/capacity-add-on)。</span><span class="sxs-lookup"><span data-stu-id="4ef90-129">If you plan to use a custom Power Platform environment, you must [allocate credits to that environment](/power-platform/admin/capacity-add-on).</span></span>

<span data-ttu-id="4ef90-130">請移至 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/resources/capacity)查看您的點數和使用狀況。</span><span class="sxs-lookup"><span data-stu-id="4ef90-130">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="4ef90-131">若要設定 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4ef90-131">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="4ef90-132">在 [Microsoft 365 系統管理中心] 中，選取 **[設定]**，然後查看 **[檔案和內容]** 區段。</span><span class="sxs-lookup"><span data-stu-id="4ef90-132">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="4ef90-133">在 **[檔案和內容]** 區段中，選取 **[自動化內容瞭解]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-133">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="4ef90-134">在 **[自動化內容瞭解]** 頁面上，按一下 **[開始使用]** 逐步執行設定流程。</span><span class="sxs-lookup"><span data-stu-id="4ef90-134">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4ef90-135">![開始設定](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="4ef90-135">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="4ef90-136">在 **[設定表單處理]** 頁面上，您可以選擇是否要讓使用者能夠在特定 SharePoint 文件庫中建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="4ef90-136">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="4ef90-137">您可以在 [文件庫] 功能區中使用功能表選項，在啟用此功能的 SharePoint 文件庫中 **[建立表單處理模型]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-137">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="4ef90-138">針對 **哪個 SharePoint 文件庫應顯示建立表單處理模型的選項**，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="4ef90-138">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="4ef90-139">**所有 SharePoint 文件庫**，讓貴組織中的所有 SharePoint 文件庫皆可使用。</span><span class="sxs-lookup"><span data-stu-id="4ef90-139">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="4ef90-140">**僅限選取 SharePoint 網站中的文件庫**，然後選取您要讓其可供使用的網站，或上傳最多 50 個網站的清單。</span><span class="sxs-lookup"><span data-stu-id="4ef90-140">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="4ef90-141">**不使用 SharePoint 文件庫**，如果您不想讓任何網站都能使用 SharePoint 文件庫 (您可以在設定後變更)。</span><span class="sxs-lookup"><span data-stu-id="4ef90-141">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ef90-142">![設定表單處理網站選項](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="4ef90-142">![Configure form processing site options](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="4ef90-143">當網站被包含之後移除網站，並不會影響該網站中文件庫套用的現有模型，或將文件理解模型套用至文件庫的功能。</span><span class="sxs-lookup"><span data-stu-id="4ef90-143">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
    <span data-ttu-id="4ef90-144">若您已經設定多個 Power Platform 環境，您可以選擇您想要與表單處理一起使用的環境。</span><span class="sxs-lookup"><span data-stu-id="4ef90-144">If you have multiple Power Platform environments configured, you can choose which one you want to use with for form processing.</span></span> <span data-ttu-id="4ef90-145">(如果您只有一個環境，則不會出現此選項)。</span><span class="sxs-lookup"><span data-stu-id="4ef90-145">(This option will not appear if you only have one environment.)</span></span>

    ![設定表單處理 Power Platform 選項](../media/content-understanding/setup-power-platform-env.png)

    <span data-ttu-id="4ef90-147">針對 **Power Platform 環境**，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="4ef90-147">For **Power Platform environment**, you can select:</span></span>
    - <span data-ttu-id="4ef90-148">**使用預設環境** 以使用您的預設 Power Platform 環境。</span><span class="sxs-lookup"><span data-stu-id="4ef90-148">**Use the default environment** to use your default Power Platform environment.</span></span>
    - <span data-ttu-id="4ef90-149">**使用自訂環境** 以使用自訂的環境。</span><span class="sxs-lookup"><span data-stu-id="4ef90-149">**Use a custom environment** to use a custom environment.</span></span> <span data-ttu-id="4ef90-150">從清單中選擇您要使用的環境。</span><span class="sxs-lookup"><span data-stu-id="4ef90-150">Choose the environment that you want to use from the list.</span></span> <span data-ttu-id="4ef90-151">您必須在此環境中安裝 *Project Cortex 的 AI Builder* 應用程式，並在建立表單處理模型之前先配置 AI Builder 點數。</span><span class="sxs-lookup"><span data-stu-id="4ef90-151">You must install the *AI Builder for Project Cortex* app in this environment and allocate AI Builder credits to it before you can create form processing models.</span></span>

    <span data-ttu-id="4ef90-152">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-152">Click **Next**.</span></span>

5. <span data-ttu-id="4ef90-153">在 **[建立內容中心]** 頁面上，您可以建立 SharePoint 內容中心網站，讓使用者建立及管理文件理解模型。</span><span class="sxs-lookup"><span data-stu-id="4ef90-153">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="4ef90-154">在 **[網站名稱]** 中，輸入您要給予內容中心網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="4ef90-154">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="4ef90-155">**[網站位址]** 會根據您為網站名稱所選取的內容，顯示網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="4ef90-155">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="4ef90-156">如果您想要變更，請按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-156">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="4ef90-157">![建立內容中心](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="4ef90-157">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="4ef90-158">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-158">Select **Next**.</span></span>

6. <span data-ttu-id="4ef90-159">在 **[檢閱並完成]** 頁面上，您可以查看您選取的設定，並選擇進行變更。</span><span class="sxs-lookup"><span data-stu-id="4ef90-159">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="4ef90-160">如果您對您的選擇感到滿意，請選取 **[啟用]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-160">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="4ef90-161">在 [確認] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-161">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="4ef90-162">您將會回到 **[自動化內容瞭解]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="4ef90-162">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="4ef90-163">在此頁面上，您可以選取 **[管理]**，以對設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="4ef90-163">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="4ef90-164">指派授權</span><span class="sxs-lookup"><span data-stu-id="4ef90-164">Assign licenses</span></span>

<span data-ttu-id="4ef90-165">一旦您設定 SharePoint Syntex 之後，您必須為將使用任何 SharePoint Syntex 功能的使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="4ef90-165">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="4ef90-166">若要指派授權：</span><span class="sxs-lookup"><span data-stu-id="4ef90-166">To assign licenses:</span></span>

1. <span data-ttu-id="4ef90-167">在 Microsoft 365 系統管理中心中，在 **[使用者]** 底下，按一下 **[作用中使用者]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-167">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="4ef90-168">選取您要授權的使用者，然後選擇 **[管理產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-168">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="4ef90-169">從下拉式功能表中選擇 **[應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-169">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="4ef90-170">選取 **[顯示 SharePoint Syntex 的應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-170">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="4ef90-171">在 **[應用程式]** 下，確定選取 **[Common Data Service for SharePoint Syntex]**、**[SharePoint Syntex]** 和 **[SharePoint Syntex - SPO 類型]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-171">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4ef90-172">![Microsoft 365 系統管理中心中的 SharePoint Syntex 授權](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="4ef90-172">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="4ef90-173">按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="4ef90-173">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ef90-174">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ef90-174">See also</span></span>

[<span data-ttu-id="4ef90-175">表單處理模型概觀</span><span class="sxs-lookup"><span data-stu-id="4ef90-175">Overview of the form processing model</span></span>](/ai-builder/form-processing-model-overview)

[<span data-ttu-id="4ef90-176">逐步執行：如何建立文件理解模型 (影片)</span><span class="sxs-lookup"><span data-stu-id="4ef90-176">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

[<span data-ttu-id="4ef90-177">在 Power Platform 系統管理中心建立和管理環境</span><span class="sxs-lookup"><span data-stu-id="4ef90-177">Create and manage environments in the Power Platform admin center</span></span>](/power-platform/admin/create-environment)
