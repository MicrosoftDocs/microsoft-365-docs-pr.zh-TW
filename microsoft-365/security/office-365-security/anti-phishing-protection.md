---
title: Office 365 的防網路釣魚保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: 根據預設，office 365 提供各種不同的防範網路釣魚攻擊，也是透過 Office 365 高級威脅防護（ATP）中的其他功能。 本主題將介紹可用於深入瞭解及實施 Office 365 中的反網路釣魚選項與策略的線上資源。
ms.openlocfilehash: 321d983f422bf4d231a772ca445bb74a7150a56e
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537422"
---
# <a name="anti-phishing-protection-in-office-365"></a><span data-ttu-id="e61fa-104">Office 365 的防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="e61fa-104">Anti-phishing protection in Office 365</span></span>

<span data-ttu-id="e61fa-105">*網路釣魚*會嘗試竊取看似來自合法或信任寄件者的郵件中的機密資訊的電子郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="e61fa-105">*Phishing* an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="e61fa-106">有特定類別的網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="e61fa-106">There are specific categories of phishing.</span></span> <span data-ttu-id="e61fa-107">例如：</span><span class="sxs-lookup"><span data-stu-id="e61fa-107">For example:</span></span>

- <span data-ttu-id="e61fa-108">**Spear 網路釣魚**使用專門為目標收件者量身定制之非常專注和自訂的內容（通常是攻擊者在收件者的偵測之後）。</span><span class="sxs-lookup"><span data-stu-id="e61fa-108">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="e61fa-109">**Whaling**是導向組織中的主管或其他高價值目標，以達到最大效果。</span><span class="sxs-lookup"><span data-stu-id="e61fa-109">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="e61fa-110">**商務電子郵件安全（BEC）** 會使用偽造的信任寄件者（財務主管、客戶、信任的合作夥伴等等），以誘騙收件者以核准付款、轉帳基金或公開客戶資料。</span><span class="sxs-lookup"><span data-stu-id="e61fa-110">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="e61fa-111">在網路釣魚郵件中，加密您的資料和要求付款以進行解密的**勒索軟體**幾乎永遠不會開始。</span><span class="sxs-lookup"><span data-stu-id="e61fa-111">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="e61fa-112">反網路釣魚保護無法協助您解密加密的檔案，但可協助偵測與勒索軟體相關的初始網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="e61fa-112">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="e61fa-113">如需從勒索軟體攻擊復原的詳細資訊，請參閱[在 Office 365 中復原從勒索軟體攻擊](recover-from-ransomware.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-113">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Office 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="e61fa-114">隨著攻擊複雜度的日益增加，訓練的使用者甚至很難識別複雜的網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="e61fa-114">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="e61fa-115">幸運的是，Exchange Online Protection （EOP）和 Office 365 高級威脅防護（ATP）中的其他功能都有助您的協助。</span><span class="sxs-lookup"><span data-stu-id="e61fa-115">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="e61fa-116">EOP 中的反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="e61fa-116">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="e61fa-117">EOP （也就是，不含 ATP 的 Office 365 組織）包含可協助您保護組織免受網路釣魚威脅的功能：</span><span class="sxs-lookup"><span data-stu-id="e61fa-117">EOP (that is, Office 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="e61fa-118">**哄騙情報**：查看內部及外部網域中寄件者的欺騙性郵件，並允許或封鎖這些寄件者。</span><span class="sxs-lookup"><span data-stu-id="e61fa-118">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="e61fa-119">如需詳細資訊，請參閱[Configure 哄騙情報 In Office 365](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-119">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="e61fa-120">**預設的反網路釣魚原則**：開啟或關閉欺騙智慧，開啟或關閉 Outlook 中未驗證的寄件者識別，並指定封鎖的欺騙寄件者的動作（移至 [垃圾郵件] 資料夾或 [隔離]）。</span><span class="sxs-lookup"><span data-stu-id="e61fa-120">**Default anti-phishing policy**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="e61fa-121">如需詳細資訊，請參閱[CONFIGURE EOP 中的反網路釣魚原則](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-121">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="e61fa-122">**隱含的電子郵件驗證**： EOP 可增強輸入電子郵件（[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及[DMARC](use-dmarc-to-validate-email.md)）的標準電子郵件驗證檢查，具有寄件者信譽、寄件者記錄、收件者記錄、行為分析，以及其他可協助識別偽造寄件者的高級技術。</span><span class="sxs-lookup"><span data-stu-id="e61fa-122">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="e61fa-123">如需詳細資訊，請參閱[Office 365 中的電子郵件驗證](email-validation-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-123">For more information, see [Email authentication in Office 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="e61fa-124">Office 365 ATP 中的其他反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="e61fa-124">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="e61fa-125">Office 365 ATP 包含更多和更高級的反網路釣魚功能：</span><span class="sxs-lookup"><span data-stu-id="e61fa-125">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="e61fa-126">**ATP 反網路釣魚原則**：建立新的自訂原則、設定反模仿設定（保護使用者和網域不會模仿）、信箱智慧設定，以及可調整的高級網路釣魚臨界值。</span><span class="sxs-lookup"><span data-stu-id="e61fa-126">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="e61fa-127">如需詳細資訊，請參閱[在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-127">For more information, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="e61fa-128">如需反網路釣魚原則和 ATP 反網路釣魚原則之間差異的詳細資訊，請參閱[Office 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-128">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="e61fa-129">**即時檢視**：機器學習和其他試探法識別及分析與整個服務和組織有關之協同網頁網路攻擊的相關訊息。</span><span class="sxs-lookup"><span data-stu-id="e61fa-129">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="e61fa-130">如需詳細資訊，請參閱[Office 365 ATP 中的市場即時檢視](campaigns.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-130">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="e61fa-131">**攻擊模擬器**：系統管理員可以建立虛假的網路釣魚郵件，並以教育工具形式傳送給內部使用者。</span><span class="sxs-lookup"><span data-stu-id="e61fa-131">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="e61fa-132">如需詳細資訊，請參閱[Office 365 ATP 中的攻擊模擬器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-132">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="e61fa-133">其他反網路釣魚資源</span><span class="sxs-lookup"><span data-stu-id="e61fa-133">Other anti-phishing resources</span></span>

- <span data-ttu-id="e61fa-134">針對使用者：[保護您自己免受網路釣魚騙術和其他形式的線上欺詐](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-134">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span></span>

- <span data-ttu-id="e61fa-135">[Office 365 如何驗證寄件者位址，以防止網路釣魚](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="e61fa-135">[How Office 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
