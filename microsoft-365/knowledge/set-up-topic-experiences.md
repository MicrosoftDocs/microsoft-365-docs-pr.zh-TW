---
title: 設定 Microsoft Viva 主題
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 瞭解如何設定 Microsoft Viva 主題
ms.openlocfilehash: 6bd0d3eca653ae44e46b410ef3ac55fe11629a6b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150497"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="5909f-103">設定 Microsoft Viva 主題</span><span class="sxs-lookup"><span data-stu-id="5909f-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="5909f-104">您可以使用 Microsoft 365 系統管理中心來設定及設定 [主題](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5909f-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="5909f-105">在您的環境中規劃設定和設定主題的最佳方式是很重要的。</span><span class="sxs-lookup"><span data-stu-id="5909f-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="5909f-106">在您開始本文中的程式之前，請務必閱讀 [Microsoft Viva 主題的計畫](plan-topic-experiences.md) 。</span><span class="sxs-lookup"><span data-stu-id="5909f-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="5909f-107">您必須 [訂閱 Viva 主題](https://www.microsoft.com/microsoft-viva/topics) ，以及全域管理員或 SharePoint 管理員，才能存取 Microsoft 365 系統管理中心及設定相關主題。</span><span class="sxs-lookup"><span data-stu-id="5909f-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5909f-108">影片示範</span><span class="sxs-lookup"><span data-stu-id="5909f-108">Video demonstration</span></span>

<span data-ttu-id="5909f-109">這段影片顯示在 Microsoft 365 中設定主題的程式。</span><span class="sxs-lookup"><span data-stu-id="5909f-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="5909f-110">設定 [主題]</span><span class="sxs-lookup"><span data-stu-id="5909f-110">Set up Topics</span></span>

<span data-ttu-id="5909f-111">設定主題</span><span class="sxs-lookup"><span data-stu-id="5909f-111">To set up Topics</span></span>

1. <span data-ttu-id="5909f-112">在 [Microsoft 365 系統管理中心](https://admin.microsoft.com)中，選取 [ **安裝**]，然後查看 [檔案 **與內容** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="5909f-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="5909f-113">在 [檔案 **與內容** ] 區段中，按一下 **[將人員連線到知識]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![將人員連線至知識](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="5909f-115">在 [連線 **人員至知識]** 頁面上，按一下 [ **開始** ]，逐步引導您完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="5909f-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![入門](../media/k-get-started.png) 

4. <span data-ttu-id="5909f-117">在 [ **選擇 Viva 主題如何尋找主題** ] 頁面上，您會設定主題探索。</span><span class="sxs-lookup"><span data-stu-id="5909f-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="5909f-118">在 [ **選取 SharePoint 主題來源** ] 區段中，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="5909f-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="5909f-119">請選擇：</span><span class="sxs-lookup"><span data-stu-id="5909f-119">Choose from:</span></span>
    - <span data-ttu-id="5909f-120">**所有網站**：您組織中的所有 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="5909f-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="5909f-121">這包括目前和未來的網站。</span><span class="sxs-lookup"><span data-stu-id="5909f-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="5909f-122">**全部，除了選取的網站以外**：請輸入您要排除的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="5909f-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="5909f-123">您也可以上傳想要從探索中選擇的網站清單。</span><span class="sxs-lookup"><span data-stu-id="5909f-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="5909f-124">在未來建立的網站將會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="5909f-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="5909f-125">**僅限選取的網站**：輸入您要包含的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="5909f-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="5909f-126">您也可以上傳網站清單。</span><span class="sxs-lookup"><span data-stu-id="5909f-126">You can also upload a list of sites.</span></span> <span data-ttu-id="5909f-127">未來建立的網站不會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="5909f-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="5909f-128">**無網站**：不包含任何 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="5909f-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![選擇尋找主題的方式](../media/ksetup1.png) 
   
5. <span data-ttu-id="5909f-130">在 [以 **名稱排除主題** ] 區段中，您可以新增要從主題探索中排除的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="5909f-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="5909f-131">使用此設定可防止敏感資訊包含為主題。</span><span class="sxs-lookup"><span data-stu-id="5909f-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="5909f-132">選項包括：</span><span class="sxs-lookup"><span data-stu-id="5909f-132">The options are:</span></span>
    - <span data-ttu-id="5909f-133">**不排除任何主題**</span><span class="sxs-lookup"><span data-stu-id="5909f-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="5909f-134">**依名稱排除主題**</span><span class="sxs-lookup"><span data-stu-id="5909f-134">**Exclude topics by name**</span></span>

    ![排除主題](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="5909f-136"> (知識管理員也可以排除探索之後主題中心的主題。 ) </span><span class="sxs-lookup"><span data-stu-id="5909f-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="5909f-137">操作方法：依名稱排除主題</span><span class="sxs-lookup"><span data-stu-id="5909f-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="5909f-138">如果您需要排除相關主題，請在選取 [ **依名稱排除主題**] 之後，下載 .csv 範本，並將其更新為您想要從探索結果中排除的主題清單。</span><span class="sxs-lookup"><span data-stu-id="5909f-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![排除 CSV 範本中的主題](../media/exclude-topics-csv.png) 

    <span data-ttu-id="5909f-140">在 CSV 範本中，輸入您要排除之主題的下列相關資訊：</span><span class="sxs-lookup"><span data-stu-id="5909f-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="5909f-141">**名稱**：輸入您要排除的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="5909f-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="5909f-142">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="5909f-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="5909f-143">完全相符：您可以包含確切的名稱或縮寫 (例如， *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="5909f-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="5909f-144">部分相符：您可以排除包含特定單字的所有主題。</span><span class="sxs-lookup"><span data-stu-id="5909f-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="5909f-145">例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形*、 *等離子弧線焊接* 或 *訓練弧*。請注意，它不會排除包含文字（如 *架構*）一部分的主題。</span><span class="sxs-lookup"><span data-stu-id="5909f-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="5909f-146">**代表 (選用)**：若要排除縮寫，請輸入縮寫所代表的字。</span><span class="sxs-lookup"><span data-stu-id="5909f-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="5909f-147">**MatchType-Exact/partial**：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。</span><span class="sxs-lookup"><span data-stu-id="5909f-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="5909f-148">完成並儲存 .csv 檔案之後，請選取 **[流覽]** 以找出並選取。</span><span class="sxs-lookup"><span data-stu-id="5909f-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="5909f-149">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-149">Select **Next**.</span></span>

6. <span data-ttu-id="5909f-150">在 [ **誰可以看到主題及其可以查看的位置** ] 頁面上，您會設定主題可見度。</span><span class="sxs-lookup"><span data-stu-id="5909f-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="5909f-151">在 [ **可以查看主題** ] 設定中，您可以選擇誰可以存取主題詳細資料，例如高亮主題、主題卡片、搜尋中的主題答案和主題頁面。</span><span class="sxs-lookup"><span data-stu-id="5909f-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="5909f-152">您可以選取：</span><span class="sxs-lookup"><span data-stu-id="5909f-152">You can select:</span></span>
    - <span data-ttu-id="5909f-153">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="5909f-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="5909f-154">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="5909f-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="5909f-155">**沒人**</span><span class="sxs-lookup"><span data-stu-id="5909f-155">**No one**</span></span>

    ![誰可以查看主題](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="5909f-157">雖然此設定可讓您選取組織中的任何使用者，但只有具有指派授權之使用者的使用者可以查看主題。</span><span class="sxs-lookup"><span data-stu-id="5909f-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="5909f-158">在 [ **主題管理的許可權** ] 頁面中，您可以選擇誰將可以建立、編輯或管理主題。</span><span class="sxs-lookup"><span data-stu-id="5909f-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="5909f-159">在 [ **可以建立及編輯主題的人員** ] 區段中，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="5909f-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="5909f-160">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="5909f-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="5909f-161">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="5909f-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="5909f-162">**沒人**</span><span class="sxs-lookup"><span data-stu-id="5909f-162">**No one**</span></span>

    ![主題管理的許可權，誰可以建立及編輯主題。](../media/ksetup3.png) 

8. <span data-ttu-id="5909f-164">您可以在 [ **誰可以管理主題** ] 區段中，選取：</span><span class="sxs-lookup"><span data-stu-id="5909f-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="5909f-165">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="5909f-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="5909f-166">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="5909f-166">**Only selected people or security groups**</span></span>

    ![主題管理的許可權](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="5909f-168">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-168">Select **Next**.</span></span>

9. <span data-ttu-id="5909f-169">在 [ **建立主題中心** ] 頁面上，您可以建立可以查看主題頁面和管理主題的主題中心網站。</span><span class="sxs-lookup"><span data-stu-id="5909f-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="5909f-170">在 [ **網站名稱** ] 方塊中，輸入主題中心的名稱。</span><span class="sxs-lookup"><span data-stu-id="5909f-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="5909f-171">您可以選擇性地在 [ **描述** ] 方塊中輸入簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="5909f-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="5909f-172">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-172">Select **Next**.</span></span>

   ![建立知識中心](../media/ksetup4.png)  

10. <span data-ttu-id="5909f-174">在 **[檢閱並完成]** 頁面上，您可以查看您選取的設定，並選擇進行變更。</span><span class="sxs-lookup"><span data-stu-id="5909f-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="5909f-175">如果您對您的選擇感到滿意，請選取 **[啟用]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="5909f-176">隨即會顯示 [ **Viva 主題** ] 頁面，確認系統會立即開始分析您所選取的網站，以取得主題及建立主題中心網站。</span><span class="sxs-lookup"><span data-stu-id="5909f-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="5909f-177">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-177">Select **Done**.</span></span>

12. <span data-ttu-id="5909f-178">您將會傳回 [連線 **人員到知識]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="5909f-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="5909f-179">在此頁面上，您可以選取 **[管理]**，以對設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="5909f-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![套用的設定](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="5909f-181">指派授權</span><span class="sxs-lookup"><span data-stu-id="5909f-181">Assign licenses</span></span>

<span data-ttu-id="5909f-182">當您設定好主題經驗後，您必須指派授權給將要使用主題的使用者。</span><span class="sxs-lookup"><span data-stu-id="5909f-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="5909f-183">只有具有授權的使用者可以查看主題的相關資訊，包括要聞、主題卡片、主題頁面和主題中心。</span><span class="sxs-lookup"><span data-stu-id="5909f-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="5909f-184">若要指派授權：</span><span class="sxs-lookup"><span data-stu-id="5909f-184">To assign licenses:</span></span>

1. <span data-ttu-id="5909f-185">在 Microsoft 365 系統管理中心中，在 **[使用者]** 底下，按一下 **[作用中使用者]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="5909f-186">選取您要授權的使用者，然後按一下 [ **授權和應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="5909f-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="5909f-187">在 [**應用程式**] 底下，請確定已同時選取 [使用索引及 **主題體驗** 的 **圖形連接器搜尋]** 。</span><span class="sxs-lookup"><span data-stu-id="5909f-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

4. <span data-ttu-id="5909f-188">按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="5909f-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="5909f-189">管理主題經驗</span><span class="sxs-lookup"><span data-stu-id="5909f-189">Manage topic experiences</span></span>

<span data-ttu-id="5909f-190">在您設定好主題之後，您可以在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)變更您在安裝期間所選擇的設定。</span><span class="sxs-lookup"><span data-stu-id="5909f-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="5909f-191">請參閱下列參考：</span><span class="sxs-lookup"><span data-stu-id="5909f-191">See the following references:</span></span>

- [<span data-ttu-id="5909f-192">在 Microsoft Viva 主題中管理主題探索</span><span class="sxs-lookup"><span data-stu-id="5909f-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="5909f-193">在 Microsoft Viva 主題中管理主題可見度</span><span class="sxs-lookup"><span data-stu-id="5909f-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="5909f-194">管理 Microsoft Viva 主題中的主題許可權</span><span class="sxs-lookup"><span data-stu-id="5909f-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="5909f-195">變更 Microsoft Viva 主題中主題中心的名稱</span><span class="sxs-lookup"><span data-stu-id="5909f-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="5909f-196">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5909f-196">See also</span></span>

[<span data-ttu-id="5909f-197">主題經驗概述</span><span class="sxs-lookup"><span data-stu-id="5909f-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
