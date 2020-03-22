---
title: Office 365 中的反垃圾郵件保護常見問題
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
ms.openlocfilehash: daabb84115f1f993fd01891bcef74c23f0391bb4
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894055"
---
# <a name="anti-spam-protection-in-office-365-faq"></a><span data-ttu-id="ac31b-104">Office 365 中的反垃圾郵件保護常見問題</span><span class="sxs-lookup"><span data-stu-id="ac31b-104">Anti-spam protection in Office 365 FAQ</span></span>

<span data-ttu-id="ac31b-105">本主題針對沒有 Exchange Online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶中的信箱，提供 Office 365 客戶的反垃圾郵件保護的常見問題與解答。</span><span class="sxs-lookup"><span data-stu-id="ac31b-105">This topic provides frequently asked questions and answers about anti-spam protection for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

<span data-ttu-id="ac31b-106">如需有關隔離區的問題與解答，請參閱[隔離常見問題集](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-106">For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>

<span data-ttu-id="ac31b-107">如需有關反惡意程式碼保護的問題和解答，請參閱[反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-107">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

## <a name="q-by-default-what-happens-to-a-spam-detected-message"></a><span data-ttu-id="ac31b-108">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-108">Q.</span></span> <span data-ttu-id="ac31b-109">依預設，偵測到垃圾郵件會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="ac31b-109">By default, what happens to a spam-detected message?</span></span>

<span data-ttu-id="ac31b-110">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-110">A.</span></span> <span data-ttu-id="ac31b-111">若**為輸入郵件：** 大部分的垃圾郵件是透過連線篩選刪除，這是根據來源電子郵件伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ac31b-111">**For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the source email server.</span></span> <span data-ttu-id="ac31b-112">反垃圾郵件原則（也稱為垃圾郵件篩選原則或內容篩選原則）會以垃圾郵件、大量或網路釣魚形式檢查郵件，並將郵件分類。</span><span class="sxs-lookup"><span data-stu-id="ac31b-112">Anti-spam policies (also known as spam filter policies or content filter policies) inspect and classify messages as spam, bulk, or phishing.</span></span> <span data-ttu-id="ac31b-113">依預設，歸類為垃圾郵件或大量的郵件會傳遞至收件者的 [垃圾郵件] 資料夾，並會隔離分類為網路釣魚的郵件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-113">By default, messages that are classified as spam or bulk are delivered to the recipient's Junk Email folder, while messages classified as phishing are quarantined.</span></span> <span data-ttu-id="ac31b-114">您可以修改預設反垃圾郵件原則（適用于所有收件者），也可以以更嚴格的使用者群組設定來建立自訂反垃圾郵件原則（例如，您可以隔離傳送給主管的垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="ac31b-114">You can modify the default anti-spam policy (applies to all recipients), or you can create custom anti-spam policies with stricter settings for specific groups of users (for example, you can quarantine spam that's sent to executives).</span></span> <span data-ttu-id="ac31b-115">如需詳細資訊，請參閱[設定 Office 365 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)和[建議的反垃圾郵件原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) and [Recommended anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac31b-116">在 EOP 保護內部部署信箱的混合部署中，您必須在內部部署 Exchange 組織中設定兩個 Exchange 郵件流程規則（也稱為傳輸規則），以偵測新增至郵件的 EOP 垃圾郵件篩選標頭。</span><span class="sxs-lookup"><span data-stu-id="ac31b-116">In hybrid deployments where EOP protects on-premises mailboxes, you need to configure two Exchange mail flow rules (also known as transport rules) in your on-premises Exchange organization to detect the EOP spam filtering headers that are added to messages.</span></span> <span data-ttu-id="ac31b-117">如需詳細資訊，請參閱[Configure 獨立 EOP 以將垃圾郵件傳送至混合式環境中的 [垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-117">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

 <span data-ttu-id="ac31b-118">**輸出郵件：** 郵件是透過[高風險傳遞集](high-risk-delivery-pool-for-outbound-messages.md)區路由傳送，或是傳回給寄件者的未傳遞回報（也稱為 NDR 或退回的郵件）。</span><span class="sxs-lookup"><span data-stu-id="ac31b-118">**For outbound messages:** The message is either routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) or is returned to the sender in a non-delivery report (also known as an NDR or bounce message).</span></span> <span data-ttu-id="ac31b-119">如需輸出垃圾郵件保護的詳細資訊，請參閱[Office 365 中的輸出垃圾郵件控制](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-119">For more information about outbound spam protection, see [Outbound spam controls in Office 365](outbound-spam-controls.md).</span></span>

## <a name="q-whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a><span data-ttu-id="ac31b-120">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-120">Q.</span></span> <span data-ttu-id="ac31b-121">哪一天是垃圾郵件變種，服務是如何處理的？</span><span class="sxs-lookup"><span data-stu-id="ac31b-121">What's a zero-day spam variant and how is it handled by the service?</span></span>

<span data-ttu-id="ac31b-122">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-122">A.</span></span> <span data-ttu-id="ac31b-123">零天垃圾郵件變種是一種最近產生的垃圾郵件變種，永遠不會被捕獲或分析，所以反垃圾郵件篩選器還沒有任何可供您偵測的資訊。</span><span class="sxs-lookup"><span data-stu-id="ac31b-123">A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our anti-spam filters don't yet have any information available for detecting it.</span></span> <span data-ttu-id="ac31b-124">在垃圾郵件分析員取得並分析零天的垃圾郵件樣本（如果它符合垃圾郵件分類準則）之後，我們會更新反垃圾郵件篩選器以偵測它，而且不會再視為「零一天」。</span><span class="sxs-lookup"><span data-stu-id="ac31b-124">After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our anti-spam filters are updated to detect it, and it's no longer considered "zero-day."</span></span> <span data-ttu-id="ac31b-125">（**附注：** 如果您收到的郵件可能是零天的垃圾郵件變種，為了協助我們改善服務，請使用[提交垃圾郵件、非垃圾郵件和網路釣魚詐騙郵件](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)中所述的其中一種方法，將郵件提交給 microsoft 進行分析。）</span><span class="sxs-lookup"><span data-stu-id="ac31b-125">(**Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)</span></span>

## <a name="q-do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a><span data-ttu-id="ac31b-126">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-126">Q.</span></span> <span data-ttu-id="ac31b-127">是否需要設定服務以提供反垃圾郵件保護？</span><span class="sxs-lookup"><span data-stu-id="ac31b-127">Do I need to configure the service to provide anti-spam protection?</span></span>

<span data-ttu-id="ac31b-128">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-128">A.</span></span> <span data-ttu-id="ac31b-129">在您註冊服務並新增您的網域之後，就會自動啟用垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="ac31b-129">After you sign up for the service and add your domain, spam filtering is automatically enabled.</span></span> <span data-ttu-id="ac31b-130">根據預設，垃圾郵件篩選會經過調整，以保護您不需要任何其他設定（除了先前所述的例外狀況，針對混合式環境中的獨立 EOP 獨立客戶）。</span><span class="sxs-lookup"><span data-stu-id="ac31b-130">By default, spam filtering is tuned to protect you without needing any additional configuration (aside from the previously noted exception for standalone EOP standalone customers in hybrid environments).</span></span> <span data-ttu-id="ac31b-131">以管理員身分，您可以編輯預設的垃圾郵件篩選設定，以最符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ac31b-131">As an admin, you can edit the default spam filtering settings to best meet the needs of your organization.</span></span> <span data-ttu-id="ac31b-132">為了獲得更多細微性，您也可以建立反垃圾郵件原則和輸出的反垃圾郵件原則，套用至組織中的指定使用者、群組或網域。</span><span class="sxs-lookup"><span data-stu-id="ac31b-132">For greater granularity, you can also create anti-spam policies and outbound anti-spam policies that are applied to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="ac31b-133">自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-133">Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>

<span data-ttu-id="ac31b-134">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="ac31b-134">For more information, see the following topics:</span></span>

[<span data-ttu-id="ac31b-135">EOP 和 Office 365 ATP 安全性的建議設定</span><span class="sxs-lookup"><span data-stu-id="ac31b-135">Recommended settings for EOP and Office 365 ATP security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

[<span data-ttu-id="ac31b-136">設定反原則</span><span class="sxs-lookup"><span data-stu-id="ac31b-136">Configure anti- policy</span></span>](configure-the-connection-filter-policy.md)

[<span data-ttu-id="ac31b-137">在 Office 365 中設定反垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ac31b-137">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="ac31b-138">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="ac31b-138">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)

## <a name="q-if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a><span data-ttu-id="ac31b-139">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-139">Q.</span></span> <span data-ttu-id="ac31b-140">如果我對反垃圾郵件原則進行變更，請在將變更儲存至其之後所需的時間，才會生效？</span><span class="sxs-lookup"><span data-stu-id="ac31b-140">If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?</span></span>

<span data-ttu-id="ac31b-141">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-141">A.</span></span> <span data-ttu-id="ac31b-142">最多可能需要1小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="ac31b-142">It may take up to 1 hour for the changes to take effect.</span></span>

## <a name="q-is-bulk-email-filtering-automatically-enabled"></a><span data-ttu-id="ac31b-143">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-143">Q.</span></span> <span data-ttu-id="ac31b-144">是否自動啟用大量電子郵件篩選？</span><span class="sxs-lookup"><span data-stu-id="ac31b-144">Is bulk email filtering automatically enabled?</span></span>

<span data-ttu-id="ac31b-145">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-145">A.</span></span> <span data-ttu-id="ac31b-146">是的。</span><span class="sxs-lookup"><span data-stu-id="ac31b-146">Yes.</span></span> <span data-ttu-id="ac31b-147">如需大量電子郵件的詳細資訊，請參閱[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-147">For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

## <a name="q-does-the-service-provide-url-filtering"></a><span data-ttu-id="ac31b-148">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-148">Q.</span></span> <span data-ttu-id="ac31b-149">服務是否提供 URL 篩選？</span><span class="sxs-lookup"><span data-stu-id="ac31b-149">Does the service provide URL filtering?</span></span>

<span data-ttu-id="ac31b-150">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-150">A.</span></span> <span data-ttu-id="ac31b-151">是的，服務具有 URL 篩選器，可檢查郵件中的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ac31b-151">Yes, the service has a URL filter that checks for URLs within messages.</span></span> <span data-ttu-id="ac31b-152">如果偵測到與已知垃圾郵件或惡意內容相關聯的 URLs，郵件會標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-152">If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>

## <a name="q-how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a><span data-ttu-id="ac31b-153">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-153">Q.</span></span> <span data-ttu-id="ac31b-154">客戶如何使用服務將否定的否定（垃圾郵件）和誤報（非垃圾郵件）郵件傳送給 Microsoft？</span><span class="sxs-lookup"><span data-stu-id="ac31b-154">How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?</span></span>

<span data-ttu-id="ac31b-155">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-155">A.</span></span> <span data-ttu-id="ac31b-156">客戶可以透過多種方式將垃圾郵件與非垃圾郵件提交給 Microsoft 以進行分析。</span><span class="sxs-lookup"><span data-stu-id="ac31b-156">Spam and non-spam messages can be submitted to Microsoft for analysis in several ways.</span></span> <span data-ttu-id="ac31b-157">如需詳細資訊，請參閱[將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-157">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>

## <a name="q-can-i-get-spam-reports"></a><span data-ttu-id="ac31b-158">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-158">Q.</span></span> <span data-ttu-id="ac31b-159">我是否可以取得垃圾郵件報告？</span><span class="sxs-lookup"><span data-stu-id="ac31b-159">Can I get spam reports?</span></span>

<span data-ttu-id="ac31b-160">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-160">A.</span></span> <span data-ttu-id="ac31b-161">是，例如，您可以在 Microsoft 365 系統管理中心取得垃圾郵件偵測報告。</span><span class="sxs-lookup"><span data-stu-id="ac31b-161">Yes, for example you can get a spam detection report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ac31b-162">報告內容會將呈現垃圾郵件唯一的郵件的樹木。</span><span class="sxs-lookup"><span data-stu-id="ac31b-162">This report shows spam volume as a count of unique messages.</span></span> <span data-ttu-id="ac31b-163">如需報告的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="ac31b-163">For more information about reporting, see the following links:</span></span>

<span data-ttu-id="ac31b-164">Exchange Online 客戶：[在 Exchange Online 中監控、報告和執行郵件追蹤](https://docs.microsoft.com/exchange/monitoring/monitoring) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="ac31b-164">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)</span></span>

<span data-ttu-id="ac31b-165">獨立 EOP 客戶：[在 Exchange Online Protection 中報告和郵件追蹤](reporting-and-message-trace-in-exchange-online-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ac31b-165">Standalone EOP customers: [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)</span></span>

## <a name="q-someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a><span data-ttu-id="ac31b-166">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-166">Q.</span></span> <span data-ttu-id="ac31b-167">某人傳送給我訊息，但找不到。</span><span class="sxs-lookup"><span data-stu-id="ac31b-167">Someone sent me a message and I can't find it.</span></span> <span data-ttu-id="ac31b-168">我懷疑它可能被偵測為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-168">I suspect that it may have been detected as spam.</span></span> <span data-ttu-id="ac31b-169">是否有可用來找出的工具？</span><span class="sxs-lookup"><span data-stu-id="ac31b-169">Is there a tool that I can use to find out?</span></span>

<span data-ttu-id="ac31b-170">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-170">A.</span></span> <span data-ttu-id="ac31b-171">有的，郵件追蹤工具可讓您追蹤透過此服務的電子郵件，以了解這些電子郵件的處理情形。</span><span class="sxs-lookup"><span data-stu-id="ac31b-171">Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them.</span></span> <span data-ttu-id="ac31b-172">如需關於如何使用郵件追蹤工具來查出郵件為何被標示為垃圾郵件的詳細資訊，請參閱[郵件是否被標示為垃圾郵件？](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="ac31b-172">For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span></span>

## <a name="q-will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a><span data-ttu-id="ac31b-173">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-173">Q.</span></span> <span data-ttu-id="ac31b-174">如果我的使用者已傳送輸出垃圾郵件，服務節流（速率限制）是我的郵件？</span><span class="sxs-lookup"><span data-stu-id="ac31b-174">Will the service throttle (rate limit) my mail if my users send outbound spam?</span></span>

<span data-ttu-id="ac31b-175">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-175">A.</span></span> <span data-ttu-id="ac31b-176">如果 Office 365 判定在特定時間範圍內 (例如每小時)，使用者透過服務傳送的郵件中有一半以上是垃圾郵件，系統將封鎖該使用者傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-176">If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by Office 365, the user will be blocked from sending messages.</span></span> <span data-ttu-id="ac31b-177">在大多數情況下，系統若判定輸出郵件是垃圾郵件，則會透過高風險傳遞集區進行路由傳送，以減少正常的輸出 IP 集區被新增至封鎖清單的可能性。</span><span class="sxs-lookup"><span data-stu-id="ac31b-177">In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>

<span data-ttu-id="ac31b-178">您可以在寄件者被禁止對外傳送垃圾郵件時，傳送通知到指定的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ac31b-178">You can send a notification to a specified email address when a sender is blocked sending outbound spam.</span></span> <span data-ttu-id="ac31b-179">如需此設定的相關資訊，請參閱[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-179">For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>

## <a name="q-can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a><span data-ttu-id="ac31b-180">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-180">Q.</span></span> <span data-ttu-id="ac31b-181">是否可以搭配 Exchange Online 使用協力廠商的反垃圾郵件和反惡意程式碼提供者？</span><span class="sxs-lookup"><span data-stu-id="ac31b-181">Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?</span></span>

<span data-ttu-id="ac31b-182">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-182">A.</span></span> <span data-ttu-id="ac31b-183">是的。</span><span class="sxs-lookup"><span data-stu-id="ac31b-183">Yes.</span></span> <span data-ttu-id="ac31b-184">雖然我們建議您將 MX 記錄指向 Office 365，但我們意識到有正當的商業理由可以將電子郵件路由傳送至 Office 365 以外的地方。</span><span class="sxs-lookup"><span data-stu-id="ac31b-184">Although we recommend that you point your MX record to Office 365, we realize that there are legitimate business reasons to route your email to somewhere other than Office 365 first.</span></span>

- <span data-ttu-id="ac31b-185">**輸入**：變更您的 MX 記錄以指向協力廠商提供者，然後將郵件重新導向至 EOP 進行其他處理。</span><span class="sxs-lookup"><span data-stu-id="ac31b-185">**Inbound**: Change your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing.</span></span> <span data-ttu-id="ac31b-186">如需詳細資訊，請參閱[在 Exchange Online 中針對連接器的增強型篩選](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-186">For more information, see [Enhanced Filtering for connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="ac31b-187">**輸出**：設定從 Office 365 到目的地協力廠商提供者的智慧主機路由。</span><span class="sxs-lookup"><span data-stu-id="ac31b-187">**Outbound**: Configure smart host routing from Office 365 to the destination third-party provider.</span></span>

## <a name="q-does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a><span data-ttu-id="ac31b-188">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-188">Q.</span></span> <span data-ttu-id="ac31b-189">Microsoft 是否有任何有關如何保護自己免受網頁仿冒騙局的保護的檔？</span><span class="sxs-lookup"><span data-stu-id="ac31b-189">Does Microsoft have any documentation about how I can protect myself from phishing scams?</span></span>

<span data-ttu-id="ac31b-190">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-190">A.</span></span> <span data-ttu-id="ac31b-191">是的。</span><span class="sxs-lookup"><span data-stu-id="ac31b-191">Yes.</span></span> <span data-ttu-id="ac31b-192">如需詳細資訊，請參閱在[網際網路上保護您的隱私權](https://support.microsoft.com/help/4091455)</span><span class="sxs-lookup"><span data-stu-id="ac31b-192">For more information, see [Protect your privacy on the internet](https://support.microsoft.com/help/4091455)</span></span>

## <a name="q-are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a><span data-ttu-id="ac31b-193">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-193">Q.</span></span> <span data-ttu-id="ac31b-194">垃圾郵件和惡意程式碼是否會進行調查，以供誰傳送或轉接至法律強制執行實體？</span><span class="sxs-lookup"><span data-stu-id="ac31b-194">Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?</span></span>

<span data-ttu-id="ac31b-p131">答：雖然我們偶爾會調查特別危險或具破壞性的垃圾郵件或攻擊行動，並追捕其幕後黑手，但此服務的重心主要放在偵測及移除垃圾郵件與惡意程式碼。這之中牽涉到與法律和數位犯罪單位合作打擊濫發垃圾郵件者所控制的殭屍網路 (Botnet)、阻止濫發垃圾郵件者使用服務 (如果他們使用服務來傳送輸出電子郵件)，以及將資訊轉交給執法單位以起訴犯罪行為。</span><span class="sxs-lookup"><span data-stu-id="ac31b-p131">A. The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators. This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>

## <a name="q-what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a><span data-ttu-id="ac31b-198">問：我收到的電子郵件有我不熟悉的附件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-198">Q.</span></span> <span data-ttu-id="ac31b-199">您可以使用哪一組最佳的輸出郵件做法，以確保已傳遞郵件？</span><span class="sxs-lookup"><span data-stu-id="ac31b-199">What are a set of best outbound mailing practices that will ensure that my mail is delivered?</span></span>

<span data-ttu-id="ac31b-200">答：</span><span class="sxs-lookup"><span data-stu-id="ac31b-200">A.</span></span> <span data-ttu-id="ac31b-201">下列所述的指導方針是傳送輸出電子郵件訊息的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="ac31b-201">The guidelines presented below are best practices for sending outbound email messages.</span></span>

- <span data-ttu-id="ac31b-202">**來源電子郵件網域應在 DNS 中解析。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-202">**The source email domain should resolve in DNS.**</span></span>

  <span data-ttu-id="ac31b-203">例如，如果寄件者為 user@fabrikam，網域 fabrikam 會解析為 IP 位址192.0.43.10。</span><span class="sxs-lookup"><span data-stu-id="ac31b-203">For example, if the sender is user@fabrikam, the domain fabrikam resolves to the IP address 192.0.43.10.</span></span>
  
  <span data-ttu-id="ac31b-204">如果傳送端網域在 DNS 中沒有 A 記錄與 MX 記錄，則無論郵件的內容是否為垃圾郵件訊息，此服務都會透過其較高風險傳遞集區來路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-204">If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam.</span></span> <span data-ttu-id="ac31b-205">如需較高風險傳遞集區的詳細資訊，請參閱[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="ac31b-205">For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="ac31b-206">**輸出郵件 eserver 應具有反向 DNS （PTR）專案。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-206">**Outbound mail eserver should have a reverse DNS (PTR) entry.**</span></span>

  <span data-ttu-id="ac31b-207">例如，如果電子郵件來源 IP 位址是192.0.43.10，則反向 DNS 專案應該是`43-10.any.icann.org`。 '</span><span class="sxs-lookup"><span data-stu-id="ac31b-207">For example, if the email source IP address is 192.0.43.10, the reverse DNS entry would be `43-10.any.icann.org`.\`</span></span>

- <span data-ttu-id="ac31b-208">**HELO/EHLO 與 MAIL FROM 命令應一致，且以網域名稱而非 IP 位址的形式存在。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-208">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>

  <span data-ttu-id="ac31b-209">HELO/EHLO 命令應設定成符合傳送端 IP 位址的反向 DNS，讓網域在郵件標頭的各個部分間都能保持相同。</span><span class="sxs-lookup"><span data-stu-id="ac31b-209">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>

- <span data-ttu-id="ac31b-210">**確實 DNS 中已設定適當的 SPF 記錄。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-210">**Ensure that proper SPF records are set up in DNS.**</span></span>

  <span data-ttu-id="ac31b-p135">SPF 記錄是一項驗證機制，可驗證從某個網域傳送的郵件是否真的來自該網域而不是詐騙郵件。如需 SPF 記錄的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="ac31b-p135">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>

  [<span data-ttu-id="ac31b-213">在 Office 365 中設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="ac31b-213">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  <span data-ttu-id="ac31b-214">[網域常見問題集](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="ac31b-214">[Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

- <span data-ttu-id="ac31b-215">**使用 DKIM 簽署電子郵件時，應以寬鬆的規範簽署。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-215">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>

  <span data-ttu-id="ac31b-p136">如果寄件者要使用 Domain Keys Identified Mail (DKIM) 簽署其郵件，並且要透過此服務傳送輸出郵件，他們應使用寬鬆的標頭規範演算法進行簽署。若使用嚴格的標頭規範進行簽署，簽章可能會在通過此服務時失效。</span><span class="sxs-lookup"><span data-stu-id="ac31b-p136">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>

- <span data-ttu-id="ac31b-218">**網域擁有者應在 WHOIS 資料庫中具有正確的資訊。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-218">**Domain owners should have accurate information in the WHOIS database.**</span></span>

  <span data-ttu-id="ac31b-219">如此可識別網域的擁有者，以及如何輸入可靠的母公司、連絡點與名稱伺服器來連絡這些擁有者。</span><span class="sxs-lookup"><span data-stu-id="ac31b-219">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>

- <span data-ttu-id="ac31b-220">**若為大量郵件寄件者，[寄件者:]名稱應該反映郵件的傳送者是誰，而郵件的主旨行應該顯示郵件內容的簡短摘要。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-220">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>

  <span data-ttu-id="ac31b-p137">郵件內文應明確指出所提供的優惠、服務或產品。 例如，如果寄件者為 Contoso 公司寄出大量郵件，其電子郵件的 [寄件者] 與 [主旨] 應類似如下：</span><span class="sxs-lookup"><span data-stu-id="ac31b-p137">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>

  > <span data-ttu-id="ac31b-223">From:marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac31b-223">From: marketing@contoso.com</span></span> <br/> <span data-ttu-id="ac31b-224">主旨：聖誕節商品最新型錄！</span><span class="sxs-lookup"><span data-stu-id="ac31b-224">Subject: New updated catalog for the Christmas season!</span></span>

  <span data-ttu-id="ac31b-225">以下是說明性不足的錯誤範例：</span><span class="sxs-lookup"><span data-stu-id="ac31b-225">The following is an example of what not to do because it is not descriptive:</span></span>

  > <span data-ttu-id="ac31b-226">From:user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="ac31b-226">From: user@hotmail.com</span></span> <br/> <span data-ttu-id="ac31b-227">主旨：型錄</span><span class="sxs-lookup"><span data-stu-id="ac31b-227">Subject: Catalogs</span></span>

- <span data-ttu-id="ac31b-228">**如果傳送大量郵件給眾多收件者，且郵件屬於電子報格式，則應於郵件的最下方提供取消訂閱的方式。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-228">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>

  <span data-ttu-id="ac31b-229">取消訂閱選項應類似如下：</span><span class="sxs-lookup"><span data-stu-id="ac31b-229">The unsubscribe option should resemble the following:</span></span>

  > <span data-ttu-id="ac31b-230">本郵件由 sender@fabrikam.com 傳送給 example@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="ac31b-230">This message was sent to example@contoso.com by sender@fabrikam.com.</span></span> <span data-ttu-id="ac31b-231">更新設定檔/電子郵件地址 |立即移除與**SafeUnsubscribe** &trade; |隱私權原則</span><span class="sxs-lookup"><span data-stu-id="ac31b-231">Update Profile/Email Address | Instant removal with **SafeUnsubscribe**&trade; | Privacy Policy</span></span>

- <span data-ttu-id="ac31b-232">**如果傳送大量電子郵件，則應使用雙重加入確認程序來執行清單的取得。如果您是大量郵件的寄件者，雙重加入確認程序會是業界的最佳做法。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-232">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>

  <span data-ttu-id="ac31b-233">採用雙重加入確認程序時，使用者必須執行兩個動作，才能註冊行銷郵件：</span><span class="sxs-lookup"><span data-stu-id="ac31b-233">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>

  1. <span data-ttu-id="ac31b-234">首先，使用者必須點選原先未勾選的核取方塊，表示他們選擇要進一步接收行銷者提供的產品服務或電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="ac31b-234">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>

  2. <span data-ttu-id="ac31b-235">其次，行銷者會將確認電子郵件傳送至使用者提供的電子郵件地址，要求使用者點選具有時效性的連結，以完成確認動作。</span><span class="sxs-lookup"><span data-stu-id="ac31b-235">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>

  <span data-ttu-id="ac31b-236">使用雙重加入確認程序，大量電子郵件寄件者可建立良好聲譽。</span><span class="sxs-lookup"><span data-stu-id="ac31b-236">Using double opt-in builds a good reputation for bulk email senders.</span></span>

- <span data-ttu-id="ac31b-237">**大量郵件寄件者應建立清楚透明的內容，以示負責：**</span><span class="sxs-lookup"><span data-stu-id="ac31b-237">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>

  1. <span data-ttu-id="ac31b-238">在請收件者將寄件者加入通訊錄的用語中，應明確指出這個加入動作並不保證郵件可以成功送達。</span><span class="sxs-lookup"><span data-stu-id="ac31b-238">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>

  2. <span data-ttu-id="ac31b-239">在郵件內文中建構重新導向連結時，請使用一致的連結樣式。</span><span class="sxs-lookup"><span data-stu-id="ac31b-239">When constructing redirects in the body of the message, use a consistent link style.</span></span>

  3. <span data-ttu-id="ac31b-240">不要傳送龐大的影像或附件，或是純由影像呈現的郵件。</span><span class="sxs-lookup"><span data-stu-id="ac31b-240">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>

  4. <span data-ttu-id="ac31b-241">使用追蹤像素 (Web Bug 或指標) 時，請在您的公眾隱私權或 P3P 設定中明確指出有這些項目存在。</span><span class="sxs-lookup"><span data-stu-id="ac31b-241">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>

- <span data-ttu-id="ac31b-242">**格式化輸出退回郵件。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-242">**Format outbound bounce messages.**</span></span>

  <span data-ttu-id="ac31b-243">產生傳遞狀態通知郵件時（也稱為未傳遞回報、NDRs 或退回的郵件），寄件者應該遵循[RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)中所指定的反彈格式。</span><span class="sxs-lookup"><span data-stu-id="ac31b-243">When generating delivery status notification messages (also known as non-delivery reports, NDRs, or bounce messages), senders should follow the format of a bounce as specified in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).</span></span>

- <span data-ttu-id="ac31b-244">**移除因使用者不存在而使郵件退回的電子郵件地址。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-244">**Remove bounced email addresses for non-existent users.**</span></span>

  <span data-ttu-id="ac31b-p139">如果您收到 NDR，指出某電子郵件地址已不再使用，請從您的清單中移除不存在的電子郵件別名。電子郵件地址會隨時間變更，而且使用者有時會棄之不用。</span><span class="sxs-lookup"><span data-stu-id="ac31b-p139">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>

- <span data-ttu-id="ac31b-247">**使用 Hotmail 的智慧型網路資料服務 (SNDS) 程式。**</span><span class="sxs-lookup"><span data-stu-id="ac31b-247">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>

  <span data-ttu-id="ac31b-p140">Hotmail 使用名為智慧型網路資料服務的程式，供寄件者查看使用者所提交的投訴。SNDS 是對 Hotmail 傳遞問題進行疑難排解時的主要入口網站。</span><span class="sxs-lookup"><span data-stu-id="ac31b-p140">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>
