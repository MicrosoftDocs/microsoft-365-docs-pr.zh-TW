---
title: 使用進階搜捕尋找裝置和電子郵件的威脅
description: 研究常見的捕尋案例和涵蓋裝置與電子郵件的範例查詢。
keywords: 進階搜捕, Office365 資料, Windows 裝置, Office365 電子郵件正常化, 電子郵件, 威脅搜捕, 網路威脅搜捕, 搜尋, 查詢, 遙測, Microsoft 365, Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b374aac84b309d18a88ee7248021b50a893e120c
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910901"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="dde42-104">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="dde42-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="dde42-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="dde42-105">**Applies to:**</span></span>
- <span data-ttu-id="dde42-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dde42-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="dde42-107">Microsoft 威脅防護的[進階搜捕](advanced-hunting-overview.md)能讓您主動搜捕 Windows 裝置和 Office 365 電子郵件的威脅。</span><span class="sxs-lookup"><span data-stu-id="dde42-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="dde42-108">以下是一些搜捕案例和範例查詢，可協助您探索如何建立涵蓋裝置和電子郵件的查詢。</span><span class="sxs-lookup"><span data-stu-id="dde42-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="dde42-109">從電子郵件地址取得使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="dde42-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="dde42-110">在[涵蓋裝置和電子郵件的表格](advanced-hunting-schema-tables.md)建立查詢時，您可能需要取得寄件者或收件者電子郵件地址的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="dde42-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="dde42-111">若要這麼做，請使用電子郵件地址的*本機主機*：</span><span class="sxs-lookup"><span data-stu-id="dde42-111">To do this use the *local-host* from the email address:</span></span>

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="dde42-112">我們會在後續的案例中使用此正規化技術。</span><span class="sxs-lookup"><span data-stu-id="dde42-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="dde42-113">搜捕案例</span><span class="sxs-lookup"><span data-stu-id="dde42-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="dde42-114">檢查裝置上是否有來自已知惡意寄件者的檔案</span><span class="sxs-lookup"><span data-stu-id="dde42-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="dde42-115">假設您知道某電子郵件地址傳送惡意檔案，您可以執行此查詢來判斷來自此寄件者的檔案是否存在於您的裝置上。</span><span class="sxs-lookup"><span data-stu-id="dde42-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="dde42-116">例如，您可以使用此查詢來判斷受惡意軟體發佈活動影響的裝置數量。</span><span class="sxs-lookup"><span data-stu-id="dde42-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
FileCreationEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="dde42-117">在收到惡意電子郵件後檢閱登入嘗試</span><span class="sxs-lookup"><span data-stu-id="dde42-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="dde42-118">此查詢會在收到已知的惡意電子郵件後，尋找 30 分鐘內由電子郵件收件者執行的最近 10 次登入。</span><span class="sxs-lookup"><span data-stu-id="dde42-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="dde42-119">您可以使用此查詢來檢查電子郵件收件者的帳戶是否遭入侵。</span><span class="sxs-lookup"><span data-stu-id="dde42-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
LogonEvents
| project LogonTime = EventTime, AccountName, ComputerName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="dde42-120">在收到已知惡意寄件者的電子郵件後檢閱 PowerShell 活動</span><span class="sxs-lookup"><span data-stu-id="dde42-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="dde42-121">惡意電子郵件通常包含文件和其他精心設計的附件，以執行 PowerShell 命令來提供額外的承載。</span><span class="sxs-lookup"><span data-stu-id="dde42-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="dde42-122">如果您發現來自已知惡意寄件者的電子郵件，可以使用此查詢來列出及檢閱收到該寄件者的電子郵件後 30 分鐘內發生的 PowerShell 活動。</span><span class="sxs-lookup"><span data-stu-id="dde42-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
ProcessCreationEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = EventTime, AccountName, ComputerName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="dde42-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="dde42-123">Related topics</span></span>
- [<span data-ttu-id="dde42-124">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="dde42-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dde42-125">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="dde42-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dde42-126">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="dde42-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dde42-127">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="dde42-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dde42-128">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="dde42-128">Apply design best practices.</span></span>](advanced-hunting-best-practices.md)