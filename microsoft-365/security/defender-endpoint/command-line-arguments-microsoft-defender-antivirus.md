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
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538900"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="8425b-104">使用 mpcmdrun.exe 命令列工具來設定及管理 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="8425b-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="8425b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8425b-105">**Applies to:**</span></span>

- [<span data-ttu-id="8425b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8425b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8425b-107">您可以 **mpcmdrun.exe** 使用專用命令列工具來執行各種 Microsoft Defender 防毒軟體功能。</span><span class="sxs-lookup"><span data-stu-id="8425b-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="8425b-108">當您想要自動化 Microsoft Defender 防毒軟體使用時，此公用程式非常有用。</span><span class="sxs-lookup"><span data-stu-id="8425b-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="8425b-109">您可以在中找到該公用程式 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="8425b-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="8425b-110">您必須從命令提示字元執行它。</span><span class="sxs-lookup"><span data-stu-id="8425b-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="8425b-111">您可能需要開啟命令提示字元的系統管理員層級版本。</span><span class="sxs-lookup"><span data-stu-id="8425b-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="8425b-112">當您在 [開始] 功能表上搜尋 **命令提示** 字元時，選擇 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="8425b-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="8425b-113">如果您正在執行更新的 Microsoft Defender 平臺版本，請 `**MpCmdRun**` 從下列位置執行： `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 。</span><span class="sxs-lookup"><span data-stu-id="8425b-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="8425b-114">如需有關反惡意程式碼平臺的詳細資訊，請參閱[Microsoft Defender 防毒軟體更新和基準](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="8425b-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="8425b-115">MpCmdRun 實用程式使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8425b-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="8425b-116">以下為範例:</span><span class="sxs-lookup"><span data-stu-id="8425b-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="8425b-117">命令</span><span class="sxs-lookup"><span data-stu-id="8425b-117">Command</span></span>  | <span data-ttu-id="8425b-118">描述</span><span class="sxs-lookup"><span data-stu-id="8425b-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="8425b-119">`-?`**或**`-h`</span><span class="sxs-lookup"><span data-stu-id="8425b-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="8425b-120">顯示此工具的所有可用選項</span><span class="sxs-lookup"><span data-stu-id="8425b-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="8425b-121">掃描惡意軟體。</span><span class="sxs-lookup"><span data-stu-id="8425b-121">Scans for malicious software.</span></span> <span data-ttu-id="8425b-122">**ScanType** 的值包括：</span><span class="sxs-lookup"><span data-stu-id="8425b-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="8425b-123">根據您的設定，預設為 **0**</span><span class="sxs-lookup"><span data-stu-id="8425b-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="8425b-124">**-1** 快速掃描</span><span class="sxs-lookup"><span data-stu-id="8425b-124">**-1** Quick scan</span></span><p><span data-ttu-id="8425b-125">**-2** 完整掃描</span><span class="sxs-lookup"><span data-stu-id="8425b-125">**-2** Full scan</span></span><p><span data-ttu-id="8425b-126">**-3** 檔案與目錄自訂掃描。</span><span class="sxs-lookup"><span data-stu-id="8425b-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="8425b-127">CpuThrottling 將會服從原則設定的 CPU 節流</span><span class="sxs-lookup"><span data-stu-id="8425b-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="8425b-128">啟動診斷追蹤</span><span class="sxs-lookup"><span data-stu-id="8425b-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="8425b-129">收集支援資訊。</span><span class="sxs-lookup"><span data-stu-id="8425b-129">Collects support information.</span></span> <span data-ttu-id="8425b-130">請參閱[收集診斷資料](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="8425b-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="8425b-131">等同于 `-GetFiles` ，但輸出到暫時 DiagTrack 資料夾</span><span class="sxs-lookup"><span data-stu-id="8425b-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="8425b-132">將已安裝的安全性情報還原為先前的備份副本或原始的預設集合</span><span class="sxs-lookup"><span data-stu-id="8425b-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="8425b-133">僅移除已下載的安全性情報</span><span class="sxs-lookup"><span data-stu-id="8425b-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="8425b-134">還原先前安裝的引擎</span><span class="sxs-lookup"><span data-stu-id="8425b-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="8425b-135">檢查新的安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="8425b-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="8425b-136">還原或列出隔離的專案 (s) </span><span class="sxs-lookup"><span data-stu-id="8425b-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="8425b-137">載入動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="8425b-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="8425b-138">列出已載入的動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="8425b-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="8425b-139">移除動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="8425b-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="8425b-140">檢查是否排除路徑</span><span class="sxs-lookup"><span data-stu-id="8425b-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="8425b-141">驗證您的網路是否可以與 Microsoft Defender 防毒軟體雲端服務通訊。</span><span class="sxs-lookup"><span data-stu-id="8425b-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="8425b-142">這個命令只會在 Windows 10 版本1703或更高版本上運作。</span><span class="sxs-lookup"><span data-stu-id="8425b-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="8425b-143">透過 mpcmdrun.exe 執行命令時的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="8425b-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="8425b-144">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="8425b-144">Error message</span></span> | <span data-ttu-id="8425b-145">可能的原因</span><span class="sxs-lookup"><span data-stu-id="8425b-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="8425b-146">已停用 Microsoft Defender 防毒軟體服務。</span><span class="sxs-lookup"><span data-stu-id="8425b-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="8425b-147">請啟用服務，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="8425b-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="8425b-148">**附注：** 在 Windows 10 1909 或更舊版本，以及 Windows Server 2019 或更舊版本中，服務是用來呼叫 *Windows Defender 防毒軟體* 服務。</span><span class="sxs-lookup"><span data-stu-id="8425b-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="8425b-149">您正在 `-ValidateMapsConnection` 從 Windows 10 版本1607或更舊版本的電腦，或 Windows Server 2016 或更舊版本執行命令。</span><span class="sxs-lookup"><span data-stu-id="8425b-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="8425b-150">從 Windows 10 版本1703或更新版本的機器執行命令，或 Windows 伺服器2019或更新版本。</span><span class="sxs-lookup"><span data-stu-id="8425b-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="8425b-151">工具需要執行的來源： `%ProgramFiles%\Windows Defender` 或 `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (， `2012.4-0` 因為平臺更新是每月以外的，而不是三月份) </span><span class="sxs-lookup"><span data-stu-id="8425b-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="8425b-152">沒有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="8425b-152">Not enough privileges.</span></span> <span data-ttu-id="8425b-153">以系統管理員身分 (cmd.exe) 使用命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="8425b-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="8425b-154">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="8425b-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="8425b-155">可能的網路相關問題，例如名稱解析問題</span><span class="sxs-lookup"><span data-stu-id="8425b-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="8425b-156">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="8425b-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="8425b-157">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="8425b-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="8425b-158">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="8425b-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8425b-159">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8425b-159">See also</span></span>

- [<span data-ttu-id="8425b-160">設定 Microsoft Defender 防毒軟體功能</span><span class="sxs-lookup"><span data-stu-id="8425b-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="8425b-161">管理貴公司的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="8425b-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8425b-162">管理及設定工具的參考主題</span><span class="sxs-lookup"><span data-stu-id="8425b-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8425b-163">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="8425b-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)