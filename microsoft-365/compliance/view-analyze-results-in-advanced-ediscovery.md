---
title: 在 Office 365 進階電子文件探索中檢視分析結果
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: '了解要檢視 Office 365 進階電子文件探索，包括顯示的工作選項的定義中的分析處理的結果。  '
ms.openlocfilehash: bac173beebe2fdf3d07122bfca04cbaaee6410e6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069176"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中檢視分析結果

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在 [進階電子文件，進度和分析處理程序的結果可以檢視中顯示各種如下所示。
  
## <a name="view-analyze-task-status"></a>檢視分析工作狀態

在 [**準備\>分析\>結果\>任務狀態**、 期間和之後分析處理程序執行，會顯示狀態。 
  
![分析工作狀態](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
顯示的工作會視所選取的選項而異。 
  
- **ND/ET： 安裝程式**： 準備來執行，例如，設定執行與案例的參數。
    
- **ND/ET: ND 計算**： 程序近似重複分析的檔案。
    
- **ND/ET: ET 計算**： 執行電子郵件執行緒分析對整個電子郵件設定。
    
- **ND/ET： 樞紐分析表和相似之處**： 執行樞紐分析表和檔案相似性處理。
    
- **ND/ET： 中繼資料更新**： 完成在資料庫中的檔案上收集到的新資料。
    
- **佈景主題： 佈景主題計算**： 執行佈景主題分析。 （顯示唯有在選取了）。
    
- **工作狀態**： 這一行顯示在工作完成之後。 執行工作時，會顯示執行的持續時間。
    
> [!NOTE]
> 近似重複項目和電子郵件執行緒 （ND 和 ED） 的分析結果套用至可進行處理的文件數目。 它不包含完全重複的檔案。 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>檢視接近重複項目和電子郵件執行緒狀態

**目標**母體結果會顯示目標母體中的文件、 電子郵件、 附件及錯誤數目。 
  
**文件**結果顯示樞紐分析表、 唯一近似重複項目，並完全重複的檔案的數目。 
  
**電子郵件**結果會顯示數目 （含），內含減唯一內含的副本，以及電子郵件的其餘部分。 不同類型的電子郵件的結果是： 
  
- **Inclusive**: （含） 的電子郵件是在電子郵件執行緒中的終止節點，且包含該執行緒的所有舊的歷程記錄。 因此，檢閱者可以放心地專注於 （含） 的電子郵件，而不需要讀取在執行緒中舊的郵件。 
    
- **減 Inclusive**: （含） 的電子郵件會被指定為內含減號如果沒有父項 （含） 的郵件相關聯的一個或多個不同的附件。 在這個內容、 向上位於電子郵件執行緒或交談的郵件都使用父系字詞包含在該特定 （含） 的電子郵件。 檢閱者可以使用內含減為訊號的指示，雖然不可能需要檢閱 （含） 的電子郵件家長的內容，可能很有用來檢閱 （含） 的路徑家長相關聯的附件。 
    
- **內含的複本**： （含） 的電子郵件指定作為內含複製如果它是另一個郵件副本標示為 （含） 或減號 （含）。 換句話說，此訊息有相同的主體和主體為另一個 （含） 的郵件，因此共同位於相同的節點。 內含複製郵件包含相同的內容，因為他們可以通常會略過檢閱程序。 
    
- **其餘**： 這表示不包含任何唯一的內容，因此不屬於任何先前的三種類別的電子郵件。 這些電子郵件訊息不需要檢閱。 如果郵件包含不在稍後內含電子郵件的附件，可能需要檢閱的附件。 這被指定的電子郵件執行緒內減去 （含） 存在。
    
**附件**結果會顯示附件，根據這類為唯一的類型和重複項目數目。 
  
![近似重複項目和電子郵件執行緒](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析進階設定](view-analyze-results-in-advanced-ediscovery.md)

