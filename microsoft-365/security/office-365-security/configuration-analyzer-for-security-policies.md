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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用設定分析器，找出並修正低於標準防護和嚴格保護預設安全性原則的安全性原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 49c54fa93d5ed95c6c3e0aa948646dd544ea4a5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924441"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="4b2d3-103">EOP 和 Microsoft Defender for Office 365 中保護原則的設定分析器</span><span class="sxs-lookup"><span data-stu-id="4b2d3-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4b2d3-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-104">**Applies to**</span></span>
- [<span data-ttu-id="4b2d3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4b2d3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4b2d3-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="4b2d3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4b2d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b2d3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4b2d3-108">Security & 合規性中心的設定分析器提供一個集中位置，以找出並修正安全性原則，其中的設定低於標準 [安全性原則](preset-security-policies.md)中的標準防護和嚴格保護設定檔設定。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="4b2d3-109">設定分析器會分析下列類型的原則：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="4b2d3-110">**Exchange Online Protection (EOP) 原則**：這包括使用 exchange online 信箱的 Microsoft 365 組織和獨立 EOP 組織，但沒有 exchange online 信箱：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="4b2d3-111">[反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="4b2d3-112">[反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="4b2d3-113">[EOP 反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="4b2d3-114">**Microsoft Defender For office 365 原則**：這包括具有 Microsoft 365 E5 或 Defender for office 365 附加元件訂閱的組織：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="4b2d3-115">Microsoft Defender for Office 365 中的反網路釣魚原則，其中包括：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="4b2d3-116">EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="4b2d3-117">類比設定</span><span class="sxs-lookup"><span data-stu-id="4b2d3-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="4b2d3-118">高級網路釣魚臨界值</span><span class="sxs-lookup"><span data-stu-id="4b2d3-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="4b2d3-119">[安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-119">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="4b2d3-120">[安全附件原則](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-120">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="4b2d3-121">[EOP 和 Microsoft Defender For Office 365 安全性](recommended-settings-for-eop-and-office365-atp.md)中所述做為基準的 **標準** 和 **嚴格** 原則設定值。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4b2d3-122">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="4b2d3-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4b2d3-123">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4b2d3-124">若要直接移至 [設定 **分析器** ] 頁面，請使用 <https://protection.office.com/configurationAnalyzer> 。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="4b2d3-125">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4b2d3-126">您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4b2d3-127">若要使用設定分析器 **並** 更新安全性原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4b2d3-128">若要唯讀存取設定分析器，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4b2d3-129">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="4b2d3-130">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4b2d3-131">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="4b2d3-132">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="4b2d3-133">在安全性 & 規範中心使用設定分析器</span><span class="sxs-lookup"><span data-stu-id="4b2d3-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="4b2d3-134">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** 設定 \> **分析器**]。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![[威脅管理原則] 頁面上的設定分析器小工具 \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="4b2d3-136">設定分析器有兩個主要的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="4b2d3-137">**設定和建議**：選擇 [標準] 或 [嚴格]，然後將這些設定與您現有的安全性原則進行比較。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="4b2d3-138">在結果中，您可以調整設定的值，使其具有與標準或嚴格相同的層級。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="4b2d3-139">設定 **偏移分析和記錄**：此 view 可讓您追蹤一段時間的原則變更。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="4b2d3-140">設定分析器中的 [設定與建議] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="4b2d3-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="4b2d3-141">依預設，索引標籤會在與標準保護設定檔的比較上開啟。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="4b2d3-142">您可以按一下 [ **查看嚴格建議**] 切換到嚴格保護設定檔的比較。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="4b2d3-143">若要切換回來，請選取 [ **查看標準建議**]。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-143">To switch back, select **View Standard recommendations**.</span></span>

![設定分析器中的設定和建議視圖](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="4b2d3-145">根據預設，[ **原則群組/設定名稱** ] 欄會包含不同類型的安全性原則及設定數目的折疊模式，如果有任何) 則需要改進 (。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="4b2d3-146">原則類型包括：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-146">The types of policies are:</span></span>

- <span data-ttu-id="4b2d3-147">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-147">**Anti-spam**</span></span>
- <span data-ttu-id="4b2d3-148">**防網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-148">**Anti-phishing**</span></span>
- <span data-ttu-id="4b2d3-149">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-149">**Anti-malware**</span></span>
- <span data-ttu-id="4b2d3-150">如果您的訂閱包含 Microsoft Defender for Office 365， **ATP 安全附件** () </span><span class="sxs-lookup"><span data-stu-id="4b2d3-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="4b2d3-151">如果您的訂閱包含 Microsoft Defender for Office 365， **ATP 安全連結** () </span><span class="sxs-lookup"><span data-stu-id="4b2d3-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="4b2d3-152">在預設的視圖中，會折疊所有專案。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="4b2d3-153">每個原則旁都有一個原則的比較結果摘要，您可以在您的原則 (中修改) 和設定標準或嚴格保護設定檔對應之原則中的設定， (但不能修改) 。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="4b2d3-154">您將會看到您要比較的保護設定檔的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="4b2d3-155">**綠色**：所有現有原則中的所有設定，至少都是保護設定檔的安全性。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="4b2d3-156">**琥珀色**：現有原則中的少量設定，不如保護設定檔的安全性。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="4b2d3-157">**紅色**：現有原則中的大量設定與保護設定檔的安全性不符。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="4b2d3-158">這可能是許多原則中的一些設定或一個原則中的眾多設定。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="4b2d3-159">就理想的比較而言，您會看到文字： **所有設定都會遵循** \<**Standard** or **Strict**\> **建議**。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="4b2d3-160">否則，您會看到建議設定的變更數目。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="4b2d3-161">如果您展開 [ **原則] 群組/設定名稱**，則會顯示每個需要注意之特定原則中的所有原則和相關設定。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="4b2d3-162">或者，您可以展開特定類型的原則 (例如， **反垃圾郵件**) ，只查看那些需要注意之原則類型中的設定。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="4b2d3-163">如果比較沒有改進 (綠) 的建議，則展開原則會顯示 nothing。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="4b2d3-164">如果有任何數量的改進建議 (琥珀色或紅色) ，則會顯示需要注意的設定，並會顯示下列各欄中的對應資訊：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="4b2d3-165">需要注意之設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="4b2d3-166">例如，在先前的螢幕擷取畫面中，它是反垃圾郵件原則中的 **大量電子郵件閾值** 。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="4b2d3-167">**原則**：包含設定之受影響原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="4b2d3-168">**適用** 于：受影響的原則所套用的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="4b2d3-169">**目前** 設定：設定的目前值。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="4b2d3-170">**上次修改** 日期：上次修改原則的日期。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="4b2d3-171">**建議**：標準或嚴格保護設定檔中的設定值。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="4b2d3-172">若要變更原則中設定的值，使其符合保護設定檔中的建議值，請按一下 [ **採用**]。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="4b2d3-173">如果變更成功，您會看到訊息： **已成功採用的建議**。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="4b2d3-174">按一下 **[** 重新整理] 以查看減少的建議數量，並從結果中移除特定設定/原則列。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="4b2d3-175">設定分析器中的設定偏移分析和記錄] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="4b2d3-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="4b2d3-176">此索引標籤可讓您追蹤您對自訂安全性原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="4b2d3-177">根據預設，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="4b2d3-178">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-178">**Last modified**</span></span>
- <span data-ttu-id="4b2d3-179">**修改者**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-179">**Modified by**</span></span>
- <span data-ttu-id="4b2d3-180">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-180">**Setting Name**</span></span>
- <span data-ttu-id="4b2d3-181">**原則**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-181">**Policy**</span></span>
- <span data-ttu-id="4b2d3-182">**Type**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-182">**Type**</span></span>

<span data-ttu-id="4b2d3-183">若要篩選結果，請按一下 [篩選]。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4b2d3-184">在出現的 [ **篩選** ] 浮出控制項中，您可以選取下列篩選：</span><span class="sxs-lookup"><span data-stu-id="4b2d3-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="4b2d3-185"> (日期) 的 **開始時間** 和 **結束時間**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="4b2d3-186">**標準保護** 或 **嚴格保護**</span><span class="sxs-lookup"><span data-stu-id="4b2d3-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="4b2d3-187">若要將結果匯出至 .csv 檔案，請按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="4b2d3-187">To export the results to a .csv file, click **Export**.</span></span>

![設定分析器中的設定偏移分析和歷程記錄視圖](../../media/configuration-analyzer-configuration-drift-analysis-view.png)