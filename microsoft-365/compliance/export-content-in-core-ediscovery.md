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
description: 說明如何從 Microsoft 365 中的核心 eDiscovery 案例中匯出及下載內容。
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310837"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="9420f-103">從核心電子文件探索案例匯出內容</span><span class="sxs-lookup"><span data-stu-id="9420f-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="9420f-104">成功執行與核心 eDiscovery 案例相關聯的搜尋之後，您可以匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="9420f-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="9420f-105">當您匯出搜尋結果時，信箱專案會下載到 PST 檔案或個別郵件。</span><span class="sxs-lookup"><span data-stu-id="9420f-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="9420f-106">當您從 SharePoint 和商務用 OneDrive 網站匯出內容時，會匯出原生 Office 檔和其他檔的副本。</span><span class="sxs-lookup"><span data-stu-id="9420f-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="9420f-107">包含每個匯出專案的資訊的 Results.csv 檔案，以及包含每個搜尋結果相關資訊的資訊清單檔)  (也會匯出。</span><span class="sxs-lookup"><span data-stu-id="9420f-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="9420f-108">匯出搜尋結果</span><span class="sxs-lookup"><span data-stu-id="9420f-108">Export search results</span></span>

1. <span data-ttu-id="9420f-109">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="9420f-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="9420f-110">在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Core**]。</span><span class="sxs-lookup"><span data-stu-id="9420f-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="9420f-111">在 [ **核心電子** 檔探索] 頁面上，按一下您要在其中建立保留的案例名稱。</span><span class="sxs-lookup"><span data-stu-id="9420f-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="9420f-112">在案例的 **首頁** 上，按一下 [ **搜尋** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9420f-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="9420f-113">在飛入頁面底部的 [ **動作** ] 功能表上，按一下 [ **匯出結果**]。</span><span class="sxs-lookup"><span data-stu-id="9420f-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![[動作] 功能表中的 [匯出結果] 選項](../media/ActionMenuExportResults.png)

   <span data-ttu-id="9420f-115">匯出與核心 eDiscovery 案例相關聯之搜尋結果的工作流程，與在 [ **內容搜尋** ] 頁面上匯出搜尋的搜尋結果相同。</span><span class="sxs-lookup"><span data-stu-id="9420f-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="9420f-116">如需逐步指示，請參閱 [匯出內容搜尋結果](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="9420f-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9420f-117">當您匯出搜尋結果時，您可以選擇啟用重復資料刪除，這樣一來，即使在搜尋的信箱中找到多個相同郵件的實例，也只會匯出電子郵件的一個副本。</span><span class="sxs-lookup"><span data-stu-id="9420f-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="9420f-118">如需有關重復資料刪除以及如何識別重複專案的詳細資訊，請參閱 [eDiscovery 搜尋結果中的重復資料](de-duplication-in-ediscovery-search-results.md)刪除。</span><span class="sxs-lookup"><span data-stu-id="9420f-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="9420f-119">在您開始匯出後，搜尋結果即會做好下載準備，這表示它們會傳送至 microsoft 雲端中的 microsoft 所提供的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="9420f-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="9420f-120">按一下案例中的 [ **匯出** ] 索引標籤，顯示匯出工作清單。</span><span class="sxs-lookup"><span data-stu-id="9420f-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![在核心 eDiscovery 案例的 [匯出] 索引標籤上匯出工作](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="9420f-122">您可能 **需要按一下 [** 重新整理] 以更新匯出工作清單，使其顯示您建立的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="9420f-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="9420f-123">匯出工作與對應的搜尋同名， **_Export** 附加至搜尋名稱。</span><span class="sxs-lookup"><span data-stu-id="9420f-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="9420f-124">按一下您建立的匯出工作，以在飛入頁面上顯示狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="9420f-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="9420f-125">此資訊包含已轉接至 Azure 儲存體位置之專案的百分比。</span><span class="sxs-lookup"><span data-stu-id="9420f-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="9420f-126">所有專案都已轉接後，按一下 [ **下載結果** ]，將搜尋結果下載至您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="9420f-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="9420f-127">如需下載搜尋結果的詳細資訊，請參閱[匯出內容搜尋結果](export-search-results.md#step-2-download-the-search-results)中的步驟2。</span><span class="sxs-lookup"><span data-stu-id="9420f-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="9420f-128">從案例中匯出搜尋的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9420f-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="9420f-129">如需匯出搜尋結果時所包含匯出檔案的詳細資訊，請參閱 [匯出內容搜尋報告](export-a-content-search-report.md#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="9420f-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="9420f-130">如果您重新開機匯出，對組成匯出工作之搜尋查詢所做的任何變更，都不會影響所檢索的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="9420f-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="9420f-131">當您重新開機匯出時，在建立匯出工作時所執行的相同組合搜尋查詢工作會再次執行。</span><span class="sxs-lookup"><span data-stu-id="9420f-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="9420f-132">此外，如果您重新開機匯出，會複製到 Azure 儲存體位置的搜尋結果會覆寫先前的結果。</span><span class="sxs-lookup"><span data-stu-id="9420f-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="9420f-133">先前所複製的結果將不會下載。</span><span class="sxs-lookup"><span data-stu-id="9420f-133">The previous results that were copied won't be available to be downloaded.</span></span>
