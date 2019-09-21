---
title: 隔離 Office 365 中的電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: 您可以設定隔離的 Office 365 其中大量被篩選為垃圾郵件的內送電子郵件、 網路釣魚郵件中的內送電子郵件和惡意程式碼可以保留供日後檢閱。
ms.openlocfilehash: 5590c9de9ff596c359910b5b1793004ae1913365
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077997"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="c46af-103">隔離 Office 365 中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="c46af-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="c46af-104">您可以設定供日後檢閱隔離被篩選為垃圾郵件、 大量郵件、 網路釣魚郵件、 郵件包含惡意程式碼，並符合指定的郵件流程規則的郵件的郵件可以保持在其中的 Office 365 中的內送電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c46af-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule can be kept for later review.</span></span>
  
<span data-ttu-id="c46af-105">根據預設，已篩選的郵件會傳送至收件者的垃圾郵件] 資料夾，但不包括包含惡意程式碼的預設傳送至隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="c46af-105">By default, filtered messages are sent to the recipients' Junk Email folder, except for mail that contains malware which is sent to quarantine by default.</span></span> <span data-ttu-id="c46af-106">身為系統管理員，您可以設定傳送至隔離區改為所有已篩選的郵件內容篩選原則。</span><span class="sxs-lookup"><span data-stu-id="c46af-106">As an admin, you can set up content filter policies to send all filtered messages to quarantine instead.</span></span> <span data-ttu-id="c46af-107">不同的內容篩選的郵件時可採取的動作取決於[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c46af-107">The different actions that you can take for content-filtered messages depend on the [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="c46af-108">使用者與系統管理員可以使用隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="c46af-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="c46af-109">隔離區中，使用者可以使用剛自己已篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="c46af-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="c46af-110">系統管理員可以搜尋並管理隔離的郵件，所有使用者。</span><span class="sxs-lookup"><span data-stu-id="c46af-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="c46af-111">Phish 郵件以及隔離的郵件流程規則 （也稱為傳輸規則） 動作的郵件中才有系統管理員隔離區。</span><span class="sxs-lookup"><span data-stu-id="c46af-111">Phish messages and messages quarantined by mail flow rule (also known as transport rule) actions are only available in the admin quarantine.</span></span>
  
<span data-ttu-id="c46af-112">深入了解使用被隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="c46af-112">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="c46af-113">系統管理員身分管理被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="c46af-113">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="c46af-114">以使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="c46af-114">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="c46af-115">利用使用者垃圾郵件通知來釋放並回報被當成垃圾郵件隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="c46af-115">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="c46af-116">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="c46af-116">Quarantine FAQ</span></span>](quarantine-faq.md)
