---
title: 設定輸出垃圾郵件篩選
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在 Exchange Online Protection (EOP) 中查看、建立、修改和刪除輸出垃圾郵件原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c2f68cac05f296771fc56d400e95d014811fe03a
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793001"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="a562b-103">在 EOP 中設定輸出垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="a562b-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a562b-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="a562b-104">**Applies to**</span></span>
- [<span data-ttu-id="a562b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a562b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a562b-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="a562b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a562b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a562b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a562b-108">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，則會自動檢查透過 EOP 傳送的輸出電子郵件是否有垃圾郵件和不尋常的傳送活動。</span><span class="sxs-lookup"><span data-stu-id="a562b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="a562b-109">組織中使用者的外寄垃圾郵件通常表示已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="a562b-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="a562b-110">可疑的輸出郵件會標示為垃圾郵件 (不論垃圾郵件信賴等級或 SCL) 並透過[高風險傳遞集](high-risk-delivery-pool-for-outbound-messages.md)區路由傳送，以協助保護服務的信譽， (也就是保留 Microsoft 365 來源電子郵件伺服器，而不是 IP 封鎖清單) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="a562b-111">系統管理員會自動收到可疑的輸出電子郵件活動，並透過 [警示原則](../../compliance/alert-policies.md)封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="a562b-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="a562b-112">EOP 使用輸出垃圾郵件原則做為組織的整體防禦垃圾郵件的一部分。</span><span class="sxs-lookup"><span data-stu-id="a562b-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="a562b-113">如需詳細資訊，請參閱[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="a562b-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="a562b-114">系統管理員可以查看、編輯和設定 (，但不會刪除預設的輸出垃圾郵件原則) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="a562b-115">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a562b-116">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="a562b-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a562b-117">您可以在「Microsoft 365 安全性中心」或「PowerShell (Exchange Online PowerShell 中設定輸出垃圾郵件原則，以 Microsoft 365 具有 Exchange Online 之信箱的組織;組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-117">You can configure outbound spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="a562b-118">EOP 中的外寄垃圾郵件原則基本元素為：</span><span class="sxs-lookup"><span data-stu-id="a562b-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="a562b-119">**輸出垃圾郵件篩選原則**：指定輸出垃圾郵件篩選 verdicts 和通知選項的動作。</span><span class="sxs-lookup"><span data-stu-id="a562b-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="a562b-120">**輸出垃圾郵件篩選規則**：指定原則套用至) 外寄垃圾郵件篩選原則的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="a562b-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="a562b-121">當您在 [安全性中心] 管理輸出垃圾郵件原則時，這兩個元素之間的差異並不明顯。</span><span class="sxs-lookup"><span data-stu-id="a562b-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the security center:</span></span>

- <span data-ttu-id="a562b-122">當您建立原則時，實際上是建立輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="a562b-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a562b-123">當您修改原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改外寄垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="a562b-124">所有其他設定都會修改相關聯的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="a562b-125">當您移除原則時，會移除輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="a562b-126">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a562b-127">如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定輸出垃圾郵件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)一節。</span><span class="sxs-lookup"><span data-stu-id="a562b-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="a562b-128">每個組織都有一個名為 Default 的內建輸出垃圾郵件原則，具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="a562b-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="a562b-129">原則會套用至組織中的所有收件者，即使沒有輸出的垃圾郵件篩選規則 (收件者篩選器，) 與原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="a562b-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a562b-130">此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="a562b-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a562b-131">任何自訂垃圾郵件原則的優先順序一律都高於名為「預設」的原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="a562b-132">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a562b-133">若要增加輸出垃圾郵件篩選的效能，您可以使用套用至特定使用者或使用者群組的更嚴格設定來建立自訂輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a562b-134">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a562b-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a562b-135">您可以開啟安全性中心，網址為 <https://security.microsoft.com/>。</span><span class="sxs-lookup"><span data-stu-id="a562b-135">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="a562b-136">若要直接移至 [反垃圾郵件設定] 頁面，請使用 <https://security.microsoft.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="a562b-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="a562b-137">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a562b-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a562b-138">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a562b-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a562b-139">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="a562b-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a562b-140">若要新增、修改和刪除輸出垃圾郵件原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a562b-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a562b-141">若要唯讀的輸出垃圾郵件原則的存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a562b-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a562b-142">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="a562b-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a562b-143">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a562b-143">**Notes**:</span></span>

  - <span data-ttu-id="a562b-144">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="a562b-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a562b-145">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a562b-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a562b-146">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="a562b-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a562b-147">如需輸出垃圾郵件原則的建議設定，請參閱 [EOP 呼出垃圾郵件篩選原則設定](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="a562b-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="a562b-148">已 **超過名稱電子郵件傳送限制** 的預設 [警示原則](../../compliance/alert-policies.md)、已偵測 **到的可疑電子郵件**，以及 **限制傳送電子郵件的使用者** 已將電子郵件通知傳送給 **TenantAdmins** (**Global admins** 的成員。) 群組關於不尋常的外寄電子郵件活動，以及由於輸出垃圾郵件而封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="a562b-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="a562b-149">如需詳細資訊，請參閱 [確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="a562b-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="a562b-150">建議您使用這些警示原則，而不是在輸出垃圾郵件原則中使用通知選項。</span><span class="sxs-lookup"><span data-stu-id="a562b-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a><span data-ttu-id="a562b-151">使用安全中心建立輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="a562b-151">Use the security center to create outbound spam policies</span></span>

