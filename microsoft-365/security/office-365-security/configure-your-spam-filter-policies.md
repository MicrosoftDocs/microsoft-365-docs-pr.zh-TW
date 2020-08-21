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
description: 系統管理員可以了解如何在 Exchange Online Protection (EOP) 中檢視、建立、修改及刪除反垃圾郵件原則。
ms.openlocfilehash: 21e2142eb62c25a7301e2ea5f9160ef6d6ef7947
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804217"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="d92c0-103">在 EOP 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-103">Configure anti-spam policies in EOP</span></span>

<span data-ttu-id="d92c0-104">在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，EOP 會自動保護內送電子郵件，防止垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="d92c0-105">EOP 使用反垃圾郵件原則 (也稱為垃圾郵件過篩選原則或內容篩選原則)，作為貴組織全面防範垃圾郵件的一環。</span><span class="sxs-lookup"><span data-stu-id="d92c0-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="d92c0-106">如需詳細資訊，請參閱[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-106">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="d92c0-107">系統管理員可以檢視、編輯、設定 (但不能刪除) 預設的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="d92c0-108">若要提高精確性，您也可以建立自訂的反垃圾郵件原則，並套用至貴組織中的特定使用者、群組或網域。</span><span class="sxs-lookup"><span data-stu-id="d92c0-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d92c0-109">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d92c0-110">在擁有 Exchange Online 信箱的 Exchange Online PowerShell for Microsoft 365 組織中；沒有 Exchange Online 信箱的獨立 EOP PowerShell 組織中，您可以在 PowerShell 的 [安全性與合規性中心] 設定反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-110">You can configure anti-spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="d92c0-111">反垃圾郵件原則的基本元素有：</span><span class="sxs-lookup"><span data-stu-id="d92c0-111">The basic elements of an anti-spam policy are:</span></span>

