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
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137712"
---
# <a name="outbound-delivery-pools"></a>輸出傳遞集區

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。 例如，內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Microsoft 365 傳送輸出郵件，或 Microsoft 365 帳戶遭到破壞。 攻擊者也會嘗試透過 Microsoft 365 轉送來轉送郵件，以避免偵測。

這些案例可能會產生協力廠商 blocklists 上受影響的 Microsoft 365 datacenter 伺服器的 IP 位址。 使用這些 blocklists 的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。

## <a name="high-risk-delivery-pool"></a>高風險傳遞集區
若要防止這種情況，來自決定是垃圾郵件的 Microsoft 365 datacenter 伺服器的所有輸出郵件，或超過 [服務](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)之傳送限制或 [輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)的所有輸出郵件都會透過 _高風險傳遞集_ 區來傳送。

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


### <a name="relay-pool"></a>轉送集區

透過特定案例中的 Microsoft 365 轉寄或轉送的郵件，將會使用特殊轉送集區傳送，因為目的地不應視為實際寄件者 Microsoft 365。 請務必隔離此電子郵件流量，因為自動轉寄或轉寄電子郵件 Microsoft 365 以外的情況會有合法且不正確案例。 與高風險傳遞集區類似，中繼郵件使用個別的 IP 位址集區。 此位址集區不會發佈，因為它可能經常變更，而且不是 Microsoft 365 發佈的 SPF 記錄的一部分。

Microsoft 365 需要驗證原始寄件者是否合法，讓我們能夠滿懷信心地傳遞轉寄的郵件。

轉寄/轉送郵件應該符合下列其中一個準則，以避免使用轉送集區：

- 輸出寄件者位於 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中。
- 當郵件來自 Microsoft 365 時，SPF 會通過。
- 當郵件來自 Microsoft 365 時，寄件者網域上的 DKIM 會傳送。
 
您可以查看郵件是透過轉送集區傳送，方法是查看輸出伺服器 IP (轉送集區將會在 40.95.0.0/16 範圍內) ，或是查看 (名稱) 中的外寄伺服器名稱。

在我們可驗證寄件者的情況下，我們會使用寄件者修正配置 (SRS) 協助收件者的電子郵件系統知道轉寄的郵件來自信任的來源。 您可以深入瞭解該作業的運作方式及可執行檔動作，以協助確保傳送網域在 Office 365 中的[寄件者修正模式 (SRS) 中](/office365/troubleshoot/antispam/sender-rewriting-scheme)傳遞驗證。

若要讓 DKIM 正常運作，請確定啟用 DKIM 以傳送網域。 例如，fabrikam.com 是 contoso.com 的一部分，且是在組織的公認的網域中定義的。 如果郵件寄件者是 sender@fabrikam.com，必須啟用 DKIM 以進行 fabrikam.com。 您可以閱讀如何啟用 at [DKIM，以驗證從您的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。

若要新增自訂網域，請依照[add a domain to Microsoft 365](../../admin/setup/add-domain.md)中的步驟進行。
