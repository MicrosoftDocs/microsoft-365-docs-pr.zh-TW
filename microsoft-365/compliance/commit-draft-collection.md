---
title: 草稿集合提交至檢閱集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 建立並重複使用草擬集合之後，您可以將其認可為審閱集。 當您認可草稿集合時，所收集的專案會新增至此案例中的「審閱」集。 收集的專案在考核集中後，您就可以進行分析、檢查及匯出。
ms.openlocfilehash: dceb661d9586e324482dc4f56bce12fafaf9b251
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276974"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="ce8b7-105">將草稿集合認可為 Advanced eDiscovery 中的審閱集</span><span class="sxs-lookup"><span data-stu-id="ce8b7-105">Commit a draft collection to a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="ce8b7-106">當您對您在草稿集合中收集並準備好進行分析、標記及檢查的專案滿意時，您可以在案例中新增集合至審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-106">When you're satisfied with the items you've collected in a draft collection and are ready to analyze, tag, and review them, you can add a collection to a review set in the case.</span></span> <span data-ttu-id="ce8b7-107">當您將草稿集合認可至審閱集時，收集的專案會從其原始內容位置複製到 Microsoft 365 的審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-107">When you commit a draft collection to a review set, collected items are copied from their original content location in Microsoft 365 to a review set.</span></span> <span data-ttu-id="ce8b7-108">「審閱集」是 microsoft 雲端中，由 microsoft 提供的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-108">A review set is a secure, Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>

## <a name="commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="ce8b7-109">草稿集合提交至檢閱集</span><span class="sxs-lookup"><span data-stu-id="ce8b7-109">Commit a draft collection to a review set</span></span>

1. <span data-ttu-id="ce8b7-110">在 Microsoft 365 合規性中心中，開啟 Advanced eDiscovery 案例，然後選取 [**集合**] 索引標籤，以顯示案例的集合清單。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-110">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, and then select the **Collections** tab to display a list of the collections in the case.</span></span>

   ![案例中的集合清單](../media/CommitDraftCollections1.png)

   > [!TIP]
   > <span data-ttu-id="ce8b7-112">`Estimated`[**狀態**] 欄中的值會識別可以新增至審閱集的草稿集合。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-112">A value of `Estimated` in the **Status** column identifies the draft collections that can be added to a review set.</span></span> <span data-ttu-id="ce8b7-113">「狀態」 `Committed` 表示集合已經新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-113">A status of `Committed` indicates that a collection has already been added to a review set.</span></span>

2. <span data-ttu-id="ce8b7-114">在 [ **集合** ] 頁面上，選取您要認可為審閱集的草稿集合。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-114">On the **Collections** page, select the draft collection that you want to commit to a review set.</span></span>

3. <span data-ttu-id="ce8b7-115">在飛入頁面底部，選取 [**動作**  >  **編輯集合**]。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-115">On the bottom of the flyout page, select **Actions** > **Edit collection**.</span></span>