- <span data-ttu-id="d92c0-112">**垃圾郵件篩選原則**：指定垃圾郵件篩選裁決的動作和通知選項。</span><span class="sxs-lookup"><span data-stu-id="d92c0-112">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="d92c0-113">**垃圾郵件篩選規則**：指定垃圾郵件篩選原則的優先順序及收件者篩選器 (原則套用對象)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-113">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="d92c0-114">當您在安全性與合規性中心管理反垃圾郵件原則時，上述兩個元素的差異不大：</span><span class="sxs-lookup"><span data-stu-id="d92c0-114">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d92c0-115">當您建立ㄧ項反垃圾郵件原則時，其實只是以相同的名稱，同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-115">When you create an anti-spam policy, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="d92c0-116">當您修改反垃圾郵件原則時，與名稱、優先順序、已啟用或已停用、收件者篩選相關的設定皆會修改垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-116">When you modify an anti-spam policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="d92c0-117">所有其他設定都會修改相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-117">All other settings modify the associated spam filter policy.</span></span>
- <span data-ttu-id="d92c0-118">當您移除反垃圾郵件原則時，也會一併移除垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-118">When you remove an anti-spam policy, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="d92c0-119">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="d92c0-120">如需其他更多資訊，請參照此主題之後的 [使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定反垃圾郵件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) 章節。</span><span class="sxs-lookup"><span data-stu-id="d92c0-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="d92c0-121">每個組織都有一個名為「預設」的內建反垃圾郵件原則，且具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="d92c0-121">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="d92c0-122">即使沒有與此原則相關聯的垃圾郵件篩選規則 (收件者篩選器)，此原則仍會套用至組織中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-122">The policy is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="d92c0-123">此原則的自訂優先順序值是**最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。</span><span class="sxs-lookup"><span data-stu-id="d92c0-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d92c0-124">任何您建立的自訂原則皆具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="d92c0-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="d92c0-125">此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d92c0-126">若要提高垃圾郵件篩選的效率，您可以建立自訂反垃圾郵件原則，以更嚴格的設定套用到特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d92c0-126">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d92c0-127">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d92c0-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d92c0-128">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="d92c0-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d92c0-129">若要直接移至 [反垃圾郵件設定]\*\*\*\* 頁面，請使用 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="d92c0-129">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="d92c0-130">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d92c0-131">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d92c0-132">您必須已獲派權限，才能進行此主題中的程序:</span><span class="sxs-lookup"><span data-stu-id="d92c0-132">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d92c0-133">若要新增、修改及刪除反垃圾郵件原則，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="d92c0-133">To add, modify, and delete anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d92c0-134">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="d92c0-134">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d92c0-135">**組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-135">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d92c0-136">若要以唯讀方式存取反垃圾郵件原則，您必須是下列其中一個角色群組的成員:</span><span class="sxs-lookup"><span data-stu-id="d92c0-136">For read-only access to anti-spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d92c0-137">[安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-137">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d92c0-138">[線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-138">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="d92c0-139">如需反惡意程式碼原則的建議設定，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-139">For our recommended settings for anti-malware policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="d92c0-140">使用安全性與合規性中心來建立反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-140">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="d92c0-141">在安全性與合規性中心建立自訂的反垃圾郵件原則時，是同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則，且為兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="d92c0-141">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d92c0-142">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d92c0-143">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-143">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="d92c0-144">在隨即開啟的 [新增垃圾郵件篩選原則]\*\*\*\* 飛出視窗中進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="d92c0-144">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d92c0-145">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="d92c0-145">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="d92c0-146">請勿使用下列字元：`\ % & * + / = ? { } | < > ( ) ; : , [ ] "`。</span><span class="sxs-lookup"><span data-stu-id="d92c0-146">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="d92c0-147">如果您先前在 Exchange 系統管理中心 (EAC) 中建立的反垃圾郵件原則包含這些字元，您應用 PowerShell 重新命名該反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-147">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="d92c0-148">如需相關指示，請參閱本主題稍後的[使用 PowerShell 修改垃圾郵件篩選規則](#use-powershell-to-modify-spam-filter-rules)一節。</span><span class="sxs-lookup"><span data-stu-id="d92c0-148">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="d92c0-149">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="d92c0-149">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="d92c0-150">(選用) 展開 [垃圾郵件和大量動作]\*\*\*\* 區段，然後確認或設定如下設定：</span><span class="sxs-lookup"><span data-stu-id="d92c0-150">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="d92c0-151">**選取對內送的垃圾郵件和大量電子郵件要採取的動作**：根據下列垃圾郵件篩選裁決，選取或檢查對郵件要採取的動作：</span><span class="sxs-lookup"><span data-stu-id="d92c0-151">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="d92c0-152">**垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d92c0-152">**Spam**</span></span>
     - <span data-ttu-id="d92c0-153">**高信賴度的垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d92c0-153">**High confidence spam**</span></span>
     - <span data-ttu-id="d92c0-154">**網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="d92c0-154">**Phishing email**</span></span>
     - <span data-ttu-id="d92c0-155">**高信賴度的網路釣魚電子郵件**</span><span class="sxs-lookup"><span data-stu-id="d92c0-155">**High confidence phishing email**</span></span>
     - <span data-ttu-id="d92c0-156">**大量電子郵件**</span><span class="sxs-lookup"><span data-stu-id="d92c0-156">**Bulk email**</span></span>

     <span data-ttu-id="d92c0-157">下表說明垃圾郵件篩選裁決可採取的動作。</span><span class="sxs-lookup"><span data-stu-id="d92c0-157">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="d92c0-158">核取記號 (</span><span class="sxs-lookup"><span data-stu-id="d92c0-158">A check mark (</span></span> ![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="d92c0-160">) 表示可採取的動作 (並非所有的垃圾郵件篩選裁決皆可採取所有動作)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-160">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="d92c0-161">核取記號之後有星號 (<sup>\*</sup>) 表示垃圾郵件篩選裁決的預設動作。</span><span class="sxs-lookup"><span data-stu-id="d92c0-161">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     ****

     |<span>|<span data-ttu-id="d92c0-162">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="d92c0-162">Spam</span></span>|<span data-ttu-id="d92c0-163">高</span><span class="sxs-lookup"><span data-stu-id="d92c0-163">High</span></span><br/><span data-ttu-id="d92c0-164">信賴度</span><span class="sxs-lookup"><span data-stu-id="d92c0-164">confidence</span></span><br/><span data-ttu-id="d92c0-165">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="d92c0-165">spam</span></span>|<span data-ttu-id="d92c0-166">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="d92c0-166">Phishing</span></span><br/><span data-ttu-id="d92c0-167">電子郵件</span><span class="sxs-lookup"><span data-stu-id="d92c0-167">email</span></span>|<span data-ttu-id="d92c0-168">高</span><span class="sxs-lookup"><span data-stu-id="d92c0-168">High</span></span><br/><span data-ttu-id="d92c0-169">信賴度</span><span class="sxs-lookup"><span data-stu-id="d92c0-169">confidence</span></span><br/><span data-ttu-id="d92c0-170">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="d92c0-170">phishing</span></span><br/><span data-ttu-id="d92c0-171">電子郵件</span><span class="sxs-lookup"><span data-stu-id="d92c0-171">email</span></span>|<span data-ttu-id="d92c0-172">大量</span><span class="sxs-lookup"><span data-stu-id="d92c0-172">Bulk</span></span><br/><span data-ttu-id="d92c0-173">電子郵件</span><span class="sxs-lookup"><span data-stu-id="d92c0-173">email</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="d92c0-174">**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-174">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="d92c0-175">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-175">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="d92c0-176">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-176">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="d92c0-179">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-179">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="d92c0-180">**新增 X 標頭**：在郵件標頭中新增 X 標頭，並將郵件傳送到信箱。</span><span class="sxs-lookup"><span data-stu-id="d92c0-180">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="d92c0-181">您稍後可以在 [新增此 X 標頭文字]\*\*\*\* 方塊中輸入 X 標頭欄位的名稱 (不是值)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-181">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="d92c0-182">裁決為**垃圾郵件**和**高信賴度垃圾郵件**的郵件會移至 [垃圾郵件] 資料夾。<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-182">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="d92c0-186">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-186">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="d92c0-187">**在主旨列前加上文字**：新增文字至郵件主旨列的開頭。</span><span class="sxs-lookup"><span data-stu-id="d92c0-187">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="d92c0-188">郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-188">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="d92c0-189">您稍後可以在 [在主旨列前加上此文字]\*\*\*\* 方塊中輸入文字。</span><span class="sxs-lookup"><span data-stu-id="d92c0-189">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="d92c0-194">**將郵件重新導向至電子郵件地址**：將郵件傳送給其他收件者，而不是預定收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-194">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="d92c0-195">您稍後可以在 [重新導向到這個電子郵件地址]\*\*\*\* 方塊中指定收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-195">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="d92c0-201">**刪除郵件**：刪除整封郵件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-201">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="d92c0-206">**隔離郵件**：將郵件傳送到隔離信箱，而不是傳送給預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-206">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="d92c0-207">您稍後可以在 [隔離]\*\*\*\* 方塊中指定郵件要在隔離區保留多久。</span><span class="sxs-lookup"><span data-stu-id="d92c0-207">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="d92c0-210">![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d92c0-210">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="d92c0-213">**無動作**</span><span class="sxs-lookup"><span data-stu-id="d92c0-213">**No action**</span></span>|||||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     > <span data-ttu-id="d92c0-215"><sup>1</sup> 在 Exchange Online 中，如果信箱已啟用垃圾郵件規則 (預設為啟用)，郵件會移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d92c0-215"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="d92c0-216">如需詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-216">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="d92c0-217">在獨立版 EOP 環境中，EOP 會保護內部部署 Exchange 信箱，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d92c0-217">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="d92c0-218">如需詳細資訊，請參閱[設定獨立版 EOP 將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-218">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>
     >
     > <span data-ttu-id="d92c0-219"><sup>2</sup> 您可以使用此值做為郵件流程規則 (又稱為傳輸規則) 的條件，以便篩選或傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-219"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="d92c0-220">**選取閾值**：針對會觸發**大量電子郵件**垃圾郵件篩選裁決指定動作的訊息，指定大量抱怨層級 (BCL)，(大於、不大於或等於指定的值)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-220">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="d92c0-221">較高的值表示不太理想的郵件 (更可能像是垃圾郵件)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-221">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="d92c0-222">預設值為 7。</span><span class="sxs-lookup"><span data-stu-id="d92c0-222">The default value is 7.</span></span> <span data-ttu-id="d92c0-223">如需詳細資訊，請參閱 [EOP 中的大量抱怨層級 (BCL)](bulk-complaint-level-values.md) 和[垃圾電子郵件與大量電子郵件之間有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-223">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="d92c0-224">根據預設，PowerShell 只會將反垃圾郵件原則中的 MarkAsSpamBulkMail__ 設定為 `On`。</span><span class="sxs-lookup"><span data-stu-id="d92c0-224">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="d92c0-225">這項設定會嚴重影響**大量電子郵件**篩選的裁決：</span><span class="sxs-lookup"><span data-stu-id="d92c0-225">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="d92c0-226">**MarkAsSpamBulkMail__ 為 On**：大於閾值的 BCL 會轉換成 SCL 6 (對應到**垃圾郵件**篩選裁決)，然後對郵件採取**大量電子郵件**篩選裁決的動作。</span><span class="sxs-lookup"><span data-stu-id="d92c0-226">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="d92c0-227">**MarkAsSpamBulkMail__ 為 Off**：郵件會加蓋 BCL 戳記，但**大量電子郵件**篩選裁決不會執行任何動作__。</span><span class="sxs-lookup"><span data-stu-id="d92c0-227">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="d92c0-228">實際上，BCL 閾值和**大量電子郵件**篩選裁決動作並不相關。</span><span class="sxs-lookup"><span data-stu-id="d92c0-228">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="d92c0-229">**隔離**：指定當您選取**隔離郵件**做為垃圾郵件篩選裁決的動作時，郵件將存放在隔離中要多久的時間。</span><span class="sxs-lookup"><span data-stu-id="d92c0-229">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="d92c0-230">時間到了之後，就會刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-230">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="d92c0-231">預設值是 30 天。</span><span class="sxs-lookup"><span data-stu-id="d92c0-231">The default value is 30 days.</span></span> <span data-ttu-id="d92c0-232">有效值是從 1 到 30 天。</span><span class="sxs-lookup"><span data-stu-id="d92c0-232">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="d92c0-233">如需隔離的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="d92c0-233">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="d92c0-234">EOP 中的隔離郵件</span><span class="sxs-lookup"><span data-stu-id="d92c0-234">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="d92c0-235">在 EOP 中管理隔離的郵件與檔案</span><span class="sxs-lookup"><span data-stu-id="d92c0-235">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="d92c0-236">在 EOP 中尋找及釋出隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="d92c0-236">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="d92c0-237">**新增此 X 標題文字**：只有當您選取 [新增 X 標頭]\*\*\*\* 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-237">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="d92c0-238">您指定的值是郵件標頭「名稱」\*\*，會新增到郵件標頭中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-238">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="d92c0-239">標題欄位的「值」\*\* 一律是 `This message appears to be spam`。</span><span class="sxs-lookup"><span data-stu-id="d92c0-239">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="d92c0-240">長度上限為 255 個字元，且值不能包含空格或冒號 (:)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-240">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="d92c0-241">例如，如果輸入 `X-This-is-my-custom-header` 值，則新增到郵件的 X 標頭為 `X-This-is-my-custom-header: This message appears to be spam.`。</span><span class="sxs-lookup"><span data-stu-id="d92c0-241">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="d92c0-242">如果您輸入的值包含空格或冒號 (:)，系統會忽略您輸入的值，並在郵件中新增預設的 X 標頭 (`X-This-Is-Spam: This message appears to be spam.`)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-242">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="d92c0-243">**在主旨列前加上此文字**：只有當您選取 [在主旨列前加上文字]\*\*\*\* 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-243">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="d92c0-244">輸入要新增至郵件主旨列開頭的文字。</span><span class="sxs-lookup"><span data-stu-id="d92c0-244">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="d92c0-245">**重新導向到這個電子郵件地址**：只有當您選取 [將郵件重新導向至電子郵件地址]\*\*\*\* 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-245">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="d92c0-246">輸入您要遞送郵件的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d92c0-246">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="d92c0-247">您可以輸入多個值並以分號 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="d92c0-247">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="d92c0-248">**安全提示**：預設會啟用安全提示，但您可以清除 [開啟]\*\*\*\* 核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="d92c0-248">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="d92c0-249">如需有關安全性提示的詳細資訊，請參閱[電子郵件的安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-249">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="d92c0-250">**零時差自動清除**設定：ZAP 會偵測傳送到 Exchange Online 信箱的郵件，並採取行動。</span><span class="sxs-lookup"><span data-stu-id="d92c0-250">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="d92c0-251">如需有關 ZAP 的詳細資訊，請參閱[零時差自動清除 - 防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-251">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="d92c0-252">**垃圾郵件 ZAP**：預設會啟用 ZAP 以偵測垃圾郵件，但您可以清除 [開啟]\*\*\*\* 核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="d92c0-252">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="d92c0-253">**網路釣魚 ZAP**：預設會啟用 ZAP 以偵測網路釣魚，但您可以清除 [開啟]\*\*\*\* 核取方塊加以停用。</span><span class="sxs-lookup"><span data-stu-id="d92c0-253">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="d92c0-254">(選用) 展開 [允許清單]\*\*\*\* 區段，依據允許跳過垃圾郵件篩選的電子郵件地址或電子郵件網域，來設定郵件寄件人：</span><span class="sxs-lookup"><span data-stu-id="d92c0-254">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   >
   > - <span data-ttu-id="d92c0-255">在此新增網域前請仔細考慮。</span><span class="sxs-lookup"><span data-stu-id="d92c0-255">Think very carefully before you add domains here.</span></span> <span data-ttu-id="d92c0-256">如需詳細資訊，請參閱[在 EOP 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-256">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > - <span data-ttu-id="d92c0-257">絕對不要將接受的網域 (您擁有的網域) 或一般網域 (例如 microsoft.com 或 office.com) 新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-257">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="d92c0-258">這會讓攻擊者能夠略過垃圾郵件篩選將電子郵件送進您的貴組織。</span><span class="sxs-lookup"><span data-stu-id="d92c0-258">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span>

   - <span data-ttu-id="d92c0-259">**允許寄件者**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-259">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="d92c0-260">在 [允許的寄件者清單]\*\*\*\* 飛出視窗中：</span><span class="sxs-lookup"><span data-stu-id="d92c0-260">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="d92c0-261">a.</span><span class="sxs-lookup"><span data-stu-id="d92c0-261">a.</span></span> <span data-ttu-id="d92c0-262">輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d92c0-262">Enter the sender's email address.</span></span> <span data-ttu-id="d92c0-263">您可以指定多個電子郵件地址並以分號 (;) 隔開。</span><span class="sxs-lookup"><span data-stu-id="d92c0-263">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="d92c0-264">b.</span><span class="sxs-lookup"><span data-stu-id="d92c0-264">b.</span></span> <span data-ttu-id="d92c0-265">按一下</span><span class="sxs-lookup"><span data-stu-id="d92c0-265">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d92c0-267">以新增寄件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-267">to add the senders.</span></span>

      <span data-ttu-id="d92c0-268">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="d92c0-268">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="d92c0-269">您新增的寄件者會出現在飛出視窗的 [允許的寄件者]\*\*\*\* 區段中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-269">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="d92c0-270">若要刪除寄件者，按一下 ![移除圖示](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-270">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="d92c0-271">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-271">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="d92c0-272">**允許網域**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-272">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="d92c0-273">在隨即出現的 [允許的網域清單]\*\*\*\* 飛出視窗中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d92c0-273">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="d92c0-274">a.</span><span class="sxs-lookup"><span data-stu-id="d92c0-274">a.</span></span> <span data-ttu-id="d92c0-275">輸入網域。</span><span class="sxs-lookup"><span data-stu-id="d92c0-275">Enter the domain.</span></span> <span data-ttu-id="d92c0-276">您可以指定多個網域並以分號 (;) 隔開的。</span><span class="sxs-lookup"><span data-stu-id="d92c0-276">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="d92c0-277">b.</span><span class="sxs-lookup"><span data-stu-id="d92c0-277">b.</span></span> <span data-ttu-id="d92c0-278">按一下</span><span class="sxs-lookup"><span data-stu-id="d92c0-278">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d92c0-280">以新增網域。</span><span class="sxs-lookup"><span data-stu-id="d92c0-280">to add the domains.</span></span>

      <span data-ttu-id="d92c0-281">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="d92c0-281">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="d92c0-282">您新增的網域會出現在飛出視窗的 [允許的網域]\*\*\*\* 區段中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-282">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="d92c0-283">若要刪除網域，按一下 ![移除圖示](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-283">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="d92c0-284">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-284">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="d92c0-285">(選用) 展開 [封鎖清單]\*\*\*\* 區段，依據將一律標示為「高信賴度的垃圾郵件」的電子郵件地址或電子郵件網域，來設定郵件寄件人：</span><span class="sxs-lookup"><span data-stu-id="d92c0-285">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="d92c0-286">手動封鎖網域並不危險，但會增加您的管理工作量。</span><span class="sxs-lookup"><span data-stu-id="d92c0-286">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="d92c0-287">如需詳細資訊，請參閱[在 EOP 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-287">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="d92c0-288">**封鎖寄件者**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-288">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="d92c0-289">在隨即出現的 [封鎖的寄件者清單]\*\*\*\* 飛出視窗中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d92c0-289">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="d92c0-290">a.</span><span class="sxs-lookup"><span data-stu-id="d92c0-290">a.</span></span> <span data-ttu-id="d92c0-291">輸入寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d92c0-291">Enter the sender's email address.</span></span> <span data-ttu-id="d92c0-292">您可以指定多個電子郵件地址並以分號 (;) 隔開。</span><span class="sxs-lookup"><span data-stu-id="d92c0-292">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="d92c0-293">不可使用萬用字元 (\*)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-293">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="d92c0-294">b.</span><span class="sxs-lookup"><span data-stu-id="d92c0-294">b.</span></span> <span data-ttu-id="d92c0-295">按一下</span><span class="sxs-lookup"><span data-stu-id="d92c0-295">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d92c0-297">以新增寄件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-297">to add the senders.</span></span>

      <span data-ttu-id="d92c0-298">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="d92c0-298">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="d92c0-299">您新增的寄件者會出現在飛出視窗的 [封鎖的寄件者]\*\*\*\* 區段中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-299">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="d92c0-300">若要刪除寄件者，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-300">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="d92c0-301">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-301">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="d92c0-302">**封鎖網域**：按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-302">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="d92c0-303">在隨即出現的 [封鎖的網域清單]\*\*\*\* 飛出視窗中：</span><span class="sxs-lookup"><span data-stu-id="d92c0-303">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="d92c0-304">a.</span><span class="sxs-lookup"><span data-stu-id="d92c0-304">a.</span></span> <span data-ttu-id="d92c0-305">輸入網域。</span><span class="sxs-lookup"><span data-stu-id="d92c0-305">Enter the domain.</span></span> <span data-ttu-id="d92c0-306">您可以指定多個網域並以分號 (;) 隔開的。</span><span class="sxs-lookup"><span data-stu-id="d92c0-306">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="d92c0-307">不可使用萬用字元 (\*)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-307">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="d92c0-308">b.</span><span class="sxs-lookup"><span data-stu-id="d92c0-308">b.</span></span> <span data-ttu-id="d92c0-309">按一下</span><span class="sxs-lookup"><span data-stu-id="d92c0-309">Click</span></span> ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d92c0-311">以新增網域。</span><span class="sxs-lookup"><span data-stu-id="d92c0-311">to add the domains.</span></span>

      <span data-ttu-id="d92c0-312">視需要重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="d92c0-312">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="d92c0-313">您新增的網域會顯示在飛出視窗的 [封鎖的網域]\*\*\*\* 清單中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-313">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="d92c0-314">若要刪除網域，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-314">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="d92c0-315">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-315">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="d92c0-316">(選用) 展開 [國際垃圾郵件]\*\*\*\* 區段，根據垃圾郵件篩選會封鎖的電子郵件語言或來源國家/地區，來設定電子郵件語言：</span><span class="sxs-lookup"><span data-stu-id="d92c0-316">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="d92c0-317">**篩選以下列語言撰寫的電子郵件**：預設會停用此設定 ([狀態： 關閉]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-317">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="d92c0-318">按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-318">Click **Edit**.</span></span> <span data-ttu-id="d92c0-319">在隨即出現的 [國際垃圾郵件設定]\*\*\*\* 飛出視窗中，進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="d92c0-319">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="d92c0-320">**篩選以下列語言撰寫的電子郵件**：選取核取方塊以啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="d92c0-320">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="d92c0-321">清除核取方塊可停用此設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-321">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="d92c0-322">在方塊中按一下，然後開始輸入語言的「名稱」\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-322">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="d92c0-323">將會顯示篩選過的支援語言清單，以及對應的 ISO 639-2 語言代碼。</span><span class="sxs-lookup"><span data-stu-id="d92c0-323">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="d92c0-324">當您找到所需語言時，請選取該語言。</span><span class="sxs-lookup"><span data-stu-id="d92c0-324">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="d92c0-325">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="d92c0-325">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="d92c0-326">您選取的語言清單會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-326">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="d92c0-327">若要刪除語言，按一下</span><span class="sxs-lookup"><span data-stu-id="d92c0-327">To delete a language, click</span></span> ![移除按鈕](../../media/scc-remove-icon.png)<span data-ttu-id="d92c0-329">。</span><span class="sxs-lookup"><span data-stu-id="d92c0-329">.</span></span>

     <span data-ttu-id="d92c0-330">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-330">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="d92c0-331">**篩選從下列國家或地區傳送的電子郵件**：預設會停用此設定 ([狀態：關閉]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-331">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="d92c0-332">若要啟用，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-332">To enable it, click **Edit**.</span></span> <span data-ttu-id="d92c0-333">在隨即出現的 [國際垃圾郵件設定]\*\*\*\* 飛出視窗中，進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="d92c0-333">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="d92c0-334">**篩選從下列國家或地區傳送的電子郵件**：選取核取方塊以啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-334">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="d92c0-335">清除核取方塊可停用此設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-335">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="d92c0-336">在方塊中按一下，然後開始輸入國家或地區的「名稱」\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-336">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="d92c0-337">將會顯示篩選過的支援國家/地區清單，以及對應的 ISO 3166-1 雙字母國碼。</span><span class="sxs-lookup"><span data-stu-id="d92c0-337">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="d92c0-338">當您找到您要尋找的國家或地區時，請選取它。</span><span class="sxs-lookup"><span data-stu-id="d92c0-338">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="d92c0-339">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="d92c0-339">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="d92c0-340">您選取的國家/地區清單會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-340">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="d92c0-341">若要刪除國家或地區，按一下</span><span class="sxs-lookup"><span data-stu-id="d92c0-341">To delete a country or region, click</span></span> ![移除按鈕](../../media/scc-remove-icon.png)<span data-ttu-id="d92c0-343">。</span><span class="sxs-lookup"><span data-stu-id="d92c0-343">.</span></span>

     <span data-ttu-id="d92c0-344">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-344">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="d92c0-345">選用的 [垃圾郵件屬性]\*\*\*\* 區段中有的進階垃圾郵件篩選 (ASF) 設定，預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="d92c0-345">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="d92c0-346">我們正逐漸淘汰 ASF 設定，其功能正併入篩選堆疊的其他部分。</span><span class="sxs-lookup"><span data-stu-id="d92c0-346">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="d92c0-347">建議您將反垃圾郵件原則中的所有 ASF 設定關閉。</span><span class="sxs-lookup"><span data-stu-id="d92c0-347">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="d92c0-348">如需有關這些設定的詳細資訊，請參閱 [EOP 中的進階垃圾郵件篩選設定](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-348">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="d92c0-349">(必要) 展開 [套用至]\*\*\*\* 區段，找出原則所套用的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-349">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="d92c0-350">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="d92c0-350">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d92c0-351">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-351">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d92c0-352">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-352">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="d92c0-353">最簡單的方法是按一下 [新增條件]\*\*\*\* 三次，查看所有可用的條件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-353">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="d92c0-354">您可以按一下 ![移除按鈕](../../media/scc-remove-icon.png)移除您不想要設定的條件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-354">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="d92c0-355">**收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-355">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span> <span data-ttu-id="d92c0-356">按一下 [新增標籤]\*\*\*\* 方塊，可查看並選取網域。</span><span class="sxs-lookup"><span data-stu-id="d92c0-356">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="d92c0-357">如果有不止一個網域，再次按一下 [新增標籤]\*\*\*\* 方塊可選取其他網域。</span><span class="sxs-lookup"><span data-stu-id="d92c0-357">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="d92c0-358">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="d92c0-358">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="d92c0-359">在 [新增標籤]\*\*\*\* 內按一下，然後開始輸入以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="d92c0-359">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d92c0-360">再次按一下 [新增標籤]\*\*\*\* 方塊以選取其他收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-360">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="d92c0-361">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="d92c0-361">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="d92c0-362">在 [新增標籤]\*\*\*\* 內按一下，然後開始輸入以篩選清單。</span><span class="sxs-lookup"><span data-stu-id="d92c0-362">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d92c0-363">再次按一下 [新增標籤]\*\*\*\* 方塊以選取其他收件者。</span><span class="sxs-lookup"><span data-stu-id="d92c0-363">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="d92c0-364">**除了**：若要為規則新增例外情況，按一下 [新增條件]\*\*\*\* 三次，即可查看所有可用的例外。</span><span class="sxs-lookup"><span data-stu-id="d92c0-364">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="d92c0-365">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-365">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="d92c0-366">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-366">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="d92c0-367">使用安全性與合規性中心來檢視反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-367">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="d92c0-368">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-368">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d92c0-369">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-369">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="d92c0-370">預設原則名為**預設的垃圾郵件篩選原則**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-370">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="d92c0-371">您建立的自訂原則的 [類型]\*\*\*\* 資料行中的值是 [自訂的反垃圾郵件原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-371">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="d92c0-372">重要的原則設定會顯示在展開的原則詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="d92c0-372">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="d92c0-373">若要查看更多詳細資料，按一下 [編輯原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-373">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="d92c0-374">使用安全性與合規性中心來修改反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-374">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="d92c0-375">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-375">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d92c0-376">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-376">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="d92c0-377">預設原則名為**預設的垃圾郵件篩選原則**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-377">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="d92c0-378">您建立的自訂原則的 [類型]\*\*\*\* 資料行中的值是 [自訂的反垃圾郵件原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-378">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="d92c0-379">按一下 [編輯原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-379">Click **Edit policy**.</span></span>

<span data-ttu-id="d92c0-380">若是自訂的反垃圾郵件原則，隨即出現的飛出視窗中顯示的設定會和[使用安全性與合規性中心來建立反垃圾郵件原則](#use-the-security--compliance-center-to-create-anti-spam-policies)一節所述的完全相同。</span><span class="sxs-lookup"><span data-stu-id="d92c0-380">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="d92c0-381">若是名為**預設的垃圾郵件篩選原則**的預設反垃圾郵件原則，則無法使用 [套用至]\*\*\*\* 區段 (原則套用至每個人)，而且您無法重新命名原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-381">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="d92c0-382">若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="d92c0-382">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="d92c0-383">啟用或停用反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-383">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="d92c0-384">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-384">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d92c0-385">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開您所建立的自訂原則 (其 [類型]\*\*\*\* 資料行的值是 [自訂的反垃圾郵件原則]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-385">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="d92c0-386">在隨即出現的展開的原則詳細資料中，請注意**開啟**資料行的值。</span><span class="sxs-lookup"><span data-stu-id="d92c0-386">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="d92c0-387">將切換開關向左移動以停用原則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-387">Move the toggle to the left to disable the policy:</span></span> ![關閉](../../media/scc-toggle-off.png)

   <span data-ttu-id="d92c0-389">將切換開關向右移動以啟用原則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-389">Move the toggle to the right to enable the policy:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="d92c0-391">您無法停用預設的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-391">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="d92c0-392">設定自訂反垃圾郵件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="d92c0-392">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="d92c0-393">根據預設，系統是根據反垃圾郵件原則的建立順序給予優先順序 (較新原則的優先順序比較舊原則的優先順序低)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-393">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="d92c0-394">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="d92c0-394">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d92c0-395">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="d92c0-395">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="d92c0-396">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-396">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="d92c0-397">自訂反垃圾郵件原則會以其處理順序顯示 (第一個原則的**優先順序**值為 0)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-397">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d92c0-398">名為**預設的垃圾郵件篩選原則**的預設反垃圾郵件原則具有 **Lowest** 優先順序值，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="d92c0-398">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="d92c0-399">**附註**：在安全性與合規性中心中，只能在建立反垃圾郵件原則後變更它的優先順序。</span><span class="sxs-lookup"><span data-stu-id="d92c0-399">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="d92c0-400">在 PowerShell 中，您可以在建立垃圾郵件篩選規則時覆寫預設優先順序 (會影響現有規則的優先順序)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-400">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d92c0-401">若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序]\*\*\*\* 數字)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-401">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="d92c0-402">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-402">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d92c0-403">在 [反垃圾郵件設定]\*\*\*\* 頁面上，找到 [類型]\*\*\*\* 資料行的值為[自訂的反垃圾郵件原則]\*\*\*\* 的原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-403">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="d92c0-404">請注意 [優先順序]\*\*\*\* 資料行中的值：</span><span class="sxs-lookup"><span data-stu-id="d92c0-404">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="d92c0-405">優先順序最高的自訂反垃圾郵件原則的值是 ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **0**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-405">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="d92c0-406">優先順序最低的自訂反垃圾郵件原則的值是 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **n** (例如，![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **3**)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-406">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="d92c0-407">如果有三個以上的自訂反垃圾郵件原則，則最高和最低優先順序之間的原則的值會是 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png)![向下鍵圖示](../../media/ITPro-EAC-DownArrowIcon.png) **n** (例如，![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png)![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **2**)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-407">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="d92c0-408">按一下</span><span class="sxs-lookup"><span data-stu-id="d92c0-408">Click</span></span> ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="d92c0-410">或</span><span class="sxs-lookup"><span data-stu-id="d92c0-410">or</span></span> ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="d92c0-412">可在優先順序清單中，將自訂反垃圾郵件原則往上或向下移動。</span><span class="sxs-lookup"><span data-stu-id="d92c0-412">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="d92c0-413">設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="d92c0-413">Configure end-user spam notifications</span></span>

<span data-ttu-id="d92c0-414">當垃圾郵件篩選裁決要隔離郵件時，您可以設定使用者垃圾郵件通知，讓收件者知道寄給他們的郵件發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="d92c0-414">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="d92c0-415">如需有關這些通知的詳細資訊，請參閱 [EOP 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-415">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="d92c0-416">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-416">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d92c0-417">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-417">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="d92c0-418">預設原則名為**預設的垃圾郵件篩選原則**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-418">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="d92c0-419">您建立的自訂原則的 [類型]\*\*\*\* 資料行中的值是 [自訂的反垃圾郵件原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-419">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="d92c0-420">在隨即出現的展開的原則詳細資料中，按一下 [設定使用者垃圾郵件通知]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-420">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="d92c0-421">在隨即開啟的 **\<Policy Name\>** 對話方塊中，進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="d92c0-421">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d92c0-422">**啟用使用者垃圾郵件通知**：選取核取方塊以啟用通知。</span><span class="sxs-lookup"><span data-stu-id="d92c0-422">**Enable end-user spam notifications**: Select the checkbox to enable notifications.</span></span> <span data-ttu-id="d92c0-423">清除核取方塊以停用通知。</span><span class="sxs-lookup"><span data-stu-id="d92c0-423">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="d92c0-424">**傳送使用者垃圾郵件通知的頻率 (天)**：選取每隔幾天要傳送通知。</span><span class="sxs-lookup"><span data-stu-id="d92c0-424">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="d92c0-425">預設值是 3 天。</span><span class="sxs-lookup"><span data-stu-id="d92c0-425">The default value is 3 days.</span></span> <span data-ttu-id="d92c0-426">您可以輸入 1 到 15 天。</span><span class="sxs-lookup"><span data-stu-id="d92c0-426">You can enter 1 to 15 days.</span></span>

     <span data-ttu-id="d92c0-427">在 24 小時期間內有 3 個使用者垃圾郵件通知週期，從下列時間開始：01:00 UTC、08:00 UTC 和 16:00 UTC。</span><span class="sxs-lookup"><span data-stu-id="d92c0-427">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d92c0-428">如果我們錯過了上一個週期的通知，後續週期會推播通知。</span><span class="sxs-lookup"><span data-stu-id="d92c0-428">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="d92c0-429">如此可能會在同一天內呈現多個通知。</span><span class="sxs-lookup"><span data-stu-id="d92c0-429">This may give the appearance of multiple notifications within the same day.</span></span>

   - <span data-ttu-id="d92c0-430">**通知語言**：按一下下拉式清單並從中選取可用的語言。</span><span class="sxs-lookup"><span data-stu-id="d92c0-430">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="d92c0-431">預設值為 **[預設]**，也就是英文。</span><span class="sxs-lookup"><span data-stu-id="d92c0-431">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="d92c0-432">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-432">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="d92c0-433">使用安全性與合規性中心來移除反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-433">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="d92c0-434">在安全性與合規性中心，移至 [威脅管理]\*\*\*\* \> [原則]\*\*\*\* \> [反垃圾郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-434">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d92c0-435">在 [反垃圾郵件設定]\*\*\*\* 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開您想要刪除的自訂原則 (其 [類型]\*\*\*\* 資料行的值是 [自訂的反垃圾郵件原則]\*\*\*\*)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-435">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="d92c0-436">在隨即出現的展開原則詳細資料中，按一下 [刪除原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-436">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="d92c0-437">在隨即出現的警告對話方塊中，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d92c0-437">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d92c0-438">您無法移除預設原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-438">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="d92c0-439">使用 Exchange Online PowerShell 或獨立版 EOP PowerShell 來設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-439">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="d92c0-440">如先前所述，反垃圾郵件原則是由垃圾郵件篩選原則和垃圾郵件篩選規則組成的。</span><span class="sxs-lookup"><span data-stu-id="d92c0-440">As previously described, an anti-spam policy consists of a spam filter policy and a spam filter rule.</span></span>

<span data-ttu-id="d92c0-441">在 Exchange Online PowerShell 或獨立版 EOP PowerShell 中，垃圾郵件篩選原則與垃圾郵件篩選規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="d92c0-441">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="d92c0-442">您使用 **\*-HostedContentFilterPolicy** Cmdlet 來管理垃圾郵件篩選原則，但使用 **\*-HostedContentFilterRule** Cmdlet 來管理垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-442">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="d92c0-443">在 PowerShell 中，您要先建立垃圾郵件篩選原則，然後再建立垃圾郵件篩選規則來識別將套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-443">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d92c0-444">在 PowerShell 中，您可以分開修改垃圾郵件篩選原則和垃圾郵件篩選規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-444">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>
- <span data-ttu-id="d92c0-445">當您移除 PowerShell 中的垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會自動移除，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="d92c0-445">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

<span data-ttu-id="d92c0-446">下列反垃圾郵件原則設定僅適用於 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="d92c0-446">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="d92c0-447">MarkAsSpamBulkMail__ 參數預設是 `On`。</span><span class="sxs-lookup"><span data-stu-id="d92c0-447">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="d92c0-448">此設定的效果已在本主題前面的 [使用安全性與合規性中心來建立本反垃圾郵件原則](#use-the-security--compliance-center-to-create-anti-spam-policies) 一節中說明。</span><span class="sxs-lookup"><span data-stu-id="d92c0-448">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="d92c0-449">使用者垃圾郵件隔離通知的下列設定：</span><span class="sxs-lookup"><span data-stu-id="d92c0-449">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="d92c0-450">DownloadLink__ 參數，用於顯示或隱藏 Outlook 的垃圾郵件報告工具連結。</span><span class="sxs-lookup"><span data-stu-id="d92c0-450">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="d92c0-451">EndUserSpamNotificationCustomSubject__ 參數，您可以用來自訂通知的主旨列。</span><span class="sxs-lookup"><span data-stu-id="d92c0-451">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="d92c0-452">使用 PowerShell 來建立反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-452">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="d92c0-453">在 PowerShell 中建立反垃圾郵件原則需執行兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="d92c0-453">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d92c0-454">建立垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-454">Create the spam filter policy.</span></span>
2. <span data-ttu-id="d92c0-455">建立垃圾郵件選規則，此規則會指定要套用規則的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-455">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="d92c0-456">**附註**：</span><span class="sxs-lookup"><span data-stu-id="d92c0-456">**Notes**:</span></span>

- <span data-ttu-id="d92c0-457">您可以建立新的垃圾郵件篩選規則，並對其指派未關聯的現有垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-457">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="d92c0-458">垃圾郵件篩選規則無法與多個垃圾郵件篩選原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="d92c0-458">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="d92c0-459">您可以使用 PowerShell 對安全性與合規性中心中還沒有的新垃圾郵件篩選原則進行下列設定，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="d92c0-459">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d92c0-460">建立「停用」的新原則 (在 **New-HostedContentFilterRule** Cmdlet 中啟用__ `$false`)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-460">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="d92c0-461">在建立期間設定原則的優先順序 (在 **New-HostedContentFilterRule** Cmdlet 使用 _Priority_ _\<Number\>_)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-461">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="d92c0-462">您在 PowerShell 中建立的新垃圾郵件篩選原則不會顯示在安全性與合規性中心中，直到您將該原則指派到垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-462">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="d92c0-463">步驟 1：使用 PowerShell 建立垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-463">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="d92c0-464">使用下列語法建立垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-464">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="d92c0-465">本範例會建立名為 Contoso Executives 的垃圾郵件篩選原則，並使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="d92c0-465">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="d92c0-466">當垃圾郵件篩選裁決為垃圾郵件或高信賴度垃圾郵件時隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-466">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="d92c0-467">BCL 6 會觸發大量垃圾郵件篩選裁決的動作。</span><span class="sxs-lookup"><span data-stu-id="d92c0-467">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="d92c0-468">**Set-hostedcontentfilterpolicy** 和 **Set-Set-hostedcontentfilterpolicy** 有較舊的 ZapEnabled__ 參數，以及較新的 PhishZapEnabled__ 和 SpamZapEnabled__ 參數。</span><span class="sxs-lookup"><span data-stu-id="d92c0-468">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="d92c0-469">_ZapEnabled_ 參數已在 2020 年 2 月淘汰。</span><span class="sxs-lookup"><span data-stu-id="d92c0-469">The _ZapEnabled_ parameter was deprecated in February 2020.</span></span> <span data-ttu-id="d92c0-470">PhishZapEnabled__ 和 SpamZapEnabled__ 參數則用來繼承 ZapEnabled__ 參數的值。</span><span class="sxs-lookup"><span data-stu-id="d92c0-470">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="d92c0-471">不過，如果您在命令中使用 PhishZapEnabled__ 和 SpamZapEnabled__ 參數，或是在安全性與合規性中心中的反垃圾郵件原則中使用 [垃圾郵件 ZAP]\*\*\*\* 或 [網路釣魚 ZAP]\*\*\*\* 設定，系統就會忽略 ZapEnabled__ 參數的值。</span><span class="sxs-lookup"><span data-stu-id="d92c0-471">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="d92c0-472">換句話說，請勿使用 ZapEnabled__ 參數，改用 PhishZapEnabled__ 和 SpamZapEnabled__ 參數。</span><span class="sxs-lookup"><span data-stu-id="d92c0-472">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="d92c0-473">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-473">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="d92c0-474">步驟 2：使用 PowerShell 建立垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="d92c0-474">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="d92c0-475">使用下列語法建立垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-475">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d92c0-476">此範例使用下列設定來建立名為 Contoso Executives 的新垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-476">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="d92c0-477">名為 Contoso Executives 的垃圾郵件篩選原則會與此規則相關聯。</span><span class="sxs-lookup"><span data-stu-id="d92c0-477">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="d92c0-478">此規則會套用至名為 ContosoExecutives Group 的群組成員。</span><span class="sxs-lookup"><span data-stu-id="d92c0-478">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="d92c0-479">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-479">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="d92c0-480">使用 PowerShell 檢視垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-480">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="d92c0-481">若要傳回所有垃圾郵件篩選原則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d92c0-481">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="d92c0-482">若要傳回特定垃圾郵件篩選原則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d92c0-482">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d92c0-483">此範例會傳回名為 Executives 的垃圾郵件篩選原則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="d92c0-483">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="d92c0-484">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-484">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="d92c0-485">使用 PowerShell 檢視垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="d92c0-485">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="d92c0-486">若要檢視現有的垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d92c0-486">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="d92c0-487">若要傳回所有垃圾郵件篩選規則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d92c0-487">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="d92c0-488">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d92c0-488">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="d92c0-489">若要傳回特定垃圾郵件篩選規則的詳細資訊，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d92c0-489">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d92c0-490">此範例會傳回名為 Contoso Executives 的垃圾郵件篩選規則的所有屬性值。</span><span class="sxs-lookup"><span data-stu-id="d92c0-490">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="d92c0-491">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-491">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="d92c0-492">使用 PowerShell 修改垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-492">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="d92c0-493">除了下列項目外，當您如同本主題前面的[步驟 1：使用 PowerShell 建立垃圾郵件篩選原則](#step-1-use-powershell-to-create-a-spam-filter-policy) 一節所述在 PowerShell 中修改惡意程式碼篩選原則時，會出現相同的設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-493">Other than the following items, the same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="d92c0-494">MakeDefault__ 可將指定的原則轉換成預設原則 (套用至每個人，一律**最低**優先順序，且無法刪除)，但只有當您在 PowerShell 中修改垃圾郵件篩選原則時才能使用。</span><span class="sxs-lookup"><span data-stu-id="d92c0-494">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="d92c0-495">您無法重新命名垃圾郵件篩選原則(**Set-hostedcontentfilterpolicy** Cmdlet 沒有 Name__ 參數)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-495">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d92c0-496">當您在安全性與合規性中心中重新命名反垃圾郵件原則時，只會重新命名垃圾郵件篩選「規則」__。</span><span class="sxs-lookup"><span data-stu-id="d92c0-496">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="d92c0-497">使用下列語法修改垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-497">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d92c0-498">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-498">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="d92c0-499">使用 PowerShell 修改垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="d92c0-499">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="d92c0-500">當您用 PowerShell 修改垃圾郵件篩選規則時，唯一無法使用的設定為 Enabled__ 參數 (可讓您建立停用的規則)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-500">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d92c0-501">若要啟用或停用現有的垃圾郵件篩選規則，請看下一節。</span><span class="sxs-lookup"><span data-stu-id="d92c0-501">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="d92c0-502">另一方面，當您用 PowerShell 修改垃圾郵件篩選規則時，將無法使用其他設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-502">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="d92c0-503">當您如同本主題前面的 [步驟 2：使用 PowerShell 建立垃圾郵件篩選規則](#step-2-use-powershell-to-create-a-spam-filter-rule)一節所述建立規則時，會出現相同的設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-503">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="d92c0-504">使用下列語法修改垃圾郵件篩選規則：</span><span class="sxs-lookup"><span data-stu-id="d92c0-504">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d92c0-505">此範例會替可能導致安全性與合規性中心出問題的現有垃圾郵件篩選規則 `{Fabrikam Spam Filter}` 重新命名。</span><span class="sxs-lookup"><span data-stu-id="d92c0-505">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="d92c0-506">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-506">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="d92c0-507">使用 PowerShell 來啟用或停用垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="d92c0-507">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="d92c0-508">使用 PowerShell 啟用或停用垃圾郵件篩選規則，可啟用或停用整個反垃圾郵件原則 (垃圾郵件篩選規則和指派的垃圾郵件篩選原則)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-508">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="d92c0-509">您無法啟用或停用預設的反垃圾郵件原則 (一定一律會套用至所有收件者)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-509">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="d92c0-510">若要在 PowerShell 中啟用或停用垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d92c0-510">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="d92c0-511">此範例會停用名為 Marketing Department 的垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-511">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d92c0-512">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-512">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d92c0-513">如需詳細的語法和參數資訊，請參閱 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-513">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="d92c0-514">使用 PowerShell 設定垃圾郵件篩選規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="d92c0-514">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="d92c0-515">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="d92c0-515">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d92c0-516">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="d92c0-516">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d92c0-517">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="d92c0-517">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d92c0-518">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="d92c0-518">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d92c0-519">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="d92c0-519">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d92c0-520">若要在 PowerShell 中設定垃圾郵件篩選規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d92c0-520">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d92c0-521">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="d92c0-521">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d92c0-522">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-522">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d92c0-523">**附註**：</span><span class="sxs-lookup"><span data-stu-id="d92c0-523">**Notes**:</span></span>

- <span data-ttu-id="d92c0-524">若要在建立新規則時設定其優先順序，請使用 **New-HostedContentFilterRule** Cmdlet 上的 Priority__ 參數。</span><span class="sxs-lookup"><span data-stu-id="d92c0-524">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="d92c0-525">預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，且一律有不可修改的優先順序值 **Lowest**。</span><span class="sxs-lookup"><span data-stu-id="d92c0-525">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="d92c0-526">使用 PowerShell 移除垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="d92c0-526">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="d92c0-527">當您使用 PowerShell 來移除垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會遭到移除。</span><span class="sxs-lookup"><span data-stu-id="d92c0-527">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="d92c0-528">若要在 PowerShell 中移除垃圾郵件篩選原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d92c0-528">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d92c0-529">此範例會移除名為 Marketing Department 的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-529">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d92c0-530">如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-530">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="d92c0-531">使用 PowerShell 移除垃圾郵件篩選規則</span><span class="sxs-lookup"><span data-stu-id="d92c0-531">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="d92c0-532">當您使用 PowerShell 來移除垃圾郵件篩選規則時，對應的垃圾郵件篩選原則不會遭到移除。</span><span class="sxs-lookup"><span data-stu-id="d92c0-532">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="d92c0-533">若要在 PowerShell 中移除垃圾郵件篩選規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d92c0-533">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="d92c0-534">此範例會移除名為 Marketing Department 的垃圾郵件篩選規則。</span><span class="sxs-lookup"><span data-stu-id="d92c0-534">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d92c0-535">如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="d92c0-535">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d92c0-536">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="d92c0-536">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="d92c0-537">傳送 GTUBE 訊息以測試您的垃圾郵件原則設定</span><span class="sxs-lookup"><span data-stu-id="d92c0-537">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="d92c0-538">只有當寄出 GTUBE 訊息的電子郵件組織無法掃描輸出的垃圾郵件時，這些步驟才有用。</span><span class="sxs-lookup"><span data-stu-id="d92c0-538">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="d92c0-539">如果能掃描，則無法傳送測試郵件。</span><span class="sxs-lookup"><span data-stu-id="d92c0-539">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="d92c0-540">未經同意大量電子郵件的一般測試 (GTUBE) 是文字字串，可放入測試郵件中，用於確認貴組織的反垃圾郵件設定。</span><span class="sxs-lookup"><span data-stu-id="d92c0-540">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="d92c0-541">GTUBE 訊息類似於歐洲反電腦病毒協會 (EICAR) 用於測試惡意程式碼設定的文字檔。</span><span class="sxs-lookup"><span data-stu-id="d92c0-541">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="d92c0-542">請在電子郵件中，將下列 GTUBE 文字放在單一行上，不加任何空格或換行：</span><span class="sxs-lookup"><span data-stu-id="d92c0-542">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="d92c0-543">允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="d92c0-543">Allow/Block Lists</span></span>

<span data-ttu-id="d92c0-544">有時我們的篩選器會錯過郵件，或者我們的系統需要時間才能完成目標。</span><span class="sxs-lookup"><span data-stu-id="d92c0-544">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="d92c0-545">在此情況下，反垃圾郵件原則提供 [允許] 和 [封鎖] 清單來提供覆寫目前的結果。</span><span class="sxs-lookup"><span data-stu-id="d92c0-545">In this cases, the anti-spam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="d92c0-546">請盡量不要使用此選項。因為暫時我們的篩選堆疊應該執行該做的事，而清單可能因此變得無法管理。</span><span class="sxs-lookup"><span data-stu-id="d92c0-546">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="d92c0-547">在某些情況下，有時您的組織可能不同意服務所提供的結果。</span><span class="sxs-lookup"><span data-stu-id="d92c0-547">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="d92c0-548">如果這樣，您可能希望永久保留 [允許] 或 [封鎖] 清單。</span><span class="sxs-lookup"><span data-stu-id="d92c0-548">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="d92c0-549">不過，如果您要長期將網域放在 [允許]清單上，請告知寄件者先確認他們使用已驗證的網域；如果不是則將遭 DMARC 拒絕。</span><span class="sxs-lookup"><span data-stu-id="d92c0-549">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
