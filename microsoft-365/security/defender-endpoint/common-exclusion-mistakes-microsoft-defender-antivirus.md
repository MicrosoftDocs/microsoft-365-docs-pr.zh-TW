---
title: 定義排除時所避免的常見錯誤
description: 在定義 Microsoft Defender 防病毒掃描的排除專案時，請避免常見的錯誤。
keywords: 排除專案、檔、副檔名、檔案類型、資料夾名稱、檔案名、掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d14e37c8f3cfdfe8d88bfd4e255a431fbb8d6d41
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690126"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="a6982-104">定義排除時所避免的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="a6982-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6982-105">您可以為不想要 Microsoft Defender 防病毒掃描的專案定義排除清單。</span><span class="sxs-lookup"><span data-stu-id="a6982-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="a6982-106">這類排除的專案可能包含使您的裝置受到攻擊的威脅。</span><span class="sxs-lookup"><span data-stu-id="a6982-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="a6982-107">本文說明在定義排除時，應避免的常見錯誤。</span><span class="sxs-lookup"><span data-stu-id="a6982-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="a6982-108">在定義您的排除清單之前，請參閱 [定義排除專案的建議](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="a6982-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="a6982-109">排除特定信任專案</span><span class="sxs-lookup"><span data-stu-id="a6982-109">Excluding certain trusted items</span></span>

<span data-ttu-id="a6982-110">某些檔案、檔案類型、資料夾或進程不應該從掃描中排除，即使您信任這些檔案不是惡意的。</span><span class="sxs-lookup"><span data-stu-id="a6982-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="a6982-111">請不要為下清單格所列的資料夾位置、副檔名及程式定義排除專案：</span><span class="sxs-lookup"><span data-stu-id="a6982-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following table:</span></span>

| <span data-ttu-id="a6982-112">資料夾位置</span><span class="sxs-lookup"><span data-stu-id="a6982-112">Folder locations</span></span> | <span data-ttu-id="a6982-113">副檔名</span><span class="sxs-lookup"><span data-stu-id="a6982-113">File extensions</span></span> | <span data-ttu-id="a6982-114">過程</span><span class="sxs-lookup"><span data-stu-id="a6982-114">Processes</span></span> |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> <span data-ttu-id="a6982-115">`bginfo.exe`1</span><span class="sxs-lookup"><span data-stu-id="a6982-115">`bginfo.exe`[1]</span></span> <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> <span data-ttu-id="a6982-116">`msbuild.exe`第</span><span class="sxs-lookup"><span data-stu-id="a6982-116">`msbuild.exe`[2]</span></span> <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> <span data-ttu-id="a6982-117">您可以選擇排除檔案類型，例如，， `.gif` `.jpg` `.jpeg` 或 `.png` 如果您的環境具有可處理任何漏洞之嚴格更新原則的新式軟體。</span><span class="sxs-lookup"><span data-stu-id="a6982-117">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="a6982-118">在排除清單中只使用檔案名</span><span class="sxs-lookup"><span data-stu-id="a6982-118">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="a6982-119">惡意程式碼可能會與您信任且要從掃描中排除的檔案名具有相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="a6982-119">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="a6982-120">因此，若要避免從掃描中排除潛在的惡意程式碼，請在您想要排除的檔案上使用完整路徑，而不只是使用檔案名。</span><span class="sxs-lookup"><span data-stu-id="a6982-120">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="a6982-121">例如，如果您想要從掃描中排除，請使用檔案的 `Filename.exe` 完整路徑，例如 `C:\program files\contoso\Filename.exe` 。</span><span class="sxs-lookup"><span data-stu-id="a6982-121">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="a6982-122">針對多個伺服器工作負載使用單一排除清單</span><span class="sxs-lookup"><span data-stu-id="a6982-122">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="a6982-123">請勿使用單一排除清單來定義多個伺服器工作負載的排除專案。</span><span class="sxs-lookup"><span data-stu-id="a6982-123">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="a6982-124">將不同應用程式或服務工作負載的排除項分割成多個排除清單。</span><span class="sxs-lookup"><span data-stu-id="a6982-124">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="a6982-125">例如，您的 IIS 伺服器工作負載的排除清單必須不同于 SQL Server 工作負載的排除清單。</span><span class="sxs-lookup"><span data-stu-id="a6982-125">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="a6982-126">在檔案名和資料夾路徑或副檔名排除清單中使用不正確的環境變數做為萬用字元</span><span class="sxs-lookup"><span data-stu-id="a6982-126">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="a6982-127">Microsoft Defender 防病毒服務會使用 LocalSystem 帳戶在系統內容中執行，這表示它會從系統內容變數，而不是從使用者環境變數中取得資訊。</span><span class="sxs-lookup"><span data-stu-id="a6982-127">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="a6982-128">使用環境變數做為排除清單中的萬用字元時，會限制為系統變數，以及適用于以 NT AUTHORITY\SYSTEM 帳戶執行之進程的變數。</span><span class="sxs-lookup"><span data-stu-id="a6982-128">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="a6982-129">因此，在新增 Microsoft Defender 防病毒資料夾及程式排除時，請勿使用使用者環境變數做為萬用字元。</span><span class="sxs-lookup"><span data-stu-id="a6982-129">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="a6982-130">請參閱 [系統內容變數](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 底下的表格，以取得系統內容變數的完整清單。</span><span class="sxs-lookup"><span data-stu-id="a6982-130">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="a6982-131">如需如何在排除清單中使用萬用字元的詳細資訊，請參閱在 [檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。</span><span class="sxs-lookup"><span data-stu-id="a6982-131">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a6982-132">相關文章</span><span class="sxs-lookup"><span data-stu-id="a6982-132">Related articles</span></span>

- [<span data-ttu-id="a6982-133">設定及驗證 Microsoft Defender 防病毒掃描中的排除專案</span><span class="sxs-lookup"><span data-stu-id="a6982-133">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6982-134">根據副檔名和資料夾位置，設定及驗證排除</span><span class="sxs-lookup"><span data-stu-id="a6982-134">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6982-135">設定及驗證由進程開啟之檔案的排除專案</span><span class="sxs-lookup"><span data-stu-id="a6982-135">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6982-136">設定 Windows Server 上的 Microsoft Defender 防病毒排除</span><span class="sxs-lookup"><span data-stu-id="a6982-136">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
