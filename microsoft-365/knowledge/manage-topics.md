---
title: 管理 Microsoft Viva 主題中主題中心的主題
description: 如何管理主題中心的主題。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2443319d254130b38bb1047a633c85c160eadd8c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925997"
---
# <a name="manage-topics-in-the-topic-center"></a><span data-ttu-id="128bf-103">管理主題中心的主題</span><span class="sxs-lookup"><span data-stu-id="128bf-103">Manage topics in the Topic center</span></span> 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="128bf-104">在 Viva 主題主題中心，知識管理員可以查看「 **管理主題** 」頁面，以查看已在您的知識系統管理員所指定 SharePoint 來源位置識別的主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-104">In the Viva Topics Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![主題中心](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="128bf-106">知識管理員會協助您透過主題生命週期來引導探索的主題：</span><span class="sxs-lookup"><span data-stu-id="128bf-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="128bf-107">建議：主題已透過 AI 識別，且具有足夠的支援資源、連線和屬性。</span><span class="sxs-lookup"><span data-stu-id="128bf-107">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="128bf-108">已確認：已驗證 AI 已建議的主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-108">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="128bf-109">驗證是由知識管理員的確認所完成。</span><span class="sxs-lookup"><span data-stu-id="128bf-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="128bf-110">此外，如果至少有兩位使用者透過主題卡片上的意見反應提供積極的意見反應，也可以確認主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="128bf-111">已發佈：已策劃的已確認主題：已進行手動編輯，以提升其品質。</span><span class="sxs-lookup"><span data-stu-id="128bf-111">Published: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="128bf-112">已移除：主題是由知識管理員拒絕，且不會再對檢視器顯示。</span><span class="sxs-lookup"><span data-stu-id="128bf-112">Removed: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="128bf-113">主題可以處於移除狀態時的任何狀態 (建議、確認或發佈的) 。</span><span class="sxs-lookup"><span data-stu-id="128bf-113">The topic can be in any state when it is removed (suggested, confirmed or published).</span></span> <span data-ttu-id="128bf-114">移除已發佈的主題時，將需要透過主題中心的頁面庫手動刪除策劃詳細資料的頁面。</span><span class="sxs-lookup"><span data-stu-id="128bf-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![主題生命週期圖表](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="128bf-116">在 [管理主題] 頁面中，每個知識管理員只會看到可存取主題檔案及頁面的主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-116">In the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="128bf-117">這會反映在 [建議]、[已確認]、[已移除] 及 [已發佈] 索引標籤底下的主題中。</span><span class="sxs-lookup"><span data-stu-id="128bf-117">This will be reflected in the topics that are listed under the Suggested, Confirmed, Removed, and Published tabs.</span></span> <span data-ttu-id="128bf-118">不過，主題會計陣列織中的總計計數。</span><span class="sxs-lookup"><span data-stu-id="128bf-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="128bf-119">需求</span><span class="sxs-lookup"><span data-stu-id="128bf-119">Requirements</span></span>

<span data-ttu-id="128bf-120">若要管理主題中心的主題，您必須：</span><span class="sxs-lookup"><span data-stu-id="128bf-120">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="128bf-121">具有 Viva 主題授權。</span><span class="sxs-lookup"><span data-stu-id="128bf-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="128bf-122">讓 [**誰可以管理主題**](./topic-experiences-user-permissions.md) 許可權。</span><span class="sxs-lookup"><span data-stu-id="128bf-122">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="128bf-123">知識系統管理員可以在 Viva 主題主題許可權設定中，將此許可權授與使用者。</span><span class="sxs-lookup"><span data-stu-id="128bf-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="128bf-124">除非您有 **可以管理主題** 許可權的人員，否則您將無法在主題中心中查看「管理主題」頁面。</span><span class="sxs-lookup"><span data-stu-id="128bf-124">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="128bf-125">在主題中心，知識管理員可以查看已在您指定的 SharePoint 來源位置中識別的主題，也可以確認或拒絕這些主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="128bf-126">知識管理員也可以建立及發佈新的主題頁面（如果未在主題探索中找到的話），或編輯現有的主題頁面（如果需要更新）。</span><span class="sxs-lookup"><span data-stu-id="128bf-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="128bf-127">查看建議的主題</span><span class="sxs-lookup"><span data-stu-id="128bf-127">Review suggested topics</span></span>

