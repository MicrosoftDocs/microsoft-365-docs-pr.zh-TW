---
title: 使用郵件流程規則來篩選大量電子郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用郵件流程規則 (傳輸規則) 來識別及篩選大宗郵件 (在 Exchange Online Protection (EOP) 中) 的灰色郵件。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057187"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="45dd1-103">在 EOP 中使用郵件流程規則來篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="45dd1-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="45dd1-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="45dd1-104">**Applies to**</span></span>
- [<span data-ttu-id="45dd1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="45dd1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="45dd1-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="45dd1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="45dd1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45dd1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="45dd1-108">在包含 Exchange Online 或獨立 Exchange online)  (Protection 中信箱的 Microsoft 365 組織中，EOP 會使用反垃圾郵件原則 (也稱為垃圾郵件篩選原則或內容篩選原則) ，以掃描輸入郵件中的垃圾郵件和大宗郵件 (也稱為灰色郵件) 。</span><span class="sxs-lookup"><span data-stu-id="45dd1-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="45dd1-109">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="45dd1-110">如果您想要更多的選項來篩選大宗郵件，您可以建立郵件流程規則 (也稱為傳輸規則) 搜尋大宗郵件中經常找到的文字模式或片語，並將這些郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="45dd1-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="45dd1-111">如需大宗郵件的詳細資訊，請參閱 EOP 中 [垃圾郵件和大量電子郵件之間的差異](what-s-the-difference-between-junk-email-and-bulk-email.md) 和 [大量投訴層級 (BCL) ](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="45dd1-112">本主題說明如何使用 exchange Online 中的信箱，在 Exchange 系統管理中心中建立這些郵件流程規則 (EAC) 和 PowerShell (Exchange Online PowerShell，以供 Microsoft 365 組織使用。沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="45dd1-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="45dd1-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="45dd1-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="45dd1-114">您必須先在 Exchange Online 或 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="45dd1-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="45dd1-115">具體說來，您需要「 **傳輸規則** 」角色，該角色會指派給「 **組織管理**」、「 **合規性管理** 」 (全域系統管理員) ，並依預設 **記錄管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="45dd1-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="45dd1-116">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="45dd1-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="45dd1-117">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="45dd1-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="45dd1-118">獨立版 EOP 中的權限</span><span class="sxs-lookup"><span data-stu-id="45dd1-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="45dd1-119">使用 EAC 修改角色群組中的成員清單</span><span class="sxs-lookup"><span data-stu-id="45dd1-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="45dd1-120">若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="45dd1-121">若要在獨立 EOP 中開啟 EAC，請參閱 [Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="45dd1-122">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="45dd1-123">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="45dd1-124">如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="45dd1-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="45dd1-125">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="45dd1-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="45dd1-126">Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)</span><span class="sxs-lookup"><span data-stu-id="45dd1-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="45dd1-127">Exchange Online 中的郵件流程規則動作</span><span class="sxs-lookup"><span data-stu-id="45dd1-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="45dd1-128">在範例中用來識別大宗郵件的單字和文字模式清單並不詳盡;您可以視需要新增及移除專案。</span><span class="sxs-lookup"><span data-stu-id="45dd1-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="45dd1-129">不過，它們是一個很好的起點。</span><span class="sxs-lookup"><span data-stu-id="45dd1-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="45dd1-p107">在主旨或郵件的其他標頭欄位中搜尋字詞或文字模式，會發生在郵件已從 MIME 內容傳輸編碼方法進行解碼 *之後*，該編碼方法用來在 SMTP 伺服器之間傳送 ASCII 文字二進位訊息。您無法使用條件或例外狀況來搜尋主旨或郵件中其他標頭欄位的原始 (通常是 Base64) 編碼值。</span><span class="sxs-lookup"><span data-stu-id="45dd1-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="45dd1-132">下列程式會將大宗郵件標記為您整個組織的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="45dd1-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="45dd1-133">不過，您可以新增另一個條件，只將這些規則套用至特定的收件者，這樣您就可以在一些高度具有目標的使用者上使用嚴格篩選，而其餘的使用者 (通常會取得已註冊) 大量電子郵件的使用者，不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="45dd1-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="45dd1-134">使用 EAC 來建立郵件流程規則，以篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="45dd1-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="45dd1-135">在 EAC 中，移至 [郵件流程] \> [規則]。</span><span class="sxs-lookup"><span data-stu-id="45dd1-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="45dd1-136">按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [ **建立新的規則**]。</span><span class="sxs-lookup"><span data-stu-id="45dd1-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="45dd1-137">在開啟的 [ **新增規則** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="45dd1-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="45dd1-138">**名稱**：輸入規則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="45dd1-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="45dd1-139">按一下 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="45dd1-139">Click **More Options**.</span></span>

   - <span data-ttu-id="45dd1-140">**在下列情況中套用此規則**：設定下列其中一項設定，以在使用正則運算式的郵件中尋找內容 (RegEx) 或字或片語：</span><span class="sxs-lookup"><span data-stu-id="45dd1-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="45dd1-141">**主語或** \> 本文主旨或內文 **符合這些文字模式**：在出現的 [ **指定字詞或片語** ] 對話方塊中，輸入下列其中一個值，按一下 [ **新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。</span><span class="sxs-lookup"><span data-stu-id="45dd1-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="45dd1-142">若要編輯專案，請選取它，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="45dd1-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="45dd1-143">若要移除專案，請選取它，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="45dd1-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="45dd1-144">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="45dd1-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="45dd1-145">**主語或** \> 本文主旨或內文 **包含下列任何文字**：在出現的 [ **指定字詞或片語** ] 對話方塊中，輸入下列其中一個值，按一下 [ **新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。</span><span class="sxs-lookup"><span data-stu-id="45dd1-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="45dd1-146">若要編輯專案，請選取它，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="45dd1-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="45dd1-147">若要移除專案，請選取它，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="45dd1-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="45dd1-148">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="45dd1-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="45dd1-149">**請執行下列** 動作：選取 **[修改郵件** 內容] \> 。 **(SCL) 設定垃圾郵件信賴等級**。</span><span class="sxs-lookup"><span data-stu-id="45dd1-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="45dd1-150">在出現的 [ **指定 SCL** ] 對話方塊中，設定下列其中一個設定：</span><span class="sxs-lookup"><span data-stu-id="45dd1-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="45dd1-151">若要將郵件標示為 **垃圾** 郵件，請選取 [ **6**]。</span><span class="sxs-lookup"><span data-stu-id="45dd1-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="45dd1-152">您為反垃圾郵件原則中的 **垃圾** 郵件篩選 verdicts 設定的動作會套用至郵件 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。</span><span class="sxs-lookup"><span data-stu-id="45dd1-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="45dd1-153">將郵件標示為 **高信賴度垃圾郵件** 選取 **9**。</span><span class="sxs-lookup"><span data-stu-id="45dd1-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="45dd1-154">您為反垃圾郵件原則中已設定 **高信賴垃圾郵件** 篩選 verdicts 的動作會套用至郵件 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。</span><span class="sxs-lookup"><span data-stu-id="45dd1-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="45dd1-155">如需 SCL 值的詳細資訊，請參閱 [垃圾郵件信賴等級 (scl) 在 EOP 中](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="45dd1-156">完成後，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="45dd1-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="45dd1-157">使用 PowerShell 建立郵件流程規則，以篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="45dd1-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="45dd1-158">使用下列語法來建立一或兩個郵件流程規則 (正則運算式與 words) ：</span><span class="sxs-lookup"><span data-stu-id="45dd1-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="45dd1-159">本範例會建立名為「大量電子郵件篩選-RegEx」的新規則，該規則使用主題中早期的正則運算式清單，將郵件設定為 **垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="45dd1-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="45dd1-160">本範例會建立名為「大量電子郵件篩選-字」的新規則，該規則使用主題中相同的單字清單，將郵件設定為 **高信賴的垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="45dd1-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="45dd1-161">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="45dd1-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="45dd1-162">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="45dd1-162">How do you know this worked?</span></span>

<span data-ttu-id="45dd1-163">若要驗證您是否已設定郵件流程規則以篩選大量電子郵件，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="45dd1-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="45dd1-164">在 EAC 中，移至 [ **郵件流程** \> **規則**] \> 選取規則 \> ，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="45dd1-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="45dd1-165">在 PowerShell 中，以 \<Rule Name\> 規則名稱取代，並執行下列命令來確認設定：</span><span class="sxs-lookup"><span data-stu-id="45dd1-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="45dd1-166">從外部帳戶，傳送測試郵件至受影響的收件者，其中包含其中一個短語或文字模式，並確認結果。</span><span class="sxs-lookup"><span data-stu-id="45dd1-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>