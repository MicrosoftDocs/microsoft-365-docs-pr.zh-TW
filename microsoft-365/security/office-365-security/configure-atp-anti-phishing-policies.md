---
title: 在 Microsoft Defender for Office 365 中設定反網路釣魚原則
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
description: 系統管理員可以瞭解如何建立、修改及刪除使用 Microsoft Defender for Office 365 的組織中可用的高級反網路釣魚原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2985766cf3388382dbe1d2217843504b2bfd1a1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906585"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-103">在 Microsoft Defender for Office 365 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0289a-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="0289a-104">**Applies to**</span></span>
- [<span data-ttu-id="0289a-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="0289a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0289a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0289a-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="0289a-107">[Microsoft Defender For Office 365](office-365-atp.md)中的反網路釣魚原則可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他類型的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="0289a-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="0289a-108">如需 Exchange Online Protection 中防網路釣魚原則 (EOP) 和 Microsoft Defender for Office 365 中的反網路釣魚原則之間差異的詳細資訊，請參閱 [反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0289a-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="0289a-109">系統管理員可以查看、編輯和設定 (，但不會刪除預設的反網路釣魚原則) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="0289a-110">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0289a-111">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="0289a-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0289a-112">您可以在 Security & 合規性中心或 Exchange Online PowerShell 中設定反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="0289a-113">如需在 Exchange Online Protection 組織中所提供的防網路釣魚原則中，設定更有限的資訊 (也就是說，組織沒有 Microsoft Defender for Office 365) ，請參閱 [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="0289a-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="0289a-114">反網路釣魚原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="0289a-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="0289a-115">**反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。</span><span class="sxs-lookup"><span data-stu-id="0289a-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="0289a-116">**反網路釣魚規則**：指定原則套用至) 以進行反網路釣魚原則的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="0289a-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0289a-117">當您在安全性 & 合規性中心管理反網路釣魚原則時，這兩個元素之間的差異並不明顯。</span><span class="sxs-lookup"><span data-stu-id="0289a-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0289a-118">當您建立原則時，實際上是建立反網路釣魚規則和相關聯的反網路釣魚原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="0289a-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="0289a-119">當您修改原則時，與名稱、優先順序、啟用或停用及收件者篩選器相關的設定會修改反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0289a-120">所有其他設定會修改關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="0289a-121">當您移除原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0289a-122">在 Exchange Online PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="0289a-123">如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 設定 Microsoft Defender For Office 365 中的反網路釣魚原則](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) 一節。</span><span class="sxs-lookup"><span data-stu-id="0289a-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="0289a-124">每個 Microsoft Defender for Office 365 組織都有一個名為 Office365 AntiPhish 的內建反網路釣魚原則，其具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="0289a-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0289a-125">原則會套用至組織中的所有收件者，即使沒有反網路釣魚的規則 (收件者篩選) 與原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="0289a-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="0289a-126">此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="0289a-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0289a-127">任何您建立的自訂原則皆具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="0289a-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="0289a-128">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0289a-129">若要提高 Microsoft Defender for Office 365 中防網路釣魚保護的效能，您可以建立自訂的反網路釣魚原則，並將嚴格的設定套用至特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="0289a-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0289a-130">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="0289a-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0289a-131">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="0289a-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0289a-132">若要直接移至 **ATP 反網路釣魚** 頁面，請使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="0289a-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0289a-133">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0289a-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0289a-134">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="0289a-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0289a-135">若要新增、修改和刪除反網路釣魚原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0289a-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0289a-136">若要唯讀的反網路釣魚原則存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="0289a-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="0289a-137">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="0289a-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="0289a-138">**附註**：</span><span class="sxs-lookup"><span data-stu-id="0289a-138">**Notes**:</span></span>

  - <span data-ttu-id="0289a-139">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="0289a-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0289a-140">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0289a-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="0289a-141">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的「 **View-Only 組織管理**」角色群組也會提供該功能的唯讀存取權 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="0289a-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="0289a-142"><sup>\*</sup> 在 [安全性 & 規範中心] 中，唯讀存取可讓使用者查看自訂反網路釣魚原則的設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="0289a-143">唯讀使用者看不到預設反網路釣魚原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="0289a-144">如需 Microsoft Defender for Office 365 中的反網路釣魚原則建議設定，請參閱 [在 office 365 的 defender 中的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="0289a-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="0289a-145">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0289a-146">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱 [電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="0289a-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-147">使用安全性 & 規範中心在 Microsoft Defender for Office 365 中建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0289a-148">在安全性 & 合規性中心建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0289a-149">當您建立反網路釣魚原則時，您只能指定原則名稱、描述及識別套用原則的收件者篩選器。</span><span class="sxs-lookup"><span data-stu-id="0289a-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0289a-150">建立原則之後，您可以修改原則，以變更或審閱預設的反網路釣魚設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0289a-151">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0289a-152">在 [ **反網路釣魚** ] 頁面上，按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0289a-153">[ **建立新的反網路釣魚原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="0289a-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0289a-154">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0289a-155">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="0289a-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0289a-156">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="0289a-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0289a-157">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="0289a-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0289a-158">在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="0289a-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0289a-159">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="0289a-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0289a-160">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="0289a-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0289a-161">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="0289a-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0289a-162">按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-162">Click **Add a condition**.</span></span> <span data-ttu-id="0289a-163">在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="0289a-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0289a-164">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="0289a-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0289a-165">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="0289a-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0289a-166">**收件者網域為**：指定組織中一或多個已設定公認的網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="0289a-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="0289a-167">選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。</span><span class="sxs-lookup"><span data-stu-id="0289a-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0289a-168">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="0289a-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0289a-169">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="0289a-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0289a-170">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="0289a-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0289a-171">若要移除個別專案， 請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="0289a-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0289a-172">若要移除整個條件，請按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="0289a-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0289a-173">若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if** 中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="0289a-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0289a-174">若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="0289a-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0289a-175">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="0289a-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0289a-176">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="0289a-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0289a-177">在 [ **複查您的設定** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0289a-178">您可以按一下每個設定的 [ **編輯** ] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="0289a-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0289a-179">當您完成時，按一下 [ **建立這個原則**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0289a-180">在出現的確認對話方塊中，按一下 [ **確定** ]。</span><span class="sxs-lookup"><span data-stu-id="0289a-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0289a-181">使用這些一般設定建立反網路釣魚原則之後，請使用下一節的指示來設定原則中的保護設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-182">使用安全性 & 合規性中心，修改 Microsoft Defender for Office 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0289a-183">請使用下列程式修改反網路釣魚原則：您建立的新原則，或您已自訂的現有原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0289a-184">如果您還沒有，開啟安全性 & 規範中心，然後移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0289a-185">選取您要修改的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0289a-186">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="0289a-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0289a-187">隨即會顯示 [**編輯您的原則 \<name\>** ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="0289a-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0289a-188">按一下任何區段中的 [ **編輯** ]，即可存取該區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0289a-189">下列步驟會以區段出現的順序顯示，但不依序 (您可以選取及修改所有順序) 中的區段。</span><span class="sxs-lookup"><span data-stu-id="0289a-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0289a-190">按一下區段中的 [**編輯**] 之後，可用的設定會以一種方式呈現出來，但是您可以在頁面中以任何順序跳轉，您可以按一下 [**儲存**) ] 任何頁面 (] 或 [**取消**] 或 [**關閉** ![ ](../../media/scc-remove-icon.png) ] [關閉] 圖示，以回到 [**編輯您的 \<name\> 原則**] (頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0289a-191">**原則設定**：按一下 [ **編輯** ]，修改當您在上一節中 [建立原則](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) 時可用的相同設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="0289a-192">**名稱**</span><span class="sxs-lookup"><span data-stu-id="0289a-192">**Name**</span></span>
   - <span data-ttu-id="0289a-193">**描述**</span><span class="sxs-lookup"><span data-stu-id="0289a-193">**Description**</span></span>
   - <span data-ttu-id="0289a-194">**套用對象**</span><span class="sxs-lookup"><span data-stu-id="0289a-194">**Applied to**</span></span>
   - <span data-ttu-id="0289a-195">**檢查您的設定**</span><span class="sxs-lookup"><span data-stu-id="0289a-195">**Review your settings**</span></span>

   <span data-ttu-id="0289a-196">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0289a-197">模擬 **：按一下**[**編輯**] 修改原則中的受保護寄件者與受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="0289a-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="0289a-198">這些設定是原則的條件，可識別哄騙寄件者，以在輸入郵件的「寄件者」位址中個別或網域) 尋找 (。</span><span class="sxs-lookup"><span data-stu-id="0289a-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="0289a-199">如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的反網路釣魚原則中的模仿設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="0289a-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0289a-200">**新增要保護的使用者**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="0289a-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="0289a-201">若要開啟它，請將開關滑動至 [ **開啟**]，然後按一下所出現的 [ **新增使用者** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0289a-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="0289a-202">在出現的 [ **新增使用者** ] 浮出項目中，設定下列值：</span><span class="sxs-lookup"><span data-stu-id="0289a-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="0289a-203">**電子郵件地址**：</span><span class="sxs-lookup"><span data-stu-id="0289a-203">**Email address**:</span></span>

       - <span data-ttu-id="0289a-204">在方塊中按一下，並在使用者清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="0289a-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0289a-205">按一下方塊中的 [開始輸入]，以篩選清單並選取使用者。</span><span class="sxs-lookup"><span data-stu-id="0289a-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0289a-206">若要移除專案，請按一下 ![ ](../../media/scc-remove-icon.png) 使用者上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="0289a-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0289a-207">**名稱**：此值會根據您選取的電子郵件地址來填入，但您可以變更它。</span><span class="sxs-lookup"><span data-stu-id="0289a-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="0289a-208">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="0289a-209">若要編輯現有的專案，請在清單中選取受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="0289a-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="0289a-210">在每個反網路釣魚原則中，您可以指定最多60個受保護的使用者 (寄件者的電子郵件地址) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="0289a-211">您無法在多個原則中指定同一個受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="0289a-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="0289a-212">如果寄件者和收件者先前透過電子郵件進行通訊，使用者模擬保護便無法運作。</span><span class="sxs-lookup"><span data-stu-id="0289a-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="0289a-213">如果寄件者和收件者永不透過電子郵件進行通訊，郵件會被識別為類比嘗試。</span><span class="sxs-lookup"><span data-stu-id="0289a-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="0289a-214">**新增要保護的網域**：設定下列其中一項或兩項設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="0289a-215">**自動包含我擁有的網域**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="0289a-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="0289a-216">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0289a-217">**包含自訂網域**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="0289a-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="0289a-218">若要開啟它，請將開關滑動至 [ **開啟**]，然後在 [ **新增網域** ] 方塊中，輸入功能變數名稱 (例如，CONTOSO.COM) ，按 enter，然後視需要重複。</span><span class="sxs-lookup"><span data-stu-id="0289a-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0289a-219">在所有的反網路釣魚原則中，您最多可以有50個網域。</span><span class="sxs-lookup"><span data-stu-id="0289a-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="0289a-220">**動作**：按一下 [**編輯**]</span><span class="sxs-lookup"><span data-stu-id="0289a-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="0289a-221">**如果由模仿的使用者傳送電子郵件**：針對哄騙寄件者是您在 [ **新增使用者以保護**] 指定的其中一個受保護的使用者，設定下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="0289a-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="0289a-222">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="0289a-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="0289a-223">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="0289a-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0289a-224">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="0289a-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0289a-225">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="0289a-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="0289a-226">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="0289a-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0289a-227">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="0289a-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="0289a-228">**如果模仿的網域傳送電子郵件**：針對哄騙寄件者位於您在 [ **新增網域**] 中指定的其中一個受保護的網域，設定下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="0289a-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="0289a-229">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="0289a-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="0289a-230">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="0289a-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0289a-231">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="0289a-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0289a-232">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="0289a-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="0289a-233">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="0289a-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0289a-234">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="0289a-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0289a-235">按一下 [ **開啟模擬安全性秘訣** ]，然後設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="0289a-236">**顯示類比使用者的提示**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="0289a-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="0289a-237">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0289a-238">**顯示類比網域的秘訣**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="0289a-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="0289a-239">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0289a-240">**顯示不尋常字元的提示**：預設值為 **Off**。</span><span class="sxs-lookup"><span data-stu-id="0289a-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="0289a-241">若要將其開啟，請將開關滑動至 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="0289a-242">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0289a-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="0289a-243">**信箱智慧**：</span><span class="sxs-lookup"><span data-stu-id="0289a-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="0289a-244">**啟用信箱智慧？**：預設值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="0289a-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="0289a-245">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="0289a-246">**啟用信箱智慧型類比保護？**：此設定只有在 [ **啟用信箱智慧？** 已 **開啟**] 時才可用。</span><span class="sxs-lookup"><span data-stu-id="0289a-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="0289a-247">在 **類比的使用者傳送電子郵件時**，您可以指定下列其中一項動作，對信箱智慧失敗的郵件執行 (與受保護的使用者與受保護的網域) 的相同動作：</span><span class="sxs-lookup"><span data-stu-id="0289a-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="0289a-248">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="0289a-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="0289a-249">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="0289a-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0289a-250">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="0289a-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0289a-251">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="0289a-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="0289a-252">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="0289a-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0289a-253">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="0289a-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0289a-254">**新增信任的寄件者和網域**：指定原則的例外狀況：</span><span class="sxs-lookup"><span data-stu-id="0289a-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="0289a-255">**受信任的寄件者**：</span><span class="sxs-lookup"><span data-stu-id="0289a-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="0289a-256">在方塊中按一下，並在使用者清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="0289a-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0289a-257">按一下方塊中的 [開始輸入]，以篩選清單並選取使用者。</span><span class="sxs-lookup"><span data-stu-id="0289a-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0289a-258">若要移除專案，請按一下 ![ ](../../media/scc-remove-icon.png) 使用者上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="0289a-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0289a-259">**信任的網域**：輸入功能變數名稱 (例如，contoso.com) ，按 enter，然後視需要重複。</span><span class="sxs-lookup"><span data-stu-id="0289a-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0289a-260">請 **複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="0289a-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0289a-261">您可以按一下每個區段中的 [ **編輯** ]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0289a-262">您可以在此頁面 **上\*\*\*\*直接切換** 下列設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0289a-263">**受保護的使用者**</span><span class="sxs-lookup"><span data-stu-id="0289a-263">**Protected users**</span></span>
       - <span data-ttu-id="0289a-264">**受保護的網域** \>**包含我擁有的網域**</span><span class="sxs-lookup"><span data-stu-id="0289a-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="0289a-265">**受保護的網域** \>**受保護的網域** (自訂網域) </span><span class="sxs-lookup"><span data-stu-id="0289a-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="0289a-266">**信箱情報**</span><span class="sxs-lookup"><span data-stu-id="0289a-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="0289a-267">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0289a-268">**哄騙**：按一下 [ **編輯** ] 以開啟或關閉欺騙情報、在 Outlook 中開啟或關閉未驗證寄件者識別，以及設定要套用至封鎖的欺騙寄件者的郵件的動作。</span><span class="sxs-lookup"><span data-stu-id="0289a-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0289a-269">如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="0289a-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0289a-270">請注意，EOP 中的反網路釣魚原則也提供這些相同設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="0289a-271">**哄騙篩選設定**：預設值為 [ **開啟**]，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="0289a-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="0289a-272">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0289a-273">如需詳細資訊，請參閱 [在 EOP 中設定欺騙智慧](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="0289a-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0289a-274">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="0289a-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0289a-275">如需相關指示，請參閱 [在 Exchange Online 中的連接器增強型篩選](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="0289a-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0289a-276">**啟用未經驗證的寄件者功能**：預設值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="0289a-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="0289a-277">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0289a-278">**動作**：指定對哄騙智慧失敗的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="0289a-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0289a-279">**如果電子郵件是由不允許哄騙您網域的人員所傳送**：</span><span class="sxs-lookup"><span data-stu-id="0289a-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="0289a-280">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="0289a-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0289a-281">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="0289a-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="0289a-282">請 **複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="0289a-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0289a-283">您可以按一下每個區段中的 [ **編輯** ]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0289a-284">您可以在此頁面 **上\*\*\*\*直接切換** 下列設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="0289a-285">**啟用 antispoofing 保護**</span><span class="sxs-lookup"><span data-stu-id="0289a-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0289a-286">**啟用未經驗證的寄件者功能**</span><span class="sxs-lookup"><span data-stu-id="0289a-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0289a-287">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="0289a-288">**高級設定**：按一下 [ **編輯** ] 以設定高級網路釣魚閾值。</span><span class="sxs-lookup"><span data-stu-id="0289a-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="0289a-289">如需詳細資訊，請參閱 [Microsoft Defender For Office 365 的反網路釣魚原則中的高級網路釣魚閾值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="0289a-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0289a-290">**高級網路釣魚閥** 值：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="0289a-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="0289a-291">**1-Standard** (此為預設值。 ) </span><span class="sxs-lookup"><span data-stu-id="0289a-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="0289a-292">**2-嚴格**</span><span class="sxs-lookup"><span data-stu-id="0289a-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="0289a-293">**3-更嚴格**</span><span class="sxs-lookup"><span data-stu-id="0289a-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="0289a-294">**4-最積極**</span><span class="sxs-lookup"><span data-stu-id="0289a-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="0289a-295">**檢查您的設定**：按一下 [ **編輯** ]，可跳至 [ **高級網路釣魚閥** 值] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="0289a-296">當您完成時，按一下 [ **儲存** ] 任何一頁。</span><span class="sxs-lookup"><span data-stu-id="0289a-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="0289a-297">回到 [**編輯您的原則 \<Name\>** ] 頁面上，複查您的設定，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-298">使用安全性 & 合規性中心，在 Microsoft Defender for Office 365 中修改預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0289a-299">Microsoft Defender for Office 365 中的預設反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會出現在原則清單中。</span><span class="sxs-lookup"><span data-stu-id="0289a-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0289a-300">若要修改預設的反網路釣魚原則，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0289a-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0289a-301">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0289a-302">在 [ **反網路釣魚** ] 頁面上，按一下 [ **預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0289a-303">隨即會顯示 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0289a-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0289a-304">下列各節可供使用，其中包含 [修改自訂原則](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)時的相同設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="0289a-305">**模擬**</span><span class="sxs-lookup"><span data-stu-id="0289a-305">**Impersonation**</span></span>
   - <span data-ttu-id="0289a-306">**惡搞**</span><span class="sxs-lookup"><span data-stu-id="0289a-306">**Spoof**</span></span>
   - <span data-ttu-id="0289a-307">**進階設定**</span><span class="sxs-lookup"><span data-stu-id="0289a-307">**Advanced settings**</span></span>

   <span data-ttu-id="0289a-308">當您修改預設原則時，無法使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0289a-309">您可以看到 [ **原則設定** ] 區段和 [值]，但沒有 **編輯** 連結，所以您無法修改設定 (原則名稱、描述，以及原則 (套用至所有收件者) ) 的原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0289a-310">您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0289a-311">您無法變更預設原則的優先順序 (它永遠套用於最後) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0289a-312">在 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面上，複查您的設定，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0289a-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-313">在 Microsoft Defender for Office 365 中啟用或停用自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0289a-314">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0289a-315">請注意 [ **狀態** ] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="0289a-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0289a-316">將 [切換] 滑動至 [ **關閉** ] 以停用原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0289a-317">將切換滑動至 **開啟** 以啟用原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0289a-318">您無法停用預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-319">在 Microsoft Defender for Office 365 中設定自訂的反網路釣魚原則優先順序</span><span class="sxs-lookup"><span data-stu-id="0289a-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0289a-320">根據預設，反網路釣魚原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0289a-321">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="0289a-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0289a-322">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="0289a-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="0289a-323">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="0289a-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="0289a-324">自訂的反網路釣魚原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0289a-325">預設的反網路釣魚原則（名為 Office365 AntiPhish Default）的自訂優先順序值是 **最低** 的，您無法變更它。</span><span class="sxs-lookup"><span data-stu-id="0289a-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="0289a-326">**附注**：在 [安全性 & 規範中心] 中，您只能在建立反網路釣魚原則之後變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="0289a-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="0289a-327">在 PowerShell 中，您可以在建立反網路釣魚規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="0289a-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0289a-328">若要變更原則的優先順序，您可以按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 中的原則 (您無法直接修改安全性 & 規範中心) 中的 **優先順序** 號碼。</span><span class="sxs-lookup"><span data-stu-id="0289a-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0289a-329">如果您有多個原則，變更原則的優先順序只會有意義。</span><span class="sxs-lookup"><span data-stu-id="0289a-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0289a-330">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0289a-331">選取您要修改的原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="0289a-332">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="0289a-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0289a-333">隨即會顯示 [**編輯您的原則 \<name\>** ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="0289a-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0289a-334">**優先順序** 值為 **0** 的自訂反網路釣魚原則只有「**降低優先順序**」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="0289a-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0289a-335">具有最低 **優先順序** 值的自訂反網路釣魚原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="0289a-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0289a-336">如果您有三個或多個自訂的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0289a-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0289a-337">按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。</span><span class="sxs-lookup"><span data-stu-id="0289a-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0289a-338">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="0289a-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-339">使用安全性 & 合規性中心來查看 Microsoft Defender for Office 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0289a-340">在安全性 & 規範中心，然後移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0289a-341">請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="0289a-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="0289a-342">選取您要查看的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0289a-343">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="0289a-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0289a-344">按一下 [ **預設原則** ] 以查看預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0289a-345">此時會出現 [**編輯您的原則 \<name\>** ] 快顯視窗，您可以在其中查看設定和值。</span><span class="sxs-lookup"><span data-stu-id="0289a-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-346">使用安全性 & 合規性中心移除 Microsoft Defender for Office 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0289a-347">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0289a-348">選取您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="0289a-349">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="0289a-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0289a-350">在出現的 [**編輯 \<name\> 您的原則**] 浮出視窗中，按一下 [**刪除原則**]，然後在出現的警告對話方塊中按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="0289a-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0289a-351">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0289a-352">使用 Exchange Online PowerShell 來設定 Microsoft Defender for Office 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0289a-353">如先前所述，反垃圾郵件原則是由反網路釣魚原則和反網路釣魚規則所組成。</span><span class="sxs-lookup"><span data-stu-id="0289a-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="0289a-354">在 Exchange Online PowerShell 中，反網路釣魚原則和反網路釣魚規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="0289a-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0289a-355">您可以使用 **\* -AntiPhishPolicy** Cmdlet 來管理反網路釣魚原則，並使用 **\* -AntiPhishRule** Cmdlet 來管理反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0289a-356">在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="0289a-357">在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="0289a-358">當您從 PowerShell 中移除反網路釣魚原則時，不會自動移除對應的反網路釣魚規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="0289a-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0289a-359">使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0289a-360">在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="0289a-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0289a-361">建立反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="0289a-362">建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0289a-363">**附註**：</span><span class="sxs-lookup"><span data-stu-id="0289a-363">**Notes**:</span></span>

- <span data-ttu-id="0289a-364">您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="0289a-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0289a-365">反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="0289a-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0289a-366">您可以在 PowerShell 中為安全性 & 相容性中心以外的新反網路釣魚原則設定下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="0289a-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0289a-367">_在_ `$false` **AntiPhishRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="0289a-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="0289a-368">在 _\<Number\>_ **AntiPhishRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="0289a-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0289a-369">在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="0289a-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0289a-370">步驟1：使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0289a-371">若要建立反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="0289a-372">此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="0289a-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0289a-373"> (未使用 _enabled_ 參數時，也會啟用該原則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="0289a-374">描述為：「調研部門原則」。</span><span class="sxs-lookup"><span data-stu-id="0289a-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="0289a-375">針對所有公認的網域及目標網域的 fabrikam.com 保護，啟用組織網域保護。</span><span class="sxs-lookup"><span data-stu-id="0289a-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="0289a-376">指定 Mai Fujito (mfujito@fabrikam.com) 做為使用者以防範模擬。</span><span class="sxs-lookup"><span data-stu-id="0289a-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="0289a-377">啟用信箱智慧。</span><span class="sxs-lookup"><span data-stu-id="0289a-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="0289a-378">啟用信箱智慧保護，並指定隔離動作。</span><span class="sxs-lookup"><span data-stu-id="0289a-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="0289a-379">啟用安全提示。</span><span class="sxs-lookup"><span data-stu-id="0289a-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="0289a-380">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="0289a-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0289a-381">步驟2：使用 PowerShell 建立反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="0289a-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0289a-382">若要建立反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0289a-383">在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：</span><span class="sxs-lookup"><span data-stu-id="0289a-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0289a-384">此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="0289a-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0289a-385">此規則適用於名為 Research Department 之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0289a-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0289a-386">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="0289a-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0289a-387">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="0289a-387">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0289a-388">使用 PowerShell 來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0289a-389">若要查看現有的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0289a-390">此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="0289a-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0289a-391">此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="0289a-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0289a-392">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="0289a-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0289a-393">使用 PowerShell 來查看反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="0289a-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0289a-394">若要查看現有的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0289a-395">此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="0289a-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0289a-396">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0289a-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0289a-397">此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="0289a-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0289a-398">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="0289a-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0289a-399">使用 PowerShell 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0289a-400">除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，如您在建立原則（如您在本文稍早的 [步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy) 區段中所述），您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="0289a-401">_MakeDefault_ 參數會將指定的原則轉換成預設原則 (套用至每個使用者，永遠 **最低** 的優先順序，而且您無法刪除只有當您在 PowerShell 中修改反網路釣魚原則時，才可使用此參數) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0289a-402">您無法重新命名反網路釣魚原則 (**AntiPhishPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0289a-403">當您在安全性 & 合規性中心重新命名防網路釣魚原則時，您只是重新命名反網路釣魚 _規則_。</span><span class="sxs-lookup"><span data-stu-id="0289a-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0289a-404">若要修改反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0289a-405">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="0289a-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0289a-406">使用 PowerShell 修改反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="0289a-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0289a-407">在 PowerShell 中修改反網路釣魚規則時，唯一無法使用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0289a-408">若要啟用或停用現有的反網路釣魚規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="0289a-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0289a-409">否則，當您在 PowerShell 中修改反網路釣魚規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="0289a-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="0289a-410">當您建立規則時，如本文稍早 [使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule) 一節所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="0289a-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="0289a-411">若要修改反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0289a-412">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="0289a-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0289a-413">使用 PowerShell 來啟用或停用反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="0289a-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0289a-414">啟用或停用 PowerShell 中的反網路釣魚規則，可啟用或停用反網路釣魚規則和指派的反網路釣魚原則)  (的整個反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0289a-415">您無法啟用或停用預設的反網路釣魚原則 (它永遠套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="0289a-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0289a-416">若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0289a-417">本範例會停用名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0289a-418">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0289a-419">如需詳細的語法及參數資訊，請參閱 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="0289a-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0289a-420">使用 PowerShell 設定反網路釣魚規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="0289a-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0289a-421">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="0289a-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0289a-422">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="0289a-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0289a-423">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="0289a-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0289a-424">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="0289a-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0289a-425">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="0289a-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0289a-426">若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0289a-427">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="0289a-427">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="0289a-428">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="0289a-428">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0289a-429">**附註**：</span><span class="sxs-lookup"><span data-stu-id="0289a-429">**Notes**:</span></span>

- <span data-ttu-id="0289a-430">若要在建立新規則時設定其優先順序，請改用 **AntiPhishRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="0289a-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0289a-431">預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序 **值。**</span><span class="sxs-lookup"><span data-stu-id="0289a-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0289a-432">使用 PowerShell 移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="0289a-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0289a-433">當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0289a-434">若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0289a-435">此範例會移除名為「行銷部門」的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0289a-436">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="0289a-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0289a-437">使用 PowerShell 移除反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="0289a-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0289a-438">當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="0289a-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0289a-439">若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="0289a-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0289a-440">此範例會移除名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="0289a-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0289a-441">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="0289a-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0289a-442">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="0289a-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="0289a-443">若要確認您是否已在 Microsoft Defender for Office 365 中成功設定反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="0289a-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="0289a-444">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="0289a-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="0289a-445">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="0289a-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0289a-446">若要查看更多詳細資料，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="0289a-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0289a-447">從清單中選取原則，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0289a-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0289a-448">按一下 [ **預設原則** ]，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0289a-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0289a-449">在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，並執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="0289a-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```