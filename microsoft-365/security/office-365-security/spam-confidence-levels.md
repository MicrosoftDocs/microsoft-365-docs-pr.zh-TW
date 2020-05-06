---
title: 垃圾郵件信賴等級
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 在本文中，系統管理員可以瞭解垃圾郵件信賴等級（SCL）如何判斷郵件的 likeliness 為垃圾郵件。
ms.openlocfilehash: 9448b1fd99878dbb85bc8699afc0719bc62dd951
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035245"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>Office 365 中的垃圾郵件信賴等級（SCL）

當 Microsoft 365 （Exchange Online 或獨立 Exchange online Protection （EOP）（沒有 Exchange Online 信箱）收到輸入電子郵件訊息時，郵件會透過垃圾郵件篩選功能，並被指派垃圾郵件分數。 該分數對應于個別垃圾郵件信賴等級（SCL），它會新增至 X 標頭中的郵件。 較高的 SCL 表示郵件可能是垃圾郵件。 服務會根據 SCL 的郵件採取動作。

下表說明 SCL 的含義和郵件所採取的預設動作。 如需根據垃圾郵件篩選判定，可對郵件採取之動作的詳細資訊，請參閱 Configure the anti-spam[原則 In Office 365](configure-your-spam-filter-policies.md)。

||||
|:---:|---|---|
|**SCL**|**定義**|**預設動作**|
|-1|郵件略過垃圾郵件篩選。 例如，郵件來自安全寄件者、傳送至安全收件者，或是來自 IP 允許清單上的電子郵件來源伺服器。 如需詳細資訊，請參閱[在 Office 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。|將郵件傳遞至收件者的收件匣。|
|0、1|垃圾郵件篩選決定郵件不是垃圾郵件。|將郵件傳遞至收件者的收件匣。|
|5，6|垃圾郵件篩選標示郵件為**垃圾**郵件|將郵件傳遞至收件者的 [垃圾郵件] 資料夾。|
|9 |垃圾郵件篩選標示郵件為**高信賴垃圾郵件**|將郵件傳遞至收件者的 [垃圾郵件] 資料夾。|
|

您會注意到 SCL 2、3、4、7和8不是由垃圾郵件篩選使用。

您可以使用郵件流程規則（也稱為傳輸規則）來標記郵件上的 SCL。 如果您使用郵件流程規則來設定 SCL，則值5或6會觸發垃圾郵件的垃圾郵件篩選**動作，而**值7、8或9會觸發垃圾郵件篩選動作，以取得**高信賴的垃圾郵件**。 如需詳細資訊，請參閱[使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

類似 SCL，大量投訴層級（BCL）會識別錯誤的大量大量電子郵件（也稱為_灰色郵件_）。 較高的 BCL 表示大宗郵件訊息很可能會產生抱怨（因此可能是垃圾郵件）。 您可以在反垃圾郵件原則中設定 BCL 閾值。 如需詳細資訊，請參閱設定 office 365 中的[反垃圾郵件原則](configure-your-spam-filter-policies.md)、[大量投訴層級（BCL）中的 office 365）](bulk-complaint-level-values.md)，以及[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

||
|:-----|
|![LinkedIn Learning 的短圖示](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索適用于**Microsoft 365 系統管理員和 IT 專業人員**的免費影片課程，並 LinkedIn 的知識。|
