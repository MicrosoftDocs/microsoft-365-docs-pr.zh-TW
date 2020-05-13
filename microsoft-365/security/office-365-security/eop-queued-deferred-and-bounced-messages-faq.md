---
title: EOP 排入佇列、延後和退回的訊息常見問題集
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
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: 尋找在 Exchange Online Protection （EOP）篩選程式期間，有關已排入佇列、延遲或退回之郵件的最常見問題的答案。
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206589"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="afabc-103">EOP 排入佇列、延後和退回的訊息常見問題集</span><span class="sxs-lookup"><span data-stu-id="afabc-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="afabc-104">本主題提供 Exchange Online Protection （EOP）篩選過程中已排入佇列、延遲或退回之郵件的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="afabc-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="afabc-105">為什麼為郵件佇列？</span><span class="sxs-lookup"><span data-stu-id="afabc-105">Why is mail queuing?</span></span>

<span data-ttu-id="afabc-106">如果服務無法連線至收件者伺服器以進行傳遞，郵件會排隊或延遲。</span><span class="sxs-lookup"><span data-stu-id="afabc-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="afabc-107">當收件者網路傳回500系列錯誤時，它不會推遲郵件。</span><span class="sxs-lookup"><span data-stu-id="afabc-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="afabc-108">郵件如何成為延遲的？</span><span class="sxs-lookup"><span data-stu-id="afabc-108">How does a message become deferred?</span></span>

<span data-ttu-id="afabc-109">當收件者伺服器無法連線，且收件者的伺服器傳回「暫時失敗」（例如，連接逾時、連線拒絕或400系列錯誤）時，就會保留郵件。</span><span class="sxs-lookup"><span data-stu-id="afabc-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="afabc-110">如果發生永久失敗，例如 500-數列錯誤，則郵件會傳回給寄件者。</span><span class="sxs-lookup"><span data-stu-id="afabc-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="afabc-111">郵件保持延遲的時間和重試間隔是多少？</span><span class="sxs-lookup"><span data-stu-id="afabc-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="afabc-112">延遲中的郵件會保留1天的佇列。</span><span class="sxs-lookup"><span data-stu-id="afabc-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="afabc-113">郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。</span><span class="sxs-lookup"><span data-stu-id="afabc-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="afabc-114">前幾個 deferrals 為15分鐘或更少，後續的重試次數（透過接下來的一半或如此），將多次重試間隔增加到最大的60分鐘。</span><span class="sxs-lookup"><span data-stu-id="afabc-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="afabc-115">間隔持續時間擴充是動態的，其中考慮了多個變數，如佇列大小和內部郵件優先順序。</span><span class="sxs-lookup"><span data-stu-id="afabc-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="afabc-116">在 basic 中，它是15分鐘（或更少）的開始時間，然後從未來數小時到最多60分鐘進行擴充。</span><span class="sxs-lookup"><span data-stu-id="afabc-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="afabc-117">還原電子郵件伺服器之後，佇列中的郵件會如何散佈？</span><span class="sxs-lookup"><span data-stu-id="afabc-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="afabc-118">還原電子郵件伺服器之後，當伺服器無法使用時，所有已排入佇列的郵件都會以接收順序進行處理，並進行佇列佇列。</span><span class="sxs-lookup"><span data-stu-id="afabc-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
