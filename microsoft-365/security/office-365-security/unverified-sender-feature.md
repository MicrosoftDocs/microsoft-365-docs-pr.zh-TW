---
title: 未驗證寄件者
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 本文將引導您開啟，如何防止網路釣魚郵件到達您的信箱、Outlook.com 和網頁型 Outlook。
ms.openlocfilehash: ed317f5673aa37b91e8c5092eb127b8df6be944e
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754829"
---
# <a name="unverified-sender"></a><span data-ttu-id="47b27-103">未驗證寄件者</span><span class="sxs-lookup"><span data-stu-id="47b27-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="47b27-104">這些更新現在會立即推出，並非所有使用者都能使用這些更新。</span><span class="sxs-lookup"><span data-stu-id="47b27-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="47b27-105">Enterprise Outlook.com 和 Enterprise Outlook Win32 桌面使用者均支援此功能。</span><span class="sxs-lookup"><span data-stu-id="47b27-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="47b27-106">目前不適用於消費者 Office 365 使用者。</span><span class="sxs-lookup"><span data-stu-id="47b27-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="47b27-107">若要防止網路釣魚郵件到達您的信箱，Office 365 會驗證寄件者是否為他們所說的使用者，並將可疑郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="47b27-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47b27-108">當郵件標示為網路釣魚詐騙時，Outlook 會在頁面頂端顯示警告，但仍然可以開啟郵件中的任何連結。</span><span class="sxs-lookup"><span data-stu-id="47b27-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="47b27-109">如何在收件匣中識別可疑郵件？</span><span class="sxs-lookup"><span data-stu-id="47b27-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="47b27-110">當郵件的寄件者無法識別或其身分識別與 [寄件者] 位址中所看到的不同時，Outlook 會顯示指示器。</span><span class="sxs-lookup"><span data-stu-id="47b27-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="47b27-111">您會在寄件者圖像中看到 '？ '</span><span class="sxs-lookup"><span data-stu-id="47b27-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="47b27-112">當 Office 365 無法使用電子郵件驗證技術驗證寄件者的身分識別時，會在寄件者圖像中顯示「？」。</span><span class="sxs-lookup"><span data-stu-id="47b27-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![郵件未通過驗證](../../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="47b27-114">並非所有驗證失敗的郵件皆為惡意。</span><span class="sxs-lookup"><span data-stu-id="47b27-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="47b27-115">不過，如果您無法辨識寄件者，請務必小心與不會驗證的郵件互動。</span><span class="sxs-lookup"><span data-stu-id="47b27-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="47b27-116">或者，如果您辨識的寄件者在寄件者圖像中通常不會有 '？ '，但您突然開始看到此寄件者，則可能是寄件者遭到欺騙的簽署。</span><span class="sxs-lookup"><span data-stu-id="47b27-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="47b27-117">如何管理接收未驗證寄件者處理的郵件</span><span class="sxs-lookup"><span data-stu-id="47b27-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="47b27-118">如果您是 Office 365 客戶，您可以透過 Office 365 安全性 & 規範中心管理這項功能。</span><span class="sxs-lookup"><span data-stu-id="47b27-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="47b27-119">在安全性 & 規範中心中，全域或安全性管理員可以透過反網路釣魚原則的反欺騙防護功能開啟或關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="47b27-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="47b27-120">此外，您可以在 Exchange Online PowerShell 中使用**AntiPhishPolicy 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="47b27-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="47b27-121">如需詳細資訊，請參閱[Office 365 中的反網路釣魚保護](anti-phishing-protection.md)和 [設定 AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy)。</span><span class="sxs-lookup"><span data-stu-id="47b27-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy).</span></span>

    ![編輯圖形介面中未經驗證的寄件者。](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="47b27-123">如果系統管理員識別出誤報，但寄件者不應接收未驗證的寄件者治療，則可以採取下列其中一項動作，將寄件者新增至「欺騙智慧欺騙允許」清單：</span><span class="sxs-lookup"><span data-stu-id="47b27-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="47b27-124">透過欺騙智慧洞察力新增網域配對。</span><span class="sxs-lookup"><span data-stu-id="47b27-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="47b27-125">如需詳細資訊，請參閱[演練：欺騙性智慧洞察力](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="47b27-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="47b27-126">透過 Exchange Online PowerShell 中的**Set-PhishFilterPolicy** Cmdlet 新增網域對。</span><span class="sxs-lookup"><span data-stu-id="47b27-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="47b27-127">如需詳細資訊，請參閱[Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)和[設定 Office 365 ATP 反網路釣魚和反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="47b27-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="47b27-128">此外，如果郵件透過郵件流程規則（也稱為傳輸規則）或安全網域清單（反垃圾郵件原則）傳遞至 [收件匣]，則不會套用未驗證寄件者的處理。</span><span class="sxs-lookup"><span data-stu-id="47b27-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="47b27-129">如何管理 "via" 標記</span><span class="sxs-lookup"><span data-stu-id="47b27-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="47b27-130">如果您是 Office 365 客戶，您可以透過 Office 365 安全性 & 規範中心管理這項功能，與管理未驗證之寄件者處理的方式相同。</span><span class="sxs-lookup"><span data-stu-id="47b27-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="47b27-131">如果您將寄件者新增至欺騙智慧欺騙允許清單，將不會套用「透過」處理。</span><span class="sxs-lookup"><span data-stu-id="47b27-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="47b27-132">常見問題集</span><span class="sxs-lookup"><span data-stu-id="47b27-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="47b27-133">Outlook.com 和 Outlook Win32 桌面使用哪些準則來新增 '？ ' 和「透過」屬性？</span><span class="sxs-lookup"><span data-stu-id="47b27-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="47b27-134">針對寄件者影像中的 '？ '： Outlook.com 要求郵件傳遞 SPF 或 DKIM 驗證，並接收 dmarc pass 或從 Office 365 欺騙智慧的複合驗證傳遞。</span><span class="sxs-lookup"><span data-stu-id="47b27-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="47b27-135">如需詳細資訊，請參閱[在 office 365 中設定 SPF 以協助防止](set-up-spf-in-office-365-to-help-prevent-spoofing.md)詐騙和[使用 DKIM 驗證從您的自訂365網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="47b27-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="47b27-136">在 [via] 標記中：如果 [寄件者] 位址中的網域與 DKIM 簽章中的網域不同，或是來自于 SMTP 郵件，Outlook.com 會顯示這兩個欄位之一的網域（首選 DKIM 簽章）。</span><span class="sxs-lookup"><span data-stu-id="47b27-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="47b27-137">如何在不利用欺騙智慧欺騙允許清單的情況下移除 '？ '？</span><span class="sxs-lookup"><span data-stu-id="47b27-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="47b27-138">針對寄件者映射中的 '？ '：作為寄件者，您應該使用 SPF 或 DKIM 來驗證郵件。</span><span class="sxs-lookup"><span data-stu-id="47b27-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="47b27-139">在 [via] 標記中：作為寄件者，您應該確定 DKIM 簽章中的網域或 SMTP 郵件與「寄件者」位址中的網域相同，或為子域。</span><span class="sxs-lookup"><span data-stu-id="47b27-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="47b27-140">Outlook.com 和 Outlook Win32 桌面會針對所有未通過驗證的郵件顯示此值嗎？</span><span class="sxs-lookup"><span data-stu-id="47b27-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="47b27-141">不一定。</span><span class="sxs-lookup"><span data-stu-id="47b27-141">Not necessarily.</span></span> <span data-ttu-id="47b27-142">Office 365 可能會在郵件中有其他屬性可驗證寄件者。</span><span class="sxs-lookup"><span data-stu-id="47b27-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="47b27-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="47b27-143">Related topics</span></span>

[<span data-ttu-id="47b27-144">協助保護您的 Outlook.com 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="47b27-144">Help protect your Outlook.com email account</span></span>](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="47b27-145">如何處理 Outlook.com 中的網路釣魚</span><span class="sxs-lookup"><span data-stu-id="47b27-145">How to deal with phishing in Outlook.com</span></span>](https://support.microsoft.com/office/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="47b27-146">在網頁上的 Outlook 中篩選垃圾郵件和垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="47b27-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.microsoft.com/office/db786e79-54e2-40cc-904f-d89d57b7f41d)
