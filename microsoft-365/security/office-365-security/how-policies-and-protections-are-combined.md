---
title: 電子郵件保護的順序和優先順序
keywords: 安全性，惡意程式碼，Microsoft 365，M365，安全性中心，ATP，Microsoft Defender ATP，Office 365 ATP，Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解 Exchange Online Protection (EOP) 中的保護應用程式順序，以及保護原則中的優先順序值如何決定所套用的原則。
ms.openlocfilehash: e2da22bfbe0e7df70cf8d8b0d8cfd09eaf6e2ee3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196044"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="9c22a-104">電子郵件保護的順序和優先順序</span><span class="sxs-lookup"><span data-stu-id="9c22a-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9c22a-105">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，輸入的電子郵件可能會以多種保護形式進行標記。</span><span class="sxs-lookup"><span data-stu-id="9c22a-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="9c22a-106">例如，可供所有 Microsoft 365 客戶使用的內建 EOP 防網路釣魚原則，以及 Office 365 高級威脅防護中也可使用的更強健的 ATP 反網路釣魚原則 (Office 365 ATP) 客戶。</span><span class="sxs-lookup"><span data-stu-id="9c22a-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection (Office 365 ATP) customers.</span></span> <span data-ttu-id="9c22a-107">郵件也會透過多個偵測掃描進行惡意程式碼、垃圾郵件、網路釣魚等的掃描。在此活動中，可能會對套用的原則產生一些混淆。</span><span class="sxs-lookup"><span data-stu-id="9c22a-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="9c22a-108">一般說來，套用至郵件的原則會在**CAT (Category) **屬性的**X-Forefront-Antispam-Report**標頭中識別。</span><span class="sxs-lookup"><span data-stu-id="9c22a-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="9c22a-109">如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。</span><span class="sxs-lookup"><span data-stu-id="9c22a-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="9c22a-110">有兩個主要因素會決定要套用至郵件的原則：</span><span class="sxs-lookup"><span data-stu-id="9c22a-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="9c22a-111">**電子郵件保護類型的優先順序**：此順序並不是可設定的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="9c22a-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="9c22a-112">優先順序</span><span class="sxs-lookup"><span data-stu-id="9c22a-112">Priority</span></span>|<span data-ttu-id="9c22a-113">電子郵件保護</span><span class="sxs-lookup"><span data-stu-id="9c22a-113">Email protection</span></span>|<span data-ttu-id="9c22a-114">類別</span><span class="sxs-lookup"><span data-stu-id="9c22a-114">Category</span></span>|<span data-ttu-id="9c22a-115">要管理的位置</span><span class="sxs-lookup"><span data-stu-id="9c22a-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="9c22a-116">1</span><span class="sxs-lookup"><span data-stu-id="9c22a-116">1</span></span>|<span data-ttu-id="9c22a-117">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="9c22a-117">Malware</span></span>|<span data-ttu-id="9c22a-118">CAT： MALW</span><span class="sxs-lookup"><span data-stu-id="9c22a-118">CAT:MALW</span></span>|[<span data-ttu-id="9c22a-119">在 EOP 中設定反惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="9c22a-120">2 </span><span class="sxs-lookup"><span data-stu-id="9c22a-120">2</span></span>|<span data-ttu-id="9c22a-121">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="9c22a-121">Phishing</span></span>|<span data-ttu-id="9c22a-122">CAT： PHSH</span><span class="sxs-lookup"><span data-stu-id="9c22a-122">CAT:PHSH</span></span>|[<span data-ttu-id="9c22a-123">在 EOP 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="9c22a-124">個</span><span class="sxs-lookup"><span data-stu-id="9c22a-124">3</span></span>|<span data-ttu-id="9c22a-125">高信賴度的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="9c22a-125">High confidence spam</span></span>|<span data-ttu-id="9c22a-126">CAT： HSPM</span><span class="sxs-lookup"><span data-stu-id="9c22a-126">CAT:HSPM</span></span>|[<span data-ttu-id="9c22a-127">在 EOP 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="9c22a-128">4 </span><span class="sxs-lookup"><span data-stu-id="9c22a-128">4</span></span>|<span data-ttu-id="9c22a-129">詐騙</span><span class="sxs-lookup"><span data-stu-id="9c22a-129">Spoofing</span></span>|<span data-ttu-id="9c22a-130">CAT：欺騙</span><span class="sxs-lookup"><span data-stu-id="9c22a-130">CAT:SPOOF</span></span>|[<span data-ttu-id="9c22a-131">在 EOP 中設定欺騙情報</span><span class="sxs-lookup"><span data-stu-id="9c22a-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="9c22a-132">5 </span><span class="sxs-lookup"><span data-stu-id="9c22a-132">5</span></span>|<span data-ttu-id="9c22a-133">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="9c22a-133">Spam</span></span>|<span data-ttu-id="9c22a-134">CAT： SPM</span><span class="sxs-lookup"><span data-stu-id="9c22a-134">CAT:SPM</span></span>|[<span data-ttu-id="9c22a-135">在 EOP 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-135">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="9c22a-136">6 </span><span class="sxs-lookup"><span data-stu-id="9c22a-136">6</span></span>|<span data-ttu-id="9c22a-137">大量</span><span class="sxs-lookup"><span data-stu-id="9c22a-137">Bulk</span></span>|<span data-ttu-id="9c22a-138">CAT：大量</span><span class="sxs-lookup"><span data-stu-id="9c22a-138">CAT:BULK</span></span>|[<span data-ttu-id="9c22a-139">在 EOP 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-139">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="9c22a-140">7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c22a-140">7<sup>\*</sup></span></span>|<span data-ttu-id="9c22a-141">網域模擬 (受保護的使用者) </span><span class="sxs-lookup"><span data-stu-id="9c22a-141">Domain impersonation (protected users)</span></span>|<span data-ttu-id="9c22a-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="9c22a-142">DIMP</span></span>|[<span data-ttu-id="9c22a-143">設定 ATP 防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-143">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="9c22a-144">8：00<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c22a-144">8<sup>\*</sup></span></span>|<span data-ttu-id="9c22a-145">使用者模擬 (受保護的網域) </span><span class="sxs-lookup"><span data-stu-id="9c22a-145">User impersonation (protected domains)</span></span>|<span data-ttu-id="9c22a-146">UIMP</span><span class="sxs-lookup"><span data-stu-id="9c22a-146">UIMP</span></span>|[<span data-ttu-id="9c22a-147">設定 ATP 防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-147">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="9c22a-148"><sup>\*</sup> 這些功能只有在 ATP 反網路釣魚原則中才能使用。</span><span class="sxs-lookup"><span data-stu-id="9c22a-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="9c22a-149">**原則的優先順序**：針對每個防護類型 (反垃圾郵件、反惡意程式碼、反網路釣魚等 ) ，都有一個適用于每個人的預設原則，但您可以建立適用于特定使用者的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="9c22a-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="9c22a-150">每個自訂原則都有一個優先順序值，以決定原則的套用順序。</span><span class="sxs-lookup"><span data-stu-id="9c22a-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="9c22a-151">預設原則永遠套用於最後。</span><span class="sxs-lookup"><span data-stu-id="9c22a-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="9c22a-152">如果使用者是在相同類型的多個原則中定義，則只有具有最高優先順序的原則適用于。</span><span class="sxs-lookup"><span data-stu-id="9c22a-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="9c22a-153">不會評估該類型的任何其餘原則 (包括預設原則) 。</span><span class="sxs-lookup"><span data-stu-id="9c22a-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="9c22a-154">例如，請考慮下列 **適用于相同使用者**的 ATP 反網路釣魚原則，以及識別為使用者模擬和欺騙的郵件：</span><span class="sxs-lookup"><span data-stu-id="9c22a-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="9c22a-155">ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="9c22a-155">ATP anti-phishing policy</span></span>|<span data-ttu-id="9c22a-156">優先順序</span><span class="sxs-lookup"><span data-stu-id="9c22a-156">Priority</span></span>|<span data-ttu-id="9c22a-157">使用者模擬</span><span class="sxs-lookup"><span data-stu-id="9c22a-157">User impersonation</span></span>|<span data-ttu-id="9c22a-158">反詐騙</span><span class="sxs-lookup"><span data-stu-id="9c22a-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="9c22a-159">原則 A</span><span class="sxs-lookup"><span data-stu-id="9c22a-159">Policy A</span></span>|<span data-ttu-id="9c22a-160">1</span><span class="sxs-lookup"><span data-stu-id="9c22a-160">1</span></span>|<span data-ttu-id="9c22a-161">開啟</span><span class="sxs-lookup"><span data-stu-id="9c22a-161">On</span></span>|<span data-ttu-id="9c22a-162">關閉</span><span class="sxs-lookup"><span data-stu-id="9c22a-162">Off</span></span>|
  |<span data-ttu-id="9c22a-163">原則 B</span><span class="sxs-lookup"><span data-stu-id="9c22a-163">Policy B</span></span>|<span data-ttu-id="9c22a-164">2 </span><span class="sxs-lookup"><span data-stu-id="9c22a-164">2</span></span>|<span data-ttu-id="9c22a-165">關閉</span><span class="sxs-lookup"><span data-stu-id="9c22a-165">Off</span></span>|<span data-ttu-id="9c22a-166">開啟</span><span class="sxs-lookup"><span data-stu-id="9c22a-166">On</span></span>|
  |

1. <span data-ttu-id="9c22a-167">郵件會標示及視為欺騙性，因為哄騙具有比使用者模擬 (8) 更高優先順序的 (4) 。</span><span class="sxs-lookup"><span data-stu-id="9c22a-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="9c22a-168">原則 A 會套用至使用者，因為其優先順序高於原則 B。</span><span class="sxs-lookup"><span data-stu-id="9c22a-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="9c22a-169">根據原則 A 中的設定，不會對郵件採取任何動作，因為會在原則中關閉反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="9c22a-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="9c22a-170">原則處理會停止，因此原則 B 永遠不會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="9c22a-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="9c22a-171">因為相同的使用者可能會故意或無意中包含相同類型的多個自訂原則，所以請針對自訂原則使用下列設計原則：</span><span class="sxs-lookup"><span data-stu-id="9c22a-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="9c22a-172">指派較高優先順序的原則套用至少量的使用者，以及套用至大量使用者之原則的優先順序較低。</span><span class="sxs-lookup"><span data-stu-id="9c22a-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="9c22a-173">請記住，預設原則永遠會最後套用。</span><span class="sxs-lookup"><span data-stu-id="9c22a-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="9c22a-174">設定較高優先順序的原則，使其具有比低優先順序原則更嚴格或更多的特殊設定。</span><span class="sxs-lookup"><span data-stu-id="9c22a-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="9c22a-175">請考慮使用較少的自訂原則 (只對需要更嚴格或更多專用設定) 的使用者使用自訂原則。</span><span class="sxs-lookup"><span data-stu-id="9c22a-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
