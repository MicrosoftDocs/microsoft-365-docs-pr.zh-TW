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
ms.openlocfilehash: 84ec1ad42f2cec2487debe7160a3f24e09bdd830
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288188"
---
# <a name="train-a-predictive-coding-model-preview"></a>訓練 (預覽的預測編碼模型) 

在 Advanced eDiscovery 中建立預測編碼模型之後，下一步是執行第一個訓練，以訓練模型對您的審閱集中的相關和非相關內容的相關訓練。 在您完成第一輪訓練後，您可以執行後續訓練，以提升模型預測相關和非相關內容的能力。

若要查看預測編碼工作流程，請參閱[瞭解 Advanced eDiscovery 中的預測編碼](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>訓練模型之前

- 在訓練過程中，會根據檔內容的關聯性，將專案標籤設為 **相關** 或 **不相關** 。 請勿根據元資料欄位中的值進行決策。 例如，電子郵件訊息或 Teams 交談，請勿將您的標記決定于郵件參與者。

## <a name="train-a-model-for-the-first-time"></a>第一次訓練模型

1. 在 Microsoft 365 合規性中心中，開啟 Advanced eDiscovery 案例，然後選取 [**複查集**] 索引標籤。

2. 開啟一個複查集，然後按一下 [**分析**  >  **管理預測編碼 (預覽])**。

3. 在 [ **預測編碼模型] (預覽)** ] 頁面上，選取您要訓練的模型。

4. 在 [ **一覽** ] 索引標籤的 [ **圓形 1**] 底下，按一下 **[開始下一個訓練圓形**]。

   [ **訓練** ] 索引標籤隨即顯示，並包含50個專案供您用標籤。

5. 請複習每份檔，然後選取 [讀取窗格] 底部的 [ **相關** ] 或 [ **不相關** ] 按鈕，以進行標籤。

   ![將每個檔標示為相關或不相關](..\media\TrainModel1.png)

6. 在您標示所有50專案之後，請按一下 **[完成]**。

    系統會花幾分鐘的時間，讓系統從您的標記 "瞭解" 並更新模型。 完成此程式之後，就會在 **預測編碼模型 (預覽)** ] 頁面上顯示模型的狀態 [**就緒**]。

## <a name="perform-additional-training-rounds"></a>執行其他訓練舍入

在您執行第一輪訓練後，您可以遵循上一節中的步驟來執行後續訓練。 唯一的區別是會在 [模型 **一覽** ] 索引標籤上更新訓練的數目。例如，在執行第一個訓練輪後，您可以按一下 **[開始下一個訓練] 迴圈** 開始第二輪訓練。 等等。

每一輪訓練都會在模型的 [ **訓練** ] 索引標籤上，顯示所進行的 (和完成) 。 當您選取訓練圓形時，會顯示含有該圓形資訊和度量指標的飛入頁面。

## <a name="what-happens-after-you-perform-a-training-round"></a>執行訓練輪後會發生什麼事

在您執行第一筆訓練後，就會開始執行下列作業的工作：

- 根據您標示訓練集中的40專案的方式，模型會從您的標記開始，並自行更新，以變得更準確。

- 然後，模型會處理整個審閱集中的每個專案，並指定介於 **0** (不相關的預測分數) 與 **1** (相關) 。

- 模型將預測分數指派給您在訓練迴圈期間標示的控制項集中的10個專案。 模型會將這10個專案的預測分數與您在訓練迴圈期間指派給專案的實際標籤進行比較。 根據此比較，模型會識別下列分類 (稱為「 *控制項集混淆」清單*) 以評估模型的預測效能：

  <br>

  ****

  |標籤|模型預測專案是相關的|模型預測專案與專案不相關|
  |---|---|---|
  |**檢閱者標籤專案為相關**|True 正值|誤判|
  |**[校對] 標籤專案不相關**|False 負數|True 負值|
  |

  根據這些比較，模型會針對每個值的 F 分數、精確度及召回度量值和誤差邊界衍生值。 這些模型效能值的分數會顯示在訓練圓形的飛入頁面上。 如需這些計量的描述，請參閱 [預測編碼參考](predictive-coding-reference.md)。

- 最後，模型會決定下一個訓練圓形將使用的後續50專案。 這段時間，模型可能會從控制項集選取20個專案，並將其指定為下一個圓形的訓練集。 下一個訓練迴圈的採樣並未進行均勻抽樣。 模型會將專案的抽樣選取範圍優化為選取專案，其中預測是不明確的，也就是說預測分數是在0.5 範圍內。 此程式稱為偏迭的 *選取範圍*。

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>在您執行後續訓練輪後，會發生什麼事

在您執行後續訓練) 之後 (第一個訓練舍入之後，模型會執行下列動作：

- 模型的更新取決於您套用到該圓形訓練集中之訓練集的標籤。

- 系統會評估控制項集內專案的模型預測分數，並檢查分數是否與您在控制項集中標示專案的方式相符。 評估是針對所有訓練舍入從控制項集的所有已標示專案執行。 這項評估的結果會合並到模型 [ **一覽表** ] 索引標籤上的儀表板中。

- 更新的模型會 reprocesses 每個專案的複查集，並將更新的預測分數指派給每個專案。

## <a name="next-steps"></a>後續步驟

在您執行第一個訓練迴圈後，您可以執行更多訓練，或將模型的預測分數篩選器套用至評審集，以查看模型預測的相關或不相關的專案。 如需詳細資訊，請參閱套用 [預測分數篩選器到審閱集](predictive-coding-apply-prediction-filter.md)。
