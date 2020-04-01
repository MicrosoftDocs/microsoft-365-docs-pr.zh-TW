---
title: 欺騙情報探索的演練
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/30/2018
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
description: 請參閱新的欺騙性智慧洞察力的運作方式。
ms.openlocfilehash: 797cbc07fd068ae80edc6cea699f78b2304a8f6c
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081409"
---
# <a name="walkthrough-spoof-intelligence-insight"></a><span data-ttu-id="ac029-103">逐步解說：欺騙性智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="ac029-103">Walkthrough: spoof intelligence insight</span></span>

<span data-ttu-id="ac029-104">透過使用哄騙智慧洞察力，您可以快速判斷哪些寄件者可合法傳送您未驗證的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac029-104">By using the Spoof Intelligence insight, you can quickly determine which senders are legitimately sending you unauthenticated email.</span></span> <span data-ttu-id="ac029-105">透過允許他們傳送哄騙郵件，您可以降低任何誤報給使用者的風險。</span><span class="sxs-lookup"><span data-stu-id="ac029-105">By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span>

<span data-ttu-id="ac029-106">此外，您也可以使用 [偽造智慧監視器] 和 [管理允許的網域對]，以提供額外的安全性層級，並防止不安全的郵件到達您的組織中。</span><span class="sxs-lookup"><span data-stu-id="ac029-106">In addition, you can also use Spoof Intelligence monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="ac029-107">如果您的工作或學校帳戶已具備 Office &amp; 365 全域系統管理員、安全性管理員或安全性讀取者的許可權，您可以使用安全規範中心中的欺騙智慧洞察力。</span><span class="sxs-lookup"><span data-stu-id="ac029-107">You can use the spoof intelligence insight in the Security &amp; Compliance Center if your work or school account has been given Office 365 global administrator, security administrator, or security reader permissions.</span></span> <span data-ttu-id="ac029-108">如需詳細資訊，請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ac029-108">For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="ac029-109">如果您是[Office 365 安全性&amp;與合規性中心內的報表和洞察力的](reports-and-insights-in-security-and-compliance.md)最新資訊，它可能會協助您瞭解如何輕鬆從儀表板流覽至真知灼見及建議的動作。</span><span class="sxs-lookup"><span data-stu-id="ac029-109">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>

<span data-ttu-id="ac029-110">您可以在安全性&amp;與合規性中心的多個儀表板上查看哄騙智慧洞察力。</span><span class="sxs-lookup"><span data-stu-id="ac029-110">You can view the spoof intelligence insight from more than one dashboard in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ac029-111">不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。</span><span class="sxs-lookup"><span data-stu-id="ac029-111">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

<span data-ttu-id="ac029-112">這是安全性&amp;與合規性中心的幾個演練中的其中一個。</span><span class="sxs-lookup"><span data-stu-id="ac029-112">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ac029-113">若要瞭解如何導覽報表和真知灼見，請參閱相關主題區段中的演練。</span><span class="sxs-lookup"><span data-stu-id="ac029-113">To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>

## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a><span data-ttu-id="ac029-114">取得安全性&amp;與合規性中心的欺騙智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="ac029-114">Getting to the spoof intelligence insight in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="ac029-115">若要開始，您需要[移至安全性&amp;與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ac029-115">To get started, you'll need [go to the Security &amp; Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="ac029-116">在安全性&amp;與合規性中心，移至 [**威脅管理** \> **儀表板]。**</span><span class="sxs-lookup"><span data-stu-id="ac029-116">In the Security &amp; Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

3. <span data-ttu-id="ac029-117">在 [**洞察力**] 列中，尋找 [偽造智慧洞察力]。</span><span class="sxs-lookup"><span data-stu-id="ac029-117">In the **Insights** row, look for the spoof intelligence insight.</span></span> <span data-ttu-id="ac029-118">如果您已啟用欺騙情報，則真知灼見會有權**驗證過去30天內驗證失敗的欺騙性網域**。</span><span class="sxs-lookup"><span data-stu-id="ac029-118">If you have enabled spoof intelligence, then the insight is entitled **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="ac029-119">如果您尚未啟用欺騙保護，則真知灼見會提示您使用標題 [**啟用欺騙防護**] 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ac029-119">If you haven't enabled spoof protection, then the insight will prompt you to do so by using the title **Enable Spoof Protection**.</span></span>

## <a name="about-the-insight-on-the-dashboard"></a><span data-ttu-id="ac029-120">關於儀表板上的洞察力</span><span class="sxs-lookup"><span data-stu-id="ac029-120">About the insight on the dashboard</span></span>

<span data-ttu-id="ac029-121">儀表板上的洞察力顯示如下所示的資訊。</span><span class="sxs-lookup"><span data-stu-id="ac029-121">The insight on the dashboard shows you information like this.</span></span>

