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
ms.openlocfilehash: 742c58a8a94938c5896382a6d53acac127974f02
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288930"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="42ed9-103">在 EOP 中設定輸出垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="42ed9-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="42ed9-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="42ed9-104">**Applies to**</span></span>
- [<span data-ttu-id="42ed9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="42ed9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="42ed9-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="42ed9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="42ed9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42ed9-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="42ed9-108">在使用 Exchange Online 中的信箱或獨立 Exchange Online (Protection 中的 Microsoft 365 組織中，EOP) 不含 Exchange Online 信箱的組織，會自動檢查透過 EOP 傳送的輸出電子郵件是否有垃圾郵件和不尋常的傳送活動。</span><span class="sxs-lookup"><span data-stu-id="42ed9-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="42ed9-109">組織中使用者的外寄垃圾郵件通常表示已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="42ed9-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="42ed9-110">可疑的輸出郵件會標示為垃圾郵件 (不論垃圾郵件信賴等級或 SCL) 並透過 [高風險傳遞集](high-risk-delivery-pool-for-outbound-messages.md) 區路由傳送，以協助保護服務的信譽， (也就是將 Microsoft 365 來源電子郵件伺服器從 IP 封鎖清單) 保留。</span><span class="sxs-lookup"><span data-stu-id="42ed9-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="42ed9-111">系統管理員會自動收到可疑的輸出電子郵件活動，並透過 [警示原則](../../compliance/alert-policies.md)封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="42ed9-112">EOP 使用輸出垃圾郵件原則做為組織的整體防禦垃圾郵件的一部分。</span><span class="sxs-lookup"><span data-stu-id="42ed9-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="42ed9-113">如需詳細資訊，請參閱[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="42ed9-114">系統管理員可以查看、編輯和設定 (，但不會刪除預設的輸出垃圾郵件原則) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="42ed9-115">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="42ed9-116">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="42ed9-117">您可以使用 Exchange Online 中的信箱，在安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中設定輸出垃圾郵件原則;沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="42ed9-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="42ed9-118">EOP 中的外寄垃圾郵件原則基本元素為：</span><span class="sxs-lookup"><span data-stu-id="42ed9-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="42ed9-119">**輸出垃圾郵件篩選原則**：指定輸出垃圾郵件篩選 verdicts 和通知選項的動作。</span><span class="sxs-lookup"><span data-stu-id="42ed9-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="42ed9-120">**輸出垃圾郵件篩選規則**：指定原則套用至) 外寄垃圾郵件篩選原則的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="42ed9-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="42ed9-121">當您在安全性 & 合規性中心管理輸出垃圾郵件原則時，這兩個元素之間的差異並不明顯。</span><span class="sxs-lookup"><span data-stu-id="42ed9-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="42ed9-122">當您建立原則時，實際上是建立輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="42ed9-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="42ed9-123">當您修改原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改外寄垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="42ed9-124">所有其他設定都會修改相關聯的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="42ed9-125">當您移除原則時，會移除輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="42ed9-126">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="42ed9-127">如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定輸出垃圾郵件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 一節。</span><span class="sxs-lookup"><span data-stu-id="42ed9-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="42ed9-128">每個組織都有一個名為 Default 的內建輸出垃圾郵件原則，具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="42ed9-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="42ed9-129">原則會套用至組織中的所有收件者，即使沒有輸出的垃圾郵件篩選規則 (收件者篩選器，) 與原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="42ed9-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="42ed9-130">此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="42ed9-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="42ed9-131">任何自訂垃圾郵件原則的優先順序一律都高於名為「預設」的原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="42ed9-132">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="42ed9-133">若要增加輸出垃圾郵件篩選的效能，您可以使用套用至特定使用者或使用者群組的更嚴格設定來建立自訂輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="42ed9-134">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="42ed9-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="42ed9-135">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="42ed9-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="42ed9-136">若要直接移至 [反垃圾郵件設定] 頁面，請使用 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="42ed9-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="42ed9-137">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="42ed9-138">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="42ed9-139">您必須先獲指派安全性與合規性中心的權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="42ed9-139">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="42ed9-140">若要新增、修改和刪除輸出垃圾郵件原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="42ed9-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="42ed9-141">若要唯讀的輸出垃圾郵件原則的存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="42ed9-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="42ed9-142">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-142">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="42ed9-143">**附註**：</span><span class="sxs-lookup"><span data-stu-id="42ed9-143">**Notes**:</span></span>

  - <span data-ttu-id="42ed9-144">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="42ed9-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="42ed9-145">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="42ed9-146">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="42ed9-146">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="42ed9-147">如需輸出垃圾郵件原則的建議設定，請參閱 [EOP 呼出垃圾郵件篩選原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="42ed9-148">已 **超過名稱電子郵件傳送限制** 的預設 [警示原則](../../compliance/alert-policies.md)、已偵測 **到的可疑電子郵件**，以及 **限制傳送電子郵件的使用者** 已將電子郵件通知傳送給 **TenantAdmins** (**Global admins** 的成員。) 群組關於不尋常的外寄電子郵件活動，以及由於輸出垃圾郵件而封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="42ed9-149">如需詳細資訊，請參閱 [確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="42ed9-150">建議您使用這些警示原則，而不是在輸出垃圾郵件原則中使用通知選項。</span><span class="sxs-lookup"><span data-stu-id="42ed9-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="42ed9-151">使用安全性 & 規範中心建立輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="42ed9-152">在安全性 & 合規性中心建立自訂輸出垃圾郵件原則，會同時使用相同的名稱建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="42ed9-153">在安全性與合規性中心，移至 [威脅管理] \> [原則] \> [反垃圾郵件]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="42ed9-154">在 [ **反垃圾郵件設定** ] 頁面上，按一下 [ **建立輸出原則**]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="42ed9-155">在 [ **輸出垃圾郵件篩選原則** ] 的 [飛出開啟] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="42ed9-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="42ed9-156">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="42ed9-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="42ed9-157">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="42ed9-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="42ed9-158"> (選用) 展開 [ **通知** ] 區段，設定其他應接收副本的使用者，以及可疑外寄電子郵件訊息的通知：</span><span class="sxs-lookup"><span data-stu-id="42ed9-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="42ed9-159">**將可疑的輸出電子郵件的複本傳送給特定人員**：此設定會將指定的使用者當做 Bcc 收件者新增至可疑的輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="42ed9-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="42ed9-160">此設定僅適用于預設輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="42ed9-161">在您建立的自訂輸出垃圾郵件原則中無法運作。</span><span class="sxs-lookup"><span data-stu-id="42ed9-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="42ed9-162">若要啟用此設定：</span><span class="sxs-lookup"><span data-stu-id="42ed9-162">To enable this setting:</span></span>

     1. <span data-ttu-id="42ed9-163">選取 [啟用] 設定的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="42ed9-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="42ed9-164">按一下 [ **新增人員**]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-164">Click **Add people**.</span></span> <span data-ttu-id="42ed9-165">在出現的 [ **新增或移除** 收件者] 浮出控制項中：</span><span class="sxs-lookup"><span data-stu-id="42ed9-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="42ed9-166">輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="42ed9-166">Enter the sender's email address.</span></span> <span data-ttu-id="42ed9-167">您可以指定多個以分號分隔的電子郵件地址 (; ) 或每行一個收件者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="42ed9-168">按一下</span><span class="sxs-lookup"><span data-stu-id="42ed9-168">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="42ed9-170">以加入收件者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-170">to add the recipients.</span></span>

        <span data-ttu-id="42ed9-171">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="42ed9-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="42ed9-172">您新增的收件者會出現在飛入的 [ **收件者清單** ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="42ed9-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="42ed9-173">若要刪除收件者，請按一下 [ ![ 移除] 按鈕 ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="42ed9-174">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="42ed9-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="42ed9-175">若要停用此設定，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="42ed9-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="42ed9-176">**如果寄件者因傳送輸出的垃圾郵件而遭到封鎖，請通知特定人員**：</span><span class="sxs-lookup"><span data-stu-id="42ed9-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="42ed9-177">此設定正從輸出垃圾郵件原則中被取代。</span><span class="sxs-lookup"><span data-stu-id="42ed9-177">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="42ed9-178">名為「**使用者限制于傳送電子郵件** 的預設 [警示原則](../../compliance/alert-policies.md)」已將電子郵件通知傳送給 **TenantAdmins** (**Global admins**) 群組中的使用者，因為超過 [**收件者限制**] 區段中的限制時，已遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="42ed9-178">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="42ed9-179">**強烈建議您在輸出垃圾郵件原則中使用警示原則，而不是此設定，以通知系統管理員和其他使用者**。</span><span class="sxs-lookup"><span data-stu-id="42ed9-179">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="42ed9-180">如需相關指示，請參閱 [確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-180">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="42ed9-181"> (選用) 請展開 [ **收件者限制** ] 區段，以設定可疑輸出電子郵件訊息的限制和動作：</span><span class="sxs-lookup"><span data-stu-id="42ed9-181">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="42ed9-182">這些設定只適用于雲端架構信箱。</span><span class="sxs-lookup"><span data-stu-id="42ed9-182">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="42ed9-183">**每位使用者的收件者數目上限**</span><span class="sxs-lookup"><span data-stu-id="42ed9-183">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="42ed9-184">有效的值為0到10000。</span><span class="sxs-lookup"><span data-stu-id="42ed9-184">A valid value is 0 to 10000.</span></span> <span data-ttu-id="42ed9-185">預設值為0，這表示使用服務預設值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-185">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="42ed9-186">如需詳細資訊，請參閱傳送 [限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-186">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="42ed9-187">**外部每小時限制**：每小時的外部收件者數目上限。</span><span class="sxs-lookup"><span data-stu-id="42ed9-187">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="42ed9-188">**內部每小時限制**：每小時內部收件者的數目上限。</span><span class="sxs-lookup"><span data-stu-id="42ed9-188">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="42ed9-189">**每日限制**：每日總收件者數目上限。</span><span class="sxs-lookup"><span data-stu-id="42ed9-189">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="42ed9-190">**當使用者超過上述限制時的動作**：設定超出任何一位 **收件者限制** 時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="42ed9-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="42ed9-191">針對所有動作，使用者指定的收件者 **受到限制傳送電子郵件** 警示原則 (和現在的重複，當收件者因傳送輸出垃圾郵件原則中的外寄垃圾郵件設定而 **遭到封鎖時，會封鎖特定人員** 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-191">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="42ed9-192">**限制使用者在下列日期之後傳送郵件**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-192">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="42ed9-193">傳送電子郵件通知，而且在下一天（根據 UTC 時間）之後，使用者將無法再傳送一封以上的郵件。</span><span class="sxs-lookup"><span data-stu-id="42ed9-193">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="42ed9-194">系統管理員無法覆寫此區塊。</span><span class="sxs-lookup"><span data-stu-id="42ed9-194">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="42ed9-195">名為「 **使用者限制傳送電子郵件** 的活動警示」會通知系統管理員 (透過電子郵件和「 **查看提醒** 」頁面) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-195">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="42ed9-196">**當寄件者因** 在原則中傳送輸出垃圾郵件設定而遭到封鎖時，在 [通知特定人員] 中指定的任何收件者也都會收到通知。</span><span class="sxs-lookup"><span data-stu-id="42ed9-196">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="42ed9-197">在下一天之後，使用者將無法再傳送任何郵件到以 UTC 時間為基礎。</span><span class="sxs-lookup"><span data-stu-id="42ed9-197">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="42ed9-198">系統管理員無法覆寫此區塊。</span><span class="sxs-lookup"><span data-stu-id="42ed9-198">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="42ed9-199">**限制使用者傳送郵件**：已傳送電子郵件通知，使用者會新增至安全性 & 合規性中心內的 **[受限制的使用者] <https://sip.protection.office.com/restrictedusers>** 入口網站，直到系統管理員將其從 **受限使用者** 入口網站中移除之後，使用者才會傳送電子郵件。系統管理員從清單中移除使用者後，該天的使用者將不會受到限制。</span><span class="sxs-lookup"><span data-stu-id="42ed9-199">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="42ed9-200">如需相關指示，請參閱 [在傳送垃圾郵件後移除受限使用者入口網站中的使用者](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-200">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="42ed9-201">**無動作，只發出警示**：已傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="42ed9-201">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="42ed9-202"> (選用) 展開 **自動** 轉寄區段，以控制使用者自動將電子郵件轉寄給外部寄件者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-202">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="42ed9-203">如需詳細資訊，請參閱 [在 Microsoft 365 中控制自動外部電子郵件轉接](external-email-forwarding.md)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-203">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="42ed9-204">在2020年9月之前，這些設定均可供使用，但未強制執行。</span><span class="sxs-lookup"><span data-stu-id="42ed9-204">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="42ed9-205">這些設定只適用于雲端架構信箱。</span><span class="sxs-lookup"><span data-stu-id="42ed9-205">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="42ed9-206">停用自動轉寄功能時，收件者會收到未傳遞回報 (也稱為 NDR 或退回郵件) 如果外部寄件者將電子郵件傳送至已就地進行轉接的信箱。</span><span class="sxs-lookup"><span data-stu-id="42ed9-206">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="42ed9-207">如果郵件是由內部寄件者傳送 **，且** 轉寄方法是 [信箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) 轉寄 (又稱為 _SMTP 轉送_) ，則內部寄件者會收到 NDR。</span><span class="sxs-lookup"><span data-stu-id="42ed9-207">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="42ed9-208">如果因收件匣規則而發生轉接，內部寄件者不會收到 NDR。</span><span class="sxs-lookup"><span data-stu-id="42ed9-208">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="42ed9-209">可用值包括：</span><span class="sxs-lookup"><span data-stu-id="42ed9-209">The available values are:</span></span>

   - <span data-ttu-id="42ed9-210">**自動系統控制**：允許輸出垃圾郵件篩選控制自動外部電子郵件轉發。</span><span class="sxs-lookup"><span data-stu-id="42ed9-210">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="42ed9-211">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-211">This is the default value.</span></span>
   - <span data-ttu-id="42ed9-212">**On**：自動外部電子郵件轉寄功能未由原則停用。</span><span class="sxs-lookup"><span data-stu-id="42ed9-212">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="42ed9-213">**Off**：原則已停用所有自動外部電子郵件轉接。</span><span class="sxs-lookup"><span data-stu-id="42ed9-213">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="42ed9-214"> (必要) 請展開 [套用 **于** ] 區段，識別套用原則的內部寄件者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-214">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="42ed9-215">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-215">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="42ed9-216">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<sender1\>_ 或 _\<sender2\>_)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-216">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="42ed9-217">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<sender1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-217">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="42ed9-218">最簡單的方法是按一下 [新增條件] 三次，查看所有可用的條件。</span><span class="sxs-lookup"><span data-stu-id="42ed9-218">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="42ed9-219">您可以按一下 ![移除按鈕](../../media/scc-remove-icon.png)移除您不想要設定的條件。</span><span class="sxs-lookup"><span data-stu-id="42ed9-219">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="42ed9-220">**寄件者網域為**：指定組織中一或多個已設定公認的網域中的寄件者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-220">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="42ed9-221">按一下 [新增標籤] 方塊，可查看並選取網域。</span><span class="sxs-lookup"><span data-stu-id="42ed9-221">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="42ed9-222">如果有不止一個網域，再次按一下 [新增標籤] 方塊可選取其他網域。</span><span class="sxs-lookup"><span data-stu-id="42ed9-222">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="42ed9-223">**寄件者為**：指定組織中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-223">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="42ed9-224">在 [新增標籤] 內按一下，然後開始輸入以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="42ed9-224">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="42ed9-225">再次按一下 [ **新增標記** ] 方塊，以選取其他寄件者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-225">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="42ed9-226">**寄件者隸屬于**：指定組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="42ed9-226">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="42ed9-227">在 [新增標籤] 內按一下，然後開始輸入以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="42ed9-227">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="42ed9-228">再次按一下 [ **新增標記** ] 方塊，以選取其他寄件者。</span><span class="sxs-lookup"><span data-stu-id="42ed9-228">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="42ed9-229">**除了**：若要為規則新增例外情況，按一下 [新增條件] 三次，即可查看所有可用的例外。</span><span class="sxs-lookup"><span data-stu-id="42ed9-229">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="42ed9-230">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="42ed9-230">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="42ed9-231">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-231">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="42ed9-232">使用安全性 & 規範中心來查看輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-232">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="42ed9-233">在安全性與合規性中心，移至 [威脅管理] \> [原則] \> [反垃圾郵件]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="42ed9-234">在 [ **反垃圾郵件設定** ] 頁面上，按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 以展開輸出垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="42ed9-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="42ed9-235">名為 [ **輸出垃圾郵件篩選原則**] 的預設原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-235">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="42ed9-236">您在 [ **類型** ] 欄中的值為 **自訂輸出垃圾郵件原則** 時所建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="42ed9-237">原則設定會顯示在已展開的原則詳細資料中，您也可以按一下 [ **編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-237">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="42ed9-238">使用安全性 & 規範中心來修改輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-238">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="42ed9-239">在安全性與合規性中心，移至 [威脅管理] \> [原則] \> [反垃圾郵件]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="42ed9-240">在 [ **反垃圾郵件設定** ] 頁面上，按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 以展開輸出垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="42ed9-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="42ed9-241">名為 [ **輸出垃圾郵件篩選原則**] 的預設原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="42ed9-242">您在 [ **類型** ] 欄中的值為 **自訂輸出垃圾郵件原則** 時所建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="42ed9-243">按一下 [編輯原則]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-243">Click **Edit policy**.</span></span>

