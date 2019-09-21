---
title: 在 Office 365 進階電子文件探索中瞭解相關性評估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 取得評估階段和在 Office 365 進階電子文件探索中的相關性訓練期間判斷問題的豐富性其角色的概觀。
ms.openlocfilehash: 77d9449ad15fd3a53709f2a28a96b06ab54556eb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076688"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中瞭解相關性評估

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
進階電子文件啟用早期評估，例如，定義的問題及案例匯入的資料。 進階電子文件可讓專家制定決策相關採用方法，並將它們套用至文件檢閱專案。
  
## <a name="understanding-assessment"></a>了解評估

在評估、 專家會檢閱隨機的一組至少 500 檔案，這用來判定問題的豐富性並產生反映訓練結果的統計資料。 若要達到有助於進階電子文件提供準確的統計資料，以及有效地判斷穩定點訓練程序中的相關性統計層級找不到足夠相關檔案時，成功評估。 
  
較高的相關檔案數目集中評估，更精確的統計資料和穩定性演算法的有效性。 評估檔案中的相關檔案的數目，可根據的問題而定。 豐富性是預估的百分之集中相關問題的相關檔案。 較高的豐富性問題會更快速地問題達到更高版本相關的檔案數目，具有較低的豐富性。 非常低的豐富性的問題 (例如，2%或更少) 時，需要設定為達到相當數量的相關檔案非常大評估。
  
統計資料，而一文中所述追蹤及決定] 索引標籤的訓練期間和之後批次計算，包括數量的重新叫用不同檢閱組的估計值。 根據樣本的估算設定 （在此案例中，評估檔案） 中的統計資料，包括錯誤的邊界和該錯誤邊界的信賴等級。 例如，預估的重新叫用的 80%可能會有 95%的信賴等級錯誤再加上或減去 5%的邊界。 這表示估計重新叫用是實際 75%的 85%，而且此估計有 95%信賴。 越大評估組的錯誤限度變小，且更精確的統計資料。 
  
專家檢閱初始評估的一組 500 檔案之後，相關性是能夠判斷錯誤的重新叫用值的目前邊界。 相關性也會設定預設邊界為它到達最佳化評估組建議的錯誤。 以下是一些範例：
  
- 如果已設定的評估會產生錯誤，再加上或減去 10%的邊界，將會建議相關性移至訓練 （需要任何額外評定檢閱）。 
    
- 如果評估組產生的錯誤，再加上或減去 13%限度，相關性可能建議另一組評估檔案，以達到較小的邊界的檢閱。 
    
- 如果豐富性極低，相關性可能建議停止評估，即使的錯誤限度是大型 （進行統計資料並不實用），因為到達有用的錯誤限度所需的評估集太大。
    
每一項問題有它自己的豐富性、 目前邊界的錯誤，並如此一來，估計的其他評估的檔案數目。 下一步評估集建立根據 （最多 1000 個在一組) 檔案的數目上限。
  
您可以接受的相關性建議或調整目前的錯誤限度根據您的需求。 錯誤的目前的預設邊界決定等於或高於 75%的重新叫用。
  
> [!NOTE]
> 評估階段可以略過，在**相關性\>追蹤**中有問題，清除 [**評估**] 核取方塊每個問題，然後針對 「 所有問題 」 的擴充檢視] 索引標籤。 不過，因此，會有這個問題沒有統計資料。 清除 [**評估**] 核取方塊 > 只能執行評估之前執行。 在多個問題存在於案例中，核取方塊已清除的每一項問題時，才將略過評估 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[標記與評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[標記與相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[決定根據結果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

