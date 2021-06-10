---
title: 訓練 Advanced eDiscovery 中的預測編碼模型
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
description: ''
ms.openlocfilehash: ef6d1cf23d6cca58f4226696bc63c1dea5816cc1
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822506"
---
# <a name="train-a-predictive-coding-model-preview"></a><span data-ttu-id="25b33-102">訓練 (預覽的預測編碼模型) </span><span class="sxs-lookup"><span data-stu-id="25b33-102">Train a predictive coding model (preview)</span></span>

<span data-ttu-id="25b33-103">在 Advanced eDiscovery 中建立預測編碼模型之後，下一步是執行第一個訓練，以訓練模型對您的審閱集中的相關和非相關內容的相關訓練。</span><span class="sxs-lookup"><span data-stu-id="25b33-103">After you create a predictive coding model in Advanced eDiscovery, the next step is to performing the first training round to train the model on what is relevant and non-relevant content in your review set.</span></span> <span data-ttu-id="25b33-104">在您完成第一輪訓練後，您可以執行後續訓練，以提升模型預測相關和非相關內容的能力。</span><span class="sxs-lookup"><span data-stu-id="25b33-104">After you complete the first round of training, you can perform subsequent training rounds to improve the model's ability to predict relevant and non-relevant content.</span></span>

<span data-ttu-id="25b33-105">若要查看預測編碼工作流程，請參閱[瞭解 Advanced eDiscovery 中的預測編碼](predictive-coding-overview.md#the-predictive-coding-workflow)</span><span class="sxs-lookup"><span data-stu-id="25b33-105">To review the predictive coding workflow, see [Learn about predictive coding in Advanced eDiscovery ](predictive-coding-overview.md#the-predictive-coding-workflow)</span></span>

## <a name="before-you-train-a-model"></a><span data-ttu-id="25b33-106">訓練模型之前</span><span class="sxs-lookup"><span data-stu-id="25b33-106">Before you train a model</span></span>

- <span data-ttu-id="25b33-107">在訓練過程中，會根據檔內容的關聯性，將專案標籤設為 **相關** 或 **不相關** 。</span><span class="sxs-lookup"><span data-stu-id="25b33-107">During a training round, label items as **Relevant** or **Not relevant** based on the relevancy of the content in the document.</span></span> <span data-ttu-id="25b33-108">請勿根據元資料欄位中的值進行決策。</span><span class="sxs-lookup"><span data-stu-id="25b33-108">Don't base your decision on the values in the metadata fields.</span></span> <span data-ttu-id="25b33-109">例如，電子郵件訊息或 Teams 交談，請勿將您的標記決定于郵件參與者。</span><span class="sxs-lookup"><span data-stu-id="25b33-109">For example, for email messages or Teams conversations, don't base your labeling decision on the message participants.</span></span> 

## <a name="train-a-model-for-the-first-time"></a><span data-ttu-id="25b33-110">第一次訓練模型</span><span class="sxs-lookup"><span data-stu-id="25b33-110">Train a model for the first time</span></span>

1. <span data-ttu-id="25b33-111">在 Microsoft 365 規範中心] 中，開啟 Advanced eDiscovery 案例，然後選取 [**複查集**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="25b33-111">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="25b33-112">開啟一個複查集，然後按一下 [**分析**  >  **管理預測編碼 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="25b33-112">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

3. <span data-ttu-id="25b33-113">在 [ **預測編碼模型] (預覽)** ] 頁面上，選取您要訓練的模型。</span><span class="sxs-lookup"><span data-stu-id="25b33-113">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

4. <span data-ttu-id="25b33-114">在 [ **一覽** ] 索引標籤的 [ **圓形 1**] 底下，按一下 **[開始下一個訓練圓形**]。</span><span class="sxs-lookup"><span data-stu-id="25b33-114">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="25b33-115">[ **訓練** ] 索引標籤隨即顯示，並包含50個專案供您用標籤。</span><span class="sxs-lookup"><span data-stu-id="25b33-115">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

5. <span data-ttu-id="25b33-116">請複習每份檔，然後選取 [讀取窗格] 底部的 [ **相關** ] 或 [ **不相關** ] 按鈕，以進行標籤。</span><span class="sxs-lookup"><span data-stu-id="25b33-116">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![將每個檔標示為相關或不相關](..\media\TrainModel1.png)

6. <span data-ttu-id="25b33-118">在您標示所有50專案之後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="25b33-118">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="25b33-119">系統會花幾分鐘的時間，讓系統從您的標記 "瞭解" 並更新模型。</span><span class="sxs-lookup"><span data-stu-id="25b33-119">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="25b33-120">完成此程式之後，就會在 **預測編碼模型 (預覽)** ] 頁面上顯示模型的狀態 [**就緒**]。</span><span class="sxs-lookup"><span data-stu-id="25b33-120">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

## <a name="perform-additional-training-rounds"></a><span data-ttu-id="25b33-121">執行其他訓練舍入</span><span class="sxs-lookup"><span data-stu-id="25b33-121">Perform additional training rounds</span></span>

