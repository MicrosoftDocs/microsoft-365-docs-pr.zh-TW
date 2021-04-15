---
title: 設定 Microsoft Defender 防病毒偵測的修正
description: 在偵測到威脅時，設定 Microsoft Defender 防毒軟體應執行的動作，以及隔離檔案應該在隔離資料夾中保留多久
keywords: 修正、修正、移除、威脅、隔離、掃描、還原
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765056"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a><span data-ttu-id="86185-104">設定 Microsoft Defender 防病毒偵測的修正</span><span class="sxs-lookup"><span data-stu-id="86185-104">Configure remediation for Microsoft Defender Antivirus detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="86185-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="86185-105">**Applies to:**</span></span>

- [<span data-ttu-id="86185-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="86185-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="86185-107">當 Microsoft Defender 防病毒執行掃描時，它會嘗試修正或移除所偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="86185-107">When Microsoft Defender Antivirus runs a scan, it attempts to remediate or remove threats that are detected.</span></span> <span data-ttu-id="86185-108">您可以設定 Microsoft Defender 防毒軟體應如何解決特定威脅、是否應該在修正之前建立還原點，以及何時應移除威脅。</span><span class="sxs-lookup"><span data-stu-id="86185-108">You can configure how Microsoft Defender Antivirus should address certain threats, whether a restore point should be created before remediating, and when threats should be removed.</span></span>

<span data-ttu-id="86185-109">本文說明如何使用群組原則來設定這些設定，但是您也可以使用 [Microsoft 端點 Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) 和 [microsoft Intune](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="86185-109">This article describes how to configure these settings by using Group Policy, but you can also use [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) and [Microsoft Intune](/intune/device-restrictions-configure).</span></span> 

<span data-ttu-id="86185-110">您也可以使用[ `Set-MpPreference` PowerShell Cmdlet](/powershell/module/defender/set-mppreference)或[ `MSFT_MpPreference` WMI 類別](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="86185-110">You can also use the [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) or [`MSFT_MpPreference` WMI class](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) to configure these settings.</span></span>

## <a name="configure-remediation-options"></a><span data-ttu-id="86185-111">設定修正選項</span><span class="sxs-lookup"><span data-stu-id="86185-111">Configure remediation options</span></span>

1. <span data-ttu-id="86185-112">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="86185-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="86185-113">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="86185-113">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="86185-114">將樹狀目錄展開為  >  **microsoft Defender 防毒軟體** 的 Windows 元件。</span><span class="sxs-lookup"><span data-stu-id="86185-114">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**.</span></span> 

4. <span data-ttu-id="86185-115">使用下表，選取位置，然後視需要編輯原則。</span><span class="sxs-lookup"><span data-stu-id="86185-115">Using the table below, select a location, and then edit the policy as needed.</span></span> 

5. <span data-ttu-id="86185-116">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86185-116">Select **OK**.</span></span>

|<span data-ttu-id="86185-117">位置</span><span class="sxs-lookup"><span data-stu-id="86185-117">Location</span></span> | <span data-ttu-id="86185-118">設定</span><span class="sxs-lookup"><span data-stu-id="86185-118">Setting</span></span> | <span data-ttu-id="86185-119">描述</span><span class="sxs-lookup"><span data-stu-id="86185-119">Description</span></span> | <span data-ttu-id="86185-120">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="86185-120">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="86185-121">掃描</span><span class="sxs-lookup"><span data-stu-id="86185-121">Scan</span></span> | <span data-ttu-id="86185-122">建立系統還原點</span><span class="sxs-lookup"><span data-stu-id="86185-122">Create a system restore point</span></span> | <span data-ttu-id="86185-123">在嘗試清除或掃描之前每天都會建立系統還原點</span><span class="sxs-lookup"><span data-stu-id="86185-123">A system restore point will be created each day before cleaning or scanning is attempted</span></span> | <span data-ttu-id="86185-124">已停用</span><span class="sxs-lookup"><span data-stu-id="86185-124">Disabled</span></span>|
|<span data-ttu-id="86185-125">掃描</span><span class="sxs-lookup"><span data-stu-id="86185-125">Scan</span></span> | <span data-ttu-id="86185-126">開啟從掃描歷程記錄資料夾中移除專案</span><span class="sxs-lookup"><span data-stu-id="86185-126">Turn on removal of items from scan history folder</span></span> | <span data-ttu-id="86185-127">指定在掃描歷程記錄中應該保留的專案數天數</span><span class="sxs-lookup"><span data-stu-id="86185-127">Specify how many days items should be kept in the scan history</span></span> | <span data-ttu-id="86185-128">30 天</span><span class="sxs-lookup"><span data-stu-id="86185-128">30 days</span></span> |
|<span data-ttu-id="86185-129">根</span><span class="sxs-lookup"><span data-stu-id="86185-129">Root</span></span> | <span data-ttu-id="86185-130">關閉常式修復</span><span class="sxs-lookup"><span data-stu-id="86185-130">Turn off routine remediation</span></span> | <span data-ttu-id="86185-131">您可以指定 Microsoft Defender 防毒程式是否會自動 remediates 威脅，或者是否應要求端點使用者執行的動作。</span><span class="sxs-lookup"><span data-stu-id="86185-131">You can specify whether Microsoft Defender Antivirus automatically remediates threats, or if it should ask the endpoint user what to do.</span></span> | <span data-ttu-id="86185-132">停用 (威脅會自動修正) </span><span class="sxs-lookup"><span data-stu-id="86185-132">Disabled (threats are remediated automatically)</span></span> |
|<span data-ttu-id="86185-133">隔離</span><span class="sxs-lookup"><span data-stu-id="86185-133">Quarantine</span></span> | <span data-ttu-id="86185-134">設定從隔離資料夾中移除專案</span><span class="sxs-lookup"><span data-stu-id="86185-134">Configure removal of items from Quarantine folder</span></span> | <span data-ttu-id="86185-135">指定專案應該保留在隔離之前多少天之後才能被移除</span><span class="sxs-lookup"><span data-stu-id="86185-135">Specify how many days items should be kept in quarantine before being removed</span></span> | <span data-ttu-id="86185-136">90 天</span><span class="sxs-lookup"><span data-stu-id="86185-136">90 days</span></span> |
|<span data-ttu-id="86185-137">威脅</span><span class="sxs-lookup"><span data-stu-id="86185-137">Threats</span></span> | <span data-ttu-id="86185-138">指定偵測到預設動作時不應該採取的威脅警示層級</span><span class="sxs-lookup"><span data-stu-id="86185-138">Specify threat alert levels at which default action should not be taken when detected</span></span> | <span data-ttu-id="86185-139">Microsoft Defender 防病毒偵測到的每個威脅都會被指派威脅層級 (低、中、高或嚴重) 。</span><span class="sxs-lookup"><span data-stu-id="86185-139">Every threat that is detected by Microsoft Defender Antivirus is assigned a threat level (low, medium, high, or severe).</span></span> <span data-ttu-id="86185-140">您可以使用此設定來定義每個威脅層級的所有威脅應如何補救 (隔離、移除或忽略) </span><span class="sxs-lookup"><span data-stu-id="86185-140">You can use this setting to define how all threats for each of the threat levels should be remediated (quarantined, removed, or ignored)</span></span> | <span data-ttu-id="86185-141">不適用</span><span class="sxs-lookup"><span data-stu-id="86185-141">Not applicable</span></span> |
|<span data-ttu-id="86185-142">威脅</span><span class="sxs-lookup"><span data-stu-id="86185-142">Threats</span></span> | <span data-ttu-id="86185-143">指定當偵測到預設動作時不應該採取的威脅</span><span class="sxs-lookup"><span data-stu-id="86185-143">Specify threats upon which default action should not be taken when detected</span></span> | <span data-ttu-id="86185-144">指定應該修正 (使用威脅識別碼的特定威脅) 。</span><span class="sxs-lookup"><span data-stu-id="86185-144">Specify how specific threats (using their threat ID) should be remediated.</span></span> <span data-ttu-id="86185-145">您可以指定是否應該隔離、移除或忽略特定威脅。</span><span class="sxs-lookup"><span data-stu-id="86185-145">You can specify whether the specific threat should be quarantined, removed, or ignored</span></span> | <span data-ttu-id="86185-146">不適用</span><span class="sxs-lookup"><span data-stu-id="86185-146">Not applicable</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="86185-147">Microsoft Defender 防毒軟體會根據許多因素偵測和 remediates 檔案。</span><span class="sxs-lookup"><span data-stu-id="86185-147">Microsoft Defender Antivirus detects and remediates files based on many factors.</span></span> <span data-ttu-id="86185-148">在某些情況下，完成修復需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="86185-148">Sometimes, completing a remediation requires a reboot.</span></span> <span data-ttu-id="86185-149">即使後來判斷出的偵測是誤報，也必須完成重新開機，以確保已完成所有其他的修復步驟。</span><span class="sxs-lookup"><span data-stu-id="86185-149">Even if the detection is later determined to be a false positive, the reboot must be completed to ensure all additional remediation steps have been completed.</span></span>
>
> <span data-ttu-id="86185-150">如果您是根據誤報將檔案隔離的 Microsoft Defender 防病毒，您可以在裝置重新開機後，從隔離區還原檔案。</span><span class="sxs-lookup"><span data-stu-id="86185-150">If you are certain Microsoft Defender Antivirus quarantined a file based on a false positive, you can restore the file from quarantine after the device reboots.</span></span> <span data-ttu-id="86185-151">請參閱 [在 Microsoft Defender 防毒軟體中還原隔離的](restore-quarantined-files-microsoft-defender-antivirus.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="86185-151">See [Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> 
> <span data-ttu-id="86185-152">為了避免未來發生此問題，您可以從掃描中排除檔案。</span><span class="sxs-lookup"><span data-stu-id="86185-152">To avoid this problem in the future, you can exclude files from the scans.</span></span> <span data-ttu-id="86185-153">請參閱 [設定及驗證 Microsoft Defender 防病毒掃描的排除](configure-exclusions-microsoft-defender-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="86185-153">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="86185-154">另請參閱 [設定修正-必要的定時完整 Microsoft Defender 防病毒掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) ，以取得更多修正相關設定。</span><span class="sxs-lookup"><span data-stu-id="86185-154">Also see [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="86185-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86185-155">See also</span></span>

- [<span data-ttu-id="86185-156">設定 Microsoft Defender 防病毒掃描選項</span><span class="sxs-lookup"><span data-stu-id="86185-156">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86185-157">設定排定的 Microsoft Defender 防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="86185-157">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86185-158">設定及執行隨選 Microsoft Defender 防毒程式掃描</span><span class="sxs-lookup"><span data-stu-id="86185-158">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86185-159">設定出現在端點上的通知</span><span class="sxs-lookup"><span data-stu-id="86185-159">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86185-160">設定使用者的 Microsoft Defender 防毒程式互動</span><span class="sxs-lookup"><span data-stu-id="86185-160">Configure end-user Microsoft Defender Antivirus interaction</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86185-161">自訂、啟動和審閱 Microsoft Defender 防病毒掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="86185-161">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="86185-162">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="86185-162">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)