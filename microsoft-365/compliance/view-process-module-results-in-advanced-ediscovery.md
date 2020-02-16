---
title: 在 Office 365 進階電子文件探索中檢視處理序模組結果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: '了解如何尋找 Office 365 進階電子文件探索，包括任務狀態和處理程序摘要中執行的處理序模組結果。  '
ms.openlocfilehash: 95e5e8f5ddc24bf0b8bf38800289abd233c655ad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068829"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中檢視處理序模組結果

在**準備**之後\>初始化**程序**，您可以檢視進度和結果。 
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="process-task-status"></a>程序的工作狀態

在 [**準備** \> **程序** \> **結果**，頁面會顯示目前狀態 （如果目前正在執行程序） 或最後一個的處理序狀態任務狀態在下列範例所示。
  
![處理序模組的工作狀態](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
顯示的工作會視所選取的處理程序選項而異。 
  
- **清查**： 進階電子文件會逐一查看所有程序所選取的檔案，並執行基本資料收集。
    
- **計算簽章**： 計算 MD5 數位簽章。
    
- **組合擷取**： 擷取內部或包含從複合檔案 (例如，PST，郵遞區號，MSG) 檔案以遞迴方式。 解壓縮的檔案儲存在這種情況的案例資料夾中。
    
- **同步處理資料庫**： Internal database 程序。
    
- **檔案副本**： 副本程序的檔案。 永遠顯示這項工作，即使已選取 [進階的複製檔案] 選項。
    
- **文字擷取**： 進階電子文件原生檔案時，會使用 DTSearch 這些檔案中擷取文字。 擷取的文字，這些檔案會儲存為案例的資料夾中的文字檔案。
    
- **更新的中繼資料**： 處理的載入的中繼資料。 
    
- **Finalizing**： 終結資料的內部處理載入案例檔案 （例如，找出錯誤及成功檔案）。 
    
任務狀態： 工作完成後顯示。 執行工作時，會顯示執行的持續時間。
  
> [!NOTE]
> 已完成的工作可能也包含完成處理的檔案或檔案發生錯誤的總數。 
  
> [!TIP]
> [取消] 提供停止處理程序執行，並再將回復到先前的資料填入 [復原] 選項，或儲存已處理的資料。 復原會清除所有已處理的資料。 如果您不想要選取 「 取消 「 在此視窗中的選擇選項不適用於回復 （例如，您計劃重新載入這些檔案），會遺失已處理的資料。 
  
## <a name="process-summary"></a>處理程序摘要

在 [準備\>程序\>結果\>程序摘要，明細載入的檔案的結果會顯示是根據成功檔案處理和錯誤的結果。
  
Panes 呈現匯入的檔案統計資料的圖形顯示，如下所示：
  
- **處理程序摘要累積**d： 所有檔案的情況下。
    
- **上次處理摘要**： 從最後一個工作階段或巨集指令載入的檔案。 
    
- **系列上次**： 系列資訊 （如果有的話） 的情況。
    
- 如果已新增**植入**的檔案，植入的檔案數目會列出每個已定義檔案的問題。 
    
    如果**植入**檔案的標示失敗，也記下。 
    
- 如果**預先標記**檔案已經新增，預先標記檔案的數目會列出每個已定義檔案的問題。 
    
    如果**預先標記**檔案的標示失敗，也記下。 
    
![處理序模組摘要](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>處理程序摘要累積版本和上一個圖表

左列包含來源 + 解壓縮的檔案： 這是所有檔案找到。 
  
右橫條圖、 處理，包括：
  
- 檔案載入錯誤
    
- 已成功載入的檔案，其中可能包含： 
    
  - **現有**： 之前已載入並立即載入一次 （包括重複項目） 的檔案。
    
  - **文字**： 具有文字的唯一檔案。
    
  - **非文字**： 空白文字檔案，空白的原生文字檔案，原生非文字檔案。 
    
  - **重複**s： 重複具有檔案的文字。
    
## <a name="last-process-errors"></a>上次處理錯誤

在 [準備\>程序\>結果\>會顯示最後一個程序錯誤，在最後一個工作階段或執行動作的錯誤詳細資料。
  
![處理序模組錯誤](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[執行處理序模組及載入資料](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

