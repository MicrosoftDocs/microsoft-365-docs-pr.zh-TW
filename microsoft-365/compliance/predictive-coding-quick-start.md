---
title: Advanced eDiscovery 中的預測編碼-快速入門
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
description: 瞭解如何開始使用 Advanced eDiscovery 中的預測編碼模組。 本文將引導您完成使用預測編碼的端對端程式，以在與調查最相關的評審集中識別內容。
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822510"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="8d85e-104">快速入門： Advanced eDiscovery (預覽中的預測編碼) </span><span class="sxs-lookup"><span data-stu-id="8d85e-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="8d85e-105">本文提供在 Advanced eDiscovery 中使用預測性編碼的快速入門。</span><span class="sxs-lookup"><span data-stu-id="8d85e-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="8d85e-106">Advanced eDiscovery 中的預測編碼模組使用 Advanced eDiscovery 中的智慧機學習功能，協助您減少要查看的內容數量。</span><span class="sxs-lookup"><span data-stu-id="8d85e-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="8d85e-107">預測編碼可協助您將大量案例內容縮小及挑選為一組可供查看的相關專案。</span><span class="sxs-lookup"><span data-stu-id="8d85e-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="8d85e-108">這是透過建立及訓練您自己的預測編碼模型，協助您在評審集中查看最相關專案的優先順序。</span><span class="sxs-lookup"><span data-stu-id="8d85e-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="8d85e-109">以下是預測編碼程式的快速綜述：</span><span class="sxs-lookup"><span data-stu-id="8d85e-109">Here's an a quick overview of the predictive coding process:</span></span>

