---
title: 定義排除時應避免的常見錯誤
description: 在為 Microsoft Defender 防毒軟體掃描定義排除項時，請避免常見的錯誤。
keywords: 排除專案、檔、副檔名、檔案類型、資料夾名稱、檔案名、掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950128"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>定義排除時應避免的常見錯誤

您可以為不想 Microsoft Defender 防毒軟體掃描的專案定義排除清單。 這類排除的專案可能包含使您的裝置受到攻擊的威脅。 本文說明在定義排除時，應避免的常見錯誤。 

在定義您的排除清單之前，請參閱[建議以定義排除](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)專案。

## <a name="excluding-certain-trusted-items"></a>排除特定信任專案

某些檔案、檔案類型、資料夾或進程不應該從掃描中排除，即使您信任這些檔案不是惡意的。 

請勿為下列各節所列的資料夾位置、副檔名及程式定義排除專案：
- 資料夾位置
- 副檔名
- 過程

### <a name="folder-locations"></a>資料夾位置

一般而言，請勿為下列資料夾位置定義排除專案：

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**請注意，SharePoint 的下列例外** 狀況： `C:\Users\ServiceAccount\AppData\Local\Temp` 當您 [在 SharePoint 中使用檔層級防防毒保護](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)時，請排除此項。

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**請注意，SharePoint 的下列例外** 狀況： `C:\Users\Default\AppData\Local\Temp` 當您 [在 SharePoint 中使用檔層級防防毒保護](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)時，請排除此項。

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a>副檔名

一般而言，請勿為下列副檔名定義排除專案：

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>過程 

一般而言，請勿為下列程式定義排除專案：

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`

`dotnet.exe`

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> 您可以選擇排除檔案類型，例如，， `.gif` `.jpg` `.jpeg` 或 `.png` 如果您的環境具有可處理任何漏洞之嚴格更新原則的新式軟體。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>在排除清單中只使用檔案名

惡意程式碼可能會與您信任且要從掃描中排除的檔案名具有相同的名稱。 因此，若要避免從掃描中排除潛在的惡意程式碼，請在您想要排除的檔案上使用完整路徑，而不只是使用檔案名。 例如，如果您想要從掃描中排除，請使用檔案的 `Filename.exe` 完整路徑，例如 `C:\program files\contoso\Filename.exe` 。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>針對多個伺服器工作負載使用單一排除清單

請勿使用單一排除清單來定義多個伺服器工作負載的排除專案。 將不同應用程式或服務工作負載的排除項分割成多個排除清單。 例如，您的 IIS 伺服器工作負載的排除清單必須不同于 SQL Server 工作量的排除清單。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在檔案名和資料夾路徑或副檔名排除清單中使用不正確的環境變數做為萬用字元

Microsoft Defender 防毒軟體服務會使用 LocalSystem 帳戶在系統內容中執行，這表示它會從系統內容變數中取得資訊，而不是從使用者環境變數取得資訊。 使用環境變數做為排除清單中的萬用字元時，會限制為系統變數，以及適用于以 NT AUTHORITY\SYSTEM 帳戶執行之進程的變數。 因此，新增 Microsoft Defender 防毒軟體資料夾與處理常式排除時，請勿使用使用者環境變數做為萬用字元。 請參閱 [系統內容變數](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 底下的表格，以取得系統內容變數的完整清單。

如需如何在排除清單中使用萬用字元的詳細資訊，請參閱在 [檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。

