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
ms.openlocfilehash: e533a0292bed1c6cd5d70796da2a25a7d8411884
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871179"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="a1da8-103">利用使用者垃圾郵件通知來釋放並回報被當成垃圾郵件隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="a1da8-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="a1da8-104">[![關於從 TechNet 移動到 support.office.com 的內容圖像中的文字](../media/ab7c897a-4798-4f31-8c84-f17a8409b133.png)](https://go.microsoft.com/fwlink/p/?LinkID=624152)</span><span class="sxs-lookup"><span data-stu-id="a1da8-104">[![Text in image about content moving from TechNet to support.office.com](../media/ab7c897a-4798-4f31-8c84-f17a8409b133.png)](https://go.microsoft.com/fwlink/p/?LinkID=624152)</span></span>

<span data-ttu-id="a1da8-p101">如果系統管理員啟用使用者垃圾郵件通知，您將會收到通知訊息，其中列出預計傳送到您的信箱、但因被視為垃圾郵件而遭到隔離的郵件。這則訊息包括所列出因垃圾郵件而遭到隔離的郵件數目，以及清單中最後一封郵件的日期和時間 (全球定位時間 (UTC))。在此清單中，您可以檢視關於每則郵件的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a1da8-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="a1da8-108">**寄件者** 隔離之郵件的寄件者名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a1da8-108">**Sender** The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="a1da8-109">**主旨** 隔離之郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="a1da8-109">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="a1da8-110">**日期** 郵件遭隔離時的日期和時間 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="a1da8-110">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="a1da8-111">**大小** 隔離之郵件的大小 (KB)。</span><span class="sxs-lookup"><span data-stu-id="a1da8-111">**Size** The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="a1da8-112">您可以對每則郵件執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a1da8-112">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="a1da8-113">**釋出到收件匣** 按一下此連結可將郵件傳送到收件匣以便檢視。</span><span class="sxs-lookup"><span data-stu-id="a1da8-113">**Release to Inbox** Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="a1da8-p102">**報告為不是垃圾郵件** 按一下此連結可將郵件的副本傳送到 Microsoft 以供分析。垃圾郵件小組會評估及分析郵件，並且根據分析結果來調整反垃圾郵件篩選規則以允許此郵件通過。</span><span class="sxs-lookup"><span data-stu-id="a1da8-p102">**Report as Not Junk** Clicking this link sends a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="a1da8-116">因為郵件流程規則而遭到隔離的郵件 (也稱為) 比對不包括在使用者垃圾郵件隔離訊息。</span><span class="sxs-lookup"><span data-stu-id="a1da8-116">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="a1da8-117">該訊息只會列出因垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="a1da8-117">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="a1da8-118">您只能釋出郵件並將其報告為誤判 (非垃圾郵件)   一次。</span><span class="sxs-lookup"><span data-stu-id="a1da8-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
