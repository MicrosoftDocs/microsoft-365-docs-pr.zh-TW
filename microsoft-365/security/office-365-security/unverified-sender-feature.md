---
title: 未驗證的寄件者
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
description: 若要防止網路釣魚郵件送達您的信箱，Outlook.com 和網頁型 Outlook 確認寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。
ms.openlocfilehash: a6ae80adb9ddae2c675e75d747dda27f09a404fb
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957248"
---
# <a name="unverified-sender"></a><span data-ttu-id="4d914-103">未驗證的寄件者</span><span class="sxs-lookup"><span data-stu-id="4d914-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="4d914-104">這些更新會循環現在，而且可能無法提供給所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4d914-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="4d914-105">這項功能被支援企業 Outlook.com 和企業 Outlook Win32 桌面的使用者。</span><span class="sxs-lookup"><span data-stu-id="4d914-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="4d914-106">它不是目前適用於家庭用戶 Office 365 使用者。</span><span class="sxs-lookup"><span data-stu-id="4d914-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="4d914-107">若要防止網路釣魚郵件送達您的信箱，Office 365 會驗證寄件者是誰他們說他們且可疑的郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="4d914-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d914-108">將郵件標記為網路釣魚詐騙郵件時，Outlook 就會顯示警告] 頁面頂端，但仍然可以開啟任何郵件中的連結。</span><span class="sxs-lookup"><span data-stu-id="4d914-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="4d914-109">如何識別我的收件匣中的可疑的郵件？</span><span class="sxs-lookup"><span data-stu-id="4d914-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="4d914-110">郵件的寄件者也無法識別或其身分識別是不同於從地址中看到的內容時，outlook 會顯示標記。</span><span class="sxs-lookup"><span data-stu-id="4d914-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="4d914-111">您會看到 '？ ' 中的寄件者影像</span><span class="sxs-lookup"><span data-stu-id="4d914-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="4d914-112">Office 365 無法驗證使用電子郵件驗證技術，寄件者的身分識別時 '？ ' 顯示寄件者映像中。</span><span class="sxs-lookup"><span data-stu-id="4d914-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![郵件未通過驗證](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="4d914-114">若要驗證失敗不是每個訊息是惡意。</span><span class="sxs-lookup"><span data-stu-id="4d914-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="4d914-115">不過，您應該謹慎互動與未驗證如果您不能辨識寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="4d914-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="4d914-116">或者，如果您辨識通常沒有寄件者 '？ ' 寄件者的影像，但您突然開始看到它，可能會登寄件者詐騙。</span><span class="sxs-lookup"><span data-stu-id="4d914-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="4d914-117">如何管理哪些郵件接收未驗證的寄件者處理方式</span><span class="sxs-lookup"><span data-stu-id="4d914-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="4d914-118">如果您是 Office 365 客戶可以管理此功能透過 Office 365 安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="4d914-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="4d914-119">安全性 & 合規性中心，全域或安全性系統管理員可以關閉透過反 Phish 原則] 底下的反詐騙保護功能，開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="4d914-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="4d914-120">此外，您可以使用**Set AntiPhishPolicy**指令程式在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4d914-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="4d914-121">如需詳細資訊，請參閱[在 Office 365 中的反網路釣魚保護](anti-phishing-protection.md)及 [設定 AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)。</span><span class="sxs-lookup"><span data-stu-id="4d914-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![編輯的圖形介面中的未驗證寄件者。](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="4d914-123">如果系統管理員已識別為誤判，而寄件者應該不會收到未驗證的寄件者處理方式，其中一個下列動作可以採取新增至詐騙智慧詐騙的寄件者允許清單：</span><span class="sxs-lookup"><span data-stu-id="4d914-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="4d914-124">加入網域組經由詐騙智慧深入解析。</span><span class="sxs-lookup"><span data-stu-id="4d914-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="4d914-125">如需詳細資訊，請參閱[逐步解說： 詐騙智慧深入了解](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="4d914-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="4d914-126">加入網域組經由**Set-phishfilterpolicy** cmdlet 在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4d914-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="4d914-127">如需詳細資訊，請參閱[Set-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)和[設定 Office 365 ATP 防網路釣魚和防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4d914-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="4d914-128">此外，我們不適用未驗證的寄件者處理方式，如果郵件已傳遞至郵件流程規則 （也稱為傳輸規則） 透過收件匣] 或 [安全的網域清單 （反垃圾郵件原則）。</span><span class="sxs-lookup"><span data-stu-id="4d914-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="4d914-129">如何管理透過' 標記</span><span class="sxs-lookup"><span data-stu-id="4d914-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="4d914-130">如果您是 Office 365 客戶可以管理此功能透過 Office 365 安全性 & 合規性中心，您管理未驗證的寄件者處理方式的相同方式。</span><span class="sxs-lookup"><span data-stu-id="4d914-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="4d914-131">如果您新增寄件者詐騙允許詐騙智慧清單中，將不會套用透過' 處理方式。</span><span class="sxs-lookup"><span data-stu-id="4d914-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="4d914-132">常見問題集</span><span class="sxs-lookup"><span data-stu-id="4d914-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="4d914-133">準則沒有新增 Outlook.com 和 Outlook Win32 桌面使用 '？ ' 和 '透過' 屬性？</span><span class="sxs-lookup"><span data-stu-id="4d914-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="4d914-134">為 '？ ' 中的寄件者影像： Outlook.com 需要郵件通過 SPF 或 DKIM 驗證，並將會收到任一 dmarc 複雜，或從 Office 365 詐騙情報傳遞複合驗證。</span><span class="sxs-lookup"><span data-stu-id="4d914-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="4d914-135">如需詳細資訊，請參閱[Set up SPF in Office 365，以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="4d914-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="4d914-136">針對透過標記： Outlook.com 中自地址的網域不同網域的 DKIM 簽章或 SMTP MAIL FROM 中時，顯示在兩個欄位 （偏好的 DKIM 簽章） 的其中一個網域。</span><span class="sxs-lookup"><span data-stu-id="4d914-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="4d914-137">如何移除 '？ ' 而不需使用詐騙智慧詐騙允許清單？</span><span class="sxs-lookup"><span data-stu-id="4d914-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="4d914-138">為 '？ ' 中的寄件者影像： 為寄件者，您應該驗證與 SPF 或 DKIM 郵件。</span><span class="sxs-lookup"><span data-stu-id="4d914-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="4d914-139">針對透過標記： 為寄件者，您應該確定是在 DKIM 簽章的網域或 SMTP 郵件從相同，或是的在 [從地址的網域子網域。</span><span class="sxs-lookup"><span data-stu-id="4d914-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="4d914-140">Outlook.com 和 Outlook Win32 桌面顯示這不會通過驗證每封郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="4d914-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="4d914-141">不是一定。</span><span class="sxs-lookup"><span data-stu-id="4d914-141">Not necessarily.</span></span> <span data-ttu-id="4d914-142">Office 365 可能已驗證寄件者的郵件內的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="4d914-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d914-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="4d914-143">Related topics</span></span>

[<span data-ttu-id="4d914-144">協助保護您的 Outlook.com 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="4d914-144">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="4d914-145">處理網路釣魚或 Outlook.com 中詐騙</span><span class="sxs-lookup"><span data-stu-id="4d914-145">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="4d914-146">篩選垃圾電子郵件和網頁型 Outlook 中的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="4d914-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
