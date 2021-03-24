---
title: 隔離的郵件常見問題
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以在 Exchange Online Protection (EOP) 中查看有關隔離郵件的常見問題和解答。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 342f6b7f27c99352c4e5906799ce463b658e0c87
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059575"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="5cb41-103">隔離的郵件常見問題</span><span class="sxs-lookup"><span data-stu-id="5cb41-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5cb41-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5cb41-104">**Applies to**</span></span>
- [<span data-ttu-id="5cb41-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5cb41-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5cb41-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="5cb41-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5cb41-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cb41-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5cb41-108">本主題針對 Exchange Online 中的信箱或獨立 Exchange Online Protection (EOP) 組織中的 exchange 電子郵件，提供有關隔離365的電子郵件的常見問題和解答，但沒有 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="5cb41-108">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="5cb41-109">如需反垃圾郵件保護的相關問題和解答，請參閱 [反垃圾郵件保護常見問題](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb41-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="5cb41-110">如需有關反惡意程式碼保護的問題和解答，請參閱 [反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb41-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="5cb41-111">如需反欺騙保護的相關問題和解答，請參閱 [反欺騙保護常見問題](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb41-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="5cb41-112">如何管理被隔離以進行惡意程式碼的郵件？</span><span class="sxs-lookup"><span data-stu-id="5cb41-112">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="5cb41-113">只有系統管理員可以管理隔離惡意程式碼的郵件。</span><span class="sxs-lookup"><span data-stu-id="5cb41-113">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="5cb41-114">如需詳細資訊，請參閱 [以系統管理員身分管理被隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="5cb41-114">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="5cb41-115">如何隔離垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="5cb41-115">How do I quarantine spam?</span></span>

<span data-ttu-id="5cb41-116">依預設，歸類為垃圾郵件或大量電子郵件的郵件會傳遞至使用者的信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5cb41-116">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="5cb41-117">不過，您也可以建立並設定反垃圾郵件原則，以隔離垃圾郵件或大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5cb41-117">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="5cb41-118">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb41-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="5cb41-119">如何讓使用者能夠存取隔離區？</span><span class="sxs-lookup"><span data-stu-id="5cb41-119">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="5cb41-120">使用者必須具有有效的帳戶，才能存取隔離中自己的郵件。</span><span class="sxs-lookup"><span data-stu-id="5cb41-120">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="5cb41-121">獨立 EOP 要求使用者在 EOP (會以目錄同步處理) 手動建立或建立的方式呈現給郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="5cb41-121">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="5cb41-122">如需在獨立 EOP 環境中管理使用者的詳細資訊，請參閱 [Manage mail users IN EOP](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb41-122">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="5cb41-123">使用者可以在隔離區中存取哪些郵件？</span><span class="sxs-lookup"><span data-stu-id="5cb41-123">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="5cb41-124">使用者可以存取垃圾郵件、大量電子郵件，以及從2020年4月的 () 網路釣魚郵件的收件者。</span><span class="sxs-lookup"><span data-stu-id="5cb41-124">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="5cb41-125">使用者無法存取隔離的惡意程式碼、高信賴網路釣魚或因將郵件傳遞至郵件流程規則中 **主控的隔離** 動作而隔離的郵件 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="5cb41-125">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="5cb41-126">如需存取隔離郵件之使用者的詳細資訊，請參閱 [尋找和以使用者身分發行隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb41-126">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="5cb41-127">郵件保存在隔離區中的時間多久？</span><span class="sxs-lookup"><span data-stu-id="5cb41-127">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="5cb41-128">您可以使用反垃圾郵件原則，設定隔離區中的垃圾郵件、網路釣魚和大量電子郵件的保留時間。</span><span class="sxs-lookup"><span data-stu-id="5cb41-128">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="5cb41-129">預設值為30天，也就是最大值。</span><span class="sxs-lookup"><span data-stu-id="5cb41-129">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="5cb41-130">如需詳細資訊，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5cb41-130">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="5cb41-131">針對由郵件流程規則動作隔離的郵件，會將 **郵件傳遞至主控隔離區**，並將郵件保留30天。</span><span class="sxs-lookup"><span data-stu-id="5cb41-131">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="5cb41-132">您無法設定此持續時間。</span><span class="sxs-lookup"><span data-stu-id="5cb41-132">You can't configure this duration.</span></span>

<span data-ttu-id="5cb41-133">時段到期後，郵件即會刪除，而且無法復原。</span><span class="sxs-lookup"><span data-stu-id="5cb41-133">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="5cb41-134">我是否可以一次放開或報告一封以上的隔離郵件？</span><span class="sxs-lookup"><span data-stu-id="5cb41-134">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="5cb41-135">在 [安全性 & 規範中心] 中，您可以一次選取及發行最多100封郵件。</span><span class="sxs-lookup"><span data-stu-id="5cb41-135">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="5cb41-136">系統管理員可以使用 Exchange Online PowerShell 或獨立 EOP PowerShell 中的 [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) Cmdlet，以大量尋找及發行隔離的郵件，並大量報告誤報。</span><span class="sxs-lookup"><span data-stu-id="5cb41-136">Admins can use the the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="5cb41-137">搜尋隔離郵件時，是否支援萬用字元？</span><span class="sxs-lookup"><span data-stu-id="5cb41-137">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="5cb41-138">是否可以搜尋特定網域的隔離郵件？</span><span class="sxs-lookup"><span data-stu-id="5cb41-138">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="5cb41-139">在安全性 & 規範中心內不支援萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5cb41-139">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="5cb41-140">例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5cb41-140">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="5cb41-141">不過，您可以在 Exchange Online PowerShell 或獨立 EOP PowerShell 中使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5cb41-141">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="5cb41-142">例如，將下列 PowerShell 程式碼複製到 [記事本] 中，並將檔案儲存為. ps1 在輕鬆找到 (的位置，例如 C:\Data\QuarantineRelease.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="5cb41-142">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="5cb41-143">當您連線至 [Exchange online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 或 [exchange online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)之後，請執行下列命令以執行腳本：</span><span class="sxs-lookup"><span data-stu-id="5cb41-143">Then, after you connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="5cb41-144">腳本會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5cb41-144">The script does the following actions:</span></span>

- <span data-ttu-id="5cb41-145">尋找以垃圾郵件隔離的 unreleased 郵件（來自 fabrikam 網域中的所有寄件者）。</span><span class="sxs-lookup"><span data-stu-id="5cb41-145">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="5cb41-146">結果的最大數目為 50000 (50 頁面的1000結果) 。</span><span class="sxs-lookup"><span data-stu-id="5cb41-146">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="5cb41-147">將結果儲存至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="5cb41-147">Save the results to a CSV file.</span></span>
- <span data-ttu-id="5cb41-148">釋放對應的隔離郵件給所有原始收件者。</span><span class="sxs-lookup"><span data-stu-id="5cb41-148">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="5cb41-149">在您發佈郵件後，就無法再放開。</span><span class="sxs-lookup"><span data-stu-id="5cb41-149">After you release a message, you can't release it again.</span></span>