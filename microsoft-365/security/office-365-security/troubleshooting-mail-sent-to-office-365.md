---
title: 疑難排解傳送至 Microsoft 365 的郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 本文提供將電子郵件傳送至 Microsoft 365 收件匣之問題的疑難排解資訊 & 大量郵遞至 Microsoft 365 客戶的最佳作法。
ms.openlocfilehash: 4243f46746cb21425fc2dc7493c69818f095e71f
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307576"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="63b49-103">疑難排解傳送至 Microsoft 365 的郵件</span><span class="sxs-lookup"><span data-stu-id="63b49-103">Troubleshooting mail sent to Microsoft 365</span></span>

<span data-ttu-id="63b49-104">本文提供嘗試將電子郵件傳送至 Microsoft 365 收件匣的寄件者疑難排解資訊，以及大量郵遞至客戶的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="63b49-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="63b49-105">您是否正在管理您的 IP 和網域的傳送信譽？</span><span class="sxs-lookup"><span data-stu-id="63b49-105">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="63b49-106">EOP 篩選技術是專門為 Microsoft 365 及其他 Microsoft 產品（如 Exchange Server）提供反垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="63b49-106">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="63b49-107">我們也會利用 SPF、DKIM 及 DMARC;電子郵件驗證技術，可協助您驗證傳送電子郵件的網域是否獲得授權，以解決哄騙和網路釣魚問題。</span><span class="sxs-lookup"><span data-stu-id="63b49-107">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="63b49-108">EOP 篩選會受到許多與傳送 IP、網域、驗證、清單準確性、投訴率、內容等等相關的因素所影響。</span><span class="sxs-lookup"><span data-stu-id="63b49-108">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="63b49-109">其中一個主要因素是降低寄件者的信譽，並提供電子郵件的能力為垃圾郵件的投訴率。</span><span class="sxs-lookup"><span data-stu-id="63b49-109">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="63b49-110">您從新的 IP 位址送出電子郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="63b49-110">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="63b49-111">先前未用來傳送電子郵件的 IP 位址，通常不會在我們的系統中建立任何信譽。</span><span class="sxs-lookup"><span data-stu-id="63b49-111">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="63b49-112">因此，來自新 Ip 的電子郵件很可能會遇到傳遞問題。</span><span class="sxs-lookup"><span data-stu-id="63b49-112">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="63b49-113">一旦 IP 已具備未傳送垃圾郵件的信譽，EOP 通常會允許更佳的電子郵件傳遞體驗。</span><span class="sxs-lookup"><span data-stu-id="63b49-113">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="63b49-114">在現有的 SPF 記錄中驗證的網域所新增的新 Ip，通常會有額外的優點，可繼承某些網域的傳送信譽。</span><span class="sxs-lookup"><span data-stu-id="63b49-114">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="63b49-115">如果您的網域有良好的送出信譽，新的 Ip 可能會經歷較短的起步時間。</span><span class="sxs-lookup"><span data-stu-id="63b49-115">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="63b49-116">新的 IP 可以預計會在數個星期內完全 ramped，也可以更快，視數量、清單準確性和垃圾郵件投訴率而定。</span><span class="sxs-lookup"><span data-stu-id="63b49-116">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="63b49-117">確認已正確設定 DNS</span><span class="sxs-lookup"><span data-stu-id="63b49-117">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="63b49-118">如需如何建立及維護 DNS 記錄的指示（包括郵件路由所需的 MX 記錄），您必須聯繫您的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="63b49-118">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="63b49-119">確定您未以無法路由傳送的 IP 形式刊登廣告</span><span class="sxs-lookup"><span data-stu-id="63b49-119">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="63b49-120">我們可能不會接受寄件者的電子郵件，而不是寄件者進行反向 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="63b49-120">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="63b49-121">在某些情況下，合法寄件者會在嘗試開啟與 EOP 的連線時，宣告自身，將其自我宣告為非網際網路可路由傳送的 IP。</span><span class="sxs-lookup"><span data-stu-id="63b49-121">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="63b49-122">保留用於私人 (不可路由傳送) 網路的 IP 位址包括：</span><span class="sxs-lookup"><span data-stu-id="63b49-122">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="63b49-123">192.168.0.0/16 (或 192.168.0.0-192.168.255.255) </span><span class="sxs-lookup"><span data-stu-id="63b49-123">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="63b49-124">10.0.0.0/8 (或 10.0.0.0-10.255.255.255) </span><span class="sxs-lookup"><span data-stu-id="63b49-124">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="63b49-125">172.16.0.0/11 (或 172.16.0.0 172.31.255.255) </span><span class="sxs-lookup"><span data-stu-id="63b49-125">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="63b49-126">傳送電子郵件給 Office 365 中的使用者時，收到未傳遞回報 (NDR) </span><span class="sxs-lookup"><span data-stu-id="63b49-126">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="63b49-127">有些傳遞問題是由 Microsoft 封鎖的寄件者的 IP 位址，或是因為先前的垃圾郵件，將使用者帳戶識別為封鎖的寄件者的結果。</span><span class="sxs-lookup"><span data-stu-id="63b49-127">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="63b49-128">如果您認為您已接收到錯誤 NDR，請先遵循 NDR 訊息中的任何指示來解決問題。</span><span class="sxs-lookup"><span data-stu-id="63b49-128">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="63b49-129">如需您收到之錯誤的詳細資訊，請參閱 Exchange Online 中的 [電子郵件未傳遞](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)回報中的錯誤代碼清單。</span><span class="sxs-lookup"><span data-stu-id="63b49-129">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="63b49-130">例如，如果您收到下列 NDR，它表示 Microsoft 已封鎖傳送 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="63b49-130">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="63b49-131">若要從此清單要求移除，您可以 [使用取消列出入口網站，將您自己從 [封鎖的寄件者] 清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="63b49-131">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="63b49-132">收件者的 [垃圾郵件] 資料夾中的我的電子郵件進入</span><span class="sxs-lookup"><span data-stu-id="63b49-132">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="63b49-133">如果郵件被 EOP 錯誤地辨識為垃圾郵件，您可以使用收件者將此錯誤的郵件提交給 Microsoft 垃圾郵件分析小組，該小組會評估和分析郵件。</span><span class="sxs-lookup"><span data-stu-id="63b49-133">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="63b49-134">如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="63b49-134">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="63b49-135">EOP 傳輸來自我的 IP 位址的流量</span><span class="sxs-lookup"><span data-stu-id="63b49-135">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="63b49-136">如果您收到來自 EOP 的 NDR，指出您的 IP 位址正由 EOP 節流，例如：</span><span class="sxs-lookup"><span data-stu-id="63b49-136">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="63b49-137">您接收到 NDR，因為已偵測到 IP 位址有可疑的活動，而且在進一步評估時會暫時加以限制。</span><span class="sxs-lookup"><span data-stu-id="63b49-137">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="63b49-138">如果懷疑是透過評估加以清除，則會很快解除此限制。</span><span class="sxs-lookup"><span data-stu-id="63b49-138">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="63b49-139">我無法從 Microsoft 365 中的寄件者接收電子郵件</span><span class="sxs-lookup"><span data-stu-id="63b49-139">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="63b49-140">若要從我們的使用者接收郵件，請確定您的網路允許來自 EOP 在我們資料中心使用的 IP 位址的連線。</span><span class="sxs-lookup"><span data-stu-id="63b49-140">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="63b49-141">如需詳細資訊，請參閱 [Exchange Online PROTECTION IP 位址](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="63b49-141">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="63b49-142">大量電子郵件至 Microsoft 365 使用者的最佳作法</span><span class="sxs-lookup"><span data-stu-id="63b49-142">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="63b49-143">如果您經常對 Microsoft 365 使用者執行大量電子郵件行銷活動，並想確保您的電子郵件能夠以安全且及時的方式送達，請遵循本節中的秘訣。</span><span class="sxs-lookup"><span data-stu-id="63b49-143">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="63b49-144">確定 [寄件者] 名稱會反映傳送郵件的寄件者</span><span class="sxs-lookup"><span data-stu-id="63b49-144">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="63b49-145">主旨應該是郵件內容的簡短摘要，郵件內文應該清楚並簡潔指出產品的功能、服務或產品。</span><span class="sxs-lookup"><span data-stu-id="63b49-145">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="63b49-146">例如：</span><span class="sxs-lookup"><span data-stu-id="63b49-146">For example:</span></span>

