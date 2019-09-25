---
title: 執行分析以更快速地調查
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
ms.openlocfilehash: 7462b415c2e5b0a66c08bb9b5abb647f366e9785
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077572"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="6bb07-102">執行分析以更快速地調查</span><span class="sxs-lookup"><span data-stu-id="6bb07-102">Run analytics to investigate faster</span></span>

<span data-ttu-id="6bb07-103">当证据收集规模较大时，很难审查所有证据。</span><span class="sxs-lookup"><span data-stu-id="6bb07-103">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="6bb07-104">一组证据通常包括相同或类似的电子邮件或文档的多个副本。</span><span class="sxs-lookup"><span data-stu-id="6bb07-104">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="6bb07-105">数据调查 （预览版） 提供了许多分析工具，可帮助您减少需要审阅的文档数量，而不会丢失任何信息。</span><span class="sxs-lookup"><span data-stu-id="6bb07-105">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="6bb07-106">要了解有关这些功能的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6bb07-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="6bb07-107">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="6bb07-107">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="6bb07-108">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="6bb07-108">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="6bb07-109">佈景主題</span><span class="sxs-lookup"><span data-stu-id="6bb07-109">Themes</span></span>](themes.md)

<span data-ttu-id="6bb07-110">要分析证据集中的数据，请：</span><span class="sxs-lookup"><span data-stu-id="6bb07-110">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="6bb07-111">为调查配置分析设置。</span><span class="sxs-lookup"><span data-stu-id="6bb07-111">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="6bb07-112">有关详细信息，请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="6bb07-112">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="6bb07-113">打开证据集。</span><span class="sxs-lookup"><span data-stu-id="6bb07-113">Open the evidence set.</span></span>

3. <span data-ttu-id="6bb07-114">**单击"管理证据"。**</span><span class="sxs-lookup"><span data-stu-id="6bb07-114">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="6bb07-115">**在"分析"** 下，单击"**分析"。**</span><span class="sxs-lookup"><span data-stu-id="6bb07-115">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="6bb07-116">您可以在调查中的"**作业"** 选项卡上检查分析进度。</span><span class="sxs-lookup"><span data-stu-id="6bb07-116">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="6bb07-117">触发的作业类型**名为"运行分析"。**</span><span class="sxs-lookup"><span data-stu-id="6bb07-117">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="6bb07-118">分析完成后，您可以看到右侧面板中正在查看的文档的确切重复项或接近重复项的列表。</span><span class="sxs-lookup"><span data-stu-id="6bb07-118">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="6bb07-119">要选择要查看的文档的所有副本，您可以轻松地使用此面板执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6bb07-119">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="6bb07-120">要了解有关此面板中其他功能的更多详细信息，请参阅[查看证据中的数据。](review-data-in-evidence.md)</span><span class="sxs-lookup"><span data-stu-id="6bb07-120">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="6bb07-121">您还可以使用分析的输出（如主题）在证据中运行其他查询。</span><span class="sxs-lookup"><span data-stu-id="6bb07-121">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="6bb07-122">有关详细信息，请参阅[查询证据中的数据。](evidence-query.md)</span><span class="sxs-lookup"><span data-stu-id="6bb07-122">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="6bb07-123">分析报告</span><span class="sxs-lookup"><span data-stu-id="6bb07-123">Analytics report</span></span>

<span data-ttu-id="6bb07-124">要查看分析报告以提供证据：</span><span class="sxs-lookup"><span data-stu-id="6bb07-124">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="6bb07-125">打开证据集。</span><span class="sxs-lookup"><span data-stu-id="6bb07-125">Open the evidence set.</span></span>

2. <span data-ttu-id="6bb07-126">**单击"管理证据"。**</span><span class="sxs-lookup"><span data-stu-id="6bb07-126">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="6bb07-127">**在"分析"** 下，**单击"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="6bb07-127">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="6bb07-128">该报告有四个分析内容：</span><span class="sxs-lookup"><span data-stu-id="6bb07-128">The report has four components from analysis:</span></span>

- <span data-ttu-id="6bb07-129">**细分**- 在证据集中找到的原始电子邮件、附件和文档的数量。</span><span class="sxs-lookup"><span data-stu-id="6bb07-129">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="6bb07-130">**电子邮件**- 包含、包含减数、包含副本或上述任何内容的 eamil 邮件数量。</span><span class="sxs-lookup"><span data-stu-id="6bb07-130">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="6bb07-131">包含内容：电子邮件线程中包含所有以前历史记录且需要审阅的最后一条消息。</span><span class="sxs-lookup"><span data-stu-id="6bb07-131">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="6bb07-132">包含减数：线程中包含一个或多个需要审阅的不同附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="6bb07-132">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="6bb07-133">包含副本：是另一个包含或包含的减消息（主题和正文）的副本。</span><span class="sxs-lookup"><span data-stu-id="6bb07-133">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="6bb07-134">**附件**- 相同证据中不同电子邮件附件的唯一或重复的电子邮件附件数。</span><span class="sxs-lookup"><span data-stu-id="6bb07-134">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="6bb07-135">**文档（不包括电子邮件附件）** - 需要审阅的唯一文档的数量，例如，几乎重复集最具代表性的文档或另一文档的精确副本）。</span><span class="sxs-lookup"><span data-stu-id="6bb07-135">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>