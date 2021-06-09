---
title: 在 Advanced eDiscovery 中分析審閱集中的資料
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
description: 瞭解在分析 Advanced eDiscovery 案例時可用於組織檔組的工具。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751368"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="94eb8-103">在 Advanced eDiscovery 中分析審閱集中的資料</span><span class="sxs-lookup"><span data-stu-id="94eb8-103">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="94eb8-104">當收集的檔數目很大時，可能很難全部查看。</span><span class="sxs-lookup"><span data-stu-id="94eb8-104">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="94eb8-105">Advanced eDiscovery 提供許多工具來分析檔，以減少要檢查的檔量，而不會遺失資訊，以及協助您以一致的方式組織檔。</span><span class="sxs-lookup"><span data-stu-id="94eb8-105">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="94eb8-106">若要深入瞭解這些功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="94eb8-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="94eb8-107">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="94eb8-107">Near duplicate detection</span></span>](near-duplicate-detection-in-advanced-ediscovery.md)

- [<span data-ttu-id="94eb8-108">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="94eb8-108">Email threading</span></span>](email-threading-in-advanced-ediscovery.md)

- [<span data-ttu-id="94eb8-109">佈景主題</span><span class="sxs-lookup"><span data-stu-id="94eb8-109">Themes</span></span>](themes-in-advanced-ediscovery.md)

<span data-ttu-id="94eb8-110">若要分析審閱集中的資料：</span><span class="sxs-lookup"><span data-stu-id="94eb8-110">To analyze data in a review set:</span></span>

1. <span data-ttu-id="94eb8-111">設定案例的分析設定。</span><span class="sxs-lookup"><span data-stu-id="94eb8-111">Configure analytics settings for your case.</span></span> <span data-ttu-id="94eb8-112">如需詳細資訊，請參閱 [設定搜尋及分析設定](configure-search-and-analytics-settings-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="94eb8-112">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).</span></span>

2. <span data-ttu-id="94eb8-113">開啟您要分析的複查集。</span><span class="sxs-lookup"><span data-stu-id="94eb8-113">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="94eb8-114">按一下 [ **管理審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="94eb8-114">Click **Manage review set**.</span></span>

4. <span data-ttu-id="94eb8-115">**針對審閱集按一下 [執行分析**]。</span><span class="sxs-lookup"><span data-stu-id="94eb8-115">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="94eb8-116">您可以在案例的 [ **作業** ] 索引標籤上檢查分析進度。</span><span class="sxs-lookup"><span data-stu-id="94eb8-116">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="94eb8-117">分析完成之後，您可以在分析的輸出上，查看分析報告、執行查詢 (中的查詢。請參閱在 [您的複查集中查詢](review-set-search.md)) ]，然後查看指定檔的相關檔 (請參閱 [複習 data in report set](reviewing-data-in-review-set.md)) 。</span><span class="sxs-lookup"><span data-stu-id="94eb8-117">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="94eb8-118">分析報告</span><span class="sxs-lookup"><span data-stu-id="94eb8-118">Analytics report</span></span>

<span data-ttu-id="94eb8-119">若要查看複查集的分析報告：</span><span class="sxs-lookup"><span data-stu-id="94eb8-119">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="94eb8-120">開啟審閱集。</span><span class="sxs-lookup"><span data-stu-id="94eb8-120">Open the review set.</span></span>

2. <span data-ttu-id="94eb8-121">按一下 [ **管理審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="94eb8-121">Click **Manage review set**.</span></span>

3. <span data-ttu-id="94eb8-122">按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="94eb8-122">Click **View report**.</span></span>

<span data-ttu-id="94eb8-123">報告中有七個元件可供分析：</span><span class="sxs-lookup"><span data-stu-id="94eb8-123">The report has seven components from analysis:</span></span>

- <span data-ttu-id="94eb8-124">**目標人口：** 在審閱集中找到的電子郵件訊息、附件和鬆散檔的數目。</span><span class="sxs-lookup"><span data-stu-id="94eb8-124">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="94eb8-125">**檔 (排除附件) ：** 旋轉的鬆散檔數目、重複接近的樞紐分析表或其他檔的完全相同的數目。</span><span class="sxs-lookup"><span data-stu-id="94eb8-125">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="94eb8-126">**電子郵件：** Inclusives、包含的副本、包含的 minuses 或無上述的電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="94eb8-126">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="94eb8-127">**附件：** 審閱集中其他電子郵件附件的唯一或重複的電子郵件附件數目。</span><span class="sxs-lookup"><span data-stu-id="94eb8-127">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="94eb8-128">**依類型的檔數目：** 以 file extension 識別的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="94eb8-128">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="94eb8-129">**檔來源來源：** 內容摘要（依其原始的資料來源）。</span><span class="sxs-lookup"><span data-stu-id="94eb8-129">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="94eb8-130">**依處理匯總的檔：** 依考核集流程的內容摘要。</span><span class="sxs-lookup"><span data-stu-id="94eb8-130">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
