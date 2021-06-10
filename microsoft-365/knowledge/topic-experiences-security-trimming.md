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
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939620"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="221b6-103">Microsoft Viva 主題安全性調整</span><span class="sxs-lookup"><span data-stu-id="221b6-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="221b6-104">Viva 主題使用者無法在主題中查看其現有 Office 365 許可權可防止他們看到的資訊。</span><span class="sxs-lookup"><span data-stu-id="221b6-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="221b6-105">使用者在主題頁面上看到的所有內容 (例如 SharePoint 網站、文件、檔案) 將是他們獲允許可看到的資訊。</span><span class="sxs-lookup"><span data-stu-id="221b6-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="221b6-106">Viva Topics 不會變更任何現有的權限。</span><span class="sxs-lookup"><span data-stu-id="221b6-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="221b6-107">為何兩位使用者可能會有不同的相同主題視圖</span><span class="sxs-lookup"><span data-stu-id="221b6-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="221b6-108">透過 AI 或手動策劃建立主題時，可以包含主題描述、替代名稱、與主題相關聯的人員，以及與該主題相關的網站、頁面和檔案。</span><span class="sxs-lookup"><span data-stu-id="221b6-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="221b6-109">當您在主題頁面上查看這項資訊時，可能是兩位查看相同主題的使用者看不到相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="221b6-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="221b6-110">例如，當使用者 1 檢視海王星主題頁面時，他們可能會看到此主題頁面檢視。</span><span class="sxs-lookup"><span data-stu-id="221b6-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![使用者1的 Neptune 主題](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="221b6-112">不過，當使用者2查看同一個 Neptune 主題頁面時，其視圖與使用者1不同。</span><span class="sxs-lookup"><span data-stu-id="221b6-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="221b6-113">使用者2能夠在主題頁面的 [已固定的檔案 **及頁面**] 區段中查看 *DG-2000 產品概述* 檔案，但不會針對使用者1顯示此頁面。</span><span class="sxs-lookup"><span data-stu-id="221b6-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![使用者2的 Neptune 主題](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="221b6-115">使用者在相同主題上看到的不同之處在于，使用者可能沒有查看相關網站或檔案的 Office 365 許可權。</span><span class="sxs-lookup"><span data-stu-id="221b6-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="221b6-116">Viva 主題會尊重為主題中的專案設定的許可權，而且無法變更其存取權。</span><span class="sxs-lookup"><span data-stu-id="221b6-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="221b6-117">在我們的範例中，使用者1無法在 Neptune 的 [主題] 頁面中查看 *DG-2000 產品概述* 檔案，因為使用者1沒有查看檔案的 Office 365 許可權。</span><span class="sxs-lookup"><span data-stu-id="221b6-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="221b6-118">如果使用者無法在主題中看到足夠的資訊供其使用，則使用者將無法使用該主題。</span><span class="sxs-lookup"><span data-stu-id="221b6-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="221b6-119">發生這種情況時，使用者將不會看到反白顯示的主題。</span><span class="sxs-lookup"><span data-stu-id="221b6-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="221b6-120">另一位擁有主題中更多資訊權限的使用者，將能看到該主題。</span><span class="sxs-lookup"><span data-stu-id="221b6-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="221b6-121">知識管理員和主題參與者的主題許可權</span><span class="sxs-lookup"><span data-stu-id="221b6-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="221b6-122">指派管理主題許可權的使用者-知識主管，只能夠查看其具有在主題中查看之許可權的資訊。</span><span class="sxs-lookup"><span data-stu-id="221b6-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="221b6-123">同樣地，具有「建立及編輯」主題許可權的使用者-主題投稿者-只能夠查看其具有在主題中查看之許可權的資訊。</span><span class="sxs-lookup"><span data-stu-id="221b6-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="221b6-124">AI 與手動策劃的主題資訊</span><span class="sxs-lookup"><span data-stu-id="221b6-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="221b6-125">主題可以包含 AI 所產生的資訊，以及主題投稿者或知識主管新增或編輯的資訊。</span><span class="sxs-lookup"><span data-stu-id="221b6-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="221b6-126">AI 新增的主題資訊只有擁有來源內容存取權的人才能看到。</span><span class="sxs-lookup"><span data-stu-id="221b6-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="221b6-127">主題描述和人員資訊，由主題投稿人或知識管理員手動新增或編輯，可供每個可以查看主題的人看到。</span><span class="sxs-lookup"><span data-stu-id="221b6-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="221b6-128">不論是使用來源內容的許可權，還是透過 AI 手動新增或新增檔、頁面和網站，都只會看到這些使用者。</span><span class="sxs-lookup"><span data-stu-id="221b6-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="221b6-129">下表說明哪些使用者-主題查看者、投稿人和知識管理員-根據其許可權，可在指定的主題中查看。</span><span class="sxs-lookup"><span data-stu-id="221b6-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="221b6-130">主題項目</span><span class="sxs-lookup"><span data-stu-id="221b6-130">Topic item</span></span>|<span data-ttu-id="221b6-131">使用者可以看到的內容</span><span class="sxs-lookup"><span data-stu-id="221b6-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="221b6-132">主題名稱</span><span class="sxs-lookup"><span data-stu-id="221b6-132">Topic name</span></span>|<span data-ttu-id="221b6-133">使用者可以查看主題中心主題的主題名稱。</span><span class="sxs-lookup"><span data-stu-id="221b6-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="221b6-134">若使用者沒有來源內容的許可權或對使用者的關聯性很低，某些主題可能不會顯示。</span><span class="sxs-lookup"><span data-stu-id="221b6-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="221b6-135">主題描述</span><span class="sxs-lookup"><span data-stu-id="221b6-135">Topic description</span></span>|<span data-ttu-id="221b6-136">僅具有來源內容存取權限的使用者可以看到 AI 產生的描述。</span><span class="sxs-lookup"><span data-stu-id="221b6-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="221b6-137">所有使用者都可以看到手動輸入或編輯的描述。</span><span class="sxs-lookup"><span data-stu-id="221b6-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="221b6-138">人員</span><span class="sxs-lookup"><span data-stu-id="221b6-138">People</span></span>|<span data-ttu-id="221b6-139">所有使用者都可以看到釘選人員。</span><span class="sxs-lookup"><span data-stu-id="221b6-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="221b6-140">僅具有來源內容存取權限的使用者可以看到建議人員。</span><span class="sxs-lookup"><span data-stu-id="221b6-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="221b6-141">檔案</span><span class="sxs-lookup"><span data-stu-id="221b6-141">Files</span></span>|<span data-ttu-id="221b6-142">僅具有來源內容存取權限的使用者可以看到檔案。</span><span class="sxs-lookup"><span data-stu-id="221b6-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="221b6-143">頁面</span><span class="sxs-lookup"><span data-stu-id="221b6-143">Pages</span></span>|<span data-ttu-id="221b6-144">僅具有來源內容存取權限的使用者可以看到頁面。</span><span class="sxs-lookup"><span data-stu-id="221b6-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="221b6-145">網站</span><span class="sxs-lookup"><span data-stu-id="221b6-145">Sites</span></span>|<span data-ttu-id="221b6-146">僅具有來源內容存取權限的使用者可以看到網站。</span><span class="sxs-lookup"><span data-stu-id="221b6-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="221b6-147">請參閱</span><span class="sxs-lookup"><span data-stu-id="221b6-147">See also</span></span>

