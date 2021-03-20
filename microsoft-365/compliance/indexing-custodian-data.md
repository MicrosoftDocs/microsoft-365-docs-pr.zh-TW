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
description: 當保管人新增至高級 eDiscovery 案例時，被視為部分索引的任何內容都會重新處理，使其完全可供搜尋。
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911207"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="05344-103">進階的監管人資料索引</span><span class="sxs-lookup"><span data-stu-id="05344-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="05344-104">當保管人新增至高級 eDiscovery 案例時，被視為部分索引的任何內容都會重新處理，使其完全可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="05344-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="05344-105">此處理程式稱為「 *高級索引*」。</span><span class="sxs-lookup"><span data-stu-id="05344-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="05344-106">內容可能會因原因而部分編制索引，包括映射的存在、不支援的檔案類型，或是遇到索引檔案大小限制。</span><span class="sxs-lookup"><span data-stu-id="05344-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="05344-107">若要深入瞭解處理支援和部分索引項目目的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="05344-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="05344-108">高級 eDiscovery 中支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="05344-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="05344-109">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="05344-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="05344-110">Exchange 搜尋編製索引的檔案格式</span><span class="sxs-lookup"><span data-stu-id="05344-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="05344-111">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="05344-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="05344-112">查看高級索引結果</span><span class="sxs-lookup"><span data-stu-id="05344-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="05344-113">在高級索引處理常式完成之後，您就可以深入瞭解重新處理的有效性。</span><span class="sxs-lookup"><span data-stu-id="05344-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="05344-114">在案例的 [ **處理** ] 索引標籤上，在 [高級索引結果] 視圖中，圖表會列出新增至 *混合索引* 的專案數。</span><span class="sxs-lookup"><span data-stu-id="05344-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="05344-115">混合索引是指 Advanced eDiscovery 儲存重新處理內容的位置。</span><span class="sxs-lookup"><span data-stu-id="05344-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="05344-116">此視圖也包含需要修正的專案數，以及另一個依檔案類型的錯誤圖表。</span><span class="sxs-lookup"><span data-stu-id="05344-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="05344-117">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="05344-117">For more information, see:</span></span>

- [<span data-ttu-id="05344-118">處理資料時發生補救錯誤</span><span class="sxs-lookup"><span data-stu-id="05344-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="05344-119">單一項目錯誤補救</span><span class="sxs-lookup"><span data-stu-id="05344-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="05344-120">更新保管人的高級索引</span><span class="sxs-lookup"><span data-stu-id="05344-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="05344-121">當系統管理員新增至高級 eDiscovery 案例時，會重新處理所有部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="05344-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="05344-122">不過，隨著時間的推移，可將更多的索引項目目新增至使用者的信箱或 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="05344-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="05344-123">如有必要，您可以更新特定保管人的索引。</span><span class="sxs-lookup"><span data-stu-id="05344-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="05344-124">如需詳細資訊，請參閱 [Manage 保管人 In Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data)。</span><span class="sxs-lookup"><span data-stu-id="05344-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="05344-125">您也可以在案例中，按一下 [**處理**] 索引標籤上的 [**更新索引**]，以更新所有保管人的索引。</span><span class="sxs-lookup"><span data-stu-id="05344-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="05344-126">更新保管人索引是一個長時間的處理常式。</span><span class="sxs-lookup"><span data-stu-id="05344-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="05344-127">建議您不要在案例中一天更新一次索引。</span><span class="sxs-lookup"><span data-stu-id="05344-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>