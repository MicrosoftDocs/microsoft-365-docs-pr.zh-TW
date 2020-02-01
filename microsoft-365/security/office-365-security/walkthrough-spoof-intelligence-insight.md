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
description: 請參閱 < 新的詐騙智慧深入了解的運作方式。
ms.openlocfilehash: 38bf75a2ebeabd41aace42c6116d37ecbe28a2de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598010"
---
# <a name="walkthrough-spoof-intelligence-insight"></a><span data-ttu-id="129bb-103">逐步解說： 詐騙智慧深入解析</span><span class="sxs-lookup"><span data-stu-id="129bb-103">Walkthrough: spoof intelligence insight</span></span>

<span data-ttu-id="129bb-104">藉由使用詐騙智慧深入見解，您可以快速地判斷哪一個寄件者合法傳送未驗證電子郵件。</span><span class="sxs-lookup"><span data-stu-id="129bb-104">By using the Spoof Intelligence insight, you can quickly determine which senders are legitimately sending you unauthenticated email.</span></span> <span data-ttu-id="129bb-105">藉由允許他們傳送冒名的郵件，您可以降低風險的任何誤判移至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="129bb-105">By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span>
  
<span data-ttu-id="129bb-106">此外，您也可以使用詐騙智慧監視及管理允許的網域-配對，以提供額外的安全性層級，並防止不安全的郵件抵達您組織中。</span><span class="sxs-lookup"><span data-stu-id="129bb-106">In addition, you can also use Spoof Intelligence monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>
  
<span data-ttu-id="129bb-107">您可以使用詐騙智慧深入了解安全性&amp;合規性中心，如果您的公司或學校帳戶具有 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取權限。</span><span class="sxs-lookup"><span data-stu-id="129bb-107">You can use the spoof intelligence insight in the Security &amp; Compliance Center if your work or school account has been given Office 365 global administrator, security administrator, or security reader permissions.</span></span> <span data-ttu-id="129bb-108">如需詳細資訊，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="129bb-108">For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="129bb-109">如果您是初次使用[報表和深入了解 Office 365 安全性&amp;合規性中心](reports-and-insights-in-security-and-compliance.md)，它可能會說明若要查看如何您可以輕鬆地瀏覽從儀表板到深入見解和建議的動作。</span><span class="sxs-lookup"><span data-stu-id="129bb-109">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>
  
<span data-ttu-id="129bb-110">您可以檢視從多個儀表板詐騙智慧深入了解安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="129bb-110">You can view the spoof intelligence insight from more than one dashboard in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="129bb-111">不論您正在尋找在哪一個儀表板，深入了解提供相同的詳細資訊，並可讓您快速地執行相同工作。</span><span class="sxs-lookup"><span data-stu-id="129bb-111">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>
  
