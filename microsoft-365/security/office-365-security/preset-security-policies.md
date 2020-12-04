---
title: 預設安全性原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 的保護功能上套用標準和嚴格的原則設定
ms.openlocfilehash: e968f7ea768ac8a0b402c28f3830a52b44afa342
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572774"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="5763a-103">EOP 和 Microsoft Defender for Office 365 中的預先設定安全性原則</span><span class="sxs-lookup"><span data-stu-id="5763a-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5763a-104">「預設」安全性原則提供集中式的位置，可讓使用者同時套用所有建議的垃圾郵件、惡意程式碼和網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="5763a-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="5763a-105">無法設定原則設定。</span><span class="sxs-lookup"><span data-stu-id="5763a-105">The policy settings are not configurable.</span></span> <span data-ttu-id="5763a-106">相反地，這些是由 us 設定，並以資料中心的觀察和經驗為基礎，以在保持有害內容不中斷其運作的情況下進行平衡。</span><span class="sxs-lookup"><span data-stu-id="5763a-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="5763a-107">本主題的其餘部分將說明預設的安全性原則，以及如何加以設定。</span><span class="sxs-lookup"><span data-stu-id="5763a-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="5763a-108">做為什麼預設安全性原則</span><span class="sxs-lookup"><span data-stu-id="5763a-108">What preset security policies are made of</span></span>

<span data-ttu-id="5763a-109">預先設定的安全性原則包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="5763a-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="5763a-110">設定檔</span><span class="sxs-lookup"><span data-stu-id="5763a-110">Profiles</span></span>
- <span data-ttu-id="5763a-111">原則</span><span class="sxs-lookup"><span data-stu-id="5763a-111">Policies</span></span>
- <span data-ttu-id="5763a-112">原則設定</span><span class="sxs-lookup"><span data-stu-id="5763a-112">Policy settings</span></span>

<span data-ttu-id="5763a-113">此外，如果有多個預先設定的安全性原則和其他原則套用至同一個人員，優先順序順序就很重要。</span><span class="sxs-lookup"><span data-stu-id="5763a-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="5763a-114">預先設定安全性原則中的設定檔</span><span class="sxs-lookup"><span data-stu-id="5763a-114">Profiles in preset security policies</span></span>

<span data-ttu-id="5763a-115">設定檔決定保護的層級。</span><span class="sxs-lookup"><span data-stu-id="5763a-115">A profile determines the level of protection.</span></span> <span data-ttu-id="5763a-116">可供使用的設定檔如下：</span><span class="sxs-lookup"><span data-stu-id="5763a-116">The following profiles are available:</span></span>

- <span data-ttu-id="5763a-117">**標準保護**：適用于大多數使用者的基準保護設定檔。</span><span class="sxs-lookup"><span data-stu-id="5763a-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="5763a-118">**嚴格保護**：針對所選使用者的更為嚴格的保護設定檔 (高值目標或優先順序使用者) 。</span><span class="sxs-lookup"><span data-stu-id="5763a-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="5763a-119">您可以使用符合條件和例外狀況的規則，判斷哪些是設定檔或未套用至哪一個。</span><span class="sxs-lookup"><span data-stu-id="5763a-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="5763a-120">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="5763a-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="5763a-121">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="5763a-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="5763a-122">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="5763a-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="5763a-123">可用的條件和例外狀況如下：</span><span class="sxs-lookup"><span data-stu-id="5763a-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="5763a-124">收件者 **是**：信箱、郵件使用者或您組織中的郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="5763a-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="5763a-125">收件者屬於：您組織中 **的群組的成員**。</span><span class="sxs-lookup"><span data-stu-id="5763a-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="5763a-126">**收件者網域為**：已在 Microsoft 365 中設定的公認網域。</span><span class="sxs-lookup"><span data-stu-id="5763a-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="5763a-127">預先設定安全性原則中的原則</span><span class="sxs-lookup"><span data-stu-id="5763a-127">Policies in preset security policies</span></span>

<span data-ttu-id="5763a-128">預設的安全性原則使用 EOP 和 Microsoft Defender for Office 365 中的各種保護功能對應的原則。</span><span class="sxs-lookup"><span data-stu-id="5763a-128">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="5763a-129">在您指派 **標準保護** 或 **嚴格保護** 的預設安全性原則給使用者 _之後_，就會建立這些原則。</span><span class="sxs-lookup"><span data-stu-id="5763a-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="5763a-130">您無法修改這些原則。</span><span class="sxs-lookup"><span data-stu-id="5763a-130">You can't modify these policies.</span></span>

