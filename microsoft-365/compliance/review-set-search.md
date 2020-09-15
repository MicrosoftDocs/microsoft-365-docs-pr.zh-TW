---
title: 查詢檢視集中的資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何在評審集中建立及執行查詢，以在高級 eDiscovery 案例中組織資料，以進行更有效率的審閱。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 508e8e9fdb4a558a998a33aa561dc3755edcc40d
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816716"
---
# <a name="query-the-data-in-a-review-set"></a>查詢檢視集中的資料

在大多數情況下，可以深入查看檢查集合中的資料，並整理該資料，以促進更有效率的審閱。 使用審閱集中的查詢可協助您將重點放在符合您的審閱準則的檔子集。

## <a name="creating-and-running-a-query-in-a-review-set"></a>在審閱集中建立及執行查詢

若要為審閱集內的檔建立並執行查詢，請選取 [檢查集合] 中的 [ **新增查詢** ]。 在命名查詢並定義條件之後，請選取 [ **儲存** ] 以儲存並執行查詢。 若要執行先前已儲存的查詢，請選取一個已儲存的查詢。

![檢查集合查詢](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>建立審閱集查詢

您可以使用關鍵字條件卡中的條件卡和查詢語言組合，建立查詢。 您也可以將條件卡片組合在一起，當作稱為 *條件群組* 的封鎖 () 建立更複雜的查詢。 如需您可以搜尋之中繼資料屬性的清單和描述，請參閱 [Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。

### <a name="condition-cards"></a>條件卡片

每個審閱集中的可搜尋欄位都有對應的條件卡，可供您用來建立查詢。

有多種狀況卡片類型：

- Freetext：透過文字欄位（例如 subject）使用 freetext 條件卡。 您可以將多個搜尋字詞以逗號分隔，以加以列出。

- 日期：日期功能卡片用於日期欄位（例如「上次修改日期」）。

- 搜尋選項：「搜尋選項」條件卡會為您的考核集中的特定欄位提供可能的值清單。 這適用于在您的考核集中，具有有限數目的可能值的欄位（例如寄件者）。

- 關鍵字：關鍵字條件卡片是 freetext 條件卡的特定實例，可供您用來搜尋字詞，或使用 KQL 類似的查詢語言。 如需詳細資訊，請參閱下一節。

### <a name="query-language"></a>查詢語言

除了條件卡片之外，您還可以使用關鍵字智慧卡中的類似 KQL 的查詢語言來建立您的查詢。 「檢查的複查集」查詢語言支援標準 Boolean 運算子，例如 **and**、 **OR**、 **NOT**和 **NEAR**。 它也支援單一字元萬用字元 (？ ) 和多字元萬用字元 ( * ) 。

## <a name="filters"></a>篩選

除了您可以儲存的查詢之外，您還可以使用「複查集」篩選，將其他條件快速套用至審閱集查詢。 使用篩選可協助您進一步精煉「審閱集」查詢所顯示的結果。

![審閱集合篩選](../media/AeDReviewSetFilters.png)

篩選不同于查詢的兩個重要方式：

- 篩選是暫時性的。 它們不會存在於現有的會話之外。 換句話說，您無法儲存篩選。 查詢會儲存至複查集，並在開啟評審集時進行存取。

- 篩選永遠都是累加的。 除了目前的複查集查詢之外，還會套用篩選器。 套用不同的查詢會取代目前查詢所傳回的結果。
