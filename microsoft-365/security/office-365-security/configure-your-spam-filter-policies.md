---
title: 設定垃圾郵件篩選原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何在 Exchange Online Protection (EOP) 中檢視、建立、修改及刪除反垃圾郵件原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb3e378c13507e354cdd1d739214c1c2d9d6aa98
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950092"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="8acc9-103">在 EOP 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-103">Configure anti-spam policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8acc9-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8acc9-104">**Applies to**</span></span>
- [<span data-ttu-id="8acc9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8acc9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8acc9-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="8acc9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8acc9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8acc9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8acc9-108">在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，EOP 會自動保護內送電子郵件，防止垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="8acc9-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="8acc9-109">EOP 使用反垃圾郵件原則 (也稱為垃圾郵件過篩選原則或內容篩選原則)，作為貴組織全面防範垃圾郵件的一環。</span><span class="sxs-lookup"><span data-stu-id="8acc9-109">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="8acc9-110">如需詳細資訊，請參閱[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-110">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="8acc9-111">系統管理員可以檢視、編輯、設定 (但不能刪除) 預設的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-111">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="8acc9-112">若要提高精確性，您也可以建立自訂的反垃圾郵件原則，並套用至貴組織中的特定使用者、群組或網域。</span><span class="sxs-lookup"><span data-stu-id="8acc9-112">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="8acc9-113">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-113">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="8acc9-114">您可以在 Microsoft 365 Defender 入口網站或在 PowerShell (在 Exchange Online 中有信箱的組織中為適用於 Microsoft 365 的 Exchange Online PowerShell；在沒有 Exchange Online 信箱的組織中則為獨立 EOP PowerShell) 中設定反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-114">You can configure anti-spam policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="8acc9-115">反垃圾郵件原則的基本元素有：</span><span class="sxs-lookup"><span data-stu-id="8acc9-115">The basic elements of an anti-spam policy are:</span></span>

- <span data-ttu-id="8acc9-116">**垃圾郵件篩選原則**：指定垃圾郵件篩選裁決的動作和通知選項。</span><span class="sxs-lookup"><span data-stu-id="8acc9-116">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="8acc9-117">**垃圾郵件篩選規則**：指定垃圾郵件篩選原則的優先順序及收件者篩選器 (原則套用對象)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-117">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="8acc9-118">當您在 Microsoft 365 Defender 入口網站中管理反垃圾郵件原則時，上述兩個元素的差異不大：</span><span class="sxs-lookup"><span data-stu-id="8acc9-118">The difference between these two elements isn't obvious when you manage anti-spam polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="8acc9-119">當您建立ㄧ項反垃圾郵件原則時，其實只是以相同的名稱，同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-119">When you create an anti-spam policy, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="8acc9-120">當您修改反垃圾郵件原則時，與名稱、優先順序、已啟用或已停用、收件者篩選相關的設定皆會修改垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-120">When you modify an anti-spam policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="8acc9-121">所有其他設定都會修改相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-121">All other settings modify the associated spam filter policy.</span></span>
- <span data-ttu-id="8acc9-122">當您移除反垃圾郵件原則時，也會一併移除垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-122">When you remove an anti-spam policy, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="8acc9-123">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-123">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="8acc9-124">如需其他更多資訊，請參照本文章稍後的 [「使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定反垃圾郵件原則」](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) 章節。</span><span class="sxs-lookup"><span data-stu-id="8acc9-124">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) section later in this article.</span></span>

<span data-ttu-id="8acc9-125">每個組織都有一個名為「預設」的內建反垃圾郵件原則，且具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8acc9-125">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="8acc9-126">即使沒有與此原則相關聯的垃圾郵件篩選規則 (收件者篩選器)，此原則仍會套用至組織中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="8acc9-126">The policy is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="8acc9-127">此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="8acc9-127">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="8acc9-128">任何您建立的自訂原則皆具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="8acc9-128">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="8acc9-129">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-129">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="8acc9-130">若要提高垃圾郵件篩選的效率，您可以建立自訂反垃圾郵件原則，以更嚴格的設定套用到特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="8acc9-130">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8acc9-131">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="8acc9-131">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8acc9-132">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="8acc9-132">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="8acc9-133">若要直接移至 [反垃圾郵件原則 **]** 頁面，請使用 <https://security.microsoft.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="8acc9-133">To go directly to the **Anti-spam policies** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="8acc9-134">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-134">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8acc9-135">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-135">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8acc9-136">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="8acc9-136">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8acc9-137">若要新增、修改、刪除反垃圾郵件原則，您必須是 **組織管理** 或 **安全性系統管理員** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8acc9-137">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8acc9-138">若要唯讀存取反垃圾郵件原則，您必須是 **全域讀取者** 或 **安全性讀取者** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8acc9-138">For read-only access to anti-spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8acc9-139">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-139">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="8acc9-140">**附註**：</span><span class="sxs-lookup"><span data-stu-id="8acc9-140">**Notes**:</span></span>

  - <span data-ttu-id="8acc9-141">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="8acc9-141">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8acc9-142">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-142">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8acc9-143">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="8acc9-143">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="8acc9-144">如需反垃圾郵件原則的建議設定，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-144">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a><span data-ttu-id="8acc9-145">使用 Microsoft 365 Defender 入口網站建立反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-145">Use the Microsoft 365 Defender portal to create anti-spam policies</span></span>

<span data-ttu-id="8acc9-146">在 Microsoft 365 Defender 入口網站建立自訂的反垃圾郵件原則時，是同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則，且為兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="8acc9-146">Creating a custom anti-spam policy in the Microsoft 365 Defender portal creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="8acc9-147">在 Microsoft 365 Defender 入口網站中，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則]** 選擇\> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8acc9-148">在 **反垃圾郵件原則** 頁面，按一下![建立圖示](../../media/m365-cc-sc-create-icon.png) **建立原則**，然後從下拉式選單中選取 **輸入**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-148">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Inbound** from the drop down list.</span></span>

