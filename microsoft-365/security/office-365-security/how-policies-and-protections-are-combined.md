---
title: Office 365 中的電子郵件保護順序和優先順序
keywords: 安全性，惡意程式碼，Microsoft 365，M365，安全性中心，ATP，Microsoft Defender ATP，Office 365 ATP，Azure ATP
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
ms.collection:
- M365-security-compliance
description: 說明 Office 365 保護的應用程式順序，以及保護原則中的優先順序值如何決定所套用的原則。
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537410"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Office 365 中的電子郵件保護順序和優先順序

在 Office 365 中，輸入的電子郵件會由其評估，因此可能會以多種保護形式（惡意程式碼、垃圾郵件、網路釣魚等）加以標記。 在此活動中，可能很難判斷已套用的原則和順序。

一般說來，套用至郵件的原則會在**CAT （類別）** 屬性的**X-Forefront-Antispam-Report**標頭中識別。 如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。

有兩個主要因素會決定要套用至郵件的原則：

- **電子郵件保護類型的優先順序**：此順序並不是可設定的，如下表所述：

  |||||
  |---|---|---|---|
  |**優先順序**|**電子郵件保護**|**類別**|**要管理的位置**|
  |1 |惡意程式碼|CAT： MALW|[在 Office 365 中設定反惡意程式碼原則](configure-anti-malware-policies.md)|
  |2 |網路釣魚|CAT： PHSH|[設定 Office 365 的反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |3 |高信賴度的垃圾郵件|CAT： HSPM|[設定 Office 365 的反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |4 |詐騙|CAT：欺騙|[在 Office 365 中設定假冒情報](learn-about-spoof-intelligence.md)|
  |5 |垃圾郵件|CAT： SPM|[設定 Office 365 的反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |6 |大量|CAT：大量|[設定 Office 365 的反垃圾郵件原則](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|網域模仿（受保護的使用者）|DIMP|[在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)|
  |8：00<sup>\*</sup>|使用者類比（受保護的網域）|UIMP|[在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>這些功能只有在 ATP 反網路釣魚原則中才能使用。

- **原則的優先順序**：針對每一種保護類型（反垃圾郵件、反惡意程式碼、反網路釣魚等等），都有一個適用于每個人的預設原則，但您通常可以建立適用于特定使用者的自訂原則。 每個自訂原則都有一個優先順序值，以決定原則的套用順序。 預設原則永遠套用於最後。

  如果使用者是在相同類型的多個原則中定義，則只有具有最高優先順序的原則適用于。 不會為使用者評估任何其他類型的原則（包括預設原則）。

例如，請考慮下列**適用于相同使用者**的 ATP 反網路釣魚原則，以及識別為使用者模擬和欺騙的郵件：

  |||||
  |---|---|---|---|
  |**ATP 反網路釣魚原則**|**優先順序**|**使用者模擬**|**反詐騙**|
  |原則 A|1 |開啟|關閉|
  |原則 B|2 |關閉|開啟|
  |

1. 郵件會標示並視為欺騙性，因為哄騙具有比使用者模擬（8）更高的優先順序（4）。
2. 原則 A 會套用至使用者，因為其優先順序高於原則 B。
3. 根據原則 A 中的設定，不會對郵件採取任何動作，因為會在原則中關閉反欺騙功能。
4. 原則處理會停止，因此原則 B 永遠不會套用至使用者。

因為相同的使用者可能會故意或無意中包含相同類型的多個自訂原則，所以請針對自訂原則使用下列設計原則：

- 指派較高優先順序的原則套用至少量的使用者，以及套用至大量使用者之原則的優先順序較低。 請記住，預設原則永遠會最後套用。
- 設定較高優先順序的原則，使其具有比低優先順序原則更嚴格或更多的特殊設定。
- 請考慮使用較少的自訂原則（只對需要更嚴格或更多特殊設定的使用者使用自訂原則）。
