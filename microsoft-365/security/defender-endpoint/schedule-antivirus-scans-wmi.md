---
title: 使用 Windows 管理工具來排程防病毒掃描
description: 使用 WMI 排定防病毒掃描
keywords: 快速掃描、完整掃描、WMI、排程、防毒程式
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
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879673"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>使用 (WMI) 的 Windows 管理工具來排程防病毒掃描

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

本文說明如何使用 WMI 設定排程掃描。 若要深入瞭解排程掃描及掃描類型的相關資訊，請參閱[設定排程快速或完整 Microsoft Defender 防毒軟體掃描](schedule-antivirus-scans.md)。 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>使用 Windows 管理指令 (WMI) 來排程掃描

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>在端點未使用時進行排程掃描的 WMI

針對下列屬性，使用 [MSFT_MpPreference 類別的 Set 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanOnlyIfIdleEnabled
```

如需 APIs 及允許參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

> [!NOTE]
> 當您排程掃描時未使用端點時，掃描功能不會服從 CPU 節流設定，而且將充分利用可讓您盡可能快地完成掃描的資源。


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>用於排程掃描以完成修復的 WMI

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="wmi-for-scheduling-daily-scans"></a>用於排程每日掃描的 WMI

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanScheduleQuickScanTime
```

如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

