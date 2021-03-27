---
title: '適用于高級 eDiscovery (預覽的預測編碼模組) '
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
description: 「高級 eDiscovery」中的新的預測編碼模組會利用機器學習來分析檔，以供您案例或調查相關的檔的審閱集合中的預測。
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382958"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="8efbc-103">適用于高級 eDiscovery (預覽的預測編碼模組) </span><span class="sxs-lookup"><span data-stu-id="8efbc-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="8efbc-104">在高級 eDiscovery 中使用新的預測編碼模組，您可以建立及建立模型，以從最相關的檔開始查看檔的優先順序。</span><span class="sxs-lookup"><span data-stu-id="8efbc-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="8efbc-105">若要開始使用，您可以建立模型、標籤為50檔，然後依模型預測分數篩選檔，以複查相關的非相關檔。</span><span class="sxs-lookup"><span data-stu-id="8efbc-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="8efbc-106">以下是工作流程的快速綜述：</span><span class="sxs-lookup"><span data-stu-id="8efbc-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="8efbc-107">在複查集中開啟預測編碼模組。</span><span class="sxs-lookup"><span data-stu-id="8efbc-107">Open the predictive coding module in a review set.</span></span>

   ![按一下 [檢查] 中的 [分析] 下拉式清單，以移至預測編碼模組](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="8efbc-109">在 [ **預測編碼模型** ] 頁面上，按一下 [ **新增模型** ] 以建立新的預測編碼模型。</span><span class="sxs-lookup"><span data-stu-id="8efbc-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![建立新的模型](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="8efbc-111">標籤至少為 **相關** 或 **不相關** 的50檔。</span><span class="sxs-lookup"><span data-stu-id="8efbc-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="8efbc-112">這種標記是用來訓練系統。</span><span class="sxs-lookup"><span data-stu-id="8efbc-112">This labeling is used to train the system.</span></span>

   ![將檔標示為相關或不相關的訓練系統](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="8efbc-114">將模型的 **預測分數** 篩選器套用至評審集。</span><span class="sxs-lookup"><span data-stu-id="8efbc-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="8efbc-115">若要執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="8efbc-115">To do this:</span></span>

   1. <span data-ttu-id="8efbc-116">在 [審閱集合] 中，按一下 [ **篩選**]。</span><span class="sxs-lookup"><span data-stu-id="8efbc-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="8efbc-117">在 [ **篩選器** 飛入] 頁面中，展開 [ **分析/ML** ] 區段，然後選取您要套用之模型的 [ **預測分數** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8efbc-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="8efbc-118">在 [ **預測分數** ] 篩選中，指定預測分數。</span><span class="sxs-lookup"><span data-stu-id="8efbc-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="8efbc-119">篩選會顯示符合預測分數的審閱集合中的檔。</span><span class="sxs-lookup"><span data-stu-id="8efbc-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![指定篩選檔的預測分數](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="8efbc-121">監視模型的效能、狀態及穩定性。</span><span class="sxs-lookup"><span data-stu-id="8efbc-121">Monitor the performance, status, and stability of your model.</span></span>

   ![監視模型的效能、狀態和穩定性](..\media\PredictiveCoding5.png)
