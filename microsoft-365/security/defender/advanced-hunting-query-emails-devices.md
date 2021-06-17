---
title: 使用高級搜尋來尋找跨裝置、電子郵件、應用程式和身分識別的威脅
description: 研究常見搜尋案例，以及涵蓋裝置、電子郵件、應用程式和身分識別的範例查詢。
keywords: advanced 搜尋，Office365 資料，Windows 裝置，Office365 電子郵件正規化，電子郵件，應用程式，身分識別，威脅搜尋，網路威脅搜尋，搜尋，查詢，遙測，Microsoft 365，Microsoft 365 Defender
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
ms.openlocfilehash: aacd0745ff507356035f8f460ed2b4307e9da6ed
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964870"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="8a44b-104">跨裝置、電子郵件、應用程式和身分識別搜捕威脅</span><span class="sxs-lookup"><span data-stu-id="8a44b-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a44b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8a44b-105">**Applies to:**</span></span>
- <span data-ttu-id="8a44b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a44b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8a44b-107">Microsoft 365 Defender 中的[高級搜尋](advanced-hunting-overview.md)可讓您主動搜尋整個威脅：</span><span class="sxs-lookup"><span data-stu-id="8a44b-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="8a44b-108">Microsoft Defender for Endpoint 所管理的裝置</span><span class="sxs-lookup"><span data-stu-id="8a44b-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="8a44b-109">Microsoft 365 所處理的電子郵件</span><span class="sxs-lookup"><span data-stu-id="8a44b-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="8a44b-110">由 Microsoft Cloud App Security 和 Microsoft Defender 身分識別所追蹤的雲端應用程式活動、驗證事件和網域控制站活動</span><span class="sxs-lookup"><span data-stu-id="8a44b-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="8a44b-111">透過這種可視性層次，您可以快速尋找跨越網路各部分的威脅，包括抵達電子郵件或網頁的複雜入侵、提升本機許可權、取得許可權的網域認證，以及橫向移至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="8a44b-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="8a44b-112">以下是以各種搜尋案例為基礎的一般技術和範例查詢，可協助您探索在搜尋複雜威脅時，如何建立查詢。</span><span class="sxs-lookup"><span data-stu-id="8a44b-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="8a44b-113">取得實體資訊</span><span class="sxs-lookup"><span data-stu-id="8a44b-113">Get entity info</span></span>
<span data-ttu-id="8a44b-114">您可以使用這些查詢來瞭解如何快速取得使用者帳戶、裝置及檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8a44b-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="8a44b-115">從電子郵件地址取得使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8a44b-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="8a44b-116">在[涵蓋裝置和電子郵件的表格](advanced-hunting-schema-tables.md)建立查詢時，您可能需要取得寄件者或收件者電子郵件地址的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="8a44b-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="8a44b-117">您通常可以使用 *本機主機* 從電子郵件地址進行收件者或寄件者位址。</span><span class="sxs-lookup"><span data-stu-id="8a44b-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="8a44b-118">在下方的程式碼片段中，我們使用 [tostring () ](/azure/data-explorer/kusto/query/tostringfunction) Kusto 函數，先 `@` 從欄中的從收件者電子郵件地址開始解壓縮本機主機 `RecipientEmailAddress` 。</span><span class="sxs-lookup"><span data-stu-id="8a44b-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="8a44b-119">下列查詢會顯示如何使用此程式碼片段：</span><span class="sxs-lookup"><span data-stu-id="8a44b-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="8a44b-120">合併 IdentityInfo 表格</span><span class="sxs-lookup"><span data-stu-id="8a44b-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="8a44b-121">您可以合併或加入 [IdentityInfo 表格](advanced-hunting-identityinfo-table.md)，以取得帳戶名稱及其他帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="8a44b-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="8a44b-122">下列查詢會從 [EmailEvents 資料表](advanced-hunting-emailevents-table.md) 取得網路釣魚和惡意程式碼偵測清單，然後將該資訊加入表格， `IdentityInfo` 以取得每個收件者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8a44b-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="8a44b-123">取得裝置資訊</span><span class="sxs-lookup"><span data-stu-id="8a44b-123">Get device information</span></span>
<span data-ttu-id="8a44b-124">「 [高級搜尋架構](advanced-hunting-schema-tables.md) 」在各種表格中提供大量的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="8a44b-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="8a44b-125">例如， [DeviceInfo 表格](advanced-hunting-deviceinfo-table.md) 會根據定期匯總的事件資料，提供完整的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="8a44b-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="8a44b-126">此查詢會使用 `DeviceInfo` 表格來檢查是否有可能已遭破壞的使用者 (`<account-name>`) 已登入任何裝置，然後列出已在那些裝置上觸發的警示。</span><span class="sxs-lookup"><span data-stu-id="8a44b-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="8a44b-127">此查詢 `kind=inner` 會使用來指定 [內部聯接](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)，以避免重復資料刪除的左側值 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="8a44b-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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


### <a name="get-file-event-information"></a><span data-ttu-id="8a44b-128">取得檔案事件資訊</span><span class="sxs-lookup"><span data-stu-id="8a44b-128">Get file event information</span></span>

<span data-ttu-id="8a44b-129">使用下列查詢取得檔案相關事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a44b-129">Use the following query to get information on file related events.</span></span> 

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceFileEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="get-network-event-information"></a><span data-ttu-id="8a44b-130">取得網路事件資訊</span><span class="sxs-lookup"><span data-stu-id="8a44b-130">Get network event information</span></span>

