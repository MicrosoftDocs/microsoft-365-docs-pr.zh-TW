---
title: 为审阅集生成搜索词报告
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078148"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="b91c1-102">为审阅集生成搜索词报告</span><span class="sxs-lookup"><span data-stu-id="b91c1-102">Generate search term report for a review set</span></span>

<span data-ttu-id="b91c1-103">在电子数据展示中，查询文档最常用的条件之一是使用关键字搜索词。</span><span class="sxs-lookup"><span data-stu-id="b91c1-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="b91c1-104">通过识别包含对案例很重要的特定关键字（也称为*术语）* 的文档，审阅者可以开始深入了解他们所面临的问题。</span><span class="sxs-lookup"><span data-stu-id="b91c1-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="b91c1-105">在 Microsoft 365 中的高级电子数据展示中，您可以通过在审阅集中生成搜索字词报告来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b91c1-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="b91c1-106">步骤 1：在审阅集中创建保存的查询</span><span class="sxs-lookup"><span data-stu-id="b91c1-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="b91c1-107">要生成有意义的搜索词报表，请创建一个保存的查询，该查询定义要为其生成搜索词报表的审阅集中的文档集。</span><span class="sxs-lookup"><span data-stu-id="b91c1-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="b91c1-108">例如，可以使用日期范围或实际搜索词集（通过使用关键字条件卡）来创建查询。</span><span class="sxs-lookup"><span data-stu-id="b91c1-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="b91c1-109">要了解有关审阅集查询的更多详细信息，请参阅[查询审阅集中的数据。](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="b91c1-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="b91c1-110">第 2 步：生成搜索词报告</span><span class="sxs-lookup"><span data-stu-id="b91c1-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="b91c1-111">生成搜索字词报表的方法有两种：通过在步骤 1 中创建的已保存查询的上下文菜单，或通过搜索词报表管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b91c1-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="b91c1-112">要使用上下文菜单，请打开在步骤 1 中创建的已保存查询的上下文菜单，**然后单击"生成搜索词报告"。**</span><span class="sxs-lookup"><span data-stu-id="b91c1-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="b91c1-113">要使用管理控制台，请**转到"管理审阅集>查看搜索词报告，\*\*\*\*单击"新建"，** 然后选择您在步骤 1 中创建的已保存查询。</span><span class="sxs-lookup"><span data-stu-id="b91c1-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="b91c1-114">然后，输入您要报告的术语，用排行分隔;如果在步骤 1 中创建的已保存查询使用了关键字条件卡，则弹出窗口将预填充来自已保存查询中使用的第一个关键字条件卡中的字词。</span><span class="sxs-lookup"><span data-stu-id="b91c1-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="b91c1-115">然后，选择最多三个要报告的透视，**然后单击"生成"，** 这将启动搜索词报表生成作业。</span><span class="sxs-lookup"><span data-stu-id="b91c1-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="b91c1-116">什么是枢轴？</span><span class="sxs-lookup"><span data-stu-id="b91c1-116">What is a pivot?</span></span>

<span data-ttu-id="b91c1-117">数据透视是报表的组织方式。</span><span class="sxs-lookup"><span data-stu-id="b91c1-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="b91c1-118">请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="b91c1-118">Consider the following example.</span></span>

- <span data-ttu-id="b91c1-119">保存的查询检索 10 个文档：doc1 到 doc10。</span><span class="sxs-lookup"><span data-stu-id="b91c1-119">The saved query retrieves 10 documents: doc1 thru doc10.</span></span>

- <span data-ttu-id="b91c1-120">doc1、doc2、doc3、doc4、doc5、doc6 和 doc7 包含术语"电子数据展示"。</span><span class="sxs-lookup"><span data-stu-id="b91c1-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="b91c1-121">doc6、doc7、doc8、doc9 和 doc10 包含术语"调查"。</span><span class="sxs-lookup"><span data-stu-id="b91c1-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="b91c1-122">单1、doc3、doc5、doc7、doc9均来自保管人A。</span><span class="sxs-lookup"><span data-stu-id="b91c1-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="b91c1-123">doc2、doc4、doc6、doc8、doc10 均来自保管人 B。</span><span class="sxs-lookup"><span data-stu-id="b91c1-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="b91c1-124">在这种情况下，如果您要生成关于术语"电子数据展示"和"调查"的搜索字词报告，并基于保管人，则搜索字词报告将组织如下：</span><span class="sxs-lookup"><span data-stu-id="b91c1-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="b91c1-125">"电子数据展示" - 保管人 A：4 份文件</span><span class="sxs-lookup"><span data-stu-id="b91c1-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="b91c1-126">"电子数据展示" - 保管人 B：3 份文件</span><span class="sxs-lookup"><span data-stu-id="b91c1-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="b91c1-127">"调查" - 保管人 A：2份文件</span><span class="sxs-lookup"><span data-stu-id="b91c1-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="b91c1-128">"调查" - 保管人 B：3份文件</span><span class="sxs-lookup"><span data-stu-id="b91c1-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="b91c1-129">第 3 步：下载报告</span><span class="sxs-lookup"><span data-stu-id="b91c1-129">Step 3: Download report</span></span>

<span data-ttu-id="b91c1-130">在搜索字词管理控制台中，可以跟踪以前创建的搜索词报表作业的状态。</span><span class="sxs-lookup"><span data-stu-id="b91c1-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="b91c1-131">作业完成后，您可以单击搜索词报告的行并单击"下载"，这将以 CSV 格式下载搜索词报告。</span><span class="sxs-lookup"><span data-stu-id="b91c1-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="b91c1-132">每个组（搜索术语、枢轴）组组将有一行，每行将包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="b91c1-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="b91c1-133">检索了多少文档？</span><span class="sxs-lookup"><span data-stu-id="b91c1-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="b91c1-134">在文档中找到搜索字词多少次？</span><span class="sxs-lookup"><span data-stu-id="b91c1-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="b91c1-135">检索到的文档的总数量是多少？</span><span class="sxs-lookup"><span data-stu-id="b91c1-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="b91c1-136">被找回了多少个家庭？</span><span class="sxs-lookup"><span data-stu-id="b91c1-136">How many families were retrieved?</span></span>

- <span data-ttu-id="b91c1-137">这些系列的文档总数是多少，包括没有搜索字词的文档？</span><span class="sxs-lookup"><span data-stu-id="b91c1-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="b91c1-138">上述总体积是多少？</span><span class="sxs-lookup"><span data-stu-id="b91c1-138">What is the total volume of the above?</span></span>