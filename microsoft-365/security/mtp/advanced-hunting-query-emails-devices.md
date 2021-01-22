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
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="fd392-104">跨裝置、電子郵件、應用程式和身分身分尋找威脅</span><span class="sxs-lookup"><span data-stu-id="fd392-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fd392-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fd392-105">**Applies to:**</span></span>
- <span data-ttu-id="fd392-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd392-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fd392-107">[](advanced-hunting-overview.md) Microsoft 365 Defender 中的進一步搜尋可讓您主動搜尋來自：</span><span class="sxs-lookup"><span data-stu-id="fd392-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="fd392-108">由 Microsoft Defender for Endpoint 管理的裝置</span><span class="sxs-lookup"><span data-stu-id="fd392-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="fd392-109">Microsoft 365 處理的電子郵件</span><span class="sxs-lookup"><span data-stu-id="fd392-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="fd392-110">由 Microsoft Cloud App 安全性與 Microsoft Defender for Identity 追蹤的雲端應用程式活動、驗證事件及網域控制站活動</span><span class="sxs-lookup"><span data-stu-id="fd392-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="fd392-111">有了這個層級的可見度，您可以快速搜尋流覽網路區段的威脅，包括送達電子郵件或網路的複雜入侵、提高當地許可權、取得特殊許可權的網域認證，以及稍後在裝置上移動。</span><span class="sxs-lookup"><span data-stu-id="fd392-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="fd392-112">以下是根據各種搜尋案例所根據的一般技巧和範例查詢，可協助探索在搜尋如此複雜的威脅時如何建構查詢。</span><span class="sxs-lookup"><span data-stu-id="fd392-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="fd392-113">取得實體資訊</span><span class="sxs-lookup"><span data-stu-id="fd392-113">Get entity info</span></span>
<span data-ttu-id="fd392-114">使用這些查詢來瞭解如何快速取得使用者帳戶、裝置和檔案的資訊。</span><span class="sxs-lookup"><span data-stu-id="fd392-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="fd392-115">從電子郵件地址取得使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="fd392-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="fd392-116">在[涵蓋裝置和電子郵件的表格](advanced-hunting-schema-tables.md)建立查詢時，您可能需要取得寄件者或收件者電子郵件地址的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="fd392-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="fd392-117">您通常可以使用電子郵件地址的 *local-host* 為收件者或寄件者位址這麼做。</span><span class="sxs-lookup"><span data-stu-id="fd392-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="fd392-118">在下列片段中，我們使用[tostring () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto 函數，在欄中的收件者電子郵件地址之前，抽選 `@` local-host。 `RecipientEmailAddress`</span><span class="sxs-lookup"><span data-stu-id="fd392-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="fd392-119">下列查詢顯示此程式碼片段的使用方式：</span><span class="sxs-lookup"><span data-stu-id="fd392-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="fd392-120">合併 IdentityInfo 資料表</span><span class="sxs-lookup"><span data-stu-id="fd392-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="fd392-121">您可以合併或加入 IdentityInfo 資料表，以取得帳戶名稱 [和其他帳戶資訊](advanced-hunting-identityinfo-table.md)。</span><span class="sxs-lookup"><span data-stu-id="fd392-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="fd392-122">下列查詢會從 [EmailEvents](advanced-hunting-emailevents-table.md) 資料表取得網路釣魚和惡意程式碼偵測清單，然後將該資訊與資料表聯起來，以取得每個收件者 `IdentityInfo` 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fd392-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="fd392-123">取得裝置資訊</span><span class="sxs-lookup"><span data-stu-id="fd392-123">Get device information</span></span>
<span data-ttu-id="fd392-124">進 [位搜尋架構](advanced-hunting-schema-tables.md) 在各種資料表中提供廣泛的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="fd392-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="fd392-125">例如 [，DeviceInfo 資料表](advanced-hunting-deviceinfo-table.md) 會根據定期匯總的事件資料，提供完整的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="fd392-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="fd392-126">此查詢會使用資料表檢查有潛在威脅的使用者 () 已登入任何裝置，然後列出這些裝置上觸發的 `DeviceInfo` `<account-name>` 警示。</span><span class="sxs-lookup"><span data-stu-id="fd392-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="fd392-127">此查詢 `kind=inner` 會用來指定 [內部連接](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)，可防止重復資料刪除的左側值 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="fd392-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="fd392-128">搜捕案例</span><span class="sxs-lookup"><span data-stu-id="fd392-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="fd392-129">收到未成功刪除電子郵件之使用者的登入活動清單</span><span class="sxs-lookup"><span data-stu-id="fd392-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="fd392-130">[使用 0 小時自動清除 ZAP (可) ](../office-365-security/zero-hour-auto-purge.md) 收到惡意電子郵件後執行清除。</span><span class="sxs-lookup"><span data-stu-id="fd392-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="fd392-131">如果 ZAP 失敗，惡意程式碼最後可能會在裝置上執行，並破壞帳戶。</span><span class="sxs-lookup"><span data-stu-id="fd392-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="fd392-132">此查詢會檢查電子郵件收件者所登入的活動是否未成功由 ZAP 處理。</span><span class="sxs-lookup"><span data-stu-id="fd392-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="fd392-133">以認證竊取為目標的網域帳戶嘗試登入</span><span class="sxs-lookup"><span data-stu-id="fd392-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="fd392-134">此查詢會先識別資料表中的所有認證存取 `AlertInfo` 通知。</span><span class="sxs-lookup"><span data-stu-id="fd392-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="fd392-135">然後，它會合並或加入資料表，其中會剖析目標帳戶的名稱，並只剖析網 `AlertEvidence` 域加入帳戶的篩選。</span><span class="sxs-lookup"><span data-stu-id="fd392-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="fd392-136">最後，它會檢查 `IdentityLogonEvents` 資料表，以取得網域加入的目標帳戶的所有登入活動。</span><span class="sxs-lookup"><span data-stu-id="fd392-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="fd392-137">檢查裝置上是否有來自已知惡意寄件者的檔案</span><span class="sxs-lookup"><span data-stu-id="fd392-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="fd392-138">假設您知道有電子郵件地址傳送惡意檔案 () ，您可以執行此查詢來判斷此寄件者的檔案是否存在於 `MaliciousSender@example.com` 您的裝置上。</span><span class="sxs-lookup"><span data-stu-id="fd392-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="fd392-139">例如，您可以使用此查詢來識別受到惡意程式碼發佈行銷活動影響的裝置。</span><span class="sxs-lookup"><span data-stu-id="fd392-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="fd392-140">在收到惡意電子郵件後檢閱登入嘗試</span><span class="sxs-lookup"><span data-stu-id="fd392-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="fd392-141">此查詢會在收到已知的惡意電子郵件後，尋找 30 分鐘內由電子郵件收件者執行的最近 10 次登入。</span><span class="sxs-lookup"><span data-stu-id="fd392-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="fd392-142">您可以使用此查詢來檢查電子郵件收件者的帳戶是否遭入侵。</span><span class="sxs-lookup"><span data-stu-id="fd392-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="fd392-143">在收到已知惡意寄件者的電子郵件後檢閱 PowerShell 活動</span><span class="sxs-lookup"><span data-stu-id="fd392-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="fd392-144">惡意電子郵件通常包含文件和其他精心設計的附件，以執行 PowerShell 命令來提供額外的承載。</span><span class="sxs-lookup"><span data-stu-id="fd392-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="fd392-145">如果您發現來自已知惡意寄件者 () 的電子郵件，您可以使用此查詢列出並檢查收到寄件者的電子郵件後 30 分鐘內發生的 `MaliciousSender@example.com` PowerShell 活動。</span><span class="sxs-lookup"><span data-stu-id="fd392-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="fd392-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="fd392-146">Related topics</span></span>
- [<span data-ttu-id="fd392-147">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="fd392-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fd392-148">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="fd392-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fd392-149">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="fd392-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="fd392-150">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="fd392-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fd392-151">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="fd392-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fd392-152">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="fd392-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
