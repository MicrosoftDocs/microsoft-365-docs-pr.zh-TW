---
title: Microsoft 威脅防護中的高級搜尋查詢最佳作法
description: 瞭解如何使用高級搜尋來構建快速、有效率及無錯誤的威脅搜尋查詢
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema，kusto，避免超時，命令列，程式識別碼，優化，最佳作法，剖析，聯結，摘要
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: e3b29a8182e38fa05e5f791478157c978632fb13
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477002"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="026f1-104">進階搜捕查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="026f1-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="026f1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="026f1-105">**Applies to:**</span></span>
- <span data-ttu-id="026f1-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="026f1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="026f1-107">套用這些建議以快速取得結果，並避免執行複雜的查詢時發生超時。</span><span class="sxs-lookup"><span data-stu-id="026f1-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="026f1-108">如需提高查詢效能的更多指導方針，請參閱 [Kusto 查詢最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="026f1-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-limits"></a><span data-ttu-id="026f1-109">瞭解 CPU 資源限制</span><span class="sxs-lookup"><span data-stu-id="026f1-109">Understand CPU resource limits</span></span>
<span data-ttu-id="026f1-110">視其大小而定，每個租使用者都有權存取一組為執行高級搜尋查詢所指派的 CPU 資源量。</span><span class="sxs-lookup"><span data-stu-id="026f1-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="026f1-111">如需各種服務限制的詳細資訊，請 [閱讀相關的高級搜尋限制](advanced-hunting-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="026f1-111">For detailed information about various service limits, [read about advanced hunting limits](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="026f1-112">定期執行多個查詢的客戶應追蹤工作量，並套用本文中的優化指導，以將超出限制的中斷降至最低。</span><span class="sxs-lookup"><span data-stu-id="026f1-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding the limits.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="026f1-113">一般優化秘訣</span><span class="sxs-lookup"><span data-stu-id="026f1-113">General optimization tips</span></span>

