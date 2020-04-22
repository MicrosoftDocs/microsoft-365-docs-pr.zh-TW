---
title: 隔離常見問題集
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
description: 有關 Office 365 中的隔離常見問題的答案。
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634421"
---
# <a name="quarantine-faq"></a><span data-ttu-id="97746-103">隔離區常見問題集</span><span class="sxs-lookup"><span data-stu-id="97746-103">Quarantine FAQ</span></span>

<span data-ttu-id="97746-104">本主題提供 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶沒有 Exchange Online 信箱之信箱的365隔離問題和解答。</span><span class="sxs-lookup"><span data-stu-id="97746-104">This topic provides frequently asked questions and answers about quarantine for Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="97746-105">Q：如何管理被隔離以進行惡意程式碼的郵件？</span><span class="sxs-lookup"><span data-stu-id="97746-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="97746-106">只有系統管理員可以管理隔離惡意程式碼的郵件。</span><span class="sxs-lookup"><span data-stu-id="97746-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="97746-107">如需詳細資訊，請參閱[以 Office 365 系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="97746-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="97746-108">問：如何隔離垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="97746-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="97746-109">答：</span><span class="sxs-lookup"><span data-stu-id="97746-109">A.</span></span> <span data-ttu-id="97746-110">依預設，歸類為垃圾郵件或大量電子郵件的郵件會傳遞至使用者的信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="97746-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="97746-111">不過，您也可以建立並設定反垃圾郵件原則，以隔離垃圾郵件或大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="97746-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="97746-112">如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="97746-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="97746-113">問：如何讓使用者能夠存取隔離區？</span><span class="sxs-lookup"><span data-stu-id="97746-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="97746-114">答：</span><span class="sxs-lookup"><span data-stu-id="97746-114">A.</span></span> <span data-ttu-id="97746-115">使用者必須具有有效的帳戶，才能存取隔離中自己的郵件。</span><span class="sxs-lookup"><span data-stu-id="97746-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="97746-116">獨立 EOP 要求使用者在 EOP 中以郵件使用者的身分呈現（透過目錄同步處理手動建立或建立）。</span><span class="sxs-lookup"><span data-stu-id="97746-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="97746-117">如需在獨立 EOP 環境中管理使用者的詳細資訊，請參閱[Manage mail users IN EOP](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="97746-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="97746-118">問：哪些郵件可以讓使用者在隔離區中存取？</span><span class="sxs-lookup"><span data-stu-id="97746-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="97746-119">答：</span><span class="sxs-lookup"><span data-stu-id="97746-119">A.</span></span> <span data-ttu-id="97746-120">使用者可以存取垃圾郵件、大量電子郵件，以及（從2020年4月的）網路釣魚郵件，其為收件者。</span><span class="sxs-lookup"><span data-stu-id="97746-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="97746-121">由於將**郵件傳遞至**郵件流程規則（也稱為傳輸規則）中的主控隔離動作，因此使用者無法存取隔離的惡意程式碼、高信賴網路釣魚或已隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="97746-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="97746-122">如需存取隔離郵件之使用者的詳細資訊，請參閱[在 Office 365 中尋找及發行隔離郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="97746-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="97746-123">問：郵件保存在隔離區中的時間多久？</span><span class="sxs-lookup"><span data-stu-id="97746-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="97746-124">答：</span><span class="sxs-lookup"><span data-stu-id="97746-124">A.</span></span> <span data-ttu-id="97746-125">您可以使用反垃圾郵件原則，設定隔離區中的垃圾郵件、網路釣魚和大量電子郵件的保留時間。</span><span class="sxs-lookup"><span data-stu-id="97746-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="97746-126">預設值為30天，也就是最大值。</span><span class="sxs-lookup"><span data-stu-id="97746-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="97746-127">如需詳細資訊，請參閱[在 Office 365 設定反垃圾郵件原則](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="97746-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="97746-128">針對由郵件流程規則動作隔離的郵件，會將**郵件傳遞至主控隔離區**，並將郵件保留30天。</span><span class="sxs-lookup"><span data-stu-id="97746-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="97746-129">您無法設定此持續時間。</span><span class="sxs-lookup"><span data-stu-id="97746-129">You can't configure this duration.</span></span>

<span data-ttu-id="97746-130">時段到期後，郵件即會刪除，而且無法復原。</span><span class="sxs-lookup"><span data-stu-id="97746-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="97746-131">問：一次可以放開或報告一封以上的隔離郵件？</span><span class="sxs-lookup"><span data-stu-id="97746-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="97746-132">答：</span><span class="sxs-lookup"><span data-stu-id="97746-132">A.</span></span> <span data-ttu-id="97746-133">在 [安全性 & 規範中心] 中，您可以一次選取及發行最多100封郵件。</span><span class="sxs-lookup"><span data-stu-id="97746-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="97746-134">系統管理員可以使用 Exchange Online 中的[Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)和[Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) Cmdlet PowerShell 或獨立 Exchange online Protection PowerShell 以大量尋找及發行隔離的郵件，以及大量報告誤報。</span><span class="sxs-lookup"><span data-stu-id="97746-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="97746-135">Q：搜尋隔離郵件時是否支援萬用字元？</span><span class="sxs-lookup"><span data-stu-id="97746-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="97746-136">是否可以搜尋特定網域的隔離郵件？</span><span class="sxs-lookup"><span data-stu-id="97746-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="97746-137">答：</span><span class="sxs-lookup"><span data-stu-id="97746-137">A.</span></span> <span data-ttu-id="97746-138">在安全性 & 規範中心內不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="97746-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="97746-139">例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="97746-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="97746-140">不過，您可以在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="97746-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="97746-141">例如，執行下列命令，尋找來自網域 contoso.com 中所有寄件者的垃圾郵件隔離郵件：</span><span class="sxs-lookup"><span data-stu-id="97746-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="97746-142">然後，執行下列命令，以將這些郵件釋放給所有原始收件者：</span><span class="sxs-lookup"><span data-stu-id="97746-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="97746-143">在您發佈郵件後，就無法再放開。</span><span class="sxs-lookup"><span data-stu-id="97746-143">After you release a message, you can't release it again.</span></span>
