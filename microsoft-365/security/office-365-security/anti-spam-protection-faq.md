---
title: 反垃圾郵件保護常見問題集
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: 本主題提供有關反垃圾郵件保護的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection (EOP) 客戶。
ms.openlocfilehash: 9be51b4967a558aec254262052d7c01446a7d643
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599870"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="f0b18-104">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="f0b18-104">Anti-spam protection FAQ</span></span>

<span data-ttu-id="f0b18-p102">本主題提供有關反垃圾郵件保護的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection (EOP) 客戶。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p102">This topic provides frequently asked questions and answers about anti-spam protection. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection (EOP) customers.</span></span>

> [!TIP]
> <span data-ttu-id="f0b18-107">如需有關安全寄件者清單與封鎖寄件者清單的問題與解答，請參閱[Exchange Online 安全寄件者和封鎖寄件者清單](safe-sender-and-blocked-sender-lists-faq.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-107">For questions and answers about safe sender and blocked sender lists, see [Safe sender and blocked sender lists in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).</span></span> <span data-ttu-id="f0b18-108">如需有關隔離區的問題與解答，請參閱[隔離常見問題集](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-108">For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>

 <span data-ttu-id="f0b18-109">**問：偵測到的垃圾郵件預設會受到怎麼樣的處理？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-109">**Q. By default, what happens to a spam-detected message?**</span></span>

<span data-ttu-id="f0b18-p104">答： **若為輸入郵件：** 大部分的垃圾郵件是由連線篩選根據寄件者 IP 位址予以刪除。然後服務就會檢查郵件的內容。依預設，依內容篩選出的垃圾郵件會傳送至收件者的 [垃圾郵件] 資料夾。您可以變更此動作。例如，您可以設定內容篩選原則，選擇將垃圾郵件訊息傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p104">A. **For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the sender. The service then inspects the contents of the message. By default, content-filtered spam is sent to the recipient's Junk Email folder. You can change this action. For example, you can choose to send spam messages to the quarantine instead by configuring the content filter policy.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0b18-116">針對 EOP 獨立客戶：為確保 [將郵件移至垃圾郵件資料夾]\*\*\*\* 動作能夠在內部部署信箱中運作，您必須在內部部署伺服器上設定兩項 Exchange 郵件流程規則 (也稱為傳輸規則)，以偵測由 EOP 新增的垃圾郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="f0b18-116">For EOP standalone customers: In order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="f0b18-117">如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-117">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

 <span data-ttu-id="f0b18-118">**若為輸出郵件：** 郵件已透過較高風險傳遞集區路由傳送或已退回並未傳遞，在此情況下，寄件者應該會收到傳遞狀態通知 (DSN) 郵件，從中得知此郵件無法傳遞。</span><span class="sxs-lookup"><span data-stu-id="f0b18-118">**For outbound messages:** The message is either routed through the higher risk delivery pool or is bounced and not delivered, in which case the sender should receive a delivery status notification (DSN) message telling them that the message couldn't be delivered.</span></span>

 <span data-ttu-id="f0b18-119">**問：什麼是零時差垃圾郵件變體以及服務處理的方式為何？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-119">**Q. What's a zero-day spam variant and how is it handled by the service?**</span></span>

<span data-ttu-id="f0b18-120">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-120">A.</span></span> <span data-ttu-id="f0b18-121">零時差垃圾郵件變體是第一代垃圾郵件變體，從前從未擷取或分析過的變體，因此垃圾郵件內容篩選器尚無任何可供偵測的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0b18-121">A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our spam content filters don't yet have any information available for detecting it.</span></span> <span data-ttu-id="f0b18-122">一旦零時差垃圾郵件樣本由垃圾郵件分析人員擷取和分析之後，如果符合垃圾郵件分類條件，則垃圾郵件內容篩選器將會更新以進行偵測，並且不再視為「零時差」。</span><span class="sxs-lookup"><span data-stu-id="f0b18-122">After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our spam content filters are updated to detect it, and it's no longer considered "zero-day."</span></span> <span data-ttu-id="f0b18-123">(**請注意：** 如果您收到一封電子郵件，可能是零時差垃圾郵件變體，為協助我們改進服務，請使用[向 Microsoft 提交垃圾郵件、非垃圾郵件及網路釣魚詐騙郵件進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md) (英文) 中所述的其中一種方法，將郵件提交給 Microsoft，以供分析。)</span><span class="sxs-lookup"><span data-stu-id="f0b18-123">( **Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)</span></span>

 <span data-ttu-id="f0b18-124">**問：我是否需要將此服務設定為提供反垃圾郵件保護？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-124">**Q. Do I need to configure the service to provide anti-spam protection?**</span></span>

<span data-ttu-id="f0b18-p107">答：在您註冊此服務並新增自己的網域後，此服務即會透過預設的反垃圾郵件原則對整個公司啟用垃圾郵件篩選功能。預設的原則已調整為無須進行任何額外設定 (除了針對 EOP 獨立版客戶提及的上述例外狀況)，即可保護您。如果您是系統管理員，您可以編輯預設的反垃圾郵件原則，使其確切符合貴組織的需求。若要提高精確性，您也可以建立自訂的內容篩選原則，並套用至組織中指定的使用者、群組或網域。自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p107">A. After you sign up for the service and add your domain, spam filtering is automatically enabled company-wide through the default anti-spam policies. The default policies are tuned to protect you without needing any additional configuration (aside from the exception noted above for EOP standalone customers). As an admin, you can edit the default anti-spam policies so that they're tailored to best meet the needs of your organization. For greater granularity, you can also create custom content filter policies and apply them to specified users, groups, or domains in your organization. Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>

<span data-ttu-id="f0b18-131">如需設定反垃圾郵件原則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="f0b18-131">For more about configuring your anti-spam policies, see the following topics:</span></span>

<span data-ttu-id="f0b18-132">[設定連線篩選原則](configure-the-connection-filter-policy.md) (英文)</span><span class="sxs-lookup"><span data-stu-id="f0b18-132">[Configure the connection filter policy](configure-the-connection-filter-policy.md)</span></span>

[<span data-ttu-id="f0b18-133">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="f0b18-133">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

<span data-ttu-id="f0b18-134">[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-134">[Configure the outbound spam policy](configure-the-outbound-spam-policy.md)</span></span>

 <span data-ttu-id="f0b18-135">**問：如果我對反垃圾郵件原則進行變更並儲存變更，這些變更經過多久才會生效？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-135">**Q. If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?**</span></span>

<span data-ttu-id="f0b18-p108">答：最多可能需要 1 小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p108">A. It may take up to 1 hour for the changes to take effect.</span></span>

 <span data-ttu-id="f0b18-138">**問：大量電子郵件篩選功能是否會自動啟用？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-138">**Q. Is bulk email filtering automatically enabled?**</span></span>

<span data-ttu-id="f0b18-139">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-139">A.</span></span> <span data-ttu-id="f0b18-140">根據預設，系統會為新客戶啟用 **大宗郵件**進階垃圾郵件篩選選項。</span><span class="sxs-lookup"><span data-stu-id="f0b18-140">By default, the **Bulk mail** advanced spam filtering option is enabled for new customers.</span></span> <span data-ttu-id="f0b18-141">對於遷移而來的客戶，此設定將會與您的 FOPE 組態相符。</span><span class="sxs-lookup"><span data-stu-id="f0b18-141">For migrated customers, this setting will match your FOPE configuration.</span></span> <span data-ttu-id="f0b18-142">如需大宗郵件的詳細資訊，請參閱[垃圾郵件與大宗郵件有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-142">For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

 <span data-ttu-id="f0b18-143">**問：此服務是否提供 URL 篩選？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-143">**Q. Does the service provide URL filtering?**</span></span>

<span data-ttu-id="f0b18-p110">答：是，此服務有 URL 篩選器可檢查郵件內的 URL。如果偵測到與已知垃圾郵件或惡意內容相關聯的 URL，則會將郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p110">A. Yes the service has a URL filter that checks for URLs within messages. If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>

 <span data-ttu-id="f0b18-147">**問：客戶可以如何使用此服務將誤判正常 (是垃圾郵件) 和誤判 (非垃圾郵件) 的郵件傳送給 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-147">**Q. How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?**</span></span>

<span data-ttu-id="f0b18-148">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-148">A.</span></span> <span data-ttu-id="f0b18-149">客戶可以透過多種方式將垃圾郵件與非垃圾郵件提交給 Microsoft 以進行分析。</span><span class="sxs-lookup"><span data-stu-id="f0b18-149">Spam and non-spam messages can be submitted to Microsoft for analysis in several ways.</span></span> <span data-ttu-id="f0b18-150">如需詳細資訊，請參閱[將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-150">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>

 <span data-ttu-id="f0b18-151">**問：我是否可以取得垃圾郵件報告？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-151">**Q. Can I get spam reports?**</span></span>

<span data-ttu-id="f0b18-152">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-152">A.</span></span> <span data-ttu-id="f0b18-153">是，例如，您可以在 Microsoft 365 系統管理中心取得垃圾郵件偵測報告。</span><span class="sxs-lookup"><span data-stu-id="f0b18-153">Yes, for example you can get a spam detection report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f0b18-154">報告內容會將呈現垃圾郵件唯一的郵件的樹木。</span><span class="sxs-lookup"><span data-stu-id="f0b18-154">This report shows spam volume as a count of unique messages.</span></span> <span data-ttu-id="f0b18-155">如需報告的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="f0b18-155">For more information about reporting, see the following links:</span></span>

<span data-ttu-id="f0b18-156">Exchange Online 客戶：[在 Exchange Online 中監控、報告和執行郵件追蹤](https://docs.microsoft.com/exchange/monitoring/monitoring) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-156">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)</span></span>

<span data-ttu-id="f0b18-157">Exchange Online Protection 客戶：[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-157">Exchange Online Protection customers: [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)</span></span>

 <span data-ttu-id="f0b18-158">**問：有人寄郵件給我，但我找不到。我懷疑該郵件可能被當成垃圾郵件。是否有工具可讓我查明？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-158">**Q. Someone sent me a message and I can't find it. I suspect that it may have been detected as spam. Is there a tool that I can use to find out?**</span></span>

<span data-ttu-id="f0b18-159">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-159">A.</span></span> <span data-ttu-id="f0b18-160">有的，郵件追蹤工具可讓您追蹤透過此服務的電子郵件，以了解這些電子郵件的處理情形。</span><span class="sxs-lookup"><span data-stu-id="f0b18-160">Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them.</span></span> <span data-ttu-id="f0b18-161">如需關於如何使用郵件追蹤工具來查出郵件為何被標示為垃圾郵件的詳細資訊，請參閱[郵件是否被標示為垃圾郵件？](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-161">For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span></span>

 <span data-ttu-id="f0b18-162">**問：如果我的使用者對外傳送垃圾郵件，此服務是否會對我的郵件進行節流 (速率限制)？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-162">**Q. Will the service throttle (rate limit) my mail if my users send outbound spam?**</span></span>

<span data-ttu-id="f0b18-163">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-163">A.</span></span> <span data-ttu-id="f0b18-164">如果 Office 365 判定在特定時間範圍內 (例如每小時)，使用者透過服務傳送的郵件中有一半以上是垃圾郵件，系統將封鎖該使用者傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f0b18-164">If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by Office 365, the user will be blocked from sending messages.</span></span> <span data-ttu-id="f0b18-165">在大多數情況下，系統若判定輸出郵件是垃圾郵件，則會透過高風險傳遞集區進行路由傳送，以減少正常的輸出 IP 集區被新增至封鎖清單的可能性。</span><span class="sxs-lookup"><span data-stu-id="f0b18-165">In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>

<span data-ttu-id="f0b18-166">您可以在寄件者被禁止對外傳送垃圾郵件時，傳送通知到指定的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f0b18-166">You can send a notification to a specified email address when a sender is blocked sending outbound spam.</span></span> <span data-ttu-id="f0b18-167">如需此設定的相關資訊，請參閱[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-167">For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>

 <span data-ttu-id="f0b18-168">**問：我是否可以將 Exchange Online 搭配第三方反垃圾郵件和反惡意程式碼提供者來使用？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-168">**Q. Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?**</span></span>

<span data-ttu-id="f0b18-169">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-169">A.</span></span> <span data-ttu-id="f0b18-170">可以，您可以設定其他垃圾郵件和惡意程式碼篩選服務來保護 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="f0b18-170">Yes, you may configure another spam and malware filtering service to protect your Exchange Online mailboxes.</span></span> <span data-ttu-id="f0b18-171">若要對輸入郵件執行此動作，您必須將 MX 記錄變更為指向協力廠商提供者，以將電子郵件重新導向至協力廠商提供者，然後將郵件重新導向至 EOP 進行其他處理。</span><span class="sxs-lookup"><span data-stu-id="f0b18-171">To do this for inbound mail, you should redirect your email messages to the third-party provider by changing your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing.</span></span> <span data-ttu-id="f0b18-172">若要對輸出郵件執行此動作，請將郵件傳遞目的地設定為協力廠商提供者 (智慧主機)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-172">To do this for outbound mail, please configure the message delivery destination to the third-party provider (smart host).</span></span>

 <span data-ttu-id="f0b18-173">**問：Microsoft 是否有任何關於如何自我保護以免於網路釣魚詐騙的文件？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-173">**Q. Does Microsoft have any documentation about how I can protect myself from phishing scams?**</span></span>

<span data-ttu-id="f0b18-174">答：</span><span class="sxs-lookup"><span data-stu-id="f0b18-174">A.</span></span> <span data-ttu-id="f0b18-175">有的，請參閱[保護您在網際網路上的隱私權](https://support.microsoft.com/help/4091455)</span><span class="sxs-lookup"><span data-stu-id="f0b18-175">Yes we do, please read [Protect your privacy on the internet](https://support.microsoft.com/help/4091455)</span></span>

 <span data-ttu-id="f0b18-176">**問：是否會調查垃圾郵件與惡意程式碼郵件的傳送人，或是將其轉交給執法單位？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-176">**Q. Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?**</span></span>

<span data-ttu-id="f0b18-p118">答：雖然我們偶爾會調查特別危險或具破壞性的垃圾郵件或攻擊行動，並追捕其幕後黑手，但此服務的重心主要放在偵測及移除垃圾郵件與惡意程式碼。這之中牽涉到與法律和數位犯罪單位合作打擊濫發垃圾郵件者所控制的殭屍網路 (Botnet)、阻止濫發垃圾郵件者使用服務 (如果他們使用服務來傳送輸出電子郵件)，以及將資訊轉交給執法單位以起訴犯罪行為。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p118">A. The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators. This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>

 <span data-ttu-id="f0b18-180">**問：對外傳送電子郵件時有哪些最佳做法，可確保我的郵件都能順利傳遞？**</span><span class="sxs-lookup"><span data-stu-id="f0b18-180">**Q. What are a set of best outbound mailing practices that will ensure that my mail is delivered?**</span></span>

<span data-ttu-id="f0b18-p119">答：以下提供的指導方針，是對外傳送電子郵件時的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p119">A. The guidelines presented below are best practices for sending outbound email messages.</span></span>

1. <span data-ttu-id="f0b18-183">**電子郵件的傳送端網域應在 DNS 中獲得解析。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-183">**The sending domain of the email should resolve in DNS.**</span></span>

    <span data-ttu-id="f0b18-184">例如，如果寄件者是 user@example.com，網域 example.com 會解析為 IP 位址 192.0.43.10。</span><span class="sxs-lookup"><span data-stu-id="f0b18-184">For example, if the sender is user@example.com, the domain example.com resolves to the IP address 192.0.43.10.</span></span> <span data-ttu-id="f0b18-185">如果傳送端網域在 DNS 中沒有 A 記錄與 MX 記錄，則無論郵件的內容是否為垃圾郵件訊息，此服務都會透過其較高風險傳遞集區來路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="f0b18-185">If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam.</span></span> <span data-ttu-id="f0b18-186">如需較高風險傳遞集區的詳細資訊，請參閱[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f0b18-186">For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

2. <span data-ttu-id="f0b18-187">**輸出郵件伺服器的傳送端 IP 位址應具有反向 DNS (PTR) 項目。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-187">**The sending IP address of the outbound mail server should have a reverse DNS (PTR) entry.**</span></span>

    <span data-ttu-id="f0b18-188">例如，如果從 IP 位址 192.0.43.10 傳送，此 IP 的反向 DNS 項目是 43-10.any.icann.org。</span><span class="sxs-lookup"><span data-stu-id="f0b18-188">For example, if sending from the IP address 192.0.43.10, the reverse DNS entry for this IP is 43-10.any.icann.org.</span></span>

3. <span data-ttu-id="f0b18-189">**HELO/EHLO 與 MAIL FROM 命令應一致，且以網域名稱而非 IP 位址的形式存在。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-189">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>

    <span data-ttu-id="f0b18-190">HELO/EHLO 命令應設定成符合傳送端 IP 位址的反向 DNS，讓網域在郵件標頭的各個部分間都能保持相同。</span><span class="sxs-lookup"><span data-stu-id="f0b18-190">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>

4. <span data-ttu-id="f0b18-191">**確實 DNS 中已設定適當的 SPF 記錄。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-191">**Ensure that proper SPF records are set up in DNS.**</span></span>

    <span data-ttu-id="f0b18-p121">SPF 記錄是一項驗證機制，可驗證從某個網域傳送的郵件是否真的來自該網域而不是詐騙郵件。如需 SPF 記錄的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="f0b18-p121">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>

    [<span data-ttu-id="f0b18-194">在 Office 365 中設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="f0b18-194">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

    <span data-ttu-id="f0b18-195">[網域常見問題集](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-195">[Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

5. <span data-ttu-id="f0b18-196">**使用 DKIM 簽署電子郵件時，應以寬鬆的規範簽署。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-196">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>

    <span data-ttu-id="f0b18-p122">如果寄件者要使用 Domain Keys Identified Mail (DKIM) 簽署其郵件，並且要透過此服務傳送輸出郵件，他們應使用寬鬆的標頭規範演算法進行簽署。若使用嚴格的標頭規範進行簽署，簽章可能會在通過此服務時失效。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p122">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>

6. <span data-ttu-id="f0b18-199">**網域擁有者應在 WHOIS 資料庫中具有正確的資訊。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-199">**Domain owners should have accurate information in the WHOIS database.**</span></span>

    <span data-ttu-id="f0b18-200">如此可識別網域的擁有者，以及如何輸入可靠的母公司、連絡點與名稱伺服器來連絡這些擁有者。</span><span class="sxs-lookup"><span data-stu-id="f0b18-200">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>

7. <span data-ttu-id="f0b18-201">**若為大量郵件寄件者，[寄件者:]名稱應該反映郵件的傳送者是誰，而郵件的主旨行應該顯示郵件內容的簡短摘要。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-201">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>

    <span data-ttu-id="f0b18-p123">郵件內文應明確指出所提供的優惠、服務或產品。 例如，如果寄件者為 Contoso 公司寄出大量郵件，其電子郵件的 [寄件者] 與 [主旨] 應類似如下：</span><span class="sxs-lookup"><span data-stu-id="f0b18-p123">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>

    <span data-ttu-id="f0b18-204">From:marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0b18-204">From: marketing@contoso.com</span></span>

    <span data-ttu-id="f0b18-205">主旨：聖誕節商品最新型錄！</span><span class="sxs-lookup"><span data-stu-id="f0b18-205">Subject: New updated catalog for the Christmas season!</span></span>

    <span data-ttu-id="f0b18-206">以下是說明性不足的錯誤範例：</span><span class="sxs-lookup"><span data-stu-id="f0b18-206">The following is an example of what not to do because it is not descriptive:</span></span>

    <span data-ttu-id="f0b18-207">From:user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="f0b18-207">From: user@hotmail.com</span></span>

    <span data-ttu-id="f0b18-208">主旨：型錄</span><span class="sxs-lookup"><span data-stu-id="f0b18-208">Subject: Catalogs</span></span>

8. <span data-ttu-id="f0b18-209">**如果傳送大量郵件給眾多收件者，且郵件屬於電子報格式，則應於郵件的最下方提供取消訂閱的方式。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-209">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>

    <span data-ttu-id="f0b18-210">取消訂閱選項應類似如下：</span><span class="sxs-lookup"><span data-stu-id="f0b18-210">The unsubscribe option should resemble the following:</span></span>

    <span data-ttu-id="f0b18-p124">本郵件由 sender@fabrikam.com 傳送給 example@contoso.com。更新個人資料/電子郵件地址 | 使用 **SafeUnsubscribe** 立即取消訂閱 | 隱私權原則</span><span class="sxs-lookup"><span data-stu-id="f0b18-p124">This message was sent to example@contoso.com by sender@fabrikam.com. Update Profile/Email Address | Instant removal with **SafeUnsubscribe**™ | Privacy Policy</span></span>

9. <span data-ttu-id="f0b18-213">**如果傳送大量電子郵件，則應使用雙重加入確認程序來執行清單的取得。如果您是大量郵件的寄件者，雙重加入確認程序會是業界的最佳做法。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-213">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>

    <span data-ttu-id="f0b18-214">採用雙重加入確認程序時，使用者必須執行兩個動作，才能註冊行銷郵件：</span><span class="sxs-lookup"><span data-stu-id="f0b18-214">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>

   1. <span data-ttu-id="f0b18-215">首先，使用者必須點選原先未勾選的核取方塊，表示他們選擇要進一步接收行銷者提供的產品服務或電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="f0b18-215">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>

   2. <span data-ttu-id="f0b18-216">其次，行銷者會將確認電子郵件傳送至使用者提供的電子郵件地址，要求使用者點選具有時效性的連結，以完成確認動作。</span><span class="sxs-lookup"><span data-stu-id="f0b18-216">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>

      <span data-ttu-id="f0b18-217">使用雙重加入確認程序，大量電子郵件寄件者可建立良好聲譽。</span><span class="sxs-lookup"><span data-stu-id="f0b18-217">Using double opt-in builds a good reputation for bulk email senders.</span></span>

10. <span data-ttu-id="f0b18-218">**大量郵件寄件者應建立清楚透明的內容，以示負責：**</span><span class="sxs-lookup"><span data-stu-id="f0b18-218">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>

    1. <span data-ttu-id="f0b18-219">在請收件者將寄件者加入通訊錄的用語中，應明確指出這個加入動作並不保證郵件可以成功送達。</span><span class="sxs-lookup"><span data-stu-id="f0b18-219">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>

    2. <span data-ttu-id="f0b18-220">在郵件內文中建構重新導向連結時，請使用一致的連結樣式。</span><span class="sxs-lookup"><span data-stu-id="f0b18-220">When constructing redirects in the body of the message, use a consistent link style.</span></span>

    3. <span data-ttu-id="f0b18-221">不要傳送龐大的影像或附件，或是純由影像呈現的郵件。</span><span class="sxs-lookup"><span data-stu-id="f0b18-221">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>

    4. <span data-ttu-id="f0b18-222">使用追蹤像素 (Web Bug 或指標) 時，請在您的公眾隱私權或 P3P 設定中明確指出有這些項目存在。</span><span class="sxs-lookup"><span data-stu-id="f0b18-222">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>

11. <span data-ttu-id="f0b18-223">**讓輸出的傳遞狀態通知有適當的格式。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-223">**Format outbound delivery status notifications.**</span></span>

    <span data-ttu-id="f0b18-224">在產生傳遞狀態通知訊息時，寄件者應遵循 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt) 中指定的退回格式。</span><span class="sxs-lookup"><span data-stu-id="f0b18-224">When generating delivery status notification messages, senders should follow the format of a bounce as specified in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).</span></span>

12. <span data-ttu-id="f0b18-225">**移除因使用者不存在而使郵件退回的電子郵件地址。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-225">**Remove bounced email addresses for non-existent users.**</span></span>

    <span data-ttu-id="f0b18-p125">如果您收到 NDR，指出某電子郵件地址已不再使用，請從您的清單中移除不存在的電子郵件別名。電子郵件地址會隨時間變更，而且使用者有時會棄之不用。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p125">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>

13. <span data-ttu-id="f0b18-228">**使用 Hotmail 的智慧型網路資料服務 (SNDS) 程式。**</span><span class="sxs-lookup"><span data-stu-id="f0b18-228">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>

    <span data-ttu-id="f0b18-p126">Hotmail 使用名為智慧型網路資料服務的程式，供寄件者查看使用者所提交的投訴。SNDS 是對 Hotmail 傳遞問題進行疑難排解時的主要入口網站。</span><span class="sxs-lookup"><span data-stu-id="f0b18-p126">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f0b18-231">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f0b18-231">For more information</span></span>

<span data-ttu-id="f0b18-232">[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-232">[Office 365 email anti-spam protection](anti-spam-protection.md)</span></span>

<span data-ttu-id="f0b18-233">[Exchange Online 中的安全寄件者和封鎖寄件者清單](safe-sender-and-blocked-sender-lists-faq.md) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="f0b18-233">[Safe sender and blocked sender lists in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)</span></span>

[<span data-ttu-id="f0b18-234">反垃圾郵件訊息標頭</span><span class="sxs-lookup"><span data-stu-id="f0b18-234">Anti-spam message headers</span></span>](anti-spam-message-headers.md)

[<span data-ttu-id="f0b18-235">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="f0b18-235">Backscatter messages and EOP</span></span>](backscatter-messages-and-eop.md)
