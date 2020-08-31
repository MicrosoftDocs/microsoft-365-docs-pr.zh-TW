---
title: 防網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 和 Office 365 的高級威脅防護 (Office 365 ATP) 中可用的反網路釣魚原則。
ms.openlocfilehash: 7118bca15102fd52e7825ee873187fa11d9fc0f9
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308192"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="69952-103">Microsoft 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="69952-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="69952-104">使用 Exchange Online 信箱、獨立 Exchange Online Protection (EOP) 組織（沒有 Exchange Online 信箱）和 Office 365 高級威脅防護 (Office 365 ATP) 組織，可在 Microsoft 365 組織中取得設定反網路釣魚保護設定的原則。</span><span class="sxs-lookup"><span data-stu-id="69952-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="69952-105">ATP 反網路釣魚原則僅可用於具有 Office 365 ATP 的組織。</span><span class="sxs-lookup"><span data-stu-id="69952-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="69952-106">例如：</span><span class="sxs-lookup"><span data-stu-id="69952-106">For example:</span></span>

- <span data-ttu-id="69952-107">Microsoft 365 企業版 E5、Microsoft 365 教育版 A5 等等。</span><span class="sxs-lookup"><span data-stu-id="69952-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="69952-108">Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="69952-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="69952-109">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="69952-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="69952-110">Office 365 ATP 做為附加元件</span><span class="sxs-lookup"><span data-stu-id="69952-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="69952-111">所有其他組織皆具有反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="69952-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="69952-112">下表說明反網路釣魚原則與 ATP 反網路釣魚原則之間的高層級差異：</span><span class="sxs-lookup"><span data-stu-id="69952-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

****

