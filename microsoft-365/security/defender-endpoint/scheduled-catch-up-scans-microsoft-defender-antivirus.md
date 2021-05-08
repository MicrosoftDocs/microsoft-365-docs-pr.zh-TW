---
title: 使用 Microsoft Defender 防毒軟體安排一般快速和完整掃描
description: 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描
keywords: 「快速掃描」、「完整掃描」、「快速完整」、「排程掃描」、「每天」、「排程」、「定期」、「定期」
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 038818b711400eb16fea89573dc70664a442fc1d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245897"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="b09d1-104">設定排程的快速或完整 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="b09d1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b09d1-105">**Applies to:**</span></span>

- [<span data-ttu-id="b09d1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b09d1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="b09d1-107">根據預設，Microsoft Defender 防毒軟體會在任何排程的掃描時間之前，先檢查是否有15分鐘的更新。</span><span class="sxs-lookup"><span data-stu-id="b09d1-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="b09d1-108">您可以 [管理應下載保護更新及](manage-protection-update-schedule-microsoft-defender-antivirus.md) 套用的時程表，以覆寫此預設值。</span><span class="sxs-lookup"><span data-stu-id="b09d1-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="b09d1-109">除了無條件即時保護和 [手動](run-scan-microsoft-defender-antivirus.md) 掃描之外，您還可以設定週期性排程掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="b09d1-110">您可以設定掃描類型、掃描應該發生時，以及在執行 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後或在使用端點時進行掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="b09d1-111">您也可以指定何時應該進行特殊的掃描，以完成修復。</span><span class="sxs-lookup"><span data-stu-id="b09d1-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="b09d1-112">本文說明如何使用「群組原則」、「PowerShell Cmdlet」和 WMI 來設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="b09d1-113">您也可以使用[Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings)或[Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="b09d1-114">若要設定本文所述的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="b09d1-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="b09d1-115">在您的群組原則管理電腦上，在 [群組原則編輯器] 中，移至 [電腦設定]**系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。</span><span class="sxs-lookup"><span data-stu-id="b09d1-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="b09d1-116">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b09d1-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="b09d1-117">指定「群組原則」物件的設定，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b09d1-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="b09d1-118">針對每個您要設定的設定，請重複步驟1-4。</span><span class="sxs-lookup"><span data-stu-id="b09d1-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="b09d1-119">照常部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="b09d1-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="b09d1-120">如果您需要「群組原則」物件的協助，請參閱 [建立群組原則物件](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。</span><span class="sxs-lookup"><span data-stu-id="b09d1-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="b09d1-121">另請參閱 [管理應下載及套用保護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) ，並 [防止或允許使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主題。</span><span class="sxs-lookup"><span data-stu-id="b09d1-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="b09d1-122">快速掃描與完整掃描及自訂掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="b09d1-123">當您設定排程掃描時，您可以設定掃描是否應為完整或快速掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="b09d1-124">快速掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-124">Quick scan</span></span>  |<span data-ttu-id="b09d1-125">完整掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-125">Full scan</span></span>  | <span data-ttu-id="b09d1-126">自訂掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b09d1-127">快速掃描會查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 開機檔案夾。</span><span class="sxs-lookup"><span data-stu-id="b09d1-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="b09d1-128">在大多數情況下，快速掃描足以滿足排程掃描的建議。</span><span class="sxs-lookup"><span data-stu-id="b09d1-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="b09d1-129">完整掃描會從執行快速掃描開始，繼續執行所有已裝載固定磁片及移除/網路磁碟機的連續檔案掃描 (如果完整掃描已設定為執行此作業) 。</span><span class="sxs-lookup"><span data-stu-id="b09d1-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="b09d1-130">根據需要掃描的資料量和類型，完整掃描可能需要數小時或數天才能完成。</span><span class="sxs-lookup"><span data-stu-id="b09d1-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="b09d1-131">完成完整掃描後，即可使用新的安全性智慧，並需要進行新的掃描，以確保不會偵測到新安全性情報的其他威脅。</span><span class="sxs-lookup"><span data-stu-id="b09d1-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="b09d1-132">自訂掃描是在您指定的檔案和資料夾上執行的快速掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="b09d1-133">例如，您可以選擇掃描 USB 磁片磁碟機，或裝置的本機磁片磁碟機上的特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="b09d1-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="b09d1-134">根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="b09d1-135">如何知道要選擇的掃描類型為何？</span><span class="sxs-lookup"><span data-stu-id="b09d1-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="b09d1-136">請使用下表選擇掃描類型。</span><span class="sxs-lookup"><span data-stu-id="b09d1-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="b09d1-137">案例</span><span class="sxs-lookup"><span data-stu-id="b09d1-137">Scenario</span></span>  |<span data-ttu-id="b09d1-138">建議的掃描類型</span><span class="sxs-lookup"><span data-stu-id="b09d1-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="b09d1-139">您想要設定定期、排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="b09d1-140">快速掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-140">Quick scan</span></span> <p><span data-ttu-id="b09d1-141">快速掃描會檢查裝置上的處理常式、記憶體、設定檔及特定位置。</span><span class="sxs-lookup"><span data-stu-id="b09d1-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="b09d1-142">[！注意] 結合了 [always on 即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)，快速掃描可為以系統和內核層級惡意程式碼開頭的惡意程式碼提供強大的覆蓋。</span><span class="sxs-lookup"><span data-stu-id="b09d1-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="b09d1-143">即時保護會在開啟及關閉檔時查看檔案，以及每當使用者流覽至資料夾時，就會檢查檔案。</span><span class="sxs-lookup"><span data-stu-id="b09d1-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="b09d1-144">在裝置上偵測到威脅，例如惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="b09d1-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="b09d1-145">完整掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-145">Full scan</span></span> <p><span data-ttu-id="b09d1-146">完整掃描可協助識別是否有任何非使用中的元件需要更徹底的清理。</span><span class="sxs-lookup"><span data-stu-id="b09d1-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="b09d1-147">您想要執行 [隨選掃描](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b09d1-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="b09d1-148">完整掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-148">Full scan</span></span>  <p><span data-ttu-id="b09d1-149">完整掃描會查看裝置磁片上的所有檔案，包括已過時、已封存的檔案，以及每日未存取的檔。</span><span class="sxs-lookup"><span data-stu-id="b09d1-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="b09d1-150">您想確定可擕式裝置（例如 USB 磁片磁碟機）不包含惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="b09d1-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="b09d1-151">自訂掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-151">Custom scan</span></span> <p><span data-ttu-id="b09d1-152">自訂掃描可讓您選取特定位置、資料夾或檔案，並執行快速掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="b09d1-153">若要瞭解快速和完整掃描，還需要瞭解什麼？</span><span class="sxs-lookup"><span data-stu-id="b09d1-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="b09d1-154">惡意檔案可以儲存在快速掃描中未包含的位置。</span><span class="sxs-lookup"><span data-stu-id="b09d1-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="b09d1-155">不過，always on 即時保護會檢查開啟和關閉的所有檔案，以及使用者可存取之資料夾中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="b09d1-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="b09d1-156">即時保護和快速掃描的組合，可協助抵禦惡意程式碼的加強防護。</span><span class="sxs-lookup"><span data-stu-id="b09d1-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="b09d1-157">以 [雲端傳送保護](cloud-protection-microsoft-defender-antivirus.md) 的存取保護，可協助確保已使用最新的安全性情報和雲端機教學模型掃描系統上存取的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="b09d1-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="b09d1-158">當即時保護偵測到惡意程式碼，且不會最初決定受影響的檔案的程度時，Microsoft Defender 防毒軟體會在修復程式中啟動完整掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="b09d1-159">完整掃描可偵測其他掃描未偵測到的惡意檔，例如快速掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="b09d1-160">不過，完整掃描可能需要一段時間，並使用寶貴的系統資源完成。</span><span class="sxs-lookup"><span data-stu-id="b09d1-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="b09d1-161">如果裝置離線一段時間，則完整掃描可能需要較長的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="b09d1-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="b09d1-162">設定排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-162">Set up scheduled scans</span></span>

<span data-ttu-id="b09d1-163">排定的掃描會在您指定的日期和時間執行。</span><span class="sxs-lookup"><span data-stu-id="b09d1-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="b09d1-164">您可以使用「群組原則」、「PowerShell」和「WMI」來設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="b09d1-165">如果在排程完整掃描期間，裝置已拔出並在電池上執行，則排定的掃描會停止事件1002，這表明掃描在完成前已停止。</span><span class="sxs-lookup"><span data-stu-id="b09d1-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="b09d1-166">Microsoft Defender 防毒軟體會在下一個排程的時間執行完整掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="b09d1-167">使用群組原則來排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="b09d1-168">位置</span><span class="sxs-lookup"><span data-stu-id="b09d1-168">Location</span></span> | <span data-ttu-id="b09d1-169">設定</span><span class="sxs-lookup"><span data-stu-id="b09d1-169">Setting</span></span> | <span data-ttu-id="b09d1-170">描述</span><span class="sxs-lookup"><span data-stu-id="b09d1-170">Description</span></span> | <span data-ttu-id="b09d1-171">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="b09d1-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b09d1-172">掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-172">Scan</span></span> | <span data-ttu-id="b09d1-173">指定用於排程掃描的掃描類型</span><span class="sxs-lookup"><span data-stu-id="b09d1-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="b09d1-174">快速掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-174">Quick scan</span></span> |
|<span data-ttu-id="b09d1-175">掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-175">Scan</span></span> | <span data-ttu-id="b09d1-176">指定一周中的哪一天執行排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="b09d1-177">指定 [天] (或 [永不) ] 執行掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="b09d1-178">從來不需要</span><span class="sxs-lookup"><span data-stu-id="b09d1-178">Never</span></span> |
|<span data-ttu-id="b09d1-179">掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-179">Scan</span></span> | <span data-ttu-id="b09d1-180">指定一天中執行排程掃描的時間</span><span class="sxs-lookup"><span data-stu-id="b09d1-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="b09d1-181">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) 。</span><span class="sxs-lookup"><span data-stu-id="b09d1-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="b09d1-182">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="b09d1-182">2 a.m.</span></span> |
|<span data-ttu-id="b09d1-183">根</span><span class="sxs-lookup"><span data-stu-id="b09d1-183">Root</span></span> | <span data-ttu-id="b09d1-184">隨機化排程的任務時間</span><span class="sxs-lookup"><span data-stu-id="b09d1-184">Randomize scheduled task times</span></span> |<span data-ttu-id="b09d1-185">在 Microsoft Defender 防毒軟體中，將掃描的開始時間隨機化為從0到4小時的任何間隔。</span><span class="sxs-lookup"><span data-stu-id="b09d1-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="b09d1-186">在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，隨機化掃描任何間隔加上或減30分鐘。</span><span class="sxs-lookup"><span data-stu-id="b09d1-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="b09d1-187">這對虛擬機器或 VDI 部署很有用。</span><span class="sxs-lookup"><span data-stu-id="b09d1-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="b09d1-188">Enabled</span><span class="sxs-lookup"><span data-stu-id="b09d1-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="b09d1-189">使用 PowerShell Cmdlet 來排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="b09d1-190">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b09d1-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="b09d1-191">如需詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) ，以取得如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b09d1-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="b09d1-192">使用 Windows 管理指令 (WMI) 來排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="b09d1-193">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="b09d1-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="b09d1-194">如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="b09d1-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="b09d1-195">只有在端點未使用中時才開始排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="b09d1-196">您可以設定排程的掃描，只會在端點開啟時，但不能與群組原則、PowerShell 或 WMI 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b09d1-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="b09d1-197">這些掃描不會服從 CPU 節流設定，而且可充分利用資源，以盡可能快地完成掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="b09d1-198">使用群組原則來排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="b09d1-199">位置</span><span class="sxs-lookup"><span data-stu-id="b09d1-199">Location</span></span> | <span data-ttu-id="b09d1-200">設定</span><span class="sxs-lookup"><span data-stu-id="b09d1-200">Setting</span></span> | <span data-ttu-id="b09d1-201">描述</span><span class="sxs-lookup"><span data-stu-id="b09d1-201">Description</span></span> | <span data-ttu-id="b09d1-202">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="b09d1-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b09d1-203">掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-203">Scan</span></span> | <span data-ttu-id="b09d1-204">僅當電腦已開啟但未在使用中時啟動排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="b09d1-205">除非電腦已開啟但未在使用中，否則不會執行排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="b09d1-206">Enabled</span><span class="sxs-lookup"><span data-stu-id="b09d1-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="b09d1-207">使用 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b09d1-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="b09d1-208">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b09d1-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="b09d1-209">如需詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="b09d1-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="b09d1-210"> (WMI) 使用 Windows 管理指令</span><span class="sxs-lookup"><span data-stu-id="b09d1-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="b09d1-211">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="b09d1-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="b09d1-212">如需 APIs 及允許參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="b09d1-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="b09d1-213">設定應該執行完整掃描以完成修復的時間</span><span class="sxs-lookup"><span data-stu-id="b09d1-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="b09d1-214">有些威脅可能需要完整掃描，才能完成移除和修復。</span><span class="sxs-lookup"><span data-stu-id="b09d1-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="b09d1-215">您可以指定何時使用群組原則、PowerShell 或 WMI 進行這些掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="b09d1-216">使用群組原則來排定修復所需的掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="b09d1-217">位置</span><span class="sxs-lookup"><span data-stu-id="b09d1-217">Location</span></span> | <span data-ttu-id="b09d1-218">設定</span><span class="sxs-lookup"><span data-stu-id="b09d1-218">Setting</span></span> | <span data-ttu-id="b09d1-219">描述</span><span class="sxs-lookup"><span data-stu-id="b09d1-219">Description</span></span> | <span data-ttu-id="b09d1-220">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="b09d1-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="b09d1-221">修復</span><span class="sxs-lookup"><span data-stu-id="b09d1-221">Remediation</span></span> | <span data-ttu-id="b09d1-222">指定一周中的哪幾天執行排程完整掃描以完成修復</span><span class="sxs-lookup"><span data-stu-id="b09d1-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="b09d1-223">指定 [天] (或 [永不) ] 執行掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="b09d1-224">從來不需要</span><span class="sxs-lookup"><span data-stu-id="b09d1-224">Never</span></span> |
|<span data-ttu-id="b09d1-225">修復</span><span class="sxs-lookup"><span data-stu-id="b09d1-225">Remediation</span></span> | <span data-ttu-id="b09d1-226">指定一天中執行計畫完整掃描以完成修復的時間</span><span class="sxs-lookup"><span data-stu-id="b09d1-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="b09d1-227">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) </span><span class="sxs-lookup"><span data-stu-id="b09d1-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="b09d1-228">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="b09d1-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="b09d1-229">使用 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b09d1-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="b09d1-230">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b09d1-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="b09d1-231">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="b09d1-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="b09d1-232"> (WMI) 使用 Windows 管理指令</span><span class="sxs-lookup"><span data-stu-id="b09d1-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="b09d1-233">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="b09d1-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="b09d1-234">如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="b09d1-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="b09d1-235">設定每日快速掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-235">Set up daily quick scans</span></span>

<span data-ttu-id="b09d1-236">除了使用群組原則、PowerShell 或 WMI 排定的其他排程掃描之外，您還可以啟用執行每日快速掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="b09d1-237">使用群組原則排定每日掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="b09d1-238">位置</span><span class="sxs-lookup"><span data-stu-id="b09d1-238">Location</span></span> | <span data-ttu-id="b09d1-239">設定</span><span class="sxs-lookup"><span data-stu-id="b09d1-239">Setting</span></span> | <span data-ttu-id="b09d1-240">描述</span><span class="sxs-lookup"><span data-stu-id="b09d1-240">Description</span></span> | <span data-ttu-id="b09d1-241">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="b09d1-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b09d1-242">掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-242">Scan</span></span> | <span data-ttu-id="b09d1-243">指定每天執行快速掃描的間隔</span><span class="sxs-lookup"><span data-stu-id="b09d1-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="b09d1-244">指定下一個快速掃描之前所應經過的小時數。</span><span class="sxs-lookup"><span data-stu-id="b09d1-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="b09d1-245">例如，若要每兩個小時執行一次，請輸入 **2** 一天一次，輸入 **24**。</span><span class="sxs-lookup"><span data-stu-id="b09d1-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="b09d1-246">輸入 **0** ，永遠不執行每日快速掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="b09d1-247">從來不需要</span><span class="sxs-lookup"><span data-stu-id="b09d1-247">Never</span></span> |
|<span data-ttu-id="b09d1-248">掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-248">Scan</span></span> | <span data-ttu-id="b09d1-249">指定每日快速掃描的時間</span><span class="sxs-lookup"><span data-stu-id="b09d1-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="b09d1-250">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) </span><span class="sxs-lookup"><span data-stu-id="b09d1-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="b09d1-251">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="b09d1-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="b09d1-252">使用 PowerShell Cmdlet 排程每日掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="b09d1-253">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b09d1-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="b09d1-254">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="b09d1-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="b09d1-255">使用 Windows 管理指令 (WMI) 排定每日掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="b09d1-256">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="b09d1-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="b09d1-257">如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="b09d1-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="b09d1-258">在保護更新後啟用掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-258">Enable scans after protection updates</span></span>

