---
title: 在 Advanced eDiscovery 中建立預測編碼模型
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
description: 瞭解如何在 Advanced eDiscovery 中建立預測編碼模型。 這是在 Advanced eDiscovery 中使用電腦學習功能的第一步，可協助您識別出評審集中的相關和非相關內容。
ms.openlocfilehash: 7724062848d8d757fbfd3a7870853d6f2c409d84
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822515"
---
# <a name="create-a-predictive-coding-model-preview"></a>建立預測編碼模型 (預覽) 

在 Advanced eDiscovery 中使用「預測編碼的機器學習功能的第一步是建立預測編碼模型。 在您建立模型之後，您可以訓練此模型，識別考核集中的相關和非相關內容。

若要查看預測編碼工作流程，請參閱[瞭解 Advanced eDiscovery 中的預測編碼](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>建立模型之前

- 若要建立預測編碼模型，檢查集合中必須至少要有2000個專案。

- 在建立模型之前，請務必先將所有集合都認可至審閱集。 建立模型之後，將不會處理新增至考核集的專案，而且會將其指派給模型所產生的預測分數。

- 不含文字的複查集中的任何專案，將不會由模型處理，也不會被指定為預測分數。 具有文字的專案將會包含在控制項集或訓練集內。

## <a name="create-a-model"></a>建立模型

1. 在 Microsoft 365 規範中心] 中，開啟 Advanced eDiscovery 案例，然後選取 [**複查集**] 索引標籤。

2. 開啟一個複查集，然後按一下 [**分析**  >  **管理預測編碼 (預覽])**。

   ![按一下 [檢查集合] 中的 [分析] 下拉式功能表，以移至 [預測編碼] 頁面](..\media\ManagePredictiveCoding.png)

3. 在 [ **預測編碼模型] (預覽)** ] 頁面上，按一下 [ **新增模型**]。

4. 在 [飛入] 頁面上，輸入模型的名稱和選用的描述。

5. 或者，您可以按一下彈出頁面上的 [ **高級選項** ]，以設定 [高級設定 (]) 與「置信層級」與「錯誤」邊界相關。 這些設定會影響控制項集中包含的專案數。 在訓練程式期間使用該 *控制項集* ，評估模型會指派給具有您在訓練過程中所執行之標籤之專案的預測分數。 如果您的組織具有對檔審閱之信賴等級和誤差邊界的指導方針，請在適當的方塊中加以指定。 否則，請使用預設設定。

6. 按一下 [ **儲存** ] 以建立模型。

   系統會花幾分鐘的時間來準備您的模型。 準備好後，您就可以執行第一輪訓練。

## <a name="what-happens-after-you-create-a-model"></a>建立模型後會發生什麼事

在您建立模型之後，在建立及準備模型時，會在背景中發生下列情況：

- 系統會計算控制項集的專案數。 這個大小是以考核集中的專案數和信賴層級的設定以及錯誤的邊界來定。 會隨機選取控制項集的專案，並指定為控制項集專案。 系統會在第一輪訓練中的控制項集中包含10個專案。

- 系統會從考核集內隨機選取40專案，以包含在第一輪訓練的訓練集內。 因此，第一輪訓練包括50個專案的標籤40：每個訓練集的專案和控制項集中的10個專案。

## <a name="next-steps"></a>後續步驟

在您建立複查集的模型之後，下一步是執行訓練以「講授」模型，以識別與調查相關的內容。 如需詳細資訊，請參閱 [訓練預測編碼模型](predictive-coding-train-model.md)。
