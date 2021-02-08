---
title: 文件瞭解模型使用情況分析
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 瞭解如何將保留標籤套用至文件瞭解模型
ms.openlocfilehash: 92115d8b1985fa84cd72671442aca18f255355de
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080414"
---
# <a name="document-understanding-model-usage-analytics"></a>文件瞭解模型使用情況分析

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


您的 Microsoft SharePoint Syntex 內容中心可提供有關您的模型使用情況分析，以便提供您更多有關從內容中心發佈之模型的使用情況詳細資訊。 內容中心的 <b>[模型在過去 30 天的表現]</b> 區段包括下列圖表與清單中提供的使用情況分析資料的 30日 彙總：

- 依模型分類
- 依文件庫分類
- 模型使用情況 

 ![模型分析](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a>預設內容中心的模型使用情況資料彙總

在 SharePoint Syntex 中，系統會在設定過程中建立預設內容中心。 您也可以視需要建立其他內容中心。 例如，部門可以建立自己的內容中心來建立和管理其模型。 

關於模型使用情況分析，請注意下列事項：

- 您的預設內容中心會顯示貴組織中所有內容中心和模型的模型使用情況分析，包括在其他內容中心建立的模型。 這為內容經理和其他專案關係人提供一個集中入口網站，以管理和監督組織內部的內容中心和模型。  
- 其他內容中心將只會顯示為其建立之模型的模型使用情況分析。 這可讓內容經理深入了解他們所關注之模型的使用資料。


## <a name="classification-by-model"></a>依模型分類

   ![總計模型百分比](../media/content-understanding/total-model-percentage.png) </br>

**依模型分類** 圓形圖顯示哪些模型已分類最多檔案。 此圓形圖會以每個已發佈模型佔總檔案數 (由內容中心上的所有已發佈模型所處理) 的形式顯示每個已發佈的模型。

每個模型也會顯示 **完整性比率**，即經該模型成功分析且已上傳檔案的百分比。 低完整性比率可能表示正在分析的模型或檔案有問題。

## <a name="classification-by-library"></a>依文件庫分類

   ![已處理的檔案](../media/content-understanding/files-processed-over-time.png) </br>

**依文件庫分類** 橫條圖可協助您判斷貴組織內容瞭解的有效性。  除了可顯示每個模型隨著時間所處理的檔案數目，以及圖表欄位選擇，也同時顯示已套用該模型的文件庫。


## <a name="model-usage"></a>模型使用情況

模型使用情況清單將顯示透過內容中心所建立之模型的使用情況分析。  

> [!NOTE]
> 如果您位於預設內容中心中，且組織中有其他內容中心，模型使用情況清單將會依內容中心分組。

模型使用情況清單中的每個模型都會顯示使用情況資料：

- 分類項目計數：由模型處理的檔案數目。
- 平均信賴度分數：執行檔案時的模型平均精確度分數。
- 靶心圖清單 URL：模型所套用的 SharePoint 文件庫。



## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)

[建立擷取器](create-an-extractor.md)

[文件瞭解概觀](document-understanding-overview.md)

[建立表單處理模型](create-a-form-processing-model.md)  
