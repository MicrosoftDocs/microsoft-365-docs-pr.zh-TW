---
title: 設定 Microsoft Defender AV 設定的本機覆寫
description: 在 Microsoft Defender AV 中，啟用或停用使用者在本機變更設定。
keywords: 本機覆寫、本機原則、群組原則、gpo、鎖定、合併、清單
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 2d23ca6d98d86666d72b75723a2205fcd83b08d7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924240"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a><span data-ttu-id="994aa-104">防止或允許使用者本機修改 Microsoft Defender 防毒軟體原則設定</span><span class="sxs-lookup"><span data-stu-id="994aa-104">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>


<span data-ttu-id="994aa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="994aa-105">**Applies to:**</span></span>

- [<span data-ttu-id="994aa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="994aa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="994aa-107">根據預設，透過「群組原則」物件部署到網路端點的 Microsoft Defender 防毒軟體設定，可防止使用者在本機上變更設定。</span><span class="sxs-lookup"><span data-stu-id="994aa-107">By default, Microsoft Defender Antivirus settings that are deployed via a Group Policy Object to the endpoints in your network will prevent users from locally changing the settings.</span></span> <span data-ttu-id="994aa-108">在某些情況中，您可以變更這種情況。</span><span class="sxs-lookup"><span data-stu-id="994aa-108">You can change this in some instances.</span></span>

<span data-ttu-id="994aa-109">例如，您可能需要允許某些使用者群組 (例如，安全性調查人員和威脅調查人員) 對使用的端點上的個別設定進行進一步的控制。</span><span class="sxs-lookup"><span data-stu-id="994aa-109">For example, it may be necessary to allow certain user groups (such as security researchers and threat investigators) further control over individual settings on the endpoints they use.</span></span>

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a><span data-ttu-id="994aa-110">設定 Microsoft Defender 防毒軟體設定的本機覆寫</span><span class="sxs-lookup"><span data-stu-id="994aa-110">Configure local overrides for Microsoft Defender Antivirus settings</span></span>

<span data-ttu-id="994aa-111">這些原則的預設設定為 [ **停用**]。</span><span class="sxs-lookup"><span data-stu-id="994aa-111">The default setting for these policies is **Disabled**.</span></span>

<span data-ttu-id="994aa-112">如果設定為 [**啟用**]，端點上的使用者可以使用 [Windows 安全性](microsoft-defender-security-center-antivirus.md)app、本機組策略設定，以及適當)  (中的 PowerShell Cmdlet，對相關聯的設定進行變更。</span><span class="sxs-lookup"><span data-stu-id="994aa-112">If they are set to **Enabled**, users on endpoints can make changes to the associated setting with the [Windows Security](microsoft-defender-security-center-antivirus.md) app, local Group Policy settings, and PowerShell cmdlets (where appropriate).</span></span>

<span data-ttu-id="994aa-113">下表列出每個覆寫原則設定，以及相關聯的功能或設定的設定指示。</span><span class="sxs-lookup"><span data-stu-id="994aa-113">The following table lists each of the override policy setting and the configuration instructions for the associated feature or setting.</span></span>

<span data-ttu-id="994aa-114">若要設定這些設定：</span><span class="sxs-lookup"><span data-stu-id="994aa-114">To configure these settings:</span></span>

1. <span data-ttu-id="994aa-115">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="994aa-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="994aa-116">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="994aa-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="994aa-117">展開樹狀目錄， **Windows 元件 > Microsoft Defender 防毒軟體**，然後在下表中所指定的 **位置**。</span><span class="sxs-lookup"><span data-stu-id="994aa-117">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="994aa-118">按兩下下表中所指定的原則 **設定** ，並將選項設定為您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="994aa-118">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="994aa-119">按一下 **[確定]**，然後對任何其他設定重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="994aa-119">Click **OK**, and repeat for any other settings.</span></span>

5. <span data-ttu-id="994aa-120">照常部署群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="994aa-120">Deploy the Group Policy Object as usual.</span></span>

<span data-ttu-id="994aa-121">位置</span><span class="sxs-lookup"><span data-stu-id="994aa-121">Location</span></span> | <span data-ttu-id="994aa-122">設定</span><span class="sxs-lookup"><span data-stu-id="994aa-122">Setting</span></span> | <span data-ttu-id="994aa-123">文章</span><span class="sxs-lookup"><span data-stu-id="994aa-123">Article</span></span>
---|---|---|---
<span data-ttu-id="994aa-124">地圖</span><span class="sxs-lookup"><span data-stu-id="994aa-124">MAPS</span></span> | <span data-ttu-id="994aa-125">設定本地設定覆寫以進行 Microsoft MAPS 報告</span><span class="sxs-lookup"><span data-stu-id="994aa-125">Configure local setting override for reporting to Microsoft MAPS</span></span> | [<span data-ttu-id="994aa-126">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="994aa-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-127">隔離</span><span class="sxs-lookup"><span data-stu-id="994aa-127">Quarantine</span></span> | <span data-ttu-id="994aa-128">設定從隔離區移除專案的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="994aa-128">Configure local setting override for the removal of items from Quarantine folder</span></span> | [<span data-ttu-id="994aa-129">設定掃描的修正</span><span class="sxs-lookup"><span data-stu-id="994aa-129">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-130">即時保護</span><span class="sxs-lookup"><span data-stu-id="994aa-130">Real-time protection</span></span> | <span data-ttu-id="994aa-131">設定本機設定覆寫以監控電腦上的檔案和程式活動</span><span class="sxs-lookup"><span data-stu-id="994aa-131">Configure local setting override for monitoring file and program activity on your computer</span></span> | [<span data-ttu-id="994aa-132">啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控</span><span class="sxs-lookup"><span data-stu-id="994aa-132">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-133">即時保護</span><span class="sxs-lookup"><span data-stu-id="994aa-133">Real-time protection</span></span> | <span data-ttu-id="994aa-134">設定針對內送和外寄檔案活動進行監視的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="994aa-134">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | [<span data-ttu-id="994aa-135">啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控</span><span class="sxs-lookup"><span data-stu-id="994aa-135">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-136">即時保護</span><span class="sxs-lookup"><span data-stu-id="994aa-136">Real-time protection</span></span> | <span data-ttu-id="994aa-137">設定本機設定覆寫以掃描所有已下載的檔案和附件</span><span class="sxs-lookup"><span data-stu-id="994aa-137">Configure local setting override for scanning all downloaded files and attachments</span></span> | [<span data-ttu-id="994aa-138">啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控</span><span class="sxs-lookup"><span data-stu-id="994aa-138">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-139">即時保護</span><span class="sxs-lookup"><span data-stu-id="994aa-139">Real-time protection</span></span> | <span data-ttu-id="994aa-140">設定本機設定超越開啟行為監控</span><span class="sxs-lookup"><span data-stu-id="994aa-140">Configure local setting override for turn on behavior monitoring</span></span> | [<span data-ttu-id="994aa-141">啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控</span><span class="sxs-lookup"><span data-stu-id="994aa-141">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-142">即時保護</span><span class="sxs-lookup"><span data-stu-id="994aa-142">Real-time protection</span></span> | <span data-ttu-id="994aa-143">設定本機設定覆寫以開啟即時保護</span><span class="sxs-lookup"><span data-stu-id="994aa-143">Configure local setting override to turn on real-time protection</span></span> | [<span data-ttu-id="994aa-144">啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控</span><span class="sxs-lookup"><span data-stu-id="994aa-144">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-145">修復</span><span class="sxs-lookup"><span data-stu-id="994aa-145">Remediation</span></span> | <span data-ttu-id="994aa-146">設定本機設定覆寫以執行排定的完整掃描以完成修復的時間</span><span class="sxs-lookup"><span data-stu-id="994aa-146">Configure local setting override for the time of day to run a scheduled full scan to complete remediation</span></span> | [<span data-ttu-id="994aa-147">設定掃描的修正</span><span class="sxs-lookup"><span data-stu-id="994aa-147">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-148">掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-148">Scan</span></span> | <span data-ttu-id="994aa-149">設定本機設定覆寫以取得 CPU 使用率的最大百分比</span><span class="sxs-lookup"><span data-stu-id="994aa-149">Configure local setting override for maximum percentage of CPU utilization</span></span> | [<span data-ttu-id="994aa-150">設定及執行掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-150">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-151">掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-151">Scan</span></span> | <span data-ttu-id="994aa-152">設定排程掃描日的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="994aa-152">Configure local setting override for schedule scan day</span></span> | [<span data-ttu-id="994aa-153">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-153">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-154">掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-154">Scan</span></span> | <span data-ttu-id="994aa-155">設定計劃快速掃描時間的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="994aa-155">Configure local setting override for scheduled quick scan time</span></span> | [<span data-ttu-id="994aa-156">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-156">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-157">掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-157">Scan</span></span> | <span data-ttu-id="994aa-158">設定計劃掃描時間的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="994aa-158">Configure local setting override for scheduled scan time</span></span> | [<span data-ttu-id="994aa-159">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-159">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="994aa-160">掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-160">Scan</span></span> | <span data-ttu-id="994aa-161">設定針對掃描類型用於排程掃描的本機設定覆寫</span><span class="sxs-lookup"><span data-stu-id="994aa-161">Configure local setting override for the scan type to use for a scheduled scan</span></span> | [<span data-ttu-id="994aa-162">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="994aa-162">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a><span data-ttu-id="994aa-163">設定如何合併本機和全域定義的威脅修復和排除清單</span><span class="sxs-lookup"><span data-stu-id="994aa-163">Configure how locally and globally defined threat remediation and exclusions lists are merged</span></span>

<span data-ttu-id="994aa-164">您也可以設定如何組合或合併本機定義的清單與全域定義的清單。</span><span class="sxs-lookup"><span data-stu-id="994aa-164">You can also configure how locally defined lists are combined or merged with globally defined lists.</span></span> <span data-ttu-id="994aa-165">此設定適用于 [排除清單](configure-exclusions-microsoft-defender-antivirus.md)、 [指定的修正清單](configure-remediation-microsoft-defender-antivirus.md)和 [攻擊面降低](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。</span><span class="sxs-lookup"><span data-stu-id="994aa-165">This setting applies to [exclusion lists](configure-exclusions-microsoft-defender-antivirus.md), [specified remediation lists](configure-remediation-microsoft-defender-antivirus.md), and [attack surface reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).</span></span>

<span data-ttu-id="994aa-166">依預設，已在本機組策略中設定的清單和 Windows 安全性應用程式會與您在網路上部署的適當群組原則物件所定義的清單合併。</span><span class="sxs-lookup"><span data-stu-id="994aa-166">By default, lists that have been configured in local group policy and the Windows Security app are merged with lists that are defined by the appropriate Group Policy Object that you have deployed on your network.</span></span> <span data-ttu-id="994aa-167">在發生衝突的情況下，全域定義的清單優先。</span><span class="sxs-lookup"><span data-stu-id="994aa-167">Where there are conflicts, the globally-defined list takes precedence.</span></span>

<span data-ttu-id="994aa-168">您可以停用此設定，以確保只會使用全域定義的清單 (例如任何已部署的 Gpo) 中的清單。</span><span class="sxs-lookup"><span data-stu-id="994aa-168">You can disable this setting to ensure that only globally-defined lists (such as those from any deployed GPOs) are used.</span></span>

### <a name="use-group-policy-to-disable-local-list-merging"></a><span data-ttu-id="994aa-169">使用群組原則來停用本地清單合併</span><span class="sxs-lookup"><span data-stu-id="994aa-169">Use Group Policy to disable local list merging</span></span>

1. <span data-ttu-id="994aa-170">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="994aa-170">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="994aa-171">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="994aa-171">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="994aa-172">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="994aa-172">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

4. <span data-ttu-id="994aa-173">按兩下 [ **設定清單的本機系統管理員合併行為** ]，並將選項設定為 [ **已停用**]。</span><span class="sxs-lookup"><span data-stu-id="994aa-173">Double-click **Configure local administrator merge behavior for lists** and set the option to **Disabled**.</span></span> <span data-ttu-id="994aa-174">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="994aa-174">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="994aa-175">如果您停用本機清單合併，它會覆寫控制的資料夾存取設定。</span><span class="sxs-lookup"><span data-stu-id="994aa-175">If you disable local list merging, it will override controlled folder access settings.</span></span> <span data-ttu-id="994aa-176">它也會覆寫任何受保護的資料夾或本機系統管理員所設定的允許應用程式。</span><span class="sxs-lookup"><span data-stu-id="994aa-176">It also overrides any protected folders or allowed apps set by the local administrator.</span></span> <span data-ttu-id="994aa-177">如需受控資料夾存取設定的詳細資訊，請參閱[在 Windows 安全性中允許封鎖的應用程式](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)。</span><span class="sxs-lookup"><span data-stu-id="994aa-177">For more information about controlled folder access settings, see [Allow a blocked app in Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).</span></span>

## <a name="related-topics"></a><span data-ttu-id="994aa-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="994aa-178">Related topics</span></span>

- [<span data-ttu-id="994aa-179">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="994aa-179">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="994aa-180">設定使用者與 Microsoft Defender 防毒軟體互動互動</span><span class="sxs-lookup"><span data-stu-id="994aa-180">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
