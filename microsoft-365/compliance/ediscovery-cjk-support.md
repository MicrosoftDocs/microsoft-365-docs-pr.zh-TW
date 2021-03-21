---
title: 針對高級電子檔探索的 CJK/Double Byte 支援
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
description: 瞭解 Microsoft 365 中的「高級 eDiscovery」如何支援中文、日文和韓文 (CJK) 語言，使用雙位元組字元集。
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926599"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="0b970-103">適用于 Advanced eDiscovery 的 CJK 語言支援</span><span class="sxs-lookup"><span data-stu-id="0b970-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="0b970-104">Advanced eDiscovery 支援雙位元組字元集語言 (包括簡化的中文、繁體中文、日文和韓文，這兩種是在審校集中稱為下列高級案例的 *CJK* 語言) ：</span><span class="sxs-lookup"><span data-stu-id="0b970-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="0b970-105">當您 [查詢審閱集中的資料](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="0b970-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="0b970-106">當您 [為審閱集中的檔標記](tagging-documents.md)時。</span><span class="sxs-lookup"><span data-stu-id="0b970-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="0b970-107">當您使用近乎重複偵測、電子郵件執行緒及主題分析來 [分析檢查集合中的案例資料](analyzing-data-in-review-set.md) 時。</span><span class="sxs-lookup"><span data-stu-id="0b970-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="0b970-108">常見問題集</span><span class="sxs-lookup"><span data-stu-id="0b970-108">Frequently asked questions</span></span>

<span data-ttu-id="0b970-109">**如何建立搜尋來收集包含 CJK 字元的專案？**</span><span class="sxs-lookup"><span data-stu-id="0b970-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="0b970-110">在高級 eDiscovery 中搜尋內容時，您可以使用 CJK 字元做為 [關鍵字搜尋](building-search-queries.md#keyword-searches)、 [關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md) 。</span><span class="sxs-lookup"><span data-stu-id="0b970-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="0b970-111">在核心 eDiscovery 和內容搜尋中搜尋內容時，也支援搜尋 CJK 字元。</span><span class="sxs-lookup"><span data-stu-id="0b970-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="0b970-112">我們為所有 [搜尋運算子](keyword-queries-and-search-conditions.md#search-operators) 和 [搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)提供 CJK 支援，包括 boolean 運算子 **和**、 **或**、 **NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="0b970-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="0b970-113">如果您確定內容位置或專案包含 CJK 字元，但是搜尋不會傳回任何結果，請按一下查詢語言-國家/地區圖示。</span><span class="sxs-lookup"><span data-stu-id="0b970-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![查詢語言-內容搜尋中的國家/地區圖示](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="0b970-115">，然後選取對應的語言國家地區文化代碼值進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="0b970-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="0b970-116">預設的語言-國家/地區為中性。</span><span class="sxs-lookup"><span data-stu-id="0b970-116">The default language/region is neutral.</span></span>

<span data-ttu-id="0b970-117">**是否可以一次搜尋多種語言？**</span><span class="sxs-lookup"><span data-stu-id="0b970-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="0b970-118">這取決於您的搜尋案例。</span><span class="sxs-lookup"><span data-stu-id="0b970-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="0b970-119">當您在 [Advanced eDiscovery] 中 [查詢複查集中的資料](review-set-search.md) 時，您可以搜尋多種語言。</span><span class="sxs-lookup"><span data-stu-id="0b970-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="0b970-120">當您 [建立搜尋以收集資料](create-search-to-collect-data.md)時，請針對您所針對的每種語言建立不同的搜尋。</span><span class="sxs-lookup"><span data-stu-id="0b970-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="0b970-121">例如，如果您正在搜尋包含中文和韓文的檔，請選取 [中文] 做為第一個查詢，然後選取 [韓文] 做為第二個查詢。</span><span class="sxs-lookup"><span data-stu-id="0b970-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="0b970-122">**我沒有看到 [查詢語言-國家/地區] 圖示，以選取審閱集中的查詢語言。如何在複查集搜尋中指定查詢語言？**</span><span class="sxs-lookup"><span data-stu-id="0b970-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="0b970-123">若為複查集查詢，您不需要指定檔語言。</span><span class="sxs-lookup"><span data-stu-id="0b970-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="0b970-124">當您將內容新增至審閱集時，「高級 eDiscovery」會自動偵測檔語言。</span><span class="sxs-lookup"><span data-stu-id="0b970-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="0b970-125">這可協助您優化檢查集合中的查詢結果。</span><span class="sxs-lookup"><span data-stu-id="0b970-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="0b970-126">**我是否可以查看檔案 [中繼資料](view-documents-in-review-set.md#file-metadata)中偵測到的語言？**</span><span class="sxs-lookup"><span data-stu-id="0b970-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="0b970-127">否，您看不到檔案中繼資料中偵測到的語言。</span><span class="sxs-lookup"><span data-stu-id="0b970-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="0b970-128">**是否可以使用審閱集中的檔語言進行篩選**？</span><span class="sxs-lookup"><span data-stu-id="0b970-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="0b970-129">否，您無法在審閱集中篩選、排序或搜尋檔語言。</span><span class="sxs-lookup"><span data-stu-id="0b970-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="0b970-130">**此 CJK 發行的審閱集合案例會影響所有的現有搜尋和審閱集？**</span><span class="sxs-lookup"><span data-stu-id="0b970-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="0b970-131">否，您的現有搜尋和審閱集合都不會變更。</span><span class="sxs-lookup"><span data-stu-id="0b970-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="0b970-132">您不需要重新索引現有的資料，而且英文文字的搜尋結果會相同。</span><span class="sxs-lookup"><span data-stu-id="0b970-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="0b970-133">**我要如何將我的顯示語言變更為中文、日文或韓文？**</span><span class="sxs-lookup"><span data-stu-id="0b970-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="0b970-134">如需如何變更顯示語言和時區的詳細資訊，請參閱 how [to 設定 Office 365 的語言和地區設定](/office365/troubleshoot/access-management/set-language-and-region)。</span><span class="sxs-lookup"><span data-stu-id="0b970-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="0b970-135">已知問題</span><span class="sxs-lookup"><span data-stu-id="0b970-135">Known issues</span></span>

- <span data-ttu-id="0b970-136">OCR 不支援來自影像檔的 CJK 字元</span><span class="sxs-lookup"><span data-stu-id="0b970-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="0b970-137">電子郵件檔案 (例如 \* .eml 和 \* .msg) 中的 [ [批註] 視圖](view-documents-in-review-set.md#annotate-view) 不支援 CJK 語言。</span><span class="sxs-lookup"><span data-stu-id="0b970-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="0b970-138">CJK 語言不支援 [文字視圖](view-documents-in-review-set.md#text-view) 中的搜尋順序醒目提示。</span><span class="sxs-lookup"><span data-stu-id="0b970-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="0b970-139">用於分析資料的 [相關性模組](using-relevance.md) 不支援 CJK 語言。</span><span class="sxs-lookup"><span data-stu-id="0b970-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="0b970-140">CJK 語言不支援[查詢型保留](managing-holds.md#manage-non-custodial-holds)。</span><span class="sxs-lookup"><span data-stu-id="0b970-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>