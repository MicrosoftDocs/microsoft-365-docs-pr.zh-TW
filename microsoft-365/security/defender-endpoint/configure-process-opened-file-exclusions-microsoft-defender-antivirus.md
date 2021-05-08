---
title: 設定特定進程開啟之檔案的排除專案
description: 您可以從掃描中排除檔案（如果這些檔案已由特定進程開啟）。
keywords: Microsoft Defender 防毒程式、處理常式、排除、檔案、掃描
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
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274603"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>設定處理常式開啟之檔案的排除專案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以從 Microsoft Defender 防病毒掃描中排除特定進程已開啟的檔案。 定義排除清單之前，請參閱定義排除專案 [的建議](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 。

本文說明如何設定排除清單。 

## <a name="examples-of-exclusions"></a>排除的範例

|排除 | 範例 |
|---|---|
|電腦上任何具有特定檔案名之進程所開啟的檔案 | 指定 `test.exe` 會排除以下列方式開啟的檔案： <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|電腦上的任何檔案，由特定資料夾下的任何處理程式開啟 | 指定 `c:\test\sample\*` 會排除以下列方式開啟的檔案：<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|電腦上特定資料夾中特定進程所開啟的任何檔案 | 指定 `c:\test\process.exe` 會排除只開啟的檔案 `c:\test\process.exe` |


當您將程式新增至程式排除清單時，不論檔案位於何處，Microsoft Defender 防毒軟體都會掃描該程式所開啟的檔案。 不過，系統會先掃描此程式，除非該程式也已新增至 [檔排除清單](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

[排除] 只適用于 [永不間斷的即時保護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)。 它們不適用於排程或隨選的掃描。

使用群組原則對排除清單所做的變更， **會顯示** 在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)的清單中。 不過，在 Windows 安全性應用程式中所做的變更 **將不會顯示** 在 [群組原則] 清單中。

您可以在群組原則、Microsoft Endpoint Configuration 管理員、Microsoft Intune 及 Windows 安全性應用程式中新增、移除及檢查排除專案的清單，也可以使用萬用字元進一步自訂清單。

您也可以使用 PowerShell Cmdlet 和 WMI 來設定排除清單，包括複查清單。

依預設，具有系統管理員許可權之使用者 (清單的本機變更;使用 PowerShell 和 WMI) 所做的變更，會隨著群組原則、設定管理員或 Intune 的定義 (和部署) ，與清單合併。 群組原則清單會在衝突的情況下優先。

您可以 [設定如何合併本機和全域定義的排除清單](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) ，以允許本機變更覆寫受管理的部署設定。

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>針對由指定的程式開啟的檔案，設定排除清單

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 Microsoft Intune 排除已由指定的程式從掃描開啟的檔案

