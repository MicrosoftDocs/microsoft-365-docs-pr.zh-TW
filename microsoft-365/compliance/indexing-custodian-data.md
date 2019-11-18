---
title: 進階的監管人資料索引
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
ms.openlocfilehash: a6259d839dd9a0ca196bae37afe374d1d8f21d53
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2019
ms.locfileid: "38685511"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="08cfc-102">進階的監管人資料索引</span><span class="sxs-lookup"><span data-stu-id="08cfc-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="08cfc-103">Custodian 會新增至進階電子文件探索案例中，已被視為的 Office 365 中的所有內容已局部編製索引都時，使其成為完整搜尋重新處理。</span><span class="sxs-lookup"><span data-stu-id="08cfc-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="08cfc-104">此程序稱為 「*進階編製索引*」。</span><span class="sxs-lookup"><span data-stu-id="08cfc-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="08cfc-105">內容可以是已局部編製索引數量的原因包括影像、 不支援的檔案類型或時遇到索引檔案大小限制存在。</span><span class="sxs-lookup"><span data-stu-id="08cfc-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="08cfc-106">若要深入了解關於處理 Office 365 和已局部編製索引的項目中支援的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="08cfc-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="08cfc-107">在進階電子文件中支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="08cfc-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="08cfc-108">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="08cfc-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="08cfc-109">Exchange 搜尋編製索引的檔案格式</span><span class="sxs-lookup"><span data-stu-id="08cfc-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="08cfc-110">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="08cfc-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="08cfc-111">檢視進階索引的結果</span><span class="sxs-lookup"><span data-stu-id="08cfc-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="08cfc-112">進階的索引程序完成之後，您可以取得的重新處理效率了解。</span><span class="sxs-lookup"><span data-stu-id="08cfc-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="08cfc-113">在 Custodian 編製索引] 檢視中，此圖形會列出所有的項目新增至*混合式索引*。</span><span class="sxs-lookup"><span data-stu-id="08cfc-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="08cfc-114">混合式索引是進階電子文件重新處理的內容，儲存位置。</span><span class="sxs-lookup"><span data-stu-id="08cfc-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="08cfc-115">此圖形也包含需要修復的項目數與另一個圖形的檔案類型的錯誤。</span><span class="sxs-lookup"><span data-stu-id="08cfc-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="08cfc-116">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="08cfc-116">For more information, see:</span></span>

- [<span data-ttu-id="08cfc-117">處理資料時發生補救錯誤</span><span class="sxs-lookup"><span data-stu-id="08cfc-117">Error remediation when processing data</span></span>](error-remediation.md)
- [<span data-ttu-id="08cfc-118">單一項目錯誤補救</span><span class="sxs-lookup"><span data-stu-id="08cfc-118">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="08cfc-119">更新 custodians 進階的索引</span><span class="sxs-lookup"><span data-stu-id="08cfc-119">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="08cfc-120">當 custodian 加入至進階電子文件探索案例時，所有已局部編製索引的項目會重新處理。</span><span class="sxs-lookup"><span data-stu-id="08cfc-120">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="08cfc-121">不過，經過一段時間，更局部編製索引的項目可能會新增至使用者的信箱或 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="08cfc-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="08cfc-122">視需要，您可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="08cfc-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="08cfc-123">更新 custodian 索引是一個長時間執行的程序。</span><span class="sxs-lookup"><span data-stu-id="08cfc-123">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="08cfc-124">最好不要更新索引每天案例中的一次以上。</span><span class="sxs-lookup"><span data-stu-id="08cfc-124">It's recommended that you don't update indexes more than once per day in a case.</span></span>
