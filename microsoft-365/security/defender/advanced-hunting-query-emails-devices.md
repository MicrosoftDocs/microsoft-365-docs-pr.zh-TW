---
title: 使用高級搜尋來尋找跨裝置、電子郵件、應用程式和身分識別的威脅
description: 研究常見搜尋案例，以及涵蓋裝置、電子郵件、應用程式和身分識別的範例查詢。
keywords: 高級搜尋，Office365 資料，Windows 裝置，Office365 電子郵件正常化，電子郵件，應用程式，身分識別，威脅搜尋，網路威脅搜尋，搜尋，查詢，遙測，Microsoft 365，Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8a811d60af281bb534776736e77c3eb54ab6a760
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932962"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>跨裝置、電子郵件、應用程式和身分識別搜捕威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

Microsoft 365 Defender 中的[高級搜尋](advanced-hunting-overview.md)可讓您主動搜尋整個威脅：
- Microsoft Defender for Endpoint 所管理的裝置
- Microsoft 365 處理的電子郵件
- Microsoft Cloud App Security 和 Microsoft Defender 身分識別追蹤的雲端應用程式活動、驗證事件和網域控制站活動

透過這種可視性層次，您可以快速尋找跨越網路各部分的威脅，包括抵達電子郵件或網頁的複雜入侵、提升本機許可權、取得許可權的網域認證，以及橫向移至您的裝置。 

以下是以各種搜尋案例為基礎的一般技術和範例查詢，可協助您探索在搜尋複雜威脅時，如何建立查詢。

## <a name="get-entity-info"></a>取得實體資訊
您可以使用這些查詢來瞭解如何快速取得使用者帳戶、裝置及檔案的相關資訊。 

### <a name="obtain-user-accounts-from-email-addresses"></a>從電子郵件地址取得使用者帳戶
在[涵蓋裝置和電子郵件的表格](advanced-hunting-schema-tables.md)建立查詢時，您可能需要取得寄件者或收件者電子郵件地址的使用者帳戶名稱。 您通常可以使用 *本機主機* 從電子郵件地址進行收件者或寄件者位址。

在下方的程式碼片段中，我們使用 [tostring () ](/azure/data-explorer/kusto/query/tostringfunction) Kusto 函數，先 `@` 從欄中的從收件者電子郵件地址開始解壓縮本機主機 `RecipientEmailAddress` 。

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
下列查詢會顯示如何使用此程式碼片段：

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>合併 IdentityInfo 表格

您可以合併或加入 [IdentityInfo 表格](advanced-hunting-identityinfo-table.md)，以取得帳戶名稱及其他帳戶資訊。 下列查詢會從 [EmailEvents 資料表](advanced-hunting-emailevents-table.md) 取得網路釣魚和惡意程式碼偵測清單，然後將該資訊加入表格， `IdentityInfo` 以取得每個收件者的詳細資訊。 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>取得裝置資訊
「 [高級搜尋架構](advanced-hunting-schema-tables.md) 」在各種表格中提供大量的裝置資訊。 例如， [DeviceInfo 表格](advanced-hunting-deviceinfo-table.md) 會根據定期匯總的事件資料，提供完整的裝置資訊。 此查詢會使用 `DeviceInfo` 表格來檢查是否有可能已遭破壞的使用者 (`<account-name>`) 已登入任何裝置，然後列出已在那些裝置上觸發的警示。

>[!Tip]
> 此查詢 `kind=inner` 會使用來指定 [內部聯接](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)，以避免重復資料刪除的左側值 `DeviceId` 。

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

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>列出收到未順利 zapped 之電子郵件的使用者登入活動
[零小時自動清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md) 會在收到惡意電子郵件之後，加以解決。 如果 ZAP 失敗，惡意的程式碼可能會最終在裝置上執行，並使帳戶受到損害。 此查詢會檢查是否有由 ZAP 未成功解決的電子郵件收件者所進行的登入活動。

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>以認證盜竊為目標的網域帳戶來取得登入嘗試
此查詢會先識別表格中的所有認證訪問警示 `AlertInfo` 。 然後，它會合並或連接 `AlertEvidence` 資料表，它會針對目標帳戶的名稱進行分析，並且只會針對已加入網域的帳戶篩選。 最後，它會檢查 `IdentityLogonEvents` 表格，以透過加入網域的目標帳戶取得所有登入活動。

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
假設您知道傳送惡意檔案 () 的電子郵件地址 `MaliciousSender@example.com` ，您可以執行此查詢，以判斷您的裝置上是否存在來自此寄件者的檔案。 例如，您可以使用此查詢來識別受惡意軟體發佈活動影響的裝置。

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
| where ThreatTypes has "Malware" 
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
惡意電子郵件通常包含文件和其他精心設計的附件，以執行 PowerShell 命令來提供額外的承載。 如果您知道來自已知惡意寄件者的電子郵件 (`MaliciousSender@example.com`) ，您可以使用此查詢，列出並複查從寄件者收到電子郵件後30分鐘內發生的 PowerShell 活動。  

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