<span data-ttu-id="b09d1-259">您可以使用群組原則，強制進行每個 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後的掃描。</span><span class="sxs-lookup"><span data-stu-id="b09d1-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="b09d1-260">使用群組原則在保護更新後排程掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="b09d1-261">位置</span><span class="sxs-lookup"><span data-stu-id="b09d1-261">Location</span></span> | <span data-ttu-id="b09d1-262">設定</span><span class="sxs-lookup"><span data-stu-id="b09d1-262">Setting</span></span> | <span data-ttu-id="b09d1-263">描述</span><span class="sxs-lookup"><span data-stu-id="b09d1-263">Description</span></span> | <span data-ttu-id="b09d1-264">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="b09d1-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="b09d1-265">特徵碼更新</span><span class="sxs-lookup"><span data-stu-id="b09d1-265">Signature updates</span></span> | <span data-ttu-id="b09d1-266">在安全性智慧更新後開啟掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="b09d1-267">下載新的保護更新後會立即進行掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="b09d1-268">Enabled</span><span class="sxs-lookup"><span data-stu-id="b09d1-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="b09d1-269">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b09d1-269">See also</span></span>

- [<span data-ttu-id="b09d1-270">防止或允許使用者本機修改原則設定</span><span class="sxs-lookup"><span data-stu-id="b09d1-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b09d1-271">設定和執行隨選 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="b09d1-271">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b09d1-272">設定 Microsoft Defender 防毒軟體掃描選項</span><span class="sxs-lookup"><span data-stu-id="b09d1-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b09d1-273">管理 Microsoft Defender 防毒軟體更新及套用基準</span><span class="sxs-lookup"><span data-stu-id="b09d1-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b09d1-274">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="b09d1-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="b09d1-275">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="b09d1-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)