---
title: Office 365 中的電子郵件保護順序和優先順序
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
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537410"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a><span data-ttu-id="97488-104">Office 365 中的電子郵件保護順序和優先順序</span><span class="sxs-lookup"><span data-stu-id="97488-104">Order and precedence of email protection in Office 365</span></span>

<span data-ttu-id="97488-105">在 Office 365 中，輸入的電子郵件會由其評估，因此可能會以多種保護形式（惡意程式碼、垃圾郵件、網路釣魚等）加以標記。</span><span class="sxs-lookup"><span data-stu-id="97488-105">In Office 365, inbound email is evaluated by, and therefore might be flagged by, multiple forms of protection (malware, spam, phishing, etc).</span></span> <span data-ttu-id="97488-106">在此活動中，可能很難判斷已套用的原則和順序。</span><span class="sxs-lookup"><span data-stu-id="97488-106">Given all of this activity, it can be hard to determine which policy was applied and in what order.</span></span>

<span data-ttu-id="97488-107">一般說來，套用至郵件的原則會在**CAT （類別）** 屬性的**X-Forefront-Antispam-Report**標頭中識別。</span><span class="sxs-lookup"><span data-stu-id="97488-107">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="97488-108">如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。</span><span class="sxs-lookup"><span data-stu-id="97488-108">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="97488-109">有兩個主要因素會決定要套用至郵件的原則：</span><span class="sxs-lookup"><span data-stu-id="97488-109">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="97488-110">**電子郵件保護類型的優先順序**：此順序並不是可設定的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="97488-110">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="97488-111">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="97488-111">**Priority**</span></span>|<span data-ttu-id="97488-112">**電子郵件保護**</span><span class="sxs-lookup"><span data-stu-id="97488-112">**Email protection**</span></span>|<span data-ttu-id="97488-113">**類別**</span><span class="sxs-lookup"><span data-stu-id="97488-113">**Category**</span></span>|<span data-ttu-id="97488-114">**要管理的位置**</span><span class="sxs-lookup"><span data-stu-id="97488-114">**Where to manage**</span></span>|
  |<span data-ttu-id="97488-115">1 </span><span class="sxs-lookup"><span data-stu-id="97488-115">1</span></span>|<span data-ttu-id="97488-116">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="97488-116">Malware</span></span>|<span data-ttu-id="97488-117">CAT： MALW</span><span class="sxs-lookup"><span data-stu-id="97488-117">CAT:MALW</span></span>|[<span data-ttu-id="97488-118">在 Office 365 中設定反惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="97488-118">Configure anti-malware policies in Office 365</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="97488-119">2 </span><span class="sxs-lookup"><span data-stu-id="97488-119">2</span></span>|<span data-ttu-id="97488-120">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="97488-120">Phishing</span></span>|<span data-ttu-id="97488-121">CAT： PHSH</span><span class="sxs-lookup"><span data-stu-id="97488-121">CAT:PHSH</span></span>|[<span data-ttu-id="97488-122">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="97488-122">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="97488-123">3 </span><span class="sxs-lookup"><span data-stu-id="97488-123">3</span></span>|<span data-ttu-id="97488-124">高信賴度的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="97488-124">High confidence spam</span></span>|<span data-ttu-id="97488-125">CAT： HSPM</span><span class="sxs-lookup"><span data-stu-id="97488-125">CAT:HSPM</span></span>|[<span data-ttu-id="97488-126">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="97488-126">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="97488-127">4 </span><span class="sxs-lookup"><span data-stu-id="97488-127">4</span></span>|<span data-ttu-id="97488-128">詐騙</span><span class="sxs-lookup"><span data-stu-id="97488-128">Spoofing</span></span>|<span data-ttu-id="97488-129">CAT：欺騙</span><span class="sxs-lookup"><span data-stu-id="97488-129">CAT:SPOOF</span></span>|[<span data-ttu-id="97488-130">在 Office 365 中設定假冒情報</span><span class="sxs-lookup"><span data-stu-id="97488-130">Configure spoof intelligence in Office 365</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="97488-131">5 </span><span class="sxs-lookup"><span data-stu-id="97488-131">5</span></span>|<span data-ttu-id="97488-132">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="97488-132">Spam</span></span>|<span data-ttu-id="97488-133">CAT： SPM</span><span class="sxs-lookup"><span data-stu-id="97488-133">CAT:SPM</span></span>|[<span data-ttu-id="97488-134">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="97488-134">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="97488-135">6 </span><span class="sxs-lookup"><span data-stu-id="97488-135">6</span></span>|<span data-ttu-id="97488-136">大量</span><span class="sxs-lookup"><span data-stu-id="97488-136">Bulk</span></span>|<span data-ttu-id="97488-137">CAT：大量</span><span class="sxs-lookup"><span data-stu-id="97488-137">CAT:BULK</span></span>|[<span data-ttu-id="97488-138">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="97488-138">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="97488-139">7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97488-139">7<sup>\*</sup></span></span>|<span data-ttu-id="97488-140">網域模仿（受保護的使用者）</span><span class="sxs-lookup"><span data-stu-id="97488-140">Domain impersonation (protected users)</span></span>|<span data-ttu-id="97488-141">DIMP</span><span class="sxs-lookup"><span data-stu-id="97488-141">DIMP</span></span>|[<span data-ttu-id="97488-142">在 Office 365 中設定 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="97488-142">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="97488-143">8：00<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97488-143">8<sup>\*</sup></span></span>|<span data-ttu-id="97488-144">使用者類比（受保護的網域）</span><span class="sxs-lookup"><span data-stu-id="97488-144">User impersonation (protected domains)</span></span>|<span data-ttu-id="97488-145">UIMP</span><span class="sxs-lookup"><span data-stu-id="97488-145">UIMP</span></span>|[<span data-ttu-id="97488-146">在 Office 365 中設定 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="97488-146">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="97488-147"><sup>\*</sup>這些功能只有在 ATP 反網路釣魚原則中才能使用。</span><span class="sxs-lookup"><span data-stu-id="97488-147"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="97488-148">**原則的優先順序**：針對每一種保護類型（反垃圾郵件、反惡意程式碼、反網路釣魚等等），都有一個適用于每個人的預設原則，但您通常可以建立適用于特定使用者的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="97488-148">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can often create custom policies that apply to specific users.</span></span> <span data-ttu-id="97488-149">每個自訂原則都有一個優先順序值，以決定原則的套用順序。</span><span class="sxs-lookup"><span data-stu-id="97488-149">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="97488-150">預設原則永遠套用於最後。</span><span class="sxs-lookup"><span data-stu-id="97488-150">The default policy is always applied last.</span></span>

  <span data-ttu-id="97488-151">如果使用者是在相同類型的多個原則中定義，則只有具有最高優先順序的原則適用于。</span><span class="sxs-lookup"><span data-stu-id="97488-151">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="97488-152">不會為使用者評估任何其他類型的原則（包括預設原則）。</span><span class="sxs-lookup"><span data-stu-id="97488-152">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="97488-153">例如，請考慮下列**適用于相同使用者**的 ATP 反網路釣魚原則，以及識別為使用者模擬和欺騙的郵件：</span><span class="sxs-lookup"><span data-stu-id="97488-153">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="97488-154">**ATP 反網路釣魚原則**</span><span class="sxs-lookup"><span data-stu-id="97488-154">**ATP anti-phishing policy**</span></span>|<span data-ttu-id="97488-155">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="97488-155">**Priority**</span></span>|<span data-ttu-id="97488-156">**使用者模擬**</span><span class="sxs-lookup"><span data-stu-id="97488-156">**User impersonation**</span></span>|<span data-ttu-id="97488-157">**反詐騙**</span><span class="sxs-lookup"><span data-stu-id="97488-157">**Anti-spoofing**</span></span>|
  |<span data-ttu-id="97488-158">原則 A</span><span class="sxs-lookup"><span data-stu-id="97488-158">Policy A</span></span>|<span data-ttu-id="97488-159">1 </span><span class="sxs-lookup"><span data-stu-id="97488-159">1</span></span>|<span data-ttu-id="97488-160">開啟</span><span class="sxs-lookup"><span data-stu-id="97488-160">On</span></span>|<span data-ttu-id="97488-161">關閉</span><span class="sxs-lookup"><span data-stu-id="97488-161">Off</span></span>|
  |<span data-ttu-id="97488-162">原則 B</span><span class="sxs-lookup"><span data-stu-id="97488-162">Policy B</span></span>|<span data-ttu-id="97488-163">2 </span><span class="sxs-lookup"><span data-stu-id="97488-163">2</span></span>|<span data-ttu-id="97488-164">關閉</span><span class="sxs-lookup"><span data-stu-id="97488-164">Off</span></span>|<span data-ttu-id="97488-165">開啟</span><span class="sxs-lookup"><span data-stu-id="97488-165">On</span></span>|
  |

1. <span data-ttu-id="97488-166">郵件會標示並視為欺騙性，因為哄騙具有比使用者模擬（8）更高的優先順序（4）。</span><span class="sxs-lookup"><span data-stu-id="97488-166">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="97488-167">原則 A 會套用至使用者，因為其優先順序高於原則 B。</span><span class="sxs-lookup"><span data-stu-id="97488-167">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="97488-168">根據原則 A 中的設定，不會對郵件採取任何動作，因為會在原則中關閉反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="97488-168">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="97488-169">原則處理會停止，因此原則 B 永遠不會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="97488-169">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="97488-170">因為相同的使用者可能會故意或無意中包含相同類型的多個自訂原則，所以請針對自訂原則使用下列設計原則：</span><span class="sxs-lookup"><span data-stu-id="97488-170">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="97488-171">指派較高優先順序的原則套用至少量的使用者，以及套用至大量使用者之原則的優先順序較低。</span><span class="sxs-lookup"><span data-stu-id="97488-171">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="97488-172">請記住，預設原則永遠會最後套用。</span><span class="sxs-lookup"><span data-stu-id="97488-172">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="97488-173">設定較高優先順序的原則，使其具有比低優先順序原則更嚴格或更多的特殊設定。</span><span class="sxs-lookup"><span data-stu-id="97488-173">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="97488-174">請考慮使用較少的自訂原則（只對需要更嚴格或更多特殊設定的使用者使用自訂原則）。</span><span class="sxs-lookup"><span data-stu-id="97488-174">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
