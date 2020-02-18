---
title: 檢閱在進階電子文件中的交談
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
description: ''
ms.openlocfilehash: 01f2e6f9ceccd1903f62e8661f2cfc8f4cc2b47e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078115"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="80452-102">檢閱在進階電子文件中的交談</span><span class="sxs-lookup"><span data-stu-id="80452-102">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="80452-103">立即訊息是提問、 分享想法，或跨大型對象快速通訊便利方式。</span><span class="sxs-lookup"><span data-stu-id="80452-103">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="80452-104">為立即訊息平台，例如 Microsoft Teams，成為企業共同作業的核心，組織必須評估其的 eDiscovery 工作流程如何解決這些新的表單的通訊和共同作業。</span><span class="sxs-lookup"><span data-stu-id="80452-104">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="80452-105">進階電子文件中的交談重建功能被設計來協助您識別內容相關的內容，並產生不同的交談檢視。</span><span class="sxs-lookup"><span data-stu-id="80452-105">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="80452-106">這項功能可讓您有效地和快速檢閱完整的立即訊息對話 （也稱為*執行緒模式下執行交談*） 而產生的平台像是 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="80452-106">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="80452-107">與交談重建，您可以使用內建功能來重建、 進行檢閱，以及匯出執行緒的交談。</span><span class="sxs-lookup"><span data-stu-id="80452-107">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="80452-108">使用進階電子文件交談重建來：</span><span class="sxs-lookup"><span data-stu-id="80452-108">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="80452-109">保留唯一郵件層級中繼資料內交談的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="80452-109">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="80452-110">收集周圍您的搜尋結果的內容相關訊息。</span><span class="sxs-lookup"><span data-stu-id="80452-110">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="80452-111">檢閱、 加上註解，並 redact 執行緒的交談。</span><span class="sxs-lookup"><span data-stu-id="80452-111">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="80452-112">匯出個別郵件或執行緒的交談</span><span class="sxs-lookup"><span data-stu-id="80452-112">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="80452-113">術語</span><span class="sxs-lookup"><span data-stu-id="80452-113">Terminology</span></span>

<span data-ttu-id="80452-114">以下是一些定義，以協助您開始使用交談重建。</span><span class="sxs-lookup"><span data-stu-id="80452-114">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="80452-115">**郵件：** 代表交談的最小單位。</span><span class="sxs-lookup"><span data-stu-id="80452-115">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="80452-116">在大小、 結構和中繼資料，郵件可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="80452-116">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="80452-117">**交談：** 代表一個或多封郵件的群組。</span><span class="sxs-lookup"><span data-stu-id="80452-117">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="80452-118">跨不同的應用程式，可能會不同的方式表示交談。</span><span class="sxs-lookup"><span data-stu-id="80452-118">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="80452-119">某些應用程式，在沒有明確的動作所產生的回覆至現有的郵件。</span><span class="sxs-lookup"><span data-stu-id="80452-119">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="80452-120">交談是明確地形成，由於此使用者動作。</span><span class="sxs-lookup"><span data-stu-id="80452-120">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="80452-121">例如，以下是在 Microsoft Teams 的通道交談的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="80452-121">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams 通道交談](../media/threadedchat.png)

   <span data-ttu-id="80452-123">在其他應用程式 （例如 teams 1xN 聊天訊息），並沒有正式回覆鏈結，改為郵件顯示為 「 平面河的郵件 」 的單一執行緒內。</span><span class="sxs-lookup"><span data-stu-id="80452-123">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="80452-124">在這些類型的應用程式，從一群發生在特定時間內的郵件會推斷交談。</span><span class="sxs-lookup"><span data-stu-id="80452-124">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="80452-125">這個 「 虛群組 」 的郵件 （而非回覆鏈結） 代表 「 往返 」 交談相關的特定主題感興趣。</span><span class="sxs-lookup"><span data-stu-id="80452-125">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="80452-126">步驟 1： 執行搜尋</span><span class="sxs-lookup"><span data-stu-id="80452-126">Step 1: Run a search</span></span>

