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
description: 新增與高級 eDiscovery 案例相關的搜尋結果。 從原始位置複製專案，並將其複製到 Microsoft 提供的 Azure 儲存位置。 專案也會重新編制索引，而高級 eDiscovery 將會在圖像檔案上執行光學字元辨識（OCR），並上傳圖像文本以供複查和分析。
ms.openlocfilehash: 5e4eaa5e83bbca3a80abe0026f3880ce8d3c85c4
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634561"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="8d08f-105">將搜尋結果新增至檢閱集</span><span class="sxs-lookup"><span data-stu-id="8d08f-105">Add search results to a review set</span></span>

<span data-ttu-id="8d08f-106">當您符合搜尋的結果並準備好檢查和分析這些搜尋結果時，您可以在案例中將其新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="8d08f-106">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="8d08f-107">將原始資料複製到審閱集也可提供高級分析工具，例如主題偵測、接近重複偵測，以及電子郵件線索識別，以協助檢查和分析處理常式。</span><span class="sxs-lookup"><span data-stu-id="8d08f-107">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="8d08f-108">您也可以將非 Office 365 資料來源中的資料新增至審閱集，讓您除了從 Office 365 收集的資料之外，還可以查看資料。</span><span class="sxs-lookup"><span data-stu-id="8d08f-108">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span> 

<span data-ttu-id="8d08f-109">當您將搜尋結果新增至審閱集（案例中的審閱集會列于 [**檢查集合**] 索引標籤上）時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="8d08f-109">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="8d08f-110">再次執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="8d08f-110">The search is run again.</span></span> <span data-ttu-id="8d08f-111">這表示複製到審閱集的實際搜尋結果可能會與上次執行搜尋時所傳回的估計結果不同。</span><span class="sxs-lookup"><span data-stu-id="8d08f-111">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="8d08f-112">搜尋結果中的所有專案都會從 live Office 365 服務中的原始資料來源複製，然後複製至 Microsoft 雲端中的安全 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="8d08f-112">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="8d08f-113">所有專案（包括內容和中繼資料）都會重新建立索引，讓審閱集中的所有資料在複查案例資料時完全可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="8d08f-113">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="8d08f-114">當您在案例調查期間搜尋考核集中的資料時，重新編制資料的索引會產生徹底且快速的搜尋。</span><span class="sxs-lookup"><span data-stu-id="8d08f-114">Re-indexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="8d08f-115">若要將資料新增至審閱集，請按一下 [**搜尋**] 索引標籤上的搜尋，然後按一下彈出頁面上的 [**將結果新增至審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="8d08f-115">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![將資料新增至審閱集](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="8d08f-117">您可以新增至現有的複查集，或建立新的審閱集。</span><span class="sxs-lookup"><span data-stu-id="8d08f-117">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="8d08f-118">若要新增至新的審閱集，請指定名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8d08f-118">If adding to a new review set, specify the name and then click **Add**.</span></span>

![選取複查集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="8d08f-120">將資料新增至審閱集是一個長時間執行的程式。</span><span class="sxs-lookup"><span data-stu-id="8d08f-120">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="8d08f-121">此套裝程式括從 Office 365 （例如，從信箱和網站）收集原始資料來源中的專案，將其複製到 Azure 存放位置（此複製程式也稱為*攝取*），然後重新編制專案的索引。</span><span class="sxs-lookup"><span data-stu-id="8d08f-121">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="8d08f-122">您可以在 [**作業**] 索引標籤或 [**搜尋**] 索引標籤上，透過監視 [**新增資料至審閱集合**] 欄中的狀態，追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="8d08f-122">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="8d08f-123">完成審閱集處理之後，按一下案例中的 [**檢查集合**] 索引標籤，然後按一下 [複查集]，以開始篩選、檢查、標示及匯出審閱集中的資料。</span><span class="sxs-lookup"><span data-stu-id="8d08f-123">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="8d08f-124">將範例新增至審閱集</span><span class="sxs-lookup"><span data-stu-id="8d08f-124">Add a sample to a review set</span></span>

<span data-ttu-id="8d08f-125">如果您想要在將所有搜尋的結果新增至審閱集之前，先驗證搜尋結果，您可以將搜尋結果的範例新增至審閱集，而不是新增任何專案。</span><span class="sxs-lookup"><span data-stu-id="8d08f-125">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="8d08f-126">若要將範例新增至審閱集，請按一下 [**搜尋**] 索引標籤上的搜尋，然後按一下彈出頁面上的 [**範例**]。</span><span class="sxs-lookup"><span data-stu-id="8d08f-126">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="8d08f-127">在 [**抽樣參數**] 頁面上，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="8d08f-127">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="8d08f-128">**信賴等級%** 和**置信區間%** -新增至審閱集的專案將由您設定的統計參數所決定。</span><span class="sxs-lookup"><span data-stu-id="8d08f-128">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="8d08f-129">如果當採樣結果時，通常會使用信賴等級和間隔，請在下拉式方塊中指定這些結果。</span><span class="sxs-lookup"><span data-stu-id="8d08f-129">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="8d08f-130">否則，請使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="8d08f-130">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="8d08f-131">**隨機範例%** -新增至審閱集的專案是以隨機選取搜尋所傳回之總專案數目的指定百分比為基礎。</span><span class="sxs-lookup"><span data-stu-id="8d08f-131">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="8d08f-132">選取及設定上述其中一個選項之後，請選擇要新增範例的複查集，然後按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="8d08f-132">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="8d08f-133">您也可以在 [**工作**] 索引標籤或 [**搜尋**] 索引標籤上，監控 [**已新增資料至審閱集合**] 欄中的狀態，以追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="8d08f-133">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="8d08f-134">光學字元辨識</span><span class="sxs-lookup"><span data-stu-id="8d08f-134">Optical character recognition</span></span>

<span data-ttu-id="8d08f-135">當您將搜尋結果新增至審閱集時，在 [高級 eDiscovery] 中的光學字元辨識（OCR）功能會自動從影像提取文字，並包含新增至審閱集之資料的影像文字。</span><span class="sxs-lookup"><span data-stu-id="8d08f-135">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="8d08f-136">您可以在 [審閱] 集中的選取影像檔的文字檢視器中查看解壓縮的文字。</span><span class="sxs-lookup"><span data-stu-id="8d08f-136">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="8d08f-137">這可讓您對影像中的文字進行進一步的複查和分析。</span><span class="sxs-lookup"><span data-stu-id="8d08f-137">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="8d08f-138">疏鬆檔案、電子郵件附件和內嵌的圖像支援 OCR。</span><span class="sxs-lookup"><span data-stu-id="8d08f-138">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="8d08f-139">如需 OCR 支援的圖像檔案格式清單，請參閱[Advanced eDiscovery 中的支援檔案類型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="8d08f-139">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="8d08f-140">您必須為您在高級 eDiscovery 中所建立的每個案例啟用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="8d08f-140">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="8d08f-141">如需詳細資訊，請參閱[設定搜尋及分析設定](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="8d08f-141">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
