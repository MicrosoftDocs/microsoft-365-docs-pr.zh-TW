---
title: 設定 Microsoft Defender 防毒軟體的掃描選項
description: 您可以設定 Microsoft Defender AV 掃描電子郵件儲存檔案、備份或重新分析點、網路檔，以及封存的檔案 (例如 .zip 檔案) 。
keywords: 高級掃描、掃描、電子郵件、封存、zip、rar、封存、重新分析掃描
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 34f423222068236271afdda13afb95cffa58b709
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683808"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="2faaa-104">設定 Microsoft Defender 防毒軟體掃描選項</span><span class="sxs-lookup"><span data-stu-id="2faaa-104">Configure Microsoft Defender Antivirus scanning options</span></span>

<span data-ttu-id="2faaa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2faaa-105">**Applies to:**</span></span>

- [<span data-ttu-id="2faaa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2faaa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="2faaa-107">使用 Microsoft Intune 設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="2faaa-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="2faaa-108">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="2faaa-108">See the following resources:</span></span> 

- [<span data-ttu-id="2faaa-109">在 Microsoft Intune 中設定裝置限制設定</span><span class="sxs-lookup"><span data-stu-id="2faaa-109">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure) 
- [<span data-ttu-id="2faaa-110">在 Intune 中 Microsoft Defender 防毒軟體 Windows 10 裝置限制設定</span><span class="sxs-lookup"><span data-stu-id="2faaa-110">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="2faaa-111">使用 Microsoft 端點管理員設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="2faaa-111">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="2faaa-112">請參閱 [如何建立及部署反惡意程式碼原則：掃描設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。</span><span class="sxs-lookup"><span data-stu-id="2faaa-112">See [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="2faaa-113">使用群組原則設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="2faaa-113">Use Group Policy to configure scanning options</span></span>

1. <span data-ttu-id="2faaa-114">在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="2faaa-114">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="2faaa-115">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2faaa-115">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="2faaa-116">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="2faaa-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

4. <span data-ttu-id="2faaa-117">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**，然後選取位置 (參閱本文) 的 [設定和位置](#settings-and-locations)。</span><span class="sxs-lookup"><span data-stu-id="2faaa-117">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**, and then select a location (refer to [Settings and locations](#settings-and-locations) in this article).</span></span>

5. <span data-ttu-id="2faaa-118">編輯 policy 物件。</span><span class="sxs-lookup"><span data-stu-id="2faaa-118">Edit the policy object.</span></span> 

6. <span data-ttu-id="2faaa-119">按一下 **[確定]**，然後對任何其他設定重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="2faaa-119">Click **OK**, and repeat for any other settings.</span></span>

### <a name="settings-and-locations"></a><span data-ttu-id="2faaa-120">設定和位置</span><span class="sxs-lookup"><span data-stu-id="2faaa-120">Settings and locations</span></span>

| <span data-ttu-id="2faaa-121">原則專案和位置</span><span class="sxs-lookup"><span data-stu-id="2faaa-121">Policy item and location</span></span> | <span data-ttu-id="2faaa-122">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="2faaa-122">Default setting (if not configured)</span></span> | <span data-ttu-id="2faaa-123">`Set-MpPreference`Class 的 PowerShell 參數或 WMI 屬性 `MSFT_MpPreference`</span><span class="sxs-lookup"><span data-stu-id="2faaa-123">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span> |
|---|---|---|
| <span data-ttu-id="2faaa-124">電子郵件掃描</span><span class="sxs-lookup"><span data-stu-id="2faaa-124">Email scanning</span></span> <p> <span data-ttu-id="2faaa-125">**掃描**  > **開啟電子郵件掃描**</span><span class="sxs-lookup"><span data-stu-id="2faaa-125">**Scan** > **Turn on e-mail scanning**</span></span><p><span data-ttu-id="2faaa-126">請參閱本文 (的 [電子郵件掃描限制](#email-scanning-limitations)) </span><span class="sxs-lookup"><span data-stu-id="2faaa-126">See [Email scanning limitations](#email-scanning-limitations) (in this article)</span></span> | <span data-ttu-id="2faaa-127">停用</span><span class="sxs-lookup"><span data-stu-id="2faaa-127">Disabled</span></span> | `-DisableEmailScanning` |
|<span data-ttu-id="2faaa-128">掃描重新 [分析點](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="2faaa-128">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> <p> <span data-ttu-id="2faaa-129">**掃描**  > **開啟重新分析點掃描**</span><span class="sxs-lookup"><span data-stu-id="2faaa-129">**Scan** > **Turn on reparse point scanning**</span></span> | <span data-ttu-id="2faaa-130">停用</span><span class="sxs-lookup"><span data-stu-id="2faaa-130">Disabled</span></span> | <span data-ttu-id="2faaa-131">無</span><span class="sxs-lookup"><span data-stu-id="2faaa-131">Not available</span></span> <p><span data-ttu-id="2faaa-132">請參閱重新 [分析點](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="2faaa-132">See [Reparse points](/windows/win32/fileio/reparse-points)</span></span>  |
| <span data-ttu-id="2faaa-133">掃描對應的網路磁碟機</span><span class="sxs-lookup"><span data-stu-id="2faaa-133">Scan mapped network drives</span></span> <p> <span data-ttu-id="2faaa-134">**掃描**  > **在對應的網路磁碟機上執行完整掃描**</span><span class="sxs-lookup"><span data-stu-id="2faaa-134">**Scan** > **Run full scan on mapped network drives**</span></span> | <span data-ttu-id="2faaa-135">停用</span><span class="sxs-lookup"><span data-stu-id="2faaa-135">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`|
| <span data-ttu-id="2faaa-136">掃描封存檔案 (例如 .zip 或 .rar 檔) 。</span><span class="sxs-lookup"><span data-stu-id="2faaa-136">Scan archive files (such as .zip or .rar files).</span></span>  <p> <span data-ttu-id="2faaa-137">**掃描**  > **掃描封存檔案**</span><span class="sxs-lookup"><span data-stu-id="2faaa-137">**Scan** > **Scan archive files**</span></span> | <span data-ttu-id="2faaa-138">啟用</span><span class="sxs-lookup"><span data-stu-id="2faaa-138">Enabled</span></span> | `-DisableArchiveScanning` <p><span data-ttu-id="2faaa-139">[副檔名排除清單](configure-extension-file-exclusions-microsoft-defender-antivirus.md)會優先于此設定。</span><span class="sxs-lookup"><span data-stu-id="2faaa-139">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span>|
| <span data-ttu-id="2faaa-140">掃描網路上的檔案</span><span class="sxs-lookup"><span data-stu-id="2faaa-140">Scan files on the network</span></span> <p> <span data-ttu-id="2faaa-141">**掃描**  > **掃描網路檔**</span><span class="sxs-lookup"><span data-stu-id="2faaa-141">**Scan** > **Scan network files**</span></span> | <span data-ttu-id="2faaa-142">停用</span><span class="sxs-lookup"><span data-stu-id="2faaa-142">Disabled</span></span> | `-DisableScanningNetworkFiles` |
| <span data-ttu-id="2faaa-143">掃描打包的可執行檔</span><span class="sxs-lookup"><span data-stu-id="2faaa-143">Scan packed executables</span></span> <p> <span data-ttu-id="2faaa-144">**掃描**  > **掃描打包的可執行檔**</span><span class="sxs-lookup"><span data-stu-id="2faaa-144">**Scan** > **Scan packed executables**</span></span> | <span data-ttu-id="2faaa-145">啟用</span><span class="sxs-lookup"><span data-stu-id="2faaa-145">Enabled</span></span> | <span data-ttu-id="2faaa-146">無</span><span class="sxs-lookup"><span data-stu-id="2faaa-146">Not available</span></span> |
| <span data-ttu-id="2faaa-147">僅在完整掃描期間掃描抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="2faaa-147">Scan removable drives during full scans only</span></span> <p> <span data-ttu-id="2faaa-148">**掃描**  > **掃描可移除的磁片磁碟機**</span><span class="sxs-lookup"><span data-stu-id="2faaa-148">**Scan** > **Scan removable drives**</span></span> | <span data-ttu-id="2faaa-149">停用</span><span class="sxs-lookup"><span data-stu-id="2faaa-149">Disabled</span></span> | `-DisableRemovableDriveScanning` |
| <span data-ttu-id="2faaa-150">指定要掃描之封存資料夾內的子資料夾層級</span><span class="sxs-lookup"><span data-stu-id="2faaa-150">Specify the level of subfolders within an archive folder to scan</span></span> <p><span data-ttu-id="2faaa-151">**掃描**  > **指定掃描封存檔案的最大深度**</span><span class="sxs-lookup"><span data-stu-id="2faaa-151">**Scan** > **Specify the maximum depth to scan archive files**</span></span> | <span data-ttu-id="2faaa-152">0</span><span class="sxs-lookup"><span data-stu-id="2faaa-152">0</span></span> | <span data-ttu-id="2faaa-153">無法使用</span><span class="sxs-lookup"><span data-stu-id="2faaa-153">Not available</span></span> |
| <span data-ttu-id="2faaa-154">在掃描期間，指定 CPU 負載 (為百分比) 。</span><span class="sxs-lookup"><span data-stu-id="2faaa-154">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <p> <span data-ttu-id="2faaa-155">**掃描**  > **指定掃描期間 CPU 使用率的最大百分比**</span><span class="sxs-lookup"><span data-stu-id="2faaa-155">**Scan** > **Specify the maximum percentage of CPU utilization during a scan**</span></span> | <span data-ttu-id="2faaa-156">50</span><span class="sxs-lookup"><span data-stu-id="2faaa-156">50</span></span> |  `-ScanAvgCPULoadFactor` <p><span data-ttu-id="2faaa-157">**附注**： CPU 負載上限不是硬性限制，但是掃描引擎不會超過平均平均上限的指導。</span><span class="sxs-lookup"><span data-stu-id="2faaa-157">**NOTE**: The maximum CPU load is not a hard limit, but is guidance for the scanning engine to not exceed the maximum on average.</span></span> <span data-ttu-id="2faaa-158">手動執行掃描將會略過此設定，而不需要任何 CPU 限制即可執行。</span><span class="sxs-lookup"><span data-stu-id="2faaa-158">Manually run scans will ignore this setting and run without any CPU limits.</span></span> |
| <span data-ttu-id="2faaa-159">指定應掃描之封存檔的大小上限 (以 kb 為單位）) 。</span><span class="sxs-lookup"><span data-stu-id="2faaa-159">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <p> <span data-ttu-id="2faaa-160">**掃描**  > **指定要掃描的封存檔案大小上限**</span><span class="sxs-lookup"><span data-stu-id="2faaa-160">**Scan** > **Specify the maximum size of archive files to be scanned**</span></span> | <span data-ttu-id="2faaa-161">無限制</span><span class="sxs-lookup"><span data-stu-id="2faaa-161">No limit</span></span> | <span data-ttu-id="2faaa-162">無</span><span class="sxs-lookup"><span data-stu-id="2faaa-162">Not available</span></span> <p><span data-ttu-id="2faaa-163">預設值0不會套用任何限制</span><span class="sxs-lookup"><span data-stu-id="2faaa-163">The default value of 0 applies no limit</span></span> |
| <span data-ttu-id="2faaa-164">設定排程掃描的低 CPU 優先順序</span><span class="sxs-lookup"><span data-stu-id="2faaa-164">Configure low CPU priority for scheduled scans</span></span> <p> <span data-ttu-id="2faaa-165">**掃描**  > 設定 **排程掃描的低 CPU 優先順序**</span><span class="sxs-lookup"><span data-stu-id="2faaa-165">**Scan** > **Configure low CPU priority for scheduled scans**</span></span> | <span data-ttu-id="2faaa-166">停用</span><span class="sxs-lookup"><span data-stu-id="2faaa-166">Disabled</span></span> | <span data-ttu-id="2faaa-167">無</span><span class="sxs-lookup"><span data-stu-id="2faaa-167">Not available</span></span> |
 
> [!NOTE]
> <span data-ttu-id="2faaa-168">如果即時保護已開啟，則會先掃描檔案，再加以存取和執行。</span><span class="sxs-lookup"><span data-stu-id="2faaa-168">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="2faaa-169">掃描範圍包括所有檔案，包括裝入的卸除式媒體（例如 USB 磁片磁碟機）上的檔案。</span><span class="sxs-lookup"><span data-stu-id="2faaa-169">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="2faaa-170">如果執行掃描的裝置已開啟即時保護或開啟時保護，則掃描也會包含網路共用。</span><span class="sxs-lookup"><span data-stu-id="2faaa-170">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="2faaa-171">使用 PowerShell 設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="2faaa-171">Use PowerShell to configure scanning options</span></span>

<span data-ttu-id="2faaa-172">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="2faaa-172">See the following resources:</span></span>

- [<span data-ttu-id="2faaa-173">使用 PowerShell Cmdlet 管理 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2faaa-173">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2faaa-174">Defender Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2faaa-174">Defender cmdlets</span></span>](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="2faaa-175">使用 WMI 設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="2faaa-175">Use WMI to configure scanning options</span></span>

<span data-ttu-id="2faaa-176">請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="2faaa-176">See [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="email-scanning-limitations"></a><span data-ttu-id="2faaa-177">電子郵件掃描限制</span><span class="sxs-lookup"><span data-stu-id="2faaa-177">Email scanning limitations</span></span>

<span data-ttu-id="2faaa-178">電子郵件掃描可讓 Outlook 和其他郵件客戶程式使用的電子郵件檔案掃描時，進行隨選及排程的掃描。</span><span class="sxs-lookup"><span data-stu-id="2faaa-178">Email scanning enables scanning of email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="2faaa-179">也會掃描電子郵件 (中的內嵌物件，例如附件及已封存的檔案) 。</span><span class="sxs-lookup"><span data-stu-id="2faaa-179">Embedded objects within email (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="2faaa-180">您可以掃描和修正下列檔案格式類型：</span><span class="sxs-lookup"><span data-stu-id="2faaa-180">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="2faaa-181">Dbx</span><span class="sxs-lookup"><span data-stu-id="2faaa-181">DBX</span></span>
- <span data-ttu-id="2faaa-182">MBX</span><span class="sxs-lookup"><span data-stu-id="2faaa-182">MBX</span></span>
- <span data-ttu-id="2faaa-183">Mime</span><span class="sxs-lookup"><span data-stu-id="2faaa-183">MIME</span></span>

<span data-ttu-id="2faaa-184">Outlook 2003 或舊版 (使用的 PST 檔案，封存類型設為非 unicode) 也會加以掃描，但是 Microsoft Defender 防毒軟體無法修正在 PST 檔案中偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="2faaa-184">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) are also scanned, but Microsoft Defender Antivirus cannot remediate threats that are detected inside PST files.</span></span>

<span data-ttu-id="2faaa-185">如果 Microsoft Defender 防毒軟體偵測到電子郵件中的威脅，它會顯示下列資訊，協助您識別遭到損害的電子郵件，因此您可以手動修正威脅：</span><span class="sxs-lookup"><span data-stu-id="2faaa-185">If Microsoft Defender Antivirus detects a threat inside an email message, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="2faaa-186">電子郵件主旨</span><span class="sxs-lookup"><span data-stu-id="2faaa-186">Email subject</span></span>
- <span data-ttu-id="2faaa-187">附件名稱</span><span class="sxs-lookup"><span data-stu-id="2faaa-187">Attachment name</span></span>

## <a name="see-also"></a><span data-ttu-id="2faaa-188">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2faaa-188">See also</span></span>

- [<span data-ttu-id="2faaa-189">自訂、啟動及審閱 Microsoft Defender 防毒軟體掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="2faaa-189">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2faaa-190">設定和執行隨選 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="2faaa-190">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2faaa-191">設定排定的 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="2faaa-191">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2faaa-192">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2faaa-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
