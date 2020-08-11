---
title: '設定內容瞭解 (預覽)  '
description: 如何設定專案 Cortex。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612699"
---
# <a name="set-up-content-understanding-preview"></a><span data-ttu-id="32bb9-103">設定內容瞭解 (預覽) </span><span class="sxs-lookup"><span data-stu-id="32bb9-103">Set up content understanding (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="32bb9-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="32bb9-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="32bb9-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="32bb9-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="32bb9-106">系統管理員可以使用 Microsoft 365 系統管理中心來設定和設定內容瞭解。</span><span class="sxs-lookup"><span data-stu-id="32bb9-106">Admins can use the Microsoft 365 admin center to set up and configure content understanding.</span></span> 

<span data-ttu-id="32bb9-107">設定之前，請務必規劃如何在環境中設定和設定內容瞭解的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="32bb9-107">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="32bb9-108">例如，您將需要考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="32bb9-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="32bb9-109">您將在哪些 SharePoint 網站上啟用表單處理？</span><span class="sxs-lookup"><span data-stu-id="32bb9-109">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="32bb9-110">所有的網站、部分或選取的網站？</span><span class="sxs-lookup"><span data-stu-id="32bb9-110">All of them, some, or select sites?</span></span>
- <span data-ttu-id="32bb9-111">內容中心的名稱，以及主要網站管理員的名稱。</span><span class="sxs-lookup"><span data-stu-id="32bb9-111">Name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="32bb9-112">系統管理員也可以在安裝程式完成之後，透過 Microsoft 365 系統管理中心的內容瞭解管理設定，對選取的設定進行變更。</span><span class="sxs-lookup"><span data-stu-id="32bb9-112">An admin can also make changes to your selected settings anytime after setup through the content understanding management settings in the Microsoft 365 admin center.</span></span>


## <a name="requirements"></a><span data-ttu-id="32bb9-113">需求</span><span class="sxs-lookup"><span data-stu-id="32bb9-113">Requirements</span></span> 
<span data-ttu-id="32bb9-114">您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心和設定內容瞭解。</span><span class="sxs-lookup"><span data-stu-id="32bb9-114">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>


## <a name="to-set-up-content-understanding"></a><span data-ttu-id="32bb9-115">設定內容瞭解</span><span class="sxs-lookup"><span data-stu-id="32bb9-115">To set up content understanding</span></span>

1. <span data-ttu-id="32bb9-116">在 Microsoft 365 系統管理中心中，選取 [**安裝**]，然後查看 [**組織知識**] 區段。</span><span class="sxs-lookup"><span data-stu-id="32bb9-116">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>
2. <span data-ttu-id="32bb9-117">在 [**組織知識**] 區段中，選取 [**自動瞭解內容**]。</span><span class="sxs-lookup"><span data-stu-id="32bb9-117">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![組織知識設定頁面](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="32bb9-119">在 [**自動化內容瞭解**] 頁面上，按一下 [**快速入門**] 以逐步引導您完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="32bb9-119">On the **Automate content understanding** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![開始安裝程式](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. <span data-ttu-id="32bb9-121">在 [**設定表單處理**] 頁面上，您可以選擇是否要讓使用者能夠使用 AI 建立器在特定 SharePoint 文件庫中建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="32bb9-121">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="32bb9-122">[文件庫] 功能區中會提供功能表選項，以在啟用該模型的 SharePoint 文件庫中**建立表單處理模型**。</span><span class="sxs-lookup"><span data-stu-id="32bb9-122">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="32bb9-123">**若要 SharePoint 文件庫應該顯示以建立表單處理模型的選項**，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="32bb9-123">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
    - <span data-ttu-id="32bb9-124">**所有 SharePoint 文件庫**，使其可供您租使用者中的所有 SharePoint 庫使用。</span><span class="sxs-lookup"><span data-stu-id="32bb9-124">**All SharePoint libraries** to make it available to all SharePoint libraries in your tenant.</span></span></br>
    - <span data-ttu-id="32bb9-125">**僅限選取的網站中**的文件庫，然後選取您要讓其可供使用的網站。</span><span class="sxs-lookup"><span data-stu-id="32bb9-125">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>
    - <span data-ttu-id="32bb9-126">如果您目前不想讓任何網站使用**SharePoint 程式庫** (您可以在 setup) 之後變更此設定。</span><span class="sxs-lookup"><span data-stu-id="32bb9-126">**No SharePoint libraries** if you currently don't want to make it available to any sites (you can change this after setup).</span></span>
</br>

   <span data-ttu-id="32bb9-127">![設定表單處理](../media/content-understanding/admin-configforms.png)
</span><span class="sxs-lookup"><span data-stu-id="32bb9-127">![Configure form processing](../media/content-understanding/admin-configforms.png)
</span></span></br>

   > [!Note]
   > <span data-ttu-id="32bb9-128">在 SharePoint 文件庫上啟用此設定不會影響已套用至文件庫的現有模型，也不會影響將檔理解模型套用至文件庫的功能。</span><span class="sxs-lookup"><span data-stu-id="32bb9-128">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 

    
5. <span data-ttu-id="32bb9-129">在 [**建立內容中心**] 頁面上，您可以建立 SharePoint 內容中心網站，您的使用者可以在該網站上建立及管理檔理解模型。</span><span class="sxs-lookup"><span data-stu-id="32bb9-129">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="32bb9-130">a.</span><span class="sxs-lookup"><span data-stu-id="32bb9-130">a.</span></span> <span data-ttu-id="32bb9-131">在 [**網站名稱**] 中，輸入您要提供給內容中心網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="32bb9-131">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="32bb9-132">b.</span><span class="sxs-lookup"><span data-stu-id="32bb9-132">b.</span></span> <span data-ttu-id="32bb9-133">**網站位址**會根據您為網站名稱所選取的內容，顯示網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="32bb9-133">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span></br>

    > [!Note] 
    > <span data-ttu-id="32bb9-134">您可以選擇任何支援的語言，請注意，僅能為英文建立內容瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="32bb9-134">While you can select any supported language, note that content understanding models can only be created for English.</span></span></br>

      ![建立內容中心](../media/content-understanding/admin-cu-create-cc.png)</br>


    <span data-ttu-id="32bb9-136">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="32bb9-136">Select **Next**.</span></span>
6. <span data-ttu-id="32bb9-137">在 [**完成與複查]** 頁面上，您可以查看選取的設定，並選擇進行變更。</span><span class="sxs-lookup"><span data-stu-id="32bb9-137">On the **Finish and review** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="32bb9-138">如果您對選擇滿意，請選取 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="32bb9-138">If you are satisfied with your selections, select **Activate**.</span></span>



7. <span data-ttu-id="32bb9-139">隨即會顯示 [**內容瞭解**已啟動] 頁面，確認系統已新增您的表單處理喜好設定，以及建立內容中心網站。</span><span class="sxs-lookup"><span data-stu-id="32bb9-139">The **Content understanding activated** page will display, confirming that the system has added your form processing preferences and creating the Content Center site.</span></span> <span data-ttu-id="32bb9-140">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="32bb9-140">Select **Done**.</span></span>

8. <span data-ttu-id="32bb9-141">您將會傳回 [**自動化內容瞭解**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="32bb9-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="32bb9-142">您可以從這個頁面，選取 [**管理**]，對您的設定設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="32bb9-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="32bb9-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="32bb9-143">See also</span></span>



  






