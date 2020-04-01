---
title: 調整 Office 365 中的反網路釣魚保護
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
description: 系統管理員可以瞭解如何知道網路釣魚郵件的取得原因，以及如何防止未來的更多網路釣魚郵件。
ms.openlocfilehash: 37d1e8bbf91bc6f0a1c8e9b5aa97fe460e8b5c82
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081205"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a><span data-ttu-id="2bbff-103">調整 Office 365 中的反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="2bbff-103">Tune anti-phishing protection in Office 365</span></span>

<span data-ttu-id="2bbff-104">雖然 Office 365 附帶的各種防網路釣魚功能預設為啟用，但是有些網路釣魚郵件仍可進入您的信箱。</span><span class="sxs-lookup"><span data-stu-id="2bbff-104">Although Office 365 comes with a variety of anti-phishing features that are enabled by default, it's possible that some phishing messages could still get through to your mailboxes.</span></span> <span data-ttu-id="2bbff-105">本主題說明如何探索網路釣魚郵件的執行原因，以及您可以如何調整 Exchange Online 組織中的反網路釣魚設定，_而不會不慎使事情更糟_。</span><span class="sxs-lookup"><span data-stu-id="2bbff-105">This topic describes what you can do to discover why a phishing message got through, and what you can do to adjust the anti-phishing settings in your Exchange Online organization _without accidentally making things worse_.</span></span>

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a><span data-ttu-id="2bbff-106">第一件事是：處理任何已遭破壞的帳戶，並確定您封鎖其他網路釣魚郵件，讓</span><span class="sxs-lookup"><span data-stu-id="2bbff-106">First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through</span></span>

