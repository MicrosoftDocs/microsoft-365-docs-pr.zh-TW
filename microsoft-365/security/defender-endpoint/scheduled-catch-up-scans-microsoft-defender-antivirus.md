---
title: 使用 Microsoft Defender 防病毒定期快速和完整掃描排程
description: 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描
keywords: 「快速掃描」、「完整掃描」、「快速完整」、「排程掃描」、「每天」、「排程」、「定期」、「定期」
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bfa616423fc0c097b9909df8abf5b9c414490383
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764084"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>設定排程的快速或完整 Microsoft Defender 防病毒掃描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> 根據預設，Microsoft Defender 防毒程式會在任何排程的掃描時間之前，先檢查是否有15分鐘的更新。 您可以 [管理應下載保護更新及](manage-protection-update-schedule-microsoft-defender-antivirus.md) 套用的時程表，以覆寫此預設值。 

除了無條件即時保護和 [手動](run-scan-microsoft-defender-antivirus.md) 掃描之外，您還可以設定週期性排程掃描。 

您可以設定掃描類型、掃描應該發生時，以及在執行 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後或在使用端點時進行掃描。 您也可以指定何時應該進行特殊的掃描，以完成修復。

本文說明如何使用「群組原則」、「PowerShell Cmdlet」和 WMI 來設定排程掃描。 您也可以使用 [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) 或 [microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)設定排程掃描。

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>若要設定本文所述的群組原則設定

1.  在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

3.  在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

4.  按一下 [系統 **管理範本**]。

5.  在 [ **Microsoft Defender 防病毒 >** ] 的 [Windows 元件] 中，展開樹狀目錄，然後展開下表中所指定的 **位置** 。

6. 按兩下下表中所指定的原則 **設定** ，並將選項設定為您想要的設定。 

7. 按一下 **[確定]**，然後對任何其他設定重複此步驟。

另請參閱 [管理應下載及套用保護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) ，並 [防止或允許使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主題。

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>快速掃描與完整掃描及自訂掃描

當您設定排程掃描時，您可以設定掃描是否應為完整或快速掃描。

快速掃描查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 的 [啟動] 資料夾。 

與 [always on 即時保護功能](configure-real-time-protection-microsoft-defender-antivirus.md) 組合在一起，可在開啟和關閉檔時檢查檔案，以及每當使用者流覽至資料夾時，都可以為以系統和內核層級惡意程式碼開始的惡意程式碼提供強大的覆蓋。  

在大多數的情況下，這表示快速掃描足以找到即時保護未挑選的惡意程式碼。

在發生惡意程式碼威脅的端點上，您可以使用完整掃描來識別是否有任何非使用中的元件需要更徹底的清理。 在此範例中，您可能會想要在執行 [隨選掃描](run-scan-microsoft-defender-antivirus.md)時使用完整掃描。

自訂掃描可讓您指定要掃描的檔案和資料夾，例如 USB 磁片磁碟機。 

>[!NOTE]
>根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。

## <a name="set-up-scheduled-scans"></a>設定排程掃描

排程的掃描會在您指定的日期和時間執行。 您可以使用「群組原則」、「PowerShell」和「WMI」來設定排程掃描。

>[!NOTE]
>如果電腦已在排程完整掃描期間已拔出並在電池上執行，則排定的掃描會停止事件1002，這表明掃描在完成前已停止。 Microsoft Defender 防病毒會在下一個排程的時間執行完整掃描。

### <a name="use-group-policy-to-schedule-scans"></a>使用群組原則來排程掃描

|位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
|掃描 | 指定用於排程掃描的掃描類型 | 快速掃描 |
|掃描 | 指定一周中的哪一天執行排程掃描 | 指定 [天] (或 [永不) ] 執行掃描。 | 從來不需要 |
|掃描 | 指定一天中執行排程掃描的時間 | 指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) 。 | 淩晨2點 |
|根 | 隨機化排程的任務時間 |在 Microsoft Defender 防毒程式中：從0到4小時隨機化掃描的開始時間。 <br>在 FEP/SCEP 中：隨機化到任何間隔加上或減30分鐘。 在 VM 或 VDI 部署中，這會很有用。 | Enabled |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>使用 PowerShell Cmdlet 來排程掃描

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>使用 Windows 管理指令 (WMI) 排定掃描

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>只有在端點未使用中時才開始排程掃描

您可以設定排程的掃描，只會在端點開啟時，但不能與群組原則、PowerShell 或 WMI 搭配使用。

> [!NOTE]
> 這些掃描不會服從 CPU 節流設定，而且可充分利用資源，以盡可能快地完成掃描。

### <a name="use-group-policy-to-schedule-scans"></a>使用群組原則來排程掃描

|位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
|掃描 | 僅當電腦已開啟但未在使用中時啟動排程掃描 | 除非電腦已開啟但未在使用中，否則不會執行排程掃描 | Enabled |

### <a name="use-powershell-cmdlets"></a>使用 PowerShell Cmdlet

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi"></a>使用 Windows Management 指令 (WMI) 

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanOnlyIfIdleEnabled
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>設定應該執行完整掃描以完成修復的時間

有些威脅可能需要完整掃描，才能完成移除和修復。 您可以使用「群組原則」、「PowerShell」或「WMI」時排程進行這些掃描。

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>使用群組原則來排定修復所需的掃描

| 位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|---|---|---|---|
|修復 | 指定一周中的哪幾天執行排程完整掃描以完成修復 | 指定 [天] (或 [永不) ] 執行掃描。 | 從來不需要 |
|修復 | 指定一天中執行計畫完整掃描以完成修復的時間 | 指定午夜後的分鐘數 (例如，輸入 **60** a.m. )  | 淩晨2點 |

### <a name="use-powershell-cmdlets"></a>使用 PowerShell Cmdlet

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi"></a>使用 Windows Management 指令 (WMI) 

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>設定每日快速掃描

除了使用群組原則、PowerShell 或 WMI 排定的其他排程掃描之外，您還可以啟用執行每日快速掃描。


### <a name="use-group-policy-to-schedule-daily-scans"></a>使用群組原則排定每日掃描


|位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
|掃描 | 指定每天執行快速掃描的間隔 | 指定下一個快速掃描之前所應經過的小時數。 例如，若要每兩個小時執行一次，請輸入 **2** 一天一次，輸入 **24**。 輸入 **0** ，永遠不執行每日快速掃描。 | 從來不需要 |
|掃描 | 指定每日快速掃描的時間 | 指定午夜後的分鐘數 (例如，輸入 **60** a.m. )  | 淩晨2點 |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>使用 PowerShell Cmdlet 排程每日掃描

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>使用 Windows 管理指令 (WMI) 排定每日掃描

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanScheduleQuickScanTime
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>在保護更新後啟用掃描

您可以使用群組原則，強制進行每個 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後的掃描。

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>使用群組原則在保護更新後排程掃描

|位置 | 設定 | 描述 | 預設設定 (（如果未設定）) |
|:---|:---|:---|:---|
|特徵碼更新 | 在安全性智慧更新後開啟掃描 | 下載新的保護更新後會立即進行掃描 | Enabled |

## <a name="see-also"></a>另請參閱
- [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [設定及執行隨選 Microsoft Defender 防毒程式掃描](run-scan-microsoft-defender-antivirus.md)
- [設定 Microsoft Defender 防病毒掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防病毒更新並套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)