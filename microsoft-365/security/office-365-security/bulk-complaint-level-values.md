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
description: 系統管理員可以瞭解 Exchange Online Protection （EOP）中使用的大量規范層級（BCL）值。
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209604"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP 中的大量投訴層級（BCL）

在有信箱在 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中的 Microsoft 365 組織中，如果組織沒有 Exchange Online 信箱，EOP 會指派大量的相容性（BCL）來自大宗郵件傳送者的輸入郵件。 BCL 會新增至 X 標頭中的郵件，類似于用來識別郵件為垃圾郵件的[垃圾郵件信賴等級（SCL）](spam-confidence-levels.md) 。 較高的 BCL 表示大宗郵件可能會產生抱怨（因此可能是垃圾郵件）。 Microsoft 會同時使用內部和協力廠商來源來識別大宗郵件，並決定適當的 BCL。

大量的寄件者會因傳送模式、內容建立和收件者購買慣例而異。 良好的大宗郵件傳送會透過相關的內容傳送至其訂閱者。 這些郵件會從收件者中產生少量的投訴。 其他大宗郵件傳送程式會傳送近類似垃圾郵件的未主動訊息，並從收件者產生許多投訴。 大宗郵件寄件者的郵件，稱為大宗郵件或灰階郵件。

 垃圾郵件篩選會將郵件標示為以 BCL 閾值（預設值或您指定的值）為基礎的**電子郵件**，並對郵件採取指定的動作（預設動作會將郵件傳遞至收件者的 [垃圾郵件] 資料夾）。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)和[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

下表說明 BCL 閾值。

|||
|:---:|---|
|**BCL**|**描述**|
|0|郵件並非來自大量寄件者。|
|1、2、3|郵件來自產生少量投訴的大量寄件者。|
|4、5、6、7|郵件來自大量寄件者，該寄件者會產生混和數目的投訴。|
|8, 9|郵件來自大量寄件者，其會產生大量的投訴。|
|
