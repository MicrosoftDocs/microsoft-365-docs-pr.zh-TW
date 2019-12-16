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
# <a name="hunt-for-threats-across-devices-and-emails"></a>搜捕所有裝置和電子郵件的威脅

**適用於：**
- Microsoft 威脅防護

[!include[Prerelease information](prerelease.md)]

Microsoft 威脅防護的[進階搜捕](advanced-hunting-overview.md)能讓您主動搜捕 Windows 裝置和 Office 365 電子郵件的威脅。 以下是一些搜捕案例和範例查詢，可協助您探索如何建立涵蓋裝置和電子郵件的查詢。

## <a name="obtain-user-accounts-from-email-addresses"></a>從電子郵件地址取得使用者帳戶
在[涵蓋裝置和電子郵件的表格](advanced-hunting-schema-tables.md)建立查詢時，您可能需要取得寄件者或收件者電子郵件地址的使用者帳戶名稱。 若要這麼做，請使用電子郵件地址的*本機主機*：

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

我們會在後續的案例中使用此正規化技術。

## <a name="hunting-scenarios"></a>搜捕案例

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>檢查裝置上是否有來自已知惡意寄件者的檔案
假設您知道某電子郵件地址傳送惡意檔案，您可以執行此查詢來判斷來自此寄件者的檔案是否存在於您的裝置上。 例如，您可以使用此查詢來判斷受惡意軟體發佈活動影響的裝置數量。

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>在收到惡意電子郵件後檢閱登入嘗試
此查詢會在收到已知的惡意電子郵件後，尋找 30 分鐘內由電子郵件收件者執行的最近 10 次登入。 您可以使用此查詢來檢查電子郵件收件者的帳戶是否遭入侵。

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>在收到已知惡意寄件者的電子郵件後檢閱 PowerShell 活動
惡意電子郵件通常包含文件和其他精心設計的附件，以執行 PowerShell 命令來提供額外的承載。 如果您發現來自已知惡意寄件者的電子郵件，可以使用此查詢來列出及檢閱收到該寄件者的電子郵件後 30 分鐘內發生的 PowerShell 活動。  

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

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)