---
title: 在 Office 365 進階電子文件探索中設定分析選項
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '檢閱步驟以設定 Office 365 進階電子文件探索，包括近似重複項目、 電子郵件執行緒，以及佈景主題中的分析處理程序的選項。  '
ms.openlocfilehash: b6155814a4540f4cc619382d82cee34c471390d1
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802736"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中設定分析選項

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在進階電子文件探索中設定分析選項之前執行分析。
  
## <a name="set-analyze-options"></a>設定分析選項

開啟**準備\>分析** \> **安裝程式**。 會顯示下列視窗。
  
![設定分析選項](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **近似重複項目和電子郵件執行緒**如果您想要執行分析，請核取此方塊。 此為預設選取的選項。 
  
 **文件相似性**輸入 Near 重複的臨界值，或接受預設值是 65%。 
  
 **佈景主題**核取此方塊可處理所有檔案，並將佈景主題指派給他們。 根據預設，不會選取此核取方塊。 如果您想要執行處理的佈景主題，請輸入下列選項。
  
- **佈景主題的最大數目**輸入或選取要建立的佈景主題數目的值。 預設值為 200。 
    
    > [!NOTE]
    > 增加的佈景主題數目會影響效能，以及佈景主題一般化的能力。 佈景主題數目愈高，更細微它們是。 例如，如果 50 個佈景主題的一組包括 「 籃球、 Spurs、 Clippers，Lakers 」; 例如佈景主題300 佈景主題可能會包含不同的佈景主題: 「 Spurs 」、 「 Clippers 」、 「 Lakers 」。 如果您不有任何認知佈景主題的 「 籃球 」，並使用 ECA 這項功能，看到佈景主題 」 籃球 」 可能是很有用。 但是，如果處理有太多的佈景主題，您可能永遠不會看到 「 籃球 」 這個字後，可能不知道，Spurs 和 Clippers 是很好的籃球佈景主題，若要檢閱，而非移入的項目會開機並用於字形。 
  
- **建議的佈景主題**您可以建議來控制處理的佈景主題的佈景主題文字。 進階電子文件探索會專注於這些建議的字詞，並嘗試建立一或多個相關的佈景主題，根據 「 最大的佈景主題的數字 」 的設定。 
    
    例如，如果建議的單字"computer"，且您指定作為 」 主題數目上限 「"2"，進階電子文件會嘗試產生關聯到 「 電腦 」 這個字的兩個佈景主題。 佈景主題的兩個可能會 「 電腦軟體 」 和 「 電腦硬體 」，例如。 
    
    ![新增建議的佈景主題](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. 若要檢視、 新增或編輯建議的佈景主題，按一下 [**修改**]。
    
2. 在 [**建議追蹤的佈景主題**] 面板中，按一下 [**新增**![新增圖示](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)圖示以新增佈景主題。 在 [**新增建議的佈景主題**] 面板中，新增字詞，以逗號隔開。 
    
3. **佈景主題數目**，選取一個值來判斷進階電子文件會嘗試將產生的 （預設值為 1 佈景主題） 這些字詞的佈景主題數目。
    
4. 按一下 [**儲存**]，然後關閉對話方塊。 
    
    > [!NOTE]
    > 總數的佈景主題包含建議的佈景主題。 總數的建議的佈景主題不能超過總佈景主題。 如果有許多的建議的佈景主題，相對於總佈景主題，只有幾個 「 小說 」 佈景主題會偵測系統，因為大部分的佈景主題會專用於建議的佈景主題。 
  
- **模式**從下拉式清單中選取**佈景主題**選項： 
    
  - **建立並套用模型**： 計算的模型檔案的線段的佈景主題，並再將它們之間的檔案。
    
  - **建立模型**： 計算從檔案的線段的佈景主題模型。 在其他時候分別完成的分割檔案套用程序。
    
  - **套用模型**： 是否先前建立及尚未套用模型，僅會顯示此選項。 這會將佈景主題為基礎的檔案。
    
您也可以[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)，並[設定分析進階設定]](set-analyze-advanced-settings-in-advanced-ediscovery.md)的分析。 
  
您已設定這些選項之後，按一下 [**分析**]，以執行。 [檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)會顯示。 
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)