4. <span data-ttu-id="ce8b7-116">在 [編輯集合] 嚮導中，按 **[下一步** ]，直到顯示 [ **儲存草稿] 或 [收集** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-116">In the edit collection wizard, click **Next** until the **Save draft or collect** page is displayed.</span></span>

5. <span data-ttu-id="ce8b7-117">進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="ce8b7-117">Configure the following settings:</span></span>

   1. <span data-ttu-id="ce8b7-118">選取 [ **收集項目並新增至審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-118">Select **Collect items and add to review set**.</span></span>

   2. <span data-ttu-id="ce8b7-119">決定是否要將集合新增至新的審閱集 (該集合在您提交集合) 之後建立，或將其新增至現有的審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-119">Decide whether to add the collection to a new review set (which is created after you submit the collection) or add it to an existing review set.</span></span> <span data-ttu-id="ce8b7-120">請根據您的決定完成本節。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-120">Complete this section based on your decision.</span></span>

   3. <span data-ttu-id="ce8b7-121">設定其他集合設定：</span><span class="sxs-lookup"><span data-stu-id="ce8b7-121">Configure the additional collection settings:</span></span>

       - <span data-ttu-id="ce8b7-122">**Teams 和 Yammer 郵件**：選取此選項可將討論執行緒新增至集合，此集合包含集合中的搜尋查詢所傳回的聊天室專案。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-122">**Teams and Yammer messages**: Select this option to add conversation threads to the collection that include the chat items returned by the search query in the collection.</span></span> <span data-ttu-id="ce8b7-123">這表示會重建包含符合搜尋準則之專案的交談交談。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-123">This means that the chat conversation that contains items that match the search criteria is reconstructed.</span></span> <span data-ttu-id="ce8b7-124">這可讓您查看前後交談內容中的聊天室專案。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-124">This lets you review chat items in the context of the back and forth conversation.</span></span> <span data-ttu-id="ce8b7-125">如需詳細資訊，請參閱[Advanced eDiscovery 中的交談執行緒](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-125">For more information, see [Conversation threading in Advanced eDiscovery](conversation-review-sets.md).</span></span>

       - <span data-ttu-id="ce8b7-126">**雲端附件**：選取此選項可在將集合結果新增至審閱集時包含新式附件或連結的檔案。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-126">**Cloud attachments**: Select this option to include modern attachments or linked files when the collection results are added to the review set.</span></span> <span data-ttu-id="ce8b7-127">這表示新式附件或連結檔案的目標檔案會新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-127">This means that the target file of a modern attachment or linked file is added to the review set.</span></span>

       - <span data-ttu-id="ce8b7-128">**SharePoint 版本**：選取此選項可啟用集合中每個版本限制和搜尋參數的所有版本 SharePoint 檔的集合。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-128">**SharePoint versions**: Select this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="ce8b7-129">選取此選項會大幅增加新增至審閱集之專案的大小。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-129">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

   4. <span data-ttu-id="ce8b7-130">設定設定以定義要新增至審閱集的集合規模：</span><span class="sxs-lookup"><span data-stu-id="ce8b7-130">Configure the settings to define the scale of the collection to add to the review set:</span></span>

      - <span data-ttu-id="ce8b7-131">**新增所有集合結果**：選取此選項可將符合集合之搜尋準則的所有專案新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-131">**Add all collection results**: Select this option to add all the items that match the search criteria of the collection to the review set.</span></span>

      - <span data-ttu-id="ce8b7-132">**新增集合結果的範例**：選取此選項可將集合結果的範例新增至審閱集，而不是新增所有結果。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-132">**Add a sample of the collection results**: Select this option to add a sample of the collection results to the review set instead of adding all results.</span></span> <span data-ttu-id="ce8b7-133">如果您選取此選項，請按一下 [ **編輯範例參數** ]，然後選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="ce8b7-133">If you select this option, click **Edit sample parameters** and choose one of the following options:</span></span>

         - <span data-ttu-id="ce8b7-134">**範例基礎**：將集合中的專案新增至審閱集會由您設定的統計參數所決定。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-134">**Sample based on confidence**: Items from the collection are added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="ce8b7-135">如果當採樣結果時，通常會使用信賴等級和間隔，請在下拉式方塊中指定這些結果。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-135">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="ce8b7-136">否則，請使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-136">Otherwise, use the default settings.</span></span>

         - <span data-ttu-id="ce8b7-137">**隨機範例**：集合中的專案會根據搜尋傳回之總專案數目的指定百分比之隨機選取，新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-137">**Randomly sample**: Items from the collection are added to the review set based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

6. <span data-ttu-id="ce8b7-138">在 [ **檢查您的集合** ] 頁面上，您可以查看您在前一頁上設定的集合設定。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-138">On the **Review your collection** page, you can review the collection settings that you configured on the previous page.</span></span> <span data-ttu-id="ce8b7-139">若要變更，請按一下 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-139">Click **Edit** if you want to change them.</span></span>

7. <span data-ttu-id="ce8b7-140">按一下 [ **提交** ] 以建立草稿收集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-140">Click **Submit** to create the draft collection.</span></span> <span data-ttu-id="ce8b7-141">隨即會顯示一個頁面，確認已建立集合。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-141">A page is displayed confirming that the collection was created.</span></span>

## <a name="what-happens-after-you-commit-a-draft-collection"></a><span data-ttu-id="ce8b7-142">在您認可草稿集合後會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="ce8b7-142">What happens after you commit a draft collection</span></span>

<span data-ttu-id="ce8b7-143">當您將草稿集合認可至審閱集時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="ce8b7-143">When you commit a draft collection to a review set, the following things happen:</span></span>

- <span data-ttu-id="ce8b7-144">如果您建立了新的審閱集以認可集合，則在案例中的「 **複查集** 」索引標籤上會建立並顯示「審閱」集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-144">If you created a new review set to commit the collection to, the review set is created and displayed on the **Review sets** tab in the case.</span></span> <span data-ttu-id="ce8b7-145">新審閱集的狀態為 [ **就緒**]。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-145">The status of the new review set is **Ready**.</span></span> <span data-ttu-id="ce8b7-146">此狀態值表示已建立審閱集;這並不表示集合已新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-146">This status value means the review set has been created; it doesn't mean that the collection has been added to the review set.</span></span> <span data-ttu-id="ce8b7-147">將集合中的專案新增至審閱集的狀態會顯示在 [ **集合** ] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-147">The status of adding items in the collection to the review set is displayed on the **Collections** tab.</span></span>

- <span data-ttu-id="ce8b7-148">會再次執行收藏搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-148">The collection search query is run again.</span></span> <span data-ttu-id="ce8b7-149">這表示複製到審閱集的實際搜尋結果可能會不同于上次執行集合搜尋時所傳回的估計結果。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-149">This means the actual search results copied to the review set may be different than the estimated results that were returned when the collection search was last run.</span></span>

- <span data-ttu-id="ce8b7-150">搜尋結果中的所有專案都會從 live service 中的原始資料來源複製，然後複製至 Microsoft 雲端中的安全 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-150">All items in the search results are copied from the original data source in the live service, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="ce8b7-151">所有專案 (包含不位於保管人或非保管人資料來源中的內容和中繼資料) ，會在稱為「 *深度索引*) 」的程式中重新編制索引 (，這樣就能在複查案例資料時完全搜尋評審集中的所有資料。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-151">All items (including the content and metadata) that aren't located in custodian or non-custodian data sources are reindexed (in a process called *deep indexing*) so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="ce8b7-152">當您在案例調查期間搜尋或篩選考核集中的內容時，會在集合中的內容進行完整且快速的搜尋。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-152">Reindexing the content in a collection results in thorough and fast searches when you search or filter the content in the review set during the case investigation.</span></span>

- <span data-ttu-id="ce8b7-153">在將集合認可至審閱集時，會解密在搜尋結果中傳回的加密 SharePoint 和 OneDrive 檔與加密檔案。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-153">Encrypted SharePoint and OneDrive documents and encrypted files attached email messages that's returned in the search results are decrypted when you commit the collection to a review set.</span></span> <span data-ttu-id="ce8b7-154">您可以在複查集中複查及查詢解密的檔案。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-154">You can review and query the decrypted files in the review set.</span></span> <span data-ttu-id="ce8b7-155">如需詳細資訊，請參閱[Microsoft 365 eDiscovery tools 中的解密](ediscovery-decryption.md)。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-155">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

- <span data-ttu-id="ce8b7-156">光學字元辨識 (OCR) 功能會從影像析取文字，並包含具有新增至審閱集之內容的影像文字。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-156">Optical character recognition (OCR) functionality extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="ce8b7-157">如需詳細資訊，請參閱本文中的 [光學字元辨識](#optical-character-recognition) 一節。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-157">For more information, see the [Optical character recognition](#optical-character-recognition) section in this article.</span></span>

- <span data-ttu-id="ce8b7-158">在成功完成認可之後，[ **集合** ] 索引標籤上的 [狀態] 欄的值會變更為 `Committed` 。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-158">After the commit is successfully completed, the value of the status column of on the **Collections** tab is changed to `Committed`.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="ce8b7-159">光學字元辨識</span><span class="sxs-lookup"><span data-stu-id="ce8b7-159">Optical character recognition</span></span>

<span data-ttu-id="ce8b7-160">當您將集合認可至審閱集時，會自動從影像提取文字的光字元識別 (OCR) Advanced eDiscovery 功能，並包含包含在審閱集新增內容的影像文字。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-160">When you commit a collection to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="ce8b7-161">您可以在 [審閱] 集中的選取影像檔的文字檢視器中查看解壓縮的文字。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-161">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="ce8b7-162">這可讓您對影像中的文字進行進一步的檢閱和分析。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-162">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="ce8b7-163">OCR 支援用於鬆散檔案、電子郵件附件和內嵌影像。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-163">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="ce8b7-164">如需 OCR 支援的影像檔格式清單，請參閱[進階電子文件探索中支援的檔案類型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-164">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="ce8b7-165">您必須針對在進階電子文件探索中建立的每個案例啟用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-165">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="ce8b7-166">如需詳細資訊，請參閱 [設定搜尋及分析設定](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="ce8b7-166">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
