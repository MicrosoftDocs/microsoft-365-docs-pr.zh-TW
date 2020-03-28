---
title: 大量投訴層級值、大宗郵件寄件者、BCL 層級、BCL 的運作方式、BCL 分級、反垃圾郵件標頭、大宗郵件篩選、停止大宗郵件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 瞭解 Office 365 中的大量規范層級（BCL）值。
ms.openlocfilehash: aa839fc1bcab141fe71c76e7f27b4f6bb23048b2
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030147"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Office 365 中的大量投訴層級（BCL）

大量的寄件者會因傳送模式、內容建立和收件者購買慣例而異。 有些是很好的大宗郵件傳送，可將相關的郵件傳送至訂閱者。 這些郵件會從收件者中產生少量的投訴。 其他大宗郵件傳送程式會傳送近類似垃圾郵件的未主動訊息，並從收件者產生許多投訴。 大宗郵件寄件者的郵件稱為大宗郵件或灰階郵件。

若要辨別來自不同類型大宗郵件的郵件，來自大宗郵件傳送至 Office 365 的輸入電子郵件（Exchange Online 或獨立 Exchange Online Protection （EOP）（未使用 Exchange Online 信箱），則會獲增值至X 標頭中的郵件。 BCL 類似于[垃圾郵件信賴等級（SCL）](spam-confidence-levels.md) ，用來識別郵件為垃圾郵件。 較高的 BCL 表示大宗郵件可能會產生抱怨（因此可能是垃圾郵件）。 Microsoft 會同時使用內部和協力廠商來源來識別大宗郵件，並決定適當的 BCL。

 垃圾郵件篩選會將郵件標示為以 BCL 閾值（預設值或您指定的值）為基礎的**電子郵件**，並對郵件採取指定的動作（預設動作會將郵件傳遞至收件者的 [垃圾郵件] 資料夾）。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)和[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

下表說明 BCL 閾值。

|||
|:---:|---|
|**BCL**|**描述**|
|0|郵件並非來自大量寄件者。|
|1、2、3|郵件來自產生少量投訴的大量寄件者。|
|4、5、6、7|郵件來自大量寄件者，該寄件者會產生混和數目的投訴。|
|8, 9|郵件來自大量寄件者，其會產生大量的投訴。|
|
