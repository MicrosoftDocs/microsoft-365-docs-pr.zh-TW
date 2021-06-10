---
title: 使用 Microsoft 365 的調度程式
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 使用 Microsoft 365 的調度程式。
ms.openlocfilehash: 2987861856611ae4698f49dc8123a5cf733074ef
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286163"
---
# <a name="how-to-use-scheduler-for-microsoft-365"></a><span data-ttu-id="f8d37-103">如何使用 Microsoft 365 的調度程式</span><span class="sxs-lookup"><span data-stu-id="f8d37-103">How to use Scheduler for Microsoft 365</span></span>

<span data-ttu-id="f8d37-104">Cortana 識別自然語言。</span><span class="sxs-lookup"><span data-stu-id="f8d37-104">Cortana understands natural language.</span></span> <span data-ttu-id="f8d37-105">透過電子郵件將 cortana@yourdomain.com 納入其他出席者，Cortana 會從那裡取得。</span><span class="sxs-lookup"><span data-stu-id="f8d37-105">Include cortana@yourdomain.com in an email with other attendees, and Cortana will take over from there.</span></span> <span data-ttu-id="f8d37-106">Cortana 會傳送電子郵件通知，以確認會議時間，並讓您掌握最新的進度。</span><span class="sxs-lookup"><span data-stu-id="f8d37-106">Cortana will send email notifications confirming meeting times and keep you up to date on progress.</span></span>

<span data-ttu-id="f8d37-107">若要使用排程器，您可以將 Cortana 的電子郵件地址新增至您的電子郵件，以及您想要進行會議的人員。</span><span class="sxs-lookup"><span data-stu-id="f8d37-107">To use Scheduler, add Cortana’s email address to your email in addition to the people you want to meeting with.</span></span> <span data-ttu-id="f8d37-108">在您電子郵件中的小娜和其他出席者，告知 Cortana 使用自然語言排程會議。</span><span class="sxs-lookup"><span data-stu-id="f8d37-108">In your email to Cortana and the other attendees, tell Cortana to schedule a meeting using natural language.</span></span>  

## <a name="when-to-use-scheduler"></a><span data-ttu-id="f8d37-109">何時使用調度程式？</span><span class="sxs-lookup"><span data-stu-id="f8d37-109">When to use Scheduler?</span></span>

- <span data-ttu-id="f8d37-110">**排程具有內部出席者的會議** 使用 Cortana 以5或更少的出席者排程會議。</span><span class="sxs-lookup"><span data-stu-id="f8d37-110">**Scheduling meetings with internal attendees** Use Cortana to schedule your meetings with 5 or fewer attendees.</span></span> <span data-ttu-id="f8d37-111">Cortana 對 Outlook calendar 中的其他使用者看到的空閒/忙碌資訊存取權相同。</span><span class="sxs-lookup"><span data-stu-id="f8d37-111">Cortana has the same access to free/busy information that you see for others in Outlook calendar.</span></span> <span data-ttu-id="f8d37-112">它會挑選一段時間，可供所有人使用，並代表您傳送邀請。</span><span class="sxs-lookup"><span data-stu-id="f8d37-112">It will pick a time that works for everyone and send an invite on your behalf.</span></span> <span data-ttu-id="f8d37-113">Cortana 會自動 Teams 啟用其排程的所有會議。</span><span class="sxs-lookup"><span data-stu-id="f8d37-113">Cortana will automatically Teams-enable all the meetings that it schedules.</span></span> <span data-ttu-id="f8d37-114">「抄送」行的任何人都會收到邀請做為選用的出席者。</span><span class="sxs-lookup"><span data-stu-id="f8d37-114">Anyone on the CC line will receive the invite as an optional attendee.</span></span>  

- <span data-ttu-id="f8d37-115">**排程與外部出席者的會議**</span><span class="sxs-lookup"><span data-stu-id="f8d37-115">**Scheduling meetings with external attendees**</span></span>  
<span data-ttu-id="f8d37-116">Cortana 會與外部被邀請者進行通訊，以協商您可以開會的時間。</span><span class="sxs-lookup"><span data-stu-id="f8d37-116">Cortana communicates with external invitees to negotiate times that you are available to meet.</span></span> <span data-ttu-id="f8d37-117">在確認要開會的時間之後，Cortana 會將邀請傳送給出席者，並通知您會議已排程。</span><span class="sxs-lookup"><span data-stu-id="f8d37-117">After confirming a time to meet, Cortana sends an invite to attendees and notifies you that the meeting has been scheduled.</span></span>

## <a name="what-to-say-to-cortana"></a><span data-ttu-id="f8d37-118">怎麼說小娜？</span><span class="sxs-lookup"><span data-stu-id="f8d37-118">What to say to Cortana?</span></span>

