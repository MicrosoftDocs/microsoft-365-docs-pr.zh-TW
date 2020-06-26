---
title: Office 365 中的 ATP 防網路釣魚功能
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解屬於 Office 365 高級威脅防護的反網路釣魚功能，以提供對商用 & spear 網路釣魚攻擊的保護。
ms.openlocfilehash: dda94145dfbef7466ebd8e1fb9f01d592515f598
ms.sourcegitcommit: 5e8901e7e571f20ede04f460bd3e7077dda004ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2020
ms.locfileid: "44875412"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Office 365 中的 ATP 防網路釣魚功能

ATP 反網路釣魚是[Office 365 高級威脅防護](office-365-atp.md)的一部分。 ATP 反網路釣魚會將一組機器學習模型與冒充偵測演算法一起套用到內送郵件，以針對商品和魚叉式網路釣魚攻擊提供保護。 所有郵件都受限於一組廣泛的機器學習模型，以偵測網路釣魚郵件，以及一組用來防禦各種使用者和網域模擬攻擊的高級演算法。 ATP 反網路釣魚會根據您的 Office 365 全域或安全性管理員所設定的原則來保護您的組織。
  
若要深入瞭解，請參閱[在 Office 365 中設定反網路釣魚原則](set-up-anti-phishing-policies.md)。
  
> [!NOTE]
> ATP 反網路釣魚只有在「高級威脅防護」（包括[microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商務](https://www.microsoft.com/microsoft-365/business)版、Office 365 企業版 E5、Office 365 教育版 A5 等等）中才有提供。如果您的組織有 Office 365 訂閱，但未包含 Office 365 ATP，您可以將 ATP 購買為附加元件。 如需詳細資訊，請參閱 [Office 365 進階威脅防護方案和定價](https://products.office.com/exchange/advance-threat-protection)和 [Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (部分機器翻譯)。

## <a name="how-atp-anti-phishing-works"></a>ATP 反網路釣魚的運作方式

ATP 反網路釣魚檢查內送郵件的指示，郵件可能是網路釣魚。 每當 ATP 原則涵蓋使用者（安全的附件、安全連結或反網路釣魚）時，就會透過分析郵件的多部機器教學模型評估內送郵件，以判斷原則是否套用至郵件，並根據設定的原則採取適當的動作。
  
ATP 反網路釣魚允許 Office 365 全域管理員或安全性系統管理員定義原則，以防範包含使用者或網域模擬的網路釣魚攻擊。 （或兩者）。 Office 365 全域系統管理員或安全性系統管理員會在原則中定義使用者和網域應如何使用固定的使用者或網域清單，或透過信箱智慧加以保護，以防範模仿攻擊。 信箱智慧指的是使用者的電子郵件習慣和個人連絡人的深入瞭解。 ATP 瞭解每個個別使用者如何與組織內部和外部的使用者通訊，並建立這些關聯的對應。 此對應表允許 ATP 深入瞭解如何確認正確的郵件可識別為模擬的詳細資訊。
  
ATP 反網路釣魚原則可以套用到組織中特定的一組人員或群組，或是整個網域或所有自訂網域。 若要深入瞭解，請參閱[在 Office 365 中設定反網路釣魚原則](set-up-anti-phishing-policies.md)。
  
## <a name="how-to-get-atp-anti-phishing"></a>如何取得 ATP 反網路釣魚

ATP 反網路釣魚功能是[高級威脅防護](office-365-atp.md)的一部分;不過，當反網路釣魚原則定義時，ATP 反網路釣魚防護會套用。 （其中一個範例是類比型原則。）請參閱[在 Office 365 中設定反網路釣魚原則](set-up-anti-phishing-policies.md)。
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>如何知道 ATP 反網路釣魚是否已到位

必須定義 ATP 反網路釣魚原則，保護功能才能生效。 請先檢查此項，以確認已就地保護。

此外，報告可用於示範服務對您組織的運作方式。 若要深入瞭解，請參閱[View reports For Office 365 Advanced 威脅 Protection](view-reports-for-atp.md)。

針對特定使用者，ATP 反網路釣魚機器教學模型為作用中，該使用者必須是定義的[ATP 安全附件](atp-safe-attachments.md)、 [ATP 安全連結](atp-safe-links.md)或 ATP 反網路釣魚原則的一部分。 

下表說明一些範例案例。 在上述每個範例中，組織使用的是 Office 365 企業版 E5，其中包括「高級威脅防護」。
  
|**範例案例**|**ATP 反網路釣魚是否適用于此案例？**|
|:-----|:-----|
|Pat 的組織有 Office 365 企業版 E5，但沒有任何人已定義 ATP 安全附件、ATP 安全連結或 ATP 高級網路釣魚的任何原則。|否。 雖然可以使用此功能，至少必須定義一個 ATP 原則，才能讓 ATP 機器學習模型能夠運作。 若為模擬，ATP 反網路釣魚原則也必須已到位。|
|Lee 是 Contoso 銷售部門的員工。 「他的組織」有適當的 ATP 反網路釣魚原則，只適用于財務員工。|否。 在此情況下，ATP 反網路釣魚（機器模型和模擬保護）將會套用到財務員工，但其他員工（包括銷售部門）將不會。|
|昨天，Jean-francois 組織的 Office 365 系統管理員會設定一種適用于所有員工的 ATP 反網路釣魚原則。 到目前為止，Jean-francois 收到一個包含原則所涵蓋之模仿的電子郵件訊息。|是。 在此範例中，Jean-francois 具有高級威脅防護的授權，並已定義包含 Jean-francois 的 ATP 反網路釣魚原則。 新原則通常需要 30 分鐘的時間才會在資料中心之間生效；在此案例中已經過了一天，所以原則應該會生效。|

## <a name="related-topics"></a>相關主題

[Office 365 進階威脅防護](office-365-atp.md)
  
[Office 365 的防網路釣魚保護](anti-phishing-protection.md)
  
[在 Office 365 中設定反網路釣魚原則](set-up-anti-phishing-policies.md)
  
[Office 365 中的 ATP 安全連結](atp-safe-links.md)
  
[在 Office 365 中設定 ATP 安全連結原則](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)
  
[查看高級威脅防護的報告](view-reports-for-atp.md)