<span data-ttu-id="128bf-128">在 [主題中心管理主題] 頁面上，在您指定的 SharePoint 來源位置中探索的主題將會列在 [ **建議** ] 索引標籤中。如有需要，知識管理員可以查看未確認的主題，並選擇確認或拒絕這些主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-128">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![建議的主題](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="128bf-130">若要查看建議的主題：</span><span class="sxs-lookup"><span data-stu-id="128bf-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="128bf-131">在 [ **管理主題** ] 頁面上，選取 [ **建議** ] 索引標籤，選取主題，以開啟 [主題] 頁面。</span><span class="sxs-lookup"><span data-stu-id="128bf-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="128bf-132">在 [主題] 頁面上，複查 [主題] 頁面，如果您需要對頁面進行任何變更，請選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="128bf-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="128bf-133">發佈任何編輯都會將此主題移至 [ **發佈** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="128bf-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="128bf-134">檢查主題之後，請回到 [管理主題] 頁面。</span><span class="sxs-lookup"><span data-stu-id="128bf-134">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="128bf-135">針對所選主題，您可以：</span><span class="sxs-lookup"><span data-stu-id="128bf-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="128bf-136">選取 [核取記號] 以確認主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="128bf-137">如果您想要拒絕該主題，請選取 **x** 。</span><span class="sxs-lookup"><span data-stu-id="128bf-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="128bf-138">已確認的主題將從 **建議** 的清單中移除，現在會顯示在 [已 **確認** ] 清單中。</span><span class="sxs-lookup"><span data-stu-id="128bf-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="128bf-139">已拒絕的主題將會從 **建議** 的清單中移除，現在會顯示在 [ **已移除** ] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="128bf-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="128bf-140">品質分數</span><span class="sxs-lookup"><span data-stu-id="128bf-140">Quality score</span></span>

<span data-ttu-id="128bf-141">[建議的主題] 頁面中顯示的每個主題都有指派的 <b>品質</b> 分數。</span><span class="sxs-lookup"><span data-stu-id="128bf-141">Each topic that appears in your Suggested Topics page has a <b>Quality</b> score assigned to it.</span></span> <span data-ttu-id="128bf-142">品質分數是一般使用者將看到之相關資訊的資訊數量反映，請記住，每當使用者可能會有或可能不會對主題中的資訊所做的許可權，都可能會看到更多或更少的資訊。</span><span class="sxs-lookup"><span data-stu-id="128bf-142">The Quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user may see more or less information because of the permissions they may or may not have on the information in a topic.</span></span> 

<span data-ttu-id="128bf-143">品質分數可協助深入瞭解大部分資訊的主題，並可用於尋找可能需要手動編輯的主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-143">The Quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span>  <span data-ttu-id="128bf-144">例如，較低品質分數的主題可能是部分使用者未具有 AI 主題所包含之相關檔案或網站的 SharePoint 許可權所導致的結果。</span><span class="sxs-lookup"><span data-stu-id="128bf-144">For example, a topic with a lower quality score may be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="128bf-145">然後，參與者便可編輯主題，以在適當的) 中包含資訊 (，該主題將可供所有可查看該主題的使用者查看。</span><span class="sxs-lookup"><span data-stu-id="128bf-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="128bf-146">品質分數介於1到100。</span><span class="sxs-lookup"><span data-stu-id="128bf-146">The Quality score could range from 1 to 100.</span></span> <span data-ttu-id="128bf-147">新探索的主題會具有高品質分數0，直到兩位以上的使用者都已查看為止。</span><span class="sxs-lookup"><span data-stu-id="128bf-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="128bf-148">每個使用者的品質分數取決於許多因素，例如特定使用者顯示的內容數量，也就是針對特定使用者顯示的內容數量，可在每個主題頁面具有 AI 產生之內容的安全性修整時，控制使用者的許可權。</span><span class="sxs-lookup"><span data-stu-id="128bf-148">Each users quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="128bf-149">[建議的主題] 索引標籤上顯示的品質分數是各使用者的平均分數。</span><span class="sxs-lookup"><span data-stu-id="128bf-149">The Quality score shown on the Suggested topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="128bf-150">印象</span><span class="sxs-lookup"><span data-stu-id="128bf-150">Impressions</span></span>

<span data-ttu-id="128bf-151">「 <b>印記</b> 」欄會顯示主題向使用者顯示的次數。</span><span class="sxs-lookup"><span data-stu-id="128bf-151">The <b>Impressions</b> column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="128bf-152">這包括透過搜尋中的主題卡片、透過主題要聞及透過主題中心視圖的視圖。</span><span class="sxs-lookup"><span data-stu-id="128bf-152">This includes views through topic cards in search, through topic highlights, and through Topic center views.</span></span> <span data-ttu-id="128bf-153">它不會反映這些主題上的點擊式，但已顯示主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="128bf-154">[印象] 欄會顯示在 [管理主題] 頁面中建議、已確認、已發佈及已移除的索引標籤中的主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-154">The Impressions column will show for topics in the Suggested, Confirmed, Published, and Removed tabs in the Manage Topics page.</span></span>


## <a name="confirmed-topics"></a><span data-ttu-id="128bf-155">已確認主題</span><span class="sxs-lookup"><span data-stu-id="128bf-155">Confirmed topics</span></span>

<span data-ttu-id="128bf-156">在 [管理主題] 頁面上，在您指定的 SharePoint 來源位置中探索的主題，並已由兩個或多個透過卡片意見反應機制的人員確認的知識管理員或「具有相同」的主題，將會列于 [已 **確認** ] 索引標籤中。如有需要，具有管理主題許可權的使用者可以查看已確認的主題，並選擇拒絕這些主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-156">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="128bf-157">若要查看已確認的主題：</span><span class="sxs-lookup"><span data-stu-id="128bf-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="128bf-158">在 [已 **確認** ] 索引標籤上，選取主題，以開啟 [主題] 頁面。</span><span class="sxs-lookup"><span data-stu-id="128bf-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="128bf-159">在 [主題] 頁面上，複查 [主題] 頁面，如果您需要對頁面進行任何變更，請選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="128bf-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="128bf-160">請注意，您仍然可以選擇拒絕已確認的主題。</span><span class="sxs-lookup"><span data-stu-id="128bf-160">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="128bf-161">若要這樣做，請移至已確認清單中的選取主題，如果您想要拒絕該主題，請選取 **x** 。</span><span class="sxs-lookup"><span data-stu-id="128bf-161">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="128bf-162">已發佈主題</span><span class="sxs-lookup"><span data-stu-id="128bf-162">Published topics</span></span>
<span data-ttu-id="128bf-163">已發佈的主題已經過編輯，使特定資訊永遠會出現在頁面出現的任何處。</span><span class="sxs-lookup"><span data-stu-id="128bf-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="128bf-164">手動建立的主題也會列在這裡。</span><span class="sxs-lookup"><span data-stu-id="128bf-164">Manually created topics are listed here as well.</span></span>

   ![管理主題](../media/knowledge-management/manage-topics-new.png) </br>