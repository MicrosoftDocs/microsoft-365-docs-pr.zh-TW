---
title: 設定 ATP 防網路釣魚原則
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
description: 系統管理員可以瞭解如何建立、修改及刪除組織中可用的高級防網路釣魚原則，以及 Office 365 的高級威脅防護 (Office 365 ATP) 。
ms.openlocfilehash: c08046bdc9e72bc824dc28acdf2443c9071236a0
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333543"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-103">設定 ATP 防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-103">Configure ATP anti-phishing policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3b731-104">ATP 反網路釣魚原則是 [Office 365 Advanced 威脅防護](office-365-atp.md)的一部分。</span><span class="sxs-lookup"><span data-stu-id="3b731-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="3b731-105">ATP 反網路釣魚原則可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他類型的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="3b731-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="3b731-106">如需 Exchange Online Protection 中防網路釣魚原則 (EOP) 和 ATP 反網路釣魚原則之間差異的詳細資訊，請參閱 [反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="3b731-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="3b731-107">系統管理員可以查看、編輯和設定 (，但不會刪除預設的 ATP 反網路釣魚原則) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="3b731-108">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3b731-109">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="3b731-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3b731-110">您可以在 Security & 合規性中心或 Exchange Online PowerShell 中設定 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="3b731-111">如需在 Exchange Online Protection 組織中所提供的防網路釣魚原則中，設定更有限的資訊 (也就是說，Microsoft 365 組織沒有 Office 365 ATP) ，請參閱 [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3b731-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="3b731-112">安全性 & 規範中心與 PowerShell 中的 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="3b731-113">ATP 反網路釣魚原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="3b731-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="3b731-114">**反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。</span><span class="sxs-lookup"><span data-stu-id="3b731-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="3b731-115">**反網路釣魚規則**：指定原則套用至) 以進行反網路釣魚原則的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="3b731-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="3b731-116">當您在安全性 & 合規性中心管理 ATP 反網路釣魚原則時，這兩個元素之間的差異並不明顯：</span><span class="sxs-lookup"><span data-stu-id="3b731-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="3b731-117">當您建立原則時，實際上是建立反網路釣魚規則和相關聯的反網路釣魚原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="3b731-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="3b731-118">當您修改原則時，與名稱、優先順序、啟用或停用及收件者篩選器相關的設定會修改反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="3b731-119">所有其他設定會修改關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="3b731-120">當您移除原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="3b731-121">在 Exchange Online PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="3b731-122">如需詳細資訊，請參閱本主題稍後的 [使用 Exchange Online PowerShell 設定 ATP 反網路釣魚原則](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) 一節。</span><span class="sxs-lookup"><span data-stu-id="3b731-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="3b731-123">每個 Office 365 ATP 組織都有一個內建的 ATP 反網路釣魚原則，名稱為 Office365 AntiPhish 預設值具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="3b731-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="3b731-124">原則會套用至組織中的所有收件者，即使沒有反網路釣魚的規則 (收件者篩選) 與原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="3b731-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="3b731-125">此原則的自訂優先順序值是**最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="3b731-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3b731-126">任何您建立的自訂原則皆具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3b731-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="3b731-127">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3b731-128">若要提高反網路釣魚防護的效能，您可以使用套用至特定使用者或使用者群組的更嚴格設定來建立自訂 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3b731-129">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="3b731-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3b731-130">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="3b731-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3b731-131">若要直接移至 **ATP 反網路釣魚** 頁面，請使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="3b731-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="3b731-132">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3b731-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3b731-133">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="3b731-133">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="3b731-134">若要新增、修改和刪除 ATP 反網路釣魚原則，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="3b731-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3b731-135">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="3b731-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3b731-136">**組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理**。</span><span class="sxs-lookup"><span data-stu-id="3b731-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="3b731-137">若要取得 ATP 反網路釣魚原則的唯讀存取權，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="3b731-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3b731-138">[安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者**。</span><span class="sxs-lookup"><span data-stu-id="3b731-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3b731-139">[線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理**。</span><span class="sxs-lookup"><span data-stu-id="3b731-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="3b731-140">如需有關 ATP 反網路釣魚原則的建議設定，請參閱 [atp 反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="3b731-140">For our recommended settings for ATP anti-phishing policies, see [ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="3b731-141">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="3b731-142">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱 [電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="3b731-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-143">使用安全性 & 合規性中心建立 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="3b731-144">在安全性 & 合規性中心建立自訂 ATP 反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="3b731-145">當您建立 ATP 反網路釣魚原則時，您只能指定原則名稱、描述及識別套用原則的收件者篩選器。</span><span class="sxs-lookup"><span data-stu-id="3b731-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="3b731-146">建立原則之後，您可以修改原則，以變更或審閱預設的反網路釣魚設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="3b731-147">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b731-148">在 [ **反網路釣魚** ] 頁面上，按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-148">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="3b731-149">[ **建立新的反網路釣魚原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="3b731-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="3b731-150">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="3b731-151">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="3b731-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="3b731-152">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="3b731-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="3b731-153">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b731-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3b731-154">在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="3b731-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="3b731-155">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="3b731-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3b731-156">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="3b731-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3b731-157">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="3b731-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="3b731-158">按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-158">Click **Add a condition**.</span></span> <span data-ttu-id="3b731-159">在出現的下拉式清單中，選取 [ **適用于**下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="3b731-159">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="3b731-160">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="3b731-160">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="3b731-161">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="3b731-161">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="3b731-162">**收件者網域為**：指定組織中一或多個已設定公認的網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="3b731-162">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="3b731-163">選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。</span><span class="sxs-lookup"><span data-stu-id="3b731-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="3b731-164">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="3b731-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="3b731-165">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="3b731-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="3b731-166">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="3b731-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="3b731-167">若要移除個別專案， **Remove**請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="3b731-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="3b731-168">若要移除整個條件，請**Remove**按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="3b731-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="3b731-169">若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if**中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="3b731-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="3b731-170">若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="3b731-170">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="3b731-171">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="3b731-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3b731-172">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b731-172">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3b731-173">在 [ **複查您的設定** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="3b731-174">您可以按一下每個設定的 [ **編輯** ] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="3b731-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="3b731-175">當您完成時，按一下 [ **建立這個原則**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-175">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="3b731-176">在出現的確認對話方塊中，按一下 [ **確定** ]。</span><span class="sxs-lookup"><span data-stu-id="3b731-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="3b731-177">在您建立具有這些一般原則設定的 ATP 反網路釣魚原則之後，請使用下一節的指示來設定原則中的保護設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-178">使用安全性 & 規範中心來修改 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="3b731-179">使用下列程式可修改 ATP 反網路釣魚原則：您建立的新原則，或您已自訂的現有原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="3b731-180">如果您還沒有，開啟安全性 & 規範中心，然後移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b731-181">選取您要修改的自訂 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="3b731-182">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="3b731-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3b731-183">隨即會顯示 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="3b731-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="3b731-184">按一下任何區段中的 [ **編輯** ]，即可存取該區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="3b731-185">下列步驟會以區段出現的順序顯示，但不依序 (您可以選取及修改所有順序) 中的區段。</span><span class="sxs-lookup"><span data-stu-id="3b731-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="3b731-186">按一下區段中的 [**編輯**] 之後，可用的設定會以一種方式呈現出來，但是您可以在頁面中以任何順序跳轉，您可以按一下 [**儲存**) ] 任何頁面 (] 或 [**取消**] 或 [**關閉** ![ ](../../media/scc-remove-icon.png) ] [關閉] 圖示，以回到 [**編輯您的 \<name\> 原則**] (頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="3b731-187">**原則設定**：按一下 [ **編輯** ]，修改當您在上一節中 [建立原則](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) 時可用的相同設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-187">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="3b731-188">**名稱**</span><span class="sxs-lookup"><span data-stu-id="3b731-188">**Name**</span></span>
   - <span data-ttu-id="3b731-189">**描述**</span><span class="sxs-lookup"><span data-stu-id="3b731-189">**Description**</span></span>
   - <span data-ttu-id="3b731-190">**套用對象**</span><span class="sxs-lookup"><span data-stu-id="3b731-190">**Applied to**</span></span>
   - <span data-ttu-id="3b731-191">**檢查您的設定**</span><span class="sxs-lookup"><span data-stu-id="3b731-191">**Review your settings**</span></span>

   <span data-ttu-id="3b731-192">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="3b731-193">模擬 **：按一下**[**編輯**] 修改原則中的受保護寄件者與受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="3b731-193">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="3b731-194">這些設定是原則的條件，可識別哄騙寄件者，以在輸入郵件的「寄件者」位址中個別或網域) 尋找 (。</span><span class="sxs-lookup"><span data-stu-id="3b731-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="3b731-195">如需詳細資訊，請參閱 [ATP 反網路釣魚原則中的類比設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="3b731-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="3b731-196">**新增要保護的使用者**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="3b731-196">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="3b731-197">若要開啟它，請將開關滑動至 [ **開啟**]，然後按一下所出現的 [ **新增使用者** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3b731-197">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="3b731-198">在出現的 [ **新增使用者** ] 浮出項目中，設定下列值：</span><span class="sxs-lookup"><span data-stu-id="3b731-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="3b731-199">**電子郵件地址**：</span><span class="sxs-lookup"><span data-stu-id="3b731-199">**Email address**:</span></span>

        - <span data-ttu-id="3b731-200">在方塊中按一下，並在使用者清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="3b731-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="3b731-201">按一下方塊中的 [開始輸入]，以篩選清單並選取使用者。</span><span class="sxs-lookup"><span data-stu-id="3b731-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="3b731-202">若要移除專案，請**Remove**按一下 ![ ](../../media/scc-remove-icon.png) 使用者上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="3b731-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="3b731-203">**名稱**：此值會根據您選取的電子郵件地址來填入，但您可以變更它。</span><span class="sxs-lookup"><span data-stu-id="3b731-203">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="3b731-204">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-204">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="3b731-205">若要編輯現有的專案，請在清單中選取受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="3b731-205">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="3b731-206">**新增要保護的網域**：設定下列其中一項或兩項設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-206">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="3b731-207">**自動包含我擁有的網域**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="3b731-207">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="3b731-208">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="3b731-209">**包含自訂網域**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="3b731-209">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="3b731-210">若要開啟它，請將開關滑動至 [ **開啟**]，然後在 [ **新增網域** ] 方塊中，輸入功能變數名稱 (例如，CONTOSO.COM) ，按 enter，然後視需要重複。</span><span class="sxs-lookup"><span data-stu-id="3b731-210">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

       <span data-ttu-id="3b731-211">**附注**：在安全性 & 規範中心，您最多可以輸入20個網域。</span><span class="sxs-lookup"><span data-stu-id="3b731-211">**Note**: In the Security & Compliance Center, you can enter a maximum of 20 domains.</span></span> <span data-ttu-id="3b731-212">在 Exchange Online PowerShell 中，您最多可以輸入50個網域。</span><span class="sxs-lookup"><span data-stu-id="3b731-212">In Exchange Online PowerShell, you can enter a maximum of 50 domains.</span></span>

   - <span data-ttu-id="3b731-213">**動作**：按一下 [**編輯**]</span><span class="sxs-lookup"><span data-stu-id="3b731-213">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="3b731-214">**如果由模仿的使用者傳送電子郵件**：針對哄騙寄件者是您在 [ **新增使用者以保護**] 指定的其中一個受保護的使用者，設定下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="3b731-214">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="3b731-215">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="3b731-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="3b731-216">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="3b731-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="3b731-217">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="3b731-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="3b731-218">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="3b731-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="3b731-219">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="3b731-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="3b731-220">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="3b731-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="3b731-221">**如果模仿的網域傳送電子郵件**：針對哄騙寄件者位於您在 [ **新增網域**] 中指定的其中一個受保護的網域，設定下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="3b731-221">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="3b731-222">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="3b731-222">**Don't apply any action**</span></span>
     - <span data-ttu-id="3b731-223">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="3b731-223">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="3b731-224">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="3b731-224">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="3b731-225">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="3b731-225">**Quarantine the message**</span></span>
     - <span data-ttu-id="3b731-226">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="3b731-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="3b731-227">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="3b731-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="3b731-228">按一下 [ **開啟模擬安全性秘訣** ]，然後設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="3b731-229">**顯示類比使用者的提示**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="3b731-229">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="3b731-230">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="3b731-231">**顯示類比網域的秘訣**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="3b731-231">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="3b731-232">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="3b731-233">**顯示不尋常字元的提示**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="3b731-233">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="3b731-234">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-234">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="3b731-235">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b731-235">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="3b731-236">**信箱智慧**：</span><span class="sxs-lookup"><span data-stu-id="3b731-236">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="3b731-237">**啟用信箱智慧？**：預設值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="3b731-237">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="3b731-238">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-238">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="3b731-239">**啟用信箱智慧型類比保護？**：此設定只有在 [ **啟用信箱智慧？** 已 **開啟**] 時才可用。</span><span class="sxs-lookup"><span data-stu-id="3b731-239">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="3b731-240">在 **類比的使用者傳送電子郵件時**，您可以指定下列其中一項動作，對信箱智慧失敗的郵件執行 (與受保護的使用者與受保護的網域) 的相同動作：</span><span class="sxs-lookup"><span data-stu-id="3b731-240">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="3b731-241">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="3b731-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="3b731-242">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="3b731-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="3b731-243">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="3b731-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="3b731-244">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="3b731-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="3b731-245">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="3b731-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="3b731-246">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="3b731-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="3b731-247">**新增信任的寄件者和網域**：指定原則的例外狀況：</span><span class="sxs-lookup"><span data-stu-id="3b731-247">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="3b731-248">**受信任的寄件者**：</span><span class="sxs-lookup"><span data-stu-id="3b731-248">**Trusted senders**:</span></span>

       - <span data-ttu-id="3b731-249">在方塊中按一下，並在使用者清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="3b731-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="3b731-250">按一下方塊中的 [開始輸入]，以篩選清單並選取使用者。</span><span class="sxs-lookup"><span data-stu-id="3b731-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="3b731-251">若要移除專案，請**Remove**按一下 ![ ](../../media/scc-remove-icon.png) 使用者上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="3b731-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="3b731-252">**信任的網域**：輸入功能變數名稱 (例如，contoso.com) ，按 enter，然後視需要重複。</span><span class="sxs-lookup"><span data-stu-id="3b731-252">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="3b731-253">請**複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="3b731-253">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="3b731-254">您可以按一下每個區段中的 [ **編輯** ]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="3b731-255">您可以在此頁面**上\*\*\*\*直接切換**下列設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="3b731-256">**受保護的使用者**</span><span class="sxs-lookup"><span data-stu-id="3b731-256">**Protected users**</span></span>
       - <span data-ttu-id="3b731-257">**受保護的網域** \>**包含我擁有的網域**</span><span class="sxs-lookup"><span data-stu-id="3b731-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="3b731-258">**受保護的網域** \>**受保護的網域** (自訂網域) </span><span class="sxs-lookup"><span data-stu-id="3b731-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="3b731-259">**信箱情報**</span><span class="sxs-lookup"><span data-stu-id="3b731-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="3b731-260">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="3b731-261">**哄騙**：按一下 [ **編輯** ] 以開啟或關閉欺騙情報、在 Outlook 中開啟或關閉未驗證寄件者識別，以及設定要套用至封鎖的欺騙寄件者的郵件的動作。</span><span class="sxs-lookup"><span data-stu-id="3b731-261">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="3b731-262">如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="3b731-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="3b731-263">請注意，EOP 中的反網路釣魚原則也提供這些相同設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="3b731-264">**哄騙篩選設定**：預設值為 [ **開啟**]，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="3b731-264">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="3b731-265">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-265">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="3b731-266">如需詳細資訊，請參閱 [在 EOP 中設定欺騙智慧](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="3b731-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="3b731-267">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="3b731-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="3b731-268">如需相關指示，請參閱 [在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="3b731-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="3b731-269">**啟用未經驗證的寄件者功能**：預設值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="3b731-269">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="3b731-270">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-270">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="3b731-271">**動作**：指定對哄騙智慧失敗的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="3b731-271">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="3b731-272">**如果電子郵件是由不允許哄騙您網域的人員所傳送**：</span><span class="sxs-lookup"><span data-stu-id="3b731-272">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="3b731-273">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="3b731-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="3b731-274">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="3b731-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="3b731-275">請**複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="3b731-275">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="3b731-276">您可以按一下每個區段中的 [ **編輯** ]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="3b731-277">您可以在此頁面**上\*\*\*\*直接切換**下列設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="3b731-278">**啟用 antispoofing 保護**</span><span class="sxs-lookup"><span data-stu-id="3b731-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="3b731-279">**啟用未經驗證的寄件者功能**</span><span class="sxs-lookup"><span data-stu-id="3b731-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="3b731-280">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="3b731-281">**高級設定**：按一下 [ **編輯** ] 以設定高級網路釣魚閾值。</span><span class="sxs-lookup"><span data-stu-id="3b731-281">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="3b731-282">如需詳細資訊，請參閱 [ATP 反網路釣魚原則中的高級網路釣魚閥](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)值。</span><span class="sxs-lookup"><span data-stu-id="3b731-282">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="3b731-283">**高級網路釣魚閥**值：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="3b731-283">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="3b731-284">**1-Standard** (此為預設值。 ) </span><span class="sxs-lookup"><span data-stu-id="3b731-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="3b731-285">**2-嚴格**</span><span class="sxs-lookup"><span data-stu-id="3b731-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="3b731-286">**3-更嚴格**</span><span class="sxs-lookup"><span data-stu-id="3b731-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="3b731-287">**4-最積極**</span><span class="sxs-lookup"><span data-stu-id="3b731-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="3b731-288">**檢查您的設定**：按一下 [ **編輯** ]，可跳至 [ **高級網路釣魚閥** 值] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-288">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="3b731-289">當您完成時，按一下 [ **儲存** ] 任何一頁。</span><span class="sxs-lookup"><span data-stu-id="3b731-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="3b731-290">回到 [**編輯您的原則 \<Name\> \*\* ] 頁面上，複查您的設定，然後按一下 [**關閉\*\*]。</span><span class="sxs-lookup"><span data-stu-id="3b731-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="3b731-291">使用安全性 & 合規性中心，修改預設的 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-291">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="3b731-292">預設的 ATP 反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會出現在原則清單中。</span><span class="sxs-lookup"><span data-stu-id="3b731-292">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="3b731-293">若要修改預設的 ATP 反網路釣魚原則，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3b731-293">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="3b731-294">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b731-295">在 [ **反網路釣魚** ] 頁面上，按一下 [ **預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-295">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="3b731-296">隨即會顯示 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3b731-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="3b731-297">下列各節可供使用，其中包含 [修改自訂原則](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)時的相同設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="3b731-298">**模擬**</span><span class="sxs-lookup"><span data-stu-id="3b731-298">**Impersonation**</span></span>
   - <span data-ttu-id="3b731-299">**惡搞**</span><span class="sxs-lookup"><span data-stu-id="3b731-299">**Spoof**</span></span>
   - <span data-ttu-id="3b731-300">**進階設定**</span><span class="sxs-lookup"><span data-stu-id="3b731-300">**Advanced settings**</span></span>

   <span data-ttu-id="3b731-301">當您修改預設原則時，無法使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="3b731-302">您可以看到 [ **原則設定** ] 區段和 [值]，但沒有 **編輯** 連結，所以您無法修改設定 (原則名稱、描述，以及原則套用至所有收件者的設定 (套用至所有收件者) # A3。</span><span class="sxs-lookup"><span data-stu-id="3b731-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="3b731-303">您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="3b731-304">您無法變更預設原則的優先順序 (它永遠套用於最後) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="3b731-305">在 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面上，複查您的設定，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b731-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-306">啟用或停用自訂 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-306">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="3b731-307">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b731-308">請注意 [ **狀態** ] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="3b731-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="3b731-309">將 [切換] 滑動至 [ **關閉** ] 以停用原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="3b731-310">將切換滑動至 **開啟** 以啟用原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="3b731-311">您無法停用預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-312">設定自訂 ATP 反網路釣魚原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="3b731-312">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="3b731-313">根據預設，ATP 反網路釣魚原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-313">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3b731-314">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="3b731-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3b731-315">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="3b731-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="3b731-316">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="3b731-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="3b731-317">自訂 ATP 反網路釣魚原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-317">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3b731-318">預設的反網路釣魚原則（名為 Office365 AntiPhish Default）的自訂優先順序值是 **最低**的，您無法變更它。</span><span class="sxs-lookup"><span data-stu-id="3b731-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="3b731-319">**附注**：在 [安全性 & 規範中心] 中，您可以在建立後，只變更 ATP 反網路釣魚原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3b731-319">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="3b731-320">在 PowerShell 中，您可以在建立反網路釣魚規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3b731-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="3b731-321">若要變更原則的優先順序，您可以按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 中的原則 (您無法直接修改安全性 & 規範中心) 中的 **優先順序** 號碼。</span><span class="sxs-lookup"><span data-stu-id="3b731-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="3b731-322">如果您有多個原則，變更原則的優先順序只會有意義。</span><span class="sxs-lookup"><span data-stu-id="3b731-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="3b731-323">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b731-324">選取您要修改的原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="3b731-325">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="3b731-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3b731-326">隨即會顯示 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="3b731-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="3b731-327">具有 **Priority** 值 **0** 的自訂 ATP 反網路釣魚原則，只有「 **降低優先順序** 」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="3b731-327">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="3b731-328">具有最低 **優先順序** 值的自訂 ATP 反網路釣魚原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="3b731-328">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="3b731-329">如果您有三個或多個自訂的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3b731-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="3b731-330">按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。</span><span class="sxs-lookup"><span data-stu-id="3b731-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="3b731-331">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b731-331">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-332">使用安全性 & 合規性中心來查看 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-332">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="3b731-333">在安全性 & 規範中心，然後移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b731-334">請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="3b731-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="3b731-335">選取您要查看的自訂 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-335">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="3b731-336">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="3b731-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="3b731-337">按一下 [ **預設原則** ] 以查看預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="3b731-338">此時會出現 [\*\*編輯您的原則 \<name\> \*\* ] 快顯視窗，您可以在其中查看設定和值。</span><span class="sxs-lookup"><span data-stu-id="3b731-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-339">使用安全性 & 規範中心移除 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-339">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="3b731-340">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="3b731-341">選取您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="3b731-342">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="3b731-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="3b731-343">在出現的 [**編輯 \<name\> 您的原則**] 浮出視窗中，按一下 [**刪除原則**]，然後在出現的警告對話方塊中按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="3b731-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="3b731-344">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="3b731-345">使用 Exchange Online PowerShell 設定 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-345">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="3b731-346">如先前所述，ATP 反垃圾郵件原則是由反網路釣魚原則和反網路釣魚規則所組成。</span><span class="sxs-lookup"><span data-stu-id="3b731-346">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="3b731-347">在 Exchange Online PowerShell 中，反網路釣魚原則和反網路釣魚規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="3b731-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="3b731-348">您可以使用\*\* \* -AntiPhishPolicy\*\* Cmdlet 來管理反網路釣魚原則，並使用\*\* \* -AntiPhishRule\*\* Cmdlet 來管理反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="3b731-349">在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="3b731-350">在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="3b731-351">當您從 PowerShell 中移除反網路釣魚原則時，不會自動移除對應的反網路釣魚規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="3b731-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="3b731-352">使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="3b731-353">在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="3b731-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3b731-354">建立反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="3b731-355">建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="3b731-356">**附註**：</span><span class="sxs-lookup"><span data-stu-id="3b731-356">**Notes**:</span></span>

- <span data-ttu-id="3b731-357">您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="3b731-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="3b731-358">反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="3b731-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="3b731-359">您可以在 PowerShell 中為安全性 & 相容性中心以外的新反網路釣魚原則設定下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="3b731-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="3b731-360">_在_ `$false` **AntiPhishRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="3b731-360">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="3b731-361">在_Priority_ _\<Number\>_ **AntiPhishRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3b731-361">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="3b731-362">在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="3b731-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="3b731-363">步驟1：使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="3b731-364">若要建立反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="3b731-365">此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="3b731-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="3b731-366"> (未使用 _enabled_ 參數時，也會啟用該原則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="3b731-367">描述為：「調研部門原則」。</span><span class="sxs-lookup"><span data-stu-id="3b731-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="3b731-368">針對所有公認的網域及目標網域的 fabrikam.com 保護，啟用組織網域保護。</span><span class="sxs-lookup"><span data-stu-id="3b731-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="3b731-369">指定 Mai Fujito (mfujito@fabrikam.com) 做為使用者以防範模擬。</span><span class="sxs-lookup"><span data-stu-id="3b731-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="3b731-370">啟用信箱智慧。</span><span class="sxs-lookup"><span data-stu-id="3b731-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="3b731-371">啟用信箱智慧保護，並指定隔離動作。</span><span class="sxs-lookup"><span data-stu-id="3b731-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="3b731-372">啟用安全提示。</span><span class="sxs-lookup"><span data-stu-id="3b731-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="3b731-373">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3b731-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="3b731-374">步驟2：使用 PowerShell 建立反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="3b731-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="3b731-375">若要建立反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3b731-376">在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：</span><span class="sxs-lookup"><span data-stu-id="3b731-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="3b731-377">此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="3b731-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="3b731-378">此規則適用於名為 Research Department 之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3b731-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="3b731-379">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3b731-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="3b731-380">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="3b731-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="3b731-381">使用 PowerShell 來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="3b731-382">若要查看現有的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3b731-383">此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="3b731-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="3b731-384">此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="3b731-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="3b731-385">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3b731-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="3b731-386">使用 PowerShell 來查看反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="3b731-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="3b731-387">若要查看現有的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3b731-388">此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="3b731-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="3b731-389">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3b731-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="3b731-390">此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="3b731-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="3b731-391">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="3b731-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="3b731-392">使用 PowerShell 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="3b731-393">除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，當您在本主題稍早的 [步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy) 區段中所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="3b731-394">_MakeDefault_參數會將指定的原則轉換成預設原則 (套用至每個使用者，永遠**最低**的優先順序，而且您無法刪除只有當您在 PowerShell 中修改反網路釣魚原則時，才可使用此參數) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="3b731-395">您無法重新命名反網路釣魚原則 (**AntiPhishPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3b731-396">當您在安全性 & 合規性中心重新命名防網路釣魚原則時，您只是重新命名反網路釣魚 _規則_。</span><span class="sxs-lookup"><span data-stu-id="3b731-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="3b731-397">若要修改反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3b731-398">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3b731-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="3b731-399">使用 PowerShell 修改反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="3b731-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="3b731-400">在 PowerShell 中修改反網路釣魚規則時，唯一無法使用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3b731-401">若要啟用或停用現有的反網路釣魚規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="3b731-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="3b731-402">否則，當您在 PowerShell 中修改反網路釣魚規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="3b731-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="3b731-403">當您建立規則時，如本主題稍早的 [步驟2：使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule) 一節所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="3b731-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="3b731-404">若要修改反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3b731-405">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="3b731-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="3b731-406">使用 PowerShell 來啟用或停用反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="3b731-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="3b731-407">啟用或停用 PowerShell 中的反網路釣魚規則，可啟用或停用反網路釣魚規則和指派的反網路釣魚原則)  (的整個反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="3b731-408">您無法啟用或停用預設的反網路釣魚原則 (它永遠套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="3b731-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="3b731-409">若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="3b731-410">本範例會停用名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3b731-411">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3b731-412">如需詳細的語法及參數資訊，請參閱 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="3b731-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="3b731-413">使用 PowerShell 設定反網路釣魚規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="3b731-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="3b731-414">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="3b731-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3b731-415">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="3b731-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3b731-416">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="3b731-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3b731-417">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="3b731-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3b731-418">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="3b731-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3b731-419">若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3b731-420">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="3b731-420">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="3b731-421">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="3b731-421">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3b731-422">**附註**：</span><span class="sxs-lookup"><span data-stu-id="3b731-422">**Notes**:</span></span>

- <span data-ttu-id="3b731-423">若要在建立新規則時設定其優先順序，請改用**AntiPhishRule** Cmdlet 上的_priority_參數。</span><span class="sxs-lookup"><span data-stu-id="3b731-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="3b731-424">預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序**值。**</span><span class="sxs-lookup"><span data-stu-id="3b731-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="3b731-425">使用 PowerShell 移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="3b731-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="3b731-426">當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="3b731-427">若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3b731-428">此範例會移除名為「行銷部門」的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3b731-429">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="3b731-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="3b731-430">使用 PowerShell 移除反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="3b731-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="3b731-431">當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="3b731-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="3b731-432">若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="3b731-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="3b731-433">此範例會移除名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="3b731-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3b731-434">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="3b731-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3b731-435">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="3b731-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="3b731-436">若要確認您是否已成功設定 ATP 反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="3b731-436">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="3b731-437">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="3b731-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="3b731-438">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="3b731-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="3b731-439">若要查看更多詳細資料，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="3b731-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="3b731-440">從清單中選取原則，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3b731-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="3b731-441">按一下 [ **預設原則** ]，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3b731-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="3b731-442">在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，並執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="3b731-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
