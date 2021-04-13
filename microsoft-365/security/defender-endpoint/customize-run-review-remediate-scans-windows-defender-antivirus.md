---
title: 執行及自訂排程和隨選掃描
description: 在您的網路上，自訂及啟動端點的 Microsoft Defender 防病毒掃描。
keywords: 掃描、排程、自訂、排除、排除檔案、修正、掃描結果、隔離、移除威脅、快速掃描、完整掃描、Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5f8e5606b01186e31a58f6d506b5898f20b63511
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690024"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>自訂、啟動和審閱 Microsoft Defender 防病毒掃描的結果 & 修正

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用「群組原則」、「PowerShell」和「Windows Management Instrumentation」 (WMI) 來設定 Microsoft Defender 防病毒掃描。 

## <a name="in-this-section"></a>在本章節中

| 文章 | 描述 |
|:---|:---|
|[設定及驗證 Microsoft Defender 防病毒掃描中的檔案、資料夾及處理常式開啟檔排除](configure-exclusions-microsoft-defender-antivirus.md) | 您可以排除檔案 (包括由指定的程式所修改的檔案) 和資料夾從隨選的掃描、排程的掃描，以及時刻的即時防護監控及掃描 |
|[設定 Microsoft Defender 防病毒掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) | 您可以設定 Microsoft Defender 防毒軟體，使其包含某些類型的電子郵件儲存檔、備份或重新分析點，以及封存的檔案 (例如，在掃描中) .zip 檔案。 您也可以啟用網路檔掃描 |
|[設定掃描的修正](configure-remediation-microsoft-defender-antivirus.md) | 在偵測到威脅時，設定 Microsoft Defender 防毒軟體應執行的動作，以及隔離檔案應該在隔離資料夾中保留多久 |
|[設定排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | 設定週期性 (排程) 掃描，包括何時應執行，以及是否執行為完整或快速掃描 |
|[設定及執行掃描](run-scan-microsoft-defender-antivirus.md) | 在具有 Windows Security app 的端點上使用 PowerShell、Windows Management Instrumentation 或個別的方式執行及設定隨選掃描 |
|[查看掃描結果](review-scan-results-microsoft-defender-antivirus.md) | 使用 Microsoft Endpoint Configuration Manager、Microsoft Intune 或 Windows 安全性應用程式複查掃描結果 |