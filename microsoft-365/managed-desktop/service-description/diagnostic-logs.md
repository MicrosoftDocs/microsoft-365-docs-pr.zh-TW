---
title: 診斷記錄
description: 疑難排解時可能會從裝置收集的記錄，以及如何儲存這些記錄
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272886"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="3f1ed-104">診斷記錄</span><span class="sxs-lookup"><span data-stu-id="3f1ed-104">Diagnostic logs</span></span>

<span data-ttu-id="3f1ed-105">當我們對 Microsoft 受管理的電腦所管理的裝置進行疑難排解時，無論您是否已報告或由我們服務識別的裝置，我們可能必須從該裝置收集特定的診斷記錄，而不需要使用者介入。</span><span class="sxs-lookup"><span data-stu-id="3f1ed-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="3f1ed-106">我們不會從使用者目錄收集任何使用者產生的內容或資訊。</span><span class="sxs-lookup"><span data-stu-id="3f1ed-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="3f1ed-107">我們只收集關心裝置健康情況和狀態的診斷和記錄資料。</span><span class="sxs-lookup"><span data-stu-id="3f1ed-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="3f1ed-108">我們會將任何收集的記錄儲存一28天，然後加以刪除。</span><span class="sxs-lookup"><span data-stu-id="3f1ed-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="3f1ed-109">我們處理 [資料處理標準](privacy-personal-data.md)之後從裝置收集到的任何記錄。</span><span class="sxs-lookup"><span data-stu-id="3f1ed-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="3f1ed-110">收集的資料</span><span class="sxs-lookup"><span data-stu-id="3f1ed-110">Data collected</span></span>

<span data-ttu-id="3f1ed-111">此清單包含 Microsoft 受管理的電腦可能收集診斷記錄的所有資料夾、事件記錄檔、可執行檔或登錄位置。</span><span class="sxs-lookup"><span data-stu-id="3f1ed-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="3f1ed-112">收集的實際資料會是此清單的子集，視已識別的問題而定。</span><span class="sxs-lookup"><span data-stu-id="3f1ed-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="3f1ed-113">登錄機碼</span><span class="sxs-lookup"><span data-stu-id="3f1ed-113">Registry keys</span></span>

- <span data-ttu-id="3f1ed-114">HKLM \\ 系統 \\ CurrentControlSet \\ 服務</span><span class="sxs-lookup"><span data-stu-id="3f1ed-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="3f1ed-115">HKLM \\ 軟體 \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="3f1ed-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="3f1ed-116">HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ Windows \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="3f1ed-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="3f1ed-117">HKLM \\ 系統 \\ CurrentControlSet \\ 控制 \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="3f1ed-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="3f1ed-118">HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="3f1ed-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="3f1ed-119">HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="3f1ed-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="3f1ed-120">HKLM \\ 軟體 \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="3f1ed-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="3f1ed-121">HKLM \\ 軟體 \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="3f1ed-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="3f1ed-122">HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="3f1ed-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="3f1ed-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ 控制 \\ FirmwareResources</span><span class="sxs-lookup"><span data-stu-id="3f1ed-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="3f1ed-124">HKLM \\ 軟體 \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="3f1ed-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="3f1ed-125">HKLM \\ 軟體 \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="3f1ed-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="3f1ed-126">HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="3f1ed-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="3f1ed-127">HKLM \\ 軟體 \\ Microsoft \\ Windows NT \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="3f1ed-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="3f1ed-128">HKLM \\ 系統 \\ 設定</span><span class="sxs-lookup"><span data-stu-id="3f1ed-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="3f1ed-129">HKLM \\ 軟體 \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="3f1ed-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="3f1ed-130">HKLM \\ 軟體 \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="3f1ed-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="3f1ed-131">HKLM \\ 軟體 \\ Microsoft \\ Windows 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="3f1ed-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="3f1ed-132">HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ 驗證 \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="3f1ed-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="3f1ed-133">HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ Internet 設定</span><span class="sxs-lookup"><span data-stu-id="3f1ed-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="3f1ed-134">HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ 卸載</span><span class="sxs-lookup"><span data-stu-id="3f1ed-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="3f1ed-135">HKLM \\ 軟體 \\ 原則</span><span class="sxs-lookup"><span data-stu-id="3f1ed-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="3f1ed-136">HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ 加密 \\ 設定 \\ SSL</span><span class="sxs-lookup"><span data-stu-id="3f1ed-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="3f1ed-137">HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ Windows 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="3f1ed-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="3f1ed-138">HKLM \\ 軟體 \\ WOW6432Node \\ Microsoft \\ Windows \\ CurrentVersion \\ 卸載</span><span class="sxs-lookup"><span data-stu-id="3f1ed-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="3f1ed-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="3f1ed-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="3f1ed-140">命令</span><span class="sxs-lookup"><span data-stu-id="3f1ed-140">Commands</span></span>

