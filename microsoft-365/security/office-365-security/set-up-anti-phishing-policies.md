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
description: 系統管理員可以瞭解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中可用的反網路釣魚原則。
ms.openlocfilehash: a02d69b278420d814871df8eebdd6efcdf5d8e7f
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376339"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="78f48-103">Microsoft 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="78f48-103">Anti-phishing policies in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="78f48-104">設定反網路釣魚防護設定的原則，可在 Microsoft 365 組織中使用 Exchange Online 信箱、獨立 Exchange Online Protection (EOP) 沒有 Exchange Online 信箱的組織，以及 Microsoft Defender for Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="78f48-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Microsoft Defender for Office 365 organizations.</span></span>

<span data-ttu-id="78f48-105">Microsoft Defender for Office 365 中的反網路釣魚原則只適用于擁有 Office 365 的企業。</span><span class="sxs-lookup"><span data-stu-id="78f48-105">Anti-phishing policies in Microsoft Defender for Office 365 are only available in organizations that have Defender for Office 365.</span></span> <span data-ttu-id="78f48-106">例如：</span><span class="sxs-lookup"><span data-stu-id="78f48-106">For example:</span></span>

- <span data-ttu-id="78f48-107">Microsoft 365 企業版 E5、Microsoft 365 教育版 A5 等等。</span><span class="sxs-lookup"><span data-stu-id="78f48-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="78f48-108">Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="78f48-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="78f48-109">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="78f48-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="78f48-110">Microsoft Defender for Office 365 做為附加元件</span><span class="sxs-lookup"><span data-stu-id="78f48-110">Microsoft Defender for Office 365 as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="78f48-111">下表說明 EOP 中的和反網路釣魚原則中的 Microsoft Defender for Office 365 中的反網路釣魚原則之間的高層次差異：</span><span class="sxs-lookup"><span data-stu-id="78f48-111">The high-level differences between anti-phishing policies in EOP and anti-phishing policies in Microsoft Defender for Office 365 are described in the following table:</span></span>

****

|<span data-ttu-id="78f48-112">功能</span><span class="sxs-lookup"><span data-stu-id="78f48-112">Feature</span></span>|<span data-ttu-id="78f48-113">EOP 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="78f48-113">Anti-phishing policies in EOP</span></span>|<span data-ttu-id="78f48-114">Microsoft Defender for Office 365 中的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="78f48-114">Anti-phishing policies in Microsoft Defender for Office 365</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="78f48-115">自動建立的預設原則</span><span class="sxs-lookup"><span data-stu-id="78f48-115">Automatically created default policy</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="78f48-118">建立自訂原則</span><span class="sxs-lookup"><span data-stu-id="78f48-118">Create custom policies</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="78f48-121">原則設定<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78f48-121">Policy settings<sup>\*</sup></span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="78f48-124">類比設定</span><span class="sxs-lookup"><span data-stu-id="78f48-124">Impersonation settings</span></span>||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="78f48-126">欺騙設定</span><span class="sxs-lookup"><span data-stu-id="78f48-126">Spoof settings</span></span>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="78f48-129">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="78f48-129">Advanced phishing thresholds</span></span>||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="78f48-131"><sup>\*</sup> 在 [預設原則] 中，[原則名稱] 和 [描述] 是唯讀的 (描述是空白的) ，而且您不能指定原則套用至所有收件者) 的 (。</span><span class="sxs-lookup"><span data-stu-id="78f48-131"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="78f48-132">若要設定反網路釣魚原則，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="78f48-132">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="78f48-133">在 EOP 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="78f48-133">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="78f48-134">在 Microsoft Defender for Office 365 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="78f48-134">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="78f48-135">本文的其餘部分將說明 EOP 和 Defender for Office 365 中的反網路釣魚原則中可用的設定。</span><span class="sxs-lookup"><span data-stu-id="78f48-135">The rest of this article describes the settings that are available in anti-phishing policies in EOP and Defender for Office 365.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="78f48-136">原則設定</span><span class="sxs-lookup"><span data-stu-id="78f48-136">Policy settings</span></span>

<span data-ttu-id="78f48-137">下列原則設定可用於 EOP 和 Microsoft Defender for Office 365 中的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="78f48-137">The following policy settings are available in anti-phishing policies in EOP and Microsoft Defender for Office 365:</span></span>

