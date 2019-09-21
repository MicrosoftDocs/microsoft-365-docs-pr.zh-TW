---
title: Office 365 進階電子文件探索中的結果為基礎的決策
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: '了解如何在 Office 365 進階電子文件探索中的決定] 索引標籤提供資料，可協助您決定正確的檢閱一組案例檔案大小。 '
ms.openlocfilehash: 3f8ce0343b5a09cf3ab4c4bd94a53d8d0cbe0cce
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076385"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>Office 365 進階電子文件探索中的結果為基礎的決策

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
 在進階電子文件，決定] 索引標籤，提供檢視和使用來決定檢閱一組案例檔案的大小決策支援統計資料的其他資訊。 
  
## <a name="using-the-decide-tab"></a>使用 [決定] 索引標籤

![決定相關性](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
此索引標籤包含下列特性：
  
- **此問題**： 從這裡開始，您可以選取從清單感興趣的問題。 
    
- **檢閱重新叫用比率**： 根據相關性分數比較的進階電子文件探索檢閱。 截止點在圖表中的代表對應至相關性分數若要檢閱，檔案的百分比。 這用於在相關性測試階段，然後為匯出閾值挑選。 重新叫用與精確度之間取得平衡是最佳的作法點位於預設截止點，若要檢閱的檔案數目。 實際的截止點應根據目標和成本取捨 （%檢閱） 和風險 （%重新叫用） 之使用者所決定。使用滑桿，您可以調整截止點，並調整相關的檔案，以擷取，並驗證決策之前先 %時，請參閱圖和參數，影響。
    
- **參數**： 檢閱，請記得下, 一步相關以及總成本參數都是屬於整個案例集合的 relation 中設定檢閱累計計算統計資料。 這些參數的定義如下所示：
    
    **檢閱**： 若要檢閱的檔案百分比根據此截止。 
    
    **回想一下**： 檢閱集中相關檔案的百分比。 
    
    **下一步與相關**： 若要檢閱並識別目前尚未檢閱中設定的其他相關檔案的成本。 
    
    **總成本**： 成本檢閱此百分比的大小寫的檔案。 成本的參數設定可以設定的大小寫的管理員。
    
- **由相關性分數的通訊群組**： 檔案在暗灰色向左顯示如下的截止分數。 工具提示顯示的相關性分數，以及相關的檔案百分比檢閱檔案中設定關聯的總檔案中。
    
展開 [詳細資料] 窗格會顯示其他詳細資料。 集合圖表目錄中的檔案不包括空白或不是很明確的檔案。 家庭檔案數字代表不載入相關性，但仍會計算在內系列的一部分的檔案。
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解相關性評估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記與評估](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[執行相關性訓練](tagging-and-assessment-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

