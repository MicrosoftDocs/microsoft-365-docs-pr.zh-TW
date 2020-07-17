---
title: 防網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解 Exchange Online Protection （EOP）和 Office 365 Advanced 威脅防護（Office 365 ATP）中可用的反網路釣魚原則。
ms.openlocfilehash: a61123e3d90a4125bf5a8303654973e1b478fc4c
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754661"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="b9d2e-103">Microsoft 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="b9d2e-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="b9d2e-104">Microsoft 365 組織中有 Exchange Online 信箱、獨立 Exchange Online Protection （EOP）組織（沒有 Exchange Online 信箱）和 Office 365 高級威脅防護（Office 365 ATP）組織的 Microsoft 組織皆可使用設定反網路釣魚防護設定的原則。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="b9d2e-105">ATP 反網路釣魚原則僅可用於具有 Office 365 ATP 的組織。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="b9d2e-106">例如：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-106">For example:</span></span>

- <span data-ttu-id="b9d2e-107">Microsoft 365 企業版 E5、Microsoft 365 教育版 A5 等等。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="b9d2e-108">Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="b9d2e-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="b9d2e-109">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="b9d2e-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="b9d2e-110">Office 365 ATP 做為附加元件</span><span class="sxs-lookup"><span data-stu-id="b9d2e-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="b9d2e-111">所有其他組織皆具有反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="b9d2e-112">下表說明反網路釣魚原則與 ATP 反網路釣魚原則之間的高層級差異：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

||||
|---|:---:|:---:|
|<span data-ttu-id="b9d2e-113">**功能**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-113">**Feature**</span></span>|<span data-ttu-id="b9d2e-114">**防網路釣魚原則**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-114">**Anti-phishing policies**</span></span>|<span data-ttu-id="b9d2e-115">**ATP 反網路釣魚原則**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-115">**ATP anti-phishing policies**</span></span>|
|<span data-ttu-id="b9d2e-116">自動建立的預設原則</span><span class="sxs-lookup"><span data-stu-id="b9d2e-116">Automatically created default policy</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b9d2e-119">建立自訂原則</span><span class="sxs-lookup"><span data-stu-id="b9d2e-119">Create custom policies</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b9d2e-122">原則設定<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9d2e-122">Policy settings<sup>\*</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b9d2e-125">類比設定</span><span class="sxs-lookup"><span data-stu-id="b9d2e-125">Impersonation settings</span></span>||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b9d2e-127">欺騙設定</span><span class="sxs-lookup"><span data-stu-id="b9d2e-127">Spoof settings</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b9d2e-130">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="b9d2e-130">Advanced phishing thresholds</span></span>||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="b9d2e-132"><sup>\*</sup>在 [預設原則] 中，[原則名稱] 和 [描述] 是唯讀的（描述是空白），您無法指定套用原則的人員（預設原則會套用至所有收件者）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="b9d2e-133">若要設定反網路釣魚原則，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-133">To configure anti-phishing policies, see the following topics:</span></span>

