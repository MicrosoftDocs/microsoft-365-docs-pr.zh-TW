---
title: EOP 排入佇列、延後和退回的訊息常見問題集
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: 尋找在 Exchange Online Protection (EOP) 篩選程式期間，有關已排入佇列、延遲或退回之郵件的最常見問題的答案。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289696"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排入佇列、延後和退回的訊息常見問題集

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

本主題提供 Exchange Online Protection (EOP) 篩選程式期間已排入佇列、延遲或退回之郵件的常見問題解答。

## <a name="why-is-mail-queuing"></a>為什麼為郵件佇列？

如果服務無法連線至收件者伺服器以進行傳遞，郵件會排隊或延遲。 當收件者網路傳回500系列錯誤時，它不會推遲郵件。

## <a name="how-does-a-message-become-deferred"></a>郵件如何成為延遲的？

當收件者伺服器無法連線，且收件者的伺服器傳回「暫時失敗」（例如，連接逾時、連線拒絕或400系列錯誤）時，就會保留郵件。 如果發生永久失敗，例如 500-數列錯誤，則郵件會傳回給寄件者。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>郵件保持延遲的時間和重試間隔是多少？

延遲中的郵件會保留1天的佇列。 郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。 前幾個 deferrals 為15分鐘或更少，後續的重試次數 (于接下來的0.5 分鐘內，否則) 會以多個重試次數增加超過60分鐘的重試間隔。 間隔持續時間擴充是動態的，其中考慮了多個變數，如佇列大小和內部郵件優先順序。 在 basic 中，它是15分鐘 (或更少) 開始，然後從未來數小時到最多60分鐘。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>還原電子郵件伺服器之後，佇列中的郵件會如何散佈？

還原電子郵件伺服器之後，當伺服器無法使用時，所有已排入佇列的郵件都會以接收順序進行處理，並進行佇列佇列。
