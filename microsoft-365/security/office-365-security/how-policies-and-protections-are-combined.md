---
title: 電子郵件保護的順序和優先順序
keywords: 安全性，惡意程式碼，Microsoft 365，M365，安全性中心，ATP，Microsoft Defender ATP，Office 365 ATP，Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解 Exchange Online Protection (EOP) 中的保護應用程式順序，以及保護原則中的優先順序值如何決定所套用的原則。
ms.openlocfilehash: a18234344e1100f3b6a03c10e970c8195e53e7df
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760563"
---
# <a name="order-and-precedence-of-email-protection"></a>電子郵件保護的順序和優先順序

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，輸入的電子郵件可能會以多種保護形式進行標記。 例如，EOP 中內建的反網路釣魚原則，可供所有 Microsoft 365 客戶使用，以及適用于 Microsoft Defender for Office 365 客戶的更強健的反網路釣魚原則。 郵件也會透過多個偵測掃描進行惡意程式碼、垃圾郵件、網路釣魚等的掃描。在此活動中，可能會對套用的原則產生一些混淆。

一般說來，套用至郵件的原則會在 **CAT (Category)** 屬性的 **X-Forefront-Antispam-Report** 標頭中識別。 如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。

有兩個主要因素會決定要套用至郵件的原則：

- **電子郵件保護類型的優先順序**：此順序並不是可設定的，如下表所述：

  ****

  |優先順序|電子郵件保護|類別|要管理的位置|
  |---|---|---|---|
  |1 |惡意程式碼|CAT： MALW|[在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)|
  |2 |網路釣魚|CAT： PHSH|[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |3 |高信賴度的垃圾郵件|CAT： HSPM|[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |4 |詐騙|CAT：欺騙|[在 EOP 中設定欺騙情報](learn-about-spoof-intelligence.md)|
  |位<sup>\*</sup>| (受保護的使用者模擬使用者模擬) |UIMP|[在 Microsoft Defender for Office 365 中設定反網路釣魚原則](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|網域模擬 (受保護的網域) |DIMP|[在 Microsoft Defender for Office 365 中設定反網路釣魚原則](configure-atp-anti-phishing-policies.md)|
  |7 |垃圾郵件|CAT： SPM|[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |8 |大量|CAT：大量|[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> 這些功能僅適用于 Office 365 的 Microsoft Defender 中的反網路釣魚原則。

- **原則的優先順序**：針對每個防護類型 (反垃圾郵件、反惡意程式碼、反網路釣魚等 ) ，都有一個適用于每個人的預設原則，但您可以建立適用于特定使用者的自訂原則。 每個自訂原則都有一個優先順序值，以決定原則的套用順序。 預設原則永遠套用於最後。

  如果使用者是在相同類型的多個原則中定義，則只有具有最高優先順序的原則適用于。 不會評估該類型的任何其餘原則 (包括預設原則) 。

例如，請考慮下列 Microsoft Defender for Office 365 的反網路釣魚原則， **該原則套用至相同的使用者**，以及識別為使用者模擬和欺騙的郵件：

  ****

  |原則名稱|優先順序|使用者模擬|反詐騙|
  |---|---|---|---|
  |原則 A|1 |開啟|關閉|
  |原則 B|2 |關閉|開啟|
  |

1. 郵件會標示及視為欺騙性，因為哄騙具有比使用者模擬 (5) 更高優先順序的 (4) 。
2. 原則 A 會套用至使用者，因為其優先順序高於原則 B。
3. 根據原則 A 中的設定，不會對郵件採取任何動作，因為會在原則中關閉反欺騙功能。
4. 原則處理會停止，因此原則 B 永遠不會套用至使用者。

因為相同的使用者可能會故意或無意中包含相同類型的多個自訂原則，所以請針對自訂原則使用下列設計原則：

- 指派較高優先順序的原則套用至少量的使用者，以及套用至大量使用者之原則的優先順序較低。 請記住，預設原則永遠會最後套用。
- 設定較高優先順序的原則，使其具有比低優先順序原則更嚴格或更多的特殊設定。
- 請考慮使用較少的自訂原則 (只對需要更嚴格或更多專用設定) 的使用者使用自訂原則。
