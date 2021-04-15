---
title: 使用命令列來管理 Microsoft Defender 防毒程式
description: 執行 Microsoft Defender 防病毒掃描，並使用專用命令列公用程式設定下一代保護。
keywords: 執行 windows defender 掃描，從命令列執行防病毒掃描，從命令列、mpcmdrun、defender 執行 windows defender 掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764624"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="f18f8-104">使用 mpcmdrun.exe 命令列工具設定及管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="f18f8-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f18f8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f18f8-105">**Applies to:**</span></span>

- [<span data-ttu-id="f18f8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f18f8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f18f8-107">您可以使用專用命令列工具 **mpcmdrun.exe** 來執行各種 Microsoft Defender 防病毒功能。</span><span class="sxs-lookup"><span data-stu-id="f18f8-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="f18f8-108">當您想要自動化 Microsoft Defender 防病毒用途時，此公用程式非常有用。</span><span class="sxs-lookup"><span data-stu-id="f18f8-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="f18f8-109">您可以在中找到該公用程式 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="f18f8-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="f18f8-110">您必須從命令提示字元執行它。</span><span class="sxs-lookup"><span data-stu-id="f18f8-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="f18f8-111">您可能需要開啟命令提示字元的系統管理員層級版本。</span><span class="sxs-lookup"><span data-stu-id="f18f8-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="f18f8-112">當您在 [開始] 功能表上搜尋 **命令提示** 字元時，選擇 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="f18f8-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="f18f8-113">如果您正在執行更新的 Microsoft Defender 平臺版本，請 `**MpCmdRun**` 從下列位置執行： `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 。</span><span class="sxs-lookup"><span data-stu-id="f18f8-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="f18f8-114">公用程式包含下列命令：</span><span class="sxs-lookup"><span data-stu-id="f18f8-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="f18f8-115">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="f18f8-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="f18f8-116">命令</span><span class="sxs-lookup"><span data-stu-id="f18f8-116">Command</span></span>  | <span data-ttu-id="f18f8-117">描述</span><span class="sxs-lookup"><span data-stu-id="f18f8-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="f18f8-118">`-?`**或**`-h`</span><span class="sxs-lookup"><span data-stu-id="f18f8-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="f18f8-119">顯示此工具的所有可用選項</span><span class="sxs-lookup"><span data-stu-id="f18f8-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="f18f8-120">掃描惡意軟體。</span><span class="sxs-lookup"><span data-stu-id="f18f8-120">Scans for malicious software.</span></span> <span data-ttu-id="f18f8-121">**ScanType** 的值為： **0** 預設值，取決於您的設定、 **-1 個** 快速掃描、 **-2** 個完整掃描、 **-3** 檔及目錄自訂掃描。</span><span class="sxs-lookup"><span data-stu-id="f18f8-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="f18f8-122">CpuThrottling 將會服從原則設定的 CPU 節流</span><span class="sxs-lookup"><span data-stu-id="f18f8-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="f18f8-123">啟動診斷追蹤</span><span class="sxs-lookup"><span data-stu-id="f18f8-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="f18f8-124">收集支援資訊。</span><span class="sxs-lookup"><span data-stu-id="f18f8-124">Collects support information.</span></span> <span data-ttu-id="f18f8-125">請參閱[收集診斷資料](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="f18f8-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="f18f8-126">等同于 `-GetFiles` ，但輸出到暫時 DiagTrack 資料夾</span><span class="sxs-lookup"><span data-stu-id="f18f8-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="f18f8-127">將已安裝的安全性情報還原為先前的備份副本或原始的預設集合</span><span class="sxs-lookup"><span data-stu-id="f18f8-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="f18f8-128">僅移除已下載的安全性情報</span><span class="sxs-lookup"><span data-stu-id="f18f8-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="f18f8-129">還原先前安裝的引擎</span><span class="sxs-lookup"><span data-stu-id="f18f8-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="f18f8-130">檢查新的安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="f18f8-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="f18f8-131">還原或列出隔離的專案 (s) </span><span class="sxs-lookup"><span data-stu-id="f18f8-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="f18f8-132">載入動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="f18f8-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="f18f8-133">列出已載入的動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="f18f8-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="f18f8-134">移除動態安全性情報</span><span class="sxs-lookup"><span data-stu-id="f18f8-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="f18f8-135">檢查是否排除路徑</span><span class="sxs-lookup"><span data-stu-id="f18f8-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="f18f8-136">驗證您的網路是否可以與 Microsoft Defender 防毒軟體雲端服務通訊。</span><span class="sxs-lookup"><span data-stu-id="f18f8-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="f18f8-137">這個命令只會在 Windows 10、版本1703或更高版本上運作。</span><span class="sxs-lookup"><span data-stu-id="f18f8-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="f18f8-138">透過 mpcmdrun.exe 執行命令時的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="f18f8-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="f18f8-139">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="f18f8-139">Error message</span></span> | <span data-ttu-id="f18f8-140">可能的原因</span><span class="sxs-lookup"><span data-stu-id="f18f8-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="f18f8-141">已停用 Microsoft Defender 防病毒服務。</span><span class="sxs-lookup"><span data-stu-id="f18f8-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="f18f8-142">請啟用服務，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="f18f8-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="f18f8-143">**附注：**  在 Windows 10 1909 或更舊版本，以及 Windows Server 2019 或更舊版本中，服務是用來稱為「Windows Defender 防毒程式」服務。</span><span class="sxs-lookup"><span data-stu-id="f18f8-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="f18f8-144">您 `-ValidateMapsConnection` 執行的是 windows 10 版本1607或更舊版本的電腦上的命令，或者是 Windows Server 2016 或更舊版本。</span><span class="sxs-lookup"><span data-stu-id="f18f8-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="f18f8-145">從 Windows 10 版本1703或更新版本的機器或 Windows Server 2019 或更新版本執行命令。</span><span class="sxs-lookup"><span data-stu-id="f18f8-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="f18f8-146">工具需要執行的來源： `%ProgramFiles%\Windows Defender` 或 `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (， `2012.4-0` 因為平臺更新是每月以外的，而不是三月份) </span><span class="sxs-lookup"><span data-stu-id="f18f8-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="f18f8-147">沒有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="f18f8-147">Not enough privileges.</span></span> <span data-ttu-id="f18f8-148">以系統管理員身分 (cmd.exe) 使用命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="f18f8-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="f18f8-149">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="f18f8-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="f18f8-150">可能的網路相關問題，例如名稱解析問題</span><span class="sxs-lookup"><span data-stu-id="f18f8-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="f18f8-151">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="f18f8-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="f18f8-152">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="f18f8-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="f18f8-153">防火牆會封鎖連接或進行 SSL 檢查。</span><span class="sxs-lookup"><span data-stu-id="f18f8-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f18f8-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f18f8-154">See also</span></span>

- [<span data-ttu-id="f18f8-155">設定 Microsoft Defender 防病毒功能</span><span class="sxs-lookup"><span data-stu-id="f18f8-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="f18f8-156">管理企業中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="f18f8-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f18f8-157">管理及設定工具的參考主題</span><span class="sxs-lookup"><span data-stu-id="f18f8-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f18f8-158">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="f18f8-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)