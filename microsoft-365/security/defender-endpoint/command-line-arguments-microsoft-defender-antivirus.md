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
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>使用 mpcmdrun.exe 命令列工具來設定及管理 Microsoft Defender 防毒軟體

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以 **mpcmdrun.exe** 使用專用命令列工具來執行各種 Microsoft Defender 防毒軟體功能。 當您想要自動化 Microsoft Defender 防毒軟體使用時，此公用程式非常有用。 您可以在中找到該公用程式 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 您必須從命令提示字元執行它。

> [!NOTE]
> 您可能需要開啟命令提示字元的系統管理員層級版本。 當您在 [開始] 功能表上搜尋 **命令提示** 字元時，選擇 [以 **系統管理員身分執行**]。
> 如果您正在執行更新的 Microsoft Defender 平臺版本，請 `**MpCmdRun**` 從下列位置執行： `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 。
> 如需有關反惡意程式碼平臺的詳細資訊，請參閱[Microsoft Defender 防毒軟體更新和基準](manage-updates-baselines-microsoft-defender-antivirus.md)。

MpCmdRun 實用程式使用下列語法：

```console
MpCmdRun.exe [command] [-options]
```

以下為範例:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| 命令  | 描述   |
|:----|:----|
| `-?`**或**`-h`   | 顯示此工具的所有可用選項 |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | 掃描惡意軟體。 **ScanType** 的值包括：<p>根據您的設定，預設為 **0**<p>**-1** 快速掃描<p>**-2** 完整掃描<p>**-3** 檔案與目錄自訂掃描。<p>CpuThrottling 將會服從原則設定的 CPU 節流 |
| `-Trace [-Grouping #] [-Level #]` | 啟動診斷追蹤 |
| `-GetFiles [-SupportLogLocation <path>]` | 收集支援資訊。 請參閱[收集診斷資料](collect-diagnostic-data.md)'  |
| `-GetFilesDiagTrack`  | 等同于 `-GetFiles` ，但輸出到暫時 DiagTrack 資料夾 |
| `-RemoveDefinitions [-All]` | 將已安裝的安全性情報還原為先前的備份副本或原始的預設集合 |
| `-RemoveDefinitions [-DynamicSignatures]` | 僅移除已下載的安全性情報 |
| `-RemoveDefinitions [-Engine]` | 還原先前安裝的引擎 |
| `-SignatureUpdate [-UNC \| -MMPC]` | 檢查新的安全性智慧更新 |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | 還原或列出隔離的專案 (s)  |
| `-AddDynamicSignature [-Path]` | 載入動態安全性情報 |
| `-ListAllDynamicSignatures` | 列出已載入的動態安全性情報 |
| `-RemoveDynamicSignature [-SignatureSetID]` | 移除動態安全性情報 |
| `-CheckExclusion -path <path>` | 檢查是否排除路徑 |
| `-ValidateMapsConnection` | 驗證您的網路是否可以與 Microsoft Defender 防毒軟體雲端服務通訊。 這個命令只會在 Windows 10 版本1703或更高版本上運作。|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>透過 mpcmdrun.exe 執行命令時的常見錯誤 

|錯誤訊息 | 可能的原因
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | 已停用 Microsoft Defender 防毒軟體服務。 請啟用服務，然後再試一次。 <br>   **附注：** 在 Windows 10 1909 或更舊版本，以及 Windows Server 2019 或更舊版本中，服務是用來呼叫 *Windows Defender 防毒軟體* 服務。|
| `0x80070667` | 您正在 `-ValidateMapsConnection` 從 Windows 10 版本1607或更舊版本的電腦，或 Windows Server 2016 或更舊版本執行命令。 從 Windows 10 版本1703或更新版本的機器執行命令，或 Windows 伺服器2019或更新版本。|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | 工具需要執行的來源： `%ProgramFiles%\Windows Defender` 或 `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (， `2012.4-0` 因為平臺更新是每月以外的，而不是三月份) |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | 沒有足夠的許可權。 以系統管理員身分 (cmd.exe) 使用命令提示字元。|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | 防火牆會封鎖連接或進行 SSL 檢查。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | 可能的網路相關問題，例如名稱解析問題|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | 防火牆會封鎖連接或進行 SSL 檢查。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | 防火牆會封鎖連接或進行 SSL 檢查。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | 防火牆會封鎖連接或進行 SSL 檢查。 |

## <a name="see-also"></a>另請參閱

- [設定 Microsoft Defender 防毒軟體功能](configure-microsoft-defender-antivirus-features.md)
- [管理貴公司的 Microsoft Defender 防毒軟體](configuration-management-reference-microsoft-defender-antivirus.md)
- [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)