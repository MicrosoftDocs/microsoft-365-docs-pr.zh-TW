---
title: 在您的企業中管理 Windows Defender
description: 瞭解如何使用群組原則、Configuration Manager、PowerShell、WMI、Intune 和命令列來管理 Microsoft Defender AV
keywords: 群組原則，gpo，config manager，sccm，scep，powershell，wmi，intune，defender，防毒程式，反惡意軟體，安全性，保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764864"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>管理企業中的 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用下列工具來管理及設定 Microsoft Defender 防毒程式：

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (現在是 Microsoft 端點管理員的一部分) 
- [Microsoft 端點 Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) 現在 (Microsoft 端點管理員的一部分) 
- [群組原則](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell Cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Management Instrumentation (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Microsoft 惡意程式碼保護命令列公用程式](./command-line-arguments-microsoft-defender-antivirus.md) (稱為 *mpcmdrun.exe* 公用程式

下列文章提供使用這些工具來管理及設定 Microsoft Defender 防毒程式的進一步資訊、連結及資源。

| 文章 | 描述 |
|:---|:---|
|[使用 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 管理 Microsoft Defender 防毒程式](use-intune-config-manager-microsoft-defender-antivirus.md)|使用 Intune 及 Configuration Manager 來部署、管理、報告和設定 Microsoft Defender 防毒程式的資訊 |
|[使用群組原則設定來管理 Microsoft Defender 防毒程式](use-group-policy-microsoft-defender-antivirus.md)|位於 ADMX 範本中的所有群組原則設定清單 |
|[使用 PowerShell Cmdlet 來管理 Microsoft Defender 防毒程式](use-powershell-cmdlets-microsoft-defender-antivirus.md)|使用 PowerShell Cmdlet 來管理 Microsoft Defender 防毒程式的指示，外加所有 Cmdlet 及允許參數的檔連結 |
|[使用 Windows Management Instrumentation (WMI) 管理 Microsoft Defender 防毒程式 ](use-wmi-microsoft-defender-antivirus.md)| 使用 WMI 來管理 Microsoft Defender 防毒程式的指示，加上 WMIv2 APIs (檔的連結，包括所有的類別、方法及屬性)  |
|[使用 mpcmdrun.exe 命令列工具管理 Microsoft Defender 防毒程式](command-line-arguments-microsoft-defender-antivirus.md)|使用專用命令列工具來管理及使用 Microsoft Defender 防毒程式的指示 |