如需詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure) 及 [Intune 中 Windows 10 的 Microsoft Defender 防病毒裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 。

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 Microsoft 端點管理員排除已由指定的進程從掃描中開啟的檔案

請參閱 [如何建立及部署反惡意程式碼原則：有關設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft 端點管理員 (目前分支) 的詳細資訊，請參閱 [排除] 設定。

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用群組原則來排除已由指定的進程從掃描開啟的檔案

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

3. 在 **Microsoft Defender 防病毒 > 排除 >**，展開樹狀目錄至 Windows 元件。

4. 按兩下 [ **處理常式排除** ]，並新增排除專案：

    1. 將選項設定為 [ **啟用**]。
    2. 在 [ **選項** ] 區段中，按一下 [ **顯示 ...**]。
    3. 在 [ **值名稱** ] 欄底下，于各自的行上輸入每個程式。 請參閱範例表格，以瞭解不同的程式排除類型。  在 [**值**] 欄中輸入 [所有處理常式] 的 [ **0** ]。

5. 按一下 ****[確定]。

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 PowerShell Cmdlet 來排除已由指定的進程從掃描開啟的檔案

使用 PowerShell 新增或移除已由進程開啟之檔案的排除專案時，需要使用三個 Cmdlet 搭配 `-ExclusionProcess` 參數。 Cmdlet 全都位於 [Defender 模組](/powershell/module/defender/)中。

Cmdlet 的格式為：

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

下列專案是允許的 \<cmdlet> ：

|設定動作 | PowerShell Cmdlet |
|---|---|
|建立或覆寫清單 | `Set-MpPreference` |
|新增至清單 | `Add-MpPreference` |
|從清單中移除專案 | `Remove-MpPreference` |

>[!IMPORTANT]
>如果您已建立清單，請使用 `Set-MpPreference` 或 `Add-MpPreference` 再次使用 Cmdlet， `Set-MpPreference` 將覆寫現有清單。

例如，下列程式碼段會導致 Microsoft Defender AV 掃描排除指定程式所開啟的任何檔案：

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

如需如何將 PowerShell 與 Microsoft Defender 防毒軟體搭配使用的詳細資訊，請參閱使用 PowerShell Cmdlet 和 [Microsoft Defender 防病毒 Cmdlet](/powershell/module/defender)管理防病毒。

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 Windows Management 指令 (WMI) ，以排除已由指定的進程從掃描開啟的檔案

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set**、 **Add** 和 **Remove** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ExclusionProcess
```

[ **設定**]、[ **新增**] 和 [ **移除** ] 的使用與其在 PowerShell:、] 和中的對等專案類似 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 。

如需詳細資訊及允許的參數，請參閱  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>使用 Windows 安全性應用程式排除已由指定的進程從掃描開啟的檔案

如需相關指示，請參閱 [在 Windows 安全性應用程式中新增排除](microsoft-defender-security-center-antivirus.md) 專案。

## <a name="use-wildcards-in-the-process-exclusion-list"></a>在進程排除清單中使用萬用字元

在處理常式排除清單中使用萬用字元，與在其他排除清單中使用的順序不同。

具體說來，您無法使用問號 (`?`) 萬用字元，而且星號 (`*`) 萬用字元只會在完整路徑的結尾使用。 在程式排除清單中定義專案時，您仍然可以使用環境變數 (例如 `%ALLUSERSPROFILE%`) 做為萬用字元。

下表說明如何在進程排除清單中使用萬用字元：

|萬用字元 | 範例使用 | 範例符合 |
|:---|:---|:---|
|`*` (星號)  <br/><br/> 會取代任何數目的字元 | `C:\MyData\*` | 任何開啟的檔案 `C:\MyData\file.exe` |
|環境變數 <br/><br/> 在評估排除時，已定義的變數會填入為路徑 | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | 任何開啟的檔案 `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>審閱排除清單

您可以使用 MpCmdRun、PowerShell、 [Microsoft 端點 Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)、 [Intune](/intune/device-restrictions-configure)或 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)，在排除清單中取得專案。

如果您使用 PowerShell，您可以使用下列兩種方式來找回清單：

- 取得所有 Microsoft Defender 防毒軟體偏好設定的狀態。 每個清單都會顯示在不同的行上，但是每個清單中的專案會組合成同一行。
- 將所有喜好設定的狀態寫入變數中，並使用該變數只呼叫您感興趣的特定清單。 每次使用 `Add-MpPreference` 都會寫入新行。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>使用 MpCmdRun 驗證排除清單

若要使用專用 [命令列工具 mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)檢查排除，請使用下列命令：

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> 使用 MpCmdRun 檢查排除專案時，需要 Microsoft Defender 防病毒預約通話版本 4.18.1812.3 (于十二月 2018) 或更新版本發行。


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>使用 PowerShell 查看排除清單及所有其他 Microsoft Defender 防病毒偏好設定

請使用下列 Cmdlet：

```PowerShell
Get-MpPreference
```

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender) 。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>使用 PowerShell 來檢索特定排除清單

使用下列程式碼片段 (將每一行輸入為個別的命令) ;以您想要命名變數的任何標籤取代 **WDAVprefs** ：

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender) 。

## <a name="related-articles"></a>相關文章

- [設定及驗證 Microsoft Defender 防病毒掃描中的排除專案](configure-exclusions-microsoft-defender-antivirus.md)
- [根據檔案名、副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [設定 Windows Server 上的 Microsoft Defender 防病毒排除](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定義排除時應避免的常見錯誤](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [自訂、啟動和審閱 Microsoft Defender 防病毒掃描和修正的結果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)