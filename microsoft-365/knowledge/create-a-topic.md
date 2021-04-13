---
title: 在 Microsoft Viva 主題中建立新的主題
description: 如何在 Microsoft Viva 主題中建立新的主題。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7d1dc1af6e845ccfe2fb0e8f5701a2cd3018c308
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687528"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a><span data-ttu-id="6cb7a-103">在 Microsoft Viva 主題中建立新的主題</span><span class="sxs-lookup"><span data-stu-id="6cb7a-103">Create a new topic in Microsoft Viva Topics</span></span>

<span data-ttu-id="6cb7a-104">在 Viva 主題中，您可以建立新的主題如果沒有透過索引探索，或是 AI 技術沒有找到足夠的證據來建立主題。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-104">In Viva Topics, you can create a new topic if one is not discovered through indexing or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

> [!Note] 
> <span data-ttu-id="6cb7a-105">[！附注] 透過 AI 收集的主題中的資訊是 [安全修整](topic-experiences-security-trimming.md)的，請注意，所有具有查看主題許可權的使用者皆可看到手動建立主題中的主題描述和人員資訊。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-105">While information in a topic that is gathered by AI is [security trimmed](topic-experiences-security-trimming.md), note that topic description and people information in a manually created topic is visible to all users who have permissions to view the topic.</span></span> 


## <a name="requirements"></a><span data-ttu-id="6cb7a-106">需求</span><span class="sxs-lookup"><span data-stu-id="6cb7a-106">Requirements</span></span>

<span data-ttu-id="6cb7a-107">若要建立新的主題，您必須：</span><span class="sxs-lookup"><span data-stu-id="6cb7a-107">To create a new topic, you need to:</span></span>
- <span data-ttu-id="6cb7a-108">具有 Viva 主題授權。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-108">Have a Viva Topics license.</span></span>
- <span data-ttu-id="6cb7a-109">具有 [**可建立或編輯主題的人員**](./topic-experiences-user-permissions.md)許可權。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-109">Have permissions to [**Who can create or edit topics**](./topic-experiences-user-permissions.md).</span></span> <span data-ttu-id="6cb7a-110">知識系統管理員可以在 Viva 主題主題許可權設定中，將此許可權授與使用者。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-110">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

> [!Note] 
> <span data-ttu-id="6cb7a-111">有權管理主題中心主題的使用者 (知識管理員) 已具備建立及編輯主題的許可權。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-111">Users who have permission to manage topics in the topic center (knowledge managers) already have permissions to create and edit topics.</span></span>

## <a name="to-create-a-topic"></a><span data-ttu-id="6cb7a-112">若要建立主題</span><span class="sxs-lookup"><span data-stu-id="6cb7a-112">To create a topic</span></span>

<span data-ttu-id="6cb7a-113">您可以從兩個位置建立新的主題：</span><span class="sxs-lookup"><span data-stu-id="6cb7a-113">You can create a new topic from two locations:</span></span>

- <span data-ttu-id="6cb7a-114">主題中心首頁：具有 **可建立或編輯主題** 許可權 (參與者的任何授權使用者) 可以從主題中心建立新的主題，方法是選取 [ **新增** ] 功能表，然後選取 [ **主題] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-114">Topic center home page: Any licensed user with the **Who can create or edit topics** permission (contributors) can create a new topic from the topic center by selecting the **New** menu and select **Topic page**.</span></span> 

    ![主題中心的新主題](../media/knowledge-management/new-topic.png)  

