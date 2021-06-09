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
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>將預測分數篩選套用至審閱集 (預覽) 

在 Advanced eDiscovery 中建立預測編碼模型，並將其訓練至穩定的點之後，您可以套用預測分數篩選，以顯示模型所決定的評審專案（相關） (或不相關) 。 當您建立模型時，也會建立對應的預測分數篩選。 您可以使用此篩選器，在指定的範圍內顯示指派了預測分數的專案。 一般說來，介於 **0** 和 **0.5** 之間的預測分數會指派給模型產生預測的專案。 在 **0.5** 和 **1.0** 之間指派預測分數的專案是指模型有預測性的專案。

以下是您可以使用預測分數篩選的兩種方式：

- 在評審集中，依模型預測的，檢查項目的檢查優先順序是否相關。

- 剔除模型所預測之複查集中的專案不相關。 或者，您可以使用「預測分數」篩選取消對非相關專案的審閱優先順序。

## <a name="before-you-apply-a-prediction-score-filter"></a>套用預測分數篩選之前

- 建立預測編碼模型，以建立對應的預測分數篩選。

- 您可以在任何訓練四捨五入之後套用預測計分篩選。 不過，您可能想要在執行數次舍入或模型穩定之前等待，以使用預測計分篩選。

## <a name="apply-a-prediction-score-filter"></a>套用預測分數篩選

1. 在 Microsoft 365 規範中心] 中，開啟 Advanced eDiscovery 案例，選取 [**複查集**] 索引標籤，然後開啟審閱集。

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

  > [!TIP]
  > 若要查看指派給檔的實際預測分數，您可以按一下 [讀取窗格] 中的 [ **中繼資料** ] 索引標籤。 在考核集中，所有模型的預測分數會顯示在 **RelevanceScores** 中繼資料屬性中。

## <a name="more-information"></a>詳細資訊

- 如需使用篩選的詳細資訊，請參閱 [查詢及篩選審閱集中的內容](review-set-search.md)。
