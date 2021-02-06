---
title: 在高級 eDiscovery 中停用相關性模組
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
ms.collection: M365-security-compliance
description: 在2021年3月10日，「高級 eDiscovery」中的 [相關性] 模組會停用。 本文說明停用相關性之前所執行的動作。 尤其是，您可以執行批次計算來精加工任何未完成的模型，這樣您就可以保留模型中的中繼資料。
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122527"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>在高級 eDiscovery 中停用相關性模組

在2021年3月10日，我們即將在「高級 eDiscovery」中淘汰相關性模組。 這項淘汰表示組織將無法再存取相關性模組 (，方法是在高級 eDiscovery 案例中 **管理「複查」設定**  >  **相關性**) 或能夠存取任何現有的相關性模型。 即將停用的目前相關性模組會取代為第2季度2021的新預測編碼解決方案。 這項新功能可讓組織在更輕鬆且更為直觀的工作流程中建立自己的預測編碼模型。

若要準備即將進行的退休狀態，建議使用相關性模組的組織，針對所有現有模型執行批次計算，以匯出其模型輸出。 您的模型中的所有相關性分數會永久儲存在對應的審查集內，並可在匯出檔時加以存取。 相關性分數也會保留為載入檔案中的中繼資料。 此外，您仍然可以根據相關性分數篩選審查集中的內容，並存取相關性模型所產生的所有中繼資料。

## <a name="complete-unfinished-models"></a>完成未完成的模型

針對任何未完成的相關模型，請完成評估、訓練和批次計算，這樣您就可以將模型套用至審閱集中的檔。 完成批次計算會保留相關性模組的退休日期之後的資訊。

若要完成任何未完成的模型，請執行以下步驟：

1. 訓練模型，直到它穩定且準備好進行批次計算。 請參閱 [標記與相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)。

   下列螢幕擷取畫面顯示準備好進行批次計算的模組。 請注意，評估與訓練已完成，下一步是執行批次計算。

   ![可供批次計算用的模型螢幕擷取畫面](../media/ReadyForBatchCalculation.png)

2. 執行批次計算。 請參閱 [執行批次計算](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)。

3. 確認批次計算成功。 請參閱 [批次計算結果](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。

如需完成未完成相關模型的協助，請與 Microsoft 支援人員聯繫。
