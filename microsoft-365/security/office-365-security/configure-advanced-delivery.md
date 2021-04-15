---
title: 設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 系統管理員可以瞭解如何使用 Exchange Online Protection (EOP) 中的高級傳遞原則，以識別不應該在特定支援的案例中篩選的郵件 (協力廠商網路釣魚模擬及傳送至安全性作業 (SecOps) 信箱的郵件。
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 09e07d8406b470fd3dac25944d013b997f2f90c1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760426"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="460c0-103">設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱</span><span class="sxs-lookup"><span data-stu-id="460c0-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="460c0-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="460c0-104">**Applies to**</span></span>
- [<span data-ttu-id="460c0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="460c0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="460c0-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="460c0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="460c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="460c0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="460c0-108">本文所述的功能都是在預覽中，並非每個人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="460c0-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="460c0-109">我們想要讓您的組織成為 [預設安全性](secure-by-default.md)，因此 Exchange Online PROTECTION (EOP) 不允許對導致惡意程式碼或高可信度網路釣魚 verdicts 的郵件執行安全清單或篩選旁路。</span><span class="sxs-lookup"><span data-stu-id="460c0-109">We want to keep your organization [secure by default](secure-by-default.md), so Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that result in malware or high confidence phishing verdicts.</span></span> <span data-ttu-id="460c0-110">不過，我們意識到有需要傳遞未篩選郵件的特定案例。</span><span class="sxs-lookup"><span data-stu-id="460c0-110">But, we recognize there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="460c0-111">例如：</span><span class="sxs-lookup"><span data-stu-id="460c0-111">For example:</span></span>

- <span data-ttu-id="460c0-112">**協力廠商網路釣魚模擬**：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。</span><span class="sxs-lookup"><span data-stu-id="460c0-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="460c0-113">**(SecOps 的安全性作業) 信箱**：安全小組用來收集及分析未篩選郵件 (良好和不良) 的專用信箱。</span><span class="sxs-lookup"><span data-stu-id="460c0-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="460c0-114">您可以使用 Microsoft 365 中的 _高級傳遞原則_ ，避免這些 _特定案例中_ 的郵件受到篩選 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="460c0-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered<sup>\*</sup>.</span></span> <span data-ttu-id="460c0-115">高級傳遞原則可確保不會篩選這些案例中的郵件：</span><span class="sxs-lookup"><span data-stu-id="460c0-115">The advanced delivery policy ensures that messages in these scenarios are not filtered:</span></span>

- <span data-ttu-id="460c0-116">EOP 和 Microsoft Defender for Office 365 中的篩選器不會對這些郵件採取任何動作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="460c0-116">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="460c0-117">[零小時清除 (](zero-hour-auto-purge.md) 用於垃圾郵件和網路釣魚的 ZAP) 不會對這些郵件採取任何動作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="460c0-117">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="460c0-118">在這些情況下，不會觸發[預設系統警示](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="460c0-118">[Default system alerts](alerts.md) are not triggered for these scenarios.</span></span>
- <span data-ttu-id="460c0-119">[在 365 Office 的 Defender 中的 AIR 和](office-365-air.md) 叢集會忽略這些訊息。</span><span class="sxs-lookup"><span data-stu-id="460c0-119">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="460c0-120">特別是協力廠商網路釣魚模擬：</span><span class="sxs-lookup"><span data-stu-id="460c0-120">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="460c0-121">系統[管理報送](admin-submission.md)會產生自動回應，表明郵件屬於網路釣魚模擬活動的一部分，而且不是實際威脅。</span><span class="sxs-lookup"><span data-stu-id="460c0-121">[Admin submissions](admin-submission.md) generates an automatic response stating that the message is part of a phishing simulation campaign and is not a real threat.</span></span> <span data-ttu-id="460c0-122">不會觸發警示和空氣。</span><span class="sxs-lookup"><span data-stu-id="460c0-122">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="460c0-123">[在 Office 365 的 Defender 中的安全連結](safe-links.md) ，不會封鎖或引爆這些郵件中明確識別的 URLs。</span><span class="sxs-lookup"><span data-stu-id="460c0-123">[Safe Links in Defender for Office 365](safe-links.md) does not block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="460c0-124">[在 Office 365 的 Defender 中的安全附件](safe-attachments.md) 不會引爆這些郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="460c0-124">[Safe Attachments in Defender for Office 365](safe-attachments.md) does not detonate attachments in these messages.</span></span>

<span data-ttu-id="460c0-125"><sup>\*</sup> 您無法略過惡意程式碼篩選或 ZAP 惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="460c0-125"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="460c0-126">由高級傳遞原則識別的郵件不會受到安全性威脅，所以郵件會標示為系統覆寫。</span><span class="sxs-lookup"><span data-stu-id="460c0-126">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="460c0-127">系統管理員可以在下列體驗中篩選和分析這些系統覆寫：</span><span class="sxs-lookup"><span data-stu-id="460c0-127">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="460c0-128">適用于 Office 365 方案2之 Defender 中的威脅瀏覽器/即時偵測</span><span class="sxs-lookup"><span data-stu-id="460c0-128">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="460c0-129">[威脅瀏覽器/即時偵測中的電子郵件實體頁面](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="460c0-129">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="460c0-130">[威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="460c0-130">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="460c0-131">Microsoft Defender for Endpoint 中的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="460c0-131">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="460c0-132">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="460c0-132">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="460c0-133">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="460c0-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="460c0-134">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="460c0-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="460c0-135">若要直接移至 [ **高級傳遞** ] 頁面，請開啟] <https://protection.office.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="460c0-135">To go directly to the **Advanced delivery** page, open <https://protection.office.com/advanceddelivery>.</span></span>

- <span data-ttu-id="460c0-136">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="460c0-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="460c0-137">若要在高級傳遞原則中建立、修改或移除已設定的設定，您必須是 **security & 合規性中心** 內的 **安全性系統管理員** 角色群組成員，以及 **Exchange Online** 中 **組織管理** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="460c0-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Security & Compliance Center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="460c0-138">若要以唯讀方式存取高級傳遞原則，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="460c0-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="460c0-139">如需詳細資訊，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md) 和 [Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="460c0-139">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="460c0-140">使用安全性 & 合規性中心設定高級傳遞原則中的協力廠商網路釣魚模擬</span><span class="sxs-lookup"><span data-stu-id="460c0-140">Use the Security & Compliance Center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="460c0-141">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **高級傳遞**。</span><span class="sxs-lookup"><span data-stu-id="460c0-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="460c0-142">在 [ **高級傳遞** ] 頁面上，選取 [ **網路釣魚類比** ] 索引標籤，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="460c0-142">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="460c0-143">在開啟的 **協力廠商網路釣魚類比** 浮出控制項上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="460c0-143">On the **Third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="460c0-144">**送出網域**：必須至少有一個電子郵件地址網域 (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="460c0-144">**Sending domain**: At least one email address domain is required (for example, contoso.com).</span></span> <span data-ttu-id="460c0-145">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="460c0-145">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="460c0-146">傳送 **IP**：必須至少有一個有效的 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="460c0-146">**Sending IP**: At least one valid IPv4 address is required.</span></span> <span data-ttu-id="460c0-147">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="460c0-147">You can add up to 10 entries.</span></span> <span data-ttu-id="460c0-148">有效值為：</span><span class="sxs-lookup"><span data-stu-id="460c0-148">Valid values are:</span></span>
     - <span data-ttu-id="460c0-149">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="460c0-149">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="460c0-150">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="460c0-150">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="460c0-151">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="460c0-151">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="460c0-152">**類比 URLs 若要允許**：請輸入您的網路釣魚類比活動中不應該封鎖或引爆的特定 URLs。</span><span class="sxs-lookup"><span data-stu-id="460c0-152">**Simulation URLs to allow**: Optionally, enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated.</span></span> <span data-ttu-id="460c0-153">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="460c0-153">You can add up to 10 entries.</span></span>

4. <span data-ttu-id="460c0-154">完成後，按一下 [ **儲存]。**</span><span class="sxs-lookup"><span data-stu-id="460c0-154">When you're finished, click **Save.**</span></span>

<span data-ttu-id="460c0-155">您設定的協力廠商網路釣魚模擬專案會顯示在 [ **網路釣魚類比** ] 索引標籤上。若要進行變更，請按一下索引標籤上的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="460c0-155">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="460c0-156">使用安全性 & 合規性中心設定高級傳遞原則中的 SecOps 信箱</span><span class="sxs-lookup"><span data-stu-id="460c0-156">Use the Security & Compliance Center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="460c0-157">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **高級傳遞**。</span><span class="sxs-lookup"><span data-stu-id="460c0-157">In the Security & Compliance Center, go to **Threat Management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="460c0-158">在 [ **高級傳遞** ] 頁面上，選取 [ **SecOps 信箱** ] 索引標籤，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="460c0-158">On the **Advanced delivery** page, select the **SecOps mailbox** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="460c0-159">在開啟的 **SecOps 信箱** 快顯視窗中，輸入您要指定為 SecOps 信箱的現有 Exchange Online 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="460c0-159">On the **SecOps mailbox** flyout that opens, enter the email addresses of existing Exchange Online mailboxes that you want to designate as SecOps mailboxes.</span></span> <span data-ttu-id="460c0-160">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="460c0-160">Distribution groups are not allowed.</span></span>

4. <span data-ttu-id="460c0-161">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="460c0-161">When you're finished, click **Save**.</span></span>

<span data-ttu-id="460c0-162">您設定的 SecOps 信箱專案會顯示在 [ **SecOps 信箱** ] 索引標籤上。若要進行變更，請按一下索引標籤上的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="460c0-162">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="460c0-163">需要篩選略過的其他案例</span><span class="sxs-lookup"><span data-stu-id="460c0-163">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="460c0-164">除了高級傳遞原則可以協助您使用的兩種情形之外，還有其他情況可能需要您略過篩選：</span><span class="sxs-lookup"><span data-stu-id="460c0-164">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="460c0-165">**協力廠商篩選**：如果您網域的 MX 記錄沒有指向 Office 365 (郵件會先在其他地方傳送) ，否則無法使用 [secure](secure-by-default.md) 。</span><span class="sxs-lookup"><span data-stu-id="460c0-165">**Third-party filters**: If you domain's MX record doesn't point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) is not available.</span></span>

  <span data-ttu-id="460c0-166">若要繞過協力廠商篩選所評估之郵件的 Microsoft 篩選功能，請使用郵件流程規則 (也稱為傳輸規則) ，請參閱 [使用郵件流程規則來設定郵件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="460c0-166">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules), see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

- <span data-ttu-id="460c0-167">**審核** 中的誤報：您可能想要暫時允許 Microsoft 透過系統 [管理員提交](admin-submission.md) 進行的某些郵件仍要進行分析，以報告未正確標記為壞于 microsoft (誤報) 的已知良好郵件。</span><span class="sxs-lookup"><span data-stu-id="460c0-167">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="460c0-168">就像所有覆寫一樣，強烈建議這些余量是暫時的。</span><span class="sxs-lookup"><span data-stu-id="460c0-168">As with all overrides, we highly recommended that these allowances are temporary.</span></span>
