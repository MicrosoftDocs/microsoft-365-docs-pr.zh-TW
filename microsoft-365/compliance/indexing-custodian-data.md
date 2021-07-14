---
title: 進階的監管人資料索引
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
description: 當保管人加入 Advanced eDiscovery 案例時，被視為部分索引的任何內容都會重新處理，使其完全可供搜尋。
ms.openlocfilehash: f510b7e9c0fa2c5c181709c96907610066a4b1cf
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430502"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="bd642-103">進階的監管人資料索引</span><span class="sxs-lookup"><span data-stu-id="bd642-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="bd642-104">當系統管理員加入 Advanced eDiscovery 案例時，任何被視為已做為部分索引的內容或是具有索引錯誤，都是重新編制索引，讓它完全可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="bd642-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="bd642-105">這種重建索引過程稱為「 *高級索引*」。</span><span class="sxs-lookup"><span data-stu-id="bd642-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="bd642-106">內容已部分編制索引或出現索引錯誤的原因有許多。</span><span class="sxs-lookup"><span data-stu-id="bd642-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="bd642-107">這包括圖像檔案或檔中的圖像、不支援的檔案類型或檔案大小的索引限制。</span><span class="sxs-lookup"><span data-stu-id="bd642-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="bd642-108">若為 SharePoint 檔案，則只有在專案上執行的高級索引程式會標示為已部分編制索引或具有索引錯誤。</span><span class="sxs-lookup"><span data-stu-id="bd642-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="bd642-109">在 Exchange 中，具有影像附件的電子郵件將不會標示為已部分編制索引或具有索引錯誤。</span><span class="sxs-lookup"><span data-stu-id="bd642-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="bd642-110">這表示將不會重新編制索引高級索引處理常式的檔案。</span><span class="sxs-lookup"><span data-stu-id="bd642-110">This means that those files will not be reindexed by Advanced indexing process.</span></span>

<span data-ttu-id="bd642-111">若要深入瞭解處理支援和部分索引項目目的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="bd642-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="bd642-112">Advanced eDiscovery 中支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="bd642-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="bd642-113">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="bd642-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="bd642-114">Exchange 搜尋編製索引的檔案格式</span><span class="sxs-lookup"><span data-stu-id="bd642-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="bd642-115">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="bd642-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="bd642-116">查看高級索引結果</span><span class="sxs-lookup"><span data-stu-id="bd642-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="bd642-117">在高級索引處理常式完成之後，您就可以深入瞭解重新處理的有效性。</span><span class="sxs-lookup"><span data-stu-id="bd642-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="bd642-118">在案例的 [ **處理** ] 索引標籤上，在 [高級索引結果] 視圖中，圖表會列出新增至 *混合索引* 的專案數。</span><span class="sxs-lookup"><span data-stu-id="bd642-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="bd642-119">混合索引是指 Advanced eDiscovery 儲存重新處理內容的位置。</span><span class="sxs-lookup"><span data-stu-id="bd642-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="bd642-120">此視圖也包含需要修正的專案數，以及另一個依檔案類型的錯誤圖表。</span><span class="sxs-lookup"><span data-stu-id="bd642-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="bd642-121">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="bd642-121">For more information, see:</span></span>

- [<span data-ttu-id="bd642-122">處理資料時發生補救錯誤</span><span class="sxs-lookup"><span data-stu-id="bd642-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="bd642-123">單一項目錯誤補救</span><span class="sxs-lookup"><span data-stu-id="bd642-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="bd642-124">更新保管人的高級索引</span><span class="sxs-lookup"><span data-stu-id="bd642-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="bd642-125">當保管人加入 Advanced eDiscovery 案例時，會重新處理所有部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="bd642-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="bd642-126">不過，隨著時間的推移，可將更多的索引項目目新增至使用者的信箱或 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd642-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="bd642-127">如有必要，您可以更新特定保管人的索引。</span><span class="sxs-lookup"><span data-stu-id="bd642-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="bd642-128">如需詳細資訊，請參閱[在 Advanced eDiscovery 案例中管理保管人](manage-new-custodians.md#re-index-custodian-data)。</span><span class="sxs-lookup"><span data-stu-id="bd642-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="bd642-129">您也可以在案例中，按一下 [**處理**] 索引標籤上的 [**更新索引**]，以更新所有保管人的索引。</span><span class="sxs-lookup"><span data-stu-id="bd642-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="bd642-130">更新保管人索引是一個長時間的處理常式。</span><span class="sxs-lookup"><span data-stu-id="bd642-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="bd642-131">建議您不要在案例中一天更新一次索引。</span><span class="sxs-lookup"><span data-stu-id="bd642-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
