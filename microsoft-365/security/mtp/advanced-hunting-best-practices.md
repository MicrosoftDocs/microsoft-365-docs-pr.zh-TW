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
ms.openlocfilehash: 29e5eb64445c6c5c45b8e1fd1633c030b5f32b86
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649664"
---
# <a name="advanced-hunting-query-best-practices"></a>進階搜捕查詢最佳做法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 威脅防護

套用這些建議以快速取得結果，並避免執行複雜的查詢時發生超時。 如需提高查詢效能的更多指導方針，請參閱 [Kusto 查詢最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。

## <a name="understand-cpu-resource-quotas"></a>瞭解 CPU 資源配額
視其大小而定，每個租使用者都有權存取一組為執行高級搜尋查詢所指派的 CPU 資源量。 如需各種服務限制的詳細資訊，請 [閱讀相關的高級搜尋配額和使用參數](advanced-hunting-limits.md)。

定期執行多個查詢的客戶應追蹤工作量，並套用本文中的優化指導，以盡可能減少超出配額或使用參數所產生的中斷。

## <a name="general-optimization-tips"></a>一般優化秘訣

- [**新增查詢大小**]：如果您懷疑查詢會傳回大型結果集，請先使用[count 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)來評估。 使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或其同義字 `take` 以避免大型結果集。
- **及早套用篩選器**—套用時間篩選和其他篩選器，以減少資料集，尤其是在使用轉換和分析功能之前（如 [子字串 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)、 [取代 ( # B3 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)、 [trim ( # B5 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)、 [toupper ( # B7 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json ( # B9 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)）。 在下列範例中，會在篩選運算子減少記錄數目後，使用 [ ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) 的分析函數 extractjson。

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **具有節拍**：若要避免在非必要字詞中搜尋子字串，請使用 `has` 運算子，而不要使用 `contains` 。 [瞭解字串運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **在特定欄中查看**--查看特定欄，而不是在所有欄中執行完整的文字搜尋。 請勿使用 `*` 以檢查所有欄。
- **以區分大小寫的速度**-區分大小寫的搜尋更為具體，而且通常更為具性能。 區分大小寫的 [字串運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)（例如 `has_cs` 和）的名稱 `contains_cs` 一般為 `_cs` 。 您也可以使用區分大小寫的 equals 運算子， `==` 而不要使用 `=~` 。
- **剖析：請**盡可能使用 [parse 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 或類似 [parse_json ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)的分析函數。 避免 `matches regex` 使用正則運算式的字串運算子或 [析取 ( # A1 函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)。 保留使用正則運算式以取得更複雜的案例。 [閱讀有關分析函數的詳細資訊](#parse-strings)
- **篩選資料表不是運算式**-如果您可以在資料表欄上篩選，請勿在計算欄上篩選。
- **無三個字元的字詞**，避免使用包含三個字元或更少的字詞來比較或篩選。 這些字詞不會編制索引，而且符合這些字詞將需要更多資源。
- **專案可選擇性地**透過只投影您所需的欄，使您的結果更容易理解。 在執行 [加入](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 或類似作業之前，先投射特定欄，也有助於提升效能。

## <a name="optimize-the-join-operator"></a>優化 `join` 運算子
[Join 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)會透過比對指定的欄中的值，合併兩個數據表中的資料行。 套用這些秘訣以優化使用此操作符的查詢。

- 向**左縮小的表格**，運算子會將 `join` join 語句左邊表格中的記錄與右邊的記錄進行比較。 將較小的表格保留在左邊，必須符合較少的記錄，進而加速查詢。 

    在下表中，我們 `DeviceLogonEvents` 會在加入帳戶 sid 之前，先將左側表格縮小為只涵蓋三個特定裝置 `IdentityLogonEvents` 。
 
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

- 在將每個相符的列傳回給右表之前，**請先使用內部聯接**口味（預設的[join 口味](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)）及左表中的[innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)鍵 deduplicates 列。 如果左表的多個資料列的索引鍵具有相同的值 `join` ，這些資料列將會被重複的資料列，保留每個唯一值的單一隨機列。

    此預設行為會從左資料表中留下重要資訊，可提供有用的洞察力。 例如，下列查詢只會顯示一個包含特定附件的電子郵件，即使該相同附件是使用多封電子郵件訊息傳送：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    若要解決這項限制，我們會套用 [內部聯接](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 口味，其方式是指定 `kind=inner` [顯示左表格中的所有列的右側都有相符的值：
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **從時間範圍加入記錄**：在調查安全性事件時，分析程式會尋找在相同時間週期內發生的相關事件。 使用相同的方法， `join` 也就是減少要檢查的記錄數目的效能的優點。
    
    下列查詢會檢查在接收惡意檔30分鐘內的登入事件：

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
- **在兩側套用時間篩選**-即使您不是在調查特定時間範圍，在左和右表上套用時間篩選也可以減少要檢查的記錄數目，並改善 `join` 效能。 下列查詢適用于 `Timestamp > ago(1h)` 這兩個數據表，只會從過去的小時加入記錄：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **使用提示效能**-在執行 `join` 大量佔用資源的作業時，以運算子搭配使用提示，以指示後端分配負載。 [深入瞭解聯接提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    例如，當使用具有很高基數的索引鍵來聯接資料表時， **[無序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 會協助改善查詢效能（具有許多唯一值的索引鍵，如下表所示） `AccountObjectId` ：

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    當左表為小型 (至 100000) 記錄時， **[廣播提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 會有説明，而且右資料表非常大。 例如，下列查詢會嘗試加入少數幾封電子郵件，其中的特定 _主題包含_ 表格中的連結 `EmailUrlInfo` ：

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>優化 `summarize` 運算子
[匯總運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator)會匯總表格的內容。 套用這些秘訣以優化使用此操作符的查詢。

- **尋找非重複的值**（一般 `summarize` 是用來尋找可以重複的非重複值）。 不需要使用它來匯總沒有重複值的資料行。

    雖然單一電子郵件可以是多個事件的一部分，但以下範例 _不_ 是有效使用， `summarize` 因為個別電子郵件的網路郵件識別碼總會附帶唯一的寄件者位址。
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    `summarize`操作員可輕鬆取代 `project` ，在消耗較少的資源時產生的結果可能相同：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    下列範例會更有效率地使用， `summarize` 因為寄件者位址可以有多個不同的實例，將電子郵件傳送至相同的收件者位址。 這類組合不太明顯，而且可能有重複專案。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **無序處理查詢**--當 `summarize` 資料行中的最大值是重複值時，相同的資料列也可以具有 _高基數_ 或大量的唯一值。 如同 `join` 運算子，您也可以在使用具有高基數的資料行上作業時，套用 [無序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) ，以 `summarize` 散佈處理負載，並可能提升效能。

    下列查詢可用於 `summarize` 計算非重複的收件者電子郵件地址，其可在大型組織的成百上千中執行。 為了改善效能，它包含 `hint.shufflekey` ：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>查詢案例

### <a name="identify-unique-processes-with-process-ids"></a>使用處理 IDs 識別唯一的程式
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
有許多方法可以建構命令列來完成工作。 例如，攻擊者可以參考沒有路徑、沒有副檔名、使用環境變數或引號的映射檔。 攻擊者也可以變更參數的順序，或新增多個引號及空格。

若要在命令列上建立更耐用的查詢，請套用下列做法：

- 透過比對的檔案名欄位，而不是在命令列本身上進行篩選，來識別已知的處理常式 (例如 *net.exe* 或 *psexec.exe*) 。
- 使用[parse_command_line ( # A1 函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)來分析命令列區段 
- 查詢命令列引數時，請勿以特定順序尋找多個不相關引數上完全相符的內容。 請改用規則運算式或使用多個不同的包含運算子。
- 使用不區分大小寫對比。 例如，使用 `=~` 、 `in~` 和， `contains` 而不是 `==` 、 `in` 和 `contains_cs` 。
- 若要緩解命令列混淆技術，請考慮移除引號、將逗號取代為空格，並以單一空格取代多個連續空格。 有些複雜的混淆技術需要其他方法，但這些調整功能可協助您解決常見的方法。

下列範例會示範各種構造查詢的方式，用來尋找檔案 *net.exe* 停止防火牆服務「MpsSvc」：

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

### <a name="ingest-data-from-external-sources"></a>從外部來源插入資料
若要將長清單或大型資料表納入查詢中，請使用 [externaldata 運算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 從指定的 URI 中攝取資料。 您可以從 TXT、CSV、JSON 或 [其他格式](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)的檔案中取得資料。 下列範例顯示如何利用 MalwareBazaar (abuse.ch) 所提供的大量惡意程式碼 SHA-256 雜湊，以檢查電子郵件上的附件：

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
您可以使用各種功能來有效處理需要剖析或轉換的字串。 

| 字串 | 函數 | 使用範例 |
|--|--|--|
| 命令列 | [parse_command_line ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | 解壓縮命令及所有引數。 | 
| Paths | [parse_path ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | 解壓縮檔的區段或資料夾路徑。 |
| 版本號碼 | [parse_version ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct 最多四個區段的版本號碼，且每個區段最多可有八個字元。 使用已分析的資料來比較版本時期。 |
| IPv4 位址 | [parse_ipv4 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | 將 IPv4 位址轉換成長整數。 若要比較 IPv4 位址但未轉換，請使用 [ipv4_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。 |
| IPv6 位址 | [parse_ipv6 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | 將 IPv4 或 IPv6 位址轉換為正常化 IPv6 標記法。 若要比較 IPv6 位址，請使用 [ipv6_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。 |

若要瞭解所有支援的分析功能，請 [閱讀 Kusto 字串函數](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。 

## <a name="related-topics"></a>相關主題
- [Kusto 查詢語言檔](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [配額和使用參數](advanced-hunting-limits.md)
- [處理高級搜尋錯誤](advanced-hunting-errors.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