<span data-ttu-id="80452-127">識別相關 custodians 和內容位置之後，您可以建立搜尋，以尋找潛在相關的內容。</span><span class="sxs-lookup"><span data-stu-id="80452-127">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="80452-128">進階電子文件探索案例中的 [**搜尋**] 索引標籤，您可以按一下 [**新增搜尋**，並遵循精靈建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="80452-128">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="80452-129">如需如何建立搜尋，建置搜尋查詢，和檢視搜尋結果，請參閱[收集資料的大小寫](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="80452-129">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="80452-130">步驟 2： 建立交談檢閱設定</span><span class="sxs-lookup"><span data-stu-id="80452-130">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="80452-131">檢閱集中，您可以搜尋、 標記、 加上註解，以及 redact 文件、 電子郵件訊息和聊天交談。</span><span class="sxs-lookup"><span data-stu-id="80452-131">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="80452-132">在 [進階電子文件，您可以自訂交談、 根據中的個別郵件或執行緒的交談的檢閱。</span><span class="sxs-lookup"><span data-stu-id="80452-132">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="80452-133">這取決於檢閱集的類型，您將新增至步驟 1 中建立的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="80452-133">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="80452-134">有兩種不同檢閱設定：</span><span class="sxs-lookup"><span data-stu-id="80452-134">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="80452-135">**標準檢閱設定：** 在交談中的郵件會處理，並顯示為個別項目。</span><span class="sxs-lookup"><span data-stu-id="80452-135">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="80452-136">**交談檢閱設定：** 交談中的郵件會個別處理，但顯示在 [交談] 檢視中。</span><span class="sxs-lookup"><span data-stu-id="80452-136">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="80452-137">交談中檢閱設定，您可以加上註解、 標記，redact 執行緒的交談] 檢視中的郵件。</span><span class="sxs-lookup"><span data-stu-id="80452-137">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="80452-138">如需如何檢閱，以及管理內容中檢閱設定，請參閱[管理檢閱設定](managing-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="80452-138">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="80452-139">步驟 3： 啟用交談擷取選項</span><span class="sxs-lookup"><span data-stu-id="80452-139">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="80452-140">您已檢閱並完成您的搜尋查詢之後，您可以檢閱組新增搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="80452-140">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="80452-141">當您新增您的搜尋結果成檢閱集時，原始的資料會複製到 Azure 儲存體區域，以利檢閱和分析處理程序。</span><span class="sxs-lookup"><span data-stu-id="80452-141">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="80452-142">如需有關將搜尋結果新增至檢閱設定，請參閱[新增搜尋結果，以檢閱設定](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="80452-142">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="80452-143">當您從交談中新增資料，檢閱設定時，您可以使用交談擷取選項擴大搜尋範圍，並將包含內容相關訊息。</span><span class="sxs-lookup"><span data-stu-id="80452-143">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="80452-144">設定交談擷取選項之後，可以發生下列情形：</span><span class="sxs-lookup"><span data-stu-id="80452-144">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![交談擷取](../media/messagesandconversations.png)
  
1. <span data-ttu-id="80452-146">使用關鍵字和日期範圍查詢，搜尋所傳回落點的*訊息 3*。</span><span class="sxs-lookup"><span data-stu-id="80452-146">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="80452-147">此郵件為較大的交談， *CRC1*所說明的一部分。</span><span class="sxs-lookup"><span data-stu-id="80452-147">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="80452-148">當您新增資料至檢閱設定並啟用交談擷取選項時，將會回復進階電子文件，並收集*CRC1*中的其他項目。</span><span class="sxs-lookup"><span data-stu-id="80452-148">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="80452-149">項目已新增至檢閱設定之後，您可以檢閱來自*CRC1*的所有個別郵件。</span><span class="sxs-lookup"><span data-stu-id="80452-149">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 



<span data-ttu-id="80452-150">若要啟用交談擷取：</span><span class="sxs-lookup"><span data-stu-id="80452-150">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="80452-151">進階電子文件探索案例的 [**搜尋**] 索引標籤上選擇 [搜尋]，，然後按一下彈出式頁面上的 [**新增]，檢閱設定**。</span><span class="sxs-lookup"><span data-stu-id="80452-151">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="80452-152">選取現有的檢閱設定或建立檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="80452-152">Select an existing review set or create a review set.</span></span> <span data-ttu-id="80452-153">新增搜尋結果，以 standard 或交談檢閱設定時，您可以設定擷取選項。</span><span class="sxs-lookup"><span data-stu-id="80452-153">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="80452-154">[**集合選項**] 下設定您要在搜尋中，依序展開 [內容來源的交談擷取選項，然後按一下 [**新增**] 以開始程序。</span><span class="sxs-lookup"><span data-stu-id="80452-154">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="80452-155">在 [**工作**] 索引標籤上的 [**新增]，檢閱設定**工作已完成之後，您可以開始檢閱交談。</span><span class="sxs-lookup"><span data-stu-id="80452-155">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-conversations-in-the-review-set"></a><span data-ttu-id="80452-156">步驟 4： 檢閱檢閱組中的交談</span><span class="sxs-lookup"><span data-stu-id="80452-156">Step 4: Review conversations in the review set</span></span>

<span data-ttu-id="80452-157">已處理並新增至檢閱組內容之後，您可以開始檢閱檢閱集中的資料。</span><span class="sxs-lookup"><span data-stu-id="80452-157">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="80452-158">檢閱功能會根據是否內容已新增至標準檢閱組或交談檢閱集不同。</span><span class="sxs-lookup"><span data-stu-id="80452-158">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="80452-159">檢閱交談標準中的檢閱設定</span><span class="sxs-lookup"><span data-stu-id="80452-159">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="80452-160">標準中檢閱設定，郵件會處理並顯示為個別項目，類似於如何依據儲存在信箱資料夾。</span><span class="sxs-lookup"><span data-stu-id="80452-160">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="80452-161">在此工作流程，做為個別的項目處理每個訊息。</span><span class="sxs-lookup"><span data-stu-id="80452-161">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="80452-162">因此，執行緒的摘要和匯出選項無法使用標準檢閱集合中。</span><span class="sxs-lookup"><span data-stu-id="80452-162">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![標準檢閱設定](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="80452-164">檢閱在交談檢閱交談設定</span><span class="sxs-lookup"><span data-stu-id="80452-164">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="80452-165">交談中檢閱設定，個別的郵件都會一起執行緒，並當作交談來呈現。</span><span class="sxs-lookup"><span data-stu-id="80452-165">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="80452-166">這可讓您檢視及匯出內容相關的交談。</span><span class="sxs-lookup"><span data-stu-id="80452-166">This lets you review and export contextual conversations.</span></span> 

  ![交談檢閱設定](../media/ConversationRSOptions.PNG)

<span data-ttu-id="80452-168">下列各節說明檢閱和匯出交談檢閱集合中的交談。</span><span class="sxs-lookup"><span data-stu-id="80452-168">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="80452-169">檢閱交談</span><span class="sxs-lookup"><span data-stu-id="80452-169">Reviewing conversations</span></span>

<span data-ttu-id="80452-170">在交談中檢閱設定，您可以使用下列選項以利檢閱程序。</span><span class="sxs-lookup"><span data-stu-id="80452-170">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="80452-171">**依交談群組：** 群組內相同對話訊息一起可協助簡化並加速其檢閱程序的使用者。</span><span class="sxs-lookup"><span data-stu-id="80452-171">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="80452-172">**摘要檢視：** 會顯示執行緒的交談。</span><span class="sxs-lookup"><span data-stu-id="80452-172">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="80452-173">在此檢視中，您可以看見整個交談，並也存取每個個別訊息的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="80452-173">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="80452-174">檢視個別郵件的中繼資料</span><span class="sxs-lookup"><span data-stu-id="80452-174">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="80452-175">下載個別郵件</span><span class="sxs-lookup"><span data-stu-id="80452-175">Download individual messages</span></span>

- <span data-ttu-id="80452-176">**文字檢視：** 提供整個交談的擷取的文字。</span><span class="sxs-lookup"><span data-stu-id="80452-176">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="80452-177">**加上註解檢視：** 可讓您標記的對話執行緒檢視。</span><span class="sxs-lookup"><span data-stu-id="80452-177">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="80452-178">交談中的所有郵件會都共用相同的註解文件。</span><span class="sxs-lookup"><span data-stu-id="80452-178">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="80452-179">**標記：** 檢視時交談中檢閱設定，您可以檢視及套用標籤的 [編碼] 面板中的 [**標記] 面板**。</span><span class="sxs-lookup"><span data-stu-id="80452-179">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="80452-180">**重新執行交談轉換：** 當郵件新增至交談檢閱設定時，轉換執行作業時自動建立執行緒的摘要，並加上註解的檢視。</span><span class="sxs-lookup"><span data-stu-id="80452-180">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="80452-181">如果交談重建作業失敗時，您可以檢閱集合中的 [**巨集指令 > 建立交談 Pdf**重新執行此工作。</span><span class="sxs-lookup"><span data-stu-id="80452-181">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>


#### <a name="exporting-conversations"></a><span data-ttu-id="80452-182">匯出的交談</span><span class="sxs-lookup"><span data-stu-id="80452-182">Exporting conversations</span></span>

<span data-ttu-id="80452-183">在交談中檢閱設定，您可以設定下列選項來匯出交談：</span><span class="sxs-lookup"><span data-stu-id="80452-183">In a conversation review set, you can set the following options to export conversations:</span></span>

![匯出](../media/export.png)

<span data-ttu-id="80452-185">a.</span><span class="sxs-lookup"><span data-stu-id="80452-185">a.</span></span> <span data-ttu-id="80452-186">中繼資料] 選項</span><span class="sxs-lookup"><span data-stu-id="80452-186">Metadata options</span></span>

   - <span data-ttu-id="80452-187">**載入檔案：** 包含每個個別訊息、 電子郵件和文件中繼資料。</span><span class="sxs-lookup"><span data-stu-id="80452-187">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="80452-188">沒有對話中的每一封郵件的一列。</span><span class="sxs-lookup"><span data-stu-id="80452-188">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="80452-189">**標記：** 從您檢閱程序的標記會包含在中繼資料檔案。</span><span class="sxs-lookup"><span data-stu-id="80452-189">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="80452-190">交談中的郵件會共用相同的標籤。</span><span class="sxs-lookup"><span data-stu-id="80452-190">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="80452-191">b.</span><span class="sxs-lookup"><span data-stu-id="80452-191">b.</span></span> <span data-ttu-id="80452-192">對話選項</span><span class="sxs-lookup"><span data-stu-id="80452-192">Conversation options</span></span>
  
   - <span data-ttu-id="80452-193">**交談檔案：** 當您匯出交談檔案時，有註解的檢視轉換成 PDF 檔案，並下載至 [匯出] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="80452-193">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="80452-194">PDF 版本的同一個交談檔案指向一個交談檔案中的郵件。</span><span class="sxs-lookup"><span data-stu-id="80452-194">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="80452-195">**個別聊天訊息：** 當您匯出個別郵件時，交談中每個唯一的郵件會匯出為獨立的項目。</span><span class="sxs-lookup"><span data-stu-id="80452-195">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="80452-196">檔案會儲存如信箱所示的相同格式匯出。</span><span class="sxs-lookup"><span data-stu-id="80452-196">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="80452-197">針對特定的交談，您會收到多個.msg 檔案。</span><span class="sxs-lookup"><span data-stu-id="80452-197">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="80452-198">如果您套用至交談檔案的註釋，這些註釋不會傳輸至個別郵件。</span><span class="sxs-lookup"><span data-stu-id="80452-198">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="80452-199">c.</span><span class="sxs-lookup"><span data-stu-id="80452-199">c.</span></span> <span data-ttu-id="80452-200">其他選項</span><span class="sxs-lookup"><span data-stu-id="80452-200">Other options</span></span>

   - <span data-ttu-id="80452-201">**產生所有匯出內容的文字檔：** 會產生匯出檢閱組中每個交談的文字檔案。</span><span class="sxs-lookup"><span data-stu-id="80452-201">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="80452-202">**取代匯出內容與 redacted Pdf:** 如果檢閱程序期間產生 redacted 的交談檔案，然後這些檔案可在匯出期間。</span><span class="sxs-lookup"><span data-stu-id="80452-202">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="80452-203">您可以決定是否要匯出只有的原生檔案 （未選取此選項） 或以的原生檔案 （藉由選取此選項），這會匯出為 PDF 檔案 redacted 版本取代的原生檔案。</span><span class="sxs-lookup"><span data-stu-id="80452-203">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="80452-204">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="80452-204">More information</span></span>

<span data-ttu-id="80452-205">若要深入了解如何檢閱進階電子文件中的案例資料，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="80452-205">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="80452-206">檢視案例資料</span><span class="sxs-lookup"><span data-stu-id="80452-206">View case data</span></span>](view-documents-in-review-set.md) 

- [<span data-ttu-id="80452-207">分析案例資料</span><span class="sxs-lookup"><span data-stu-id="80452-207">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="80452-208">匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="80452-208">Export case data</span></span>](exporting-data-ediscover20.md)
