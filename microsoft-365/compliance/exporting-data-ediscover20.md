---
title: 在高級電子檔探索中匯出案例資料
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
description: 瞭解如何在高級 eDiscovery 案例中匯出或下載簡報或外部評論的審閱集合中的內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 114264f342a51f3ce68696f321cf7c6e929dc6d1
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726472"
---
# <a name="export-case-data-in-advanced-ediscovery"></a><span data-ttu-id="e0052-103">在高級電子檔探索中匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="e0052-103">Export case data in Advanced eDiscovery</span></span>

<span data-ttu-id="e0052-104">有三種方式可以從審查集匯出資料：</span><span class="sxs-lookup"><span data-stu-id="e0052-104">There are three ways to export data from a review set:</span></span>

<span data-ttu-id="e0052-105">**下載：** 下載（使用瀏覽器）小型原生檔案集。</span><span class="sxs-lookup"><span data-stu-id="e0052-105">**Download:** Download (by using a browser) a small set of native files.</span></span> <span data-ttu-id="e0052-106">這是匯出小型資料集的最快方法。</span><span class="sxs-lookup"><span data-stu-id="e0052-106">This is the quickest way to export a small set of data.</span></span> <span data-ttu-id="e0052-107">此方法會保留原生檔案名。</span><span class="sxs-lookup"><span data-stu-id="e0052-107">This method preserves the native file names.</span></span>

<span data-ttu-id="e0052-108">**匯出：** 自訂匯出的資料。</span><span class="sxs-lookup"><span data-stu-id="e0052-108">**Export:** Customize what data is exported.</span></span> <span data-ttu-id="e0052-109">這包括匯出檔案中繼資料、原生檔案、文字檔，以及已儲存至 PDF 檔案的 redacted 檔。</span><span class="sxs-lookup"><span data-stu-id="e0052-109">This includes exporting file metadata, native files, text files, and redacted documents that have been saved to a PDF file.</span></span> <span data-ttu-id="e0052-110">將匯出的資料上傳至 Azure 存放區位置之後，您可以將它下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="e0052-110">After the exported data is uploaded to an Azure Storage location, you can download it to a local computer.</span></span> <span data-ttu-id="e0052-111">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e0052-111">For more information, see:</span></span>

- [<span data-ttu-id="e0052-112">從檢閱集匯出文件</span><span class="sxs-lookup"><span data-stu-id="e0052-112">Export documents from a review set</span></span>](export-documents-from-review-set.md)

- [<span data-ttu-id="e0052-113">下載匯出工作</span><span class="sxs-lookup"><span data-stu-id="e0052-113">Download export jobs</span></span>](download-export-jobs.md)

<span data-ttu-id="e0052-114">**新增至其他審閱集：** 將資料從一個複查集複製到不同的審閱集。</span><span class="sxs-lookup"><span data-stu-id="e0052-114">**Add to another review set:** Copy data from one review set to a different review set.</span></span> <span data-ttu-id="e0052-115">如需詳細資訊，請參閱[將資料從一個複查集新增至另一個複查集](add-data-to-review-set-from-another-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="e0052-115">For more information, see [Add data from one review set to another review set](add-data-to-review-set-from-another-review-set.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e0052-116">在 Microsoft 365 中，會雜湊資料，而這些雜湊會在輸出檔案中提供，以供驗證之用。</span><span class="sxs-lookup"><span data-stu-id="e0052-116">In Microsoft 365, data is hashed and those hashes are provided in the output file for verification purposes.</span></span> <span data-ttu-id="e0052-117">這是由審計記錄檔和報告功能（如收集統計資料、負載設定報告及匯出報告（包括匯出載入檔案）所補充。</span><span class="sxs-lookup"><span data-stu-id="e0052-117">This is supplemented by audit logs and reporting functionality, such as collection statistics, load set reports, and export reports (including the export load file).</span></span>
