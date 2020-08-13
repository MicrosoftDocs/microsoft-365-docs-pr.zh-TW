---
title: 大量投訴層級值
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 中所用的大量規范層級 (BCL) 數值。
ms.openlocfilehash: 19fa7172bd242852d03822c588e163b7a13f9201
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653206"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP 中的大量投訴層級 (BCL) 

在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，EOP 會指派大量相容層級 (BCL) 至來自大宗郵件寄件者的輸入郵件。 BCL 會新增至 X 標頭中的郵件，類似于[垃圾郵件信賴等級 (SCL) ](spam-confidence-levels.md) ，用來識別郵件為垃圾郵件。 較高的 BCL 表示大宗郵件可能會產生抱怨 (，因此很可能是) 的垃圾郵件。 Microsoft 會同時使用內部和協力廠商來源來識別大宗郵件，並決定適當的 BCL。

大量的寄件者會因傳送模式、內容建立和收件者購買慣例而異。 良好的大宗郵件傳送會透過相關的內容傳送至其訂閱者。 這些郵件會從收件者中產生少量的投訴。 其他大宗郵件傳送程式會傳送近類似垃圾郵件的未主動訊息，並從收件者產生許多投訴。 大宗郵件寄件者的郵件，稱為大宗郵件或灰階郵件。

 垃圾郵件篩選會將郵件標示為以 BCL 閾值為基礎的**電子郵件** (預設值或您指定的值) 並對郵件採取指定的動作 (預設動作會將郵件傳遞至收件者的 [垃圾郵件] 資料夾) 。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)和[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

下表說明 BCL 閾值。

****

|BCL|描述|
|:---:|---|
|0|郵件並非來自大量寄件者。|
|1、2、3|郵件來自產生少量投訴的大量寄件者。|
|4、5、6、7|郵件來自大量寄件者，該寄件者會產生混和數目的投訴。|
|8, 9|郵件來自大量寄件者，其會產生大量的投訴。|
|
