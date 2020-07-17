---
title: 在 [高級 eDiscovery] 中設定 [忽略文字] 選項以進行分析
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 瞭解如何在使用高級 eDiscovery 中的 [分析與處理模組時，定義規則以忽略特定文字]。
ms.openlocfilehash: fd7b1f3236c88faf792a97146bbed35802f6c695
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936890"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a>設定 [忽略文字] 選項，以在高級 eDiscovery （古典）中進行分析

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
[忽略文字] 功能可以套用到下列所有或任何的高級 eDiscovery 模組：分析（近乎重複的電子郵件執行緒、主題）及相關性。 「相關性」顯示的檔案中不會顯示忽略的文字，而且分析/計算會捨棄忽略的文字。
  
如果先前已經為已執行的模組定義 [忽略文字] 功能，則 [忽略文字] 設定現在會受到保護，無法進行修改。 不過，相關性模組的 [忽略文字] 功能仍可在任何時間變更。
  
## <a name="how-ignore-text-filters-are-applied"></a>如何套用 Ignore 文字篩選

多個 Ignore Text 篩選依輸入的順序套用。 若要變更套用的順序，必須將它們刪除並以所需的順序重新輸入。
  
例如，如果文字內容是：「DAVE 小明小紅 CAROL 前夕」，下列為 Ignore Text entries 和 results 的範例：
  
||||
|:-----|:-----|:-----|
|**忽略文字專案** <br/> |**==\>** <br/> |**Results** <br/> |
|"ALICE"，"小明 CAROL"  <br/> |==\>  <br/> |"DAVE 前夕"  <br/> |
|"ALICE"，"小明 ALICE CAROL"  <br/> |==\>  <br/> |"DAVE 小明 CAROL 前夕"  <br/> |
   
第二個 Ignore Text 專案並未執行，因為在套用第一個 Ignore 文字之後，就不會找到該字串。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>定義忽略文字時使用正則運算式

定義 Ignore Text 時，支援使用正則運算式。 以下是正則運算式語法和用法的範例：
  
- 若要移除（ignore）文字，直到行尾為止：
    
     `Begin(.*)$`
    
    其中，"Begin" 是此字串在該行中的初始出現次數。
    
    例如，下列文字：
    
    **這是第一個句子和第一行**
    
    **這是第二個句子和第二行 "**
    
    正則運算式 first （. \* ）$ 會產生：
    
    **「這是**
    
    **這是第二個句子和第二行 "**
    
- 若要移除在電子郵件執行緒結束時自動插入免責聲明和法律陳述：
    
     `Begin(.|\s)*End`
    
    其中，「開始」和「結束」是換行文欄位落的開頭和結尾的唯一字串。 
    
    例如，下列正則運算式將移除電子郵件執行緒中的開始和結束字串之間的免責聲明和法律聲明：
    
    **此郵件包含機密資訊（. |\s） \* 如果需要驗證，請要求硬拷貝版本**
    
- 若要移除免責聲明（包括特殊字元）： 
    
    例如，下列文字（由 x 所代表的免責聲明）： 
    
    **/\*\ 此郵件包含機密資訊。xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx 如果需要驗證，請要求硬拷貝版本。/\*\**
    
    移除上述免責聲明的正則運算式應該是： 
    
    **\/\\*\\此郵件包含機密資訊 \. （. |\s） \* 如果需要驗證，請要求硬拷貝版本 \.\/\\*\\**
    
- 正則運算式規則：
    
  - 除了空格、"_" 和 "-" 以外的字母表以外的任何字元，都必須加上 " \" 。
    
  - 一般 eExpression 欄位可以是無限長度。
    
> [!TIP]
> 如需正則運算式的說明和詳細語法，請參閱：[正則運算式語言-快速參考](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)。 
  
## <a name="define-ignore-text-rule"></a>定義忽略文字規則

1. 在 [**管理 \> 分析 \> 分析選項**] 索引標籤的 [**忽略文字**] 區段中，按一下 **+** 圖示以新增規則。 
    
2. 在 [**新增忽略文字**] 對話方塊的 [**名稱**] 欄位中，輸入 Ignore Text 規則的名稱。 
    
    ![加入略過的文字](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. 在**文字方塊**中，輸入要忽略的文字。 Text 欄位允許無限制數目的字元。 
    
    > [!TIP]
    > 如上表所示 **，按一下 [** 略過] 以查看 [忽略文字規則] 的常見語法指導方針。 
  
4. 如有需要，請選取 [**區分大小寫**] 核取方塊。 
    
5. 在 [套用**至**] 清單中，選取要套用定義的高級 eDiscovery 模組。 
    
6. 如果您想要測試執行樣本文字，請在 [**輸入**] 文字方塊中輸入範例文字，然後按一下 [**測試**]。 結果會顯示在 [**輸出**] 文字方塊中。 
    
7. 按一下 **[確定]** 以儲存 [忽略文字] 規則。 已定義的 Ignore 文字規則隨即顯示。 
    
    ![設定忽略文字名稱](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[瞭解檔相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定分析選項](set-analyze-options-in-advanced-ediscovery.md)
  
[設定分析高級設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析結果](view-analyze-results-in-advanced-ediscovery.md)