<span data-ttu-id="42ed9-244">若為自訂輸出垃圾郵件原則，快顯視窗中所述的可用設定與 [ [使用安全性 & 規範中心建立輸出垃圾郵件原則](#use-the-security--compliance-center-to-create-outbound-spam-policies) ] 區段中所述的設定相同。</span><span class="sxs-lookup"><span data-stu-id="42ed9-244">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="42ed9-245">針對預設輸出垃圾郵件原則，名稱為 **輸出垃圾郵件篩選原則**，[套用 **至** ] 區段無法使用 (原則套用至所有人) ，而且您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-245">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="42ed9-246">若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="42ed9-246">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="42ed9-247">啟用或停用輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-247">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="42ed9-248">在安全性與合規性中心，移至 [威脅管理] \> [原則] \> [反垃圾郵件]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="42ed9-249">在 [ **反垃圾郵件設定** ] 頁面上，按一下 [ ![ 展開圖示]， ](../../media/scc-expand-icon.png) 展開您建立的自訂原則 ([ **類型** ] 欄中的值為 [ **自訂輸出垃圾郵件原則** ]) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="42ed9-250">在隨即出現的展開的原則詳細資料中，請注意 **開啟** 資料行的值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-250">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="42ed9-251">將切換開關向左移動以停用原則：</span><span class="sxs-lookup"><span data-stu-id="42ed9-251">Move the toggle to the left to disable the policy:</span></span> ![關閉](../../media/scc-toggle-off.png)

   <span data-ttu-id="42ed9-253">將切換開關向右移動以啟用原則：</span><span class="sxs-lookup"><span data-stu-id="42ed9-253">Move the toggle to the right to enable the policy:</span></span> ![開啟](../../media/scc-toggle-on.png)

<span data-ttu-id="42ed9-255">您無法停用預設輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-255">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="42ed9-256">設定自訂輸出垃圾郵件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="42ed9-256">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="42ed9-257">根據預設，輸出垃圾郵件原則的優先順序會根據在 (較舊的原則中所建立的順序，優先順序低於舊版的原則) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-257">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="42ed9-258">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="42ed9-258">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="42ed9-259">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="42ed9-259">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="42ed9-260">自訂輸出垃圾郵件原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-260">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="42ed9-261">預設的輸出垃圾郵件原則（名為 **輸出垃圾郵件篩選原則** ）的優先順序值是 **最低** 的，您無法變更。</span><span class="sxs-lookup"><span data-stu-id="42ed9-261">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="42ed9-262">若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序] 數字)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-262">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="42ed9-263">在安全性與合規性中心，移至 [威脅管理] \> [原則] \> [反垃圾郵件]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="42ed9-264">在 [ **反垃圾郵件設定** ] 頁面上，尋找 [ **類型** ] 欄中的值為 [ **自訂輸出垃圾郵件原則**] 的原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-264">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="42ed9-265">請注意 [優先順序] 資料行中的值：</span><span class="sxs-lookup"><span data-stu-id="42ed9-265">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="42ed9-266">具有最高優先順序的自訂輸出垃圾郵件原則，具有值 ![ 向中箭號圖示 ](../../media/ITPro-EAC-DownArrowIcon.png) **0**。</span><span class="sxs-lookup"><span data-stu-id="42ed9-266">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="42ed9-267">具有最低優先順序的自訂輸出垃圾郵件原則的 value ![ 向上箭號圖示 ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (例如， ![ 向上箭號圖示 ](../../media/ITPro-EAC-UpArrowIcon.png) **3**) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-267">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="42ed9-268">如果您有三個或多個自訂輸出垃圾郵件原則，則最高和最低優先順序之間的原則會有值向上箭號圖示 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (例如， ![ 向上箭號圖示 ](../../media/ITPro-EAC-UpArrowIcon.png)![ 向下箭號圖示 ](../../media/ITPro-EAC-DownArrowIcon.png) **2**) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-268">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="42ed9-269">按一下</span><span class="sxs-lookup"><span data-stu-id="42ed9-269">Click</span></span> ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="42ed9-271">或</span><span class="sxs-lookup"><span data-stu-id="42ed9-271">or</span></span> ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="42ed9-273">在 [優先順序] 清單中，將自訂的輸出垃圾郵件原則上移或下移。</span><span class="sxs-lookup"><span data-stu-id="42ed9-273">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="42ed9-274">使用安全性 & 規範中心移除輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-274">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="42ed9-275">在安全性與合規性中心，移至 [威脅管理] \> [原則] \> [反垃圾郵件]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="42ed9-276">在 [ **反垃圾郵件設定** ] 頁面上，按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 以展開您要刪除的自訂原則 ([ **類型** ] 欄是 **自訂輸出垃圾郵件原則**) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-276">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="42ed9-277">在隨即出現的展開原則詳細資料中，按一下 [刪除原則]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-277">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="42ed9-278">在隨即出現的警告對話方塊中，按一下 [是]。</span><span class="sxs-lookup"><span data-stu-id="42ed9-278">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="42ed9-279">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="42ed9-280">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-280">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="42ed9-281">如先前所述，輸出垃圾郵件原則是由輸出垃圾郵件篩選原則和外寄垃圾郵件篩選規則所組成。</span><span class="sxs-lookup"><span data-stu-id="42ed9-281">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="42ed9-282">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="42ed9-282">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="42ed9-283">您可以使用 **\* -HostedOutboundSpamFilterPolicy** Cmdlet 來管理輸出垃圾郵件篩選原則，也可以使用 **\* -HostedOutboundSpamFilterRule** Cmdlet 來管理輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-283">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="42ed9-284">在 PowerShell 中，您先建立輸出垃圾郵件篩選原則，然後建立輸出垃圾郵件篩選規則，以識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-284">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="42ed9-285">在 PowerShell 中，您可以分別修改輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="42ed9-285">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="42ed9-286">當您從 PowerShell 中移除輸出垃圾郵件篩選原則時，對應的輸出垃圾郵件篩選規則不會自動移除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="42ed9-286">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="42ed9-287">使用 PowerShell 建立輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="42ed9-288">在 PowerShell 中建立輸出垃圾郵件原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="42ed9-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="42ed9-289">建立輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-289">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="42ed9-290">建立輸出垃圾郵件篩選規則，以指定套用規則的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="42ed9-291">**附註**：</span><span class="sxs-lookup"><span data-stu-id="42ed9-291">**Notes**:</span></span>

- <span data-ttu-id="42ed9-292">您可以建立新的輸出垃圾郵件篩選規則，並將現有的未關聯輸出垃圾郵件篩選原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="42ed9-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="42ed9-293">輸出垃圾郵件篩選規則無法與一個以上的輸出垃圾郵件篩選原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="42ed9-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="42ed9-294">您可以在 PowerShell 中的新外寄垃圾郵件篩選原則上設定下列設定，而這些原則在安全性 & 規範中心內無法使用，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="42ed9-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="42ed9-295">_在_ `$false` **HostedOutboundSpamFilterRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="42ed9-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="42ed9-296">在 _\<Number\>_ **HostedOutboundSpamFilterRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="42ed9-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="42ed9-297">在您將原則指派給垃圾郵件篩選規則之前，您在 PowerShell 中所建立的新輸出垃圾郵件篩選原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="42ed9-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="42ed9-298">步驟1：使用 PowerShell 來建立輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="42ed9-299">若要建立輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="42ed9-300">此範例會建立名為 Contoso 主管的新輸出垃圾郵件篩選原則，並提供下列設定：</span><span class="sxs-lookup"><span data-stu-id="42ed9-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="42ed9-301">收件者速率限制限制為預設值較小的值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="42ed9-302">如需詳細資訊，請參閱 [在 Microsoft 365 選項](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)中傳送限制。</span><span class="sxs-lookup"><span data-stu-id="42ed9-302">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="42ed9-303">達到其中一個限制之後，使用者就無法傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="42ed9-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="42ed9-304">如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="42ed9-305">步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="42ed9-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="42ed9-306">若要建立輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="42ed9-307">此範例會使用下列設定建立名為 Contoso 主管的新輸出垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="42ed9-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="42ed9-308">名為 Contoso 主管的輸出垃圾郵件篩選原則與規則相關聯。</span><span class="sxs-lookup"><span data-stu-id="42ed9-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="42ed9-309">此規則會套用至名為 ContosoExecutives Group 的群組成員。</span><span class="sxs-lookup"><span data-stu-id="42ed9-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="42ed9-310">如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="42ed9-311">使用 PowerShell 來查看輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="42ed9-312">若要傳回所有輸出垃圾郵件篩選原則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42ed9-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="42ed9-313">若要傳回特定輸出垃圾郵件篩選原則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="42ed9-314">本範例會傳回名為「主管」的輸出垃圾郵件篩選原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="42ed9-315">如需詳細的語法及參數資訊，請參閱 [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="42ed9-316">使用 PowerShell 來查看輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="42ed9-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="42ed9-317">若要查看現有的輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="42ed9-318">若要傳回所有輸出垃圾郵件篩選規則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42ed9-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="42ed9-319">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42ed9-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="42ed9-320">若要傳回特定輸出垃圾郵件篩選規則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="42ed9-321">此範例會傳回名為 Contoso 主管的輸出垃圾郵件篩選規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="42ed9-322">如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="42ed9-323">使用 PowerShell 修改輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="42ed9-324">當您在 PowerShell 中修改惡意程式碼篩選原則時，如您依照「 [步驟1：使用 PowerShell 建立外寄垃圾郵件篩選原則](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 」一節所述，您在建立原則時，可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="42ed9-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="42ed9-325">您無法重新命名外寄垃圾郵件篩選原則 (**Set-HostedOutboundSpamFilterPolicy** 指令程式沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-325">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="42ed9-326">當您在安全性 & 合規性中心重新命名輸出垃圾郵件原則時，您只是重新命名輸出垃圾郵件篩選 _規則_。</span><span class="sxs-lookup"><span data-stu-id="42ed9-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="42ed9-327">若要修改輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="42ed9-328">如需詳細的語法及參數資訊，請參閱 [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="42ed9-329">使用 PowerShell 修改輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="42ed9-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="42ed9-330">當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="42ed9-331">若要啟用或停用現有的輸出垃圾郵件篩選規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="42ed9-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="42ed9-332">否則，當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="42ed9-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="42ed9-333">當您建立規則時，如您在本文稍早的 [步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 區段中所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="42ed9-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="42ed9-334">若要修改輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="42ed9-335">如需詳細的語法及參數資訊，請參閱 [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="42ed9-336">使用 PowerShell 來啟用或停用輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="42ed9-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="42ed9-337">啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，可啟用或停用輸出垃圾郵件篩選規則和指派的外寄垃圾郵件篩選原則) 的整體輸出垃圾郵件原則 (。</span><span class="sxs-lookup"><span data-stu-id="42ed9-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="42ed9-338">您無法啟用或停用預設輸出垃圾郵件原則 (永遠永遠套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="42ed9-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="42ed9-339">若要啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="42ed9-340">本範例會停用名為「行銷部門」的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="42ed9-341">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="42ed9-342">如需詳細的語法及參數資訊，請參閱 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="42ed9-343">使用 PowerShell 設定輸出垃圾郵件篩選規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="42ed9-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="42ed9-344">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="42ed9-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="42ed9-345">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="42ed9-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="42ed9-346">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="42ed9-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="42ed9-347">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="42ed9-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="42ed9-348">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="42ed9-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="42ed9-349">若要設定 PowerShell 中的外寄垃圾郵件篩選規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="42ed9-350">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="42ed9-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="42ed9-351">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="42ed9-352">若要在建立新規則時設定其優先順序，請改用 **HostedOutboundSpamFilterRule** Cmdlet 上的 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="42ed9-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="42ed9-353">外寄的預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，它永遠具有「不可修改的優先順序 **」值。**</span><span class="sxs-lookup"><span data-stu-id="42ed9-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="42ed9-354">使用 PowerShell 移除輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="42ed9-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="42ed9-355">當您使用 PowerShell 來移除輸出垃圾郵件篩選原則時，並不會移除對應的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="42ed9-356">若要在 PowerShell 中移除輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="42ed9-357">此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="42ed9-358">如需詳細的語法及參數資訊，請參閱 [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="42ed9-359">使用 PowerShell 移除輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="42ed9-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="42ed9-360">當您使用 PowerShell 移除外寄垃圾郵件篩選規則時，並不會移除對應的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="42ed9-361">若要移除 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="42ed9-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="42ed9-362">此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="42ed9-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="42ed9-363">如需詳細的語法及參數資訊，請參閱 [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="42ed9-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="42ed9-364">相關資訊</span><span class="sxs-lookup"><span data-stu-id="42ed9-364">For more information</span></span>

<span data-ttu-id="42ed9-365">[從 [受限使用者] 入口網站中移除封鎖的使用者](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="42ed9-365">[Remove blocked users from the Restricted Users portal](removing-user-from-restricted-users-portal-after-spam.md)</span></span>

[<span data-ttu-id="42ed9-366">輸出郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="42ed9-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="42ed9-367">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="42ed9-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="42ed9-368">自動轉寄訊息的報告</span><span class="sxs-lookup"><span data-stu-id="42ed9-368">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
