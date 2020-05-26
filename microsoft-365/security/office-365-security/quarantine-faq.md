---
title: 隔離的郵件常見問題
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 系統管理員可以在 Exchange Online Protection （EOP）中查看有關隔離郵件的常見問題和解答。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a231e363d5764465547ee1e80cc080c3d7c006c
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351092"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="e1913-103">隔離的郵件常見問題</span><span class="sxs-lookup"><span data-stu-id="e1913-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="e1913-104">本主題針對 Exchange Online 中的信箱或獨立 Exchange Online Protection （EOP）組織中的 Microsoft 365 組織，提供有關隔離的電子郵件的常見問題和解答，但沒有 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="e1913-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="e1913-105">如需反垃圾郵件保護的相關問題和解答，請參閱[反垃圾郵件保護常見問題](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="e1913-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="e1913-106">如需有關反惡意程式碼保護的問題和解答，請參閱[反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="e1913-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="e1913-107">如需反欺騙保護的相關問題和解答，請參閱[反欺騙保護常見問題](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="e1913-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="e1913-108">如何管理被隔離以進行惡意程式碼的郵件？</span><span class="sxs-lookup"><span data-stu-id="e1913-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="e1913-109">只有系統管理員可以管理隔離惡意程式碼的郵件。</span><span class="sxs-lookup"><span data-stu-id="e1913-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="e1913-110">如需詳細資訊，請參閱[以系統管理員身分管理被隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="e1913-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="e1913-111">如何隔離垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="e1913-111">How do I quarantine spam?</span></span>

<span data-ttu-id="e1913-112">依預設，歸類為垃圾郵件或大量電子郵件的郵件會傳遞至使用者的信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e1913-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="e1913-113">不過，您也可以建立並設定反垃圾郵件原則，以隔離垃圾郵件或大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e1913-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="e1913-114">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e1913-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="e1913-115">如何讓使用者能夠存取隔離區？</span><span class="sxs-lookup"><span data-stu-id="e1913-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="e1913-116">使用者必須具有有效的帳戶，才能存取隔離中自己的郵件。</span><span class="sxs-lookup"><span data-stu-id="e1913-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="e1913-117">獨立 EOP 要求使用者在 EOP 中以郵件使用者的身分呈現（透過目錄同步處理手動建立或建立）。</span><span class="sxs-lookup"><span data-stu-id="e1913-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="e1913-118">如需在獨立 EOP 環境中管理使用者的詳細資訊，請參閱[Manage mail users IN EOP](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="e1913-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="e1913-119">使用者可以在隔離區中存取哪些郵件？</span><span class="sxs-lookup"><span data-stu-id="e1913-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="e1913-120">使用者可以存取垃圾郵件、大量電子郵件，以及（從2020年4月的）網路釣魚郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="e1913-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="e1913-121">由於將**郵件傳遞至**郵件流程規則（也稱為傳輸規則）中的主控隔離動作，因此使用者無法存取隔離的惡意程式碼、高信賴網路釣魚或已隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="e1913-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e1913-122">如需存取隔離郵件之使用者的詳細資訊，請參閱[尋找和以使用者身分發行隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="e1913-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="e1913-123">郵件保存在隔離區中的時間多久？</span><span class="sxs-lookup"><span data-stu-id="e1913-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="e1913-124">您可以使用反垃圾郵件原則，設定隔離區中的垃圾郵件、網路釣魚和大量電子郵件的保留時間。</span><span class="sxs-lookup"><span data-stu-id="e1913-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="e1913-125">預設值為30天，也就是最大值。</span><span class="sxs-lookup"><span data-stu-id="e1913-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="e1913-126">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e1913-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="e1913-127">針對由郵件流程規則動作隔離的郵件，會將**郵件傳遞至主控隔離區**，並將郵件保留30天。</span><span class="sxs-lookup"><span data-stu-id="e1913-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="e1913-128">您無法設定此持續時間。</span><span class="sxs-lookup"><span data-stu-id="e1913-128">You can't configure this duration.</span></span>

<span data-ttu-id="e1913-129">時段到期後，郵件即會刪除，而且無法復原。</span><span class="sxs-lookup"><span data-stu-id="e1913-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="e1913-130">我是否可以一次放開或報告一封以上的隔離郵件？</span><span class="sxs-lookup"><span data-stu-id="e1913-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="e1913-131">在 [安全性 & 規範中心] 中，您可以一次選取及發行最多100封郵件。</span><span class="sxs-lookup"><span data-stu-id="e1913-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="e1913-132">系統管理員可以使用 Exchange Online PowerShell 或獨立 EOP PowerShell 中的[Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)和[Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) Cmdlet，以大量尋找及發行隔離的郵件，並大量報告誤報。</span><span class="sxs-lookup"><span data-stu-id="e1913-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="e1913-133">搜尋隔離郵件時，是否支援萬用字元？</span><span class="sxs-lookup"><span data-stu-id="e1913-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="e1913-134">是否可以搜尋特定網域的隔離郵件？</span><span class="sxs-lookup"><span data-stu-id="e1913-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="e1913-135">在安全性 & 規範中心內不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="e1913-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="e1913-136">例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e1913-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="e1913-137">不過，您可以在 Exchange Online PowerShell 或獨立 EOP PowerShell 中使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="e1913-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="e1913-138">例如，執行下列命令，尋找來自網域 contoso.com 中所有寄件者的垃圾郵件隔離郵件：</span><span class="sxs-lookup"><span data-stu-id="e1913-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="e1913-139">然後，執行下列命令，以將這些郵件釋放給所有原始收件者：</span><span class="sxs-lookup"><span data-stu-id="e1913-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="e1913-140">在您發佈郵件後，就無法再放開。</span><span class="sxs-lookup"><span data-stu-id="e1913-140">After you release a message, you can't release it again.</span></span>
