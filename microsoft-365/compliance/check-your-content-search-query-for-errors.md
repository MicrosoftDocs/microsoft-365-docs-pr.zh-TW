---
title: 檢查您的內容搜尋查詢是否有錯誤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 瞭解如何在執行搜尋之前，偵測關鍵字搜尋中的錯誤與打字錯誤。
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818092"
---
# <a name="check-your-content-search-query-for-errors"></a>檢查您的內容搜尋查詢是否有錯誤

當您建立或編輯內容搜尋時，您可以讓 Microsoft 365 檢查您的查詢中是否有不支援的字元及小寫 Boolean 運算子。 怎麼做？ 只需在內容搜尋的 [查詢] 頁面上，按一下 [**檢查查詢以進行錄入**。 
  
![按一下 [檢查查詢的錄入錯誤]，檢查您的搜尋查詢是否有不支援的字元](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
以下是我們所檢查的不支援字元清單。 不支援的字元通常是隱藏的，而且通常會導致搜尋錯誤或傳回意外的結果。
  
- **彎引號**-智慧單引號和雙引號（也稱為彎引號）不受支援。 在搜尋查詢中只可以使用直引號。 
    
- **不可列印和控制字元**-不可列印和控制字元不代表書面符號，例如字母數位字元。 非列印字元和控制字元的範例包含格式化文字或個別文字行的字元。 
    
- **從左至右和從右至左的標記**是指用來表示從左至右語言（例如英文和西班牙文）和從右至左語言（例如阿拉伯和希伯來文）的文字方向的控制項字元。
    
- **小寫 boolean 運算子**-如果您使用 Boolean 運算子（例如**AND**、 **OR**、 **NOT** in 搜尋查詢），則該運算子必須為大寫。 當我們檢查輸入錯誤的查詢時，查詢語法通常會指出即使可以使用小寫運算子，還是要使用布林運算子;例如， `(WordA or WordB) and (WordC or WordD)` 。
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>如果查詢有不支援的字元，會發生什麼事？

如果在查詢中找到不支援的字元，就會顯示警告訊息，指出找到不支援的字元，並提出替代方法。 然後您可以選擇保留原始查詢或以建議的修訂查詢取代。 以下是在先前的螢幕擷取畫面中，針對搜尋查詢按一下 [**檢查查詢是否錄入**] 後顯示的警告訊息範例。 請注意，原始查詢包含 smart 引號及小寫 Boolean 運算子。 
  
![會顯示一則警告訊息，其中包含查詢的建議修訂](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>如何防止搜尋查詢中不支援的字元

當您從其他應用程式（例如 Microsoft Word 或 Microsoft Excel）複製查詢或部分查詢，並將其貼到內容搜尋之 [查詢] 頁面上的 [關鍵字] 方塊中時，通常會將不支援的字元加入查詢。 若要避免不支援的字元，最好的方法是在 [關鍵字] 方塊中輸入查詢。 或者，您可以複製 Word 或 Excel 中的查詢，然後將它貼到純文字編輯器（例如 Microsoft Notepad）。 儲存文字檔，並在**編碼**下拉式清單中選取**ANSI** 。 這將會移除任何格式及不支援的字元。 然後，您可以將查詢從文本檔案複製並貼到關鍵字查詢方塊。 
