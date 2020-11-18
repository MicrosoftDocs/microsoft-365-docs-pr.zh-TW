---
title: 反詐騙保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: 系統管理員可以了解 Exchange Online Protection (EOP) 中提供的反詐騙功能，可協助緩解來自詐騙寄件者和網域的網路釣魚攻擊。
ms.openlocfilehash: 57d6dc8d9c1935578db15abdbb3e17e72bb64257
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130826"
---
# <a name="anti-spoofing-protection-in-eop"></a><span data-ttu-id="2a663-103">EOP 中的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="2a663-103">Anti-spoofing protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2a663-104">在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，EOP 所包含的功能可協助保護貴組織抵禦詐騙 (偽造) 寄件者。</span><span class="sxs-lookup"><span data-stu-id="2a663-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>

<span data-ttu-id="2a663-105">為保護使用者，Microsoft 嚴正看待網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="2a663-105">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="2a663-106">詐騙是攻擊者所使用的常見技巧。</span><span class="sxs-lookup"><span data-stu-id="2a663-106">Spoofing is a common technique that's used by attackers.</span></span> <span data-ttu-id="2a663-107">**詐騙訊息是來自實際來源以外的某人或某個位置**。</span><span class="sxs-lookup"><span data-stu-id="2a663-107">**Spoofed messages appear to originate from someone or somewhere other than the actual source**.</span></span> <span data-ttu-id="2a663-108">這是設計來取得使用者認證的網路釣魚攻擊的慣用伎倆。</span><span class="sxs-lookup"><span data-stu-id="2a663-108">This technique is often used in phishing campaigns that are designed to obtain user credentials.</span></span> <span data-ttu-id="2a663-109">EOP 中的反詐騙技術專門檢查郵件內文中的 [寄件者] 標頭(用於顯示電子郵件用戶端中的郵件寄件者)。</span><span class="sxs-lookup"><span data-stu-id="2a663-109">The anti-spoofing technology in EOP specifically examines forgery of the From header in the message body (used to display the message sender in email clients).</span></span> <span data-ttu-id="2a663-110">當 EOP 高度認為 [寄件者] 標頭為偽造時，會將該郵件視為詐騙。</span><span class="sxs-lookup"><span data-stu-id="2a663-110">When EOP has high confidence that the From header is forged, the message is identified as spoofed.</span></span>

<span data-ttu-id="2a663-111">EOP 中提供下列反詐騙技術：</span><span class="sxs-lookup"><span data-stu-id="2a663-111">The following anti-spoofing technologies are available in EOP:</span></span>

