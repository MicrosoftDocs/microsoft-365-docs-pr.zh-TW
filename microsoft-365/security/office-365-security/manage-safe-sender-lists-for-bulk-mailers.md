---
title: 管理大量郵件寄件者的安全寄件者清單
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
ms.openlocfilehash: f73cc3fc88318c4f625bf5579f73d92625624fd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078110"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>管理大量郵件寄件者的安全寄件者清單

如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理方式處理。 Office 365 服務會藉由檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，Outlook 會在使用者的安全寄件者清單中新增 RFC 5322.From 地址時遵守安全寄件者和網域。 (請注意： 此服務會檢查是否有 5321.MailFrom 地址和 5322.From 地址的封鎖寄件者和網域。)
  
SMTP 郵件從地址，又稱為 RFC 5321.MailFrom 地址，是用來執行 SPF 檢查電子郵件地址和如果無法傳遞郵件，退回的郵件會傳遞至的路徑。 雖然可以指定不同的形式傳回路徑地址寄件者是根據預設，在郵件標頭中傳回路徑進入此電子郵件地址。
  
[從： 郵件標頭，又稱為 RFC 5322.From 地址的地址會隨即出現在郵件用戶端 Outlook 之類的電子郵件地址。
  
大部分的時間、 5321.MailFrom 和 5322.From 地址都相同。 這是一般的人對人通訊。 不過，當電子郵件傳送代表其他人時，會經常不同位址。 這通常是最常的大量電子郵件。
  
例如，假設航空公司 Blue Yonder Airlines 具有收起出 Margie 的旅行寄出其電子郵件通知。 您然後收到的訊息收件匣中從寄件者 blueyonder@news.blueyonderairlines.com。 在此情況下，5321.MailFrom 地址是 blueyonder.airlines@margiestravel.com，且 blueyonder@news.blueyonderairlines.com 5322.From 地址也就是，您在 Outlook 中看到。 因為服務遵守區別發音 RFC 5322.From 地址，若要避免這個訊息取得篩選，您可以新增 RFC 5322.From 地址中 （如使用者） 的 Outlook 安全寄件者或如果您是在[反垃圾郵件所示設定郵件流程規則系統管理員保護](anti-spam-protection.md)區段。
  

