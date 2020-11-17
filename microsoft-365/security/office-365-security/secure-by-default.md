---
title: Office 365 中預設的安全性
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '深入瞭解 Exchange Online Protection (EOP 中的安全性預設設定) '
ms.openlocfilehash: d4345134e98ae204f73dfb51a0abf5136590a24c
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126658"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="ae07f-103">Office 365 中預設的安全性</span><span class="sxs-lookup"><span data-stu-id="ae07f-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ae07f-104">「預設使用安全」是一種術語，用來定義盡可能最安全的預設設定。</span><span class="sxs-lookup"><span data-stu-id="ae07f-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="ae07f-105">不過，安全性需要與生產力進行平衡。</span><span class="sxs-lookup"><span data-stu-id="ae07f-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="ae07f-106">這可能包括平衡：</span><span class="sxs-lookup"><span data-stu-id="ae07f-106">This can include balancing across:</span></span>

- <span data-ttu-id="ae07f-107">可用性：設定不應該以使用者生產力的方式取得。</span><span class="sxs-lookup"><span data-stu-id="ae07f-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="ae07f-108">風險：安全性可能會封鎖重要的活動。</span><span class="sxs-lookup"><span data-stu-id="ae07f-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="ae07f-109">舊的設定：有些舊版產品及功能的設定可能出於商務原因而必須維護，即使新的新式設定也有所改善。</span><span class="sxs-lookup"><span data-stu-id="ae07f-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="ae07f-110">在 Exchange Online 中使用信箱的 Microsoft 365 組織會受到 Exchange Online Protection (EOP) 的保護。</span><span class="sxs-lookup"><span data-stu-id="ae07f-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="ae07f-111">這種保護包括：</span><span class="sxs-lookup"><span data-stu-id="ae07f-111">This protection includes:</span></span>

1. <span data-ttu-id="ae07f-112">具有可疑惡意軟體的電子郵件將會自動遭到隔離，並會通知收件者。</span><span class="sxs-lookup"><span data-stu-id="ae07f-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="ae07f-113">請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ae07f-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="ae07f-114">識別為「高信賴」的網路釣魚電子郵件會依照反垃圾郵件原則動作進行處理。</span><span class="sxs-lookup"><span data-stu-id="ae07f-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="ae07f-115">請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ae07f-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ae07f-116">因為 Microsoft 想要讓我們的客戶在預設情況下是安全的，所以部分承租人覆寫不會針對惡意程式碼或高可信度網路釣魚應用程式。</span><span class="sxs-lookup"><span data-stu-id="ae07f-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="ae07f-117">這些覆寫包括：</span><span class="sxs-lookup"><span data-stu-id="ae07f-117">These overrides include:</span></span>

- <span data-ttu-id="ae07f-118"> (反垃圾郵件原則所允許的寄件者清單或允許的網域清單) </span><span class="sxs-lookup"><span data-stu-id="ae07f-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="ae07f-119">Outlook 安全寄件者</span><span class="sxs-lookup"><span data-stu-id="ae07f-119">Outlook Safe senders</span></span>
- <span data-ttu-id="ae07f-120">IP 允許清單 (連線篩選) </span><span class="sxs-lookup"><span data-stu-id="ae07f-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="ae07f-121">您可以在 [ [建立安全的寄件者清單](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)] 中找到這些優先選項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ae07f-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="ae07f-122">在下列情況下安全保護此設定不是一種可能開啟或關閉的設定，但是我們的篩選功能會從盒出的方式，讓您的信箱無法使用可能有害或有害的郵件。</span><span class="sxs-lookup"><span data-stu-id="ae07f-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="ae07f-123">惡意程式碼和高可信度網路釣魚應該傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="ae07f-123">Malware and high confidence phishing should be sent to quarantine.</span></span> <span data-ttu-id="ae07f-124">只有系統管理員可以管理被隔離為惡意程式碼或高可信度網路釣魚的郵件，也可以從那裡向 Microsoft 報告誤報。</span><span class="sxs-lookup"><span data-stu-id="ae07f-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="ae07f-125">如需詳細資訊，請參閱 [在 EOP 中管理被隔離的郵件和檔案為系統管理員](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="ae07f-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="ae07f-126">例外狀況</span><span class="sxs-lookup"><span data-stu-id="ae07f-126">Exceptions</span></span>

<span data-ttu-id="ae07f-127">只有「高可信度網路釣魚」郵件可以略過篩選的唯一覆寫，Exchange 郵件流程規則 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="ae07f-127">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ae07f-128">若要使用郵件流程規則來略過篩選，請參閱 [使用郵件流程規則設定郵件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="ae07f-128">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="ae07f-129">覆寫只應該用於下列專案：</span><span class="sxs-lookup"><span data-stu-id="ae07f-129">Overrides should only be used for:</span></span>

- <span data-ttu-id="ae07f-130">網路釣魚模擬：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。</span><span class="sxs-lookup"><span data-stu-id="ae07f-130">Phishing simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="ae07f-131">安全性/SecOps 信箱：安全小組用來取得未篩選郵件 (良好且錯誤) 的專用信箱。</span><span class="sxs-lookup"><span data-stu-id="ae07f-131">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="ae07f-132">然後，小組可以查看是否包含惡意內容。</span><span class="sxs-lookup"><span data-stu-id="ae07f-132">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="ae07f-133">協力廠商篩選器：部分協力廠商廠商會建議您關閉 EOP (SCL =-1) ，因為協力廠商篩選器會管理郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="ae07f-133">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="ae07f-134">Microsoft 不建議關閉 EOP （適用于 Office 365 的 Defender 所需）。</span><span class="sxs-lookup"><span data-stu-id="ae07f-134">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="ae07f-135">誤報：您可能想要允許由 Microsoft 透過系統 [管理員報送](admin-submission.md)進行的某些郵件仍在進行分析。</span><span class="sxs-lookup"><span data-stu-id="ae07f-135">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="ae07f-136">就像所有覆寫一樣，建議它們是臨時性的。</span><span class="sxs-lookup"><span data-stu-id="ae07f-136">As with all overrides, it is recommended that they are temporary.</span></span>
