---
title: 在 Microsoft 365 中設定主題體驗
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何在 Microsoft 365 中設定主題體驗
ms.openlocfilehash: e11f0b75556a4a8ac0ffa40269d7166258128daf
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698552"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="218a6-103">在 Microsoft 365 中設定主題體驗</span><span class="sxs-lookup"><span data-stu-id="218a6-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="218a6-104">您可以使用 Microsoft 365 系統管理中心來設定及設定 [主題經驗](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="218a6-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="218a6-105">在您的環境中規劃設定和設定主題的最佳方式是很重要的。</span><span class="sxs-lookup"><span data-stu-id="218a6-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="218a6-106">在您開始本文中的程式之前，請務必閱讀 [Plan 主題經驗](plan-topic-experiences.md) 。</span><span class="sxs-lookup"><span data-stu-id="218a6-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="218a6-107">您必須是全域管理員或 SharePoint 管理員，才能存取 Microsoft 365 系統管理中心及設定主題經驗。</span><span class="sxs-lookup"><span data-stu-id="218a6-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="218a6-108">設定主題經驗</span><span class="sxs-lookup"><span data-stu-id="218a6-108">Set up topic experiences</span></span>

<span data-ttu-id="218a6-109">設定 Microsoft 365 中的主題體驗</span><span class="sxs-lookup"><span data-stu-id="218a6-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="218a6-110">在 [Microsoft 365 系統管理中心](https://admin.microsoft.com)中，選取 [ **安裝**]，然後查看 [檔案 **與內容** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="218a6-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="218a6-111">在 [檔案 **與內容** ] 區段中，按一下 **[將人員連線到知識]**。</span><span class="sxs-lookup"><span data-stu-id="218a6-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![將人員連線至知識](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="218a6-113">在 [連線 **人員至知識]** 頁面上，按一下 [ **開始** ]，逐步引導您完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="218a6-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![入門](../media/k-get-started.png) 

4. <span data-ttu-id="218a6-115">在 [ **選擇知識網路可如何尋找主題** ] 頁面上，您會設定主題探索。</span><span class="sxs-lookup"><span data-stu-id="218a6-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="218a6-116">在 [ **選取 SharePoint 主題來源** ] 區段中，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="218a6-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="218a6-117">請選擇：</span><span class="sxs-lookup"><span data-stu-id="218a6-117">Choose from:</span></span>
    - <span data-ttu-id="218a6-118">**所有網站**：您組織中的所有 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="218a6-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="218a6-119">這包括目前和未來的網站。</span><span class="sxs-lookup"><span data-stu-id="218a6-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="218a6-120">**全部，除了選取的網站以外**：請輸入您要排除的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="218a6-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="218a6-121">您也可以上傳想要從探索中選擇的網站清單。</span><span class="sxs-lookup"><span data-stu-id="218a6-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="218a6-122">在未來建立的網站將會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="218a6-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="218a6-123">**僅限選取的網站**：輸入您要包含的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="218a6-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="218a6-124">您也可以上傳網站清單。</span><span class="sxs-lookup"><span data-stu-id="218a6-124">You can also upload a list of sites.</span></span> <span data-ttu-id="218a6-125">未來建立的網站不會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="218a6-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="218a6-126">**無網站**：不包含任何 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="218a6-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![選擇尋找主題的方式](../media/ksetup1.png) 
   
5. <span data-ttu-id="218a6-128">在 [以 **名稱排除主題** ] 區段中，您可以新增要從主題探索中排除的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="218a6-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="218a6-129">使用此設定可防止敏感資訊包含為主題。</span><span class="sxs-lookup"><span data-stu-id="218a6-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="218a6-130">選項包括：</span><span class="sxs-lookup"><span data-stu-id="218a6-130">The options are:</span></span>
    - <span data-ttu-id="218a6-131">**不排除任何主題**</span><span class="sxs-lookup"><span data-stu-id="218a6-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="218a6-132">**依名稱排除主題**</span><span class="sxs-lookup"><span data-stu-id="218a6-132">**Exclude topics by name**</span></span>

    ![排除主題](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="218a6-134"> (知識管理員也可以排除探索之後主題中心的主題。 ) </span><span class="sxs-lookup"><span data-stu-id="218a6-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="218a6-135">操作方法：依名稱排除主題</span><span class="sxs-lookup"><span data-stu-id="218a6-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="218a6-136">如果您需要排除相關主題，請在選取 [ **依名稱排除主題**] 之後，選取 [下載 .csv 範本並以您想要從探索結果中排除的主題清單加以更新]。</span><span class="sxs-lookup"><span data-stu-id="218a6-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![排除 CSV 範本中的主題](../media/exclude-topics-csv.png) 

    <span data-ttu-id="218a6-138">在 CSV 範本中，輸入您要排除之主題的下列相關資訊：</span><span class="sxs-lookup"><span data-stu-id="218a6-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="218a6-139">**名稱**：輸入您要排除的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="218a6-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="218a6-140">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="218a6-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="218a6-141">完全相符：您可以包含確切的名稱或縮寫 (例如， *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="218a6-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="218a6-142">部分相符：您可以排除包含特定單字的所有主題。</span><span class="sxs-lookup"><span data-stu-id="218a6-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="218a6-143">例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形*、 *等離子弧線焊接* 或 *訓練弧*。請注意，它不會排除包含文字（如 *架構*）一部分的主題。</span><span class="sxs-lookup"><span data-stu-id="218a6-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="218a6-144">**代表 (選用)**：若要排除縮寫，請輸入縮寫所代表的字。</span><span class="sxs-lookup"><span data-stu-id="218a6-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="218a6-145">**MatchType-Exact/partial**：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。</span><span class="sxs-lookup"><span data-stu-id="218a6-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="218a6-146">完成並儲存 .csv 檔案之後，請選取 **[流覽]** 以找出並選取。</span><span class="sxs-lookup"><span data-stu-id="218a6-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="218a6-147">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="218a6-147">Select **Next**.</span></span>

6. <span data-ttu-id="218a6-148">在 [ **誰可以看到主題及其可以查看的位置** ] 頁面上，您會設定主題可見度。</span><span class="sxs-lookup"><span data-stu-id="218a6-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="218a6-149">在 [在 **知識網路中查看主題** ] 設定中，您可以選擇誰可以存取主題詳細資料，例如高亮主題、主題卡片、搜尋中的主題答案及主題頁面。</span><span class="sxs-lookup"><span data-stu-id="218a6-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="218a6-150">您可以選取：</span><span class="sxs-lookup"><span data-stu-id="218a6-150">You can select:</span></span>
    - <span data-ttu-id="218a6-151">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="218a6-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="218a6-152">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="218a6-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="218a6-153">**沒人**</span><span class="sxs-lookup"><span data-stu-id="218a6-153">**No one**</span></span>

    ![誰可以查看主題](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="218a6-155">雖然此設定可讓您選取組織中的任何使用者，但只有具有指派授權之使用者的使用者可以查看主題。</span><span class="sxs-lookup"><span data-stu-id="218a6-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="218a6-156">在 [ **主題管理的許可權** ] 頁面中，您可以選擇誰將可以建立、編輯或管理主題。</span><span class="sxs-lookup"><span data-stu-id="218a6-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="218a6-157">在 [ **可以建立及編輯主題的人員** ] 區段中，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="218a6-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="218a6-158">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="218a6-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="218a6-159">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="218a6-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="218a6-160">**沒人**</span><span class="sxs-lookup"><span data-stu-id="218a6-160">**No one**</span></span>

    ![主題管理的許可權，誰可以建立及編輯主題。](../media/ksetup3.png) 

8. <span data-ttu-id="218a6-162">您可以在 [ **誰可以管理主題** ] 區段中，選取：</span><span class="sxs-lookup"><span data-stu-id="218a6-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="218a6-163">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="218a6-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="218a6-164">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="218a6-164">**Only selected people or security groups**</span></span>

    ![主題管理的許可權](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="218a6-166">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="218a6-166">Select **Next**.</span></span>

9. <span data-ttu-id="218a6-167">在 [ **建立主題中心** ] 頁面上，您可以建立可以查看主題頁面和管理主題的主題中心網站。</span><span class="sxs-lookup"><span data-stu-id="218a6-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="218a6-168">在 [ **網站名稱** ] 方塊中，輸入主題中心的名稱。</span><span class="sxs-lookup"><span data-stu-id="218a6-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="218a6-169">您可以選擇性地在 [ **描述** ] 方塊中輸入簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="218a6-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="218a6-170">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="218a6-170">Select **Next**.</span></span>

   ![建立知識中心](../media/ksetup4.png)  

10. <span data-ttu-id="218a6-172">在 **[檢閱並完成]** 頁面上，您可以查看您選取的設定，並選擇進行變更。</span><span class="sxs-lookup"><span data-stu-id="218a6-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="218a6-173">如果您對您的選擇感到滿意，請選取 **[啟用]**。</span><span class="sxs-lookup"><span data-stu-id="218a6-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="218a6-174">隨即會顯示 **知識網路啟用** 頁面，確認系統會立即開始分析您所選取的網站，以取得主題及建立「知識中心」網站。</span><span class="sxs-lookup"><span data-stu-id="218a6-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="218a6-175">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="218a6-175">Select **Done**.</span></span>

12. <span data-ttu-id="218a6-176">您將會傳回 [連線 **人員到知識]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="218a6-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="218a6-177">在此頁面上，您可以選取 **[管理]**，以對設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="218a6-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![套用的設定](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="218a6-179">指派授權</span><span class="sxs-lookup"><span data-stu-id="218a6-179">Assign licenses</span></span>

<span data-ttu-id="218a6-180">當您設定好主題經驗後，您必須指派授權給將使用主題經驗的使用者。</span><span class="sxs-lookup"><span data-stu-id="218a6-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="218a6-181">只有具有授權的使用者可以查看主題的相關資訊，包括要聞、主題卡片、主題頁面和主題中心。</span><span class="sxs-lookup"><span data-stu-id="218a6-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="218a6-182">若要指派授權：</span><span class="sxs-lookup"><span data-stu-id="218a6-182">To assign licenses:</span></span>

1. <span data-ttu-id="218a6-183">在 Microsoft 365 系統管理中心中，在 **[使用者]** 底下，按一下 **[作用中使用者]**。</span><span class="sxs-lookup"><span data-stu-id="218a6-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="218a6-184">選取您要授權的使用者，然後按一下 **[管理產品授權]**。</span><span class="sxs-lookup"><span data-stu-id="218a6-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="218a6-185">選取 **[指派更多]**。</span><span class="sxs-lookup"><span data-stu-id="218a6-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="218a6-186">在 [ **授權**] 底下，選取 **主題經驗**。</span><span class="sxs-lookup"><span data-stu-id="218a6-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="218a6-187">在 [**應用程式**] 底下，請確定已同時選取 [使用索引及 **主題體驗** 的 **圖形連接器搜尋]** 。</span><span class="sxs-lookup"><span data-stu-id="218a6-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="218a6-188">![Microsoft 365 系統管理中心中的 SharePoint Syntex 授權](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="218a6-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="218a6-189">按一下 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="218a6-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="218a6-190">管理主題經驗</span><span class="sxs-lookup"><span data-stu-id="218a6-190">Manage topic experiences</span></span>

<span data-ttu-id="218a6-191">在您設定好主題經驗後，您可以在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)變更您在安裝期間所選擇的設定。</span><span class="sxs-lookup"><span data-stu-id="218a6-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="218a6-192">請參閱下列參考：</span><span class="sxs-lookup"><span data-stu-id="218a6-192">See the following references:</span></span>

- [<span data-ttu-id="218a6-193">在 Microsoft 365 中管理主題探索</span><span class="sxs-lookup"><span data-stu-id="218a6-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="218a6-194">在 Microsoft 365 中管理主題可見度</span><span class="sxs-lookup"><span data-stu-id="218a6-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="218a6-195">在 Microsoft 365 中管理主題許可權</span><span class="sxs-lookup"><span data-stu-id="218a6-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="218a6-196">變更 Microsoft 365 主題中心的名稱</span><span class="sxs-lookup"><span data-stu-id="218a6-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="218a6-197">另請參閱</span><span class="sxs-lookup"><span data-stu-id="218a6-197">See also</span></span>

[<span data-ttu-id="218a6-198">主題經驗概述</span><span class="sxs-lookup"><span data-stu-id="218a6-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
