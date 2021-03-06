---
title: 瞭解 Advanced eDiscovery 中的相關評估
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 取得評估階段及其角色，以決定 Microsoft 365 Advanced eDiscovery 中的相關性訓練期間的豐富問題。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769274"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Advanced eDiscovery 中的「相關性」模組中的評估
  
Advanced eDiscovery 會啟用早期評估，例如，針對已定義的問題和針對案例匯入的資料。 Advanced eDiscovery 可讓專家決定所採用的方法，並將這些決策套用至檔審閱專案。
  
## <a name="understanding-assessment"></a>瞭解評估

在評估中，專家會檢查至少一組500檔案，用來判斷問題的豐富程度，並產生反映訓練結果的統計資料。 當找到足夠的相關檔案以達到統計層級，將有助於 Advanced eDiscovery 相關性以提供準確的統計資料，並有效地判斷訓練程式中的穩定化點，評估會順利完成。 
  
評估集內相關檔案的數量越高，其統計資料和穩定性演算法的效能就會越精確。 評估檔案中的相關檔案數目取決於問題的豐富程度。 豐富程度是與問題相關之集合中的相關檔案預估百分比。 大量豐富的相關檔案會比使用較低豐富的問題更快速地達到較高的相關檔案。 大量豐富的大量豐富 (問題例如，2% 或更少) 會需要非常大的評估，以達到大量相關檔案。
  
在訓練和批次計算之後的 [追蹤] 索引標籤中呈現的統計資料，包括針對不同的審查集估計的召回。 在 [統計資料] 中，根據範例 (集進行估計會在此案例中，評估檔) 會包含錯誤的邊界以及該誤差邊界的信賴等級。 例如，估計召回80% 時，可能會有超出95% 信賴等級的正負寬的誤差。 這表示預估的召回實際為 75%-85%，而這預估的估計為95%。 評估集越大，錯誤的邊界就會變小，而且統計資料也會更準確。 
  
在專家檢查500檔的初始評估集合之後，相關性可以判斷召回值的目前錯誤的邊界。 相關性也會建議要達到的預設誤差邊界，以優化評估集。 範例如下：
  
- 如果評估設定已經產生加減或減10% 的誤差，相關性將建議移至訓練 () 不需要其他評估評論。 

- 如果評估設定產生的誤差為加減或減13%，相關性可能會建議您複查另一組評估檔，以達到較小的邊界。 

- 如果豐富程度特別低，即使錯誤的邊界很大 (使統計資料變得不) 實用，也可能會導致停止評估，因為這是因為達到有用的錯誤邊界所需的評估設定太大。

每個問題都有自己的豐富程度、目前的錯誤邊界，以及結果、估計數目的額外評估檔。 下一個評估集是根據 1000 (一組) 中的最大檔案數目。
  
您可以接受相關性建議，或根據您的需求調整目前的錯誤邊界。 在等於或高於75% 的情況下，會判斷目前的錯誤目前邊界是否可重新叫用。
  
> [!NOTE]
> 您可以在問題展開的 [ **相關性 \> 追蹤** ] 索引標籤中，清除 [每個問題的 **評估** ] 核取方塊，然後針對「所有問題」，以略過評估階段。 因此，此問題不會有任何統計資料。 清除 [ **評估** ] 核取方塊只會在執行評估之前完成。 如果有多個問題存在於案例中，只有針對每個問題清除此核取方塊時，才會略過評估。
