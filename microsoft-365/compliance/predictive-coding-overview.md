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
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>適用于高級 eDiscovery (預覽的預測編碼模組) 

在高級 eDiscovery 中使用新的預測編碼模組，您可以建立及建立模型，以從最相關的檔開始查看檔的優先順序。 若要開始使用，您可以建立模型、標籤為50檔，然後依模型預測分數篩選檔，以複查相關的非相關檔。

以下是工作流程的快速綜述：

1. 在複查集中開啟預測編碼模組。

   ![按一下 [檢查] 中的 [分析] 下拉式清單，以移至預測編碼模組](..\media\PredictiveCoding1.png)

2. 在 [ **預測編碼模型** ] 頁面上，按一下 [ **新增模型** ] 以建立新的預測編碼模型。

   ![建立新的模型](..\media\PredictiveCoding2.png)

3. 標籤至少為 **相關** 或 **不相關** 的50檔。 這種標記是用來訓練系統。

   ![將檔標示為相關或不相關的訓練系統](..\media\PredictiveCoding3.png)

4. 將模型的 **預測分數** 篩選器套用至評審集。 若要執行這項作業：

   1. 在 [審閱集合] 中，按一下 [ **篩選**]。
   2. 在 [ **篩選器** 飛入] 頁面中，展開 [ **分析/ML** ] 區段，然後選取您要套用之模型的 [ **預測分數** ] 核取方塊。
   3. 在 [ **預測分數** ] 篩選中，指定預測分數。 篩選會顯示符合預測分數的審閱集合中的檔。

      ![指定篩選檔的預測分數](..\media\PredictiveCoding4.png)

5. 監視模型的效能、狀態及穩定性。

   ![監視模型的效能、狀態和穩定性](..\media\PredictiveCoding5.png)
