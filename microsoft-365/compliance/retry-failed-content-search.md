---
title: 重試內容搜尋以解決內容位置錯誤
f1.keywords:
- NOCSH
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
description: 在調查過程中，您可以使用 [重試] 按鈕來解析內容位置發生錯誤的內容搜尋。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 55ef7ff59bfc58809d0e00ff1f2edf7a8455ba13
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527631"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="fd379-103">重試內容搜尋以解決內容位置錯誤</span><span class="sxs-lookup"><span data-stu-id="fd379-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="fd379-104">當您在安全性與合規性中心使用內容搜尋來搜尋大量信箱時，可能會收到與錯誤類似的搜尋錯誤：</span><span class="sxs-lookup"><span data-stu-id="fd379-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="fd379-105">這些錯誤（錯誤碼為 CS001-002，CS003-002，CS008-009，CS012-002，及其他格式 CS0XX-0XX）表示內容搜尋無法搜尋特定的內容位置;在此範例中，未搜尋兩個信箱。</span><span class="sxs-lookup"><span data-stu-id="fd379-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="fd379-106">這些錯誤會顯示在內容搜尋的 [狀態詳細資料浮出] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="fd379-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="fd379-107">內容位置錯誤的原因</span><span class="sxs-lookup"><span data-stu-id="fd379-107">Cause of content location errors</span></span>

<span data-ttu-id="fd379-108">搜尋大量信箱時，搜尋會在 Microsoft 資料中心的數千部伺服器間散佈。</span><span class="sxs-lookup"><span data-stu-id="fd379-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="fd379-109">在任何時候，特定伺服器都可能是在重新開機狀態，或在容錯移轉至多餘副本的程式中。</span><span class="sxs-lookup"><span data-stu-id="fd379-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="fd379-110">在這兩種情況下，內容搜尋要求取得的資料將會超時。在上一個範例中，失敗的信箱錯誤是搜尋超時的結果。</span><span class="sxs-lookup"><span data-stu-id="fd379-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="fd379-111">解決內容位置錯誤</span><span class="sxs-lookup"><span data-stu-id="fd379-111">Resolving content location errors</span></span>

<span data-ttu-id="fd379-112">重新開機搜尋通常會在不同的伺服器上導致類似的錯誤。</span><span class="sxs-lookup"><span data-stu-id="fd379-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="fd379-113">若不重新開機搜尋，請按一下顯示在搜尋結果頁面頂端的 [**重試**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="fd379-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![按一下 [重試] 按鈕以解決內容位置錯誤](../media/retrycontentsearch3.png)

<span data-ttu-id="fd379-115">這會導致僅對失敗的信箱重試搜尋。</span><span class="sxs-lookup"><span data-stu-id="fd379-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="fd379-116">當您重試搜尋時，會保留已成功傳回的其他結果。</span><span class="sxs-lookup"><span data-stu-id="fd379-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="fd379-117">避免內容位置錯誤的秘訣</span><span class="sxs-lookup"><span data-stu-id="fd379-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="fd379-118">以下是內容位置錯誤的一些額外原因，以及協助您在搜尋大量信箱時避免出現問題的一些秘訣。</span><span class="sxs-lookup"><span data-stu-id="fd379-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="fd379-119">正在搜尋的信箱可能由於使用者活動而忙碌。</span><span class="sxs-lookup"><span data-stu-id="fd379-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="fd379-120">在此情況下，搜尋服務可能會節流自身，以防止信箱變得無法使用。</span><span class="sxs-lookup"><span data-stu-id="fd379-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="fd379-121">若要避免這種情況，請試著在非上班時間執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="fd379-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="fd379-122">搜尋查詢可能會從信箱中檢索太多的內容。</span><span class="sxs-lookup"><span data-stu-id="fd379-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="fd379-123">如果可能的話，請嘗試使用關鍵字、日期範圍和搜尋條件來縮小搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="fd379-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="fd379-124">使用[關鍵字清單](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)建立搜尋查詢時，關鍵字或關鍵字片語太多。</span><span class="sxs-lookup"><span data-stu-id="fd379-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="fd379-125">當您執行使用關鍵字清單的搜尋查詢時，此服務實質上會針對關鍵字清單中的每一列執行個別的搜尋，以產生統計資料。</span><span class="sxs-lookup"><span data-stu-id="fd379-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="fd379-126">如果您是在搜尋查詢中使用關鍵字清單，請將關鍵字清單中的列數減至最少，或是將數位關鍵字分割成較小的清單，並為每個關鍵字清單建立不同的搜尋。</span><span class="sxs-lookup"><span data-stu-id="fd379-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd379-127">為了避免大型關鍵字清單所造成的問題，您目前限制在搜尋查詢的關鍵字清單中，最多可有20列。</span><span class="sxs-lookup"><span data-stu-id="fd379-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="fd379-128">在相同的信箱上同時執行太多搜尋。</span><span class="sxs-lookup"><span data-stu-id="fd379-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="fd379-129">如果可能的話，請嘗試一次在任何一個信箱上執行一個搜尋。</span><span class="sxs-lookup"><span data-stu-id="fd379-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="fd379-130">搜尋單一搜尋中的信箱太多。</span><span class="sxs-lookup"><span data-stu-id="fd379-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="fd379-131">搜尋大量信箱時，內容位置錯誤的發生幾率會增加。</span><span class="sxs-lookup"><span data-stu-id="fd379-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="fd379-132">如果可能的話，請嘗試執行多個搜尋，讓每個搜尋都包含您組織中的信箱子集。</span><span class="sxs-lookup"><span data-stu-id="fd379-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="fd379-133">在信箱上執行必要的維護。</span><span class="sxs-lookup"><span data-stu-id="fd379-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="fd379-134">雖然這種原因很少發生，請稍候片刻後再收到內容位置錯誤，然後再試一次搜尋。</span><span class="sxs-lookup"><span data-stu-id="fd379-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
