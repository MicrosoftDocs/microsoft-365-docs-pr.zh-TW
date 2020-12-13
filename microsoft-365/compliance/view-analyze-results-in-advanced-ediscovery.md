---
title: 在高級電子檔探索中查看分析結果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 瞭解在高級 eDiscovery 中查看分析程式結果的位置，包括所顯示之任務選項的定義。
ms.openlocfilehash: 64c91cb5929a7a74e53d653faff98d5792d3f131
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663253"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a>在「高級 eDiscovery (傳統) 中查看分析結果

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在 [高級 eDiscovery] 中，分析程式的進度和結果可以透過如下所述的各種顯示器加以查看。
  
## <a name="view-analyze-task-status"></a>View 分析任務狀態

在 [ **準備 \> 分析 \> 結果 \>**] 工作狀態中，會在分析程式執行期間和之後顯示狀態。 
  
![分析工作狀態](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
顯示的工作可能會隨選取的選項而異。 
  
- **ND/ET： setup**：為執行做好準備，例如設定 run 和 case 參數。
    
- **Nd/ET： nd 計算**：處理檔案的接近重複的分析。
    
- **ND/ET： ET 計算**：對整個電子郵件集執行電子郵件執行緒分析。
    
- **ND/ET：旋轉及類似** 點：執行 pivot 及檔相似性處理。
    
- **ND/ET：中繼資料更新**：完成資料庫中檔案上收集的新資料。
    
- **主題：主題計算**：執行主題分析。 只有選取此選項才會顯示 (。 ) 
    
- 工作 **狀態**：在任務完成後會顯示此行。 在執行工作時，會顯示 [執行持續時間]。
    
> [!NOTE]
> 「近期重複」和「電子郵件」執行緒的分析結果 (ND 和 ED) 會套用到要處理的檔數目。 不會包含完全重複的檔案。 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>查看接近重複和電子郵件的執行緒狀態

**目標** 人口結果會顯示目標人口中的檔、電子郵件、附件及錯誤數目。 
  
**檔** 結果會顯示轉動的數目、唯一接近重複的專案，以及完全重複的檔案。 
  
**電子** 郵件結果會顯示包含、包含減去包含的唯一包含副本，以及其餘的電子郵件訊息的數目。 不同類型的電子郵件結果如下： 
  
- **包含**：包含電子郵件是電子郵件線索中的終止節點，且包含該執行緒先前的所有歷史。 因此，檢閱者可以安全地著重于包含的電子郵件，而不需要先讀取執行緒中的先前訊息。 
    
- **包括減號**：若有一個或多個不同的附件與包含的郵件的父代相關聯，則指定為包含的非獨佔電子郵件。 在此內容中，「父項」是用於向上的電子郵件線索或該特定包含電子郵件中所含之交談的郵件。 檢閱者可以使用包括減號表示做為信號，雖然可能不需要複查包含的電子郵件父代的內容，但審閱與包含的路徑父系相關聯的附件可能很有用。 
    
- **包含副本**：若包含的電子郵件是另一封標記為包含或包含減號的郵件複本，則指定為包含副本。 換句話說，這封郵件與另一個包含的郵件有相同的主旨和內文，所以共同位於相同的節點。 由於包含的副本郵件包含相同的內容，因此通常可以在審核程式中略過。 
    
- **Rest**：這表示不含任何唯一內容的電子郵件，因此不屬於上述任何一種類別。 不需要檢查這些電子郵件訊息。 如果郵件包含附件，但不在後續包含的電子郵件中，可能需要檢查附件。 這會線上程記憶體在非獨佔減去電子郵件的指示。
    
[ **附件** ] 結果會顯示附件的數目，根據這種類型的唯一和重複。 
  
![近似重複項目和電子郵件執行緒](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>請參閱

[Office 365 進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[瞭解檔相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析高級設定](view-analyze-results-in-advanced-ediscovery.md)