- <span data-ttu-id="6cb7a-116">「管理主題」頁面：任何有 **權管理主題** 許可權的授權使用者 (知識管理員) 可以從主題中心的 [管理主題] 頁面，選取 [ **新增主題] 頁面**，以建立新的主題。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-116">Manage topics page:  Any licensed user who has **Who can manage topics** permission (knowledge managers) can create a new topic from the Manage topics page in the Topic Center by selecting **New topic page**.</span></span> 

    ![管理主題中的新主題](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a><span data-ttu-id="6cb7a-118">若要建立新的主題：</span><span class="sxs-lookup"><span data-stu-id="6cb7a-118">To create a new topic:</span></span>

1. <span data-ttu-id="6cb7a-119">從 [管理主題] 頁面上的功能區中，選取用來建立新主題頁面的選項。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-119">Select the option to create a new Topic Page from the ribbon on the Manage Topics page.</span></span>

2.  <span data-ttu-id="6cb7a-120">在 [ **名稱這個主題** ] 區段中，輸入新主題的名稱。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-120">In the **Name this topic** section, type the name of the new topic.</span></span>

    ![名稱本主題](../media/knowledge-management/k-new-topic-page.png)  

3. <span data-ttu-id="6cb7a-122">在 [ **替代名稱** ] 區段中，輸入該主題可能參考的任何其他名稱。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-122">In the **Alternate Names** section, type any other names that the topic might be referred to.</span></span> 

    ![替代名稱](../media/knowledge-management/alt-names.png)  

4. <span data-ttu-id="6cb7a-124">在 [ **描述** ] 區段中，輸入一些描述主題的句子。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-124">In the **Description** section, type a couple of sentences that describe the topic.</span></span> 

    ![主題的描述](../media/knowledge-management/description.png)

4. <span data-ttu-id="6cb7a-126">在 [ **固定人員** ] 區段中，您可以「固定」人員，將其顯示為與主題的連線 (例如，連接資源的擁有者) 。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-126">In the **Pinned people** section, you can "pin" a person to show them as having a connection to the topic (for example, an owner of a connected resource).</span></span> <span data-ttu-id="6cb7a-127">請先在 [ **新增使用者** ] 方塊中輸入他們的名稱或電子郵件地址，然後從搜尋結果中選取您要新增的使用者。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-127">Begin by typing their name or email address in the **add a new user** box, and then select the user you want to add from the search results.</span></span> <span data-ttu-id="6cb7a-128">您也可以從使用者卡片上選取 [ **從清單移除** ] 圖示來「解除固定」。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-128">You can also "unpin" them by selecting the **Remove from list** icon on the user card.</span></span> <span data-ttu-id="6cb7a-129">您也可以將人員拖曳到清單中的另一個位置。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-129">You can also drag the person to another place in the list.</span></span>
 
    ![固定人員](../media/knowledge-management/pinned-people.png)

5. <span data-ttu-id="6cb7a-131">在 [ **附加的檔案與頁面** ] 區段中，您可以新增或「固定」與主題相關聯的檔案或 SharePoint 網站] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-131">In the **Pinned files and pages** section, you can add or "pin" a file or SharePoint site page that is associated to the topic.</span></span>

   ![釘選的檔案和頁面](../media/knowledge-management/pinned-files-and-pages.png)
 
    <span data-ttu-id="6cb7a-133">若要新增檔案，請選取 [ **新增**]，選取您經常或已追蹤網站的 SharePoint 網站，然後從網站的文件庫中選取檔案。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-133">To add a new file, select **Add**, select the SharePoint site from your Frequent or Followed sites, and then select the file from the site's document library.</span></span>

    <span data-ttu-id="6cb7a-134">您也可以透過提供 URL，使用 [ **發件** 人] 中的 [連結] 選項來新增檔或頁面。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-134">You can also use the **From a link** option to add a file or page by providing the URL.</span></span> 

    > [!Note] 
    > <span data-ttu-id="6cb7a-135">您新增的檔案和頁面必須位於相同的 Microsoft 365 租使用者內。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-135">Files and pages that you add must be located within the same Microsoft 365 tenant.</span></span> <span data-ttu-id="6cb7a-136">如果您想要在主題中新增外部資源的連結，您可以透過步驟8中的 canvas 圖示加以新增。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-136">If you want to add a link to an external resource in the topic, you can add it through the canvas icon in step 8.</span></span>


