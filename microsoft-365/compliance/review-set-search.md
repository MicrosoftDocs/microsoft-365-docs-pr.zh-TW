---
title: 查詢檢視集中的資料
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078172"
---
# <a name="query-the-data-in-a-review-set"></a>查詢檢視集中的資料

在大多數情況下，將能夠深入探討還有什麼中檢閱設定，並將它們更有效率地檢閱組織很有用。 檢閱集合內的查詢可讓您若要這樣做，可讓您專注於符合一次您所定義之準則的文件的子集。

## <a name="creating-and-running-a-query-within-a-review-set"></a>建立和執行檢閱集合內的查詢

才能建立及執行查詢，以在您檢閱集內，按一下 [您檢閱集中在 「 新增查詢 」。 在您的查詢名稱並定義條件之後，按一下 「 儲存 」 以執行查詢。 若要執行的查詢，先前尚未儲存，只要按一下已儲存的查詢。 如需您可以藉由搜尋的中繼資料的清單，請參閱[文件中繼資料](document-metadata-fields.md)欄位。

## <a name="building-your-query"></a>建立您的查詢

您可以建置查詢關鍵字條件卡片中使用條件卡和查詢語言的組合。 您可以在一起作為區塊，以製作較複雜的查詢群組條件卡。

### <a name="condition-card"></a>條件卡

檢閱集合中每個可搜尋的欄位具有對應的條件介面卡，您可用來建置您的查詢。

有多種類型的條件卡：
- Freetext 條件卡用於文字欄位，例如主旨 Freetext:。 您可以使用分號分隔這些列出多個搜尋字詞。
- 日期： 日期條件卡係供例如上次修改日期的日期欄位。
- 搜尋選項： 搜尋選項條件卡提供可能的值清單中檢閱設定特定的欄位。 這用於欄位，例如寄件者數量有限的可能值在您檢閱集中的地方。
- 關鍵字： 關鍵字條件卡片是 freetext 條件卡片，您可以使用搜尋字詞，或使用 KQL 類似的查詢語言中的特定執行個體。 如需詳細資訊，請參閱以下內容。

### <a name="query-language"></a>查詢語言

除了條件卡] 底下，您可以使用類似的 KQL 查詢語言關鍵字卡片，製作您的查詢。 語言支援標準 KQL 語法，例如 AND、 OR、 NOT、 查詢和 NEAR(n)。 它也支援單一字元萬用字元 （？） 以及多重字元萬用字元 （*）。

## <a name="filter"></a>篩選

除了您可以儲存的查詢，您可以使用篩選器您查詢結果重疊飛出視窗上的其他條件。 篩選與一些重大的方式不同查詢：
- 篩選器是暫時性 （亦即它們不會保存透過不同的工作階段），而查詢會儲存至檢閱設定。
- 篩選器永遠都會 additive;篩選會套用掌握您此時，有作用中的查詢，而套用查詢將會取代查詢作用中。