3. <span data-ttu-id="8acc9-149">原則精靈隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="8acc9-149">The policy wizard opens.</span></span> <span data-ttu-id="8acc9-150">在 [命名您的原則 **]** 頁面上，設定這些設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-150">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="8acc9-151">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="8acc9-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="8acc9-152">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="8acc9-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="8acc9-153">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8acc9-154">在顯示的 [使用者、群組和網域 **]** 頁面上，識別原則適用的內部收件者 (收件者條件)：</span><span class="sxs-lookup"><span data-stu-id="8acc9-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="8acc9-155">**使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="8acc9-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="8acc9-156">**群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="8acc9-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="8acc9-157">**網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="8acc9-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="8acc9-158">按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="8acc9-159">視需要重複此程序多次。</span><span class="sxs-lookup"><span data-stu-id="8acc9-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="8acc9-160">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="8acc9-160">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="8acc9-162">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="8acc9-162">next to the value.</span></span>

   <span data-ttu-id="8acc9-163">針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="8acc9-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="8acc9-164">針對使用者，接著輸入星號 (\*) 來查看所有可用的值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="8acc9-165">相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="8acc9-166">不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="8acc9-167">**排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。</span><span class="sxs-lookup"><span data-stu-id="8acc9-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="8acc9-168">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="8acc9-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="8acc9-169">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8acc9-170">在 [大量電子郵件閾值與垃圾郵件屬性 **]** 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-170">On the **Bulk email threshold & spam properties** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8acc9-171">**大量電子郵件閾值**：針對您在下一個頁面上設定、會觸發 **大量** 垃圾郵件篩選決策指定動作的訊息，指定大量抱怨層級 (BCL)，(大於、不大於或等於指定的值)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-171">**Bulk email threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk** spam filtering verdict that you configure on the next page (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="8acc9-172">較高的值表示不太理想的郵件 (更可能像是垃圾郵件)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-172">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="8acc9-173">預設值為 7。</span><span class="sxs-lookup"><span data-stu-id="8acc9-173">The default value is 7.</span></span> <span data-ttu-id="8acc9-174">如需詳細資訊，請參閱 [EOP 中的大量抱怨層級 (BCL)](bulk-complaint-level-values.md) 和[垃圾電子郵件與大量電子郵件之間有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-174">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="8acc9-175">根據預設，PowerShell 只會將反垃圾郵件原則中的 MarkAsSpamBulkMail 設定為 `On`。</span><span class="sxs-lookup"><span data-stu-id="8acc9-175">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="8acc9-176">此設定會大幅影響 **大量** 篩選決策的結果：</span><span class="sxs-lookup"><span data-stu-id="8acc9-176">This setting dramatically affects the results of a **Bulk** filtering verdict:</span></span>

     - <span data-ttu-id="8acc9-177">**_MarkAsSpamBulkMail_ 為 On**：大於閾值的 BCL 會轉換成 SCL 6 (對應到 **垃圾郵件** 篩選決策)，然後對郵件採取 **大量** 篩選決策的動作。</span><span class="sxs-lookup"><span data-stu-id="8acc9-177">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk** filtering verdict is taken on the message.</span></span>
     - <span data-ttu-id="8acc9-178">**_MarkAsSpamBulkMail_ 為 Off**：郵件會加上 BCL 戳記，但 _不會_ 對 **大量** 篩選決策執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="8acc9-178">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk** filtering verdict.</span></span> <span data-ttu-id="8acc9-179">實際上，BCL 閾值和 **大量** 篩選決策動作並不相關。</span><span class="sxs-lookup"><span data-stu-id="8acc9-179">In effect, the BCL threshold and **Bulk** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="8acc9-180">**增加垃圾郵件分數**、**標記為垃圾郵件**<sup>\*</sup>和 **測試模式**：包含預設關閉的進階垃圾郵件篩選 (ASF) 設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-180">**Increase spam score**, **Mark as spam**<sup>\*</sup> and **Test mode**: Contains the Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="8acc9-181">我們正逐漸淘汰 ASF 設定，其功能正併入篩選堆疊的其他部分。</span><span class="sxs-lookup"><span data-stu-id="8acc9-181">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="8acc9-182">建議您將反垃圾郵件原則中的所有 ASF 設定關閉。</span><span class="sxs-lookup"><span data-stu-id="8acc9-182">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

     <span data-ttu-id="8acc9-183">如需有關這些設定的詳細資訊，請參閱 [EOP 中的進階垃圾郵件篩選設定](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-183">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

      <span data-ttu-id="8acc9-184"><sup>\*</sup> [包含特定語言 **]** 和 [來自這些國家/地區 **]** 不屬於 ASF 設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="8acc9-184"><sup>\*</sup> **Contains specific languages** and **from these countries** are not part of ASF settings.</span></span>

   - <span data-ttu-id="8acc9-185">**包含特定語言**：按一下方塊，然後從下拉式清單中選取 [**開啟**] 或 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="8acc9-185">**Contains specific languages**: Click the box and select **On** or **Off** from the drop down list.</span></span> <span data-ttu-id="8acc9-186">如果您將它開啟，會顯示一個方塊。</span><span class="sxs-lookup"><span data-stu-id="8acc9-186">If you turn it on, a box appears.</span></span> <span data-ttu-id="8acc9-187">開始在方塊中輸入語言的名稱。</span><span class="sxs-lookup"><span data-stu-id="8acc9-187">Start typing the name of a language in the box.</span></span> <span data-ttu-id="8acc9-188">已篩選的支援語言清單將會顯示。</span><span class="sxs-lookup"><span data-stu-id="8acc9-188">A filtered list of supported languages will appear.</span></span> <span data-ttu-id="8acc9-189">當您找到所需語言時，請選取該語言。</span><span class="sxs-lookup"><span data-stu-id="8acc9-189">When you find the language that you're looking for, select it.</span></span> <span data-ttu-id="8acc9-190">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="8acc9-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8acc9-191">若要移除現有的值，請按一下值旁邊的 ![移除圖示](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-191">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   - <span data-ttu-id="8acc9-192">**來自這些國家/地區**：按一下方塊，然後從下拉式清單中選取 [*開啟*]\* 或 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="8acc9-192">**From these countries** _: Click the box and select _ *On*\* or **Off** from the drop down list.</span></span> <span data-ttu-id="8acc9-193">如果您將它開啟，會顯示一個方塊。</span><span class="sxs-lookup"><span data-stu-id="8acc9-193">If you turn it on, a box appears.</span></span> <span data-ttu-id="8acc9-194">開始在方塊中輸入國家/地區的名稱。</span><span class="sxs-lookup"><span data-stu-id="8acc9-194">Start typing the name of a country in the box.</span></span> <span data-ttu-id="8acc9-195">已篩選的支援國家/地區清單將會顯示。</span><span class="sxs-lookup"><span data-stu-id="8acc9-195">A filtered list of supported countries will appear.</span></span> <span data-ttu-id="8acc9-196">當您找到您要尋找的國家/地區時，請選取它。</span><span class="sxs-lookup"><span data-stu-id="8acc9-196">When you find the country that you're looking for, select it.</span></span> <span data-ttu-id="8acc9-197">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="8acc9-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8acc9-198">若要移除現有的值，請按一下值旁邊的 ![移除圖示](../../media/m365-cc-sc-remove-selection-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-198">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   <span data-ttu-id="8acc9-199">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-199">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="8acc9-200">在顯示的 [動作 **]** 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-200">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8acc9-201">**郵件動作**：根據下列垃圾郵件篩選決策，來選取或檢閱要對郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="8acc9-201">**Message actions**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>
     - <span data-ttu-id="8acc9-202">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="8acc9-202">**Spam**</span></span>
     - <span data-ttu-id="8acc9-203">**高信賴度的垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="8acc9-203">**High confidence spam**</span></span>
     - <span data-ttu-id="8acc9-204">**網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="8acc9-204">**Phishing**</span></span>
     - <span data-ttu-id="8acc9-205">**高信賴度網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="8acc9-205">**High confidence phishing**</span></span>
     - <span data-ttu-id="8acc9-206">**大量**</span><span class="sxs-lookup"><span data-stu-id="8acc9-206">**Bulk**</span></span>

     <span data-ttu-id="8acc9-207">下表說明垃圾郵件篩選裁決可採取的動作。</span><span class="sxs-lookup"><span data-stu-id="8acc9-207">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="8acc9-208">核取記號 (</span><span class="sxs-lookup"><span data-stu-id="8acc9-208">A check mark (</span></span> ![核取記號](../../media/checkmark.png)<span data-ttu-id="8acc9-210">) 表示可採取的動作 (並非所有的決策皆可採取所有動作)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-210">) indicates the action is available (not all actions are available for all verdicts).</span></span>
     - <span data-ttu-id="8acc9-211">核取記號之後有星號 (<sup>\*</sup>) 表示垃圾郵件篩選裁決的預設動作。</span><span class="sxs-lookup"><span data-stu-id="8acc9-211">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     <br>

     ****

     |<span data-ttu-id="8acc9-212">動作</span><span class="sxs-lookup"><span data-stu-id="8acc9-212">Action</span></span>|<span data-ttu-id="8acc9-213">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="8acc9-213">Spam</span></span>|<span data-ttu-id="8acc9-214">高</span><span class="sxs-lookup"><span data-stu-id="8acc9-214">High</span></span><br><span data-ttu-id="8acc9-215">信賴度</span><span class="sxs-lookup"><span data-stu-id="8acc9-215">confidence</span></span><br><span data-ttu-id="8acc9-216">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="8acc9-216">spam</span></span>|<span data-ttu-id="8acc9-217">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="8acc9-217">Phishing</span></span>|<span data-ttu-id="8acc9-218">高</span><span class="sxs-lookup"><span data-stu-id="8acc9-218">High</span></span><br><span data-ttu-id="8acc9-219">信賴度</span><span class="sxs-lookup"><span data-stu-id="8acc9-219">confidence</span></span><br><span data-ttu-id="8acc9-220">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="8acc9-220">phishing</span></span>|<span data-ttu-id="8acc9-221">大量</span><span class="sxs-lookup"><span data-stu-id="8acc9-221">Bulk</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="8acc9-222">**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-222">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="8acc9-223">![核取記號](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-223">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="8acc9-224">![核取記號](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-224">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|<span data-ttu-id="8acc9-227">![核取記號](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-227">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="8acc9-228">**新增 X 標頭**：在郵件標頭中新增 X 標頭，並將郵件傳送到信箱。</span><span class="sxs-lookup"><span data-stu-id="8acc9-228">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <p> <span data-ttu-id="8acc9-229">您稍後可以在 [新增此 X 標頭文字] 方塊中輸入 X 標頭欄位的名稱 (不是值)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-229">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <p> <span data-ttu-id="8acc9-230">裁決為 **垃圾郵件** 和 **高信賴度垃圾郵件** 的郵件會移至 [垃圾郵件] 資料夾。<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-230">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)||<span data-ttu-id="8acc9-234">![核取記號](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-234">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="8acc9-235">**在主旨列前加上文字**：新增文字至郵件主旨列的開頭。</span><span class="sxs-lookup"><span data-stu-id="8acc9-235">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="8acc9-236">郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-236">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <p> <span data-ttu-id="8acc9-237">您稍後可以在 [在主旨列前加上此文字] 方塊中輸入文字。</span><span class="sxs-lookup"><span data-stu-id="8acc9-237">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)||![核取記號](../../media/checkmark.png)|
     |<span data-ttu-id="8acc9-242">**將郵件重新導向至電子郵件地址**：將郵件傳送給其他收件者，而不是預定收件者。</span><span class="sxs-lookup"><span data-stu-id="8acc9-242">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <p> <span data-ttu-id="8acc9-243">您稍後可以在 [重新導向到這個電子郵件地址] 方塊中指定收件者。</span><span class="sxs-lookup"><span data-stu-id="8acc9-243">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
     |<span data-ttu-id="8acc9-249">**刪除郵件**：刪除整封郵件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="8acc9-249">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)||![核取記號](../../media/checkmark.png)|
     |<span data-ttu-id="8acc9-254">**隔離郵件**：將郵件傳送到隔離信箱，而不是傳送給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="8acc9-254">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <p> <span data-ttu-id="8acc9-255">您稍後可以在 [隔離] 方塊中指定郵件要在隔離區保留多久。</span><span class="sxs-lookup"><span data-stu-id="8acc9-255">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|<span data-ttu-id="8acc9-258">![核取記號](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8acc9-258">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
     |<span data-ttu-id="8acc9-261">**無動作**</span><span class="sxs-lookup"><span data-stu-id="8acc9-261">**No action**</span></span>|||||![核取記號](../../media/checkmark.png)|
     |

     > <span data-ttu-id="8acc9-263"><sup>1</sup> 在 Exchange Online 中，如果信箱已啟用垃圾郵件規則 (預設為啟用)，郵件會移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8acc9-263"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="8acc9-264">如需詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-264">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="8acc9-265">在 EOP 會保護內部部署 Exchange 信箱的混合式環境中，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8acc9-265">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="8acc9-266">如需詳細資訊，請參閱[設定 EOP 以將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-266">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span>
     >
     > <span data-ttu-id="8acc9-267"><sup>2</sup> 您可以使用此值做為郵件流程規則的條件，以便篩選或傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="8acc9-267"><sup>2</sup> You can this use value as a condition in mail flow rules to filter or route the message.</span></span>

   - <span data-ttu-id="8acc9-268">**在此天數內保留隔離的垃圾郵件**：指定當您選取 **隔離郵件** 做為垃圾郵件篩選決策的動作時，郵件將存放在隔離中要多久的時間。</span><span class="sxs-lookup"><span data-stu-id="8acc9-268">**Retain spam in quarantine for this many days**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8acc9-269">時間到了之後，就會刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="8acc9-269">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="8acc9-270">預設值是 30 天。</span><span class="sxs-lookup"><span data-stu-id="8acc9-270">The default value is 30 days.</span></span> <span data-ttu-id="8acc9-271">有效值是從 1 到 30 天。</span><span class="sxs-lookup"><span data-stu-id="8acc9-271">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="8acc9-272">如需隔離的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="8acc9-272">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="8acc9-273">EOP 中的隔離郵件</span><span class="sxs-lookup"><span data-stu-id="8acc9-273">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="8acc9-274">在 EOP 中管理隔離的郵件與檔案</span><span class="sxs-lookup"><span data-stu-id="8acc9-274">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="8acc9-275">在 EOP 中尋找及釋出隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="8acc9-275">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="8acc9-276">**新增此 X 標題文字**：只有當您選取 [新增 X 標頭] 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-276">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8acc9-277">您指定的值是郵件標頭「名稱」，會新增到郵件標頭中。</span><span class="sxs-lookup"><span data-stu-id="8acc9-277">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="8acc9-278">標題欄位的「值」一律是 `This message appears to be spam`。</span><span class="sxs-lookup"><span data-stu-id="8acc9-278">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="8acc9-279">長度上限為 255 個字元，且值不能包含空格或冒號 (:)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-279">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="8acc9-280">例如，如果輸入 `X-This-is-my-custom-header` 值，則新增到郵件的 X 標頭為 `X-This-is-my-custom-header: This message appears to be spam.`。</span><span class="sxs-lookup"><span data-stu-id="8acc9-280">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="8acc9-281">如果您輸入的值包含空格或冒號 (:)，系統會忽略您輸入的值，並在郵件中新增預設的 X 標頭 (`X-This-Is-Spam: This message appears to be spam.`)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-281">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="8acc9-282">**在主旨列前加上此文字**：只有當您選取 [在主旨列前加上文字] 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-282">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8acc9-283">輸入要新增至郵件主旨列開頭的文字。</span><span class="sxs-lookup"><span data-stu-id="8acc9-283">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="8acc9-284">**重新導向到這個電子郵件地址**：只有當您選取 [將郵件重新導向至電子郵件地址] 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-284">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8acc9-285">輸入您要遞送郵件的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8acc9-285">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="8acc9-286">您可以輸入多個值並以分號 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="8acc9-286">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="8acc9-287">**啟用安全提示**：預設會啟用安全提示，但您可以清除核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="8acc9-287">**Enable safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the checkbox.</span></span> <span data-ttu-id="8acc9-288">如需有關安全性提示的詳細資訊，請參閱[電子郵件的安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-288">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   - <span data-ttu-id="8acc9-289">**啟用零時差自動清除 (ZAP)**：ZAP 會偵測傳送到 Exchange Online 信箱的郵件，並採取行動。</span><span class="sxs-lookup"><span data-stu-id="8acc9-289">**Enable zero-hour auto purge (ZAP)**: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="8acc9-290">如需詳細資訊，請參閱[零時差自動清除 - 防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-290">For more information, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

     <span data-ttu-id="8acc9-291">ZAP 預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="8acc9-291">ZAP is turned on by default.</span></span> <span data-ttu-id="8acc9-292">當 ZAP 開啟時，可以使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-292">When ZAP is turned on, the following settings are available:</span></span>

     - <span data-ttu-id="8acc9-293">**針對網路釣魚郵件啟用 ZAP**：預設會啟用 ZAP 以偵測網路釣魚，但您可以清除核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="8acc9-293">**Enable ZAP for phishing messages**: By default, ZAP is enabled for phishing detections, but you can disable it by clearing the checkbox.</span></span>
     - <span data-ttu-id="8acc9-294">**針對垃圾郵件啟用 ZAP**：預設會啟用 ZAP 以偵測垃圾郵件，但您可以清除核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="8acc9-294">**Enable ZAP for spam messages**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the checkbox.</span></span>

   - <span data-ttu-id="8acc9-295">**啟用使用者垃圾郵件通知**：如需詳細資訊，請參閱本主題稍後的 [設定使用者垃圾郵件通知](#configure-end-user-spam-notifications)一節。</span><span class="sxs-lookup"><span data-stu-id="8acc9-295">**Enable end-user spam notifications**: For more information, see the [Configure end-user spam notifications](#configure-end-user-spam-notifications) section later in this topic.</span></span>

   <span data-ttu-id="8acc9-296">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-296">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="8acc9-297">在顯示的 [允許與封鎖清單 **]** 飛出視窗上，您可以根據允許略過垃圾郵件篩選的電子郵件地址或電子郵件網域來設定郵件寄件者。</span><span class="sxs-lookup"><span data-stu-id="8acc9-297">On the **Allow & block list** flyout that appears, you are able to configure message senders by email address or email domain that are allowed to skip spam filtering.</span></span>

   <span data-ttu-id="8acc9-298">在 [允許 **]** 區段，您可以設定允許的寄件者和允許的網域。</span><span class="sxs-lookup"><span data-stu-id="8acc9-298">In the **Allowed** section, you can configure allowed senders and allowed domains.</span></span> <span data-ttu-id="8acc9-299">在 [封鎖 **]** 區段，您可以新增封鎖的寄件者和封鎖的網域。</span><span class="sxs-lookup"><span data-stu-id="8acc9-299">In the **Blocked** section, you can add blocked senders and blocked domains.</span></span>

   > [!IMPORTANT]
   >
   > <span data-ttu-id="8acc9-300">在將網域新增到允許的網域清單之前，請仔細考慮。</span><span class="sxs-lookup"><span data-stu-id="8acc9-300">Think very carefully before you add domains to the allowed domains list.</span></span> <span data-ttu-id="8acc9-301">如需詳細資訊，請參閱[在 EOP 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-301">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > <span data-ttu-id="8acc9-302">絕對不要將您自己的[公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)或一般網域 (例如 microsoft.com 或 office.com) 新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="8acc9-302">Never add your own [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="8acc9-303">如果允許這些網域略過垃圾郵件篩選，則會允許攻擊者輕鬆地將電子郵件傳送至您的組織。</span><span class="sxs-lookup"><span data-stu-id="8acc9-303">If these domains are allowed to bypass spam filtering, allow attackers an easily send email into your organization.</span></span>
   >
   > <span data-ttu-id="8acc9-304">將網域新增到封鎖的網域清單以手動封鎖網域並不危險，但會增加您的管理工作量。</span><span class="sxs-lookup"><span data-stu-id="8acc9-304">Manually blocking domains by adding the domains to the blocked domains list isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="8acc9-305">如需詳細資訊，請參閱[在 EOP 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-305">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>
   >
   > <span data-ttu-id="8acc9-306">有時我們的篩選器會錯過郵件、您不同意篩選決策，或者我們的系統需要時間才能跟上。</span><span class="sxs-lookup"><span data-stu-id="8acc9-306">There will be times when our filters will miss a message, you don't agree with the filtering verdict, or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="8acc9-307">在這些情況下，允許清單和封鎖清單可用於取代目前的篩選決策。</span><span class="sxs-lookup"><span data-stu-id="8acc9-307">In these cases, the allow list and block list are available to override the current filtering verdicts.</span></span> <span data-ttu-id="8acc9-308">但是，您應該謹慎且暫時使用這些清單：冗長的清單可能會變得無法管理，而我們的篩選堆疊應該執行它預期該執行的工作。</span><span class="sxs-lookup"><span data-stu-id="8acc9-308">But, you should use these lists sparingly and temporarily: longs lists can become unmanageable, and our filtering stack should be doing what it's supposed to be doing.</span></span> <span data-ttu-id="8acc9-309">如果您要將允許的網域保留一段時間，您應該告訴寄件者驗證其網域是否經過驗證，如果未經驗證，則設為 DMARC 拒絕。</span><span class="sxs-lookup"><span data-stu-id="8acc9-309">If you're going to keep an allowed domain for an extended period of time, you should tell the sender to verify that their domain is authenticated and set to DMARC reject if it's not.</span></span>

   <span data-ttu-id="8acc9-310">將項目新增到任何清單的步驟都相同：</span><span class="sxs-lookup"><span data-stu-id="8acc9-310">The steps to add entries to any of the lists are the same:</span></span>

   1. <span data-ttu-id="8acc9-311">按一下要設定的清單連結：</span><span class="sxs-lookup"><span data-stu-id="8acc9-311">Click the link for the list that you want to configure:</span></span>
      - <span data-ttu-id="8acc9-312">**允許** \> **寄件者**：按一下 [管理 (nn) 寄件者 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-312">**Allowed** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="8acc9-313">**允許** \> **網域**：按一下 [允許網域 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-313">**Allowed** \> **Domains**: Click **Allow domains**.</span></span>
      - <span data-ttu-id="8acc9-314">**封鎖** \> **寄件者**：按一下 [管理 (nn) 寄件者 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-314">**Blocked** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="8acc9-315">**封鎖** \> **網域**：按一下 [封鎖網域 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-315">**Blocked** \> **Domains**: Click **Block domains**.</span></span>

   2. <span data-ttu-id="8acc9-316">在顯示的飛出視窗中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8acc9-316">In the flyout that appears, do the following steps:</span></span>
      1. <span data-ttu-id="8acc9-317">按一下 ![建立圖示](../../media/m365-cc-sc-create-icon.png) [新增寄件者 **]** 或 [新增網域 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-317">Click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Add senders** or **Add domains**.</span></span>
      2. <span data-ttu-id="8acc9-318">在 [新增寄件者 **]** 或 [新增網域 **]** 飛出視窗中，於 [寄件者 **]** 方塊或 [網域 **]** 方塊中輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8acc9-318">In the **Add senders** or **Add domains** flyout that appears, enter the sender's email address in the **Sender** box or the domain in the **Domain** box.</span></span> <span data-ttu-id="8acc9-319">當您輸入時，值會顯示在方塊下方。</span><span class="sxs-lookup"><span data-stu-id="8acc9-319">As you're typing, the value appears below the box.</span></span> <span data-ttu-id="8acc9-320">輸入完電子郵件地址或網域後，請選取方塊下方的值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-320">When you're finished typing the email address or domain, select the value below the box.</span></span>
      3. <span data-ttu-id="8acc9-321">視需要重複先前的步驟多次。</span><span class="sxs-lookup"><span data-stu-id="8acc9-321">Repeat the previous step as many times as necessary.</span></span> <span data-ttu-id="8acc9-322">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="8acc9-322">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="8acc9-324">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="8acc9-324">next to the value.</span></span>

      <span data-ttu-id="8acc9-325">完成後，請按一下 [新增寄件者 **]** 或 [新增網域 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-325">When you're finished, click **Add senders** or **Add domains**.</span></span>

      <span data-ttu-id="8acc9-326">回到主要飛出頁面，頁面上會列出您新增的寄件者或網域。</span><span class="sxs-lookup"><span data-stu-id="8acc9-326">Back on the main flyout, the senders or domains that you added are listed on the page.</span></span> <span data-ttu-id="8acc9-327">若要從此頁面移除項目，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8acc9-327">To remove an entry from this page, do the following steps:</span></span>

      1. <span data-ttu-id="8acc9-328">從清單中選取一或多個項目。</span><span class="sxs-lookup"><span data-stu-id="8acc9-328">Select one or more entries from the list.</span></span> <span data-ttu-id="8acc9-329">您也可以使用 [搜尋 **]** 方塊來尋找清單中的值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-329">You can also use the **Search** box to find values in the list.</span></span>
      2. <span data-ttu-id="8acc9-330">選取至少一個項目後，刪除圖示</span><span class="sxs-lookup"><span data-stu-id="8acc9-330">After you select at least one entry, the delete icon</span></span> ![[刪除] 圖示](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="8acc9-332">隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="8acc9-332">appears.</span></span>
      3. <span data-ttu-id="8acc9-333">按一下 [刪除] 圖示</span><span class="sxs-lookup"><span data-stu-id="8acc9-333">Click the delete icon</span></span> ![[刪除] 圖示](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="8acc9-335">以移除選取的項目。</span><span class="sxs-lookup"><span data-stu-id="8acc9-335">to remove the selected entries.</span></span>

      <span data-ttu-id="8acc9-336">完成後，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-336">When you're finished, click **Done**.</span></span>

      <span data-ttu-id="8acc9-337">回到 [允許與封鎖清單 **]** 頁面，提示時請按 [下一步 **]** 以繼續。</span><span class="sxs-lookup"><span data-stu-id="8acc9-337">Back on the **Allow & block list** page, click **Next** when you're read to continue.</span></span>

8. <span data-ttu-id="8acc9-338">在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-338">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="8acc9-339">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-339">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="8acc9-340">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="8acc9-340">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="8acc9-341">完成時，按一下 [建立 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-341">When you're finished, click **Create**.</span></span>

9. <span data-ttu-id="8acc9-342">在顯示的確認頁面上，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-342">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a><span data-ttu-id="8acc9-343">使用 Microsoft 365 Defender 入口網站檢視反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-343">Use the Microsoft 365 Defender portal to view anti-spam policies</span></span>

1. <span data-ttu-id="8acc9-344">在 Microsoft 365 Defender 入口網站中，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則]** 選擇\> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-344">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8acc9-345">在 [**反垃圾郵件原則**] 頁面上，尋找下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="8acc9-345">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="8acc9-346">[類型 **]** 值為 [自訂反垃圾郵件原則 **]**</span><span class="sxs-lookup"><span data-stu-id="8acc9-346">The **Type** value is **Custom anti-spam policy**</span></span>
   - <span data-ttu-id="8acc9-347">[名稱 **]** 值為 [反垃圾郵件輸入原則 (預設值)**]**</span><span class="sxs-lookup"><span data-stu-id="8acc9-347">The **Name** value is **Anti-spam inbound policy (Default)**</span></span>

   <span data-ttu-id="8acc9-348">反垃圾郵件原則清單中會顯示下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8acc9-348">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="8acc9-349">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8acc9-349">**Name**</span></span>
   - <span data-ttu-id="8acc9-350">**狀態**</span><span class="sxs-lookup"><span data-stu-id="8acc9-350">**Status**</span></span>
   - <span data-ttu-id="8acc9-351">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="8acc9-351">**Priority**</span></span>
   - <span data-ttu-id="8acc9-352">**類型**</span><span class="sxs-lookup"><span data-stu-id="8acc9-352">**Type**</span></span>

3. <span data-ttu-id="8acc9-353">當您按一下名稱以選取反垃圾郵件原則時，該原則設定會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="8acc9-353">When you select an anti-spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a><span data-ttu-id="8acc9-354">使用 Microsoft 365 Defender 入口網站修改反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-354">Use the Microsoft 365 Defender portal to modify anti-spam policies</span></span>

1. <span data-ttu-id="8acc9-355">在 Microsoft 365 Defender 入口網站中，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則]** 選擇\> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-355">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8acc9-356">在 [反垃圾郵件原則 **]** 頁面上，按一下清單中的名稱，以從中選取反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="8acc9-356">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="8acc9-357">您建立的自訂原則的 [類型 **]** 資料行中的值是 [自訂的反垃圾郵件原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-357">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="8acc9-358">預設原則名為 **反垃圾郵件輸入原則 (預設值)**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-358">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="8acc9-359">在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-359">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="8acc9-360">如需設定的詳細資訊，請參閱本文章中的[使用 Microsoft 365 Defender 入口網站來建立反垃圾郵件原則](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="8acc9-360">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create anti-spam policies](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) section in this article.</span></span>

   <span data-ttu-id="8acc9-361">若是預設反垃圾郵件原則，則無法使用 [套用至 **]** 區段 (原則會套用至每個人)，而且您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-361">For the default anti-spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="8acc9-362">若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="8acc9-362">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="8acc9-363">啟用或停用反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-363">Enable or disable anti-spam policies</span></span>

<span data-ttu-id="8acc9-364">您無法停用預設的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-364">You can't disable the default anti-spam policy.</span></span>

1. <span data-ttu-id="8acc9-365">在 Microsoft 365 Defender 入口網站中，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則]** 選擇\> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-365">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8acc9-366">在 [反垃圾郵件原則 **]** 頁面上，按一下名稱以從清單中選取具有 [類型值 **]** 為 [自訂反垃圾郵件 **]** 的規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-366">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="8acc9-367">在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="8acc9-367">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="8acc9-368">**原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-368">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="8acc9-369">**原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-369">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="8acc9-370">在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-370">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="8acc9-371">按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-371">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="8acc9-372">回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-372">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="8acc9-373">設定自訂反垃圾郵件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="8acc9-373">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="8acc9-374">根據預設，系統是根據反垃圾郵件原則的建立順序給予優先順序 (較新原則的優先順序比較舊原則的優先順序低)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-374">By default, anti-spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="8acc9-375">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="8acc9-375">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="8acc9-376">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="8acc9-376">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="8acc9-377">若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在 Microsoft 365 Defender 入口網站直接修改 [優先順序 **]** 編號)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-377">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="8acc9-378">只有在您有多個原則時，變更原則的優先順序才有意義。</span><span class="sxs-lookup"><span data-stu-id="8acc9-378">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="8acc9-379">**附註**：</span><span class="sxs-lookup"><span data-stu-id="8acc9-379">**Notes**:</span></span>

- <span data-ttu-id="8acc9-380">在 Microsoft 365 Defender 入口網站中，您只能在建立反垃圾郵件原則後變更它的優先順序。</span><span class="sxs-lookup"><span data-stu-id="8acc9-380">In the Microsoft 365 Defender portal, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="8acc9-381">在 PowerShell 中，您可以在建立垃圾郵件篩選規則時覆寫預設優先順序 (這會影響現有規則的優先順序)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-381">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="8acc9-382">反垃圾郵件原則會以其顯示的順序處理 (第一個原則的 **優先順序** 值為 0)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-382">Anti-spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="8acc9-383">預設反垃圾郵件原則的優先順序值為 **最低**，因此無法變更它。</span><span class="sxs-lookup"><span data-stu-id="8acc9-383">The default anti-spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="8acc9-384">在 Microsoft 365 Defender 入口網站中，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則]** 選擇\> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-384">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8acc9-385">在 [反垃圾郵件原則 **]** 頁面上，按一下名稱以從清單中選取具有 [類型值 **]** 為 [自訂反垃圾郵件 **]** 的規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-385">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="8acc9-386">在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：</span><span class="sxs-lookup"><span data-stu-id="8acc9-386">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="8acc9-387">[優先順序 **]** 值為 **0** 的反垃圾郵件原則只有 [降低優先順序 **]** 選項可用。</span><span class="sxs-lookup"><span data-stu-id="8acc9-387">The anti-spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="8acc9-388">具有最低 [優先順序 **]** 值為 (例如 **3**) 的反垃圾郵件原則只有 [增加優先順序 **]** 選項可用。</span><span class="sxs-lookup"><span data-stu-id="8acc9-388">The anti-spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="8acc9-389">如果您有三個或多個反垃圾郵件原則，則最高與最低優先順序值之間的原則，其 [增加優先順序] 和 [降低優先順序] 選項會同時可用。</span><span class="sxs-lookup"><span data-stu-id="8acc9-389">If you have three or more anti-spam policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="8acc9-390">按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-390">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="8acc9-391">完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-391">When you're finished, click **Close** in the policy details flyout.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="8acc9-392">設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="8acc9-392">Configure end-user spam notifications</span></span>

<span data-ttu-id="8acc9-393">當垃圾郵件篩選裁決要隔離郵件時，您可以設定使用者垃圾郵件通知，讓收件者知道寄給他們的郵件發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="8acc9-393">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="8acc9-394">如需有關這些通知的詳細資訊，請參閱 [EOP 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-394">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="8acc9-395">在 Microsoft 365 Defender 入口網站中，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則]** 選擇\> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-395">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8acc9-396">在 [反垃圾郵件原則 **]** 頁面上，按一下清單中的名稱，以從中選取反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="8acc9-396">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="8acc9-397">您建立的自訂原則的 [類型 **]** 資料行中的值是 [自訂的反垃圾郵件原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-397">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="8acc9-398">預設原則名為 **反垃圾郵件輸入原則 (預設值)**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-398">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="8acc9-399">在顯示的原則詳細資料飛出視窗中，按一下 [動作 **]** 中的 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-399">In the policy details flyout that appears, click **Edit** in the **Actions** section.</span></span> <span data-ttu-id="8acc9-400">在顯示的 [動作 **]** 飛出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-400">In the **Actions** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8acc9-401">**啟用使用者垃圾郵件通知**：選取核取方塊以啟用通知，或清除核取方塊以停用通知。</span><span class="sxs-lookup"><span data-stu-id="8acc9-401">**Enable end-user spam notifications**: Select the checkbox to enable notifications or clear the checkbox to disable notifications.</span></span> <span data-ttu-id="8acc9-402">選取核取方塊時，會顯示下列其他設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-402">When you select the checkbox, the following additional settings appear:</span></span>

     - <span data-ttu-id="8acc9-403">**傳送使用者垃圾郵件通知的頻率 (天)**：選取每隔幾天要傳送通知。</span><span class="sxs-lookup"><span data-stu-id="8acc9-403">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="8acc9-404">預設值是 3 天。</span><span class="sxs-lookup"><span data-stu-id="8acc9-404">The default value is 3 days.</span></span> <span data-ttu-id="8acc9-405">您可以輸入 1 到 15 天。</span><span class="sxs-lookup"><span data-stu-id="8acc9-405">You can enter 1 to 15 days.</span></span>

       <span data-ttu-id="8acc9-406">在 24 小時期間內有 3 個使用者垃圾郵件通知週期，從下列時間開始：01:00 UTC、08:00 UTC 和 16:00 UTC。</span><span class="sxs-lookup"><span data-stu-id="8acc9-406">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

       > [!NOTE]
       > <span data-ttu-id="8acc9-407">如果我們錯過了上一個週期的通知，後續週期會推播通知。</span><span class="sxs-lookup"><span data-stu-id="8acc9-407">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="8acc9-408">如此可能會在同一天內呈現多個通知。</span><span class="sxs-lookup"><span data-stu-id="8acc9-408">This might give the appearance of multiple notifications within the same day.</span></span>

     - <span data-ttu-id="8acc9-409">**語言**：按一下下拉式清單並從中選取可用的語言。</span><span class="sxs-lookup"><span data-stu-id="8acc9-409">**Language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="8acc9-410">預設值為 **[預設]**，也就是英文。</span><span class="sxs-lookup"><span data-stu-id="8acc9-410">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="8acc9-411">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="8acc9-411">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="8acc9-412">回到原則詳細資料飛出視窗，按一下 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-412">Back on the policy details flyout, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a><span data-ttu-id="8acc9-413">使用 Microsoft 365 Defender 入口網站移除自訂反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-413">Use the Microsoft 365 Defender portal to remove custom anti-spam policies</span></span>

<span data-ttu-id="8acc9-p151">若您使用 Microsoft 365 Defender 入口網站來移除自訂的反垃圾郵件原則時，會同時刪除垃圾郵件篩選規則與對應的垃圾郵件篩選原則。您無法移除預設的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-p151">When you use the Microsoft 365 Defender portal to remove a custom anti-spam policy, the spam filter rule and the corresponding spam filter policy are both deleted. You can't remove the default anti-spam policy.</span></span>

1. <span data-ttu-id="8acc9-416">在 Microsoft 365 Defender 入口網站中，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則]** 選擇\> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-416">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8acc9-417">在 [反垃圾郵件原則 **]** 頁面上，按一下名稱以從清單中選取具有 [類型值 **]** 為 [自訂反垃圾郵件 **]** 的規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-417">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="8acc9-418">在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-418">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="8acc9-419">在顯示的確認對話方塊中，按一下 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-419">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="8acc9-420">使用 Exchange Online PowerShell 或獨立版 EOP PowerShell 來設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-420">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="8acc9-421">如先前所述，反垃圾郵件原則是由垃圾郵件篩選原則和垃圾郵件篩選規則組成的。</span><span class="sxs-lookup"><span data-stu-id="8acc9-421">As previously described, an anti-spam policy consists of a spam filter policy and a spam filter rule.</span></span>

<span data-ttu-id="8acc9-422">在 Exchange Online PowerShell 或獨立版 EOP PowerShell 中，垃圾郵件篩選原則與垃圾郵件篩選規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="8acc9-422">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="8acc9-423">您使用 **\*-HostedContentFilterPolicy** Cmdlet 來管理垃圾郵件篩選原則，但使用 **\*-HostedContentFilterRule** Cmdlet 來管理垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-423">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="8acc9-424">在 PowerShell 中，您要先建立垃圾郵件篩選原則，然後再建立垃圾郵件篩選規則來識別將套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-424">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="8acc9-425">在 PowerShell 中，您可以分開修改垃圾郵件篩選原則和垃圾郵件篩選規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-425">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>
- <span data-ttu-id="8acc9-426">當您移除 PowerShell 中的垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會自動移除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="8acc9-426">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

<span data-ttu-id="8acc9-427">下列反垃圾郵件原則設定僅適用於 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="8acc9-427">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="8acc9-428">MarkAsSpamBulkMail 參數預設是 `On`。</span><span class="sxs-lookup"><span data-stu-id="8acc9-428">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="8acc9-429">此設定的效果已在本文章前面的[使用 Microsoft 365 Defender 入口網站來建立本反垃圾郵件原則](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)章節中說明。</span><span class="sxs-lookup"><span data-stu-id="8acc9-429">The effects of this setting were explained in the [Use the Microsoft 365 Defender portal to create anti-spam policies](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) section earlier in this article.</span></span>

- <span data-ttu-id="8acc9-430">使用者垃圾郵件隔離通知的下列設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-430">The following settings for end-user spam quarantine notifications:</span></span>
  - <span data-ttu-id="8acc9-431">DownloadLink 參數，用於顯示或隱藏 Outlook 的垃圾郵件報告工具連結。</span><span class="sxs-lookup"><span data-stu-id="8acc9-431">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>
  - <span data-ttu-id="8acc9-432">EndUserSpamNotificationCustomSubject 參數，您可以用來自訂通知的主旨列。</span><span class="sxs-lookup"><span data-stu-id="8acc9-432">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="8acc9-433">使用 PowerShell 來建立反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-433">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="8acc9-434">在 PowerShell 中建立反垃圾郵件原則需執行兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="8acc9-434">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="8acc9-435">建立垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-435">Create the spam filter policy.</span></span>
2. <span data-ttu-id="8acc9-436">建立垃圾郵件選規則，此規則會指定要套用規則的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-436">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="8acc9-437">**附註**：</span><span class="sxs-lookup"><span data-stu-id="8acc9-437">**Notes**:</span></span>

- <span data-ttu-id="8acc9-438">您可以建立新的垃圾郵件篩選規則，並對其指派未關聯的現有垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-438">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="8acc9-439">垃圾郵件篩選規則無法與多個垃圾郵件篩選原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="8acc9-439">A spam filter rule can't be associated with more than one spam filter policy.</span></span>
- <span data-ttu-id="8acc9-440">您可以使用 PowerShell 對 Microsoft 365 Defender 入口網站中還沒有的新垃圾郵件篩選原則進行下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="8acc9-440">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="8acc9-441">建立「停用」的新原則 (在 **New-HostedContentFilterRule** Cmdlet 中啟用 `$false`)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-441">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="8acc9-442">在建立期間設定原則的優先順序 (在 **New-HostedContentFilterRule** Cmdlet 使用 _Priority_ _\<Number\>_)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-442">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="8acc9-443">您在 PowerShell 中建立的新垃圾郵件篩選原則不會顯示在 Microsoft 365 Defender 入口網站中，直到您將該原則指派到垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-443">A new spam filter policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="8acc9-444">步驟 1：使用 PowerShell 建立垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-444">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="8acc9-445">使用下列語法建立垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="8acc9-445">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="8acc9-446">本範例會建立名為 Contoso Executives 的垃圾郵件篩選原則，並使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="8acc9-446">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="8acc9-447">當垃圾郵件篩選裁決為垃圾郵件或高信賴度垃圾郵件時隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="8acc9-447">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>
- <span data-ttu-id="8acc9-448">BCL 7、8 或 9 會觸發大量垃圾郵件篩選決策的動作。</span><span class="sxs-lookup"><span data-stu-id="8acc9-448">BCL 7, 8, or 9 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

<span data-ttu-id="8acc9-449">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-449">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="8acc9-450">步驟 2：使用 PowerShell 建立垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="8acc9-450">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="8acc9-451">使用下列語法建立垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="8acc9-451">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="8acc9-452">此範例使用下列設定來建立名為 Contoso Executives 的新垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="8acc9-452">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="8acc9-453">名為 Contoso Executives 的垃圾郵件篩選原則會與此規則相關聯。</span><span class="sxs-lookup"><span data-stu-id="8acc9-453">The spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="8acc9-454">此規則會套用至名為 ContosoExecutives Group 的群組成員。</span><span class="sxs-lookup"><span data-stu-id="8acc9-454">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="8acc9-455">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-455">For detailed syntax and parameter information, see [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="8acc9-456">使用 PowerShell 檢視垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-456">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="8acc9-457">若要傳回所有垃圾郵件篩選原則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8acc9-457">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="8acc9-458">若要傳回特定垃圾郵件篩選原則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8acc9-458">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="8acc9-459">此範例會傳回名為 Executives 的垃圾郵件篩選原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-459">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="8acc9-460">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-460">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="8acc9-461">使用 PowerShell 檢視垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="8acc9-461">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="8acc9-462">若要檢視現有的垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8acc9-462">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="8acc9-463">若要傳回所有垃圾郵件篩選規則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8acc9-463">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="8acc9-464">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8acc9-464">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="8acc9-465">若要傳回特定垃圾郵件篩選規則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8acc9-465">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="8acc9-466">此範例會傳回名為 Contoso Executives 的垃圾郵件篩選規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-466">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="8acc9-467">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-467">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="8acc9-468">使用 PowerShell 修改垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-468">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="8acc9-469">除了下列項目外，當您如同本文章前面的[步驟 1：使用 PowerShell 建立垃圾郵件篩選原則](#step-1-use-powershell-to-create-a-spam-filter-policy) 章節所述在 PowerShell 中修改垃圾郵件篩選原則時，會出現相同的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-469">Other than the following items, the same settings are available when you modify a spam filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this article.</span></span>

- <span data-ttu-id="8acc9-470">MakeDefault 可將指定的原則轉換成預設原則 (套用至每個人，一律 **最低** 優先順序，且無法刪除)，但只有當您在 PowerShell 中修改垃圾郵件篩選原則時才能使用。</span><span class="sxs-lookup"><span data-stu-id="8acc9-470">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>
- <span data-ttu-id="8acc9-471">您無法重新命名垃圾郵件篩選原則(**Set-hostedcontentfilterpolicy** Cmdlet 沒有 Name 參數)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-471">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="8acc9-472">當您在 Microsoft 365 Defender 入口網站中重新命名反垃圾郵件原則時，只會重新命名垃圾郵件篩選 _規則_。</span><span class="sxs-lookup"><span data-stu-id="8acc9-472">When you rename an anti-spam policy in the Microsoft 365 Defender portal, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="8acc9-473">使用下列語法修改垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="8acc9-473">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="8acc9-474">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-474">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="8acc9-475">使用 PowerShell 修改垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="8acc9-475">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="8acc9-476">當您用 PowerShell 修改垃圾郵件篩選規則時，唯一無法使用的設定為 Enabled 參數 (可讓您建立停用的規則)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-476">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="8acc9-477">若要啟用或停用現有的垃圾郵件篩選規則，請看下一節。</span><span class="sxs-lookup"><span data-stu-id="8acc9-477">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="8acc9-478">另一方面，當您用 PowerShell 修改垃圾郵件篩選規則時，將無法使用其他設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-478">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="8acc9-479">當您如同本文章前面的 [步驟 2：使用 PowerShell 建立垃圾郵件篩選規則](#step-2-use-powershell-to-create-a-spam-filter-rule) 章節所述建立規則時，會出現相同的設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-479">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="8acc9-480">使用下列語法修改垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="8acc9-480">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="8acc9-481">此範例會將名為 `{Fabrikam Spam Filter}` 的現有垃圾郵件篩選規則重新命名。</span><span class="sxs-lookup"><span data-stu-id="8acc9-481">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}`.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="8acc9-482">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-482">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="8acc9-483">使用 PowerShell 來啟用或停用垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="8acc9-483">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="8acc9-484">使用 PowerShell 啟用或停用垃圾郵件篩選規則，可啟用或停用整個反垃圾郵件原則 (垃圾郵件篩選規則和指派的垃圾郵件篩選原則)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-484">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="8acc9-485">您無法啟用或停用預設的反垃圾郵件原則 (一定一律會套用至所有收件者)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-485">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="8acc9-486">若要在 PowerShell 中啟用或停用垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8acc9-486">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="8acc9-487">此範例會停用名為 Marketing Department 的垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-487">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="8acc9-488">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-488">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="8acc9-489">如需詳細的語法和參數資訊，請參閱 [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-489">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="8acc9-490">使用 PowerShell 設定垃圾郵件篩選規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="8acc9-490">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="8acc9-491">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="8acc9-491">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="8acc9-492">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="8acc9-492">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="8acc9-493">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="8acc9-493">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="8acc9-494">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="8acc9-494">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="8acc9-495">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="8acc9-495">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="8acc9-496">若要在 PowerShell 中設定垃圾郵件篩選規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8acc9-496">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="8acc9-497">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="8acc9-497">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="8acc9-498">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-498">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="8acc9-499">**附註**：</span><span class="sxs-lookup"><span data-stu-id="8acc9-499">**Notes**:</span></span>

- <span data-ttu-id="8acc9-500">若要在建立新規則時設定其優先順序，請使用 **New-HostedContentFilterRule** Cmdlet 上的 Priority 參數。</span><span class="sxs-lookup"><span data-stu-id="8acc9-500">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="8acc9-501">預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，且一律有不可修改的優先順序值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="8acc9-501">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="8acc9-502">使用 PowerShell 移除垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="8acc9-502">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="8acc9-503">當您使用 PowerShell 來移除垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會遭到移除。</span><span class="sxs-lookup"><span data-stu-id="8acc9-503">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="8acc9-504">若要在 PowerShell 中移除垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8acc9-504">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="8acc9-505">此範例會移除名為 Marketing Department 的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-505">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="8acc9-506">如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-506">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="8acc9-507">使用 PowerShell 移除垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="8acc9-507">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="8acc9-508">當您使用 PowerShell 來移除垃圾郵件篩選規則時，對應的垃圾郵件篩選原則不會遭到移除。</span><span class="sxs-lookup"><span data-stu-id="8acc9-508">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="8acc9-509">若要在 PowerShell 中移除垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8acc9-509">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="8acc9-510">此範例會移除名為 Marketing Department 的垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="8acc9-510">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="8acc9-511">如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-511">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8acc9-512">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="8acc9-512">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="8acc9-513">傳送 GTUBE 訊息以測試您的垃圾郵件原則設定</span><span class="sxs-lookup"><span data-stu-id="8acc9-513">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="8acc9-p162">只有當傳送 GTUBE 訊息的電子郵件組織無法掃描輸出的垃圾郵件時，這些步驟才有用。如果會掃描，則您無法傳送測試郵件。</span><span class="sxs-lookup"><span data-stu-id="8acc9-p162">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam. If it does, you can't send the test message.</span></span>

<span data-ttu-id="8acc9-516">未經同意大量電子郵件的一般測試 (GTUBE) 是文字字串，可放入測試郵件中，用於確認貴組織的反垃圾郵件設定。</span><span class="sxs-lookup"><span data-stu-id="8acc9-516">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="8acc9-517">GTUBE 訊息類似於歐洲反電腦病毒協會 (EICAR) 用於測試惡意程式碼設定的文字檔。</span><span class="sxs-lookup"><span data-stu-id="8acc9-517">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="8acc9-518">請在電子郵件中，將下列 GTUBE 文字放在單一行上，不加任何空格或換行：</span><span class="sxs-lookup"><span data-stu-id="8acc9-518">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
