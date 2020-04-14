---
title: 設定垃圾郵件篩選原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入了解如何在 Exchange Online 和獨立 Exchange Online Protection (EOP) 中建立、修改及刪除反垃圾郵件原則。
ms.openlocfilehash: 3f71a9c9a62e409d4a54c01523270fb10a723a96
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2020
ms.locfileid: "43231013"
---
# <a name="configure-anti-spam-policies-in-office-365"></a><span data-ttu-id="033dc-103">設定 Office 365 的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-103">Configure anti-spam policies in Office 365</span></span>

<span data-ttu-id="033dc-104">如果您是 Office 365 客戶並且有 Exchange Online 信箱，或是獨立版 Exchange Online Protection (EOP) 客戶且沒有 Exchange Online 信箱，則輸入的電子郵件會自動受到 EOP 的保護。</span><span class="sxs-lookup"><span data-stu-id="033dc-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="033dc-105">EOP 使用反垃圾郵件原則 (也稱為垃圾郵件過篩選原則或內容篩選原則)，作為貴組織全面防範垃圾郵件的一環。</span><span class="sxs-lookup"><span data-stu-id="033dc-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="033dc-106">如需詳細資訊，請參閱 [Office 365 中的反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-106">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="033dc-107">系統管理員可以檢視、編輯、設定 (但不能刪除) 預設的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="033dc-108">若要提高精確性，您也可以建立自訂的反垃圾郵件原則，並套用至貴組織中的特定使用者、群組或網域。</span><span class="sxs-lookup"><span data-stu-id="033dc-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="033dc-109">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="033dc-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="033dc-110">您可以在 Office 365 安全性與合規性中心設定反垃圾郵件原則，或在 PowerShell 設定反垃圾郵件原則 (Office 365 客戶使用 Exchange Online PowerShell，獨立版 EOP 客戶使用 Exchange Online Protection PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="033dc-110">You can configure anti-spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="anti-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="033dc-111">Office 365 安全性與合規性中心和 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-111">Anti-spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="033dc-112">EOP 中反垃圾郵件原則的基本元素有：</span><span class="sxs-lookup"><span data-stu-id="033dc-112">The basic elements of an anti-spam policy in EOP are:</span></span>

- <span data-ttu-id="033dc-113">**垃圾郵件篩選原則**：指定垃圾郵件篩選裁決的動作和通知選項。</span><span class="sxs-lookup"><span data-stu-id="033dc-113">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="033dc-114">**垃圾郵件篩選規則**：指定垃圾郵件篩選原則的優先順序及收件者篩選器 (原則套用對象)。</span><span class="sxs-lookup"><span data-stu-id="033dc-114">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="033dc-115">當您在安全性與合規性中心管理反垃圾郵件原則時，上述兩個元素的差異不大：</span><span class="sxs-lookup"><span data-stu-id="033dc-115">The difference between these two elements isn't obvious when you manage anti-spam policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="033dc-116">當您在安全性與合規性中心建立反垃圾郵件原則時，其實是同時在建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則，只是為兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="033dc-116">When you create an anti-spam policy in the Security & Compliance Center, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="033dc-117">當您修改安全性與合規性中心中的反垃圾郵件原則時，與名稱、優先順序、已啟用或已停用、收件者篩選相關的設定皆會修改垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="033dc-117">When you modify an anti-spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="033dc-118">所有其他設定都會修改相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-118">All other settings modify the associated spam filter policy.</span></span>

- <span data-ttu-id="033dc-119">當您從安全性與合規性中心移除反垃圾郵件原則時，垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則都會被移除。</span><span class="sxs-lookup"><span data-stu-id="033dc-119">When you remove an anti-spam policy from the Security & Compliance Center, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="033dc-120">在 Exchange Online PowerShell 或獨立版 Exchange Online Protection PowerShell 中，垃圾郵件篩選原則與垃圾郵件篩選規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="033dc-120">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="033dc-121">您使用 **\*-HostedContentFilterPolicy** Cmdlet 來管理垃圾郵件篩選原則，但使用 **\*-HostedContentFilterRule** Cmdlet 來管理垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="033dc-121">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="033dc-122">在 PowerShell 中，您要先建立垃圾郵件篩選原則，然後再建立垃圾郵件篩選規則來識別將套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-122">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="033dc-123">在 PowerShell 中，您可以分開修改垃圾郵件篩選原則和垃圾郵件篩選規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-123">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>

- <span data-ttu-id="033dc-124">當您移除 PowerShell 中的垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會自動移除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="033dc-124">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-anti-spam-policy"></a><span data-ttu-id="033dc-125">預設的反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-125">Default anti-spam policy</span></span>

<span data-ttu-id="033dc-126">每個組織都有一個名為「預設」的內建反垃圾郵件原則，其中包含下列屬性：</span><span class="sxs-lookup"><span data-stu-id="033dc-126">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="033dc-127">名為「預設」垃圾郵件篩選原則適用於組織中所有的收件者，即使沒有與原則相關聯的垃圾郵件篩選規則 (收件者篩選器)。</span><span class="sxs-lookup"><span data-stu-id="033dc-127">The spam filter policy named Default is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="033dc-128">名為「預設」的原則具有不能修改的自訂優先順序 **Lowest** (一律最後才會套用的原則)。</span><span class="sxs-lookup"><span data-stu-id="033dc-128">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="033dc-129">任何自訂垃圾郵件原則的優先順序一律都高於名為「預設」的原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-129">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="033dc-130">名為「預設」的原則是預設的原則 (**IsDefault** 屬性具有值 `True`)，且您無法刪除預設原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-130">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="033dc-131">若要提高垃圾郵件篩選的效率，您可以建立自訂反垃圾郵件原則，以更嚴格的設定套用到特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="033dc-131">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="033dc-132">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="033dc-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="033dc-133">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="033dc-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="033dc-134">若要直接移至 [反垃圾郵件設定]\*\*\*\* 頁面，請使用 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="033dc-134">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="033dc-135">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="033dc-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="033dc-136">若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="033dc-136">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="033dc-137">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="033dc-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="033dc-138">若要新增、修改、刪除反垃圾郵件原則，您必須是**組織管理**或**安全性系統管理員**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="033dc-138">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="033dc-139">若要唯讀存取反垃圾郵件原則，您必須是**安全性讀取者**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="033dc-139">For read-only access to anti-spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="033dc-140">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱 [Office 365 安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="033dc-141">如需反垃圾郵件原則的建議設定，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings) (英文)。</span><span class="sxs-lookup"><span data-stu-id="033dc-141">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="033dc-142">使用安全性與合規性中心來建立反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-142">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="033dc-143">在安全性與合規性中心建立自訂的反垃圾郵件原則時，是同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則，且為兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="033dc-143">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="033dc-144">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-144">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="033dc-145">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-145">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="033dc-146">在隨即開啟的 [新增垃圾郵件篩選原則]\*\*\*\* 飛出視窗中進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="033dc-146">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="033dc-147">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="033dc-147">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="033dc-148">請勿使用下列字元：`\ % & * + / = ? { } | < > ( ) ; : , [ ] "`。</span><span class="sxs-lookup"><span data-stu-id="033dc-148">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="033dc-149">如果您先前在 Exchange 系統管理中心 (EAC) 中建立的反垃圾郵件原則包含這些字元，您應用 PowerShell 重新命名該反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-149">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="033dc-150">如需相關指示，請參閱本主題稍後的[使用 PowerShell 修改垃圾郵件篩選規則](#use-powershell-to-modify-spam-filter-rules)一節。</span><span class="sxs-lookup"><span data-stu-id="033dc-150">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="033dc-151">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="033dc-151">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="033dc-152">(選用) 展開 [垃圾郵件和大量動作]\*\*\*\* 區段，然後確認或設定如下設定：</span><span class="sxs-lookup"><span data-stu-id="033dc-152">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="033dc-153">**選取對內送的垃圾郵件和大量電子郵件要採取的動作**：根據下列垃圾郵件篩選裁決，選取或檢查對郵件要採取的動作：</span><span class="sxs-lookup"><span data-stu-id="033dc-153">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="033dc-154">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-154">**Spam**</span></span>
     - <span data-ttu-id="033dc-155">**高信賴度的垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-155">**High confidence spam**</span></span>
     - <span data-ttu-id="033dc-156">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-156">**Phishing email**</span></span>
     - <span data-ttu-id="033dc-157">**高信賴度的網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-157">**High confidence phishing email**</span></span>
     - <span data-ttu-id="033dc-158">**大量電子郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-158">**Bulk email**</span></span>

     <span data-ttu-id="033dc-159">下表說明垃圾郵件篩選裁決可採取的動作。</span><span class="sxs-lookup"><span data-stu-id="033dc-159">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="033dc-160">核取記號 (</span><span class="sxs-lookup"><span data-stu-id="033dc-160">A check mark (</span></span> ![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="033dc-162">) 表示可採取的動作 (並非所有的垃圾郵件篩選裁決皆可採取所有動作)。</span><span class="sxs-lookup"><span data-stu-id="033dc-162">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="033dc-163">核取記號之後有星號 (<sup>\*</sup>) 表示垃圾郵件篩選裁決的預設動作。</span><span class="sxs-lookup"><span data-stu-id="033dc-163">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||<span data-ttu-id="033dc-164">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-164">**Spam**</span></span>|<span data-ttu-id="033dc-165">**高信賴度<br/>垃圾郵件<br/>**</span><span class="sxs-lookup"><span data-stu-id="033dc-165">**High<br/>confidence<br/>spam**</span></span>|<span data-ttu-id="033dc-166">**網路釣魚<br/>電子郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-166">**Phishing<br/>email**</span></span>|<span data-ttu-id="033dc-167">**高信賴度<br/>網路釣魚<br/>電子郵件<br/>**</span><span class="sxs-lookup"><span data-stu-id="033dc-167">**High<br/>confidence<br/>phishing<br/>email**</span></span>|<span data-ttu-id="033dc-168">**大量<br/>電子郵件**</span><span class="sxs-lookup"><span data-stu-id="033dc-168">**Bulk<br/>email**</span></span>|
    |<span data-ttu-id="033dc-169">**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-169">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="033dc-170">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-170">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="033dc-171">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-171">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="033dc-174">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-174">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="033dc-175">**新增 X 標頭**：在郵件標頭中新增 X 標頭，並將郵件傳送到信箱。</span><span class="sxs-lookup"><span data-stu-id="033dc-175">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="033dc-176">您稍後可以在 [新增此 X 標頭文字]\*\*\*\* 方塊中輸入 X 標頭欄位的名稱 (不是值)。</span><span class="sxs-lookup"><span data-stu-id="033dc-176">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="033dc-177">裁決為**垃圾郵件**和**高信賴度垃圾郵件**的郵件會移至 [垃圾郵件] 資料夾。<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-177">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="033dc-181">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-181">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="033dc-182">**在主旨列前加上文字**：新增文字至郵件主旨列的開頭。</span><span class="sxs-lookup"><span data-stu-id="033dc-182">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="033dc-183">郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-183">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="033dc-184">您稍後可以在 [在主旨列前加上此文字]\*\*\*\* 方塊中輸入文字。</span><span class="sxs-lookup"><span data-stu-id="033dc-184">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="033dc-189">**將郵件重新導向至電子郵件地址**：將郵件傳送給其他收件者，而不是預定收件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-189">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="033dc-190">您稍後可以在 [重新導向到這個電子郵件地址]\*\*\*\* 方塊中指定收件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-190">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="033dc-196">**刪除郵件**：刪除整封郵件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="033dc-196">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="033dc-201">**隔離郵件**：將郵件傳送到隔離信箱，而不是傳送給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-201">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="033dc-202">您稍後可以在 [隔離]\*\*\*\* 方塊中指定郵件要在隔離區保留多久。</span><span class="sxs-lookup"><span data-stu-id="033dc-202">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="033dc-205">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="033dc-205">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="033dc-208">**無動作**</span><span class="sxs-lookup"><span data-stu-id="033dc-208">**No action**</span></span>|||||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <span data-ttu-id="033dc-210"><sup>1</sup> 在 Exchange Online 中，如果信箱已啟用垃圾郵件規則 (預設為啟用)，郵件會移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="033dc-210"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="033dc-211">如需詳細資訊，請參閱[在 Office 365中設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-211">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span><br/><span data-ttu-id="033dc-212">在獨立版 EOP 環境中，EOP 會保護內部部署 Exchange 信箱，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="033dc-212">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="033dc-213">如需詳細資訊，請參閱[設定獨立版 EOP 將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-213">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span><br/><br/><span data-ttu-id="033dc-214"><sup>2</sup> 您可以使用此值做為郵件流程規則 (又稱為傳輸規則) 的條件，以便篩選或傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="033dc-214"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="033dc-215">**選取閾值**：針對會觸發**大量電子郵件**垃圾郵件篩選裁決指定動作的訊息，指定大量抱怨層級 (BCL)，(大於、不大於或等於指定的值)。</span><span class="sxs-lookup"><span data-stu-id="033dc-215">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="033dc-216">較高的值表示不太理想的郵件 (更可能像是垃圾郵件)。</span><span class="sxs-lookup"><span data-stu-id="033dc-216">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="033dc-217">預設值為 7。</span><span class="sxs-lookup"><span data-stu-id="033dc-217">The default value is 7.</span></span> <span data-ttu-id="033dc-218">如需詳細資訊，請參閱 [Office 365 中的大量抱怨層級 (BCL)](bulk-complaint-level-values.md) 和[垃圾電子郵件與大量電子郵件之間有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-218">For more information, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="033dc-219">根據預設，PowerShell 只會將反垃圾郵件原則中的 MarkAsSpamBulkMail__ 設定為 `On`。</span><span class="sxs-lookup"><span data-stu-id="033dc-219">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="033dc-220">這項設定會嚴重影響**大量電子郵件**篩選的裁決：</span><span class="sxs-lookup"><span data-stu-id="033dc-220">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="033dc-221">**MarkAsSpamBulkMail__ 為 On**：大於閾值的 BCL 會轉換成 SCL 6 (對應到**垃圾郵件**篩選裁決)，然後對郵件採取**大量電子郵件**篩選裁決的動作。</span><span class="sxs-lookup"><span data-stu-id="033dc-221">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="033dc-222">**MarkAsSpamBulkMail__ 為 Off**：郵件會加蓋 BCL 戳記，但**大量電子郵件**篩選裁決不會執行任何動作__。</span><span class="sxs-lookup"><span data-stu-id="033dc-222">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="033dc-223">實際上，BCL 閾值和**大量電子郵件**篩選裁決動作並不相關。</span><span class="sxs-lookup"><span data-stu-id="033dc-223">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="033dc-224">**隔離**：指定當您選取**隔離郵件**做為垃圾郵件篩選裁決的動作時，郵件將存放在隔離中要多久的時間。</span><span class="sxs-lookup"><span data-stu-id="033dc-224">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="033dc-225">時間到了之後，就會刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="033dc-225">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="033dc-226">預設值是 30 天。</span><span class="sxs-lookup"><span data-stu-id="033dc-226">The default value is 30 days.</span></span> <span data-ttu-id="033dc-227">有效值是從 1 到 30 天。</span><span class="sxs-lookup"><span data-stu-id="033dc-227">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="033dc-228">如需隔離的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="033dc-228">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="033dc-229">Office 365 中的隔離區</span><span class="sxs-lookup"><span data-stu-id="033dc-229">Quarantine in Office 365</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="033dc-230">以 Office 365 系統管理員身分管理隔離的郵件與檔案</span><span class="sxs-lookup"><span data-stu-id="033dc-230">Manage quarantined messages and files as an admin in Office 365</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="033dc-231">以 Office 365 使用者身分尋找及釋出隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="033dc-231">Find and release quarantined messages as a user in Office 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="033dc-232">**新增此 X 標題文字**：只有當您選取 [新增 X 標頭]\*\*\*\* 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-232">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="033dc-233">您指定的值是郵件標頭「名稱」\*\*，會新增到郵件標頭中。</span><span class="sxs-lookup"><span data-stu-id="033dc-233">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="033dc-234">標題欄位的「值」\*\* 一律是 `This message appears to be spam`。</span><span class="sxs-lookup"><span data-stu-id="033dc-234">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="033dc-235">長度上限為 255 個字元，且值不能包含空格或冒號 (:)。</span><span class="sxs-lookup"><span data-stu-id="033dc-235">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="033dc-236">例如，如果輸入 `X-This-is-my-custom-header` 值，則新增到郵件的 X 標頭為 `X-This-is-my-custom-header: This message appears to be spam.`。</span><span class="sxs-lookup"><span data-stu-id="033dc-236">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="033dc-237">如果您輸入的值包含空格或冒號 (:)，系統會忽略您輸入的值，並在郵件中新增預設的 X 標頭 (`X-This-Is-Spam: This message appears to be spam.`)。</span><span class="sxs-lookup"><span data-stu-id="033dc-237">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="033dc-238">**在主旨列前加上此文字**：只有當您選取 [在主旨列前加上文字]\*\*\*\* 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-238">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="033dc-239">輸入要新增至郵件主旨列開頭的文字。</span><span class="sxs-lookup"><span data-stu-id="033dc-239">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="033dc-240">**重新導向到這個電子郵件地址**：只有當您選取 [將郵件重新導向至電子郵件地址]\*\*\*\* 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-240">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="033dc-241">輸入您要遞送郵件的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="033dc-241">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="033dc-242">您可以輸入多個值並以分號 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="033dc-242">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="033dc-243">**安全提示**：預設會啟用安全提示，但您可以清除 [開啟]\*\*\*\* 核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="033dc-243">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="033dc-244">如需有關安全性提示的詳細資訊，請參閱 [Office 365 中的電子郵件安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-244">For more information about Safety Tips, see [Safety tips in email messages in Office 365](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="033dc-245">**零時差自動清除**設定：ZAP 會偵測傳送到 Exchange Online 信箱的郵件，並採取行動。</span><span class="sxs-lookup"><span data-stu-id="033dc-245">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="033dc-246">如需有關 ZAP 的詳細資訊，請參閱[零時差自動清除 - 防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-246">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="033dc-247">**垃圾郵件 ZAP**：預設會啟用 ZAP 以偵測垃圾郵件，但您可以清除 [開啟]\*\*\*\* 核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="033dc-247">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="033dc-248">**網路釣魚 ZAP**：預設會啟用 ZAP 以偵測網路釣魚，但您可以清除 [開啟]\*\*\*\* 核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="033dc-248">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="033dc-249">(選用) 展開 [允許清單]\*\*\*\* 區段，依據允許跳過垃圾郵件篩選的電子郵件地址或電子郵件網域，來設定郵件寄件人：</span><span class="sxs-lookup"><span data-stu-id="033dc-249">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   > <ul><li><span data-ttu-id="033dc-250">在此新增網域前請仔細考慮。</span><span class="sxs-lookup"><span data-stu-id="033dc-250">Think very carefully before you add domains here.</span></span> <span data-ttu-id="033dc-251">如需詳細資訊，請參閱[在 Office 365 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-251">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md)</span></span></li><li><span data-ttu-id="033dc-252">絕對不要將接受的網域 (您擁有的網域) 或一般網域 (例如 microsoft.com 或 office.com) 新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="033dc-252">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="033dc-253">這會讓攻擊者能夠略過垃圾郵件篩選將電子郵件送進您的貴組織。</span><span class="sxs-lookup"><span data-stu-id="033dc-253">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span></li></ul>

   - <span data-ttu-id="033dc-254">**允許寄件者**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-254">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="033dc-255">在 [允許的寄件者清單]\*\*\*\* 飛出視窗中：</span><span class="sxs-lookup"><span data-stu-id="033dc-255">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="033dc-256">a.</span><span class="sxs-lookup"><span data-stu-id="033dc-256">a.</span></span> <span data-ttu-id="033dc-257">輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="033dc-257">Enter the sender's email address.</span></span> <span data-ttu-id="033dc-258">您可以指定多個電子郵件地址並以分號 (;) 隔開。</span><span class="sxs-lookup"><span data-stu-id="033dc-258">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="033dc-259">b.</span><span class="sxs-lookup"><span data-stu-id="033dc-259">b.</span></span> <span data-ttu-id="033dc-260">按一下</span><span class="sxs-lookup"><span data-stu-id="033dc-260">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="033dc-262">以新增寄件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-262">to add the senders.</span></span>

      <span data-ttu-id="033dc-263">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="033dc-263">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="033dc-264">您新增的寄件者會出現在飛出視窗的 [允許的寄件者]\*\*\*\* 區段中。</span><span class="sxs-lookup"><span data-stu-id="033dc-264">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="033dc-265">若要刪除寄件者，按一下 ![移除圖示](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="033dc-265">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="033dc-266">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-266">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="033dc-267">**允許網域**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-267">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="033dc-268">在隨即出現的 [允許的網域清單]\*\*\*\* 飛出視窗中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="033dc-268">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="033dc-269">a.</span><span class="sxs-lookup"><span data-stu-id="033dc-269">a.</span></span> <span data-ttu-id="033dc-270">輸入網域。</span><span class="sxs-lookup"><span data-stu-id="033dc-270">Enter the domain.</span></span> <span data-ttu-id="033dc-271">您可以指定多個網域並以分號 (;) 隔開的。</span><span class="sxs-lookup"><span data-stu-id="033dc-271">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="033dc-272">b.</span><span class="sxs-lookup"><span data-stu-id="033dc-272">b.</span></span> <span data-ttu-id="033dc-273">按一下</span><span class="sxs-lookup"><span data-stu-id="033dc-273">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="033dc-275">以新增網域。</span><span class="sxs-lookup"><span data-stu-id="033dc-275">to add the domains.</span></span>

      <span data-ttu-id="033dc-276">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="033dc-276">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="033dc-277">您新增的網域會出現在飛出視窗的 [允許的網域]\*\*\*\* 區段中。</span><span class="sxs-lookup"><span data-stu-id="033dc-277">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="033dc-278">若要刪除網域，按一下 ![移除圖示](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="033dc-278">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="033dc-279">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-279">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="033dc-280">(選用) 展開 [封鎖清單]\*\*\*\* 區段，依據將一律標示為「高信賴度的垃圾郵件」的電子郵件地址或電子郵件網域，來設定郵件寄件人：</span><span class="sxs-lookup"><span data-stu-id="033dc-280">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="033dc-281">手動封鎖網域並不危險，但會增加您的管理工作量。</span><span class="sxs-lookup"><span data-stu-id="033dc-281">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="033dc-282">如需詳細資訊，請參閱[在 Office 365 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-282">For more information, see [Create block sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="033dc-283">**封鎖寄件者**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-283">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="033dc-284">在隨即出現的 [封鎖的寄件者清單]\*\*\*\* 飛出視窗中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="033dc-284">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="033dc-285">a.</span><span class="sxs-lookup"><span data-stu-id="033dc-285">a.</span></span> <span data-ttu-id="033dc-286">輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="033dc-286">Enter the sender's email address.</span></span> <span data-ttu-id="033dc-287">您可以指定多個電子郵件地址並以分號 (;) 隔開。</span><span class="sxs-lookup"><span data-stu-id="033dc-287">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="033dc-288">不可使用萬用字元 (\*)。</span><span class="sxs-lookup"><span data-stu-id="033dc-288">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="033dc-289">b.</span><span class="sxs-lookup"><span data-stu-id="033dc-289">b.</span></span> <span data-ttu-id="033dc-290">按一下</span><span class="sxs-lookup"><span data-stu-id="033dc-290">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="033dc-292">以新增寄件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-292">to add the senders.</span></span>

      <span data-ttu-id="033dc-293">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="033dc-293">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="033dc-294">您新增的寄件者會出現在飛出視窗的 [封鎖的寄件者]\*\*\*\* 區段中。</span><span class="sxs-lookup"><span data-stu-id="033dc-294">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="033dc-295">若要刪除寄件者，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="033dc-295">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="033dc-296">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-296">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="033dc-297">**封鎖網域**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-297">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="033dc-298">在隨即出現的 [封鎖的網域清單]\*\*\*\* 飛出視窗中：</span><span class="sxs-lookup"><span data-stu-id="033dc-298">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="033dc-299">a.</span><span class="sxs-lookup"><span data-stu-id="033dc-299">a.</span></span> <span data-ttu-id="033dc-300">輸入網域。</span><span class="sxs-lookup"><span data-stu-id="033dc-300">Enter the domain.</span></span> <span data-ttu-id="033dc-301">您可以指定多個網域並以分號 (;) 隔開的。</span><span class="sxs-lookup"><span data-stu-id="033dc-301">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="033dc-302">不可使用萬用字元 (\*)。</span><span class="sxs-lookup"><span data-stu-id="033dc-302">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="033dc-303">b.</span><span class="sxs-lookup"><span data-stu-id="033dc-303">b.</span></span> <span data-ttu-id="033dc-304">按一下</span><span class="sxs-lookup"><span data-stu-id="033dc-304">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="033dc-306">以新增網域。</span><span class="sxs-lookup"><span data-stu-id="033dc-306">to add the domains.</span></span>

      <span data-ttu-id="033dc-307">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="033dc-307">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="033dc-308">您新增的網域會顯示在飛出視窗的 [封鎖的網域]\*\*\*\* 清單中。</span><span class="sxs-lookup"><span data-stu-id="033dc-308">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="033dc-309">若要刪除網域，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="033dc-309">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="033dc-310">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-310">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="033dc-311">(選用) 展開 [國際垃圾郵件]\*\*\*\* 區段，根據垃圾郵件篩選會封鎖的電子郵件語言或來源國家/地區，來設定電子郵件語言：</span><span class="sxs-lookup"><span data-stu-id="033dc-311">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="033dc-312">**篩選以下列語言撰寫的電子郵件**：預設會停用此設定 ([狀態： 關閉]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="033dc-312">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="033dc-313">按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-313">Click **Edit**.</span></span> <span data-ttu-id="033dc-314">在隨即出現的 [國際垃圾郵件設定]\*\*\*\* 飛出視窗中，進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="033dc-314">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="033dc-315">**篩選以下列語言撰寫的電子郵件**：選取核取方塊以啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="033dc-315">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="033dc-316">清除核取方塊可停用此設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-316">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="033dc-317">在方塊中按一下，然後開始輸入語言的「名稱」\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-317">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="033dc-318">將會顯示篩選過的支援語言清單，以及對應的 ISO 639-2 語言代碼。</span><span class="sxs-lookup"><span data-stu-id="033dc-318">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="033dc-319">當您找到所需語言時，請選取該語言。</span><span class="sxs-lookup"><span data-stu-id="033dc-319">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="033dc-320">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="033dc-320">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="033dc-321">您選取的語言清單會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="033dc-321">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="033dc-322">若要刪除語言，按一下</span><span class="sxs-lookup"><span data-stu-id="033dc-322">To delete a language, click</span></span> ![移除按鈕](../../media/scc-remove-icon.png)<span data-ttu-id="033dc-324">。</span><span class="sxs-lookup"><span data-stu-id="033dc-324">.</span></span>

     <span data-ttu-id="033dc-325">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-325">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="033dc-326">**篩選從下列國家或地區傳送的電子郵件**：預設會停用此設定 ([狀態：關閉]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="033dc-326">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="033dc-327">若要啟用，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-327">To enable it, click **Edit**.</span></span> <span data-ttu-id="033dc-328">在隨即出現的 [國際垃圾郵件設定]\*\*\*\* 飛出視窗中，進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="033dc-328">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="033dc-329">**篩選從下列國家或地區傳送的電子郵件**：選取核取方塊以啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-329">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="033dc-330">清除核取方塊可停用此設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-330">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="033dc-331">在方塊中按一下，然後開始輸入國家或地區的「名稱」\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-331">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="033dc-332">將會顯示篩選過的支援國家/地區清單，以及對應的 ISO 3166-1 雙字母國碼。</span><span class="sxs-lookup"><span data-stu-id="033dc-332">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="033dc-333">當您找到您要尋找的國家或地區時，請選取它。</span><span class="sxs-lookup"><span data-stu-id="033dc-333">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="033dc-334">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="033dc-334">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="033dc-335">您選取的國家/地區清單會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="033dc-335">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="033dc-336">若要刪除國家或地區，按一下</span><span class="sxs-lookup"><span data-stu-id="033dc-336">To delete a country or region, click</span></span> ![移除按鈕](../../media/scc-remove-icon.png)<span data-ttu-id="033dc-338">。</span><span class="sxs-lookup"><span data-stu-id="033dc-338">.</span></span>

     <span data-ttu-id="033dc-339">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-339">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="033dc-340">選用的 [垃圾郵件屬性]\*\*\*\* 區段中有的進階垃圾郵件篩選 (ASF) 設定，預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="033dc-340">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="033dc-341">我們正逐漸淘汰 ASF 設定，其功能正併入篩選堆疊的其他部分。</span><span class="sxs-lookup"><span data-stu-id="033dc-341">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="033dc-342">建議您將反垃圾郵件原則中的所有 ASF 設定關閉。</span><span class="sxs-lookup"><span data-stu-id="033dc-342">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="033dc-343">如需有關這些設定的詳細資訊，請參閱 [Office 365 中的進階垃圾郵件篩選設定](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-343">For details about these settings, see [Advanced Spam Filter settings in Office 365](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="033dc-344">(必要) 展開 [套用至]\*\*\*\* 區段，找出原則所套用的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-344">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="033dc-345">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="033dc-345">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="033dc-346">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="033dc-346">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="033dc-347">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<群組 1 的成員\>_)。</span><span class="sxs-lookup"><span data-stu-id="033dc-347">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="033dc-348">最簡單的方法是按一下 [新增條件]\*\*\*\* 三次，查看所有可用的條件。</span><span class="sxs-lookup"><span data-stu-id="033dc-348">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="033dc-349">您可以按一下 ![移除按鈕](../../media/scc-remove-icon.png)移除您不想要設定的條件。</span><span class="sxs-lookup"><span data-stu-id="033dc-349">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="033dc-350">**收件者網域為**：指定 Office 365 中一個或多個接受網域 (已設定) 中的收件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-350">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="033dc-351">按一下 [新增標籤]\*\*\*\* 方塊，可查看並選取網域。</span><span class="sxs-lookup"><span data-stu-id="033dc-351">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="033dc-352">如果有不止一個網域，再次按一下 [新增標籤]\*\*\*\* 方塊可選取其他網域。</span><span class="sxs-lookup"><span data-stu-id="033dc-352">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="033dc-353">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="033dc-353">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="033dc-354">在 [新增標籤]\*\*\*\* 內按一下，然後開始輸入以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="033dc-354">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="033dc-355">再次按一下 [新增標籤]\*\*\*\* 方塊以選取其他收件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-355">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="033dc-356">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="033dc-356">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="033dc-357">在 [新增標籤]\*\*\*\* 內按一下，然後開始輸入以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="033dc-357">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="033dc-358">再次按一下 [新增標籤]\*\*\*\* 方塊以選取其他收件者。</span><span class="sxs-lookup"><span data-stu-id="033dc-358">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="033dc-359">**除了**：若要為規則新增例外情況，按一下 [新增條件]\*\*\*\* 三次，即可查看所有可用的例外。</span><span class="sxs-lookup"><span data-stu-id="033dc-359">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="033dc-360">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="033dc-360">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="033dc-361">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-361">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="033dc-362">使用安全性與合規性中心來檢視反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-362">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="033dc-363">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-363">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="033dc-364">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="033dc-364">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="033dc-365">預設原則名為**預設的垃圾郵件篩選原則**。</span><span class="sxs-lookup"><span data-stu-id="033dc-365">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="033dc-366">您建立的自訂原則的 [類型]\*\*\*\* 資料行中的值是 [自訂的反垃圾郵件原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-366">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="033dc-367">重要的原則設定會顯示在展開的原則詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="033dc-367">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="033dc-368">若要查看更多詳細資料，按一下 [編輯原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-368">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="033dc-369">使用安全性與合規性中心來修改反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-369">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="033dc-370">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-370">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="033dc-371">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="033dc-371">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="033dc-372">預設原則名為**預設的垃圾郵件篩選原則**。</span><span class="sxs-lookup"><span data-stu-id="033dc-372">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="033dc-373">您建立的自訂原則的 [類型]\*\*\*\* 資料行中的值是 [自訂的反垃圾郵件原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-373">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="033dc-374">按一下 [編輯原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-374">Click **Edit policy**.</span></span>

<span data-ttu-id="033dc-375">在飛出視窗中顯示的設定會和[使用安全性與合規性中心來建立反垃圾郵件原則](#use-the-security--compliance-center-to-create-anti-spam-policies)一節可用的設定完全相同。</span><span class="sxs-lookup"><span data-stu-id="033dc-375">The settings in the flyout that appears are identical to the settings that are available in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="033dc-376">若是名為**預設的垃圾郵件篩選原則**的預設反垃圾郵件原則，則無法使用 [套用至]\*\*\*\* 區段 (原則套用至每個人)，而且您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-376">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="033dc-377">若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="033dc-377">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="033dc-378">啟用或停用反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-378">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="033dc-379">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-379">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="033dc-380">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開您所建立的自訂原則 (其 [類型]\*\*\*\* 資料行的值是 [自訂的反垃圾郵件原則]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="033dc-380">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="033dc-381">在隨即出現的展開的原則詳細資料中，請注意**開啟**資料行的值。</span><span class="sxs-lookup"><span data-stu-id="033dc-381">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="033dc-382">將切換開關向左移動以停用原則：</span><span class="sxs-lookup"><span data-stu-id="033dc-382">Move the toggle to the left to disable the policy:</span></span> ![關閉](../../media/scc-toggle-off.png)

   <span data-ttu-id="033dc-384">將切換開關向右移動以啟用原則：</span><span class="sxs-lookup"><span data-stu-id="033dc-384">Move the toggle to the right to enable the policy:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="033dc-386">您無法停用預設的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-386">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="033dc-387">設定自訂反垃圾郵件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="033dc-387">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="033dc-388">根據預設，系統是根據反垃圾郵件原則的建立順序給予優先順序 (較新原則的優先順序比較舊原則的優先順序低)。</span><span class="sxs-lookup"><span data-stu-id="033dc-388">By default, anti-spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="033dc-389">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="033dc-389">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="033dc-390">不會有兩個原則的優先順序相同。</span><span class="sxs-lookup"><span data-stu-id="033dc-390">No two policies can have the same priority.</span></span>

<span data-ttu-id="033dc-391">自訂反垃圾郵件原則會以其處理順序顯示 (第一個原則的**優先順序**值為 0)。</span><span class="sxs-lookup"><span data-stu-id="033dc-391">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="033dc-392">名為**預設的垃圾郵件篩選原則**的預設反垃圾郵件原則具有 **Lowest** 優先順序值，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="033dc-392">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="033dc-393">**附註**：在安全性與合規性中心中，只能在建立反垃圾郵件原則後變更它的優先順序。</span><span class="sxs-lookup"><span data-stu-id="033dc-393">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="033dc-394">在 PowerShell 中，您可以在建立垃圾郵件篩選規則時覆寫預設優先順序 (會影響現有規則的優先順序)。</span><span class="sxs-lookup"><span data-stu-id="033dc-394">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="033dc-395">若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序]\*\*\*\* 數字)。</span><span class="sxs-lookup"><span data-stu-id="033dc-395">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="033dc-396">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-396">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="033dc-397">在 [反垃圾郵件設定]\*\*\*\* 頁面上，找到 [類型]\*\*\*\* 資料行的值為[自訂的反垃圾郵件原則]\*\*\*\* 的原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-397">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="033dc-398">請注意 [優先順序]\*\*\*\* 資料行中的值：</span><span class="sxs-lookup"><span data-stu-id="033dc-398">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="033dc-399">優先順序最高的自訂反垃圾郵件原則的值是 ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **0**。</span><span class="sxs-lookup"><span data-stu-id="033dc-399">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="033dc-400">優先順序最低的自訂反垃圾郵件原則的值是 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **n** (例如，![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **3**)。</span><span class="sxs-lookup"><span data-stu-id="033dc-400">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="033dc-401">如果有三個以上的自訂反垃圾郵件原則，則最高和最低優先順序之間的原則的值會是 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png)![向下鍵圖示](../../media/ITPro-EAC-DownArrowIcon.png) **n** (例如，![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png)![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **2**)。</span><span class="sxs-lookup"><span data-stu-id="033dc-401">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="033dc-402">按一下</span><span class="sxs-lookup"><span data-stu-id="033dc-402">Click</span></span> ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="033dc-404">或</span><span class="sxs-lookup"><span data-stu-id="033dc-404">or</span></span> ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="033dc-406">可在優先順序清單中，將自訂反垃圾郵件原則往上或向下移動。</span><span class="sxs-lookup"><span data-stu-id="033dc-406">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="033dc-407">設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="033dc-407">Configure end-user spam notifications</span></span>

<span data-ttu-id="033dc-408">當垃圾郵件篩選裁決要隔離郵件時，您可以設定使用者垃圾郵件通知，讓收件者知道寄給他們的郵件發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="033dc-408">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="033dc-409">如需有關這些通知的詳細資訊，請參閱 [Office 365 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="033dc-409">For more information about these notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="033dc-410">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-410">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="033dc-411">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="033dc-411">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="033dc-412">預設原則名為**預設的垃圾郵件篩選原則**。</span><span class="sxs-lookup"><span data-stu-id="033dc-412">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="033dc-413">您建立的自訂原則的 [類型]\*\*\*\* 資料行中的值是 [自訂的反垃圾郵件原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-413">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="033dc-414">在隨即出現的展開的原則詳細資料中，按一下 [設定使用者垃圾郵件通知]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-414">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="033dc-415">在隨即開啟的 **[\<原則名稱\>]** 視窗中，進行設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="033dc-415">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="033dc-416">**啟用使用者垃圾郵件通知**：選取核取方塊以啟用通知。</span><span class="sxs-lookup"><span data-stu-id="033dc-416">**Enable end-user spam notifications**: Select the checkbobx to enable notifications.</span></span> <span data-ttu-id="033dc-417">清除核取方塊以停用通知。</span><span class="sxs-lookup"><span data-stu-id="033dc-417">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="033dc-418">**傳送使用者垃圾郵件通知的頻率 (天)**：選取每隔幾天要傳送通知。</span><span class="sxs-lookup"><span data-stu-id="033dc-418">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="033dc-419">預設值是 3 天。</span><span class="sxs-lookup"><span data-stu-id="033dc-419">The default value is 3 days.</span></span> <span data-ttu-id="033dc-420">您可以輸入 1 到 15 天。</span><span class="sxs-lookup"><span data-stu-id="033dc-420">You can enter 1 to 15 days.</span></span>

   - <span data-ttu-id="033dc-421">**通知語言**：按一下下拉式清單並從中選取可用的語言。</span><span class="sxs-lookup"><span data-stu-id="033dc-421">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="033dc-422">預設值為 [預設]\*\*\*\*，表示使用者隔離通知使用 EOP 組織的預設語言。</span><span class="sxs-lookup"><span data-stu-id="033dc-422">The default value is **Default**, which means end-user quarantine notifications use the default language of the EOP organization.</span></span>

   <span data-ttu-id="033dc-423">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-423">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="033dc-424">使用安全性與合規性中心來移除反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-424">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="033dc-425">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-425">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="033dc-426">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開您想要刪除的自訂原則 (其 [類型]\*\*\*\* 資料行的值是 [自訂的反垃圾郵件原則]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="033dc-426">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="033dc-427">在隨即出現的展開原則詳細資料中，按一下 [刪除原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-427">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="033dc-428">在隨即出現的警告對話方塊中，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="033dc-428">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="033dc-429">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-429">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="033dc-430">使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 來設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-430">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="033dc-431">下列反垃圾郵件原則設定僅適用於 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="033dc-431">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="033dc-432">MarkAsSpamBulkMail__ 參數預設是 `On`。</span><span class="sxs-lookup"><span data-stu-id="033dc-432">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="033dc-433">此設定的效果已在本主題前面的 [使用安全性與合規性中心來建立本反垃圾郵件原則](#use-the-security--compliance-center-to-create-anti-spam-policies) 一節中說明。</span><span class="sxs-lookup"><span data-stu-id="033dc-433">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="033dc-434">使用者垃圾郵件隔離通知的下列設定：</span><span class="sxs-lookup"><span data-stu-id="033dc-434">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="033dc-435">DownloadLink__ 參數，用於顯示或隱藏 Outlook 的垃圾郵件報告工具連結。</span><span class="sxs-lookup"><span data-stu-id="033dc-435">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="033dc-436">EndUserSpamNotificationCustomSubject__ 參數，您可以用來自訂通知的主旨列。</span><span class="sxs-lookup"><span data-stu-id="033dc-436">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="033dc-437">使用 PowerShell 來建立反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="033dc-437">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="033dc-438">在 PowerShell 中建立反垃圾郵件原則需執行兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="033dc-438">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="033dc-439">建立垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-439">Create the spam filter policy.</span></span>

2. <span data-ttu-id="033dc-440">建立垃圾郵件選規則，此規則會指定要套用規則的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-440">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="033dc-441">**附註**：</span><span class="sxs-lookup"><span data-stu-id="033dc-441">**Notes**:</span></span>

- <span data-ttu-id="033dc-442">您可以建立新的垃圾郵件篩選規則，並對其指派未關聯的現有垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-442">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="033dc-443">垃圾郵件篩選規則無法與多個垃圾郵件篩選原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="033dc-443">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="033dc-444">您可以使用 PowerShell 對安全性與合規性中心中還沒有的新垃圾郵件篩選原則進行下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="033dc-444">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="033dc-445">建立「停用」的新原則 (在 **New-HostedContentFilterRule** Cmdlet 中啟用__ `$false`)。</span><span class="sxs-lookup"><span data-stu-id="033dc-445">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="033dc-446">在建立期間設定原則的優先順序 (在 **New-HostedContentFilterRule** Cmdlet 使用 _Priority_ _\<Number\>_)。</span><span class="sxs-lookup"><span data-stu-id="033dc-446">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="033dc-447">您在 PowerShell 中建立的新垃圾郵件篩選原則不會顯示在安全性與合規性中心中，直到您將該原則指派到垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="033dc-447">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="033dc-448">步驟 1：使用 PowerShell 建立垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="033dc-448">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="033dc-449">使用下列語法建立垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="033dc-449">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="033dc-450">本範例會建立名為 Contoso Executives 的垃圾郵件篩選原則，並使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="033dc-450">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="033dc-451">當垃圾郵件篩選裁決為垃圾郵件或高信賴度垃圾郵件時隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="033dc-451">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="033dc-452">BCL 6 會觸發大量垃圾郵件篩選裁決的動作。</span><span class="sxs-lookup"><span data-stu-id="033dc-452">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="033dc-453">**Set-hostedcontentfilterpolicy** 和 **Set-Set-hostedcontentfilterpolicy** 有較舊的 ZapEnabled__ 參數，以及較新的 PhishZapEnabled__ 和 SpamZapEnabled__ 參數。</span><span class="sxs-lookup"><span data-stu-id="033dc-453">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="033dc-454">ZapEnabled__ 參數已在 2020 年 2 月淘汰。</span><span class="sxs-lookup"><span data-stu-id="033dc-454">The _ZapEnabled_ parameter was deprecated in February, 2020.</span></span> <span data-ttu-id="033dc-455">PhishZapEnabled__ 和 SpamZapEnabled__ 參數則用來繼承 ZapEnabled__ 參數的值。</span><span class="sxs-lookup"><span data-stu-id="033dc-455">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="033dc-456">不過，如果您在命令中使用 PhishZapEnabled__ 和 SpamZapEnabled__ 參數，或是在安全性與合規性中心中的反垃圾郵件原則中使用 [垃圾郵件 ZAP]\*\*\*\* 或 [網路釣魚 ZAP]\*\*\*\* 設定，系統就會忽略 ZapEnabled__ 參數的值。</span><span class="sxs-lookup"><span data-stu-id="033dc-456">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="033dc-457">換句話說，請勿使用 ZapEnabled__ 參數，改用 PhishZapEnabled__ 和 SpamZapEnabled__ 參數。</span><span class="sxs-lookup"><span data-stu-id="033dc-457">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="033dc-458">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="033dc-458">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="033dc-459">步驟 2：使用 PowerShell 建立垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="033dc-459">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="033dc-460">使用下列語法建立垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="033dc-460">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="033dc-461">此範例使用下列設定來建立名為 Contoso Executives 的新垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="033dc-461">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="033dc-462">名為 Contoso Executives 的垃圾郵件篩選原則會與此規則相關聯。</span><span class="sxs-lookup"><span data-stu-id="033dc-462">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="033dc-463">此規則會套用至名為 ContosoExecutives Group 的群組成員。</span><span class="sxs-lookup"><span data-stu-id="033dc-463">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="033dc-464">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="033dc-464">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="033dc-465">使用 PowerShell 檢視垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="033dc-465">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="033dc-466">若要傳回所有垃圾郵件篩選原則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="033dc-466">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="033dc-467">若要傳回特定垃圾郵件篩選原則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="033dc-467">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="033dc-468">此範例會傳回名為 Executives 的垃圾郵件篩選原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="033dc-468">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="033dc-469">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="033dc-469">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="033dc-470">使用 PowerShell 檢視垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="033dc-470">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="033dc-471">若要檢視現有的垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="033dc-471">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled]
```

<span data-ttu-id="033dc-472">若要傳回所有垃圾郵件篩選規則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="033dc-472">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="033dc-473">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="033dc-473">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="033dc-474">若要傳回特定垃圾郵件篩選規則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="033dc-474">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="033dc-475">此範例會傳回名為 Contoso Executives 的垃圾郵件篩選規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="033dc-475">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="033dc-476">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="033dc-476">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="033dc-477">使用 PowerShell 修改垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="033dc-477">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="033dc-478">除了下列項目外，當您如同本主題前面的[步驟 1：使用 PowerShell 建立垃圾郵件篩選原則](#step-1-use-powershell-to-create-a-spam-filter-policy) 一節所述在 PowerShell 中修改垃圾郵件篩選原則時，會出現相同的設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-478">Other than the following items, the same settings are available when you modify a spam filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="033dc-479">MakeDefault__ 可將指定的原則轉換成預設原則 (套用至每個人，一律**最低**優先順序，且無法刪除)，但只有當您在 PowerShell 中修改垃圾郵件篩選原則時才能使用。</span><span class="sxs-lookup"><span data-stu-id="033dc-479">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="033dc-480">您無法重新命名垃圾郵件篩選原則(**Set-hostedcontentfilterpolicy** Cmdlet 沒有 Name__ 參數)。</span><span class="sxs-lookup"><span data-stu-id="033dc-480">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="033dc-481">當您在安全性與合規性中心中重新命名反垃圾郵件原則時，只會重新命名垃圾郵件篩選「規則」__。</span><span class="sxs-lookup"><span data-stu-id="033dc-481">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="033dc-482">使用下列語法修改垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="033dc-482">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="033dc-483">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="033dc-483">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="033dc-484">使用 PowerShell 修改垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="033dc-484">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="033dc-485">當您用 PowerShell 修改垃圾郵件篩選規則時，唯一無法使用的設定為 Enabled__ 參數 (可讓您建立停用的規則)。</span><span class="sxs-lookup"><span data-stu-id="033dc-485">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="033dc-486">若要啟用或停用現有的垃圾郵件篩選規則，請看下一節。</span><span class="sxs-lookup"><span data-stu-id="033dc-486">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="033dc-487">另一方面，當您用 PowerShell 修改垃圾郵件篩選規則時，將無法使用其他設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-487">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="033dc-488">當您如同本主題前面的 [步驟 2：使用 PowerShell 建立垃圾郵件篩選規則](#step-2-use-powershell-to-create-a-spam-filter-rule)一節所述建立規則時，會出現相同的設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-488">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="033dc-489">使用下列語法修改垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="033dc-489">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="033dc-490">此範例會替可能導致安全性與合規性中心出問題的現有垃圾郵件篩選規則 `{Fabrikam Spam Filter}` 重新命名。</span><span class="sxs-lookup"><span data-stu-id="033dc-490">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="033dc-491">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="033dc-491">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="033dc-492">使用 PowerShell 來啟用或停用垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="033dc-492">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="033dc-493">使用 PowerShell 啟用或停用垃圾郵件篩選規則，可啟用或停用整個反垃圾郵件原則 (垃圾郵件篩選規則和指派的垃圾郵件篩選原則)。</span><span class="sxs-lookup"><span data-stu-id="033dc-493">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="033dc-494">您無法啟用或停用預設的反垃圾郵件原則 (一定一律會套用至所有收件者)。</span><span class="sxs-lookup"><span data-stu-id="033dc-494">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="033dc-495">若要在 PowerShell 中啟用或停用垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="033dc-495">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="033dc-496">此範例會停用名為 Marketing Department 的垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="033dc-496">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="033dc-497">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="033dc-497">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="033dc-498">如需詳細的語法和參數資訊，請參閱 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="033dc-498">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="033dc-499">使用 PowerShell 設定垃圾郵件篩選規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="033dc-499">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="033dc-500">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="033dc-500">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="033dc-501">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="033dc-501">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="033dc-502">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="033dc-502">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="033dc-503">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="033dc-503">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="033dc-504">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="033dc-504">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="033dc-505">若要在 PowerShell 中設定垃圾郵件篩選規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="033dc-505">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="033dc-506">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="033dc-506">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="033dc-507">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="033dc-507">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="033dc-508">**附註**：</span><span class="sxs-lookup"><span data-stu-id="033dc-508">**Notes**:</span></span>

- <span data-ttu-id="033dc-509">若要在建立新規則時設定其優先順序，請使用 **New-HostedContentFilterRule** Cmdlet 上的 Priority__ 參數。</span><span class="sxs-lookup"><span data-stu-id="033dc-509">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="033dc-510">預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，且一律有不可修改的優先順序值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="033dc-510">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="033dc-511">使用 PowerShell 移除垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="033dc-511">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="033dc-512">當您使用 PowerShell 來移除垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會遭到移除。</span><span class="sxs-lookup"><span data-stu-id="033dc-512">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="033dc-513">若要在 PowerShell 中移除垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="033dc-513">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="033dc-514">此範例會移除名為 Marketing Department 的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="033dc-514">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="033dc-515">如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="033dc-515">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="033dc-516">使用 PowerShell 移除垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="033dc-516">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="033dc-517">當您使用 PowerShell 來移除垃圾郵件篩選規則時，對應的垃圾郵件篩選原則不會遭到移除。</span><span class="sxs-lookup"><span data-stu-id="033dc-517">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="033dc-518">若要在 PowerShell 中移除垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="033dc-518">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="033dc-519">此範例會移除名為 Marketing Department 的垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="033dc-519">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="033dc-520">如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="033dc-520">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="033dc-521">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="033dc-521">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="033dc-522">傳送 GTUBE 訊息以測試您的垃圾郵件原則設定</span><span class="sxs-lookup"><span data-stu-id="033dc-522">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="033dc-523">只有當寄出 GTUBE 訊息的電子郵件組織無法掃描輸出的垃圾郵件時，這些步驟才有用。</span><span class="sxs-lookup"><span data-stu-id="033dc-523">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="033dc-524">如果能掃描，則無法傳送測試郵件。</span><span class="sxs-lookup"><span data-stu-id="033dc-524">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="033dc-525">未經同意大量電子郵件的一般測試 (GTUBE) 是文字字串，可放入測試郵件中，用於確認貴組織的反垃圾郵件設定。</span><span class="sxs-lookup"><span data-stu-id="033dc-525">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="033dc-526">GTUBE 訊息類似於歐洲反電腦病毒協會 (EICAR) 用於測試惡意程式碼設定的文字檔。</span><span class="sxs-lookup"><span data-stu-id="033dc-526">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="033dc-527">請在電子郵件中，將下列 GTUBE 文字放在單一行上，不加任何空格或換行：</span><span class="sxs-lookup"><span data-stu-id="033dc-527">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="033dc-528">允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="033dc-528">Allow/Block Lists</span></span>

<span data-ttu-id="033dc-529">有時我們的篩選器會錯過郵件，或者我們的系統需要時間才能完成目標。</span><span class="sxs-lookup"><span data-stu-id="033dc-529">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="033dc-530">在此情況下，反垃圾郵件原則提供 [允許] 和 [封鎖] 清單來提供覆寫目前的結果。</span><span class="sxs-lookup"><span data-stu-id="033dc-530">In this cases, the antispam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="033dc-531">請盡量不要使用此選項。因為暫時我們的篩選堆疊應該執行該做的事，而清單可能因此變得無法管理。</span><span class="sxs-lookup"><span data-stu-id="033dc-531">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="033dc-532">在某些情況下，有時您的組織可能不同意服務所提供的結果。</span><span class="sxs-lookup"><span data-stu-id="033dc-532">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="033dc-533">如果這樣，您可能希望永久保留 [允許] 或 [封鎖] 清單。</span><span class="sxs-lookup"><span data-stu-id="033dc-533">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="033dc-534">不過，如果您要長期將網域放在 [允許]清單上，請告知寄件者先確認他們使用已驗證的網域；如果不是則將遭 DMARC 拒絕。</span><span class="sxs-lookup"><span data-stu-id="033dc-534">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
