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
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204826"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="b1317-103">EOP 排入佇列、延後和退回的訊息常見問題集</span><span class="sxs-lookup"><span data-stu-id="b1317-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1317-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="b1317-104">**Applies to**</span></span>
- [<span data-ttu-id="b1317-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b1317-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b1317-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="b1317-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b1317-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1317-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b1317-108">本主題提供 Exchange Online Protection (EOP) 篩選程式期間已排入佇列、延遲或退回之郵件的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="b1317-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="b1317-109">為什麼為郵件佇列？</span><span class="sxs-lookup"><span data-stu-id="b1317-109">Why is mail queuing?</span></span>

<span data-ttu-id="b1317-110">如果服務無法連線至收件者伺服器以進行傳遞，郵件會排隊或延遲。</span><span class="sxs-lookup"><span data-stu-id="b1317-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="b1317-111">當收件者網路傳回500系列錯誤時，它不會推遲郵件。</span><span class="sxs-lookup"><span data-stu-id="b1317-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="b1317-112">郵件如何成為延遲的？</span><span class="sxs-lookup"><span data-stu-id="b1317-112">How does a message become deferred?</span></span>

<span data-ttu-id="b1317-113">當收件者伺服器無法連線，且收件者的伺服器傳回「暫時失敗」（例如，連接逾時、連線拒絕或400系列錯誤）時，就會保留郵件。</span><span class="sxs-lookup"><span data-stu-id="b1317-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="b1317-114">如果發生永久失敗，例如 500-數列錯誤，則郵件會傳回給寄件者。</span><span class="sxs-lookup"><span data-stu-id="b1317-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="b1317-115">郵件保持延遲的時間和重試間隔是多少？</span><span class="sxs-lookup"><span data-stu-id="b1317-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="b1317-116">延遲中的郵件會保留1天的佇列。</span><span class="sxs-lookup"><span data-stu-id="b1317-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="b1317-117">郵件重試次數乃是根據我們從收件者的郵件系統所取回的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b1317-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="b1317-118">前幾個 deferrals 為15分鐘或更少，後續的重試次數 (于接下來的0.5 分鐘內，否則) 會以多個重試次數增加超過60分鐘的重試間隔。</span><span class="sxs-lookup"><span data-stu-id="b1317-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="b1317-119">間隔持續時間擴充是動態的，其中考慮了多個變數，如佇列大小和內部郵件優先順序。</span><span class="sxs-lookup"><span data-stu-id="b1317-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="b1317-120">在 basic 中，它是15分鐘 (或更少) 開始，然後從未來數小時到最多60分鐘。</span><span class="sxs-lookup"><span data-stu-id="b1317-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="b1317-121">還原電子郵件伺服器之後，佇列中的郵件會如何散佈？</span><span class="sxs-lookup"><span data-stu-id="b1317-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="b1317-122">還原電子郵件伺服器之後，當伺服器無法使用時，所有已排入佇列的郵件都會以接收順序進行處理，並進行佇列佇列。</span><span class="sxs-lookup"><span data-stu-id="b1317-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
