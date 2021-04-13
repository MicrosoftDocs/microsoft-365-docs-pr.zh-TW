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
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>定義排除時所避免的常見錯誤

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

您可以為不想要 Microsoft Defender 防病毒掃描的專案定義排除清單。 這類排除的專案可能包含使您的裝置受到攻擊的威脅。 

本文說明在定義排除時，應避免的常見錯誤。 

在定義您的排除清單之前，請參閱 [定義排除專案的建議](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。

## <a name="excluding-certain-trusted-items"></a>排除特定信任專案

某些檔案、檔案類型、資料夾或進程不應該從掃描中排除，即使您信任這些檔案不是惡意的。 

請不要為下清單格所列的資料夾位置、副檔名及程式定義排除專案：

| 資料夾位置 | 副檔名 | 過程 |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`1 <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`第 <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> 您可以選擇排除檔案類型，例如，， `.gif` `.jpg` `.jpeg` 或 `.png` 如果您的環境具有可處理任何漏洞之嚴格更新原則的新式軟體。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>在排除清單中只使用檔案名

惡意程式碼可能會與您信任且要從掃描中排除的檔案名具有相同的名稱。 因此，若要避免從掃描中排除潛在的惡意程式碼，請在您想要排除的檔案上使用完整路徑，而不只是使用檔案名。 例如，如果您想要從掃描中排除，請使用檔案的 `Filename.exe` 完整路徑，例如 `C:\program files\contoso\Filename.exe` 。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>針對多個伺服器工作負載使用單一排除清單

請勿使用單一排除清單來定義多個伺服器工作負載的排除專案。 將不同應用程式或服務工作負載的排除項分割成多個排除清單。 例如，您的 IIS 伺服器工作負載的排除清單必須不同于 SQL Server 工作負載的排除清單。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在檔案名和資料夾路徑或副檔名排除清單中使用不正確的環境變數做為萬用字元

Microsoft Defender 防病毒服務會使用 LocalSystem 帳戶在系統內容中執行，這表示它會從系統內容變數，而不是從使用者環境變數中取得資訊。 使用環境變數做為排除清單中的萬用字元時，會限制為系統變數，以及適用于以 NT AUTHORITY\SYSTEM 帳戶執行之進程的變數。 因此，在新增 Microsoft Defender 防病毒資料夾及程式排除時，請勿使用使用者環境變數做為萬用字元。 請參閱 [系統內容變數](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 底下的表格，以取得系統內容變數的完整清單。

如需如何在排除清單中使用萬用字元的詳細資訊，請參閱在 [檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。

## <a name="related-articles"></a>相關文章

- [設定及驗證 Microsoft Defender 防病毒掃描中的排除專案](configure-exclusions-microsoft-defender-antivirus.md)
- [根據副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [設定及驗證由進程開啟之檔案的排除專案](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [設定 Windows Server 上的 Microsoft Defender 防病毒排除](configure-server-exclusions-microsoft-defender-antivirus.md)
