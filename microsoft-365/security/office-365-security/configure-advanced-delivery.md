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
ms.openlocfilehash: b989b11739b5418ad14e147f76dde0e0dd7b1b1a
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383447"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="668e8-103">設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱</span><span class="sxs-lookup"><span data-stu-id="668e8-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="668e8-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="668e8-104">**Applies to**</span></span>
- [<span data-ttu-id="668e8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="668e8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="668e8-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="668e8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="668e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="668e8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="668e8-108">本文所述的功能都是在預覽中，並非每個人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="668e8-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="668e8-109">若要讓組織保持[預設安全性](secure-by-default.md)，Exchange Online Protection (EOP) 不允許對識別為惡意程式碼或高可信度網路釣魚的郵件進行安全清單或篩選旁路。</span><span class="sxs-lookup"><span data-stu-id="668e8-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="668e8-110">不過，有些特定案例需要傳遞未篩選的郵件。</span><span class="sxs-lookup"><span data-stu-id="668e8-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="668e8-111">例如：</span><span class="sxs-lookup"><span data-stu-id="668e8-111">For example:</span></span>

- <span data-ttu-id="668e8-112">**協力廠商網路釣魚模擬**：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。</span><span class="sxs-lookup"><span data-stu-id="668e8-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="668e8-113">**(SecOps 的安全性作業) 信箱**：安全小組用來收集及分析未篩選郵件 (良好和不良) 的專用信箱。</span><span class="sxs-lookup"><span data-stu-id="668e8-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="668e8-114">您可以使用 Microsoft 365 中的 _高級傳遞原則_，以避免篩選這些 _特定案例中_ 的郵件。 <sup>\*</sup>[高級傳遞原則] 可確保這些案例中的郵件達到下列結果：</span><span class="sxs-lookup"><span data-stu-id="668e8-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="668e8-115">EOP 中的篩選器和 Microsoft Defender for Office 365 不會對這些郵件採取任何動作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="668e8-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="668e8-116">[零小時清除 (](zero-hour-auto-purge.md) 用於垃圾郵件和網路釣魚的 ZAP) 不會對這些郵件採取任何動作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="668e8-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="668e8-117">在這些情況下，不會觸發[預設系統警示](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="668e8-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="668e8-118">[Office 365 中的 AIR 和](office-365-air.md)叢集會忽略這些郵件。</span><span class="sxs-lookup"><span data-stu-id="668e8-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="668e8-119">特別是協力廠商網路釣魚模擬：</span><span class="sxs-lookup"><span data-stu-id="668e8-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="668e8-120">系統[管理報送](admin-submission.md)會產生自動回應，表示郵件屬於網路釣魚模擬活動的一部分，而且不是實際威脅。</span><span class="sxs-lookup"><span data-stu-id="668e8-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="668e8-121">不會觸發警示和空氣。</span><span class="sxs-lookup"><span data-stu-id="668e8-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="668e8-122">[保管庫的 Defender 中的連結 Office 365](safe-links.md)不會封鎖或引爆這些郵件中的明確識別 URLs。</span><span class="sxs-lookup"><span data-stu-id="668e8-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="668e8-123">[保管庫的 Defender 中的附件 Office 365](safe-attachments.md)不會引爆這些郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="668e8-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="668e8-124"><sup>\*</sup> 您無法略過惡意程式碼篩選或 ZAP 惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="668e8-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="668e8-125">由高級傳遞原則識別的郵件不會受到安全性威脅，所以郵件會標示為系統覆寫。</span><span class="sxs-lookup"><span data-stu-id="668e8-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="668e8-126">系統管理員可以在下列體驗中篩選和分析這些系統覆寫：</span><span class="sxs-lookup"><span data-stu-id="668e8-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="668e8-127">Office 365 方案2之 Defender 中的威脅瀏覽器/即時偵測</span><span class="sxs-lookup"><span data-stu-id="668e8-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="668e8-128">[威脅瀏覽器/即時偵測中的電子郵件實體頁面](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="668e8-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="668e8-129">[威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="668e8-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="668e8-130">Microsoft Defender for Endpoint 中的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="668e8-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="668e8-131">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="668e8-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="668e8-132">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="668e8-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="668e8-133">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="668e8-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="668e8-134">若要直接移至 [ **高級傳遞** ] 頁面，請開啟] <https://security.microsoft.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="668e8-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="668e8-135">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="668e8-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="668e8-136">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="668e8-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="668e8-137">若要建立、修改或移除 advanced 傳遞原則中已設定的設定，您必須是 **Microsoft 365 Defender 入口網站** 中 **安全性管理員** 角色群組的成員，以及 **Exchange Online** 中 **組織管理** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="668e8-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="668e8-138">若要以唯讀方式存取高級傳遞原則，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="668e8-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="668e8-139">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)及[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="668e8-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="668e8-140">將使用者新增至對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="668e8-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="668e8-141">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="668e8-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="668e8-142">使用 Microsoft 365 Defender 入口網站設定高級傳遞原則中的 SecOps 信箱</span><span class="sxs-lookup"><span data-stu-id="668e8-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="668e8-143">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則**] 頁面 \> **規則**] 「 \> **高級傳遞**」。</span><span class="sxs-lookup"><span data-stu-id="668e8-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="668e8-144">在 [ **高級傳遞** ] 頁面上，確認已選取 [ **SecOps 信箱** ] 索引標籤，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="668e8-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="668e8-145">按一下 [ ![ 編輯圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="668e8-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="668e8-146">若未設定網路釣魚模擬，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="668e8-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="668e8-147">在開啟的 [**編輯 SecOps 信箱**] 浮出控制項上，執行下列其中一個步驟，輸入您要指定為 SecOps 信箱的現有 Exchange Online 信箱：</span><span class="sxs-lookup"><span data-stu-id="668e8-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="668e8-148">在方塊中按一下，讓信箱清單得以解析，然後選取信箱。</span><span class="sxs-lookup"><span data-stu-id="668e8-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="668e8-149">按一下方塊中的 [開始輸入信箱識別碼] (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等 ) ，然後從結果中選取信箱 (顯示名稱) 。</span><span class="sxs-lookup"><span data-stu-id="668e8-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="668e8-150">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="668e8-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="668e8-151">不允許通訊群組。</span><span class="sxs-lookup"><span data-stu-id="668e8-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="668e8-152">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="668e8-152">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="668e8-154">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="668e8-154">next to the value.</span></span>

4. <span data-ttu-id="668e8-155">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="668e8-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="668e8-156">您設定的 SecOps 信箱專案會顯示在 [ **SecOps 信箱** ] 索引標籤上。若要進行變更，請按一下索引標籤 ![ ](../../media/m365-cc-sc-edit-icon.png) 上的 [編輯圖示 **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="668e8-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="668e8-157">使用 Microsoft 365 Defender 入口網站設定高級傳遞原則中的協力廠商網路釣魚模擬</span><span class="sxs-lookup"><span data-stu-id="668e8-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="668e8-158">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則**] 頁面 \> **規則**] 「 \> **高級傳遞**」。</span><span class="sxs-lookup"><span data-stu-id="668e8-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="668e8-159">在 [ **高級傳遞** ] 頁面上，選取 [ **網路釣魚類比** ] 索引標籤，然後執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="668e8-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="668e8-160">按一下 [ ![ 編輯圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="668e8-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="668e8-161">若未設定網路釣魚模擬，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="668e8-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="668e8-162">在開啟的 [ **編輯協力廠商網路釣魚類比** ] 浮出控制項上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="668e8-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="668e8-163">傳送 **網域**：展開此設定，然後輸入至少一個電子郵件地址網域 (例如，contoso.com) 按一下方塊中的方塊，輸入值，然後按 enter 或選取方塊下方所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="668e8-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="668e8-164">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="668e8-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="668e8-165">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="668e8-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="668e8-166">傳送 **IP**：展開此設定，並輸入至少一個有效的 IPv4 位址是在方塊中按一下，輸入值，然後按 enter 或選取方塊下方所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="668e8-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="668e8-167">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="668e8-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="668e8-168">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="668e8-168">You can add up to 10 entries.</span></span> <span data-ttu-id="668e8-169">有效值為：</span><span class="sxs-lookup"><span data-stu-id="668e8-169">Valid values are:</span></span>
     - <span data-ttu-id="668e8-170">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="668e8-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="668e8-171">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="668e8-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="668e8-172">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="668e8-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="668e8-173">**類比 URLs 允許**：展開此設定，並選擇性地 URLs 輸入您的網路釣魚類比活動的一部分，而不應該封鎖或引爆，方法是按一下 [方塊]，輸入值，然後按 enter 或選取方塊下方所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="668e8-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="668e8-174">您最多可以新增10個專案。</span><span class="sxs-lookup"><span data-stu-id="668e8-174">You can add up to 10 entries.</span></span> <span data-ttu-id="668e8-175">如需 URL 語法格式，請參閱 [承租人 Allow/封鎖清單的 URL 語法](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list)。</span><span class="sxs-lookup"><span data-stu-id="668e8-175">For the URL syntax format, see [URL syntax for the Tenant Allow/Block List](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list).</span></span>

   <span data-ttu-id="668e8-176">若要移除現有的值，請按一下</span><span class="sxs-lookup"><span data-stu-id="668e8-176">To remove an existing value, click remove</span></span> ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="668e8-178">值旁邊的 [移除]。</span><span class="sxs-lookup"><span data-stu-id="668e8-178">next to the value.</span></span>

4. <span data-ttu-id="668e8-179">完成作業後，請執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="668e8-179">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="668e8-180">**第一次**：按一下 [ **新增**]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="668e8-180">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="668e8-181">**編輯現有**：按一下 [ **儲存** ]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="668e8-181">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="668e8-182">您設定的協力廠商網路釣魚模擬專案會顯示在 [ **網路釣魚類比** ] 索引標籤上。若要進行變更，請按一下索引標籤 ![ ](../../media/m365-cc-sc-edit-icon.png) 上的 [編輯圖示 **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="668e8-182">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="668e8-183">需要篩選略過的其他案例</span><span class="sxs-lookup"><span data-stu-id="668e8-183">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="668e8-184">除了高級傳遞原則可以協助您使用的兩種情形之外，還有其他情況可能需要您略過篩選：</span><span class="sxs-lookup"><span data-stu-id="668e8-184">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="668e8-185">**協力廠商篩選**：如果您的網域的 MX 記錄 *沒有* 指向 Office 365 (郵件會先在其他地方傳送) ，否則 *無法使用* [secure](secure-by-default.md) 。</span><span class="sxs-lookup"><span data-stu-id="668e8-185">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="668e8-186">如果您想要新增保護，必須啟用連接器的增強篩選 (也稱為 *skip 清單*) 。</span><span class="sxs-lookup"><span data-stu-id="668e8-186">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="668e8-187">如需詳細資訊，請參閱[使用具有 Exchange Online 的協力廠商雲端服務管理郵件流程](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)。</span><span class="sxs-lookup"><span data-stu-id="668e8-187">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="668e8-188">如果您不想要增強的連接器篩選功能，請使用郵件流程規則 (也稱為傳輸規則) ，以略過協力廠商篩選已評估之郵件的 Microsoft 篩選功能。</span><span class="sxs-lookup"><span data-stu-id="668e8-188">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="668e8-189">如需詳細資訊，請參閱 [使用郵件流程規則設定郵件中的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)。</span><span class="sxs-lookup"><span data-stu-id="668e8-189">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="668e8-190">**審核** 中的誤報：您可能想要暫時允許 Microsoft 透過系統 [管理員提交](admin-submission.md) 進行的某些郵件仍要進行分析，以報告未正確標記為壞于 microsoft (誤報) 的已知良好郵件。</span><span class="sxs-lookup"><span data-stu-id="668e8-190">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="668e8-191">就像所有覆寫一樣， **_強烈建議_** 這些余量是暫時的。</span><span class="sxs-lookup"><span data-stu-id="668e8-191">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="668e8-192">Exchange OnlineSecOps 高級傳遞原則中的信箱的 PowerShell 程式</span><span class="sxs-lookup"><span data-stu-id="668e8-192">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="668e8-193">在 Exchange Online PowerShell 中，高級傳遞原則中 SecOps 信箱的基本元素為：</span><span class="sxs-lookup"><span data-stu-id="668e8-193">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="668e8-194">**SecOps 覆寫原則**：由 **\* -SecOpsOverridePolicy** Cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="668e8-194">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="668e8-195">**SecOps 覆寫規則**：由 **\* -SecOpsOverrideRule** Cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="668e8-195">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="668e8-196">這種行為具有下列結果：</span><span class="sxs-lookup"><span data-stu-id="668e8-196">This behavior has the following results:</span></span>

- <span data-ttu-id="668e8-197">您必須先建立原則，然後建立規則來識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-197">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="668e8-198">當您從 PowerShell 中移除原則時，也會移除對應的規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-198">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="668e8-199">當您從 PowerShell 中移除規則時，並不會移除對應的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-199">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="668e8-200">您必須手動移除對應的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-200">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="668e8-201">使用 PowerShell 設定 SecOps 信箱</span><span class="sxs-lookup"><span data-stu-id="668e8-201">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="668e8-202">在 PowerShell 的高級傳遞原則中設定 SecOps 信箱是兩個步驟的程式：</span><span class="sxs-lookup"><span data-stu-id="668e8-202">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="668e8-203">建立 SecOps 覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-203">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="668e8-204">建立 SecOps 覆寫規則，以指定套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-204">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="668e8-205">步驟1：使用 PowerShell 來建立 SecOps 覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-205">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="668e8-206">若要建立 SecOps 覆寫原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="668e8-206">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="668e8-207">**附注**：不管您指定的名稱值為何，原則名稱都會是 SecOpsOverridePolicy，因此您也可以使用該值。</span><span class="sxs-lookup"><span data-stu-id="668e8-207">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="668e8-208">此範例會建立 SecOps 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-208">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="668e8-209">如需詳細的語法及參數資訊，請參閱 [SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-209">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="668e8-210">步驟2：使用 PowerShell 建立 SecOps 覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-210">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="668e8-211">本範例會建立具有指定設定的 SecOps 信箱規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-211">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="668e8-212">**附注**： \* \* 不論您指定的名稱值為何，規則名稱都會是 SecOpsOverrideRule \<GUID\> ，其中 \<GUID\> 是唯一的 GUID 值 (例如，6fed4b63-3563-495d-a481-b24a311f8329) 。</span><span class="sxs-lookup"><span data-stu-id="668e8-212">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="668e8-213">如需詳細的語法及參數資訊，請參閱 [SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="668e8-213">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="668e8-214">使用 PowerShell 來查看 SecOps 覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-214">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="668e8-215">此範例會傳回單一 SecOps 信箱原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="668e8-215">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="668e8-216">如需詳細的語法及參數資訊，請參閱 [SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-216">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="668e8-217">使用 PowerShell 來查看 SecOps 覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-217">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="668e8-218">本範例會傳回 SecOps 覆寫規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="668e8-218">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="668e8-219">雖然上一個命令只會傳回一個規則，但結果中也可能會包含任何擱置刪除的規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-219">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="668e8-220">這個範例會識別 (一) 和任何無效規則的有效規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-220">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="668e8-221">在您識別不正確規則之後，您可以使用 **SecOpsOverrideRule** 指令程式（如 [本文稍後](#use-powershell-to-remove-secops-override-rules)所述）移除這些規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-221">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="668e8-222">如需詳細的語法及參數資訊，請參閱 [SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="668e8-222">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="668e8-223">使用 PowerShell 修改 SecOps 覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-223">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="668e8-224">若要修改 SecOps 覆寫原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="668e8-224">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="668e8-225">本範例會將 secops2@contoso.com 新增至 SecOps 覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-225">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="668e8-226">**附注**：如果存在相關聯且有效的 SecOps 覆寫規則，則也會更新該規則中的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="668e8-226">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="668e8-227">如需詳細的語法及參數資訊，請參閱 [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-227">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="668e8-228">使用 PowerShell 修改 SecOps 覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-228">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="668e8-229">**SecOpsOverrideRule** Cmdlet 不會修改 SecOps 覆寫規則中的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="668e8-229">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="668e8-230">若要修改 SecOps 覆寫規則中的電子郵件地址，請使用 **SecOpsOverridePolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="668e8-230">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="668e8-231">如需詳細的語法及參數資訊，請參閱 [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="668e8-231">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="668e8-232">使用 PowerShell 移除 SecOps 覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-232">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="668e8-233">此範例會移除 SecOps 信箱原則和對應的規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-233">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="668e8-234">如需詳細的語法及參數資訊，請參閱 [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-234">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="668e8-235">使用 PowerShell 移除 SecOps 覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-235">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="668e8-236">若要移除 SecOps 覆寫規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="668e8-236">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="668e8-237">本範例會移除指定的 SecOps 覆寫規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-237">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="668e8-238">如需詳細的語法及參數資訊，請參閱 [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="668e8-238">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="668e8-239">Exchange Online在高級傳遞原則中 PowerShell 協力廠商網路釣魚模擬的程式</span><span class="sxs-lookup"><span data-stu-id="668e8-239">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="668e8-240">在 Exchange Online PowerShell 中，高級傳遞原則中的協力廠商網路釣魚模擬基本元素為：</span><span class="sxs-lookup"><span data-stu-id="668e8-240">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="668e8-241">**網路釣魚類比覆寫原則**：由 **\* -PhishSimOverridePolicy** Cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="668e8-241">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="668e8-242">**網路釣魚類比覆寫規則**：由 **\* -PhishSimOverrideRule** Cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="668e8-242">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="668e8-243">這種行為具有下列結果：</span><span class="sxs-lookup"><span data-stu-id="668e8-243">This behavior has the following results:</span></span>

- <span data-ttu-id="668e8-244">您必須先建立原則，然後建立規則來識別套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-244">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="668e8-245">您可以修改原則和規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="668e8-245">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="668e8-246">當您從 PowerShell 中移除原則時，也會移除對應的規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-246">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="668e8-247">當您從 PowerShell 中移除規則時，並不會移除對應的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-247">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="668e8-248">您必須手動移除對應的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-248">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="668e8-249">使用 PowerShell 設定協力廠商網路釣魚模擬</span><span class="sxs-lookup"><span data-stu-id="668e8-249">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="668e8-250">在 PowerShell 中的高級傳遞原則中設定協力廠商網路釣魚模擬的程式分為兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="668e8-250">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="668e8-251">建立網路釣魚類比覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-251">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="668e8-252">建立網路釣魚類比覆寫規則，以指定套用規則的原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-252">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="668e8-253">步驟1：使用 PowerShell 建立網路釣魚類比覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-253">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="668e8-254">此範例會建立網路釣魚類比覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-254">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="668e8-255">**附注**：不管您指定的名稱值為何，原則名稱都會是 PhishSimOverridePolicy，因此您也可以使用該值。</span><span class="sxs-lookup"><span data-stu-id="668e8-255">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="668e8-256">如需詳細的語法及參數資訊，請參閱 [PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-256">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="668e8-257">步驟2：使用 PowerShell 建立網路釣魚類比覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-257">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="668e8-258">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="668e8-258">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="668e8-259">不論您指定的名稱值為何，規則名稱都會是 PhishSimOverrideRule \<GUID\> ，其中 \<GUID\> 是唯一的 GUID 值 (例如，a0eae53e-d755-4a42-9320-b9c6b55c5011) 。</span><span class="sxs-lookup"><span data-stu-id="668e8-259">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="668e8-260">有效的 IP 位址專案為下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="668e8-260">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="668e8-261">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="668e8-261">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="668e8-262">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="668e8-262">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="668e8-263">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="668e8-263">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="668e8-264">此範例會建立具有指定設定的網路釣魚類比覆寫規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-264">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="668e8-265">如需詳細的語法及參數資訊，請參閱 [PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="668e8-265">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="668e8-266">使用 PowerShell 來查看網路釣魚類比覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-266">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="668e8-267">此範例會傳回單一網路釣魚類比覆寫原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="668e8-267">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="668e8-268">如需詳細的語法及參數資訊，請參閱 [PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-268">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="668e8-269">使用 PowerShell 來查看網路釣魚類比覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-269">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="668e8-270">此範例會傳回網路釣魚類比覆寫規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="668e8-270">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="668e8-271">雖然上一個命令只會傳回一個規則，但結果中也可能會包含任何擱置刪除的規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-271">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="668e8-272">這個範例會識別 (一) 和任何無效規則的有效規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-272">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="668e8-273">在您識別不正確規則之後，您可以使用 **PhisSimOverrideRule** 指令程式（如 [本文稍後](#use-powershell-to-remove-phishing-simulation-override-rules)所述）移除這些規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-273">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="668e8-274">如需詳細的語法及參數資訊，請參閱 [PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="668e8-274">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="668e8-275">使用 PowerShell 修改網路釣魚類比覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-275">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="668e8-276">若要修改網路釣魚類比覆寫原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="668e8-276">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="668e8-277">此範例會停用網路釣魚類比覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="668e8-277">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="668e8-278">如需詳細的語法及參數資訊，請參閱 [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-278">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="668e8-279">使用 PowerShell 修改網路釣魚類比覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-279">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="668e8-280">若要修改網路釣魚類比覆寫規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="668e8-280">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="668e8-281">此範例會使用下列設定修改指定的網路釣魚類比覆寫規則：</span><span class="sxs-lookup"><span data-stu-id="668e8-281">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="668e8-282">新增網域專案 blueyonderairlines.com。</span><span class="sxs-lookup"><span data-stu-id="668e8-282">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="668e8-283">移除 IP 位址專案192.168.1.55。</span><span class="sxs-lookup"><span data-stu-id="668e8-283">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="668e8-284">請注意，這些變更不會影響現有專案。</span><span class="sxs-lookup"><span data-stu-id="668e8-284">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="668e8-285">如需詳細的語法及參數資訊，請參閱 [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="668e8-285">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="668e8-286">使用 PowerShell 移除網路釣魚類比覆寫原則</span><span class="sxs-lookup"><span data-stu-id="668e8-286">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="668e8-287">此範例會移除網路釣魚類比覆寫原則和對應的規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-287">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="668e8-288">如需詳細的語法及參數資訊，請參閱 [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="668e8-288">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="668e8-289">使用 PowerShell 移除網路釣魚類比覆寫規則</span><span class="sxs-lookup"><span data-stu-id="668e8-289">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="668e8-290">若要移除網路釣魚類比覆寫規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="668e8-290">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="668e8-291">此範例會移除指定的網路釣魚類比覆寫規則。</span><span class="sxs-lookup"><span data-stu-id="668e8-291">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="668e8-292">如需詳細的語法及參數資訊，請參閱 [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="668e8-292">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
