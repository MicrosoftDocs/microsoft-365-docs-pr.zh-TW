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
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="34f2f-104">使用 PowerShell 排定防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="34f2f-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="34f2f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="34f2f-105">**Applies to:**</span></span>

- [<span data-ttu-id="34f2f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="34f2f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="34f2f-107">本文說明如何使用 PowerShell Cmdlet 設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="34f2f-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="34f2f-108">若要深入瞭解排程掃描及掃描類型的相關資訊，請參閱[設定排程快速或完整 Microsoft Defender 防毒軟體掃描](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="34f2f-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="34f2f-109">使用 PowerShell Cmdlet 來排程掃描</span><span class="sxs-lookup"><span data-stu-id="34f2f-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="34f2f-110">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="34f2f-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="34f2f-111">如需詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) ，以取得如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="34f2f-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="34f2f-112">在端點未使用時進行排程掃描的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="34f2f-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="34f2f-113">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="34f2f-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="34f2f-114">要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="34f2f-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="34f2f-115">當您排程掃描時未使用端點時，掃描功能不會服從 CPU 節流設定，而且將充分利用可讓您盡可能快地完成掃描的資源。</span><span class="sxs-lookup"><span data-stu-id="34f2f-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="34f2f-116">用於排程掃描以完成修復的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="34f2f-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="34f2f-117">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="34f2f-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="34f2f-118">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="34f2f-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="34f2f-119">用於排程每日掃描的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="34f2f-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="34f2f-120">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="34f2f-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="34f2f-121">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="34f2f-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


