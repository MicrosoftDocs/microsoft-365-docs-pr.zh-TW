---
title: Advanced eDiscovery 的 CJK/雙位元組支援
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解 Microsoft 365 中的 Advanced eDiscovery 如何支援中文、日文和韓文 (CJK) 語言，使用雙位元組字元集。
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926599"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Advanced eDiscovery 的 CJK 語言支援

Advanced eDiscovery 支援雙位元組字元集語言 (這包括簡化的繁體中文、繁體中文、日文和韓文，這兩種是在審校集中稱為下列高級案例的 *CJK* 語言) ：

- 當您 [查詢審閱集中的資料](review-set-search.md)。

- 當您 [為審閱集中的檔標記](tagging-documents.md)時。

- 當您使用近乎重複偵測、電子郵件執行緒及主題分析來 [分析檢查集合中的案例資料](analyzing-data-in-review-set.md) 時。

## <a name="frequently-asked-questions"></a>常見問題集

**如何建立搜尋來收集包含 CJK 字元的專案？**

在 Advanced eDiscovery 中搜尋內容時，您可以使用 CJK 字元做為[關鍵字搜尋](building-search-queries.md#keyword-searches)、[關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。 在核心 eDiscovery 和內容搜尋中搜尋內容時，也支援搜尋 CJK 字元。

我們為所有 [搜尋運算子](keyword-queries-and-search-conditions.md#search-operators) 和 [搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)提供 CJK 支援，包括 boolean 運算子 **和**、 **或**、 **NOT** 和 **NEAR**。

如果您確定內容位置或專案包含 CJK 字元，但是搜尋不會傳回任何結果，請按一下查詢語言-國家/地區圖示。 ![查詢語言-內容搜尋中的國家/地區圖示](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) ，然後選取對應的語言國家地區文化代碼值進行搜尋。 預設的語言-國家/地區為中性。

**是否可以一次搜尋多種語言？**

這取決於您的搜尋案例。

- 當您在 Advanced eDiscovery 中[查詢審閱集合](review-set-search.md)中的資料時，您可以搜尋多種語言。

- 當您 [建立搜尋以收集資料](create-search-to-collect-data.md)時，請針對您所針對的每種語言建立不同的搜尋。 例如，如果您正在搜尋包含中文和韓文的檔，請選取 [中文] 做為第一個查詢，然後選取 [韓文] 做為第二個查詢。

**我沒有看到 [查詢語言-國家/地區] 圖示，以選取審閱集中的查詢語言。如何在複查集搜尋中指定查詢語言？**

若為複查集查詢，您不需要指定檔語言。 Advanced eDiscovery 會在您將內容新增至審閱集時，自動偵測檔語言。 這可協助您優化檢查集合中的查詢結果。

**我是否可以查看檔案 [中繼資料](view-documents-in-review-set.md#file-metadata)中偵測到的語言？**

否，您看不到檔案中繼資料中偵測到的語言。

**是否可以使用審閱集中的檔語言進行篩選**？

否，您無法在審閱集中篩選、排序或搜尋檔語言。

**此 CJK 發行的審閱集合案例會影響所有的現有搜尋和審閱集？**

否，您的現有搜尋和審閱集合都不會變更。 您不需要重新索引現有的資料，而且英文文字的搜尋結果會相同。

**我要如何將我的顯示語言變更為中文、日文或韓文？**

如需如何變更顯示語言和時區的詳細資訊，請參閱 how [to set Office 365 的語言和地區設定](/office365/troubleshoot/access-management/set-language-and-region)。

## <a name="known-issues"></a>已知問題

- OCR 不支援來自影像檔的 CJK 字元

- 電子郵件檔案 (例如 * .eml 和 * .msg) 中的 [ [批註] 視圖](view-documents-in-review-set.md#annotate-view) 不支援 CJK 語言。

- CJK 語言不支援 [文字視圖](view-documents-in-review-set.md#text-view) 中的搜尋順序醒目提示。

- 用於分析資料的 [相關性模組](using-relevance.md) 不支援 CJK 語言。

- CJK 語言不支援[查詢型保留](managing-holds.md#manage-non-custodial-holds)。