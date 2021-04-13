---
title: 設定 Microsoft Defender AV 的掃描選項
description: 您可以設定 Microsoft Defender AV 掃描電子郵件儲存檔案、備份或重新分析點、網路檔案，以及封存的檔案 (例如 .zip 檔案) 。
keywords: 高級掃描、掃描、電子郵件、封存、zip、rar、封存、重新分析掃描
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690124"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="e97c1-104">設定 Microsoft Defender 防病毒掃描選項</span><span class="sxs-lookup"><span data-stu-id="e97c1-104">Configure Microsoft Defender Antivirus scanning options</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e97c1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e97c1-105">**Applies to:**</span></span>

- [<span data-ttu-id="e97c1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e97c1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="e97c1-107">使用 Microsoft Intune 設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="e97c1-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="e97c1-108">如需詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure) 及 [Intune 中 Windows 10 的 Microsoft Defender 防病毒裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 。</span><span class="sxs-lookup"><span data-stu-id="e97c1-108">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="e97c1-109">使用 Microsoft 端點管理員設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="e97c1-109">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="e97c1-110">請參閱 [如何建立及部署反惡意程式碼原則：掃描設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) ，以取得設定 Microsoft 端點管理員 (目前分支) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e97c1-110">See [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="e97c1-111">使用群組原則設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="e97c1-111">Use Group Policy to configure scanning options</span></span>

<span data-ttu-id="e97c1-112">若要設定下表所述的群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="e97c1-112">To configure the Group Policy settings described in the following table:</span></span>

1. <span data-ttu-id="e97c1-113">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e97c1-113">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e97c1-114">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="e97c1-114">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="e97c1-115">在 [ **Microsoft Defender 防病毒 >** ] 的 [Windows 元件] 中，展開樹狀目錄，然後展開下表中所指定的 **位置** 。</span><span class="sxs-lookup"><span data-stu-id="e97c1-115">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="e97c1-116">按兩下下表中所指定的原則 **設定** ，並將選項設定為您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="e97c1-116">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="e97c1-117">按一下 **[確定]**，然後對任何其他設定重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="e97c1-117">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="e97c1-118">描述</span><span class="sxs-lookup"><span data-stu-id="e97c1-118">Description</span></span> | <span data-ttu-id="e97c1-119">位置和設定</span><span class="sxs-lookup"><span data-stu-id="e97c1-119">Location and setting</span></span> | <span data-ttu-id="e97c1-120">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="e97c1-120">Default setting (if not configured)</span></span> | <span data-ttu-id="e97c1-121">`Set-MpPreference`Class 的 PowerShell 參數或 WMI 屬性 `MSFT_MpPreference`</span><span class="sxs-lookup"><span data-stu-id="e97c1-121">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span>
---|---|---|---
<span data-ttu-id="e97c1-122">電子郵件掃描請參閱 [電子郵件掃描限制](#ref1)</span><span class="sxs-lookup"><span data-stu-id="e97c1-122">Email scanning See [Email scanning limitations](#ref1)</span></span>| <span data-ttu-id="e97c1-123">掃描 > 開啟電子郵件掃描</span><span class="sxs-lookup"><span data-stu-id="e97c1-123">Scan > Turn on e-mail scanning</span></span> | <span data-ttu-id="e97c1-124">已停用</span><span class="sxs-lookup"><span data-stu-id="e97c1-124">Disabled</span></span> | `-DisableEmailScanning`
<span data-ttu-id="e97c1-125">掃描重新 [分析點](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="e97c1-125">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> | <span data-ttu-id="e97c1-126">掃描 > 開啟重新分析點掃描</span><span class="sxs-lookup"><span data-stu-id="e97c1-126">Scan > Turn on reparse point scanning</span></span> | <span data-ttu-id="e97c1-127">已停用</span><span class="sxs-lookup"><span data-stu-id="e97c1-127">Disabled</span></span> | <span data-ttu-id="e97c1-128">無</span><span class="sxs-lookup"><span data-stu-id="e97c1-128">Not available</span></span>
<span data-ttu-id="e97c1-129">掃描對應的網路磁碟機</span><span class="sxs-lookup"><span data-stu-id="e97c1-129">Scan mapped network drives</span></span> | <span data-ttu-id="e97c1-130">掃描 > 在對應的網路磁碟機上執行完整掃描</span><span class="sxs-lookup"><span data-stu-id="e97c1-130">Scan > Run full scan on mapped network drives</span></span> | <span data-ttu-id="e97c1-131">已停用</span><span class="sxs-lookup"><span data-stu-id="e97c1-131">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`
 <span data-ttu-id="e97c1-132">掃描封存檔案 (例如 .zip 或 rar 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="e97c1-132">Scan archive files (such as .zip or .rar files).</span></span> <span data-ttu-id="e97c1-133">[副檔名排除清單](configure-extension-file-exclusions-microsoft-defender-antivirus.md)會優先于此設定。</span><span class="sxs-lookup"><span data-stu-id="e97c1-133">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span> | <span data-ttu-id="e97c1-134">掃描 > 掃描封存檔案</span><span class="sxs-lookup"><span data-stu-id="e97c1-134">Scan > Scan archive files</span></span> | <span data-ttu-id="e97c1-135">Enabled</span><span class="sxs-lookup"><span data-stu-id="e97c1-135">Enabled</span></span> | `-DisableArchiveScanning`
<span data-ttu-id="e97c1-136">掃描網路上的檔案</span><span class="sxs-lookup"><span data-stu-id="e97c1-136">Scan files on the network</span></span> | <span data-ttu-id="e97c1-137">掃描 > 掃描網路檔</span><span class="sxs-lookup"><span data-stu-id="e97c1-137">Scan > Scan network files</span></span> | <span data-ttu-id="e97c1-138">已停用</span><span class="sxs-lookup"><span data-stu-id="e97c1-138">Disabled</span></span> | `-DisableScanningNetworkFiles`
<span data-ttu-id="e97c1-139">掃描打包的可執行檔</span><span class="sxs-lookup"><span data-stu-id="e97c1-139">Scan packed executables</span></span> | <span data-ttu-id="e97c1-140">掃描 > 掃描打包的可執行檔</span><span class="sxs-lookup"><span data-stu-id="e97c1-140">Scan > Scan packed executables</span></span> | <span data-ttu-id="e97c1-141">Enabled</span><span class="sxs-lookup"><span data-stu-id="e97c1-141">Enabled</span></span> | <span data-ttu-id="e97c1-142">無</span><span class="sxs-lookup"><span data-stu-id="e97c1-142">Not available</span></span>
<span data-ttu-id="e97c1-143">僅在完整掃描期間掃描抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="e97c1-143">Scan removable drives during full scans only</span></span> | <span data-ttu-id="e97c1-144">掃描 > 掃描可移除磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="e97c1-144">Scan > Scan removable drives</span></span> | <span data-ttu-id="e97c1-145">已停用</span><span class="sxs-lookup"><span data-stu-id="e97c1-145">Disabled</span></span> | `-DisableRemovableDriveScanning`
<span data-ttu-id="e97c1-146">指定要掃描之封存資料夾內的子資料夾層級</span><span class="sxs-lookup"><span data-stu-id="e97c1-146">Specify the level of subfolders within an archive folder to scan</span></span> | <span data-ttu-id="e97c1-147">掃描 > 指定掃描封存檔案的最大深度</span><span class="sxs-lookup"><span data-stu-id="e97c1-147">Scan > Specify the maximum depth to scan archive files</span></span> | <span data-ttu-id="e97c1-148">0</span><span class="sxs-lookup"><span data-stu-id="e97c1-148">0</span></span> | <span data-ttu-id="e97c1-149">無法使用</span><span class="sxs-lookup"><span data-stu-id="e97c1-149">Not available</span></span>
 <span data-ttu-id="e97c1-150">在掃描期間，指定 CPU 負載 (為百分比) 。</span><span class="sxs-lookup"><span data-stu-id="e97c1-150">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <span data-ttu-id="e97c1-151">注意：這不是硬性限制，但掃描引擎的指導方針不會超過平均這一上限。</span><span class="sxs-lookup"><span data-stu-id="e97c1-151">Note: This is not a hard limit but rather a guidance for the scanning engine to not exceed this maximum on average.</span></span> | <span data-ttu-id="e97c1-152">掃描 > 指定掃描期間 CPU 使用率的最大百分比</span><span class="sxs-lookup"><span data-stu-id="e97c1-152">Scan > Specify the maximum percentage of CPU utilization during a scan</span></span> | <span data-ttu-id="e97c1-153">50</span><span class="sxs-lookup"><span data-stu-id="e97c1-153">50</span></span> |  `-ScanAvgCPULoadFactor`
 <span data-ttu-id="e97c1-154">指定應掃描之封存檔的大小上限 (以 kb 為單位）) 。</span><span class="sxs-lookup"><span data-stu-id="e97c1-154">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <span data-ttu-id="e97c1-155">預設值為 **0**，套用無限制</span><span class="sxs-lookup"><span data-stu-id="e97c1-155">The default, **0**, applies no limit</span></span> | <span data-ttu-id="e97c1-156">掃描 > 指定要掃描的封存檔案大小上限</span><span class="sxs-lookup"><span data-stu-id="e97c1-156">Scan > Specify the maximum size of archive files to be scanned</span></span> | <span data-ttu-id="e97c1-157">無限制</span><span class="sxs-lookup"><span data-stu-id="e97c1-157">No limit</span></span> | <span data-ttu-id="e97c1-158">無</span><span class="sxs-lookup"><span data-stu-id="e97c1-158">Not available</span></span>
 <span data-ttu-id="e97c1-159">設定排程掃描的低 CPU 優先順序</span><span class="sxs-lookup"><span data-stu-id="e97c1-159">Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="e97c1-160">掃描 > 設定排程掃描的低 CPU 優先順序</span><span class="sxs-lookup"><span data-stu-id="e97c1-160">Scan > Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="e97c1-161">已停用</span><span class="sxs-lookup"><span data-stu-id="e97c1-161">Disabled</span></span> | <span data-ttu-id="e97c1-162">無</span><span class="sxs-lookup"><span data-stu-id="e97c1-162">Not available</span></span>
 
> [!NOTE]
> <span data-ttu-id="e97c1-163">如果即時保護已開啟，則會先掃描檔案，再加以存取和執行。</span><span class="sxs-lookup"><span data-stu-id="e97c1-163">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="e97c1-164">掃描範圍包括所有檔案，包括裝入的卸除式媒體（例如 USB 磁片磁碟機）上的檔案。</span><span class="sxs-lookup"><span data-stu-id="e97c1-164">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="e97c1-165">如果執行掃描的裝置已開啟即時保護或開啟時保護，則掃描也會包含網路共用。</span><span class="sxs-lookup"><span data-stu-id="e97c1-165">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="e97c1-166">使用 PowerShell 設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="e97c1-166">Use PowerShell to configure scanning options</span></span>

<span data-ttu-id="e97c1-167">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [管理含 PowerShell Cmdlet 的 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="e97c1-167">See [Manage Microsoft Defender Antivirus with PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="e97c1-168">使用 WMI 設定掃描選項</span><span class="sxs-lookup"><span data-stu-id="e97c1-168">Use WMI to configure scanning options</span></span>

<span data-ttu-id="e97c1-169">如需使用 WMI 類別，請參閱 [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="e97c1-169">For using WMI classes, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a><span data-ttu-id="e97c1-170">電子郵件掃描限制</span><span class="sxs-lookup"><span data-stu-id="e97c1-170">Email scanning limitations</span></span>

<span data-ttu-id="e97c1-171">電子郵件掃描可讓 Outlook 和其他郵件用戶端在按需求和排程掃描期間使用的電子郵件檔案進行掃描。</span><span class="sxs-lookup"><span data-stu-id="e97c1-171">Email scanning enables scanning of  email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="e97c1-172">也會掃描電子郵件檔案中的內嵌物件 (例如附件及封存的檔案) 。</span><span class="sxs-lookup"><span data-stu-id="e97c1-172">Embedded objects within an email file (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="e97c1-173">您可以掃描和修正下列檔案格式類型：</span><span class="sxs-lookup"><span data-stu-id="e97c1-173">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="e97c1-174">Dbx</span><span class="sxs-lookup"><span data-stu-id="e97c1-174">DBX</span></span>
- <span data-ttu-id="e97c1-175">MBX</span><span class="sxs-lookup"><span data-stu-id="e97c1-175">MBX</span></span>
- <span data-ttu-id="e97c1-176">Mime</span><span class="sxs-lookup"><span data-stu-id="e97c1-176">MIME</span></span>

<span data-ttu-id="e97c1-177">Outlook 2003 或舊版 (所使用的 PST 檔案，其封存類型設為非 unicode) 也會進行掃描，但是 Windows Defender 無法修正在 PST 檔案中偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="e97c1-177">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) will also be scanned, but Windows Defender cannot remediate threats detected inside PST files.</span></span>

<span data-ttu-id="e97c1-178">如果 Microsoft Defender 防毒程式偵測到電子郵件內的威脅，它會顯示下列資訊以協助您識別遭到損害的電子郵件，因此您可以手動修正威脅：</span><span class="sxs-lookup"><span data-stu-id="e97c1-178">If Microsoft Defender Antivirus detects a threat inside an email, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="e97c1-179">電子郵件主旨</span><span class="sxs-lookup"><span data-stu-id="e97c1-179">Email subject</span></span>
- <span data-ttu-id="e97c1-180">附件名稱</span><span class="sxs-lookup"><span data-stu-id="e97c1-180">Attachment name</span></span>

## <a name="related-topics"></a><span data-ttu-id="e97c1-181">相關主題</span><span class="sxs-lookup"><span data-stu-id="e97c1-181">Related topics</span></span>

- [<span data-ttu-id="e97c1-182">自訂、啟動和審閱 Microsoft Defender 防病毒掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="e97c1-182">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e97c1-183">設定及執行隨選 Microsoft Defender 防毒程式掃描</span><span class="sxs-lookup"><span data-stu-id="e97c1-183">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e97c1-184">設定排定的 Microsoft Defender 防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="e97c1-184">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e97c1-185">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="e97c1-185">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)