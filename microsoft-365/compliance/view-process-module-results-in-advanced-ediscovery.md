---
title: 在高級電子檔探索中查看進程模組結果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 瞭解如何在高級 eDiscovery 中尋找處理模組的結果，包括任務狀態和流程摘要。
ms.openlocfilehash: 73699d77e305055f6c2dc444fff00fb714b458cd
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663257"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a>在高級 eDiscovery (傳統) 中查看進程模組結果

啟動 **準備** \> 程式後，您可以查看進度和結果。 
  
> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="process-task-status"></a>進程任務狀態

在 [ **準備** \> **處理** \> **結果**] 中，頁面會顯示目前的狀態 (如果處理常式目前是否正在執行) 或上一個處理狀態任務狀態，如下列範例所示。
  
![處理序模組的工作狀態](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
顯示的工作可能會因選取的處理選項而異。 
  
- **庫存**：高級電子檔探索會迴圈查看所有選取進行處理的檔案，並執行基本資料收集。
    
- **計算簽名**：計算 MD5 數位簽章。
    
- **複合提取**：以遞迴方式從複合檔案（例如，PST，ZIP，MSG) ）內，解壓縮內檔或包含的檔案 (。 解壓縮的檔案會儲存在案例的 case 資料夾中。
    
- **同步處理資料庫**：內部資料庫處理常式。
    
- 檔案 **複本**：複製處理檔案。 即使已選取 [高級複製檔案] 選項，此工作還是會一直顯示。
    
- **文字提取**：有原生檔案時，「高級 eDiscovery」會使用 DTSearch 從這些檔案中解壓縮文字。 這些檔案的解壓縮文字會儲存為案例資料夾中的文字檔。
    
- **更新中繼資料**：處理已載入的中繼資料。 
    
- **完成**：處理已載入之案例檔案之資料的內部處理 (例如，識別錯誤和成功檔案) 。 
    
工作狀態：顯示在任務完成之後。 在執行工作時，會顯示 [執行持續時間]。
  
> [!NOTE]
> 已完成的工作也可以包含完成處理的檔案或發生錯誤的檔案的總數。 
  
> [!TIP]
> 「取消」提供回滾選項，可停止程式的執行，然後回到先前的資料填充或儲存的已處理資料。 Rollback 會清除所有已處理的資料。 如果您不希望處理的資料遺失 (例如，您計畫在) 中重新載入這些檔案，請選取此視窗中的 [取消] 選項，選擇不復原。 
  
## <a name="process-summary"></a>進程摘要

在 [準備 \> 處理 \> 結果] \> 流程摘要中，會根據成功的檔案處理及錯誤結果，顯示已載入檔案結果的分解。
  
此窗格呈現匯入的檔案統計資料的圖形顯示，如下所示：
  
- **進程摘要會累積** d：案例中的所有檔案。
    
- **進程摘要最後**：從上一個會話或動作中載入的檔案。 
    
- **過去**：在案例中的系列資訊 (如果有任何) 。
    
- 如果已新增 **seed** 檔案，則會針對檔案所定義的每個問題列出 seed 檔案數目。 
    
    如果 **植** 入檔的標記失敗，也會注明。 
    
- 如果新增 **預先標記** 的檔案，則會針對檔案所定義的每個問題列出預先標記的檔案數目。 
    
    如果 **預先標記** 檔的標記失敗，也會注明。 
    
![處理序模組摘要](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>處理摘要及最後一個圖表

左邊的列包括來源 + 解壓縮的檔案：這是找到的所有檔案。 
  
正確的列（處理的）包括：
  
- 有載入錯誤的檔案
    
- 已成功載入檔案，可能包括： 
    
  - **現有**：以前載入和現在載入的檔案， (包含重複) 。
    
  - **Text**：具有文字的唯一檔。
    
  - **非文字**：空白的文字檔、空白的原生文字檔、原生非文字檔。 
    
  - **重複** s：具有文字的重複檔案。
    
## <a name="last-process-errors"></a>最後處理常式錯誤

在 [準備 \> 處理結果] 中 \> \> ，會顯示最後一個會話或執行的錯誤詳細資料中的處理常式錯誤。
  
![處理序模組錯誤](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>請參閱

[Office 365 進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[執行處理模組及載入資料](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

