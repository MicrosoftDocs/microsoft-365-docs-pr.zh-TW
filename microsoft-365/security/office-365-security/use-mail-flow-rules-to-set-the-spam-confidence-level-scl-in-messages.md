---
title: 使用郵件流程規則到郵件中的 SCL
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
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 瞭解如何建立郵件流程規則 (傳輸規則) 識別郵件，以及在 Exchange Online Protection 中設定郵件的垃圾郵件信賴等級 (SCL) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aa2893214543f77114d517dc38f874d6172a920a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287554"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="5d2d5-103">使用郵件流程規則設定 EOP 中郵件中的垃圾郵件信賴等級 (SCL) </span><span class="sxs-lookup"><span data-stu-id="5d2d5-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5d2d5-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5d2d5-104">**Applies to**</span></span>
- [<span data-ttu-id="5d2d5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5d2d5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5d2d5-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="5d2d5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="5d2d5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d2d5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="5d2d5-108">在包含 Exchange Online 或獨立 Exchange online)  (Protection 中信箱的 Microsoft 365 組織中，EOP 會使用反垃圾郵件原則 (也稱為垃圾郵件篩選原則或內容篩選原則) ，以掃描輸入郵件中的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="5d2d5-109">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="5d2d5-110">如果您想要將特定郵件標記為垃圾郵件，然後再透過垃圾郵件篩選進行掃描，或將郵件標示為略過垃圾郵件篩選，您可以建立郵件流程規則 (也稱為傳輸規則) 來識別郵件，並設定垃圾郵件信賴等級 (SCL) 。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="5d2d5-111">如需有關 SCL 的詳細資訊，請參閱 [EOP 中的垃圾郵件信賴等級 (SCL) ](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5d2d5-112">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="5d2d5-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5d2d5-113">您必須先在 Exchange Online 或 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="5d2d5-114">具體說來，您需要「 **傳輸規則** 」角色，該角色會指派給「 **組織管理**」、「 **合規性管理** 」 (全域系統管理員) ，並依預設 **記錄管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="5d2d5-115">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="5d2d5-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="5d2d5-116">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="5d2d5-116">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="5d2d5-117">獨立版 EOP 中的權限</span><span class="sxs-lookup"><span data-stu-id="5d2d5-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="5d2d5-118">使用 EAC 修改角色群組中的成員清單</span><span class="sxs-lookup"><span data-stu-id="5d2d5-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="5d2d5-119">若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="5d2d5-120">若要在獨立 EOP 中開啟 EAC，請參閱 [Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5d2d5-121">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5d2d5-122">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5d2d5-123">如需 Exchange Online 和 Exchange Online Protection 中郵件流程規則的相關資訊，請參閱 [mail flow rules (transport rules) In Exchange online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="5d2d5-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="5d2d5-124">使用 EAC 來建立郵件流程規則，以設定郵件的 SCL</span><span class="sxs-lookup"><span data-stu-id="5d2d5-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="5d2d5-125">在 EAC 中，移至 [郵件流程] \> [規則]。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="5d2d5-126">按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [ **建立新的規則**]。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="5d2d5-127">在開啟的 [ **新增規則** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="5d2d5-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="5d2d5-128">**名稱**：輸入規則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="5d2d5-129">按一下 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-129">Click **More Options**.</span></span>

   - <span data-ttu-id="5d2d5-130">在下列情況中套用 **此規則**：選取一或多個條件來識別郵件。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="5d2d5-131">如需詳細資訊，請參閱 [郵件流程規則條件和例外狀況 (謂語) 在 Exchange Online 中](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="5d2d5-132">**請執行下列** 動作：選取 **[修改郵件** 內容] \> 。 **(SCL) 設定垃圾郵件信賴等級**。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="5d2d5-133">在出現的 [ **指定 SCL** ] 對話方塊中，設定下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="5d2d5-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="5d2d5-134">**略過垃圾郵件篩選**：郵件會略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="5d2d5-135">請務必小心允許郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="5d2d5-136">攻擊者可以利用此弱點，將網路釣魚和其他惡意郵件傳送至您的組織。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="5d2d5-137">郵件流程規則需要的不僅僅是寄件者的電子郵件地址或網域。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="5d2d5-138">如需詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="5d2d5-139">**0 至 4**：透過垃圾郵件篩選傳送郵件以進行其他處理。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="5d2d5-140">**5 或 6**：郵件被標示為 **垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="5d2d5-141">您為反垃圾郵件原則中的 **垃圾** 郵件篩選 verdicts 設定的動作會套用至郵件 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="5d2d5-142">**7 至 9**：郵件標示為 **高信賴的垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="5d2d5-143">您為反垃圾郵件原則中已設定 **高信賴垃圾郵件** 篩選 verdicts 的動作會套用至郵件 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="5d2d5-144">指定規則所需的任何其他屬性。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="5d2d5-145">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5d2d5-146">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="5d2d5-146">How do you know this worked?</span></span>

<span data-ttu-id="5d2d5-147">若要驗證此程式是否正常運作，請將電子郵件訊息傳送給組織內部的人員，並確認對郵件執行的動作如期。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="5d2d5-148">例如，如果您 **將垃圾郵件信賴等級設定 (SCL)** **略過垃圾郵件篩選**，則郵件應該會傳送至指定的收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="5d2d5-149">不過，如果您 **將垃圾郵件信賴等級的 (SCL) 設定** 為 **9**，且適用的反垃圾郵件原則的 **高信賴垃圾郵件** 動作是將郵件移至 [垃圾郵件] 資料夾，則郵件應該會傳送至指定收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5d2d5-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
