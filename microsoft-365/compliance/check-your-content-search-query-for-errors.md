---
title: 檢查您的內容搜尋查詢是否有錯誤
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: 檢查錯誤和錯字，例如不支援的字元的內容搜尋的關鍵字查詢和小寫布林運算子，才能執行搜尋。 如果我們發現錯誤，則將建議的修訂的查詢。
ms.openlocfilehash: 9f9f59c4466102d678bc3a599aa208869bbd9d64
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076643"
---
# <a name="check-your-content-search-query-for-errors"></a>檢查您的內容搜尋查詢是否有錯誤

當您建立或編輯內容搜尋時，您可以檢查您的查詢不支援的字元及不可能必須大寫的布林值運算元的 Office 365。 怎麼做？ 只要按一下**檢查錯字查詢**的內容搜尋的查詢] 頁面上。 
  
![按一下 「 檢查錯字查詢 」 來檢查您的搜尋查詢不受支援的字元](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
以下是我們檢查不支援字元的清單。 通常已隱藏不支援的字元，而且它們通常會導致搜尋錯誤，或傳回非預期的結果。
  
- 不支援**智慧引號**智慧單引號及雙引號引號 （也稱為 「 智慧引號 」）。 僅限一般引號將可用於搜尋查詢。 
    
- **不可列印和控制字元**的非可列印和控制字元不代表撰寫的符號，例如英數字元。 範例的非可列印和控制字元加入文字或個別行文字格式的字元。 
    
- **左到右和從右至左標記**-這些是用來指出文字方向為左到右的語言 （例如英文和西班牙文） 和 （例如阿拉伯文和希伯來文） 的從右至左語言的控制字元。
    
- **小寫布林運算子**-如果您使用布林運算子，例如**AND**、**或者**，並**不**在 [搜尋查詢時，它必須大寫。 當我們檢查錯字的查詢時，查詢語法會通常指出即使可能使用小寫運算子;，正在使用布林運算子例如， `(WordA or WordB) and (WordC or WordD)`。
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>如果查詢有不支援的字元，會發生什麼事？

如果找不到查詢中的不受支援的字元，會顯示警告訊息表示找不到的不支援的字元和建議的另一種方法。 然後您然後可以選擇保留原始查詢，或取代的建議的修訂查詢。 以下是您的搜尋查詢的前一個螢幕擷取畫面中按一下 [**檢查錯字查詢**後，會出現警告訊息的範例。 請注意，原始查詢包含智慧引號和小寫布林運算子。 
  
![針對您的查詢建議修訂會顯示警告訊息](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>如何避免在搜尋查詢中不支援的字元

當您從其他應用程式 （例如 Microsoft Word 或 Microsoft Excel） 複製的查詢的組件，並將其複製到的內容搜尋的 [查詢] 頁面上的 [關鍵字] 方塊時，不支援的字元通常會新增至查詢。 若要防止不支援的字元，最好是只需要輸入 [關鍵字] 方塊中的查詢。 或者，您可以從 Word 或 Excel 複製查詢，並再將它的純文字編輯器，Microsoft [記事本] 之類的檔案貼。 然後儲存為文字檔，並在 [**編碼**] 下拉式清單中選取**ANSI** 。 這會移除任何格式設定與不支援的字元。 然後您可以複製並貼上文字檔案中查詢，以關鍵字的查詢] 方塊中。 