- <span data-ttu-id="5763a-131">**Exchange Online Protection (EOP) 原則**：這包括使用 exchange online 信箱的 Microsoft 365 組織和獨立 EOP 組織，但沒有 exchange online 信箱：</span><span class="sxs-lookup"><span data-stu-id="5763a-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="5763a-132">名為 **Standard Standard Security policy** And **Strict Standard Security policy** 的 [反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5763a-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="5763a-133">名為 **Standard Standard Security policy** And **Strict Standard Security policy** 的 [反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5763a-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="5763a-134">EOP 欺騙設定) 的「**標準預先設定安全性原則**」和「**嚴格預設安全性 (原則**」[的反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="5763a-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="5763a-135">**Microsoft Defender For office 365 原則**：這包括具有 Microsoft 365 E5 或 Defender for office 365 附加元件訂閱的組織：</span><span class="sxs-lookup"><span data-stu-id="5763a-135">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="5763a-136">Microsoft Defender for Office 365 中名為 **Standard Standard Security policy** 和 **Strict Standard security policy** 的反網路釣魚原則，其中包括：</span><span class="sxs-lookup"><span data-stu-id="5763a-136">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="5763a-137">EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="5763a-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="5763a-138">類比設定</span><span class="sxs-lookup"><span data-stu-id="5763a-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="5763a-139">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="5763a-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="5763a-140">名為 **Standard Standard Security policy** and Strict Standard **Security Policy** 的 [安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5763a-140">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="5763a-141">名為 **Standard Standard Security policy** and Strict Standard **Security Policy** 的 [安全附件原則](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5763a-141">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="5763a-142">請注意，您可以將 EOP 防護套用至不同于 Microsoft Defender for Office 365 保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="5763a-142">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="5763a-143">預設安全性原則中的原則設定</span><span class="sxs-lookup"><span data-stu-id="5763a-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="5763a-144">您無法修改保護設定檔中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="5763a-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="5763a-145">[EOP 和 Microsoft Defender For Office 365 security 的建議設定](recommended-settings-for-eop-and-office365-atp.md)會說明 **標準** 和 **嚴格** 的原則設定值。</span><span class="sxs-lookup"><span data-stu-id="5763a-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="5763a-146">預先設定的安全性原則及其他原則的優先權順序</span><span class="sxs-lookup"><span data-stu-id="5763a-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="5763a-147">將多個原則套用至使用者時，下列順序會從最高優先順序套用至最低優先順序：</span><span class="sxs-lookup"><span data-stu-id="5763a-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="5763a-148">**嚴格保護** 預設安全性原則</span><span class="sxs-lookup"><span data-stu-id="5763a-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="5763a-149">**標準保護** 預設安全性原則</span><span class="sxs-lookup"><span data-stu-id="5763a-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="5763a-150">自訂安全性原則</span><span class="sxs-lookup"><span data-stu-id="5763a-150">Custom security policies</span></span>
4. <span data-ttu-id="5763a-151">預設的安全性原則</span><span class="sxs-lookup"><span data-stu-id="5763a-151">Default security policies</span></span>

<span data-ttu-id="5763a-152">換句話說， **嚴格保護** 原則的設定會覆寫 **標準保護** 原則的設定，它會覆寫自訂原則中的設定，以覆寫預設原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="5763a-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="5763a-153">將預先設定的安全性原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="5763a-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5763a-154">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="5763a-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5763a-155">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="5763a-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5763a-156">若要直接移至 [ **預先設定的安全性原則** ] 頁面，請使用 <https://protection.office.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="5763a-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="5763a-157">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5763a-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5763a-158">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="5763a-158">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="5763a-159">若要設定預先設定的安全性原則，您必須是 [security & 合規性中心](permissions-in-the-security-and-compliance-center.md)內的 **組織管理** 或 **安全性系統管理員** 角色成員。</span><span class="sxs-lookup"><span data-stu-id="5763a-159">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="5763a-160">若要針對預設安全性原則進行唯讀存取，您必須是 [security & 合規性中心](permissions-in-the-security-and-compliance-center.md)內 **全域讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5763a-160">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="5763a-161">使用安全性 & 規範中心，將預先設定的安全性原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="5763a-161">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="5763a-162">在 [安全性 & 規範中心] 中，移至 [**威脅管理** 原則] 「預設 \> **Policy** \> **安全性原則**」。</span><span class="sxs-lookup"><span data-stu-id="5763a-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="5763a-163">在 [ **標準防護** ] 或 [ **嚴格防護**] 底下，按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5763a-163">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="5763a-164">[套用 **標準保護** ] 或 [套用 **嚴格防護** ] 嚮導即會啟動。</span><span class="sxs-lookup"><span data-stu-id="5763a-164">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="5763a-165">在 [ **EOP 保護] 適用** 于步驟，識別 [EOP 防護](#policies-in-preset-security-policies) 適用的內部收件者：</span><span class="sxs-lookup"><span data-stu-id="5763a-165">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="5763a-166">按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="5763a-166">Click **Add a condition**.</span></span> <span data-ttu-id="5763a-167">在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="5763a-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="5763a-168">**收件者是**</span><span class="sxs-lookup"><span data-stu-id="5763a-168">**The recipients are**</span></span>
      - <span data-ttu-id="5763a-169">**收件者的成員屬於**</span><span class="sxs-lookup"><span data-stu-id="5763a-169">**The recipients are members of**</span></span>
      - <span data-ttu-id="5763a-170">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="5763a-170">**The recipient domains are**</span></span>

      <span data-ttu-id="5763a-171">您只能使用一次條件，但是您可以指定條件的多個值。</span><span class="sxs-lookup"><span data-stu-id="5763a-171">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="5763a-172">相同條件使用或邏輯 (的多個值，例如 _\<recipient1\>_ 或 _\<recipient2\>_) 。</span><span class="sxs-lookup"><span data-stu-id="5763a-172">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="5763a-173">您選取的條件會出現在陰影區段中。</span><span class="sxs-lookup"><span data-stu-id="5763a-173">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="5763a-174">在該區段中，按一下 [ **任何** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="5763a-174">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="5763a-175">如果您稍候片刻，便會出現一個清單，讓您可以選取值。</span><span class="sxs-lookup"><span data-stu-id="5763a-175">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="5763a-176">或者，您可以開始輸入值以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="5763a-176">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="5763a-177">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="5763a-177">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="5763a-178">若要移除個別值，請 **Remove** 按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="5763a-178">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="5763a-179">若要移除整個條件，請 **Remove** 按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="5763a-179">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="5763a-180">若要新增其他條件，請按一下 [ **新增條件** ]，然後從其餘的條件中選取。</span><span class="sxs-lookup"><span data-stu-id="5763a-180">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="5763a-181">使用不同的條件和邏輯 (例如， _\<recipient1\>_ 及 _\<member of group 1\>_) 。</span><span class="sxs-lookup"><span data-stu-id="5763a-181">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="5763a-182">重複上述步驟，將值加入條件，並視需要重複此步驟，或在條件不足時重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="5763a-182">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="5763a-183">若要新增例外狀況，請按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="5763a-183">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="5763a-184">在出現的下拉式清單中，選取 [ **除外**] 下的條件。</span><span class="sxs-lookup"><span data-stu-id="5763a-184">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="5763a-185">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="5763a-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="5763a-186">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5763a-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5763a-187">[！注意事項] 如果您的組織有 Microsoft Defender for Office 365，您將會進入 **ATP 防護** ，以識別 [Microsoft defender for office 365 防護](#policies-in-preset-security-policies) 適用的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="5763a-187">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="5763a-188">設定和行為完全像是 **EOP 保護套用至** 步驟。</span><span class="sxs-lookup"><span data-stu-id="5763a-188">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="5763a-189">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5763a-189">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5763a-190">在 [ **確認** ] 步驟中，確認您的選擇，然後按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="5763a-190">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="5763a-191">使用安全性 & 合規性中心，修改預設安全性原則的指派</span><span class="sxs-lookup"><span data-stu-id="5763a-191">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="5763a-192">修改 **標準保護** 或 **嚴格保護** 安全性原則指派的步驟，與初次 [指派預先設定的安全性原則給使用者](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)相同。</span><span class="sxs-lookup"><span data-stu-id="5763a-192">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="5763a-193">若要停用 **標準保護** 或 **嚴格保護** 安全性原則，同時仍保留現有的條件和例外狀況，請將此切換滑動至 [ **停用**]。</span><span class="sxs-lookup"><span data-stu-id="5763a-193">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="5763a-194">若要啟用原則，請將開關滑動至 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="5763a-194">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5763a-195">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="5763a-195">How do you know these procedures worked?</span></span>

<span data-ttu-id="5763a-196">若要確認您是否已成功將 **標準保護** 或 **嚴格保護** 安全性原則指派給使用者，請使用預設值與 **標準防護** 設定不同的保護設定，這與 **嚴格防護** 設定不同。</span><span class="sxs-lookup"><span data-stu-id="5763a-196">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="5763a-197">例如，針對偵測為垃圾郵件的電子郵件 (不會有高信心的垃圾郵件) 確認郵件會傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，並隔離為 **嚴格保護** 使用者。</span><span class="sxs-lookup"><span data-stu-id="5763a-197">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="5763a-198">或者，針對 [大量電子郵件](bulk-complaint-level-values.md)，確認 BCL 值6或更高版本可將郵件傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，而且 bcl 值4或更高隔離郵件以取得 **嚴格保護** 使用者。</span><span class="sxs-lookup"><span data-stu-id="5763a-198">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
