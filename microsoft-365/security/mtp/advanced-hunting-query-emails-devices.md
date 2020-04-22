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
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ec7f9083401fdf7a2114d99ddd2dcc009411e34b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633504"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>搜捕所有裝置和電子郵件的威脅

**適用於：**
- Microsoft 威脅防護



Microsoft 威脅防護中的[高級搜尋](advanced-hunting-overview.md)可讓您主動搜尋您的 Windows 裝置和 Microsoft 電子郵件中的威脅。 以下是一些搜捕案例和範例查詢，可協助您探索如何建立涵蓋裝置和電子郵件的查詢。

## <a name="obtain-user-accounts-from-email-addresses"></a>從電子郵件地址取得使用者帳戶
在[涵蓋裝置和電子郵件的表格](advanced-hunting-schema-tables.md)建立查詢時，您可能需要取得寄件者或收件者電子郵件地址的使用者帳戶名稱。 若要這麼做，請使用電子郵件地址的*本機主機*：

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

我們會在後續的案例中使用此正規化技術。

## <a name="hunting-scenarios"></a>搜捕案例

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>檢查裝置上是否有來自已知惡意寄件者的檔案
假設您知道某電子郵件地址傳送惡意檔案，您可以執行此查詢來判斷來自此寄件者的檔案是否存在於您的裝置上。 例如，您可以使用此查詢來判斷受惡意軟體發佈活動影響的裝置數量。

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>在收到惡意電子郵件後檢閱登入嘗試
此查詢會在收到已知的惡意電子郵件後，尋找 30 分鐘內由電子郵件收件者執行的最近 10 次登入。 您可以使用此查詢來檢查電子郵件收件者的帳戶是否遭入侵。

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>在收到已知惡意寄件者的電子郵件後檢閱 PowerShell 活動
惡意電子郵件通常包含文件和其他精心設計的附件，以執行 PowerShell 命令來提供額外的承載。 如果您發現來自已知惡意寄件者的電子郵件，可以使用此查詢來列出及檢閱收到該寄件者的電子郵件後 30 分鐘內發生的 PowerShell 活動。  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
