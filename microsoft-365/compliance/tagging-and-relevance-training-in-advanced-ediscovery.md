---
title: 高級 eDiscovery 中的標記與相關性訓練
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 在 [高級 eDiscovery] 的「相關性訓練」階段中，瞭解標記的步驟，然後再使用40檔案的訓練範例。
ms.openlocfilehash: d576b0a907a4c12eabe4f3cba9846de670b0ee12
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663448"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery-classic"></a>Advanced eDiscovery (傳統) 中的標記與相關性訓練

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主題說明使用高級 eDiscovery 相關性訓練模組的程式。 
  
在 [Advanced eDiscovery] 中完成評估之後，並輸入相關性訓練階段時，40檔的訓練範例會進入 [標籤] 索引標籤以進行標記。 
  
## <a name="performing-relevance-training"></a>執行相關性訓練

1. 在 [ **相關性 \>** 標籤] 索引標籤中，預設會在左窗格中顯示 [標記] 窗格，並顯示範例檔案，一次顯示一個標記。 
    
    ![相關性標籤面板](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    **在 [卷** 標] 索引標籤中，會顯示檔的顯示名稱。 這可以是路徑、電子郵件主題、標題或使用者定義的名稱。 您可以在檔案的路徑上按一下滑鼠右鍵，以複製識別碼、檔路徑或文字路徑。 
    
    [標籤] 卷 **標標記統計** 資料會顯示左窗格頂端 (的檔案範例編號) 、目前顯示的檔案的總數（從右窗格中的 [下一個] 的 [下一個] 窗格 (中的 [下一個]）和 [範例中的標籤總數]) ，以及在左 (窗格的範例中，會隨著您標籤檔而變更的範例 這適用于任何已完成的相關性標記，不論是在評估、訓練、追趕或測試中。 
    
    指出批註、標記及系列檔是否存在的圖示會顯示在檔案上方的檔案視圖中的檔。
    
2. 判斷案例問題的相關程度，並使用 [標記] 選項圖示按鈕或快速鍵標記檔案，如下表所示：

|**標記選項**|**描述**|**捷徑**|**針對多個問題-大量標記鍵盤快速鍵**|
|-----|-----|-----|-----|
|R  <br/> |相關  <br/> |Z  <br/> |Shift + Z  <br/> |
|星期日  <br/> |不相關  <br/> |X  <br/> |Shift + X  <br/> |
|略過  <br/> |略過  <br/> |C  <br/> |Shift + A  <br/> |
   
  - 如果有多個問題存在於檔案中，在標記一個問題之後，選取範圍就會移至下一個問題 (如果有任何) 。 
    
  - 當醒目提示的關鍵字 (相關性設定醒目提示的關鍵字) 時，系統會以 \> 指定的色彩顯示 () 的關鍵字，以協助識別標記時的相關檔案。 如果關鍵字具有雙底線，可按一下該關鍵字以顯示具有關鍵詞描述的工具提示。 
    
    （選用）在 **[卷** 標] 索引標籤中，按一下 [ **標記設定** ] 以設定下列選項： 
    
    ![相關性標籤設定](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - **大容量** 標籤：使用此選項可為檔案指派多個問題，方法是選取 [ **全部** ]，為所選取的檔案設定所有問題的標記， (覆寫已標記的問題) 或選取 **[其他** ]，將標記套用至其餘的未加標記的問題。 選取的選項會在所有使用者的案例中一直保持作用，直到使用者變更 (設定為每位使用者) 所有使用者的案例。 
    
  - **自動標記**：選取此核取方塊，可在單一相關標記之後，將檔案的其他問題設定為 [不相關]。
    
  - **自動推進**：選取此核取方塊，當您將所顯示的檔案選取範圍移至下一個檔時，會將其移至下一個檔案。 
    
    已略過的檔案不會被視為相關性訓練及相關性計分的目的。
    
3. 您可以透過左窗格下拉式清單中的 [ **批註** ] 選項，查看及編輯與檔案相關聯的任意文字批註。  (選用)  
    
4. 您可以在左窗格下拉式清單中選取 [ **標記指導方針** ] 選項，以查看標記的指導方針。 
    
5. 當您完成清單中所有檔案的標記且準備好計算結果之後，請按一下 [ **計算**]。 顯示 [ **追蹤** ] 索引標籤。 
    
## <a name="working-with-the-sample-files-list"></a>使用範例檔案清單

範例檔案清單可讓您在訓練範例中查看檔案的清單，並在一或多個檔案上執行各種動作。 在 [**相關性** 標籤] 索引標籤中 \>  ，**範例** 檔案左窗格會顯示範例檔案的清單，以進行評估、訓練、追趕及不一致的處理常式。 
  
1. 在 [ **相關性 \> 標記** ] 索引標籤中，選取左窗格下拉式清單中的範例檔案。 範例檔案會列在左窗格中。 
    
    ![相關性標籤範例檔案清單](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. 在 [ **範例** ] 或 [檔案] 方塊中輸入或選取特定的範例或 **檔編號** ，以選取它。 
    
  -   - 檔順序編號會列 **在 [標籤] 索引** 標籤上顯示之檔案清單的左欄中。按一下頁首，檔案的原始顯示順序會傳回其原始訂單。 
    
  - 按一下檔列時，會在右窗格中顯示其內容。
    
  - 使用下方的功能表列選項，在目前範例中的檔案間流覽。 此外，導覽鍵盤快速鍵也可供使用：
    
    流覽至範例中的第一個檔案： Shift + Ctrl + \<
    
    若要流覽至範例中的上一個檔案： Shift + \<
    
    流覽至範例中的下一個檔案： Shift + \>
    
    若要流覽至範例中的最後一個檔案： Shift + Ctrl + \>
    
## <a name="see-also"></a>請參閱

[Office 365 進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[瞭解相關評估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記與評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[根據結果決定](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

