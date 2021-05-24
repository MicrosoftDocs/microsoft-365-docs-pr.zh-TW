---
title: Office 365 預設安全性
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '深入瞭解 Exchange Online Protection (EOP 中的 [安全的預設值] 設定) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d5cdc8f8faa9c2d5772fd1572134ea49cdd77da
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624046"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="3ff7f-103">Office 365 預設安全性</span><span class="sxs-lookup"><span data-stu-id="3ff7f-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ff7f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="3ff7f-104">**Applies to**</span></span>
- [<span data-ttu-id="3ff7f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3ff7f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3ff7f-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="3ff7f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3ff7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ff7f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3ff7f-108">「預設使用安全」是一種術語，用來定義盡可能最安全的預設設定。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="3ff7f-109">不過，安全性需要與生產力進行平衡。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="3ff7f-110">這可能包括平衡：</span><span class="sxs-lookup"><span data-stu-id="3ff7f-110">This can include balancing across:</span></span>

- <span data-ttu-id="3ff7f-111">**可用性**：設定不應該以使用者生產力的方式取得。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="3ff7f-112">**風險**：安全性可能會封鎖重要的活動。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="3ff7f-113">**舊的設定**：有些舊版產品及功能的設定可能出於商務原因而必須維護，即使新的新式設定也有所改善。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="3ff7f-114">使用 Exchange Online 中信箱的 Microsoft 365 組織會受到 Exchange Online Protection (EOP) 的保護。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="3ff7f-115">這種保護包括：</span><span class="sxs-lookup"><span data-stu-id="3ff7f-115">This protection includes:</span></span>

- <span data-ttu-id="3ff7f-116">具有可疑惡意軟體的電子郵件將會自動遭到隔離，並會通知收件者。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="3ff7f-117">請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="3ff7f-118">識別為高可信度網路釣魚的電子郵件會依照反垃圾郵件原則動作進行處理。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="3ff7f-119">請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3ff7f-120">如需 EOP 的詳細資訊，請參閱[Exchange Online Protection 總覽](exchange-online-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="3ff7f-121">因為 Microsoft 想要讓客戶保持安全，但在預設情況下，有些承租人覆寫不會套用到惡意程式碼或高可信度網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="3ff7f-122">這些覆寫包括：</span><span class="sxs-lookup"><span data-stu-id="3ff7f-122">These overrides include:</span></span>

- <span data-ttu-id="3ff7f-123"> (反垃圾郵件原則所允許的寄件者清單或允許的網域清單) </span><span class="sxs-lookup"><span data-stu-id="3ff7f-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="3ff7f-124">Outlook安全寄件者</span><span class="sxs-lookup"><span data-stu-id="3ff7f-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="3ff7f-125">IP 允許清單 (連線篩選) </span><span class="sxs-lookup"><span data-stu-id="3ff7f-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="3ff7f-126">您可以在 [ [建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)] 中找到這些優先選項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3ff7f-127">我們正在取代 [ **將郵件移至垃圾郵件資料夾** ] 動作，以取得 EOP 反垃圾郵件原則中的 **高可信度網路釣魚電子郵件** 。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="3ff7f-128">使用此動作進行高可信度網路釣魚郵件的反垃圾郵件原則會轉換成 **隔離郵件**。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="3ff7f-129">高信賴網路釣魚郵件的重新 **導向電子郵件地址** 動作不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="3ff7f-130">安全的預設值不是可以開啟或關閉的設定，但是我們的篩選功能的方式，讓您的信箱不會有潛在危險或有害的郵件。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="3ff7f-131">應該隔離惡意程式碼和高可信度網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="3ff7f-132">只有系統管理員可以管理被隔離為惡意程式碼或高可信度網路釣魚的郵件，而且也可以從那裡向 Microsoft 報告誤報。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="3ff7f-133">如需詳細資訊，請參閱 [在 EOP 中管理被隔離的郵件和檔案為系統管理員](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="3ff7f-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="3ff7f-134">更深入瞭解為何這麼做</span><span class="sxs-lookup"><span data-stu-id="3ff7f-134">More on why we're doing this</span></span>

<span data-ttu-id="3ff7f-135">根據預設，安全的精神是：我們對郵件採取相同的動作，即使您知道郵件是惡意的，即使已設定的例外狀況允許傳送郵件也是一樣。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="3ff7f-136">這是我們永遠用於惡意程式碼的相同方法，現在我們將這種相同的行為擴充為高信賴網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="3ff7f-137">我們的資料會指出使用者的30倍于垃圾郵件資料夾和隔離區中的郵件中，按一下惡意連結的可能性也會比較高。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="3ff7f-138">我們的資料也會指出為高信賴網路釣魚郵件標示為錯誤) 的誤報比率 (很低，且系統管理員可以使用系統管理員提交來解析任何誤報。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="3ff7f-139">我們也會判斷反垃圾郵件原則中的允許寄件者與允許的網域清單和 Outlook 中的安全寄件者過於廣泛，造成的損害超過良好的損害。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="3ff7f-140">若要將它放在另一種方式中：作為一種安全性服務，我們將替您代表，以避免使用者遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span>

## <a name="exceptions"></a><span data-ttu-id="3ff7f-141">例外狀況</span><span class="sxs-lookup"><span data-stu-id="3ff7f-141">Exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="3ff7f-142">在2021年7月，安全性預設會擴充為 Exchange 郵件流程規則 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-142">In July 2021, secure by default will be extended to Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="3ff7f-143">如果您使用郵件流程規則來允許協力廠商網路釣魚模擬或未篩選的傳遞至安全作業信箱，您最後必須消除這些規則，並在 _有可用的功能時_，切換至使用 [高級傳遞原則](configure-advanced-delivery.md)。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-143">If you use mail flow rules to allow third-party phishing simulations or unfiltered delivery to security operation mailboxes, you eventually need to eliminate these rules and switch to using the [advanced delivery policy](configure-advanced-delivery.md) _when the feature is available to you_.</span></span>

<span data-ttu-id="3ff7f-144">唯一允許高信賴網路釣魚郵件旁路篩選的覆寫是郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-144">The only override that allows high confidence phishing message to bypass filtering is mail flow rules.</span></span> <span data-ttu-id="3ff7f-145">若要使用郵件流程規則來略過篩選，請參閱 [使用郵件流程規則設定郵件中的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-145">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="3ff7f-146">在下列案例中，您應該只考慮使用覆寫：</span><span class="sxs-lookup"><span data-stu-id="3ff7f-146">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="3ff7f-147">網路釣魚模擬：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-147">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="3ff7f-148">安全性/SecOps 信箱：安全小組用來取得未篩選郵件 (良好且錯誤) 的專用信箱。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-148">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="3ff7f-149">Teams 可以查看是否包含惡意內容。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-149">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="3ff7f-150">協力廠商篩選：當網域的 MX 記錄未指向 Office 365 時，Secure 預設不適用。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-150">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="3ff7f-151">誤報：您可能想要暫時允許由 Microsoft 透過系統 [管理員報送](admin-submission.md)進行的某些郵件仍在進行分析。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-151">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="3ff7f-152">就像所有覆寫一樣，建議它們是臨時性的。</span><span class="sxs-lookup"><span data-stu-id="3ff7f-152">As with all overrides, it is recommended that they are temporary.</span></span>