<span data-ttu-id="129bb-112">這是下列其中一個安全性的幾個逐步解說&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="129bb-112">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="129bb-113">若要瀏覽報表和深入資訊，請參閱 [相關的主題] 區段中的逐步解說。</span><span class="sxs-lookup"><span data-stu-id="129bb-113">To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a><span data-ttu-id="129bb-114">易於存取安全性詐騙智慧深入見解&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="129bb-114">Getting to the spoof intelligence insight in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="129bb-115">若要開始，您將需要[移至安全性&amp;合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="129bb-115">To get started, you'll need [go to the Security &amp; Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="129bb-116">安全性&amp;合規性中心，移至**威脅管理** \> **儀表板。**</span><span class="sxs-lookup"><span data-stu-id="129bb-116">In the Security &amp; Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>
    
3. <span data-ttu-id="129bb-117">在 [**深入了解**] 列中，尋找詐騙智慧深入解析。</span><span class="sxs-lookup"><span data-stu-id="129bb-117">In the **Insights** row, look for the spoof intelligence insight.</span></span> <span data-ttu-id="129bb-118">如果您已啟用詐騙智慧，然後深入解析為授權**Spoofed 網域，在過去 30 天的驗證失敗**。</span><span class="sxs-lookup"><span data-stu-id="129bb-118">If you have enabled spoof intelligence, then the insight is entitled **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="129bb-119">如果您未啟用詐騙保護，然後深入了解會提示您若要這麼做所使用的標題**啟用詐騙保護**。</span><span class="sxs-lookup"><span data-stu-id="129bb-119">If you haven't enabled spoof protection, then the insight will prompt you to do so by using the title **Enable Spoof Protection**.</span></span> 
    
## <a name="about-the-insight-on-the-dashboard"></a><span data-ttu-id="129bb-120">關於儀表板上深入解析</span><span class="sxs-lookup"><span data-stu-id="129bb-120">About the insight on the dashboard</span></span>

<span data-ttu-id="129bb-121">深入了解儀表板上的會顯示如下的資訊。</span><span class="sxs-lookup"><span data-stu-id="129bb-121">The insight on the dashboard shows you information like this.</span></span>
  
![詐騙智慧深入了解的螢幕擷取畫面](../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
<span data-ttu-id="129bb-123">此深入了解有兩種模式：</span><span class="sxs-lookup"><span data-stu-id="129bb-123">This insight has two modes:</span></span>
  
 <span data-ttu-id="129bb-124">**深入了解模式**。</span><span class="sxs-lookup"><span data-stu-id="129bb-124">**Insight mode**.</span></span> <span data-ttu-id="129bb-125">如果您有啟用任何詐騙原則，然後深入了解顯示多少郵件已由我們詐騙智慧功能影響過去 30 天。</span><span class="sxs-lookup"><span data-stu-id="129bb-125">If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
 <span data-ttu-id="129bb-126">**如果模式**。</span><span class="sxs-lookup"><span data-stu-id="129bb-126">**What if mode**.</span></span> <span data-ttu-id="129bb-127">如果您沒有任何已啟用的詐騙原則，然後深入了解顯示多少留言可能*會*有已受到我們詐騙智慧功能過去 30 天。</span><span class="sxs-lookup"><span data-stu-id="129bb-127">If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
<span data-ttu-id="129bb-128">無論如何，深入了解中顯示的詐騙的網域分成兩個類別;可疑網域配對和非可疑網域配對。</span><span class="sxs-lookup"><span data-stu-id="129bb-128">Either way, the spoofed domains displayed in the insight are separated into two categories; suspicious domain pairs and non-suspicious domain pairs.</span></span> <span data-ttu-id="129bb-129">這些類別會進一步細分為三個不同的 bucket，供您檢閱。</span><span class="sxs-lookup"><span data-stu-id="129bb-129">These categories are further subdivided into three different buckets for you to review.</span></span> 
  
<span data-ttu-id="129bb-130">*網域配對*是組合 」 從: 「 地址和傳送基礎結構。</span><span class="sxs-lookup"><span data-stu-id="129bb-130">A  *domain pair*  is a combination of the "From:" address and the sending infrastructure.</span></span> 
  
- <span data-ttu-id="129bb-131">「 從 」 地址是由您的郵件應用程式顯示自地址的地址。</span><span class="sxs-lookup"><span data-stu-id="129bb-131">The "From" address is the address displayed as the From address by your mail application.</span></span> <span data-ttu-id="129bb-132">此地址可識別電子郵件的作者。</span><span class="sxs-lookup"><span data-stu-id="129bb-132">This address identifies the author of the email.</span></span> <span data-ttu-id="129bb-133">也就是負責撰寫郵件的使用者或系統信箱。</span><span class="sxs-lookup"><span data-stu-id="129bb-133">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="129bb-134">這有時稱為 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="129bb-134">This is sometimes called the 5322.From address.</span></span>
    
- <span data-ttu-id="129bb-135">傳送基礎結構或寄件者是組織網域的傳送端 IP 位址的 PTR 記錄。</span><span class="sxs-lookup"><span data-stu-id="129bb-135">The sending infrastructure, or sender, is the organizational domain of the PTR record of the sending IP address.</span></span> <span data-ttu-id="129bb-136">如果傳送 IP 位址不有任何的 PTR 記錄，則寄件者會用來識別所傳送的 IP 255.255.255.0 CIDR 標記法的子網路遮罩 （/ 24）。</span><span class="sxs-lookup"><span data-stu-id="129bb-136">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="129bb-137">例如，如果 IP 位址是 192.168.100.100 完成 IP 位址的寄件者則 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="129bb-137">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>
    
 <span data-ttu-id="129bb-138">**可疑網域組**包括：</span><span class="sxs-lookup"><span data-stu-id="129bb-138">**Suspicious domain pairs** include:</span></span> 
  
- <span data-ttu-id="129bb-139">**高信賴度詐騙**。</span><span class="sxs-lookup"><span data-stu-id="129bb-139">**High-confidence spoof**.</span></span> <span data-ttu-id="129bb-140">Office 365 收到強式訊號這些網域所可疑，根據歷史傳送模式和網域信譽分數。</span><span class="sxs-lookup"><span data-stu-id="129bb-140">Office 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="129bb-141">Office 365 是高度以內的網域詐騙並從這些網域傳送的訊息是較不可能是合法。</span><span class="sxs-lookup"><span data-stu-id="129bb-141">Office 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span> 
    
- <span data-ttu-id="129bb-142">**中度信賴詐騙**。</span><span class="sxs-lookup"><span data-stu-id="129bb-142">**Moderate confidence spoof**.</span></span> <span data-ttu-id="129bb-143">Office 365 收到中等訊號這些網域所可疑，根據歷史傳送模式和網域信譽分數。</span><span class="sxs-lookup"><span data-stu-id="129bb-143">Office 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="129bb-144">Office 365 是普通以內的網域詐騙和是合法的寄件者這些網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="129bb-144">Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="129bb-145">此 bucket 有更多機會包含 false positive (Fp) 比高信賴度詐騙 bucket。</span><span class="sxs-lookup"><span data-stu-id="129bb-145">This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span> 
    
 <span data-ttu-id="129bb-146">**非可疑網域組**包括**人詐騙**。</span><span class="sxs-lookup"><span data-stu-id="129bb-146">**Non-suspicious domain pairs** include **rescued spoof**.</span></span> <span data-ttu-id="129bb-147">救回的詐騙都有失敗的明確的驗證檢查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)， [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email))，但傳遞我們延伸的驗證檢查的網域。</span><span class="sxs-lookup"><span data-stu-id="129bb-147">Rescued spoof are domains that have failed the explicit authentication checks ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) but passed our extended authentication checks.</span></span> <span data-ttu-id="129bb-148">由於此，Office 365 人代替您郵件和反詐騙採取任何動作已在郵件上。</span><span class="sxs-lookup"><span data-stu-id="129bb-148">As a result of this, Office 365 rescued the mail on your behalf and no anti-spoofing action was taken on the mail.</span></span> 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="129bb-149">檢視從詐騙智慧深入了解可疑網域組的詳細的資訊</span><span class="sxs-lookup"><span data-stu-id="129bb-149">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="129bb-150">詐騙智慧深入見解，在按一下任何網域組 （高、 中或救回）。</span><span class="sxs-lookup"><span data-stu-id="129bb-150">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>
  