- <span data-ttu-id="026f1-114">[**新增查詢大小**]：如果您懷疑查詢會傳回大型結果集，請先使用[count 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)來評估。</span><span class="sxs-lookup"><span data-stu-id="026f1-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="026f1-115">使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或其同義字 `take` 以避免大型結果集。</span><span class="sxs-lookup"><span data-stu-id="026f1-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="026f1-116">**及早套用篩選器**—套用時間篩選和其他篩選器，以減少資料集，尤其是在使用轉換和分析功能之前（如 [子字串 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)、 [取代 ( # B3 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)、 [trim ( # B5 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)、 [toupper ( # B7 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json ( # B9 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)）。</span><span class="sxs-lookup"><span data-stu-id="026f1-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="026f1-117">在下列範例中，會在篩選運算子減少記錄數目後，使用 [ ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) 的分析函數 extractjson。</span><span class="sxs-lookup"><span data-stu-id="026f1-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="026f1-118">**具有節拍**：若要避免在非必要字詞中搜尋子字串，請使用 `has` 運算子，而不要使用 `contains` 。</span><span class="sxs-lookup"><span data-stu-id="026f1-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="026f1-119">瞭解字串運算子</span><span class="sxs-lookup"><span data-stu-id="026f1-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="026f1-120">**在特定欄中查看**--查看特定欄，而不是在所有欄中執行完整的文字搜尋。</span><span class="sxs-lookup"><span data-stu-id="026f1-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="026f1-121">請勿使用 `*` 以檢查所有欄。</span><span class="sxs-lookup"><span data-stu-id="026f1-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="026f1-122">**以區分大小寫的速度**-區分大小寫的搜尋更為具體，而且通常更為具性能。</span><span class="sxs-lookup"><span data-stu-id="026f1-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="026f1-123">區分大小寫的 [字串運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)（例如 `has_cs` 和）的名稱 `contains_cs` 一般為 `_cs` 。</span><span class="sxs-lookup"><span data-stu-id="026f1-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="026f1-124">您也可以使用區分大小寫的 equals 運算子， `==` 而不要使用 `=~` 。</span><span class="sxs-lookup"><span data-stu-id="026f1-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="026f1-125">**剖析：請**盡可能使用 [parse 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 或類似 [parse_json ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)的分析函數。</span><span class="sxs-lookup"><span data-stu-id="026f1-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="026f1-126">避免 `matches regex` 使用正則運算式的字串運算子或 [析取 ( # A1 函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)。</span><span class="sxs-lookup"><span data-stu-id="026f1-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="026f1-127">保留使用正則運算式以取得更複雜的案例。</span><span class="sxs-lookup"><span data-stu-id="026f1-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="026f1-128">閱讀有關分析函數的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="026f1-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="026f1-129">**篩選資料表不是運算式**-如果您可以在資料表欄上篩選，請勿在計算欄上篩選。</span><span class="sxs-lookup"><span data-stu-id="026f1-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="026f1-130">**無三個字元的字詞**，避免使用包含三個字元或更少的字詞來比較或篩選。</span><span class="sxs-lookup"><span data-stu-id="026f1-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="026f1-131">這些字詞不會編制索引，而且符合這些字詞將需要更多資源。</span><span class="sxs-lookup"><span data-stu-id="026f1-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="026f1-132">**專案可選擇性地**透過只投影您所需的欄，使您的結果更容易理解。</span><span class="sxs-lookup"><span data-stu-id="026f1-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="026f1-133">在執行 [加入](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 或類似作業之前，先投射特定欄，也有助於提升效能。</span><span class="sxs-lookup"><span data-stu-id="026f1-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="026f1-134">優化 `join` 運算子</span><span class="sxs-lookup"><span data-stu-id="026f1-134">Optimize the `join` operator</span></span>
<span data-ttu-id="026f1-135">[Join 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)會透過比對指定的欄中的值，合併兩個數據表中的資料行。</span><span class="sxs-lookup"><span data-stu-id="026f1-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="026f1-136">套用這些秘訣以優化使用此操作符的查詢。</span><span class="sxs-lookup"><span data-stu-id="026f1-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="026f1-137">向**左縮小的表格**，運算子會將 `join` join 語句左邊表格中的記錄與右邊的記錄進行比較。</span><span class="sxs-lookup"><span data-stu-id="026f1-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="026f1-138">將較小的表格保留在左邊，必須符合較少的記錄，進而加速查詢。</span><span class="sxs-lookup"><span data-stu-id="026f1-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="026f1-139">在下表中，我們 `DeviceLogonEvents` 會在加入帳戶 sid 之前，先將左側表格縮小為只涵蓋三個特定裝置 `IdentityLogonEvents` 。</span><span class="sxs-lookup"><span data-stu-id="026f1-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- <span data-ttu-id="026f1-140">在將每個相符的列傳回給右表之前，**請先使用內部聯接**口味（預設的[join 口味](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)）及左表中的[innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)鍵 deduplicates 列。</span><span class="sxs-lookup"><span data-stu-id="026f1-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="026f1-141">如果左表的多個資料列的索引鍵具有相同的值 `join` ，這些資料列將會被重複的資料列，保留每個唯一值的單一隨機列。</span><span class="sxs-lookup"><span data-stu-id="026f1-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="026f1-142">此預設行為會從左資料表中留下重要資訊，可提供有用的洞察力。</span><span class="sxs-lookup"><span data-stu-id="026f1-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="026f1-143">例如，下列查詢只會顯示一個包含特定附件的電子郵件，即使該相同附件是使用多封電子郵件訊息傳送：</span><span class="sxs-lookup"><span data-stu-id="026f1-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="026f1-144">若要解決這項限制，我們會套用 [內部聯接](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 口味，其方式是指定 `kind=inner` [顯示左表格中的所有列的右側都有相符的值：</span><span class="sxs-lookup"><span data-stu-id="026f1-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="026f1-145">**從時間範圍加入記錄**：在調查安全性事件時，分析程式會尋找在相同時間週期內發生的相關事件。</span><span class="sxs-lookup"><span data-stu-id="026f1-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="026f1-146">使用相同的方法， `join` 也就是減少要檢查的記錄數目的效能的優點。</span><span class="sxs-lookup"><span data-stu-id="026f1-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="026f1-147">下列查詢會檢查在接收惡意檔30分鐘內的登入事件：</span><span class="sxs-lookup"><span data-stu-id="026f1-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="026f1-148">**在兩側套用時間篩選**-即使您不是在調查特定時間範圍，在左和右表上套用時間篩選也可以減少要檢查的記錄數目，並改善 `join` 效能。</span><span class="sxs-lookup"><span data-stu-id="026f1-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="026f1-149">下列查詢適用于 `Timestamp > ago(1h)` 這兩個數據表，只會從過去的小時加入記錄：</span><span class="sxs-lookup"><span data-stu-id="026f1-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="026f1-150">**使用提示效能**-在執行 `join` 大量佔用資源的作業時，以運算子搭配使用提示，以指示後端分配負載。</span><span class="sxs-lookup"><span data-stu-id="026f1-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="026f1-151">深入瞭解聯接提示</span><span class="sxs-lookup"><span data-stu-id="026f1-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="026f1-152">例如，當使用具有很高基數的索引鍵來聯接資料表時， **[無序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 會協助改善查詢效能（具有許多唯一值的索引鍵，如下表所示） `AccountObjectId` ：</span><span class="sxs-lookup"><span data-stu-id="026f1-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="026f1-153">當左表為小型 (至 100000) 記錄時， **[廣播提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 會有説明，而且右資料表非常大。</span><span class="sxs-lookup"><span data-stu-id="026f1-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="026f1-154">例如，下列查詢會嘗試加入少數幾封電子郵件，其中的特定 _主題包含_ 表格中的連結 `EmailUrlInfo` ：</span><span class="sxs-lookup"><span data-stu-id="026f1-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="026f1-155">優化 `summarize` 運算子</span><span class="sxs-lookup"><span data-stu-id="026f1-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="026f1-156">[匯總運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator)會匯總表格的內容。</span><span class="sxs-lookup"><span data-stu-id="026f1-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="026f1-157">套用這些秘訣以優化使用此操作符的查詢。</span><span class="sxs-lookup"><span data-stu-id="026f1-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="026f1-158">**尋找非重複的值**（一般 `summarize` 是用來尋找可以重複的非重複值）。</span><span class="sxs-lookup"><span data-stu-id="026f1-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="026f1-159">不需要使用它來匯總沒有重複值的資料行。</span><span class="sxs-lookup"><span data-stu-id="026f1-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="026f1-160">雖然單一電子郵件可以是多個事件的一部分，但以下範例 _不_ 是有效使用， `summarize` 因為個別電子郵件的網路郵件識別碼總會附帶唯一的寄件者位址。</span><span class="sxs-lookup"><span data-stu-id="026f1-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="026f1-161">`summarize`操作員可輕鬆取代 `project` ，在消耗較少的資源時產生的結果可能相同：</span><span class="sxs-lookup"><span data-stu-id="026f1-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="026f1-162">下列範例會更有效率地使用， `summarize` 因為寄件者位址可以有多個不同的實例，將電子郵件傳送至相同的收件者位址。</span><span class="sxs-lookup"><span data-stu-id="026f1-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="026f1-163">這類組合不太明顯，而且可能有重複專案。</span><span class="sxs-lookup"><span data-stu-id="026f1-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="026f1-164">**無序處理查詢**--當 `summarize` 資料行中的最大值是重複值時，相同的資料列也可以具有 _高基數_ 或大量的唯一值。</span><span class="sxs-lookup"><span data-stu-id="026f1-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="026f1-165">如同 `join` 運算子，您也可以在使用具有高基數的資料行上作業時，套用 [無序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) ，以 `summarize` 散佈處理負載，並可能提升效能。</span><span class="sxs-lookup"><span data-stu-id="026f1-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="026f1-166">下列查詢可用於 `summarize` 計算非重複的收件者電子郵件地址，其可在大型組織的成百上千中執行。</span><span class="sxs-lookup"><span data-stu-id="026f1-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="026f1-167">為了改善效能，它包含 `hint.shufflekey` ：</span><span class="sxs-lookup"><span data-stu-id="026f1-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="026f1-168">查詢案例</span><span class="sxs-lookup"><span data-stu-id="026f1-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="026f1-169">使用處理 IDs 識別唯一的程式</span><span class="sxs-lookup"><span data-stu-id="026f1-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="026f1-170">程序識別碼 (PID) 會在 Windows 中回收，並針對新程序重複使用。</span><span class="sxs-lookup"><span data-stu-id="026f1-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="026f1-171">它們本身不能充當特定程序的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="026f1-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="026f1-172">若要為特定電腦上的程序取得唯一識別碼，請使用程序識別碼與程序建立時間。</span><span class="sxs-lookup"><span data-stu-id="026f1-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="026f1-173">結合或摘要處理程序中的資料時，需包含電腦識別碼的欄位 (`DeviceId` 或 `DeviceName`)、程序識別碼 (`ProcessId` 或 `InitiatingProcessId`) 以及程序建立時間 (`ProcessCreationTime` 或 `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="026f1-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="026f1-174">下列範例查詢發現透過連接埠 445 (SMB) 存取 10 個以上 IP 位址的程序，可能是因為掃描檔案共用。</span><span class="sxs-lookup"><span data-stu-id="026f1-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="026f1-175">例如查詢：</span><span class="sxs-lookup"><span data-stu-id="026f1-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="026f1-176">查詢會以 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 進行彙總，因此它會檢查單一程序，而不會將多個具有相同程序識別碼的程序混合在一起。</span><span class="sxs-lookup"><span data-stu-id="026f1-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="026f1-177">查詢命令列</span><span class="sxs-lookup"><span data-stu-id="026f1-177">Query command lines</span></span>
<span data-ttu-id="026f1-178">有許多方法可以建構命令列來完成工作。</span><span class="sxs-lookup"><span data-stu-id="026f1-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="026f1-179">例如，攻擊者可以參考沒有路徑、沒有副檔名、使用環境變數或引號的映射檔。</span><span class="sxs-lookup"><span data-stu-id="026f1-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="026f1-180">攻擊者也可以變更參數的順序，或新增多個引號及空格。</span><span class="sxs-lookup"><span data-stu-id="026f1-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="026f1-181">若要在命令列上建立更耐用的查詢，請套用下列做法：</span><span class="sxs-lookup"><span data-stu-id="026f1-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="026f1-182">透過比對的檔案名欄位，而不是在命令列本身上進行篩選，來識別已知的處理常式 (例如 *net.exe* 或 *psexec.exe*) 。</span><span class="sxs-lookup"><span data-stu-id="026f1-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="026f1-183">使用[parse_command_line ( # A1 函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)來分析命令列區段</span><span class="sxs-lookup"><span data-stu-id="026f1-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="026f1-184">查詢命令列引數時，請勿以特定順序尋找多個不相關引數上完全相符的內容。</span><span class="sxs-lookup"><span data-stu-id="026f1-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="026f1-185">請改用規則運算式或使用多個不同的包含運算子。</span><span class="sxs-lookup"><span data-stu-id="026f1-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="026f1-186">使用不區分大小寫對比。</span><span class="sxs-lookup"><span data-stu-id="026f1-186">Use case insensitive matches.</span></span> <span data-ttu-id="026f1-187">例如，使用 `=~` 、 `in~` 和， `contains` 而不是 `==` 、 `in` 和 `contains_cs` 。</span><span class="sxs-lookup"><span data-stu-id="026f1-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="026f1-188">若要緩解命令列混淆技術，請考慮移除引號、將逗號取代為空格，並以單一空格取代多個連續空格。</span><span class="sxs-lookup"><span data-stu-id="026f1-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="026f1-189">有些複雜的混淆技術需要其他方法，但這些調整功能可協助您解決常見的方法。</span><span class="sxs-lookup"><span data-stu-id="026f1-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="026f1-190">下列範例會示範各種構造查詢的方式，用來尋找檔案 *net.exe* 停止防火牆服務「MpsSvc」：</span><span class="sxs-lookup"><span data-stu-id="026f1-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="026f1-191">從外部來源插入資料</span><span class="sxs-lookup"><span data-stu-id="026f1-191">Ingest data from external sources</span></span>
<span data-ttu-id="026f1-192">若要將長清單或大型資料表納入查詢中，請使用 [externaldata 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 從指定的 URI 中攝取資料。</span><span class="sxs-lookup"><span data-stu-id="026f1-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="026f1-193">您可以從 TXT、CSV、JSON 或 [其他格式](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)的檔案中取得資料。</span><span class="sxs-lookup"><span data-stu-id="026f1-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="026f1-194">下列範例顯示如何利用 MalwareBazaar (abuse.ch) 所提供的大量惡意程式碼 SHA-256 雜湊，以檢查電子郵件上的附件：</span><span class="sxs-lookup"><span data-stu-id="026f1-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a><span data-ttu-id="026f1-195">剖析字串</span><span class="sxs-lookup"><span data-stu-id="026f1-195">Parse strings</span></span>
<span data-ttu-id="026f1-196">您可以使用各種功能來有效處理需要剖析或轉換的字串。</span><span class="sxs-lookup"><span data-stu-id="026f1-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="026f1-197">字串</span><span class="sxs-lookup"><span data-stu-id="026f1-197">String</span></span> | <span data-ttu-id="026f1-198">函數</span><span class="sxs-lookup"><span data-stu-id="026f1-198">Function</span></span> | <span data-ttu-id="026f1-199">使用範例</span><span class="sxs-lookup"><span data-stu-id="026f1-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="026f1-200">命令列</span><span class="sxs-lookup"><span data-stu-id="026f1-200">Command-lines</span></span> | [<span data-ttu-id="026f1-201">parse_command_line ( # B1 </span><span class="sxs-lookup"><span data-stu-id="026f1-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="026f1-202">解壓縮命令及所有引數。</span><span class="sxs-lookup"><span data-stu-id="026f1-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="026f1-203">Paths</span><span class="sxs-lookup"><span data-stu-id="026f1-203">Paths</span></span> | [<span data-ttu-id="026f1-204">parse_path ( # B1 </span><span class="sxs-lookup"><span data-stu-id="026f1-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="026f1-205">解壓縮檔的區段或資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="026f1-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="026f1-206">版本號碼</span><span class="sxs-lookup"><span data-stu-id="026f1-206">Version numbers</span></span> | [<span data-ttu-id="026f1-207">parse_version ( # B1 </span><span class="sxs-lookup"><span data-stu-id="026f1-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="026f1-208">Deconstruct 最多四個區段的版本號碼，且每個區段最多可有八個字元。</span><span class="sxs-lookup"><span data-stu-id="026f1-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="026f1-209">使用已分析的資料來比較版本時期。</span><span class="sxs-lookup"><span data-stu-id="026f1-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="026f1-210">IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="026f1-210">IPv4 addresses</span></span> | [<span data-ttu-id="026f1-211">parse_ipv4 ( # B1 </span><span class="sxs-lookup"><span data-stu-id="026f1-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="026f1-212">將 IPv4 位址轉換成長整數。</span><span class="sxs-lookup"><span data-stu-id="026f1-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="026f1-213">若要比較 IPv4 位址但未轉換，請使用 [ipv4_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="026f1-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="026f1-214">IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="026f1-214">IPv6 addresses</span></span> | [<span data-ttu-id="026f1-215">parse_ipv6 ( # B1 </span><span class="sxs-lookup"><span data-stu-id="026f1-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="026f1-216">將 IPv4 或 IPv6 位址轉換為正常化 IPv6 標記法。</span><span class="sxs-lookup"><span data-stu-id="026f1-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="026f1-217">若要比較 IPv6 位址，請使用 [ipv6_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="026f1-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="026f1-218">若要瞭解所有支援的分析功能，請 [閱讀 Kusto 字串函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。</span><span class="sxs-lookup"><span data-stu-id="026f1-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="026f1-219">相關主題</span><span class="sxs-lookup"><span data-stu-id="026f1-219">Related topics</span></span>
- [<span data-ttu-id="026f1-220">Kusto 查詢語言檔</span><span class="sxs-lookup"><span data-stu-id="026f1-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="026f1-221">服務限制</span><span class="sxs-lookup"><span data-stu-id="026f1-221">Service limits</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="026f1-222">處理高級搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="026f1-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="026f1-223">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="026f1-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="026f1-224">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="026f1-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