- <span data-ttu-id="78f48-138">**名稱**：您無法重新命名預設的反網路釣魚原則，但您可以命名和重新命名您建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="78f48-138">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="78f48-139">**描述** 您無法將描述新增至預設的反網路釣魚原則，但您可以新增及變更所建立之自訂原則的描述。</span><span class="sxs-lookup"><span data-stu-id="78f48-139">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="78f48-140">**適用于**：識別反網路釣魚原則套用的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-140">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="78f48-141">此值是自訂原則中的必要條件，在預設原則中不可使用 (預設原則會套用至所有收件者) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-141">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="78f48-142">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="78f48-142">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="78f48-143">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="78f48-143">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="78f48-144">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="78f48-144">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="78f48-145">**收件** 者：一或多個信箱、郵件使用者或您組織中的郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="78f48-145">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="78f48-146">**收件者隸屬** 于組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="78f48-146">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="78f48-147">**收件者網域是**： Microsoft 365 中的一或多個已設定公認的網域。</span><span class="sxs-lookup"><span data-stu-id="78f48-147">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="78f48-148">例外狀況 **除外**：規則的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="78f48-148">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="78f48-149">設定和行為完全像是條件：</span><span class="sxs-lookup"><span data-stu-id="78f48-149">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="78f48-150">**收件者為**</span><span class="sxs-lookup"><span data-stu-id="78f48-150">**Recipient is**</span></span>
    - <span data-ttu-id="78f48-151">**收件者是的成員**</span><span class="sxs-lookup"><span data-stu-id="78f48-151">**Recipient is a member of**</span></span>
    - <span data-ttu-id="78f48-152">**收件者網域是**</span><span class="sxs-lookup"><span data-stu-id="78f48-152">**The recipient domain is**</span></span>

  > [!NOTE]
  > <span data-ttu-id="78f48-153">在自訂的反網路釣魚原則中，需要套用 **to** 設定來識別 <u>原則所套用</u>**的郵件收** 件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-153">The **Applied to** setting is required in custom anti-phishing policies to identify the message **recipients** <u>that the policy applies to</u>.</span></span> <span data-ttu-id="78f48-154">Microsoft Defender for Office 365 中的反網路釣魚原則也會有 [類比設定](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) ，您可以在其中指定個別寄件者電子郵件地址或寄件者網域，以在本主題稍後所述 <u>的方式接收模擬保護</u> 。</span><span class="sxs-lookup"><span data-stu-id="78f48-154">Anti-phishing policies in Microsoft Defender for Office 365 also have [impersonation settings](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) where you can specify individual sender email addresses or sender domains <u>that will receive impersonation protection</u> as described later in this topic.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="78f48-155">欺騙設定</span><span class="sxs-lookup"><span data-stu-id="78f48-155">Spoof settings</span></span>