|<span data-ttu-id="69952-113">功能</span><span class="sxs-lookup"><span data-stu-id="69952-113">Feature</span></span>|<span data-ttu-id="69952-114">防網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="69952-114">Anti-phishing policies</span></span>|<span data-ttu-id="69952-115">ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="69952-115">ATP anti-phishing policies</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="69952-116">自動建立的預設原則</span><span class="sxs-lookup"><span data-stu-id="69952-116">Automatically created default policy</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="69952-119">建立自訂原則</span><span class="sxs-lookup"><span data-stu-id="69952-119">Create custom policies</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="69952-122">原則設定<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="69952-122">Policy settings<sup>\*</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="69952-125">類比設定</span><span class="sxs-lookup"><span data-stu-id="69952-125">Impersonation settings</span></span>||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="69952-127">欺騙設定</span><span class="sxs-lookup"><span data-stu-id="69952-127">Spoof settings</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="69952-130">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="69952-130">Advanced phishing thresholds</span></span>||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="69952-132"><sup>\*</sup> 在 [預設原則] 中，[原則名稱] 和 [描述] 是唯讀的 (描述是空白的) ，而且您不能指定原則套用至所有收件者) 的 (。</span><span class="sxs-lookup"><span data-stu-id="69952-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="69952-133">若要設定反網路釣魚原則，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="69952-133">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="69952-134">在 EOP 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="69952-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="69952-135">在 Microsoft 365 中設定 ATP 反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="69952-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="69952-136">本文的其餘部分將說明反網路釣魚原則和 ATP 反網路釣魚原則中可用的設定。</span><span class="sxs-lookup"><span data-stu-id="69952-136">The rest of this article describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="69952-137">原則設定</span><span class="sxs-lookup"><span data-stu-id="69952-137">Policy settings</span></span>

<span data-ttu-id="69952-138">反網路釣魚原則和 ATP 反網路釣魚原則中提供下列原則設定：</span><span class="sxs-lookup"><span data-stu-id="69952-138">The following policy settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="69952-139">**名稱**：您無法重新命名預設的反網路釣魚原則，但您可以命名和重新命名您建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="69952-139">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="69952-140">**描述** 您無法將描述新增至預設的反網路釣魚原則，但您可以新增及變更所建立之自訂原則的描述。</span><span class="sxs-lookup"><span data-stu-id="69952-140">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="69952-141">**適用于**：識別反網路釣魚原則套用的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-141">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="69952-142">此值是自訂原則中的必要條件，在預設原則中不可使用 (預設原則會套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="69952-142">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="69952-143">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="69952-143">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="69952-144">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="69952-144">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="69952-145">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="69952-145">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="69952-146">**收件**者：一或多個信箱、郵件使用者或您組織中的郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="69952-146">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="69952-147">**收件者隸屬**于組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="69952-147">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="69952-148">**收件者網域是**： Microsoft 365 中的一或多個已設定公認的網域。</span><span class="sxs-lookup"><span data-stu-id="69952-148">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="69952-149">例外狀況**除外**：規則的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="69952-149">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="69952-150">設定和行為完全像是條件：</span><span class="sxs-lookup"><span data-stu-id="69952-150">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="69952-151">**收件者為**</span><span class="sxs-lookup"><span data-stu-id="69952-151">**Recipient is**</span></span>
    - <span data-ttu-id="69952-152">**收件者是的成員**</span><span class="sxs-lookup"><span data-stu-id="69952-152">**Recipient is a member of**</span></span>
    - <span data-ttu-id="69952-153">**收件者網域是**</span><span class="sxs-lookup"><span data-stu-id="69952-153">**The recipient domain is**</span></span>

  > [!NOTE]
  > <span data-ttu-id="69952-154">您必須在自訂的反網路釣魚原則中，套用**to**設定，以辨識<u>原則所套用</u>**的郵件收件者**。</span><span class="sxs-lookup"><span data-stu-id="69952-154">The **Applied to** setting is required in custom anti-phishing policies to identify them message **recipients** <u>that the policy applies to</u>.</span></span> <span data-ttu-id="69952-155">ATP 反網路釣魚原則也有 [類比設定](#impersonation-settings-in-atp-anti-phishing-policies) ，您可以在其中指定個別寄件者的電子郵件地址或寄件者網域，以在本主題稍後所述 <u>的方式接收模擬保護</u> 。</span><span class="sxs-lookup"><span data-stu-id="69952-155">ATP anti-phishing policies also have [impersonation settings](#impersonation-settings-in-atp-anti-phishing-policies) where you can specify individual sender email addresses or sender domains <u>that will receive impersonation protection</u> as described later in this topic.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="69952-156">欺騙設定</span><span class="sxs-lookup"><span data-stu-id="69952-156">Spoof settings</span></span>

<span data-ttu-id="69952-157">哄騙是指電子郵件中的寄件者位址 (電子郵件客戶程式中所顯示的寄件者位址) 不會符合電子郵件來源的網域。</span><span class="sxs-lookup"><span data-stu-id="69952-157">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="69952-158">如需有關欺騙的詳細資訊，請參閱 [Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="69952-158">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="69952-159">下列欺騙設定可在反網路釣魚原則和 ATP 反網路釣魚原則中使用：</span><span class="sxs-lookup"><span data-stu-id="69952-159">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="69952-160">**反欺騙保護**：啟用或停用反欺詐防護。</span><span class="sxs-lookup"><span data-stu-id="69952-160">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="69952-161">建議您讓它保留啟用狀態。</span><span class="sxs-lookup"><span data-stu-id="69952-161">We recommend that you leave it enabled.</span></span> <span data-ttu-id="69952-162">您可以使用 **哄騙智慧原則** 來允許或封鎖特定的欺騙內部和外部寄件者。</span><span class="sxs-lookup"><span data-stu-id="69952-162">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="69952-163">如需詳細資訊，請參閱[在 Microsoft 365 中設定詐騙情報](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="69952-163">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="69952-164">預設會在 EOP 的預設反網路釣魚原則、預設的 ATP 反網路釣魚原則，以及您建立的新自訂反網路釣魚原則或 ATP 反網路釣魚原則中啟用欺騙設定。</span><span class="sxs-lookup"><span data-stu-id="69952-164">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="69952-165">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="69952-165">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="69952-166">如需相關指示，請參閱 [在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="69952-166">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="69952-167">針對來自封鎖欺騙寄件者的郵件，您也可以指定要對郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="69952-167">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="69952-168">**將郵件移至 [垃圾郵件] 資料夾**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="69952-168">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="69952-169">郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="69952-169">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="69952-170">在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。</span><span class="sxs-lookup"><span data-stu-id="69952-170">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="69952-171">如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="69952-171">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="69952-172">**隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-172">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="69952-173">如需隔離的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="69952-173">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="69952-174">Microsoft 365 中的隔離</span><span class="sxs-lookup"><span data-stu-id="69952-174">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="69952-175">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="69952-175">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="69952-176">以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="69952-176">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="69952-177">**未經驗證的寄件者**：請參閱下一節的描述。</span><span class="sxs-lookup"><span data-stu-id="69952-177">**Unauthenticated Sender**: See the description in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="69952-178">未驗證寄件者</span><span class="sxs-lookup"><span data-stu-id="69952-178">Unauthenticated Sender</span></span>

<span data-ttu-id="69952-179">未經驗證的寄件者識別碼是反網路釣魚原則和 ATP 反網路釣魚原則中提供的 [欺騙設定](#spoof-settings) 的一部分，如上一節所述。</span><span class="sxs-lookup"><span data-stu-id="69952-179">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies and ATP anti-phishing policies as described in the previous section.</span></span>

<span data-ttu-id="69952-180">**未經驗證的寄件者**設定可啟用或停用 Outlook 中未識別的寄件者識別</span><span class="sxs-lookup"><span data-stu-id="69952-180">The **Unauthenticated Sender** setting enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="69952-181">特別是：</span><span class="sxs-lookup"><span data-stu-id="69952-181">Specifically:</span></span>

- <span data-ttu-id="69952-182">當郵件未通過 SPF 或 DKIM 檢查 **，且** 郵件未通過 DMARC 或 [複合驗證](email-validation-and-authentication.md#composite-authentication)時，就會在寄件者的相片中加入一個問號 (？ ) 。</span><span class="sxs-lookup"><span data-stu-id="69952-182">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

- <span data-ttu-id="69952-183">如果 [寄件者] 位址中的網域 (電子郵件) 客戶程式中顯示的郵件寄件者不同于 DKIM 簽章中的網域或**郵件**的 [寄件者] 位址中的網域，則會新增 via 標籤<u> (chris@contoso.com 透過</u>michelle@fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="69952-183">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="69952-184">如需這些位址的詳細資訊，請參閱 [電子郵件標準的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="69952-184">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

<span data-ttu-id="69952-185">若要防止這些識別碼新增至特定寄件者的郵件，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="69952-185">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="69952-186">允許寄件者在欺騙智慧原則中哄騙。</span><span class="sxs-lookup"><span data-stu-id="69952-186">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="69952-187">如需相關指示，請參閱 [Configure 哄騙情報 In Microsoft 365](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="69952-187">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="69952-188">設定寄件者網域的[電子郵件驗證](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。</span><span class="sxs-lookup"><span data-stu-id="69952-188">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
  - <span data-ttu-id="69952-189">針對寄件者相片中的問號，SPF 或 DKIM 最為重要。</span><span class="sxs-lookup"><span data-stu-id="69952-189">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="69952-190">在 [via] 標籤上，確認 DKIM 簽章中的網域，或 [ **郵件發件** 人位址相符 (] 或 [寄件者] 位址中) 網域的子域。</span><span class="sxs-lookup"><span data-stu-id="69952-190">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="69952-191">如需詳細資訊，請參閱 [在 Outlook.com 中識別可疑郵件和網頁上的 Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="69952-191">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="69952-192">ATP 反網路釣魚原則中的獨佔設定</span><span class="sxs-lookup"><span data-stu-id="69952-192">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="69952-193">本節說明只可用於 ATP 反網路釣魚原則中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="69952-193">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="69952-194">根據預設，不會設定或開啟 ATP 獨佔設定，即使在預設原則中也是一樣。</span><span class="sxs-lookup"><span data-stu-id="69952-194">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="69952-195">若要利用這些功能，您必須在預設的 ATP 反網路釣魚原則中啟用和設定這些功能，或建立及設定自訂 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="69952-195">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="69952-196">ATP 反網路釣魚原則中的類比設定</span><span class="sxs-lookup"><span data-stu-id="69952-196">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="69952-197">模仿是指寄件者或寄件者的電子郵件網域與實際寄件者或網域類似的位置：</span><span class="sxs-lookup"><span data-stu-id="69952-197">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="69952-198">網域 contoso.com 的模仿範例是ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="69952-198">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="69952-199">使用者 michelle@contoso.com 的模仿範例是 michele@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="69952-199">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="69952-200">另一個模擬的網域可能會被視為合法 (已註冊的網域、設定的電子郵件驗證記錄等等 ) ，但其目的是欺騙收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-200">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="69952-201">下列模擬設定僅適用于 ATP 反網路釣魚原則中：</span><span class="sxs-lookup"><span data-stu-id="69952-201">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="69952-202">**要保護的使用者**：防止將指定的內部或外部電子郵件地址類比 **為郵件寄件者**。</span><span class="sxs-lookup"><span data-stu-id="69952-202">**Users to protect**: Prevents the specified internal or external email addresses from being impersonated **as message senders**.</span></span> <span data-ttu-id="69952-203">例如，主管 (內部寄件者) 和董事會成員 (外部寄件者) 。</span><span class="sxs-lookup"><span data-stu-id="69952-203">For example, executives (internal senders) and board members (external senders).</span></span> <span data-ttu-id="69952-204">您最多可以新增60的內部和外部寄件者電子郵件地址，以防止假冒。</span><span class="sxs-lookup"><span data-stu-id="69952-204">You can add up to 60 internal and external sender email addresses to protect from impersonation.</span></span> <span data-ttu-id="69952-205">保護自模擬的 **寄件者** 清單，與套用 **原則的收** 件者清單不同。</span><span class="sxs-lookup"><span data-stu-id="69952-205">This list of **senders** that are protected from impersonation is different from the list of **recipients** that the policy applies to.</span></span>

  <span data-ttu-id="69952-206">預設原則會套用至傳送給所有收件者的郵件，而自訂原則只會套用至您在 [[原則設定](#policy-settings)] 區段中所述的 [套用**至**] 設定中所述的收件者所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="69952-206">The default policy applies to messages sent to all recipients, while custom policies apply only to messages sent to the recipients you define in the **Applied to** setting as described in the [Policy settings](#policy-settings) section.</span></span>

  <span data-ttu-id="69952-207">根據預設，不會將寄件者電子郵件地址設定為 **要保護的使用者**類比保護。</span><span class="sxs-lookup"><span data-stu-id="69952-207">By default, no sender email addresses are configured for impersonation protection in **Users to protect**.</span></span> <span data-ttu-id="69952-208">因此，根據預設，在 [預設原則] 或 [自訂原則] 中，模擬保護不會涵蓋任何寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="69952-208">Therefore, by default, no sender email addresses are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="69952-209">當您將內部或外部電子郵件地址新增至 **要保護的使用者** 清單時，來自這些 **寄件者** 的郵件會受到模仿保護檢查的制約。</span><span class="sxs-lookup"><span data-stu-id="69952-209">When you add internal or external email addresses to the **Users to protect** list, messages from those **senders** are subject to impersonation protection checks.</span></span> <span data-ttu-id="69952-210">**如果**郵件傳送給收件者的郵件是套用至預設原則的所有**收件**者，則會檢查郵件，以進行模擬 (;**適用于**自訂原則) 中的收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-210">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="69952-211">如果在寄件者的電子郵件地址中偵測到模擬，使用者的類比保護動作會套用至郵件 (郵件上的動作、類比的使用者安全提示等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="69952-211">If impersonation is detected in the sender's email address, the impersonation protections actions for users are applied to the message (the action on the message, the impersonated users safety tip, etc.).</span></span>

- <span data-ttu-id="69952-212">**要保護的網域**：防止 **在郵件寄件者的網域中**類比指定的網域。</span><span class="sxs-lookup"><span data-stu-id="69952-212">**Domains to protect**: Prevents the specified domains from being impersonated **in the message sender's domain**.</span></span> <span data-ttu-id="69952-213">例如，您擁有的所有網域 ([公認的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或特定網域 (您擁有的網域或夥伴網域) 。</span><span class="sxs-lookup"><span data-stu-id="69952-213">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="69952-214">保護自模擬的 **寄件者網域** 清單，與套用 **原則的收** 件者清單不同。</span><span class="sxs-lookup"><span data-stu-id="69952-214">This list of **sender domains** that are protected from impersonation is different from the list of **recipients** that the policy applies to.</span></span>

  <span data-ttu-id="69952-215">預設原則會套用至傳送給所有收件者的郵件，而自訂原則只會套用至您在 [[原則設定](#policy-settings)] 區段中所述的 [套用**至**] 設定中所述的收件者所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="69952-215">The default policy applies to messages sent to all recipients, while custom policies apply only to messages sent to the recipients you define in the **Applied to** setting as described in the [Policy settings](#policy-settings) section.</span></span>

  <span data-ttu-id="69952-216">根據預設，不會將寄件者網域設定為 **要保護的網域**中的類比保護。</span><span class="sxs-lookup"><span data-stu-id="69952-216">By default, no sender domains are configured for impersonation protection in **Domains to protect**.</span></span> <span data-ttu-id="69952-217">因此，根據預設，在 [預設原則] 或 [自訂原則] 中，模擬保護不會涵蓋任何寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="69952-217">Therefore, by default, no sender domains are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="69952-218">當您將網域新增至 **要保護的網域** 清單時，來自 **這些網域中寄件者** 的郵件會受到模擬保護檢查的制約。</span><span class="sxs-lookup"><span data-stu-id="69952-218">When you add domains to the **Domains to protect** list, messages from **senders in those domains** are subject to impersonation protection checks.</span></span> <span data-ttu-id="69952-219">**如果**郵件傳送給收件者的郵件是套用至預設原則的所有**收件**者，則會檢查郵件，以進行模擬 (;**適用于**自訂原則) 中的收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-219">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="69952-220">如果在寄件者的網域中偵測到模擬，就會將網域的模仿保護動作套用至郵件 (郵件上的動作、類比的網域安全提示等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="69952-220">If impersonation is detected in the sender's domain, the impersonation protection actions for domains are applied to the message (the action on the message, the impersonated domains safety tip, etc.).</span></span>

- <span data-ttu-id="69952-221">**受保護的使用者或網域的動作**：選擇要針對輸入郵件採取的動作，該郵件包含對原則中受保護的使用者與受保護的網域的模仿嘗試。</span><span class="sxs-lookup"><span data-stu-id="69952-221">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="69952-222">您可以指定不同的使用者模擬，以類比受保護的使用者與模擬受保護的網域：</span><span class="sxs-lookup"><span data-stu-id="69952-222">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="69952-223">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="69952-223">**Don't apply any action**</span></span>

  - <span data-ttu-id="69952-224">將**郵件重新導向至其他電子郵件地址**：將郵件傳送給指定的收件者，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-224">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="69952-225">**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="69952-225">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="69952-226">在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。</span><span class="sxs-lookup"><span data-stu-id="69952-226">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="69952-227">如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="69952-227">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="69952-228">**隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-228">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="69952-229">如需隔離的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="69952-229">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="69952-230">Microsoft 365 中的隔離</span><span class="sxs-lookup"><span data-stu-id="69952-230">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="69952-231">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="69952-231">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="69952-232">以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="69952-232">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="69952-233">**傳遞郵件並將其他位址新增至 Bcc 行**：將郵件傳遞給預定的收件者，並以無訊息方式將郵件傳遞給指定的收件者。</span><span class="sxs-lookup"><span data-stu-id="69952-233">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="69952-234">**傳遞郵件之前將其刪除**：無訊息地刪除整個郵件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="69952-234">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="69952-235">**安全性秘訣**：啟用或停用下列會顯示失敗之模擬檢查的模仿安全性秘訣：</span><span class="sxs-lookup"><span data-stu-id="69952-235">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="69952-236">**類比使用者**：寄件者位址包含受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="69952-236">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="69952-237">**類比網域**：寄件者位址包含受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="69952-237">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="69952-238">不**尋常的字元**： From 位址包含不尋常的字元集 (例如數學符號和文字，或是混合的大小寫字母) 在受保護的寄件者或網域中。</span><span class="sxs-lookup"><span data-stu-id="69952-238">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="69952-239">**信箱智慧**：啟用或停用使用者的智慧 (AI) ，可決定使用者的電子郵件模式與經常的連絡人。</span><span class="sxs-lookup"><span data-stu-id="69952-239">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="69952-240">此設定可協助 AI 區分合法和欺騙的電子郵件與這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="69952-240">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="69952-241">信箱智慧只適用于 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="69952-241">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="69952-242">**信箱智慧**型模擬保護：根據每個使用者的個人寄件者地圖，啟用或停用增強型類比結果。</span><span class="sxs-lookup"><span data-stu-id="69952-242">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="69952-243">這種智慧可讓 Microsoft 365 自訂使用者模擬偵測，並更好地處理誤報。</span><span class="sxs-lookup"><span data-stu-id="69952-243">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="69952-244">偵測到使用者模擬時，您可以定義要對郵件採取的特定動作：</span><span class="sxs-lookup"><span data-stu-id="69952-244">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="69952-245">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="69952-245">**Don't apply any action**</span></span>
  - <span data-ttu-id="69952-246">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="69952-246">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="69952-247">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="69952-247">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="69952-248">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="69952-248">**Quarantine the message**</span></span>
  - <span data-ttu-id="69952-249">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="69952-249">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="69952-250">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="69952-250">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="69952-251">**受信任的寄件者和網域**：模仿保護設定的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="69952-251">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="69952-252">來自指定寄件者和寄件者網域的郵件，永遠不會分類為以模仿為模擬的受原則攻擊。</span><span class="sxs-lookup"><span data-stu-id="69952-252">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="69952-253">換句話說，受保護寄件者、受保護的網域或信箱智慧保護的動作不會套用到這些受信任的寄件者或寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="69952-253">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="69952-254">這兩個清單的上限大約是1000個專案。</span><span class="sxs-lookup"><span data-stu-id="69952-254">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="69952-255">ATP 反網路釣魚原則中的高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="69952-255">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="69952-256">下列高級網路釣魚臨界值僅可用於 ATP 反網路釣魚原則，以控制將機器學習模型套用至郵件以判定網路釣魚是否判定的敏感程度：</span><span class="sxs-lookup"><span data-stu-id="69952-256">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="69952-257">**1-Standard**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="69952-257">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="69952-258">針對郵件採取的動作嚴重性，取決於郵件為網路釣魚 (低、中、高或非常高的信賴度) 的置信度。</span><span class="sxs-lookup"><span data-stu-id="69952-258">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="69952-259">例如，以非常高的信賴程度識別為網路釣魚的郵件會套用最嚴重的動作，而識別為低信任程度之網路釣魚的郵件，則會套用較低的嚴重動作。</span><span class="sxs-lookup"><span data-stu-id="69952-259">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="69952-260">**2-嚴格**：識別為具有高可信度之網路釣魚的郵件，就像是以非常高的信賴程度加以識別一樣加以對待。</span><span class="sxs-lookup"><span data-stu-id="69952-260">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="69952-261">**3-更嚴格**：辨識為具有中等或高置信度之網路釣魚的郵件，視為以極高的信賴程度加以識別。</span><span class="sxs-lookup"><span data-stu-id="69952-261">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="69952-262">**4-最主動**：以低、中或高置信度識別為網路釣魚的郵件，視為以極高的置信度識別。</span><span class="sxs-lookup"><span data-stu-id="69952-262">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="69952-263">誤報的機率 (，標記為壞) 會隨著您增加此設定而增加。</span><span class="sxs-lookup"><span data-stu-id="69952-263">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="69952-264">如需建議設定的詳細資訊，請參閱 [OFFICE ATP 反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="69952-264">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>
