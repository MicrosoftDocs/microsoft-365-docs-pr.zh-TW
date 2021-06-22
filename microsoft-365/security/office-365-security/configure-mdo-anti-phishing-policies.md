---
title: 在 Microsoft Defender 中設定 Office 365 的反網路釣魚原則
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
description: 系統管理員可以瞭解如何建立、修改及刪除使用 Microsoft Defender Office 365 的組織中可用的高級防網路釣魚原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bbf90f52127e96e08f1c176a23d5f5ab1d6d86c4
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054540"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="eb6e1-103">在 Microsoft Defender 中設定 Office 365 的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eb6e1-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-104">**Applies to**</span></span>
- [<span data-ttu-id="eb6e1-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="eb6e1-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eb6e1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb6e1-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eb6e1-107">[Microsoft Defender for Office 365](defender-for-office-365.md)中的反網路釣魚原則可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他類型的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="eb6e1-108">如需 Microsoft Defender for Office 365 中 Exchange Online Protection (EOP) 和反網路釣魚原則中之防網路釣魚原則之間差異的詳細資訊，請參閱[反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="eb6e1-109">系統管理員可以查看、編輯和設定 (，但不會刪除預設的反網路釣魚原則) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="eb6e1-110">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="eb6e1-111">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="eb6e1-112">您可以在 Microsoft 365 Defender 入口網站或 Exchange Online PowerShell 中，設定 Office 365 的 Defender 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="eb6e1-113">如需設定 Exchange Online Protection 中可用之防網路釣魚原則的限制，也就是 (Office 365) 的組織，請參閱[在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="eb6e1-114">反網路釣魚原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="eb6e1-115">**反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="eb6e1-116">**反網路釣魚規則**：指定原則套用至) 以進行反網路釣魚原則的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="eb6e1-117">當您在 Microsoft 365 Defender 入口網站中管理反網路釣魚原則時，這兩個元素之間的差異不明顯。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="eb6e1-118">當您建立原則時，實際上是建立反網路釣魚規則和相關聯的反網路釣魚原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="eb6e1-119">當您修改原則時，與名稱、優先順序、啟用或停用及收件者篩選器相關的設定會修改反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="eb6e1-120">所有其他設定會修改關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="eb6e1-121">當您移除原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="eb6e1-122">在 Exchange Online PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="eb6e1-123">如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 設定反網路釣魚原則](#use-exchange-online-powershell-to-configure-anti-phishing-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="eb6e1-124">每個 Office 365 組織的 Defender 都有一個內建的反網路釣魚原則，名稱為 Office365 AntiPhish 具有下列屬性的預設值：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="eb6e1-125">原則會套用至組織中的所有收件者，即使沒有反網路釣魚的規則 (收件者篩選) 與原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="eb6e1-126">此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="eb6e1-127">任何您建立的自訂原則皆具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="eb6e1-128">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="eb6e1-129">若要提高 Office 365 之 Defender 中防網路釣魚保護的效能，您可以建立自訂的反網路釣魚原則，並將嚴格的設定套用至特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eb6e1-130">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="eb6e1-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eb6e1-131">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="eb6e1-132">若要直接移至 [ **反網路釣魚** ] 頁面，請使用 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="eb6e1-133">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="eb6e1-134">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="eb6e1-135">若要新增、修改和刪除反網路釣魚原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="eb6e1-136">若要唯讀的反網路釣魚原則存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="eb6e1-137">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="eb6e1-138">**附註**：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-138">**Notes**:</span></span>

  - <span data-ttu-id="eb6e1-139">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="eb6e1-140">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="eb6e1-141">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="eb6e1-142">如需 Office 365 之 defender 中的反網路釣魚原則建議設定，請參閱[在 Office 365 設定的 defender 中的反網路釣魚原則](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="eb6e1-143">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="eb6e1-144">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱 [電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="eb6e1-145">使用 Microsoft 365 Defender 入口網站建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="eb6e1-146">在 Microsoft 365 Defender 入口網站中建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="eb6e1-147">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="eb6e1-148">在 [ **反網路釣魚** 網頁] 頁面上，按一下 [ ![ 建立圖示 ](../../media/m365-cc-sc-create-icon.png) **建立**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="eb6e1-149">原則精靈隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-149">The policy wizard opens.</span></span> <span data-ttu-id="eb6e1-150">在 [ **原則名稱** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="eb6e1-151">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="eb6e1-152">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="eb6e1-153">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="eb6e1-154">在顯示的 [使用者、群組和網域 **]** 頁面上，識別原則適用的內部收件者 (收件者條件)：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="eb6e1-155">**使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="eb6e1-156">**群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="eb6e1-157">**網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="eb6e1-158">按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="eb6e1-159">視需要重複此程序多次。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="eb6e1-160">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="eb6e1-160">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="eb6e1-162">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-162">next to the value.</span></span>

   <span data-ttu-id="eb6e1-163">針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="eb6e1-164">針對使用者，接著輸入星號 (\*) 來查看所有可用的值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="eb6e1-165">相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="eb6e1-166">不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="eb6e1-167">**排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="eb6e1-168">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="eb6e1-169">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="eb6e1-170">在出現的 [ **網路釣魚閥值 & 保護** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="eb6e1-171">**網路釣魚電子郵件閥值**：使用滑塊選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="eb6e1-172">**1-Standard** (此為預設值。 ) </span><span class="sxs-lookup"><span data-stu-id="eb6e1-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="eb6e1-173">**2-嚴格**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="eb6e1-174">**3-更嚴格**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="eb6e1-175">**4-最積極**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="eb6e1-176">如需詳細資訊，請參閱[Microsoft Defender 中的反網路釣魚原則中的高級網路釣魚臨界值 Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="eb6e1-177">模擬 **：這些** 設定是原則的條件，可識別特定寄件者，以在輸入郵件的 [寄件者] 位址中個別或網域) 尋找 (。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="eb6e1-178">如需詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的模仿設定 Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="eb6e1-179">在每個反網路釣魚原則中，您可以指定最多60個受保護的使用者 (寄件者的電子郵件地址) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="eb6e1-180">您無法在多個原則中指定同一個受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="eb6e1-181">如果寄件者和收件者先前透過電子郵件進行通訊，使用者模擬保護便無法運作。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="eb6e1-182">如果寄件者和收件者永不透過電子郵件進行通訊，郵件會被識別為類比嘗試。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="eb6e1-183">**讓使用者能夠加以保護**：預設值為 off (未選取) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="eb6e1-184">若要將其開啟，請選取核取方塊，然後按一下 [ **管理 (nn) sender (s)** 連結。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="eb6e1-185">在 [管理已出現之 **類比保護的寄件者** ] 浮出視窗中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="eb6e1-186">**內部寄件者**：按一下 [ ![ 新增內部圖示] ](../../media/m365-cc-sc-add-internal-icon.png) **選取 [內部**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="eb6e1-187">在出現的 [ **新增內部寄件者** ] 浮出視窗中，按一下方塊，然後從清單中選取一個內部使用者。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="eb6e1-188">您可以輸入使用者，然後從結果中選取使用者，以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="eb6e1-189">您可以使用大部分的識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等 ) ，但是對應的顯示名稱會顯示在結果中。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="eb6e1-190">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb6e1-191">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="eb6e1-191">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="eb6e1-193">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-193">next to the value.</span></span>

         <span data-ttu-id="eb6e1-194">完成後，請按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="eb6e1-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="eb6e1-195">**外部寄件者**：按一下 [ ![ 新增外部圖示 ](../../media/m365-cc-sc-create-icon.png) **選取外部**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="eb6e1-196">在出現的 [ **新增外部寄件者** ] 浮出視窗中，在 [新增 **名稱** ] 方塊中輸入顯示名稱，並在 [ **新增 vaild 電子郵件** ] 方塊中輸入電子郵件地址，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="eb6e1-197">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb6e1-198">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="eb6e1-198">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="eb6e1-200">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-200">next to the value.</span></span>

         <span data-ttu-id="eb6e1-201">完成後，請按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="eb6e1-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="eb6e1-202">回到 [管理模仿] 浮出的 **寄件者** ，您可以從清單中選取一或多個專案來移除專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="eb6e1-203">您可以使用「 ![ 搜尋」圖示 ](../../media/m365-cc-sc-create-icon.png) **搜尋** 方塊來搜尋專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="eb6e1-204">選取至少一個專案之後， ![ 會出現 [移除選取的使用者] 圖示 ](../../media/m365-cc-sc-remove-selected-users-icon.png) [ **移除選取的使用者** ] 圖示，您可以使用此圖示移除選取的專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="eb6e1-205">完成後，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="eb6e1-206">**啟用網域以加以保護**：預設值為 off (未選取) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="eb6e1-207">若要將其開啟，請選取核取方塊，然後設定下列其中一個或兩個顯示的設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="eb6e1-208">**包含我擁有的網域**：若要開啟此設定，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="eb6e1-209">若要查看您擁有的網域，請按一下 [ **查看我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="eb6e1-210">**包含自訂網域**：若要開啟此設定，請選取核取方塊，然後按一下 [ **管理 (nn) 自訂網域 (s)** 連結。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="eb6e1-211">在顯示的 [ **管理模擬保護的自訂網域** ] 浮出視窗中，按一下 [ ![ 新增網域圖示] [ ](../../media/m365-cc-sc-create-icon.png) **新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="eb6e1-212">在出現的 [ **新增自訂網域** ] 浮出視窗中，按一下 [ **網域** ] 方塊，輸入值，然後按 enter 或選取方塊下方顯示的值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="eb6e1-213">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb6e1-214">若要移除現有的值，請按一下值旁邊的 ![移除圖示](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="eb6e1-215">完成作業後，按一下 [**新增網域**]</span><span class="sxs-lookup"><span data-stu-id="eb6e1-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="eb6e1-216">在所有的反網路釣魚原則中，您最多可以有50個網域。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="eb6e1-217">回到 [管理可模擬的 **自訂網域** ] 浮出的，您可以從清單中選取一或多個專案來移除專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="eb6e1-218">您可以使用「 ![ 搜尋」圖示 ](../../media/m365-cc-sc-create-icon.png) **搜尋** 方塊來搜尋專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="eb6e1-219">選取至少一個專案後， ![ 就會出現 [刪除網域圖示 ](../../media/m365-cc-sc-delete-icon.png) **刪除** ] 圖示，您可以使用此圖示移除選取的專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="eb6e1-220">**新增信任的寄件者和網域**：：若要指定原則的模擬保護例外狀況，請按一下 [ **管理 (nn) 信任的寄件者 (s) 及 [網域 (s)**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="eb6e1-221">在 [管理已出現之 **類比保護的自訂網域** ] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="eb6e1-222">**寄件者**：確認選取 [**寄件者**] 索引標籤，然後按一下 [ ![ 新增寄件者 ](../../media/m365-cc-sc-create-icon.png)</span><span class="sxs-lookup"><span data-stu-id="eb6e1-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="eb6e1-223">在出現的 [ **新增信任的寄件者** ] 飛入視窗中，輸入方塊中的電子郵件地址，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="eb6e1-224">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb6e1-225">若要移除現有的專案，請按一下 ![ 專案的 [刪除圖示] ](../../media/m365-cc-sc-close-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="eb6e1-226">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="eb6e1-227">**網域**：選取 [ **網域** ] 索引標籤，然後按一下 [ ![ 新增網域] 圖示 ](../../media/m365-cc-sc-create-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="eb6e1-228">在出現的 [ **新增信任的網域** ] 浮出視窗中，按一下 [ **網域** ] 方塊中輸入值，然後按 enter 或選取方塊下方所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="eb6e1-229">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb6e1-230">若要移除現有的值，請按一下值旁邊的 ![移除圖示](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="eb6e1-231">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="eb6e1-232">回到 [ **管理自訂網域進行類比** ] 浮出，您可以從清單中選取一或多個專案，以移除 **寄件者** 和 **網域** 索引標籤中的專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="eb6e1-233">您可以使用「 ![ 搜尋」圖示 ](../../media/m365-cc-sc-create-icon.png) **搜尋** 方塊來搜尋專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="eb6e1-234">選取至少一個專案後，即會出現 [ **刪除** ] 圖示，您可以使用此圖示移除選取的專案。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="eb6e1-235">完成後，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="eb6e1-236">**啟用信箱情報**：預設值為 (選取) 上，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="eb6e1-237">若要將它關閉，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="eb6e1-238">**啟用情報** 型模擬保護：只有在選取的)  (**啟用信箱情報** 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="eb6e1-239">此設定允許信箱智慧針對識別為類比嘗試的郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="eb6e1-240">您可以指定 [ **如果信箱智慧偵測** 到下一頁上的模仿使用者] 設定採取的動作。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="eb6e1-241">建議您選取此核取方塊來開啟此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="eb6e1-242">若要關閉此設定，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="eb6e1-243">**哄騙**：在此區段中，使用 [ **啟用哄騙情報** ] 核取方塊來開啟或關閉欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="eb6e1-244">預設值為 (選取) 上，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="eb6e1-245">在下一個頁面上，您可以指定在 [ **If 郵件被偵測為欺騙** ] 設定時，對郵件進行封鎖的欺騙寄件者採取的動作。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="eb6e1-246">若要關閉欺騙情報，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="eb6e1-247">如果您的 MX 記錄未指向 Microsoft 365，您就不需要關閉反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="eb6e1-248">如需相關指示，請參閱[強化篩選的 Exchange Online 中的連接器](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="eb6e1-249">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="eb6e1-250">在顯示的 [動作 **]** 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="eb6e1-251">**郵件動作**：設定此區段中的下列動作：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="eb6e1-252">**如果偵測到郵件為模仿的使用者**：只有在您選取 [ **允許使用者** 在前一頁上保護] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="eb6e1-253">在 [寄件者] 的下拉式清單中，選取下列其中一個動作，以取得您在前一頁上指定的其中一個受保護的使用者：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="eb6e1-254">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="eb6e1-255">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="eb6e1-256">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="eb6e1-257">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="eb6e1-258">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="eb6e1-259">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="eb6e1-260">**如果偵測到郵件為模擬的網域**：只有在先前頁面上選取 [ **啟用網域來保護** ] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="eb6e1-261">在下拉式清單中，針對寄件者的電子郵件地址位於先前頁面上所指定的其中一個受保護網域中，選取下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="eb6e1-262">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="eb6e1-263">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="eb6e1-264">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="eb6e1-265">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="eb6e1-266">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="eb6e1-267">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="eb6e1-268">**如果信箱智慧偵測到模仿的使用者**：只有在先前頁面上選取 [ **啟用類比功能的智慧功能** ] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="eb6e1-269">在下拉式清單中，針對信箱智慧所識別為模擬嘗試的郵件，選取下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="eb6e1-270">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="eb6e1-271">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="eb6e1-272">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="eb6e1-273">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="eb6e1-274">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="eb6e1-275">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="eb6e1-276">**如果偵測到郵件為欺騙** 性：只有在先前頁面上選取 [ **啟用哄騙情報** ] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="eb6e1-277">在已封鎖的欺騙寄件者的郵件下拉式清單中，選取下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="eb6e1-278">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="eb6e1-279">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="eb6e1-280">**安全性秘訣 & 指示器**：設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="eb6e1-281">**顯示第一個連絡人安全提示**：此安全提示會取代建立郵件流程規則的需求， (也稱為傳輸規則) ，該會將名為 **X-MS Exchange-EnableFirstContactSafetyTip** 的標頭新增為郵件的 **啟用** 值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-281">**Show first contact safety tip**: This safety tip replaces the need to create mail flow rules (also known as transport rules) that add the header named **X-MS-Exchange-EnableFirstContactSafetyTip** with the value **Enable** to messages.</span></span>
     - <span data-ttu-id="eb6e1-282">**顯示使用者模擬安全提示**：只有當您選取 [**允許使用者** 在前一頁上保護] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-282">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="eb6e1-283">**顯示網域模擬安全提示**：只有在先前頁面上選取 [**啟用要保護的網域**] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-283">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="eb6e1-284">**顯示使用者模擬不尋常的字元安全提示** 只有在您選取 [**讓使用者能夠保護** 或 **啟用網域以** 在前一頁上保護] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-284">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="eb6e1-285">**顯示 (？ ) 針對哄騙未驗證的寄件者**：只有在您選取 [啟用上一頁的 **欺騙智慧** ] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-285">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="eb6e1-286">如果郵件未通過 SPF 或 DKIM 檢查 **，且** 郵件未通過 DMARC 或 [複合驗證](email-validation-and-authentication.md#composite-authentication)，則 Outlook 會在 [寄件者] 方塊的 [寄件者] 方塊中新增問號給寄件者的相片。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-286">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="eb6e1-287">**顯示「透過**」標籤：只有在您選取了 [啟用上一頁的 **欺騙情報** 時，才可使用此設定]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-287">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="eb6e1-288">透過 chris@contoso.com 透過 fabrikam.com) 的 [寄件者] **或 [寄件者位址]** 中的網域，將透過 (標記新增至 [寄件者] 位址。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-288">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="eb6e1-289">預設值為 (選取) 上。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-289">The default value is on (selected).</span></span> <span data-ttu-id="eb6e1-290">若要將它關閉，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-290">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="eb6e1-291">如果您沒有顯示「**透過」標記** 設定，則會使用 [**顯示 (？ ) 針對您組織中未驗證的寄件者進行欺騙** 設定）來控制 [問號]**或**[via] 標記。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="eb6e1-292">若要開啟設定，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="eb6e1-293">若要將它關閉，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="eb6e1-294">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="eb6e1-295">在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="eb6e1-296">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="eb6e1-297">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="eb6e1-298">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="eb6e1-299">在顯示的確認頁面上，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="eb6e1-300">使用 Microsoft 365 Defender 入口網站來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="eb6e1-301">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="eb6e1-302">在 [ **反網路釣魚** ] 頁面上，下列屬性會顯示在反網路釣魚原則的清單中：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="eb6e1-303">**名稱**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-303">**Name**</span></span>
   - <span data-ttu-id="eb6e1-304">**狀態**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-304">**Status**</span></span>
   - <span data-ttu-id="eb6e1-305">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-305">**Priority**</span></span>
   - <span data-ttu-id="eb6e1-306">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-306">**Last modified**</span></span>

3. <span data-ttu-id="eb6e1-307">當您按一下名稱來選取原則時，原則設定會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="eb6e1-308">使用 Microsoft 365 Defender 入口網站修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="eb6e1-309">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="eb6e1-310">在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="eb6e1-311">在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="eb6e1-312">如需這些設定的詳細資訊，請參閱本文前面的[使用 Microsoft 365 Defender 入口網站建立反網路釣魚原則](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="eb6e1-313">針對預設的反網路釣魚原則，「 **使用者、群組及網域** 」區段無法使用 (原則套用至所有人) ，而且您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="eb6e1-314">若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="eb6e1-315">啟用或停用自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="eb6e1-316">您無法停用預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="eb6e1-317">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="eb6e1-318">在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取自訂原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="eb6e1-319">在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="eb6e1-320">**原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="eb6e1-321">**原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="eb6e1-322">在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="eb6e1-323">按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="eb6e1-324">回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="eb6e1-325">設定自訂的反網路釣魚原則優先順序</span><span class="sxs-lookup"><span data-stu-id="eb6e1-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="eb6e1-326">根據預設，反網路釣魚原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="eb6e1-327">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="eb6e1-328">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="eb6e1-329">若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在 Microsoft 365 Defender 入口網站直接修改 [優先順序 **]** 編號)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="eb6e1-330">只有在您有多個原則時，變更原則的優先順序才有意義。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="eb6e1-331">**附註**：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-331">**Notes**:</span></span>

- <span data-ttu-id="eb6e1-332">在 Microsoft 365 Defender 入口網站中，您只能在建立反網路釣魚原則之後，才能變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="eb6e1-333">在 PowerShell 中，您可以在建立反網路釣魚規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="eb6e1-334">反網路釣魚原則會依顯示的連續處理 (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="eb6e1-335">預設的反網路釣魚原則的優先順序值是 **最低** 的，您無法變更。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="eb6e1-336">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="eb6e1-337">在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取自訂原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="eb6e1-338">在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="eb6e1-339">**優先順序** 值為 **0** 的原則只有 [**降低優先順序**] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-339">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="eb6e1-340">具有最低 **優先順序** 值的原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-340">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="eb6e1-341">如果您有三個或多個原則，則最高和最低優先順序值之間的原則都具有 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-341">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="eb6e1-342">按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="eb6e1-343">完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="eb6e1-344">使用 Microsoft 365 Defender 入口網站來移除自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="eb6e1-345">當您使用 Microsoft 365 Defender 入口網站移除自訂的反網路釣魚原則時，會同時刪除反網路釣魚規則和對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="eb6e1-346">您無法移除預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="eb6e1-347">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="eb6e1-348">在 [ **反網路釣魚** 網頁] 頁面上，按一下原則的名稱，從清單中選取自訂原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-348">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="eb6e1-349">在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="eb6e1-350">在顯示的確認對話方塊中，按一下 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="eb6e1-351">使用 Exchange Online PowerShell 設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="eb6e1-352">如先前所述，反垃圾郵件原則是由反網路釣魚原則和反網路釣魚規則所組成。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="eb6e1-353">在 Exchange Online PowerShell 中，反網路釣魚原則與反網路釣魚規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="eb6e1-354">您可以使用 **\* -AntiPhishPolicy** Cmdlet 來管理反網路釣魚原則，並使用 **\* -AntiPhishRule** Cmdlet 來管理反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="eb6e1-355">在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="eb6e1-356">在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="eb6e1-357">當您從 PowerShell 中移除反網路釣魚原則時，不會自動移除對應的反網路釣魚規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="eb6e1-358">使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="eb6e1-359">在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="eb6e1-360">建立反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="eb6e1-361">建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="eb6e1-362">**附註**：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-362">**Notes**:</span></span>

- <span data-ttu-id="eb6e1-363">您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="eb6e1-364">反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="eb6e1-365">您可以在建立原則之前，于 Microsoft 365 Defender 入口網站中無法使用 PowerShell 中的新反網路釣魚原則上設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="eb6e1-366">_在_ `$false` **AntiPhishRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="eb6e1-367">在 _\<Number\>_ **AntiPhishRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="eb6e1-368">在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在 Microsoft 365 Defender 入口網站中。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="eb6e1-369">步驟1：使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="eb6e1-370">若要建立反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="eb6e1-371">此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="eb6e1-372"> (未使用 _enabled_ 參數時，也會啟用該原則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="eb6e1-373">描述為：「調研部門原則」。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="eb6e1-374">針對所有公認的網域及目標網域的 fabrikam.com 保護，啟用組織網域保護。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="eb6e1-375">指定 Mai Fujito (mfujito@fabrikam.com) 做為使用者以防範模擬。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="eb6e1-376">啟用信箱智慧。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="eb6e1-377">啟用信箱智慧保護，並指定隔離動作。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="eb6e1-378">啟用安全提示。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="eb6e1-379">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="eb6e1-380">步驟2：使用 PowerShell 建立反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="eb6e1-381">若要建立反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="eb6e1-382">在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="eb6e1-383">此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="eb6e1-384">此規則適用於名為 Research Department 之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="eb6e1-385">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="eb6e1-386">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="eb6e1-387">使用 PowerShell 來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="eb6e1-388">若要查看現有的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="eb6e1-389">此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="eb6e1-390">此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="eb6e1-391">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="eb6e1-392">使用 PowerShell 來查看反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="eb6e1-393">若要查看現有的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="eb6e1-394">此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="eb6e1-395">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="eb6e1-396">此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="eb6e1-397">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="eb6e1-398">使用 PowerShell 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="eb6e1-399">除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，如您在建立原則（如您在本文稍早的 [步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy) 區段中所述），您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="eb6e1-400">_MakeDefault_ 參數會將指定的原則轉換成預設原則 (套用至每個使用者，永遠 **最低** 的優先順序，而且您無法刪除只有當您在 PowerShell 中修改反網路釣魚原則時，才可使用此參數) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="eb6e1-401">您無法重新命名反網路釣魚原則 (**AntiPhishPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="eb6e1-402">當您重新命名 Microsoft 365 Defender 入口網站中的反網路釣魚原則時，您只會重新命名反網路釣魚 _規則_。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="eb6e1-403">若要修改反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="eb6e1-404">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="eb6e1-405">使用 PowerShell 修改反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="eb6e1-406">在 PowerShell 中修改反網路釣魚規則時，唯一無法使用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="eb6e1-407">若要啟用或停用現有的反網路釣魚規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="eb6e1-408">否則，當您在 PowerShell 中修改反網路釣魚規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="eb6e1-409">當您建立規則時，如本文稍早 [使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule) 一節所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="eb6e1-410">若要修改反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="eb6e1-411">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="eb6e1-412">使用 PowerShell 來啟用或停用反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="eb6e1-413">啟用或停用 PowerShell 中的反網路釣魚規則，可啟用或停用反網路釣魚規則和指派的反網路釣魚原則)  (的整個反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="eb6e1-414">您無法啟用或停用預設的反網路釣魚原則 (它永遠套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="eb6e1-415">若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="eb6e1-416">本範例會停用名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="eb6e1-417">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="eb6e1-418">如需詳細的語法及參數資訊，請參閱 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="eb6e1-419">使用 PowerShell 設定反網路釣魚規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="eb6e1-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="eb6e1-420">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-420">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="eb6e1-421">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-421">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="eb6e1-422">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-422">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="eb6e1-423">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-423">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="eb6e1-424">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-424">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="eb6e1-425">若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="eb6e1-426">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-426">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="eb6e1-427">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-427">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="eb6e1-428">**附註**：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-428">**Notes**:</span></span>

- <span data-ttu-id="eb6e1-429">若要在建立新規則時設定其優先順序，請改用 **AntiPhishRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="eb6e1-430">預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序 **值。**</span><span class="sxs-lookup"><span data-stu-id="eb6e1-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="eb6e1-431">使用 PowerShell 移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="eb6e1-432">當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="eb6e1-433">若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="eb6e1-434">此範例會移除名為「行銷部門」的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="eb6e1-435">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="eb6e1-436">使用 PowerShell 移除反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="eb6e1-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="eb6e1-437">當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="eb6e1-438">若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="eb6e1-439">此範例會移除名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="eb6e1-440">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="eb6e1-441">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="eb6e1-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="eb6e1-442">若要確認您是否已在 Office 365 的 Defender 中成功設定反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="eb6e1-443">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="eb6e1-444">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="eb6e1-445">若要查看更多詳細資料，請按一下 [名稱]，然後在顯示的浮出控制項中查看詳細資料，以選取清單中的原則。</span><span class="sxs-lookup"><span data-stu-id="eb6e1-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="eb6e1-446">在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，並執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="eb6e1-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