6.  <span data-ttu-id="6cb7a-137">[ **相關網站** ] 區段會顯示網站，其中包含主題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-137">The **Related sites** section shows sites that have information about the topic.</span></span> 

    ![相關網站區段](../media/knowledge-management/related-sites.png)

    <span data-ttu-id="6cb7a-139">您可以選取 [ **新增** ]，然後搜尋網站，或從您經常或最近的網站清單中進行選取，以新增相關的網站。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-139">You can add a related site by selecting **Add** and then either searching for the site, or selecting it from your list of Frequent or Recent sites.</span></span>
    
    ![選取網站](../media/knowledge-management/sites.png)

7. <span data-ttu-id="6cb7a-141">[ **相關主題** ] 區段會顯示主題之間存在的連線。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-141">The **Related topics** section shows connections that exist between topics.</span></span> <span data-ttu-id="6cb7a-142">您可以選取 [ **連線至相關主題]** 按鈕，然後輸入相關主題的名稱，然後再從搜尋結果中進行選取，以新增與其他主題的連接。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-142">You can add a connection to a different topic by selecting the **Connect to a related topic** button, and then typing the name of the related topic, and selecting it from the search results.</span></span> 

   ![相關主題](../media/knowledge-management/related-topic.png)  

    <span data-ttu-id="6cb7a-144">您可以接著提供相關主題的相關描述，然後選取 [ **更新**]。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-144">You can then give a description of how the topics are related, and select **Update**.</span></span>

   ![相關主題描述](../media/knowledge-management/related-topics-update.png) 

   <span data-ttu-id="6cb7a-146">您新增的相關主題會顯示為連線的主題。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-146">The related topic you added will display as a connected topic.</span></span>

   ![連線的相關主題](../media/knowledge-management/related-topics-final.png) 

   <span data-ttu-id="6cb7a-148">若要移除相關主題，請選取您要移除的主題，然後選取 **移除主題** 圖示。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-148">To remove a related topic, select the topic you want to remove, then select the **Remove topic** icon.</span></span>
 
   ![移除相關主題](../media/knowledge-management/remove-related.png)  

   <span data-ttu-id="6cb7a-150">然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-150">Then select **Remove**.</span></span>

   ![確認移除](../media/knowledge-management/remove-related-confirm.png) 

8. <span data-ttu-id="6cb7a-152">您也可以選取 [畫布] 圖示，將靜態專案新增至頁面 (例如文字、圖像或連結) ，您可以在簡短描述下方找到該圖示。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-152">You can also add static items to the page (such as text, images, or links) by selecting the canvas icon, which you can find below the short description.</span></span> <span data-ttu-id="6cb7a-153">選取它會開啟 SharePoint 工具箱，您可以從中選擇要新增至頁面的專案。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-153">Selecting it will open the SharePoint toolbox from which you can choose the item you want to add to the page.</span></span>

   ![畫布圖示](../media/knowledge-management/webpart-library.png) 

9. <span data-ttu-id="6cb7a-155">選取 [ **發佈** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-155">Select **Publish** to save your changes.</span></span> 

<span data-ttu-id="6cb7a-156">在您發佈頁面後，主題名稱、替代名稱、描述及固定人員將會向所有查看該主題的授權使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-156">After you publish the page, the topic name, alternate name, description, and pinned people will display to all licensed users who view the topic.</span></span> <span data-ttu-id="6cb7a-157">只有當檢視器具有專案的 Office 365 許可權時，特定檔案、頁面和網站才會出現在 [主題] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="6cb7a-157">Specific files, pages, and sites will only appear on the topic page if the viewer has Office 365 permissions to the item.</span></span> 



## <a name="see-also"></a><span data-ttu-id="6cb7a-158">請參閱</span><span class="sxs-lookup"><span data-stu-id="6cb7a-158">See also</span></span>



