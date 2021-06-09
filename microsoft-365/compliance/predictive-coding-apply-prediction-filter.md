---
title: 將預測分數篩選套用至審閱集中的專案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 使用預測分數篩選，顯示預測編碼模型預測相關或不相關的專案。
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822494"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="6de8c-103">將預測分數篩選套用至審閱集 (預覽) </span><span class="sxs-lookup"><span data-stu-id="6de8c-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="6de8c-104">在 Advanced eDiscovery 中建立預測編碼模型，並將其訓練至穩定的點之後，您可以套用預測分數篩選，以顯示模型所決定的評審專案（相關） (或不相關) 。</span><span class="sxs-lookup"><span data-stu-id="6de8c-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="6de8c-105">當您建立模型時，也會建立對應的預測分數篩選。</span><span class="sxs-lookup"><span data-stu-id="6de8c-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="6de8c-106">您可以使用此篩選器，在指定的範圍內顯示指派了預測分數的專案。</span><span class="sxs-lookup"><span data-stu-id="6de8c-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="6de8c-107">一般說來，介於 **0** 和 **0.5** 之間的預測分數會指派給模型產生預測的專案。</span><span class="sxs-lookup"><span data-stu-id="6de8c-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="6de8c-108">在 **0.5** 和 **1.0** 之間指派預測分數的專案是指模型有預測性的專案。</span><span class="sxs-lookup"><span data-stu-id="6de8c-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="6de8c-109">以下是您可以使用預測分數篩選的兩種方式：</span><span class="sxs-lookup"><span data-stu-id="6de8c-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="6de8c-110">在評審集中，依模型預測的，檢查項目的檢查優先順序是否相關。</span><span class="sxs-lookup"><span data-stu-id="6de8c-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="6de8c-111">剔除模型所預測之複查集中的專案不相關。</span><span class="sxs-lookup"><span data-stu-id="6de8c-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="6de8c-112">或者，您可以使用「預測分數」篩選取消對非相關專案的審閱優先順序。</span><span class="sxs-lookup"><span data-stu-id="6de8c-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="6de8c-113">套用預測分數篩選之前</span><span class="sxs-lookup"><span data-stu-id="6de8c-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="6de8c-114">建立預測編碼模型，以建立對應的預測分數篩選。</span><span class="sxs-lookup"><span data-stu-id="6de8c-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="6de8c-115">您可以在任何訓練四捨五入之後套用預測計分篩選。</span><span class="sxs-lookup"><span data-stu-id="6de8c-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="6de8c-116">不過，您可能想要在執行數次舍入或模型穩定之前等待，以使用預測計分篩選。</span><span class="sxs-lookup"><span data-stu-id="6de8c-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="6de8c-117">套用預測分數篩選</span><span class="sxs-lookup"><span data-stu-id="6de8c-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="6de8c-118">在 Microsoft 365 規範中心] 中，開啟 Advanced eDiscovery 案例，選取 [**複查集**] 索引標籤，然後開啟審閱集。</span><span class="sxs-lookup"><span data-stu-id="6de8c-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![按一下篩選以顯示篩選器飛出頁面](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="6de8c-120">預先載入的預設篩選器會顯示在 [審閱集合] 頁面的頂端。</span><span class="sxs-lookup"><span data-stu-id="6de8c-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="6de8c-121">您可以將這些設定保留為 **任何**。</span><span class="sxs-lookup"><span data-stu-id="6de8c-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="6de8c-122">按一下 [ **篩選** ] 以顯示 [ **篩選** ] 飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="6de8c-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="6de8c-123">展開 [ **分析 & 預測編碼** ] 區段，以顯示一組篩選器。</span><span class="sxs-lookup"><span data-stu-id="6de8c-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![分析 & 預測編碼區段中的預測分數篩選](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="6de8c-125">「預測計分」篩選的命名慣例是「 **預測分數 (模型名稱)**。</span><span class="sxs-lookup"><span data-stu-id="6de8c-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="6de8c-126">例如，名為 **Model a** 模型的預測分數篩選名稱是 **預測分數 (模型 a)**。</span><span class="sxs-lookup"><span data-stu-id="6de8c-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="6de8c-127">選取您要使用的預測分數篩選，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="6de8c-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="6de8c-128">在 [檢查集合] 頁面上，按一下 [預測分數] 篩選器的下拉式清單，並輸入預測分數範圍的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="6de8c-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="6de8c-129">例如，下列螢幕擷取畫面顯示介於 **0.5** 到 **1.0** 之間的預測分數範圍。</span><span class="sxs-lookup"><span data-stu-id="6de8c-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![預測分數篩選的最小值和最大值](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="6de8c-131">按一下篩選外部，以自動將篩選套用至審閱集。</span><span class="sxs-lookup"><span data-stu-id="6de8c-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="6de8c-132">在您指定範圍內的預測分數的檔案清單會顯示在 [審閱集合] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="6de8c-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="6de8c-133">若要查看指派給檔的實際預測分數，您可以按一下 [讀取窗格] 中的 [ **中繼資料** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6de8c-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="6de8c-134">在考核集中，所有模型的預測分數會顯示在 **RelevanceScores** 中繼資料屬性中。</span><span class="sxs-lookup"><span data-stu-id="6de8c-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="6de8c-135">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6de8c-135">More information</span></span>

- <span data-ttu-id="6de8c-136">如需使用篩選的詳細資訊，請參閱 [查詢及篩選審閱集中的內容](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="6de8c-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
