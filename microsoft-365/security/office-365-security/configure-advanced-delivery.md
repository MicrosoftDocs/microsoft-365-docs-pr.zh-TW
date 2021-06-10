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
description: 系統管理員可以瞭解如何使用 Exchange Online Protection (EOP) 中的高級傳遞原則，以識別不應該在特定支援案例中篩選的郵件 (協力廠商網路釣魚模擬及傳送至安全性作業的郵件 (SecOps) 信箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a9c1c6f7635b87e25adcb121db79f67d4ec1988f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788990"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="46942-103">設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱</span><span class="sxs-lookup"><span data-stu-id="46942-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="46942-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="46942-104">**Applies to**</span></span>
- [<span data-ttu-id="46942-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="46942-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="46942-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="46942-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="46942-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46942-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="46942-108">本文所述的功能都是在預覽中，並非每個人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="46942-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="46942-109">若要讓組織保持[預設安全性](secure-by-default.md)，Exchange Online Protection (EOP) 不允許對識別為惡意程式碼或高可信度網路釣魚的郵件進行安全清單或篩選旁路。</span><span class="sxs-lookup"><span data-stu-id="46942-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="46942-110">不過，有些特定案例需要傳遞未篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="46942-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="46942-111">例如：</span><span class="sxs-lookup"><span data-stu-id="46942-111">For example:</span></span>

- <span data-ttu-id="46942-112">**協力廠商網路釣魚模擬**：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。</span><span class="sxs-lookup"><span data-stu-id="46942-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="46942-113">**(SecOps 的安全性作業) 信箱**：安全小組用來收集及分析未篩選郵件 (良好和不良) 的專用信箱。</span><span class="sxs-lookup"><span data-stu-id="46942-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="46942-114">您可以使用 Microsoft 365 中的 _高級傳遞原則_，以避免篩選這些 _特定案例中_ 的郵件。 <sup>\*</sup>[高級傳遞原則] 可確保這些案例中的郵件達到下列結果：</span><span class="sxs-lookup"><span data-stu-id="46942-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="46942-115">EOP 中的篩選器和 Microsoft Defender for Office 365 不會對這些郵件採取任何動作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="46942-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="46942-116">[零小時清除 (](zero-hour-auto-purge.md) 用於垃圾郵件和網路釣魚的 ZAP) 不會對這些郵件採取任何動作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="46942-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="46942-117">在這些情況下，不會觸發[預設系統警示](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="46942-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="46942-118">[Office 365 中的 AIR 和](office-365-air.md)叢集會忽略這些郵件。</span><span class="sxs-lookup"><span data-stu-id="46942-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="46942-119">特別是協力廠商網路釣魚模擬：</span><span class="sxs-lookup"><span data-stu-id="46942-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="46942-120">系統[管理報送](admin-submission.md)會產生自動回應，表示郵件屬於網路釣魚模擬活動的一部分，而且不是實際威脅。</span><span class="sxs-lookup"><span data-stu-id="46942-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="46942-121">不會觸發警示和空氣。</span><span class="sxs-lookup"><span data-stu-id="46942-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="46942-122">[Office 365 的 Defender 中的安全連結](safe-links.md)不會封鎖或引爆這些郵件中特別識別的 URLs。</span><span class="sxs-lookup"><span data-stu-id="46942-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="46942-123">[Office 365 的 Defender 中的安全附件](safe-attachments.md)不會引爆這些郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="46942-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="46942-124"><sup>\*</sup> 您無法略過惡意程式碼篩選或 ZAP 惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="46942-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="46942-125">由高級傳遞原則識別的郵件不會受到安全性威脅，所以郵件會標示為系統覆寫。</span><span class="sxs-lookup"><span data-stu-id="46942-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="46942-126">系統管理員可以在下列體驗中篩選和分析這些系統覆寫：</span><span class="sxs-lookup"><span data-stu-id="46942-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="46942-127">Office 365 方案2之 Defender 中的威脅瀏覽器/即時偵測</span><span class="sxs-lookup"><span data-stu-id="46942-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="46942-128">[威脅瀏覽器/即時偵測中的電子郵件實體頁面](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="46942-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="46942-129">[威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="46942-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="46942-130">Microsoft Defender for Endpoint 中的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="46942-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="46942-131">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="46942-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="46942-132">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="46942-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="46942-133">您可以開啟安全性中心，網址為 <https://security.microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="46942-133">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="46942-134">若要直接移至 [ **高級傳遞** ] 頁面，請開啟] <https://security.microsoft.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="46942-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="46942-135">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="46942-135">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="46942-136">若要在高級傳遞原則中建立、修改或移除已設定的設定，您必須是 **security center** 中的「**安全性管理員**」角色群組成員，以及 **Exchange Online** 中「**組織管理**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="46942-136">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **security center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="46942-137">若要以唯讀方式存取高級傳遞原則，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="46942-137">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="46942-138">如需詳細資訊，請參閱[Microsoft 365 security center 中的許可權](permissions-microsoft-365-security-center.md)及[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="46942-138">For more information, see [Permissions in the Microsoft 365 security center](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="46942-139">將使用者新增至對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 中的其他功能的 _安全性中心的_ 必要許可權。</span><span class="sxs-lookup"><span data-stu-id="46942-139">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the security center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="46942-140">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="46942-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-security-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="46942-141">使用安全中心設定高級傳遞原則中的 SecOps 信箱</span><span class="sxs-lookup"><span data-stu-id="46942-141">Use the security center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="46942-142">在 [安全性中心] 中，移至 [ **電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅** 原則 \> **規則** ] 區段 \> **高級傳遞**。</span><span class="sxs-lookup"><span data-stu-id="46942-142">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="46942-143">在 [ **高級傳遞** ] 頁面上，確認已選取 [ **SecOps 信箱** ] 索引標籤，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="46942-143">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="46942-144">按一下 [ ![ 編輯圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="46942-144">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="46942-145">若未設定網路釣魚模擬，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="46942-145">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="46942-146">在開啟的 [**編輯 SecOps 信箱**] 浮出控制項上，執行下列其中一個步驟，輸入您要指定為 SecOps 信箱的現有 Exchange Online 信箱：</span><span class="sxs-lookup"><span data-stu-id="46942-146">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="46942-147">在方塊中按一下，讓信箱清單得以解析，然後選取信箱。</span><span class="sxs-lookup"><span data-stu-id="46942-147">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="46942-148">按一下方塊中的 [開始輸入信箱識別碼] (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等 ) ，然後從結果中選取信箱 (顯示名稱) 。</span><span class="sxs-lookup"><span data-stu-id="46942-148">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="46942-149">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="46942-149">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="46942-150">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="46942-150">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="46942-151">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="46942-151">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="46942-153">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="46942-153">next to the value.</span></span>

4. <span data-ttu-id="46942-154">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="46942-154">When you're finished, click **Save**.</span></span>

<span data-ttu-id="46942-155">您設定的 SecOps 信箱專案會顯示在 [ **SecOps 信箱** ] 索引標籤上。若要進行變更，請按一下索引標籤 ![ ](../../media/m365-cc-sc-edit-icon.png) 上的 [編輯圖示 **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="46942-155">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-security-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="46942-156">使用安全中心設定高級傳遞原則中的協力廠商網路釣魚模擬</span><span class="sxs-lookup"><span data-stu-id="46942-156">Use the security center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="46942-157">在 [安全性中心] 中，移至 [ **電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅** 原則 \> **規則** ] 區段 \> **高級傳遞**。</span><span class="sxs-lookup"><span data-stu-id="46942-157">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="46942-158">在 [ **高級傳遞** ] 頁面上，選取 [ **網路釣魚類比** ] 索引標籤，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="46942-158">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="46942-159">按一下 [ ![ 編輯圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="46942-159">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="46942-160">若未設定網路釣魚模擬，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="46942-160">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="46942-161">在開啟的 [ **編輯協力廠商網路釣魚類比** ] 浮出控制項上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="46942-161">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="46942-162">傳送 **網域**：展開此設定，然後輸入至少一個電子郵件地址網域 (例如，contoso.com) 按一下方塊中的方塊，輸入值，然後按 enter 或選取方塊下方所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="46942-162">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="46942-163">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="46942-163">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="46942-164">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="46942-164">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="46942-165">傳送 **IP**：展開此設定，並輸入至少一個有效的 IPv4 位址是在方塊中按一下，輸入值，然後按 enter 或選取方塊下方所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="46942-165">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="46942-166">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="46942-166">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="46942-167">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="46942-167">You can add up to 10 entries.</span></span> <span data-ttu-id="46942-168">有效值為：</span><span class="sxs-lookup"><span data-stu-id="46942-168">Valid values are:</span></span>
     - <span data-ttu-id="46942-169">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="46942-169">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="46942-170">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="46942-170">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="46942-171">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="46942-171">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="46942-172">**類比 URLs 允許**：展開此設定，並選擇性地 URLs 輸入您的網路釣魚類比活動的一部分，而不應該封鎖或引爆，方法是按一下 [方塊]，輸入值，然後按 enter 或選取方塊下方所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="46942-172">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="46942-173">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="46942-173">You can add up to 10 entries.</span></span>

   <span data-ttu-id="46942-174">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="46942-174">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="46942-176">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="46942-176">next to the value.</span></span>

4. <span data-ttu-id="46942-177">完成作業後，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="46942-177">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="46942-178">**第一次**：按一下 [ **新增**]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="46942-178">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="46942-179">**編輯現有**：按一下 [ **儲存** ]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="46942-179">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="46942-180">您設定的協力廠商網路釣魚模擬專案會顯示在 [ **網路釣魚類比** ] 索引標籤上。若要進行變更，請按一下索引標籤 ![ ](../../media/m365-cc-sc-edit-icon.png) 上的 [編輯圖示 **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="46942-180">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="46942-181">需要篩選略過的其他案例</span><span class="sxs-lookup"><span data-stu-id="46942-181">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="46942-182">除了高級傳遞原則可以協助您使用的兩種情形之外，還有其他情況可能需要您略過篩選：</span><span class="sxs-lookup"><span data-stu-id="46942-182">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="46942-183">**協力廠商篩選**：如果您的網域的 MX 記錄 *沒有* 指向 Office 365 (郵件會先在其他地方傳送) ，否則 *無法使用* [secure](secure-by-default.md) 。</span><span class="sxs-lookup"><span data-stu-id="46942-183">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="46942-184">若要略過協力廠商篩選所評估之郵件的 Microsoft 篩選功能，請使用郵件流程規則 (也稱為 transport rules) 。</span><span class="sxs-lookup"><span data-stu-id="46942-184">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="46942-185">如需詳細資訊，請參閱 [使用郵件流程規則設定郵件中的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)。</span><span class="sxs-lookup"><span data-stu-id="46942-185">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="46942-186">**審核** 中的誤報：您可能想要暫時允許 Microsoft 透過系統 [管理員提交](admin-submission.md) 進行的某些郵件仍要進行分析，以報告未正確標記為壞于 microsoft (誤報) 的已知良好郵件。</span><span class="sxs-lookup"><span data-stu-id="46942-186">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="46942-187">就像所有覆寫一樣， **_強烈建議_** 這些余量是暫時的。</span><span class="sxs-lookup"><span data-stu-id="46942-187">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>
