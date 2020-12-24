---
title: '在 (預覽的 [主題經驗] 中，管理主題中心的主題)  '
description: 如何管理主題中心的主題。
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 92cf9c860ddbf199c70a7c2d89a7daba3dfe0fe7
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731321"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="25698-103">管理主題中央 (預覽中的主題) </span><span class="sxs-lookup"><span data-stu-id="25698-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="25698-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="25698-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="25698-105">[如需詳細資訊，請參閱 Project Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="25698-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="25698-106">在主題中心，知識管理員可以查看「 **管理主題** 」頁面，以查看已在 SharePoint 來源位置識別的主題，如您的知識系統管理員所指定的主題。</span><span class="sxs-lookup"><span data-stu-id="25698-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![主題中心](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="25698-108">知識管理員會協助您透過主題生命週期來引導探索的主題：</span><span class="sxs-lookup"><span data-stu-id="25698-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="25698-109">建議：主題已透過 AI 識別，且具有足夠的支援資源、連線和屬性，可滿足主題閾值。</span><span class="sxs-lookup"><span data-stu-id="25698-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="25698-110">已確認：已驗證 AI 已建議的主題。</span><span class="sxs-lookup"><span data-stu-id="25698-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="25698-111">驗證是由知識系統管理員的確認所完成。此外，如果至少有兩位使用者透過主題所提供的意見反應提供積極的反應，也可以確認主題。</span><span class="sxs-lookup"><span data-stu-id="25698-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="25698-112">已移除：主題是由知識管理員拒絕，且不會再對檢視器顯示。</span><span class="sxs-lookup"><span data-stu-id="25698-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="25698-113">主題可以處於移除狀態時的任何狀態 (建議或確認) 。</span><span class="sxs-lookup"><span data-stu-id="25698-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="25698-114">已發佈：已手動更新的已確認主題。</span><span class="sxs-lookup"><span data-stu-id="25698-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![主題生命週期圖表](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="25698-116">需求</span><span class="sxs-lookup"><span data-stu-id="25698-116">Requirements</span></span>

<span data-ttu-id="25698-117">若要管理主題中心的主題，您必須：</span><span class="sxs-lookup"><span data-stu-id="25698-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="25698-118">有一個主題經驗豐富授權。</span><span class="sxs-lookup"><span data-stu-id="25698-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="25698-119">擁有 [**誰可以管理主題**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)的許可權。</span><span class="sxs-lookup"><span data-stu-id="25698-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="25698-120">知識系統管理員可以在知識網路主題許可權設定中，將此許可權授與使用者。</span><span class="sxs-lookup"><span data-stu-id="25698-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="25698-121">除非您有 **可以管理主題** 許可權的人員，否則您將無法在主題中心中查看「管理主題」頁面。</span><span class="sxs-lookup"><span data-stu-id="25698-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="25698-122">在主題中心，知識管理員可以查看已在您指定的 SharePoint 來源位置中識別的主題，也可以確認或拒絕這些主題。</span><span class="sxs-lookup"><span data-stu-id="25698-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="25698-123">知識管理員也可以建立及發佈新的主題頁面（如果未在主題探索中找到的話），或編輯現有的主題頁面（如果需要更新）。</span><span class="sxs-lookup"><span data-stu-id="25698-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="25698-124">查看建議的主題</span><span class="sxs-lookup"><span data-stu-id="25698-124">Review suggested topics</span></span>

<span data-ttu-id="25698-125">在 [主題中心管理主題] 頁面上，在您指定的 SharePoint 來源位置中探索的主題將會列在 [ **建議** ] 索引標籤中。知識管理員可以查看未確認的主題，並選擇確認或拒絕這些主題。</span><span class="sxs-lookup"><span data-stu-id="25698-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="25698-126">若要查看建議的主題：</span><span class="sxs-lookup"><span data-stu-id="25698-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="25698-127">在 [ **管理主題** ] 頁面上，選取 [ **建議** ] 索引標籤，選取主題，以開啟 [主題] 頁面。</span><span class="sxs-lookup"><span data-stu-id="25698-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="25698-128">在 [主題] 頁面上，複查 [主題] 頁面，如果您需要對頁面進行任何變更，請選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="25698-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="25698-129">檢查主題之後，請回到 [管理主題] 頁面。</span><span class="sxs-lookup"><span data-stu-id="25698-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="25698-130">針對所選主題，您可以：</span><span class="sxs-lookup"><span data-stu-id="25698-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="25698-131">選取 [核取記號] 以確認主題。</span><span class="sxs-lookup"><span data-stu-id="25698-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="25698-132">如果您想要拒絕該主題，請選取 **x** 。</span><span class="sxs-lookup"><span data-stu-id="25698-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="25698-133">已確認的主題將從 **建議** 的清單中移除，現在會顯示在 [已 **確認** ] 清單中。</span><span class="sxs-lookup"><span data-stu-id="25698-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="25698-134">已拒絕的主題將會從 **建議** 的清單中移除，現在會顯示在 [ **已移除** ] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="25698-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="25698-135">已確認主題</span><span class="sxs-lookup"><span data-stu-id="25698-135">Confirmed topics</span></span>

<span data-ttu-id="25698-136">在 [管理主題] 頁面上，在您指定的 SharePoint 來源位置中探索的主題，並已由兩個或多個透過卡片意見反應機制的人員確認的知識管理員或「具有相同」的主題，將會列于 [已 **確認** ] 索引標籤中。如有需要，具有管理主題許可權的使用者可以查看已確認的主題，並選擇拒絕這些主題。</span><span class="sxs-lookup"><span data-stu-id="25698-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="25698-137">若要查看已確認的主題：</span><span class="sxs-lookup"><span data-stu-id="25698-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="25698-138">在 [已 **確認** ] 索引標籤上，選取主題，以開啟 [主題] 頁面。</span><span class="sxs-lookup"><span data-stu-id="25698-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="25698-139">在 [主題] 頁面上，複查 [主題] 頁面，如果您需要對頁面進行任何變更，請選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="25698-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="25698-140">請注意，您仍然可以選擇拒絕已確認的主題。</span><span class="sxs-lookup"><span data-stu-id="25698-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="25698-141">若要這樣做，請移至已確認清單中的選取主題，如果您想要拒絕該主題，請選取 **x** 。</span><span class="sxs-lookup"><span data-stu-id="25698-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="25698-142">已發佈主題</span><span class="sxs-lookup"><span data-stu-id="25698-142">Published topics</span></span>
<span data-ttu-id="25698-143">已發佈的主題已經過編輯，使特定資訊永遠會出現在頁面出現的任何處。</span><span class="sxs-lookup"><span data-stu-id="25698-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="25698-144">手動建立的主題會列在這裡。</span><span class="sxs-lookup"><span data-stu-id="25698-144">Manually created topics are listed here.</span></span>




