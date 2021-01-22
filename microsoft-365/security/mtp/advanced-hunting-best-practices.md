---
title: Microsoft 365 Defender 中的進位搜尋查詢最佳做法
description: 瞭解如何建構快速、有效率且無錯誤的威脅搜尋查詢，並用於進位搜尋
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構、kusto、避免超時、命令列、程式識別碼、優化、最佳做法、剖析、聯結、摘要
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928471"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="dae3e-104">進階搜捕查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="dae3e-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dae3e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="dae3e-105">**Applies to:**</span></span>
- <span data-ttu-id="dae3e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dae3e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dae3e-107">請執行這些建議以更快獲得結果，並避免執行複雜查詢時執行超時。</span><span class="sxs-lookup"><span data-stu-id="dae3e-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="dae3e-108">如需提高查詢效能的更多指導方針，請參閱 [Kusto 查詢最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="dae3e-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="dae3e-109">瞭解 CPU 資源配額</span><span class="sxs-lookup"><span data-stu-id="dae3e-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="dae3e-110">根據租使用者的大小，每個租使用者可以存取配置給執行進位搜尋查詢的一組 CPU 資源。</span><span class="sxs-lookup"><span data-stu-id="dae3e-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="dae3e-111">有關各種服務限制的詳細資訊， [請參閱進位搜尋配額及使用參數](advanced-hunting-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="dae3e-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="dae3e-112">定期執行多個查詢的客戶應追蹤使用狀況，並運用本文中的優化指引，將超出配額或使用量參數所產生的干擾降至最低。</span><span class="sxs-lookup"><span data-stu-id="dae3e-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="dae3e-113">一般優化秘訣</span><span class="sxs-lookup"><span data-stu-id="dae3e-113">General optimization tips</span></span>

- <span data-ttu-id="dae3e-114">**調整新查詢的大小**— 如果您懷疑查詢會回回大型結果集，首先使用計數運算子 [進行評估](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)。</span><span class="sxs-lookup"><span data-stu-id="dae3e-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="dae3e-115">使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或其同名避免 `take` 產生大型結果集。</span><span class="sxs-lookup"><span data-stu-id="dae3e-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="dae3e-116">提早 **套** 用篩選 -套用時間篩選及其他篩選，以減少資料集，尤其是在使用轉換及剖析函數 #B0 例如子字串 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)取代 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)修剪 [ () 、toupper](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction) [ ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json () 之前 #C3。](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)</span><span class="sxs-lookup"><span data-stu-id="dae3e-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="dae3e-117">在下列範例中，當篩選運算子減少記錄數目之後，會使用剖析函數解壓縮 ( [) 。](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction)</span><span class="sxs-lookup"><span data-stu-id="dae3e-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="dae3e-118">**包含 -** 若要避免不必要地搜尋字詞內的子字串，請使用 `has` 運算子，而不要 `contains` 。</span><span class="sxs-lookup"><span data-stu-id="dae3e-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="dae3e-119">瞭解字串運算子</span><span class="sxs-lookup"><span data-stu-id="dae3e-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="dae3e-120">**查看特定欄**—查看特定欄，而不是在所有資料行中執行完整文字搜尋。</span><span class="sxs-lookup"><span data-stu-id="dae3e-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="dae3e-121">不檢查 `*` 所有欄。</span><span class="sxs-lookup"><span data-stu-id="dae3e-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="dae3e-122">**針對速度區分大小寫**- 區分大小寫的搜尋更特定且通常更具有執行性。</span><span class="sxs-lookup"><span data-stu-id="dae3e-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="dae3e-123">區分大小寫的字串 [運算子名稱](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)，例如 `has_cs` and `contains_cs` ，通常以 `_cs` .</span><span class="sxs-lookup"><span data-stu-id="dae3e-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="dae3e-124">您也可以使用區分大小寫的等號運算子來 `==` 取代 `=~` 。</span><span class="sxs-lookup"><span data-stu-id="dae3e-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="dae3e-125">**剖析#B0** 請勿解壓縮 #C1—[](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator)盡可能使用剖析運算子或剖析函數 #B2 例如 [parse_json ( #C3。](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)</span><span class="sxs-lookup"><span data-stu-id="dae3e-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="dae3e-126">避免 `matches regex` 使用字串運算子或 [解壓縮 () 函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)，這兩者都是使用正則運算式。</span><span class="sxs-lookup"><span data-stu-id="dae3e-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="dae3e-127">針對更複雜的情況，請保留使用正則運算式。</span><span class="sxs-lookup"><span data-stu-id="dae3e-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="dae3e-128">瞭解更多關於剖析函數</span><span class="sxs-lookup"><span data-stu-id="dae3e-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="dae3e-129">**篩選表格而不是運算式**—如果可以篩選資料表資料行，就不要篩選計算結果欄。</span><span class="sxs-lookup"><span data-stu-id="dae3e-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="dae3e-130">**無三個字元的字詞**- 請避免使用三個字元以下的字詞來比較或篩選。</span><span class="sxs-lookup"><span data-stu-id="dae3e-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="dae3e-131">這些詞彙未編制索引，因此必須比對更多資源。</span><span class="sxs-lookup"><span data-stu-id="dae3e-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="dae3e-132">**選擇性 Project**- 只預測您需要的欄，讓結果更容易理解。</span><span class="sxs-lookup"><span data-stu-id="dae3e-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="dae3e-133">在執行聯集 [或類似作業](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 前先預測特定資料行，也可協助改善績效。</span><span class="sxs-lookup"><span data-stu-id="dae3e-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="dae3e-134">優化 `join` 運算子</span><span class="sxs-lookup"><span data-stu-id="dae3e-134">Optimize the `join` operator</span></span>
<span data-ttu-id="dae3e-135">聯 [集運算子會](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 比對指定資料行中的值，以合併兩個數據表中的資料列。</span><span class="sxs-lookup"><span data-stu-id="dae3e-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="dae3e-136">請使用這些秘訣來優化使用這個運算子的查詢。</span><span class="sxs-lookup"><span data-stu-id="dae3e-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="dae3e-137">**左方較小的資料表**—運算子將連接語句左側資料表中的記錄與 `join` 右邊的記錄進行比對。</span><span class="sxs-lookup"><span data-stu-id="dae3e-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="dae3e-138">左側有較小的資料表後，需要比對的記錄就會變少，因而能加快查詢的速度。</span><span class="sxs-lookup"><span data-stu-id="dae3e-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="dae3e-139">在下表中，我們先將左側表格縮小為只涵蓋三部特定裝置，然後再使用帳戶 `DeviceLogonEvents` `IdentityLogonEvents` SIDs 加入左側資料表。</span><span class="sxs-lookup"><span data-stu-id="dae3e-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="dae3e-140">使用內部聯集型 **：預設** 連接 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)詞型或 [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows by join key to the join key for each match to right table.</span><span class="sxs-lookup"><span data-stu-id="dae3e-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="dae3e-141">如果左側資料表有多個資料列的索引鍵值相同，這些列將會重復資料，以針對每個唯一值保留單一 `join` 隨機列。</span><span class="sxs-lookup"><span data-stu-id="dae3e-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="dae3e-142">此預設行為會從左側資料表中排除重要資訊，以提供有用的深入見解。</span><span class="sxs-lookup"><span data-stu-id="dae3e-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="dae3e-143">例如，以下查詢只會顯示一封包含特定附件的電子郵件，即使該相同附件是使用多封電子郵件訊息送出：</span><span class="sxs-lookup"><span data-stu-id="dae3e-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="dae3e-144">若要解決這項限制，我們套用[](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)內部聯集型，指定在左側資料表中顯示所有列，並向右顯示 `kind=inner` 符合的值：</span><span class="sxs-lookup"><span data-stu-id="dae3e-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="dae3e-145">**從時間視窗加入記錄**- 在調查安全性事件時，分析師會尋找同一時段內發生的相關事件。</span><span class="sxs-lookup"><span data-stu-id="dae3e-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="dae3e-146">使用相同方法也可減少要檢查的記錄數目，以提升 `join` 效果。</span><span class="sxs-lookup"><span data-stu-id="dae3e-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="dae3e-147">以下查詢會檢查在收到惡意檔案的 30 分鐘內是否發生登入事件：</span><span class="sxs-lookup"><span data-stu-id="dae3e-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="dae3e-148">**在兩** 側都使用時間篩選 -即使您沒有調查特定時段，在左右兩個數據表上都適用時間篩選，可以減少檢查記錄的數量並提升 `join` 績效。</span><span class="sxs-lookup"><span data-stu-id="dae3e-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="dae3e-149">下列查詢會同時適用于 `Timestamp > ago(1h)` 這兩個數據表，因此它只能連接過去一小時的記錄：</span><span class="sxs-lookup"><span data-stu-id="dae3e-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="dae3e-150">**使用提升效率的提示**—執行耗用大量資源的作業時，使用提示與運算子指示後端 `join` 分配負載。</span><span class="sxs-lookup"><span data-stu-id="dae3e-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="dae3e-151">深入瞭解加入提示</span><span class="sxs-lookup"><span data-stu-id="dae3e-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="dae3e-152">例如，隨機播放 **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 提示在使用有高基數的索引鍵加入資料表時，協助改善查詢的顯示效果 ，此機率是具有許多唯一值的索引鍵，例如下面的 `AccountObjectId` 查詢：</span><span class="sxs-lookup"><span data-stu-id="dae3e-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="dae3e-153">廣播 **[提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 有助於當左側資料表 (多達 100，000 個記錄) 而右資料表則相當大。</span><span class="sxs-lookup"><span data-stu-id="dae3e-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="dae3e-154">例如，下列查詢嘗試聯入一些具有特定主題的電子郵件，而所有郵件都包含資料表中的 `EmailUrlInfo` 連結：</span><span class="sxs-lookup"><span data-stu-id="dae3e-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="dae3e-155">優化 `summarize` 運算子</span><span class="sxs-lookup"><span data-stu-id="dae3e-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="dae3e-156">摘要 [運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 會匯總資料表的內容。</span><span class="sxs-lookup"><span data-stu-id="dae3e-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="dae3e-157">請使用這些秘訣來優化使用這個運算子的查詢。</span><span class="sxs-lookup"><span data-stu-id="dae3e-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="dae3e-158">**尋找不同的值**—一般會用於 `summarize` 尋找重複的區分值。</span><span class="sxs-lookup"><span data-stu-id="dae3e-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="dae3e-159">您可以使用它來匯總沒有重複值的欄。</span><span class="sxs-lookup"><span data-stu-id="dae3e-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="dae3e-160">雖然單一電子郵件可以屬於多個事件的一部分，但下列範例沒有效率地使用，因為個別電子郵件的網路郵件識別碼一定隨附唯一寄件者 `summarize` 位址。</span><span class="sxs-lookup"><span data-stu-id="dae3e-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="dae3e-161">運算子 `summarize` 很容易被取代，這有可能會獲得相同的結果， `project` 同時耗用較少的資源：</span><span class="sxs-lookup"><span data-stu-id="dae3e-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="dae3e-162">下列範例是比較有效率地使用，因為傳送電子郵件至相同收件者位址的寄件者位址可能會有多個 `summarize` 不同的實例。</span><span class="sxs-lookup"><span data-stu-id="dae3e-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="dae3e-163">這類組合較不區分，而且可能重複。</span><span class="sxs-lookup"><span data-stu-id="dae3e-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="dae3e-164">**隨機排列** 查詢 — 雖然最適合用於重複值的欄，但相同的資料行也可以擁有高基數或大量的 `summarize` 唯一值。 </span><span class="sxs-lookup"><span data-stu-id="dae3e-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="dae3e-165">就像運算子一樣，您也可以使用隨機播放提示來分配處理負載，並可能提升在高基數欄 `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` 上作業時的績效。</span><span class="sxs-lookup"><span data-stu-id="dae3e-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="dae3e-166">下面這個查詢會用來計算不同的收件者電子郵件地址，它可以在數十萬大型組織中 `summarize` 執行。</span><span class="sxs-lookup"><span data-stu-id="dae3e-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="dae3e-167">為提升效果，它整合了 `hint.shufflekey` ：</span><span class="sxs-lookup"><span data-stu-id="dae3e-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="dae3e-168">查詢案例</span><span class="sxs-lookup"><span data-stu-id="dae3e-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="dae3e-169">使用流程名稱識別唯一流程</span><span class="sxs-lookup"><span data-stu-id="dae3e-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="dae3e-170">程序識別碼 (PID) 會在 Windows 中回收，並針對新程序重複使用。</span><span class="sxs-lookup"><span data-stu-id="dae3e-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="dae3e-171">它們本身不能充當特定程序的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="dae3e-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="dae3e-172">若要為特定電腦上的程序取得唯一識別碼，請使用程序識別碼與程序建立時間。</span><span class="sxs-lookup"><span data-stu-id="dae3e-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="dae3e-173">結合或摘要處理程序中的資料時，需包含電腦識別碼的欄位 (`DeviceId` 或 `DeviceName`)、程序識別碼 (`ProcessId` 或 `InitiatingProcessId`) 以及程序建立時間 (`ProcessCreationTime` 或 `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="dae3e-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="dae3e-174">下列範例查詢發現透過連接埠 445 (SMB) 存取 10 個以上 IP 位址的程序，可能是因為掃描檔案共用。</span><span class="sxs-lookup"><span data-stu-id="dae3e-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="dae3e-175">例如查詢：</span><span class="sxs-lookup"><span data-stu-id="dae3e-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="dae3e-176">查詢會以 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 進行彙總，因此它會檢查單一程序，而不會將多個具有相同程序識別碼的程序混合在一起。</span><span class="sxs-lookup"><span data-stu-id="dae3e-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="dae3e-177">查詢命令列</span><span class="sxs-lookup"><span data-stu-id="dae3e-177">Query command lines</span></span>
<span data-ttu-id="dae3e-178">有許多方法可以建構命令列來完成工作。</span><span class="sxs-lookup"><span data-stu-id="dae3e-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="dae3e-179">例如，攻擊者可能會以沒有路徑、沒有副檔名、使用環境變數或引號來參考影像檔案。</span><span class="sxs-lookup"><span data-stu-id="dae3e-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="dae3e-180">攻擊者也可以變更參數的順序，或新增多個引號和空格。</span><span class="sxs-lookup"><span data-stu-id="dae3e-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="dae3e-181">若要在命令列周圍建立更多查詢，請採用下列做法：</span><span class="sxs-lookup"><span data-stu-id="dae3e-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="dae3e-182">比對 (名稱欄位 *net.exe或\*\*psexec.exe)* 來識別已知程式，而不是篩選命令列本身。</span><span class="sxs-lookup"><span data-stu-id="dae3e-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="dae3e-183">使用 [parse_command_line () 函數剖析命令列區段](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="dae3e-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="dae3e-184">查詢命令列引數時，請勿以特定順序尋找多個不相關引數上完全相符的內容。</span><span class="sxs-lookup"><span data-stu-id="dae3e-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="dae3e-185">請改用規則運算式或使用多個不同的包含運算子。</span><span class="sxs-lookup"><span data-stu-id="dae3e-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="dae3e-186">使用不區分大小寫對比。</span><span class="sxs-lookup"><span data-stu-id="dae3e-186">Use case insensitive matches.</span></span> <span data-ttu-id="dae3e-187">例如，使用 `=~` `in~` 、、及 `contains` `==` `in` `contains_cs` 。</span><span class="sxs-lookup"><span data-stu-id="dae3e-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="dae3e-188">若要減輕命令列混淆技巧，請考慮移除引號、以空格取代逗號，以及使用單一空格取代多個連續空格。</span><span class="sxs-lookup"><span data-stu-id="dae3e-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="dae3e-189">有更複雜的混淆技巧需要其他方法，但這些調整可以協助解決常見的問題。</span><span class="sxs-lookup"><span data-stu-id="dae3e-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="dae3e-190">下列範例顯示各種方式，以建構查詢來尋找要尋找的檔案net.exe防火牆服務 "MpsSvc"：</span><span class="sxs-lookup"><span data-stu-id="dae3e-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="dae3e-191">從外部來源中輸入資料</span><span class="sxs-lookup"><span data-stu-id="dae3e-191">Ingest data from external sources</span></span>
<span data-ttu-id="dae3e-192">若要將長清單或大型資料表併入查詢中，請使用 [外部](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 資料表運算子從指定的 URI 內入資料。</span><span class="sxs-lookup"><span data-stu-id="dae3e-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="dae3e-193">您可以取得來自 TXT、CSV、JSON 或其他格式 [之檔案的資料](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)。</span><span class="sxs-lookup"><span data-stu-id="dae3e-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="dae3e-194">下列範例顯示如何使用 MalwareBazaar (abuse.ch) 提供的惡意程式碼 SHA-256 雜湊清單來檢查電子郵件的附件：</span><span class="sxs-lookup"><span data-stu-id="dae3e-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="dae3e-195">剖析字串</span><span class="sxs-lookup"><span data-stu-id="dae3e-195">Parse strings</span></span>
<span data-ttu-id="dae3e-196">您可以使用各種函數有效率地處理需要剖析或轉換的字串。</span><span class="sxs-lookup"><span data-stu-id="dae3e-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="dae3e-197">字串</span><span class="sxs-lookup"><span data-stu-id="dae3e-197">String</span></span> | <span data-ttu-id="dae3e-198">函數</span><span class="sxs-lookup"><span data-stu-id="dae3e-198">Function</span></span> | <span data-ttu-id="dae3e-199">使用範例</span><span class="sxs-lookup"><span data-stu-id="dae3e-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="dae3e-200">命令列</span><span class="sxs-lookup"><span data-stu-id="dae3e-200">Command-lines</span></span> | [<span data-ttu-id="dae3e-201">parse_command_line ( ) </span><span class="sxs-lookup"><span data-stu-id="dae3e-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="dae3e-202">解壓縮命令及所有引數。</span><span class="sxs-lookup"><span data-stu-id="dae3e-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="dae3e-203">Paths</span><span class="sxs-lookup"><span data-stu-id="dae3e-203">Paths</span></span> | [<span data-ttu-id="dae3e-204">parse_path ( ) </span><span class="sxs-lookup"><span data-stu-id="dae3e-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="dae3e-205">解壓縮檔案或資料夾路徑的區段。</span><span class="sxs-lookup"><span data-stu-id="dae3e-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="dae3e-206">版本號碼</span><span class="sxs-lookup"><span data-stu-id="dae3e-206">Version numbers</span></span> | [<span data-ttu-id="dae3e-207">parse_version ( ) </span><span class="sxs-lookup"><span data-stu-id="dae3e-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="dae3e-208">使用最多四個區段以及每個區段最多八個字元來解說版本號碼。</span><span class="sxs-lookup"><span data-stu-id="dae3e-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="dae3e-209">使用剖析的資料來比較版本年齡。</span><span class="sxs-lookup"><span data-stu-id="dae3e-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="dae3e-210">IPv4 位址</span><span class="sxs-lookup"><span data-stu-id="dae3e-210">IPv4 addresses</span></span> | [<span data-ttu-id="dae3e-211">parse_ipv4 ( ) </span><span class="sxs-lookup"><span data-stu-id="dae3e-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="dae3e-212">將 IPv4 位址轉換為長整數。</span><span class="sxs-lookup"><span data-stu-id="dae3e-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="dae3e-213">若要比較 IPv4 位址而不轉換位址，請使用[ipv4_compare () 。](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)</span><span class="sxs-lookup"><span data-stu-id="dae3e-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="dae3e-214">IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="dae3e-214">IPv6 addresses</span></span> | [<span data-ttu-id="dae3e-215">parse_ipv6 ( ) </span><span class="sxs-lookup"><span data-stu-id="dae3e-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="dae3e-216">將 IPv4 或 IPv6 位址轉換為規範的 IPv6 標記法。</span><span class="sxs-lookup"><span data-stu-id="dae3e-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="dae3e-217">若要比較 IPv6 位址，請使用 [ipv6_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="dae3e-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="dae3e-218">若要瞭解所有支援的剖析函數，請閱讀[Kusto 字串函數。](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="dae3e-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="dae3e-219">相關主題</span><span class="sxs-lookup"><span data-stu-id="dae3e-219">Related topics</span></span>
- [<span data-ttu-id="dae3e-220">Kusto 查詢語言檔</span><span class="sxs-lookup"><span data-stu-id="dae3e-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="dae3e-221">配額和使用量參數</span><span class="sxs-lookup"><span data-stu-id="dae3e-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="dae3e-222">處理進位搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="dae3e-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="dae3e-223">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="dae3e-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dae3e-224">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="dae3e-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