<span data-ttu-id="2bbff-107">如果寄件者的帳戶因網路釣魚郵件而遭到損害，請遵循在[Office 365 中回應受損電子郵件帳戶](responding-to-a-compromised-email-account.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="2bbff-107">If a recipient's account was compromised as a result of the phishing message, follow the steps in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="2bbff-108">如果您的訂閱包含高級威脅防護（ATP），您可以使用[Office 365 威脅情報](office-365-ti.md)來識別也收到網路釣魚郵件的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="2bbff-108">If your subscription includes Advanced Threat Protection (ATP), you can use [Office 365 Threat Intelligence](office-365-ti.md) to identify other users who also received the phishing message.</span></span> <span data-ttu-id="2bbff-109">您可以使用其他選項封鎖網路釣魚郵件：</span><span class="sxs-lookup"><span data-stu-id="2bbff-109">You have additional options to block phishing messages:</span></span>

- [<span data-ttu-id="2bbff-110">ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="2bbff-110">ATP Safe Links</span></span>](set-up-atp-safe-links-policies.md)

- [<span data-ttu-id="2bbff-111">ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="2bbff-111">ATP Safe Attachments</span></span>](set-up-atp-safe-attachments-policies.md)

- <span data-ttu-id="2bbff-112">[ATP 反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2bbff-112">[ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="2bbff-113">請注意，您可以暫時將原則中的**高級網路釣魚閥**值從**Standard**增加為**積極**、**更積極**或**最積極**的。</span><span class="sxs-lookup"><span data-stu-id="2bbff-113">Note that you can temporarily increase the **Advanced phishing thresholds** in the policy from **Standard** to **Aggressive**, **More aggressive**, or **Most aggressive**.</span></span>

<span data-ttu-id="2bbff-114">確認已開啟這些 ATP 功能。</span><span class="sxs-lookup"><span data-stu-id="2bbff-114">Verify these ATP features are turned on.</span></span>

## <a name="report-the-phishing-message-to-microsoft"></a><span data-ttu-id="2bbff-115">將網路釣魚郵件報告給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="2bbff-115">Report the phishing message to Microsoft</span></span>

<span data-ttu-id="2bbff-116">報告網路釣魚郵件有助於調整用來保護 Office 365 中所有客戶的篩選。</span><span class="sxs-lookup"><span data-stu-id="2bbff-116">Reporting phishing messages is helpful in tuning the filters that are used to protect all customers in Office 365.</span></span> <span data-ttu-id="2bbff-117">如需相關指示，請參閱[將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="2bbff-117">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="inspect-the-message-headers"></a><span data-ttu-id="2bbff-118">檢查郵件頭</span><span class="sxs-lookup"><span data-stu-id="2bbff-118">Inspect the message headers</span></span>

<span data-ttu-id="2bbff-119">您可以檢查網路釣魚郵件的標頭，以查看是否有任何可以執行的動作，以防止更多網路釣魚郵件進入。</span><span class="sxs-lookup"><span data-stu-id="2bbff-119">You can examine the headers of the phishing message to see if there's anything that you can do yourself to prevent more phishing messages from coming through.</span></span> <span data-ttu-id="2bbff-120">換句話說，檢查郵件頭可協助您識別組織中負責允許網路釣魚郵件的任何設定。</span><span class="sxs-lookup"><span data-stu-id="2bbff-120">In other words, examining the messages headers can help you identify any settings in your organization that were responsible for allowing the phishing messages in.</span></span>

<span data-ttu-id="2bbff-121">具體而言，您應該檢查郵件頭中的**X-Forefront-Antispam-Report**標頭欄位，以瞭解在垃圾郵件篩選判定（SFV）值中略過的垃圾郵件或網路釣魚篩選跡象。</span><span class="sxs-lookup"><span data-stu-id="2bbff-121">Specifically, you should check the **X-Forefront-Antispam-Report** header field in the message headers for indications of skipped spam or phish filtering in the Spam Filtering Verdict (SFV) value.</span></span> <span data-ttu-id="2bbff-122">略過篩選的郵件會有輸入`SCL:-1`，這表示您的其中一個設定是透過覆寫由服務所決定的垃圾郵件或網路釣魚 verdicts，允許這封郵件。</span><span class="sxs-lookup"><span data-stu-id="2bbff-122">Messages that skip filtering will have an entry of `SCL:-1`, which means one of your settings allowed this message through by overriding the spam or phish verdicts that were determined by the service.</span></span> <span data-ttu-id="2bbff-123">如需如何取得郵件頭及所有可用反垃圾郵件和反網路釣魚郵件標題之完整清單的詳細資訊，請參閱[Office 365 中的反垃圾郵件郵件頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="2bbff-123">For more details on how to get message headers and the complete list of all available anti-spam and anti-phish message headers, see [Anti-spam message headers in Office 365](anti-spam-message-headers.md).</span></span>

## <a name="best-practices-to-stay-protected"></a><span data-ttu-id="2bbff-124">保持受保護狀態的最佳作法</span><span class="sxs-lookup"><span data-stu-id="2bbff-124">Best practices to stay protected</span></span>

- <span data-ttu-id="2bbff-125">請以每月的頻率執行[安全評分](../mtp/microsoft-secure-score.md)，以評估 Office 365 組織的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="2bbff-125">On a monthly basis, run [Secure Score](../mtp/microsoft-secure-score.md) to assess your Office 365 organization's security settings.</span></span>

- <span data-ttu-id="2bbff-126">定期查看[欺騙性智慧報告](learn-about-spoof-intelligence.md)，並[在反網路釣魚原則中啟用反欺騙保護](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy)，以**隔離**可疑郵件，而不是將可疑郵件傳遞至使用者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="2bbff-126">Periodically review the [Spoof intelligence report](learn-about-spoof-intelligence.md) and [enable anti-spoofing protection in the anti-phishing policy](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) to **quarantine** suspicious messages instead of delivering them to the user's Junk Email folder.</span></span>

- <span data-ttu-id="2bbff-127">定期查看「[威脅防護狀態」報告](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="2bbff-127">Periodically review the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>

- <span data-ttu-id="2bbff-128">有些客戶會將自己的網域放入反垃圾郵件原則中的允許寄件者或允許網域清單中，以無意間允許網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="2bbff-128">Some customers inadvertently allow phishing messages through by putting their own domains in the Allow sender or Allow domain list in anti-spam policies.</span></span> <span data-ttu-id="2bbff-129">如果您選擇這麼做，您必須特別小心使用。</span><span class="sxs-lookup"><span data-stu-id="2bbff-129">If you choose to do this, you must use extreme caution.</span></span> <span data-ttu-id="2bbff-130">雖然這種設定可讓某些合法的郵件透過，但也會允許 Office 365 垃圾郵件和/或網路釣魚篩選器通常會封鎖的惡意郵件。</span><span class="sxs-lookup"><span data-stu-id="2bbff-130">Although this configuration will allow some legitimate messages through, it will also allow malicious messages that would normally be blocked by the Office 365 spam and/or phish filters.</span></span>

  <span data-ttu-id="2bbff-131">若要處理受 Office 365 （誤報）封鎖的合法郵件（包括網域中的寄件者），最好在 DNS 中完整且完整地為您的 Office 365 中的_所有_電子郵件網域設定 SPF、DKIM 及 DMARC 記錄：</span><span class="sxs-lookup"><span data-stu-id="2bbff-131">The best way to deal with legitimate messages that are blocked by Office 365 (false positives) that involve senders in your domain is to fully and completely configure the SPF, DKIM, and DMARC records in DNS for _all_ of your email domains in Office 365:</span></span>

  - <span data-ttu-id="2bbff-132">確認您的 SPF 記錄識別出您網域中寄件者的_所有_電子郵件來源（請勿忘記協力廠商服務！）。</span><span class="sxs-lookup"><span data-stu-id="2bbff-132">Verify that your SPF record identifies _all_ sources of email for senders in your domain (don't forget third-party services!).</span></span>

  - <span data-ttu-id="2bbff-133">使用 hard fail （\-）以確保已設定為執行此作業的電子郵件系統拒絕未授權的寄件者。</span><span class="sxs-lookup"><span data-stu-id="2bbff-133">Use hard fail (\-) to ensure that unauthorized senders are rejected by email systems that are configured to do so.</span></span> <span data-ttu-id="2bbff-134">您可以使用[哄騙情報](learn-about-spoof-intelligence.md)來協助識別使用您網域的寄件者，這樣您就可以在 SPF 記錄中包含授權的協力廠商寄件者。</span><span class="sxs-lookup"><span data-stu-id="2bbff-134">You can use [spoof intelligence](learn-about-spoof-intelligence.md) to help identify senders that are using your domain so that you can include authorized third-party senders in your SPF record.</span></span>

  <span data-ttu-id="2bbff-135">如需設定指示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="2bbff-135">For configuration instructions, see:</span></span>
  
  - [<span data-ttu-id="2bbff-136">在 Office 365 中設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="2bbff-136">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [<span data-ttu-id="2bbff-137">使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="2bbff-137">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

  - [<span data-ttu-id="2bbff-138">在 Office 365 中使用 DMARC 來驗證電子郵件</span><span class="sxs-lookup"><span data-stu-id="2bbff-138">Use DMARC to validate email in Office 365</span></span>](use-dmarc-to-validate-email.md)

- <span data-ttu-id="2bbff-139">建議您盡可能將網域的電子郵件直接傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2bbff-139">Whenever possible, we recommend that you deliver email for your domain directly to Office 365.</span></span> <span data-ttu-id="2bbff-140">換句話說，請將您的 Office 365 網域的 MX 記錄指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2bbff-140">In other words, point your Office 365 domain's MX record to Office 365.</span></span> <span data-ttu-id="2bbff-141">Exchange Online Protection （EOP）可在您的使用者郵件直接傳遞至 Office 365 時，為您的雲端使用者提供最佳的保護。</span><span class="sxs-lookup"><span data-stu-id="2bbff-141">Exchange Online Protection (EOP) is able to provide the best protection for your cloud users when their mail is delivered directly to Office 365.</span></span> <span data-ttu-id="2bbff-142">如果您必須在 EOP 前使用協力廠商的電子郵件清潔系統，請使用增強型介面篩選功能。</span><span class="sxs-lookup"><span data-stu-id="2bbff-142">If you must use a third-party email hygiene system in front of EOP, use Enhanced Filtering for Connectors.</span></span> <span data-ttu-id="2bbff-143">如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="2bbff-143">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="2bbff-144">多重要素驗證（MFA）是一種避免受損帳戶的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="2bbff-144">Multi factor authentication (MFA) is a really good way to prevent compromised accounts.</span></span> <span data-ttu-id="2bbff-145">您應強烈考慮為您的所有使用者啟用 MFA。</span><span class="sxs-lookup"><span data-stu-id="2bbff-145">You should strongly consider enabling MFA for all of your users.</span></span> <span data-ttu-id="2bbff-146">針對分段的方法，在您為所有人啟用 MFA 之前，先為您最機密的使用者（系統管理員、行政人員等等）啟用 MFA，以開始執行。</span><span class="sxs-lookup"><span data-stu-id="2bbff-146">For a phased approach, start by enabling MFA for your most sensitive users (admins, executives, etc.) before you enable MFA for everyone.</span></span> <span data-ttu-id="2bbff-147">如需相關指示，請參閱[設定多重要素驗證](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="2bbff-147">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="2bbff-148">將規則轉寄給外部收件者通常是被攻擊者用來提取資料。</span><span class="sxs-lookup"><span data-stu-id="2bbff-148">Forwarding rules to external recipients are often used by attackers to extract data.</span></span> <span data-ttu-id="2bbff-149">使用[Microsoft Secure 得分](../mtp/microsoft-secure-score.md)中的 [**複查信箱轉寄規則**] 資訊，尋找甚至避免將轉寄規則轉接給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="2bbff-149">Use the **Review mailbox forwarding rules** information in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) to find and even prevent forwarding rules to external recipients.</span></span> <span data-ttu-id="2bbff-150">如需詳細資訊，請參閱[含有安全分數的用戶端外部轉寄降低風險規則](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/) (英文)。</span><span class="sxs-lookup"><span data-stu-id="2bbff-150">For more information, see [Mitigating Client External Forwarding Rules with Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).</span></span>
