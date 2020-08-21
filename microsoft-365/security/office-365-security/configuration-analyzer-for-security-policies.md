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
description: 系統管理員可以瞭解如何使用設定分析器來尋找並修正包含低於標準防護和嚴格保護的預設安全性原則的設定的安全性原則。
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825770"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="e323c-103">EOP 和 Office 365 ATP 中保護原則的設定分析器</span><span class="sxs-lookup"><span data-stu-id="e323c-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="e323c-104">本主題中所述的功能包括預覽、並非所有組織都提供，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="e323c-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="e323c-105">Security & 合規性中心的設定分析器提供一個集中位置，以找出並修正您的任何安全性原則，其中包含預設 [安全性原則](preset-security-policies.md)中低於標準保護和嚴格保護設定檔設定的設定。</span><span class="sxs-lookup"><span data-stu-id="e323c-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="e323c-106">設定分析器會分析下列類型的原則：</span><span class="sxs-lookup"><span data-stu-id="e323c-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="e323c-107">**Exchange Online Protection (EOP) 原則**：這包括使用 exchange online 信箱的 Microsoft 365 組織和獨立 EOP 組織，但沒有 exchange online 信箱：</span><span class="sxs-lookup"><span data-stu-id="e323c-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="e323c-108">[反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e323c-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="e323c-109">[反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e323c-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="e323c-110">[EOP 反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="e323c-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="e323c-111">**Office 365 Advanced 威脅防護 (ATP) 原則**：這包括使用 Microsoft 365 E5 或 OFFICE 365 ATP 附加元件訂閱的組織：</span><span class="sxs-lookup"><span data-stu-id="e323c-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="e323c-112">ATP 反網路釣魚原則，其中包括：</span><span class="sxs-lookup"><span data-stu-id="e323c-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="e323c-113">EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="e323c-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="e323c-114">類比設定</span><span class="sxs-lookup"><span data-stu-id="e323c-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="e323c-115">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="e323c-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="e323c-116">[安全連結原則](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)。</span><span class="sxs-lookup"><span data-stu-id="e323c-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="e323c-117">[安全附件原則](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)。</span><span class="sxs-lookup"><span data-stu-id="e323c-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="e323c-118">[EOP 和 Office 365 ATP security 的建議設定](recommended-settings-for-eop-and-office365-atp.md)會說明用作基準的**標準**和**嚴格**原則設定值。</span><span class="sxs-lookup"><span data-stu-id="e323c-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e323c-119">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="e323c-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e323c-120">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e323c-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e323c-121">若要直接移至 [設定 **分析器** ] 頁面，請使用 <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="e323c-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="e323c-122">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e323c-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e323c-123">您必須已獲派權限，才能進行此主題中的程序:</span><span class="sxs-lookup"><span data-stu-id="e323c-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="e323c-124">若要使用設定分析器 **並** 更新安全性原則，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="e323c-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e323c-125">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="e323c-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e323c-126">**組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理**。</span><span class="sxs-lookup"><span data-stu-id="e323c-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="e323c-127">若要對設定分析器進行唯讀存取，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="e323c-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e323c-128">[安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者**。</span><span class="sxs-lookup"><span data-stu-id="e323c-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e323c-129">[線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理**。</span><span class="sxs-lookup"><span data-stu-id="e323c-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="e323c-130">在安全性 & 規範中心使用設定分析器</span><span class="sxs-lookup"><span data-stu-id="e323c-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="e323c-131">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**設定 \> **分析器**]。</span><span class="sxs-lookup"><span data-stu-id="e323c-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![[威脅管理原則] 頁面上的設定分析器小工具 \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="e323c-133">設定分析器有兩個主要的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="e323c-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="e323c-134">**設定和建議**：選擇 [標準] 或 [嚴格]，然後將這些設定與您現有的安全性原則進行比較。</span><span class="sxs-lookup"><span data-stu-id="e323c-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="e323c-135">在結果中，您可以調整設定的值，使其具有與標準或嚴格相同的層級。</span><span class="sxs-lookup"><span data-stu-id="e323c-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="e323c-136">設定**偏移分析和記錄**：此 view 可讓您根據設定 analyzer 在一段時間內的結果，追蹤您對原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="e323c-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="e323c-137">設定分析器中的 [設定與建議] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="e323c-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="e323c-138">依預設，索引標籤會在與標準保護設定檔的比較上開啟。</span><span class="sxs-lookup"><span data-stu-id="e323c-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="e323c-139">您可以按一下 [ **查看嚴格建議**] 切換到嚴格保護設定檔的比較。</span><span class="sxs-lookup"><span data-stu-id="e323c-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="e323c-140">若要切換回來，請選取 [ **查看標準建議**]。</span><span class="sxs-lookup"><span data-stu-id="e323c-140">To switch back, select **View Standard recommendations**.</span></span>

![設定分析器中的設定和建議視圖](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="e323c-142">根據預設，[ **原則群組/設定名稱** ] 欄會包含不同型別安全性原則的折疊模式，以及這些原則中需要提高 (如果任何) 的設定數目。</span><span class="sxs-lookup"><span data-stu-id="e323c-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="e323c-143">原則類型包括：</span><span class="sxs-lookup"><span data-stu-id="e323c-143">The types of policies are:</span></span>

- <span data-ttu-id="e323c-144">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="e323c-144">**Anti-spam**</span></span>
- <span data-ttu-id="e323c-145">**防網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="e323c-145">**Anti-phishing**</span></span>
- <span data-ttu-id="e323c-146">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="e323c-146">**Anti-malware**</span></span>
- <span data-ttu-id="e323c-147">如果您的訂閱包含 ATP) ， **Atp 安全附件** (</span><span class="sxs-lookup"><span data-stu-id="e323c-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="e323c-148">如果您的訂閱包含 ATP) ， **Atp 安全連結** (</span><span class="sxs-lookup"><span data-stu-id="e323c-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="e323c-149">在預設的視圖中，會折疊所有專案。</span><span class="sxs-lookup"><span data-stu-id="e323c-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="e323c-150">在每個原則旁，您可以修改原則的比較結果摘要， (您可以修改其原則的) ，以及您無法修改) 之標準或嚴格保護設定檔 (對應原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="e323c-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="e323c-151">您將會看到下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e323c-151">You'll see the following information:</span></span>

- <span data-ttu-id="e323c-152">**綠色**：所有現有原則中的所有設定，至少與您要比較的保護設定檔一樣安全。</span><span class="sxs-lookup"><span data-stu-id="e323c-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="e323c-153">**琥珀色**：現有原則中的少量設定，不如您要比較的保護設定檔安全。</span><span class="sxs-lookup"><span data-stu-id="e323c-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="e323c-154">**紅色**：現有原則中的大量設定，不如您要比較的保護設定檔安全。</span><span class="sxs-lookup"><span data-stu-id="e323c-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="e323c-155">這可能是許多原則中的一些設定或一個原則中的眾多設定。</span><span class="sxs-lookup"><span data-stu-id="e323c-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="e323c-156">就理想的比較而言，您會看到文字： **所有設定都會遵循** \<**Standard** or **Strict**\> **建議**。</span><span class="sxs-lookup"><span data-stu-id="e323c-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="e323c-157">否則，您會看到建議設定的變更數目。</span><span class="sxs-lookup"><span data-stu-id="e323c-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="e323c-158">如果您展開 [ **原則] 群組/設定名稱**，則會顯示每個需要注意之特定原則中的所有原則和相關設定。</span><span class="sxs-lookup"><span data-stu-id="e323c-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="e323c-159">或者，您可以展開特定類型的原則 (例如， **反垃圾郵件**) ，只查看那些需要注意之原則類型中的設定。</span><span class="sxs-lookup"><span data-stu-id="e323c-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="e323c-160">如果比較沒有改進 (綠) 的建議，則展開原則會顯示 nothing。</span><span class="sxs-lookup"><span data-stu-id="e323c-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="e323c-161">如果有任何數量的改進建議 (琥珀色或紅色) ，則會顯示需要注意的設定，並會顯示下列各欄中的對應資訊：</span><span class="sxs-lookup"><span data-stu-id="e323c-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="e323c-162">需要注意之設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="e323c-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="e323c-163">例如，在先前的螢幕擷取畫面中，它是反垃圾郵件原則中的 **大量電子郵件閾值** 。</span><span class="sxs-lookup"><span data-stu-id="e323c-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="e323c-164">**原則**：包含設定之受影響原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="e323c-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="e323c-165">**適用**于：受影響的原則所套用的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="e323c-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="e323c-166">**目前**設定：設定的目前值。</span><span class="sxs-lookup"><span data-stu-id="e323c-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="e323c-167">**上次修改**日期：上次修改原則的日期。</span><span class="sxs-lookup"><span data-stu-id="e323c-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="e323c-168">**建議**：標準或嚴格保護設定檔中的設定值。</span><span class="sxs-lookup"><span data-stu-id="e323c-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="e323c-169">若要變更原則中設定的值，使其符合保護設定檔中的建議值，請按一下 [ **採用**]。</span><span class="sxs-lookup"><span data-stu-id="e323c-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="e323c-170">如果變更成功，您會看到訊息： **已成功採用的建議**。</span><span class="sxs-lookup"><span data-stu-id="e323c-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="e323c-171">按一下 **[** 重新整理] 以查看減少的建議數量，並從結果中移除特定設定/原則列。</span><span class="sxs-lookup"><span data-stu-id="e323c-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="e323c-172">設定分析器中的設定偏移分析和記錄] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="e323c-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="e323c-173">此索引標籤可讓您根據安全性分析器中的資訊，追蹤您對自訂安全性原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="e323c-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="e323c-174">根據預設，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e323c-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="e323c-175">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="e323c-175">**Last modified**</span></span>
- <span data-ttu-id="e323c-176">**修改者**</span><span class="sxs-lookup"><span data-stu-id="e323c-176">**Modified by**</span></span>
- <span data-ttu-id="e323c-177">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="e323c-177">**Setting Name**</span></span>
- <span data-ttu-id="e323c-178">**原則**</span><span class="sxs-lookup"><span data-stu-id="e323c-178">**Policy**</span></span>
- <span data-ttu-id="e323c-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="e323c-179">**Type**</span></span>

<span data-ttu-id="e323c-180">若要篩選結果，請按一下 [篩選]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e323c-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e323c-181">在出現的 [ **篩選** ] 浮出控制項中，您可以選取下列篩選：</span><span class="sxs-lookup"><span data-stu-id="e323c-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="e323c-182"> (日期) 的**開始時間**和**結束時間**</span><span class="sxs-lookup"><span data-stu-id="e323c-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="e323c-183">**標準保護** 或 **嚴格保護**</span><span class="sxs-lookup"><span data-stu-id="e323c-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="e323c-184">若要將結果匯出至 .csv 檔案，請按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="e323c-184">To export the results to a .csv file, click **Export**.</span></span>

![設定分析器中的設定偏移分析和歷程記錄視圖](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