<span data-ttu-id="8a44b-131">使用下列查詢取得與網路相關事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a44b-131">Use the following query to get information on network related events.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-agent-version-information"></a><span data-ttu-id="8a44b-132">取得裝置代理程式版本資訊</span><span class="sxs-lookup"><span data-stu-id="8a44b-132">Get device agent version information</span></span>

<span data-ttu-id="8a44b-133">使用下列查詢取得裝置上所執行代理程式的版本。</span><span class="sxs-lookup"><span data-stu-id="8a44b-133">Use the following query to get the version of the agent running on a device.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="example-query-for-macos-devices"></a><span data-ttu-id="8a44b-134">macOS 裝置的範例查詢</span><span class="sxs-lookup"><span data-stu-id="8a44b-134">Example query for macOS devices</span></span>

<span data-ttu-id="8a44b-135">使用下列範例查詢，查看所有執行 macOS 且 Catalina 版本超過的裝置。</span><span class="sxs-lookup"><span data-stu-id="8a44b-135">Use the following example query to see all devices running macOS with a version older than Catalina.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OSPlatform == "macOS" and  OSVersion !contains "10.15" and OSVersion !contains "11."
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-status-info"></a><span data-ttu-id="8a44b-136">取得裝置狀態資訊</span><span class="sxs-lookup"><span data-stu-id="8a44b-136">Get device status info</span></span>

<span data-ttu-id="8a44b-137">使用下列查詢取得裝置的狀態。</span><span class="sxs-lookup"><span data-stu-id="8a44b-137">Use the following query to get status of a device.</span></span> <span data-ttu-id="8a44b-138">在下列範例中，查詢會檢查裝置是否為架。</span><span class="sxs-lookup"><span data-stu-id="8a44b-138">In the following example, the query checks to see if the device is onboarded.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OnboardingStatus != "Onboarded"
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


## <a name="hunting-scenarios"></a><span data-ttu-id="8a44b-139">搜捕案例</span><span class="sxs-lookup"><span data-stu-id="8a44b-139">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="8a44b-140">列出收到未順利 zapped 之電子郵件的使用者登入活動</span><span class="sxs-lookup"><span data-stu-id="8a44b-140">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="8a44b-141">[零小時自動清除 (ZAP) ](../office-365-security/zero-hour-auto-purge.md) 會在收到惡意電子郵件之後，加以解決。</span><span class="sxs-lookup"><span data-stu-id="8a44b-141">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="8a44b-142">如果 ZAP 失敗，惡意的程式碼可能會最終在裝置上執行，並使帳戶受到損害。</span><span class="sxs-lookup"><span data-stu-id="8a44b-142">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="8a44b-143">此查詢會檢查是否有由 ZAP 未成功解決的電子郵件收件者所進行的登入活動。</span><span class="sxs-lookup"><span data-stu-id="8a44b-143">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="8a44b-144">以認證盜竊為目標的網域帳戶來取得登入嘗試</span><span class="sxs-lookup"><span data-stu-id="8a44b-144">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="8a44b-145">此查詢會先識別表格中的所有認證訪問警示 `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="8a44b-145">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="8a44b-146">然後，它會合並或連接 `AlertEvidence` 資料表，它會針對目標帳戶的名稱進行分析，並且只會針對已加入網域的帳戶篩選。</span><span class="sxs-lookup"><span data-stu-id="8a44b-146">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="8a44b-147">最後，它會檢查 `IdentityLogonEvents` 表格，以透過加入網域的目標帳戶取得所有登入活動。</span><span class="sxs-lookup"><span data-stu-id="8a44b-147">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="8a44b-148">檢查裝置上是否有來自已知惡意寄件者的檔案</span><span class="sxs-lookup"><span data-stu-id="8a44b-148">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="8a44b-149">假設您知道傳送惡意檔案 () 的電子郵件地址 `MaliciousSender@example.com` ，您可以執行此查詢，以判斷您的裝置上是否存在來自此寄件者的檔案。</span><span class="sxs-lookup"><span data-stu-id="8a44b-149">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="8a44b-150">例如，您可以使用此查詢來識別受惡意軟體發佈活動影響的裝置。</span><span class="sxs-lookup"><span data-stu-id="8a44b-150">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="8a44b-151">在收到惡意電子郵件後檢閱登入嘗試</span><span class="sxs-lookup"><span data-stu-id="8a44b-151">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="8a44b-152">此查詢會在收到已知的惡意電子郵件後，尋找 30 分鐘內由電子郵件收件者執行的最近 10 次登入。</span><span class="sxs-lookup"><span data-stu-id="8a44b-152">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="8a44b-153">您可以使用此查詢來檢查電子郵件收件者的帳戶是否遭入侵。</span><span class="sxs-lookup"><span data-stu-id="8a44b-153">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="8a44b-154">在收到已知惡意寄件者的電子郵件後檢閱 PowerShell 活動</span><span class="sxs-lookup"><span data-stu-id="8a44b-154">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="8a44b-155">惡意電子郵件通常包含文件和其他精心設計的附件，以執行 PowerShell 命令來提供額外的承載。</span><span class="sxs-lookup"><span data-stu-id="8a44b-155">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="8a44b-156">如果您知道來自已知惡意寄件者的電子郵件 (`MaliciousSender@example.com`) ，您可以使用此查詢，列出並複查從寄件者收到電子郵件後30分鐘內發生的 PowerShell 活動。</span><span class="sxs-lookup"><span data-stu-id="8a44b-156">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="8a44b-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="8a44b-157">Related topics</span></span>
- [<span data-ttu-id="8a44b-158">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="8a44b-158">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a44b-159">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="8a44b-159">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a44b-160">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="8a44b-160">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8a44b-161">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="8a44b-161">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a44b-162">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="8a44b-162">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a44b-163">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="8a44b-163">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