<span data-ttu-id="129bb-151">**詐騙智慧深入了解**頁面隨即出現顯示未經驗證的郵件傳送到組織的寄件者的清單。</span><span class="sxs-lookup"><span data-stu-id="129bb-151">The **Spoof Intelligence Insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization.</span></span> <span data-ttu-id="129bb-152">在此頁面上的資訊可協助您判斷是否與否，會獲授權冒名的郵件，或如果您需要採取進一步的動作。</span><span class="sxs-lookup"><span data-stu-id="129bb-152">The information on this page helps you determine whether spoofed messages are authorized or not or if you need to take further action.</span></span> <span data-ttu-id="129bb-153">您可以排序資訊訊息計數，偵測上次到詐騙，日期等等。</span><span class="sxs-lookup"><span data-stu-id="129bb-153">You can sort the information by message count, the date the spoof was last detected, and more.</span></span> <span data-ttu-id="129bb-154">（按一下欄標題，例如**郵件計數**或**最後一次看到**，例如）。</span><span class="sxs-lookup"><span data-stu-id="129bb-154">(Click column headings, such as **Message count** or **Last seen**, for example.)</span></span> 
    
2. <span data-ttu-id="129bb-155">表格，開啟包含相關的網域組豐富資訊的詳細資料] 窗格中選取項目，包括為什麼我們攔截這，您需要做些什麼，網域摘要、 WhoIs 有關寄件者和我們討論過寄件者相同租用戶中的類似電子郵件。</span><span class="sxs-lookup"><span data-stu-id="129bb-155">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender.</span></span> <span data-ttu-id="129bb-156">從這裡開始，您也可以選擇新增或移除**AllowedToSpoof**安全寄件者清單中的網域組。</span><span class="sxs-lookup"><span data-stu-id="129bb-156">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span> 
  