- <span data-ttu-id="3f1ed-141">% programfiles% \\ windows defender \\mpcmdrun.exe-GetFiles</span><span class="sxs-lookup"><span data-stu-id="3f1ed-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="3f1ed-142">% windir% \\ system32 \\certutil.exe-儲存區</span><span class="sxs-lookup"><span data-stu-id="3f1ed-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="3f1ed-143">% windir% \\ system32 \\certutil.exe-store-使用者 my</span><span class="sxs-lookup"><span data-stu-id="3f1ed-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="3f1ed-144">% windir% \\ system32 \\Dsregcmd.exe/status</span><span class="sxs-lookup"><span data-stu-id="3f1ed-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="3f1ed-145">% windir% \\ system32 \\ipconfig.exe/all</span><span class="sxs-lookup"><span data-stu-id="3f1ed-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="3f1ed-146">% windir% \\ system32 \\ipconfig.exe/displaydns</span><span class="sxs-lookup"><span data-stu-id="3f1ed-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="3f1ed-147">% windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="3f1ed-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="3f1ed-148">% windir% \\ system32 \\msinfo32.exe/report% temp% \\ MDMDiagnostics \\ msinfo32，記錄檔</span><span class="sxs-lookup"><span data-stu-id="3f1ed-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="3f1ed-149">% windir% \\ system32 \\netsh.exe advfirewall show allprofiles</span><span class="sxs-lookup"><span data-stu-id="3f1ed-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="3f1ed-150">% windir% \\ system32 \\netsh.exe advfirewall show global</span><span class="sxs-lookup"><span data-stu-id="3f1ed-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="3f1ed-151">% windir% \\ system32 \\netsh.exe lan 顯示設定檔</span><span class="sxs-lookup"><span data-stu-id="3f1ed-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="3f1ed-152">% windir% \\ system32 \\netsh.exe winHTTP 顯示 proxy</span><span class="sxs-lookup"><span data-stu-id="3f1ed-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="3f1ed-153">% windir% \\ system32 \\netsh.exe wlan 顯示設定檔</span><span class="sxs-lookup"><span data-stu-id="3f1ed-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="3f1ed-154">% windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="3f1ed-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="3f1ed-155">% windir% \\ system32 \\ping.exe-n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="3f1ed-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="3f1ed-156">% windir% \\ system32 \\powercfg.exe/batteryreport/output% temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="3f1ed-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="3f1ed-157">% windir% \\ system32 \\powercfg.exe/energy/output% temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="3f1ed-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="3f1ed-158">bitsadmin/list/allusers/verbose</span><span class="sxs-lookup"><span data-stu-id="3f1ed-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="3f1ed-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="3f1ed-159">fltMC.exe</span></span>
- <span data-ttu-id="3f1ed-160">bcdedit/enum all/v</span><span class="sxs-lookup"><span data-stu-id="3f1ed-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="3f1ed-161">manage-bde-保護-取得</span><span class="sxs-lookup"><span data-stu-id="3f1ed-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="3f1ed-162">Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="3f1ed-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="3f1ed-163">Appxpackage-allusers</span><span class="sxs-lookup"><span data-stu-id="3f1ed-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="3f1ed-164">Appxpackage-packagetype 型捆綁</span><span class="sxs-lookup"><span data-stu-id="3f1ed-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="3f1ed-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="3f1ed-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="3f1ed-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="3f1ed-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="3f1ed-167">Get-WmiObject 類別的 win32 \_ 產品</span><span class="sxs-lookup"><span data-stu-id="3f1ed-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="3f1ed-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="3f1ed-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="3f1ed-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="3f1ed-169">Get-Service</span></span>
    - <span data-ttu-id="3f1ed-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="3f1ed-170">Get-Process</span></span>
    - <span data-ttu-id="3f1ed-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="3f1ed-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="3f1ed-172">事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="3f1ed-172">Event logs</span></span>

