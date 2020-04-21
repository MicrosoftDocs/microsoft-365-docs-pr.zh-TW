---
title: 逐步解說-欺騙性的智慧洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 請參閱 Office 365 的 [高級威脅防護] 中的欺騙智慧洞察力的運作方式。
ms.openlocfilehash: 4ad3de8812e09b73018c02232e3e66e4bec9d041
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630926"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a><span data-ttu-id="7566c-103">逐步解說-在 Microsoft 365 中的 ATP 欺騙智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="7566c-103">Walkthrough - ATP Spoof intelligence insight in Microsoft 365</span></span>

<span data-ttu-id="7566c-104">在使用高級威脅防護（ATP）的 Microsoft 365 組織中，您可以使用哄騙智慧真知灼見，快速判斷哪些寄件者可合法傳送您未驗證的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7566c-104">In Microsoft 365 organizations with Advanced Threat Protection (ATP), you can use the spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email.</span></span> <span data-ttu-id="7566c-105">透過允許他們傳送哄騙郵件，您可以降低任何誤報給使用者的風險。</span><span class="sxs-lookup"><span data-stu-id="7566c-105">By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span> <span data-ttu-id="7566c-106">您也可以使用 [偽造智慧洞察力] 來監視和管理允許的網域對，以提供額外的安全性層級，並防止不安全的郵件到達您的組織中。</span><span class="sxs-lookup"><span data-stu-id="7566c-106">You can also use the spoof intelligence insight to monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="7566c-107">如果您不熟悉[安全性 & 規範中心的報表和洞察力](reports-and-insights-in-security-and-compliance.md)，它可能會協助您瞭解如何輕鬆從儀表板流覽至真知灼見及建議的動作。</span><span class="sxs-lookup"><span data-stu-id="7566c-107">If you're new to [reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>

