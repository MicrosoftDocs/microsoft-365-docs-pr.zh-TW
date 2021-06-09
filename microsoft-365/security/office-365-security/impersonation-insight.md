---
title: 模擬深入解析
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解類比真知灼見的運作方式。 他們可以快速判斷哪些寄件者合法將電子郵件傳送至其組織，而不是透過電子郵件驗證檢查 (SPF、DKIM 或 DMARC) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b539cc50d3cf6ad637a749faa9d2cb5b2033b81
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821319"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a><span data-ttu-id="33d52-104">Office 365 的 Defender 中的模仿洞察力</span><span class="sxs-lookup"><span data-stu-id="33d52-104">Impersonation insight in Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33d52-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="33d52-105">**Applies to**</span></span>
- [<span data-ttu-id="33d52-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="33d52-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="33d52-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33d52-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="33d52-108">本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="33d52-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="33d52-109">類比是指電子郵件寄件者與實際或預期寄件者電子郵件地址非常類似的地方。</span><span class="sxs-lookup"><span data-stu-id="33d52-109">Impersonation is where the sender of an email message looks very similar to a real or expected sender email address.</span></span> <span data-ttu-id="33d52-110">攻擊者常常會利用網路釣魚或其他類型的攻擊中的使用者模仿寄件者電子郵件地址，以取得收件者的信任。</span><span class="sxs-lookup"><span data-stu-id="33d52-110">Attackers often user impersonated sender email addresses in phishing or other types of attacks in an effort to gain the trust of the recipient.</span></span> <span data-ttu-id="33d52-111">這主要有兩種模擬類型：</span><span class="sxs-lookup"><span data-stu-id="33d52-111">There are basically two types of impersonation:</span></span>

- <span data-ttu-id="33d52-112">**網域** 模擬：非 lila@contoso.com，類比寄件者的電子郵件地址是 lila@ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="33d52-112">**Domain impersonation**: Instead of lila@contoso.com, the impersonated sender's email address is lila@ćóntoso.com.</span></span>
- <span data-ttu-id="33d52-113">**使用者** 模擬：非 michelle@contoso.com，類比寄件者的電子郵件地址是 rnichell@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="33d52-113">**User impersonation**: Instead of michelle@contoso.com, the impersonated sender's email address is rnichell@contoso.com.</span></span>

<span data-ttu-id="33d52-114">網域模擬與 [網域欺騙](anti-spoofing-protection.md)不同，因為模擬的網域通常是實際註冊的網域。</span><span class="sxs-lookup"><span data-stu-id="33d52-114">Domain impersonation is different from [domain spoofing](anti-spoofing-protection.md), because the impersonated domain is typically a real, registered domain.</span></span> <span data-ttu-id="33d52-115">來自模擬網域中寄件者的郵件，通常可通過一般的電子郵件驗證檢查，以驗證 (SPF、DKIM 及 DMARC) 的欺騙嘗試。</span><span class="sxs-lookup"><span data-stu-id="33d52-115">Messages from senders in the impersonated domain can and often do pass regular email authentication checks that would otherwise identify spoofing attempts (SPF, DKIM, and DMARC).</span></span>

<span data-ttu-id="33d52-116">模擬保護是適用于 Microsoft Defender Office 365 的反網路釣魚原則設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="33d52-116">Impersonation protection is part of the anti-phishing policy settings that are exclusive to Microsoft Defender for Office 365.</span></span> <span data-ttu-id="33d52-117">如需這些設定的詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的模仿設定 Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="33d52-117">For more information about these settings, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="33d52-118">您可以使用 Microsoft 365 security center 中的模仿洞察力，快速識別已設定為模擬保護的模仿寄件者或寄件者網域中的郵件。</span><span class="sxs-lookup"><span data-stu-id="33d52-118">You can use the impersonation insight in the Microsoft 365 security center to quickly identify messages from impersonated senders or sender domains that you've configured for impersonation protection.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33d52-119">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="33d52-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33d52-120">您可以開啟安全性中心，網址為 <https://security.microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="33d52-120">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="33d52-121">若要直接移至 **反網路釣魚** 網頁上的類比洞察力，請使用 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="33d52-121">To go directly to the impersonation insight on the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span> <span data-ttu-id="33d52-122">若要直接移至 [模擬 **洞察力** ] 頁面，請使用 <https://security.microsoft.com/impersonationinsight> 。</span><span class="sxs-lookup"><span data-stu-id="33d52-122">To go directly to the **Impersonation insight** page, use <https://security.microsoft.com/impersonationinsight>.</span></span>

- <span data-ttu-id="33d52-123">您必須先在 [安全性中心] 中指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="33d52-123">You need to be assigned permissions in the security center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="33d52-124">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="33d52-124">**Organization Management**</span></span>
  - <span data-ttu-id="33d52-125">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="33d52-125">**Security Administrator**</span></span>
  - <span data-ttu-id="33d52-126">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="33d52-126">**Security Reader**</span></span>
  - <span data-ttu-id="33d52-127">**全域讀取者**</span><span class="sxs-lookup"><span data-stu-id="33d52-127">**Global Reader**</span></span>

  <span data-ttu-id="33d52-128">如需詳細資訊，請參閱 [安全性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="33d52-128">For more information, see [Permissions in the security center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="33d52-129">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色 _，_ 可為使用者提供 Microsoft 365 中其他功能的必要許可權。</span><span class="sxs-lookup"><span data-stu-id="33d52-129">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the security center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="33d52-130">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="33d52-130">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="33d52-131">您可以在 Microsoft Defender 的反網路釣魚原則中啟用和設定模擬保護，以供 Office 365。</span><span class="sxs-lookup"><span data-stu-id="33d52-131">You enable and configure impersonation protection in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="33d52-132">預設不會啟用類比保護。</span><span class="sxs-lookup"><span data-stu-id="33d52-132">Impersonation protection is not enabled by default.</span></span> <span data-ttu-id="33d52-133">如需詳細資訊，請參閱[Configure Office 365 的 Microsoft Defender 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="33d52-133">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="open-the-impersonation-insight-in-the-security-center"></a><span data-ttu-id="33d52-134">在 [安全性中心] 開啟類比真知灼見</span><span class="sxs-lookup"><span data-stu-id="33d52-134">Open the impersonation insight in the security center</span></span>

1. <span data-ttu-id="33d52-135">在 [安全性中心] 中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則** 原則] \> 區段 \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="33d52-135">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33d52-136">在 [ **反網路釣魚** ] 頁面上，類比洞察力看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="33d52-136">On the **Anti-phishing** page, the impersonation insight looks like this:</span></span>

   ![反網路釣魚原則頁面上的模擬洞察力和欺騙智慧](../../media/m365-sc-impersonation-and-spoof-intelligence-insight.png)

   <span data-ttu-id="33d52-138">洞察力有兩種模式：</span><span class="sxs-lookup"><span data-stu-id="33d52-138">The insight has two modes:</span></span>

    - <span data-ttu-id="33d52-139">**深入瞭解模式**：如果在任何反網路釣魚原則中啟用並設定了模擬保護，則真知灼見會顯示在過去七天內，由模擬的網域和模擬使用者 (寄件者) 所偵測到的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="33d52-139">**Insight mode**: If impersonation protection is enabled and configured in any anti-phishing policies, the insight shows the number of detected messages from impersonated domains and impersonated users (senders) over the past seven days.</span></span> <span data-ttu-id="33d52-140">這是所有反網路釣魚原則中偵測到的所有已模擬寄件者總數。</span><span class="sxs-lookup"><span data-stu-id="33d52-140">This is the total of all detected impersonated senders from all anti-phishing policies.</span></span>
    - <span data-ttu-id="33d52-141">**假設模式**：如果未啟用並設定任何使用中的反網路釣魚原則，則洞察力會顯示在過去7天內，類比保護功能 *會* 偵測到的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="33d52-141">**What if mode**: If impersonation protection is not enabled and configured in any active anti-phishing policies, the insight shows you how many messages *would* have been detected by our impersonation protection capabilities over the past seven days.</span></span>

<span data-ttu-id="33d52-142">若要查看模擬偵測的相關資訊，請按一下 [類比洞察力] 中的 [ **view impersonations** ]。</span><span class="sxs-lookup"><span data-stu-id="33d52-142">To view information about the impersonation detections, click **View impersonations** in the impersonation insight.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33d52-143">如需有關欺騙智慧洞察力的詳細資訊，請參閱 [EOP 中的欺騙智慧洞察力](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="33d52-143">For information about the spoof intelligence insight, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).</span></span>

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a><span data-ttu-id="33d52-144">從類比網域中的寄件者查看郵件相關資訊</span><span class="sxs-lookup"><span data-stu-id="33d52-144">View information about messages from senders in impersonated domains</span></span>

<span data-ttu-id="33d52-145">在 [模擬洞察力] 中按一下 [ **View impersonations** ] 之後所出現的 [**類比洞察力**] 頁面，確認已選取 [**網域**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="33d52-145">On the **Impersonation insight** page that appears after you click **View impersonations** in the impersonation insight, verify that the **Domains** tab is selected.</span></span> <span data-ttu-id="33d52-146">[ **網域** ] 索引標籤包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="33d52-146">The **Domains** tab contains the following information:</span></span>

- <span data-ttu-id="33d52-147">**寄件者網域**：模仿的網域，它是用來傳送電子郵件的網域。</span><span class="sxs-lookup"><span data-stu-id="33d52-147">**Sender Domain**: The impersonating domain, which is the domain that was used to send the email message.</span></span>
- <span data-ttu-id="33d52-148">**郵件計數**：從過去7天類比寄件者網域的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="33d52-148">**Message count**: The number of messages from impersonating sender domain over the last 7 days.</span></span>
- <span data-ttu-id="33d52-149">模擬 **類型**：此值會顯示模擬 (的偵測位置（例如，**網域在位址) 中**）。</span><span class="sxs-lookup"><span data-stu-id="33d52-149">**Impersonation type**: This value shows the detected location of the impersonation (for example, **Domain in address**).</span></span>
- <span data-ttu-id="33d52-150">模擬的 **網域 (s)**：模擬的網域，它應接近于在反網路釣魚原則中為模擬保護設定的網域。</span><span class="sxs-lookup"><span data-stu-id="33d52-150">**Impersonated domain(s)**: The impersonated domain, which should closely resemble the domain that's configured for impersonation protection in the anti-phishing policy.</span></span>
- <span data-ttu-id="33d52-151">**網欄位型別**：此值是自訂網域的內部網域或 **自訂網域** 的 **公司網域**。</span><span class="sxs-lookup"><span data-stu-id="33d52-151">**Domain type**: This value is **Company domain** for internal domains or **Custom domain** for custom domains.</span></span>
- <span data-ttu-id="33d52-152">**原則**：偵測到模擬的網域的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="33d52-152">**Policy**: The anti-phishing policy that detected the impersonated domain.</span></span>
- <span data-ttu-id="33d52-153">**允許模仿**：下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="33d52-153">**Allowed to impersonate**: One of the following values:</span></span>
  - <span data-ttu-id="33d52-154">**是**：網域已設定為受信任的網域 (反網路釣魚原則中的類比保護) 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="33d52-154">**Yes**: The domain was configured as trusted domain (an exception for impersonation protection) in the anti-phishing policy.</span></span> <span data-ttu-id="33d52-155">已偵測到來自類比網域中寄件者的郵件，但允許。</span><span class="sxs-lookup"><span data-stu-id="33d52-155">Messages from senders in the impersonated domain were detected, but allowed.</span></span>
  - <span data-ttu-id="33d52-156">**No**：網域已設定為在反網路釣魚原則中進行類比保護。</span><span class="sxs-lookup"><span data-stu-id="33d52-156">**No**: The domain was configured for impersonation protection in the anti-phishing policy.</span></span> <span data-ttu-id="33d52-157">已偵測來自模擬網域中寄件者的郵件，並根據反網路釣魚原則中模擬網域的動作來採取行動。</span><span class="sxs-lookup"><span data-stu-id="33d52-157">Messages from senders in the impersonated domain were detected and acted upon based on the action for impersonated domains in the anti-phishing policy.</span></span>

<span data-ttu-id="33d52-158">您可以按一下 [選取的欄標題] 來排序結果。</span><span class="sxs-lookup"><span data-stu-id="33d52-158">You can click selected column headings to sort the results.</span></span>

<span data-ttu-id="33d52-159">若要篩選結果，您可以使用「 ![ 搜尋」圖示 ](../../media/m365-cc-sc-search-icon.png) **搜尋** 方塊來輸入以逗號分隔的值清單，以篩選結果。</span><span class="sxs-lookup"><span data-stu-id="33d52-159">To filter the results, you can use the ![Search icon](../../media/m365-cc-sc-search-icon.png) **Search** box to enter a comma-separated list of values to filter the results.</span></span>

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a><span data-ttu-id="33d52-160">從類比網域中的寄件者查看郵件的詳細資料</span><span class="sxs-lookup"><span data-stu-id="33d52-160">View details about messages from senders in impersonated domains</span></span>

<span data-ttu-id="33d52-161">在 [模擬 **洞察力**] 頁面上的 [**網域**] 索引標籤上，選取其中一個可用的類比偵測。</span><span class="sxs-lookup"><span data-stu-id="33d52-161">On the **Domains** tab on the **Impersonation insight** page, select one of the available impersonation detections.</span></span> <span data-ttu-id="33d52-162">出現的詳細資料浮出控制項包含下列資訊和功能：</span><span class="sxs-lookup"><span data-stu-id="33d52-162">The details flyout that appears contains the following information and features:</span></span>

- <span data-ttu-id="33d52-163">**要修改的選取專案模擬原則**：選取您要修改的受影響的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="33d52-163">**Selection impersonation policy to modify**: Select the affected anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="33d52-164">僅適用于原則中定義模擬網域的原則。</span><span class="sxs-lookup"><span data-stu-id="33d52-164">Only polices where the impersonated domain is defined in the policy are available.</span></span> <span data-ttu-id="33d52-165">請參閱前一頁，查看哪個原則實際負責偵測模擬的網域 (可能是根據收件者和原則) 的優先順序而定。</span><span class="sxs-lookup"><span data-stu-id="33d52-165">Refer to the previous page to see which policy was actually responsible for detecting the impersonated domain (likely based on the recipient and the priority of the policy).</span></span>
- <span data-ttu-id="33d52-166">**新增至允許的模仿清單**：使用此切換，可在 [ **信任的寄件者和網域** ] 中新增或移除寄件者。 (類比例外狀況) 針對您選取的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="33d52-166">**Add to the allowed to impersonation list**: Use this toggle to add or remove the sender from the **Trusted senders and domains** (impersonation exceptions) for the anti-phishing policy that you selected:</span></span>
  - <span data-ttu-id="33d52-167">如果此專案的 **允許** 模擬值為 [ **否**]，則會關閉切換功能。</span><span class="sxs-lookup"><span data-stu-id="33d52-167">If the **Allowed to impersonate** value for this entry was **No**, the toggle is off.</span></span> <span data-ttu-id="33d52-168">若要免除模擬保護評估此網域中的所有寄件者，請將開關滑動至 [開啟]：開啟開啟] ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="33d52-168">To exempt all senders in this domain from evaluation by impersonation protection, slide the toggle to on: ![Toggle on](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="33d52-169">網域會新增至反網路釣魚原則之類比保護設定中的 [ **受信任的網域** ] 清單。</span><span class="sxs-lookup"><span data-stu-id="33d52-169">The domain is added to the **Trusted domains** list in the impersonation protection settings of the anti-phishing policy.</span></span>
  - <span data-ttu-id="33d52-170">如果此專案的 **允許** 模擬值為 **[是]**，則開啟切換功能。</span><span class="sxs-lookup"><span data-stu-id="33d52-170">If the **Allowed to impersonate** value for this entry was **Yes**, the toggle is on.</span></span> <span data-ttu-id="33d52-171">若要透過模擬保護將此網域中的所有寄件者傳回評估，請將此開關滑動至 [關閉]： [關閉] ![ ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="33d52-171">To return all senders in this domain to evaluation by impersonation protection, slide the toggle to off: ![Toggle off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="33d52-172">此網域會從反網路釣魚原則的類比保護設定中的 [ **受信任的網域** ] 清單中移除。</span><span class="sxs-lookup"><span data-stu-id="33d52-172">The domain is removed from the **Trusted domains** list in the impersonation protection settings of the anti-phishing policy.</span></span>
- <span data-ttu-id="33d52-173">我們為何會發現這種情況。</span><span class="sxs-lookup"><span data-stu-id="33d52-173">Why we caught this.</span></span>
- <span data-ttu-id="33d52-174">您需要執行的工作。</span><span class="sxs-lookup"><span data-stu-id="33d52-174">What you need to do.</span></span>
- <span data-ttu-id="33d52-175">列出類比網域的域摘要。</span><span class="sxs-lookup"><span data-stu-id="33d52-175">A domain summary that list the impersonated domain.</span></span>
- <span data-ttu-id="33d52-176">WhoIs 寄件者的相關資料。</span><span class="sxs-lookup"><span data-stu-id="33d52-176">WhoIs data about the sender.</span></span>
- <span data-ttu-id="33d52-177">開啟 [威脅瀏覽器](threat-explorer.md) 的連結，以查看有關寄件者的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="33d52-177">A link to open [Threat Explorer](threat-explorer.md) to see additional details about the sender.</span></span>
- <span data-ttu-id="33d52-178">來自相同寄件者的類似郵件已傳遞給您的組織。</span><span class="sxs-lookup"><span data-stu-id="33d52-178">Similar messages from the same sender that were delivered to your organization.</span></span>

## <a name="view-information-about-messages-from-impersonated-senders"></a><span data-ttu-id="33d52-179">查看類比寄件者的郵件相關資訊</span><span class="sxs-lookup"><span data-stu-id="33d52-179">View information about messages from impersonated senders</span></span>

<span data-ttu-id="33d52-180">在 [模擬洞察力] 中按一下 [ **View impersonations** ] 之後所出現的 [**類比洞察力**] 頁面，按一下 [**使用者**] 索引標籤。[**使用者**] 索引標籤包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="33d52-180">On the **Impersonation insight** page that appears after you click **View impersonations** in the impersonation insight, click the **Users** tab. The **Users** tab contains the following information:</span></span>

- <span data-ttu-id="33d52-181">**寄件者**：傳送電子郵件之模仿寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="33d52-181">**Sender**: The email address of the impersonating sender that sent the email message.</span></span>
- <span data-ttu-id="33d52-182">**郵件數目**：來自于過去7天之模仿寄件者的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="33d52-182">**Message count**: The number of messages from the impersonating sender over the last 7 days.</span></span>
- <span data-ttu-id="33d52-183">**模仿類型**：此值是 **使用者在顯示名稱中**。</span><span class="sxs-lookup"><span data-stu-id="33d52-183">**Impersonation type**: This value is **User in display name**.</span></span>
- <span data-ttu-id="33d52-184">模擬 **使用者 (s)**：模擬之寄件者的電子郵件地址，其應接近于在反網路釣魚原則中為模擬保護設定的使用者。</span><span class="sxs-lookup"><span data-stu-id="33d52-184">**Impersonated user(s)**: The email address of the impersonated sender, which should closely resemble the user that's configured for impersonation protection in the anti-phishing policy.</span></span>
- <span data-ttu-id="33d52-185">**使用者類型**：此值顯示套用的保護類型 (例如， **受保護的使用者** 或 **信箱智慧**) 。</span><span class="sxs-lookup"><span data-stu-id="33d52-185">**User type**: This value shows the type of protection applied (for example, **Protected user** or **Mailbox Intelligence**).</span></span>
- <span data-ttu-id="33d52-186">**原則**：偵測模擬寄件者的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="33d52-186">**Policy**: The anti-phishing policy that detected the impersonated sender.</span></span>
- <span data-ttu-id="33d52-187">**允許模仿**：下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="33d52-187">**Allowed to impersonate**: One of the following values:</span></span>
  - <span data-ttu-id="33d52-188">**是**：寄件者已設定為「信任的使用者」 (反網路釣魚原則中的類比保護) 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="33d52-188">**Yes**: The sender was configured as trusted user (an exception for impersonation protection) in the anti-phishing policy.</span></span> <span data-ttu-id="33d52-189">偵測到來自類比寄件者的郵件，但允許。</span><span class="sxs-lookup"><span data-stu-id="33d52-189">Messages from the impersonated sender were detected, but allowed.</span></span>
  - <span data-ttu-id="33d52-190">**No**：在反網路釣魚原則中，寄件者已設定為類比保護。</span><span class="sxs-lookup"><span data-stu-id="33d52-190">**No**: The sender was configured for impersonation protection in the anti-phishing policy.</span></span> <span data-ttu-id="33d52-191">偵測到寄件者的郵件會根據反網路釣魚原則中模擬使用者的動作偵測並處理。</span><span class="sxs-lookup"><span data-stu-id="33d52-191">Messages from the impersonated sender were detected and acted upon based on the action for impersonated users in the anti-phishing policy.</span></span>

<span data-ttu-id="33d52-192">您可以按一下 [選取的欄標題] 來排序結果。</span><span class="sxs-lookup"><span data-stu-id="33d52-192">You can click selected column headings to sort the results.</span></span>

<span data-ttu-id="33d52-193">若要篩選結果，您可以使用 [ **篩選寄件者** ] 方塊來輸入以逗號分隔的值清單，以篩選結果。</span><span class="sxs-lookup"><span data-stu-id="33d52-193">To filter the results, you can use the **Filter sender** box to enter a comma-separated list of values to filter the results.</span></span>

### <a name="view-details-about-messages-from-impersonated-senders"></a><span data-ttu-id="33d52-194">從類比寄件者查看郵件的詳細資料</span><span class="sxs-lookup"><span data-stu-id="33d52-194">View details about messages from impersonated senders</span></span>

<span data-ttu-id="33d52-195">在 [**類比洞察力**] 頁面上的 [**使用者**] 索引標籤上，選取其中一個可用的模擬偵測。</span><span class="sxs-lookup"><span data-stu-id="33d52-195">On the **Users** tab on the **Impersonation insight** page, select one of the available impersonation detections.</span></span> <span data-ttu-id="33d52-196">出現的詳細資料浮出控制項包含下列資訊和功能：</span><span class="sxs-lookup"><span data-stu-id="33d52-196">The details flyout that appears contains the following information and features:</span></span>

- <span data-ttu-id="33d52-197">**要修改的選取專案模擬原則**：選取您要修改的受影響的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="33d52-197">**Selection impersonation policy to modify**: Select the affected anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="33d52-198">只提供在原則中定義模擬寄件者的原則。</span><span class="sxs-lookup"><span data-stu-id="33d52-198">Only polices where the impersonated sender is defined in the policy are available.</span></span> <span data-ttu-id="33d52-199">請參閱上一頁，查看哪個原則實際負責偵測模擬寄件者 (可能是根據收件者和原則) 的優先順序而定。</span><span class="sxs-lookup"><span data-stu-id="33d52-199">Refer to the previous page to see which policy was actually responsible for detecting the impersonated sender (likely based on the recipient and the priority of the policy).</span></span>
- <span data-ttu-id="33d52-200">**新增至允許的模仿清單**：使用此切換，可在 [ **信任的寄件者和網域** ] 中新增或移除寄件者。 (類比例外狀況) 針對您選取的反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="33d52-200">**Add to the allowed to impersonation list**: Use this toggle to add or remove the sender from the **Trusted senders and domains** (impersonation exceptions) for the anti-phishing policy that you selected:</span></span>
  - <span data-ttu-id="33d52-201">如果此專案的 **允許** 模擬值為 [ **否**]，則會關閉切換功能。</span><span class="sxs-lookup"><span data-stu-id="33d52-201">If the **Allowed to impersonate** value for this entry was **No**, the toggle is off.</span></span> <span data-ttu-id="33d52-202">若要將收件者從類比保護中免除，請將切換滑動至 [開啟] 開啟 ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="33d52-202">To exempt the sender from evaluation by impersonation protection, slide the toggle to on: ![Toggle on](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="33d52-203">寄件者會新增至反網路釣魚原則之類比保護設定中的 [ **信任的使用者** ] 清單。</span><span class="sxs-lookup"><span data-stu-id="33d52-203">The sender is added to the **Trusted users** list in the impersonation protection settings of the anti-phishing policy.</span></span>
  - <span data-ttu-id="33d52-204">如果此專案的 **允許** 模擬值為 **[是]**，則開啟切換功能。</span><span class="sxs-lookup"><span data-stu-id="33d52-204">If the **Allowed to impersonate** value for this entry was **Yes**, the toggle is on.</span></span> <span data-ttu-id="33d52-205">若要透過模擬保護將寄件者傳回評估，請將此開關滑動至 [關閉]： [關閉] ![ ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="33d52-205">To return the sender to evaluation by impersonation protection, slide the toggle to off: ![Toggle off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="33d52-206">寄件者會從反網路釣魚原則的類比保護設定中的 [ **信任的使用者** ] 清單中移除。</span><span class="sxs-lookup"><span data-stu-id="33d52-206">The sender is removed from the **Trusted users** list in the impersonation protection settings of the anti-phishing policy.</span></span>
- <span data-ttu-id="33d52-207">我們為何會發現這種情況。</span><span class="sxs-lookup"><span data-stu-id="33d52-207">Why we caught this.</span></span>
- <span data-ttu-id="33d52-208">您需要執行的工作。</span><span class="sxs-lookup"><span data-stu-id="33d52-208">What you need to do.</span></span>
- <span data-ttu-id="33d52-209">列出類比寄件者的寄件者摘要。</span><span class="sxs-lookup"><span data-stu-id="33d52-209">A sender summary that list the impersonated sender.</span></span>
- <span data-ttu-id="33d52-210">WhoIs 寄件者的相關資料。</span><span class="sxs-lookup"><span data-stu-id="33d52-210">WhoIs data about the sender.</span></span>
- <span data-ttu-id="33d52-211">開啟 [威脅瀏覽器](threat-explorer.md) 的連結，以查看有關寄件者的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="33d52-211">A link to open [Threat Explorer](threat-explorer.md) to see additional details about the sender.</span></span>
- <span data-ttu-id="33d52-212">來自相同寄件者的類似郵件已傳遞給您的組織。</span><span class="sxs-lookup"><span data-stu-id="33d52-212">Similar messages from the same sender that were delivered to your organization.</span></span>
