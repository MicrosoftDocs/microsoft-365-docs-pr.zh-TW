---
title: 執行分析以更快速地調查
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
description: 瞭解如何流量分析工具（如近期重複偵測）、電子郵件執行緒及主題，以加速調查。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e7c5103adabadf88028351f0314bcdfaa2cd4d0f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035845"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="e00ff-103">執行分析以更快速地調查</span><span class="sxs-lookup"><span data-stu-id="e00ff-103">Run analytics to investigate faster</span></span>

<span data-ttu-id="e00ff-104">當證據集合很大時，可能很難全部檢查。</span><span class="sxs-lookup"><span data-stu-id="e00ff-104">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="e00ff-105">一組證據通常包含相同或類似的電子郵件訊息或檔的多個複本。</span><span class="sxs-lookup"><span data-stu-id="e00ff-105">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="e00ff-106">資料調查（預覽）提供了許多分析工具，可協助您減少需要檢查的檔量，而不會遺失任何資訊。</span><span class="sxs-lookup"><span data-stu-id="e00ff-106">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="e00ff-107">若要深入瞭解這些功能，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e00ff-107">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="e00ff-108">近似重複項偵測</span><span class="sxs-lookup"><span data-stu-id="e00ff-108">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="e00ff-109">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="e00ff-109">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="e00ff-110">佈景主題</span><span class="sxs-lookup"><span data-stu-id="e00ff-110">Themes</span></span>](themes.md)

<span data-ttu-id="e00ff-111">若要分析證據集中的資料：</span><span class="sxs-lookup"><span data-stu-id="e00ff-111">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="e00ff-112">設定調查的分析設定。</span><span class="sxs-lookup"><span data-stu-id="e00ff-112">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="e00ff-113">如需詳細資訊，請參閱[設定搜尋及分析設定](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="e00ff-113">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="e00ff-114">開啟證據集。</span><span class="sxs-lookup"><span data-stu-id="e00ff-114">Open the evidence set.</span></span>

3. <span data-ttu-id="e00ff-115">按一下 [**管理證據**]。</span><span class="sxs-lookup"><span data-stu-id="e00ff-115">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="e00ff-116">在 [**分析**] 底下，按一下 [**分析**]。</span><span class="sxs-lookup"><span data-stu-id="e00ff-116">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="e00ff-117">您可以在調查中檢查 [**工作**] 索引標籤上的分析進度。</span><span class="sxs-lookup"><span data-stu-id="e00ff-117">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="e00ff-118">觸發的工作類型稱為「執行**分析**」。</span><span class="sxs-lookup"><span data-stu-id="e00ff-118">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="e00ff-119">分析完成之後，您可以在右邊的窗格中看到您正在審閱之檔的確切重複或臨近狀態的清單。</span><span class="sxs-lookup"><span data-stu-id="e00ff-119">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="e00ff-120">若要選取您要查看之檔的所有副本，您可以使用此面板輕鬆執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e00ff-120">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="e00ff-121">若要深入瞭解此面板上的其他功能，請參閱[查看證據中的資料](review-data-in-evidence.md)。</span><span class="sxs-lookup"><span data-stu-id="e00ff-121">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="e00ff-122">您也可以流量分析的輸出（如主題），在證據內執行其他查詢。</span><span class="sxs-lookup"><span data-stu-id="e00ff-122">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="e00ff-123">如需詳細資訊，請參閱[在證據中查詢資料](evidence-query.md)。</span><span class="sxs-lookup"><span data-stu-id="e00ff-123">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="e00ff-124">分析報告</span><span class="sxs-lookup"><span data-stu-id="e00ff-124">Analytics report</span></span>

<span data-ttu-id="e00ff-125">若要查看您的證據的分析報告：</span><span class="sxs-lookup"><span data-stu-id="e00ff-125">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="e00ff-126">開啟證據集。</span><span class="sxs-lookup"><span data-stu-id="e00ff-126">Open the evidence set.</span></span>

2. <span data-ttu-id="e00ff-127">按一下 [**管理證據**]。</span><span class="sxs-lookup"><span data-stu-id="e00ff-127">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="e00ff-128">在 [**分析**] 底下，按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="e00ff-128">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="e00ff-129">報表的分析有四個元件：</span><span class="sxs-lookup"><span data-stu-id="e00ff-129">The report has four components from analysis:</span></span>

- <span data-ttu-id="e00ff-130">**細目**-在證據集內找到的原始電子郵件、附件及檔數目。</span><span class="sxs-lookup"><span data-stu-id="e00ff-130">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="e00ff-131">**電子郵件**-inclusives、包含的 minuses、包含的副本或無上述的 eamil 郵件數目。</span><span class="sxs-lookup"><span data-stu-id="e00ff-131">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="e00ff-132">Inclusives：電子郵件執行緒中的最後一封郵件，其中包含所有先前的記錄，需要複查。</span><span class="sxs-lookup"><span data-stu-id="e00ff-132">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="e00ff-133">包含 minuses：包含一或多個需要審閱之不同附件的執行緒中的郵件。</span><span class="sxs-lookup"><span data-stu-id="e00ff-133">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="e00ff-134">包含副本：是另一個包含或非獨佔減號郵件（主旨和主體）複本的郵件。</span><span class="sxs-lookup"><span data-stu-id="e00ff-134">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="e00ff-135">**附件**-在相同的證據中，不同電子郵件附件的唯一或重複的電子郵件附件數目。</span><span class="sxs-lookup"><span data-stu-id="e00ff-135">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="e00ff-136">**檔（不包括電子郵件附件）** -需要複查的特殊檔數量，例如，接近重複集的最具代表性檔或另一個檔的完全相同的檔）。</span><span class="sxs-lookup"><span data-stu-id="e00ff-136">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>
