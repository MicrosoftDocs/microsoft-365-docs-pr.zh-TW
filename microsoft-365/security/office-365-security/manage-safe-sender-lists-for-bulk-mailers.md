---
title: 管理大量郵件寄件者的安全寄件者清單
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理方式處理。 服務會藉由檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，Outlook 會在使用者的安全寄件者清單中新增 RFC 5322.From 地址時遵守安全寄件者和網域。 (請注意： 此服務會檢查是否有 5321.MailFrom 地址和 5322.From 地址的封鎖寄件者和網域。)
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598940"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>管理大量郵件寄件者的安全寄件者清單

如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理方式處理。 Office 365 服務遵守區別發音安全寄件者和網域藉由檢查`RFC 5321.MailFrom`地址和`RFC 5322.From`時 Outlook 新增處理`RFC 5322.From`至使用者的安全寄件者清單的地址。 (附註： 此服務會檢查兩者`5321.MailFrom`地址和`5322.From`封鎖寄件者和網域的地址。)

`SMTP MAIL FROM`地址，又稱為`RFC 5321.MailFrom address`，是用來執行 SPF 檢查電子郵件地址和如果無法傳遞郵件，退回的郵件會傳遞至的路徑。 它是放入此電子郵件地址`Return-Path`預設郵件標頭，但有可能的寄件者指定不同`Return-Path`地址。

`From:`地址的郵件標頭，又稱為`RFC 5322.From`位址，是會顯示在郵件用戶端 Outlook 之類的電子郵件地址。

最多的時間，`5321.MailFrom`和`5322.From`都是相同的地址。 這是一般的人對人通訊。 不過，當電子郵件傳送代表其他人時，會經常不同位址。 這通常是最常的大量電子郵件。

例如，假設 Blue Yonder Airlines 已僱用 Margie 的旅行寄出其電子郵件通知。 您然後收到的訊息收件匣中從寄件者 blueyonder@news.blueyonderairlines.com。 在此範例中：

- `5321.MailFrom`地址是 blueyonder.airlines@margiestravel.com。

- `5322.From`地址為 blueyonder@news.blueyonderairlines.com，也就是您會看到在 Outlook 中。

若要避免這個訊息篩選，您可以：

- **以使用者身分**： 新增`RFC 5322.From`為在 Outlook 中的安全寄件者的地址。

- **身為系統管理員**： 設定[郵件流程規則](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)（也稱為傳輸規則）。
