---
title: '主題經驗 (預覽的安全性調整) '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何使用安全性來查看主題。
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698865"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="87f32-103">主題經驗 (預覽的安全性調整) </span><span class="sxs-lookup"><span data-stu-id="87f32-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="87f32-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="87f32-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="87f32-105">[如需詳細資訊，請參閱 Project Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="87f32-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="87f32-106">主題經驗使用者將無法在主題中查看其現有的 Office 365 許可權可防止他們看到的資訊。</span><span class="sxs-lookup"><span data-stu-id="87f32-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="87f32-107">使用者在主題頁面上看到的所有專案 (例如，SharePoint 網站、檔、檔案) 將是已允許查看的資訊。</span><span class="sxs-lookup"><span data-stu-id="87f32-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="87f32-108">主題經驗不會變更任何現有的許可權。</span><span class="sxs-lookup"><span data-stu-id="87f32-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="87f32-109">為何兩位使用者可能會有不同的相同主題視圖</span><span class="sxs-lookup"><span data-stu-id="87f32-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="87f32-110">透過 AI 或手動 curation 建立主題時，它可以包含主題的描述、替代名稱、與主題關聯的人員，以及與主題相關的網站、頁面和檔案。</span><span class="sxs-lookup"><span data-stu-id="87f32-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="87f32-111">當您在主題頁面上查看這項資訊時，可能是兩位查看相同主題的使用者看不到相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="87f32-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="87f32-112">例如，當使用者1查看「Neptune 主題」頁面時，這就是他們可能看到的內容。</span><span class="sxs-lookup"><span data-stu-id="87f32-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![使用者1的 Neptune 主題](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="87f32-114">不過，當使用者2查看同一個 Neptune 主題頁面時，其視圖與使用者1不同。</span><span class="sxs-lookup"><span data-stu-id="87f32-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="87f32-115">使用者2能夠在主題頁面的 [已固定的檔案 **及頁面**] 區段中查看 *DG-2000 產品概述* 檔案，但不會針對使用者1顯示此頁面。</span><span class="sxs-lookup"><span data-stu-id="87f32-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![使用者2的 Neptune 主題](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="87f32-117">使用者在相同主題上看到的不同之處在于，使用者可能沒有可查看相關網站或檔案的 Office 365 許可權。</span><span class="sxs-lookup"><span data-stu-id="87f32-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="87f32-118">主題經驗是指標對主題中的專案設定的許可權，且無法變更其存取權。</span><span class="sxs-lookup"><span data-stu-id="87f32-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="87f32-119">在我們的範例中，使用者1無法在 Neptune 的 [主題] 頁面中查看 *DG-2000 產品概述* 檔案，因為使用者1沒有可用於查看檔案的 Office 365 許可權。</span><span class="sxs-lookup"><span data-stu-id="87f32-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="87f32-120">如果使用者無法在主題中看到足夠的資訊供其使用，則使用者將無法使用該主題。</span><span class="sxs-lookup"><span data-stu-id="87f32-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="87f32-121">在此範例中，使用者將不會看到反白顯示的主題。</span><span class="sxs-lookup"><span data-stu-id="87f32-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="87f32-122">不過，如果有其他使用者對該主題中的詳細資訊許可權，其有用的許可權，就可以查看該主題。</span><span class="sxs-lookup"><span data-stu-id="87f32-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="87f32-123">知識管理員和主題參與者的主題許可權</span><span class="sxs-lookup"><span data-stu-id="87f32-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="87f32-124">指派管理主題許可權的使用者-知識主管，只能夠查看其具有在主題中查看之許可權的資訊。</span><span class="sxs-lookup"><span data-stu-id="87f32-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="87f32-125">同樣地，具有「建立及編輯」主題許可權的使用者-主題投稿者-只能夠查看其具有在主題中查看之許可權的資訊。</span><span class="sxs-lookup"><span data-stu-id="87f32-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="87f32-126">AI 與手動策劃主題資訊</span><span class="sxs-lookup"><span data-stu-id="87f32-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="87f32-127">主題可以包含 AI 所產生的資訊，以及主題投稿者或知識主管新增或編輯的資訊。</span><span class="sxs-lookup"><span data-stu-id="87f32-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="87f32-128">「AI」所新增之主題中的資訊僅對存取來源內容的使用者可見。</span><span class="sxs-lookup"><span data-stu-id="87f32-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="87f32-129">由主題投稿人或知識管理員手動新增或編輯的資訊，可供每個可以查看主題的人看到。</span><span class="sxs-lookup"><span data-stu-id="87f32-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="87f32-130">下表說明哪些使用者-主題查看者、投稿人和知識管理員-根據其許可權，可在指定的主題中查看。</span><span class="sxs-lookup"><span data-stu-id="87f32-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="87f32-131">主題專案</span><span class="sxs-lookup"><span data-stu-id="87f32-131">Topic item</span></span>|<span data-ttu-id="87f32-132">使用者可以看到的內容</span><span class="sxs-lookup"><span data-stu-id="87f32-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="87f32-133">主題名稱</span><span class="sxs-lookup"><span data-stu-id="87f32-133">Topic name</span></span>|<span data-ttu-id="87f32-134">使用者可以查看主題中心所有主題的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="87f32-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="87f32-135">某些主題若具有對使用者的關聯性很低，可能會看不到。</span><span class="sxs-lookup"><span data-stu-id="87f32-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="87f32-136">主題描述</span><span class="sxs-lookup"><span data-stu-id="87f32-136">Topic description</span></span>|<span data-ttu-id="87f32-137">只有對來源內容有許可權的使用者才可以看到 AI 產生的描述。</span><span class="sxs-lookup"><span data-stu-id="87f32-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="87f32-138">所有使用者皆可看到手動輸入或編輯的描述。</span><span class="sxs-lookup"><span data-stu-id="87f32-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="87f32-139">多人</span><span class="sxs-lookup"><span data-stu-id="87f32-139">People</span></span>|<span data-ttu-id="87f32-140">所有使用者皆可看到已鎖定的人員。</span><span class="sxs-lookup"><span data-stu-id="87f32-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="87f32-141">建議的人員只對具有來源內容許可權的使用者可見。</span><span class="sxs-lookup"><span data-stu-id="87f32-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="87f32-142">檔案</span><span class="sxs-lookup"><span data-stu-id="87f32-142">Files</span></span>|<span data-ttu-id="87f32-143">只有具有來源內容許可權的使用者才能看到檔案。</span><span class="sxs-lookup"><span data-stu-id="87f32-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="87f32-144">頁面</span><span class="sxs-lookup"><span data-stu-id="87f32-144">Pages</span></span>|<span data-ttu-id="87f32-145">只有具有來源內容許可權的使用者才能看到頁面。</span><span class="sxs-lookup"><span data-stu-id="87f32-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="87f32-146">網站</span><span class="sxs-lookup"><span data-stu-id="87f32-146">Sites</span></span>|<span data-ttu-id="87f32-147">只有具有來源內容許可權的使用者才能看到網站。</span><span class="sxs-lookup"><span data-stu-id="87f32-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="87f32-148">請參閱</span><span class="sxs-lookup"><span data-stu-id="87f32-148">See also</span></span>

