---
title: 使用 Microsoft Defender 防病毒定期快速和完整掃描排程
description: 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描
keywords: 「快速掃描」、「完整掃描」、「快速完整」、「排程掃描」、「每天」、「排程」、「定期」、「定期」
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690171"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="5c1aa-104">設定排程的快速或完整 Microsoft Defender 防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5c1aa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5c1aa-105">**Applies to:**</span></span>

- [<span data-ttu-id="5c1aa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5c1aa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="5c1aa-107">根據預設，Microsoft Defender 防毒程式會在任何排程的掃描時間之前，先檢查是否有15分鐘的更新。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="5c1aa-108">您可以 [管理應下載保護更新及](manage-protection-update-schedule-microsoft-defender-antivirus.md) 套用的時程表，以覆寫此預設值。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="5c1aa-109">除了無條件即時保護和 [手動](run-scan-microsoft-defender-antivirus.md) 掃描之外，您還可以設定週期性排程掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="5c1aa-110">您可以設定掃描類型、掃描應該發生時，以及在執行 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後或在使用端點時進行掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="5c1aa-111">您也可以指定何時應該進行特殊的掃描，以完成修復。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="5c1aa-112">本文說明如何使用「群組原則」、「PowerShell Cmdlet」和 WMI 來設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="5c1aa-113">您也可以使用 [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) 或 [microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="5c1aa-114">若要設定本文所述的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="5c1aa-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="5c1aa-115">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="5c1aa-116">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="5c1aa-117">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="5c1aa-118">在 [ **Microsoft Defender 防病毒 >** ] 的 [Windows 元件] 中，展開樹狀目錄，然後展開下表中所指定的 **位置** 。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="5c1aa-119">按兩下下表中所指定的原則 **設定** ，並將選項設定為您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="5c1aa-120">按一下 **[確定]**，然後對任何其他設定重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="5c1aa-121">另請參閱 [管理應下載及套用保護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) ，並 [防止或允許使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主題。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="5c1aa-122">快速掃描與完整掃描及自訂掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="5c1aa-123">當您設定排程掃描時，您可以設定掃描是否應為完整或快速掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="5c1aa-124">快速掃描查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 的 [啟動] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="5c1aa-125">與 [always on 即時保護功能](configure-real-time-protection-microsoft-defender-antivirus.md) 組合在一起，可在開啟和關閉檔時檢查檔案，以及每當使用者流覽至資料夾時，都可以為以系統和內核層級惡意程式碼開始的惡意程式碼提供強大的覆蓋。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="5c1aa-126">在大多數的情況下，這表示快速掃描足以找到即時保護未挑選的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="5c1aa-127">在發生惡意程式碼威脅的端點上，您可以使用完整掃描來識別是否有任何非使用中的元件需要更徹底的清理。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="5c1aa-128">在此範例中，您可能會想要在執行 [隨選掃描](run-scan-microsoft-defender-antivirus.md)時使用完整掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="5c1aa-129">自訂掃描可讓您指定要掃描的檔案和資料夾，例如 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="5c1aa-130">根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="5c1aa-131">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-131">Set up scheduled scans</span></span>

<span data-ttu-id="5c1aa-132">排程的掃描會在您指定的日期和時間執行。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="5c1aa-133">您可以使用「群組原則」、「PowerShell」和「WMI」來設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="5c1aa-134">如果電腦已在排程完整掃描期間已拔出並在電池上執行，則排定的掃描會停止事件1002，這表明掃描在完成前已停止。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="5c1aa-135">Microsoft Defender 防病毒會在下一個排程的時間執行完整掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="5c1aa-136">使用群組原則來排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="5c1aa-137">位置</span><span class="sxs-lookup"><span data-stu-id="5c1aa-137">Location</span></span> | <span data-ttu-id="5c1aa-138">設定</span><span class="sxs-lookup"><span data-stu-id="5c1aa-138">Setting</span></span> | <span data-ttu-id="5c1aa-139">描述</span><span class="sxs-lookup"><span data-stu-id="5c1aa-139">Description</span></span> | <span data-ttu-id="5c1aa-140">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="5c1aa-141">掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-141">Scan</span></span> | <span data-ttu-id="5c1aa-142">指定用於排程掃描的掃描類型</span><span class="sxs-lookup"><span data-stu-id="5c1aa-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="5c1aa-143">快速掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-143">Quick scan</span></span> |
|<span data-ttu-id="5c1aa-144">掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-144">Scan</span></span> | <span data-ttu-id="5c1aa-145">指定一周中的哪一天執行排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="5c1aa-146">指定 [天] (或 [永不) ] 執行掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="5c1aa-147">從來不需要</span><span class="sxs-lookup"><span data-stu-id="5c1aa-147">Never</span></span> |
|<span data-ttu-id="5c1aa-148">掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-148">Scan</span></span> | <span data-ttu-id="5c1aa-149">指定一天中執行排程掃描的時間</span><span class="sxs-lookup"><span data-stu-id="5c1aa-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="5c1aa-150">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) 。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="5c1aa-151">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="5c1aa-151">2 a.m.</span></span> |
|<span data-ttu-id="5c1aa-152">根</span><span class="sxs-lookup"><span data-stu-id="5c1aa-152">Root</span></span> | <span data-ttu-id="5c1aa-153">隨機化排程的任務時間</span><span class="sxs-lookup"><span data-stu-id="5c1aa-153">Randomize scheduled task times</span></span> |<span data-ttu-id="5c1aa-154">在 Microsoft Defender 防毒程式中：從0到4小時隨機化掃描的開始時間。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="5c1aa-155">在 FEP/SCEP 中：隨機化到任何間隔加上或減30分鐘。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="5c1aa-156">在 VM 或 VDI 部署中，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="5c1aa-157">Enabled</span><span class="sxs-lookup"><span data-stu-id="5c1aa-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="5c1aa-158">使用 PowerShell Cmdlet 來排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="5c1aa-159">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="5c1aa-160">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="5c1aa-161">使用 Windows 管理指令 (WMI) 排定掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="5c1aa-162">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="5c1aa-163">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="5c1aa-164">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="5c1aa-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="5c1aa-165">只有在端點未使用中時才開始排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="5c1aa-166">您可以設定排程的掃描，只會在端點開啟時，但不能與群組原則、PowerShell 或 WMI 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="5c1aa-167">這些掃描不會服從 CPU 節流設定，而且可充分利用資源，以盡可能快地完成掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="5c1aa-168">使用群組原則來排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="5c1aa-169">位置</span><span class="sxs-lookup"><span data-stu-id="5c1aa-169">Location</span></span> | <span data-ttu-id="5c1aa-170">設定</span><span class="sxs-lookup"><span data-stu-id="5c1aa-170">Setting</span></span> | <span data-ttu-id="5c1aa-171">描述</span><span class="sxs-lookup"><span data-stu-id="5c1aa-171">Description</span></span> | <span data-ttu-id="5c1aa-172">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="5c1aa-173">掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-173">Scan</span></span> | <span data-ttu-id="5c1aa-174">僅當電腦已開啟但未在使用中時啟動排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="5c1aa-175">除非電腦已開啟但未在使用中，否則不會執行排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="5c1aa-176">Enabled</span><span class="sxs-lookup"><span data-stu-id="5c1aa-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="5c1aa-177">使用 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5c1aa-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="5c1aa-178">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="5c1aa-179">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="5c1aa-180">使用 Windows Management 指令 (WMI) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="5c1aa-181">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="5c1aa-182">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="5c1aa-183">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="5c1aa-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="5c1aa-184">設定應該執行完整掃描以完成修復的時間</span><span class="sxs-lookup"><span data-stu-id="5c1aa-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="5c1aa-185">有些威脅可能需要完整掃描，才能完成移除和修復。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="5c1aa-186">您可以使用「群組原則」、「PowerShell」或「WMI」時排程進行這些掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="5c1aa-187">使用群組原則來排定修復所需的掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="5c1aa-188">位置</span><span class="sxs-lookup"><span data-stu-id="5c1aa-188">Location</span></span> | <span data-ttu-id="5c1aa-189">設定</span><span class="sxs-lookup"><span data-stu-id="5c1aa-189">Setting</span></span> | <span data-ttu-id="5c1aa-190">描述</span><span class="sxs-lookup"><span data-stu-id="5c1aa-190">Description</span></span> | <span data-ttu-id="5c1aa-191">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="5c1aa-192">修復</span><span class="sxs-lookup"><span data-stu-id="5c1aa-192">Remediation</span></span> | <span data-ttu-id="5c1aa-193">指定一周中的哪幾天執行排程完整掃描以完成修復</span><span class="sxs-lookup"><span data-stu-id="5c1aa-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="5c1aa-194">指定 [天] (或 [永不) ] 執行掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="5c1aa-195">從來不需要</span><span class="sxs-lookup"><span data-stu-id="5c1aa-195">Never</span></span> |
|<span data-ttu-id="5c1aa-196">修復</span><span class="sxs-lookup"><span data-stu-id="5c1aa-196">Remediation</span></span> | <span data-ttu-id="5c1aa-197">指定一天中執行計畫完整掃描以完成修復的時間</span><span class="sxs-lookup"><span data-stu-id="5c1aa-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="5c1aa-198">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="5c1aa-199">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="5c1aa-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="5c1aa-200">使用 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5c1aa-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="5c1aa-201">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="5c1aa-202">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="5c1aa-203">使用 Windows Management 指令 (WMI) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="5c1aa-204">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="5c1aa-205">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="5c1aa-206">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="5c1aa-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="5c1aa-207">設定每日快速掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-207">Set up daily quick scans</span></span>

<span data-ttu-id="5c1aa-208">除了使用群組原則、PowerShell 或 WMI 排定的其他排程掃描之外，您還可以啟用執行每日快速掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="5c1aa-209">使用群組原則排定每日掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="5c1aa-210">位置</span><span class="sxs-lookup"><span data-stu-id="5c1aa-210">Location</span></span> | <span data-ttu-id="5c1aa-211">設定</span><span class="sxs-lookup"><span data-stu-id="5c1aa-211">Setting</span></span> | <span data-ttu-id="5c1aa-212">描述</span><span class="sxs-lookup"><span data-stu-id="5c1aa-212">Description</span></span> | <span data-ttu-id="5c1aa-213">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="5c1aa-214">掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-214">Scan</span></span> | <span data-ttu-id="5c1aa-215">指定每天執行快速掃描的間隔</span><span class="sxs-lookup"><span data-stu-id="5c1aa-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="5c1aa-216">指定下一個快速掃描之前所應經過的小時數。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="5c1aa-217">例如，若要每兩個小時執行一次，請輸入 **2** 一天一次，輸入 **24**。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="5c1aa-218">輸入 **0** ，永遠不執行每日快速掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="5c1aa-219">從來不需要</span><span class="sxs-lookup"><span data-stu-id="5c1aa-219">Never</span></span> |
|<span data-ttu-id="5c1aa-220">掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-220">Scan</span></span> | <span data-ttu-id="5c1aa-221">指定每日快速掃描的時間</span><span class="sxs-lookup"><span data-stu-id="5c1aa-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="5c1aa-222">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="5c1aa-223">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="5c1aa-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="5c1aa-224">使用 PowerShell Cmdlet 排程每日掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="5c1aa-225">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="5c1aa-226">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="5c1aa-227">使用 Windows 管理指令 (WMI) 排定每日掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="5c1aa-228">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="5c1aa-229">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="5c1aa-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="5c1aa-230">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="5c1aa-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="5c1aa-231">在保護更新後啟用掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-231">Enable scans after protection updates</span></span>

<span data-ttu-id="5c1aa-232">您可以使用群組原則，強制進行每個 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後的掃描。</span><span class="sxs-lookup"><span data-stu-id="5c1aa-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="5c1aa-233">使用群組原則在保護更新後排程掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="5c1aa-234">位置</span><span class="sxs-lookup"><span data-stu-id="5c1aa-234">Location</span></span> | <span data-ttu-id="5c1aa-235">設定</span><span class="sxs-lookup"><span data-stu-id="5c1aa-235">Setting</span></span> | <span data-ttu-id="5c1aa-236">描述</span><span class="sxs-lookup"><span data-stu-id="5c1aa-236">Description</span></span> | <span data-ttu-id="5c1aa-237">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="5c1aa-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="5c1aa-238">特徵碼更新</span><span class="sxs-lookup"><span data-stu-id="5c1aa-238">Signature updates</span></span> | <span data-ttu-id="5c1aa-239">在安全性智慧更新後開啟掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="5c1aa-240">下載新的保護更新後會立即進行掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="5c1aa-241">Enabled</span><span class="sxs-lookup"><span data-stu-id="5c1aa-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="5c1aa-242">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5c1aa-242">See also</span></span>
- [<span data-ttu-id="5c1aa-243">防止或允許使用者本機修改原則設定</span><span class="sxs-lookup"><span data-stu-id="5c1aa-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5c1aa-244">設定及執行隨選 Microsoft Defender 防毒程式掃描</span><span class="sxs-lookup"><span data-stu-id="5c1aa-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5c1aa-245">設定 Microsoft Defender 防病毒掃描選項</span><span class="sxs-lookup"><span data-stu-id="5c1aa-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5c1aa-246">管理 Microsoft Defender 防病毒更新並套用基準</span><span class="sxs-lookup"><span data-stu-id="5c1aa-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5c1aa-247">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="5c1aa-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="5c1aa-248">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="5c1aa-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)