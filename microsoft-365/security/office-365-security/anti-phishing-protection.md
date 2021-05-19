---
title: 防網路釣魚保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的反網路釣魚保護功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 290f5f7797d987fb65a99e3f9e656bfec4cf83f3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538336"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="9e8ea-103">Microsoft 365 中的反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="9e8ea-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9e8ea-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="9e8ea-104">**Applies to**</span></span>
- [<span data-ttu-id="9e8ea-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9e8ea-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9e8ea-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="9e8ea-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9e8ea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e8ea-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9e8ea-108">*網路釣魚* 是一種電子郵件攻擊，會在看似來自合法或信任寄件者的訊息中嘗試竊取敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="9e8ea-109">有特定類別的網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-109">There are specific categories of phishing.</span></span> <span data-ttu-id="9e8ea-110">例如：</span><span class="sxs-lookup"><span data-stu-id="9e8ea-110">For example:</span></span>

- <span data-ttu-id="9e8ea-111">**Spear 網路釣魚** 使用具有焦點的自訂內容，專門為目標收件者量身定制 (一般會在攻擊者) 後，在收件者上偵測之後。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="9e8ea-112">**Whaling** 是導向組織中的主管或其他高價值目標，以達到最大效果。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="9e8ea-113">**商務電子郵件洩漏 (BEC)** 使用偽造的信任寄件者 (財務主管、客戶、信任的協力廠商等。 ) 欺騙收件者以核准付款、轉帳基金或透露客戶資料。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span> <span data-ttu-id="9e8ea-114">觀看[此影片](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-114">Learn more by watching [this video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).</span></span>

- <span data-ttu-id="9e8ea-115">在網路釣魚郵件中，加密您的資料和要求付款以進行解密的 **勒索軟體** 幾乎永遠不會開始。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-115">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="9e8ea-116">反網路釣魚保護無法協助您解密加密的檔案，但可協助偵測與勒索軟體相關的初始網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-116">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="9e8ea-117">如需從勒索軟體攻擊復原的詳細資訊，請參閱[從 Microsoft 365 中的勒索軟體復原](recover-from-ransomware.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-117">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="9e8ea-118">隨著攻擊複雜度的日益增加，訓練的使用者甚至很難識別複雜的網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-118">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="9e8ea-119">幸運的是，Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的其他功能都有助。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-119">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="9e8ea-120">EOP 中的防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="9e8ea-120">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="9e8ea-121">EOP (，也就是 Microsoft 365 沒有 Microsoft Defender for Office 365) 的功能包含可協助您保護組織免受網路釣魚威脅的功能：</span><span class="sxs-lookup"><span data-stu-id="9e8ea-121">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="9e8ea-122">欺詐 **情報**：使用哄騙情報洞察力，以查看來自外部和內部網域之郵件中的欺騙寄件者，並手動允許或封鎖所偵測到的寄件者。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-122">**Spoof intelligence**: Use the spoof intelligence insight to review detected spoofed senders in messages from external and internal domains, and manually allow or block those detected senders.</span></span> <span data-ttu-id="9e8ea-123">如需詳細資訊，請參閱 [EOP 中的欺騙智慧洞察力](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-123">For more information, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="9e8ea-124">**EOP 中的反網路釣魚原則**：開啟或關閉欺騙智慧，開啟或關閉 Outlook 中的未驗證寄件者識別碼，並指定封鎖的欺騙寄件者的動作。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-124">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders.</span></span> <span data-ttu-id="9e8ea-125">如需詳細資訊，請參閱 [CONFIGURE EOP 中的反網路釣魚原則](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-125">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="9e8ea-126">**允許或封鎖租使用者在承租人允許/封鎖清單中**：當您覆寫欺騙智慧洞察力中的判定時，欺騙寄件者會變成隻會出現在 [租使用者允許/封鎖] 清單的 [ **偽造** ] 索引標籤上的 [手動允許] 或 [封鎖] 專案。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-126">**Allow or block spoofed senders in the Tenant Allow/Block List**: When you override the verdict in the spoof intelligence insight, the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="9e8ea-127">您也可以手動為欺騙寄件者建立允許或封鎖專案，以取得欺騙性的智慧。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-127">You can also manually create allow or block entries for spoof senders before they're detected by spoof intelligence.</span></span> <span data-ttu-id="9e8ea-128">如需詳細資訊，請參閱 [管理 EOP 中的承租人 Allow/封鎖清單](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-128">For more information, see [Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="9e8ea-129">**隱含電子郵件驗證**： EOP 可增強內送)  (電子郵件的標準電子郵件 [](use-dmarc-to-validate-email.md) [驗證檢查](set-up-spf-in-office-365-to-help-prevent-spoofing.md)，包括發 [件人信譽](use-dkim-to-validate-outbound-email.md)、寄件者記錄、收件者記錄、行為分析和其他高級技巧，以協助識別偽造的寄件者。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-129">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="9e8ea-130">如需詳細資訊，請參閱 [Microsoft 365 中的電子郵件驗證](email-validation-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-130">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e8ea-131">適用於 Office 365 的 Microsoft Defender 中的防網路釣魚防護</span><span class="sxs-lookup"><span data-stu-id="9e8ea-131">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9e8ea-132">適用於 Office 365 的 Microsoft Defender 包含額外和進階的防網路釣魚功能：</span><span class="sxs-lookup"><span data-stu-id="9e8ea-132">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="9e8ea-133">**Microsoft Defender 中 Office 365 的反網路釣魚原則**：針對特定郵件寄件者和寄件者網域、信箱智慧設定及可調整的高級網路釣魚臨界值，設定模擬防護設定。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-133">**Anti-phishing policies in Microsoft Defender for Office 365**: Configure impersonation protection settings for specific message senders and sender domains, mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="9e8ea-134">如需詳細資訊，請參閱[Configure Office 365 的 Microsoft Defender 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-134">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="9e8ea-135">如需 EOP 中 Office 365 和反網路釣魚原則中的反網路釣魚原則之間差異的詳細資訊，請參閱[Microsoft 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-135">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="9e8ea-136">**即時檢視**：機器學習和其他試探法識別及分析與整個服務和組織有關之協同網頁網路攻擊的相關訊息。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-136">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="9e8ea-137">如需詳細資訊，請參閱[Microsoft Defender 中 Office 365 的市場即時檢視](campaigns.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-137">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="9e8ea-138">**攻擊模擬器**：系統管理員可以建立虛假的網路釣魚郵件，並以教育工具形式傳送給內部使用者。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-138">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="9e8ea-139">如需詳細資訊，請參閱[適用于 Microsoft Defender 的 Office 365 中的攻擊模擬器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-139">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="9e8ea-140">其他反網路釣魚資源</span><span class="sxs-lookup"><span data-stu-id="9e8ea-140">Other anti-phishing resources</span></span>

- <span data-ttu-id="9e8ea-141">針對使用者： [從網路釣魚騙術和其他形式的線上欺詐進行保護](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-141">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="9e8ea-142">[Microsoft 365 如何驗證寄件者位址，以防止網路釣魚](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="9e8ea-142">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
