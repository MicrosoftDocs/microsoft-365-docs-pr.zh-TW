---
title: 使用 PowerShell 排定防病毒掃描
description: 使用 PowerShell 排定防病毒掃描
keywords: 「快速掃描」、「完整掃描」、「防病毒」、「排程」 PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879676"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>使用 PowerShell 排定防病毒掃描

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

本文說明如何使用 PowerShell Cmdlet 設定排程掃描。 若要深入瞭解排程掃描及掃描類型的相關資訊，請參閱[設定排程快速或完整 Microsoft Defender 防毒軟體掃描](schedule-antivirus-scans.md)。 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>使用 PowerShell Cmdlet 來排程掃描

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

如需詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) ，以取得如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊。

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>在端點未使用時進行排程掃描的 PowerShell Cmdlet

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/)。

> [!NOTE]
> 當您排程掃描時未使用端點時，掃描功能不會服從 CPU 節流設定，而且將充分利用可讓您盡可能快地完成掃描的資源。

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>用於排程掃描以完成修復的 PowerShell Cmdlet

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>用於排程每日掃描的 PowerShell Cmdlet

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。


