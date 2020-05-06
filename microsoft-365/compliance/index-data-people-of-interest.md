---
title: 調查的高級資料索引
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
description: 瞭解如何使用高級索引，確定您的搜尋會捕獲您要調查的所有資料。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc7d73c233aa48b88e9dce32fad613ccc5e19333
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035059"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="a6519-103">調查的高級資料索引</span><span class="sxs-lookup"><span data-stu-id="a6519-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="a6519-104">即時系統中的內容可以部分編制索引，原因很多，包括影像存在、不支援的檔案類型，或是在遇到索引檔案大小限制時。</span><span class="sxs-lookup"><span data-stu-id="a6519-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="a6519-105">當您處理高風險資料溢出時，您想要確保搜尋已捕獲所有想要調查的資料。</span><span class="sxs-lookup"><span data-stu-id="a6519-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="a6519-106">當相關人員加入資料調查時，會重新處理被視為部分索引的任何內容，使其完全可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="a6519-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="a6519-107">此處理程式稱為「*高級索引*」。</span><span class="sxs-lookup"><span data-stu-id="a6519-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="a6519-108">若要深入瞭解處理支援和部分索引項目目的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="a6519-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="a6519-109">資料調查中支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="a6519-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="a6519-110">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="a6519-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="a6519-111">Exchange 搜尋編製索引的檔案格式</span><span class="sxs-lookup"><span data-stu-id="a6519-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="a6519-112">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="a6519-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="a6519-113">查看高級索引結果</span><span class="sxs-lookup"><span data-stu-id="a6519-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="a6519-114">在高級索引處理常式完成之後，您就可以深入瞭解重新處理的有效性。</span><span class="sxs-lookup"><span data-stu-id="a6519-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="a6519-115">在重要的 [索引視圖人員] 中，圖表會列出新增至*混合索引*的所有專案。</span><span class="sxs-lookup"><span data-stu-id="a6519-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="a6519-116">混合索引是資料調查（預覽）儲存重新處理內容的所在位置。</span><span class="sxs-lookup"><span data-stu-id="a6519-116">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="a6519-117">此圖也包含需要修正的專案數，以及另一個依檔案類型的錯誤圖表。</span><span class="sxs-lookup"><span data-stu-id="a6519-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="a6519-118">如需詳細資訊，請參閱[在處理資料時進行錯誤修正](error-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="a6519-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="a6519-119">更新感興趣人員的高級索引</span><span class="sxs-lookup"><span data-stu-id="a6519-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="a6519-120">當相關人員加入資料調查時，會重新處理所有部分索引項目目。</span><span class="sxs-lookup"><span data-stu-id="a6519-120">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="a6519-121">不過，隨著時間的推移，可將更多的索引項目目新增至使用者的信箱或 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a6519-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="a6519-122">如有需要，您可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="a6519-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="a6519-123">更新感興趣的索引人員會執行很長的處理常式。</span><span class="sxs-lookup"><span data-stu-id="a6519-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="a6519-124">建議您不要在調查中每日更新一次以上的索引。</span><span class="sxs-lookup"><span data-stu-id="a6519-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