![詐騙智慧深入了解詳細資料窗格中的網域的螢幕擷取畫面](../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="129bb-158">新增或移除 AllowedToSpoof 安全寄件者清單中的網域</span><span class="sxs-lookup"><span data-stu-id="129bb-158">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="129bb-159">您新增或移除 AllowedToSpoof 安全寄件者清單中的網域，同時檢閱詳細資料窗格中的網域組的詐騙智慧深入解析。</span><span class="sxs-lookup"><span data-stu-id="129bb-159">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight.</span></span> <span data-ttu-id="129bb-160">只要據此設定將開關切換。</span><span class="sxs-lookup"><span data-stu-id="129bb-160">Simply set the toggle accordingly.</span></span>
  
<span data-ttu-id="129bb-161">這會修改唯一的網域配對結合詐騙的網域與傳送基礎結構，而不提供涵蓋範圍整個詐騙的網域或隔離中的傳送基礎結構。</span><span class="sxs-lookup"><span data-stu-id="129bb-161">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation.</span></span> <span data-ttu-id="129bb-162">例如，如果您將下列網域組新增至 'AllowedToSpoof' 寄件者允許清單：*詐騙網域*」 gmail.com 」 和*傳送基礎結構*」 tms *。 mx.com 」，* 然後只從該網域配對的郵件仍可詐騙。</span><span class="sxs-lookup"><span data-stu-id="129bb-162">For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and  *Sending Infrastructure*  "tms  *.mx.com",*  then only mail from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="129bb-163">其他的寄件者嘗試詐騙 」 gmail.com 」 與 「 tms.mx.com 」 嘗試詐騙會繼續受保護的詐騙智慧其他網域。</span><span class="sxs-lookup"><span data-stu-id="129bb-163">Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="129bb-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="129bb-164">Related topics</span></span>

[<span data-ttu-id="129bb-165">深入了解詐騙情報</span><span class="sxs-lookup"><span data-stu-id="129bb-165">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)
  
[<span data-ttu-id="129bb-166">Office 365 的反詐騙保護</span><span class="sxs-lookup"><span data-stu-id="129bb-166">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)
  
[<span data-ttu-id="129bb-167">逐步解說 - 從儀表板到深入解析</span><span class="sxs-lookup"><span data-stu-id="129bb-167">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)
  
[<span data-ttu-id="129bb-168">逐步解說 - 從詳細報告到深入解析</span><span class="sxs-lookup"><span data-stu-id="129bb-168">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  
[<span data-ttu-id="129bb-169">逐步解說 - 從深入解析到詳細報告</span><span class="sxs-lookup"><span data-stu-id="129bb-169">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  

