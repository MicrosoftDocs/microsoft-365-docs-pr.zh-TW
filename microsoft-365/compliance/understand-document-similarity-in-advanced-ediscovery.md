---
title: 在高級 eDiscovery 中瞭解檔相似性
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: '請複習檔相似性值，將兩個檔案視為接近重複的最小 resemblance 層級，可在「高級 eDiscovery」中運作。 '
ms.openlocfilehash: bfce2e3018c690fc0a25bcda8e2c03690a334dc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633408"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a>瞭解 Advanced eDiscovery （古典）中的檔相似性

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在 [Advanced eDiscovery] 中，「檔相似性」是兩個檔視為接近重複專案所需的最小 resemblance 層級。
  
> [!TIP]
> 對於大部分商務應用程式，建議使用類似 60%-75% 的相似性值。 對於品質非常差的光學字元辨識（OCR）材料，可以套用較低的相似性值。 
  
> [!NOTE]
> 在指定的情況下設定及執行時，不能變更類似值。 
  
在近乎重複（ND）集內，您的檔的 resemblance 層級可能會低於相似性閾值。 若要加入 ND 集的檔，ND 集中至少必須有一個檔，且該 resemblance 的層級超過相似性。 
  
例如，假設相似性設定為80%，檔 F1 類似于85% 層級的檔 F2，而檔 F2 類似檔 F3，其層級為90%。 
  
不過，檔 F1 可能會類似于檔 F3 的一級，只是低於臨界值的70%。 不過，在此範例中，檔 F1、F2 及 F3 全都出現在一組中。 同樣地，使用相似性值80%，我們可能已建立兩個集合，EquiSet-1 和 EquiSet-2。 EquiSet-1 包含檔 E1 和 E2。 Equiset-2 包含檔 F1、F2 及 F3。 
  
Resemblance 的層級如下所示：
  
![文件相似性](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
假設現在已插入另一個檔（X1）。 X1 和 E3 之間的 resemblance 是87%。 同樣地，X1 和 F1 之間的 resemblance 是92%。 因此，EquiSet-1、EquiSet-2 和 X1 現在會結合成一個 ND 集。
  
![文件相似性](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> 如果有兩個檔指派給一個 ND 集，則即使將其他檔新增至集，或合併集時，這些檔仍會保持在相同的 ND 集中。 
  
合併設定之後，當新檔新增至集時，樞紐分析表可能會變更。 
  
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析高級設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析結果](view-analyze-results-in-advanced-ediscovery.md)

