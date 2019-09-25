---
title: 在高级电子数据展示中分析审阅集中的数据
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
ms.openlocfilehash: b331bba76f45a11a4d1c8c0552b27759cf49608a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076744"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="439ba-102">在高级电子数据展示中分析审阅集中的数据</span><span class="sxs-lookup"><span data-stu-id="439ba-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="439ba-103">当收集的文档数量很大时，要查看所有文档可能相当困难。</span><span class="sxs-lookup"><span data-stu-id="439ba-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="439ba-104">高级电子数据展示提供了多种工具来分析文档，以减少要审阅的文档数量，而不会丢失任何信息，并帮助您以连贯的方式组织文档。</span><span class="sxs-lookup"><span data-stu-id="439ba-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="439ba-105">要了解有关这些功能的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="439ba-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="439ba-106">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="439ba-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="439ba-107">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="439ba-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="439ba-108">佈景主題</span><span class="sxs-lookup"><span data-stu-id="439ba-108">Themes</span></span>](themes.md)

<span data-ttu-id="439ba-109">要分析审阅集中的数据，请：</span><span class="sxs-lookup"><span data-stu-id="439ba-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="439ba-110">为您的案例配置分析设置。</span><span class="sxs-lookup"><span data-stu-id="439ba-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="439ba-111">有关详细信息，请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="439ba-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="439ba-112">打开要分析的审阅集。</span><span class="sxs-lookup"><span data-stu-id="439ba-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="439ba-113">**单击"管理审阅集"。**</span><span class="sxs-lookup"><span data-stu-id="439ba-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="439ba-114">**单击"为审阅集运行分析"。**</span><span class="sxs-lookup"><span data-stu-id="439ba-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="439ba-115">您可以在案例的"**作业"** 选项卡上检查分析进度。</span><span class="sxs-lookup"><span data-stu-id="439ba-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="439ba-116">分析完成后，您可以查看分析报告，在审阅集中对分析的输出运行查询（请参阅[审阅集中的查询），](review-set-search.md)并查看给定文档的相关文档（请参阅[审阅集中的数据）。](reviewing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="439ba-116">After analysis is completed, you can view analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="439ba-117">分析报告</span><span class="sxs-lookup"><span data-stu-id="439ba-117">Analytics report</span></span>

<span data-ttu-id="439ba-118">要查看审核集的分析报告：</span><span class="sxs-lookup"><span data-stu-id="439ba-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="439ba-119">打开审阅集。</span><span class="sxs-lookup"><span data-stu-id="439ba-119">Open the review set.</span></span>

2. <span data-ttu-id="439ba-120">**单击"管理审阅集"。**</span><span class="sxs-lookup"><span data-stu-id="439ba-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="439ba-121">**单击"查看报表**"。</span><span class="sxs-lookup"><span data-stu-id="439ba-121">Click **View report**.</span></span>

<span data-ttu-id="439ba-122">该报告有四个分析内容：</span><span class="sxs-lookup"><span data-stu-id="439ba-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="439ba-123">**细分**- 在审阅集中找到的电子邮件、附件和松散文档数。</span><span class="sxs-lookup"><span data-stu-id="439ba-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="439ba-124">**文档（不包括附件）** - 有多少松散文档是透视、枢轴的几乎副本或另一个文档的精确副本。</span><span class="sxs-lookup"><span data-stu-id="439ba-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="439ba-125">**电子邮件**- 包含的电子邮件数量、包含副本、包含数减数或上述任何内容均无。</span><span class="sxs-lookup"><span data-stu-id="439ba-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="439ba-126">**附件**- 审阅集中的另一个电子邮件附件中有多少电子邮件附件是唯一的或重复的。</span><span class="sxs-lookup"><span data-stu-id="439ba-126">**Attachments** - How many email attachments were unique or duplicates of a another email attachment in the review set.</span></span>