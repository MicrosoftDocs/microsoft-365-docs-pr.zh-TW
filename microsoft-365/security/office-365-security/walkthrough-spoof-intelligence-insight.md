---
title: 逐步解說 - 欺騙情報深入解析
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
description: 系統管理員可以瞭解欺騙性智慧洞察力的運作方式。 他們可以快速判斷哪些寄件者合法將電子郵件傳送至其組織，而不是透過電子郵件驗證檢查 (SPF、DKIM 或 DMARC) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920475"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6711c-104">逐步解說-Microsoft Defender for Office 365 中的欺騙智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="6711c-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6711c-105">在使用 Office 的 Defender for Office 365 的 Microsoft 365 組織中，您可以使用哄騙情報洞察力，快速判斷哪些寄件者可以合法傳送您未驗證的電子郵件 (來自未通過 SPF、DKIM 或 DMARC 檢查) 的郵件。</span><span class="sxs-lookup"><span data-stu-id="6711c-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="6711c-106">透過允許已知寄件者從已知位置傳送哄騙郵件，您可以減少誤報 (已標示為錯誤) 的良好電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6711c-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="6711c-107">透過監視允許的欺騙寄件者，您可以提供額外的安全性層級，以防止不安全的郵件到達您的組織中。</span><span class="sxs-lookup"><span data-stu-id="6711c-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="6711c-108">如需報表和洞察力的詳細資訊，請參閱 [安全性 & 規範中心中的報告與深入](reports-and-insights-in-security-and-compliance.md)瞭解。</span><span class="sxs-lookup"><span data-stu-id="6711c-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="6711c-109">此逐步解說是安全性 & 規範中心的其中一項。</span><span class="sxs-lookup"><span data-stu-id="6711c-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="6711c-110">若要瞭解如何導覽報表和真知灼見，請參閱 [相關主題](#related-topics) 區段中的演練。</span><span class="sxs-lookup"><span data-stu-id="6711c-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6711c-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="6711c-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6711c-112">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="6711c-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6711c-113">若要直接移至 [ **安全性] 儀表板** 頁面，請使用 <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="6711c-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="6711c-114">您可以在安全性 & 合規性中心的多個儀表板上查看哄騙智慧洞察力。</span><span class="sxs-lookup"><span data-stu-id="6711c-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="6711c-115">不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。</span><span class="sxs-lookup"><span data-stu-id="6711c-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="6711c-116">您必須已獲指派許可權，才能執行本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="6711c-116">You need to be assigned permissions before you can do the procedures in this topic.</span></span> <span data-ttu-id="6711c-117">若要使用哄騙智慧洞察力，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="6711c-117">To use the spoof intelligence insight, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="6711c-118">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員** 。 </span><span class="sxs-lookup"><span data-stu-id="6711c-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="6711c-119">**組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理** 。</span><span class="sxs-lookup"><span data-stu-id="6711c-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>
  - <span data-ttu-id="6711c-120">[安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者** 。</span><span class="sxs-lookup"><span data-stu-id="6711c-120">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="6711c-121">[線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理** 。</span><span class="sxs-lookup"><span data-stu-id="6711c-121">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="6711c-122">您可以在 Microsoft Defender for Office 365 中啟用和停用反網路釣魚原則中的欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="6711c-122">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6711c-123">如需詳細資訊，請參閱 [Configure Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6711c-123">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="6711c-124">若要使用欺騙智慧來監視及管理傳送您未驗證之郵件的寄件者，請參閱 [在 Microsoft 365 中設定欺騙智慧](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="6711c-124">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="6711c-125">在安全性 & 規範中心開啟欺騙性智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="6711c-125">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="6711c-126">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** ] \> **儀表板。**</span><span class="sxs-lookup"><span data-stu-id="6711c-126">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="6711c-127">在 [ **洞察力** ] 列中，尋找下列其中一個專案：</span><span class="sxs-lookup"><span data-stu-id="6711c-127">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="6711c-128">**已啟用欺騙情報** ：此真知灼見稱為 **欺詐網域，其驗證過去30天失敗** 。</span><span class="sxs-lookup"><span data-stu-id="6711c-128">**Spoof intelligence is enabled** : The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="6711c-129">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="6711c-129">This is the default.</span></span>
   - <span data-ttu-id="6711c-130">**已停用欺騙情報** ：以命名方式 **啟用欺騙保護** 的洞察力，並按一下該功能可讓您啟用欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="6711c-130">**Spoof intelligence is disabled** : The insight in named **Enable Spoof Protection** , and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="6711c-131">儀表板上的洞察力顯示如下資訊：</span><span class="sxs-lookup"><span data-stu-id="6711c-131">The insight on the dashboard shows you information like this:</span></span>

   ![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="6711c-133">這兩種洞察力分為兩種模式：</span><span class="sxs-lookup"><span data-stu-id="6711c-133">This insight has two modes:</span></span>

   - <span data-ttu-id="6711c-134">**洞察力模式** ：如果已啟用欺騙智慧，則真知灼見會顯示過去30天內，我們的欺騙智慧功能會影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="6711c-134">**Insight mode** : If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="6711c-135">**假設模式** ：如果已停用欺騙智慧，則真知灼見會顯示過去30天內，我們的欺騙智慧功能 *會* 影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="6711c-135">**What if mode** : If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="6711c-136">無論是哪一種方式，顯示在真知灼見中的冒牌網域都會分為兩類： **可疑的網域配對** 和 **非可疑網域配對** 。</span><span class="sxs-lookup"><span data-stu-id="6711c-136">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="6711c-137">這些類別會進一步細分為三個不同的桶，供您審閱。</span><span class="sxs-lookup"><span data-stu-id="6711c-137">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="6711c-138">**網域對** 是 [寄件者] 位址及傳送基礎結構的組合：</span><span class="sxs-lookup"><span data-stu-id="6711c-138">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="6711c-139">寄件者位址是寄件者的電子郵件地址，顯示在電子郵件客戶程式的 [寄件者] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="6711c-139">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="6711c-140">此位址也稱為 `5322.From` 位址。</span><span class="sxs-lookup"><span data-stu-id="6711c-140">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="6711c-141">傳送基礎結構（或寄件者）是反向 DNS 查閱 (PTR 記錄) 的傳送 IP 位址的組織網域。</span><span class="sxs-lookup"><span data-stu-id="6711c-141">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="6711c-142">如果傳送 IP 位址沒有 PTR 記錄，則寄件者會透過 CIDR 標記法 (/24) 中的255.255.255.0 子網路遮罩傳送 IP 加以識別。</span><span class="sxs-lookup"><span data-stu-id="6711c-142">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="6711c-143">例如，如果 IP 位址是192.168.100.100，則寄件者的完整 IP 位址是 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="6711c-143">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="6711c-144">**可疑的網域配對** 包括：</span><span class="sxs-lookup"><span data-stu-id="6711c-144">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="6711c-145">**高度信賴性哄騙** ：根據電子郵件傳送模式和網域的信譽分數，我們強烈相信網域是哄騙的，而來自這些網域的郵件更可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="6711c-145">**High-confidence spoof** : Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="6711c-146">**適中** 的信譽哄騙：根據歷史傳送模式和網域的信譽分數，我們適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。</span><span class="sxs-lookup"><span data-stu-id="6711c-146">**Moderate confidence spoof** : Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="6711c-147">在此類別中，誤報很可能超出高可信度的欺騙。</span><span class="sxs-lookup"><span data-stu-id="6711c-147">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="6711c-148">**非可疑的網域配對** (包括 **rescued 欺騙** ) ：網域失敗明確的電子郵件驗證檢查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)) 。</span><span class="sxs-lookup"><span data-stu-id="6711c-148">**Non-suspicious domain pairs** (includes **rescued spoof** ): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="6711c-149">不過，網域已通過我們的隱含電子郵件驗證檢查 ([複合驗證](email-validation-and-authentication.md#composite-authentication)) 。</span><span class="sxs-lookup"><span data-stu-id="6711c-149">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="6711c-150">因此，不會對郵件採取任何反欺詐動作。</span><span class="sxs-lookup"><span data-stu-id="6711c-150">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="6711c-151">從哄騙情報洞察力中查看有關可疑網域配對的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6711c-151">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="6711c-152">在 [偽造情報資訊] 中，按一下 [rescued 高]、[適中] 或 []) 中的任何網域 (對。</span><span class="sxs-lookup"><span data-stu-id="6711c-152">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="6711c-153">[ **哄騙智慧洞察力** ] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="6711c-153">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="6711c-154">此頁面會向您顯示傳送未驗證電子郵件至組織的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="6711c-154">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="6711c-155">此資訊可協助您判斷是否已授權哄騙郵件，或者是否需要進一步採取動作。</span><span class="sxs-lookup"><span data-stu-id="6711c-155">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="6711c-156">您可以依郵件計數、上一次偵測欺騙的日期等等來排序資訊。</span><span class="sxs-lookup"><span data-stu-id="6711c-156">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="6711c-157">選取表格中的專案，以開啟包含網域配對相關資訊的詳細資料窗格。</span><span class="sxs-lookup"><span data-stu-id="6711c-157">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="6711c-158">此資訊包含：</span><span class="sxs-lookup"><span data-stu-id="6711c-158">The information includes:</span></span>
   - <span data-ttu-id="6711c-159">我們為何會發現這種情況。</span><span class="sxs-lookup"><span data-stu-id="6711c-159">Why we caught this.</span></span>
   - <span data-ttu-id="6711c-160">您需要執行的工作。</span><span class="sxs-lookup"><span data-stu-id="6711c-160">What you need to do.</span></span>
   - <span data-ttu-id="6711c-161">網域摘要。</span><span class="sxs-lookup"><span data-stu-id="6711c-161">A domain summary.</span></span>
   - <span data-ttu-id="6711c-162">WhoIs 寄件者的相關資料。</span><span class="sxs-lookup"><span data-stu-id="6711c-162">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="6711c-163">來自相同寄件者的您租使用者中所看到的類似訊息。</span><span class="sxs-lookup"><span data-stu-id="6711c-163">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="6711c-164">在這裡，您也可以選擇從 **AllowedToSpoof** 安全寄件者清單中新增或移除網域對。</span><span class="sxs-lookup"><span data-stu-id="6711c-164">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="6711c-166">從 AllowedToSpoof 清單中新增或移除網域</span><span class="sxs-lookup"><span data-stu-id="6711c-166">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="6711c-167">您可以在網域對的欺騙性智慧洞察力的詳細資料窗格中，新增或移除網域 AllowedToSpoof (安全寄件者) ] 清單。</span><span class="sxs-lookup"><span data-stu-id="6711c-167">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="6711c-168">只會據此設定切換。</span><span class="sxs-lookup"><span data-stu-id="6711c-168">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="6711c-169">允許網域對只允許結合欺騙的網域 *和* 傳送基礎結構。</span><span class="sxs-lookup"><span data-stu-id="6711c-169">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="6711c-170">不允許來自任何來源的冒牌網域的電子郵件，也不允許來自任何網域之傳送基礎結構的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6711c-170">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="6711c-171">例如，您可以讓下列網域對傳送欺騙性郵件給您的組織：</span><span class="sxs-lookup"><span data-stu-id="6711c-171">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="6711c-172">*冒牌網域* ： gmail.com "</span><span class="sxs-lookup"><span data-stu-id="6711c-172">*Spoofed Domain* : gmail.com"</span></span>
- <span data-ttu-id="6711c-173">傳送 *基礎結構* `tms.mx.com` ：</span><span class="sxs-lookup"><span data-stu-id="6711c-173">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="6711c-174">只允許來自該網域對的電子郵件進行欺騙。</span><span class="sxs-lookup"><span data-stu-id="6711c-174">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="6711c-175">不允許其他企圖哄騙 gmail.com 的寄件者。</span><span class="sxs-lookup"><span data-stu-id="6711c-175">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="6711c-176">來自 tms.mx.com 的其他網域中的郵件會受到欺騙智慧的檢查。</span><span class="sxs-lookup"><span data-stu-id="6711c-176">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6711c-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="6711c-177">Related topics</span></span>

[<span data-ttu-id="6711c-178">Microsoft 365 中的反欺騙保護</span><span class="sxs-lookup"><span data-stu-id="6711c-178">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
