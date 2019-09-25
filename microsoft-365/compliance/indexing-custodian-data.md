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
ms.openlocfilehash: ba85ef90570dfbf2228148bf5211a4b041a1cb61
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076253"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="249a4-102">進階的監管人資料索引</span><span class="sxs-lookup"><span data-stu-id="249a4-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="249a4-103">将保管人添加到高级电子数据展示案例时，将重新处理 Office 365 中被视为部分索引的任何内容，使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="249a4-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="249a4-104">此过程称为*高级索引。*</span><span class="sxs-lookup"><span data-stu-id="249a4-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="249a4-105">内容可以部分编制索引，原因有很多，包括存在图像、不支持的文件类型或遇到索引文件大小限制。</span><span class="sxs-lookup"><span data-stu-id="249a4-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="249a4-106">要了解有关 Office 365 和部分索引项中的处理支持的更多内容，请参阅：</span><span class="sxs-lookup"><span data-stu-id="249a4-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="249a4-107">高级电子数据展示中支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="249a4-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="249a4-108">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="249a4-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="249a4-109">Exchange 搜尋編製索引的檔案格式</span><span class="sxs-lookup"><span data-stu-id="249a4-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="249a4-110">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="249a4-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="249a4-111">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="249a4-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="249a4-112">完成高级索引过程后，您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="249a4-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="249a4-113">在"保管人索引"视图中，该图列出了添加到*混合索引*中的所有项。</span><span class="sxs-lookup"><span data-stu-id="249a4-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="249a4-114">混合索引是高级电子数据展示存储重新处理的内容的位置。</span><span class="sxs-lookup"><span data-stu-id="249a4-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="249a4-115">该图还包括需要修正的项数以及按文件类型划分的另一个错误图表。</span><span class="sxs-lookup"><span data-stu-id="249a4-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="249a4-116">有关详细信息，请参阅[处理数据时的错误修正。](error-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="249a4-116">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="249a4-117">更新保管人的高级索引</span><span class="sxs-lookup"><span data-stu-id="249a4-117">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="249a4-118">将保管人添加到高级电子数据展示案例时，将重新处理所有部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="249a4-118">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="249a4-119">但是，随着时间的推移，可能会将更多部分索引的项目添加到用户的邮箱或 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="249a4-119">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="249a4-120">如果需要，可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="249a4-120">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="249a4-121">更新保管人索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="249a4-121">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="249a4-122">建议您每天更新索引多次。</span><span class="sxs-lookup"><span data-stu-id="249a4-122">It's recommended that you don't update indexes more than once per day in a case.</span></span>
