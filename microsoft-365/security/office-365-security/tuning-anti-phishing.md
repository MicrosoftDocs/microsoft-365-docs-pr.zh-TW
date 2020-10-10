---
title: 調整防網路釣魚保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
- MET150
description: 系統管理員可以瞭解如何在 Microsoft 365 中識別網頁仿冒郵件的原因，以及如何防止未來的更多網路釣魚郵件。
ms.openlocfilehash: ca1030141dd18797c7672b95ccae60b86fe9b7f2
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414151"
---
# <a name="tune-anti-phishing-protection"></a><span data-ttu-id="fb8a1-103">調整防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="fb8a1-103">Tune anti-phishing protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fb8a1-104">雖然 Microsoft 365 附帶預設已啟用的各種防網路釣魚功能，但某些網路釣魚郵件仍有可能會進入您的信箱。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-104">Although Microsoft 365 comes with a variety of anti-phishing features that are enabled by default, it's possible that some phishing messages could still get through to your mailboxes.</span></span> <span data-ttu-id="fb8a1-105">本主題說明您可以執行哪些動作來探索網路釣魚郵件的原因，以及您可以如何調整 Microsoft 365 組織中的反網路釣魚設定， _而不會不慎使事情更糟_。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-105">This topic describes what you can do to discover why a phishing message got through, and what you can do to adjust the anti-phishing settings in your Microsoft 365 organization _without accidentally making things worse_.</span></span>

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a><span data-ttu-id="fb8a1-106">第一件事是：處理任何已遭破壞的帳戶，並確定您封鎖其他網路釣魚郵件，讓</span><span class="sxs-lookup"><span data-stu-id="fb8a1-106">First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through</span></span>

<span data-ttu-id="fb8a1-107">如果寄件者的帳戶因網路釣魚郵件而遭到損害，請依照在 [Microsoft 365 中回應受損電子郵件帳戶](responding-to-a-compromised-email-account.md)的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-107">If a recipient's account was compromised as a result of the phishing message, follow the steps in [Responding to a compromised email account in Microsoft 365](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="fb8a1-108">如果您的訂閱包含高級威脅防護 (ATP) ，您可以使用 [Office 365 威脅情報](office-365-ti.md) 來識別也收到網路釣魚郵件的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-108">If your subscription includes Advanced Threat Protection (ATP), you can use [Office 365 Threat Intelligence](office-365-ti.md) to identify other users who also received the phishing message.</span></span> <span data-ttu-id="fb8a1-109">您可以使用其他選項封鎖網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="fb8a1-109">You have additional options to block phishing messages:</span></span>

- [<span data-ttu-id="fb8a1-110">Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="fb8a1-110">Safe Links in Office 365 ATP</span></span>](set-up-atp-safe-links-policies.md)

- [<span data-ttu-id="fb8a1-111">Office 365 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="fb8a1-111">Safe Attachments in Office 365 ATP</span></span>](set-up-atp-safe-attachments-policies.md)

