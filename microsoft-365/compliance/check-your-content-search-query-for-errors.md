---
title: 檢查您的搜尋查詢是否有錯誤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 瞭解如何在執行搜尋之前，偵測電子檔探索搜尋的關鍵字查詢中的錯誤與打字錯誤。
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311685"
---
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="6cc1f-103">檢查您的搜尋查詢是否有錯誤</span><span class="sxs-lookup"><span data-stu-id="6cc1f-103">Check your search query for errors</span></span>
  
<span data-ttu-id="6cc1f-104">以下是在搜尋查詢中檢查內容搜尋及核心 eDiscovery 的不支援字元清單。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="6cc1f-105">不支援的字元通常是隱藏的，而且通常會導致搜尋錯誤或傳回意外的結果。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="6cc1f-106">**彎引號** -彎單引號和雙引號 (也稱為彎引號) 不受支援。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="6cc1f-107">在搜尋查詢中只可以使用直引號。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="6cc1f-108">**不可列印和控制字元** -不可列印和控制字元不代表書面符號，例如字母數位字元。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="6cc1f-109">非列印字元和控制字元的範例包含格式化文字或個別文字行的字元。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="6cc1f-110">**從左至右和從右至左的標記** 是用來表示從左至右語言的文字方向 (例如，英文和西班牙) 及從右至左語言 (例如阿拉伯和希伯來文) 。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="6cc1f-111">**小寫 boolean 運算子** -如果您使用 Boolean 運算子（例如 **AND**、 **OR**、 **NOT** in 搜尋查詢），則該運算子必須為大寫。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="6cc1f-112">當我們檢查輸入錯誤的查詢時，查詢語法通常會指出即使可以使用小寫運算子，還是要使用布林運算子;例如，  `(WordA or WordB) and (WordC or WordD)` 。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="6cc1f-113">如果查詢有不支援的字元，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="6cc1f-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="6cc1f-114">如果在查詢中找到不支援的字元，就會顯示警告訊息，指出找到不支援的字元，並提出替代方法。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="6cc1f-115">然後您可以選擇保留原始查詢或以建議的修訂查詢取代。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="6cc1f-116">以下是在先前的螢幕擷取畫面中，針對搜尋查詢按一下 [ **檢查查詢是否錄入** ] 後顯示的警告訊息範例。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="6cc1f-117">附注原始查詢使用的是智慧引號及小寫 Boolean 運算子。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![會顯示一則警告訊息，其中包含查詢的建議修訂](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="6cc1f-119">如何防止搜尋查詢中不支援的字元</span><span class="sxs-lookup"><span data-stu-id="6cc1f-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="6cc1f-120">當您從其他應用 (程式（例如 Microsoft Word 或 Microsoft Excel) ）複製查詢或查詢的某些部分時，通常會將不支援的字元新增至查詢，然後在內容搜尋的 [查詢] 頁面上，將其貼到 [關鍵字] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="6cc1f-121">若要避免不支援的字元，最好的方法是在 [關鍵字] 方塊中輸入查詢。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="6cc1f-122">或者，您可以複製 Word 或 Excel 中的查詢，然後將它貼到純文字編輯器中，例如 Microsoft 記事本。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="6cc1f-123">儲存文字檔，並在 **編碼** 下拉式清單中選取 **ANSI** 。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="6cc1f-124">這將會移除任何格式及不支援的字元。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="6cc1f-125">然後，您可以將查詢從文本檔案複製並貼到關鍵字查詢方塊。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
