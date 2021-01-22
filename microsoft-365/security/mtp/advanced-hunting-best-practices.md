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
# <a name="advanced-hunting-query-best-practices"></a>進階搜捕查詢最佳做法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

請執行這些建議以更快獲得結果，並避免執行複雜查詢時執行超時。 如需提高查詢效能的更多指導方針，請參閱 [Kusto 查詢最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。

## <a name="understand-cpu-resource-quotas"></a>瞭解 CPU 資源配額
根據租使用者的大小，每個租使用者可以存取配置給執行進位搜尋查詢的一組 CPU 資源。 有關各種服務限制的詳細資訊， [請參閱進位搜尋配額及使用參數](advanced-hunting-limits.md)。

定期執行多個查詢的客戶應追蹤使用狀況，並運用本文中的優化指引，將超出配額或使用量參數所產生的干擾降至最低。

## <a name="general-optimization-tips"></a>一般優化秘訣

- **調整新查詢的大小**— 如果您懷疑查詢會回回大型結果集，首先使用計數運算子 [進行評估](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)。 使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或其同名避免 `take` 產生大型結果集。
- 提早 **套** 用篩選 -套用時間篩選及其他篩選，以減少資料集，尤其是在使用轉換及剖析函數 #B0 例如子字串 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)取代 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)修剪 [ () 、toupper](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction) [ ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json () 之前 #C3。](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction) 在下列範例中，當篩選運算子減少記錄數目之後，會使用剖析函數解壓縮 ( [) 。](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction)

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **包含 -** 若要避免不必要地搜尋字詞內的子字串，請使用 `has` 運算子，而不要 `contains` 。 [瞭解字串運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **查看特定欄**—查看特定欄，而不是在所有資料行中執行完整文字搜尋。 不檢查 `*` 所有欄。
- **針對速度區分大小寫**- 區分大小寫的搜尋更特定且通常更具有執行性。 區分大小寫的字串 [運算子名稱](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)，例如 `has_cs` and `contains_cs` ，通常以 `_cs` . 您也可以使用區分大小寫的等號運算子來 `==` 取代 `=~` 。
- **剖析#B0** 請勿解壓縮 #C1—[](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator)盡可能使用剖析運算子或剖析函數 #B2 例如 [parse_json ( #C3。](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction) 避免 `matches regex` 使用字串運算子或 [解壓縮 () 函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)，這兩者都是使用正則運算式。 針對更複雜的情況，請保留使用正則運算式。 [瞭解更多關於剖析函數](#parse-strings)
- **篩選表格而不是運算式**—如果可以篩選資料表資料行，就不要篩選計算結果欄。
- **無三個字元的字詞**- 請避免使用三個字元以下的字詞來比較或篩選。 這些詞彙未編制索引，因此必須比對更多資源。
- **選擇性 Project**- 只預測您需要的欄，讓結果更容易理解。 在執行聯集 [或類似作業](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 前先預測特定資料行，也可協助改善績效。

## <a name="optimize-the-join-operator"></a>優化 `join` 運算子
聯 [集運算子會](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 比對指定資料行中的值，以合併兩個數據表中的資料列。 請使用這些秘訣來優化使用這個運算子的查詢。

- **左方較小的資料表**—運算子將連接語句左側資料表中的記錄與 `join` 右邊的記錄進行比對。 左側有較小的資料表後，需要比對的記錄就會變少，因而能加快查詢的速度。 

    在下表中，我們先將左側表格縮小為只涵蓋三部特定裝置，然後再使用帳戶 `DeviceLogonEvents` `IdentityLogonEvents` SIDs 加入左側資料表。
 
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

- 使用內部聯集型 **：預設** 連接 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)詞型或 [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows by join key to the join key for each match to right table. 如果左側資料表有多個資料列的索引鍵值相同，這些列將會重復資料，以針對每個唯一值保留單一 `join` 隨機列。

    此預設行為會從左側資料表中排除重要資訊，以提供有用的深入見解。 例如，以下查詢只會顯示一封包含特定附件的電子郵件，即使該相同附件是使用多封電子郵件訊息送出：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    若要解決這項限制，我們套用[](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)內部聯集型，指定在左側資料表中顯示所有列，並向右顯示 `kind=inner` 符合的值：
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **從時間視窗加入記錄**- 在調查安全性事件時，分析師會尋找同一時段內發生的相關事件。 使用相同方法也可減少要檢查的記錄數目，以提升 `join` 效果。
    
    以下查詢會檢查在收到惡意檔案的 30 分鐘內是否發生登入事件：

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
- **在兩** 側都使用時間篩選 -即使您沒有調查特定時段，在左右兩個數據表上都適用時間篩選，可以減少檢查記錄的數量並提升 `join` 績效。 下列查詢會同時適用于 `Timestamp > ago(1h)` 這兩個數據表，因此它只能連接過去一小時的記錄：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **使用提升效率的提示**—執行耗用大量資源的作業時，使用提示與運算子指示後端 `join` 分配負載。 [深入瞭解加入提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    例如，隨機播放 **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 提示在使用有高基數的索引鍵加入資料表時，協助改善查詢的顯示效果 ，此機率是具有許多唯一值的索引鍵，例如下面的 `AccountObjectId` 查詢：

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    廣播 **[提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 有助於當左側資料表 (多達 100，000 個記錄) 而右資料表則相當大。 例如，下列查詢嘗試聯入一些具有特定主題的電子郵件，而所有郵件都包含資料表中的 `EmailUrlInfo` 連結：

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>優化 `summarize` 運算子
摘要 [運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 會匯總資料表的內容。 請使用這些秘訣來優化使用這個運算子的查詢。

- **尋找不同的值**—一般會用於 `summarize` 尋找重複的區分值。 您可以使用它來匯總沒有重複值的欄。

    雖然單一電子郵件可以屬於多個事件的一部分，但下列範例沒有效率地使用，因為個別電子郵件的網路郵件識別碼一定隨附唯一寄件者 `summarize` 位址。
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    運算子 `summarize` 很容易被取代，這有可能會獲得相同的結果， `project` 同時耗用較少的資源：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    下列範例是比較有效率地使用，因為傳送電子郵件至相同收件者位址的寄件者位址可能會有多個 `summarize` 不同的實例。 這類組合較不區分，而且可能重複。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **隨機排列** 查詢 — 雖然最適合用於重複值的欄，但相同的資料行也可以擁有高基數或大量的 `summarize` 唯一值。  就像運算子一樣，您也可以使用隨機播放提示來分配處理負載，並可能提升在高基數欄 `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` 上作業時的績效。

    下面這個查詢會用來計算不同的收件者電子郵件地址，它可以在數十萬大型組織中 `summarize` 執行。 為提升效果，它整合了 `hint.shufflekey` ：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>查詢案例

### <a name="identify-unique-processes-with-process-ids"></a>使用流程名稱識別唯一流程
程序識別碼 (PID) 會在 Windows 中回收，並針對新程序重複使用。 它們本身不能充當特定程序的唯一識別碼。

若要為特定電腦上的程序取得唯一識別碼，請使用程序識別碼與程序建立時間。 結合或摘要處理程序中的資料時，需包含電腦識別碼的欄位 (`DeviceId` 或 `DeviceName`)、程序識別碼 (`ProcessId` 或 `InitiatingProcessId`) 以及程序建立時間 (`ProcessCreationTime` 或 `InitiatingProcessCreationTime`)

下列範例查詢發現透過連接埠 445 (SMB) 存取 10 個以上 IP 位址的程序，可能是因為掃描檔案共用。

例如查詢：
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

查詢會以 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 進行彙總，因此它會檢查單一程序，而不會將多個具有相同程序識別碼的程序混合在一起。

### <a name="query-command-lines"></a>查詢命令列
有許多方法可以建構命令列來完成工作。 例如，攻擊者可能會以沒有路徑、沒有副檔名、使用環境變數或引號來參考影像檔案。 攻擊者也可以變更參數的順序，或新增多個引號和空格。

若要在命令列周圍建立更多查詢，請採用下列做法：

- 比對 (名稱欄位 *net.exe或**psexec.exe)* 來識別已知程式，而不是篩選命令列本身。
- 使用 [parse_command_line () 函數剖析命令列區段](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- 查詢命令列引數時，請勿以特定順序尋找多個不相關引數上完全相符的內容。 請改用規則運算式或使用多個不同的包含運算子。
- 使用不區分大小寫對比。 例如，使用 `=~` `in~` 、、及 `contains` `==` `in` `contains_cs` 。
- 若要減輕命令列混淆技巧，請考慮移除引號、以空格取代逗號，以及使用單一空格取代多個連續空格。 有更複雜的混淆技巧需要其他方法，但這些調整可以協助解決常見的問題。

下列範例顯示各種方式，以建構查詢來尋找要尋找的檔案net.exe防火牆服務 "MpsSvc"：

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

### <a name="ingest-data-from-external-sources"></a>從外部來源中輸入資料
若要將長清單或大型資料表併入查詢中，請使用 [外部](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 資料表運算子從指定的 URI 內入資料。 您可以取得來自 TXT、CSV、JSON 或其他格式 [之檔案的資料](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)。 下列範例顯示如何使用 MalwareBazaar (abuse.ch) 提供的惡意程式碼 SHA-256 雜湊清單來檢查電子郵件的附件：

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

### <a name="parse-strings"></a>剖析字串
您可以使用各種函數有效率地處理需要剖析或轉換的字串。 

| 字串 | 函數 | 使用範例 |
|--|--|--|
| 命令列 | [parse_command_line ( ) ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | 解壓縮命令及所有引數。 | 
| Paths | [parse_path ( ) ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | 解壓縮檔案或資料夾路徑的區段。 |
| 版本號碼 | [parse_version ( ) ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | 使用最多四個區段以及每個區段最多八個字元來解說版本號碼。 使用剖析的資料來比較版本年齡。 |
| IPv4 位址 | [parse_ipv4 ( ) ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | 將 IPv4 位址轉換為長整數。 若要比較 IPv4 位址而不轉換位址，請使用[ipv4_compare () 。](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction) |
| IPv6 位址 | [parse_ipv6 ( ) ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | 將 IPv4 或 IPv6 位址轉換為規範的 IPv6 標記法。 若要比較 IPv6 位址，請使用 [ipv6_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。 |

若要瞭解所有支援的剖析函數，請閱讀[Kusto 字串函數。](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>相關主題
- [Kusto 查詢語言檔](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [配額和使用量參數](advanced-hunting-limits.md)
- [處理進位搜尋錯誤](advanced-hunting-errors.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