![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

<span data-ttu-id="ac029-123">這兩種洞察力分為兩種模式：</span><span class="sxs-lookup"><span data-stu-id="ac029-123">This insight has two modes:</span></span>

 <span data-ttu-id="ac029-124">**洞察力模式**。</span><span class="sxs-lookup"><span data-stu-id="ac029-124">**Insight mode**.</span></span> <span data-ttu-id="ac029-125">如果您已啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能會影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ac029-125">If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

 <span data-ttu-id="ac029-126">**If 模式**。</span><span class="sxs-lookup"><span data-stu-id="ac029-126">**What if mode**.</span></span> <span data-ttu-id="ac029-127">如果您未啟用任何欺騙原則，則真知灼見會顯示過去30天內，我們的欺騙智慧功能*會*影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ac029-127">If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

<span data-ttu-id="ac029-128">無論是哪種方式，顯示在真知灼見中的冒牌網域都會分為兩類;可疑的網域配對和非可疑的網域配對。</span><span class="sxs-lookup"><span data-stu-id="ac029-128">Either way, the spoofed domains displayed in the insight are separated into two categories; suspicious domain pairs and non-suspicious domain pairs.</span></span> <span data-ttu-id="ac029-129">這些類別會進一步細分為三個不同的桶，供您審閱。</span><span class="sxs-lookup"><span data-stu-id="ac029-129">These categories are further subdivided into three different buckets for you to review.</span></span> 

<span data-ttu-id="ac029-130">*網域對*是 [寄件者：] 位址和傳送基礎結構的組合。</span><span class="sxs-lookup"><span data-stu-id="ac029-130">A  *domain pair*  is a combination of the "From:" address and the sending infrastructure.</span></span> 

- <span data-ttu-id="ac029-131">「寄件者」位址是您的郵件應用程式顯示為 [寄件者] 位址的位址。</span><span class="sxs-lookup"><span data-stu-id="ac029-131">The "From" address is the address displayed as the From address by your mail application.</span></span> <span data-ttu-id="ac029-132">此地址可識別電子郵件的作者。</span><span class="sxs-lookup"><span data-stu-id="ac029-132">This address identifies the author of the email.</span></span> <span data-ttu-id="ac029-133">也就是負責撰寫郵件的使用者或系統信箱。</span><span class="sxs-lookup"><span data-stu-id="ac029-133">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="ac029-134">這有時稱為 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="ac029-134">This is sometimes called the 5322.From address.</span></span>

- <span data-ttu-id="ac029-135">傳送基礎結構（或寄件者）是寄件者 IP 位址之 PTR 記錄的組織網域。</span><span class="sxs-lookup"><span data-stu-id="ac029-135">The sending infrastructure, or sender, is the organizational domain of the PTR record of the sending IP address.</span></span> <span data-ttu-id="ac029-136">如果傳送 IP 位址沒有 PTR 記錄，則寄件者會透過以 CIDR 標記法（/24）的255.255.255.0 子網路遮罩傳送 IP 加以識別。</span><span class="sxs-lookup"><span data-stu-id="ac029-136">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="ac029-137">例如，如果 IP 位址是192.168.100.100，則寄件者的完整 IP 位址是 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="ac029-137">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

 <span data-ttu-id="ac029-138">**可疑的網域配對**包括：</span><span class="sxs-lookup"><span data-stu-id="ac029-138">**Suspicious domain pairs** include:</span></span>

- <span data-ttu-id="ac029-139">**高度信賴欺騙**。</span><span class="sxs-lookup"><span data-stu-id="ac029-139">**High-confidence spoof**.</span></span> <span data-ttu-id="ac029-140">Office 365 收到強信號，指出這些網域是可疑的，根據歷史傳送模式和網域的信譽分數而定。</span><span class="sxs-lookup"><span data-stu-id="ac029-140">Office 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="ac029-141">Office 365 非常確信網域是哄騙的，而從這些網域傳送的郵件則不太可能合法。</span><span class="sxs-lookup"><span data-stu-id="ac029-141">Office 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span> 

- <span data-ttu-id="ac029-142">**適中置信欺騙**。</span><span class="sxs-lookup"><span data-stu-id="ac029-142">**Moderate confidence spoof**.</span></span> <span data-ttu-id="ac029-143">Office 365 收到適中的信號，這些網域會根據歷史傳送模式和網域的信譽分數，來表示這些網域是可疑的。</span><span class="sxs-lookup"><span data-stu-id="ac029-143">Office 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="ac029-144">Office 365 適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。</span><span class="sxs-lookup"><span data-stu-id="ac029-144">Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="ac029-145">此 bucket 有更多的可能性包含誤報（FPs）的高可信度。</span><span class="sxs-lookup"><span data-stu-id="ac029-145">This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span>

 <span data-ttu-id="ac029-146">**非可疑的網域配對**包括**rescued 欺騙**。</span><span class="sxs-lookup"><span data-stu-id="ac029-146">**Non-suspicious domain pairs** include **rescued spoof**.</span></span> <span data-ttu-id="ac029-147">Rescued 欺騙是指失敗明確驗證檢查[SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)）的網域，但傳遞的是延伸驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="ac029-147">Rescued spoof are domains that have failed the explicit authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) but passed our extended authentication checks.</span></span> <span data-ttu-id="ac029-148">因此，Office 365 會以您的身分 rescued 郵件，而且不會對郵件採取任何反欺詐動作。</span><span class="sxs-lookup"><span data-stu-id="ac029-148">As a result of this, Office 365 rescued the mail on your behalf and no anti-spoofing action was taken on the mail.</span></span>

## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="ac029-149">從哄騙情報洞察力中查看有關可疑網域配對的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ac029-149">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="ac029-150">在 [偽造智慧洞察力] 中，按一下 [任何網域配對] （high、適中或 rescued）。</span><span class="sxs-lookup"><span data-stu-id="ac029-150">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

<span data-ttu-id="ac029-151">隨即會出現 [**哄騙智慧真知灼見**] 頁面，顯示將未驗證郵件傳送至組織的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="ac029-151">The **Spoof Intelligence Insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization.</span></span> <span data-ttu-id="ac029-152">此頁面上的資訊可協助您判斷是否已授權哄騙郵件，或者您是否需要進一步採取動作。</span><span class="sxs-lookup"><span data-stu-id="ac029-152">The information on this page helps you determine whether spoofed messages are authorized or not or if you need to take further action.</span></span> <span data-ttu-id="ac029-153">您可以依郵件計數、上一次偵測欺騙的日期等等來排序資訊。</span><span class="sxs-lookup"><span data-stu-id="ac029-153">You can sort the information by message count, the date the spoof was last detected, and more.</span></span> <span data-ttu-id="ac029-154">（例如，按一下 [**郵件計數**] 或 [**最後一個看到**的列標題]）。</span><span class="sxs-lookup"><span data-stu-id="ac029-154">(Click column headings, such as **Message count** or **Last seen**, for example.)</span></span>

2. <span data-ttu-id="ac029-155">選取表格中的專案，以開啟包含有關網域對之豐富資訊的詳細資訊窗格，包括以下的原因：我們所做的，您需要做的是，您需要做的是，一個網域摘要，WhoIs 有關寄件者的相關電子郵件，以及我們在您的租使用者中所看到的類似電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ac029-155">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender.</span></span> <span data-ttu-id="ac029-156">在這裡，您也可以選擇從**AllowedToSpoof**安全寄件者清單中新增或移除網域對。</span><span class="sxs-lookup"><span data-stu-id="ac029-156">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="ac029-158">從 AllowedToSpoof 安全寄件者清單中新增或移除網域</span><span class="sxs-lookup"><span data-stu-id="ac029-158">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="ac029-159">您可以從 AllowedToSpoof 安全的寄件者清單中新增或移除網域，在 [欺騙性智慧洞察力] 的 [詳細資料] 窗格中檢查網域對。</span><span class="sxs-lookup"><span data-stu-id="ac029-159">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight.</span></span> <span data-ttu-id="ac029-160">只會據此設定切換。</span><span class="sxs-lookup"><span data-stu-id="ac029-160">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="ac029-161">這會修改欺騙性網域和傳送基礎結構的唯一網域組合，不會對整個冒牌網域或獨立傳送基礎結構提供覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="ac029-161">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation.</span></span> <span data-ttu-id="ac029-162">例如，如果您將下列網域對新增至 ' AllowedToSpoof ' 寄件者允許清單：*冒牌網域*"gmail.com"，並傳送*基礎結構*" *mx.com"，* 則只有該網域對中的郵件才會遭到欺騙。</span><span class="sxs-lookup"><span data-stu-id="ac029-162">For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and  *Sending Infrastructure*  "tms  *.mx.com",*  then only mail from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="ac029-163">其他企圖哄騙 "gmail.com" 的寄件者，以及其他「tms.mx.com」嘗試欺騙的網域，會繼續受到欺騙智慧的保護。</span><span class="sxs-lookup"><span data-stu-id="ac029-163">Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac029-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="ac029-164">Related topics</span></span>

[<span data-ttu-id="ac029-165">深入了解詐騙情報</span><span class="sxs-lookup"><span data-stu-id="ac029-165">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)

[<span data-ttu-id="ac029-166">Office 365 的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="ac029-166">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="ac029-167">逐步解說 - 從儀表板到深入解析</span><span class="sxs-lookup"><span data-stu-id="ac029-167">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)

[<span data-ttu-id="ac029-168">逐步解說 - 從詳細報告到深入解析</span><span class="sxs-lookup"><span data-stu-id="ac029-168">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)

[<span data-ttu-id="ac029-169">逐步解說 - 從深入解析到詳細報告</span><span class="sxs-lookup"><span data-stu-id="ac029-169">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)


