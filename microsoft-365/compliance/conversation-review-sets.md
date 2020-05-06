---
title: 在高級電子檔探索中查看交談
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何使用「高級 eDiscovery」中的「交談重建」功能，重新構建、審閱及匯出執行緒交談。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 45cf4bdbf0956ee28e75878b7db5ec84b81c7230
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035491"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="0c684-103">在高級電子檔探索中查看交談</span><span class="sxs-lookup"><span data-stu-id="0c684-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="0c684-104">立即訊息是一種簡單的方法，可讓您在大型物件中提問、分享想法或快速交流。</span><span class="sxs-lookup"><span data-stu-id="0c684-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="0c684-105">當立即訊息平臺（如 Microsoft 小組）成為企業共同作業的核心時，組織必須評估其 eDiscovery 工作流程如何處理這些新的通訊和共同作業形式。</span><span class="sxs-lookup"><span data-stu-id="0c684-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="0c684-106">「高級 eDiscovery」中的交談重建功能是專門設計來協助您識別內容內容，並產生獨特的交談視圖。</span><span class="sxs-lookup"><span data-stu-id="0c684-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="0c684-107">這項功能可讓您有效且快速地查看平臺（如 Microsoft 團隊）中所產生的完整立即訊息交談（也稱為「*執行緒交談*」）。</span><span class="sxs-lookup"><span data-stu-id="0c684-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="0c684-108">透過交談重建，您可以使用內建的功能來重新建立、審閱及匯出執行緒交談。</span><span class="sxs-lookup"><span data-stu-id="0c684-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="0c684-109">使用高級 eDiscovery 交談重構來：</span><span class="sxs-lookup"><span data-stu-id="0c684-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="0c684-110">在交談內保留所有郵件的唯一郵件層級中繼資料。</span><span class="sxs-lookup"><span data-stu-id="0c684-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="0c684-111">收集搜尋結果周圍的上下文相關訊息。</span><span class="sxs-lookup"><span data-stu-id="0c684-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="0c684-112">審閱、批註和密文討論執行緒的交談。</span><span class="sxs-lookup"><span data-stu-id="0c684-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="0c684-113">匯出個別的郵件或串接的交談</span><span class="sxs-lookup"><span data-stu-id="0c684-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="0c684-114">術語</span><span class="sxs-lookup"><span data-stu-id="0c684-114">Terminology</span></span>

<span data-ttu-id="0c684-115">以下是很少的定義，可協助您開始使用交談重建。</span><span class="sxs-lookup"><span data-stu-id="0c684-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="0c684-116">**訊息：** 代表交談的最小單位。</span><span class="sxs-lookup"><span data-stu-id="0c684-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="0c684-117">郵件大小、結構及中繼資料可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="0c684-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="0c684-118">**交談：** 代表一或多個郵件的群組。</span><span class="sxs-lookup"><span data-stu-id="0c684-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="0c684-119">在不同的應用程式中，交談可能以不同的方式呈現。</span><span class="sxs-lookup"><span data-stu-id="0c684-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="0c684-120">在某些應用程式中，會有明確的動作，可回復現有的郵件。</span><span class="sxs-lookup"><span data-stu-id="0c684-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="0c684-121">交談是以此使用者動作的結果來明確地組成。</span><span class="sxs-lookup"><span data-stu-id="0c684-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="0c684-122">例如，以下是 Microsoft 小組中的頻道交談的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="0c684-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft 小組通道交談](../media/threadedchat.png)

   <span data-ttu-id="0c684-124">在其他應用程式中（例如，小組中的1xN 聊天室訊息），沒有正式的回復鏈，而郵件會顯示為單一線程中的「平面河郵件」。</span><span class="sxs-lookup"><span data-stu-id="0c684-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="0c684-125">在這些類型的應用程式中，對話會從一段時間內發生的一組訊息中推斷出。</span><span class="sxs-lookup"><span data-stu-id="0c684-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="0c684-126">這種郵件的「軟群組」（相對於回復鏈）代表相關特定主題的「前後」交談。</span><span class="sxs-lookup"><span data-stu-id="0c684-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="0c684-127">步驟1：執行搜尋</span><span class="sxs-lookup"><span data-stu-id="0c684-127">Step 1: Run a search</span></span>

