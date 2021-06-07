---
title: 使用 Microsoft Defender 防毒軟體安排一般快速和完整掃描
description: 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描
keywords: 「快速掃描」、「完整掃描」、「快速完整」、「排程掃描」、「每天」、「排程」、「定期」、「定期」
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789265"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>設定排程的快速或完整 Microsoft Defender 防毒軟體掃描

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> 根據預設，Microsoft Defender 防毒軟體會在任何排程的掃描時間之前，先檢查是否有15分鐘的更新。 您可以 [管理應下載保護更新及](manage-protection-update-schedule-microsoft-defender-antivirus.md) 套用的時程表，以覆寫此預設值。 

除了無條件即時保護和 [手動](run-scan-microsoft-defender-antivirus.md) 掃描之外，您還可以設定週期性排程掃描。 

您可以設定掃描類型、掃描應該發生時，以及在執行 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後或在使用端點時進行掃描。 您也可以指定何時應該進行特殊的掃描，以完成修復。

本文說明如何使用「群組原則」、「PowerShell Cmdlet」和 WMI 來設定排程掃描。 您也可以使用[Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings)或[Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)設定排程掃描。

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>若要設定本文所述的群組原則設定

1. 在您的群組原則管理電腦上，在 [群組原則編輯器] 中，移至 [電腦設定]**系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。

2. 以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。

3. 指定「群組原則」物件的設定，然後選取 **[確定]**。 

4. 針對每個您要設定的設定，請重複步驟1-4。

5. 照常部署您的群組原則物件。 如果您需要「群組原則」物件的協助，請參閱 [建立群組原則物件](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。

另請參閱 [管理應下載及套用保護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) ，並 [防止或允許使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主題。

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>快速掃描與完整掃描及自訂掃描

當您設定排程掃描時，您可以設定掃描是否應為完整或快速掃描。


|快速掃描  |完整掃描  | 自訂掃描 |
|---------|---------|---------|
|快速掃描會查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 開機檔案夾。 <p>在大多數情況下，快速掃描足以滿足排程掃描的建議。 |完整掃描會從執行快速掃描開始，繼續執行所有已裝載固定磁片及移除/網路磁碟機的連續檔案掃描 (如果完整掃描已設定為執行此作業) 。 <p>根據需要掃描的資料量和類型，完整掃描可能需要數小時或數天才能完成。<p>完成完整掃描後，即可使用新的安全性智慧，並需要進行新的掃描，以確保不會偵測到新安全性情報的其他威脅。   | 自訂掃描是在您指定的檔案和資料夾上執行的快速掃描。 例如，您可以選擇掃描 USB 磁片磁碟機，或裝置的本機磁片磁碟機上的特定資料夾。 <p> | 

>[!NOTE]
>根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。

### <a name="how-do-i-know-which-scan-type-to-choose"></a>如何知道要選擇的掃描類型為何？

請使用下表選擇掃描類型。


|案例  |建議的掃描類型  |
|---------|---------|
|您想要設定定期、排程掃描     | 快速掃描 <p>快速掃描會檢查裝置上的處理常式、記憶體、設定檔及特定位置。 [！注意] 結合了 [always on 即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)，快速掃描可為以系統和內核層級惡意程式碼開頭的惡意程式碼提供強大的覆蓋。 即時保護會在開啟及關閉檔時查看檔案，以及每當使用者流覽至資料夾時，就會檢查檔案。         |
|在個別裝置上偵測到威脅（如惡意程式碼）     | 快速掃描 <p>在大多數情況下，快速掃描會捕捉並清除偵測到的惡意程式碼。   |
|您想要執行 [隨選掃描](run-scan-microsoft-defender-antivirus.md)     | 快速掃描       |
| 您想確定可擕式裝置（例如 USB 磁片磁碟機）不包含惡意程式碼 | 自訂掃描 <p>自訂掃描可讓您選取特定位置、資料夾或檔案，並執行快速掃描。 |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>若要瞭解快速和完整掃描，還需要瞭解什麼？

- 惡意檔案可以儲存在快速掃描中未包含的位置。 不過，always on 即時保護會檢查開啟和關閉的所有檔案，以及使用者可存取之資料夾中的所有檔案。 即時保護和快速掃描的組合，可協助抵禦惡意程式碼的加強防護。

- 以 [雲端傳送保護](cloud-protection-microsoft-defender-antivirus.md) 的存取保護，可協助確保已使用最新的安全性情報和雲端機教學模型掃描系統上存取的所有檔案。

- 當即時保護偵測到惡意程式碼，且不會最初決定受影響的檔案的程度時，Microsoft Defender 防毒軟體會在修復程式中啟動完整掃描。

- 完整掃描可偵測其他掃描未偵測到的惡意檔，例如快速掃描。 不過，完整掃描可能需要一段時間，並使用寶貴的系統資源完成。

- 如果裝置離線一段時間，則完整掃描可能需要較長的時間才能完成。 

## <a name="set-up-scheduled-scans"></a>設定排程掃描

排定的掃描會在您指定的日期和時間執行。 您可以使用「群組原則」、「PowerShell」和「WMI」來設定排程掃描。

> [!NOTE]
> 如果在排程完整掃描期間，裝置已拔出並在電池上執行，則排定的掃描會停止事件1002，這表明掃描在完成前已停止。 Microsoft Defender 防毒軟體會在下一個排程的時間執行完整掃描。

### <a name="use-group-policy-to-schedule-scans"></a>使用群組原則來排程掃描

|位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
|掃描 | 指定用於排程掃描的掃描類型 | 快速掃描 |
|掃描 | 指定一周中的哪一天執行排程掃描 | 指定 [天] (或 [永不) ] 執行掃描。 | 從來不需要 |
|掃描 | 指定一天中執行排程掃描的時間 | 指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) 。 | 淩晨2點 |
|根 | 隨機化排程的任務時間 |在 Microsoft Defender 防毒軟體中，將掃描的開始時間隨機化為從0到4小時的任何間隔。 <p>在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，隨機化掃描任何間隔加上或減30分鐘。 這對虛擬機器或 VDI 部署很有用。 | 已啟用 |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>使用 PowerShell Cmdlet 來排程掃描

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

如需詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) ，以取得如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊。

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>使用 Windows 管理指令 (WMI) 來排程掃描

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>只有在端點未使用中時才開始排程掃描

