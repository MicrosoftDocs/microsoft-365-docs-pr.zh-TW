---
title: 審閱 Microsoft Defender AV 掃描的結果
description: 使用 Microsoft Endpoint Configuration Manager、Microsoft Intune 或 Windows 安全性應用程式複查掃描結果
keywords: 掃描結果、修復、完整掃描、快速掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ec3dd2edc09d504af0ed76b17577130b1cdce1b7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275369"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>審閱 Microsoft Defender 防毒軟體掃描結果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防毒軟體掃描完成後，不論是[按需](run-scan-microsoft-defender-antivirus.md)或[排程的掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)，都會記錄結果，您可以查看結果。 


## <a name="use-configuration-manager-to-review-scan-results"></a>使用 Configuration Manager 查看掃描結果

請參閱[如何監視 Endpoint Protection 狀態](/configmgr/protect/deploy-use/monitor-endpoint-protection)。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>使用 PowerShell Cmdlet 來複查掃描結果

下列 Cmdlet 會傳回端點上的每個偵測。 如果有多個偵測到相同的威脅，每個偵測都會根據每次偵測的時間，分別列出：

```PowerShell
Get-MpThreatDetection
```

![PowerShell Cmdlet 和輸出的螢幕擷取畫面](images/defender/wdav-get-mpthreatdetection.png)

您可以指定 `-ThreatID` 將輸出限制為只顯示特定威脅的偵測。

如果您想要列出威脅偵測，但將相同威脅的偵測結合到單一專案中，您可以使用下列 Cmdlet：

```PowerShell
Get-MpThreat
```

![PowerShell 的螢幕擷取畫面](images/defender/wdav-get-mpthreat.png)

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>使用 Windows 管理指令 (WMI) 以查看掃描結果

使用 [ **MSFT_MpThreat** 和 **MSFT_MpThreatDetection** 類別的 **Get** 方法](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。


## <a name="related-articles"></a>相關文章

- [自訂、啟動及審閱 Microsoft Defender 防毒軟體掃描和修正的結果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)