<span data-ttu-id="7566c-108">此逐步解說是安全性 & 規範中心的其中一項。</span><span class="sxs-lookup"><span data-stu-id="7566c-108">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="7566c-109">若要瞭解如何導覽報表和真知灼見，請參閱相關主題區段中的演練。</span><span class="sxs-lookup"><span data-stu-id="7566c-109">To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7566c-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="7566c-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7566c-111">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="7566c-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7566c-112">若要直接移至 [**安全性] 儀表板**頁面，請使用<https://protection.office.com/searchandinvestigation/dashboard>。</span><span class="sxs-lookup"><span data-stu-id="7566c-112">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="7566c-113">您可以在安全性 & 合規性中心的多個儀表板上查看哄騙智慧洞察力。</span><span class="sxs-lookup"><span data-stu-id="7566c-113">You can view the spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="7566c-114">不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。</span><span class="sxs-lookup"><span data-stu-id="7566c-114">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="7566c-115">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="7566c-115">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7566c-116">若要使用欺騙性智慧洞察力，您必須是「**組織管理**」、「**安全性管理員**」或「**安全性讀者**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7566c-116">To use the spoof intelligence insight, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="7566c-117">如需安全性 & 規範中心中角色群組的詳細資訊，請參閱[安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7566c-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7566c-118">您可以在 ATP 反網路釣魚原則中啟用和停用欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="7566c-118">You enable and disable spoof intelligence in ATP anti-phishing policies.</span></span> <span data-ttu-id="7566c-119">如需詳細資訊，請參閱[在 Microsoft 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7566c-119">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="7566c-120">在包含 Exchange Online 信箱和獨立 Exchange Online Protection （EOP）的 Microsoft 365 組織中，如果沒有 Exchange Online 信箱，您可以使用哄騙智慧來監視和管理您傳送未驗證郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="7566c-120">In Microsoft 365 organizations with Exchange Online mailboxes, and in standalone Exchange Online Protection (EOP) without Exchange Online mailboxes, you can use spoof intelligence to monitor and manage senders you are sending you unauthenticated messages.</span></span> <span data-ttu-id="7566c-121">如需詳細資訊，請參閱[Configure 哄騙情報 In Microsoft 365](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="7566c-121">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="7566c-122">在安全性 & 規範中心開啟欺騙性智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="7566c-122">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="7566c-123">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ]**儀表板。**</span><span class="sxs-lookup"><span data-stu-id="7566c-123">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="7566c-124">在 [**洞察力**] 列中，尋找下列其中一個專案：</span><span class="sxs-lookup"><span data-stu-id="7566c-124">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="7566c-125">**已啟用欺騙情報**：此真知灼見稱為**欺詐網域，其驗證過去30天失敗**。</span><span class="sxs-lookup"><span data-stu-id="7566c-125">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="7566c-126">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="7566c-126">This is the default.</span></span>

   - <span data-ttu-id="7566c-127">**已停用欺騙情報**：以命名方式**啟用欺騙保護**的洞察力，並按一下該功能可讓您啟用欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="7566c-127">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="7566c-128">儀表板上的洞察力顯示如下資訊：</span><span class="sxs-lookup"><span data-stu-id="7566c-128">The insight on the dashboard shows you information like this:</span></span>

   ![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="7566c-130">這兩種洞察力分為兩種模式：</span><span class="sxs-lookup"><span data-stu-id="7566c-130">This insight has two modes:</span></span>

   - <span data-ttu-id="7566c-131">**洞察力模式**。</span><span class="sxs-lookup"><span data-stu-id="7566c-131">**Insight mode**.</span></span> <span data-ttu-id="7566c-132">如果您已啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能會影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="7566c-132">If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="7566c-133">**If 模式**。</span><span class="sxs-lookup"><span data-stu-id="7566c-133">**What if mode**.</span></span> <span data-ttu-id="7566c-134">如果您未啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能*會*影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="7566c-134">If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="7566c-135">無論是哪一種方式，顯示在真知灼見中的冒牌網域都會分為兩類：**可疑的網域配對**和**非可疑網域配對**。</span><span class="sxs-lookup"><span data-stu-id="7566c-135">Either way, the spoofed domains displayed in the insight are separated into two categories: **suspicious domain pairs** and **non-suspicious domain pairs**.</span></span> <span data-ttu-id="7566c-136">這些類別會進一步細分為三個不同的桶，供您審閱。</span><span class="sxs-lookup"><span data-stu-id="7566c-136">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="7566c-137">**網域對**是 [寄件者] 位址及傳送基礎結構的組合：</span><span class="sxs-lookup"><span data-stu-id="7566c-137">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="7566c-138">寄件者位址是顯示在電子郵件客戶程式中的寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7566c-138">The From address is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="7566c-139">此地址可識別電子郵件的作者。</span><span class="sxs-lookup"><span data-stu-id="7566c-139">This address identifies the author of the email.</span></span> <span data-ttu-id="7566c-140">也就是負責撰寫郵件的使用者或系統信箱。</span><span class="sxs-lookup"><span data-stu-id="7566c-140">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="7566c-141">此位址也稱為`5322.From`位址。</span><span class="sxs-lookup"><span data-stu-id="7566c-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="7566c-142">傳送基礎結構（或寄件者）是寄件者 IP 位址的反向 DNS 查找（PTR 記錄）的組織網域。</span><span class="sxs-lookup"><span data-stu-id="7566c-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="7566c-143">如果傳送 IP 位址沒有 PTR 記錄，則寄件者會透過以 CIDR 標記法（/24）的255.255.255.0 子網路遮罩傳送 IP 加以識別。</span><span class="sxs-lookup"><span data-stu-id="7566c-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="7566c-144">例如，如果 IP 位址是192.168.100.100，則寄件者的完整 IP 位址是 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="7566c-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="7566c-145">**可疑的網域配對**包括：</span><span class="sxs-lookup"><span data-stu-id="7566c-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="7566c-146">**高度信賴的哄騙**： Microsoft 365 收到強信號，表示這些網域是可疑的，根據歷史傳送模式和網域的信譽得分。</span><span class="sxs-lookup"><span data-stu-id="7566c-146">**High-confidence spoof**: Microsoft 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="7566c-147">Microsoft 365 非常確信網域是哄騙的，而從這些網域傳送的郵件不太可能合法。</span><span class="sxs-lookup"><span data-stu-id="7566c-147">Microsoft 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span>

   - <span data-ttu-id="7566c-148">「**可信哄騙**」： Microsoft 365 收到的是這些網域是可疑的，根據歷史傳送模式和網域的信譽分數。</span><span class="sxs-lookup"><span data-stu-id="7566c-148">**Moderate confidence spoof**: Microsoft 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="7566c-149">Office 365 適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。</span><span class="sxs-lookup"><span data-stu-id="7566c-149">Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="7566c-150">此 bucket 有更多的可能性包含誤報（FPs）的高可信度。</span><span class="sxs-lookup"><span data-stu-id="7566c-150">This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span>

   - <span data-ttu-id="7566c-151">**非可疑的網域配對**（包括**rescued 欺騙**）： rescued 欺騙指的是未通過明確驗證檢查[SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)）的網域，但已通過我們的隱含電子郵件驗證檢查（[複合驗證](email-validation-and-authentication.md#composite-authentication)）。</span><span class="sxs-lookup"><span data-stu-id="7566c-151">**Non-suspicious domain pairs** (includes **rescued spoof**): Rescued spoof are domains that have failed the explicit authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) but passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="7566c-152">因此，Microsoft 365 會代表您 rescued 郵件，而且不會對郵件採取任何反欺詐動作。</span><span class="sxs-lookup"><span data-stu-id="7566c-152">As a result, Microsoft 365 rescued the mail on your behalf and no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="7566c-153">從哄騙情報洞察力中查看有關可疑網域配對的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7566c-153">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="7566c-154">在 [偽造智慧洞察力] 中，按一下 [任何網域配對] （high、適中或 rescued）。</span><span class="sxs-lookup"><span data-stu-id="7566c-154">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="7566c-155">隨即會出現 [**哄騙智慧真知灼見**] 頁面，顯示將未驗證郵件傳送至組織的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="7566c-155">The **Spoof Intelligence insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization.</span></span> <span data-ttu-id="7566c-156">此頁面上的資訊可協助您判斷是否已授權哄騙郵件，或者是否需要進一步採取動作。</span><span class="sxs-lookup"><span data-stu-id="7566c-156">The information on this page helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span> <span data-ttu-id="7566c-157">您可以依郵件計數、上一次偵測欺騙的日期等等來排序資訊。</span><span class="sxs-lookup"><span data-stu-id="7566c-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span> <span data-ttu-id="7566c-158">（例如，按一下 [**郵件計數**] 或 [**最後一個看到**的列標題]）。</span><span class="sxs-lookup"><span data-stu-id="7566c-158">(Click column headings, such as **Message count** or **Last seen**, for example.)</span></span>

2. <span data-ttu-id="7566c-159">選取表格中的專案，以開啟包含有關網域對之豐富資訊的詳細資訊窗格，包括以下的原因：我們所做的，您需要做的是，您需要做的是，一個網域摘要，WhoIs 有關寄件者的相關電子郵件，以及我們在您的租使用者中所看到的類似電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7566c-159">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender.</span></span> <span data-ttu-id="7566c-160">在這裡，您也可以選擇從**AllowedToSpoof**安全寄件者清單中新增或移除網域對。</span><span class="sxs-lookup"><span data-stu-id="7566c-160">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="7566c-162">從 AllowedToSpoof 安全寄件者清單中新增或移除網域</span><span class="sxs-lookup"><span data-stu-id="7566c-162">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="7566c-163">您可以從 AllowedToSpoof 安全的寄件者清單中新增或移除網域，在 [欺騙性智慧洞察力] 的 [詳細資料] 窗格中檢查網域對。</span><span class="sxs-lookup"><span data-stu-id="7566c-163">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight.</span></span> <span data-ttu-id="7566c-164">只會據此設定切換。</span><span class="sxs-lookup"><span data-stu-id="7566c-164">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="7566c-165">這會修改欺騙性網域和傳送基礎結構的唯一網域組合，不會對整個冒牌網域或獨立傳送基礎結構提供覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="7566c-165">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation.</span></span>

<span data-ttu-id="7566c-166">例如，如果您將下列網域對新增至 ' AllowedToSpoof ' 寄件者允許清單：*冒牌網域*"gmail.com"，並傳送*基礎結構*" *mx.com"，* 則只有該網域對中的郵件才會遭到欺騙。</span><span class="sxs-lookup"><span data-stu-id="7566c-166">For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and *Sending Infrastructure* "tms *.mx.com",* then only mail from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="7566c-167">其他企圖哄騙 "gmail.com" 的寄件者，以及其他「tms.mx.com」嘗試欺騙的網域，會繼續受到欺騙智慧的保護。</span><span class="sxs-lookup"><span data-stu-id="7566c-167">Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7566c-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="7566c-168">Related topics</span></span>

[<span data-ttu-id="7566c-169">Microsoft 365 中的反欺騙保護</span><span class="sxs-lookup"><span data-stu-id="7566c-169">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="7566c-170">逐步解說 - 從儀表板到深入解析</span><span class="sxs-lookup"><span data-stu-id="7566c-170">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)

[<span data-ttu-id="7566c-171">逐步解說 - 從詳細報告到深入解析</span><span class="sxs-lookup"><span data-stu-id="7566c-171">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)

[<span data-ttu-id="7566c-172">逐步解說 - 從深入解析到詳細報告</span><span class="sxs-lookup"><span data-stu-id="7566c-172">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)