---
title: 再試一次 「 內容搜尋 」 來解決錯誤的內容位置
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 用於解決有內容位置錯誤的內容搜尋中的 [重試] 按鈕。
ms.openlocfilehash: 91c656a05111391ad93e03946cf367133f2c25a2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078174"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="e385b-103">再試一次 「 內容搜尋 」 來解決錯誤的內容位置</span><span class="sxs-lookup"><span data-stu-id="e385b-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="e385b-104">當您在安全性與合規性中心中使用內容搜尋來搜尋大量的信箱時，您可能會收到類似下列的搜尋錯誤：</span><span class="sxs-lookup"><span data-stu-id="e385b-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the following:</span></span>

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="e385b-105">這些錯誤 （錯誤代碼的 CS001-002、 CS003-002、 CS008 009、 CS012-002 和其他錯誤的表單 CS0XX 0XX） 表示內容搜尋來搜尋特定的內容位置; 已經失敗在這個範例中，沒有搜尋兩個信箱。</span><span class="sxs-lookup"><span data-stu-id="e385b-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="e385b-106">內容搜尋的彈出式視窗狀態的詳細資訊] 頁面上會顯示這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="e385b-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="e385b-107">內容位置錯誤的原因</span><span class="sxs-lookup"><span data-stu-id="e385b-107">Cause of content location errors</span></span>

<span data-ttu-id="e385b-108">當您搜尋大量的信箱，搜尋會分配到千分位 Microsoft 資料中心中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e385b-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="e385b-109">在任何時候，特定伺服器可能是在重新開機狀態或容錯移轉備援副本的過程中。</span><span class="sxs-lookup"><span data-stu-id="e385b-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="e385b-110">在這些情況下，以擷取資料的內容搜尋的要求會逾時。</span><span class="sxs-lookup"><span data-stu-id="e385b-110">In either of these cases, the Content Search's request to retrieve data will timeout.</span></span> <span data-ttu-id="e385b-111">在前一個範例中，錯誤為失敗的信箱已搜尋逾時的結果。</span><span class="sxs-lookup"><span data-stu-id="e385b-111">In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="e385b-112">解決內容位置錯誤</span><span class="sxs-lookup"><span data-stu-id="e385b-112">Resolving content location errors</span></span>

<span data-ttu-id="e385b-113">重新啟動搜尋會通常會導致在不同伺服器上類似的錯誤。</span><span class="sxs-lookup"><span data-stu-id="e385b-113">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="e385b-114">而不是重新啟動搜尋時，按一下 [搜尋結果頁面頂端會顯示 [**重試**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e385b-114">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![按一下 [重試] 按鈕，以解決內容位置錯誤](media/retrycontentsearch3.png)

<span data-ttu-id="e385b-116">這會導致重試一次僅針對失敗的信箱搜尋。</span><span class="sxs-lookup"><span data-stu-id="e385b-116">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="e385b-117">當您再試一次搜尋時，會保留已成功傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="e385b-117">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="e385b-118">若要避免內容位置錯誤的祕訣</span><span class="sxs-lookup"><span data-stu-id="e385b-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="e385b-119">以下是一些加法原因的內容位置錯誤和的一些秘訣可協助您避免它們搜尋大量信箱時。</span><span class="sxs-lookup"><span data-stu-id="e385b-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="e385b-120">要搜尋的信箱可能會因為使用者活動忙碌中。</span><span class="sxs-lookup"><span data-stu-id="e385b-120">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="e385b-121">在此情況下，搜尋服務可能節流可防止信箱變成無法使用本身擷取。</span><span class="sxs-lookup"><span data-stu-id="e385b-121">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="e385b-122">若要避免此問題，請嘗試執行搜尋期間非上班時間。</span><span class="sxs-lookup"><span data-stu-id="e385b-122">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="e385b-123">搜尋查詢可能會從信箱正在擷取太多內容。</span><span class="sxs-lookup"><span data-stu-id="e385b-123">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="e385b-124">如果可能的話，請試著使用關鍵字、 日期範圍和搜尋條件縮小搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="e385b-124">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="e385b-125">太多的關鍵字或當您建立搜尋查詢中使用[關鍵字] 清單中](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)的關鍵字片語。</span><span class="sxs-lookup"><span data-stu-id="e385b-125">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="e385b-126">當您執行搜尋查詢使用關鍵字] 清單中時，基本上執行服務的每一列的個別搜尋關鍵字] 清單中，因此可以產生統計資料。</span><span class="sxs-lookup"><span data-stu-id="e385b-126">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="e385b-127">如果您在搜尋查詢中使用關鍵字] 清單中，最小化的關鍵字清單中的列數或分成較小的清單中的數字的關鍵字，建立不同的搜尋，為每個關鍵字清單。</span><span class="sxs-lookup"><span data-stu-id="e385b-127">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e385b-128">若要協助減少大型關鍵字清單所導致的問題，您現在有限的最大值為 20 列在 [關鍵字] 清單中的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="e385b-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="e385b-129">正在同時執行太多的搜尋在同一個信箱。</span><span class="sxs-lookup"><span data-stu-id="e385b-129">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="e385b-130">如果可能，請嘗試在任何一個信箱上一次執行一個搜尋。</span><span class="sxs-lookup"><span data-stu-id="e385b-130">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="e385b-131">在單一搜尋中搜尋太多的信箱。</span><span class="sxs-lookup"><span data-stu-id="e385b-131">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="e385b-132">搜尋非常大量的信箱時，會增加的內容位置錯誤的機率。</span><span class="sxs-lookup"><span data-stu-id="e385b-132">The probability of content location errors increases when searching a very large number of mailboxes.</span></span> <span data-ttu-id="e385b-133">如果可能，請嘗試執行多個搜尋，使每個搜尋組織中包含信箱的子集。</span><span class="sxs-lookup"><span data-stu-id="e385b-133">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="e385b-134">在信箱上正在執行必要的維護。</span><span class="sxs-lookup"><span data-stu-id="e385b-134">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="e385b-135">雖然此原因可能很少發生，有點等候時收到之後的內容位置錯誤，然後再重試搜尋。</span><span class="sxs-lookup"><span data-stu-id="e385b-135">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
