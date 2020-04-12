---
title: Office 365 中的隔離區
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Office 365 中的隔離會包含潛在危險或不需要的郵件。 系統管理員和使用者可以存取隔離區。
ms.openlocfilehash: d3db036210886f7a4607f477bba2cf9f450ed90c
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230931"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="ee443-104">Office 365 中的隔離區</span><span class="sxs-lookup"><span data-stu-id="ee443-104">Quarantine in Office 365</span></span>

<span data-ttu-id="ee443-105">如果您是 Office 365 客戶的信箱位於 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶，但沒有 Exchange Online 信箱，則隔離可用於保留潛在危險或不需要的郵件。</span><span class="sxs-lookup"><span data-stu-id="ee443-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="ee443-106">如果找到*任何*包含惡意程式碼的附件，反惡意程式碼原則就會自動隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="ee443-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="ee443-107">如需詳細資訊，請參閱[Configure In Office 365 的反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ee443-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="ee443-108">根據預設，反垃圾郵件原則會隔離網路釣魚郵件，並將垃圾郵件和大量電子郵件傳送至使用者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ee443-108">By default, anti-spam policies quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="ee443-109">不過，您也可以建立及自訂反垃圾郵件原則，以隔離垃圾郵件和大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ee443-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="ee443-110">如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ee443-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ee443-111">使用者和系統管理員都可以處理隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="ee443-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="ee443-112">系統管理員可以使用所有類型的隔離郵件來處理所有使用者。</span><span class="sxs-lookup"><span data-stu-id="ee443-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="ee443-113">只有系統管理員可以處理被隔離為惡意程式碼、高可信度網路釣魚或郵件流程規則（也稱為傳輸規則）結果的郵件。</span><span class="sxs-lookup"><span data-stu-id="ee443-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ee443-114">如需詳細資訊，請參閱[以 Office 365 系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="ee443-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="ee443-115">如果郵件被隔離為垃圾郵件、大量電子郵件，或（從2020）網路釣魚，使用者可以使用隔離的郵件，而這些郵件是收件者。</span><span class="sxs-lookup"><span data-stu-id="ee443-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="ee443-116">如需詳細資訊，請參閱 [以 Office 365 使用者身分尋找並釋出被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="ee443-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="ee443-117">若要防止使用者管理其自己的隔離網路釣魚郵件，系統管理員可以針對反垃圾郵件原則中的**網路釣魚電子郵件**篩選判定，設定不同的動作。</span><span class="sxs-lookup"><span data-stu-id="ee443-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="ee443-118">如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ee443-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="ee443-119">系統管理員和使用者可以向隔離中的 Microsoft 報告誤報。</span><span class="sxs-lookup"><span data-stu-id="ee443-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="ee443-120">如需有關隔離的詳細資訊，請參閱[隔離常見問題](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="ee443-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
