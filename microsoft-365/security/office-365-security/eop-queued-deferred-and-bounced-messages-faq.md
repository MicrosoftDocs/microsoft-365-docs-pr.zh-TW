---
title: EOP 排入佇列、延後和退回的訊息常見問題集
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: 尋找在 Microsoft Exchange Online Protection （EOP）篩選程式期間佇列、延遲或退回的郵件相關 FAQs 的答案。
ms.openlocfilehash: f7a7c8b5466e02353ca114d6c7ed44f37bed5592
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036545"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排入佇列、延後和退回的訊息常見問題集

本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。

**問：為何將郵件排入佇列？**

答：如果服務無法連線到傳遞的收件者伺服器，郵件會排入佇列或延遲。如果從收件者的網路傳回 500 系列錯誤，它不會延遲郵件。

**問：如何延遲郵件？**

答：當收件者伺服器的連線無法建立，而且收件者的伺服器傳回連接逾時、連線被拒絕或 400 系列錯誤等「暫存失敗」時，就會保留郵件。如果發生永久性失敗 (例如 500 系列錯誤)，郵件就會傳回給寄件者。

**問：郵件維持延遲的時間有多長，而重試間隔時間有多長？**

答： 延遲中的郵件會保留1天的佇列。 郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。 前幾個 deferrals 為15分鐘或更少，後續的重試次數（透過接下來的一半或如此），將多次重試間隔增加到最大的60分鐘。 間隔持續時間擴充是動態的，其中考慮了多個變數，如佇列大小和內部郵件優先順序。 在 basic 中，它是15分鐘（或更少）的開始時間，然後從未來數小時到最多60分鐘進行擴充。

**問：還原您的電子郵件伺服器後，已排入佇列的郵件如何散佈？**

答：您的電子郵件伺服器還原後，所有排入佇列的郵件會在伺服器無法使用時，自動根據他們被接收與排入佇列的順序自動進行處理。
