---
title: 輸出郵件的高風險傳遞集區
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 瞭解高風險傳遞集區如何用來保護 Office 365 資料中心的電子郵件伺服器信譽。
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895356"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a>Office 365 中輸出郵件的高風險傳遞集區

Office 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。 例如，在內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Office 365 傳送輸出郵件，或在 Office 365 帳戶中傳送輸出郵件。 這些案例會產生出現在協力廠商封鎖清單上受影響的 Office 365 資料中心伺服器的 IP 位址。 使用這些封鎖清單的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。

若要防止這種情況，所有來自決定是垃圾郵件或超過[服務](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)傳送限制之 Office 365 datacenter server 的所有輸出郵件，[都是透過](configure-the-outbound-spam-policy.md)_高風險傳遞集_區傳送。

「高風險傳遞集區」是僅用於傳送「低品質」郵件（例如，垃圾郵件和[退信攻擊](backscatter-messages-and-eop.md)）的外寄電子郵件的次要 IP 位址集區。 使用 [高風險傳遞集區]，可防止輸出電子郵件的一般 IP 位址集區傳送垃圾郵件。 外寄電子郵件的一般 IP 位址集區維持「高品質」郵件的信譽，這會降低這些 IP 位址會出現在 IP 封鎖清單上的可能性。

在此情況下，高風險傳遞集區中的 IP 位址會保留在 IP 封鎖清單上，但這是由設計所組成。 不會保證傳遞給預定的收件者，因為許多電子郵件組織不會接受高風險傳遞集區中的郵件。

如需詳細資訊，請參閱[控制 Office 365 中的外寄垃圾郵件](outbound-spam-controls.md)。

> [!NOTE]
> 來源電子郵件網域沒有記錄，而且公用 DNS 中未定義任何 MX 記錄的郵件，無論其垃圾郵件或傳送限制，都永遠都透過高風險傳遞集區路由傳送。

## <a name="bounce-messages"></a>退回郵件

輸出的高風險傳遞集區可管理所有未傳遞回報的傳遞（也稱為 NDRs、退回郵件、傳遞狀態通知或 DSNs）。

NDRs 中的電湧可能原因包括：

- 會影響使用服務之客戶之一的電子欺騙活動。

- 目錄收集攻擊。

- 垃圾郵件攻擊。

- 欺詐的電子郵件伺服器。

所有這些問題都會造成服務處理的 NDRs 數量突然增加。 許多情況下，這些 NDRs 似乎是對其他電子郵件伺服器和服務（也稱為_[退信攻擊](backscatter-messages-and-eop.md)_）的垃圾郵件。
