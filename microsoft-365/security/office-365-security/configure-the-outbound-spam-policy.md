---
title: 設定輸出垃圾郵件篩選
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用該服務來傳送輸出電子郵件，便會一律啟用輸出垃圾郵件篩選功能，從而保護使用該服務的組織及其預期的收件者。
ms.openlocfilehash: e788310ae8fd3c0da7f1a39fbba2dc0d6e369d30
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893883"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="ad401-103">在 Office 365 中設定輸出垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="ad401-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="ad401-104">如果您是 Office 365 客戶，其信箱位於 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶，但沒有 Exchange Online 信箱，則透過 EOP 傳送的輸出電子郵件會自動檢查垃圾郵件和不尋常傳送活動。</span><span class="sxs-lookup"><span data-stu-id="ad401-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="ad401-105">組織中使用者的外寄垃圾郵件通常表示已遭破壞的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ad401-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="ad401-106">可疑的輸出郵件會標示為垃圾郵件（不論垃圾郵件信賴等級或 SCL 為何），並透過[高風險傳遞集](high-risk-delivery-pool-for-outbound-messages.md)區路由傳送，以協助保護服務的信譽（也就是說，保留 Office 365 來源電子郵件伺服器，而非 IP 封鎖清單）。</span><span class="sxs-lookup"><span data-stu-id="ad401-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="ad401-107">系統管理員會自動收到可疑的輸出電子郵件活動，並透過[警示原則](../../compliance/alert-policies.md)封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="ad401-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="ad401-108">EOP 使用輸出垃圾郵件原則做為組織的整體防禦垃圾郵件的一部分。</span><span class="sxs-lookup"><span data-stu-id="ad401-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="ad401-109">如需詳細資訊，請參閱[Office 365 中的反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="ad401-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="ad401-110">系統管理員可以查看、編輯和設定（但不能刪除）預設輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="ad401-111">為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ad401-112">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="ad401-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ad401-113">您可以在 Office 365 Security & 合規性中心或 PowerShell （Office 365 客戶的 Exchange Online PowerShell 中設定輸出垃圾郵件原則;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。</span><span class="sxs-lookup"><span data-stu-id="ad401-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="ad401-114">Office 365 Security 中的輸出垃圾郵件原則 & 規範中心與 Exchange online PowerShell 或 Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad401-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="ad401-115">EOP 中的外寄垃圾郵件原則基本元素為：</span><span class="sxs-lookup"><span data-stu-id="ad401-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="ad401-116">**輸出垃圾郵件篩選原則**：指定輸出垃圾郵件篩選 verdicts 和通知選項的動作。</span><span class="sxs-lookup"><span data-stu-id="ad401-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="ad401-117">**輸出垃圾郵件篩選規則**：指定輸出垃圾郵件篩選器原則的優先順序和收件者篩選器（該原則適用于）。</span><span class="sxs-lookup"><span data-stu-id="ad401-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="ad401-118">當您在安全性 & 合規性中心管理輸出垃圾郵件原則時，這兩個元素之間的差異並不明顯。</span><span class="sxs-lookup"><span data-stu-id="ad401-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ad401-119">當您在安全性 & 合規性中心建立輸出垃圾郵件原則時，實際上您實際上是使用相同的名稱建立輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="ad401-120">當您在安全性 & 規範中心中修改輸出垃圾郵件原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="ad401-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="ad401-121">所有其他設定都會修改相關聯的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="ad401-122">當您從安全性 & 合規性中心移除輸出垃圾郵件原則時，會移除輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="ad401-123">在 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 中，輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="ad401-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="ad401-124">您可以使用\*\* \*-HostedContentFilterPolicy\*\* Cmdlet 來管理輸出垃圾郵件篩選原則，也可以使用\*\* \*-disable-hostedcontentfilterrule\*\* Cmdlet 來管理輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="ad401-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="ad401-125">在 PowerShell 中，您先建立輸出垃圾郵件篩選原則，然後建立輸出垃圾郵件篩選規則，以識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="ad401-126">在 PowerShell 中，您可以分別修改輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="ad401-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="ad401-127">當您從 PowerShell 中移除輸出垃圾郵件篩選原則時，對應的輸出垃圾郵件篩選規則不會自動移除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ad401-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="ad401-128">預設輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-128">Default outbound spam policy</span></span>

<span data-ttu-id="ad401-129">每個組織都有一個名為 Default 的內建輸出垃圾郵件原則，具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="ad401-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="ad401-130">名為 Default 的輸出垃圾郵件篩選原則會套用至組織中的所有收件者，即使沒有與原則相關聯的外寄垃圾郵件篩選規則（收件者篩選器）。</span><span class="sxs-lookup"><span data-stu-id="ad401-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="ad401-131">名為 Default 的原則的自訂優先順序值**最低**，您無法修改（原則永遠套用最後一個）。</span><span class="sxs-lookup"><span data-stu-id="ad401-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ad401-132">您建立的任何自訂原則的優先順序都會高於名為 Default 的原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="ad401-133">名為 Default 的原則為預設原則（ **IsDefault**屬性具有值`True`），而且您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ad401-134">若要增加輸出垃圾郵件篩選的效能，您可以使用套用至特定使用者或使用者群組的更嚴格設定來建立自訂輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad401-135">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="ad401-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad401-136">您可以在<https://protection.office.com/>中開啟安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="ad401-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ad401-137">若要直接移至 [**反垃圾郵件設定**] 頁面<https://protection.office.com/antispam>，請使用。</span><span class="sxs-lookup"><span data-stu-id="ad401-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="ad401-138">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ad401-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ad401-139">若要連線到獨立的 Exchange Online Protection PowerShell，請參閱[connect To Exchange Online protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ad401-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ad401-140">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="ad401-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="ad401-141">若要新增、修改和刪除輸出垃圾郵件原則，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ad401-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ad401-142">若要唯讀的輸出垃圾郵件原則的存取權，您必須是**Security Reader**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ad401-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="ad401-143">如需安全性 & 規範中心中角色群組的詳細資訊，請參閱[Office 365 安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ad401-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="ad401-144">如需輸出垃圾郵件原則的建議設定，請參閱[EOP 呼出垃圾郵件篩選原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="ad401-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="ad401-145">已超過名為「**電子郵件傳送限制**」的預設[警示原則](../../compliance/alert-policies.md)、偵測**到的電子**郵件，以及限制傳送**電子郵件的使用者**已將電子郵件通知傳送給**TenantAdmins** （**全域系統管理員**）群組的成員，但由於輸出的垃圾郵件而封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="ad401-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="ad401-146">如需詳細資訊，請參閱[確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="ad401-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="ad401-147">建議您使用這些警示原則，而不是在輸出垃圾郵件原則中使用通知選項。</span><span class="sxs-lookup"><span data-stu-id="ad401-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="ad401-148">使用安全性 & 規範中心建立輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="ad401-149">在安全性 & 合規性中心建立自訂輸出垃圾郵件原則，會同時使用相同的名稱建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="ad401-150">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="ad401-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ad401-151">在 [**反垃圾郵件設定**] 頁面上，按一下 [**建立輸出原則**]。</span><span class="sxs-lookup"><span data-stu-id="ad401-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="ad401-152">在 [**輸出垃圾郵件篩選原則**] 的 [飛出開啟] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="ad401-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ad401-153">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="ad401-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ad401-154">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="ad401-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="ad401-155">選展開 [**通知**] 區段，設定其他應接收副本的使用者，以及可疑外寄電子郵件訊息的通知：</span><span class="sxs-lookup"><span data-stu-id="ad401-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="ad401-156">**將可疑的輸出電子郵件的複本傳送給特定人員**：此設定會將指定的使用者當做 Bcc 收件者新增至可疑的輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="ad401-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="ad401-157">若要啟用此設定：</span><span class="sxs-lookup"><span data-stu-id="ad401-157">To enable this setting:</span></span>

     <span data-ttu-id="ad401-158">a.</span><span class="sxs-lookup"><span data-stu-id="ad401-158">a.</span></span> <span data-ttu-id="ad401-159">選取 [啟用] 設定的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ad401-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="ad401-160">b.</span><span class="sxs-lookup"><span data-stu-id="ad401-160">b.</span></span> <span data-ttu-id="ad401-161">按一下 [**新增人員**]。</span><span class="sxs-lookup"><span data-stu-id="ad401-161">Click **Add people**.</span></span> <span data-ttu-id="ad401-162">在出現的 [**新增或移除**收件者] 浮出控制項中：</span><span class="sxs-lookup"><span data-stu-id="ad401-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="ad401-163">c.</span><span class="sxs-lookup"><span data-stu-id="ad401-163">c.</span></span> <span data-ttu-id="ad401-164">輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad401-164">Enter the sender's email address.</span></span> <span data-ttu-id="ad401-165">您可以指定多個以分號分隔的電子郵件地址（;)或每行一位收件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="ad401-166">d.</span><span class="sxs-lookup"><span data-stu-id="ad401-166">d.</span></span> <span data-ttu-id="ad401-167">按一下</span><span class="sxs-lookup"><span data-stu-id="ad401-167">Click</span></span> ![[新增] 圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="ad401-169">以加入收件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-169">to add the recipients.</span></span>

        <span data-ttu-id="ad401-170">請視需要重複執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="ad401-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="ad401-171">您新增的收件者會出現在飛入的 [**收件者清單**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="ad401-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="ad401-172">若要刪除收件者![，請](../../media/scc-remove-icon.png)按一下 [移除] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ad401-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="ad401-173">e.</span><span class="sxs-lookup"><span data-stu-id="ad401-173">e.</span></span> <span data-ttu-id="ad401-174">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="ad401-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="ad401-175">若要停用此設定，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ad401-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="ad401-176">**如果寄件者因傳送輸出的垃圾郵件而遭到封鎖，請通知特定人員**：</span><span class="sxs-lookup"><span data-stu-id="ad401-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="ad401-177">當使用者因超過 [**收件者限制**] 區段中的限制時[，已封鎖](../../compliance/alert-policies.md)使用者 TenantAdmins （全域系統管理員）群組的成員時，會將**電子郵件通知**傳送至**TenantAdmins** （**全域系統管理員**）群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ad401-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="ad401-178">建議您在輸出垃圾郵件原則中使用警示原則，而不是此設定，以通知系統管理員和其他使用者。</span><span class="sxs-lookup"><span data-stu-id="ad401-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="ad401-179">如需相關指示，請參閱[確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="ad401-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="ad401-180">若要啟用此設定：</span><span class="sxs-lookup"><span data-stu-id="ad401-180">To enable this setting:</span></span>

     <span data-ttu-id="ad401-181">a.</span><span class="sxs-lookup"><span data-stu-id="ad401-181">a.</span></span> <span data-ttu-id="ad401-182">選取 [啟用] 設定的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ad401-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="ad401-183">b.</span><span class="sxs-lookup"><span data-stu-id="ad401-183">b.</span></span> <span data-ttu-id="ad401-184">按一下 [**新增人員**]。</span><span class="sxs-lookup"><span data-stu-id="ad401-184">Click **Add people**.</span></span> <span data-ttu-id="ad401-185">在出現的 [**新增或移除**收件者] 浮出控制項中：</span><span class="sxs-lookup"><span data-stu-id="ad401-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="ad401-186">c.</span><span class="sxs-lookup"><span data-stu-id="ad401-186">c.</span></span> <span data-ttu-id="ad401-187">輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad401-187">Enter the sender's email address.</span></span> <span data-ttu-id="ad401-188">您可以指定多個以分號分隔的電子郵件地址（;)或每行一位收件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="ad401-189">d.</span><span class="sxs-lookup"><span data-stu-id="ad401-189">d.</span></span> <span data-ttu-id="ad401-190">按一下</span><span class="sxs-lookup"><span data-stu-id="ad401-190">Click</span></span> ![[新增] 圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="ad401-192">以加入收件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-192">to add the recipients.</span></span>

        <span data-ttu-id="ad401-193">請視需要重複執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="ad401-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="ad401-194">您新增的收件者會出現在飛入的 [**收件者清單**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="ad401-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="ad401-195">若要刪除收件者![，請](../../media/scc-remove-icon.png)按一下 [移除] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ad401-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="ad401-196">e.</span><span class="sxs-lookup"><span data-stu-id="ad401-196">e.</span></span> <span data-ttu-id="ad401-197">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="ad401-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="ad401-198">若要停用此設定，請清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ad401-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="ad401-199">選展開 [**收件者限制**] 區段，以設定可疑輸出電子郵件訊息的限制和動作：]</span><span class="sxs-lookup"><span data-stu-id="ad401-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages: ]</span></span>
   - <span data-ttu-id="ad401-200">**每位使用者的收件者數目上限**</span><span class="sxs-lookup"><span data-stu-id="ad401-200">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="ad401-201">有效的值為0到10000。</span><span class="sxs-lookup"><span data-stu-id="ad401-201">A valid value is 0 to 10000.</span></span> <span data-ttu-id="ad401-202">預設值為0，這表示使用服務預設值。</span><span class="sxs-lookup"><span data-stu-id="ad401-202">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="ad401-203">如需詳細資訊，請參閱[在 Office 365 選項](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)中傳送限制。</span><span class="sxs-lookup"><span data-stu-id="ad401-203">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="ad401-204">**外部每小時限制**：每小時的外部收件者數目上限。</span><span class="sxs-lookup"><span data-stu-id="ad401-204">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="ad401-205">**內部每小時限制**：每小時內部收件者的數目上限。</span><span class="sxs-lookup"><span data-stu-id="ad401-205">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="ad401-206">**每日限制**：每日總收件者數目上限。</span><span class="sxs-lookup"><span data-stu-id="ad401-206">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="ad401-207">**當使用者超過上述限制時的動作**：設定超出任何一位**收件者限制**時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ad401-207">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="ad401-208">針對所有動作，使用者指定的收件者**受到限制傳送電子郵件**提醒原則的收件者（**如果收件者由於**傳出垃圾郵件原則中傳送輸出垃圾郵件設定而遭到封鎖，則在現在的重複的通知特定人員）會收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="ad401-208">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="ad401-209">**限制使用者在下列日期之後傳送郵件**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="ad401-209">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="ad401-210">傳送電子郵件通知，而且在下一天（根據 UTC 時間）之後，使用者將無法再傳送一封以上的郵件。</span><span class="sxs-lookup"><span data-stu-id="ad401-210">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="ad401-211">系統管理員無法覆寫此區塊。</span><span class="sxs-lookup"><span data-stu-id="ad401-211">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="ad401-212">名為**User 限制寄件者傳送電子郵件**的活動警示會通知系統管理員（透過電子郵件和 [**查看提醒**] 頁面）。</span><span class="sxs-lookup"><span data-stu-id="ad401-212">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="ad401-213">**當寄件者因**在原則中傳送輸出垃圾郵件設定而遭到封鎖時，在 [通知特定人員] 中指定的任何收件者也都會收到通知。</span><span class="sxs-lookup"><span data-stu-id="ad401-213">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="ad401-214">在下一天之後，使用者將無法再傳送任何郵件到以 UTC 時間為基礎。</span><span class="sxs-lookup"><span data-stu-id="ad401-214">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="ad401-215">系統管理員無法覆寫此區塊。</span><span class="sxs-lookup"><span data-stu-id="ad401-215">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="ad401-216">**限制使用者傳送郵件**：已傳送電子郵件通知，使用者會新增至安全性 & 合規性中心內的 **[受限制的使用者]<https://sip.protection.office.com/restrictedusers> **入口網站，直到系統管理員將其從**受限使用者**入口網站中移除之後，使用者才會傳送電子郵件。系統管理員從清單中移除使用者後，該天的使用者將不會受到限制。</span><span class="sxs-lookup"><span data-stu-id="ad401-216">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="ad401-217">如需相關指示，請參閱[在傳送垃圾郵件後移除受限使用者入口網站中的使用者](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="ad401-217">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="ad401-218">**無動作，只發出警示**：已傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="ad401-218">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="ad401-219">必備展開 [套用**至**] 區段，識別套用原則的內部寄件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-219">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="ad401-220">您只能使用條件或例外狀況，但您可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="ad401-220">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ad401-221">相同狀況或例外狀況或邏輯的多個值（例如， _ \<sender1\> _或_ \<sender2\>_）。</span><span class="sxs-lookup"><span data-stu-id="ad401-221">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="ad401-222">不同的條件或例外情況_ \<使用和邏輯（例如，\> _ _ \<group\>1 的成員_）。</span><span class="sxs-lookup"><span data-stu-id="ad401-222">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="ad401-223">最簡單的方法是按一下 [**新增條件**] 三次，以查看所有可用的條件。</span><span class="sxs-lookup"><span data-stu-id="ad401-223">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="ad401-224">您可以按一下![[移除](../../media/scc-remove-icon.png) ] 按鈕移除您不想要設定的條件。</span><span class="sxs-lookup"><span data-stu-id="ad401-224">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="ad401-225">**寄件者網域為**：指定 Office 365 中一或多個已設定公認的網域中的寄件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-225">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="ad401-226">在 [**新增**標籤] 方塊中按一下以查看並選取網域。</span><span class="sxs-lookup"><span data-stu-id="ad401-226">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="ad401-227">再按一下 [**新增**標籤] 方塊，以選取其他網域（若有多個網域可用）。</span><span class="sxs-lookup"><span data-stu-id="ad401-227">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="ad401-228">**寄件者為**：指定組織中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="ad401-228">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="ad401-229">按一下 [**新增標記**]，然後按一下 [開始輸入] 以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="ad401-229">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="ad401-230">再次按一下 [**新增標記**] 方塊，以選取其他寄件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-230">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="ad401-231">**寄件者隸屬于**：指定組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="ad401-231">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="ad401-232">按一下 [**新增標記**]，然後按一下 [開始輸入] 以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="ad401-232">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="ad401-233">再次按一下 [**新增標記**] 方塊，以選取其他寄件者。</span><span class="sxs-lookup"><span data-stu-id="ad401-233">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="ad401-234">**除非**：若要新增規則的例外狀況，請按一下 [**新增條件**] 三次，以查看所有可用的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ad401-234">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="ad401-235">設定和行為與條件完全相同。</span><span class="sxs-lookup"><span data-stu-id="ad401-235">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="ad401-236">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="ad401-236">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="ad401-237">使用安全性 & 規範中心來查看輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-237">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="ad401-238">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="ad401-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ad401-239">在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示] 以展開輸出垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="ad401-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="ad401-240">名為 [**輸出垃圾郵件篩選原則**] 的預設原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="ad401-241">您在 [**類型**] 欄中的值為**自訂輸出垃圾郵件原則**時所建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="ad401-242">原則設定會顯示在已展開的原則詳細資料中，您也可以按一下 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="ad401-242">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="ad401-243">使用安全性 & 規範中心來修改輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-243">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="ad401-244">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="ad401-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ad401-245">在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示] 以展開輸出垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="ad401-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="ad401-246">名為 [**輸出垃圾郵件篩選原則**] 的預設原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-246">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="ad401-247">您在 [**類型**] 欄中的值為**自訂輸出垃圾郵件原則**時所建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-247">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="ad401-248">按一下 [**編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="ad401-248">Click **Edit policy**.</span></span>

<span data-ttu-id="ad401-249">若為自訂輸出垃圾郵件原則，快顯視窗中所述的可用設定與 [[使用安全性 & 規範中心建立輸出垃圾郵件原則](#use-the-security--compliance-center-to-create-outbound-spam-policies)] 區段中所述的設定相同。</span><span class="sxs-lookup"><span data-stu-id="ad401-249">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="ad401-250">針對名為「**輸出垃圾郵件篩選原則**」的預設輸出垃圾郵件原則，[套用**至**] 區段不可用（原則套用至 [所有人]），您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-250">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="ad401-251">若要啟用或停用原則、設定原則優先順序順序或設定使用者隔離通知，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="ad401-251">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="ad401-252">啟用或停用輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-252">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="ad401-253">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="ad401-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ad401-254">在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示]，展開您建立的自訂原則（[**類型**] 欄中的值為 [**自訂輸出垃圾郵件原則**]）。</span><span class="sxs-lookup"><span data-stu-id="ad401-254">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="ad401-255">在顯示的展開原則詳細資料中，注意 [ **On** ] 欄中的值。</span><span class="sxs-lookup"><span data-stu-id="ad401-255">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="ad401-256">將切換移至左側以停用原則：</span><span class="sxs-lookup"><span data-stu-id="ad401-256">Move the toggle to the left to disable the policy:</span></span> ![關閉切換](../../media/scc-toggle-off.png)

   <span data-ttu-id="ad401-258">將切換向右移動以啟用原則：</span><span class="sxs-lookup"><span data-stu-id="ad401-258">Move the toggle to the right to enable the policy:</span></span> ![開啟開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="ad401-260">您無法停用預設輸出垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-260">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="ad401-261">設定自訂輸出垃圾郵件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="ad401-261">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="ad401-262">根據預設，輸出垃圾郵件原則的優先順序會根據建立的順序而定（較舊的原則的優先順序較舊）。</span><span class="sxs-lookup"><span data-stu-id="ad401-262">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="ad401-263">優先順序較低的值表示原則的優先順序較高（0是最高值），並以優先順序連續處理原則（較高優先順序的原則會在較低優先順序的原則之前處理）。</span><span class="sxs-lookup"><span data-stu-id="ad401-263">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ad401-264">兩個原則不會有相同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="ad401-264">No two policies can have the same priority.</span></span>

<span data-ttu-id="ad401-265">自訂輸出垃圾郵件原則會以處理的順序顯示（第一個原則的**Priority**值為0）。</span><span class="sxs-lookup"><span data-stu-id="ad401-265">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ad401-266">預設的輸出垃圾郵件原則（名為**輸出垃圾郵件篩選原則**）的優先順序值是**最低**的，您無法變更。</span><span class="sxs-lookup"><span data-stu-id="ad401-266">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="ad401-267">若要變更原則的優先順序，請在清單中上移或下移原則（您無法直接修改安全性 & 規範中心中的**優先順序**號碼）。</span><span class="sxs-lookup"><span data-stu-id="ad401-267">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="ad401-268">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="ad401-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ad401-269">在 [**反垃圾郵件設定**] 頁面上，尋找 [**類型**] 欄中的值為 [**自訂輸出垃圾郵件原則**] 的原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-269">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="ad401-270">請注意 [**優先順序**] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="ad401-270">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="ad401-271">具有最高優先順序的自訂輸出垃圾郵件原則， ![具有值向](../../media/ITPro-EAC-DownArrowIcon.png)中箭號圖示**0**。</span><span class="sxs-lookup"><span data-stu-id="ad401-271">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="ad401-272">具有最低優先順序的自訂輸出垃圾郵件原則具有值![向上箭號](../../media/ITPro-EAC-UpArrowIcon.png) **n** （ ![例如向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **3**）。</span><span class="sxs-lookup"><span data-stu-id="ad401-272">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="ad401-273">如果您有三個或多個自訂輸出垃圾郵件原則，則最高和最低優先順序![之間的原則](../../media/ITPro-EAC-UpArrowIcon.png)![會具有值](../../media/ITPro-EAC-DownArrowIcon.png)向上箭號圖示向下箭號](../../media/ITPro-EAC-UpArrowIcon.png)![圖示**n** （例如， ![向上鍵圖示向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **2**）。</span><span class="sxs-lookup"><span data-stu-id="ad401-273">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="ad401-274">按一下</span><span class="sxs-lookup"><span data-stu-id="ad401-274">Click</span></span> ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="ad401-276">或</span><span class="sxs-lookup"><span data-stu-id="ad401-276">or</span></span> ![向中箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="ad401-278">在 [優先順序] 清單中，將自訂的輸出垃圾郵件原則上移或下移。</span><span class="sxs-lookup"><span data-stu-id="ad401-278">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="ad401-279">使用安全性 & 規範中心移除輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-279">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="ad401-280">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="ad401-280">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ad401-281">在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示] 以展開您要刪除的自訂原則（[**類型**] 欄是**自訂輸出垃圾郵件原則**）。</span><span class="sxs-lookup"><span data-stu-id="ad401-281">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="ad401-282">在顯示的展開原則詳細資料中，按一下 [**刪除原則**]。</span><span class="sxs-lookup"><span data-stu-id="ad401-282">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="ad401-283">在出現的警告對話方塊中，按一下 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="ad401-283">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ad401-284">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-284">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="ad401-285">使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-285">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="ad401-286">使用 PowerShell 建立輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ad401-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="ad401-287">在 PowerShell 中建立輸出垃圾郵件原則的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="ad401-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ad401-288">建立輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-288">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="ad401-289">建立輸出垃圾郵件篩選規則，以指定套用規則的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="ad401-290">**附註**：</span><span class="sxs-lookup"><span data-stu-id="ad401-290">**Notes**:</span></span>

- <span data-ttu-id="ad401-291">您可以建立新的輸出垃圾郵件篩選規則，並將現有的未關聯輸出垃圾郵件篩選原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="ad401-291">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="ad401-292">輸出垃圾郵件篩選規則無法與一個以上的輸出垃圾郵件篩選原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="ad401-292">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="ad401-293">您可以在 PowerShell 中的新外寄垃圾郵件篩選原則上設定下列設定，而這些原則在安全性 & 規範中心內無法使用，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="ad401-293">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ad401-294">建立新原則為停用（在**HostedOutboundSpamFilterRule** Cmdlet 上_啟用_ `$false` ）。</span><span class="sxs-lookup"><span data-stu-id="ad401-294">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="ad401-295">設定在**HostedOutboundSpamFilterRule 指令程式**建立時的原則優先順序（_優先權_ _ \<編號\>_）。</span><span class="sxs-lookup"><span data-stu-id="ad401-295">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="ad401-296">在您將原則指派給垃圾郵件篩選規則之前，您在 PowerShell 中所建立的新輸出垃圾郵件篩選原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="ad401-296">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="ad401-297">步驟1：使用 PowerShell 來建立輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="ad401-297">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="ad401-298">若要建立輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-298">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ad401-299">此範例會建立名為 Contoso 主管的新輸出垃圾郵件篩選原則，並提供下列設定：</span><span class="sxs-lookup"><span data-stu-id="ad401-299">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="ad401-300">收件者速率限制限制為預設值較小的值。</span><span class="sxs-lookup"><span data-stu-id="ad401-300">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="ad401-301">如需詳細資訊，請參閱[在 Office 365 選項](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)中傳送限制。</span><span class="sxs-lookup"><span data-stu-id="ad401-301">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="ad401-302">達到其中一個限制之後，使用者就無法傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="ad401-302">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="ad401-303">如需詳細的語法及參數資訊，請參閱[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad401-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="ad401-304">步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="ad401-304">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="ad401-305">若要建立輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-305">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ad401-306">此範例會使用下列設定建立名為 Contoso 主管的新輸出垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="ad401-306">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="ad401-307">名為 Contoso 主管的輸出垃圾郵件篩選原則與規則相關聯。</span><span class="sxs-lookup"><span data-stu-id="ad401-307">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="ad401-308">此規則適用于名為 Contoso 主管群組的群組成員。</span><span class="sxs-lookup"><span data-stu-id="ad401-308">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="ad401-309">如需詳細的語法及參數資訊，請參閱[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="ad401-309">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="ad401-310">使用 PowerShell 來查看輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="ad401-310">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="ad401-311">若要傳回所有輸出垃圾郵件篩選原則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ad401-311">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="ad401-312">若要傳回特定輸出垃圾郵件篩選原則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-312">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="ad401-313">本範例會傳回名為「主管」的輸出垃圾郵件篩選原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="ad401-313">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="ad401-314">如需詳細的語法及參數資訊，請參閱[Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad401-314">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="ad401-315">使用 PowerShell 來查看輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="ad401-315">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="ad401-316">若要查看現有的輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-316">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="ad401-317">若要傳回所有輸出垃圾郵件篩選規則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ad401-317">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="ad401-318">若要依啟用或停用的規則篩選清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ad401-318">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="ad401-319">若要傳回特定輸出垃圾郵件篩選規則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-319">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="ad401-320">此範例會傳回名為 Contoso 主管的輸出垃圾郵件篩選規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="ad401-320">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ad401-321">如需詳細的語法及參數資訊，請參閱[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="ad401-321">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="ad401-322">使用 PowerShell 修改輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="ad401-322">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="ad401-323">當您在本主題稍早的[步驟1：使用 PowerShell 建立外寄垃圾郵件篩選原則](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)一節所述，在 PowerShell 中修改惡意程式碼篩選原則時，就可以使用相同設定。</span><span class="sxs-lookup"><span data-stu-id="ad401-323">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="ad401-324">**附注**：您無法重新命名外寄垃圾郵件篩選原則（ **Set-HostedOutboundSpamFilterPolicy** Cmdlet 沒有_Name_參數）。</span><span class="sxs-lookup"><span data-stu-id="ad401-324">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ad401-325">當您在安全性 & 合規性中心重新命名輸出垃圾郵件原則時，您只是重新命名輸出垃圾郵件篩選_規則_。</span><span class="sxs-lookup"><span data-stu-id="ad401-325">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="ad401-326">若要修改輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-326">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ad401-327">如需詳細的語法及參數資訊，請參閱[Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad401-327">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="ad401-328">使用 PowerShell 修改輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="ad401-328">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="ad401-329">當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，唯一可用的設定是_Enabled_參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="ad401-329">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ad401-330">若要啟用或停用現有的輸出垃圾郵件篩選規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="ad401-330">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="ad401-331">否則，當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，不會有其他設定可供使用。</span><span class="sxs-lookup"><span data-stu-id="ad401-331">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="ad401-332">當您建立一個規則時，如本主題稍早的[步驟2：使用 PowerShell 以建立輸出垃圾郵件篩選規則](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)區段所述，您可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="ad401-332">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="ad401-333">若要修改輸出垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-333">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ad401-334">如需詳細的語法及參數資訊，請參閱[Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="ad401-334">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="ad401-335">使用 PowerShell 來啟用或停用輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="ad401-335">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="ad401-336">啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，可啟用或停用整個輸出垃圾郵件原則（輸出垃圾郵件篩選規則和指派的外寄垃圾郵件篩選器原則）。</span><span class="sxs-lookup"><span data-stu-id="ad401-336">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="ad401-337">您無法啟用或停用預設輸出垃圾郵件原則（永遠都是套用至所有收件者）。</span><span class="sxs-lookup"><span data-stu-id="ad401-337">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="ad401-338">若要啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-338">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="ad401-339">本範例會停用名為「行銷部門」的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="ad401-339">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ad401-340">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="ad401-340">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ad401-341">如需詳細的語法及參數資訊，請參閱[Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule)和[Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="ad401-341">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="ad401-342">使用 PowerShell 設定輸出垃圾郵件篩選規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="ad401-342">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="ad401-343">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="ad401-343">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ad401-344">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="ad401-344">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ad401-345">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="ad401-345">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ad401-346">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="ad401-346">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ad401-347">例如，如果您有五個自訂規則（優先順序0到4），而您將規則的優先順序變更為2，則具有優先順序2的現有規則會變更為優先順序3，而優先順序為3的規則會變更為優先順序4。</span><span class="sxs-lookup"><span data-stu-id="ad401-347">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ad401-348">若要設定 PowerShell 中的外寄垃圾郵件篩選規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-348">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ad401-349">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="ad401-349">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ad401-350">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="ad401-350">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ad401-351">**附註**：</span><span class="sxs-lookup"><span data-stu-id="ad401-351">**Notes**:</span></span>

- <span data-ttu-id="ad401-352">若要在建立新規則時設定其優先順序，請改用**HostedOutboundSpamFilterRule** Cmdlet 上的_priority_參數。</span><span class="sxs-lookup"><span data-stu-id="ad401-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="ad401-353">外寄的預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，它永遠具有「不可修改的優先順序 **」值。**</span><span class="sxs-lookup"><span data-stu-id="ad401-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="ad401-354">使用 PowerShell 移除輸出垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="ad401-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="ad401-355">當您使用 PowerShell 來移除輸出垃圾郵件篩選原則時，並不會移除對應的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="ad401-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="ad401-356">若要在 PowerShell 中移除輸出垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ad401-357">此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ad401-358">如需詳細的語法及參數資訊，請參閱[Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="ad401-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="ad401-359">使用 PowerShell 移除輸出垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="ad401-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="ad401-360">當您使用 PowerShell 移除外寄垃圾郵件篩選規則時，並不會移除對應的輸出垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="ad401-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="ad401-361">若要移除 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ad401-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="ad401-362">此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="ad401-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="ad401-363">如需詳細的語法及參數資訊，請參閱[Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="ad401-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="ad401-364">相關資訊</span><span class="sxs-lookup"><span data-stu-id="ad401-364">For more information</span></span>

[<span data-ttu-id="ad401-365">傳送垃圾電子郵件之後，從限制的使用者入口網站移除使用者</span><span class="sxs-lookup"><span data-stu-id="ad401-365">Removing a user from the Restricted Users portal after sending spam email</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[<span data-ttu-id="ad401-366">輸出郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="ad401-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="ad401-367">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="ad401-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
