---
title: 了解在 Office 365 進階電子文件探索中的文件相似性
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
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: '檢閱文件相似性值，最低的層級的兩個檔案被視為接近重複，跟在 Office 365 進階電子文件探索中的運作方式。 '
ms.openlocfilehash: 78e4ab7d39600522370cd91f3d6561ff2fbdcf60
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077456"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a>了解在 Office 365 進階電子文件探索中的文件相似性

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在進階電子文件，文件相似性是跟所需的兩個文件被視為接近重複的最低層級。
  
> [!TIP]
> 對於大多數的商務應用程式，建議使用相似性值的 60%的 75%。 非常不佳的品質光學字元辨識 (OCR) 材料，可以套用較低的相似性值。 
  
> [!NOTE]
> 已設定，並針對特定情況下執行之後，就無法變更相似性值。 
  
Near-複本 (ND) 在集內，可能會有的跟低於相似性閾值等級的文件。 加入 ND 組，文件中必須有至少一個文件使用跟超過相似性的層級設定 ND。 
  
例如，假設相似性設為 80%、 文件 F1 類似的 85%的層級的文件 f2 鍵和文件 f2 鍵的格式類似於文件 F3 90%的層級。 
  
不過，文件 F1 可能類似文件 F3 僅 70%以下，以低於閾值的層級。 不過，在此範例中，文件中，F1、 F2、 F3 所有都會出現在一個 ND 設定。 同樣地，使用相似性值的 80%，我們可能會建立兩組，EquiSet-1 和 EquiSet-2。 EquiSet 1] 會包含文件 E1 和 E2。 Equiset 2 包含 F1，F2、 F3 的文件。 
  
類似的層級圖例所示，如下所示：
  
![文件相似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
假設另一個文件，X1，會立即插入。 X1 和 E3 之間跟是 87%。 同樣地，跟 X1 和 F1 之間是 92%。 因此，EquiSet-1、-2、 EquiSet 和 X1 現在結合為一個 ND 設定。
  
![文件相似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> 如果任何兩份文件或指派給一個 ND 組，它們會保持在一起 ND 組相同，即使其他文件新增至集合如果合併設定。 
  
合併設定之後，新文件加入至集合時，可以變更樞紐分析表文件。 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)

