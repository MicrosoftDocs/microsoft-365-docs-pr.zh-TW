---
title: '設定知識管理 (預覽)  '
description: 如何設定知識管理。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612545"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="19742-103">設定知識管理 (預覽) </span><span class="sxs-lookup"><span data-stu-id="19742-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="19742-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="19742-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="19742-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="19742-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="19742-106">您可以使用 Microsoft 365 系統管理中心來設定及設定[知識管理](knowledge-management-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="19742-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="19742-107">在您的環境中規劃安裝和設定知識管理的最佳方式是很重要的。</span><span class="sxs-lookup"><span data-stu-id="19742-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="19742-108">例如，您將需要考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="19742-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="19742-109">您要分析主題的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="19742-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="19742-110">您要讓主題看得見哪些使用者。</span><span class="sxs-lookup"><span data-stu-id="19742-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="19742-111">您要授與主題中心主題的許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="19742-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="19742-112">您想要在主題中心提供許可權以建立或編輯主題的使用者。</span><span class="sxs-lookup"><span data-stu-id="19742-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="19742-113">您想要為主題中心提供什麼名稱。</span><span class="sxs-lookup"><span data-stu-id="19742-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="19742-114">您可能會發現建立安全性群組以將查看主題、管理主題及建立及編輯主題所需的許可權指派給使用者十分有用。</span><span class="sxs-lookup"><span data-stu-id="19742-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="19742-115">系統管理員也可以在安裝程式之後，透過 Microsoft 365 系統管理中心的知識管理設定[變更所選取的設定](manage-knowledge-network.md)。</span><span class="sxs-lookup"><span data-stu-id="19742-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="19742-116">需求</span><span class="sxs-lookup"><span data-stu-id="19742-116">Requirements</span></span> 
<span data-ttu-id="19742-117">您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心及設定組織知識工作。</span><span class="sxs-lookup"><span data-stu-id="19742-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="19742-118">設定您的知識網路</span><span class="sxs-lookup"><span data-stu-id="19742-118">Set up your knowledge network</span></span>

<span data-ttu-id="19742-119">設定您的知識網路可引導您完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="19742-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="19742-120">主題探索：選取要從探索中排除的主題來源和主題。</span><span class="sxs-lookup"><span data-stu-id="19742-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="19742-121">主題可見度：選取可在 [搜尋] 和 [主題] 頁面中查看主題做為醒目提示的人員。</span><span class="sxs-lookup"><span data-stu-id="19742-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="19742-122">主題許可權：選擇誰可以建立、編輯及管理主題。</span><span class="sxs-lookup"><span data-stu-id="19742-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="19742-123">主題中心：建立主題中心。</span><span class="sxs-lookup"><span data-stu-id="19742-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="19742-124">檢查：檢查並套用您的設定。</span><span class="sxs-lookup"><span data-stu-id="19742-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="19742-125">若要設定您的知識網路：</span><span class="sxs-lookup"><span data-stu-id="19742-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="19742-126">在 Microsoft 365 系統管理中心 (admin.microsoft.com) 中，選取 [**設定**]，然後查看 [**組織知識**] 區段。</span><span class="sxs-lookup"><span data-stu-id="19742-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="19742-127">在 [**組織知識**] 區段中，按一下 **[將人員連線到知識]**。</span><span class="sxs-lookup"><span data-stu-id="19742-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![將人員連線至知識](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="19742-129">在 [連線**人員至知識]** 頁面上，按一下 [**開始**]，逐步引導您完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="19742-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![開始使用](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="19742-131">在 [**選擇知識網路可如何尋找主題**] 頁面上，您會設定主題探索。</span><span class="sxs-lookup"><span data-stu-id="19742-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="19742-132">在 [**選取 SharePoint 主題來源**] 區段中，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="19742-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="19742-133">這包括：</span><span class="sxs-lookup"><span data-stu-id="19742-133">This includes:</span></span></br>
    <span data-ttu-id="19742-134">a.</span><span class="sxs-lookup"><span data-stu-id="19742-134">a.</span></span> <span data-ttu-id="19742-135">**所有網站**：您租使用者中的所有 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="19742-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="19742-136">這會捕獲目前和未來的網站。</span><span class="sxs-lookup"><span data-stu-id="19742-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="19742-137">b.</span><span class="sxs-lookup"><span data-stu-id="19742-137">b.</span></span> <span data-ttu-id="19742-138">**全部，除了選取的網站以外**：請輸入您要排除的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="19742-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="19742-139">您也可以上傳想要從探索中選擇的網站清單。</span><span class="sxs-lookup"><span data-stu-id="19742-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="19742-140">在未來建立的網站將會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="19742-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="19742-141">c.</span><span class="sxs-lookup"><span data-stu-id="19742-141">c.</span></span> <span data-ttu-id="19742-142">**僅限選取的網站**：輸入您要包含的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="19742-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="19742-143">您也可以上傳網站清單。</span><span class="sxs-lookup"><span data-stu-id="19742-143">You can also upload a list of sites.</span></span> <span data-ttu-id="19742-144">未來建立的網站不會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="19742-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![選擇尋找主題的方式](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="19742-146">在 [以**名稱排除主題**] 區段中，您可以選擇包含您不想在已探索結果中的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="19742-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="19742-147">使用此設定可防止敏感主題加入為知識網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="19742-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="19742-148">您的選項包括：</span><span class="sxs-lookup"><span data-stu-id="19742-148">Your options include:</span></span></br>
    <span data-ttu-id="19742-149">a.</span><span class="sxs-lookup"><span data-stu-id="19742-149">a.</span></span> <span data-ttu-id="19742-150">**不排除任何主題**</span><span class="sxs-lookup"><span data-stu-id="19742-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="19742-151">b.</span><span class="sxs-lookup"><span data-stu-id="19742-151">b.</span></span> <span data-ttu-id="19742-152">**排除包含這些字詞的主題**：如果您有不想要在知識網路中顯示的主題。</span><span class="sxs-lookup"><span data-stu-id="19742-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="19742-153">-下載提供的範本。</span><span class="sxs-lookup"><span data-stu-id="19742-153">- Download the provided template.</span></span>
   <span data-ttu-id="19742-154">-輸入您要排除的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="19742-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="19742-155">您必須以完全或部分的方式表示相符類型。</span><span class="sxs-lookup"><span data-stu-id="19742-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="19742-156">完全相符表示會排除符合實際字詞的主題。</span><span class="sxs-lookup"><span data-stu-id="19742-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="19742-157">部分比對更嚴格，並表示會排除包含字詞的主題。</span><span class="sxs-lookup"><span data-stu-id="19742-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="19742-158">例如，如果您輸入*doc*做為主題名稱，將會在 Docker 中排除*doc 元件*，而*Docker*不會。</span><span class="sxs-lookup"><span data-stu-id="19742-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="19742-159">主題名稱不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="19742-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="19742-160">-選取  **+**   以匯入已完成的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="19742-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="19742-161">然後選取 **[上傳**]。</span><span class="sxs-lookup"><span data-stu-id="19742-161">Then select **Upload**.</span></span> <span data-ttu-id="19742-162">如果您的檔案處理順利，您會看到綠色核取記號。</span><span class="sxs-lookup"><span data-stu-id="19742-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="19742-163">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19742-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="19742-164">在 [**誰可以看到主題及其可以查看的位置**] 頁面上，您會設定主題可見度。</span><span class="sxs-lookup"><span data-stu-id="19742-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="19742-165">在 [在**知識網路中查看主題**] 設定中，您可以選擇誰可以存取主題詳細資料，例如高亮主題、主題卡片、搜尋中的主題答案及主題頁面。</span><span class="sxs-lookup"><span data-stu-id="19742-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="19742-166">您可以選取：</span><span class="sxs-lookup"><span data-stu-id="19742-166">You can select:</span></span></br>
    <span data-ttu-id="19742-167">a.</span><span class="sxs-lookup"><span data-stu-id="19742-167">a.</span></span> <span data-ttu-id="19742-168">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="19742-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="19742-169">b.</span><span class="sxs-lookup"><span data-stu-id="19742-169">b.</span></span> <span data-ttu-id="19742-170">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="19742-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="19742-171">c.</span><span class="sxs-lookup"><span data-stu-id="19742-171">c.</span></span> <span data-ttu-id="19742-172">**沒人**</span><span class="sxs-lookup"><span data-stu-id="19742-172">**No one**</span></span></br>

    ![誰可以查看主題](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="19742-174">雖然此設定可讓您選取組織中的任何使用者，但只有具有指派的知識管理授權的使用者才能查看主題。</span><span class="sxs-lookup"><span data-stu-id="19742-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="19742-175">在 [**主題管理的許可權**] 頁面中，您可以選擇誰將可以建立、編輯或管理主題。</span><span class="sxs-lookup"><span data-stu-id="19742-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="19742-176">在 [**可以建立及編輯主題的人員**] 區段中，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="19742-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="19742-177">a.</span><span class="sxs-lookup"><span data-stu-id="19742-177">a.</span></span> <span data-ttu-id="19742-178">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="19742-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="19742-179">b.</span><span class="sxs-lookup"><span data-stu-id="19742-179">b.</span></span> <span data-ttu-id="19742-180">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="19742-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="19742-181">您可以在 [**誰可以管理主題**] 區段中，選取：</span><span class="sxs-lookup"><span data-stu-id="19742-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="19742-182">a.</span><span class="sxs-lookup"><span data-stu-id="19742-182">a.</span></span> <span data-ttu-id="19742-183">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="19742-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="19742-184">b.</span><span class="sxs-lookup"><span data-stu-id="19742-184">b.</span></span> <span data-ttu-id="19742-185">**選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="19742-185">**Selected people or security groups**</span></span></br>

    ![主題管理的許可權](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="19742-187">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19742-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="19742-188">在 [**建立主題中心**] 頁面上，您可以建立可以查看主題頁面和管理主題的主題中心網站。</span><span class="sxs-lookup"><span data-stu-id="19742-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="19742-189">在 [**主題中心名稱**] 方塊中，輸入主題中心的名稱。</span><span class="sxs-lookup"><span data-stu-id="19742-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="19742-190">您可以選擇性地在 [**網站描述**] 方塊中輸入簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="19742-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="19742-191">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19742-191">Select **Next**.</span></span></br>

   ![建立知識中心](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="19742-193">在 [**檢查和完成]** 頁面上，您可以查看選取的設定，並選擇進行變更。</span><span class="sxs-lookup"><span data-stu-id="19742-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="19742-194">如果您對選擇滿意，請選取 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="19742-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![完成和審閱](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="19742-196">隨即會顯示**知識網路啟用**頁面，確認系統會立即開始分析您所選取的網站，以取得主題及建立「知識中心」網站。</span><span class="sxs-lookup"><span data-stu-id="19742-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="19742-197">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="19742-197">Select **Done**.</span></span></br>

    ![啟動](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="19742-199">您將會傳回 [連線**人員到知識]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="19742-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="19742-200">您可以從這個頁面，選取 [**管理**]，對您的設定設定進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="19742-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![套用的設定](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="19742-202">安裝程式完成後，系統管理員可以隨時[變更選取的知識管理設定](manage-knowledge-network.md)，方法是回到此頁面。</span><span class="sxs-lookup"><span data-stu-id="19742-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="19742-203">另請參閱</span><span class="sxs-lookup"><span data-stu-id="19742-203">See also</span></span>



  






