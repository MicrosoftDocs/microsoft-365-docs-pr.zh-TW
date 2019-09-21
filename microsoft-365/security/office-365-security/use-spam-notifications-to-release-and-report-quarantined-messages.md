---
title: 利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 如果您的系統管理員可讓使用者的通知，您會收到通知訊息，其中列出傳送至您的信箱已識別為垃圾郵件、 大量或網路釣魚郵件提交之郵件。 您可以釋出或回報郵件之後收到通知。
ms.openlocfilehash: 499af3ae2934eed19e421918af07a45b72fe2518
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077735"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="7f231-104">利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="7f231-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="7f231-105">如果您的系統管理員可讓使用者的垃圾郵件通知，您會收到通知訊息，列出寄送至您信箱的已識別為垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f231-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="7f231-106">如果您是系統管理員且想来啟用此功能，您可以選擇選項時您[修改預設的反垃圾郵件原則](https://go.microsoft.com/fwlink/?LinkId=800313)。</span><span class="sxs-lookup"><span data-stu-id="7f231-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="7f231-107">您收到的訊息包括清單中的垃圾郵件隔離的郵件，您有的日期和時間 （全球定位時間或 UTC） 的最後一則訊息數目。</span><span class="sxs-lookup"><span data-stu-id="7f231-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="7f231-108">清單會包含每一封郵件的下列項目：</span><span class="sxs-lookup"><span data-stu-id="7f231-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="7f231-109">**寄件者**傳送名稱和電子郵件地址將隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f231-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="7f231-110">**主旨** 隔離之郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="7f231-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="7f231-111">**日期** 郵件遭隔離時的日期和時間 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="7f231-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="7f231-112">**大小**(Kb) 郵件的大小。</span><span class="sxs-lookup"><span data-stu-id="7f231-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="7f231-113">以下是您可以對隔離的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="7f231-113">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="7f231-114">**預覽**郵件如果您想要預覽的內容或之前採取動作的標頭。</span><span class="sxs-lookup"><span data-stu-id="7f231-114">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

- <span data-ttu-id="7f231-115">**下載**郵件如果您想要檢閱的訊息和附件 （如果有的話） 之前採取行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="7f231-115">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

- <span data-ttu-id="7f231-116">**版本**如果郵件不是垃圾郵件，而且您希望 Office 365 將郵件傳送至您的信箱。</span><span class="sxs-lookup"><span data-stu-id="7f231-116">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="7f231-117">**釋出 & 允許寄件者**如果郵件不是垃圾郵件和您想要新增至安全的寄件者和收件者清單的未來的電子郵件的寄件者的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7f231-117">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="7f231-118">請記住您的系統管理員可能會有您的安全寄件者清單會覆寫其他組織整體允許/封鎖組態。</span><span class="sxs-lookup"><span data-stu-id="7f231-118">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

- <span data-ttu-id="7f231-119">**版本 & 報表**，如果郵件不是垃圾郵件和您想要將郵件傳送至您的信箱及該問題報告給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="7f231-119">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

- <span data-ttu-id="7f231-120">**封鎖寄件者**如果您希望 Office 365 將寄件者新增至封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="7f231-120">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="7f231-121">請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="7f231-121">Be aware of the following:</span></span>
  
- <span data-ttu-id="7f231-122">因為它們符合郵件流程規則遭到隔離的郵件不會包含在使用者隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f231-122">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="7f231-123">該訊息只會列出因垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f231-123">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="7f231-124">您只能釋出郵件並將其報告為誤判 (非垃圾郵件)   一次。</span><span class="sxs-lookup"><span data-stu-id="7f231-124">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

