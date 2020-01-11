---
title: 隔離 Office 365 中的電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: f7669f69abb711d71362057f2019b0dd7e30443b
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021849"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="9335e-103">隔離 Office 365 中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="9335e-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="9335e-104">您可以設定內送電子郵件訊息，其中會被篩選為垃圾郵件、 大量郵件、 網路釣魚郵件、 郵件包含惡意程式碼，並符合指定的郵件流程規則 （也稱為 trasport 規則） 的郵件的郵件保留的更新版本的 Office 365 中的隔離檢閱。</span><span class="sxs-lookup"><span data-stu-id="9335e-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule (also known as a trasport rule) can be kept for later review.</span></span>
  
<span data-ttu-id="9335e-105">根據預設，網路釣魚、 惡意程式碼，和郵件流程規則進行篩選的郵件會傳送至隔離區，而被篩選為垃圾郵件和大量郵件的郵件傳送給收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="9335e-105">By default, messages that were filtered for phishing, malware, and mail flow rules are sent to quarantine, while messages that were filtered as spam and bulk mail are sent to the recipients' Junk Email folder.</span></span> <span data-ttu-id="9335e-106">身為系統管理員，您可以設定來傳送垃圾郵件和大量郵件訊息，而是隔離的垃圾郵件篩選原則 （也就是內容篩選原則）。</span><span class="sxs-lookup"><span data-stu-id="9335e-106">As an admin, you can set up spam filter policies (also known as content filter policies) to send spam and bulk mail messages to quarantine instead.</span></span> <span data-ttu-id="9335e-107">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9335e-107">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="9335e-108">使用者與系統管理員可以使用隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="9335e-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="9335e-109">隔離區中，使用者可以使用剛自己已篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="9335e-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="9335e-110">系統管理員可以搜尋並管理隔離的郵件，所有使用者。</span><span class="sxs-lookup"><span data-stu-id="9335e-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="9335e-111">高信賴度釣魚程式的郵件以及隔離的郵件流程規則動作的郵件中才有系統管理員隔離區。</span><span class="sxs-lookup"><span data-stu-id="9335e-111">High confidence phish messages and messages quarantined by mail flow rule actions are only available in the admin quarantine.</span></span> <span data-ttu-id="9335e-112">使用者可以存取自己的釣魚程式、 垃圾郵件和大量郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="9335e-112">Users can access their own phish, spam, and bulk mail messages.</span></span> 
  
<span data-ttu-id="9335e-113">深入了解使用被隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="9335e-113">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="9335e-114">系統管理員身分管理被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="9335e-114">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="9335e-115">以使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="9335e-115">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="9335e-116">利用使用者垃圾郵件通知來釋放並回報被當成垃圾郵件隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="9335e-116">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="9335e-117">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="9335e-117">Quarantine FAQ</span></span>](quarantine-faq.md)
