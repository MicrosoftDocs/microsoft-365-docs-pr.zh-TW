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
ms.openlocfilehash: bd7686c55e05d4197d43799008596db82375222e
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616695"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="e1ebf-103">在 EOP 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="e1ebf-104">在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，有預設的反網路釣魚原則，其中包含預設啟用的有限的反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="e1ebf-105">如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="e1ebf-106">系統管理員可以查看、編輯和設定（但不能刪除）預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="e1ebf-107">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="e1ebf-108">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="e1ebf-109">具有 Exchange Online 信箱的組織可在安全性 & 合規性中心或 Exchange Online PowerShell 中設定反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="e1ebf-110">獨立 EOP 組織只能使用安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="e1ebf-111">如需建立及修改 Office 365 Advanced 威脅防護（Office 365 ATP）中可用的更高級 ATP 反網路釣魚原則的詳細資訊，請參閱[設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="e1ebf-112">安全性 & 規範中心與 PowerShell 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="e1ebf-113">反網路釣魚原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="e1ebf-114">**反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="e1ebf-115">**反網路釣魚規則**：為反網路釣魚原則指定優先順序和收件者篩選器（該原則套用於誰）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="e1ebf-116">當您在安全性 & 合規性中心管理反網路釣魚原則時，這兩個元素之間的差異並不明顯。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e1ebf-117">當您在安全性 & 合規性中心建立反網路釣魚原則時，實際上您實際上是建立反網路釣魚規則和相關聯的反網路釣魚原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="e1ebf-118">當您在安全性 & 規範中心修改反網路釣魚原則時，與名稱、優先順序、已啟用或已停用的設定或收件者篩選器相關的設定會修改反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="e1ebf-119">所有其他設定會修改關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="e1ebf-120">當您從安全性 & 合規性中心移除防網路釣魚原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="e1ebf-121">在 Exchange Online PowerShell 中，反網路釣魚原則和反網路釣魚規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="e1ebf-122">您可以使用\*\* \* -AntiPhishPolicy\*\* Cmdlet 來管理反網路釣魚原則，並使用\*\* \* -AntiPhishRule\*\* Cmdlet 來管理反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="e1ebf-123">在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="e1ebf-124">在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="e1ebf-125">預設 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="e1ebf-126">每個組織都有一個名為 Office365 AntiPhish 的內建反網路釣魚原則，其具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="e1ebf-127">名稱為 Office365 AntiPhish 的原則會套用至組織中的所有收件者，即使沒有與原則相關聯的反網路釣魚規則（收件者篩選器）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="e1ebf-128">名為 Office365 AntiPhish 的原則預設具有您無法修改的自訂**優先順序值（** 原則永遠會最後套用）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="e1ebf-129">您建立的任何自訂原則的優先順序都會高於名為 Office365 AntiPhish Default 的原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="e1ebf-130">名為 Office365 AntiPhish 的原則預設為預設原則（ **IsDefault**屬性具有值 `True` ），而且您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="e1ebf-131">若要提高反網路釣魚防護的效能，您可以建立自訂的反網路釣魚原則，其套用至特定使用者或使用者群組的更嚴格設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e1ebf-132">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="e1ebf-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e1ebf-133">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e1ebf-134">若要直接移至 [**反網路釣魚**] 頁面，請使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="e1ebf-135">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="e1ebf-136">您無法管理獨立 EOP PowerShell 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="e1ebf-137">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="e1ebf-138">若要新增、修改和刪除反網路釣魚原則，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="e1ebf-139">若要獲得反網路釣魚原則的唯讀存取權，您必須是**Security Reader**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="e1ebf-140">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e1ebf-141">若要能夠在獨立 EOP 中建立及修改反垃圾郵件原則，您需要針對租使用者執行需要_分解_的專案。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-141">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="e1ebf-142">例如，在 EAC 中，您可以移至 [**許可權**] 索引標籤、選取現有的角色群組、按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 及 [移除角色] （最終將會新增回）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-142">For example, in the EAC, you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="e1ebf-143">如果您的租使用者從未 hydrated，您會看到一個名為「**更新組織」設定**的對話方塊，其進度列應該會順利完成。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-143">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="e1ebf-144">如需分解的詳細資訊，請參閱[Enable-OrganizationCustomization 指令程式](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization)（不可在獨立 EOP PowerShell 或安全性 & 規範中心）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-144">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="e1ebf-145">如需有關反網路釣魚原則的建議設定，請參閱[EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-145">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="e1ebf-146">允許套用更新的原則最多30分鐘。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-146">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="e1ebf-147">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱[電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-147">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="e1ebf-148">使用安全性 & 規範中心建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-148">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="e1ebf-149">在安全性 & 合規性中心建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-149">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="e1ebf-150">當您建立反網路釣魚原則時，您只能指定原則名稱、描述及識別套用原則的收件者篩選器。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-150">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="e1ebf-151">建立原則之後，您可以修改原則，以變更或審閱預設的反網路釣魚設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-151">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="e1ebf-152">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-152">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e1ebf-153">在 [**反網路釣魚**] 頁面上，按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-153">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="e1ebf-154">[**建立新的反網路釣魚原則**] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-154">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="e1ebf-155">在 [**命名您的原則**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-155">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="e1ebf-156">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="e1ebf-157">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-157">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e1ebf-158">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-158">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e1ebf-159">在出現的 [套用**至**] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-159">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="e1ebf-160">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-160">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="e1ebf-161">相同狀況或例外狀況或邏輯的多個值（例如 _\<recipient1\>_ or _\<recipient2\>_ ）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-161">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e1ebf-162">使用和邏輯不同的條件或例外狀況（例如 _\<recipient1\>_ 和 _\<member of group 1\>_ ）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-162">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="e1ebf-163">按一下 [**新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-163">Click **Add a condition**.</span></span> <span data-ttu-id="e1ebf-164">在出現的下拉式清單中，選取 [**適用于**下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-164">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="e1ebf-165">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-165">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e1ebf-166">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-166">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="e1ebf-167">**收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-167">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="e1ebf-168">選取條件後，會出現對應的下拉式清單，其中有**其中**一個方塊。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-168">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="e1ebf-169">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-169">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="e1ebf-170">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-170">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="e1ebf-171">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-171">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="e1ebf-172">若要移除個別專案， **Remove**請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-172">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="e1ebf-173">若要移除整個條件，請**Remove**按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-173">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="e1ebf-174">若要新增其他條件，請按一下 [**新增條件**]，然後選取 [套用**于 if**中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-174">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="e1ebf-175">若要新增例外狀況，請按一下 [**新增條件**]，然後選取 [**除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-175">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="e1ebf-176">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-176">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e1ebf-177">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-177">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e1ebf-178">在 [**複查您的設定**] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-178">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="e1ebf-179">您可以按一下每個設定的 [**編輯**] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-179">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="e1ebf-180">當您完成時，按一下 [**建立這個原則**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-180">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="e1ebf-181">在出現的確認對話方塊中，按一下 [**確定**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-181">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="e1ebf-182">使用這些一般原則設定建立反網路釣魚原則之後，請使用下一節中的指示來設定原則中的保護設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-182">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="e1ebf-183">使用安全性 & 規範中心來修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-183">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="e1ebf-184">請使用下列程式修改反網路釣魚原則：您建立的新原則，或您已自訂的現有原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-184">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="e1ebf-185">如果您還沒有開啟安全性 & 規範中心，請移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-185">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e1ebf-186">選取您要修改的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-186">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="e1ebf-187">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-187">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e1ebf-188">隨即會顯示 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-188">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="e1ebf-189">按一下任何區段中的 [**編輯**]，即可存取該區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-189">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="e1ebf-190">下列步驟會以區段出現的順序顯示，但不是連續的（您可以選取及修改所有順序的區段）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-190">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="e1ebf-191">按一下區段中的 [**編輯**] 之後，可用的設定會以一種方式呈現出來，但是您可以在頁面中以任何順序跳離，也可以按一下任何頁面上的 [**儲存**] （或 [**取消**] 或 [**關閉** ![ ] 關閉圖示，以 ](../../media/scc-remove-icon.png) 回到 [\*\*編輯您的原則 \<name\> \*\* ] 頁面）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-191">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="e1ebf-192">**原則設定**：按一下 [**編輯**]，修改當您在上一節中[建立原則](#use-the-security--compliance-center-to-create-anti-phishing-policies)時可用的相同設定：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-192">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="e1ebf-193">**Name**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-193">**Name**</span></span>
   - <span data-ttu-id="e1ebf-194">**描述**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-194">**Description**</span></span>
   - <span data-ttu-id="e1ebf-195">**套用對象**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-195">**Applied to**</span></span>
   - <span data-ttu-id="e1ebf-196">**檢查您的設定**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-196">**Review your settings**</span></span>

   <span data-ttu-id="e1ebf-197">完成後，按一下 [**儲存**] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-197">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="e1ebf-198">**哄騙**：按一下 [**編輯**] 以開啟或關閉欺騙情報、在 Outlook 中開啟或關閉未驗證寄件者識別，以及設定要套用至封鎖的欺騙寄件者的郵件的動作。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-198">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="e1ebf-199">如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-199">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="e1ebf-200">請注意，ATP 反網路釣魚原則中也提供這些相同設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-200">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="e1ebf-201">**哄騙篩選設定**：預設值為 [**開啟**]，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-201">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="e1ebf-202">若要將它關閉，請將開關滑動至 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-202">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="e1ebf-203">如需詳細資訊，請參閱[在 EOP 中設定欺騙智慧](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-203">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="e1ebf-204">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-204">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="e1ebf-205">如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-205">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="e1ebf-206">**啟用未經驗證的寄件者功能**：預設值為**On**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-206">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="e1ebf-207">若要將它關閉，請將開關滑動至 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-207">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="e1ebf-208">**動作**：指定對哄騙智慧失敗的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-208">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="e1ebf-209">**如果電子郵件是由不允許哄騙您網域的人員所傳送**：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-209">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="e1ebf-210">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-210">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="e1ebf-211">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-211">**Quarantine the message**</span></span>

   - <span data-ttu-id="e1ebf-212">請**複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-212">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="e1ebf-213">您可以按一下每個區段中的 [**編輯**]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-213">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="e1ebf-214">您可以在此頁面**上\*\*\*\*直接切換**下列設定：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-214">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="e1ebf-215">**啟用 antispoofing 保護**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-215">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="e1ebf-216">**啟用未經驗證的寄件者功能**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-216">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="e1ebf-217">完成後，按一下 [**儲存**] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-217">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="e1ebf-218">回到 [**編輯您的原則 \<Name\> \*\* ] 頁面上，複查您的設定，然後按一下 [**關閉\*\*]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-218">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="e1ebf-219">使用安全性 & 合規性中心來修改預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-219">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="e1ebf-220">預設的反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會顯示在原則清單中。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-220">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="e1ebf-221">若要修改預設的反網路釣魚原則，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-221">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="e1ebf-222">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e1ebf-223">在 [**反網路釣魚**] 頁面上，按一下 [**預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-223">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="e1ebf-224">隨即會顯示 [**編輯您的原則 Office365 AntiPhish 預設**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-224">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="e1ebf-225">下列各節可供使用，其中包含[修改自訂原則](#use-the-security--compliance-center-to-modify-anti-phishing-policies)時的相同設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-225">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="e1ebf-226">**模擬**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-226">**Impersonation**</span></span>
   - <span data-ttu-id="e1ebf-227">**惡搞**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-227">**Spoof**</span></span>
   - <span data-ttu-id="e1ebf-228">**進階設定**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-228">**Advanced settings**</span></span>

   <span data-ttu-id="e1ebf-229">當您修改預設原則時，無法使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-229">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="e1ebf-230">您可以看到 [**原則設定**] 區段和 [值]，但沒有**編輯**連結，所以您無法修改設定（原則名稱、描述及原則套用至的人員）（此原則會套用至所有收件者）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-230">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="e1ebf-231">您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-231">You can't delete the default policy.</span></span>
   - <span data-ttu-id="e1ebf-232">您無法變更預設原則的優先順序（預設原則為 [永不最後套用]）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-232">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="e1ebf-233">在 [**編輯您的原則 Office365 AntiPhish 預設**] 頁面上，複查您的設定，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-233">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="e1ebf-234">啟用或停用自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-234">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="e1ebf-235">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-235">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e1ebf-236">請注意 [**狀態**] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-236">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="e1ebf-237">將 [切換] 滑動至 [**關閉**] 以停用原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-237">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="e1ebf-238">將切換滑動至**開啟**以啟用原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-238">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="e1ebf-239">您無法停用預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-239">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="e1ebf-240">設定自訂的反網路釣魚原則優先順序</span><span class="sxs-lookup"><span data-stu-id="e1ebf-240">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="e1ebf-241">根據預設，反網路釣魚原則的優先順序會根據建立的順序而定（較舊的原則的優先順序較舊）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-241">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="e1ebf-242">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-242">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e1ebf-243">不會有兩個原則的優先順序相同。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-243">No two policies can have the same priority.</span></span>

<span data-ttu-id="e1ebf-244">自訂的反網路釣魚原則會以處理的順序顯示（第一個原則的**Priority**值為0）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="e1ebf-245">預設的反網路釣魚原則（名為 Office365 AntiPhish Default）的自訂優先順序值是**最低**的，您無法變更它。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="e1ebf-246">**附注**：在 [安全性 & 規範中心] 中，您只能在建立反網路釣魚原則之後變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="e1ebf-247">在 PowerShell 中，您可以在建立反網路釣魚規則（可能會影響現有規則的優先順序）時，覆寫預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="e1ebf-248">若要變更原則的優先順序，請按一下 [**增加優先順序**] 或 [**降低**優先順序] 中原則的屬性（您無法直接修改安全性 & 規範中心中的**優先順序**號碼）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="e1ebf-249">如果您有多個原則，變更原則的優先順序只會有意義。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="e1ebf-250">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="e1ebf-251">選取您要修改的原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="e1ebf-252">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e1ebf-253">隨即會顯示 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="e1ebf-254">**優先順序**值為**0**的自訂反網路釣魚原則只有「**降低優先順序**」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="e1ebf-255">具有最低**優先順序**值的自訂反網路釣魚原則（例如， **3**）只有 [**增加優先順序**] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="e1ebf-256">如果您有三個或多個自訂的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [**增加優先順序**] 和 [**降低優先順序**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="e1ebf-257">按一下 [**增加優先順序**] 或 [**降低優先順序**] 以變更 [**優先順序**] 值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="e1ebf-258">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="e1ebf-259">使用安全性 & 規範中心來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="e1ebf-260">在安全性 & 規範中心，然後移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e1ebf-261">請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="e1ebf-262">選取您要查看的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="e1ebf-263">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="e1ebf-264">按一下 [**預設原則**] 以查看預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="e1ebf-265">此時會出現 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗，您可以在其中查看設定和值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="e1ebf-266">使用安全性 & 規範中心移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="e1ebf-267">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e1ebf-268">選取您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="e1ebf-269">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e1ebf-270">在出現的 [**編輯 \<name\> 您的原則**] 浮出視窗中，按一下 [**刪除原則**]，然後在出現的警告對話方塊中按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="e1ebf-271">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="e1ebf-272">使用 Exchange Online PowerShell 設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="e1ebf-273">在獨立 EOP 組織中無法使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-273">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="e1ebf-274">使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-274">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="e1ebf-275">在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-275">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e1ebf-276">建立反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-276">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="e1ebf-277">建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-277">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="e1ebf-278">**附註**：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-278">**Notes**:</span></span>

- <span data-ttu-id="e1ebf-279">您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-279">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="e1ebf-280">反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-280">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="e1ebf-281">您可以在 PowerShell 中為安全性 & 相容性中心以外的新反網路釣魚原則設定下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-281">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="e1ebf-282">建立新原則為停用（_ _ `$false` 在**AntiPhishRule** Cmdlet 上啟用）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-282">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="e1ebf-283">_Priority_ _\<Number\>_ 在**AntiPhishRule** Cmdlet 上建立（優先順序）時設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-283">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="e1ebf-284">在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-284">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="e1ebf-285">步驟1：使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-285">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="e1ebf-286">若要建立反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-286">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="e1ebf-287">此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-287">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="e1ebf-288">原則已啟用（未使用_enabled_參數，預設值為 `$true` ）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-288">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="e1ebf-289">描述為：「調研部門原則」。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-289">The description is: Research department policy.</span></span>
- <span data-ttu-id="e1ebf-290">將哄騙的預設動作變更為「隔離」。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-290">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="e1ebf-291">如需詳細的語法及參數資訊，請參閱[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-291">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="e1ebf-292">步驟2：使用 PowerShell 建立反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-292">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="e1ebf-293">若要建立反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-293">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="e1ebf-294">在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-294">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="e1ebf-295">此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-295">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="e1ebf-296">此規則適用於名為 Research Department 之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-296">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="e1ebf-297">因為我們沒有使用_priority_參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-297">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="e1ebf-298">如需詳細的語法及參數資訊，請參閱[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-298">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="e1ebf-299">使用 PowerShell 來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-299">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="e1ebf-300">若要查看現有的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-300">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e1ebf-301">此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-301">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="e1ebf-302">此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-302">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="e1ebf-303">如需詳細的語法及參數資訊，請參閱[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-303">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="e1ebf-304">使用 PowerShell 來查看反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-304">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="e1ebf-305">若要查看現有的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-305">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e1ebf-306">此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-306">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="e1ebf-307">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-307">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="e1ebf-308">此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-308">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="e1ebf-309">如需詳細的語法及參數資訊，請參閱[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-309">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="e1ebf-310">使用 PowerShell 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-310">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="e1ebf-311">除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，當您在本主題稍早的[步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy)區段中所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-311">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="e1ebf-312">在 PowerShell 中修改反網路釣魚原則時，可將指定的原則變成預設原則（適用于所有人、永不**最低**的優先順序，而且無法刪除）的_MakeDefault_參數。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-312">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="e1ebf-313">您無法重新命名反網路釣魚原則（ **AntiPhishPolicy** Cmdlet 沒有_Name_參數）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-313">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e1ebf-314">當您在安全性 & 合規性中心重新命名防網路釣魚原則時，您只是重新命名反網路釣魚_規則_。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-314">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="e1ebf-315">若要修改反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-315">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e1ebf-316">如需詳細的語法及參數資訊，請參閱[Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-316">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="e1ebf-317">使用 PowerShell 修改反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-317">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="e1ebf-318">在 PowerShell 中修改反網路釣魚規則時，唯一無法使用的設定是_Enabled_參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-318">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e1ebf-319">若要啟用或停用現有的反網路釣魚規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-319">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="e1ebf-320">否則，當您在 PowerShell 中修改反網路釣魚規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-320">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="e1ebf-321">當您建立規則時，如本主題稍早的[步驟2：使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule)一節所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-321">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="e1ebf-322">若要修改反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-322">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e1ebf-323">如需詳細的語法及參數資訊，請參閱[Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-323">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="e1ebf-324">使用 PowerShell 來啟用或停用反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-324">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="e1ebf-325">啟用或停用 PowerShell 中的反網路釣魚規則可啟用或停用整個反網路釣魚原則（反網路釣魚規則和指派的反網路釣魚原則）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-325">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="e1ebf-326">您無法啟用或停用預設的反網路釣魚原則（永遠套用到所有收件者）。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-326">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="e1ebf-327">若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-327">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="e1ebf-328">本範例會停用名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-328">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e1ebf-329">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-329">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e1ebf-330">如需詳細的語法及參數資訊，請參閱[Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule)和[Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-330">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="e1ebf-331">使用 PowerShell 設定反網路釣魚規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="e1ebf-331">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="e1ebf-332">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-332">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e1ebf-333">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-333">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e1ebf-334">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-334">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e1ebf-335">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-335">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e1ebf-336">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-336">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e1ebf-337">若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-337">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e1ebf-338">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-338">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="e1ebf-339">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-339">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="e1ebf-340">**附註**：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-340">**Notes**:</span></span>

- <span data-ttu-id="e1ebf-341">若要在建立新規則時設定其優先順序，請改用**AntiPhishRule** Cmdlet 上的_priority_參數。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-341">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="e1ebf-342">預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序**值。**</span><span class="sxs-lookup"><span data-stu-id="e1ebf-342">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="e1ebf-343">使用 PowerShell 移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-343">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="e1ebf-344">當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-344">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="e1ebf-345">若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-345">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e1ebf-346">此範例會移除名為「行銷部門」的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-346">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e1ebf-347">如需詳細的語法及參數資訊，請參閱[Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-347">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="e1ebf-348">使用 PowerShell 移除反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="e1ebf-348">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="e1ebf-349">當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-349">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="e1ebf-350">若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-350">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="e1ebf-351">此範例會移除名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-351">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e1ebf-352">如需詳細的語法及參數資訊，請參閱[Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-352">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e1ebf-353">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e1ebf-353">How do you know these procedures worked?</span></span>

<span data-ttu-id="e1ebf-354">若要確認您是否已成功設定 ATP 反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-354">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="e1ebf-355">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-355">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="e1ebf-356">請確認原則的清單、其**狀態**值，以及其**優先順序**值。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-356">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e1ebf-357">若要查看更多詳細資料，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-357">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="e1ebf-358">從清單中選取原則，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-358">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="e1ebf-359">按一下 [**預設原則**]，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e1ebf-359">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="e1ebf-360">在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，並執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="e1ebf-360">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
