---
title: 大量投訴層級值
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解大量抱怨層級 (BCL) Exchange Online Protection (EOP) 中所用的值。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537940"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP 中的大量投訴層級 (BCL) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，EOP 會指派大量的投訴等級 (BCL) 到大宗郵件傳送的輸入郵件。 BCL 會新增至 X 標頭中的郵件，類似于 [垃圾郵件信賴等級 (SCL) ](spam-confidence-levels.md) ，用來識別郵件為垃圾郵件。 較高的 BCL 表示大宗郵件可能會產生抱怨 (，因此很可能是) 的垃圾郵件。 Microsoft 會同時使用內部和協力廠商來源來識別大宗郵件，並決定適當的 BCL。

大量的寄件者會因傳送模式、內容建立和收件者購買慣例而異。 良好的大宗郵件傳送會透過相關的內容傳送至其訂閱者。 這些郵件會從收件者中產生少量的投訴。 其他大宗郵件傳送程式會傳送近類似垃圾郵件的未主動訊息，並從收件者產生許多投訴。 大宗郵件寄件者的郵件，稱為大宗郵件或灰階郵件。

 垃圾郵件篩選會將郵件標示為以 BCL 閾值為基礎的 **電子郵件** (預設值或您指定的值) 並對郵件採取指定的動作 (預設動作會將郵件傳遞至收件者的 [垃圾郵件] 資料夾) 。 如需詳細資訊，請參閱 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md) 和 [垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

您可以使用 [承租人允許/封鎖] 清單，設定大宗郵件篩選的例外狀況。 來自指定網域中寄件者的郵件，不會收到反垃圾郵件原則中 **大量電子** 郵件篩選判定的動作。 如需詳細資訊，請參閱 [管理承租人 Allow/封鎖清單](tenant-allow-block-list.md)。

下表說明 BCL 閾值。

****

|BCL|描述|
|:---:|---|
|0|郵件並非來自大量寄件者。|
|1、2、3|郵件來自產生少量投訴的大量寄件者。|
|4、5、6、7<sup>\*</sup>|郵件來自大量寄件者，該寄件者會產生混和數目的投訴。|
|8, 9|郵件來自大量寄件者，其會產生大量的投訴。|
|

<sup>\*</sup> 這是反垃圾郵件原則中使用的預設臨界值。
