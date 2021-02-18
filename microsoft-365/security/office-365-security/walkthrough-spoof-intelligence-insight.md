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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解欺騙性智慧洞察力的運作方式。 他們可以快速判斷哪些寄件者合法將電子郵件傳送至其組織，而不是透過電子郵件驗證檢查 (SPF、DKIM 或 DMARC) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287968"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e3766-104">逐步解說-Microsoft Defender for Office 365 中的欺騙智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="e3766-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e3766-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="e3766-105">**Applies to**</span></span>
- [<span data-ttu-id="e3766-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="e3766-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e3766-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3766-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e3766-108">在使用 Office 的 Defender for Office 365 的 Microsoft 365 組織中，您可以使用「欺騙性智慧洞察力」快速判斷哪些外部寄件者可合法傳送您未經驗證的電子郵件 (來自未通過 SPF、DKIM 或 DMARC 檢查的網域的郵件) 。</span><span class="sxs-lookup"><span data-stu-id="e3766-108">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="e3766-109">透過允許已知的外部寄件者從已知位置傳送哄騙郵件，您可以減少誤報 (已標示為錯誤) 的良好電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e3766-109">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="e3766-110">透過監視允許的欺騙寄件者，您可以提供額外的安全性層級，以防止不安全的郵件到達您的組織中。</span><span class="sxs-lookup"><span data-stu-id="e3766-110">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="e3766-111">如需報表和洞察力的詳細資訊，請參閱 [安全性 & 規範中心中的報告與深入](reports-and-insights-in-security-and-compliance.md)瞭解。</span><span class="sxs-lookup"><span data-stu-id="e3766-111">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="e3766-112">此逐步解說是安全性 & 規範中心的其中一項。</span><span class="sxs-lookup"><span data-stu-id="e3766-112">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="e3766-113">若要瞭解如何導覽報表和真知灼見，請參閱 [相關主題](#related-topics) 區段中的演練。</span><span class="sxs-lookup"><span data-stu-id="e3766-113">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e3766-114">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="e3766-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e3766-115">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e3766-115">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e3766-116">若要直接移至 [ **安全性] 儀表板** 頁面，請使用 <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="e3766-116">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="e3766-117">您可以在安全性 & 合規性中心的多個儀表板上查看哄騙智慧洞察力。</span><span class="sxs-lookup"><span data-stu-id="e3766-117">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="e3766-118">不論您所看到的儀表板為何，真知灼見都會提供相同的詳細資料，並可讓您快速執行相同的工作。</span><span class="sxs-lookup"><span data-stu-id="e3766-118">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly do the same tasks.</span></span>

- <span data-ttu-id="e3766-119">您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="e3766-119">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e3766-120">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="e3766-120">**Organization Management**</span></span>
  - <span data-ttu-id="e3766-121">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="e3766-121">**Security Administrator**</span></span>
  - <span data-ttu-id="e3766-122">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="e3766-122">**Security Reader**</span></span>
  - <span data-ttu-id="e3766-123">**全域讀取者**</span><span class="sxs-lookup"><span data-stu-id="e3766-123">**Global Reader**</span></span>

  <span data-ttu-id="e3766-124">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e3766-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e3766-125">**附注**：將使用者新增至 microsoft 365 系統管理中心的對應 Azure Active Directory 角色，可讓使用者具備安全性 & 合規性中心的許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="e3766-125">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e3766-126">如需詳細資訊，請參閱[系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e3766-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="e3766-127">您可以在 Microsoft Defender for Office 365 中啟用和停用反網路釣魚原則中的欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="e3766-127">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e3766-128">預設會啟用欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="e3766-128">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="e3766-129">如需詳細資訊，請參閱 [Configure Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e3766-129">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="e3766-130">若要使用欺騙智慧來監視及管理傳送您未驗證之郵件的寄件者，請參閱 [在 Microsoft 365 中設定欺騙智慧](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="e3766-130">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="e3766-131">在安全性 & 規範中心開啟欺騙性智慧洞察力</span><span class="sxs-lookup"><span data-stu-id="e3766-131">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="e3766-132">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **儀表板。**</span><span class="sxs-lookup"><span data-stu-id="e3766-132">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="e3766-133">在 [ **洞察力** ] 列中，尋找下列其中一個專案：</span><span class="sxs-lookup"><span data-stu-id="e3766-133">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="e3766-134">**過去七天內可能會出現的欺騙網域**：此認知表示已啟用欺騙情報 (預設會啟用該功能) 。</span><span class="sxs-lookup"><span data-stu-id="e3766-134">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="e3766-135">**啟用欺騙保護**：此真知灼見表示已停用欺騙智慧，按一下洞察力可讓您啟用欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="e3766-135">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="e3766-136">儀表板上的洞察力顯示如下資訊：</span><span class="sxs-lookup"><span data-stu-id="e3766-136">The insight on the dashboard shows you information like this:</span></span>

   ![欺騙智慧洞察力的螢幕擷取畫面](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="e3766-138">這兩種洞察力分為兩種模式：</span><span class="sxs-lookup"><span data-stu-id="e3766-138">This insight has two modes:</span></span>

   - <span data-ttu-id="e3766-139">**深入瞭解模式**：如果已啟用欺騙智慧，則洞察力會顯示過去7天的欺騙智慧功能會影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="e3766-139">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="e3766-140">**假設模式**：如果已停用欺騙智慧，則洞察力會顯示過去7天的欺騙智慧功能 *會* 影響的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="e3766-140">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="e3766-141">無論是哪種方式，顯示在真知灼見中的欺騙性網域都會分為兩類： **可疑的網域** 和 **非可疑的網域**。</span><span class="sxs-lookup"><span data-stu-id="e3766-141">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="e3766-142">**可疑的網域** 包括：</span><span class="sxs-lookup"><span data-stu-id="e3766-142">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="e3766-143">高度信賴性哄騙：根據電子郵件傳送模式和網域的信譽分數，我們強烈相信網域是哄騙的，而來自這些網域的郵件更可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="e3766-143">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="e3766-144">適中的信譽哄騙：根據歷史傳送模式和網域的信譽分數，我們適度相信網域是哄騙的，而從這些網域傳送的郵件是合法的。</span><span class="sxs-lookup"><span data-stu-id="e3766-144">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="e3766-145">在此類別中，誤報很可能超出高可信度的欺騙。</span><span class="sxs-lookup"><span data-stu-id="e3766-145">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="e3766-146">**非可疑網域**：網域失敗明確的電子郵件驗證檢查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)) 。</span><span class="sxs-lookup"><span data-stu-id="e3766-146">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="e3766-147">不過，網域已通過我們的隱含電子郵件驗證檢查 ([複合驗證](email-validation-and-authentication.md#composite-authentication)) 。</span><span class="sxs-lookup"><span data-stu-id="e3766-147">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="e3766-148">因此，不會對郵件採取任何反欺詐動作。</span><span class="sxs-lookup"><span data-stu-id="e3766-148">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="e3766-149">從哄騙情報洞察力中查看有關可疑網域的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e3766-149">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="e3766-150">在 [偽造智慧洞察力] 中，按一下 [ **可疑的網域** 或 **非可疑的網域** ]，以移至 [ **偽造智慧洞察力** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e3766-150">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="e3766-151">「 **欺騙性智慧洞察力** 」頁面包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e3766-151">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="e3766-152">**冒牌網域**：電子郵件客戶程式的 [ **寄件者** ] 方塊中顯示的欺騙使用者網域。</span><span class="sxs-lookup"><span data-stu-id="e3766-152">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="e3766-153">此位址也稱為 `5322.From` 位址。</span><span class="sxs-lookup"><span data-stu-id="e3766-153">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="e3766-154">**基礎結構**：也稱為傳送 _基礎結構_。</span><span class="sxs-lookup"><span data-stu-id="e3766-154">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="e3766-155">) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域。</span><span class="sxs-lookup"><span data-stu-id="e3766-155">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="e3766-156">如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="e3766-156">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="e3766-157">**郵件數目**：傳送基礎結構至您的組織中，在過去7天內包含指定的冒牌網域的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="e3766-157">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="e3766-158">**上次看到**：從包含欺騙網域之傳送基礎結構接收郵件的最後日期。</span><span class="sxs-lookup"><span data-stu-id="e3766-158">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="e3766-159">**哄騙類型**：此值為 **External**。</span><span class="sxs-lookup"><span data-stu-id="e3766-159">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="e3766-160">是否 **允許哄騙？**：您在這裡看到的值包括：</span><span class="sxs-lookup"><span data-stu-id="e3766-160">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="e3766-161">**Yes**：來自欺騙使用者網域和傳送基礎結構的電子郵件會被允許，未被視為欺騙電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e3766-161">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="e3766-162">**No**：來自欺騙使用者網域及傳送基礎結構的郵件會標示為欺騙。</span><span class="sxs-lookup"><span data-stu-id="e3766-162">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="e3766-163">此巨集指令是由預設的反網路釣魚原則或自訂的反網路釣魚原則所控制 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。</span><span class="sxs-lookup"><span data-stu-id="e3766-163">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="e3766-164">如需詳細資訊，請參閱 [Configure Microsoft Defender For Office 365 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e3766-164">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="e3766-165">選取清單中的專案，以查看快顯視窗中網域/傳送基礎結構對的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e3766-165">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="e3766-166">此資訊包含：</span><span class="sxs-lookup"><span data-stu-id="e3766-166">The information includes:</span></span>
   - <span data-ttu-id="e3766-167">我們為何會發現這種情況。</span><span class="sxs-lookup"><span data-stu-id="e3766-167">Why we caught this.</span></span>
   - <span data-ttu-id="e3766-168">您需要執行的工作。</span><span class="sxs-lookup"><span data-stu-id="e3766-168">What you need to do.</span></span>
   - <span data-ttu-id="e3766-169">網域摘要。</span><span class="sxs-lookup"><span data-stu-id="e3766-169">A domain summary.</span></span>
   - <span data-ttu-id="e3766-170">WhoIs 寄件者的相關資料。</span><span class="sxs-lookup"><span data-stu-id="e3766-170">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="e3766-171">來自相同寄件者的您租使用者中所看到的類似訊息。</span><span class="sxs-lookup"><span data-stu-id="e3766-171">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="e3766-172">在這裡，您也可以選擇從 **允許欺騙** 寄件者允許清單中，新增或移除網域/傳送基礎結構對。</span><span class="sxs-lookup"><span data-stu-id="e3766-172">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="e3766-173">只會據此設定切換。</span><span class="sxs-lookup"><span data-stu-id="e3766-173">Simply set the toggle accordingly.</span></span>

   ![欺騙智慧洞察力詳細資料窗格中的網域螢幕擷取畫面](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="e3766-175">將網域新增至允許的欺騙清單</span><span class="sxs-lookup"><span data-stu-id="e3766-175">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="e3766-176">從欺詐智慧洞察力中將網域新增至允許的欺騙性清單，只允許將冒牌網域 *和* 傳送基礎結構組合在一起。</span><span class="sxs-lookup"><span data-stu-id="e3766-176">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="e3766-177">不允許來自任何來源的冒牌網域的電子郵件，也不允許來自任何網域之傳送基礎結構的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e3766-177">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="e3766-178">例如，您可以讓下列網域成為允許的欺騙清單：</span><span class="sxs-lookup"><span data-stu-id="e3766-178">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="e3766-179">**網域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="e3766-179">**Domain**: gmail.com</span></span>
- <span data-ttu-id="e3766-180">**基礎結構**： tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="e3766-180">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="e3766-181">只有來自該網域/傳送基礎結構對的電子郵件才會遭到欺騙。</span><span class="sxs-lookup"><span data-stu-id="e3766-181">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="e3766-182">不允許其他企圖哄騙 gmail.com 的寄件者。</span><span class="sxs-lookup"><span data-stu-id="e3766-182">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="e3766-183">來自 tms.mx.com 的其他網域中的郵件會受到欺騙智慧的檢查。</span><span class="sxs-lookup"><span data-stu-id="e3766-183">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3766-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="e3766-184">Related topics</span></span>

[<span data-ttu-id="e3766-185">Microsoft 365 中的反欺騙保護</span><span class="sxs-lookup"><span data-stu-id="e3766-185">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
