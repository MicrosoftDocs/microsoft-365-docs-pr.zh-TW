---
title: '&apos;垃圾郵件和大量電子郵件有什麼不同？'
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解垃圾郵件 (垃圾郵件) 和大量電子郵件 (灰色郵件) 的差異，Exchange Online Protection (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204939"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP 中垃圾郵件和大量電子郵件有什麼不同？

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，客戶有時會問：「垃圾郵件和大量電子郵件有什麼不同？」。 本主題說明 EOP 中可用的控制項的差異和描述。

- **垃圾郵件** 為垃圾郵件，也就是) 正確辨識時， (未受歡迎和普遍有害的郵件。 根據預設，EOP 會根據來源電子郵件伺服器的信譽拒絕垃圾郵件。 如果郵件通過來源 IP 檢查，它會傳送至垃圾郵件篩選。 如果郵件是由垃圾郵件篩選歸類為垃圾郵件，則郵件預設會 () 傳送給預定的收件者，並移至其 [垃圾郵件] 資料夾。

  - 您可以設定要對垃圾郵件篩選 verdicts 採取的動作。 如需相關指示，請參閱 [CONFIGURE EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。

  - 如果您不同意垃圾郵件篩選判定，您可以使用數種方式將您認為視為垃圾郵件或非垃圾郵件的郵件，報告為 Microsoft 的 [報表訊息和](report-junk-email-messages-to-microsoft.md)檔案中所述。

- **大量電子郵件** (也稱為 _灰色郵件_) ，很難進行分類。 垃圾郵件是常數威脅，大量電子郵件常常是一次的廣告或行銷訊息。 有些使用者需要大量電子郵件訊息 (，實際上，他們已特意註冊以接收) ，其他使用者則將大量電子郵件視為垃圾郵件。 例如，有些使用者想要接收來自 Contoso 公司的廣告訊息，或在網路安全性上的即將舉行的會議邀請，其他使用者請將這些相同的郵件視為垃圾郵件。

  如需有關如何識別大量電子郵件的詳細資訊，請參閱 [EOP 中的大量投訴層級 (BCL) ](bulk-complaint-level-values.md)。

## <a name="how-to-manage-bulk-email"></a>如何管理大量電子郵件

由於大量電子郵件的混合反應，因此不會有適用于每個組織的通用指導方針。

反垃圾郵件原則具有預設的 BCL 閾值，用來識別大量電子郵件為垃圾郵件。 系統管理員可增加或減少閾值。 如需詳細資訊，請參閱下列主題：

- [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

- [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

另一種易於忽視的選項：如果接收大量電子郵件的使用者 complains，但郵件是來自可透過 EOP 中垃圾郵件篩選的著名寄件者，請使用者在大量電子郵件訊息中檢查是否有 [取消訂閱] 選項。