<span data-ttu-id="a562b-152">在 [安全性中心] 中建立自訂的輸出垃圾郵件原則，會同時使用相同的名稱建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-152">Creating a custom outbound spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a562b-153">在 [安全性中心] 中，移至 [**電子郵件 & 協同** 作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="a562b-153">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a562b-154">在 [ **反垃圾郵件原則** ] 頁面上，按一下 [建立 ![ 圖示 ](../../media/m365-cc-sc-create-icon.png) **建立原則** ]，然後從下拉式清單中選取 [ **輸出** ]。</span><span class="sxs-lookup"><span data-stu-id="a562b-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="a562b-155">原則精靈隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="a562b-155">The policy wizard opens.</span></span> <span data-ttu-id="a562b-156">在 [命名您的原則 **]** 頁面上，設定這些設定：</span><span class="sxs-lookup"><span data-stu-id="a562b-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="a562b-157">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="a562b-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="a562b-158">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="a562b-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a562b-159">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a562b-160">在顯示的 [使用者、群組和網域 **]** 頁面上，識別原則適用的內部收件者 (收件者條件)：</span><span class="sxs-lookup"><span data-stu-id="a562b-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="a562b-161">**使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="a562b-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a562b-162">**群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="a562b-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="a562b-163">**網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="a562b-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="a562b-164">按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。</span><span class="sxs-lookup"><span data-stu-id="a562b-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="a562b-165">視需要重複此程序多次。</span><span class="sxs-lookup"><span data-stu-id="a562b-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="a562b-166">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="a562b-166">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a562b-168">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="a562b-168">next to the value.</span></span>

   <span data-ttu-id="a562b-169">針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="a562b-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="a562b-170">針對使用者，接著輸入星號 (\*) 來查看所有可用的值。</span><span class="sxs-lookup"><span data-stu-id="a562b-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="a562b-171">相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="a562b-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a562b-172">不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="a562b-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="a562b-173">**排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。</span><span class="sxs-lookup"><span data-stu-id="a562b-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="a562b-174">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="a562b-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a562b-175">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a562b-176">在開啟的 [ **保護設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a562b-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="a562b-177">**郵件限制**：此區段中的設定會設定從 **Exchange Online** 信箱傳出電子郵件的限制：</span><span class="sxs-lookup"><span data-stu-id="a562b-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="a562b-178">**設定外部郵件限制**：每小時的外部收件者數目上限。</span><span class="sxs-lookup"><span data-stu-id="a562b-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="a562b-179">**設定內部郵件限制**：每小時的最大內部收件者數目。</span><span class="sxs-lookup"><span data-stu-id="a562b-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="a562b-180">**設定每日郵件限制**：每日總收件者數目上限。</span><span class="sxs-lookup"><span data-stu-id="a562b-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="a562b-181">有效的值為0到10000。</span><span class="sxs-lookup"><span data-stu-id="a562b-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="a562b-182">預設值為0，這表示使用服務預設值。</span><span class="sxs-lookup"><span data-stu-id="a562b-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="a562b-183">如需詳細資訊，請參閱傳送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="a562b-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="a562b-184">在方塊中輸入值，或使用方塊上的增加/減少箭號。</span><span class="sxs-lookup"><span data-stu-id="a562b-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="a562b-185">**對達到郵件限制之使用者的限制**：在 [ **保護設定** ] 區段中的任何限制超過時，從下拉式清單中選取動作。</span><span class="sxs-lookup"><span data-stu-id="a562b-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="a562b-186">針對所有動作，使用者指定的收件者 **受到限制傳送電子郵件** 警示原則 (和現在的重複，如果由於此頁面稍後的傳送 **輸出垃圾郵件設定而封鎖，則會通知這些使用者和群組**) 接收電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="a562b-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="a562b-187">**限制使用者傳送郵件，直到下列日期為止**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="a562b-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="a562b-188">傳送電子郵件通知，而且在下一天（根據 UTC 時間）之後，使用者將無法再傳送一封以上的郵件。</span><span class="sxs-lookup"><span data-stu-id="a562b-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="a562b-189">系統管理員無法覆寫此區塊。</span><span class="sxs-lookup"><span data-stu-id="a562b-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="a562b-190">名為「 **使用者限制傳送電子郵件** 的活動警示」會通知系統管理員 (透過電子郵件和「 **查看提醒** 」頁面) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="a562b-191">**當寄件者因** 在原則中傳送輸出垃圾郵件設定而遭到封鎖時，在 [通知特定人員] 中指定的任何收件者也都會收到通知。</span><span class="sxs-lookup"><span data-stu-id="a562b-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="a562b-192">在下一天之後，使用者將無法再傳送任何郵件到以 UTC 時間為基礎。</span><span class="sxs-lookup"><span data-stu-id="a562b-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="a562b-193">系統管理員無法覆寫此區塊。</span><span class="sxs-lookup"><span data-stu-id="a562b-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="a562b-194">**限制使用者傳送郵件**：電子郵件通知已傳送，使用者已新增至 [安全中心] 中的 [ **受限制的使用者**] <https://security.microsoft.com/restrictedusers> ，除非系統管理員從 **受限使用者** 移除電子郵件，否則使用者無法傳送電子郵件。系統管理員從清單中移除使用者後，該天的使用者將不會受到限制。</span><span class="sxs-lookup"><span data-stu-id="a562b-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the security center, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="a562b-195">如需相關指示，請參閱 [在傳送垃圾郵件後移除受限使用者入口網站中的使用者](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="a562b-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="a562b-196">**無動作，只發出警示**：已傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="a562b-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="a562b-197">轉寄 **規則**：使用本節中的設定來控制自動將電子郵件轉送 **Exchange Online 信箱** 傳送至外部寄件者。</span><span class="sxs-lookup"><span data-stu-id="a562b-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="a562b-198">如需詳細資訊，請參閱[在 Microsoft 365 中控制自動外部電子郵件轉接](external-email-forwarding.md)。</span><span class="sxs-lookup"><span data-stu-id="a562b-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="a562b-199">停用自動轉寄功能時，收件者會收到未傳遞回報 (也稱為 NDR 或退回郵件) 如果外部寄件者將電子郵件傳送至已就地進行轉接的信箱。</span><span class="sxs-lookup"><span data-stu-id="a562b-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="a562b-200">如果郵件是由內部寄件者傳送 **，且** 轉寄方法是 [信箱](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) 轉寄 (又稱為 _SMTP 轉送_) ，則內部寄件者會收到 NDR。</span><span class="sxs-lookup"><span data-stu-id="a562b-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="a562b-201">如果因收件匣規則而發生轉接，內部寄件者不會收到 NDR。</span><span class="sxs-lookup"><span data-stu-id="a562b-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="a562b-202">從 [ **自動轉送規則** ] 下拉式清單中選取下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="a562b-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="a562b-203">**自動系統控制**：允許輸出垃圾郵件篩選控制自動外部電子郵件轉發。</span><span class="sxs-lookup"><span data-stu-id="a562b-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="a562b-204">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="a562b-204">This is the default value.</span></span>
     - <span data-ttu-id="a562b-205">**On**：自動外部電子郵件轉寄功能未由原則停用。</span><span class="sxs-lookup"><span data-stu-id="a562b-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="a562b-206">**Off**：原則已停用所有自動外部電子郵件轉接。</span><span class="sxs-lookup"><span data-stu-id="a562b-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="a562b-207">**通知**：使用區段中的設定來設定其他收件者，該收件者應接收可疑輸出電子郵件訊息的副本及通知：</span><span class="sxs-lookup"><span data-stu-id="a562b-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="a562b-208">**傳送超過這些限制的可疑輸出的副本給這些使用者和群組**：此設定會將指定的收件者新增至可疑的輸出郵件的 [密件副本] 欄位。</span><span class="sxs-lookup"><span data-stu-id="a562b-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="a562b-209">此設定僅適用于預設輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="a562b-210">在您建立的自訂輸出垃圾郵件原則中無法運作。</span><span class="sxs-lookup"><span data-stu-id="a562b-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="a562b-211">若要啟用此設定，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a562b-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="a562b-212">在出現的方塊中，按一下方塊中，輸入有效的電子郵件地址，然後按 Enter 或選取方塊下方顯示的完整值。</span><span class="sxs-lookup"><span data-stu-id="a562b-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="a562b-213">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="a562b-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a562b-214">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="a562b-214">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a562b-216">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="a562b-216">next to the value.</span></span>

   - <span data-ttu-id="a562b-217">**如果寄件者因傳送輸出垃圾郵件而遭到封鎖，請通知這些使用者和群組**</span><span class="sxs-lookup"><span data-stu-id="a562b-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="a562b-218">此設定正從輸出垃圾郵件原則中被取代。</span><span class="sxs-lookup"><span data-stu-id="a562b-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="a562b-219">名為「**使用者限制于傳送電子郵件** 的預設 [警示原則](../../compliance/alert-policies.md)」已將電子郵件通知傳送給 **TenantAdmins** (**Global admins**) 群組中的使用者，因為超過 [**收件者限制**] 區段中的限制時，已遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="a562b-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="a562b-220">**強烈建議您在輸出垃圾郵件原則中使用警示原則，而不是此設定，以通知系統管理員和其他使用者**。</span><span class="sxs-lookup"><span data-stu-id="a562b-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="a562b-221">如需相關指示，請參閱 [確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="a562b-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="a562b-222">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a562b-223">在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。</span><span class="sxs-lookup"><span data-stu-id="a562b-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="a562b-224">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="a562b-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a562b-225">您也可以按一下 [ **上一步** ] 或選取嚮導中的特定頁面。</span><span class="sxs-lookup"><span data-stu-id="a562b-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="a562b-226">完成時，按一下 [建立 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="a562b-227">在顯示的確認頁面上，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a><span data-ttu-id="a562b-228">使用安全中心來查看輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="a562b-228">Use the security center to view outbound spam policies</span></span>

1. <span data-ttu-id="a562b-229">在 [安全性中心] 中，移至 [**電子郵件 & 協同** 作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="a562b-229">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a562b-230">在 [ **反垃圾郵件原則** ] 頁面上，尋找下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="a562b-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="a562b-231">**Type** 值為 **自訂輸出垃圾郵件原則**</span><span class="sxs-lookup"><span data-stu-id="a562b-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="a562b-232">**名稱** 值為 **反垃圾郵件輸出原則 (預設)**</span><span class="sxs-lookup"><span data-stu-id="a562b-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="a562b-233">反垃圾郵件原則清單中會顯示下列屬性：</span><span class="sxs-lookup"><span data-stu-id="a562b-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="a562b-234">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a562b-234">**Name**</span></span>
   - <span data-ttu-id="a562b-235">**狀態**</span><span class="sxs-lookup"><span data-stu-id="a562b-235">**Status**</span></span>
   - <span data-ttu-id="a562b-236">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="a562b-236">**Priority**</span></span>
   - <span data-ttu-id="a562b-237">**類型**</span><span class="sxs-lookup"><span data-stu-id="a562b-237">**Type**</span></span>

3. <span data-ttu-id="a562b-238">當您按一下名稱來選取輸出垃圾郵件原則時，會在飛入的視窗中顯示原則設定。</span><span class="sxs-lookup"><span data-stu-id="a562b-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="a562b-239">使用 [安全性中心] 修改輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="a562b-239">Use the security center to modify outbound spam policies</span></span>

1. <span data-ttu-id="a562b-240">在 [安全性中心] 中，移至 [**電子郵件 & 協同** 作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="a562b-240">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a562b-241">在 [ **反垃圾郵件原則** ] 頁面上，按一下 [名稱]，從清單中選取外寄垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="a562b-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="a562b-242">您在 [ **類型** ] 欄中的值為 **自訂輸出垃圾郵件原則** 時所建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="a562b-243">名為 **反垃圾郵件輸出原則的預設原則 (預設)**。</span><span class="sxs-lookup"><span data-stu-id="a562b-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="a562b-244">在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="a562b-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a562b-245">如需這些設定的詳細資訊，請參閱本文中的「 [安全性中心」建立外寄垃圾郵件原則](#use-the-security-center-to-create-outbound-spam-policies) 一節。</span><span class="sxs-lookup"><span data-stu-id="a562b-245">For more information about the settings, see the previous [Use the security center to create outbound spam policies](#use-the-security-center-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="a562b-246">針對預設輸出垃圾郵件原則，[套用 **至** ] 區段無法使用 (原則套用至所有人) ，而且您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="a562b-247">若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="a562b-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="a562b-248">啟用或停用自訂輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="a562b-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="a562b-249">您無法停用預設輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="a562b-250">在 [安全性中心] 中，移至 [**電子郵件 & 協同** 作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="a562b-250">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a562b-251">在 [**反垃圾郵件原則**] 頁面上，按一下 [名稱]，從清單中選取 [**自訂輸出垃圾郵件原則** 的 **類型值**] 的原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a562b-252">在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="a562b-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="a562b-253">**原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="a562b-254">**原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="a562b-255">在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="a562b-256">按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="a562b-257">回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="a562b-258">設定自訂輸出垃圾郵件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="a562b-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="a562b-259">根據預設，輸出垃圾郵件原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a562b-260">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="a562b-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a562b-261">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="a562b-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a562b-262">若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在安全性中心直接修改 [優先順序 **]** 編號)。</span><span class="sxs-lookup"><span data-stu-id="a562b-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="a562b-263">只有在您有多個原則時，變更原則的優先順序才有意義。</span><span class="sxs-lookup"><span data-stu-id="a562b-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="a562b-264">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a562b-264">**Notes**:</span></span>

- <span data-ttu-id="a562b-265">在 [安全性中心] 中，您在建立輸出垃圾郵件原則之後，您只能變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="a562b-265">In the security center, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="a562b-266">在 PowerShell 中，您可以在建立垃圾郵件篩選規則時覆寫預設優先順序 (這會影響現有規則的優先順序)。</span><span class="sxs-lookup"><span data-stu-id="a562b-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="a562b-267">輸出垃圾郵件原則的處理順序會依顯示的順序 (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a562b-268">預設輸出垃圾郵件原則的優先順序值為 **最低**，您無法變更。</span><span class="sxs-lookup"><span data-stu-id="a562b-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="a562b-269">在 [安全性中心] 中，移至 [**電子郵件 & 協同** 作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="a562b-269">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a562b-270">在 [**反垃圾郵件原則**] 頁面上，從清單中選取 [選取具有 **自訂輸出垃圾郵件原則** 的 **類型值** 的原則]，然後按一下名稱。</span><span class="sxs-lookup"><span data-stu-id="a562b-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a562b-271">在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：</span><span class="sxs-lookup"><span data-stu-id="a562b-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="a562b-272">**優先順序** 值為 **0** 的輸出垃圾郵件原則，只會有 [**降低優先順序**] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="a562b-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="a562b-273">具有最低 **優先順序** 值的輸出垃圾郵件原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。</span><span class="sxs-lookup"><span data-stu-id="a562b-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="a562b-274">如果您有三個以上的輸出垃圾郵件原則，則最高和最低的優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="a562b-274">If you have three or more outbound spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="a562b-275">按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。</span><span class="sxs-lookup"><span data-stu-id="a562b-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="a562b-276">完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="a562b-277">使用安全中心來移除自訂輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="a562b-277">Use the security center to remove custom outbound spam policies</span></span>

<span data-ttu-id="a562b-278">當您使用 [安全性中心] 移除自訂輸出垃圾郵件原則時，會同時刪除垃圾郵件篩選規則和對應的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-278">When you use the security center to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="a562b-279">您無法移除預設的輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="a562b-280">在 [安全性中心] 中，移至 [**電子郵件 & 協同** 作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="a562b-280">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a562b-281">在 [**反垃圾郵件原則**] 頁面上，按一下 [名稱]，從清單中選取 [**自訂輸出垃圾郵件原則** 的 **類型值**] 的原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="a562b-282">在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="a562b-283">在顯示的確認對話方塊中，按一下 [是 **]**。</span><span class="sxs-lookup"><span data-stu-id="a562b-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="a562b-284">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="a562b-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="a562b-285">如先前所述，輸出垃圾郵件原則是由輸出垃圾郵件篩選原則和外寄垃圾郵件篩選規則所組成。</span><span class="sxs-lookup"><span data-stu-id="a562b-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="a562b-286">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="a562b-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="a562b-287">您可以使用 **\* -HostedOutboundSpamFilterPolicy** Cmdlet 來管理輸出垃圾郵件篩選原則，也可以使用 **\* -HostedOutboundSpamFilterRule** Cmdlet 來管理輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="a562b-288">在 PowerShell 中，您先建立輸出垃圾郵件篩選原則，然後建立輸出垃圾郵件篩選規則，以識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a562b-289">在 PowerShell 中，您可以分別修改輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="a562b-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="a562b-290">當您從 PowerShell 中移除輸出垃圾郵件篩選原則時，對應的輸出垃圾郵件篩選規則不會自動移除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a562b-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="a562b-291">使用 PowerShell 建立輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="a562b-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="a562b-292">在 PowerShell 中建立輸出垃圾郵件原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="a562b-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a562b-293">建立輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="a562b-294">建立輸出垃圾郵件篩選規則，以指定套用規則的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="a562b-295">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a562b-295">**Notes**:</span></span>

   - <span data-ttu-id="a562b-296">您可以建立新的輸出垃圾郵件篩選規則，並將現有的未關聯輸出垃圾郵件篩選原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="a562b-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="a562b-297">輸出垃圾郵件篩選規則無法與一個以上的輸出垃圾郵件篩選原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="a562b-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="a562b-298">您可以在 [安全性中心] PowerShell 中的新輸出垃圾郵件篩選原則上設定下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="a562b-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
     - <span data-ttu-id="a562b-299">_在_ `$false` **HostedOutboundSpamFilterRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="a562b-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="a562b-300">在 _\<Number\>_ **HostedOutboundSpamFilterRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="a562b-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="a562b-301">在您將原則指派給外寄垃圾郵件篩選規則之前，您在 PowerShell 中建立的新輸出垃圾郵件篩選原則不會顯示在 [安全性中心] 中。</span><span class="sxs-lookup"><span data-stu-id="a562b-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="a562b-302">步驟1：使用 PowerShell 來建立輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="a562b-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="a562b-303">若要建立輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="a562b-304">此範例會建立名為 Contoso 主管的新輸出垃圾郵件篩選原則，並提供下列設定：</span><span class="sxs-lookup"><span data-stu-id="a562b-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="a562b-305">收件者速率限制限制為預設值較小的值。</span><span class="sxs-lookup"><span data-stu-id="a562b-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="a562b-306">如需詳細資訊，請參閱[在 Microsoft 365 選項](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)中傳送限制。</span><span class="sxs-lookup"><span data-stu-id="a562b-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="a562b-307">達到其中一個限制之後，使用者就無法傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="a562b-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="a562b-308">如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a562b-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="a562b-309">步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="a562b-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="a562b-310">若要建立輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a562b-311">此範例會使用下列設定建立名為 Contoso 主管的新輸出垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="a562b-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="a562b-312">名為 Contoso 主管的輸出垃圾郵件篩選原則與規則相關聯。</span><span class="sxs-lookup"><span data-stu-id="a562b-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="a562b-313">此規則會套用至名為 ContosoExecutives Group 的群組成員。</span><span class="sxs-lookup"><span data-stu-id="a562b-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="a562b-314">如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="a562b-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="a562b-315">使用 PowerShell 來查看輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="a562b-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="a562b-316">若要傳回所有輸出垃圾郵件篩選原則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a562b-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="a562b-317">若要傳回特定輸出垃圾郵件篩選原則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="a562b-318">本範例會傳回名為「主管」的輸出垃圾郵件篩選原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="a562b-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="a562b-319">如需詳細的語法及參數資訊，請參閱 [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a562b-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="a562b-320">使用 PowerShell 來查看輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="a562b-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="a562b-321">若要查看現有的輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="a562b-322">若要傳回所有輸出垃圾郵件篩選規則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a562b-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="a562b-323">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a562b-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="a562b-324">若要傳回特定輸出垃圾郵件篩選規則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="a562b-325">此範例會傳回名為 Contoso 主管的輸出垃圾郵件篩選規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="a562b-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="a562b-326">如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="a562b-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="a562b-327">使用 PowerShell 修改輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="a562b-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="a562b-328">當您在 PowerShell 中修改惡意程式碼篩選原則時，如您依照「 [步驟1：使用 PowerShell 建立外寄垃圾郵件篩選原則](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 」一節所述，您在建立原則時，可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="a562b-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="a562b-329">您無法重新命名外寄垃圾郵件篩選原則 (**Set-HostedOutboundSpamFilterPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a562b-330">當您重新命名 security center 中的外寄垃圾郵件原則時，您只是重新命名輸出垃圾郵件篩選 _規則_。</span><span class="sxs-lookup"><span data-stu-id="a562b-330">When you rename an outbound spam policy in the security center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="a562b-331">若要修改輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a562b-332">如需詳細的語法及參數資訊，請參閱 [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a562b-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="a562b-333">使用 PowerShell 修改輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="a562b-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="a562b-334">當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a562b-335">若要啟用或停用現有的輸出垃圾郵件篩選規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="a562b-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="a562b-336">否則，當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="a562b-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="a562b-337">當您建立規則時，如您在本文稍早的 [步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 區段中所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="a562b-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="a562b-338">若要修改輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a562b-339">如需詳細的語法及參數資訊，請參閱 [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="a562b-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="a562b-340">使用 PowerShell 來啟用或停用輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="a562b-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="a562b-341">啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，可啟用或停用輸出垃圾郵件篩選規則和指派的外寄垃圾郵件篩選原則) 的整體輸出垃圾郵件原則 (。</span><span class="sxs-lookup"><span data-stu-id="a562b-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="a562b-342">您無法啟用或停用預設輸出垃圾郵件原則 (永遠永遠套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="a562b-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="a562b-343">若要啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="a562b-344">本範例會停用名為「行銷部門」的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a562b-345">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a562b-346">如需詳細的語法及參數資訊，請參閱 [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="a562b-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="a562b-347">使用 PowerShell 設定輸出垃圾郵件篩選規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="a562b-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="a562b-348">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="a562b-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a562b-349">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="a562b-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a562b-350">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="a562b-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a562b-351">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="a562b-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a562b-352">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="a562b-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a562b-353">若要設定 PowerShell 中的外寄垃圾郵件篩選規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a562b-354">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="a562b-354">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a562b-355">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="a562b-355">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a562b-356">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a562b-356">**Notes**:</span></span>

- <span data-ttu-id="a562b-357">若要在建立新規則時設定其優先順序，請改用 **HostedOutboundSpamFilterRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="a562b-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="a562b-358">外寄的預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，它永遠具有「不可修改的優先順序 **」值。**</span><span class="sxs-lookup"><span data-stu-id="a562b-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="a562b-359">使用 PowerShell 移除輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="a562b-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="a562b-360">當您使用 PowerShell 來移除輸出垃圾郵件篩選原則時，並不會移除對應的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="a562b-361">若要在 PowerShell 中移除輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a562b-362">此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a562b-363">如需詳細的語法及參數資訊，請參閱 [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a562b-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="a562b-364">使用 PowerShell 移除輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="a562b-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="a562b-365">當您使用 PowerShell 移除外寄垃圾郵件篩選規則時，並不會移除對應的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="a562b-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="a562b-366">若要移除 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a562b-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="a562b-367">此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="a562b-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a562b-368">如需詳細的語法及參數資訊，請參閱 [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="a562b-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a562b-369">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a562b-369">For more information</span></span>

<span data-ttu-id="a562b-370">[從 [受限使用者] 入口網站中移除封鎖的使用者](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="a562b-370">[Remove blocked users from the Restricted Users portal](removing-user-from-restricted-users-portal-after-spam.md)</span></span>

[<span data-ttu-id="a562b-371">輸出郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="a562b-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="a562b-372">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="a562b-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="a562b-373">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="a562b-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
