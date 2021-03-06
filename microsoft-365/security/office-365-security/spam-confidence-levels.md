---
title: 垃圾郵件信賴等級
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解) 套用至 Exchange Online Protection (EOP) 中郵件的 SCL 的垃圾郵件信賴 (等級。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55e64c72cc472e98baa8eb71e23dafb6b276ba01
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625278"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP 中的垃圾郵件信賴等級 (SCL) 

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，輸入郵件會透過 EOP 中的垃圾郵件篩選，並指派垃圾郵件分數。 該分數對應于個別垃圾郵件信賴等級， (SCL) 新增至 X 標頭中的郵件。 較高的 SCL 表示郵件可能是垃圾郵件。 EOP 會根據 SCL 對郵件採取動作。

下表說明 SCL 的含義和郵件所採取的預設動作。 如需根據垃圾郵件篩選判定，可對郵件採取之動作的詳細資訊，請參閱在 [EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

****

|SCL|定義|預設動作|
|:---:|---|---|
|-1|郵件略過垃圾郵件篩選。 例如，郵件來自安全寄件者、傳送至安全收件者，或是來自 IP 允許清單上的電子郵件來源伺服器。 如需詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。|將郵件傳遞至收件者的收件匣。|
|0、1|垃圾郵件篩選決定郵件不是垃圾郵件。|將郵件傳遞至收件者的收件匣。|
|5，6|垃圾郵件篩選標示郵件為 **垃圾** 郵件|將郵件傳遞至收件者的 [垃圾郵件] 資料夾。|
|9 |垃圾郵件篩選標示郵件為 **高信賴垃圾郵件**|將郵件傳遞至收件者的 [垃圾郵件] 資料夾。|
|

您會注意到 SCL 2、3、4、7和8不是由垃圾郵件篩選使用。

您可以使用郵件流程規則（也稱為傳輸規則）) 來加蓋郵件上的 SCL 的 (。 如果您使用郵件流程規則來設定 SCL，則值5或6會觸發垃圾郵件的垃圾郵件篩選 **動作，而** 值7、8或9會觸發垃圾郵件篩選動作，以取得 **高信賴的垃圾郵件**。 如需詳細資訊，請參閱[使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。

類似 SCL，大量投訴層級 (BCL) 識別錯誤的大量電子郵件 (也稱為 _灰色郵件_) 。 BCL 高，表示大量郵件訊息更容易引發抱怨 (因此更可能是垃圾郵件)。 您可以在反垃圾郵件原則中設定 BCL 閾值。 如需詳細資訊，請參閱 [設定 EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)、 [大量投訴層級 (BCL) ) ](bulk-complaint-level-values.md)，以及 [垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

****

![Microsoft 365 LinkedIn 學習 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增至** 的簡短圖示？ 探索 **Microsoft 365 系統管理員和 IT 專業人員** 的免費影片課程，您可以 LinkedIn 學習。