<span data-ttu-id="0c684-128">在您識別相關的保管人和內容位置之後，您可以建立搜尋來尋找潛在的相關內容。</span><span class="sxs-lookup"><span data-stu-id="0c684-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="0c684-129">在 [高級 eDiscovery] 案例的 [**搜尋**] 索引標籤上，您可以按一下 [**新增搜尋**] 並依照嚮導來建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="0c684-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="0c684-130">如需如何建立搜尋、建立搜尋查詢及查看搜尋結果的詳細資訊，請參閱[收集案例的資料](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0c684-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="0c684-131">步驟2：建立交談複查集</span><span class="sxs-lookup"><span data-stu-id="0c684-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="0c684-132">在審閱集中，您可以搜尋、標記、批註和密文檔、電子郵件訊息和聊天交談。</span><span class="sxs-lookup"><span data-stu-id="0c684-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="0c684-133">在 [Advanced eDiscovery] 中，您可以根據個別郵件或串接交談，自訂您的交談評論。</span><span class="sxs-lookup"><span data-stu-id="0c684-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="0c684-134">這取決於您將在步驟1中建立之搜尋結果的結果新增至中的審查集類型。</span><span class="sxs-lookup"><span data-stu-id="0c684-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="0c684-135">有兩種不同的審閱集類型：</span><span class="sxs-lookup"><span data-stu-id="0c684-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="0c684-136">**標準檢查集合：** 交談中的郵件會經過處理並顯示為個別的專案。</span><span class="sxs-lookup"><span data-stu-id="0c684-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="0c684-137">**交談複查集：** 交談中的郵件會個別處理，但會顯示在交談視圖中。</span><span class="sxs-lookup"><span data-stu-id="0c684-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="0c684-138">在交談複查集中，您可以線上程交談模式中批註、標記和密文顯示郵件。</span><span class="sxs-lookup"><span data-stu-id="0c684-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="0c684-139">如需如何查看及管理審閱集中內容的詳細資訊，請參閱[管理審閱集](managing-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="0c684-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="0c684-140">步驟3：啟用交談檢索選項</span><span class="sxs-lookup"><span data-stu-id="0c684-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="0c684-141">在您檢查並完成搜尋查詢之後，您可以將搜尋結果新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="0c684-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="0c684-142">當您將搜尋結果新增至審閱集時，原始資料會複製到 Azure 儲存體區域，以協助檢查和分析程式。</span><span class="sxs-lookup"><span data-stu-id="0c684-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="0c684-143">如需將搜尋結果新增至審閱集合的詳細資訊，請參閱[將搜尋結果新增至審閱集](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="0c684-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="0c684-144">當您將資料從交談新增至審閱集時，您可以使用交談檢索選項來展開搜尋並包含內容相關訊息。</span><span class="sxs-lookup"><span data-stu-id="0c684-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="0c684-145">在您設定交談檢索選項後，可能會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="0c684-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![交談檢索](../media/messagesandconversations.png)
  
1. <span data-ttu-id="0c684-147">搜尋會使用關鍵字和日期範圍查詢，傳回*郵件 3*上的命中。</span><span class="sxs-lookup"><span data-stu-id="0c684-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="0c684-148">此郵件屬於較大的交談，如*CRC1*所示。</span><span class="sxs-lookup"><span data-stu-id="0c684-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="0c684-149">當您將資料新增至複查集並啟用交談檢索選項時，高級 eDiscovery 會傳回並收集*CRC1*中的其他專案。</span><span class="sxs-lookup"><span data-stu-id="0c684-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="0c684-150">將專案新增至審閱集合之後，您可以從*CRC1*審閱所有的個別郵件。</span><span class="sxs-lookup"><span data-stu-id="0c684-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="0c684-151">啟用交談檢索：</span><span class="sxs-lookup"><span data-stu-id="0c684-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="0c684-152">在 [高級 eDiscovery] 案例中的 [**搜尋**] 索引標籤上，選取搜尋，然後按一下彈出頁面上的 [**新增至審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="0c684-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="0c684-153">選取現有的複查集或建立一個複查集。</span><span class="sxs-lookup"><span data-stu-id="0c684-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="0c684-154">將搜尋結果新增至標準或交談複查集時，您可以設定檢索選項。</span><span class="sxs-lookup"><span data-stu-id="0c684-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="0c684-155">在 [**集合選項**] 底下，針對您想要展開的搜尋內容來源，設定其交談檢索選項，然後按一下 [**新增**] 以啟動程式。</span><span class="sxs-lookup"><span data-stu-id="0c684-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="0c684-156">在 [**工作**] 索引標籤上的 [**新增至審閱集**] 工作完成之後，您就可以開始查看交談。</span><span class="sxs-lookup"><span data-stu-id="0c684-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="0c684-157">步驟4：在審閱集中複查及匯出對話</span><span class="sxs-lookup"><span data-stu-id="0c684-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="0c684-158">在處理內容並將其新增至審閱集合之後，您可以開始查看審閱集中的資料。</span><span class="sxs-lookup"><span data-stu-id="0c684-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="0c684-159">檢查功能會因內容是否已新增至標準審閱集或交談複查集而有所不同。</span><span class="sxs-lookup"><span data-stu-id="0c684-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="0c684-160">在標準複查集中檢查交談</span><span class="sxs-lookup"><span data-stu-id="0c684-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="0c684-161">在標準的審閱集中，郵件會以個別專案的方式處理及顯示，類似于如何儲存在信箱資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0c684-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="0c684-162">在此工作流程中，會以個別的專案處理每封郵件。</span><span class="sxs-lookup"><span data-stu-id="0c684-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="0c684-163">因此，標準的審閱集中無法使用「串接摘要」和「匯出」選項。</span><span class="sxs-lookup"><span data-stu-id="0c684-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![標準複查集](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="0c684-165">在交談評審集中檢查交談</span><span class="sxs-lookup"><span data-stu-id="0c684-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="0c684-166">在交談複查集中，個別郵件會串接在一起，並以交談方式呈現。</span><span class="sxs-lookup"><span data-stu-id="0c684-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="0c684-167">這可讓您複查及匯出內容交談。</span><span class="sxs-lookup"><span data-stu-id="0c684-167">This lets you review and export contextual conversations.</span></span> 

  ![交談複查集](../media/ConversationRSOptions.PNG)

<span data-ttu-id="0c684-169">下列各節說明如何在交談複查集中複查和匯出對話。</span><span class="sxs-lookup"><span data-stu-id="0c684-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="0c684-170">審閱交談</span><span class="sxs-lookup"><span data-stu-id="0c684-170">Reviewing conversations</span></span>

<span data-ttu-id="0c684-171">在交談複查集中，您可以使用下列選項來協助審閱程式。</span><span class="sxs-lookup"><span data-stu-id="0c684-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="0c684-172">**依交談群組：** 將相同交談中的郵件分組，以協助使用者簡化及加速其審閱程式。</span><span class="sxs-lookup"><span data-stu-id="0c684-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="0c684-173">**摘要視圖：** 顯示「執行緒交談」。</span><span class="sxs-lookup"><span data-stu-id="0c684-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="0c684-174">在此視圖中，您可以看見整個交談，也可以存取每個個別郵件的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="0c684-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="0c684-175">查看個別郵件的中繼資料</span><span class="sxs-lookup"><span data-stu-id="0c684-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="0c684-176">下載個別郵件</span><span class="sxs-lookup"><span data-stu-id="0c684-176">Download individual messages</span></span>

- <span data-ttu-id="0c684-177">**文字視圖：** 會提供整個交談的解壓縮文字。</span><span class="sxs-lookup"><span data-stu-id="0c684-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="0c684-178">**批註視圖：** 可讓您標記交談的執行緒化視圖。</span><span class="sxs-lookup"><span data-stu-id="0c684-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="0c684-179">交談中的所有郵件都會共用相同的註釋檔。</span><span class="sxs-lookup"><span data-stu-id="0c684-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="0c684-180">**標記：** 在審閱集中查看交談時，您可以按一下 [編碼] 面板中的 [**標記] 面板**，以查看及套用標記。</span><span class="sxs-lookup"><span data-stu-id="0c684-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="0c684-181">**重新執行交談轉換：** 當郵件新增至交談複查集時，會自動執行轉換工作以建立執行緒摘要及批註視圖。</span><span class="sxs-lookup"><span data-stu-id="0c684-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="0c684-182">如果交談重建工作失敗，您可以按一下 [動作] 以執行 [複查] 集中的 [**動作] > 建立交談 pdf** ，以重新執行此工作。</span><span class="sxs-lookup"><span data-stu-id="0c684-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="0c684-183">匯出對話</span><span class="sxs-lookup"><span data-stu-id="0c684-183">Exporting conversations</span></span>

<span data-ttu-id="0c684-184">在交談複查集中，您可以設定下列選項來匯出對話：</span><span class="sxs-lookup"><span data-stu-id="0c684-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![匯出](../media/export.png)

<span data-ttu-id="0c684-186">a.</span><span class="sxs-lookup"><span data-stu-id="0c684-186">a.</span></span> <span data-ttu-id="0c684-187">中繼資料選項</span><span class="sxs-lookup"><span data-stu-id="0c684-187">Metadata options</span></span>

   - <span data-ttu-id="0c684-188">**載入檔案：** 每個個別的郵件、電子郵件及檔都包含中繼資料。</span><span class="sxs-lookup"><span data-stu-id="0c684-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="0c684-189">交談中的每一封郵件都有一個資料列。</span><span class="sxs-lookup"><span data-stu-id="0c684-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="0c684-190">**標記：** 您的審閱程式中的標記會包含在中繼資料檔案中。</span><span class="sxs-lookup"><span data-stu-id="0c684-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="0c684-191">交談中的郵件共用相同的標記。</span><span class="sxs-lookup"><span data-stu-id="0c684-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="0c684-192">b.</span><span class="sxs-lookup"><span data-stu-id="0c684-192">b.</span></span> <span data-ttu-id="0c684-193">交談選項</span><span class="sxs-lookup"><span data-stu-id="0c684-193">Conversation options</span></span>
  
   - <span data-ttu-id="0c684-194">**交談檔案：** 當您匯出對話檔時，批註的視圖會轉換為 PDF 檔案，並下載至匯出資料夾。</span><span class="sxs-lookup"><span data-stu-id="0c684-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="0c684-195">一個交談檔案中的郵件指向相同交談檔案的 PDF 版本。</span><span class="sxs-lookup"><span data-stu-id="0c684-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="0c684-196">**個別聊天訊息：** 當您匯出個別郵件時，交談中的每個唯一郵件都會匯出為獨立的專案。</span><span class="sxs-lookup"><span data-stu-id="0c684-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="0c684-197">檔會以儲存為信箱的相同格式匯出。</span><span class="sxs-lookup"><span data-stu-id="0c684-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="0c684-198">針對特定交談，您會收到多個 .msg 檔案。</span><span class="sxs-lookup"><span data-stu-id="0c684-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="0c684-199">如果您已將批註套用至交談檔案，這些批註將不會轉移到個別的郵件。</span><span class="sxs-lookup"><span data-stu-id="0c684-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="0c684-200">c.</span><span class="sxs-lookup"><span data-stu-id="0c684-200">c.</span></span> <span data-ttu-id="0c684-201">其他選項</span><span class="sxs-lookup"><span data-stu-id="0c684-201">Other options</span></span>

   - <span data-ttu-id="0c684-202">**為所有匯出的內容產生文字檔：** 為從審閱集匯出的每個交談產生一個文字檔。</span><span class="sxs-lookup"><span data-stu-id="0c684-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="0c684-203">**以 Redacted Pdf 取代匯出的內容：** 如果在複查程式期間產生 redacted 交談檔案，則匯出期間可使用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="0c684-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="0c684-204">您可以決定是否只匯出原生檔案（不要選取這個選項），或是以原生檔案的 redacted 版本（選取此選項）取代原生檔案（這會匯出為 PDF 檔案）。</span><span class="sxs-lookup"><span data-stu-id="0c684-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="0c684-205">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0c684-205">More information</span></span>

<span data-ttu-id="0c684-206">若要深入瞭解如何在高級 eDiscovery 中查看案例資料，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="0c684-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="0c684-207">查看案例資料</span><span class="sxs-lookup"><span data-stu-id="0c684-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="0c684-208">分析案例資料</span><span class="sxs-lookup"><span data-stu-id="0c684-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="0c684-209">匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="0c684-209">Export case data</span></span>](exporting-data-ediscover20.md)
