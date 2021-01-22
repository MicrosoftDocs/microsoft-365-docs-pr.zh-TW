---
title: 搜尋各種裝置、電子郵件、App 和身分身分間的威脅，以進一搜尋
description: 研究常見的搜尋案例和範例查詢，這些範例查詢涵蓋裝置、電子郵件、應用程式和身分。
keywords: 進層搜尋、Office365 資料、Windows 裝置、Office365 電子郵件正規化、電子郵件、App、身分驗證、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
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
ms.openlocfilehash: b408f574ab4b89806be9154394f49c00a7fd1e99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932247"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>跨裝置、電子郵件、應用程式和身分身分尋找威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[](advanced-hunting-overview.md) Microsoft 365 Defender 中的進一步搜尋可讓您主動搜尋來自：
- 由 Microsoft Defender for Endpoint 管理的裝置
- Microsoft 365 處理的電子郵件
- 由 Microsoft Cloud App 安全性與 Microsoft Defender for Identity 追蹤的雲端應用程式活動、驗證事件及網域控制站活動

有了這個層級的可見度，您可以快速搜尋流覽網路區段的威脅，包括送達電子郵件或網路的複雜入侵、提高當地許可權、取得特殊許可權的網域認證，以及稍後在裝置上移動。 

以下是根據各種搜尋案例所根據的一般技巧和範例查詢，可協助探索在搜尋如此複雜的威脅時如何建構查詢。

## <a name="get-entity-info"></a>取得實體資訊
使用這些查詢來瞭解如何快速取得使用者帳戶、裝置和檔案的資訊。 

### <a name="obtain-user-accounts-from-email-addresses"></a>從電子郵件地址取得使用者帳戶
在[涵蓋裝置和電子郵件的表格](advanced-hunting-schema-tables.md)建立查詢時，您可能需要取得寄件者或收件者電子郵件地址的使用者帳戶名稱。 您通常可以使用電子郵件地址的 *local-host* 為收件者或寄件者位址這麼做。

在下列片段中，我們使用[tostring () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto 函數，在欄中的收件者電子郵件地址之前，抽選 `@` local-host。 `RecipientEmailAddress`

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
下列查詢顯示此程式碼片段的使用方式：

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>合併 IdentityInfo 資料表

您可以合併或加入 IdentityInfo 資料表，以取得帳戶名稱 [和其他帳戶資訊](advanced-hunting-identityinfo-table.md)。 下列查詢會從 [EmailEvents](advanced-hunting-emailevents-table.md) 資料表取得網路釣魚和惡意程式碼偵測清單，然後將該資訊與資料表聯起來，以取得每個收件者 `IdentityInfo` 的詳細資訊。 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>取得裝置資訊
進 [位搜尋架構](advanced-hunting-schema-tables.md) 在各種資料表中提供廣泛的裝置資訊。 例如 [，DeviceInfo 資料表](advanced-hunting-deviceinfo-table.md) 會根據定期匯總的事件資料，提供完整的裝置資訊。 此查詢會使用資料表檢查有潛在威脅的使用者 () 已登入任何裝置，然後列出這些裝置上觸發的 `DeviceInfo` `<account-name>` 警示。

>[!Tip]
> 此查詢 `kind=inner` 會用來指定 [內部連接](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)，可防止重復資料刪除的左側值 `DeviceId` 。

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a>搜捕案例

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>收到未成功刪除電子郵件之使用者的登入活動清單
[使用 0 小時自動清除 ZAP (可) ](../office-365-security/zero-hour-auto-purge.md) 收到惡意電子郵件後執行清除。 如果 ZAP 失敗，惡意程式碼最後可能會在裝置上執行，並破壞帳戶。 此查詢會檢查電子郵件收件者所登入的活動是否未成功由 ZAP 處理。

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>以認證竊取為目標的網域帳戶嘗試登入
此查詢會先識別資料表中的所有認證存取 `AlertInfo` 通知。 然後，它會合並或加入資料表，其中會剖析目標帳戶的名稱，並只剖析網 `AlertEvidence` 域加入帳戶的篩選。 最後，它會檢查 `IdentityLogonEvents` 資料表，以取得網域加入的目標帳戶的所有登入活動。

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>檢查裝置上是否有來自已知惡意寄件者的檔案
假設您知道有電子郵件地址傳送惡意檔案 () ，您可以執行此查詢來判斷此寄件者的檔案是否存在於 `MaliciousSender@example.com` 您的裝置上。 例如，您可以使用此查詢來識別受到惡意程式碼發佈行銷活動影響的裝置。

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>在收到惡意電子郵件後檢閱登入嘗試
此查詢會在收到已知的惡意電子郵件後，尋找 30 分鐘內由電子郵件收件者執行的最近 10 次登入。 您可以使用此查詢來檢查電子郵件收件者的帳戶是否遭入侵。

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>在收到已知惡意寄件者的電子郵件後檢閱 PowerShell 活動
惡意電子郵件通常包含文件和其他精心設計的附件，以執行 PowerShell 命令來提供額外的承載。 如果您發現來自已知惡意寄件者 () 的電子郵件，您可以使用此查詢列出並檢查收到寄件者的電子郵件後 30 分鐘內發生的 `MaliciousSender@example.com` PowerShell 活動。  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
