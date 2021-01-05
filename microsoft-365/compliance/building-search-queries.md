---
title: 在高級 eDiscovery 中建立搜尋查詢
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: 使用關鍵字和條件，可在 Microsoft 365 中使用 [Advanced eDiscovery] 搜尋資料時縮小搜尋範圍。
ms.openlocfilehash: 8ec1e099625bb081f8a915f08ac818fddcc2b60d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751110"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a>在高級電子檔探索中建立搜尋集合查詢

當您建立搜尋查詢以在高級 eDiscovery 案例中收集資料時，您可以使用關鍵字來尋找特定內容和條件，以縮小搜尋範圍，以傳回與您法律調查最為相關的專案。

![使用關鍵字和條件來縮小搜尋結果的範圍](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>關鍵字搜尋

在搜尋查詢的 [ **關鍵字** ] 方塊中，輸入關鍵字查詢。 您可以指定關鍵字、電子郵件內容（如已傳送和接收的日期）或檔案屬性（例如，檔案名或檔最後變更的日期）。 您可以使用內含布林運算子的更複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 您也可以搜尋機密資訊 (例如，SharePoint 中的檔) 或 OneDrive (不在電子郵件中) ，或是搜尋外部共用的檔。 如果 [ **關鍵字** ] 方塊是空白的，則位於指定內容位置的所有內容都位於搜尋結果中。

## <a name="keyword-list"></a>關鍵字清單

或者，您也可以選取 [ **顯示關鍵字清單** ] 核取方塊，並在每一列中輸入關鍵字或關鍵字片語。 每一列中的關鍵字是由邏輯運算子 (所組成，該運算子會在搜尋查詢語法) 中以類似于在所建立之搜尋查詢中的 **OR** 運算子的功能，表示為 *c:s* 。 這表示搜尋結果中包含任何列的任何關鍵字的專案。 在高級 eDiscovery 搜尋查詢的關鍵字清單中，最多可以新增180列。

![使用關鍵字清單取得查詢中每個關鍵字的統計資料](../media/KeywordListSearch.png)

為什麼要使用關鍵字清單？ 您可以取得統計資料，顯示與關鍵字清單中每個關鍵字相符的專案數目。 這可協助您快速識別最 (及最低) 有效的關鍵字。 您也可以使用關鍵字片語 (關鍵字] 清單中某列的括弧括住) 。 如需搜尋統計資料的詳細資訊，請參閱 [搜尋統計資料](search-statistics-in-advanced-ediscovery.md)。

## <a name="conditions"></a>條件

您可以新增搜尋條件，以縮小搜尋範圍，並傳回更精緻的結果集。 每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。 條件會以邏輯方式連線至 [關鍵字] 方塊中指定的關鍵字查詢，邏輯運算子 (會以與 **AND** 運算子功能類似的搜尋查詢語法) 中的 *c:c* 表示。 這表示專案必須同時滿足關鍵字查詢，以及要包含在搜尋結果中的一或多個條件。 這是條件協助縮小搜尋結果的方式。 如需您可以在搜尋查詢中使用的條件清單和描述，請參閱 [關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)中的「搜尋條件」一節。