<span data-ttu-id="63b49-147">正確：</span><span class="sxs-lookup"><span data-stu-id="63b49-147">Correct:</span></span>

> <span data-ttu-id="63b49-148">寄件者： marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="63b49-148">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="63b49-149">主旨：耶誕節季節的更新目錄！</span><span class="sxs-lookup"><span data-stu-id="63b49-149">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="63b49-150">不正確：</span><span class="sxs-lookup"><span data-stu-id="63b49-150">Incorrect:</span></span>

> <span data-ttu-id="63b49-151">寄件者： someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="63b49-151">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="63b49-152">主旨：型錄</span><span class="sxs-lookup"><span data-stu-id="63b49-152">Subject: Catalogs</span></span>

<span data-ttu-id="63b49-153">讓使用者更輕鬆地知道您是誰和您正在做什麼時，您將無法透過大多數垃圾郵件篩選器進行傳遞的難度。</span><span class="sxs-lookup"><span data-stu-id="63b49-153">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="63b49-154">在行銷活動電子郵件中永遠包含取消訂閱選項</span><span class="sxs-lookup"><span data-stu-id="63b49-154">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="63b49-155">市場宣傳電子郵件（特別是電子報）應始終包含一種從今後電子郵件取消訂閱的方式。</span><span class="sxs-lookup"><span data-stu-id="63b49-155">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="63b49-156">例如：</span><span class="sxs-lookup"><span data-stu-id="63b49-156">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="63b49-157">某些寄件者包含此選項的方式是要求收件者將電子郵件傳送至使用中「退訂」的特定別名。</span><span class="sxs-lookup"><span data-stu-id="63b49-157">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="63b49-158">以上的按一下範例並不可取。</span><span class="sxs-lookup"><span data-stu-id="63b49-158">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="63b49-159">如果您選擇要求收件者傳送郵件，請確定當他們按一下此連結時，會預先填入所有必要的欄位。</span><span class="sxs-lookup"><span data-stu-id="63b49-159">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="63b49-160">使用雙加入宣告行銷電子郵件或電子報註冊的選項</span><span class="sxs-lookup"><span data-stu-id="63b49-160">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="63b49-161">如果您的公司需要或鼓勵使用者註冊其連絡人資訊，以便存取您的產品或服務，建議採用這種行業最佳作法。</span><span class="sxs-lookup"><span data-stu-id="63b49-161">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="63b49-162">有些公司使其在註冊過程中自動為其使用者註冊行銷電子郵件或電子新聞稿，但這會被視為電子郵件篩選世界的可疑行銷作法。</span><span class="sxs-lookup"><span data-stu-id="63b49-162">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="63b49-163">在註冊過程中，如果「是，請傳送您的簡報」或「是，請傳送我的特價產品」核取方塊預設為選取狀態。預設會選取 [您要傳送給我的特殊產品] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="63b49-163">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="63b49-164">建議您改為使用雙重加入宣告選項，也就是說預設會取消選取 [行銷電子郵件或電子報] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="63b49-164">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="63b49-165">此外，在提交註冊表單之後，會透過 URL 將驗證電子郵件傳送給使用者，以允許使用者確認他們接收行銷電子郵件的決策。</span><span class="sxs-lookup"><span data-stu-id="63b49-165">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="63b49-166">這可協助確保只會註冊要接收行銷電子郵件的使用者，進而清除傳送公司的任何可疑電子郵件行銷慣例。</span><span class="sxs-lookup"><span data-stu-id="63b49-166">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="63b49-167">確定電子郵件訊息內容透明且可追蹤</span><span class="sxs-lookup"><span data-stu-id="63b49-167">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="63b49-168">同樣重要的是，電子郵件的傳送方式也是其所包含的內容。</span><span class="sxs-lookup"><span data-stu-id="63b49-168">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="63b49-169">建立電子郵件內容時，請使用下列最佳作法，以確保電子郵件篩選服務不會標記您的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="63b49-169">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="63b49-170">當電子郵件訊息要求收件者將寄件者新增至通訊錄時，應明確指出這類動作不是傳遞的保證。</span><span class="sxs-lookup"><span data-stu-id="63b49-170">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="63b49-171">包含在郵件本文內的重新導向應該類似且一致，而且不會有多個變化。</span><span class="sxs-lookup"><span data-stu-id="63b49-171">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="63b49-172">在此內容中的重新導向是指離郵件的任何東西，例如連結和檔。</span><span class="sxs-lookup"><span data-stu-id="63b49-172">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="63b49-173">如果您有大量的廣告或取消訂閱連結，或更新設定檔連結，它們都應該指向相同的網域。</span><span class="sxs-lookup"><span data-stu-id="63b49-173">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="63b49-174">例如：</span><span class="sxs-lookup"><span data-stu-id="63b49-174">For example:</span></span>

  <span data-ttu-id="63b49-175">正確：</span><span class="sxs-lookup"><span data-stu-id="63b49-175">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="63b49-176">不正確：</span><span class="sxs-lookup"><span data-stu-id="63b49-176">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="63b49-177">避免使用大型圖像和附件的內容，或完全由圖像組成的郵件。</span><span class="sxs-lookup"><span data-stu-id="63b49-177">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="63b49-178">您的公開隱私權或 P3P 設定應明確指出追蹤圖元是否存在 (網頁臭蟲或信標) 。</span><span class="sxs-lookup"><span data-stu-id="63b49-178">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="63b49-179">移除資料庫中不正確的電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="63b49-179">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="63b49-180">資料庫中任何建立回彈的電子郵件別名都不是必要的，而是讓您的外寄電子郵件面臨進一步透過電子郵件篩選服務審查的風險。</span><span class="sxs-lookup"><span data-stu-id="63b49-180">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="63b49-181">確定您的電子郵件資料庫是最新的。</span><span class="sxs-lookup"><span data-stu-id="63b49-181">Ensure that your email database is up-to-date.</span></span>
