---
title: 從核心 eDiscovery 案例匯出及下載內容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明如何從核心 eDiscovery 案例匯出及下載內容。
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760297"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="90ca6-103">從核心 eDiscovery 案例匯出內容</span><span class="sxs-lookup"><span data-stu-id="90ca6-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="90ca6-104">成功執行搜尋之後，您可以匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="90ca6-105">當您匯出搜尋結果時，信箱專案會下載到 PST 檔案或個別郵件。</span><span class="sxs-lookup"><span data-stu-id="90ca6-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="90ca6-106">當您從商務網站的 SharePoint 和 OneDrive 匯出內容時，會匯出原生 Office 檔和其他檔的副本。</span><span class="sxs-lookup"><span data-stu-id="90ca6-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="90ca6-107">包含每個匯出專案的資訊的 Results.csv 檔案，以及包含每個搜尋結果相關資訊的資訊清單檔)  (也會匯出。</span><span class="sxs-lookup"><span data-stu-id="90ca6-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="90ca6-108">您可以匯出 [與案例相關聯之單一搜尋](#export-the-results-of-a-single-search) 的結果，也可以匯出 [與案例相關聯之多個搜尋](#export-the-results-of-multiple-searches)的結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="90ca6-109">匯出單一搜尋的結果</span><span class="sxs-lookup"><span data-stu-id="90ca6-109">Export the results of a single search</span></span>

1. <span data-ttu-id="90ca6-110">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="90ca6-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="90ca6-111">在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示**]，然後按一下 [ **eDiscovery > Core**]。</span><span class="sxs-lookup"><span data-stu-id="90ca6-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="90ca6-112">在 [ **核心電子** 檔探索] 頁面上，選取您要從中匯出搜尋結果的案例，然後按一下 [ **開啟案例**]。</span><span class="sxs-lookup"><span data-stu-id="90ca6-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="90ca6-113">在案例的 **首頁** 上，按一下 [ **搜尋** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90ca6-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="90ca6-114">在案例的搜尋清單中，按一下您想要從中匯出搜尋結果的搜尋，然後按一下快顯視窗的 [ **匯出結果** ]。</span><span class="sxs-lookup"><span data-stu-id="90ca6-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="90ca6-115">[ **匯出結果** ] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="90ca6-115">The **Export results** page is displayed.</span></span> 

    ![匯出結果頁面](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="90ca6-117">匯出與核心 eDiscovery 案例相關聯之搜尋結果的工作流程，與在 [ **內容搜尋** ] 頁面上匯出搜尋的搜尋結果相同。</span><span class="sxs-lookup"><span data-stu-id="90ca6-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="90ca6-118">如需逐步指示，請參閱 [匯出內容搜尋結果](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="90ca6-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="90ca6-119">當您匯出搜尋結果時，您可以選擇啟用重復資料刪除，這樣一來，即使在搜尋的信箱中找到多個相同郵件的實例，也只會匯出電子郵件的一個副本。</span><span class="sxs-lookup"><span data-stu-id="90ca6-119">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="90ca6-120">如需有關重復資料刪除以及如何識別重複專案的詳細資訊，請參閱 [eDiscovery 搜尋結果中的重復資料](de-duplication-in-ediscovery-search-results.md)刪除。</span><span class="sxs-lookup"><span data-stu-id="90ca6-120">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="90ca6-121">在您開始匯出後，搜尋結果即已準備好下載，這表示它們會上傳至 Microsoft 雲端中的 Microsoft 提供 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="90ca6-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="90ca6-122">按一下 [ **匯出** ] 索引標籤，顯示案例的匯出工作清單。</span><span class="sxs-lookup"><span data-stu-id="90ca6-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="90ca6-123">您可能 **需要按一下 [** 重新整理] 以更新匯出工作清單，使其顯示您建立的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="90ca6-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="90ca6-124">匯出工作與對應的搜尋同名， **_Export** 附加至搜尋名稱。</span><span class="sxs-lookup"><span data-stu-id="90ca6-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="90ca6-125">按一下您建立的匯出工作，以在飛入頁面上顯示狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="90ca6-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="90ca6-126">此資訊包含已轉接至 Azure 儲存位置的專案百分比。</span><span class="sxs-lookup"><span data-stu-id="90ca6-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="90ca6-127">所有專案都已轉接後，按一下 [ **下載結果** ]，將搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="90ca6-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="90ca6-128">如需下載搜尋結果的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md#step-2-download-the-search-results)中的步驟2。</span><span class="sxs-lookup"><span data-stu-id="90ca6-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="90ca6-129">匯出多個搜尋的結果</span><span class="sxs-lookup"><span data-stu-id="90ca6-129">Export the results of multiple searches</span></span>

<span data-ttu-id="90ca6-130">除了匯出與案例相關聯之單一搜尋的結果之外，您還可以從單一匯出工作中的相同案例中匯出多個搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="90ca6-131">匯出多個搜尋的結果比匯出一次搜尋的結果更快速且更容易。</span><span class="sxs-lookup"><span data-stu-id="90ca6-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90ca6-132">如果其中一項搜尋設定為 [保留時搜尋位置]，則您無法匯出多個搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="90ca6-133">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="90ca6-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="90ca6-134">在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示**]，然後按一下 [ **eDiscovery > Core**]。</span><span class="sxs-lookup"><span data-stu-id="90ca6-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="90ca6-135">在 [ **核心電子** 檔探索] 頁面上，選取您要從中匯出搜尋結果的案例，然後按一下 [ **開啟案例**]。</span><span class="sxs-lookup"><span data-stu-id="90ca6-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="90ca6-136">在案例的 **首頁** 上，按一下 [ **搜尋** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="90ca6-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="90ca6-137">在案例的搜尋清單中，選取您想要從中匯出搜尋結果的兩個或多個搜尋旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90ca6-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="90ca6-138">隨即會顯示 [ **大量動作** ] 飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="90ca6-138">The **Bulk actions** flyout page appears.</span></span> 

    ![在 [大量動作] 頁面上，按一下 [匯出結果]](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="90ca6-140">按一下 [ **匯出結果**]。</span><span class="sxs-lookup"><span data-stu-id="90ca6-140">Click **Export results**.</span></span>

   <span data-ttu-id="90ca6-141">[ **匯出結果** ] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="90ca6-141">The **Export results** page is displayed.</span></span> 

    ![匯出結果頁面](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="90ca6-143">此時，匯出與核心 eDiscovery 案例相關聯之多個搜尋結果的工作流程，與匯出單一搜尋的搜尋結果相同。</span><span class="sxs-lookup"><span data-stu-id="90ca6-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="90ca6-144">請參閱上一節中的步驟5。</span><span class="sxs-lookup"><span data-stu-id="90ca6-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="90ca6-145">有關匯出多個搜尋結果的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="90ca6-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="90ca6-146">當您匯出多個搜尋的結果時，會使用 **OR** 運算子組合所有搜尋中的搜尋查詢，然後啟動合併後的搜尋。</span><span class="sxs-lookup"><span data-stu-id="90ca6-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="90ca6-147">合併搜尋的預估結果會顯示在所選匯出工作的飛出頁面中。</span><span class="sxs-lookup"><span data-stu-id="90ca6-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="90ca6-148">然後將搜尋結果複製到 Microsoft 雲端中的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="90ca6-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="90ca6-149">複製工作的狀態也會顯示在飛入頁面上。</span><span class="sxs-lookup"><span data-stu-id="90ca6-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="90ca6-150">如先前所述，所有搜尋結果都已複製後，您可以將其下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="90ca6-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="90ca6-151">所有要匯出之搜尋的關鍵字數目上限為500。</span><span class="sxs-lookup"><span data-stu-id="90ca6-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="90ca6-152">這對單一搜尋的限制相同。</span><span class="sxs-lookup"><span data-stu-id="90ca6-152">This is the same limit for a single search.</span></span> <span data-ttu-id="90ca6-153">這是因為匯出工作會結合使用 **OR** 運算子的所有搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="90ca6-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="90ca6-154">如果您超過此限制，將會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="90ca6-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="90ca6-155">在此情況下，您必須從較少的搜尋中匯出結果，或是簡化您想要匯出之原始搜尋的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="90ca6-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="90ca6-156">匯出的搜尋結果會依找到專案的內容位置進行組織。</span><span class="sxs-lookup"><span data-stu-id="90ca6-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="90ca6-157">這表示匯出結果中的內容位置可能會有不同搜尋傳回的專案。</span><span class="sxs-lookup"><span data-stu-id="90ca6-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="90ca6-158">例如，如果您選擇將電子郵件訊息匯出至每個信箱的一個 PST 檔案中，則 PST 檔案可能會有多個搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="90ca6-159">如果相同內容位置的相同電子郵件專案或檔是透過您匯出的一個搜尋傳回，則只會匯出該專案的一個複本。</span><span class="sxs-lookup"><span data-stu-id="90ca6-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="90ca6-160">您在建立多個搜尋後，就無法編輯該匯出。</span><span class="sxs-lookup"><span data-stu-id="90ca6-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="90ca6-161">例如，您無法在匯出工作中新增或移除搜尋。</span><span class="sxs-lookup"><span data-stu-id="90ca6-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="90ca6-162">您必須建立匯出工作，以變更要匯出的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="90ca6-163">在建立匯出工作之後，您只可以將結果下載至電腦、重新開機匯出或刪除匯出工作。</span><span class="sxs-lookup"><span data-stu-id="90ca6-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="90ca6-164">如果您重新開機匯出，對組成匯出工作之搜尋查詢所做的任何變更，都不會影響所檢索的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="90ca6-165">當您重新開機匯出時，在建立匯出工作時所執行的相同組合搜尋查詢工作會再次執行。</span><span class="sxs-lookup"><span data-stu-id="90ca6-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="90ca6-166">此外，如果您重新開機匯出，複製到 Azure 儲存體位置的搜尋結果會覆寫先前的結果。</span><span class="sxs-lookup"><span data-stu-id="90ca6-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="90ca6-167">先前所複製的結果將不會下載。</span><span class="sxs-lookup"><span data-stu-id="90ca6-167">The previous results that were copied won't be available to be downloaded.</span></span>
