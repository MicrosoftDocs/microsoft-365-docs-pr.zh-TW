---
title: Advanced eDiscovery 停用相關性模組
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Advanced eDiscovery 中的相關性模組即將于2021年3月10日停用。 本文說明停用相關性之前所執行的動作。 尤其是，您可以執行批次計算來精加工任何未完成的模型，這樣您就可以保留模型中的中繼資料。
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821994"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="d0e8a-105">Advanced eDiscovery 中的相關性模組退休</span><span class="sxs-lookup"><span data-stu-id="d0e8a-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="d0e8a-106">在2021年3月10日，我們即將在 Advanced eDiscovery 中淘汰相關性模組。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="d0e8a-107">這項淘汰表示組織將無法再存取相關性模組 (，只要管理 Advanced eDiscovery 案例中的「**審閱」設定**  >  **相關性**) 或能夠存取任何現有的相關性模型。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="d0e8a-108">即將停用的目前相關性模組會取代為第2季度2021的新預測編碼解決方案。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="d0e8a-109">這項新功能可讓組織在更輕鬆且更為直觀的工作流程中建立自己的預測編碼模型。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="d0e8a-110">若要準備即將進行的退休狀態，建議使用相關性模組的組織，針對所有現有模型執行批次計算，以匯出其模型輸出。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="d0e8a-111">您的模型中的所有相關性分數會永久儲存在對應的審查集內，並可在匯出檔時加以存取。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="d0e8a-112">相關性分數也會保留為載入檔案中的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="d0e8a-113">此外，您仍然可以根據相關性分數篩選審查集中的內容，並存取相關性模型所產生的所有中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="d0e8a-114">完成未完成的模型</span><span class="sxs-lookup"><span data-stu-id="d0e8a-114">Complete unfinished models</span></span>

<span data-ttu-id="d0e8a-115">針對任何未完成的相關模型，請完成評估、訓練和批次計算，這樣您就可以將模型套用至審閱集中的檔。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="d0e8a-116">完成批次計算會保留相關性模組的退休日期之後的資訊。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="d0e8a-117">若要完成任何未完成的模型，請執行以下步驟：</span><span class="sxs-lookup"><span data-stu-id="d0e8a-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="d0e8a-118">訓練模型，直到它穩定且準備好進行批次計算。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="d0e8a-119">請參閱 [標記與相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="d0e8a-120">下列螢幕擷取畫面顯示準備好進行批次計算的模組。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="d0e8a-121">請注意，評估與訓練已完成，下一步是執行批次計算。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![可供批次計算用的模型螢幕擷取畫面](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="d0e8a-123">執行批次計算。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-123">Run the Batch calculation.</span></span> <span data-ttu-id="d0e8a-124">請參閱 [執行批次計算](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="d0e8a-125">確認批次計算成功。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="d0e8a-126">請參閱 [批次計算結果](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="d0e8a-127">如需完成未完成相關模型的協助，請與 Microsoft 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="d0e8a-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
