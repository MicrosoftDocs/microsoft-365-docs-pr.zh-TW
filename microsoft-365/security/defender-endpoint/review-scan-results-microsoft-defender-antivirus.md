---
title: 審閱 Microsoft Defender AV 掃描的結果
description: 使用 Microsoft Endpoint Configuration Manager、Microsoft Intune 或 Windows 安全性應用程式複查掃描結果
keywords: 掃描結果、修復、完整掃描、快速掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8fe2810ce18589d3131aa17f25ccfb01ec26b892
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690152"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="d6447-104">審閱 Microsoft Defender 防病毒掃描結果</span><span class="sxs-lookup"><span data-stu-id="d6447-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d6447-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d6447-105">**Applies to:**</span></span>

- [<span data-ttu-id="d6447-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6447-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d6447-107">Microsoft Defender 防病毒掃描完成後，不論是 [按需](run-scan-microsoft-defender-antivirus.md) 或 [排程的掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)，都會記錄結果，您可以查看結果。</span><span class="sxs-lookup"><span data-stu-id="d6447-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="d6447-108">使用 Configuration Manager 查看掃描結果</span><span class="sxs-lookup"><span data-stu-id="d6447-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="d6447-109">請參閱 [如何監視 Endpoint Protection 狀態](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="d6447-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="d6447-110">使用 PowerShell Cmdlet 來複查掃描結果</span><span class="sxs-lookup"><span data-stu-id="d6447-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="d6447-111">下列 Cmdlet 會傳回端點上的每個偵測。</span><span class="sxs-lookup"><span data-stu-id="d6447-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="d6447-112">如果有多個偵測到相同的威脅，每個偵測都會根據每次偵測的時間，分別列出：</span><span class="sxs-lookup"><span data-stu-id="d6447-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![PowerShell Cmdlet 和輸出的螢幕擷取畫面](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="d6447-114">您可以指定 `-ThreatID` 將輸出限制為只顯示特定威脅的偵測。</span><span class="sxs-lookup"><span data-stu-id="d6447-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="d6447-115">如果您想要列出威脅偵測，但將相同威脅的偵測結合到單一專案中，您可以使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d6447-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![PowerShell 的螢幕擷取畫面](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="d6447-117">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="d6447-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="d6447-118">使用 Windows Management 指令 (WMI) 以查看掃描結果</span><span class="sxs-lookup"><span data-stu-id="d6447-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="d6447-119">使用 [ **MSFT_MpThreat** 和 **MSFT_MpThreatDetection** 類別的 **Get** 方法](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="d6447-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="d6447-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="d6447-120">Related articles</span></span>

- [<span data-ttu-id="d6447-121">自訂、啟動和審閱 Microsoft Defender 防病毒掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="d6447-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d6447-122">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d6447-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)