---
title: 安全性原則的設定分析器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用設定分析器，找出並修正低於標準防護和嚴格保護預設安全性原則的安全性原則。
ms.openlocfilehash: ac70b7fa2b2d0ecc65cf81ea4e5e5f2e807f2467
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326576"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="96e83-103">EOP 和 Office 365 ATP 中保護原則的設定分析器</span><span class="sxs-lookup"><span data-stu-id="96e83-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="96e83-104">本主題中所述的功能包括預覽、並非所有組織都提供，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="96e83-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="96e83-105">如需發行排程的相關資訊，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer)。</span><span class="sxs-lookup"><span data-stu-id="96e83-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="96e83-106">Security & 合規性中心的設定分析器提供一個集中位置，以找出並修正安全性原則，其中的設定低於標準 [安全性原則](preset-security-policies.md)中的標準防護和嚴格保護設定檔設定。</span><span class="sxs-lookup"><span data-stu-id="96e83-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="96e83-107">設定分析器會分析下列類型的原則：</span><span class="sxs-lookup"><span data-stu-id="96e83-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="96e83-108">**Exchange Online Protection (EOP) 原則**：這包括使用 exchange online 信箱的 Microsoft 365 組織和獨立 EOP 組織，但沒有 exchange online 信箱：</span><span class="sxs-lookup"><span data-stu-id="96e83-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="96e83-109">[反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="96e83-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="96e83-110">[反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="96e83-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="96e83-111">[EOP 反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="96e83-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="96e83-112">**Office 365 Advanced 威脅防護 (ATP) 原則**：這包括使用 Microsoft 365 E5 或 OFFICE 365 ATP 附加元件訂閱的組織：</span><span class="sxs-lookup"><span data-stu-id="96e83-112">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="96e83-113">ATP 反網路釣魚原則，其中包括：</span><span class="sxs-lookup"><span data-stu-id="96e83-113">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="96e83-114">EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="96e83-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="96e83-115">類比設定</span><span class="sxs-lookup"><span data-stu-id="96e83-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="96e83-116">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="96e83-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="96e83-117">[安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="96e83-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="96e83-118">[安全附件原則](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="96e83-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="96e83-119">[EOP 和 Office 365 ATP security 的建議設定](recommended-settings-for-eop-and-office365-atp.md)會說明用作基準的**標準**和**嚴格**原則設定值。</span><span class="sxs-lookup"><span data-stu-id="96e83-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96e83-120">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="96e83-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="96e83-121">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="96e83-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="96e83-122">若要直接移至 [設定 **分析器** ] 頁面，請使用 <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="96e83-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="96e83-123">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="96e83-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="96e83-124">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="96e83-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="96e83-125">若要使用設定分析器 **並** 更新安全性原則，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="96e83-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="96e83-126">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="96e83-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="96e83-127">**組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理**。</span><span class="sxs-lookup"><span data-stu-id="96e83-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="96e83-128">若要對設定分析器進行唯讀存取，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="96e83-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="96e83-129">[安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者**。</span><span class="sxs-lookup"><span data-stu-id="96e83-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="96e83-130">[線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理**。</span><span class="sxs-lookup"><span data-stu-id="96e83-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="96e83-131">在安全性 & 規範中心使用設定分析器</span><span class="sxs-lookup"><span data-stu-id="96e83-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="96e83-132">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**設定 \> **分析器**]。</span><span class="sxs-lookup"><span data-stu-id="96e83-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![[威脅管理原則] 頁面上的設定分析器小工具 \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="96e83-134">設定分析器有兩個主要的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="96e83-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="96e83-135">**設定和建議**：選擇 [標準] 或 [嚴格]，然後將這些設定與您現有的安全性原則進行比較。</span><span class="sxs-lookup"><span data-stu-id="96e83-135">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="96e83-136">在結果中，您可以調整設定的值，使其具有與標準或嚴格相同的層級。</span><span class="sxs-lookup"><span data-stu-id="96e83-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="96e83-137">設定**偏移分析和記錄**：此 view 可讓您追蹤一段時間的原則變更。</span><span class="sxs-lookup"><span data-stu-id="96e83-137">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="96e83-138">設定分析器中的 [設定與建議] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="96e83-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="96e83-139">依預設，索引標籤會在與標準保護設定檔的比較上開啟。</span><span class="sxs-lookup"><span data-stu-id="96e83-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="96e83-140">您可以按一下 [ **查看嚴格建議**] 切換到嚴格保護設定檔的比較。</span><span class="sxs-lookup"><span data-stu-id="96e83-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="96e83-141">若要切換回來，請選取 [ **查看標準建議**]。</span><span class="sxs-lookup"><span data-stu-id="96e83-141">To switch back, select **View Standard recommendations**.</span></span>

![設定分析器中的設定和建議視圖](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="96e83-143">根據預設，[ **原則群組/設定名稱** ] 欄會包含不同類型的安全性原則及設定數目的折疊模式，如果有任何) 則需要改進 (。</span><span class="sxs-lookup"><span data-stu-id="96e83-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="96e83-144">原則類型包括：</span><span class="sxs-lookup"><span data-stu-id="96e83-144">The types of policies are:</span></span>

- <span data-ttu-id="96e83-145">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="96e83-145">**Anti-spam**</span></span>
- <span data-ttu-id="96e83-146">**防網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="96e83-146">**Anti-phishing**</span></span>
- <span data-ttu-id="96e83-147">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="96e83-147">**Anti-malware**</span></span>
- <span data-ttu-id="96e83-148">如果您的訂閱包含 ATP) ， **Atp 安全附件** (</span><span class="sxs-lookup"><span data-stu-id="96e83-148">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="96e83-149">如果您的訂閱包含 ATP) ， **Atp 安全連結** (</span><span class="sxs-lookup"><span data-stu-id="96e83-149">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="96e83-150">在預設的視圖中，會折疊所有專案。</span><span class="sxs-lookup"><span data-stu-id="96e83-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="96e83-151">每個原則旁都有一個原則的比較結果摘要，您可以在您的原則 (中修改) 和設定標準或嚴格保護設定檔對應之原則中的設定， (但不能修改) 。</span><span class="sxs-lookup"><span data-stu-id="96e83-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="96e83-152">您將會看到您要比較的保護設定檔的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="96e83-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="96e83-153">**綠色**：所有現有原則中的所有設定，至少都是保護設定檔的安全性。</span><span class="sxs-lookup"><span data-stu-id="96e83-153">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="96e83-154">**琥珀色**：現有原則中的少量設定，不如保護設定檔的安全性。</span><span class="sxs-lookup"><span data-stu-id="96e83-154">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="96e83-155">**紅色**：現有原則中的大量設定與保護設定檔的安全性不符。</span><span class="sxs-lookup"><span data-stu-id="96e83-155">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="96e83-156">這可能是許多原則中的一些設定或一個原則中的眾多設定。</span><span class="sxs-lookup"><span data-stu-id="96e83-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="96e83-157">就理想的比較而言，您會看到文字： **所有設定都會遵循** \<**Standard** or **Strict**\> **建議**。</span><span class="sxs-lookup"><span data-stu-id="96e83-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="96e83-158">否則，您會看到建議設定的變更數目。</span><span class="sxs-lookup"><span data-stu-id="96e83-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="96e83-159">如果您展開 [ **原則] 群組/設定名稱**，則會顯示每個需要注意之特定原則中的所有原則和相關設定。</span><span class="sxs-lookup"><span data-stu-id="96e83-159">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="96e83-160">或者，您可以展開特定類型的原則 (例如， **反垃圾郵件**) ，只查看那些需要注意之原則類型中的設定。</span><span class="sxs-lookup"><span data-stu-id="96e83-160">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="96e83-161">如果比較沒有改進 (綠) 的建議，則展開原則會顯示 nothing。</span><span class="sxs-lookup"><span data-stu-id="96e83-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="96e83-162">如果有任何數量的改進建議 (琥珀色或紅色) ，則會顯示需要注意的設定，並會顯示下列各欄中的對應資訊：</span><span class="sxs-lookup"><span data-stu-id="96e83-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="96e83-163">需要注意之設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="96e83-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="96e83-164">例如，在先前的螢幕擷取畫面中，它是反垃圾郵件原則中的 **大量電子郵件閾值** 。</span><span class="sxs-lookup"><span data-stu-id="96e83-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="96e83-165">**原則**：包含設定之受影響原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="96e83-165">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="96e83-166">**適用**于：受影響的原則所套用的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="96e83-166">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="96e83-167">**目前**設定：設定的目前值。</span><span class="sxs-lookup"><span data-stu-id="96e83-167">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="96e83-168">**上次修改**日期：上次修改原則的日期。</span><span class="sxs-lookup"><span data-stu-id="96e83-168">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="96e83-169">**建議**：標準或嚴格保護設定檔中的設定值。</span><span class="sxs-lookup"><span data-stu-id="96e83-169">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="96e83-170">若要變更原則中設定的值，使其符合保護設定檔中的建議值，請按一下 [ **採用**]。</span><span class="sxs-lookup"><span data-stu-id="96e83-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="96e83-171">如果變更成功，您會看到訊息： **已成功採用的建議**。</span><span class="sxs-lookup"><span data-stu-id="96e83-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="96e83-172">按一下 **[** 重新整理] 以查看減少的建議數量，並從結果中移除特定設定/原則列。</span><span class="sxs-lookup"><span data-stu-id="96e83-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="96e83-173">設定分析器中的設定偏移分析和記錄] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="96e83-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="96e83-174">此索引標籤可讓您追蹤您對自訂安全性原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="96e83-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="96e83-175">根據預設，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="96e83-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="96e83-176">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="96e83-176">**Last modified**</span></span>
- <span data-ttu-id="96e83-177">**修改者**</span><span class="sxs-lookup"><span data-stu-id="96e83-177">**Modified by**</span></span>
- <span data-ttu-id="96e83-178">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="96e83-178">**Setting Name**</span></span>
- <span data-ttu-id="96e83-179">**原則**</span><span class="sxs-lookup"><span data-stu-id="96e83-179">**Policy**</span></span>
- <span data-ttu-id="96e83-180">**Type**</span><span class="sxs-lookup"><span data-stu-id="96e83-180">**Type**</span></span>

<span data-ttu-id="96e83-181">若要篩選結果，請按一下 [篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="96e83-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="96e83-182">在出現的 [ **篩選** ] 浮出控制項中，您可以選取下列篩選：</span><span class="sxs-lookup"><span data-stu-id="96e83-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="96e83-183"> (日期) 的**開始時間**和**結束時間**</span><span class="sxs-lookup"><span data-stu-id="96e83-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="96e83-184">**標準保護** 或 **嚴格保護**</span><span class="sxs-lookup"><span data-stu-id="96e83-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="96e83-185">若要將結果匯出至 .csv 檔案，請按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="96e83-185">To export the results to a .csv file, click **Export**.</span></span>

![設定分析器中的設定偏移分析和歷程記錄視圖](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
