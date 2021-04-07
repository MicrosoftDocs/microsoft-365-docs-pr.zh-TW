---
title: 輸出傳遞集區
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 瞭解如何使用傳遞集區來保護 Microsoft 365 資料中心的電子郵件伺服器信譽。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599908"
---
# <a name="outbound-delivery-pools"></a>輸出傳遞集區

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。 例如，在內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Microsoft 365 傳送輸出郵件，或遭到受損的 Microsoft 365 帳戶。 攻擊者也會嘗試透過 Microsoft 365 轉寄來轉送郵件，以避免偵測。

這些案例會產生出現在協力廠商 blocklists 上受影響的 Microsoft 365 資料中心伺服器的 IP 位址。 使用這些 blocklists 的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。

## <a name="high-risk-delivery-pool"></a>高風險傳遞集區
若要防止這種情況，所有來自 Microsoft 365 datacenter server 但決定為垃圾郵件的外寄郵件，或超過 [服務](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 之傳送限制或 [輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) 的所有外寄郵件都會透過 _高風險傳遞集_ 區來傳送。

「高風險傳遞集區」是外寄電子郵件的個別 IP 位址集區，只用于傳送「低品質」郵件 (例如，垃圾郵件和 [退信攻擊](backscatter-messages-and-eop.md)) 。 使用 [高風險傳遞集區]，可防止輸出電子郵件的一般 IP 位址集區傳送垃圾郵件。 外寄電子郵件的一般 IP 位址集區維持「高品質」郵件的信譽，這會降低這些 IP 位址會出現在 IP blocklists 上的可能性。

在 blocklists 中，高風險傳遞集區中的 IP 位址會保留在 IP 上的可能性，但這是設計方式。 不會保證傳遞給預定的收件者，因為許多電子郵件組織不會接受高風險傳遞集區中的郵件。

如需詳細資訊，請參閱 [控制輸出垃圾郵件](outbound-spam-controls.md)。

> [!NOTE]
> 來源電子郵件網域沒有記錄，而且公用 DNS 中未定義任何 MX 記錄的郵件，無論其垃圾郵件或傳送限制，都永遠都透過高風險傳遞集區路由傳送。

### <a name="bounce-messages"></a>退回郵件

輸出的高風險傳遞集區可管理所有未傳遞回報 (也稱為 NDRs、退回郵件、傳遞狀態通知或 DSNs) 的傳遞。

NDRs 中的電湧可能原因包括：

- 會影響使用服務之客戶之一的電子欺騙活動。
- 目錄收集攻擊。
- 垃圾郵件攻擊。
- 欺詐的電子郵件伺服器。

所有這些問題都會造成服務處理的 NDRs 數量突然增加。 許多情況下，這些 NDRs 似乎是對其他電子郵件伺服器和服務 (也稱為 _[退信攻擊](backscatter-messages-and-eop.md)_) 的垃圾郵件。
