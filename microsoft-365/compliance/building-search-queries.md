---
title: 建立搜尋查詢-eDiscovery
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom: seo-marvel-mar2020
description: 使用關鍵字和條件，可在 Microsoft 365 中使用 [Advanced eDiscovery] 搜尋資料時縮小搜尋範圍。
ms.openlocfilehash: 86e763577c24473f8f55c5c8dc26d1853509d50a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035511"
---
# <a name="build-search-queries"></a>建立搜尋查詢

在建立搜尋查詢時，您可以使用關鍵字來尋找特定內容和條件，以縮小搜尋範圍，以傳回與您法律調查最為相關的專案。

![使用關鍵字和條件來縮小搜尋結果的範圍](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>關鍵字搜尋

在搜尋查詢的 [**關鍵字**] 方塊中，輸入關鍵字查詢。 您可以指定關鍵字、電子郵件內容（如已傳送和接收的日期）或檔案屬性（例如，檔案名或檔最後變更的日期）。 您可以使用內含布林運算子的更複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 您也可以在 SharePoint 和 OneDrive （不是在電子郵件訊息中）的檔中搜尋機密資訊（例如社會保險號碼），或搜尋已從外部共用的檔。 如果 [**關鍵字**] 方塊是空白的，則位於指定內容位置的所有內容都位於搜尋結果中。
    
或者，您也可以選取 [**顯示關鍵字清單**] 核取方塊，並在每一列中輸入關鍵字或關鍵字片語。 如果您這麼做，每一列中的關鍵字會透過邏輯運算子（表示為*c:s* in 搜尋查詢語法）來連接，該運算子在所建立的搜尋查詢中的功能與**OR**運算子類似。 這表示搜尋結果中包含任何列的任何關鍵字的專案。

![使用關鍵字清單取得查詢中每個關鍵字的統計資料](../media/KeywordListSearch.png)

為什麼要使用關鍵字清單？ 您可以取得統計資料，顯示與關鍵字清單中每個關鍵字相符的專案數目。 這可協助您快速識別最有效的關鍵字（和最低的）。 您也可以使用關鍵字] 清單中列的關鍵字片語（以括弧括住）。 如需搜尋統計資料的詳細資訊，請參閱[搜尋統計資料](search-statistics.md)。

> [!NOTE]
> 為了避免大型關鍵字清單所造成的問題，您最多隻能有20列的關鍵字清單。

## <a name="conditions"></a>條件
    
您可以新增搜尋條件，以縮小搜尋範圍，並傳回更精緻的結果集。 每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。 條件會以邏輯方式連線至關鍵字] 方塊中指定的關鍵字查詢（表示為*c:c* in 搜尋查詢語法），該運算子在功能上與**AND**運算子類似。 這表示專案必須同時滿足關鍵字查詢，以及要包含在搜尋結果中的一或多個條件。 這是條件協助縮小搜尋結果的方式。 如需您可以在搜尋查詢中使用的條件清單和描述，請參閱[關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)中的「搜尋條件」一節。
