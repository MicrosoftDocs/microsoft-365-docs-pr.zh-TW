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
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895332"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a><span data-ttu-id="690c1-104">Office 365 中的電子郵件保護順序和優先順序</span><span class="sxs-lookup"><span data-stu-id="690c1-104">Order and precedence of email protection in Office 365</span></span>

<span data-ttu-id="690c1-105">若為 Office 365 使用者，您的輸入電子郵件可能會以多種保護形式來標記。</span><span class="sxs-lookup"><span data-stu-id="690c1-105">As Office 365 user, your inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="690c1-106">例如，適用于所有 Office 365 客戶的內建 EOP 防網路釣魚原則，以及 Office 365 高級威脅防護客戶也可以使用的更強健的 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="690c1-106">For example, the built-in EOP anti-phishing policies that are available to all Office 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection customers.</span></span> <span data-ttu-id="690c1-107">郵件也會透過多個偵測掃描進行惡意程式碼、垃圾郵件、網路釣魚等的掃描。在此活動中，可能會對套用的原則產生一些混淆。</span><span class="sxs-lookup"><span data-stu-id="690c1-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="690c1-108">一般說來，套用至郵件的原則會在**CAT （類別）** 屬性的**X-Forefront-Antispam-Report**標頭中識別。</span><span class="sxs-lookup"><span data-stu-id="690c1-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="690c1-109">如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。</span><span class="sxs-lookup"><span data-stu-id="690c1-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="690c1-110">有兩個主要因素會決定要套用至郵件的原則：</span><span class="sxs-lookup"><span data-stu-id="690c1-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="690c1-111">**電子郵件保護類型的優先順序**：此順序並不是可設定的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="690c1-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="690c1-112">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="690c1-112">**Priority**</span></span>|<span data-ttu-id="690c1-113">**電子郵件保護**</span><span class="sxs-lookup"><span data-stu-id="690c1-113">**Email protection**</span></span>|<span data-ttu-id="690c1-114">**類別**</span><span class="sxs-lookup"><span data-stu-id="690c1-114">**Category**</span></span>|<span data-ttu-id="690c1-115">**要管理的位置**</span><span class="sxs-lookup"><span data-stu-id="690c1-115">**Where to manage**</span></span>|
  |<span data-ttu-id="690c1-116">1 </span><span class="sxs-lookup"><span data-stu-id="690c1-116">1</span></span>|<span data-ttu-id="690c1-117">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="690c1-117">Malware</span></span>|<span data-ttu-id="690c1-118">CAT： MALW</span><span class="sxs-lookup"><span data-stu-id="690c1-118">CAT:MALW</span></span>|[<span data-ttu-id="690c1-119">在 Office 365 中設定反惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="690c1-119">Configure anti-malware policies in Office 365</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="690c1-120">2 </span><span class="sxs-lookup"><span data-stu-id="690c1-120">2</span></span>|<span data-ttu-id="690c1-121">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="690c1-121">Phishing</span></span>|<span data-ttu-id="690c1-122">CAT： PHSH</span><span class="sxs-lookup"><span data-stu-id="690c1-122">CAT:PHSH</span></span>|[<span data-ttu-id="690c1-123">在 Office 365 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="690c1-123">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="690c1-124">3 </span><span class="sxs-lookup"><span data-stu-id="690c1-124">3</span></span>|<span data-ttu-id="690c1-125">高信賴度的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="690c1-125">High confidence spam</span></span>|<span data-ttu-id="690c1-126">CAT： HSPM</span><span class="sxs-lookup"><span data-stu-id="690c1-126">CAT:HSPM</span></span>|[<span data-ttu-id="690c1-127">在 Office 365 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="690c1-127">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="690c1-128">4 </span><span class="sxs-lookup"><span data-stu-id="690c1-128">4</span></span>|<span data-ttu-id="690c1-129">詐騙</span><span class="sxs-lookup"><span data-stu-id="690c1-129">Spoofing</span></span>|<span data-ttu-id="690c1-130">CAT：欺騙</span><span class="sxs-lookup"><span data-stu-id="690c1-130">CAT:SPOOF</span></span>|[<span data-ttu-id="690c1-131">設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="690c1-131">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>](set-up-anti-phishing-policies.md) <Br/><br/> [<span data-ttu-id="690c1-132">深入了解詐騙情報</span><span class="sxs-lookup"><span data-stu-id="690c1-132">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="690c1-133">5 </span><span class="sxs-lookup"><span data-stu-id="690c1-133">5</span></span>|<span data-ttu-id="690c1-134">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="690c1-134">Spam</span></span>|<span data-ttu-id="690c1-135">CAT： SPM</span><span class="sxs-lookup"><span data-stu-id="690c1-135">CAT:SPM</span></span>|[<span data-ttu-id="690c1-136">在 Office 365 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="690c1-136">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="690c1-137">6 </span><span class="sxs-lookup"><span data-stu-id="690c1-137">6</span></span>|<span data-ttu-id="690c1-138">大量</span><span class="sxs-lookup"><span data-stu-id="690c1-138">Bulk</span></span>|<span data-ttu-id="690c1-139">CAT：大量</span><span class="sxs-lookup"><span data-stu-id="690c1-139">CAT:BULK</span></span>|[<span data-ttu-id="690c1-140">在 Office 365 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="690c1-140">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="690c1-141">7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="690c1-141">7<sup>\*</sup></span></span>|<span data-ttu-id="690c1-142">網域冒充</span><span class="sxs-lookup"><span data-stu-id="690c1-142">Domain Impersonation</span></span>|<span data-ttu-id="690c1-143">DIMP</span><span class="sxs-lookup"><span data-stu-id="690c1-143">DIMP</span></span>|[<span data-ttu-id="690c1-144">設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="690c1-144">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>](set-up-anti-phishing-policies.md)|
  |<span data-ttu-id="690c1-145">8：00<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="690c1-145">8<sup>\*</sup></span></span>|<span data-ttu-id="690c1-146">使用者冒充</span><span class="sxs-lookup"><span data-stu-id="690c1-146">User Impersonation</span></span>|<span data-ttu-id="690c1-147">UIMP</span><span class="sxs-lookup"><span data-stu-id="690c1-147">UIMP</span></span>|[<span data-ttu-id="690c1-148">設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="690c1-148">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>](set-up-anti-phishing-policies.md)|
  |

  <span data-ttu-id="690c1-149"><sup>\*</sup>這些功能只有在 ATP 中提供。</span><span class="sxs-lookup"><span data-stu-id="690c1-149"><sup>\*</sup> These features are only available in ATP.</span></span>

- <span data-ttu-id="690c1-150">**原則的優先順序**：針對每一種保護類型（反垃圾郵件、反惡意程式碼、反網路釣魚等等），都有一個適用于每個人的預設原則，但您可以建立適用于特定使用者的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="690c1-150">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="690c1-151">每個自訂原則都有一個優先順序值，以決定原則的套用順序。</span><span class="sxs-lookup"><span data-stu-id="690c1-151">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="690c1-152">預設原則永遠套用於最後。</span><span class="sxs-lookup"><span data-stu-id="690c1-152">The default policy is always applied last.</span></span>

  <span data-ttu-id="690c1-153">如果使用者是在多重自訂原則中定義，只會套用具有最高優先順序的原則。</span><span class="sxs-lookup"><span data-stu-id="690c1-153">If a user is defined in multiple custom policies, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="690c1-154">不會評估使用者的任何剩餘原則（包括預設原則）。</span><span class="sxs-lookup"><span data-stu-id="690c1-154">Any remaining policies are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="690c1-155">例如，請考慮下列**適用于相同使用者**的反網路釣魚原則，以及識別為使用者模擬和欺騙的郵件：</span><span class="sxs-lookup"><span data-stu-id="690c1-155">For example, consider the following anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="690c1-156">**反垃圾郵件原則**</span><span class="sxs-lookup"><span data-stu-id="690c1-156">**Anti-spam policy**</span></span>|<span data-ttu-id="690c1-157">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="690c1-157">**Priority**</span></span>|<span data-ttu-id="690c1-158">**使用者模仿（ATP）**</span><span class="sxs-lookup"><span data-stu-id="690c1-158">**User Impersonation (ATP)**</span></span>|<span data-ttu-id="690c1-159">**反欺騙（EOP）**</span><span class="sxs-lookup"><span data-stu-id="690c1-159">**Anti-spoofing (EOP)**</span></span>|
  |<span data-ttu-id="690c1-160">原則 A</span><span class="sxs-lookup"><span data-stu-id="690c1-160">Policy A</span></span>|<span data-ttu-id="690c1-161">1 </span><span class="sxs-lookup"><span data-stu-id="690c1-161">1</span></span>|<span data-ttu-id="690c1-162">開啟</span><span class="sxs-lookup"><span data-stu-id="690c1-162">On</span></span>|<span data-ttu-id="690c1-163">關閉</span><span class="sxs-lookup"><span data-stu-id="690c1-163">Off</span></span>|
  |<span data-ttu-id="690c1-164">原則 B</span><span class="sxs-lookup"><span data-stu-id="690c1-164">Policy B</span></span>|<span data-ttu-id="690c1-165">2 </span><span class="sxs-lookup"><span data-stu-id="690c1-165">2</span></span>|<span data-ttu-id="690c1-166">關閉</span><span class="sxs-lookup"><span data-stu-id="690c1-166">Off</span></span>|<span data-ttu-id="690c1-167">開啟</span><span class="sxs-lookup"><span data-stu-id="690c1-167">On</span></span>|
  |

1. <span data-ttu-id="690c1-168">郵件會標示並視為欺騙性，因為哄騙具有比使用者模擬（8）更高的優先順序（4）。</span><span class="sxs-lookup"><span data-stu-id="690c1-168">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="690c1-169">原則 A 會套用至使用者，因為其優先順序高於優先順序 B。</span><span class="sxs-lookup"><span data-stu-id="690c1-169">Policy A is applied to the users because it has a higher priority than Priority B.</span></span>
3. <span data-ttu-id="690c1-170">根據原則 A 中的設定，不會對郵件採取任何動作，因為會在原則中關閉反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="690c1-170">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="690c1-171">反垃圾郵件原則處理會停止，因此原則 B 永遠不會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="690c1-171">Anti-spam policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="690c1-172">因為有許多使用者在相同類型的自訂原則中有可能有許多使用者，所以請考慮下列自訂原則的設計準則：</span><span class="sxs-lookup"><span data-stu-id="690c1-172">Because there's a potential to have many users in many custom policies of the same type, consider the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="690c1-173">指派較高優先順序的原則套用至少量的使用者，以及套用至大量使用者之原則的優先順序較低。</span><span class="sxs-lookup"><span data-stu-id="690c1-173">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="690c1-174">請記住，預設原則永遠會最後套用。</span><span class="sxs-lookup"><span data-stu-id="690c1-174">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="690c1-175">設定較高優先順序的原則，使其具有比低優先順序原則更嚴格或更多的特殊設定。</span><span class="sxs-lookup"><span data-stu-id="690c1-175">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="690c1-176">請考慮使用較少的自訂原則（只對需要更嚴格或更多 specialize 設定的使用者使用自訂原則）。</span><span class="sxs-lookup"><span data-stu-id="690c1-176">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialize settings).</span></span>
