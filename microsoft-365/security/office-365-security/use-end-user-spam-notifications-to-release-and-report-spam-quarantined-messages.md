---
title: 利用使用者垃圾郵件通知來釋放並回報被當成垃圾郵件隔離的郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: '請參閱 < 關於隔離電子郵件系統管理員從使用者垃圾郵件通知訊息的使用者可以執行以下動作的郵件。 '
ms.openlocfilehash: 5c113e186a0469714829592437698ddb1185a141
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971411"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="687ae-103">利用使用者垃圾郵件通知來釋放並回報被當成垃圾郵件隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="687ae-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="687ae-p101">如果系統管理員啟用使用者垃圾郵件通知，您將會收到通知訊息，其中列出預計傳送到您的信箱、但因被視為垃圾郵件而遭到隔離的郵件。這則訊息包括所列出因垃圾郵件而遭到隔離的郵件數目，以及清單中最後一封郵件的日期和時間 (全球定位時間 (UTC))。在此清單中，您可以檢視關於每則郵件的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="687ae-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="687ae-107">**寄件者**： 隔離之郵件的寄件者名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="687ae-107">**Sender**: The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="687ae-108">**主旨**： 隔離之郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="687ae-108">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="687ae-109">**日期**： 日期和時間 （UTC) 郵件遭隔離。</span><span class="sxs-lookup"><span data-stu-id="687ae-109">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="687ae-110">**大小**: (kb) 中的隔離郵件的大小。</span><span class="sxs-lookup"><span data-stu-id="687ae-110">**Size**: The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="687ae-111">您可以對每則郵件執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="687ae-111">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="687ae-112">**釋出到收件匣**： 按一下此連結會將郵件傳送至收件匣以便檢視它。</span><span class="sxs-lookup"><span data-stu-id="687ae-112">**Release to Inbox**: Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="687ae-113">**報告為不是垃圾郵件**： 按一下此連結會傳送郵件的副本給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="687ae-113">**Report as Not Junk**: Clicking this link sends a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="687ae-114">垃圾郵件小組會評估及分析郵件，並且根據分析結果來調整反垃圾郵件篩選規則以允許此郵件通過。</span><span class="sxs-lookup"><span data-stu-id="687ae-114">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="687ae-115">因為郵件流程規則而遭到隔離的郵件 (也稱為) 比對不包括在使用者垃圾郵件隔離訊息。</span><span class="sxs-lookup"><span data-stu-id="687ae-115">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="687ae-116">該訊息只會列出因垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="687ae-116">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="687ae-117">您只能釋出郵件並將其報告為誤判 (非垃圾郵件)   一次。</span><span class="sxs-lookup"><span data-stu-id="687ae-117">You can only release a message and report it as a false positive (not junk) once.</span></span>
