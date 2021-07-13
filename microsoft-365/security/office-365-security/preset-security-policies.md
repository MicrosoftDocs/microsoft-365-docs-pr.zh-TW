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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Exchange Online Protection (EOP) 和 Microsoft Defender Office 365 的保護功能上套用標準和嚴格的原則設定
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 61166c78f31a86882ef0e2dc2a79683aea794040
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383459"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="0a4ae-103">EOP 和 Microsoft Defender for Office 365 中的預設安全性原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0a4ae-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="0a4ae-104">**Applies to**</span></span>
- [<span data-ttu-id="0a4ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0a4ae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0a4ae-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="0a4ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0a4ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a4ae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0a4ae-108">「預設」安全性原則提供集中式的位置，可讓使用者同時套用所有建議的垃圾郵件、惡意程式碼和網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="0a4ae-109">無法設定原則設定。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-109">The policy settings are not configurable.</span></span> <span data-ttu-id="0a4ae-110">相反地，這些是由 us 設定，並以資料中心的觀察和經驗為基礎，以進行保持有害內容與使用者之間的平衡，避免不必要的中斷。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users and avoiding unnecessary disruptions.</span></span>

<span data-ttu-id="0a4ae-111">本文的其餘部分將說明預設的安全性原則，以及如何加以設定。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-111">The rest of this article describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="0a4ae-112">做為什麼預設安全性原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-112">What preset security policies are made of</span></span>

<span data-ttu-id="0a4ae-113">預先設定的安全性原則包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="0a4ae-114">設定檔</span><span class="sxs-lookup"><span data-stu-id="0a4ae-114">Profiles</span></span>
- <span data-ttu-id="0a4ae-115">原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-115">Policies</span></span>
- <span data-ttu-id="0a4ae-116">原則設定</span><span class="sxs-lookup"><span data-stu-id="0a4ae-116">Policy settings</span></span>

<span data-ttu-id="0a4ae-117">此外，如果有多個預先設定的安全性原則和其他原則套用至同一個人員，優先順序順序就很重要。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="0a4ae-118">預先設定安全性原則中的設定檔</span><span class="sxs-lookup"><span data-stu-id="0a4ae-118">Profiles in preset security policies</span></span>

<span data-ttu-id="0a4ae-119">設定檔決定保護的層級。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-119">A profile determines the level of protection.</span></span> <span data-ttu-id="0a4ae-120">可供使用的設定檔如下：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-120">The following profiles are available:</span></span>

- <span data-ttu-id="0a4ae-121">**標準保護**：適用于大多數使用者的基準保護設定檔。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="0a4ae-122">**嚴格保護**：針對所選使用者的更為嚴格的保護設定檔 (高值目標或優先順序使用者) 。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="0a4ae-123">您可以使用符合條件和例外狀況的規則，判斷哪些是設定檔或未套用至哪一個。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="0a4ae-124">可用的條件和例外狀況如下：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-124">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="0a4ae-125">**使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-125">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="0a4ae-126">**群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-126">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
- <span data-ttu-id="0a4ae-127">**網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-127">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

<span data-ttu-id="0a4ae-128">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-128">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0a4ae-129">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-129">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0a4ae-130">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-130">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="0a4ae-131">預先設定安全性原則中的原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-131">Policies in preset security policies</span></span>

<span data-ttu-id="0a4ae-132">預設的安全性原則使用 EOP 和 Microsoft Defender for Office 365 中各種保護功能的對應原則。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0a4ae-133">在您指派 **標準保護** 或 **嚴格保護** 的預設安全性原則給使用者 _之後_，就會建立這些原則。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="0a4ae-134">您無法修改這些原則。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-134">You can't modify these policies.</span></span>

- <span data-ttu-id="0a4ae-135">**Exchange Online Protection (EOP) 原則**：這包括具有 Exchange Online 信箱和獨立 EOP 組織的 Microsoft 365 組織，但沒有 Exchange Online 信箱：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="0a4ae-136">名為 **Standard Standard Security policy** And **Strict Standard Security policy** 的 [反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="0a4ae-137">名為 **Standard Standard Security policy** And **Strict Standard Security policy** 的 [反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="0a4ae-138">EOP 欺騙設定) 的「**標準預先設定安全性原則**」和「**嚴格預設安全性 (原則**」[的反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="0a4ae-139">**適用于 Office 365 原則的 Microsoft Defender**：這包括具有 Microsoft 365 E5 或 Defender 的組織 Office 365 附加元件訂閱：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="0a4ae-140">Microsoft Defender 中 Office 365 名為 **Standard Standard Standard security policy** and **Strict Standard security policy** 的反網路釣魚原則，其中包括：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="0a4ae-141">EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="0a4ae-142">類比設定</span><span class="sxs-lookup"><span data-stu-id="0a4ae-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="0a4ae-143">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="0a4ae-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="0a4ae-144">保管庫名為 **Standard Standard security policy** and **Strict standard security policy** 的 [連結原則](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="0a4ae-145">保管庫名為 **Standard Standard security policy** and **Strict standard security policy** 的 [附件原則](set-up-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="0a4ae-146">請注意，您可以將 EOP 保護套用至不同于 Microsoft Defender Office 365 保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="0a4ae-147">預設安全性原則中的原則設定</span><span class="sxs-lookup"><span data-stu-id="0a4ae-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="0a4ae-148">您無法修改保護設定檔中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="0a4ae-149">[EOP 和 Microsoft Defender for Office 365 security 的建議設定](recommended-settings-for-eop-and-office365.md)會說明 **標準** 和 **嚴格** 的原則設定值。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="0a4ae-150">預先設定的安全性原則及其他原則的優先權順序</span><span class="sxs-lookup"><span data-stu-id="0a4ae-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="0a4ae-151">將多個原則套用至使用者時，下列順序會從最高優先順序套用至最低優先順序：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="0a4ae-152">**嚴格保護** 預設安全性原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="0a4ae-153">**標準保護** 預設安全性原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="0a4ae-154">自訂安全性原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-154">Custom security policies</span></span>
4. <span data-ttu-id="0a4ae-155">預設的安全性原則</span><span class="sxs-lookup"><span data-stu-id="0a4ae-155">Default security policies</span></span>

<span data-ttu-id="0a4ae-156">換句話說， **嚴格保護** 原則的設定會覆寫 **標準保護** 原則的設定，它會覆寫自訂原則中的設定，以覆寫預設原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span> 

<span data-ttu-id="0a4ae-157">例如，如果安全性設定存在於 **標準保護** 中，且系統管理員已為使用者啟用 **標準保護** ，則會套用 **標準防護** 設定，而不是在自訂原則或 (相同使用者) 的預設原則中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-157">For example, if a security setting exists in **Standard protection** and an admin has enabled the **Standard protection** for a user, then the **Standard protection** setting will be applied instead of what is configured for that setting in a custom policy or in the default policy (for the same user).</span></span> <span data-ttu-id="0a4ae-158">請注意，當您將自訂原則套用至組織中的其他使用者，以符合特定需求時，您可能會在部分組織中只套用 **標準** 或 **嚴格保護** 原則。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-158">Note that you might have some portion of your organization to whom you want to apply only the **Standard** or **Strict protection** policy while applying a custom policy to other users in your organization to meet specific needs.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="0a4ae-159">將預先設定的安全性原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="0a4ae-159">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0a4ae-160">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="0a4ae-160">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0a4ae-161">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-161">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="0a4ae-162">若要直接移至 [ **預先設定的安全性原則** ] 頁面，請使用 <https://security.microsoft.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-162">To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="0a4ae-163">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-163">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0a4ae-164">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-164">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0a4ae-165">若要設定預先設定的安全性原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-165">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0a4ae-166">若要針對預設安全性原則進行唯讀存取，您必須是 **全域讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-166">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="0a4ae-167">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-167">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="0a4ae-168">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 中其他功能所需的許可權 _和_ 許可權。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-168">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0a4ae-169">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-169">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="0a4ae-170">使用 Microsoft 365 Defender 入口網站將預置的安全性原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="0a4ae-170">Use the Microsoft 365 Defender portal to assign preset security policies to users</span></span>

1. <span data-ttu-id="0a4ae-171">在 Microsoft 365 Defender 入口網站中，移至 **Email &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **範本化原則**] 區段中的 \> **安全性原則**。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-171">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Templated policies** section \> **Preset Security Policies**.</span></span>

2. <span data-ttu-id="0a4ae-172">在 [ **標準防護** ] 或 [ **嚴格防護**] 底下，按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-172">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="0a4ae-173">[套用 **標準保護** ] 或 [套用 **嚴格防護** ] 嚮導即會啟動。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-173">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="0a4ae-174">在 [ **EOP 保護套用至** ] 頁面上，找出 [EOP 防護](#policies-in-preset-security-policies) 適用于 (收件者條件的內部收件者) ：</span><span class="sxs-lookup"><span data-stu-id="0a4ae-174">On the **EOP protections apply to** page, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to (recipient conditions):</span></span>
   - <span data-ttu-id="0a4ae-175">**使用者**</span><span class="sxs-lookup"><span data-stu-id="0a4ae-175">**Users**</span></span>
   - <span data-ttu-id="0a4ae-176">**群組**</span><span class="sxs-lookup"><span data-stu-id="0a4ae-176">**Groups**</span></span>
   - <span data-ttu-id="0a4ae-177">**網域**</span><span class="sxs-lookup"><span data-stu-id="0a4ae-177">**Domains**</span></span>

   <span data-ttu-id="0a4ae-178">按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-178">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="0a4ae-179">視需要重複此程序多次。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-179">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="0a4ae-180">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="0a4ae-180">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="0a4ae-182">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-182">next to the value.</span></span>

   <span data-ttu-id="0a4ae-183">針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-183">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="0a4ae-184">針對使用者，接著輸入星號 (\*) 來查看所有可用的值。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-184">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   - <span data-ttu-id="0a4ae-185">**排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-185">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="0a4ae-186">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-186">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0a4ae-187">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0a4ae-188">在適用于 Office 365 組織的 Microsoft Defender 中，您會進入的「 **Office 365 防護的 defender** 」套用至頁面，識別 [Microsoft Defender for Office 365 防護](#policies-in-preset-security-policies)所套用的內部收件者，以)  (的收件者條件。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-188">In Microsoft Defender for Office 365 organizations, you're taken to the **Defender for Office 365 protections apply to** page to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to (recipient conditions).</span></span>

   <span data-ttu-id="0a4ae-189">設定和行為完全像是 **EOP 防護套用至** 頁面。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-189">The settings and behavior are exactly like the **EOP protections apply to** page.</span></span>

   <span data-ttu-id="0a4ae-190">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-190">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0a4ae-191">在 [ **檢查並確認您的變更** ] 頁面上，確認您的選擇，然後按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-191">On the **Review and confirm your changes** page, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="0a4ae-192">使用 Microsoft 365 Defender 入口網站修改預設安全性原則的指派</span><span class="sxs-lookup"><span data-stu-id="0a4ae-192">Use the Microsoft 365 Defender portal to modify the assignments of preset security policies</span></span>

<span data-ttu-id="0a4ae-193">修改 **標準保護** 或 **嚴格保護** 安全性原則指派的步驟，與初次 [指派預先設定的安全性原則給使用者](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)相同。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-193">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="0a4ae-194">若要在仍然保留現有條件和例外狀況的情況下停用 **標準保護** 或 **嚴格保護** 安全性原則，請將切換滑動到 **停用** 的 ![ 切換功能 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-194">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="0a4ae-195">若要啟用這些原則，請將切換滑動至 [ **啟用** ![ 時開啟] ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-195">To enable the policies, slide the toggle to **Enabled** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0a4ae-196">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="0a4ae-196">How do you know these procedures worked?</span></span>

<span data-ttu-id="0a4ae-197">若要確認您是否已成功將 **標準保護** 或 **嚴格保護** 安全性原則指派給使用者，請使用預設值與 **標準防護** 設定不同的保護設定，這與 **嚴格防護** 設定不同。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-197">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="0a4ae-198">例如，針對偵測為垃圾郵件的電子郵件 (不會有高信心的垃圾郵件) 確認郵件會傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，並隔離為 **嚴格保護** 使用者。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-198">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="0a4ae-199">或者，對於 [大宗郵件](bulk-complaint-level-values.md)，請確認 BCL 值6或更高版本將郵件傳遞至 **標準保護** 使用者的 [垃圾郵件] 資料夾，而且 bcl 值4或更高隔離郵件以取得 **嚴格保護** 使用者。</span><span class="sxs-lookup"><span data-stu-id="0a4ae-199">Or, for [bulk mail](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
