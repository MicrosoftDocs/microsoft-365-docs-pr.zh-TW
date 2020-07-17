---
title: 在高級 eDiscovery 中測試相關性分析
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 瞭解如何使用 [測試] 索引標籤，在 [高級 eDiscovery] 中成批計算後，測試、比較和驗證整體的處理品質。
ms.openlocfilehash: c5a885b3483b9ce319fffefa55037c0c2c8f3c85
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936206"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery-classic"></a>在高級 eDiscovery （經典）中測試相關性分析

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
Advanced eDiscovery 中的 [測試] 索引標籤可讓您測試、比較及驗證整體的處理品質。 這些測試會在批次計算之後執行。 將檔案標記在集合中，專家便可以判斷每個已標記的檔案是否實際上與案例有關。 
  
在單一和多個問題案例中，測試一般會在每個問題中執行。 您可以在每次測試後查看結果，並使用指定的範例測試檔來改編測試結果。
  
## <a name="testing-the-rest"></a>測試其他

「測試 Rest」測試是用來驗證剔除決策，例如，根據最終的高級 eDiscovery 結果，只複查高於特定相關性截止分數的檔案。 專家會檢查所選截止分數底下的檔案範例，以評估該集合內相關檔案的數量。
  
這種測試會提供統計資料，以及複查集與測試 Rest 人口之間的比較。 考核集的結果是在訓練期間依相關性計算的結果。 結果包括根據設定和輸入參數的計算，例如：
  
- 測試範例中檔案數目及識別相關檔案的範例統計資料。 
    
- 檢查集合的人口參數和其餘部分的表格比較，例如檔案數目、相關檔案的預估數目、預估豐富程度，以及尋找其他相關檔案的平均成本。 成本參數設定可由系統管理員設定。
    
1. 開啟 [**相關性 \> 測試**] 索引標籤。 
    
2. 在 [**測試**] 索引標籤中，按一下 [**新增測試**]。 隨即會顯示 [**建立測試**] 對話方塊，如下列範例所示。 
    
    ![相關性測試的其他結果](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. 在 [**測試名稱**] 和 [**描述**] 中，輸入名稱和描述。
    
4. 在 [**測試類型**] 清單中，選取 **[測試其餘**專案]
    
5. 在 [**問題/類別**] 清單中，選取問題名稱。 
    
6. 在 [**載入**] 清單中，選取負載。 
    
7. 在 [**讀取%**] 中，接受預設值，或選取截止的相關性分數值。 
    
8. 在 [**設定大小**] 或 [接受預設值]。 請注意，還原圖示會還原預設值。
    
9. 按一下 [**開始標記**]。 會產生測試範例。
    
10. 檢查及標記 [相關性標籤] 索引**卷 \> **標中的每個檔案，完成後，按一下 [**計算**]。
    
11. 在 [測試] 索引標籤中，您可以按一下 [**查看結果**] 以查看測試結果。 下圖顯示一個範例。 
    
    ![測試其他結果](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
在上圖中，表格的**範例參數**區段包含專家標記的範例中的檔案數目詳細資料，以及該範例中找到的相關檔案數目。 
  
表格的「**人口參數**」區段包含測試結果，包括檔的審閱集人口，其分數低於選取的截止點，以及 "Rest" 檔的檔與選取的截止點之上的分數。 針對每個人口，會顯示下列結果： 
  
- 包含已讀取的%-規定截止點
    
- 檔總數 
    
- 相關檔案的預估數目 
    
- 預估豐富 
    
- 尋找另一個相關檔案的平均檢查成本
    
## <a name="testing-the-slice"></a>測試切片

「測試分割區」測試會執行類似于「測試 Rest」測試的測試，但是對檔集（依相關性讀取% 所指定）進行測試。
  
1. 開啟 [**相關性 \> 測試**] 索引標籤。 
    
2. 在 [**測試**] 索引標籤中，按一下 [**新增測試**]。 隨即會顯示 [**建立測試**] 對話方塊。 
    
3. 在 [**測試名稱**和**描述**] 中，輸入資訊。
    
4. 在 [**測試類型**] 清單中，選取 **[測試切片**]。
    
5. 在 [**問題**] 清單中，選取問題名稱。 
    
6. 在 [**載入**] 清單中，選取負載。 
    
7. 在 [**介於**] 中，接受預設的 [低] 和 [高] 範圍值，或選取 [截止相關性分數] 的值。 
    
8. 在 [**設定大小**] 中，選取值或接受預設值。
    
    還原圖示會還原預設值。
    
9. 按一下 [**開始標記**]。 會產生測試範例。
    
10. 檢查及標記 [相關性標籤] 索引**卷 \> **標中的每個檔案，完成後，按一下 [**計算**]。 
    
11. 在 [測試] 索引標籤中，您可以按一下 [**查看結果**] 以查看測試結果。 
    
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[瞭解相關評估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記與評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[標記與相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[根據結果決定](decision-based-on-the-results-in-advanced-ediscovery.md)