![預測編碼的快速啟動程式](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="8d85e-111">若要開始使用，您可以建立模型，並將其標籤為相關或不相關的50專案。</span><span class="sxs-lookup"><span data-stu-id="8d85e-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="8d85e-112">然後系統會使用這項訓練，將預測分數套用至評審集合中的每個專案。</span><span class="sxs-lookup"><span data-stu-id="8d85e-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="8d85e-113">這可讓您根據預測分數來篩選項目，這可讓您先查看最相關的 (或非相關的) 專案。</span><span class="sxs-lookup"><span data-stu-id="8d85e-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="8d85e-114">如果您想要使用較高的精度和重新叫付率訓練模型，您可以在後續訓練中繼續標示專案，直到模型穩定為止。</span><span class="sxs-lookup"><span data-stu-id="8d85e-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="8d85e-115">一旦模型穩定，您可以套用最後的預測篩選，以優先處理要查看的專案。</span><span class="sxs-lookup"><span data-stu-id="8d85e-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="8d85e-116">如需預測編碼的詳細資訊，請參閱[瞭解 Advanced eDiscovery 中的預測編碼](predictive-coding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8d85e-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="8d85e-117">步驟1：建立新的預測編碼模型</span><span class="sxs-lookup"><span data-stu-id="8d85e-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="8d85e-118">第一步是在審查集內建立新的預測編碼模型。</span><span class="sxs-lookup"><span data-stu-id="8d85e-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="8d85e-119">在 Microsoft 365 規範中心] 中，開啟 Advanced eDiscovery 案例，然後選取 [**複查集**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8d85e-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="8d85e-120">開啟一個複查集，然後按一下 [**分析**  >  **管理預測編碼 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="8d85e-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![按一下 [檢查集合] 中的 [分析] 下拉式功能表，以移至 [預測編碼] 頁面](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="8d85e-122">在 [ **預測編碼模型] (預覽)** ] 頁面上，按一下 [ **新增模型**]。</span><span class="sxs-lookup"><span data-stu-id="8d85e-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="8d85e-123">在 [飛入] 頁面上，輸入模型的名稱和選用的描述。</span><span class="sxs-lookup"><span data-stu-id="8d85e-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="8d85e-124">按一下 [ **儲存** ] 以建立模型。</span><span class="sxs-lookup"><span data-stu-id="8d85e-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="8d85e-125">系統會花幾分鐘的時間來準備您的模型。</span><span class="sxs-lookup"><span data-stu-id="8d85e-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="8d85e-126">準備好後，您就可以執行第一輪訓練。</span><span class="sxs-lookup"><span data-stu-id="8d85e-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="8d85e-127">如需詳細指示，請參閱 [建立預測編碼模型](predictive-coding-create-model.md)。</span><span class="sxs-lookup"><span data-stu-id="8d85e-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="8d85e-128">步驟2：執行第一輪訓練</span><span class="sxs-lookup"><span data-stu-id="8d85e-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="8d85e-129">在您建立模型之後，下一步是將專案標記為相關或不相關，以完成第一個訓練舍入。</span><span class="sxs-lookup"><span data-stu-id="8d85e-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="8d85e-130">開啟審閱集，然後按一下 [**分析**  >  **管理預測編碼 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="8d85e-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="8d85e-131">在 [ **預測編碼模型] (預覽)** ] 頁面上，選取您要訓練的模型。</span><span class="sxs-lookup"><span data-stu-id="8d85e-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="8d85e-132">在 [ **一覽** ] 索引標籤的 [ **圓形 1**] 底下，按一下 **[開始下一個訓練圓形**]。</span><span class="sxs-lookup"><span data-stu-id="8d85e-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="8d85e-133">[ **訓練** ] 索引標籤隨即顯示，並包含50個專案供您用標籤。</span><span class="sxs-lookup"><span data-stu-id="8d85e-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="8d85e-134">請複習每份檔，然後選取 [讀取窗格] 底部的 [ **相關** ] 或 [ **不相關** ] 按鈕，以進行標籤。</span><span class="sxs-lookup"><span data-stu-id="8d85e-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![將每個檔標示為相關或不相關](..\media\TrainModel1.png)

5. <span data-ttu-id="8d85e-136">在您標示所有50專案之後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8d85e-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="8d85e-137">系統會花幾分鐘的時間，讓系統從您的標記 "瞭解" 並更新模型。</span><span class="sxs-lookup"><span data-stu-id="8d85e-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="8d85e-138">完成此程式之後，就會在 **預測編碼模型 (預覽)** ] 頁面上顯示模型的狀態 [**就緒**]。</span><span class="sxs-lookup"><span data-stu-id="8d85e-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="8d85e-139">如需詳細指示，請參閱 [訓練預測編碼模型](predictive-coding-train-model.md)。</span><span class="sxs-lookup"><span data-stu-id="8d85e-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="8d85e-140">步驟3：對評審集中的專案套用預測分數篩選器</span><span class="sxs-lookup"><span data-stu-id="8d85e-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="8d85e-141">在您執行租用一次訓練時，您可以將預測分數篩選器套用至考核組中的專案。</span><span class="sxs-lookup"><span data-stu-id="8d85e-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="8d85e-142">這可讓您查看模型預測的專案（相關或不相關）。</span><span class="sxs-lookup"><span data-stu-id="8d85e-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="8d85e-143">開啟審閱集。</span><span class="sxs-lookup"><span data-stu-id="8d85e-143">Open the review set.</span></span>

   ![按一下篩選以顯示篩選器飛出頁面](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="8d85e-145">預先載入的預設篩選器會顯示在 [審閱集合] 頁面的頂端。</span><span class="sxs-lookup"><span data-stu-id="8d85e-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="8d85e-146">您可以將這些設定保留為 **任何**。</span><span class="sxs-lookup"><span data-stu-id="8d85e-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="8d85e-147">按一下 [ **篩選** ] 以顯示 [ **篩選** ] 飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="8d85e-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="8d85e-148">展開 [ **分析 & 預測編碼** ] 區段，以顯示一組篩選器。</span><span class="sxs-lookup"><span data-stu-id="8d85e-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![分析 & 預測編碼區段中的預測分數篩選](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="8d85e-150">「預測計分」篩選的命名慣例是「 **預測分數 (模型名稱)**。</span><span class="sxs-lookup"><span data-stu-id="8d85e-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="8d85e-151">例如，名為 **Model a** 模型的預測分數篩選名稱是 **預測分數 (模型 a)**。</span><span class="sxs-lookup"><span data-stu-id="8d85e-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="8d85e-152">選取您要使用的預測分數篩選，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="8d85e-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="8d85e-153">在 [檢查集合] 頁面上，按一下 [預測分數] 篩選器的下拉式清單，並輸入預測分數範圍的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="8d85e-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="8d85e-154">例如，下列螢幕擷取畫面顯示介於 **0.5** 到 **1.0** 之間的預測分數範圍。</span><span class="sxs-lookup"><span data-stu-id="8d85e-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![預測分數篩選的最小值和最大值](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="8d85e-156">按一下篩選外部，以自動將篩選套用至審閱集。</span><span class="sxs-lookup"><span data-stu-id="8d85e-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="8d85e-157">在您指定範圍內的預測分數的檔案清單會顯示在 [審閱集合] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="8d85e-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="8d85e-158">如需詳細指示，請參閱 [Apply a 聯想 filter to a 審校 set](predictive-coding-apply-prediction-filter.md)。</span><span class="sxs-lookup"><span data-stu-id="8d85e-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="8d85e-159">步驟4：執行更多訓練舍入</span><span class="sxs-lookup"><span data-stu-id="8d85e-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="8d85e-160">您可能需要執行更多訓練，以訓練模組，以更好地預測評審集中的相關和非相關專案。</span><span class="sxs-lookup"><span data-stu-id="8d85e-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="8d85e-161">一般來講，您會訓練模型足夠的時間，直到達到滿足您需求的足夠穩定為止。</span><span class="sxs-lookup"><span data-stu-id="8d85e-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="8d85e-162">如需詳細資訊，請參閱 [執行其他訓練舍入](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="8d85e-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="8d85e-163">步驟5：套用最後的預測分數篩選，以優先審閱</span><span class="sxs-lookup"><span data-stu-id="8d85e-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="8d85e-164">重複步驟3中的指示，將最後的預測分數套用至檢查集合，以在完成所有訓練並使模型穩定後，排定相關和非相關專案的複查優先順序。</span><span class="sxs-lookup"><span data-stu-id="8d85e-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