- <span data-ttu-id="fb8a1-112">[Office 365 ATP 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-112">[Anti-phishing policies in Office 365 ATP](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="fb8a1-113">請注意，您可以暫時將原則中的 **高級網路釣魚閥** 值從 **Standard** 增加為 **積極**、 **更積極**或 **最積極**的。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-113">Note that you can temporarily increase the **Advanced phishing thresholds** in the policy from **Standard** to **Aggressive**, **More aggressive**, or **Most aggressive**.</span></span>

<span data-ttu-id="fb8a1-114">確認已開啟這些 ATP 功能。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-114">Verify these ATP features are turned on.</span></span>

## <a name="report-the-phishing-message-to-microsoft"></a><span data-ttu-id="fb8a1-115">將網路釣魚郵件報告給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb8a1-115">Report the phishing message to Microsoft</span></span>

<span data-ttu-id="fb8a1-116">報告網路釣魚郵件有助於調整用於保護 Microsoft 365 中所有客戶的篩選。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-116">Reporting phishing messages is helpful in tuning the filters that are used to protect all customers in Microsoft 365.</span></span> <span data-ttu-id="fb8a1-117">如需相關指示，請參閱 [將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-117">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="inspect-the-message-headers"></a><span data-ttu-id="fb8a1-118">檢查郵件頭</span><span class="sxs-lookup"><span data-stu-id="fb8a1-118">Inspect the message headers</span></span>

<span data-ttu-id="fb8a1-119">您可以檢查網路釣魚郵件的標頭，以查看是否有任何可以執行的動作，以防止更多網路釣魚郵件進入。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-119">You can examine the headers of the phishing message to see if there's anything that you can do yourself to prevent more phishing messages from coming through.</span></span> <span data-ttu-id="fb8a1-120">換句話說，檢查郵件頭可協助您識別組織中負責允許網路釣魚郵件的任何設定。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-120">In other words, examining the messages headers can help you identify any settings in your organization that were responsible for allowing the phishing messages in.</span></span>

<span data-ttu-id="fb8a1-121">具體而言，您應該檢查郵件頭中的 **X-Forefront-Antispam-Report** 標頭欄位，以取得 (SFV) 值的垃圾郵件篩選判定中略過的垃圾郵件或網路釣魚篩選的指示。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-121">Specifically, you should check the **X-Forefront-Antispam-Report** header field in the message headers for indications of skipped spam or phish filtering in the Spam Filtering Verdict (SFV) value.</span></span> <span data-ttu-id="fb8a1-122">略過篩選的郵件會有輸入 `SCL:-1` ，這表示您的其中一個設定是透過覆寫由服務所決定的垃圾郵件或網路釣魚 verdicts，允許這封郵件。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-122">Messages that skip filtering will have an entry of `SCL:-1`, which means one of your settings allowed this message through by overriding the spam or phish verdicts that were determined by the service.</span></span> <span data-ttu-id="fb8a1-123">如需如何取得郵件頭及所有可用反垃圾郵件和反網路釣魚郵件標題之完整清單的詳細資訊，請參閱 [Microsoft 365 中的反垃圾郵件報頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-123">For more information on how to get message headers and the complete list of all available anti-spam and anti-phish message headers, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="best-practices-to-stay-protected"></a><span data-ttu-id="fb8a1-124">保持受保護狀態的最佳作法</span><span class="sxs-lookup"><span data-stu-id="fb8a1-124">Best practices to stay protected</span></span>

- <span data-ttu-id="fb8a1-125">請以每月的頻率執行 [安全分數](../mtp/microsoft-secure-score.md) ，以評估組織的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-125">On a monthly basis, run [Secure Score](../mtp/microsoft-secure-score.md) to assess your organization's security settings.</span></span>

- <span data-ttu-id="fb8a1-126">針對因錯誤而導致隔離的郵件，或透過所允許的郵件，我們建議您在 [威脅瀏覽器和即時](threat-explorer.md)偵測中搜尋這些郵件。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-126">For messages that end up in quarantine by mistake, or for messages that are allowed through, we recommend that you search for those messages in [Threat Explorer and real-time detections](threat-explorer.md).</span></span> <span data-ttu-id="fb8a1-127">您可以依寄件者、收件者或郵件識別碼進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-127">You can search by sender, recipient, or message ID.</span></span> <span data-ttu-id="fb8a1-128">找到訊息之後，按一下主旨以移至 [詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-128">After you locate the message, go to details by clicking on the subject.</span></span> <span data-ttu-id="fb8a1-129">針對隔離的郵件，請查看「偵測技術」為何，這樣您就可以使用適當的方法來覆寫。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-129">For a quarantined message, look to see what the "detection technology" was so that you can use the appropriate method to override.</span></span> <span data-ttu-id="fb8a1-130">若為允許的郵件，請查看允許郵件使用的原則。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-130">For an allowed message, look to see which policy allowed the message.</span></span> 

- <span data-ttu-id="fb8a1-131">冒牌郵件會標記為 ATP 中的網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-131">Spoofed mail is tagged as phish in ATP.</span></span> <span data-ttu-id="fb8a1-132">有時候欺騙是良性的，有時候使用者不想隔離。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-132">Sometimes spoof is benign, and sometimes users do not want it quarantined.</span></span> <span data-ttu-id="fb8a1-133">若要將影響降至最低，請定期查看 [哄騙智慧報告](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-133">To minimize impact to users, periodically review the [Spoof intelligence report](learn-about-spoof-intelligence.md).</span></span> <span data-ttu-id="fb8a1-134">在您檢查並做任何必要的覆寫後，您就可以自信地 [設定假冒情報](set-up-anti-phishing-policies.md#spoof-settings) ，以 **隔離** 可疑郵件，而不是將其傳遞給使用者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-134">Once you have reviewed and made any necessary overrides, you can be confident to [configure spoof intelligence](set-up-anti-phishing-policies.md#spoof-settings) to **Quarantine** suspicious messages instead of delivering them to the user's Junk Email folder.</span></span>

- <span data-ttu-id="fb8a1-135">您可以重複上述步驟， (網域或使用者) 進行類比。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-135">You can repeat the above step for Impersonation (domain or user).</span></span> <span data-ttu-id="fb8a1-136">模仿報告位於 **威脅管理** \> **儀表板** \> **Insights**底下。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-136">The Impersonation report is found under **Threat Management** \> **Dashboard** \> **Insights**.</span></span>

- <span data-ttu-id="fb8a1-137">定期查看「 [威脅防護狀態」報告](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-137">Periodically review the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>

- <span data-ttu-id="fb8a1-138">有些客戶會將自己的網域放入反垃圾郵件原則中的允許寄件者或允許網域清單中，以無意間允許網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-138">Some customers inadvertently allow phishing messages through by putting their own domains in the Allow sender or Allow domain list in anti-spam policies.</span></span> <span data-ttu-id="fb8a1-139">雖然這種設定可讓某些合法的郵件透過，但也會允許垃圾郵件和/或網路釣魚篩選器通常會封鎖惡意郵件。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-139">Although this configuration will allow some legitimate messages through, it will also allow malicious messages that would normally be blocked by the spam and/or phish filters.</span></span> <span data-ttu-id="fb8a1-140">除了允許網域之外，您還應該修正基礎問題。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-140">Instead of allowing the domain, you should correct the underlying problem.</span></span>

  <span data-ttu-id="fb8a1-141">處理由 Microsoft 365 封鎖之合法郵件 (誤報) （包括網域中的寄件者）的最佳方式，是針對 _所有_ 的電子郵件網域，在 DNS 中完整且完整地設定 SPF、DKIM 及 DMARC 記錄：</span><span class="sxs-lookup"><span data-stu-id="fb8a1-141">The best way to deal with legitimate messages that are blocked by Microsoft 365 (false positives) that involve senders in your domain is to fully and completely configure the SPF, DKIM, and DMARC records in DNS for _all_ of your email domains:</span></span>

  - <span data-ttu-id="fb8a1-142">確認您的 SPF 記錄識別出您網域中寄件者的 _所有_ 電子郵件來源 (請勿忘記協力廠商服務！ ) 。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-142">Verify that your SPF record identifies _all_ sources of email for senders in your domain (don't forget third-party services!).</span></span>

  - <span data-ttu-id="fb8a1-143">使用硬性失敗 (\- 所有) ，以確保已設定為執行此作業的電子郵件系統拒絕未授權的寄件者。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-143">Use hard fail (\-all) to ensure that unauthorized senders are rejected by email systems that are configured to do so.</span></span> <span data-ttu-id="fb8a1-144">您可以使用 [哄騙情報](learn-about-spoof-intelligence.md) 來協助識別使用您網域的寄件者，這樣您就可以在 SPF 記錄中包含授權的協力廠商寄件者。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-144">You can use [spoof intelligence](learn-about-spoof-intelligence.md) to help identify senders that are using your domain so that you can include authorized third-party senders in your SPF record.</span></span>

  <span data-ttu-id="fb8a1-145">如需設定指示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="fb8a1-145">For configuration instructions, see:</span></span>
  
  - [<span data-ttu-id="fb8a1-146">設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="fb8a1-146">Set up SPF to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [<span data-ttu-id="fb8a1-147">使用 DKIM 驗證從您自訂網域傳送的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="fb8a1-147">Use DKIM to validate outbound email sent from your custom domain</span></span>](use-dkim-to-validate-outbound-email.md)

  - [<span data-ttu-id="fb8a1-148">使用 DMARC 驗證電子郵件</span><span class="sxs-lookup"><span data-stu-id="fb8a1-148">Use DMARC to validate email</span></span>](use-dmarc-to-validate-email.md)

- <span data-ttu-id="fb8a1-149">建議您盡可能將網域的電子郵件直接傳遞至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-149">Whenever possible, we recommend that you deliver email for your domain directly to Microsoft 365.</span></span> <span data-ttu-id="fb8a1-150">換句話說，請將您的 Microsoft 365 網域的 MX 記錄指向 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-150">In other words, point your Microsoft 365 domain's MX record to Microsoft 365.</span></span> <span data-ttu-id="fb8a1-151">Exchange Online Protection (EOP) 能夠在將其郵件直接傳遞至 Microsoft 365 時，為您的雲端使用者提供最佳的保護。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-151">Exchange Online Protection (EOP) is able to provide the best protection for your cloud users when their mail is delivered directly to Microsoft 365.</span></span> <span data-ttu-id="fb8a1-152">如果您必須在 EOP 前使用協力廠商的電子郵件清潔系統，請使用增強型介面篩選功能。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-152">If you must use a third-party email hygiene system in front of EOP, use Enhanced Filtering for Connectors.</span></span> <span data-ttu-id="fb8a1-153">如需相關指示，請參閱 [在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-153">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="fb8a1-154">使用者應將 [郵件報告](enable-the-report-message-add-in.md) 給 Microsoft，以進行訓練我們的系統。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-154">Users should [report messages](enable-the-report-message-add-in.md) to Microsoft, which can train our system.</span></span> <span data-ttu-id="fb8a1-155">系統管理員也應利用 [管理員提交](admin-submission.md) 功能。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-155">Admins should also take advantage of [Admin Submission](admin-submission.md) capabilities.</span></span>

- <span data-ttu-id="fb8a1-156">多重因素驗證 (MFA) 是防範已遭破壞之帳戶的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-156">Multi factor authentication (MFA) is a good way to prevent compromised accounts.</span></span> <span data-ttu-id="fb8a1-157">您應強烈考慮為您的所有使用者啟用 MFA。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-157">You should strongly consider enabling MFA for all of your users.</span></span> <span data-ttu-id="fb8a1-158">針對分段的方法，在您為每個人啟用 MFA 之前，先為最機密的使用者啟用 MFA (系統管理員、行政人員等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-158">For a phased approach, start by enabling MFA for your most sensitive users (admins, executives, etc.) before you enable MFA for everyone.</span></span> <span data-ttu-id="fb8a1-159">如需相關指示，請參閱 [設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-159">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="fb8a1-160">將規則轉寄給外部收件者通常是被攻擊者用來提取資料。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-160">Forwarding rules to external recipients are often used by attackers to extract data.</span></span> <span data-ttu-id="fb8a1-161">使用[Microsoft Secure 得分](../mtp/microsoft-secure-score.md)中的 [**複查信箱轉寄規則**] 資訊，尋找甚至避免將轉寄規則轉接給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-161">Use the **Review mailbox forwarding rules** information in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) to find and even prevent forwarding rules to external recipients.</span></span> <span data-ttu-id="fb8a1-162">如需詳細資訊，請參閱[含有安全分數的用戶端外部轉寄降低風險規則](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) (英文)。</span><span class="sxs-lookup"><span data-stu-id="fb8a1-162">For more information, see [Mitigating Client External Forwarding Rules with Secure Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).</span></span>
