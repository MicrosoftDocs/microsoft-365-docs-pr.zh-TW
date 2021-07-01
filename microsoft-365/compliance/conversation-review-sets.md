---
title: 在 Advanced eDiscovery 中查看交談
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 深入瞭解 Advanced eDiscovery (中的交談重新構建功能) ，以在 Microsoft Teams 及 Yammer 群組中重新構建、審閱及匯出聊天交談。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227184"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="61c98-103">Advanced eDiscovery 中的交談執行緒</span><span class="sxs-lookup"><span data-stu-id="61c98-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="61c98-104">立即訊息是一種簡單的方法，可讓您在大型物件中提問、分享想法或快速交流。</span><span class="sxs-lookup"><span data-stu-id="61c98-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="61c98-105">在立即訊息平臺（如 Microsoft Teams 和 Yammer 群組），變成企業共同作業的核心，組織必須評估其 eDiscovery 工作流程如何處理這些新的通訊和共同作業形式。</span><span class="sxs-lookup"><span data-stu-id="61c98-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="61c98-106">Advanced eDiscovery 中的交談重建功能是專門用來協助您識別內容內容，並產生獨特的交談視圖。</span><span class="sxs-lookup"><span data-stu-id="61c98-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="61c98-107">這項功能可讓您有效且快速地查看完整的立即訊息交談 (也稱為像是在平臺等平臺中所產生的 *執行緒交談*) Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="61c98-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="61c98-108">透過交談重建，您可以使用內建的功能來重新建立、審閱及匯出執行緒交談。</span><span class="sxs-lookup"><span data-stu-id="61c98-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="61c98-109">使用 Advanced eDiscovery 交談重建來：</span><span class="sxs-lookup"><span data-stu-id="61c98-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="61c98-110">在交談內保留所有郵件的唯一郵件層級中繼資料。</span><span class="sxs-lookup"><span data-stu-id="61c98-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="61c98-111">收集搜尋結果周圍的上下文相關訊息。</span><span class="sxs-lookup"><span data-stu-id="61c98-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="61c98-112">審閱、批註和密文討論執行緒的交談。</span><span class="sxs-lookup"><span data-stu-id="61c98-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="61c98-113">匯出個別的郵件或串接的交談</span><span class="sxs-lookup"><span data-stu-id="61c98-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="61c98-114">術語</span><span class="sxs-lookup"><span data-stu-id="61c98-114">Terminology</span></span>

<span data-ttu-id="61c98-115">以下是很少的定義，可協助您開始使用交談重建。</span><span class="sxs-lookup"><span data-stu-id="61c98-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="61c98-116">**訊息：** 代表交談的最小單位。</span><span class="sxs-lookup"><span data-stu-id="61c98-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="61c98-117">郵件大小、結構及中繼資料可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="61c98-117">Messages may vary in size, structure, and metadata.</span></span>

