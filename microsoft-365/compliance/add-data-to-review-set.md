---
title: 將搜尋結果新增至檢閱集
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
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將搜尋結果或其範例新增至「高級 eDiscovery 案例審核」集。
ms.openlocfilehash: 6eed13c2096ad3cd33fbc7af93399824866b17c2
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336648"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="cacbd-103">將搜尋結果新增至檢閱集</span><span class="sxs-lookup"><span data-stu-id="cacbd-103">Add search results to a review set</span></span>

<span data-ttu-id="cacbd-104">當您符合搜尋的結果並準備好檢查和分析這些搜尋結果時，您可以在案例中將其新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="cacbd-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="cacbd-105">將原始資料複製到審閱集也可提供高級分析工具，例如主題偵測、接近重複偵測，以及電子郵件線索識別，以協助檢查和分析處理常式。</span><span class="sxs-lookup"><span data-stu-id="cacbd-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="cacbd-106">您也可以將非 Microsoft 365 資料來源中的資料新增至審閱集，讓您除了從 Microsoft 365 收集的資料之外，還可以查看資料。</span><span class="sxs-lookup"><span data-stu-id="cacbd-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span>

<span data-ttu-id="cacbd-107">當您將搜尋結果新增至審閱集時 (的複查集會列于 [ **複查集** ] 索引標籤) 上，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="cacbd-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="cacbd-108">再次執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="cacbd-108">The search is run again.</span></span> <span data-ttu-id="cacbd-109">這表示複製到審閱集的實際搜尋結果可能會與上次執行搜尋時所傳回的估計結果不同。</span><span class="sxs-lookup"><span data-stu-id="cacbd-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="cacbd-110">搜尋結果中的所有專案都會從 live services 中的原始資料來源進行複製，並複製到 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="cacbd-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="cacbd-111">所有專案 (（包括內容和中繼資料) ）都是重新編制索引，因此複查集中的所有資料在複查案例資料期間都會完全可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="cacbd-111">All items (including the content and metadata) are reindexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="cacbd-112">當您在案例調查期間搜尋考核集中的資料時，會產生完全和 fast 搜尋的資料。</span><span class="sxs-lookup"><span data-stu-id="cacbd-112">Reindexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="cacbd-113">若要將資料新增至審閱集，請按一下 [ **搜尋** ] 索引標籤上的搜尋，然後按一下彈出頁面上的 [ **將結果新增至審閱集** ]。</span><span class="sxs-lookup"><span data-stu-id="cacbd-113">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

<span data-ttu-id="cacbd-114">您可以新增至現有的複查集，或建立新的審閱集。</span><span class="sxs-lookup"><span data-stu-id="cacbd-114">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="cacbd-115">若要新增至新的審閱集，請指定名稱，然後按一下 [ **新增** ] 以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="cacbd-115">If adding to a new review set, specify the name and then click **Add** to display the flyout page.</span></span>

![選取複查集和設定收集選項](../media/AeD_AddToReviewSet.png)

<span data-ttu-id="cacbd-117">將資料新增至審閱集是一個長時間執行的程式。</span><span class="sxs-lookup"><span data-stu-id="cacbd-117">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="cacbd-118">此套裝程式含從原始資料來源收集 Microsoft 365 (中的專案，例如，從信箱和網站) ，將其複製到 Azure 存放位置 (此複製程式也稱為 *攝取*) ，然後再重新索引項目目。</span><span class="sxs-lookup"><span data-stu-id="cacbd-118">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then reindexing the items.</span></span> <span data-ttu-id="cacbd-119">您可以在 [ **作業** ] 索引標籤或 [ **搜尋** ] 索引標籤上，透過監視 [ **新增資料至審閱集合** ] 欄中的狀態，追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="cacbd-119">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="cacbd-120">完成審閱集處理之後，按一下案例中的 [ **檢查集合** ] 索引標籤，然後按一下 [複查集]，以開始篩選、檢查、標示及匯出審閱集中的資料。</span><span class="sxs-lookup"><span data-stu-id="cacbd-120">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="cacbd-121">定義選項來限定您的集合以供審閱</span><span class="sxs-lookup"><span data-stu-id="cacbd-121">Define options to scope your collection for review</span></span>

<span data-ttu-id="cacbd-122">當您將搜尋內容新增至現有或新的審閱集時，您可以使用下列選項來收集要複查的內容：</span><span class="sxs-lookup"><span data-stu-id="cacbd-122">When you add the content of a search to an existing or new review set, you have the following options for how to collect the content for review:</span></span>

