---
title: 未驗證的寄件者
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。
ms.openlocfilehash: 4c8b8a0711ab66607d0db5923c1115c436537bd0
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970929"
---
# <a name="unverified-sender"></a><span data-ttu-id="9404e-103">未驗證的寄件者</span><span class="sxs-lookup"><span data-stu-id="9404e-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="9404e-104">這些更新會循環現在，並可能無法使用尚未對所有使用者。</span><span class="sxs-lookup"><span data-stu-id="9404e-104">These updates are rolling out now, and might not be available yet for all users.</span></span> <span data-ttu-id="9404e-105">企業 outlook.com 使用者支援這項功能。</span><span class="sxs-lookup"><span data-stu-id="9404e-105">This feature is supported for Enterprise outlook.com users.</span></span> <span data-ttu-id="9404e-106">它不是目前適用於消費者 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="9404e-106">It is not currently available for consumer outlook.com.</span></span>

<span data-ttu-id="9404e-107">若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="9404e-107">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9404e-108">當郵件標示為網路釣魚詐騙、 Outlook.com 和 Outlook 網頁顯示一則警告] 頁面頂端，但仍然可以開啟任何郵件中的連結。</span><span class="sxs-lookup"><span data-stu-id="9404e-108">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="9404e-109">如何識別我的收件匣中的可疑的郵件？</span><span class="sxs-lookup"><span data-stu-id="9404e-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="9404e-110">Outlook.com 和網頁型 Outlook 顯示指標，當郵件的寄件者也無法識別或其身分識別為不同於從地址中看到的內容。</span><span class="sxs-lookup"><span data-stu-id="9404e-110">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="9404e-111">您會看到 '？ ' 中的寄件者影像</span><span class="sxs-lookup"><span data-stu-id="9404e-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="9404e-112">當 Outlook.com 和網頁型 Outlook 無法驗證使用電子郵件驗證技術的寄件者的身分識別時，他們會顯示 '？ ' 中的寄件者相片。</span><span class="sxs-lookup"><span data-stu-id="9404e-112">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![郵件未通過驗證](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="9404e-114">若要驗證失敗不是每個訊息是惡意。</span><span class="sxs-lookup"><span data-stu-id="9404e-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="9404e-115">不過，您應該謹慎互動與未驗證如果您不能辨識寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="9404e-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="9404e-116">或者，如果您辨識通常沒有寄件者 '？ ' 寄件者的影像，但您突然開始看到它，可能會登寄件者詐騙。</span><span class="sxs-lookup"><span data-stu-id="9404e-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="9404e-117">如何管理哪些郵件接收未驗證的寄件者處理方式</span><span class="sxs-lookup"><span data-stu-id="9404e-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="9404e-118">如果您是 Office 365 客戶可以管理安全性 & 合規性中心透過這項功能。</span><span class="sxs-lookup"><span data-stu-id="9404e-118">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="9404e-119">在 Office 365 安全性 & 合規性中心，全域或安全性系統管理員可以關閉透過反 Phish 原則] 底下的反詐騙保護功能，開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="9404e-119">In the Office 365 Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="9404e-120">此外，它可以透過 ' 組 AntiPhishPolicy' 指令程式管理。</span><span class="sxs-lookup"><span data-stu-id="9404e-120">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="9404e-121">如需詳細資訊，請參閱[在 Office 365 中的反網路釣魚保護](anti-phishing-protection.md)及 [設定 AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9404e-121">For more details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![編輯的圖形介面中的未驗證寄件者。](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="9404e-123">如果系統管理員已識別為誤判，而寄件者應該不會收到未驗證的寄件者處理方式，其中一個下列動作可以採取新增至詐騙智慧詐騙的寄件者允許清單：</span><span class="sxs-lookup"><span data-stu-id="9404e-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="9404e-124">加入網域組經由詐騙智慧深入解析。</span><span class="sxs-lookup"><span data-stu-id="9404e-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="9404e-125">如需詳細資訊，請參閱[逐步解說： 詐騙智慧深入了解](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="9404e-125">For more details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="9404e-126">新增透過 PhishFilterPolicy 指令程式的網域組。</span><span class="sxs-lookup"><span data-stu-id="9404e-126">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="9404e-127">如需詳細資訊，請參閱[Set-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)和[設定 Office 365 ATP 防網路釣魚和防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9404e-127">For more details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="9404e-128">此外，我們不會套用未驗證寄件者處理方式如果已將其傳遞至收件匣透過系統允許清單，包括電子郵件傳輸規則 (Etr)、 安全網域清單 （反垃圾郵件原則）、 安全的寄件者清單，或使用者已設定為 「 安全寄件者 」 這個使用者在其收件匣。</span><span class="sxs-lookup"><span data-stu-id="9404e-128">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9404e-129">常見問題集</span><span class="sxs-lookup"><span data-stu-id="9404e-129">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="9404e-130">查看準則沒有 Outlook.com 和網頁型 Outlook 使用新增 '？ ' 和 '透過' 屬性？</span><span class="sxs-lookup"><span data-stu-id="9404e-130">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="9404e-131">為 '？ ' 中的寄件者影像： Outlook.com 需要郵件通過 SPF 或 DKIM 驗證，並將會收到任一 dmarc 複雜，或從 Office 365 詐騙情報傳遞複合驗證。</span><span class="sxs-lookup"><span data-stu-id="9404e-131">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="9404e-132">如需詳細資訊，請參閱[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="9404e-132">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="9404e-133">針對透過標記： Outlook.com 中自地址的網域不同網域的 DKIM 簽章或 SMTP MAIL FROM 中時，顯示在兩個欄位 （偏好的 DKIM 簽章） 的其中一個網域。</span><span class="sxs-lookup"><span data-stu-id="9404e-133">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="9404e-134">如何移除 '？ '</span><span class="sxs-lookup"><span data-stu-id="9404e-134">How do I remove the '?'</span></span>

<span data-ttu-id="9404e-135">為 '？ ' 中的寄件者影像： 為寄件者，您應該驗證與 SPF 或 DKIM 郵件。</span><span class="sxs-lookup"><span data-stu-id="9404e-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="9404e-136">針對透過標記： 為寄件者，您應該確定是在 DKIM 簽章的網域或 SMTP 郵件從相同，或是的在 [從地址的網域子網域。</span><span class="sxs-lookup"><span data-stu-id="9404e-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="9404e-137">Outlook.com 和 Outlook 網頁顯示執行此動作不會通過驗證每個郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="9404e-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="9404e-138">不是一定。</span><span class="sxs-lookup"><span data-stu-id="9404e-138">Not necessarily.</span></span> <span data-ttu-id="9404e-139">Outlook.com 和網頁型 Outlook 可能已驗證寄件者的郵件內的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="9404e-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9404e-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="9404e-140">Related topics</span></span>

[<span data-ttu-id="9404e-141">協助保護您的 Outlook.com 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="9404e-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="9404e-142">處理網路釣魚或 Outlook.com 中詐騙</span><span class="sxs-lookup"><span data-stu-id="9404e-142">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="9404e-143">篩選垃圾電子郵件和網頁型 Outlook 中的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="9404e-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