- <span data-ttu-id="61c98-118">**交談：** 代表一或多個郵件的群組。</span><span class="sxs-lookup"><span data-stu-id="61c98-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="61c98-119">在不同的應用程式中，交談可能以不同的方式呈現。</span><span class="sxs-lookup"><span data-stu-id="61c98-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="61c98-120">在某些應用程式中，會有明確的動作，可回復現有的郵件。</span><span class="sxs-lookup"><span data-stu-id="61c98-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="61c98-121">交談是以此使用者動作的結果來明確地組成。</span><span class="sxs-lookup"><span data-stu-id="61c98-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="61c98-122">例如，以下是 Microsoft Teams 中的通道交談的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="61c98-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams通道交談](../media/threadedchat.png)

   <span data-ttu-id="61c98-124">在其他應用程式中 (例如 Teams) 中的1xN 聊天室訊息，沒有正式的回復鏈，而郵件會顯示為單一線程中的「平面河郵件」。</span><span class="sxs-lookup"><span data-stu-id="61c98-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="61c98-125">在這些類型的應用程式中，對話會從一段時間內發生的一組訊息中推斷出。</span><span class="sxs-lookup"><span data-stu-id="61c98-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="61c98-126">「軟群組」郵件的 (相對於回復鏈) 代表相關主題的「前後」交談。</span><span class="sxs-lookup"><span data-stu-id="61c98-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="61c98-127">步驟1：建立草稿集合</span><span class="sxs-lookup"><span data-stu-id="61c98-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="61c98-128">在您識別相關的保管人和內容位置之後，您可以建立搜尋來尋找潛在的相關內容。</span><span class="sxs-lookup"><span data-stu-id="61c98-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="61c98-129">在 Advanced eDiscovery 案例中的 [**集合**] 索引標籤上，您可以按一下 [**新增集合**] 並遵循該嚮導來建立集合。</span><span class="sxs-lookup"><span data-stu-id="61c98-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="61c98-130">如需如何建立集合、建立搜尋查詢及預覽搜尋結果的詳細資訊，請參閱 [建立草稿收集](create-draft-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="61c98-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="61c98-131">步驟2：將草稿集合認可為審閱集</span><span class="sxs-lookup"><span data-stu-id="61c98-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="61c98-132">在集合中檢查並完成搜尋查詢之後，您可以將搜尋結果新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="61c98-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="61c98-133">當您將搜尋結果新增至審閱集時，原始資料會複製到 Azure 儲存體區域，以協助審閱及分析程式。</span><span class="sxs-lookup"><span data-stu-id="61c98-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="61c98-134">如需將搜尋結果新增至審閱集合的詳細資訊，請參閱 [認可 a 草稿集合至審閱集](commit-draft-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="61c98-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="61c98-135">當您將專案從交談新增至審閱集時，您可以使用 [執行緒交談] 選項，從交談中收集包含符合集合之搜尋準則之專案的上下文中郵件。</span><span class="sxs-lookup"><span data-stu-id="61c98-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="61c98-136">選取 [執行緒交談] 選項後，可能會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="61c98-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![交談檢索](../media/messagesandconversations.png)

1. <span data-ttu-id="61c98-138">搜尋會使用關鍵字和日期範圍查詢，傳回 *郵件 3* 上的命中。</span><span class="sxs-lookup"><span data-stu-id="61c98-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="61c98-139">此郵件屬於較大的交談，如 *CRC1* 所示。</span><span class="sxs-lookup"><span data-stu-id="61c98-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>

2. <span data-ttu-id="61c98-140">當您將資料新增至複查集並啟用交談檢索選項時，Advanced eDiscovery 會傳回並收集 *CRC1* 中的其他專案。</span><span class="sxs-lookup"><span data-stu-id="61c98-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>

3. <span data-ttu-id="61c98-141">將專案新增至審閱集合之後，您可以從 *CRC1* 審閱所有的個別郵件。</span><span class="sxs-lookup"><span data-stu-id="61c98-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="61c98-142">若要啟用 [執行緒交談] 選項，請參閱 [認可 a 草稿集合至審閱集](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)。</span><span class="sxs-lookup"><span data-stu-id="61c98-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>

## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="61c98-143">步驟3：審閱及匯出對話交談</span><span class="sxs-lookup"><span data-stu-id="61c98-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="61c98-144">在處理內容並將其新增至審閱集合之後，您可以開始查看審閱集中的資料。</span><span class="sxs-lookup"><span data-stu-id="61c98-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="61c98-145">檢查功能會因內容是否已新增至標準審閱集或交談複查集而有所不同。</span><span class="sxs-lookup"><span data-stu-id="61c98-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="61c98-146">在標準複查集中檢查交談</span><span class="sxs-lookup"><span data-stu-id="61c98-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="61c98-147">在標準的審閱集中，郵件會以個別專案的方式處理及顯示，類似于如何儲存在信箱資料夾中。</span><span class="sxs-lookup"><span data-stu-id="61c98-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="61c98-148">在此工作流程中，會以個別的專案處理每封郵件。</span><span class="sxs-lookup"><span data-stu-id="61c98-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="61c98-149">因此，標準的審閱集中無法使用「串接摘要」和「匯出」選項。</span><span class="sxs-lookup"><span data-stu-id="61c98-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![標準複查集](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="61c98-151">在交談評審集中檢查交談</span><span class="sxs-lookup"><span data-stu-id="61c98-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="61c98-152">在交談複查集中，個別郵件會串接在一起，並以交談方式呈現。</span><span class="sxs-lookup"><span data-stu-id="61c98-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="61c98-153">這可讓您複查及匯出內容交談。</span><span class="sxs-lookup"><span data-stu-id="61c98-153">This lets you review and export contextual conversations.</span></span>

  ![交談複查集](../media/ConversationRSOptions.PNG)

<span data-ttu-id="61c98-155">下列各節說明如何在交談複查集中複查和匯出對話。</span><span class="sxs-lookup"><span data-stu-id="61c98-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="61c98-156">審閱交談</span><span class="sxs-lookup"><span data-stu-id="61c98-156">Reviewing conversations</span></span>

<span data-ttu-id="61c98-157">在交談複查集中，您可以使用下列選項來協助審閱程式。</span><span class="sxs-lookup"><span data-stu-id="61c98-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="61c98-158">**依交談群組：** 將相同交談中的郵件分組，以協助使用者簡化及加速其審閱程式。</span><span class="sxs-lookup"><span data-stu-id="61c98-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="61c98-159">**摘要視圖：** 顯示「執行緒交談」。</span><span class="sxs-lookup"><span data-stu-id="61c98-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="61c98-160">在此視圖中，您可以看見整個交談，也可以存取每個個別郵件的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="61c98-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>

   - <span data-ttu-id="61c98-161">查看個別郵件的中繼資料</span><span class="sxs-lookup"><span data-stu-id="61c98-161">View metadata for individual messages</span></span>

   - <span data-ttu-id="61c98-162">下載個別郵件</span><span class="sxs-lookup"><span data-stu-id="61c98-162">Download individual messages</span></span>

- <span data-ttu-id="61c98-163">**文字視圖：** 會提供整個交談的解壓縮文字。</span><span class="sxs-lookup"><span data-stu-id="61c98-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="61c98-164">**批註視圖：** 可讓您標記交談的執行緒化視圖。</span><span class="sxs-lookup"><span data-stu-id="61c98-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="61c98-165">交談中的所有郵件都會共用相同的註釋檔。</span><span class="sxs-lookup"><span data-stu-id="61c98-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="61c98-166">**標記：** 在審閱集中查看交談時，您可以按一下 [編碼] 面板中的 [ **標記] 面板** ，以查看及套用標記。</span><span class="sxs-lookup"><span data-stu-id="61c98-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="61c98-167">**重新執行交談轉換：** 當郵件新增至交談複查集時，會自動執行轉換工作以建立執行緒摘要及批註視圖。</span><span class="sxs-lookup"><span data-stu-id="61c98-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="61c98-168">如果交談重建工作失敗，您可以按一下 [動作] 以執行 [複查] 集中的 [ **動作] > 建立交談 pdf** ，以重新執行此工作。</span><span class="sxs-lookup"><span data-stu-id="61c98-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="61c98-169">匯出對話</span><span class="sxs-lookup"><span data-stu-id="61c98-169">Exporting conversations</span></span>

<span data-ttu-id="61c98-170">在交談複查集中，您可以設定下列選項來匯出對話：</span><span class="sxs-lookup"><span data-stu-id="61c98-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![匯出對話的選項](../media/export.png)

1. <span data-ttu-id="61c98-172">中繼資料選項：</span><span class="sxs-lookup"><span data-stu-id="61c98-172">Metadata options:</span></span>
   - <span data-ttu-id="61c98-173">**載入檔案：** 每個個別的郵件、電子郵件及檔都包含中繼資料。</span><span class="sxs-lookup"><span data-stu-id="61c98-173">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="61c98-174">交談中的每一封郵件都有一個資料列。</span><span class="sxs-lookup"><span data-stu-id="61c98-174">There is one row for each message in a conversation.</span></span>
   - <span data-ttu-id="61c98-175">**標記：** 您的審閱程式中的標記會包含在中繼資料檔案中。</span><span class="sxs-lookup"><span data-stu-id="61c98-175">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="61c98-176">交談中的郵件共用相同的標記。</span><span class="sxs-lookup"><span data-stu-id="61c98-176">Messages in a conversation share the same tags.</span></span>

2. <span data-ttu-id="61c98-177">交談選項：</span><span class="sxs-lookup"><span data-stu-id="61c98-177">Conversation options:</span></span>
   - <span data-ttu-id="61c98-178">**交談檔案：** 當您匯出對話檔時，批註的視圖會轉換為 PDF 檔案，並下載至匯出資料夾。</span><span class="sxs-lookup"><span data-stu-id="61c98-178">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="61c98-179">一個交談檔案中的郵件指向相同交談檔案的 PDF 版本。</span><span class="sxs-lookup"><span data-stu-id="61c98-179">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>
   - <span data-ttu-id="61c98-180">**個別聊天訊息：** 當您匯出個別郵件時，交談中的每個唯一郵件都會匯出為獨立的專案。</span><span class="sxs-lookup"><span data-stu-id="61c98-180">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="61c98-181">檔會以儲存為信箱的相同格式匯出。</span><span class="sxs-lookup"><span data-stu-id="61c98-181">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="61c98-182">針對特定交談，您會收到多個 .msg 檔案。</span><span class="sxs-lookup"><span data-stu-id="61c98-182">For a specific conversation, you receive multiple .msg files.</span></span>

     > [!NOTE]
     > <span data-ttu-id="61c98-183">如果您已將批註套用至交談檔案，這些批註將不會轉移到個別的郵件。</span><span class="sxs-lookup"><span data-stu-id="61c98-183">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

3. <span data-ttu-id="61c98-184">其他選項：</span><span class="sxs-lookup"><span data-stu-id="61c98-184">Other options:</span></span>
   - <span data-ttu-id="61c98-185">**為所有匯出的內容產生文字檔：** 為從審閱集匯出的每個交談產生一個文字檔。</span><span class="sxs-lookup"><span data-stu-id="61c98-185">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>
   - <span data-ttu-id="61c98-186">**以 Redacted Pdf 取代匯出的內容：** 如果在複查程式期間產生 redacted 交談檔案，則匯出期間可使用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="61c98-186">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="61c98-187">您可以決定是否只匯出原生檔案 (但不要選取此選項) 或是使用原生檔案的 redacted 版本取代原生檔案 (方法是選取此選項) （匯出為 PDF 檔案）。</span><span class="sxs-lookup"><span data-stu-id="61c98-187">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="61c98-188">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="61c98-188">More information</span></span>

<span data-ttu-id="61c98-189">若要深入瞭解如何在 Advanced eDiscovery 中查看案例資料，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="61c98-189">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="61c98-190">查看案例資料</span><span class="sxs-lookup"><span data-stu-id="61c98-190">View case data</span></span>](view-documents-in-review-set.md)
- [<span data-ttu-id="61c98-191">分析案例資料</span><span class="sxs-lookup"><span data-stu-id="61c98-191">Analyze case data</span></span>](analyzing-data-in-review-set.md)
- [<span data-ttu-id="61c98-192">匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="61c98-192">Export case data</span></span>](exporting-data-ediscover20.md)
