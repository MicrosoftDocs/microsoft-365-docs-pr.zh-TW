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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何建立、修改及刪除 Exchange Online Protection (EOP 中可用的反網路釣魚原則，以含或不含 Exchange Online 信箱的組織) 組織。
ms.openlocfilehash: 03c1ce8e940491607fe04988d41c927f92479d96
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760329"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="a4370-103">在 EOP 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a4370-104">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，會有預設的反網路釣魚原則，其中包含預設啟用的有限的反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="a4370-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="a4370-105">如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="a4370-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="a4370-106">系統管理員可以查看、編輯和設定 (，但不會刪除預設的反網路釣魚原則) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="a4370-107">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a4370-108">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="a4370-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a4370-109">具有 Exchange Online 信箱的組織可在安全性 & 合規性中心或 Exchange Online PowerShell 中設定反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="a4370-110">獨立 EOP 組織只能使用安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="a4370-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="a4370-111">如需在適用365于 office 365 的 Microsoft Defender for Office 中建立及修改更高級的反網路釣魚原則的相關資訊，請參閱在 [Microsoft defender For office 365 中設定反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a4370-111">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="a4370-112">反網路釣魚原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="a4370-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="a4370-113">**反網路釣魚原則**：指定要啟用或停用的網路釣魚防護，以及要套用選項的動作。</span><span class="sxs-lookup"><span data-stu-id="a4370-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="a4370-114">**反網路釣魚規則**：指定原則套用至) 以進行反網路釣魚原則的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="a4370-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="a4370-115">當您在安全性 & 合規性中心管理反網路釣魚原則時，這兩個元素之間的差異並不明顯。</span><span class="sxs-lookup"><span data-stu-id="a4370-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a4370-116">當您建立反網路釣魚原則時，實際上是建立反網路釣魚規則，同時也為這兩者使用相同的名稱建立了關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a4370-117">當您修改反網路釣魚原則時，與名稱、優先順序、啟用或停用的名稱和收件者篩選器相關的設定會修改反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="a4370-118">所有其他設定會修改關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="a4370-119">當您移除防網路釣魚原則時，會移除反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="a4370-120">在 Exchange Online PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a4370-121">如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 設定反網路釣魚原則](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 一節。</span><span class="sxs-lookup"><span data-stu-id="a4370-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="a4370-122">每個組織都有一個名為 Office365 AntiPhish 的內建反網路釣魚原則，其具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="a4370-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="a4370-123">原則會套用至組織中的所有收件者，即使沒有反網路釣魚的規則 (收件者篩選) 與原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="a4370-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a4370-124">此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="a4370-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a4370-125">任何您建立的自訂原則皆具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="a4370-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="a4370-126">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a4370-127">若要提高反網路釣魚防護的效能，您可以建立自訂的反網路釣魚原則，其套用至特定使用者或使用者群組的更嚴格設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a4370-128">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a4370-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a4370-129">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="a4370-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a4370-130">若要直接移至 [ **反網路釣魚** ] 頁面，請使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="a4370-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="a4370-131">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a4370-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="a4370-132">您無法管理獨立 EOP PowerShell 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="a4370-133">您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="a4370-133">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a4370-134">若要新增、修改和刪除反網路釣魚原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a4370-134">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a4370-135">若要唯讀的反網路釣魚原則存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="a4370-135">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="a4370-136">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a4370-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a4370-137">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a4370-137">**Notes**:</span></span>

  - <span data-ttu-id="a4370-138">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="a4370-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a4370-139">如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="a4370-139">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="a4370-140">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的「 **View-Only 組織管理**」角色群組也會提供該功能的唯讀存取權 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="a4370-140">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="a4370-141"><sup>\*</sup> 在 [安全性 & 規範中心] 中，唯讀存取可讓使用者查看自訂反網路釣魚原則的設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-141"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="a4370-142">唯讀使用者看不到預設反網路釣魚原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-142">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="a4370-143">若要在獨立 EOP 中建立及修改反網路釣魚原則，您需要針對租使用者執行一些需要 _分解_ 的專案。</span><span class="sxs-lookup"><span data-stu-id="a4370-143">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="a4370-144">例如，在 Exchange 系統管理中心 (EAC) 中，您可以移至 [ **許可權** ] 索引標籤，選取現有的角色群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後移除) 最終新增回的角色 (。</span><span class="sxs-lookup"><span data-stu-id="a4370-144">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="a4370-145">如果您的租使用者從未 hydrated，您會看到一個名為「 **更新組織」設定** 的對話方塊，其進度列應該會順利完成。</span><span class="sxs-lookup"><span data-stu-id="a4370-145">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="a4370-146">如需分解的詳細資訊，請參閱 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) Cmdlet (無法在獨立 EOP PowerShell 或安全性 & 規範中心) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-146">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="a4370-147">如需有關反網路釣魚原則的建議設定，請參閱 [EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="a4370-147">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="a4370-148">允許套用更新的原則最多30分鐘。</span><span class="sxs-lookup"><span data-stu-id="a4370-148">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="a4370-149">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱 [電子郵件保護的順序及優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="a4370-149">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="a4370-150">使用安全性 & 規範中心建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-150">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="a4370-151">在安全性 & 合規性中心建立自訂的反網路釣魚原則，會同時使用相同的名稱建立反網路釣魚規則和相關聯的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-151">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="a4370-152">當您建立反網路釣魚原則時，您只能指定原則名稱、描述及識別套用原則的收件者篩選器。</span><span class="sxs-lookup"><span data-stu-id="a4370-152">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="a4370-153">建立原則之後，您可以修改原則，以變更或審閱預設的反網路釣魚設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-153">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="a4370-154">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a4370-155">在 [ **反網路釣魚** ] 頁面上，按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-155">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="a4370-156">[ **建立新的反網路釣魚原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="a4370-156">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="a4370-157">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a4370-157">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="a4370-158">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="a4370-158">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="a4370-159">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="a4370-159">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a4370-160">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="a4370-160">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a4370-161">在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="a4370-161">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="a4370-162">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="a4370-162">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a4370-163">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="a4370-163">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a4370-164">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="a4370-164">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="a4370-165">按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-165">Click **Add a condition**.</span></span> <span data-ttu-id="a4370-166">在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="a4370-166">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="a4370-167">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="a4370-167">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a4370-168">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="a4370-168">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="a4370-169">**收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="a4370-169">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="a4370-170">選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。</span><span class="sxs-lookup"><span data-stu-id="a4370-170">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="a4370-171">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="a4370-171">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="a4370-172">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="a4370-172">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="a4370-173">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="a4370-173">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="a4370-174">若要移除個別專案， 請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="a4370-174">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="a4370-175">若要移除整個條件，請按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="a4370-175">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="a4370-176">若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if** 中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="a4370-176">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="a4370-177">若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="a4370-177">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="a4370-178">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="a4370-178">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a4370-179">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="a4370-179">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a4370-180">在 [ **複查您的設定** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-180">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="a4370-181">您可以按一下每個設定的 [ **編輯** ] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="a4370-181">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="a4370-182">當您完成時，按一下 [ **建立這個原則**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-182">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="a4370-183">在出現的確認對話方塊中，按一下 [ **確定** ]。</span><span class="sxs-lookup"><span data-stu-id="a4370-183">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="a4370-184">使用這些一般原則設定建立反網路釣魚原則之後，請使用下一節中的指示來設定原則中的保護設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-184">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="a4370-185">使用安全性 & 規範中心來修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-185">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="a4370-186">請使用下列程式修改反網路釣魚原則：您建立的新原則，或您已自訂的現有原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-186">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="a4370-187">如果您還沒有開啟安全性 & 規範中心，請移至 **威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-187">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a4370-188">選取您要修改的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-188">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="a4370-189">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="a4370-189">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a4370-190">隨即會顯示 [**編輯您的原則 \<name\>** ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="a4370-190">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="a4370-191">按一下任何區段中的 [ **編輯** ]，即可存取該區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-191">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="a4370-192">下列步驟會以區段出現的順序顯示，但不依序 (您可以選取及修改所有順序) 中的區段。</span><span class="sxs-lookup"><span data-stu-id="a4370-192">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="a4370-193">按一下區段中的 [**編輯**] 之後，可用的設定會以一種方式呈現出來，但是您可以在頁面中以任何順序跳轉，您可以按一下 [**儲存**) ] 任何頁面 (] 或 [**取消**] 或 [**關閉** ![ ](../../media/scc-remove-icon.png) ] [關閉] 圖示，以回到 [**編輯您的 \<name\> 原則**] (頁面。</span><span class="sxs-lookup"><span data-stu-id="a4370-193">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="a4370-194">**原則設定**：按一下 [ **編輯** ]，修改當您在上一節中 [建立原則](#use-the-security--compliance-center-to-create-anti-phishing-policies) 時可用的相同設定：</span><span class="sxs-lookup"><span data-stu-id="a4370-194">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="a4370-195">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a4370-195">**Name**</span></span>
   - <span data-ttu-id="a4370-196">**描述**</span><span class="sxs-lookup"><span data-stu-id="a4370-196">**Description**</span></span>
   - <span data-ttu-id="a4370-197">**套用對象**</span><span class="sxs-lookup"><span data-stu-id="a4370-197">**Applied to**</span></span>
   - <span data-ttu-id="a4370-198">**檢查您的設定**</span><span class="sxs-lookup"><span data-stu-id="a4370-198">**Review your settings**</span></span>

   <span data-ttu-id="a4370-199">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="a4370-199">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="a4370-200">**哄騙**：按一下 [ **編輯** ] 以開啟或關閉欺騙情報、在 Outlook 中開啟或關閉未驗證寄件者識別，以及設定要套用至封鎖的欺騙寄件者的郵件的動作。</span><span class="sxs-lookup"><span data-stu-id="a4370-200">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="a4370-201">如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="a4370-201">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="a4370-202">請注意，Office 365 的 Defender 網路釣魚原則也提供這些相同設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-202">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="a4370-203">**哄騙篩選設定**：預設值為 [ **開啟**]，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="a4370-203">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="a4370-204">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-204">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="a4370-205">如需詳細資訊，請參閱 [在 EOP 中設定欺騙智慧](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="a4370-205">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="a4370-206">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="a4370-206">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="a4370-207">如需相關指示，請參閱 [在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="a4370-207">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="a4370-208">**啟用未經驗證的寄件者功能**：預設值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="a4370-208">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="a4370-209">若要將它關閉，請將開關滑動至 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-209">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="a4370-210">**動作**：指定對哄騙智慧失敗的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="a4370-210">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="a4370-211">**如果電子郵件是由不允許哄騙您網域的人員所傳送**：</span><span class="sxs-lookup"><span data-stu-id="a4370-211">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="a4370-212">**將郵件移至收件者的 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="a4370-212">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="a4370-213">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="a4370-213">**Quarantine the message**</span></span>

   - <span data-ttu-id="a4370-214">請 **複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="a4370-214">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="a4370-215">您可以按一下每個區段中的 [ **編輯** ]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="a4370-215">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="a4370-216">您可以在此頁面 **上\*\*\*\*直接切換** 下列設定：</span><span class="sxs-lookup"><span data-stu-id="a4370-216">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="a4370-217">**啟用 antispoofing 保護**</span><span class="sxs-lookup"><span data-stu-id="a4370-217">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="a4370-218">**啟用未經驗證的寄件者功能**</span><span class="sxs-lookup"><span data-stu-id="a4370-218">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="a4370-219">完成後，按一下 [ **儲存** ] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="a4370-219">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="a4370-220">回到 [**編輯您的原則 \<Name\>** ] 頁面上，複查您的設定，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-220">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="a4370-221">使用安全性 & 合規性中心來修改預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-221">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="a4370-222">預設的反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會顯示在原則清單中。</span><span class="sxs-lookup"><span data-stu-id="a4370-222">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="a4370-223">若要修改預設的反網路釣魚原則，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a4370-223">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="a4370-224">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a4370-225">在 [ **反網路釣魚** ] 頁面上，按一下 [ **預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-225">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="a4370-226">隨即會顯示 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a4370-226">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="a4370-227">下列各節可供使用，其中包含 [修改自訂原則](#use-the-security--compliance-center-to-modify-anti-phishing-policies)時的相同設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-227">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="a4370-228">**模擬**</span><span class="sxs-lookup"><span data-stu-id="a4370-228">**Impersonation**</span></span>
   - <span data-ttu-id="a4370-229">**惡搞**</span><span class="sxs-lookup"><span data-stu-id="a4370-229">**Spoof**</span></span>
   - <span data-ttu-id="a4370-230">**進階設定**</span><span class="sxs-lookup"><span data-stu-id="a4370-230">**Advanced settings**</span></span>

   <span data-ttu-id="a4370-231">當您修改預設原則時，無法使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="a4370-231">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="a4370-232">您可以看到 [ **原則設定** ] 區段和 [值]，但沒有 **編輯** 連結，所以您無法修改設定 (原則名稱、描述，以及原則套用至所有收件者的設定 (套用至所有收件者) # A3。</span><span class="sxs-lookup"><span data-stu-id="a4370-232">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="a4370-233">您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-233">You can't delete the default policy.</span></span>
   - <span data-ttu-id="a4370-234">您無法變更預設原則的優先順序 (它永遠套用於最後) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-234">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="a4370-235">在 [ **編輯您的原則 Office365 AntiPhish 預設** ] 頁面上，複查您的設定，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a4370-235">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="a4370-236">啟用或停用自訂的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-236">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="a4370-237">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-237">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a4370-238">請注意 [ **狀態** ] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="a4370-238">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="a4370-239">將 [切換] 滑動至 [ **關閉** ] 以停用原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-239">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="a4370-240">將切換滑動至 **開啟** 以啟用原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-240">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="a4370-241">您無法停用預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-241">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="a4370-242">設定自訂的反網路釣魚原則優先順序</span><span class="sxs-lookup"><span data-stu-id="a4370-242">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="a4370-243">根據預設，反網路釣魚原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-243">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a4370-244">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="a4370-244">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a4370-245">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="a4370-245">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a4370-246">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="a4370-246">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="a4370-247">自訂的反網路釣魚原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a4370-248">預設的反網路釣魚原則（名為 Office365 AntiPhish Default）的自訂優先順序值是 **最低** 的，您無法變更它。</span><span class="sxs-lookup"><span data-stu-id="a4370-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="a4370-249">**附注**：在 [安全性 & 規範中心] 中，您只能在建立反網路釣魚原則之後變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="a4370-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="a4370-250">在 PowerShell 中，您可以在建立反網路釣魚規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="a4370-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="a4370-251">若要變更原則的優先順序，您可以按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 中的原則 (您無法直接修改安全性 & 規範中心) 中的 **優先順序** 號碼。</span><span class="sxs-lookup"><span data-stu-id="a4370-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="a4370-252">如果您有多個原則，變更原則的優先順序只會有意義。</span><span class="sxs-lookup"><span data-stu-id="a4370-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="a4370-253">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="a4370-254">選取您要修改的原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="a4370-255">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="a4370-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a4370-256">隨即會顯示 [**編輯您的原則 \<name\>** ] 快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="a4370-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="a4370-257">**優先順序** 值為 **0** 的自訂反網路釣魚原則只有「**降低優先順序**」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="a4370-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="a4370-258">具有最低 **優先順序** 值的自訂反網路釣魚原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="a4370-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="a4370-259">如果您有三個或多個自訂的反網路釣魚原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a4370-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="a4370-260">按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。</span><span class="sxs-lookup"><span data-stu-id="a4370-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="a4370-261">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="a4370-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="a4370-262">使用安全性 & 規範中心來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="a4370-263">在安全性 & 規範中心，然後移至 **威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a4370-264">請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a4370-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="a4370-265">選取您要查看的自訂反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="a4370-266">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="a4370-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="a4370-267">按一下 [ **預設原則** ] 以查看預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="a4370-268">此時會出現 [**編輯您的原則 \<name\>** ] 快顯視窗，您可以在其中查看設定和值。</span><span class="sxs-lookup"><span data-stu-id="a4370-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="a4370-269">使用安全性 & 規範中心移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="a4370-270">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a4370-271">選取您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="a4370-272">如果已選取它，請取消選取它，然後再次選取。</span><span class="sxs-lookup"><span data-stu-id="a4370-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a4370-273">在出現的 [**編輯 \<name\> 您的原則**] 浮出視窗中，按一下 [**刪除原則**]，然後在出現的警告對話方塊中按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="a4370-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="a4370-274">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="a4370-275">使用 Exchange Online PowerShell 設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="a4370-276">如先前所述，反網路釣魚原則是由反網路釣魚原則和反網路釣魚規則所組成。</span><span class="sxs-lookup"><span data-stu-id="a4370-276">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="a4370-277">在 Exchange Online PowerShell 中，反網路釣魚原則和反網路釣魚規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="a4370-277">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="a4370-278">您可以使用 **\* -AntiPhishPolicy** Cmdlet 來管理反網路釣魚原則，並使用 **\* -AntiPhishRule** Cmdlet 來管理反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-278">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="a4370-279">在 PowerShell 中，您先建立反網路釣魚原則，然後建立反網路釣魚規則，識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-279">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a4370-280">在 PowerShell 中，您可以修改反網路釣魚原則和反網路釣魚規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-280">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="a4370-281">當您從 PowerShell 中移除反網路釣魚原則時，不會自動移除對應的反網路釣魚規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a4370-281">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="a4370-282">下列 PowerShell 程式無法在獨立 EOP 組織中使用 Exchange Online Protection PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a4370-282">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="a4370-283">使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-283">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="a4370-284">在 PowerShell 中建立反網路釣魚原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="a4370-284">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a4370-285">建立反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-285">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="a4370-286">建立反網路釣魚規則，以指定套用規則的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-286">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="a4370-287">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a4370-287">**Notes**:</span></span>

- <span data-ttu-id="a4370-288">您可以建立新的反網路釣魚規則，並將現有的、未關聯的反網路釣魚原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="a4370-288">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="a4370-289">反網路釣魚規則無法與一個以上的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="a4370-289">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="a4370-290">您可以在 PowerShell 中為安全性 & 相容性中心以外的新反網路釣魚原則設定下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="a4370-290">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="a4370-291">_在_ `$false` **AntiPhishRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="a4370-291">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="a4370-292">在 _\<Number\>_ **AntiPhishRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="a4370-292">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="a4370-293">在您指派原則至反網路釣魚規則之前，您在 PowerShell 中所建立的新反網路釣魚原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="a4370-293">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="a4370-294">步驟1：使用 PowerShell 建立反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-294">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="a4370-295">若要建立反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-295">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="a4370-296">此範例會使用下列設定來建立名為「調查隔離隔離」的反網路釣魚策略：</span><span class="sxs-lookup"><span data-stu-id="a4370-296">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="a4370-297">描述為：「調研部門原則」。</span><span class="sxs-lookup"><span data-stu-id="a4370-297">The description is: Research department policy.</span></span>
- <span data-ttu-id="a4370-298">將哄騙的預設動作變更為「隔離」。</span><span class="sxs-lookup"><span data-stu-id="a4370-298">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="a4370-299">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4370-299">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="a4370-300">步驟2：使用 PowerShell 建立反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="a4370-300">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="a4370-301">若要建立反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-301">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a4370-302">在這個範例中，會建立一個名為「調查部門」的反網路釣魚規則，條件如下：</span><span class="sxs-lookup"><span data-stu-id="a4370-302">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="a4370-303">此規則會與名為「調查隔離隔離」的反網路釣魚原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="a4370-303">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="a4370-304">此規則適用於名為 Research Department 之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a4370-304">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="a4370-305">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="a4370-305">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="a4370-306">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="a4370-306">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="a4370-307">使用 PowerShell 來查看反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-307">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="a4370-308">若要查看現有的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-308">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a4370-309">此範例會傳回所有反網路釣魚原則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="a4370-309">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="a4370-310">此範例會傳回名為「主管人員」之反網路釣魚原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="a4370-310">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="a4370-311">如需詳細的語法及參數資訊，請參閱 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4370-311">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="a4370-312">使用 PowerShell 來查看反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="a4370-312">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="a4370-313">若要查看現有的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-313">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a4370-314">此範例會傳回所有反網路釣魚規則的摘要清單及指定的屬性。</span><span class="sxs-lookup"><span data-stu-id="a4370-314">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="a4370-315">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a4370-315">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="a4370-316">此範例會傳回名為 Contoso 主管的反網路釣魚規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="a4370-316">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="a4370-317">如需詳細的語法及參數資訊，請參閱 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="a4370-317">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="a4370-318">使用 PowerShell 修改反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-318">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="a4370-319">除了下列專案之外，當您在 PowerShell 中修改反網路釣魚原則時，如您在建立原則時，依照 [步驟1：使用 PowerShell 建立反網路釣魚原則](#step-1-use-powershell-to-create-an-anti-phish-policy) 中所述，您可以在本文中修改反網路釣魚原則時，使用相同設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-319">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="a4370-320">_MakeDefault_ 參數會將指定的原則轉換成預設原則 (套用至每個使用者，永遠 **最低** 的優先順序，而且您無法刪除只有當您在 PowerShell 中修改反網路釣魚原則時，才可使用此參數) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-320">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="a4370-321">您無法重新命名反網路釣魚原則 (**AntiPhishPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-321">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a4370-322">當您在安全性 & 合規性中心重新命名防網路釣魚原則時，您只是重新命名反網路釣魚 _規則_。</span><span class="sxs-lookup"><span data-stu-id="a4370-322">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="a4370-323">若要修改反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-323">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a4370-324">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4370-324">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="a4370-325">使用 PowerShell 修改反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="a4370-325">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="a4370-326">當您在 PowerShell 中修改反網路釣魚規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-326">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a4370-327">若要啟用或停用現有的反網路釣魚規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="a4370-327">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="a4370-328">否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立反網路釣魚規則](#step-2-use-powershell-to-create-an-anti-phish-rule) ] 區段所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="a4370-328">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="a4370-329">若要修改反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-329">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a4370-330">如需詳細的語法及參數資訊，請參閱 [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="a4370-330">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="a4370-331">使用 PowerShell 來啟用或停用反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="a4370-331">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="a4370-332">啟用或停用 PowerShell 中的反網路釣魚規則，可啟用或停用反網路釣魚規則和指派的反網路釣魚原則)  (的整個反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-332">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="a4370-333">您無法啟用或停用預設的反網路釣魚原則 (它永遠套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="a4370-333">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="a4370-334">若要啟用或停用 PowerShell 中的反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-334">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="a4370-335">本範例會停用名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-335">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a4370-336">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-336">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a4370-337">如需詳細的語法及參數資訊，請參閱 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 和 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="a4370-337">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="a4370-338">使用 PowerShell 設定反網路釣魚規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="a4370-338">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="a4370-339">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="a4370-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a4370-340">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="a4370-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a4370-341">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="a4370-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a4370-342">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="a4370-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a4370-343">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="a4370-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a4370-344">若要設定 PowerShell 中的反網路釣魚規則優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-344">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a4370-345">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="a4370-345">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a4370-346">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="a4370-346">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a4370-347">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a4370-347">**Notes**:</span></span>

- <span data-ttu-id="a4370-348">若要在建立新規則時設定其優先順序，請改用 **AntiPhishRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="a4370-348">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="a4370-349">預設的反網路釣魚原則沒有相對應的反網路釣魚規則，而且它永遠具有不可修改的優先順序 **值。**</span><span class="sxs-lookup"><span data-stu-id="a4370-349">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="a4370-350">使用 PowerShell 移除反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="a4370-350">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="a4370-351">當您使用 PowerShell 來移除反網路釣魚原則時，並不會移除對應的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-351">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="a4370-352">若要在 PowerShell 中移除反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-352">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a4370-353">此範例會移除名為「行銷部門」的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-353">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a4370-354">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4370-354">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="a4370-355">使用 PowerShell 移除反網路釣魚規則</span><span class="sxs-lookup"><span data-stu-id="a4370-355">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="a4370-356">當您使用 PowerShell 來移除反網路釣魚規則時，並不會移除對應的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="a4370-356">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="a4370-357">若要在 PowerShell 中移除反網路釣魚規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a4370-357">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="a4370-358">此範例會移除名為「行銷部門」的反網路釣魚規則。</span><span class="sxs-lookup"><span data-stu-id="a4370-358">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a4370-359">如需詳細的語法及參數資訊，請參閱 [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="a4370-359">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a4370-360">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="a4370-360">How do you know these procedures worked?</span></span>

<span data-ttu-id="a4370-361">若要確認您是否已在 Microsoft Defender for Office 365 中成功設定反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="a4370-361">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="a4370-362">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4370-362">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="a4370-363">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="a4370-363">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a4370-364">若要查看更多詳細資料，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a4370-364">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="a4370-365">從清單中選取原則，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a4370-365">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="a4370-366">按一下 [ **預設原則** ]，然後在飛入的視窗中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a4370-366">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="a4370-367">在 Exchange Online PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="a4370-367">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
