---
title: 設定 Microsoft Defender AV 設定的本機覆寫
description: 在 Microsoft Defender AV 中，啟用或停用使用者在本機變更設定。
keywords: 本機覆寫、本機原則、群組原則、gpo、鎖定、合併、清單
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3c2b7ae70f42cb7ffc2deef1786ad43e65f33b6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764636"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a><span data-ttu-id="87c16-104">防止或允許使用者從本機修改 Microsoft Defender 防病毒原則設定</span><span class="sxs-lookup"><span data-stu-id="87c16-104">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="87c16-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="87c16-105">**Applies to:**</span></span>

- [<span data-ttu-id="87c16-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="87c16-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="87c16-107">根據預設，透過「群組原則」物件部署到網路端點的 Microsoft Defender 防病毒設定會使使用者無法在本機變更設定。</span><span class="sxs-lookup"><span data-stu-id="87c16-107">By default, Microsoft Defender Antivirus settings that are deployed via a Group Policy Object to the endpoints in your network will prevent users from locally changing the settings.</span></span> <span data-ttu-id="87c16-108">在某些情況中，您可以變更這種情況。</span><span class="sxs-lookup"><span data-stu-id="87c16-108">You can change this in some instances.</span></span>

<span data-ttu-id="87c16-109">例如，您可能需要允許某些使用者群組 (例如，安全性調查人員和威脅調查人員) 對使用的端點上的個別設定進行進一步的控制。</span><span class="sxs-lookup"><span data-stu-id="87c16-109">For example, it may be necessary to allow certain user groups (such as security researchers and threat investigators) further control over individual settings on the endpoints they use.</span></span>

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a><span data-ttu-id="87c16-110">設定 Microsoft Defender 防病毒設定的本機覆寫</span><span class="sxs-lookup"><span data-stu-id="87c16-110">Configure local overrides for Microsoft Defender Antivirus settings</span></span>

<span data-ttu-id="87c16-111">這些原則的預設設定為 [ **停用**]。</span><span class="sxs-lookup"><span data-stu-id="87c16-111">The default setting for these policies is **Disabled**.</span></span>

<span data-ttu-id="87c16-112">如果將其設為 [ **啟用**]，端點上的使用者可以使用 [Windows 安全性](microsoft-defender-security-center-antivirus.md) 應用程式、本機組策略設定，以及) 適當的 PowerShell (Cmdlet，對相關聯的設定進行變更。</span><span class="sxs-lookup"><span data-stu-id="87c16-112">If they are set to **Enabled**, users on endpoints can make changes to the associated setting with the [Windows Security](microsoft-defender-security-center-antivirus.md) app, local Group Policy settings, and PowerShell cmdlets (where appropriate).</span></span>

<span data-ttu-id="87c16-113">下表列出每個覆寫原則設定，以及相關聯的功能或設定的設定指示。</span><span class="sxs-lookup"><span data-stu-id="87c16-113">The following table lists each of the override policy setting and the configuration instructions for the associated feature or setting.</span></span>

<span data-ttu-id="87c16-114">若要設定這些設定：</span><span class="sxs-lookup"><span data-stu-id="87c16-114">To configure these settings:</span></span>

1. <span data-ttu-id="87c16-115">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="87c16-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="87c16-116">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="87c16-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="87c16-117">在 [ **Microsoft Defender 防病毒 >** ] 的 [Windows 元件] 中，展開樹狀目錄，然後展開下表中所指定的 **位置** 。</span><span class="sxs-lookup"><span data-stu-id="87c16-117">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="87c16-118">按兩下下表中所指定的原則 **設定** ，並將選項設定為您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="87c16-118">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="87c16-119">按一下 **[確定]**，然後對任何其他設定重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="87c16-119">Click **OK**, and repeat for any other settings.</span></span>

5. <span data-ttu-id="87c16-120">照常部署群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="87c16-120">Deploy the Group Policy Object as usual.</span></span>

<span data-ttu-id="87c16-121">位置</span><span class="sxs-lookup"><span data-stu-id="87c16-121">Location</span></span> | <span data-ttu-id="87c16-122">設定</span><span class="sxs-lookup"><span data-stu-id="87c16-122">Setting</span></span> | <span data-ttu-id="87c16-123">文章</span><span class="sxs-lookup"><span data-stu-id="87c16-123">Article</span></span>
---|---|---|---
<span data-ttu-id="87c16-124">地圖</span><span class="sxs-lookup"><span data-stu-id="87c16-124">MAPS</span></span> | <span data-ttu-id="87c16-125">設定本地設定覆寫以進行 Microsoft MAPS 報告</span><span class="sxs-lookup"><span data-stu-id="87c16-125">Configure local setting override for reporting to Microsoft MAPS</span></span> | [<span data-ttu-id="87c16-126">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="87c16-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-127">隔離</span><span class="sxs-lookup"><span data-stu-id="87c16-127">Quarantine</span></span> | <span data-ttu-id="87c16-128">設定從隔離區移除專案的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="87c16-128">Configure local setting override for the removal of items from Quarantine folder</span></span> | [<span data-ttu-id="87c16-129">設定掃描的修正</span><span class="sxs-lookup"><span data-stu-id="87c16-129">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-130">即時保護</span><span class="sxs-lookup"><span data-stu-id="87c16-130">Real-time protection</span></span> | <span data-ttu-id="87c16-131">設定本機設定覆寫以監控電腦上的檔案和程式活動</span><span class="sxs-lookup"><span data-stu-id="87c16-131">Configure local setting override for monitoring file and program activity on your computer</span></span> | [<span data-ttu-id="87c16-132">啟用並設定 Microsoft Defender 防病毒永遠開啟保護和監控</span><span class="sxs-lookup"><span data-stu-id="87c16-132">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-133">即時保護</span><span class="sxs-lookup"><span data-stu-id="87c16-133">Real-time protection</span></span> | <span data-ttu-id="87c16-134">設定針對內送和外寄檔案活動進行監視的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="87c16-134">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | [<span data-ttu-id="87c16-135">啟用並設定 Microsoft Defender 防病毒永遠開啟保護和監控</span><span class="sxs-lookup"><span data-stu-id="87c16-135">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-136">即時保護</span><span class="sxs-lookup"><span data-stu-id="87c16-136">Real-time protection</span></span> | <span data-ttu-id="87c16-137">設定本機設定覆寫以掃描所有已下載的檔案和附件</span><span class="sxs-lookup"><span data-stu-id="87c16-137">Configure local setting override for scanning all downloaded files and attachments</span></span> | [<span data-ttu-id="87c16-138">啟用並設定 Microsoft Defender 防病毒永遠開啟保護和監控</span><span class="sxs-lookup"><span data-stu-id="87c16-138">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-139">即時保護</span><span class="sxs-lookup"><span data-stu-id="87c16-139">Real-time protection</span></span> | <span data-ttu-id="87c16-140">設定本機設定超越開啟行為監控</span><span class="sxs-lookup"><span data-stu-id="87c16-140">Configure local setting override for turn on behavior monitoring</span></span> | [<span data-ttu-id="87c16-141">啟用並設定 Microsoft Defender 防病毒永遠開啟保護和監控</span><span class="sxs-lookup"><span data-stu-id="87c16-141">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-142">即時保護</span><span class="sxs-lookup"><span data-stu-id="87c16-142">Real-time protection</span></span> | <span data-ttu-id="87c16-143">設定本機設定覆寫以開啟即時保護</span><span class="sxs-lookup"><span data-stu-id="87c16-143">Configure local setting override to turn on real-time protection</span></span> | [<span data-ttu-id="87c16-144">啟用並設定 Microsoft Defender 防病毒永遠開啟保護和監控</span><span class="sxs-lookup"><span data-stu-id="87c16-144">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-145">修復</span><span class="sxs-lookup"><span data-stu-id="87c16-145">Remediation</span></span> | <span data-ttu-id="87c16-146">設定本機設定覆寫以執行排定的完整掃描以完成修復的時間</span><span class="sxs-lookup"><span data-stu-id="87c16-146">Configure local setting override for the time of day to run a scheduled full scan to complete remediation</span></span> | [<span data-ttu-id="87c16-147">設定掃描的修正</span><span class="sxs-lookup"><span data-stu-id="87c16-147">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-148">掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-148">Scan</span></span> | <span data-ttu-id="87c16-149">設定本機設定覆寫以取得 CPU 使用率的最大百分比</span><span class="sxs-lookup"><span data-stu-id="87c16-149">Configure local setting override for maximum percentage of CPU utilization</span></span> | [<span data-ttu-id="87c16-150">設定及執行掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-150">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-151">掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-151">Scan</span></span> | <span data-ttu-id="87c16-152">設定排程掃描日的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="87c16-152">Configure local setting override for schedule scan day</span></span> | [<span data-ttu-id="87c16-153">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-153">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-154">掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-154">Scan</span></span> | <span data-ttu-id="87c16-155">設定計劃快速掃描時間的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="87c16-155">Configure local setting override for scheduled quick scan time</span></span> | [<span data-ttu-id="87c16-156">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-156">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-157">掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-157">Scan</span></span> | <span data-ttu-id="87c16-158">設定計劃掃描時間的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="87c16-158">Configure local setting override for scheduled scan time</span></span> | [<span data-ttu-id="87c16-159">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-159">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="87c16-160">掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-160">Scan</span></span> | <span data-ttu-id="87c16-161">設定針對掃描類型用於排程掃描的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="87c16-161">Configure local setting override for the scan type to use for a scheduled scan</span></span> | [<span data-ttu-id="87c16-162">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="87c16-162">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a><span data-ttu-id="87c16-163">設定如何合併本機和全域定義的威脅修復和排除清單</span><span class="sxs-lookup"><span data-stu-id="87c16-163">Configure how locally and globally defined threat remediation and exclusions lists are merged</span></span>

<span data-ttu-id="87c16-164">您也可以設定如何組合或合併本機定義的清單與全域定義的清單。</span><span class="sxs-lookup"><span data-stu-id="87c16-164">You can also configure how locally defined lists are combined or merged with globally defined lists.</span></span> <span data-ttu-id="87c16-165">此設定適用于 [排除清單](configure-exclusions-microsoft-defender-antivirus.md)、 [指定的修正清單](configure-remediation-microsoft-defender-antivirus.md)和 [攻擊面降低](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。</span><span class="sxs-lookup"><span data-stu-id="87c16-165">This setting applies to [exclusion lists](configure-exclusions-microsoft-defender-antivirus.md), [specified remediation lists](configure-remediation-microsoft-defender-antivirus.md), and [attack surface reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).</span></span>

<span data-ttu-id="87c16-166">依預設，已在本機組策略中設定的清單和 Windows 安全性應用程式會與您在網路上部署的適當群組原則物件所定義的清單合併。</span><span class="sxs-lookup"><span data-stu-id="87c16-166">By default, lists that have been configured in local group policy and the Windows Security app are merged with lists that are defined by the appropriate Group Policy Object that you have deployed on your network.</span></span> <span data-ttu-id="87c16-167">在發生衝突的情況下，全域定義的清單優先。</span><span class="sxs-lookup"><span data-stu-id="87c16-167">Where there are conflicts, the globally-defined list takes precedence.</span></span>

<span data-ttu-id="87c16-168">您可以停用此設定，以確保只會使用全域定義的清單 (例如任何已部署的 Gpo) 中的清單。</span><span class="sxs-lookup"><span data-stu-id="87c16-168">You can disable this setting to ensure that only globally-defined lists (such as those from any deployed GPOs) are used.</span></span>

### <a name="use-group-policy-to-disable-local-list-merging"></a><span data-ttu-id="87c16-169">使用群組原則來停用本地清單合併</span><span class="sxs-lookup"><span data-stu-id="87c16-169">Use Group Policy to disable local list merging</span></span>

1. <span data-ttu-id="87c16-170">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="87c16-170">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="87c16-171">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="87c16-171">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="87c16-172">將樹狀目錄展開 **> Microsoft Defender 防毒軟體中的 Windows 元件**。</span><span class="sxs-lookup"><span data-stu-id="87c16-172">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

4. <span data-ttu-id="87c16-173">按兩下 [ **設定清單的本機系統管理員合併行為** ]，並將選項設定為 [ **已停用**]。</span><span class="sxs-lookup"><span data-stu-id="87c16-173">Double-click **Configure local administrator merge behavior for lists** and set the option to **Disabled**.</span></span> <span data-ttu-id="87c16-174">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="87c16-174">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="87c16-175">如果您停用本機清單合併，它會覆寫控制的資料夾存取設定。</span><span class="sxs-lookup"><span data-stu-id="87c16-175">If you disable local list merging, it will override controlled folder access settings.</span></span> <span data-ttu-id="87c16-176">它也會覆寫任何受保護的資料夾或本機系統管理員所設定的允許應用程式。</span><span class="sxs-lookup"><span data-stu-id="87c16-176">It also overrides any protected folders or allowed apps set by the local administrator.</span></span> <span data-ttu-id="87c16-177">如需有關可控資料夾存取設定的詳細資訊，請參閱 [在 Windows 安全性中允許封鎖的應用程式](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)。</span><span class="sxs-lookup"><span data-stu-id="87c16-177">For more information about controlled folder access settings, see [Allow a blocked app in Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).</span></span>

## <a name="related-topics"></a><span data-ttu-id="87c16-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="87c16-178">Related topics</span></span>

- [<span data-ttu-id="87c16-179">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="87c16-179">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="87c16-180">使用 Microsoft Defender 防毒軟體設定使用者互動</span><span class="sxs-lookup"><span data-stu-id="87c16-180">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)