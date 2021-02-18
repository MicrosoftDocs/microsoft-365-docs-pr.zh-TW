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
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289802"
---
# <a name="outbound-delivery-pools"></a>輸出傳遞集區

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。 例如，在內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Microsoft 365 傳送輸出郵件，或遭到受損的 Microsoft 365 帳戶。 攻擊者也會嘗試透過 Microsoft 365 轉寄來轉送郵件，以避免偵測。

這些案例會產生出現在協力廠商封鎖清單上之受影響的 Microsoft 365 datacenter 伺服器的 IP 位址。 使用這些封鎖清單的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。

## <a name="high-risk-delivery-pool"></a>高風險傳遞集區
若要防止這種情況，所有來自 Microsoft 365 datacenter server 但決定為垃圾郵件的外寄郵件，或超過 [服務](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 之傳送限制或 [輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) 的所有外寄郵件都會透過 _高風險傳遞集_ 區來傳送。

「高風險傳遞集區」是外寄電子郵件的個別 IP 位址集區，只用于傳送「低品質」郵件 (例如，垃圾郵件和 [退信攻擊](backscatter-messages-and-eop.md)) 。 使用 [高風險傳遞集區]，可防止輸出電子郵件的一般 IP 位址集區傳送垃圾郵件。 外寄電子郵件的一般 IP 位址集區維持「高品質」郵件的信譽，這會降低這些 IP 位址會出現在 IP 封鎖清單上的可能性。

在此情況下，高風險傳遞集區中的 IP 位址會保留在 IP 封鎖清單上，但這是由設計所組成。 不會保證傳遞給預定的收件者，因為許多電子郵件組織不會接受高風險傳遞集區中的郵件。

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

## <a name="relay-pool"></a>轉送集區

轉寄或轉送到 Microsoft 365 的郵件會以特殊轉送集區傳送，因為最後目的地不應該將 Microsoft 365 視為實際寄件者。 請務必隔離此流量，因為 autoforwarding 或將電子郵件轉送至 Microsoft 365 時，有合法和不正確案例。 與高風險傳遞集區類似，中繼郵件使用個別的 IP 位址集區。 此位址集區不會發佈，因為它可能經常變更。

Microsoft 365 需要驗證原始寄件者是否合法，讓我們可以自信地傳遞轉寄的郵件。 為了做到這一點，電子郵件驗證 (SPF、DKIM 及) DMARC，都必須傳遞給我們的郵件。 在我們可驗證寄件者的情況下，我們會使用寄件者修正，協助接收器知道轉寄的郵件來自信任的來源。 您可以深入瞭解該作業的運作方式及可執行檔動作，以協助確保傳送網域在 [寄件者修正模式中 (SRS) ](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)中的驗證。
