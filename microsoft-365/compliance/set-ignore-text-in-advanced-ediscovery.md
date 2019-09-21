---
title: 在 Office 365 進階電子文件探索中設定略過文字分析選項
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '了解如何定義規則以在 Office 365 進階電子文件探索中使用的分析和處理序模組時，略過特定的文字。  '
ms.openlocfilehash: 70d9879f1cb6b3def06ff978fc2f7fa8f20a92f0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077771"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中設定略過文字分析選項

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
略過文字功能可以套用至所有或任何下列的進階電子文件模組： 分析 （近似重複項目，電子郵件執行緒，佈景主題） 與相關性。 略過的文字不會出現在將檔案顯示在 [相關性，並分析/計算會捨棄略過的文字。
  
如果略過文字功能先前定義已執行的模組，略過文字設定現在被防止要修改的影響。 不過，相關性模組的略過文字功能仍然可以隨時變更。
  
## <a name="how-ignore-text-filters-are-applied"></a>如何套用略過文字篩選器

所輸入的順序套用多個略過文字篩選器。 若要變更已套用的順序，他們必須刪除並重新輸入想要的順序。
  
例如，如果文字的內容: 「 目前 BOB ALICE CAROL eve 進行 」，以下是搜尋時忽略的文字項目和結果的範例：
  
||||
|:-----|:-----|:-----|
|**略過的文字項目** <br/> |**==\>** <br/> |**Results** <br/> |
|「 ALICE 」、 「 BOB 收件者 」  <br/> |==\>  <br/> |「 目前 EVE 進行 」  <br/> |
|「 ALICE"，"BOB ALICE CAROL 」  <br/> |==\>  <br/> |「 目前 BOB CAROL EVE 進行 」  <br/> |
   
因為字串找不到因此套用略過的第一個文字後，不被實作的第二個略過文字項目。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>定義搜尋時忽略的文字時使用規則運算式

定義搜尋時忽略的文字時使用的支援規則運算式。 規則運算式語法和使用狀況的範例如下：
  
- 若要移除 （忽略） 從開始，直到線條結尾的文字：
    
     `Begin(.*)$`
    
    其中 「 開始 」 是此字串在一行之初始項目。
    
    例如，針對下列文字：
    
    **「 這是第一個句子和第一行**
    
    **這是第二個句子和第二行 」**
    
    規則運算式 first(.\*)$ 會導致：
    
    **「 這是**
    
    **這是第二個句子和第二行 」**
    
- 若要移除的免責聲明與自動插入的電子郵件執行緒結尾處的法律陳述式：
    
     `Begin(.|\s)*End`
    
    其中 「 開始 」 和 「 結束 」 是唯一的字串的開頭和換行的文字段落的結尾。 
    
    例如，下列規則運算式會移除免責聲明和已 Begin 和 End 字串之間的電子郵件執行緒中的法律陳述式：
    
    **此郵件會包含機密資訊 (。 |\s)\*如果需要驗證，則請要求紙版本**
    
- 若要移除免責聲明 （包括特殊字元）： 
    
    例如，針對 （使用免責聲明這裡以 x 控點） 的下列文字： 
    
    **/\*\ 此郵件會包含機密資訊。xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx 如果驗證是必要的請要求書面版的版本。/\*\**
    
    若要移除上述免責聲明的規則運算式應該先： 
    
    **\/\\*\\此郵件會包含機密資訊\.(。 |\s)\*如果需要驗證，則請要求紙版本\.\/\\*\\**
    
- 規則運算式規則：
    
  - 為不屬於空間，「 _ 」 除了英文字母的任何字元和 「-」 必須加上"\"。
    
  - 一般 eExpression 欄位可以是無限制的長度。
    
> [!TIP]
> 說明與規則運算式的詳細的語法，請參閱：[規則運算式語言-快速參考](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。 
  
## <a name="define-ignore-text-rule"></a>定義規則，略過的文字

1. 在 [**管理\>分析\>分析選項**] 索引標籤的 [**略過的文字**] 區段中，按一下 [**+** 圖示以新增規則。 
    
2. 在 [**新增略過的文字**] 對話方塊中，在 [**名稱**] 欄位中，輸入略過文字規則的名稱。 
    
    ![加入略過的文字](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. 在 [**文字**] 方塊中，輸入要忽略的文字。 [文字] 欄位允許的字元數目不受限制。 
    
    > [!TIP]
    > 上方視窗所示，按一下 [若要查看略過文字規則的一般語法指導方針的**燈泡**。 
  
4. 如有需要，請選取**區分大小寫**] 核取方塊。 
    
5. 在 [**套用至**] 清單中，選取用來套用定義的進階電子文件模組。 
    
6. 如果您想在範例文字上執行測試，請在 [**輸入**文字] 方塊中輸入範例文字，然後按一下 [**測試**。 結果會顯示在 [**輸出**] 文字方塊中。 
    
7. 按一下 **[確定]** 以儲存搜尋時忽略文字規則]。 會顯示已定義的搜尋時忽略文字規則。 
    
    ![設定忽略文字名稱](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解文件相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定分析進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[檢視分析結果](view-analyze-results-in-advanced-ediscovery.md)

