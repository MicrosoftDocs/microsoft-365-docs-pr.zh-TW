---
title: 設定 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 設定專案 Cortex 中的內容瞭解
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294840"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="05de7-103">設定 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="05de7-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="05de7-104">系統管理員可以使用 Microsoft 365 系統管理中心來設定和 Microsoft SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="05de7-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="05de7-105">開始之前，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="05de7-105">Consider the following before you start:</span></span>

- <span data-ttu-id="05de7-106">您將在哪些 SharePoint 網站上啟用表單處理？</span><span class="sxs-lookup"><span data-stu-id="05de7-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="05de7-107">所有的網站、部分或選取的網站？</span><span class="sxs-lookup"><span data-stu-id="05de7-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="05de7-108">您的內容中心及主要網站管理員的名稱為何？</span><span class="sxs-lookup"><span data-stu-id="05de7-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="05de7-109">您可以在 Microsoft 365 系統管理中心中的初始設定之後變更您的設定。</span><span class="sxs-lookup"><span data-stu-id="05de7-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="05de7-110">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="05de7-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="05de7-111">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="05de7-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="05de7-112">設定之前，請務必規劃如何在環境中設定和設定內容瞭解的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="05de7-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="05de7-113">例如，您需要考慮下列名稱：</span><span class="sxs-lookup"><span data-stu-id="05de7-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="05de7-114">您想要啟用表單處理的 SharePoint 網站-所有的網站、部分或選取的網站</span><span class="sxs-lookup"><span data-stu-id="05de7-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="05de7-115">內容中心及主要網站管理員的名稱</span><span class="sxs-lookup"><span data-stu-id="05de7-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="05de7-116">需求</span><span class="sxs-lookup"><span data-stu-id="05de7-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="05de7-117">您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心和設定內容瞭解。</span><span class="sxs-lookup"><span data-stu-id="05de7-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="05de7-118">身為系統管理員，您也可以在安裝程式完成之後，在 [Microsoft 365 系統管理中心] 的 [內容瞭解管理] 設定中隨時變更選取的設定。</span><span class="sxs-lookup"><span data-stu-id="05de7-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="05de7-119">若要設定 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="05de7-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="05de7-120">在 Microsoft 365 系統管理中心中，選取 [ **安裝**]，然後查看 [ **組織知識** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="05de7-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="05de7-121">在 [ **組織知識** ] 區段中，選取 [ **自動瞭解內容**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![組織知識設定頁面](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="05de7-123">在 [ **自動化 SharePoint Syntex** ] 頁面上，按一下 [ **開始** 使用] 以逐步執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="05de7-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![開始安裝程式](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="05de7-125">在 [開啟圖像標記] 頁面上，選擇是否要允許 [影像標記](image-tagging.md)。</span><span class="sxs-lookup"><span data-stu-id="05de7-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![影像標記選項的螢幕擷取畫面](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="05de7-127">在 [ **設定表單處理** ] 頁面上，您可以選擇是否要讓使用者能夠使用 AI 建立器在特定 SharePoint 文件庫中建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="05de7-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="05de7-128">[文件庫] 功能區中會提供功能表選項，以在啟用該模型的 SharePoint 文件庫中 **建立表單處理模型** 。</span><span class="sxs-lookup"><span data-stu-id="05de7-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="05de7-129">**若要 SharePoint 文件庫應該顯示以建立表單處理模型的選項**，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="05de7-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="05de7-130">**所有 SharePoint 文件庫** ，讓組織中的所有 SharePoint 文件庫皆可使用。</span><span class="sxs-lookup"><span data-stu-id="05de7-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="05de7-131">**僅限選取的網站中**的文件庫，然後選取您要讓其可供使用的網站。</span><span class="sxs-lookup"><span data-stu-id="05de7-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![設定表單處理](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="05de7-133">在 SharePoint 文件庫上啟用此設定不會影響已套用至文件庫的現有模型，也不會影響將檔理解模型套用至文件庫的功能。</span><span class="sxs-lookup"><span data-stu-id="05de7-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="05de7-134">在 [ **建立內容中心** ] 頁面上，您可以建立 SharePoint 內容中心網站，您的使用者可以在該網站上建立及管理檔理解模型。</span><span class="sxs-lookup"><span data-stu-id="05de7-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="05de7-135">a.</span><span class="sxs-lookup"><span data-stu-id="05de7-135">a.</span></span> <span data-ttu-id="05de7-136">在 [ **網站名稱**] 中，輸入您要提供給內容中心網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="05de7-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="05de7-137">b.</span><span class="sxs-lookup"><span data-stu-id="05de7-137">b.</span></span> <span data-ttu-id="05de7-138">**網站位址**會根據您為網站名稱所選取的內容，顯示網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="05de7-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="05de7-139">若要變更，請按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-139">If you want to change it, click **Edit**.</span></span></br>

      ![建立內容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="05de7-141">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05de7-141">Select **Next**.</span></span>

7. <span data-ttu-id="05de7-142">在 [ **檢查和完成]** 頁面上，您可以查看選取的設定，並選擇進行變更。</span><span class="sxs-lookup"><span data-stu-id="05de7-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="05de7-143">如果您對選擇滿意，請選取 [ **啟動**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="05de7-144">在 [確認] 頁面上，按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="05de7-145">您將會傳回 [ **自動化內容瞭解** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="05de7-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="05de7-146">您可以從這個頁面，選取 [ **管理** ]，對您的設定設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="05de7-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="05de7-147">指派授權</span><span class="sxs-lookup"><span data-stu-id="05de7-147">Assign licenses</span></span>

<span data-ttu-id="05de7-148">在您設定 SharePoint Syntex 後，您必須指派授權給將要使用表單處理及檔理解功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="05de7-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="05de7-149">若要指派授權：</span><span class="sxs-lookup"><span data-stu-id="05de7-149">To assign licenses:</span></span>

1. <span data-ttu-id="05de7-150">在 Microsoft 365 系統管理中心的 [ **使用者**] 下，按一下 [作用中 **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="05de7-151">選取您要授權的使用者，然後按一下 [ **管理產品授權**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="05de7-152">選取 [ **指派更多**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="05de7-153">選取 [ **智慧內容服務**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="05de7-154">在 [**應用程式**] 底下，請確定已同時選取 [智慧內容服務] 及 [**智慧內容**服務]**的一般資料服務**。</span><span class="sxs-lookup"><span data-stu-id="05de7-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![在 Microsoft 365 系統管理中心中 SharePoint Syntex 授權](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="05de7-156">按一下 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05de7-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="05de7-157">AI 產生器學分</span><span class="sxs-lookup"><span data-stu-id="05de7-157">AI Builder credits</span></span>

<span data-ttu-id="05de7-158">如果您的組織中有300或以上 SharePoint Syntex 授權 SharePoint Syntex，您將會被指派 1000000 AI 產生器信用。</span><span class="sxs-lookup"><span data-stu-id="05de7-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="05de7-159">如果您的授權少於300個，您必須購買 AI 產生器信用，才能使用表單處理。</span><span class="sxs-lookup"><span data-stu-id="05de7-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="05de7-160">您可以使用 Ai 產生器 [計算機](https://powerapps.microsoft.com/ai-builder-calculator)估計最適合您的 ai 產生器容量。</span><span class="sxs-lookup"><span data-stu-id="05de7-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

1. <span data-ttu-id="05de7-161">請移至 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/resources/capacity) ，檢查您的學分和使用方式。</span><span class="sxs-lookup"><span data-stu-id="05de7-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05de7-162">在 SharePoint 文件庫上啟用此設定，不會影響已套用至程式庫的現有模型，也不會影響將檔理解模型套用至文件庫的功能。</span><span class="sxs-lookup"><span data-stu-id="05de7-162">Enable this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
2. <span data-ttu-id="05de7-163">在 [ **建立內容中心** ] 頁面中，您可以建立 SharePoint 內容中心網站，讓使用者可以建立及管理檔理解模型。</span><span class="sxs-lookup"><span data-stu-id="05de7-163">From the **Create Content Center** page, you can create a SharePoint content center site for which users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="05de7-164">a.</span><span class="sxs-lookup"><span data-stu-id="05de7-164">a.</span></span> <span data-ttu-id="05de7-165">在 [ **網站名稱**] 中，輸入您要用於內容中心網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="05de7-165">For **Site name**, type the name you want for the content center site.</span></span></br>
    <span data-ttu-id="05de7-166">b.</span><span class="sxs-lookup"><span data-stu-id="05de7-166">b.</span></span> <span data-ttu-id="05de7-167">**網站位址**會根據網站名稱顯示網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="05de7-167">The **Site address** shows the URL for your site, based on the site name.</span></span></br>

    > [!NOTE] 
    > <span data-ttu-id="05de7-168">雖然您可以選擇任何支援的語言，但內容瞭解模型只能為英文建立。</span><span class="sxs-lookup"><span data-stu-id="05de7-168">While you can select any supported language, content understanding models can only be created for English.</span></span></br>

      ![建立內容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

3. <span data-ttu-id="05de7-170">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05de7-170">Select **Next**.</span></span>

4. <span data-ttu-id="05de7-171">在 [ **完成與複查]** 頁面上，查看您選取的設定，然後選擇進行變更。</span><span class="sxs-lookup"><span data-stu-id="05de7-171">On the **Finish and review** page, look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="05de7-172">如果您對選擇滿意，請選取 [ **啟動**]。</span><span class="sxs-lookup"><span data-stu-id="05de7-172">If you are satisfied with your selections, select **Activate**.</span></span>

5. <span data-ttu-id="05de7-173">隨即會顯示 [ **內容瞭解** 已啟動] 頁面，確認系統已新增您的表單處理喜好設定，並建立內容中心網站。</span><span class="sxs-lookup"><span data-stu-id="05de7-173">The **Content understanding activated** page displays, confirming the system added your form processing preferences and created the Content Center site.</span></span> <span data-ttu-id="05de7-174">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="05de7-174">Select **Done**.</span></span>

6. <span data-ttu-id="05de7-175">您將會傳回 [ **自動化內容瞭解** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="05de7-175">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="05de7-176">您可以從這個頁面，選取 [ **管理** ]，對您的設定設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="05de7-176">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="05de7-177">請參閱</span><span class="sxs-lookup"><span data-stu-id="05de7-177">See also</span></span>

[<span data-ttu-id="05de7-178">表單處理模型概述</span><span class="sxs-lookup"><span data-stu-id="05de7-178">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="05de7-179">逐步：如何建立檔理解模型 (影片) </span><span class="sxs-lookup"><span data-stu-id="05de7-179">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

