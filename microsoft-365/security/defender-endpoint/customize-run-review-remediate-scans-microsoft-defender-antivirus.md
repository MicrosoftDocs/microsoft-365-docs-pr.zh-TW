---
title: 執行及自訂排程及隨選的掃描。
description: 在網路上的端點上自訂和發起 Microsoft Defender 防毒軟體掃描
keywords: 掃描、排程、自訂、排除、排除檔案、修正、掃描結果、隔離、移除威脅、快速掃描、完整 Microsoft Defender 防毒軟體掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bce3fe1b6490803cb571a1a8a2387c19cc589114
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926232"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>自訂、啟動及審閱 Microsoft Defender 防毒軟體掃描和修正的結果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用「群組原則」、「PowerShell」和「Windows 管理工具」來設定 Microsoft Defender 防毒軟體掃描 (WMI) 。 

## <a name="in-this-section"></a>本節內容

主題 | 描述
---|---
[設定及驗證 Microsoft Defender 防毒軟體掃描中的檔案、資料夾及處理常式開啟檔排除](configure-exclusions-microsoft-defender-antivirus.md) | 您可以排除檔案 (包括由指定的程式所修改的檔案) 和資料夾從隨選的掃描、排程的掃描，以及時刻的即時防護監控及掃描
[設定 Microsoft Defender 防毒軟體掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) | 您可以設定 Microsoft Defender 防毒軟體包含某些類型的電子郵件儲存檔、備份或重新分析點，以及封存的檔案 (例如掃描中) 的 .zip 檔案。 您也可以啟用網路檔掃描
[設定掃描的修正](configure-remediation-microsoft-defender-antivirus.md) | 設定 Microsoft Defender 防毒軟體在偵測到威脅時應執行的動作，以及隔離檔案應該在隔離資料夾中保留多久
[設定排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描
[設定及執行掃描](run-scan-microsoft-defender-antivirus.md) | 在具有 Windows 安全性應用程式的端點上，使用 PowerShell、Windows 管理工具或個別的方式執行及設定隨選掃描
[查看掃描結果](review-scan-results-microsoft-defender-antivirus.md) | 使用 Microsoft Endpoint Configuration Manager、Microsoft Intune 或 Windows 安全性應用程式複查掃描結果