<span data-ttu-id="f8d37-119">Cortana 可識別自然語言，但建議使用簡明語言。</span><span class="sxs-lookup"><span data-stu-id="f8d37-119">Cortana understands natural language, but concise language is recommended.</span></span> 

<span data-ttu-id="f8d37-120">使用下列模式可要求會議：排程 a [時間] 會議 [時間範圍]。</span><span class="sxs-lookup"><span data-stu-id="f8d37-120">Use the following pattern to request a meeting: Schedule a [length of time] meeting [time frame].</span></span>  

- <span data-ttu-id="f8d37-121">「安排為期30分鐘的會議（下周）。」</span><span class="sxs-lookup"><span data-stu-id="f8d37-121">“Schedule a 30-minute meeting next week.”</span></span>  
- <span data-ttu-id="f8d37-122">「尋找1小時供我們在1月開會。」</span><span class="sxs-lookup"><span data-stu-id="f8d37-122">“Find 1 hour for us to meet in January.”</span></span> 
- <span data-ttu-id="f8d37-123">「可能適用于印度標準時間的第一周的45分鐘。」</span><span class="sxs-lookup"><span data-stu-id="f8d37-123">“Find 45 minutes the first week of May that works for India Standard Time.”</span></span> 

<span data-ttu-id="f8d37-124">如果您未指定時間範圍，Cortana 會在下一個工作日立即預訂會議。</span><span class="sxs-lookup"><span data-stu-id="f8d37-124">If you don't specify a time range, Cortana will book the meeting as soon as the next business day.</span></span>

## <a name="scheduling-across-multiple-time-zones"></a><span data-ttu-id="f8d37-125">跨多個時區排程</span><span class="sxs-lookup"><span data-stu-id="f8d37-125">Scheduling across multiple time zones</span></span>

<span data-ttu-id="f8d37-126">使用下列模式可要求多時區會議：「排程 a [時間] 會議，其適用于 [時區] 的 [時間範圍]。</span><span class="sxs-lookup"><span data-stu-id="f8d37-126">Use the following pattern to request a multi-time zone meeting: "Schedule a [length of time] meeting in [time frame] that works for [time zone]."</span></span> 

<span data-ttu-id="f8d37-127">如果您是在第一個電子郵件傳送至 Cortana 時，Cortana 會在另一個時區中容納出席者。</span><span class="sxs-lookup"><span data-stu-id="f8d37-127">Cortana will accommodate attendees in another time zone if you request it in the first email to Cortana.</span></span>  

<span data-ttu-id="f8d37-128">將初始要求傳送至 Cortana 後，就無法變更時區 (s) 。</span><span class="sxs-lookup"><span data-stu-id="f8d37-128">You cannot change time zone(s) after sending the initial request to Cortana.</span></span> <span data-ttu-id="f8d37-129">當某些時區的縮寫相同時，請使用完整時區名稱取得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="f8d37-129">As some time zone abbreviations are the same, use the full time zone name for best results.</span></span>  

## <a name="organizer-guidance"></a><span data-ttu-id="f8d37-130">召集人指導方針</span><span class="sxs-lookup"><span data-stu-id="f8d37-130">Organizer guidance</span></span>

<span data-ttu-id="f8d37-131">有些情況下，Cortana 可能會向您尋求召集人的指導方針。</span><span class="sxs-lookup"><span data-stu-id="f8d37-131">Occasionally, Cortana may ask you for guidance as the organizer.</span></span> <span data-ttu-id="f8d37-132">遵循 Cortana 電子郵件中的指示，並使用 Cortana 電子郵件中的回復按鈕回復。</span><span class="sxs-lookup"><span data-stu-id="f8d37-132">Follow the directions in Cortana’s email and reply using the reply buttons in Cortana emails.</span></span>

## <a name="reschedule-or-cancel"></a><span data-ttu-id="f8d37-133">重新排定或取消排程</span><span class="sxs-lookup"><span data-stu-id="f8d37-133">Reschedule or Cancel</span></span>

<span data-ttu-id="f8d37-134">如果您需要重新排程或取消，只需使用有關會議的 Cortana 回復執行緒中的電子郵件，並要求「重排」或「取消」。</span><span class="sxs-lookup"><span data-stu-id="f8d37-134">If you need to reschedule or cancel, just reply to an email in the thread with Cortana regarding the meeting and ask to “Reschedule” or “Cancel.”</span></span> 

> [!NOTE]
> <span data-ttu-id="f8d37-135">Cortana 無法重新排定或取消排程計畫者未排程的會議。</span><span class="sxs-lookup"><span data-stu-id="f8d37-135">Cortana can't reschedule or cancel meetings that were not scheduled by Scheduler.</span></span>  
