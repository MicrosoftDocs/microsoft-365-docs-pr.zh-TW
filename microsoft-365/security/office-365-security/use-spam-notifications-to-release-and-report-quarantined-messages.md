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
ms.openlocfilehash: c8253ba7002ac88932cbef07508215a3d9a65f75
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806706"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="6cbd4-104">利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="6cbd4-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="6cbd4-105">如果您的系統管理員可讓使用者的垃圾郵件通知，您會收到通知訊息，列出寄送至您信箱的已識別為垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="6cbd4-106">如果您是系統管理員且想来啟用此功能，您可以選擇選項時您[修改預設的反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="6cbd4-107">您收到的訊息包括清單中的垃圾郵件隔離的郵件，您有的日期和時間 （全球定位時間或 UTC） 的最後一則訊息數目。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="6cbd4-108">清單會包含每一封郵件的下列項目：</span><span class="sxs-lookup"><span data-stu-id="6cbd4-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="6cbd4-109">**寄件者**傳送名稱和電子郵件地址將隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="6cbd4-110">**主旨** 隔離之郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="6cbd4-111">**日期** 郵件遭隔離時的日期和時間 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="6cbd4-112">以下是您可以對隔離的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="6cbd4-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="6cbd4-113">**封鎖寄件者**如果您希望 Office 365 將寄件者新增至封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="6cbd4-114">**版本**如果郵件不是垃圾郵件，而且您希望 Office 365 將郵件傳送至您的信箱。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="6cbd4-115">如果您想要採取其他動作，例如預覽或版本，瀏覽至隔離區入口網站的安全性與合規性中心內的**檢閱**。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="6cbd4-116">請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="6cbd4-116">Be aware of the following:</span></span>

- <span data-ttu-id="6cbd4-117">因為它們符合郵件流程規則遭到隔離的郵件不會包含在使用者隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-117">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="6cbd4-118">該訊息只會列出因垃圾郵件而遭到隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-118">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="6cbd4-119">您只能釋出郵件並將其報告為誤判 (非垃圾郵件)   一次。</span><span class="sxs-lookup"><span data-stu-id="6cbd4-119">You can only release a message and report it as a false positive (not junk) once.</span></span>