- <span data-ttu-id="3f1ed-173">應用程式</span><span class="sxs-lookup"><span data-stu-id="3f1ed-173">Application</span></span>
- <span data-ttu-id="3f1ed-174">Microsoft-Windows-AppLocker/EXE 和 DLL</span><span class="sxs-lookup"><span data-stu-id="3f1ed-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="3f1ed-175">Microsoft-Windows-AppLocker/MSI 及腳本</span><span class="sxs-lookup"><span data-stu-id="3f1ed-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="3f1ed-176">Microsoft-Windows-AppLocker/封裝應用程式部署</span><span class="sxs-lookup"><span data-stu-id="3f1ed-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="3f1ed-177">Microsoft-Windows-AppLocker/封裝應用程式-執行</span><span class="sxs-lookup"><span data-stu-id="3f1ed-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="3f1ed-178">Microsoft-Windows-bitlocker/bitlocker 管理</span><span class="sxs-lookup"><span data-stu-id="3f1ed-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="3f1ed-179">Microsoft-Windows 感知/運作</span><span class="sxs-lookup"><span data-stu-id="3f1ed-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="3f1ed-180">Microsoft-Windows SenseIR/運作</span><span class="sxs-lookup"><span data-stu-id="3f1ed-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="3f1ed-181">設定</span><span class="sxs-lookup"><span data-stu-id="3f1ed-181">Setup</span></span>
- <span data-ttu-id="3f1ed-182">系統</span><span class="sxs-lookup"><span data-stu-id="3f1ed-182">System</span></span>

### <a name="files"></a><span data-ttu-id="3f1ed-183">檔案</span><span class="sxs-lookup"><span data-stu-id="3f1ed-183">Files</span></span>

- <span data-ttu-id="3f1ed-184">% ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ 收集器 \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="3f1ed-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="3f1ed-185">% ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ 記錄檔 \\ \* 。\*</span><span class="sxs-lookup"><span data-stu-id="3f1ed-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="3f1ed-186">% ProgramData% \\ Microsoft \\ Windows Defender \\ 支援 \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="3f1ed-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="3f1ed-187">% ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="3f1ed-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="3f1ed-188">% ProgramData% \\ Microsoft \\ Windows \\ WlanReport-SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="3f1ed-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="3f1ed-189">% windir% \\ ccm \\ 記錄檔 \* 記錄檔</span><span class="sxs-lookup"><span data-stu-id="3f1ed-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="3f1ed-190">% windir% \\ ccmsetup \\ 記錄檔 \* 記錄檔</span><span class="sxs-lookup"><span data-stu-id="3f1ed-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="3f1ed-191">% windir% \\ 記錄 \\ CBS \\ cbs 記錄</span><span class="sxs-lookup"><span data-stu-id="3f1ed-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="3f1ed-192">% windir% \\ 記錄檔 \\ measuredboot \* 。\*</span><span class="sxs-lookup"><span data-stu-id="3f1ed-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="3f1ed-193">% windir% \\ 記錄 \\ WindowsUpdate \*</span><span class="sxs-lookup"><span data-stu-id="3f1ed-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="3f1ed-194">% windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="3f1ed-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="3f1ed-195">% windir% \\ 服務 \\ 會話 \\ActionList.xml</span><span class="sxs-lookup"><span data-stu-id="3f1ed-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="3f1ed-196">% windir% \\ 服務 \\ 會話 \\Sessions.xml</span><span class="sxs-lookup"><span data-stu-id="3f1ed-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="3f1ed-197">% windir% \\ SoftwareDistribution \\ 資料存儲 \\ 記錄 \\ edb 記錄</span><span class="sxs-lookup"><span data-stu-id="3f1ed-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="3f1ed-198">% windir% \\ SoftwareDistribution \\ 資料存儲 \\ edb</span><span class="sxs-lookup"><span data-stu-id="3f1ed-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="3f1ed-199">% windir% \\ 記錄 \\ dism \\ dism .log 記錄檔</span><span class="sxs-lookup"><span data-stu-id="3f1ed-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="3f1ed-200">% SystemRoot% \\ System32 \\ Winevt \\ 記錄</span><span class="sxs-lookup"><span data-stu-id="3f1ed-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\
- <span data-ttu-id="3f1ed-201">% appdata% \\ Microsoft \\ Teams \\ 媒體堆疊 \\ \* 。 blog</span><span class="sxs-lookup"><span data-stu-id="3f1ed-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="3f1ed-202">% appdata% \\ Microsoft \\ Teams \\ skylib \\ \*</span><span class="sxs-lookup"><span data-stu-id="3f1ed-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="3f1ed-203">% appdata% \\ Microsoft \\ Teams \\ 媒體-堆疊 \\ \*</span><span class="sxs-lookup"><span data-stu-id="3f1ed-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="3f1ed-204">% appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="3f1ed-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="3f1ed-205">% windir% \\ Windows \\ System32 \\ winevt \\ \* 。\*</span><span class="sxs-lookup"><span data-stu-id="3f1ed-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>