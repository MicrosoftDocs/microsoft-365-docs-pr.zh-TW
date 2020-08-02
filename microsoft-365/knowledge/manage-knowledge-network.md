---
title: '管理您的知識管理網路（預覽） '
description: 如何設定知識管理。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540115"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="734c4-103">管理您的知識管理網路（預覽）</span><span class="sxs-lookup"><span data-stu-id="734c4-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="734c4-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="734c4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="734c4-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="734c4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="734c4-106">在您[設定知識管理](set-up-knowledge-network.md)之後，任何時候，系統管理員都可以透過 Microsoft 365 系統管理中心對設定設定進行調整。</span><span class="sxs-lookup"><span data-stu-id="734c4-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="734c4-107">例如，您可能需要調整下列專案的設定：</span><span class="sxs-lookup"><span data-stu-id="734c4-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="734c4-108">將新的 SharePoint 來源新增至本主題。</span><span class="sxs-lookup"><span data-stu-id="734c4-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="734c4-109">變更哪些使用者將可以存取主題。</span><span class="sxs-lookup"><span data-stu-id="734c4-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="734c4-110">變更哪些使用者具有在主題中心執行工作的許可權。</span><span class="sxs-lookup"><span data-stu-id="734c4-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="734c4-111">變更主題中心的名稱</span><span class="sxs-lookup"><span data-stu-id="734c4-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="734c4-112">需求</span><span class="sxs-lookup"><span data-stu-id="734c4-112">Requirements</span></span> 
<span data-ttu-id="734c4-113">您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心和管理組織知識工作。</span><span class="sxs-lookup"><span data-stu-id="734c4-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="734c4-114">若要存取知識管理設定：</span><span class="sxs-lookup"><span data-stu-id="734c4-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="734c4-115">在 Microsoft 365 系統管理中心中，選取 [**安裝**]，然後查看 [**組織知識**] 區段。</span><span class="sxs-lookup"><span data-stu-id="734c4-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="734c4-116">在 [**組織知識**] 區段中，按一下 **[將人員連線到知識]**。</span><span class="sxs-lookup"><span data-stu-id="734c4-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![將人員連線至知識](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="734c4-118">在 [連線**人員至知識**] 頁面上，選取 [**管理**] 開啟 [**知識網路設定**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="734c4-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![知識網路-設定](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="734c4-120">變更知識網路可尋找主題的方式</span><span class="sxs-lookup"><span data-stu-id="734c4-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="734c4-121">如果您想要為 SharePoint 主題來源更新您的選擇，請選取 [**主題探索**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="734c4-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="734c4-122">此設定可讓您選取您租使用者中的 SharePoint 網站，將會針對主題進行編目及挖掘。</span><span class="sxs-lookup"><span data-stu-id="734c4-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="734c4-123">在 [**主題探索**] 索引標籤上，選取 [ **SharePoint 主題來源**] 底下的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="734c4-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="734c4-124">在 [**選取 SharePoint 主題來源**] 頁面上，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="734c4-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="734c4-125">這包括：</span><span class="sxs-lookup"><span data-stu-id="734c4-125">This includes:</span></span></br>
    <span data-ttu-id="734c4-126">a.</span><span class="sxs-lookup"><span data-stu-id="734c4-126">a.</span></span> <span data-ttu-id="734c4-127">**所有網站**：您租使用者中的所有 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="734c4-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="734c4-128">這會捕獲目前和未來的網站。</span><span class="sxs-lookup"><span data-stu-id="734c4-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="734c4-129">b.</span><span class="sxs-lookup"><span data-stu-id="734c4-129">b.</span></span> <span data-ttu-id="734c4-130">**全部，除了選取的網站以外**：請輸入您要排除的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="734c4-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="734c4-131">您也可以從探索中上傳想要選擇從探索中移除的網站清單。</span><span class="sxs-lookup"><span data-stu-id="734c4-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="734c4-132">未來建立的網站會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="734c4-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="734c4-133">c.</span><span class="sxs-lookup"><span data-stu-id="734c4-133">c.</span></span> <span data-ttu-id="734c4-134">**僅限選取的網站**：輸入您要包含的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="734c4-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="734c4-135">您也可以上傳網站清單。</span><span class="sxs-lookup"><span data-stu-id="734c4-135">You can also upload a list of sites.</span></span> <span data-ttu-id="734c4-136">未來建立的網站不會包含為主題探索的來源。</span><span class="sxs-lookup"><span data-stu-id="734c4-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![選擇尋找主題的方式](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="734c4-138">如果您有多個您想要排除的網站（如果您選取 [**所有] （選取的網站除外**）或 [包含] （如果您**只選取了 [選取的網站**]），您可以選擇上載包含網站名稱和 URLs 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="734c4-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="734c4-139">如果您想要使用 CSV 範本檔案，您可以選取 [**下載網站範本 .csv** ]。</span><span class="sxs-lookup"><span data-stu-id="734c4-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="734c4-140">選取 **「儲存」**。</span><span class="sxs-lookup"><span data-stu-id="734c4-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="734c4-141">變更可以查看組織中主題的人員</span><span class="sxs-lookup"><span data-stu-id="734c4-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="734c4-142">如果您想要更新組織中的哪些人員可以查看搜尋結果中已發現的主題，以及在 SharePoint 頁面等內容中突出顯示主題，請選取 [**主題探索**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="734c4-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="734c4-143">在 [**主題探索**] 索引標籤上，于 [**誰可以在知識網路中查看主題**] 底下，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="734c4-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="734c4-144">在 [**知識網路] 頁面中的 [可查看主題**] 頁面上，您可以選擇誰將有權存取主題詳細資料，例如高亮主題、主題卡片、搜尋中的主題答案及主題頁面。</span><span class="sxs-lookup"><span data-stu-id="734c4-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="734c4-145">您可以選取：</span><span class="sxs-lookup"><span data-stu-id="734c4-145">You can select:</span></span></br>
    <span data-ttu-id="734c4-146">a.</span><span class="sxs-lookup"><span data-stu-id="734c4-146">a.</span></span> <span data-ttu-id="734c4-147">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="734c4-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="734c4-148">b.</span><span class="sxs-lookup"><span data-stu-id="734c4-148">b.</span></span> <span data-ttu-id="734c4-149">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="734c4-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="734c4-150">c.</span><span class="sxs-lookup"><span data-stu-id="734c4-150">c.</span></span> <span data-ttu-id="734c4-151">**沒人**</span><span class="sxs-lookup"><span data-stu-id="734c4-151">**No one**</span></span></br>

    ![誰可以查看主題](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="734c4-153">選取 **「儲存」**。</span><span class="sxs-lookup"><span data-stu-id="734c4-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="734c4-154">雖然此設定可讓您選取組織中的任何使用者，但只有具有指派的知識管理授權的使用者才能查看主題。</span><span class="sxs-lookup"><span data-stu-id="734c4-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="734c4-155">變更誰有權在主題中心執行工作？</span><span class="sxs-lookup"><span data-stu-id="734c4-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="734c4-156">如果您想要更新主題中心頁面上具有下列許可權的人員，請選取 [**主題許可權**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="734c4-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="734c4-157">哪些使用者可以建立及編輯主題：在探索或編輯現有主題頁面詳細資料時，建立未找到的新主題。</span><span class="sxs-lookup"><span data-stu-id="734c4-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="734c4-158">哪些使用者可以管理下列主題：確認或拒絕已探索的主題。</span><span class="sxs-lookup"><span data-stu-id="734c4-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="734c4-159">若要更新誰有權建立及編輯主題：</span><span class="sxs-lookup"><span data-stu-id="734c4-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="734c4-160">在 [**主題許可權**] 索引標籤的 [**誰可以建立及編輯主題**] 中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="734c4-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="734c4-161">您可以在 [**誰可以建立及編輯主題**] 頁面上，選取：</span><span class="sxs-lookup"><span data-stu-id="734c4-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="734c4-162">a.</span><span class="sxs-lookup"><span data-stu-id="734c4-162">a.</span></span> <span data-ttu-id="734c4-163">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="734c4-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="734c4-164">b.</span><span class="sxs-lookup"><span data-stu-id="734c4-164">b.</span></span> <span data-ttu-id="734c4-165">**僅限選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="734c4-165">**Only selected people or security groups**</span></span></br>

    ![建立及編輯主題](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="734c4-167">選取 **「儲存」**。</span><span class="sxs-lookup"><span data-stu-id="734c4-167">Select **Save**.</span></span></br>

<span data-ttu-id="734c4-168">若要更新誰具有管理主題的許可權：</span><span class="sxs-lookup"><span data-stu-id="734c4-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="734c4-169">在 [**主題許可權**] 索引標籤的 [**誰可以管理主題**] 下，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="734c4-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="734c4-170">您可以在 [**誰可以管理主題**] 頁面上，選取：</span><span class="sxs-lookup"><span data-stu-id="734c4-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="734c4-171">a.</span><span class="sxs-lookup"><span data-stu-id="734c4-171">a.</span></span> <span data-ttu-id="734c4-172">**組織中的所有人**</span><span class="sxs-lookup"><span data-stu-id="734c4-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="734c4-173">b.</span><span class="sxs-lookup"><span data-stu-id="734c4-173">b.</span></span> <span data-ttu-id="734c4-174">**選取的人員或安全性群組**</span><span class="sxs-lookup"><span data-stu-id="734c4-174">**Selected people or security groups**</span></span></br>

    ![管理主題](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="734c4-176">選取 **「儲存」**。</span><span class="sxs-lookup"><span data-stu-id="734c4-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="734c4-177">更新主題中心名稱</span><span class="sxs-lookup"><span data-stu-id="734c4-177">Update your topic center name</span></span>

<span data-ttu-id="734c4-178">如果您想要更新主題中心的名稱，請選取 [**主題中心**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="734c4-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="734c4-179">在 [**主題中心**] 索引標籤的 [**主題中心名稱**] 下，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="734c4-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="734c4-180">在 [**編輯主題中心名稱**] 頁面上，于 [**主題中心名稱**] 方塊中，輸入主題中心的新名稱。</span><span class="sxs-lookup"><span data-stu-id="734c4-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="734c4-181">選取 **[儲存]**</span><span class="sxs-lookup"><span data-stu-id="734c4-181">Select **Save**</span></span>

    ![編輯主題中心名稱](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="734c4-183">另請參閱</span><span class="sxs-lookup"><span data-stu-id="734c4-183">See also</span></span>



  






