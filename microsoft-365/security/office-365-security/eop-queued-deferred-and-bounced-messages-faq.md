---
title: EOP 排入佇列、延後和退回的訊息常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: 本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。
ms.openlocfilehash: e517fbf06da5bdea18f7c7af2733dbc8c359cc80
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441490"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排入佇列、延後和退回的訊息常見問題集

本主題提供有關已排入佇列、延遲，或在 Microsoft Exchange Online Protection (EOP) 篩選程序中退回之郵件的常見問題解答。

**問：為何將郵件排入佇列？**

答：如果服務無法連線到傳遞的收件者伺服器，郵件會排入佇列或延遲。如果從收件者的網路傳回 500 系列錯誤，它不會延遲郵件。

**問：如何延遲郵件？**

答：當收件者伺服器的連線無法建立，而且收件者的伺服器傳回連接逾時、連線被拒絕或 400 系列錯誤等「暫存失敗」時，就會保留郵件。如果發生永久性失敗 (例如 500 系列錯誤)，郵件就會傳回給寄件者。

**問：郵件維持延遲的時間有多長，而重試間隔時間有多長？**

答：是。 延期的郵件仍在我們佇列中的 1 天。 郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。 第一個的幾個 deferrals 是 15 分鐘或更少，與後續的重試 （透過下一個半十幾個） 透過多個最大值為 60 分鐘重試增加間隔。 間隔期間擴充是動態的考慮像佇列大小和內部郵件優先順序的多個變數。 在基本，它是 15 分鐘 （或更少） 若要開始，然後展開從該處透過下一步的幾個小時到最大 60 分鐘。

**問：還原您的電子郵件伺服器後，已排入佇列的郵件如何散佈？**

答：您的電子郵件伺服器還原後，所有排入佇列的郵件會在伺服器無法使用時，自動根據他們被接收與排入佇列的順序自動進行處理。
