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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="bd8e2-104">使用 (WMI) 的 Windows 管理工具來排程防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="bd8e2-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="bd8e2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bd8e2-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd8e2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bd8e2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bd8e2-107">本文說明如何使用 WMI 設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="bd8e2-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="bd8e2-108">若要深入瞭解排程掃描及掃描類型的相關資訊，請參閱[設定排程快速或完整 Microsoft Defender 防毒軟體掃描](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="bd8e2-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="bd8e2-109">使用 Windows 管理指令 (WMI) 來排程掃描</span><span class="sxs-lookup"><span data-stu-id="bd8e2-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="bd8e2-110">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="bd8e2-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="bd8e2-111">如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="bd8e2-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="bd8e2-112">在端點未使用時進行排程掃描的 WMI</span><span class="sxs-lookup"><span data-stu-id="bd8e2-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="bd8e2-113">針對下列屬性，使用 [MSFT_MpPreference 類別的 Set 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="bd8e2-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="bd8e2-114">如需 APIs 及允許參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="bd8e2-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="bd8e2-115">當您排程掃描時未使用端點時，掃描功能不會服從 CPU 節流設定，而且將充分利用可讓您盡可能快地完成掃描的資源。</span><span class="sxs-lookup"><span data-stu-id="bd8e2-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="bd8e2-116">用於排程掃描以完成修復的 WMI</span><span class="sxs-lookup"><span data-stu-id="bd8e2-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="bd8e2-117">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="bd8e2-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="bd8e2-118">如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="bd8e2-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="bd8e2-119">用於排程每日掃描的 WMI</span><span class="sxs-lookup"><span data-stu-id="bd8e2-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="bd8e2-120">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="bd8e2-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="bd8e2-121">如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="bd8e2-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

