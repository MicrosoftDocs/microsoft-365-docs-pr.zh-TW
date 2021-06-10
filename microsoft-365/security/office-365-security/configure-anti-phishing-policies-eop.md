---
title: 在 EOP 中設定反網路釣魚原則
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
description: 系統管理員可以瞭解如何使用或不具有 Exchange Online 信箱，來建立、修改和刪除 Exchange Online Protection (EOP) 組織中可用的反網路釣魚原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee227fe622f21d5b0f520507e1d88e2bbd0f3b31
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822307"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="30bb1-103">在 EOP 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="30bb1-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="30bb1-104">**Applies to**</span></span>
- [<span data-ttu-id="30bb1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="30bb1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="30bb1-106">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，則會有預設的反網路釣魚原則，其中包含預設會啟用的有限的反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="30bb1-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="30bb1-107">如需詳細資訊，請參閱[防網路釣魚原則中的詐騙](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="30bb1-108">系統管理員可以查看、編輯和設定 (，但不會刪除預設的反網路釣魚原則) 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="30bb1-109">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="30bb1-110">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="30bb1-111">具有 Exchange Online 信箱的組織可以設定 Microsoft 365 安全性中心或 Exchange Online PowerShell 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 security center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="30bb1-112">獨立 EOP 組織只能使用 [安全性中心]。</span><span class="sxs-lookup"><span data-stu-id="30bb1-112">Standalone EOP organizations can only use the security center.</span></span>

<span data-ttu-id="30bb1-113">如需建立及修改可用於 Office 365 microsoft defender 的更高級防網路釣魚原則的詳細資訊，請參閱[在 microsoft defender 中設定 Office 365 的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="30bb1-114">反網路釣魚原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="30bb1-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="30bb1-115">**反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。</span><span class="sxs-lookup"><span data-stu-id="30bb1-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="30bb1-116">**反網路釣魚規則**：指定原則套用至) 以進行反網路釣魚原則的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="30bb1-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="30bb1-117">當您在 [安全性中心] 管理反網路釣魚原則時，這兩個元素之間的差異並不明顯：</span><span class="sxs-lookup"><span data-stu-id="30bb1-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the security center:</span></span>

- <span data-ttu-id="30bb1-118">當您建立反網路釣魚原則時，實際上是建立反網路釣魚規則，同時也為這兩者使用相同的名稱建立了關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="30bb1-119">當您修改反網路釣魚原則時，與名稱、優先順序、啟用或停用的名稱和收件者篩選器相關的設定會修改反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="30bb1-120">所有其他設定會修改關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="30bb1-121">當您移除防網路釣魚原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="30bb1-122">在 Exchange Online PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="30bb1-123">如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 設定反網路釣魚原則](#use-exchange-online-powershell-to-configure-anti-phishing-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="30bb1-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="30bb1-124">每個組織都有一個名為 Office365 AntiPhish 的內建反網路釣魚原則，其具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="30bb1-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="30bb1-125">原則會套用至組織中的所有收件者，即使沒有反網路釣魚的規則 (收件者篩選) 與原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="30bb1-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="30bb1-126">此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="30bb1-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="30bb1-127">任何您建立的自訂原則皆具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="30bb1-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="30bb1-128">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="30bb1-129">若要提高反網路釣魚防護的效能，您可以建立自訂的反網路釣魚原則，其套用至特定使用者或使用者群組的更嚴格設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="30bb1-130">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="30bb1-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="30bb1-131">您可以開啟安全性中心，網址為 <https://security.microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="30bb1-131">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="30bb1-132">若要直接移至 [ **反網路釣魚** ] 頁面，請使用 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="30bb1-133">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="30bb1-134">您無法管理獨立 EOP PowerShell 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="30bb1-135">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="30bb1-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="30bb1-136">若要新增、修改和刪除反網路釣魚原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="30bb1-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="30bb1-137">若要唯讀的反網路釣魚原則存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="30bb1-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="30bb1-138">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="30bb1-139">**附註**：</span><span class="sxs-lookup"><span data-stu-id="30bb1-139">**Notes**:</span></span>

  - <span data-ttu-id="30bb1-140">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="30bb1-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="30bb1-141">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="30bb1-142">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **View-Only 組織管理** 角色群組也會提供該功能的唯讀存取權 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="30bb1-143">如需有關反網路釣魚原則的建議設定，請參閱 [EOP 反網路釣魚原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="30bb1-144">允許套用更新的原則最多30分鐘。</span><span class="sxs-lookup"><span data-stu-id="30bb1-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="30bb1-145">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱 [電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a><span data-ttu-id="30bb1-146">使用安全中心建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-146">Use the security center to create anti-phishing policies</span></span>

<span data-ttu-id="30bb1-147">在 [安全性中心] 中建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-147">Creating a custom anti-phishing policy in the security center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="30bb1-148">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-148">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="30bb1-149">在 [ **反網路釣魚** 網頁] 頁面上，按一下 [ ![ 建立圖示 ](../../media/m365-cc-sc-create-icon.png) **建立**]。</span><span class="sxs-lookup"><span data-stu-id="30bb1-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="30bb1-150">原則精靈隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="30bb1-150">The policy wizard opens.</span></span> <span data-ttu-id="30bb1-151">在 [ **原則名稱** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="30bb1-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="30bb1-152">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="30bb1-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="30bb1-153">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="30bb1-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="30bb1-154">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="30bb1-155">在顯示的 [使用者、群組和網域 **]** 頁面上，識別原則適用的內部收件者 (收件者條件)：</span><span class="sxs-lookup"><span data-stu-id="30bb1-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="30bb1-156">**使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="30bb1-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="30bb1-157">**群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="30bb1-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="30bb1-158">**網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="30bb1-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="30bb1-159">按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。</span><span class="sxs-lookup"><span data-stu-id="30bb1-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="30bb1-160">視需要重複此程序多次。</span><span class="sxs-lookup"><span data-stu-id="30bb1-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="30bb1-161">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="30bb1-161">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="30bb1-163">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="30bb1-163">next to the value.</span></span>

   <span data-ttu-id="30bb1-164">針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="30bb1-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="30bb1-165">針對使用者，接著輸入星號 (\*) 來查看所有可用的值。</span><span class="sxs-lookup"><span data-stu-id="30bb1-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="30bb1-166">相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="30bb1-167">不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="30bb1-168">**排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。</span><span class="sxs-lookup"><span data-stu-id="30bb1-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="30bb1-169">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="30bb1-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="30bb1-170">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="30bb1-171">在出現的 [ **網路釣魚閥值 & 保護** ] 頁面上，使用 [ **啟用欺騙情報** ] 核取方塊，以開啟或關閉欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="30bb1-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="30bb1-172">預設值為 (選取) 上，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="30bb1-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="30bb1-173">在下一個頁面上，設定要對封鎖的冒牌郵件採取的動作。</span><span class="sxs-lookup"><span data-stu-id="30bb1-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="30bb1-174">若要關閉欺騙情報，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="30bb1-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="30bb1-175">如果您的 MX 記錄未指向 Microsoft 365，您就不需要關閉反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="30bb1-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="30bb1-176">如需相關指示，請參閱[強化篩選的 Exchange Online 中的連接器](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="30bb1-177">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="30bb1-178">在顯示的 [動作 **]** 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="30bb1-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="30bb1-179">**如果偵測到郵件為欺騙** 性：只有在先前頁面上選取 [ **啟用哄騙情報** ] 時，才可使用此設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="30bb1-180">在已封鎖的欺騙寄件者的郵件下拉式清單中，選取下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="30bb1-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="30bb1-181">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="30bb1-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="30bb1-182">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="30bb1-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="30bb1-183">**安全性秘訣 & 指示器**：只有在您選取 [在上一頁上 **啟用欺騙情報** ] 時，才可使用此設定：</span><span class="sxs-lookup"><span data-stu-id="30bb1-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="30bb1-184">**Show (？ ) （未驗證的寄件者以取得哄騙**）：如果郵件未通過 SPF 或 DKIM 檢查 **，且** 郵件未透過 DMARC 或 [複合驗證](email-validation-and-authentication.md#composite-authentication)，則會在 Outlook 中的寄件者相片中新增問號。</span><span class="sxs-lookup"><span data-stu-id="30bb1-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="30bb1-185">**顯示「透過**」標籤：將透過 tag (chris@contoso.com 透過 Fabrikam.com) 新增至 [寄件者] 位址，如果不同于 DKIM 簽章中的網域或郵件的 [ **發件** 人] 位址。</span><span class="sxs-lookup"><span data-stu-id="30bb1-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

       > [!NOTE]
       > <span data-ttu-id="30bb1-186">目前，「 **透過」標記** 設定並非所有組織皆可使用。</span><span class="sxs-lookup"><span data-stu-id="30bb1-186">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="30bb1-187">如果您沒有顯示「**透過」標記** 設定，則會使用 [**顯示 (？ ) 針對您組織中未驗證的寄件者進行欺騙** 設定）來控制 [問號]**和**[via] 標記。</span><span class="sxs-lookup"><span data-stu-id="30bb1-187">If you don't have the **Show "via" tag** setting, the the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="30bb1-188">若要開啟設定，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="30bb1-188">To turn on a setting, select the check box.</span></span> <span data-ttu-id="30bb1-189">若要將它關閉，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="30bb1-189">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="30bb1-190">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-190">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="30bb1-191">在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-191">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="30bb1-192">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-192">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="30bb1-193">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="30bb1-193">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="30bb1-194">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="30bb1-194">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="30bb1-195">在顯示的確認頁面上，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-195">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a><span data-ttu-id="30bb1-196">使用安全中心來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-196">Use the security center to view anti-phishing policies</span></span>

1. <span data-ttu-id="30bb1-197">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-197">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="30bb1-198">在 [ **反網路釣魚** ] 頁面上，下列屬性會顯示在反網路釣魚原則的清單中：</span><span class="sxs-lookup"><span data-stu-id="30bb1-198">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="30bb1-199">**名稱**</span><span class="sxs-lookup"><span data-stu-id="30bb1-199">**Name**</span></span>
   - <span data-ttu-id="30bb1-200">**狀態**</span><span class="sxs-lookup"><span data-stu-id="30bb1-200">**Status**</span></span>
   - <span data-ttu-id="30bb1-201">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="30bb1-201">**Priority**</span></span>
   - <span data-ttu-id="30bb1-202">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="30bb1-202">**Last modified**</span></span>

3. <span data-ttu-id="30bb1-203">當您按一下名稱來選取原則時，原則設定會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="30bb1-203">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="30bb1-204">使用 [安全性中心] 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-204">Use the security center to modify anti-phishing policies</span></span>

1. <span data-ttu-id="30bb1-205">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-205">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="30bb1-206">在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-206">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="30bb1-207">在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-207">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="30bb1-208">如需這些設定的詳細資訊，請參閱本文前面的 [使用安全性中心建立反網路釣魚原則](#use-the-security-center-to-create-anti-phishing-policies) 一節。</span><span class="sxs-lookup"><span data-stu-id="30bb1-208">For more information about the settings, see the [Use the security center to create anti-phishing policies](#use-the-security-center-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="30bb1-209">針對預設的反網路釣魚原則，「 **使用者、群組及網域** 」區段無法使用 (原則套用至所有人) ，而且您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-209">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="30bb1-210">若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="30bb1-210">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="30bb1-211">啟用或停用自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-211">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="30bb1-212">您無法停用預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-212">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="30bb1-213">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-213">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="30bb1-214">在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取自訂原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-214">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="30bb1-215">在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="30bb1-215">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="30bb1-216">**原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-216">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="30bb1-217">**原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-217">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="30bb1-218">在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-218">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="30bb1-219">按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-219">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="30bb1-220">回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-220">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="30bb1-221">設定自訂的反網路釣魚原則優先順序</span><span class="sxs-lookup"><span data-stu-id="30bb1-221">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="30bb1-222">根據預設，反網路釣魚原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-222">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="30bb1-223">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="30bb1-223">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="30bb1-224">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="30bb1-224">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="30bb1-225">若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在安全性中心直接修改 [優先順序 **]** 編號)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-225">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="30bb1-226">只有在您有多個原則時，變更原則的優先順序才有意義。</span><span class="sxs-lookup"><span data-stu-id="30bb1-226">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="30bb1-227">**附註**：</span><span class="sxs-lookup"><span data-stu-id="30bb1-227">**Notes**:</span></span>

- <span data-ttu-id="30bb1-228">在 [安全性中心] 中，您只能在建立反網路釣魚原則之後變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="30bb1-228">In the security center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="30bb1-229">在 PowerShell 中，您可以在建立反網路釣魚規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="30bb1-229">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="30bb1-230">反網路釣魚原則會依顯示的連續處理 (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-230">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="30bb1-231">預設的反網路釣魚原則的優先順序值是 **最低** 的，您無法變更。</span><span class="sxs-lookup"><span data-stu-id="30bb1-231">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="30bb1-232">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-232">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="30bb1-233">在 [ **反網路釣魚** ] 頁面上，按一下清單中的名稱，以選取自訂原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-233">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="30bb1-234">在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：</span><span class="sxs-lookup"><span data-stu-id="30bb1-234">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="30bb1-235">具有 **Priority** 值 **0** 的反網路釣魚原則只有 [ **降低優先順序** ] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="30bb1-235">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="30bb1-236">具有最低 **優先順序** 值的反網路釣魚原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="30bb1-236">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="30bb1-237">如果您有三個或更多的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="30bb1-237">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="30bb1-238">按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。</span><span class="sxs-lookup"><span data-stu-id="30bb1-238">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="30bb1-239">完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-239">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="30bb1-240">使用安全中心來移除自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-240">Use the security center to remove custom anti-phishing policies</span></span>

<span data-ttu-id="30bb1-241">當您使用 [安全性中心] 移除自訂的反網路釣魚原則時，會同時刪除反網路釣魚規則和對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-241">When you use the security center to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="30bb1-242">您無法移除預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-242">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="30bb1-243">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-243">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="30bb1-244">按一下原則的名稱，從清單中選取自訂原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-244">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="30bb1-245">在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-245">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="30bb1-246">在顯示的確認對話方塊中，按一下 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-246">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="30bb1-247">使用 Exchange Online PowerShell 設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-247">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="30bb1-248">如先前所述，反網路釣魚原則是由反網路釣魚原則和反網路釣魚規則所組成。</span><span class="sxs-lookup"><span data-stu-id="30bb1-248">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="30bb1-249">在 Exchange Online PowerShell 中，反網路釣魚原則與反網路釣魚規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="30bb1-249">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="30bb1-250">您可以使用 **\* -AntiPhishPolicy** Cmdlet 來管理反網路釣魚原則，並使用 **\* -AntiPhishRule** Cmdlet 來管理反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-250">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="30bb1-251">在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-251">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="30bb1-252">在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-252">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="30bb1-253">當您從 PowerShell 中移除反網路釣魚原則時，不會自動移除對應的反網路釣魚規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="30bb1-253">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="30bb1-254">在獨立 EOP 組織中，使用 Exchange Online Protection PowerShell 無法使用下列 PowerShell 程式。</span><span class="sxs-lookup"><span data-stu-id="30bb1-254">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="30bb1-255">使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-255">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="30bb1-256">在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="30bb1-256">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="30bb1-257">建立反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-257">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="30bb1-258">建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-258">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="30bb1-259">**附註**：</span><span class="sxs-lookup"><span data-stu-id="30bb1-259">**Notes**:</span></span>

- <span data-ttu-id="30bb1-260">您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="30bb1-260">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="30bb1-261">反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="30bb1-261">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="30bb1-262">您可以在 [安全性中心] 中的 [PowerShell 中，設定下列設定的下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="30bb1-262">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>

  - <span data-ttu-id="30bb1-263">_在_ `$false` **AntiPhishRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="30bb1-263">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="30bb1-264">在 _\<Number\>_ **AntiPhishRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="30bb1-264">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="30bb1-265">在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在 [安全性中心] 中。</span><span class="sxs-lookup"><span data-stu-id="30bb1-265">A new anti-phish policy that you create in PowerShell isn't visible in the security center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="30bb1-266">步驟1：使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-266">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="30bb1-267">若要建立反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-267">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="30bb1-268">此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚策略：</span><span class="sxs-lookup"><span data-stu-id="30bb1-268">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="30bb1-269">描述為：「調研部門原則」。</span><span class="sxs-lookup"><span data-stu-id="30bb1-269">The description is: Research department policy.</span></span>
- <span data-ttu-id="30bb1-270">將哄騙的預設動作變更為「隔離」。</span><span class="sxs-lookup"><span data-stu-id="30bb1-270">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="30bb1-271">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-271">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="30bb1-272">步驟2：使用 PowerShell 建立反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="30bb1-272">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="30bb1-273">若要建立反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-273">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="30bb1-274">在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：</span><span class="sxs-lookup"><span data-stu-id="30bb1-274">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="30bb1-275">此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="30bb1-275">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="30bb1-276">此規則適用於名為 Research Department 之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="30bb1-276">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="30bb1-277">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="30bb1-277">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="30bb1-278">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-278">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="30bb1-279">使用 PowerShell 來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-279">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="30bb1-280">若要查看現有的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-280">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="30bb1-281">此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="30bb1-281">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="30bb1-282">此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="30bb1-282">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="30bb1-283">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-283">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="30bb1-284">使用 PowerShell 來查看反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="30bb1-284">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="30bb1-285">若要查看現有的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-285">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="30bb1-286">此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="30bb1-286">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="30bb1-287">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="30bb1-287">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="30bb1-288">此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="30bb1-288">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="30bb1-289">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-289">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="30bb1-290">使用 PowerShell 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-290">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="30bb1-291">除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，如您在建立原則時，依照 [步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy) 中所述，您可以在本文中修改反網路釣魚原則時，使用相同設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-291">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="30bb1-292">_MakeDefault_ 參數會將指定的原則轉換成預設原則 (套用至每個使用者，永遠 **最低** 的優先順序，而且您無法刪除只有當您在 PowerShell 中修改反網路釣魚原則時，才可使用此參數) 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-292">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="30bb1-293">您無法重新命名反網路釣魚原則 (**AntiPhishPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-293">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="30bb1-294">當您重新命名 [安全性中心] 中的反網路釣魚原則時，您只是重新命名反網路釣魚 _規則_。</span><span class="sxs-lookup"><span data-stu-id="30bb1-294">When you rename an anti-phishing policy in the security center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="30bb1-295">若要修改反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-295">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="30bb1-296">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-296">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="30bb1-297">使用 PowerShell 修改反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="30bb1-297">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="30bb1-298">當您在 PowerShell 中修改反網路釣魚規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-298">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="30bb1-299">若要啟用或停用現有的反網路釣魚規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="30bb1-299">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="30bb1-300">否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule) ] 區段所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="30bb1-300">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="30bb1-301">若要修改反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-301">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="30bb1-302">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-302">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="30bb1-303">使用 PowerShell 來啟用或停用反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="30bb1-303">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="30bb1-304">啟用或停用 PowerShell 中的反網路釣魚規則，可啟用或停用反網路釣魚規則和指派的反網路釣魚原則)  (的整個反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-304">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="30bb1-305">您無法啟用或停用預設的反網路釣魚原則 (它永遠套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="30bb1-305">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="30bb1-306">若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-306">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="30bb1-307">本範例會停用名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-307">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="30bb1-308">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-308">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="30bb1-309">如需詳細的語法及參數資訊，請參閱 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-309">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="30bb1-310">使用 PowerShell 設定反網路釣魚規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="30bb1-310">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="30bb1-311">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="30bb1-311">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="30bb1-312">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="30bb1-312">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="30bb1-313">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="30bb1-313">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="30bb1-314">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="30bb1-314">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="30bb1-315">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="30bb1-315">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="30bb1-316">若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-316">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="30bb1-317">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="30bb1-317">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="30bb1-318">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-318">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="30bb1-319">**附註**：</span><span class="sxs-lookup"><span data-stu-id="30bb1-319">**Notes**:</span></span>

- <span data-ttu-id="30bb1-320">若要在建立新規則時設定其優先順序，請改用 **AntiPhishRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="30bb1-320">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="30bb1-321">預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序 **值。**</span><span class="sxs-lookup"><span data-stu-id="30bb1-321">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="30bb1-322">使用 PowerShell 移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="30bb1-322">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="30bb1-323">當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-323">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="30bb1-324">若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-324">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="30bb1-325">此範例會移除名為「行銷部門」的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-325">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="30bb1-326">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-326">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="30bb1-327">使用 PowerShell 移除反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="30bb1-327">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="30bb1-328">當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-328">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="30bb1-329">若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="30bb1-329">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="30bb1-330">此範例會移除名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-330">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="30bb1-331">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="30bb1-331">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="30bb1-332">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="30bb1-332">How do you know these procedures worked?</span></span>

<span data-ttu-id="30bb1-333">若要確認您是否已在 EOP 中成功設定反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="30bb1-333">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="30bb1-334">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="30bb1-334">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="30bb1-335">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="30bb1-335">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="30bb1-336">若要查看更多詳細資料，請按一下 [名稱]，然後在顯示的浮出控制項中查看詳細資料，以選取清單中的原則。</span><span class="sxs-lookup"><span data-stu-id="30bb1-336">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="30bb1-337">在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="30bb1-337">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