- <span data-ttu-id="2a663-112">**詐騙情報**：檢閱來自內部和外部網域中寄件者的詐騙郵件，並允許或封鎖那些寄件者。</span><span class="sxs-lookup"><span data-stu-id="2a663-112">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="2a663-113">如需詳細資訊，請參閱[在 Microsoft 365 中設定詐騙情報](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-113">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="2a663-114">**防網路釣魚原則**：在 EOP 中，防網路釣魚原則可讓您開啟或關閉詐騙情報、開啟或關閉 Outlook 中未經驗證的寄件者識別碼，並針對已封鎖詐騙寄件者指定動作 (移至 [垃圾郵件] 資料夾或隔離)。</span><span class="sxs-lookup"><span data-stu-id="2a663-114">**Anti-phishing policies**: In EOP, anti-phishing policies allow you to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to the Junk Email folder or quarantine).</span></span> <span data-ttu-id="2a663-115">適用於 Office 365 的 Microsoft Defender 中提供的進階防網路釣魚原則，也包含防模擬設定 (受保護的寄件者和網域)、信箱智慧設定，以及可調整的進階網路釣魚臨界值。</span><span class="sxs-lookup"><span data-stu-id="2a663-115">Advanced anti-phishing policies that are available in Microsoft Defender for Office 365 also contain anti-impersonation settings (protected senders and domains), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="2a663-116">如需詳細資訊，請參閱 [Microsoft 365 中的防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-116">For more information, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="2a663-117">**電子郵件驗證**：任何反詐騙工作的整合部分就是在 DNS 中使用 SPF、DKIM 和 DMARC 記錄的電子郵件驗證 (Authentication) (也稱為電子郵件驗證 (Validation))。</span><span class="sxs-lookup"><span data-stu-id="2a663-117">**Email authentication**: An integral part of any anti-spoofing effort is the use of email authentication (also known as email validation) by SPF, DKIM, and DMARC records in DNS.</span></span> <span data-ttu-id="2a663-118">您可以為網域設定這些記錄，這樣目的地電子郵件系統就能檢查您網域中寄件者所聲稱郵件的有效性。</span><span class="sxs-lookup"><span data-stu-id="2a663-118">You can configure these records for your domains so destination email systems can check the validity of messages that claim to be from senders in your domains.</span></span> <span data-ttu-id="2a663-119">針對內送郵件，Microsoft 365 需要寄件者網域的電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="2a663-119">For inbound messages, Microsoft 365 requires email authentication for sender domains.</span></span> <span data-ttu-id="2a663-120">如需詳細資訊，請參閱 [Microsoft 365 中的電子郵件驗證](email-validation-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-120">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

<span data-ttu-id="2a663-121">從 2018 年 10 月開始，EOP 中提供反詐騙防護功能。</span><span class="sxs-lookup"><span data-stu-id="2a663-121">As of October 2018, anti-spoofing protection is available in EOP.</span></span>

<span data-ttu-id="2a663-122">EOP 會分析並封鎖使用標準電子郵件驗證方法與寄件者信譽技術組合無法驗證的郵件。</span><span class="sxs-lookup"><span data-stu-id="2a663-122">EOP analyzes and blocks messages that can't be authenticated by the combination of standard email authentication methods and sender reputation techniques.</span></span>

![EOP 反詐騙檢查](../../media/eop-anti-spoofing-protection.png)

## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="2a663-124">網路釣魚攻擊中的詐騙方式</span><span class="sxs-lookup"><span data-stu-id="2a663-124">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="2a663-125">詐騙郵件對使用者有下列負面影響：</span><span class="sxs-lookup"><span data-stu-id="2a663-125">Spoofing messages have the following negative implications for users:</span></span>

- <span data-ttu-id="2a663-126">**詐騙郵件會欺騙使用者**：詐騙郵件會誘騙收件者按下連結並給予其憑證，下載惡意程式碼或回覆具有敏感內容的郵件 (稱為商務電子郵件入侵或 BEC)。</span><span class="sxs-lookup"><span data-stu-id="2a663-126">**Spoofed messages deceive users**: A spoofed message might trick the recipient into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (known as a business email compromise or BEC).</span></span>

  <span data-ttu-id="2a663-127">以下郵件是使用詐騙寄件者 msoutlook94@service.outlook.com 的網路釣魚範例：</span><span class="sxs-lookup"><span data-stu-id="2a663-127">The following message is an example of phishing that uses the spoofed sender msoutlook94@service.outlook.com:</span></span>

  ![冒充 service.outlook.com 的網路釣魚郵件](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  <span data-ttu-id="2a663-129">這封郵件並非來自 service.outlook.com，而是攻擊者偽造 [寄件者] 標頭欄位，使其看起來像是來自該處。</span><span class="sxs-lookup"><span data-stu-id="2a663-129">This message didn't come from service.outlook.com, but the attacker spoofed the **From** header field to make it look like it did.</span></span> <span data-ttu-id="2a663-130">這是誘騙收件者按下 **變更密碼** 連結並給予其憑證的嘗試。</span><span class="sxs-lookup"><span data-stu-id="2a663-130">This was an attempt to trick the recipient into clicking the **change your password** link and giving up their credentials.</span></span>

  <span data-ttu-id="2a663-131">以下郵件是使用詐騙電子郵件網域 contoso.com 的 BEC 範例：</span><span class="sxs-lookup"><span data-stu-id="2a663-131">The following message is an example of BEC that uses the spoofed email domain contoso.com:</span></span>

  ![網路釣魚郵件 - 商務電子郵件入侵](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  <span data-ttu-id="2a663-133">郵件看起來合法，但寄件者卻是偽造的。</span><span class="sxs-lookup"><span data-stu-id="2a663-133">The message looks legitimate, but the sender is spoofed.</span></span>

- <span data-ttu-id="2a663-134">**使用者會對真實郵件與假冒郵件產生混淆**：即使是已經知道網路釣魚的使用者也可能難以看出真實郵件與詐騙郵件之間的差異。</span><span class="sxs-lookup"><span data-stu-id="2a663-134">**Users confuse real messages for fake ones**: Even users who know about phishing might have difficulty seeing the differences between real messages and spoofed messages.</span></span>

  <span data-ttu-id="2a663-135">以下郵件是來自 Microsoft 安全性帳戶真實密碼重設郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="2a663-135">The following message is an example of a real password reset message from the Microsoft Security account:</span></span>

  ![Microsoft 合法密碼重設](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  <span data-ttu-id="2a663-137">這封郵件確實是來自 Microsoft，但使用者認為是可疑的。</span><span class="sxs-lookup"><span data-stu-id="2a663-137">The message really did come from Microsoft, but users have been conditioned to be suspicious.</span></span> <span data-ttu-id="2a663-138">因為分辨真實密碼重設郵件與假冒郵件有其難度，使用者會略過這些郵件、將它們回報為垃圾郵件或在不應該的情況下，將這些郵件當作網路釣魚回報給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="2a663-138">Because it's difficult to the difference between a real password reset message and a fake one, users might ignore the message, report it as spam, or unnecessarily report the message to Microsoft as phishing.</span></span>

## <a name="different-types-of-spoofing"></a><span data-ttu-id="2a663-139">不同類型的詐騙</span><span class="sxs-lookup"><span data-stu-id="2a663-139">Different types of spoofing</span></span>

<span data-ttu-id="2a663-140">Microsoft 將詐騙郵件區分為兩種類型：</span><span class="sxs-lookup"><span data-stu-id="2a663-140">Microsoft differentiates between two different types of spoofed messages:</span></span>

- <span data-ttu-id="2a663-141">**組織內部詐騙**：也稱為 _自我_ 詐騙。</span><span class="sxs-lookup"><span data-stu-id="2a663-141">**Intra-org spoofing**: Also known as _self-to-self_ spoofing.</span></span> <span data-ttu-id="2a663-142">例如：</span><span class="sxs-lookup"><span data-stu-id="2a663-142">For example:</span></span>

  - <span data-ttu-id="2a663-143">寄件者和收件者位於同一個網域：</span><span class="sxs-lookup"><span data-stu-id="2a663-143">The sender and recipient are in the same domain:</span></span>
    > <span data-ttu-id="2a663-144">寄件者：chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a663-144">From: chris@contoso.com</span></span> <br/> <span data-ttu-id="2a663-145">收件者：michelle@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a663-145">To: michelle@contoso.com</span></span>

  - <span data-ttu-id="2a663-146">寄件者和收件者位於同一個網域中的子網域：</span><span class="sxs-lookup"><span data-stu-id="2a663-146">The sender and the recipient are in subdomains of the same domain:</span></span>
    > <span data-ttu-id="2a663-147">寄件者：laura@marketing.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2a663-147">From: laura@marketing.fabrikam.com</span></span> <br/> <span data-ttu-id="2a663-148">收件者：julia@engineering.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2a663-148">To: julia@engineering.fabrikam.com</span></span>

  - <span data-ttu-id="2a663-149">寄件者和收件者位於隸屬相同組織的不同網域中 (也就是兩個網域都設定為相同組織中[公認的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) (部分機器翻譯))：</span><span class="sxs-lookup"><span data-stu-id="2a663-149">The sender and recipient are in different domains that belong to the same organization (that is, both domains are configured as [accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the same organization):</span></span>
    > <span data-ttu-id="2a663-150">寄件者: sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2a663-150">From: sender @ microsoft.com</span></span> <br/> <span data-ttu-id="2a663-151">收件者: recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="2a663-151">To: recipient @ bing.com</span></span>

    <span data-ttu-id="2a663-152">電子郵件地址中會使用空格，以避免垃圾郵件機器人收集。</span><span class="sxs-lookup"><span data-stu-id="2a663-152">Spaces are used in the email addresses to prevent spambot harvesting.</span></span>

  <span data-ttu-id="2a663-153">因為組織內部詐騙包含下列標頭值，因此郵件不會通過[複合驗證](email-validation-and-authentication.md#composite-authentication)：</span><span class="sxs-lookup"><span data-stu-id="2a663-153">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to intra-org spoofing contain the following header values:</span></span>

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - <span data-ttu-id="2a663-154">`reason=6xx` 表示組織內部詐騙。</span><span class="sxs-lookup"><span data-stu-id="2a663-154">`reason=6xx` indicates intra-org spoofing.</span></span>

  - <span data-ttu-id="2a663-155">SFTY 是郵件的安全層級。</span><span class="sxs-lookup"><span data-stu-id="2a663-155">SFTY is the safety level of the message.</span></span> <span data-ttu-id="2a663-156">9 表示網路釣魚，11 表示組織內部詐騙。</span><span class="sxs-lookup"><span data-stu-id="2a663-156">9 indicates phishing, .11 indicates intra-org spoofing.</span></span>

- <span data-ttu-id="2a663-157">**跨網域詐騙**：寄件者和收件者網域並不相同，且彼此之間沒有關係 (也稱為外部網域)。</span><span class="sxs-lookup"><span data-stu-id="2a663-157">**Cross-domain spoofing**: The sender and recipient domains are different, and have no relationship to each other (also known as external domains).</span></span> <span data-ttu-id="2a663-158">例如：</span><span class="sxs-lookup"><span data-stu-id="2a663-158">For example:</span></span>
    > <span data-ttu-id="2a663-159">寄件者：chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a663-159">From: chris@contoso.com</span></span> <br/> <span data-ttu-id="2a663-160">收件者：michelle@tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="2a663-160">To: michelle@tailspintoys.com</span></span>

  <span data-ttu-id="2a663-161">因為跨網域詐騙包含下列標頭值，因此郵件不會通過[複合驗證](email-validation-and-authentication.md#composite-authentication)：</span><span class="sxs-lookup"><span data-stu-id="2a663-161">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to cross-domain spoofing contain the following headers values:</span></span>

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - <span data-ttu-id="2a663-162">`reason=000` 表示郵件未通過明確電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="2a663-162">`reason=000` indicates the message failed explicit email authentication.</span></span> <span data-ttu-id="2a663-163">`reason=001` 值表示郵件未通過隱含電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="2a663-163">`reason=001` indicates the message failed implicit email authentication.</span></span>

  - <span data-ttu-id="2a663-164">SFTY 是郵件的安全層級。</span><span class="sxs-lookup"><span data-stu-id="2a663-164">SFTY is the safety level of the message.</span></span> <span data-ttu-id="2a663-165">9 表示網路釣魚，22 表示跨網域詐騙。</span><span class="sxs-lookup"><span data-stu-id="2a663-165">9 indicates phishing, .22 indicates cross-domain spoofing.</span></span>

<span data-ttu-id="2a663-166">如需詐騙相關類別和複合驗證 (compauth) 值的詳細資訊，請參閱 [Microsoft 365 的反垃圾郵件標頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-166">For more information about the Category and composite authentication (compauth) values that are related to spoofing, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="2a663-167">如需 DMARC 的詳細資訊，請參閱[在 Microsoft 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-167">For more information about DMARC, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="2a663-168">關於有多少郵件被標示為詐騙郵件的報告</span><span class="sxs-lookup"><span data-stu-id="2a663-168">Reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="2a663-169">EOP 組織可以在 [安全性與合規性中心] 的 [報告] 儀表板中使用 **詐騙偵測** 報告。</span><span class="sxs-lookup"><span data-stu-id="2a663-169">EOP organizations can use the **Spoof detections** report in the Reports dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="2a663-170">如需詳細資訊，請參閱[詐騙偵測報告](view-email-security-reports.md#spoof-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="2a663-170">For more information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

<span data-ttu-id="2a663-171">適用於 Office 365 的 Microsoft Defender 組織可以使用 [安全性與合規性中心] 中的 [威脅總管] 來檢視網路釣魚嘗試的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2a663-171">Microsoft Defender for Office 365 organization can use Threat Explorer in the Security & Compliance Center to view information about phishing attempts.</span></span> <span data-ttu-id="2a663-172">如需詳細資訊，請參閱 [Microsoft 365 威脅調查及回應](office-365-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-172">For more information, see [Microsoft 365 threat investigation and response](office-365-ti.md).</span></span>

## <a name="problems-with-anti-spoofing-protection"></a><span data-ttu-id="2a663-173">反詐騙保護的問題</span><span class="sxs-lookup"><span data-stu-id="2a663-173">Problems with anti-spoofing protection</span></span>

<span data-ttu-id="2a663-174">郵寄清單 (也稱為討論清單) 由於其轉寄及修改郵件的方式，已知有反詐騙問題。</span><span class="sxs-lookup"><span data-stu-id="2a663-174">Mailing lists (also known as discussion lists) are known to have problems with anti-spoofing due to the way they forward and modify messages.</span></span>

<span data-ttu-id="2a663-175">例如，Gabriela Laureano (glaureano@contoso.com) 對賞鳥有興趣，因此加入 birdwatchers@fabrikam.com 郵寄清單，並且將下列郵件傳送到清單：</span><span class="sxs-lookup"><span data-stu-id="2a663-175">For example, Gabriela Laureano (glaureano@contoso.com) is interested in bird watching, joins the mailing list birdwatchers@fabrikam.com, and sends the following message to the list:</span></span>

> <span data-ttu-id="2a663-176">**寄件者：**"Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="2a663-176">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br/> <span data-ttu-id="2a663-177">**收件者：** 賞鳥的討論清單\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="2a663-177">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br/> <span data-ttu-id="2a663-178">**主旨：** 本週雷尼爾山頂</span><span class="sxs-lookup"><span data-stu-id="2a663-178">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="2a663-179">觀賞藍鳥的絕佳景點</span><span class="sxs-lookup"><span data-stu-id="2a663-179">Rainier this week</span></span> <p> <span data-ttu-id="2a663-180">有人這週想要上雷尼爾山</span><span class="sxs-lookup"><span data-stu-id="2a663-180">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="2a663-181">賞景嗎？</span><span class="sxs-lookup"><span data-stu-id="2a663-181">Rainier?</span></span>

<span data-ttu-id="2a663-182">郵寄清單伺服器會接收郵件，修改其內容，並且對清單的成員重新播放。</span><span class="sxs-lookup"><span data-stu-id="2a663-182">The mailing list server receives the message, modifies its content, and replays it to the members of list.</span></span> <span data-ttu-id="2a663-183">重新播放的郵件具有相同的 [寄件者] 地址 (glaureano@contoso.com)，但是有標記新增至主旨行，頁尾新增至郵件底端。</span><span class="sxs-lookup"><span data-stu-id="2a663-183">The replayed message has the same From address (glaureano@contoso.com), but a tag is added to the subject line, and a footer is added to the bottom of the message.</span></span> <span data-ttu-id="2a663-184">這種類型的修改常見於郵寄清單中，且可能會導致詐騙的誤判。</span><span class="sxs-lookup"><span data-stu-id="2a663-184">This type of modification is common in mailing lists, and may result in false positives for spoofing.</span></span>

> <span data-ttu-id="2a663-185">**寄件者：**"Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="2a663-185">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br/> <span data-ttu-id="2a663-186">**收件者：** 賞鳥的討論清單\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="2a663-186">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br/> <span data-ttu-id="2a663-187">**主旨：**[賞鳥人士] 本週雷尼爾山頂</span><span class="sxs-lookup"><span data-stu-id="2a663-187">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="2a663-188">觀賞藍鳥的絕佳景點</span><span class="sxs-lookup"><span data-stu-id="2a663-188">Rainier this week</span></span> <p> <span data-ttu-id="2a663-189">有人這週想要上雷尼爾山</span><span class="sxs-lookup"><span data-stu-id="2a663-189">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="2a663-190">賞景嗎？</span><span class="sxs-lookup"><span data-stu-id="2a663-190">Rainier?</span></span> <p> <span data-ttu-id="2a663-191">此郵件已傳送給「賞鳥人士」討論清單。</span><span class="sxs-lookup"><span data-stu-id="2a663-191">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="2a663-192">您隨時可以取消訂閱。</span><span class="sxs-lookup"><span data-stu-id="2a663-192">You can unsubscribe at any time.</span></span>

<span data-ttu-id="2a663-193">為了協助郵寄清單郵件通過反詐騙檢查，請根據您是否控制郵寄清單來執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2a663-193">To help mailing list messages pass anti-spoofing checks, do following steps based on whether you control the mailing list:</span></span>

- <span data-ttu-id="2a663-194">貴組織擁有郵寄清單：</span><span class="sxs-lookup"><span data-stu-id="2a663-194">Your organization owns the mailing list:</span></span>

  - <span data-ttu-id="2a663-195">請查看 DMARC.org 上的常見問題集：[我操作郵寄清單，並想要與 DMARC 互相操作，該怎麼做？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)。</span><span class="sxs-lookup"><span data-stu-id="2a663-195">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).</span></span>

  - <span data-ttu-id="2a663-196">閱讀此部落格文章的指示：[郵寄清單操作人員與 DMARC 互相操作以避免失敗的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)。</span><span class="sxs-lookup"><span data-stu-id="2a663-196">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/).</span></span>

  - <span data-ttu-id="2a663-197">若考慮在郵寄清單伺服器上安裝更新以支援 ARC，請參閱 <http://arc-spec.org>。</span><span class="sxs-lookup"><span data-stu-id="2a663-197">Consider installing updates on your mailing list server to support ARC, see <http://arc-spec.org>.</span></span>

- <span data-ttu-id="2a663-198">貴組織未擁有郵寄清單：</span><span class="sxs-lookup"><span data-stu-id="2a663-198">Your organization doesn't own the mailing list:</span></span>

  - <span data-ttu-id="2a663-199">要求郵寄清單的維護人員為轉送郵寄清單的網域設定電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="2a663-199">Ask the maintainer of the mailing list to configure email authentication for the domain that the mailing list is relaying from.</span></span>

    <span data-ttu-id="2a663-200">當有夠多寄件者回覆網域擁有者，他們應該設定電子郵件驗證記錄時，就可促使他們採取動作。</span><span class="sxs-lookup"><span data-stu-id="2a663-200">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="2a663-201">雖然 Microsoft 也會與網域擁有者合作發佈所需的記錄，但是當個別使用者提出要求時，助益更大。</span><span class="sxs-lookup"><span data-stu-id="2a663-201">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

  - <span data-ttu-id="2a663-202">在電子郵件用戶端中建立收件匣規則，將郵件移動至收件匣。</span><span class="sxs-lookup"><span data-stu-id="2a663-202">Create inbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="2a663-203">您也可以要求系統管理員設定覆寫，如[使用詐騙情報來設定未經驗證電子郵件的允許寄件者](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email)中所討論。</span><span class="sxs-lookup"><span data-stu-id="2a663-203">You can also ask your admins to configure overrides as discussed in the [Use spoof intelligence to configure permitted senders of unauthenticated email](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email).</span></span>

  - <span data-ttu-id="2a663-204">向 Microsoft 365 建立支援票證，以建立郵寄清單的覆寫，將其視為合法。</span><span class="sxs-lookup"><span data-stu-id="2a663-204">Create a support ticket with Microsoft 365 to create an override for the mailing list to treat it as legitimate.</span></span> <span data-ttu-id="2a663-205">如需詳細資訊，請參閱[連絡商務產品的支援服務 - 系統管理說明](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-205">For more information, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="2a663-206">如果其他所有項目都失敗，您可以將郵件當作誤判向 Microsoft 報告。</span><span class="sxs-lookup"><span data-stu-id="2a663-206">If all else fails, you can report the message as a false positive to Microsoft.</span></span> <span data-ttu-id="2a663-207">如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="2a663-207">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="2a663-208">您也可以連絡您的系統管理員，請他們向 Microsoft 開立支援票證。</span><span class="sxs-lookup"><span data-stu-id="2a663-208">You may also contact your admin who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="2a663-209">Microsoft 工程小組會研究該郵件為何會被標示為詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="2a663-209">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

## <a name="considerations-for-anti-spoofing-protection"></a><span data-ttu-id="2a663-210">反詐騙保護的考量</span><span class="sxs-lookup"><span data-stu-id="2a663-210">Considerations for anti-spoofing protection</span></span>

<span data-ttu-id="2a663-211">如果您是目前傳送郵件至 Microsoft 365 的系統管理員，您必須確認您的電子郵件已正確驗證。</span><span class="sxs-lookup"><span data-stu-id="2a663-211">If you're an admin who currently sends messages to Microsoft 365, you need to ensure that your email is properly authenticated.</span></span> <span data-ttu-id="2a663-212">否則，可能會標示為垃圾郵件或網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="2a663-212">Otherwise, it might be marked as spam or phishing.</span></span> <span data-ttu-id="2a663-213">如需詳細資訊，請參閱[傳送未經驗證電子郵件的合法寄件者解決方案](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email)。</span><span class="sxs-lookup"><span data-stu-id="2a663-213">For more information, see [Solutions for legitimate senders who are sending unauthenticated email](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).</span></span>

<span data-ttu-id="2a663-214">個別使用者 (或系統管理員) 的安全寄件者清單中的寄件者，將會略過篩選堆疊部分，包括詐騙防護。</span><span class="sxs-lookup"><span data-stu-id="2a663-214">Senders in an individual user's (or admin's) Safe Senders list will bypass parts of the filtering stack, including spoof protection.</span></span> <span data-ttu-id="2a663-215">如需詳細資訊，請參閱 [Outlook 安全寄件者](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders)。</span><span class="sxs-lookup"><span data-stu-id="2a663-215">For more information, see [Outlook Safe Senders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).</span></span>

<span data-ttu-id="2a663-216">系統管理員應使用允許的寄件者清單或允許的網域清單來加以避免 (若可能)。</span><span class="sxs-lookup"><span data-stu-id="2a663-216">Admins should avoid (when possible) using allowed sender lists or allowed domain lists.</span></span> <span data-ttu-id="2a663-217">這些寄件者會略過所有垃圾郵件、詐騙和網路釣魚防護，以及寄件者驗證 (SPF、DKIM、DMARC)。</span><span class="sxs-lookup"><span data-stu-id="2a663-217">These senders bypass all spam, spoofing, and phishing protection, and also sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="2a663-218">如需詳細資訊，請參閱[使用允許的寄件者清單或允許的網域清單](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists)。</span><span class="sxs-lookup"><span data-stu-id="2a663-218">For more information, see [Use allowed sender lists or allowed domain lists](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).</span></span>
