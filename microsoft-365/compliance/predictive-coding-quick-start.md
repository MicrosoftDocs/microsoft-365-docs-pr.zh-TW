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
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>快速入門： Advanced eDiscovery (預覽中的預測編碼) 

本文提供在 Advanced eDiscovery 中使用預測性編碼的快速入門。 Advanced eDiscovery 中的預測編碼模組使用 Advanced eDiscovery 中的智慧機學習功能，協助您減少要查看的內容數量。 預測編碼可協助您將大量案例內容縮小及挑選為一組可供查看的相關專案。 這是透過建立及訓練您自己的預測編碼模型，協助您在評審集中查看最相關專案的優先順序。

以下是預測編碼程式的快速綜述：

![預測編碼的快速啟動程式](..\media\PredictiveCodingQuickStartProcess.png)

若要開始使用，您可以建立模型，並將其標籤為相關或不相關的50專案。 然後系統會使用這項訓練，將預測分數套用至評審集合中的每個專案。 這可讓您根據預測分數來篩選項目，這可讓您先查看最相關的 (或非相關的) 專案。 如果您想要使用較高的精度和重新叫付率訓練模型，您可以在後續訓練中繼續標示專案，直到模型穩定為止。 一旦模型穩定，您可以套用最後的預測篩選，以優先處理要查看的專案。

如需預測編碼的詳細資訊，請參閱[瞭解 Advanced eDiscovery 中的預測編碼](predictive-coding-overview.md)。

## <a name="step-1-create-a-new-predictive-coding-model"></a>步驟1：建立新的預測編碼模型

第一步是在審查集內建立新的預測編碼模型。

1. 在 Microsoft 365 規範中心] 中，開啟 Advanced eDiscovery 案例，然後選取 [**複查集**] 索引標籤。

2. 開啟一個複查集，然後按一下 [**分析**  >  **管理預測編碼 (預覽])**。

   ![按一下 [檢查集合] 中的 [分析] 下拉式功能表，以移至 [預測編碼] 頁面](..\media\ManagePredictiveCoding.png)

3. 在 [ **預測編碼模型] (預覽)** ] 頁面上，按一下 [ **新增模型**]。

4. 在 [飛入] 頁面上，輸入模型的名稱和選用的描述。

5. 按一下 [ **儲存** ] 以建立模型。

   系統會花幾分鐘的時間來準備您的模型。 準備好後，您就可以執行第一輪訓練。

如需詳細指示，請參閱 [建立預測編碼模型](predictive-coding-create-model.md)。

## <a name="step-2-perform-the-first-training-round"></a>步驟2：執行第一輪訓練

在您建立模型之後，下一步是將專案標記為相關或不相關，以完成第一個訓練舍入。

1. 開啟審閱集，然後按一下 [**分析**  >  **管理預測編碼 (預覽])**。

2. 在 [ **預測編碼模型] (預覽)** ] 頁面上，選取您要訓練的模型。

3. 在 [ **一覽** ] 索引標籤的 [ **圓形 1**] 底下，按一下 **[開始下一個訓練圓形**]。

   [ **訓練** ] 索引標籤隨即顯示，並包含50個專案供您用標籤。

4. 請複習每份檔，然後選取 [讀取窗格] 底部的 [ **相關** ] 或 [ **不相關** ] 按鈕，以進行標籤。

   ![將每個檔標示為相關或不相關](..\media\TrainModel1.png)

5. 在您標示所有50專案之後，請按一下 **[完成]**。

    系統會花幾分鐘的時間，讓系統從您的標記 "瞭解" 並更新模型。 完成此程式之後，就會在 **預測編碼模型 (預覽)** ] 頁面上顯示模型的狀態 [**就緒**]。

如需詳細指示，請參閱 [訓練預測編碼模型](predictive-coding-train-model.md)。

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>步驟3：對評審集中的專案套用預測分數篩選器

在您執行租用一次訓練時，您可以將預測分數篩選器套用至考核組中的專案。 這可讓您查看模型預測的專案（相關或不相關）。   

1. 開啟審閱集。

   ![按一下篩選以顯示篩選器飛出頁面](..\media\PredictionScoreFilter0.png)

   預先載入的預設篩選器會顯示在 [審閱集合] 頁面的頂端。 您可以將這些設定保留為 **任何**。

2. 按一下 [ **篩選** ] 以顯示 [ **篩選** ] 飛出頁面。

3. 展開 [ **分析 & 預測編碼** ] 區段，以顯示一組篩選器。

      ![分析 & 預測編碼區段中的預測分數篩選](..\media\PredictionScoreFilter1.png)

   「預測計分」篩選的命名慣例是「 **預測分數 (模型名稱)**。 例如，名為 **Model a** 模型的預測分數篩選名稱是 **預測分數 (模型 a)**。

4. 選取您要使用的預測分數篩選，然後按一下 [ **完成**]。

5. 在 [檢查集合] 頁面上，按一下 [預測分數] 篩選器的下拉式清單，並輸入預測分數範圍的最小值和最大值。 例如，下列螢幕擷取畫面顯示介於 **0.5** 到 **1.0** 之間的預測分數範圍。

   ![預測分數篩選的最小值和最大值](..\media\PredictionScoreFilter2.png)

6. 按一下篩選外部，以自動將篩選套用至審閱集。

  在您指定範圍內的預測分數的檔案清單會顯示在 [審閱集合] 頁面上。

如需詳細指示，請參閱 [Apply a 聯想 filter to a 審校 set](predictive-coding-apply-prediction-filter.md)。

## <a name="step-4-perform-more-training-rounds"></a>步驟4：執行更多訓練舍入

您可能需要執行更多訓練，以訓練模組，以更好地預測評審集中的相關和非相關專案。 一般來講，您會訓練模型足夠的時間，直到達到滿足您需求的足夠穩定為止。

如需詳細資訊，請參閱 [執行其他訓練舍入](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>步驟5：套用最後的預測分數篩選，以優先審閱

重複步驟3中的指示，將最後的預測分數套用至檢查集合，以在完成所有訓練並使模型穩定後，排定相關和非相關專案的複查優先順序。