- <span data-ttu-id="cacbd-123">\*\*包括版本 SharePoint (Beta) \*\*：您可以使用此選項，根據集合的版本限制和搜尋參數，來啟用 SharePoint 檔所有版本的集合。</span><span class="sxs-lookup"><span data-stu-id="cacbd-123">**Include versions from SharePoint (beta)**: Use this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="cacbd-124">選取此選項會大幅增加新增至審閱集之專案的大小。</span><span class="sxs-lookup"><span data-stu-id="cacbd-124">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

- <span data-ttu-id="cacbd-125">**交談檢索選項**：新增至審閱集的專案會針對執行緒交談啟用，以協助檢查前後交談內容中的內容。</span><span class="sxs-lookup"><span data-stu-id="cacbd-125">**Conversation retrieval options**: Items added to the review set are enabled for threaded conversations to help review content in context of the back and forth conversation.</span></span> <span data-ttu-id="cacbd-126">如需詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="cacbd-126">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

- <span data-ttu-id="cacbd-127">**啟用新式附件的取回**功能：使用此選項可包含集合中新式附件或連結的檔案，以便進一步複查。</span><span class="sxs-lookup"><span data-stu-id="cacbd-127">**Enable retrieval for modern attachments**: Use this option to include modern attachments or linked files in the collection for further review.</span></span> <span data-ttu-id="cacbd-128">如需與現代附件相關的可搜尋屬性的詳細資訊，請參閱 [Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="cacbd-128">For more information about the searchable properties related to modern attachments, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="cacbd-129">將範例新增至審閱集</span><span class="sxs-lookup"><span data-stu-id="cacbd-129">Add a sample to a review set</span></span>

<span data-ttu-id="cacbd-130">如果您想要在將所有搜尋的結果新增至審閱集之前，先驗證搜尋結果，您可以將搜尋結果的範例新增至審閱集，而不是新增任何專案。</span><span class="sxs-lookup"><span data-stu-id="cacbd-130">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="cacbd-131">若要將範例新增至審閱集，請按一下 [ **搜尋** ] 索引標籤上的搜尋，然後按一下彈出頁面上的 [ **範例** ]。</span><span class="sxs-lookup"><span data-stu-id="cacbd-131">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="cacbd-132">在 [ **抽樣參數** ] 頁面上，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="cacbd-132">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="cacbd-133">**信賴等級%** 和 **置信區間%** -新增至審閱集的專案將由您設定的統計參數所決定。</span><span class="sxs-lookup"><span data-stu-id="cacbd-133">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="cacbd-134">如果當採樣結果時，通常會使用信賴等級和間隔，請在下拉式方塊中指定這些結果。</span><span class="sxs-lookup"><span data-stu-id="cacbd-134">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="cacbd-135">否則，請使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="cacbd-135">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="cacbd-136">**隨機範例%** -新增至審閱集的專案是以隨機選取搜尋所傳回之總專案數目的指定百分比為基礎。</span><span class="sxs-lookup"><span data-stu-id="cacbd-136">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="cacbd-137">選取及設定上述其中一個選項之後，請選擇要新增範例的複查集，然後按一下 [ **傳送**]。</span><span class="sxs-lookup"><span data-stu-id="cacbd-137">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="cacbd-138">您也可以在 [ **工作** ] 索引標籤或 [ **搜尋** ] 索引標籤上，監控 [ **已新增資料至審閱集合** ] 欄中的狀態，以追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="cacbd-138">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="cacbd-139">光學字元辨識</span><span class="sxs-lookup"><span data-stu-id="cacbd-139">Optical character recognition</span></span>

<span data-ttu-id="cacbd-140">當您將搜尋結果新增至審閱集時，在 [Advanced eDiscovery] 中 (OCR) 功能會自動從影像提取文字，並包含包含已新增至審閱集之資料的影像文字。</span><span class="sxs-lookup"><span data-stu-id="cacbd-140">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="cacbd-141">您可以在 [審閱] 集中的選取影像檔的文字檢視器中查看解壓縮的文字。</span><span class="sxs-lookup"><span data-stu-id="cacbd-141">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="cacbd-142">這可讓您對影像中的文字進行進一步的複查和分析。</span><span class="sxs-lookup"><span data-stu-id="cacbd-142">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="cacbd-143">疏鬆檔案、電子郵件附件和內嵌的圖像支援 OCR。</span><span class="sxs-lookup"><span data-stu-id="cacbd-143">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="cacbd-144">如需 OCR 支援的圖像檔案格式清單，請參閱 [Advanced eDiscovery 中的支援檔案類型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="cacbd-144">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="cacbd-145">您必須為您在高級 eDiscovery 中所建立的每個案例啟用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="cacbd-145">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="cacbd-146">如需詳細資訊，請參閱 [設定搜尋及分析設定](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="cacbd-146">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
