---
title: 用于调查的数据的高级索引
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
ms.openlocfilehash: 3d562dbc1fc696b1e6d2acccc92f69385da49510
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076255"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="f75fe-102">用于调查的数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="f75fe-102">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="f75fe-103">由于多种原因，包括存在图像、不支持的文件类型或遇到索引文件大小限制时，实时系统中的内容可以部分编制索引。</span><span class="sxs-lookup"><span data-stu-id="f75fe-103">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="f75fe-104">在处理高风险数据溢出时，需要确保搜索捕获要调查的所有数据。</span><span class="sxs-lookup"><span data-stu-id="f75fe-104">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="f75fe-105">将感兴趣的人员添加到数据调查时，将重新处理 Office 365 中被视为部分索引的任何内容，使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="f75fe-105">When a person of interest is added to a Data investigation, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="f75fe-106">此过程称为*高级索引。*</span><span class="sxs-lookup"><span data-stu-id="f75fe-106">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="f75fe-107">要了解有关 Office 365 和部分索引项中的处理支持的更多内容，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f75fe-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="f75fe-108">数据调查中支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="f75fe-108">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="f75fe-109">位於 Office 365 中內容搜尋的已局部編製索引項目</span><span class="sxs-lookup"><span data-stu-id="f75fe-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="f75fe-110">Exchange 搜尋編製索引的檔案格式</span><span class="sxs-lookup"><span data-stu-id="f75fe-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="f75fe-111">SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型</span><span class="sxs-lookup"><span data-stu-id="f75fe-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="f75fe-112">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="f75fe-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="f75fe-113">完成高级索引过程后，您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="f75fe-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="f75fe-114">在"感兴趣的人"索引视图中，该图列出了添加到*混合索引*中的所有项。</span><span class="sxs-lookup"><span data-stu-id="f75fe-114">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="f75fe-115">混合索引是数据调查（预览）存储重新处理的内容的位置。</span><span class="sxs-lookup"><span data-stu-id="f75fe-115">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="f75fe-116">该图还包括需要修正的项数以及按文件类型划分的另一个错误图表。</span><span class="sxs-lookup"><span data-stu-id="f75fe-116">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="f75fe-117">有关详细信息，请参阅[处理数据时的错误修正。](error-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="f75fe-117">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="f75fe-118">为感兴趣的人更新高级索引</span><span class="sxs-lookup"><span data-stu-id="f75fe-118">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="f75fe-119">将感兴趣的人员添加到数据调查时，将重新处理所有部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="f75fe-119">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="f75fe-120">但是，随着时间的推移，可能会将更多部分索引的项目添加到用户的邮箱或 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="f75fe-120">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="f75fe-121">如果需要，可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="f75fe-121">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="f75fe-122">更新感兴趣的人员索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="f75fe-122">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="f75fe-123">建议您在调查中每天更新索引多次。</span><span class="sxs-lookup"><span data-stu-id="f75fe-123">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