<span data-ttu-id="25b33-122">在您執行第一輪訓練後，您可以遵循上一節中的步驟來執行後續訓練。</span><span class="sxs-lookup"><span data-stu-id="25b33-122">After you perform the first round of training, you can perform subsequent training rounds by following the steps in the previous section.</span></span> <span data-ttu-id="25b33-123">唯一的區別是會在 [模型 **一覽** ] 索引標籤上更新訓練的數目。例如，在執行第一個訓練輪後，您可以按一下 **[開始下一個訓練] 迴圈** 開始第二輪訓練。</span><span class="sxs-lookup"><span data-stu-id="25b33-123">The only difference is the number of the training round will be updated on the model **Overview** tab. For example, after performing the first training round, you can click **Start next training round** to start the second round of training.</span></span> <span data-ttu-id="25b33-124">等等。</span><span class="sxs-lookup"><span data-stu-id="25b33-124">And so on.</span></span>

<span data-ttu-id="25b33-125">每一輪訓練都會在模型的 [ **訓練** ] 索引標籤上，顯示所進行的 (和完成) 。</span><span class="sxs-lookup"><span data-stu-id="25b33-125">Each round of training (both those in progress and those that are complete) is displayed on the **Training** tab for the model.</span></span> <span data-ttu-id="25b33-126">當您選取訓練圓形時，會顯示含有該圓形資訊和度量指標的飛入頁面。</span><span class="sxs-lookup"><span data-stu-id="25b33-126">When you select a training round, a flyout page with information and metrics for the round is displayed.</span></span>

## <a name="what-happens-after-you-perform-a-training-round"></a><span data-ttu-id="25b33-127">執行訓練輪後會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="25b33-127">What happens after you perform a training round</span></span>

<span data-ttu-id="25b33-128">在您執行第一筆訓練後，就會開始執行下列作業的工作：</span><span class="sxs-lookup"><span data-stu-id="25b33-128">After you perform the first training round, a job is started that does the following things:</span></span>

- <span data-ttu-id="25b33-129">根據您標示訓練集中的40專案的方式，模型會從您的標記開始，並自行更新，以變得更準確。</span><span class="sxs-lookup"><span data-stu-id="25b33-129">Based on how you labeled the 40 items in the training set, the model learns from your labeling and updates itself to become more accurate.</span></span>

- <span data-ttu-id="25b33-130">然後，模型會處理整個審閱集中的每個專案，並指定介於 **0** (不相關的預測分數) 與 **1** (相關) 。</span><span class="sxs-lookup"><span data-stu-id="25b33-130">The model then processes each item in the entire review set and assigns a prediction score between **0** (not relevant) and **1** (relevant).</span></span>  

