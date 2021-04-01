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
ms.openlocfilehash: 296f30f5332165017f5c7ccebc35c0663041718d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470444"
---
# <a name="check-your-content-search-query-for-errors"></a>檢查您的內容搜尋查詢是否有錯誤
  
以下是我們所檢查的不支援字元清單。 不支援的字元通常是隱藏的，而且通常會導致搜尋錯誤或傳回意外的結果。
  
- **彎引號** -彎單引號和雙引號 (也稱為彎引號) 不受支援。 在搜尋查詢中只可以使用直引號。 

- **不可列印和控制字元** -不可列印和控制字元不代表書面符號，例如字母數位字元。 非列印字元和控制字元的範例包含格式化文字或個別文字行的字元。 

- **從左至右和從右至左的標記** 是用來表示從左至右語言的文字方向 (例如，英文和西班牙) 及從右至左語言 (例如阿拉伯和希伯來文) 。

- **小寫 boolean 運算子** -如果您使用 Boolean 運算子（例如 **AND**、 **OR**、 **NOT** in 搜尋查詢），則該運算子必須為大寫。 當我們檢查輸入錯誤的查詢時，查詢語法通常會指出即使可以使用小寫運算子，還是要使用布林運算子;例如，  `(WordA or WordB) and (WordC or WordD)` 。

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>如果查詢有不支援的字元，會發生什麼事？

如果在查詢中找到不支援的字元，就會顯示警告訊息，指出找到不支援的字元，並提出替代方法。 然後您可以選擇保留原始查詢或以建議的修訂查詢取代。

以下是在先前的螢幕擷取畫面中，針對搜尋查詢按一下 [ **檢查查詢是否錄入** ] 後顯示的警告訊息範例。 附注原始查詢使用的是智慧引號及小寫 Boolean 運算子。
  
![會顯示一則警告訊息，其中包含查詢的建議修訂](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>如何防止搜尋查詢中不支援的字元

當您從其他應用 (程式（例如 Microsoft Word 或 Microsoft) Excel）複製查詢或查詢的某些部分時，通常會將不支援的字元加入查詢，然後在內容搜尋的 [查詢] 頁面上，將其貼到 [關鍵字] 方塊中。 若要避免不支援的字元，最好的方法是在 [關鍵字] 方塊中輸入查詢。 或者，您可以複製 Word 或 Excel 中的查詢，然後將它貼到純文字編輯器（例如 Microsoft Notepad）。 儲存文字檔，並在 **編碼** 下拉式清單中選取 **ANSI** 。 這將會移除任何格式及不支援的字元。 然後，您可以將查詢從文本檔案複製並貼到關鍵字查詢方塊。 
