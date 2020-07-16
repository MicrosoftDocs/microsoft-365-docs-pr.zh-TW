---
title: 在 EOP 中設定反網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 exchange Online Protection （EOP）組織中建立、修改和刪除可用的反網路釣魚原則，但不含 Exchange Online 信箱。
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726781"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="f185a-103">在 EOP 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="f185a-104">在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，有預設的反網路釣魚原則，其中包含預設啟用的有限的反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="f185a-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="f185a-105">如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="f185a-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f185a-106">系統管理員可以查看、編輯和設定（但不能刪除）預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="f185a-107">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="f185a-108">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="f185a-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="f185a-109">具有 Exchange Online 信箱的組織可在安全性 & 合規性中心或 Exchange Online PowerShell 中設定反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="f185a-110">獨立 EOP 組織只能使用安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="f185a-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="f185a-111">如需建立及修改 Office 365 Advanced 威脅防護（Office 365 ATP）中可用的更高級 ATP 反網路釣魚原則的詳細資訊，請參閱[設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f185a-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="f185a-112">安全性 & 規範中心與 PowerShell 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="f185a-113">反網路釣魚原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="f185a-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="f185a-114">**反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。</span><span class="sxs-lookup"><span data-stu-id="f185a-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="f185a-115">**反網路釣魚規則**：為反網路釣魚原則指定優先順序和收件者篩選器（該原則套用於誰）。</span><span class="sxs-lookup"><span data-stu-id="f185a-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="f185a-116">當您在安全性 & 合規性中心管理反網路釣魚原則時，這兩個元素之間的差異並不明顯。</span><span class="sxs-lookup"><span data-stu-id="f185a-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f185a-117">當您在安全性 & 合規性中心建立反網路釣魚原則時，實際上您實際上是建立反網路釣魚規則和相關聯的反網路釣魚原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="f185a-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="f185a-118">當您在安全性 & 規範中心修改反網路釣魚原則時，與名稱、優先順序、已啟用或已停用的設定或收件者篩選器相關的設定會修改反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="f185a-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="f185a-119">所有其他設定會修改關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="f185a-120">當您從安全性 & 合規性中心移除防網路釣魚原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="f185a-121">在 Exchange Online PowerShell 中，反網路釣魚原則和反網路釣魚規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="f185a-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="f185a-122">您可以使用\*\* \* -AntiPhishPolicy\*\* Cmdlet 來管理反網路釣魚原則，並使用\*\* \* -AntiPhishRule\*\* Cmdlet 來管理反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="f185a-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="f185a-123">在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="f185a-124">在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="f185a-125">預設 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="f185a-126">每個組織都有一個名為 Office365 AntiPhish 的內建反網路釣魚原則，其具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="f185a-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="f185a-127">名稱為 Office365 AntiPhish 的原則會套用至組織中的所有收件者，即使沒有與原則相關聯的反網路釣魚規則（收件者篩選器）。</span><span class="sxs-lookup"><span data-stu-id="f185a-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="f185a-128">名為 Office365 AntiPhish 的原則預設具有您無法修改的自訂**優先順序值（** 原則永遠會最後套用）。</span><span class="sxs-lookup"><span data-stu-id="f185a-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="f185a-129">您建立的任何自訂原則的優先順序都會高於名為 Office365 AntiPhish Default 的原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="f185a-130">名為 Office365 AntiPhish 的原則預設為預設原則（ **IsDefault**屬性具有值 `True` ），而且您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="f185a-131">若要提高反網路釣魚防護的效能，您可以建立自訂的反網路釣魚原則，其套用至特定使用者或使用者群組的更嚴格設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f185a-132">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="f185a-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f185a-133">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="f185a-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f185a-134">若要直接移至 [**反網路釣魚**] 頁面，請使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="f185a-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f185a-135">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f185a-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="f185a-136">您無法管理獨立 EOP PowerShell 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="f185a-137">您必須已獲指派許可權，才能執行本主題中的程式：</span><span class="sxs-lookup"><span data-stu-id="f185a-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f185a-138">若要新增、修改和刪除反網路釣魚原則，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="f185a-138">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f185a-139">在[安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md)的**組織管理**或**安全性管理員**。</span><span class="sxs-lookup"><span data-stu-id="f185a-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f185a-140">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**組織管理**或**衛生管理**。</span><span class="sxs-lookup"><span data-stu-id="f185a-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f185a-141">若要唯讀的反網路釣魚原則存取權，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="f185a-141">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f185a-142">安全性[& 規範中心](permissions-in-the-security-and-compliance-center.md)的**安全性讀取器**。</span><span class="sxs-lookup"><span data-stu-id="f185a-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f185a-143">在[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中**View-Only 的組織管理**。</span><span class="sxs-lookup"><span data-stu-id="f185a-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="f185a-144">若要能夠在獨立 EOP 中建立及修改反垃圾郵件原則，您需要針對租使用者執行需要_分解_的專案。</span><span class="sxs-lookup"><span data-stu-id="f185a-144">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="f185a-145">例如，在 Exchange 系統管理中心（EAC）中，您可以移至 [**許可權**] 索引標籤、選取現有的角色群組、按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 及 [移除角色] （最終將新增回）。</span><span class="sxs-lookup"><span data-stu-id="f185a-145">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="f185a-146">如果您的租使用者從未 hydrated，您會看到一個名為「**更新組織」設定**的對話方塊，其進度列應該會順利完成。</span><span class="sxs-lookup"><span data-stu-id="f185a-146">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="f185a-147">如需分解的詳細資訊，請參閱[Enable-OrganizationCustomization 指令程式](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization)（不可在獨立 EOP PowerShell 或安全性 & 規範中心）。</span><span class="sxs-lookup"><span data-stu-id="f185a-147">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="f185a-148">如需有關反網路釣魚原則的建議設定，請參閱[EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="f185a-148">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="f185a-149">允許套用更新的原則最多30分鐘。</span><span class="sxs-lookup"><span data-stu-id="f185a-149">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="f185a-150">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱[電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="f185a-150">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="f185a-151">使用安全性 & 規範中心建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-151">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="f185a-152">在安全性 & 合規性中心建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-152">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="f185a-153">當您建立反網路釣魚原則時，您只能指定原則名稱、描述及識別套用原則的收件者篩選器。</span><span class="sxs-lookup"><span data-stu-id="f185a-153">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="f185a-154">建立原則之後，您可以修改原則，以變更或審閱預設的反網路釣魚設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-154">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="f185a-155">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f185a-156">在 [**反網路釣魚**] 頁面上，按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-156">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="f185a-157">[**建立新的反網路釣魚原則**] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f185a-157">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="f185a-158">在 [**命名您的原則**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="f185a-158">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="f185a-159">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="f185a-159">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="f185a-160">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="f185a-160">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f185a-161">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f185a-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f185a-162">在出現的 [套用**至**] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="f185a-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="f185a-163">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="f185a-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f185a-164">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="f185a-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f185a-165">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="f185a-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="f185a-166">按一下 [**新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-166">Click **Add a condition**.</span></span> <span data-ttu-id="f185a-167">在出現的下拉式清單中，選取 [**適用于**下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="f185a-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="f185a-168">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="f185a-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f185a-169">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="f185a-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="f185a-170">**收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="f185a-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="f185a-171">選取條件後，會出現對應的下拉式清單，其中有**其中**一個方塊。</span><span class="sxs-lookup"><span data-stu-id="f185a-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="f185a-172">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="f185a-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="f185a-173">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="f185a-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="f185a-174">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="f185a-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="f185a-175">若要移除個別專案， **Remove**請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="f185a-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="f185a-176">若要移除整個條件，請**Remove**按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="f185a-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="f185a-177">若要新增其他條件，請按一下 [**新增條件**]，然後選取 [套用**于 if**中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="f185a-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="f185a-178">若要新增例外狀況，請按一下 [**新增條件**]，然後選取 [**除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="f185a-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="f185a-179">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="f185a-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f185a-180">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f185a-180">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f185a-181">在 [**複查您的設定**] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="f185a-182">您可以按一下每個設定的 [**編輯**] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="f185a-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="f185a-183">當您完成時，按一下 [**建立這個原則**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-183">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="f185a-184">在出現的確認對話方塊中，按一下 [**確定**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-184">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="f185a-185">使用這些一般原則設定建立反網路釣魚原則之後，請使用下一節中的指示來設定原則中的保護設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-185">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="f185a-186">使用安全性 & 規範中心來修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-186">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="f185a-187">請使用下列程式修改反網路釣魚原則：您建立的新原則，或您已自訂的現有原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-187">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="f185a-188">如果您還沒有開啟安全性 & 規範中心，請移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-188">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f185a-189">選取您要修改的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-189">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="f185a-190">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="f185a-190">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f185a-191">隨即會顯示 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="f185a-191">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="f185a-192">按一下任何區段中的 [**編輯**]，即可存取該區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-192">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="f185a-193">下列步驟會以區段出現的順序顯示，但不是連續的（您可以選取及修改所有順序的區段）。</span><span class="sxs-lookup"><span data-stu-id="f185a-193">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="f185a-194">按一下區段中的 [**編輯**] 之後，可用的設定會以一種方式呈現出來，但是您可以在頁面中以任何順序跳離，也可以按一下任何頁面上的 [**儲存**] （或 [**取消**] 或 [**關閉** ![ ] 關閉圖示，以 ](../../media/scc-remove-icon.png) 回到 [\*\*編輯您的原則 \<name\> \*\* ] 頁面）。</span><span class="sxs-lookup"><span data-stu-id="f185a-194">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="f185a-195">**原則設定**：按一下 [**編輯**]，修改當您在上一節中[建立原則](#use-the-security--compliance-center-to-create-anti-phishing-policies)時可用的相同設定：</span><span class="sxs-lookup"><span data-stu-id="f185a-195">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="f185a-196">**Name**</span><span class="sxs-lookup"><span data-stu-id="f185a-196">**Name**</span></span>
   - <span data-ttu-id="f185a-197">**描述**</span><span class="sxs-lookup"><span data-stu-id="f185a-197">**Description**</span></span>
   - <span data-ttu-id="f185a-198">**套用對象**</span><span class="sxs-lookup"><span data-stu-id="f185a-198">**Applied to**</span></span>
   - <span data-ttu-id="f185a-199">**檢查您的設定**</span><span class="sxs-lookup"><span data-stu-id="f185a-199">**Review your settings**</span></span>

   <span data-ttu-id="f185a-200">完成後，按一下 [**儲存**] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="f185a-200">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="f185a-201">**哄騙**：按一下 [**編輯**] 以開啟或關閉欺騙情報、在 Outlook 中開啟或關閉未驗證寄件者識別，以及設定要套用至封鎖的欺騙寄件者的郵件的動作。</span><span class="sxs-lookup"><span data-stu-id="f185a-201">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="f185a-202">如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="f185a-202">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="f185a-203">請注意，ATP 反網路釣魚原則中也提供這些相同設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-203">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="f185a-204">**哄騙篩選設定**：預設值為 [**開啟**]，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="f185a-204">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="f185a-205">若要將它關閉，請將開關滑動至 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-205">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="f185a-206">如需詳細資訊，請參閱[在 EOP 中設定欺騙智慧](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="f185a-206">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="f185a-207">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="f185a-207">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="f185a-208">如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="f185a-208">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="f185a-209">**啟用未經驗證的寄件者功能**：預設值為**On**。</span><span class="sxs-lookup"><span data-stu-id="f185a-209">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="f185a-210">若要將它關閉，請將開關滑動至 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-210">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="f185a-211">**動作**：指定對哄騙智慧失敗的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="f185a-211">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="f185a-212">**如果電子郵件是由不允許哄騙您網域的人員所傳送**：</span><span class="sxs-lookup"><span data-stu-id="f185a-212">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="f185a-213">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="f185a-213">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="f185a-214">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="f185a-214">**Quarantine the message**</span></span>

   - <span data-ttu-id="f185a-215">請**複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="f185a-215">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="f185a-216">您可以按一下每個區段中的 [**編輯**]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="f185a-216">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="f185a-217">您可以在此頁面**上\*\*\*\*直接切換**下列設定：</span><span class="sxs-lookup"><span data-stu-id="f185a-217">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="f185a-218">**啟用 antispoofing 保護**</span><span class="sxs-lookup"><span data-stu-id="f185a-218">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="f185a-219">**啟用未經驗證的寄件者功能**</span><span class="sxs-lookup"><span data-stu-id="f185a-219">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="f185a-220">完成後，按一下 [**儲存**] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="f185a-220">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="f185a-221">回到 [**編輯您的原則 \<Name\> \*\* ] 頁面上，複查您的設定，然後按一下 [**關閉\*\*]。</span><span class="sxs-lookup"><span data-stu-id="f185a-221">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="f185a-222">使用安全性 & 合規性中心來修改預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-222">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="f185a-223">預設的反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會顯示在原則清單中。</span><span class="sxs-lookup"><span data-stu-id="f185a-223">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="f185a-224">若要修改預設的反網路釣魚原則，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f185a-224">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="f185a-225">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-225">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f185a-226">在 [**反網路釣魚**] 頁面上，按一下 [**預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-226">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="f185a-227">隨即會顯示 [**編輯您的原則 Office365 AntiPhish 預設**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f185a-227">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="f185a-228">下列各節可供使用，其中包含[修改自訂原則](#use-the-security--compliance-center-to-modify-anti-phishing-policies)時的相同設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-228">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="f185a-229">**模擬**</span><span class="sxs-lookup"><span data-stu-id="f185a-229">**Impersonation**</span></span>
   - <span data-ttu-id="f185a-230">**惡搞**</span><span class="sxs-lookup"><span data-stu-id="f185a-230">**Spoof**</span></span>
   - <span data-ttu-id="f185a-231">**進階設定**</span><span class="sxs-lookup"><span data-stu-id="f185a-231">**Advanced settings**</span></span>

   <span data-ttu-id="f185a-232">當您修改預設原則時，無法使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="f185a-232">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="f185a-233">您可以看到 [**原則設定**] 區段和 [值]，但沒有**編輯**連結，所以您無法修改設定（原則名稱、描述及原則套用至的人員）（此原則會套用至所有收件者）。</span><span class="sxs-lookup"><span data-stu-id="f185a-233">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="f185a-234">您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-234">You can't delete the default policy.</span></span>
   - <span data-ttu-id="f185a-235">您無法變更預設原則的優先順序（預設原則為 [永不最後套用]）。</span><span class="sxs-lookup"><span data-stu-id="f185a-235">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="f185a-236">在 [**編輯您的原則 Office365 AntiPhish 預設**] 頁面上，複查您的設定，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f185a-236">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="f185a-237">啟用或停用自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-237">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="f185a-238">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f185a-239">請注意 [**狀態**] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="f185a-239">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="f185a-240">將 [切換] 滑動至 [**關閉**] 以停用原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-240">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="f185a-241">將切換滑動至**開啟**以啟用原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-241">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="f185a-242">您無法停用預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-242">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="f185a-243">設定自訂的反網路釣魚原則優先順序</span><span class="sxs-lookup"><span data-stu-id="f185a-243">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="f185a-244">根據預設，反網路釣魚原則的優先順序會根據建立的順序而定（較舊的原則的優先順序較舊）。</span><span class="sxs-lookup"><span data-stu-id="f185a-244">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="f185a-245">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="f185a-245">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f185a-246">不會有兩個原則的優先順序相同。</span><span class="sxs-lookup"><span data-stu-id="f185a-246">No two policies can have the same priority.</span></span>

<span data-ttu-id="f185a-247">自訂的反網路釣魚原則會以處理的順序顯示（第一個原則的**Priority**值為0）。</span><span class="sxs-lookup"><span data-stu-id="f185a-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f185a-248">預設的反網路釣魚原則（名為 Office365 AntiPhish Default）的自訂優先順序值是**最低**的，您無法變更它。</span><span class="sxs-lookup"><span data-stu-id="f185a-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="f185a-249">**附注**：在 [安全性 & 規範中心] 中，您只能在建立反網路釣魚原則之後變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="f185a-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="f185a-250">在 PowerShell 中，您可以在建立反網路釣魚規則（可能會影響現有規則的優先順序）時，覆寫預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f185a-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="f185a-251">若要變更原則的優先順序，請按一下 [**增加優先順序**] 或 [**降低**優先順序] 中原則的屬性（您無法直接修改安全性 & 規範中心中的**優先順序**號碼）。</span><span class="sxs-lookup"><span data-stu-id="f185a-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="f185a-252">如果您有多個原則，變更原則的優先順序只會有意義。</span><span class="sxs-lookup"><span data-stu-id="f185a-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="f185a-253">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="f185a-254">選取您要修改的原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="f185a-255">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="f185a-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f185a-256">隨即會顯示 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="f185a-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="f185a-257">**優先順序**值為**0**的自訂反網路釣魚原則只有「**降低優先順序**」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="f185a-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="f185a-258">具有最低**優先順序**值的自訂反網路釣魚原則（例如， **3**）只有 [**增加優先順序**] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="f185a-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="f185a-259">如果您有三個或多個自訂的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [**增加優先順序**] 和 [**降低優先順序**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f185a-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="f185a-260">按一下 [**增加優先順序**] 或 [**降低優先順序**] 以變更 [**優先順序**] 值。</span><span class="sxs-lookup"><span data-stu-id="f185a-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="f185a-261">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f185a-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="f185a-262">使用安全性 & 規範中心來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="f185a-263">在安全性 & 規範中心，然後移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f185a-264">請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="f185a-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="f185a-265">選取您要查看的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="f185a-266">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="f185a-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="f185a-267">按一下 [**預設原則**] 以查看預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="f185a-268">此時會出現 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗，您可以在其中查看設定和值。</span><span class="sxs-lookup"><span data-stu-id="f185a-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="f185a-269">使用安全性 & 規範中心移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="f185a-270">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f185a-271">選取您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="f185a-272">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="f185a-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f185a-273">在出現的 [**編輯 \<name\> 您的原則**] 浮出視窗中，按一下 [**刪除原則**]，然後在出現的警告對話方塊中按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="f185a-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="f185a-274">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="f185a-275">使用 Exchange Online PowerShell 設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="f185a-276">在獨立 EOP 組織中無法使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="f185a-276">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="f185a-277">使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-277">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="f185a-278">在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="f185a-278">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f185a-279">建立反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-279">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="f185a-280">建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-280">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="f185a-281">**附註**：</span><span class="sxs-lookup"><span data-stu-id="f185a-281">**Notes**:</span></span>

- <span data-ttu-id="f185a-282">您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="f185a-282">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="f185a-283">反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="f185a-283">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="f185a-284">您可以在 PowerShell 中為安全性 & 相容性中心以外的新反網路釣魚原則設定下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="f185a-284">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f185a-285">建立新原則為停用（_ _ `$false` 在**AntiPhishRule** Cmdlet 上啟用）。</span><span class="sxs-lookup"><span data-stu-id="f185a-285">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="f185a-286">_Priority_ _\<Number\>_ 在**AntiPhishRule** Cmdlet 上建立（優先順序）時設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f185a-286">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="f185a-287">在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="f185a-287">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="f185a-288">步驟1：使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-288">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="f185a-289">若要建立反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-289">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="f185a-290">此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="f185a-290">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="f185a-291">原則已啟用（未使用_enabled_參數，預設值為 `$true` ）。</span><span class="sxs-lookup"><span data-stu-id="f185a-291">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="f185a-292">描述為：「調研部門原則」。</span><span class="sxs-lookup"><span data-stu-id="f185a-292">The description is: Research department policy.</span></span>
- <span data-ttu-id="f185a-293">將哄騙的預設動作變更為「隔離」。</span><span class="sxs-lookup"><span data-stu-id="f185a-293">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="f185a-294">如需詳細的語法及參數資訊，請參閱[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="f185a-294">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="f185a-295">步驟2：使用 PowerShell 建立反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="f185a-295">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="f185a-296">若要建立反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-296">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="f185a-297">在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：</span><span class="sxs-lookup"><span data-stu-id="f185a-297">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="f185a-298">此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="f185a-298">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="f185a-299">此規則適用於名為 Research Department 之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f185a-299">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="f185a-300">因為我們沒有使用_priority_參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f185a-300">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="f185a-301">如需詳細的語法及參數資訊，請參閱[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="f185a-301">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="f185a-302">使用 PowerShell 來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-302">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="f185a-303">若要查看現有的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-303">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f185a-304">此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="f185a-304">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="f185a-305">此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="f185a-305">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="f185a-306">如需詳細的語法及參數資訊，請參閱[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="f185a-306">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="f185a-307">使用 PowerShell 來查看反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="f185a-307">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="f185a-308">若要查看現有的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-308">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f185a-309">此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="f185a-309">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="f185a-310">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f185a-310">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="f185a-311">此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="f185a-311">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="f185a-312">如需詳細的語法及參數資訊，請參閱[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="f185a-312">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="f185a-313">使用 PowerShell 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-313">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="f185a-314">除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，當您在本主題稍早的[步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy)區段中所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-314">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="f185a-315">在 PowerShell 中修改反網路釣魚原則時，可將指定的原則變成預設原則（適用于所有人、永不**最低**的優先順序，而且無法刪除）的_MakeDefault_參數。</span><span class="sxs-lookup"><span data-stu-id="f185a-315">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="f185a-316">您無法重新命名反網路釣魚原則（ **AntiPhishPolicy** Cmdlet 沒有_Name_參數）。</span><span class="sxs-lookup"><span data-stu-id="f185a-316">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f185a-317">當您在安全性 & 合規性中心重新命名防網路釣魚原則時，您只是重新命名反網路釣魚_規則_。</span><span class="sxs-lookup"><span data-stu-id="f185a-317">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="f185a-318">若要修改反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-318">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f185a-319">如需詳細的語法及參數資訊，請參閱[Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="f185a-319">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="f185a-320">使用 PowerShell 修改反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="f185a-320">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="f185a-321">在 PowerShell 中修改反網路釣魚規則時，唯一無法使用的設定是_Enabled_參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="f185a-321">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f185a-322">若要啟用或停用現有的反網路釣魚規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="f185a-322">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="f185a-323">否則，當您在 PowerShell 中修改反網路釣魚規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="f185a-323">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="f185a-324">當您建立規則時，如本主題稍早的[步驟2：使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule)一節所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="f185a-324">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="f185a-325">若要修改反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-325">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f185a-326">如需詳細的語法及參數資訊，請參閱[Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="f185a-326">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="f185a-327">使用 PowerShell 來啟用或停用反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="f185a-327">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="f185a-328">啟用或停用 PowerShell 中的反網路釣魚規則可啟用或停用整個反網路釣魚原則（反網路釣魚規則和指派的反網路釣魚原則）。</span><span class="sxs-lookup"><span data-stu-id="f185a-328">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="f185a-329">您無法啟用或停用預設的反網路釣魚原則（永遠套用到所有收件者）。</span><span class="sxs-lookup"><span data-stu-id="f185a-329">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="f185a-330">若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-330">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="f185a-331">本範例會停用名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="f185a-331">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f185a-332">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="f185a-332">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f185a-333">如需詳細的語法及參數資訊，請參閱[Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule)和[Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="f185a-333">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="f185a-334">使用 PowerShell 設定反網路釣魚規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="f185a-334">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="f185a-335">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="f185a-335">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f185a-336">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="f185a-336">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f185a-337">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="f185a-337">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f185a-338">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="f185a-338">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f185a-339">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="f185a-339">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f185a-340">若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-340">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f185a-341">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="f185a-341">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="f185a-342">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="f185a-342">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f185a-343">**附註**：</span><span class="sxs-lookup"><span data-stu-id="f185a-343">**Notes**:</span></span>

- <span data-ttu-id="f185a-344">若要在建立新規則時設定其優先順序，請改用**AntiPhishRule** Cmdlet 上的_priority_參數。</span><span class="sxs-lookup"><span data-stu-id="f185a-344">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="f185a-345">預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序**值。**</span><span class="sxs-lookup"><span data-stu-id="f185a-345">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="f185a-346">使用 PowerShell 移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="f185a-346">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="f185a-347">當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="f185a-347">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="f185a-348">若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-348">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f185a-349">此範例會移除名為「行銷部門」的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-349">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f185a-350">如需詳細的語法及參數資訊，請參閱[Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="f185a-350">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="f185a-351">使用 PowerShell 移除反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="f185a-351">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="f185a-352">當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="f185a-352">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="f185a-353">若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f185a-353">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="f185a-354">此範例會移除名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="f185a-354">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f185a-355">如需詳細的語法及參數資訊，請參閱[Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="f185a-355">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f185a-356">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="f185a-356">How do you know these procedures worked?</span></span>

<span data-ttu-id="f185a-357">若要確認您是否已成功設定 ATP 反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="f185a-357">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="f185a-358">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="f185a-358">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="f185a-359">請確認原則的清單、其**狀態**值，以及其**優先順序**值。</span><span class="sxs-lookup"><span data-stu-id="f185a-359">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f185a-360">若要查看更多詳細資料，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="f185a-360">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="f185a-361">從清單中選取原則，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f185a-361">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="f185a-362">按一下 [**預設原則**]，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f185a-362">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="f185a-363">在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，並執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="f185a-363">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