<span data-ttu-id="78f48-156">哄騙是指電子郵件中的寄件者位址 (電子郵件客戶程式中所顯示的寄件者位址) 不會符合電子郵件來源的網域。</span><span class="sxs-lookup"><span data-stu-id="78f48-156">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="78f48-157">如需有關欺騙的詳細資訊，請參閱 [Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="78f48-157">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="78f48-158">下列欺騙設定可用於 EOP 和 Microsoft Defender for Office 365 中的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="78f48-158">The following spoof settings are available in anti-phishing policies in EOP and Microsoft Defender for Office 365:</span></span>

- <span data-ttu-id="78f48-159">**反欺騙保護**：啟用或停用反欺詐防護。</span><span class="sxs-lookup"><span data-stu-id="78f48-159">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="78f48-160">建議您讓它保留啟用狀態。</span><span class="sxs-lookup"><span data-stu-id="78f48-160">We recommend that you leave it enabled.</span></span> <span data-ttu-id="78f48-161">您可以使用 **哄騙智慧原則** 來允許或封鎖特定的欺騙內部和外部寄件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-161">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="78f48-162">如需詳細資訊，請參閱[在 Microsoft 365 中設定詐騙情報](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="78f48-162">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="78f48-163">預設的反網路釣魚原則和您建立的任何新自訂反網路釣魚原則中，預設會啟用反欺騙保護。</span><span class="sxs-lookup"><span data-stu-id="78f48-163">Anti-spoofing protection is enabled by default in the default anti-phishing policy and in any new custom anti-phishing policies that you create.</span></span>
  >
  > - <span data-ttu-id="78f48-164">如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="78f48-164">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="78f48-165">如需相關指示，請參閱 [在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="78f48-165">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="78f48-166">針對來自封鎖欺騙寄件者的郵件，您也可以指定要對郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="78f48-166">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="78f48-167">**將郵件移至 [垃圾郵件] 資料夾**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="78f48-167">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="78f48-168">郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="78f48-168">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="78f48-169">在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-169">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="78f48-170">如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="78f48-170">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="78f48-171">**隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-171">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="78f48-172">如需隔離的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="78f48-172">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="78f48-173">Microsoft 365 中的隔離</span><span class="sxs-lookup"><span data-stu-id="78f48-173">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="78f48-174">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="78f48-174">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="78f48-175">以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="78f48-175">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="78f48-176">**未經驗證的寄件者**：請參閱下一節中的資訊。</span><span class="sxs-lookup"><span data-stu-id="78f48-176">**Unauthenticated Sender**: See the information in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="78f48-177">未驗證寄件者</span><span class="sxs-lookup"><span data-stu-id="78f48-177">Unauthenticated Sender</span></span>

<span data-ttu-id="78f48-178">未經驗證的寄件者識別碼是 EOP 和 Microsoft Defender for Office 365 中可用的 [欺騙設定](#spoof-settings) 的一部分，如前一節所述。</span><span class="sxs-lookup"><span data-stu-id="78f48-178">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies in EOP and Microsoft Defender for Office 365 as described in the previous section.</span></span>

<span data-ttu-id="78f48-179">**未經驗證的寄件者** 設定可啟用或停用 Outlook 中未經驗證的寄件者識別</span><span class="sxs-lookup"><span data-stu-id="78f48-179">The **Unauthenticated Sender** setting enables or disables unauthenticated sender identification in Outlook.</span></span> <span data-ttu-id="78f48-180">特別是：</span><span class="sxs-lookup"><span data-stu-id="78f48-180">Specifically:</span></span>

- <span data-ttu-id="78f48-181">當郵件未通過 SPF 或 DKIM 檢查 **，且** 郵件未通過 DMARC 或 [複合驗證](email-validation-and-authentication.md#composite-authentication)時，就會在寄件者的相片中加入一個問號 (？ ) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-181">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="78f48-182">停用未經驗證的寄件者識別碼，可防止問號加入寄件者的相片。</span><span class="sxs-lookup"><span data-stu-id="78f48-182">Disabling unauthenticated sender identification prevents the question mark from being added to the sender's photo.</span></span>

- <span data-ttu-id="78f48-183">如果 [寄件者] 位址中的網域 (電子郵件) 客戶程式中顯示的郵件寄件者不同于 DKIM 簽章中的網域或 **郵件** 的 [寄件者] 位址中的網域，則會新增 via 標籤 <u> (chris@contoso.com 透過</u>michelle@fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-183">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="78f48-184">如需這些位址的詳細資訊，請參閱 [電子郵件標準的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。</span><span class="sxs-lookup"><span data-stu-id="78f48-184">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

  <span data-ttu-id="78f48-185">停用未經驗證的寄件者識別碼時，如果 [寄件者] 位址中的網域與 DKIM 簽章中的網域不同或郵件的 [寄件者] 位址不同，就不會防止加入標籤。</span><span class="sxs-lookup"><span data-stu-id="78f48-185">Disabling unauthenticated sender identification does not prevent the via tag from being added if the domain in the From address is different from the domain in the DKIM signature or the MAIL FROM address.</span></span>

<span data-ttu-id="78f48-186">若要防止問號或 via 標記新增至特定寄件者的郵件，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="78f48-186">To prevent the question mark or via tag from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="78f48-187">允許寄件者在欺騙智慧原則中哄騙。</span><span class="sxs-lookup"><span data-stu-id="78f48-187">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="78f48-188">當停用未經驗證的寄件者身分識別時，此巨集指令可防止來自寄件者的郵件顯示「透過」標記。</span><span class="sxs-lookup"><span data-stu-id="78f48-188">This action will prevent the via tag from appearing in messages from the sender when unauthenticated sender identification is disabled.</span></span> <span data-ttu-id="78f48-189">如需相關指示，請參閱 [Configure 哄騙情報 In Microsoft 365](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="78f48-189">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="78f48-190">設定寄件者網域的[電子郵件驗證](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。</span><span class="sxs-lookup"><span data-stu-id="78f48-190">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
  - <span data-ttu-id="78f48-191">針對寄件者相片中的問號，SPF 或 DKIM 最為重要。</span><span class="sxs-lookup"><span data-stu-id="78f48-191">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="78f48-192">在 [via] 標籤上，確認 DKIM 簽章中的網域，或 [ **郵件發件** 人位址相符 (] 或 [寄件者] 位址中) 網域的子域。</span><span class="sxs-lookup"><span data-stu-id="78f48-192">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="78f48-193">如需詳細資訊，請參閱 [在 Outlook.com 中識別可疑郵件和網頁上的 Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="78f48-193">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="78f48-194">Microsoft Defender for Office 365 中的反網路釣魚原則中的獨佔設定</span><span class="sxs-lookup"><span data-stu-id="78f48-194">Exclusive settings in anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="78f48-195">本節說明僅適用于 Office 365 的 Microsoft Defender 中的反網路釣魚原則中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="78f48-195">This section describes the policy settings that are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="78f48-196">Microsoft Defender for Office 365 中的預設反網路釣魚原則為所有收件者提供 [欺騙保護](set-up-anti-phishing-policies.md#spoof-settings) 和信箱智慧。</span><span class="sxs-lookup"><span data-stu-id="78f48-196">The default anti-phishing policy in Microsoft Defender for Office 365 provides [spoof protection](set-up-anti-phishing-policies.md#spoof-settings) and mailbox intelligence for all recipients.</span></span> <span data-ttu-id="78f48-197">不過，預設原則中並未設定或啟用其他可用的模擬 [保護](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高級設定](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-197">However, the other available [impersonation protection](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) features and [advanced settings](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are not configured or enabled in the default policy.</span></span> <span data-ttu-id="78f48-198">若要啟用所有保護功能，請修改預設的反網路釣魚原則，或建立其他的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="78f48-198">To enable all protection features, modify the default anti-phishing policy or create additional anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="78f48-199">Microsoft Defender for Office 365 中的反網路釣魚原則中的類比設定</span><span class="sxs-lookup"><span data-stu-id="78f48-199">Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="78f48-200">模仿是指寄件者或寄件者的電子郵件網域與實際寄件者或網域類似的位置：</span><span class="sxs-lookup"><span data-stu-id="78f48-200">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="78f48-201">contoso.com 這個網域的網域模擬例子是 ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="78f48-201">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="78f48-202">使用者 michelle@contoso.com 的模擬例子是 michele@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="78f48-202">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="78f48-203">另外，模擬網域可能被視為合法 (註冊網域、設定的電子郵件驗證記錄等)，惟其目的是欺騙收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-203">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="78f48-204">下列模擬設定僅適用于 Office 365 的 Microsoft Defender 中的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="78f48-204">The following impersonation settings are only available in anti-phishing policies in Microsoft Defender for Office 365:</span></span>

- <span data-ttu-id="78f48-205">**要保護的使用者**：防止將指定的內部或外部電子郵件地址類比 **為郵件寄件者**。</span><span class="sxs-lookup"><span data-stu-id="78f48-205">**Users to protect**: Prevents the specified internal or external email addresses from being impersonated **as message senders**.</span></span> <span data-ttu-id="78f48-206">例如，您會收到來自公司副總裁的電子郵件訊息，要求您傳送給她的部分內部公司資訊。</span><span class="sxs-lookup"><span data-stu-id="78f48-206">For example, you receive an email message from the Vice President of your company asking you to send her some internal company information.</span></span> <span data-ttu-id="78f48-207">您會這麼做嗎？</span><span class="sxs-lookup"><span data-stu-id="78f48-207">Would you do it?</span></span> <span data-ttu-id="78f48-208">許多人員會在不想要的情況下傳送回復。</span><span class="sxs-lookup"><span data-stu-id="78f48-208">Many people would send the reply without thinking.</span></span>

  <span data-ttu-id="78f48-209">您可以使用受保護的使用者加入內部和外部寄件者電子郵件地址，以防止模擬。</span><span class="sxs-lookup"><span data-stu-id="78f48-209">You can use protected users to add internal and external sender email addresses to protect from impersonation.</span></span> <span data-ttu-id="78f48-210">從使用者模擬中保護的 **寄件者** 清單，與原則所 **套用的收** 件者清單不同， (預設原則的所有收件者;在 [[原則設定](#policy-settings)] 區段的 [套用 **至**] 設定中設定的特定收件者) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-210">This list of **senders** that are protected from user impersonation is different from the list of **recipients** that the policy applies to (all recipients for the default policy; specific recipients as configured in the **Applied to** setting in the [Policy settings](#policy-settings) section).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="78f48-211">在每個反網路釣魚原則中，您可以指定最多60個受保護的使用者 (寄件者的電子郵件地址) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-211">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="78f48-212">您無法在多個原則中指定同一個受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="78f48-212">You can't specify the same protected user in multiple policies.</span></span>
  >
  > - <span data-ttu-id="78f48-213">如果寄件者和收件者先前透過電子郵件進行通訊，使用者模擬保護便無法運作。</span><span class="sxs-lookup"><span data-stu-id="78f48-213">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="78f48-214">如果寄件者和收件者永不透過電子郵件進行通訊，郵件會被識別為類比嘗試。</span><span class="sxs-lookup"><span data-stu-id="78f48-214">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

  <span data-ttu-id="78f48-215">根據預設，不會將寄件者電子郵件地址設定為 **要保護的使用者** 類比保護。</span><span class="sxs-lookup"><span data-stu-id="78f48-215">By default, no sender email addresses are configured for impersonation protection in **Users to protect**.</span></span> <span data-ttu-id="78f48-216">因此，根據預設，在 [預設原則] 或 [自訂原則] 中，模擬保護不會涵蓋任何寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="78f48-216">Therefore, by default, no sender email addresses are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="78f48-217">當您將內部或外部電子郵件地址新增至 **要保護的使用者** 清單時，來自這些 **寄件者** 的郵件會受到模仿保護檢查的制約。</span><span class="sxs-lookup"><span data-stu-id="78f48-217">When you add internal or external email addresses to the **Users to protect** list, messages from those **senders** are subject to impersonation protection checks.</span></span> <span data-ttu-id="78f48-218">**如果** 郵件傳送給收件者的郵件是套用至預設原則的所有 **收件** 者，則會檢查郵件，以進行模擬 (;**適用于** 自訂原則) 中的收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-218">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="78f48-219">如果在寄件者的電子郵件地址中偵測到模擬，使用者的類比保護動作會套用至郵件 (如何處理該郵件、是否顯示類比的使用者安全提示等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-219">If impersonation is detected in the sender's email address, the impersonation protections actions for users are applied to the message (what to do with the message, whether to show impersonated users safety tips, etc.).</span></span>

- <span data-ttu-id="78f48-220">**要保護的網域**：防止 **在郵件寄件者的網域中** 類比指定的網域。</span><span class="sxs-lookup"><span data-stu-id="78f48-220">**Domains to protect**: Prevents the specified domains from being impersonated **in the message sender's domain**.</span></span> <span data-ttu-id="78f48-221">例如，您擁有的所有網域 ([公認的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或特定網域 (您擁有的網域或夥伴網域) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-221">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="78f48-222">保護自模擬的 **寄件者網域** 清單不同于原則所 **套用的收** 件者清單，以 (預設原則的所有收件者;在 [[原則設定](#policy-settings)] 區段的 [套用 **至**] 設定中設定的特定收件者) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-222">This list of **sender domains** that are protected from impersonation is different from the list of **recipients** that the policy applies to (all recipients for the default policy; specific recipients as configured in the **Applied to** setting in the [Policy settings](#policy-settings) section).</span></span>

  > [!NOTE]
  > <span data-ttu-id="78f48-223">您可以在所有反網路釣魚原則中定義的受保護網域數目上限為50。</span><span class="sxs-lookup"><span data-stu-id="78f48-223">The maximum number of protected domains that you can define in all anti-phishing policies is 50.</span></span>

  <span data-ttu-id="78f48-224">根據預設，不會將寄件者網域設定為 **要保護的網域** 中的類比保護。</span><span class="sxs-lookup"><span data-stu-id="78f48-224">By default, no sender domains are configured for impersonation protection in **Domains to protect**.</span></span> <span data-ttu-id="78f48-225">因此，根據預設，在 [預設原則] 或 [自訂原則] 中，模擬保護不會涵蓋任何寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="78f48-225">Therefore, by default, no sender domains are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="78f48-226">當您將網域新增至 **要保護的網域** 清單時，來自 **這些網域中寄件者** 的郵件會受到模擬保護檢查的制約。</span><span class="sxs-lookup"><span data-stu-id="78f48-226">When you add domains to the **Domains to protect** list, messages from **senders in those domains** are subject to impersonation protection checks.</span></span> <span data-ttu-id="78f48-227">**如果** 郵件傳送給收件者的郵件是套用至預設原則的所有 **收件** 者，則會檢查郵件，以進行模擬 (;**適用于** 自訂原則) 中的收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-227">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="78f48-228">如果在寄件者的網域中偵測到模擬，就會將網域的模仿保護動作套用至郵件 (應如何處理該郵件、是否顯示類比的使用者安全提示等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-228">If impersonation is detected in the sender's domain, the impersonation protection actions for domains are applied to the message (what to do with the message, whether to show impersonated users safety tips, etc.).</span></span>

- <span data-ttu-id="78f48-229">**受保護的使用者或網域的動作**：選擇要針對輸入郵件採取的動作，該郵件包含對原則中受保護的使用者與受保護的網域的模仿嘗試。</span><span class="sxs-lookup"><span data-stu-id="78f48-229">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="78f48-230">您可以指定不同的使用者模擬，以類比受保護的使用者與模擬受保護的網域：</span><span class="sxs-lookup"><span data-stu-id="78f48-230">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="78f48-231">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="78f48-231">**Don't apply any action**</span></span>

  - <span data-ttu-id="78f48-232">將 **郵件重新導向至其他電子郵件地址**：將郵件傳送給指定的收件者，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-232">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="78f48-233">**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="78f48-233">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="78f48-234">在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。</span><span class="sxs-lookup"><span data-stu-id="78f48-234">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="78f48-235">如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="78f48-235">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="78f48-236">**隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-236">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="78f48-237">如需隔離的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="78f48-237">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="78f48-238">Microsoft 365 中的隔離</span><span class="sxs-lookup"><span data-stu-id="78f48-238">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="78f48-239">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="78f48-239">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="78f48-240">以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="78f48-240">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="78f48-241">**傳遞郵件並將其他位址新增至 Bcc 行**：將郵件傳遞給預定的收件者，並以無訊息方式將郵件傳遞給指定的收件者。</span><span class="sxs-lookup"><span data-stu-id="78f48-241">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="78f48-242">**傳遞郵件之前將其刪除**：無訊息地刪除整個郵件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="78f48-242">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="78f48-243">**安全性秘訣**：啟用或停用下列會顯示失敗之模擬檢查的模仿安全性秘訣：</span><span class="sxs-lookup"><span data-stu-id="78f48-243">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="78f48-244">**類比使用者**：寄件者位址包含受保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="78f48-244">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="78f48-245">**類比網域**：寄件者位址包含受保護的網域。</span><span class="sxs-lookup"><span data-stu-id="78f48-245">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="78f48-246">不 **尋常的字元**： From 位址包含不尋常的字元集 (例如數學符號和文字，或是混合的大小寫字母) 在受保護的寄件者或網域中。</span><span class="sxs-lookup"><span data-stu-id="78f48-246">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="78f48-247">即使已關閉模擬安全性秘訣，也 **建議** 您使用郵件流程規則 (也稱為傳輸規則) ，將名為 **X-MS-EnableFirstContactSafetyTip** 的郵件頭新增至郵件。</span><span class="sxs-lookup"><span data-stu-id="78f48-247">Even when the impersonation safety tips are turned off, **it is recommended** you use a mail flow rule (also known as a transport rule) to add a message header named **X-MS-Exchange-EnableFirstContactSafetyTip** to messages.</span></span> <span data-ttu-id="78f48-248">當收件者第一次從寄件者取得電子郵件時，系統會顯示特定的安全性秘訣，以通知收件者他們經常無法從寄件者取得電子郵件。</span><span class="sxs-lookup"><span data-stu-id="78f48-248">Specific safety tips will be displayed notifying recipients that they often don't get email from the sender or in cases when the recipient gets an email for the first time from the sender.</span></span>
>:::image type="content" source="../../media/Urja_FirstContactEmail-Set-us-anti-phish-pol-safetyTip-ImpersonationProtection-MultipleRecipients.png" alt-text="具有多個收件者之類比保護的安全性秘訣文字。":::
<p>

- <span data-ttu-id="78f48-250">**信箱智慧**：啟用或停用使用者的智慧 (AI) ，可決定使用者的電子郵件模式與經常的連絡人。</span><span class="sxs-lookup"><span data-stu-id="78f48-250">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="78f48-251">此設定可協助 AI 區分合法和欺騙的電子郵件與這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="78f48-251">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="78f48-252">信箱智慧只適用于 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="78f48-252">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="78f48-253">**信箱智慧** 型模擬保護：根據每個使用者的個人寄件者地圖，啟用或停用增強型類比結果。</span><span class="sxs-lookup"><span data-stu-id="78f48-253">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="78f48-254">這種智慧可讓 Microsoft 365 自訂使用者模擬偵測，並更好地處理誤報。</span><span class="sxs-lookup"><span data-stu-id="78f48-254">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="78f48-255">偵測到使用者模擬時，您可以定義要對郵件採取的特定動作：</span><span class="sxs-lookup"><span data-stu-id="78f48-255">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="78f48-256">**不要套用任何動作**</span><span class="sxs-lookup"><span data-stu-id="78f48-256">**Don't apply any action**</span></span>
  - <span data-ttu-id="78f48-257">**將郵件重新導向至其他電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="78f48-257">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="78f48-258">**將郵件移至 [垃圾郵件] 資料夾**</span><span class="sxs-lookup"><span data-stu-id="78f48-258">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="78f48-259">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="78f48-259">**Quarantine the message**</span></span>
  - <span data-ttu-id="78f48-260">**傳遞郵件並將其他位址新增至 Bcc 行**</span><span class="sxs-lookup"><span data-stu-id="78f48-260">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="78f48-261">**在傳遞郵件之前將其刪除**</span><span class="sxs-lookup"><span data-stu-id="78f48-261">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="78f48-262">**受信任的寄件者和網域**：模仿保護設定的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="78f48-262">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="78f48-263">來自指定寄件者和寄件者網域的郵件，永遠不會分類為以模仿為模擬的受原則攻擊。</span><span class="sxs-lookup"><span data-stu-id="78f48-263">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="78f48-264">換句話說，受保護寄件者、受保護的網域或信箱智慧保護的動作不會套用到這些受信任的寄件者或寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="78f48-264">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="78f48-265">這兩個清單的上限大約是1000個專案。</span><span class="sxs-lookup"><span data-stu-id="78f48-265">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="78f48-266">Microsoft Defender for Office 365 中的反網路釣魚原則中的高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="78f48-266">Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="78f48-267">下列高級網路釣魚閾值只適用于 Microsoft Defender for Office 365 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="78f48-267">The following advanced phishing thresholds are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="78f48-268">這些臨界值可控制將機器學習模型套用至郵件以判定網路釣魚是否判定的靈敏度：</span><span class="sxs-lookup"><span data-stu-id="78f48-268">These thresholds control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="78f48-269">**1-Standard**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="78f48-269">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="78f48-270">針對郵件採取的動作嚴重性，取決於郵件為網路釣魚 (低、中、高或非常高的信賴度) 的置信度。</span><span class="sxs-lookup"><span data-stu-id="78f48-270">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="78f48-271">例如，以非常高的信賴程度識別為網路釣魚的郵件會套用最嚴重的動作，而識別為低信任程度之網路釣魚的郵件，則會套用較低的嚴重動作。</span><span class="sxs-lookup"><span data-stu-id="78f48-271">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="78f48-272">**2-嚴格**：識別為具有高可信度之網路釣魚的郵件，就像是以非常高的信賴程度加以識別一樣加以對待。</span><span class="sxs-lookup"><span data-stu-id="78f48-272">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="78f48-273">**3-更嚴格**：辨識為具有中等或高置信度之網路釣魚的郵件，視為以極高的信賴程度加以識別。</span><span class="sxs-lookup"><span data-stu-id="78f48-273">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="78f48-274">**4-最主動**：以低、中或高置信度識別為網路釣魚的郵件，視為以極高的置信度識別。</span><span class="sxs-lookup"><span data-stu-id="78f48-274">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="78f48-275">誤報的機率 (，標記為壞) 會隨著您增加此設定而增加。</span><span class="sxs-lookup"><span data-stu-id="78f48-275">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="78f48-276">如需建議設定的詳細資訊，請參閱 [Microsoft Defender For Office 365 設定中的反網路釣魚原則](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="78f48-276">For information about the recommended settings, see [anti-phishing policy in Microsoft Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>