- <span data-ttu-id="25b33-131">模型將預測分數指派給您在訓練迴圈期間標示的控制項集中的10個專案。</span><span class="sxs-lookup"><span data-stu-id="25b33-131">The model assigns a prediction score to the 10 items in the control set that you labeled during the training round.</span></span> <span data-ttu-id="25b33-132">模型會將這10個專案的預測分數與您在訓練迴圈期間指派給專案的實際標籤進行比較。</span><span class="sxs-lookup"><span data-stu-id="25b33-132">The model compares the prediction score of these 10 items with the actual label that you assigned to the item during the training round.</span></span> <span data-ttu-id="25b33-133">根據此比較，模型會識別下列分類 (稱為「 *控制項集混淆」清單*) 以評估模型的預測效能：</span><span class="sxs-lookup"><span data-stu-id="25b33-133">Based on this comparison, the model identifies the following classification (called the *Control set confusion matrix*) to assess the model's prediction performance:</span></span>
  
  |          |<span data-ttu-id="25b33-134">模型預測專案是相關的</span><span class="sxs-lookup"><span data-stu-id="25b33-134">Model predicts item is relevant</span></span> |<span data-ttu-id="25b33-135">模型預測專案與專案不相關</span><span class="sxs-lookup"><span data-stu-id="25b33-135">Model predicts item is not relevant</span></span> |
  |:---------|:---------|:---------|
  |<span data-ttu-id="25b33-136">**檢閱者標籤專案為相關**</span><span class="sxs-lookup"><span data-stu-id="25b33-136">**Reviewer labels item as relevant**</span></span>| <span data-ttu-id="25b33-137">True 正值</span><span class="sxs-lookup"><span data-stu-id="25b33-137">True positive</span></span>| <span data-ttu-id="25b33-138">誤判</span><span class="sxs-lookup"><span data-stu-id="25b33-138">False positive</span></span> |
  |<span data-ttu-id="25b33-139">**[校對] 標籤專案不相關**</span><span class="sxs-lookup"><span data-stu-id="25b33-139">**Reviewer labels item as not relevant**</span></span>| <span data-ttu-id="25b33-140">False 負數</span><span class="sxs-lookup"><span data-stu-id="25b33-140">False negative</span></span> |<span data-ttu-id="25b33-141">True 負值</span><span class="sxs-lookup"><span data-stu-id="25b33-141">True negative</span></span> |
  ||||

  <span data-ttu-id="25b33-142">根據這些比較，模型會針對每個值的 F 分數、精確度及召回度量值和誤差邊界衍生值。</span><span class="sxs-lookup"><span data-stu-id="25b33-142">Based on these comparisons, the model derives values for the F-score, precision, and recall metrics and the margin of error for each one.</span></span> <span data-ttu-id="25b33-143">這些模型效能值的分數會顯示在訓練圓形的飛入頁面上。</span><span class="sxs-lookup"><span data-stu-id="25b33-143">Scores for these model performance metrics are displayed on a flyout page for the training round.</span></span> <span data-ttu-id="25b33-144">如需這些計量的描述，請參閱 [預測編碼參考](predictive-coding-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="25b33-144">For a description of these metrics, see [Predictive coding reference](predictive-coding-reference.md).</span></span>

- <span data-ttu-id="25b33-145">最後，模型會決定下一個訓練圓形將使用的後續50專案。</span><span class="sxs-lookup"><span data-stu-id="25b33-145">Finally, the model determines the next 50 items that will be used for the next training round.</span></span> <span data-ttu-id="25b33-146">這段時間，模型可能會從控制項集選取20個專案，並將其指定為下一個圓形的訓練集。</span><span class="sxs-lookup"><span data-stu-id="25b33-146">This time, the model might select 20 items from the control set and 30 new items from the review set and designate them as the training set for the next round.</span></span> <span data-ttu-id="25b33-147">下一個訓練迴圈的採樣並未進行均勻抽樣。</span><span class="sxs-lookup"><span data-stu-id="25b33-147">The sampling for the next training round is not uniformly sampled.</span></span> <span data-ttu-id="25b33-148">模型會將專案的抽樣選取範圍優化為選取專案，其中預測是不明確的，也就是說預測分數是在0.5 範圍內。</span><span class="sxs-lookup"><span data-stu-id="25b33-148">The model will optimize the sampling selection of items from the review set to select items where the prediction is ambiguous, which means the prediction score is in the 0.5 range.</span></span> <span data-ttu-id="25b33-149">此程式稱為偏迭的 *選取範圍*。</span><span class="sxs-lookup"><span data-stu-id="25b33-149">This process is known as *biased selection*.</span></span>

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a><span data-ttu-id="25b33-150">在您執行後續訓練輪後，會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="25b33-150">What happens after you perform subsequent training rounds</span></span>

<span data-ttu-id="25b33-151">在您執行後續訓練) 之後 (第一個訓練舍入之後，模型會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="25b33-151">After you perform subsequent training rounds (after the first training round), the model does the following things:</span></span>

- <span data-ttu-id="25b33-152">模型的更新取決於您套用到該圓形訓練集中之訓練集的標籤。</span><span class="sxs-lookup"><span data-stu-id="25b33-152">The model is updated based on the labels that you applied to the training set in that round of training.</span></span>

- <span data-ttu-id="25b33-153">系統會評估控制項集內專案的模型預測分數，並檢查分數是否與您在控制項集中標示專案的方式相符。</span><span class="sxs-lookup"><span data-stu-id="25b33-153">The system evaluates the model's prediction score on the items in the control set and check whether the score aligns with how you labeled items in the control set.</span></span> <span data-ttu-id="25b33-154">評估是針對所有訓練舍入從控制項集的所有已標示專案執行。</span><span class="sxs-lookup"><span data-stu-id="25b33-154">The evaluation is performed on all labeled items from control set for all training rounds.</span></span> <span data-ttu-id="25b33-155">這項評估的結果會合並到模型 [ **一覽表** ] 索引標籤上的儀表板中。</span><span class="sxs-lookup"><span data-stu-id="25b33-155">The results of this evaluation are incorporated in the dashboard on the **Overview** tab for the model.</span></span>

- <span data-ttu-id="25b33-156">更新的模型會 reprocesses 每個專案的複查集，並將更新的預測分數指派給每個專案。</span><span class="sxs-lookup"><span data-stu-id="25b33-156">The updated model reprocesses every item in the review set and assign each item an updated prediction score.</span></span>

## <a name="next-steps"></a><span data-ttu-id="25b33-157">後續步驟</span><span class="sxs-lookup"><span data-stu-id="25b33-157">Next steps</span></span>

<span data-ttu-id="25b33-158">在您執行第一個訓練迴圈後，您可以執行更多訓練，或將模型的預測分數篩選器套用至評審集，以查看模型預測的相關或不相關的專案。</span><span class="sxs-lookup"><span data-stu-id="25b33-158">After you perform the first training round, you can perform more training rounds or apply the model's prediction score filter to the review set to view the items the model has predicted as relevant or not relevant.</span></span> <span data-ttu-id="25b33-159">如需詳細資訊，請參閱套用 [預測分數篩選器到審閱集](predictive-coding-apply-prediction-filter.md)。</span><span class="sxs-lookup"><span data-stu-id="25b33-159">For more information, see [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>
