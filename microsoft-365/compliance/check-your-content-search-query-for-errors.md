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
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何檢查關鍵字查詢的內容搜尋中是否有錯誤和輸入錯誤，例如不支援的字元及小寫 Boolean 運算子。
ms.openlocfilehash: 489afd8b2fe19742b63232d323197afecc257ccc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035625"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="dc4e6-103">檢查您的內容搜尋查詢是否有錯誤</span><span class="sxs-lookup"><span data-stu-id="dc4e6-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="dc4e6-104">當您建立或編輯內容搜尋時，您可以讓 Microsoft 365 檢查您的查詢中是否有不支援的字元及小寫 Boolean 運算子。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="dc4e6-105">怎麼做？</span><span class="sxs-lookup"><span data-stu-id="dc4e6-105">How?</span></span> <span data-ttu-id="dc4e6-106">只需在內容搜尋的 [查詢] 頁面上，按一下 [**檢查查詢以進行錄入**。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![按一下 [檢查查詢的錄入錯誤]，檢查您的搜尋查詢是否有不支援的字元](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="dc4e6-108">以下是我們所檢查的不支援字元清單。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="dc4e6-109">不支援的字元通常是隱藏的，而且通常會導致搜尋錯誤或傳回意外的結果。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="dc4e6-110">**彎引號**-智慧單引號和雙引號（也稱為彎引號）不受支援。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="dc4e6-111">在搜尋查詢中只可以使用直引號。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="dc4e6-112">**不可列印和控制字元**-不可列印和控制字元不代表書面符號，例如字母數位字元。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="dc4e6-113">非列印字元和控制字元的範例包含格式化文字或個別文字行的字元。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="dc4e6-114">**從左至右和從右至左的標記**是指用來表示從左至右語言（例如英文和西班牙文）和從右至左語言（例如阿拉伯和希伯來文）的文字方向的控制項字元。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="dc4e6-115">**小寫 boolean 運算子**-如果您使用 Boolean 運算子（例如**AND**、 **OR**、 **NOT** in 搜尋查詢），則該運算子必須為大寫。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="dc4e6-116">當我們檢查輸入錯誤的查詢時，查詢語法通常會指出即使可以使用小寫運算子，還是要使用布林運算子;例如， `(WordA or WordB) and (WordC or WordD)`。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="dc4e6-117">如果查詢有不支援的字元，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="dc4e6-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="dc4e6-118">如果在查詢中找到不支援的字元，就會顯示警告訊息，指出找到不支援的字元，並提出替代方法。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="dc4e6-119">然後您可以選擇保留原始查詢或以建議的修訂查詢取代。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="dc4e6-120">以下是在先前的螢幕擷取畫面中，針對搜尋查詢按一下 [**檢查查詢是否錄入**] 後顯示的警告訊息範例。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="dc4e6-121">請注意，原始查詢包含 smart 引號及小寫 Boolean 運算子。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![會顯示一則警告訊息，其中包含查詢的建議修訂](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="dc4e6-123">如何防止搜尋查詢中不支援的字元</span><span class="sxs-lookup"><span data-stu-id="dc4e6-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="dc4e6-124">當您從其他應用程式（例如 Microsoft Word 或 Microsoft Excel）複製查詢或部分查詢，並將其貼到內容搜尋之 [查詢] 頁面上的 [關鍵字] 方塊中時，通常會將不支援的字元加入查詢。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="dc4e6-125">若要避免不支援的字元，最好的方法是在 [關鍵字] 方塊中輸入查詢。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="dc4e6-126">或者，您可以複製 Word 或 Excel 中的查詢，然後將它貼到純文字編輯器（例如 Microsoft Notepad）。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="dc4e6-127">儲存文字檔，並在**編碼**下拉式清單中選取**ANSI** 。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="dc4e6-128">這將會移除任何格式及不支援的字元。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="dc4e6-129">然後，您可以將查詢從文本檔案複製並貼到關鍵字查詢方塊。</span><span class="sxs-lookup"><span data-stu-id="dc4e6-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
