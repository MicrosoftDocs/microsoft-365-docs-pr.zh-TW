---
title: 使用郵件流程規則來篩選大量電子郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用郵件流程規則（傳輸規則），在 Exchange Online Protection （EOP）中識別及篩選大宗郵件（灰色郵件）。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb305551db1e86d8d6eccf5e95cdaad29e6711ef
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208522"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="dbd34-103">使用郵件流程規則來篩選 EOP 中的大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="dbd34-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="dbd34-104">在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，EOP 會使用反垃圾郵件原則（也稱為垃圾郵件篩選原則或內容篩選原則）來掃描輸入郵件中的垃圾郵件和大宗郵件（也稱為灰色郵件）。</span><span class="sxs-lookup"><span data-stu-id="dbd34-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="dbd34-105">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="dbd34-106">如果您想要更多的選項來篩選大宗郵件，您可以建立郵件流程規則（也稱為傳輸規則），以搜尋大宗郵件中經常找到的文字模式或片語，並將這些郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="dbd34-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="dbd34-107">如需大宗郵件的詳細資訊，請參閱 EOP 中[垃圾郵件和大量電子郵件](what-s-the-difference-between-junk-email-and-bulk-email.md)以及大量[投訴（BCL）](bulk-complaint-level-values.md)之間的差異。</span><span class="sxs-lookup"><span data-stu-id="dbd34-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="dbd34-108">本主題說明如何在 Exchange 系統管理中心（EAC）中建立這些郵件流程規則 PowerShell，以及如何在 exchange Online 中建立 EOP （Exchange Online PowerShell 365 適用于 exchange Online 的信箱; 獨立 PowerShell 不含 Exchange Online 信箱的組織）。</span><span class="sxs-lookup"><span data-stu-id="dbd34-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dbd34-109">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="dbd34-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dbd34-110">您必須已獲指派許可權，才能執行這些程式：</span><span class="sxs-lookup"><span data-stu-id="dbd34-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="dbd34-111">在 Exchange Online 中，請參閱在[Exchange online 中的功能許可權中](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)的「郵件流程」專案。</span><span class="sxs-lookup"><span data-stu-id="dbd34-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="dbd34-112">在獨立 EOP 中，您需要傳輸規則角色，預設會指派給 OrganizationManagement、ComplianceManagement 和 RecordsManagement 角色。</span><span class="sxs-lookup"><span data-stu-id="dbd34-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="dbd34-113">如需詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)和[使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="dbd34-114">若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="dbd34-115">若要在獨立 EOP 中開啟 EAC，請參閱[Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="dbd34-116">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="dbd34-117">若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-117">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="dbd34-118">如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="dbd34-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="dbd34-119">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="dbd34-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="dbd34-120">Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)</span><span class="sxs-lookup"><span data-stu-id="dbd34-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="dbd34-121">Exchange Online 中的郵件流程規則動作</span><span class="sxs-lookup"><span data-stu-id="dbd34-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="dbd34-122">在範例中用來識別大宗郵件的單字和文字模式清單並不詳盡;您可以視需要新增及移除專案。</span><span class="sxs-lookup"><span data-stu-id="dbd34-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="dbd34-123">不過，它們是一個很好的起點。</span><span class="sxs-lookup"><span data-stu-id="dbd34-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="dbd34-p107">在主旨或郵件的其他標頭欄位中搜尋字詞或文字模式，會發生在郵件已從 MIME 內容傳輸編碼方法進行解碼*之後*，該編碼方法用來在 SMTP 伺服器之間傳送 ASCII 文字二進位訊息。您無法使用條件或例外狀況來搜尋主旨或郵件中其他標頭欄位的原始 (通常是 Base64) 編碼值。</span><span class="sxs-lookup"><span data-stu-id="dbd34-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="dbd34-126">下列程式會將大宗郵件標記為您整個組織的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="dbd34-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="dbd34-127">不過，您可以新增另一個條件，只將這些規則套用至特定的收件者，這樣您就可以在一些高度目標的使用者上使用嚴格篩選，而其餘的使用者（大部分已註冊的大量電子郵件）不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="dbd34-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="dbd34-128">使用 EAC 來建立郵件流程規則，以篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="dbd34-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="dbd34-129">在 EAC 中，移至 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbd34-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="dbd34-130">按一下 [**新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [**建立新的規則**]。</span><span class="sxs-lookup"><span data-stu-id="dbd34-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="dbd34-131">在開啟的 [**新增規則**] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="dbd34-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="dbd34-132">**名稱**：輸入規則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="dbd34-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="dbd34-133">按一下 [**更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="dbd34-133">Click **More Options**.</span></span>

   - <span data-ttu-id="dbd34-134">**在下列情況中套用此規則**：設定下列其中一個設定，以使用正則運算式（RegEx）或字詞或片語來尋找郵件中的內容：</span><span class="sxs-lookup"><span data-stu-id="dbd34-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="dbd34-135">**主語或** \> 本文主旨或內文**符合這些文字模式**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，按一下 [**新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。</span><span class="sxs-lookup"><span data-stu-id="dbd34-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="dbd34-136">若要編輯專案，請選取它，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="dbd34-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="dbd34-137">若要移除專案，請選取它，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="dbd34-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="dbd34-138">完成後，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbd34-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="dbd34-139">**主語或** \> 本文主旨或內文**包含下列任何文字**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，按一下 [**新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。</span><span class="sxs-lookup"><span data-stu-id="dbd34-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="dbd34-140">若要編輯專案，請選取它，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="dbd34-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="dbd34-141">若要移除專案，請選取它，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="dbd34-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="dbd34-142">完成後，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbd34-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="dbd34-143">**請執行下列**動作：選取 [**修改郵件屬性**] \> **設定垃圾郵件信賴等級（SCL）**。</span><span class="sxs-lookup"><span data-stu-id="dbd34-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="dbd34-144">在出現的 [**指定 SCL** ] 對話方塊中，設定下列其中一個設定：</span><span class="sxs-lookup"><span data-stu-id="dbd34-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="dbd34-145">若要將郵件標示為**垃圾**郵件，請選取 [ **6**]。</span><span class="sxs-lookup"><span data-stu-id="dbd34-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="dbd34-146">您為反垃圾郵件原則中的**垃圾**郵件篩選 verdicts 設定的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。</span><span class="sxs-lookup"><span data-stu-id="dbd34-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="dbd34-147">將郵件標示為**高信賴度垃圾郵件**選取**9**。</span><span class="sxs-lookup"><span data-stu-id="dbd34-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="dbd34-148">您為反垃圾郵件原則中已設定**高信賴度垃圾郵件**篩選 verdicts 的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。</span><span class="sxs-lookup"><span data-stu-id="dbd34-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="dbd34-149">如需 SCL 值的詳細資訊，請參閱[EOP 中的垃圾郵件信賴等級（SCL）](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="dbd34-150">完成後，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbd34-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="dbd34-151">使用 PowerShell 建立郵件流程規則，以篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="dbd34-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="dbd34-152">使用下列語法來建立一或兩個郵件流程規則（正則運算式與字）：</span><span class="sxs-lookup"><span data-stu-id="dbd34-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="dbd34-153">本範例會建立名為「大量電子郵件篩選-RegEx」的新規則，該規則使用主題中早期的正則運算式清單，將郵件設定為**垃圾**郵件。</span><span class="sxs-lookup"><span data-stu-id="dbd34-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="dbd34-154">本範例會建立名為「大量電子郵件篩選-字」的新規則，該規則使用主題中相同的單字清單，將郵件設定為**高信賴的垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="dbd34-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="dbd34-155">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="dbd34-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="dbd34-156">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="dbd34-156">How do you know this worked?</span></span>

<span data-ttu-id="dbd34-157">若要驗證您是否已設定郵件流程規則以篩選大量電子郵件，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="dbd34-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="dbd34-158">在 EAC 中，移至 [**郵件流程** \> **規則**] \> 選取規則 \> ，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="dbd34-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="dbd34-159">在 PowerShell 中，以 \< 規則名稱取代規則名稱 \> ，並執行下列命令來確認設定：</span><span class="sxs-lookup"><span data-stu-id="dbd34-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="dbd34-160">從外部帳戶，傳送測試郵件至受影響的收件者，其中包含其中一個短語或文字模式，並確認結果。</span><span class="sxs-lookup"><span data-stu-id="dbd34-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
