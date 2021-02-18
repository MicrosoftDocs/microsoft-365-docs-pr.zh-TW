---
title: Microsoft Viva 主題安全性調整
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: 瞭解如何使用安全性來查看主題。
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279329"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="1a9ac-103">Microsoft Viva 主題安全性調整</span><span class="sxs-lookup"><span data-stu-id="1a9ac-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="1a9ac-104">Viva 主題使用者無法在主題中查看其現有的 Office 365 許可權可防止他們看到的資訊。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="1a9ac-105">使用者在主題頁面上看到的所有專案 (例如，SharePoint 網站、檔、檔案) 將是已允許查看的資訊。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="1a9ac-106">Viva 主題不會變更任何現有的許可權。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="1a9ac-107">為何兩位使用者可能會有不同的相同主題視圖</span><span class="sxs-lookup"><span data-stu-id="1a9ac-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="1a9ac-108">透過 AI 或手動 curation 建立主題時，它可以包含主題的描述、替代名稱、與主題關聯的人員，以及與主題相關的網站、頁面和檔案。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="1a9ac-109">當您在主題頁面上查看這項資訊時，可能是兩位查看相同主題的使用者看不到相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="1a9ac-110">例如，當使用者1查看「Neptune 主題」頁面時，他們可能會看到 [主題] 頁面的此視圖。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![使用者1的 Neptune 主題](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="1a9ac-112">不過，當使用者2查看同一個 Neptune 主題頁面時，其視圖與使用者1不同。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="1a9ac-113">使用者2能夠在主題頁面的 [已固定的檔案 **及頁面**] 區段中查看 *DG-2000 產品概述* 檔案，但不會針對使用者1顯示此頁面。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![使用者2的 Neptune 主題](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="1a9ac-115">使用者在相同主題上看到的不同之處在于，使用者可能沒有可查看相關網站或檔案的 Office 365 許可權。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="1a9ac-116">Viva 主題會尊重為主題中的專案設定的許可權，而且無法變更其存取權。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="1a9ac-117">在我們的範例中，使用者1無法在 Neptune 的 [主題] 頁面中查看 *DG-2000 產品概述* 檔案，因為使用者1沒有可用於查看檔案的 Office 365 許可權。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="1a9ac-118">如果使用者無法在主題中看到足夠的資訊供其使用，則使用者將無法使用該主題。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="1a9ac-119">發生這種情況時，使用者將不會看到反白顯示的主題。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="1a9ac-120">若有其他使用者對該主題中的詳細資訊具有有用的許可權，就可以查看該主題。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="1a9ac-121">知識管理員和主題參與者的主題許可權</span><span class="sxs-lookup"><span data-stu-id="1a9ac-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="1a9ac-122">指派管理主題許可權的使用者-知識主管，只能夠查看其具有在主題中查看之許可權的資訊。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="1a9ac-123">同樣地，具有「建立及編輯」主題許可權的使用者-主題投稿者-只能夠查看其具有在主題中查看之許可權的資訊。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="1a9ac-124">AI 與手動策劃主題資訊</span><span class="sxs-lookup"><span data-stu-id="1a9ac-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="1a9ac-125">主題可以包含 AI 所產生的資訊，以及主題投稿者或知識主管新增或編輯的資訊。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="1a9ac-126">「AI」所新增之主題中的資訊僅對存取來源內容的使用者可見。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="1a9ac-127">主題描述和人員資訊，由主題投稿人或知識管理員手動新增或編輯，可供每個可以查看主題的人看到。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="1a9ac-128">不論是使用來源內容的許可權，還是透過 AI 手動新增或新增檔、頁面和網站，都只會看到這些使用者。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="1a9ac-129">下表說明哪些使用者-主題查看者、投稿人和知識管理員-根據其許可權，可在指定的主題中查看。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="1a9ac-130">主題專案</span><span class="sxs-lookup"><span data-stu-id="1a9ac-130">Topic item</span></span>|<span data-ttu-id="1a9ac-131">使用者可以看到的內容</span><span class="sxs-lookup"><span data-stu-id="1a9ac-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="1a9ac-132">主題名稱</span><span class="sxs-lookup"><span data-stu-id="1a9ac-132">Topic name</span></span>|<span data-ttu-id="1a9ac-133">使用者可以查看主題中心所有主題的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-133">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="1a9ac-134">某些主題若具有對使用者的關聯性很低，可能會看不到。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-134">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="1a9ac-135">主題描述</span><span class="sxs-lookup"><span data-stu-id="1a9ac-135">Topic description</span></span>|<span data-ttu-id="1a9ac-136">只有對來源內容有許可權的使用者才可以看到 AI 產生的描述。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="1a9ac-137">所有使用者皆可看到手動輸入或編輯的描述。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="1a9ac-138">People</span><span class="sxs-lookup"><span data-stu-id="1a9ac-138">People</span></span>|<span data-ttu-id="1a9ac-139">所有使用者皆可看到已鎖定的人員。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="1a9ac-140">建議的人員只對具有來源內容許可權的使用者可見。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="1a9ac-141">檔案</span><span class="sxs-lookup"><span data-stu-id="1a9ac-141">Files</span></span>|<span data-ttu-id="1a9ac-142">只有具有來源內容許可權的使用者才能看到檔案。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="1a9ac-143">頁面</span><span class="sxs-lookup"><span data-stu-id="1a9ac-143">Pages</span></span>|<span data-ttu-id="1a9ac-144">只有具有來源內容許可權的使用者才能看到頁面。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="1a9ac-145">網站</span><span class="sxs-lookup"><span data-stu-id="1a9ac-145">Sites</span></span>|<span data-ttu-id="1a9ac-146">只有具有來源內容許可權的使用者才能看到網站。</span><span class="sxs-lookup"><span data-stu-id="1a9ac-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="1a9ac-147">請參閱</span><span class="sxs-lookup"><span data-stu-id="1a9ac-147">See also</span></span>

