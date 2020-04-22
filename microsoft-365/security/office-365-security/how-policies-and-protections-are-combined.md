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
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 說明 Office 365 保護的應用程式順序，以及保護原則中的優先順序值如何決定所套用的原則。
ms.openlocfilehash: ed4806bad6299dc5a5380bec2f6e1247f9d6b448
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633963"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="b1364-104">電子郵件保護的順序和優先順序</span><span class="sxs-lookup"><span data-stu-id="b1364-104">Order and precedence of email protection</span></span>

<span data-ttu-id="b1364-105">做為 Microsoft 365 使用者，您的輸入電子郵件可能會以多種保護形式進行標記。</span><span class="sxs-lookup"><span data-stu-id="b1364-105">As a Microsoft 365 user, your inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="b1364-106">例如，適用于所有 Microsoft 365 客戶的內建 EOP 防網路釣魚原則，以及 Office 365 高級威脅防護客戶也可以使用的更強健的 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="b1364-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection customers.</span></span> <span data-ttu-id="b1364-107">郵件也會透過多個偵測掃描進行惡意程式碼、垃圾郵件、網路釣魚等的掃描。在此活動中，可能會對套用的原則產生一些混淆。</span><span class="sxs-lookup"><span data-stu-id="b1364-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="b1364-108">一般說來，套用至郵件的原則會在**CAT （類別）** 屬性的**X-Forefront-Antispam-Report**標頭中識別。</span><span class="sxs-lookup"><span data-stu-id="b1364-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="b1364-109">如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。</span><span class="sxs-lookup"><span data-stu-id="b1364-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="b1364-110">有兩個主要因素會決定要套用至郵件的原則：</span><span class="sxs-lookup"><span data-stu-id="b1364-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="b1364-111">**電子郵件保護類型的優先順序**：此順序並不是可設定的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="b1364-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="b1364-112">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="b1364-112">**Priority**</span></span>|<span data-ttu-id="b1364-113">**電子郵件保護**</span><span class="sxs-lookup"><span data-stu-id="b1364-113">**Email protection**</span></span>|<span data-ttu-id="b1364-114">**類別**</span><span class="sxs-lookup"><span data-stu-id="b1364-114">**Category**</span></span>|<span data-ttu-id="b1364-115">**要管理的位置**</span><span class="sxs-lookup"><span data-stu-id="b1364-115">**Where to manage**</span></span>|
  |<span data-ttu-id="b1364-116">1 </span><span class="sxs-lookup"><span data-stu-id="b1364-116">1</span></span>|<span data-ttu-id="b1364-117">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="b1364-117">Malware</span></span>|<span data-ttu-id="b1364-118">CAT： MALW</span><span class="sxs-lookup"><span data-stu-id="b1364-118">CAT:MALW</span></span>|[<span data-ttu-id="b1364-119">在 Office 365 中設定反惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="b1364-119">Configure anti-malware policies in Office 365</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="b1364-120">2 </span><span class="sxs-lookup"><span data-stu-id="b1364-120">2</span></span>|<span data-ttu-id="b1364-121">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="b1364-121">Phishing</span></span>|<span data-ttu-id="b1364-122">CAT： PHSH</span><span class="sxs-lookup"><span data-stu-id="b1364-122">CAT:PHSH</span></span>|[<span data-ttu-id="b1364-123">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="b1364-123">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b1364-124">3 </span><span class="sxs-lookup"><span data-stu-id="b1364-124">3</span></span>|<span data-ttu-id="b1364-125">高信賴度的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b1364-125">High confidence spam</span></span>|<span data-ttu-id="b1364-126">CAT： HSPM</span><span class="sxs-lookup"><span data-stu-id="b1364-126">CAT:HSPM</span></span>|[<span data-ttu-id="b1364-127">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="b1364-127">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b1364-128">4 </span><span class="sxs-lookup"><span data-stu-id="b1364-128">4</span></span>|<span data-ttu-id="b1364-129">詐騙</span><span class="sxs-lookup"><span data-stu-id="b1364-129">Spoofing</span></span>|<span data-ttu-id="b1364-130">CAT：欺騙</span><span class="sxs-lookup"><span data-stu-id="b1364-130">CAT:SPOOF</span></span>|[<span data-ttu-id="b1364-131">在 Office 365 中設定假冒情報</span><span class="sxs-lookup"><span data-stu-id="b1364-131">Configure spoof intelligence in Office 365</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="b1364-132">5 </span><span class="sxs-lookup"><span data-stu-id="b1364-132">5</span></span>|<span data-ttu-id="b1364-133">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b1364-133">Spam</span></span>|<span data-ttu-id="b1364-134">CAT： SPM</span><span class="sxs-lookup"><span data-stu-id="b1364-134">CAT:SPM</span></span>|[<span data-ttu-id="b1364-135">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="b1364-135">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b1364-136">6 </span><span class="sxs-lookup"><span data-stu-id="b1364-136">6</span></span>|<span data-ttu-id="b1364-137">大量</span><span class="sxs-lookup"><span data-stu-id="b1364-137">Bulk</span></span>|<span data-ttu-id="b1364-138">CAT：大量</span><span class="sxs-lookup"><span data-stu-id="b1364-138">CAT:BULK</span></span>|[<span data-ttu-id="b1364-139">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="b1364-139">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b1364-140">7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b1364-140">7<sup>\*</sup></span></span>|<span data-ttu-id="b1364-141">網域模仿（受保護的使用者）</span><span class="sxs-lookup"><span data-stu-id="b1364-141">Domain impersonation (protected users)</span></span>|<span data-ttu-id="b1364-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="b1364-142">DIMP</span></span>|[<span data-ttu-id="b1364-143">在 Office 365 中設定 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="b1364-143">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="b1364-144">8：00<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b1364-144">8<sup>\*</sup></span></span>|<span data-ttu-id="b1364-145">使用者類比（受保護的網域）</span><span class="sxs-lookup"><span data-stu-id="b1364-145">User impersonation (protected domains)</span></span>|<span data-ttu-id="b1364-146">UIMP</span><span class="sxs-lookup"><span data-stu-id="b1364-146">UIMP</span></span>|[<span data-ttu-id="b1364-147">在 Office 365 中設定 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="b1364-147">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="b1364-148"><sup>\*</sup>這些功能只有在 ATP 反網路釣魚原則中才能使用。</span><span class="sxs-lookup"><span data-stu-id="b1364-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="b1364-149">**原則的優先順序**：針對每一種保護類型（反垃圾郵件、反惡意程式碼、反網路釣魚等等），都有一個適用于每個人的預設原則，但您通常可以建立適用于特定使用者的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="b1364-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can often create custom policies that apply to specific users.</span></span> <span data-ttu-id="b1364-150">每個自訂原則都有一個優先順序值，以決定原則的套用順序。</span><span class="sxs-lookup"><span data-stu-id="b1364-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="b1364-151">預設原則永遠套用於最後。</span><span class="sxs-lookup"><span data-stu-id="b1364-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="b1364-152">如果使用者是在相同類型的多個原則中定義，則只有具有最高優先順序的原則適用于。</span><span class="sxs-lookup"><span data-stu-id="b1364-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="b1364-153">不會為使用者評估任何其他類型的原則（包括預設原則）。</span><span class="sxs-lookup"><span data-stu-id="b1364-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="b1364-154">例如，請考慮下列**適用于相同使用者**的 ATP 反網路釣魚原則，以及識別為使用者模擬和欺騙的郵件：</span><span class="sxs-lookup"><span data-stu-id="b1364-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="b1364-155">**ATP 反網路釣魚原則**</span><span class="sxs-lookup"><span data-stu-id="b1364-155">**ATP anti-phishing policy**</span></span>|<span data-ttu-id="b1364-156">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="b1364-156">**Priority**</span></span>|<span data-ttu-id="b1364-157">**使用者模擬**</span><span class="sxs-lookup"><span data-stu-id="b1364-157">**User impersonation**</span></span>|<span data-ttu-id="b1364-158">**反詐騙**</span><span class="sxs-lookup"><span data-stu-id="b1364-158">**Anti-spoofing**</span></span>|
  |<span data-ttu-id="b1364-159">原則 A</span><span class="sxs-lookup"><span data-stu-id="b1364-159">Policy A</span></span>|<span data-ttu-id="b1364-160">1 </span><span class="sxs-lookup"><span data-stu-id="b1364-160">1</span></span>|<span data-ttu-id="b1364-161">開啟</span><span class="sxs-lookup"><span data-stu-id="b1364-161">On</span></span>|<span data-ttu-id="b1364-162">關閉</span><span class="sxs-lookup"><span data-stu-id="b1364-162">Off</span></span>|
  |<span data-ttu-id="b1364-163">原則 B</span><span class="sxs-lookup"><span data-stu-id="b1364-163">Policy B</span></span>|<span data-ttu-id="b1364-164">2 </span><span class="sxs-lookup"><span data-stu-id="b1364-164">2</span></span>|<span data-ttu-id="b1364-165">關閉</span><span class="sxs-lookup"><span data-stu-id="b1364-165">Off</span></span>|<span data-ttu-id="b1364-166">開啟</span><span class="sxs-lookup"><span data-stu-id="b1364-166">On</span></span>|
  |

1. <span data-ttu-id="b1364-167">郵件會標示並視為欺騙性，因為哄騙具有比使用者模擬（8）更高的優先順序（4）。</span><span class="sxs-lookup"><span data-stu-id="b1364-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="b1364-168">原則 A 會套用至使用者，因為其優先順序高於原則 B。</span><span class="sxs-lookup"><span data-stu-id="b1364-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="b1364-169">根據原則 A 中的設定，不會對郵件採取任何動作，因為會在原則中關閉反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="b1364-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="b1364-170">原則處理會停止，因此原則 B 永遠不會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="b1364-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="b1364-171">因為相同的使用者可能會故意或無意中包含相同類型的多個自訂原則，所以請針對自訂原則使用下列設計原則：</span><span class="sxs-lookup"><span data-stu-id="b1364-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="b1364-172">指派較高優先順序的原則套用至少量的使用者，以及套用至大量使用者之原則的優先順序較低。</span><span class="sxs-lookup"><span data-stu-id="b1364-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="b1364-173">請記住，預設原則永遠會最後套用。</span><span class="sxs-lookup"><span data-stu-id="b1364-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="b1364-174">設定較高優先順序的原則，使其具有比低優先順序原則更嚴格或更多的特殊設定。</span><span class="sxs-lookup"><span data-stu-id="b1364-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="b1364-175">請考慮使用較少的自訂原則（只對需要更嚴格或更多特殊設定的使用者使用自訂原則）。</span><span class="sxs-lookup"><span data-stu-id="b1364-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
