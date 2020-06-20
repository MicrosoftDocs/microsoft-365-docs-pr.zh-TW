---
title: 根據高級 eDiscovery 的結果決定
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: '瞭解 Microsoft 365 Advanced eDiscovery 中的 [決定] 索引標籤可如何提供資料，以協助您決定正確的查看案例檔案集大小。 '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0139bc0505150a4d27aaca97b9b253f2043d649f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817902"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a>以 Advanced eDiscovery （古典）結果為基礎的決策

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 在 [Advanced eDiscovery] 中，[判斷] 索引標籤提供其他資訊，供您用來判斷查看案例檔案集大小的決策支援統計資料。 
  
## <a name="using-the-decide-tab"></a>使用 [決定] 索引標籤

![決定相關性](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
此索引標籤包含下列專案：
  
- **問題**：在這裡，您可以從清單中選取感興趣的問題。 
    
- **回顧-召回比率**：根據相關性分數，進行高級 eDiscovery 檢查的比較。 圖表中的截止點代表要檢查的檔百分比，對應至相關性分數。 這是用於相關性測試階段和用於剔除的匯出臨界值。 若要檢查的檔案數目是預設的截止點，表示重新開始和精確度之間的平衡是最佳的。 實際的截止點應該取決於目標及成本折衷（% 回顧）和風險（% 召回）等使用者。使用此滑塊，您可以調整截止點，並查看圖表和參數的效果，調整要檢索的相關檔案的百分比，以及驗證決策之前。
    
- **參數**：檢查、召回、接下來的相關及總成本參數是與評審集相對於整個案例集合相關的累計計算統計資料。 這些參數的定義如下：
    
    **檢查**：根據此截止點所要複查的檔案百分比。 
    
    **召回**：審閱集內相關檔案的百分比。 
    
    **下一項相關**：檢查和找出目前不在審閱集中的相關檔案的成本。 
    
    **總成本**：用於審閱此案例檔案百分比的成本。 Cost 參數設定可由 Case 管理員設定。
    
- **依相關性分數發佈**：深色灰度顯示幕中的檔案低於截止分數。 工具提示會顯示與檔總數相關的審閱檔案集中的相關性分數和相關百分比。
    
展開的詳細資料窗格會顯示其他詳細資料。 集合中的檔案不包括空白或 nebulous 檔案。 「家族檔案」是指未載入相關性的檔案，但仍會計入為該系列的一部分。
  
## <a name="related-topics"></a>相關主題

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[瞭解相關評估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記與評估](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[執行相關性訓練](tagging-and-assessment-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

