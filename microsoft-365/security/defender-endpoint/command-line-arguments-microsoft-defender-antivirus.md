---
title: 使用命令列來管理 Microsoft Defender 防毒軟體
description: 使用專用命令列公用程式執行 Microsoft Defender 防毒軟體掃描及設定下一代保護。
keywords: 執行 windows defender 掃描，從命令列執行防病毒掃描，從命令列、mpcmdrun、defender 執行 windows defender 掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 25f038846f9dd9855823382d4e1babcf0547fed6
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636167"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="07c18-104">使用 mpcmdrun.exe 命令列工具來設定及管理 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="07c18-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="07c18-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="07c18-105">**Applies to:**</span></span>

- [<span data-ttu-id="07c18-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="07c18-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="07c18-107">您可以使用專用命令列工具 **mpcmdrun.exe**，在 Microsoft Defender 防毒軟體中執行各種功能。</span><span class="sxs-lookup"><span data-stu-id="07c18-107">You can perform various functions in Microsoft Defender Antivirus using the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="07c18-108">當您想要自動化 Microsoft Defender 防毒軟體工作時，此公用程式非常有用。</span><span class="sxs-lookup"><span data-stu-id="07c18-108">This utility is useful when you want to automate Microsoft Defender Antivirus tasks.</span></span> <span data-ttu-id="07c18-109">您可以在中找到該公用程式 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="07c18-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="07c18-110">從命令提示字元執行。</span><span class="sxs-lookup"><span data-stu-id="07c18-110">Run it from a command prompt.</span></span>

> [!TIP]
> <span data-ttu-id="07c18-111">您可能需要開啟命令提示字元的系統管理員層級版本。</span><span class="sxs-lookup"><span data-stu-id="07c18-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="07c18-112">當您在 [開始] 功能表上搜尋 **命令提示** 字元時，選擇 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="07c18-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span> <span data-ttu-id="07c18-113">如果您正在執行更新的 Microsoft Defender 平臺版本，請 `MpCmdRun` 從下列位置執行： `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 。</span><span class="sxs-lookup"><span data-stu-id="07c18-113">If you're running an updated Microsoft Defender Platform version, run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span> <span data-ttu-id="07c18-114">如需有關反惡意程式碼平臺的詳細資訊，請參閱[Microsoft Defender 防毒軟體更新和基準](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="07c18-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="07c18-115">MpCmdRun 實用程式使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="07c18-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="07c18-116">以下為範例:</span><span class="sxs-lookup"><span data-stu-id="07c18-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

<span data-ttu-id="07c18-117">在我們的範例中，MpCmdRun 公用程式會在裝置上啟動完整的防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="07c18-117">In our example, the MpCmdRun utility starts a full antivirus scan on the device.</span></span>

## <a name="commands"></a><span data-ttu-id="07c18-118">命令</span><span class="sxs-lookup"><span data-stu-id="07c18-118">Commands</span></span>

| <span data-ttu-id="07c18-119">命令</span><span class="sxs-lookup"><span data-stu-id="07c18-119">Command</span></span>  | <span data-ttu-id="07c18-120">描述</span><span class="sxs-lookup"><span data-stu-id="07c18-120">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="07c18-121">`-?`**或**`-h`</span><span class="sxs-lookup"><span data-stu-id="07c18-121">`-?` **or** `-h`</span></span>   | <span data-ttu-id="07c18-122">顯示 MpCmdRun 工具的所有可用選項</span><span class="sxs-lookup"><span data-stu-id="07c18-122">Displays all available options for the MpCmdRun tool</span></span> |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="07c18-123">掃描惡意軟體。</span><span class="sxs-lookup"><span data-stu-id="07c18-123">Scans for malicious software.</span></span> <span data-ttu-id="07c18-124">**ScanType** 的值包括：</span><span class="sxs-lookup"><span data-stu-id="07c18-124">Values for **ScanType** are:</span></span><p><span data-ttu-id="07c18-125">根據您的設定，預設為 **0**</span><span class="sxs-lookup"><span data-stu-id="07c18-125">**0** Default, according to your configuration</span></span><p><span data-ttu-id="07c18-126">**1** 快速掃描</span><span class="sxs-lookup"><span data-stu-id="07c18-126">**1** Quick scan</span></span><p><span data-ttu-id="07c18-127">**2** 完全掃描</span><span class="sxs-lookup"><span data-stu-id="07c18-127">**2** Full scan</span></span><p><span data-ttu-id="07c18-128">**3** 檔案和目錄自訂掃描。</span><span class="sxs-lookup"><span data-stu-id="07c18-128">**3** File and directory custom scan.</span></span><p><span data-ttu-id="07c18-129">根據原則設定執行 CpuThrottling</span><span class="sxs-lookup"><span data-stu-id="07c18-129">CpuThrottling runs according to policy configurations</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="07c18-130">啟動診斷追蹤</span><span class="sxs-lookup"><span data-stu-id="07c18-130">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="07c18-131">收集支援資訊。</span><span class="sxs-lookup"><span data-stu-id="07c18-131">Collects support information.</span></span> <span data-ttu-id="07c18-132">請參閱[收集診斷資料](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="07c18-132">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="07c18-133">等同于 `-GetFiles` ，但輸出到暫時 DiagTrack 資料夾</span><span class="sxs-lookup"><span data-stu-id="07c18-133">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="07c18-134">將已安裝的安全性情報還原為先前的備份副本或原始的預設集合</span><span class="sxs-lookup"><span data-stu-id="07c18-134">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="07c18-135">僅移除已下載的安全性情報</span><span class="sxs-lookup"><span data-stu-id="07c18-135">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="07c18-136">還原先前安裝的引擎</span><span class="sxs-lookup"><span data-stu-id="07c18-136">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="07c18-137">檢查新的安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="07c18-137">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="07c18-138">還原或列出隔離的專案 (s) </span><span class="sxs-lookup"><span data-stu-id="07c18-138">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="07c18-139">載入動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="07c18-139">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="07c18-140">列出已載入的動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="07c18-140">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="07c18-141">移除動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="07c18-141">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="07c18-142">檢查是否排除路徑</span><span class="sxs-lookup"><span data-stu-id="07c18-142">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="07c18-143">驗證您的網路是否可以與 Microsoft Defender 防毒軟體雲端服務通訊。</span><span class="sxs-lookup"><span data-stu-id="07c18-143">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="07c18-144">這個命令只會在 Windows 10 版本1703或更高版本上運作。</span><span class="sxs-lookup"><span data-stu-id="07c18-144">This command will only work on Windows 10, version 1703 or higher.</span></span>|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="07c18-145">透過 mpcmdrun.exe 執行命令時的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="07c18-145">Common errors in running commands via mpcmdrun.exe</span></span> 

<span data-ttu-id="07c18-146">下表列出使用 MpCmdRun 工具時可能會發生的常見錯誤。</span><span class="sxs-lookup"><span data-stu-id="07c18-146">The following table lists common errors that can occur while using the MpCmdRun tool.</span></span>

|<span data-ttu-id="07c18-147">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="07c18-147">Error message</span></span> | <span data-ttu-id="07c18-148">可能的原因</span><span class="sxs-lookup"><span data-stu-id="07c18-148">Possible reason</span></span> |
|:----|:----|
| <span data-ttu-id="07c18-149">**ValidateMapsConnection 失敗 (800106BA)** 或 **0x800106BA**</span><span class="sxs-lookup"><span data-stu-id="07c18-149">**ValidateMapsConnection failed (800106BA)** or **0x800106BA**</span></span> | <span data-ttu-id="07c18-150">已停用 Microsoft Defender 防毒軟體服務。</span><span class="sxs-lookup"><span data-stu-id="07c18-150">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="07c18-151">請啟用服務，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="07c18-151">Enable the service and try again.</span></span> <span data-ttu-id="07c18-152">如果您需要協助重新啟用 Microsoft Defender 防毒軟體，請參閱[在端點上重新安裝/啟用 Microsoft Defender 防毒軟體](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="07c18-152">If you need help re-enabling Microsoft Defender Antivirus, see [Reinstall/enable Microsoft Defender Antivirus on your endpoints](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).</span></span><p>   <span data-ttu-id="07c18-153">**秘訣** 在 Windows 10 1909 或更舊版本，以及 Windows Server 2019 或更舊版本中，此服務先前稱為 *Windows Defender 防毒軟體*。</span><span class="sxs-lookup"><span data-stu-id="07c18-153">**TIP**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service was formerly called *Windows Defender Antivirus*.</span></span> |
| <span data-ttu-id="07c18-154">**0x80070667**</span><span class="sxs-lookup"><span data-stu-id="07c18-154">**0x80070667**</span></span> | <span data-ttu-id="07c18-155">您正在 `-ValidateMapsConnection` 從 Windows 10 版本1607或更舊版本的電腦，或 Windows Server 2016 或更舊版本執行命令。</span><span class="sxs-lookup"><span data-stu-id="07c18-155">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="07c18-156">從 Windows 10 版本1703或更新版本的機器執行命令，或 Windows 伺服器2019或更新版本。</span><span class="sxs-lookup"><span data-stu-id="07c18-156">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| <span data-ttu-id="07c18-157">**MpCmdRun 未被辨識為內部或外部命令、可的程式或批次檔。**</span><span class="sxs-lookup"><span data-stu-id="07c18-157">**MpCmdRun is not recognized as an internal or external command, operable program, or batch file.**</span></span> | <span data-ttu-id="07c18-158">您必須從或 (執行該工具， `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 因為平臺更新是每月以外的月，而不是三月份) </span><span class="sxs-lookup"><span data-stu-id="07c18-158">The tool must be run from either `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| <span data-ttu-id="07c18-159">**ValidateMapsConnection 無法建立與對應 (hr = 80070005 HTTPcode = 450) 的連接**</span><span class="sxs-lookup"><span data-stu-id="07c18-159">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)**</span></span> | <span data-ttu-id="07c18-160">命令嘗試使用的許可權不足。</span><span class="sxs-lookup"><span data-stu-id="07c18-160">The command was attempted using insufficient privileges.</span></span> <span data-ttu-id="07c18-161">以系統管理員身分 (cmd.exe) 使用命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="07c18-161">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| <span data-ttu-id="07c18-162">**ValidateMapsConnection 無法建立與對應 (hr = 80070006 HTTPcode = 451 的連接)**</span><span class="sxs-lookup"><span data-stu-id="07c18-162">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)**</span></span> | <span data-ttu-id="07c18-163">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="07c18-163">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="07c18-164">**ValidateMapsConnection 無法建立與對應 (hr = 80004005 HTTPcode = 450 的連接)**</span><span class="sxs-lookup"><span data-stu-id="07c18-164">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)**</span></span> | <span data-ttu-id="07c18-165">可能的網路相關問題，例如名稱解析問題</span><span class="sxs-lookup"><span data-stu-id="07c18-165">Possible network-related issues, like name resolution problems</span></span>|
| <span data-ttu-id="07c18-166">**ValidateMapsConnection 無法建立與對應 (hr = 0x80508015 的連接**</span><span class="sxs-lookup"><span data-stu-id="07c18-166">**ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015**</span></span> | <span data-ttu-id="07c18-167">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="07c18-167">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="07c18-168">**ValidateMapsConnection 無法建立與對應 (hr = 800722F0D 的連接**</span><span class="sxs-lookup"><span data-stu-id="07c18-168">**ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D**</span></span> | <span data-ttu-id="07c18-169">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="07c18-169">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="07c18-170">**ValidateMapsConnection 無法建立與對應 (hr = 80072EE7 HTTPcode = 451 的連接)**</span><span class="sxs-lookup"><span data-stu-id="07c18-170">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)**</span></span> | <span data-ttu-id="07c18-171">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="07c18-171">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="07c18-172">請參閱</span><span class="sxs-lookup"><span data-stu-id="07c18-172">See also</span></span>

- [<span data-ttu-id="07c18-173">設定 Microsoft Defender 防毒軟體功能</span><span class="sxs-lookup"><span data-stu-id="07c18-173">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="07c18-174">設定及驗證 Microsoft Defender 防毒軟體網路連線</span><span class="sxs-lookup"><span data-stu-id="07c18-174">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md)
- [<span data-ttu-id="07c18-175">管理及設定工具的參考主題</span><span class="sxs-lookup"><span data-stu-id="07c18-175">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
