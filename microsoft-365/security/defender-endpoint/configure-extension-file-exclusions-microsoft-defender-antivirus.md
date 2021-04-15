---
title: 根據副檔名、名稱或位置來設定及驗證排除
description: 根據檔案副檔名、檔案名或位置排除來自 Microsoft Defender 防病毒掃描的檔案。
keywords: 排除專案、檔、副檔名、檔案類型、資料夾名稱、檔案名、掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 338dc249bcd4e092f5a2be39e3d045d094ed957a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765212"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>根據副檔名和資料夾位置，設定及驗證排除

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Microsoft Defender 防病毒排除不會套用至其他 Microsoft Defender for Endpoint 功能，包括 [端點偵測和回應 (EDR) ](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)、 [攻擊面減少 (ASR) 規則](/microsoft-365/security/defender-endpoint/attack-surface-reduction)，以及 [受控制的資料夾存取](/microsoft-365/security/defender-endpoint/controlled-folders)。 使用本文所述方法排除的檔案，仍然可以觸發 EDR 警示及其他偵測。 若要排除廣泛的檔案，請將其新增至 Microsoft Defender for Endpoint [自訂指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。

## <a name="exclusion-lists"></a>排除清單

您可以修改排除清單，以排除 Microsoft Defender 防病毒掃描中的某些檔案。 **一般來說，您不需要套用排除**。 Microsoft Defender 防毒軟體會根據已知的作業系統行為和一般管理檔案（例如企業管理、資料庫管理及其他企業案例及案例中所使用的管理檔案），包含許多自動排除。

> [!NOTE]
> 例外狀況也適用于可能有害的應用程式 (PUA) 偵測。

> [!NOTE]
> 自動排除只適用于 Windows Server 2016 和更新版本。 在 Windows 安全性應用程式和 PowerShell 中看不到這些排除專案。

本文說明如何設定檔案和資料夾的排除清單。 定義排除清單之前，請參閱定義排除專案 [的建議](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 。

| 排除 | 範例 | 排除清單 |
|:---|:---|:---|
|具有特定副檔名的任何檔案 | 電腦上任何位置具有指定副檔名的所有檔案。 <p> 有效語法： `.test` 和 `test`  | 副檔名排除 |
|特定資料夾底下的任何檔案 | 資料夾底下的所有檔案 `c:\test\sample` | 檔案與資料夾排除 |
| 特定資料夾中的特定檔案 | 僅檔案 `c:\sample\sample.test` | 檔案與資料夾排除 |
| 特定進程 | 可執行檔 `c:\test\process.exe` | 檔案與資料夾排除 |

排除清單具有下列特性：

- 除非子資料夾是重新分析點，否則資料夾排除會套用到該資料夾底下的所有檔案和資料夾。 重新分析點必須個別排除子資料夾。
- 副檔名若未定義路徑或資料夾，則會套用至具有定義副檔名的任何檔案名。

> [!IMPORTANT]
> - 使用萬用字元（如星號 (\*) ）將會變更如何轉譯排除規則。 如需有關萬用字元如何運作的重要資訊，請參閱在檔案名 [和資料夾路徑或副檔名排除清單區段中使用萬用字元](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。
> - 您無法排除對應的網路磁碟機。 您必須指定實際的網路路徑。
> - 在 Microsoft Defender 防病毒服務啟動之後所建立並已新增至排除清單的重新分析點，將不會包含在其中的資料夾。 您必須重新開機 Windows) 以重新開機服務 (，以將新重新分析點識別為有效的排除目標。

若要排除特定程式所開啟的檔案，請參閱 [Configure and validate 由進程開啟的檔案排除](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)專案。

[排除] 適用于 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [隨選掃描](run-scan-microsoft-defender-antivirus.md)和 [即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)。

> [!IMPORTANT]
> 使用「群組原則」所做的排除清單變更 **會顯示** 在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)的清單中。
> 在 Windows 安全性應用程式中所做的變更 **將不會顯示** 在 [群組原則] 清單中。

根據預設，具有系統管理員許可權之使用者所做之 (清單的本機變更（包括 PowerShell 與 WMI) 所做的變更）會與清單一起合併，如定義 (及) 群組原則、Configuration Manager 或 Intune 部署。 當發生衝突時，群組原則清單會優先。

您可以 [設定如何合併本機和全域定義的排除清單](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) ，以允許本機變更覆寫受管理的部署設定。

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>根據資料夾名稱或副檔名設定排除清單

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Intune 設定檔案名、資料夾或副檔名排除專案

請參閱下列文章：
- [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)
- [Intune 中 Windows 10 版的 Microsoft Defender 防病毒裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Configuration Manager 來設定檔案名、資料夾或副檔名排除

請參閱 [如何建立及部署反惡意程式碼原則：有關設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft 端點管理員 (目前分支) 的詳細資訊，請參閱 [排除] 設定。

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>使用群組原則來設定資料夾或副檔名排除

>[!NOTE]
>如果您指定檔案的完整路徑，則只會排除該檔案。 如果在排除中定義資料夾，則會排除該資料夾下的所有檔案和子目錄。

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。

3. 將樹狀目錄展開為  >  **microsoft Defender 防病毒**  >  **排除** 專案的 Windows 元件。

4. 開啟 [ **路徑排除** ] 設定進行編輯，然後新增您的排除專案。

    1. 將選項設定為 [ **啟用**]。
    1. 在 [ **選項** ] 區段中，按一下 [ **顯示**]。
    1. 在 [ **值名稱** ] 欄中，指定各自列的每一個資料夾。
    1. 如果您指定的是檔案，請確定您輸入的是完整的檔案路徑，包含磁碟機號、資料夾路徑、檔案名及副檔名。 在 [**值**] 欄中輸入 **0** 。

5. 選擇 [確定]。

6. 開啟 [ **副檔名排除** ] 設定以進行編輯，並新增您的排除專案。

    1. 將選項設定為 [ **啟用**]。
    1. 在 [ **選項** ] 區段中，選取 [ **顯示**]。
    1. 在 [ **值名稱** ] 欄底下的獨佔行中輸入每個副檔名。  在 [**值**] 欄中輸入 **0** 。

7. 選擇 [確定]。

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 PowerShell Cmdlet 來設定檔案名、資料夾或副檔名排除

使用 PowerShell 若要新增或移除以副檔名、位置或檔案名為基礎的檔案排除，需要使用三個 Cmdlet 及適當的排除清單參數的組合。 Cmdlet 全都位於 [Defender 模組](/powershell/module/defender/)中。

Cmdlet 的格式如下：

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

下列專案是允許的 `<cmdlet>` ：

| 設定動作 | PowerShell Cmdlet |
|:---|:---|
|建立或覆寫清單 | `Set-MpPreference` |
|新增至清單 | `Add-MpPreference` |
|從清單中移除專案 | `Remove-MpPreference` |

下列專案是允許的 `<exclusion list>` ：

| 排除類型 | PowerShell 參數 |
|:---|:---|
| 具有指定副檔名的所有檔案 | `-ExclusionExtension` |
| 資料夾下的所有檔案 (包括子目錄) 中的檔案，或特定檔案的檔 | `-ExclusionPath` |

> [!IMPORTANT]
> 如果您已建立清單，請使用 `Set-MpPreference` 或 `Add-MpPreference` 再次使用 Cmdlet， `Set-MpPreference` 將覆寫現有清單。

例如，下列程式碼片段會使 Microsoft Defender 防病毒掃描排除副檔名為下列的任何檔案 `.test` ：

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

如需詳細資訊，請參閱 [Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Windows Management 指令 (WMI) 設定檔案名、資料夾或副檔名排除專案

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set**、 **Add** 和 **Remove** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ExclusionExtension
ExclusionPath
```

[ **設定**]、[ **新增**] 和 [ **移除** ] 的使用與其在 PowerShell:、] 和中的對等專案類似 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 。

如需詳細資訊，請參閱 [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>使用 Windows 安全性應用程式來設定檔案名、資料夾或副檔名排除

如需相關指示，請參閱 [在 Windows 安全性應用程式中新增排除](microsoft-defender-security-center-antivirus.md) 專案。

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元

在 `*` `?` 定義檔案名或資料夾路徑排除清單中的專案時，可以使用星號、問號或環境變數 (例如 `%ALLUSERSPROFILE%`) 做為萬用字元。 這些萬用字元的轉譯方式，與其他應用程式和語言中的一般使用方式不同。 請務必閱讀本節，以瞭解其特定限制。

> [!IMPORTANT]
> 這些萬用字元有主要限制和使用案例：
> - 環境變數的使用方式限制為電腦變數，以及適用于執行為 NT AUTHORITY\SYSTEM 帳戶的進程的變數。
> - 您無法使用萬用字元取代磁碟機號。
> - `*`資料夾排除中的星號會代替單一資料夾。 使用多個實例 `\*\` 來表示多個嵌套資料夾具有未指定的名稱。

下表說明如何使用萬用字元，並提供一些範例。


|萬用字元  |範例  |
|:---------|:---------|
|`*` (星號)  <p> 在 [檔案名] **和 [副檔名** 包含] 中，星號會取代任何數目的字元，而且只適用于引數中定義的最後一個資料夾中的檔案。 <p> 在 **資料夾排除** 中，星號會取代單一資料夾。 使用多個搭配 `*` 資料夾斜線 `\` 表示多個嵌套資料夾。 在比對萬用字元 carded 及命名資料夾的數目之後，也會包含所有子資料夾。   | `C:\MyData\*.txt` 包括 `C:\MyData\notes.txt` <p> `C:\somepath\*\Data`包含位於及其 `C:\somepath\Archives\Data` 子資料夾及其子資料夾中的任何檔案 `C:\somepath\Authorized\Data` <p> `C:\Serv\*\*\Backup`包含位於及其 `C:\Serv\Primary\Denied\Backup` 子資料夾及其子資料夾中的任何檔案 `C:\Serv\Secondary\Allowed\Backup`     |
|`?` (問號)   <p> 在 [檔案名] **和 [副檔名** 包含] 中，問號會取代單一字元，而且只適用于引數中所定義之最後一個資料夾中的檔案。 <p> 在 [ **資料夾排除**] 中，問號會取代資料夾名稱中的單一字元。 在比對萬用字元 carded 及命名資料夾的數目之後，也會包含所有子資料夾。   |`C:\MyData\my?.zip` 包括 `C:\MyData\my1.zip` <p> `C:\somepath\?\Data`包含位於及其子資料夾中的任何檔案 `C:\somepath\P\Data`  <p> `C:\somepath\test0?\Data` 會包含任何位於 `C:\somepath\test01\Data` 及其子資料夾中的檔案          |
|環境變數 <p> 在評估排除時，已定義的變數會填入為路徑。          |`%ALLUSERSPROFILE%\CustomLogFiles` 會包含 `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`         |
        

> [!IMPORTANT]
> 如果您混合使用資料夾排除引數的檔案排除引數，則規則會在符合資料夾中的檔案引數相符時停止，而且不會在任何子資料夾中尋找檔的相符性。
> 例如，您可以在資料夾中排除以 "date" 開頭的所有檔案 `c:\data\final\marked` ，並 `c:\data\review\marked` 使用 rule 引數 `c:\data\*\marked\date*` 。
> 不過，此引數不會符合或的子資料夾中的任何檔案 `c:\data\final\marked` `c:\data\review\marked` 。

<a id="review"></a>

### <a name="system-environment-variables"></a>系統內容變數

下表列出並說明系統帳戶環境變數。 

| 這個系統內容變數 .。。 | 重新導向至此 |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | C:\ProgramData\Start Menu\Programs |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a>審閱排除清單

您可以使用下列其中一種方法，在排除清單中取得專案：
- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
>使用「群組原則」所做的排除清單變更 **會顯示** 在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)的清單中。
>
>在 Windows 安全性應用程式中所做的變更 **將不會顯示** 在 [群組原則] 清單中。

如果您使用 PowerShell，您可以使用下列兩種方式來找回清單：

- 取得所有 Microsoft Defender 防毒軟體偏好設定的狀態。 每個清單都顯示在不同的行上，但是每個清單中的專案會組合成同一行。
- 將所有喜好設定的狀態寫入變數中，並使用該變數只呼叫您感興趣的特定清單。 每次使用 `Add-MpPreference` 都會寫入新行。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>使用 MpCmdRun 驗證排除清單

若要使用專用 [命令列工具 mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)檢查排除，請使用下列命令：

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
>使用 MpCmdRun 檢查排除專案時，需要 Microsoft Defender 防病毒預約通話版本 4.18.1812.3 (于十二月 2018) 或更新版本發行。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>使用 PowerShell 查看排除清單及所有其他 Microsoft Defender 防病毒偏好設定

請使用下列 Cmdlet：

```PowerShell
Get-MpPreference
```

在下列範例中，會將清單中包含的專案反 `ExclusionExtension` 白顯示：

![Get-MpPreference 的 PowerShell 輸出，顯示排除清單及其他喜好設定](images/defender/wdav-powershell-get-exclusions-all.png)

如需詳細資訊，請參閱 [Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlet](/powershell/module/defender/)。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>使用 PowerShell 來檢索特定排除清單

使用下列程式碼片段 (將每一行輸入為個別的命令) ;以您想要命名變數的任何標籤取代 **WDAVprefs** ：

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

在下列範例中，會將清單分割為每次使用 Cmdlet 的新行 `Add-MpPreference` ：

![PowerShell 輸出僅顯示排除清單中的專案](images/defender/wdav-powershell-get-exclusions-variable.png)

如需詳細資訊，請參閱 [Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlet](/powershell/module/defender/)。

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>使用 EICAR.TXT 測試檔案驗證排除清單

您可以使用 Cmdlet 或 .NET WebClient 類別的 PowerShell，驗證您的排除清單是否正常運作 `Invoke-WebRequest` ，以下載測試檔案。

在下列 PowerShell 片段中，將 *test.txt* 取代為符合您的排除規則的檔案。 例如，如果您已排除該 `.testing` 副檔名，請將其取代 `test.txt` `test.testing` 。 若要測試路徑，請確定您在該路徑內執行 Cmdlet。

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

如果 Microsoft Defender 防病毒報告惡意程式碼，則規則不會正常運作。 如果沒有惡意軟體的報表，而且下載的檔案存在，則排除作業正常運作。 您可以開啟檔案，確認內容與 [eicar.txt test file 網站](http://www.eicar.org/86-0-Intended-use.html)上所述的內容相同。

您也可以使用下列 PowerShell 程式碼，它會呼叫 .NET WebClient 類別以下載測試檔-如 Cmdlet 所示 `Invoke-WebRequest` ; 將 *c:\test.txt* 取代為符合您所驗證之規則的檔案：

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

如果您沒有網際網路存取權，您可以使用下列 PowerShell 命令，將 EICAR.TXT 字串寫入新的文字檔，以建立您自己的 EICAR.TXT 測試檔案：

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

您也可以將字串複製到空白的文字檔中，並嘗試使用檔案名或您嘗試排除的資料夾來儲存。

## <a name="related-topics"></a>相關主題

- [設定及驗證 Microsoft Defender 防病毒掃描中的排除專案](configure-exclusions-microsoft-defender-antivirus.md)
- [設定及驗證由進程開啟之檔案的排除專案](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [設定 Windows Server 上的 Microsoft Defender 防病毒排除](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定義排除時所避免的常見錯誤](common-exclusion-mistakes-microsoft-defender-antivirus.md)