- [<span data-ttu-id="b9d2e-134">在 EOP 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="b9d2e-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="b9d2e-135">在 Microsoft 365 中設定 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="b9d2e-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="b9d2e-136">本主題的其餘部分將說明反網路釣魚原則和 ATP 反網路釣魚原則中可用的設定。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-136">The rest of this topic describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="b9d2e-137">欺騙設定</span><span class="sxs-lookup"><span data-stu-id="b9d2e-137">Spoof settings</span></span>

<span data-ttu-id="b9d2e-138">哄騙是指電子郵件訊息中的寄件者位址（顯示在電子郵件客戶程式中的寄件者位址）不符合電子郵件來源的網域。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-138">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="b9d2e-139">如需有關欺騙的詳細資訊，請參閱[Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-139">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b9d2e-140">下列欺騙設定可在反網路釣魚原則和 ATP 反網路釣魚原則中使用：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-140">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b9d2e-141">**反欺騙保護**：啟用或停用反欺詐防護。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-141">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="b9d2e-142">建議您讓它保留啟用狀態。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-142">We recommend that you leave it enabled.</span></span> <span data-ttu-id="b9d2e-143">您可以使用**哄騙智慧原則**來允許或封鎖特定的欺騙內部和外部寄件者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-143">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="b9d2e-144">如需詳細資訊，請參閱[在 Microsoft 365 中設定詐騙情報](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-144">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b9d2e-145">預設會在 EOP 的預設反網路釣魚原則、預設的 ATP 反網路釣魚原則，以及您建立的新自訂反網路釣魚原則或 ATP 反網路釣魚原則中啟用欺騙設定。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-145">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="b9d2e-146">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-146">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="b9d2e-147">如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-147">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="b9d2e-148">針對來自封鎖欺騙寄件者的郵件，您也可以指定要對郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-148">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="b9d2e-149">**將郵件移至 [垃圾郵件] 資料夾**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-149">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="b9d2e-150">郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-150">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b9d2e-151">在 Exchange Online 中，如果信箱上已啟用垃圾郵件規則，郵件會移至 [垃圾郵件] 資料夾（預設為啟用）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-151">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b9d2e-152">如需詳細資訊，請參閱[在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-152">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="b9d2e-153">**隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-153">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b9d2e-154">如需隔離的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-154">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="b9d2e-155">Microsoft 365 中的隔離</span><span class="sxs-lookup"><span data-stu-id="b9d2e-155">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b9d2e-156">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="b9d2e-156">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b9d2e-157">以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="b9d2e-157">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="b9d2e-158">**未經驗證的寄件者**：啟用或停用 Outlook 中不明的寄件者識別。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-158">**Unauthenticated Sender**: Enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="b9d2e-159">特別是：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-159">Specifically:</span></span>

  - <span data-ttu-id="b9d2e-160">如果郵件未通過 SPF 或 DKIM 檢查 **，而且**郵件未通過 DMARC 或[複合驗證](email-validation-and-authentication.md#composite-authentication)，就會將問號（？）新增到寄件者的相片。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-160">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

  - <span data-ttu-id="b9d2e-161">如果寄件者位址（顯示在電子郵件客戶程式中的郵件寄件者）的網域不同于 DKIM 簽章中的網域或**郵件發**件人位址中的網域，則會新增 via 標記（chris@contoso.com <u>via</u> michelle@fabrikam.com）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-161">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="b9d2e-162">如需這些位址的詳細資訊，請參閱[電子郵件標準的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="b9d2e-162">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

  <span data-ttu-id="b9d2e-163">若要防止這些識別碼新增至特定寄件者的郵件，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-163">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

  - <span data-ttu-id="b9d2e-164">允許寄件者在欺騙智慧原則中哄騙。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-164">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="b9d2e-165">如需相關指示，請參閱[Configure 哄騙情報 In Microsoft 365](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-165">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  - <span data-ttu-id="b9d2e-166">設定寄件者網域的[電子郵件驗證](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-166">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
    - <span data-ttu-id="b9d2e-167">針對寄件者相片中的問號，SPF 或 DKIM 最為重要。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-167">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
    - <span data-ttu-id="b9d2e-168">在 [via] 標籤上，確認 DKIM 簽章中的網域，或是從 [寄件者] 位址的網域中的 [從位址相符（或）**郵件**的子域]。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-168">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

  <span data-ttu-id="b9d2e-169">如需詳細資訊，請參閱[在 Outlook.com 中識別可疑郵件和網頁上的 Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="b9d2e-169">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b9d2e-170">ATP 反網路釣魚原則中的獨佔設定</span><span class="sxs-lookup"><span data-stu-id="b9d2e-170">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b9d2e-171">本節說明只可用於 ATP 反網路釣魚原則中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-171">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b9d2e-172">根據預設，不會設定或開啟 ATP 獨佔設定，即使在預設原則中也是一樣。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-172">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="b9d2e-173">若要利用這些功能，您必須在預設的 ATP 反網路釣魚原則中啟用和設定這些功能，或建立及設定自訂 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-173">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="policy-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b9d2e-174">ATP 反網路釣魚原則中的原則設定</span><span class="sxs-lookup"><span data-stu-id="b9d2e-174">Policy settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b9d2e-175">下列原則設定僅適用于 ATP 反網路釣魚原則中：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-175">The following policy settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b9d2e-176">**名稱**：您無法重新命名預設的反網路釣魚原則，但您可以命名和重新命名您建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-176">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="b9d2e-177">**描述**您無法將描述新增至預設的反網路釣魚原則，但您可以新增及變更所建立之自訂原則的描述。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-177">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="b9d2e-178">**適用于**：識別 ATP 反網路釣魚原則適用的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-178">**Applied to**: Identifies internal recipients that the ATP anti-phishing policy applies to.</span></span> <span data-ttu-id="b9d2e-179">此值在自訂原則中是必要的，在預設原則中不可用（預設原則會套用至所有收件者）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-179">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

    <span data-ttu-id="b9d2e-180">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-180">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b9d2e-181">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-181">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b9d2e-182">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-182">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="b9d2e-183">**收件**者：一或多個信箱、郵件使用者或您組織中的郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-183">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="b9d2e-184">**收件者隸屬**于組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-184">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="b9d2e-185">**收件者網域是**： Microsoft 365 中的一或多個已設定公認的網域。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-185">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="b9d2e-186">例外狀況**除外**：規則的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-186">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="b9d2e-187">設定和行為完全像是條件：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-187">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="b9d2e-188">**收件者為**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-188">**Recipient is**</span></span>
    - <span data-ttu-id="b9d2e-189">**收件者是的成員**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-189">**Recipient is a member of**</span></span>
    - <span data-ttu-id="b9d2e-190">**收件者網域是**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-190">**The recipient domain is**</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b9d2e-191">ATP 反網路釣魚原則中的類比設定</span><span class="sxs-lookup"><span data-stu-id="b9d2e-191">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b9d2e-192">模仿是指寄件者或寄件者的電子郵件網域與實際寄件者或網域類似的位置：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-192">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="b9d2e-193">網域 contoso.com 的模仿範例是ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-193">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>

- <span data-ttu-id="b9d2e-194">使用者 michelle@contoso.com 的模仿範例是 michele@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-194">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="b9d2e-195">另外，模擬的網域可能被視為合法（已註冊的網域、設定的電子郵件驗證記錄等等），但其目的是欺騙收件者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-195">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="b9d2e-196">下列模擬設定僅適用于 ATP 反網路釣魚原則中：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-196">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b9d2e-197">**要保護的使用者**：防止指定的內部或外部使用者進行類比。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-197">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="b9d2e-198">例如，主管（內部）和董事會成員（外部）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-198">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="b9d2e-199">您最多可以新增60的內部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-199">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="b9d2e-200">此受保護的使用者清單與套用**至**設定之原則的收件者清單不同。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-200">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b9d2e-201">例如，您在套用至名為「主管」群組的原則中，將 Felipe Apodaca （felipea@contoso.com）指定為受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-201">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="b9d2e-202">傳送給主管群組成員的輸入郵件，其中 Felipe Apodaca 是類比的，會由原則處理（為模擬使用者設定的動作）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-202">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="b9d2e-203">**要保護的網域**：防止類比指定的網域。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-203">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="b9d2e-204">例如，您擁有的所有網域（[公認的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)）或特定網域（擁有或夥伴網域的網域）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-204">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="b9d2e-205">受保護網域的清單與套用**至**設定之原則所套用的網域清單不同。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-205">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b9d2e-206">例如，您在套用至群組成員的群組成員的原則中，將 tailspintoys.com 指定為受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-206">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="b9d2e-207">傳送給主管群組成員的輸入郵件會由原則處理（為模擬的網域所設定的動作）的 tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-207">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="b9d2e-208">**受保護的使用者或網域的動作**：選擇要針對輸入郵件採取的動作，該郵件包含對原則中受保護的使用者與受保護的網域的模仿嘗試。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-208">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="b9d2e-209">您可以指定不同的使用者模擬，以類比受保護的使用者與模擬受保護的網域：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-209">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="b9d2e-210">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-210">**Don't apply any action**</span></span>

  - <span data-ttu-id="b9d2e-211">將**郵件重新導向至其他電子郵件地址**：將郵件傳送給指定的收件者，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-211">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="b9d2e-212">**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-212">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b9d2e-213">在 Exchange Online 中，如果信箱上已啟用垃圾郵件規則，郵件會移至 [垃圾郵件] 資料夾（預設為啟用）。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-213">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b9d2e-214">如需詳細資訊，請參閱[在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-214">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="b9d2e-215">**隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-215">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b9d2e-216">如需隔離的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-216">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="b9d2e-217">Microsoft 365 中的隔離</span><span class="sxs-lookup"><span data-stu-id="b9d2e-217">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b9d2e-218">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="b9d2e-218">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b9d2e-219">以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="b9d2e-219">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="b9d2e-220">**傳遞郵件並將其他位址新增至 Bcc 行**：將郵件傳遞給預定的收件者，並以無訊息方式將郵件傳遞給指定的收件者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-220">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="b9d2e-221">**傳遞郵件之前將其刪除**：無訊息地刪除整個郵件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-221">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="b9d2e-222">**安全性秘訣**：啟用或停用下列會顯示失敗之模擬檢查的模仿安全性秘訣：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-222">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="b9d2e-223">**類比使用者**：寄件者位址包含受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-223">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="b9d2e-224">**類比網域**：寄件者位址包含受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-224">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="b9d2e-225">不**尋常的字元**：寄件者位址包含不尋常的字元集（例如數學符號和文字，或是混合的大小寫字母）在受保護的寄件者或網域中。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-225">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="b9d2e-226">**信箱智慧**：啟用或停用人工情報（AI），以決定使用者的電子郵件模式與經常的連絡人。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-226">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="b9d2e-227">此設定可協助 AI 區分合法和欺騙的電子郵件與這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-227">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="b9d2e-228">信箱智慧只適用于 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-228">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="b9d2e-229">**信箱智慧**型模擬保護：根據每個使用者的個人寄件者地圖，啟用或停用增強型類比結果。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-229">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="b9d2e-230">這種智慧可讓 Microsoft 365 自訂使用者模擬偵測，並更好地處理誤報。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-230">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="b9d2e-231">偵測到使用者模擬時，您可以定義要對郵件採取的特定動作：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-231">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="b9d2e-232">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-232">**Don't apply any action**</span></span>
  - <span data-ttu-id="b9d2e-233">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-233">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="b9d2e-234">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-234">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="b9d2e-235">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-235">**Quarantine the message**</span></span>
  - <span data-ttu-id="b9d2e-236">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-236">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="b9d2e-237">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="b9d2e-237">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="b9d2e-238">**受信任的寄件者和網域**：模仿保護設定的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-238">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="b9d2e-239">來自指定寄件者和寄件者網域的郵件，永遠不會分類為以模仿為模擬的受原則攻擊。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-239">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="b9d2e-240">換句話說，受保護寄件者、受保護的網域或信箱智慧保護的動作不會套用到這些受信任的寄件者或寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-240">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="b9d2e-241">這兩個清單的上限大約是1000個專案。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-241">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="b9d2e-242">ATP 反網路釣魚原則中的高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="b9d2e-242">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="b9d2e-243">下列高級網路釣魚臨界值僅可用於 ATP 反網路釣魚原則，以控制將機器學習模型套用至郵件以判定網路釣魚是否判定的敏感程度：</span><span class="sxs-lookup"><span data-stu-id="b9d2e-243">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="b9d2e-244">**1-Standard**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-244">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="b9d2e-245">針對郵件採取的動作嚴重性，取決於郵件為網路釣魚（低、中、高或非常高的信賴程度）的信賴程度。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-245">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="b9d2e-246">例如，以非常高的信賴程度識別為網路釣魚的郵件會套用最嚴重的動作，而識別為低信任程度之網路釣魚的郵件，則會套用較低的嚴重動作。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-246">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="b9d2e-247">**2-嚴格**：識別為具有高可信度之網路釣魚的郵件，就像是以非常高的信賴程度加以識別一樣加以對待。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-247">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b9d2e-248">**3-更嚴格**：辨識為具有中等或高置信度之網路釣魚的郵件，視為以極高的信賴程度加以識別。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-248">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b9d2e-249">**4-最主動**：以低、中或高置信度識別為網路釣魚的郵件，視為以極高的置信度識別。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-249">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="b9d2e-250">誤報的機率（正確的訊息標示為壞）會隨著您增加此設定而增加。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-250">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="b9d2e-251">如需建議設定的詳細資訊，請參閱[OFFICE ATP 反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="b9d2e-251">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>