您可以設定排程的掃描，只會在端點開啟時，但不能與群組原則、PowerShell 或 WMI 搭配使用。

> [!NOTE]
> 這些掃描不會服從 CPU 節流設定，而且可充分利用資源，以盡可能快地完成掃描。

### <a name="use-group-policy-to-schedule-scans"></a>使用群組原則來排程掃描

|位置 | 設定 | 描述 | 預設設定 (（如果未設定）)  |
|:---|:---|:---|:---|
|掃描 | 僅當電腦已開啟但未在使用中時啟動排程掃描 | 除非電腦已開啟但未在使用中，否則不會執行排程掃描 | 已啟用 |

### <a name="use-powershell-cmdlets"></a>使用 PowerShell Cmdlet

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi"></a> (WMI) 使用 Windows 管理指令

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanOnlyIfIdleEnabled
```

如需 APIs 及允許參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>設定應該執行完整掃描以完成修復的時間

有些威脅可能需要完整掃描，才能完成移除和修復。 您可以指定何時使用群組原則、PowerShell 或 WMI 進行這些掃描。

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

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi"></a> (WMI) 使用 Windows 管理指令

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。


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

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>使用 Windows 管理指令 (WMI) 排定每日掃描

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanScheduleQuickScanTime
```

如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。


## <a name="enable-scans-after-protection-updates"></a>在保護更新後啟用掃描

您可以使用群組原則，強制進行每個 [保護更新](manage-protection-updates-microsoft-defender-antivirus.md) 後的掃描。

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>使用群組原則在保護更新後排程掃描

|位置 | 設定 | 描述 | 預設設定 (（如果未設定）) |
|:---|:---|:---|:---|
|特徵碼更新 | 在安全性智慧更新後開啟掃描 | 下載新的保護更新後會立即進行掃描 | 已啟用 |

## <a name="see-also"></a>另請參閱

- [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [設定和執行隨選 Microsoft Defender 防毒軟體掃描](run-scan-microsoft-defender-antivirus.md)
- [設定 Microsoft Defender 防毒軟體掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)