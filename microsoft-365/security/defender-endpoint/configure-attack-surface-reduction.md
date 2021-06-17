---
title: 設定受攻擊面縮小功能
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell Cmdlet 及群組原則來設定攻擊面降低。
keywords: asr、攻擊面減少、windows defender、microsoft defender、防毒軟體、av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984445"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>設定受攻擊面縮小功能

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要體驗 Defender for Endpoint？ [註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。

Defender for Endpoint 包含數個攻擊面降低功能。 若要深入瞭解，請參閱 [攻擊面降減功能](overview-attack-surface-reduction.md)。 若要設定環境中的攻擊面減少，請遵循下列步驟：

1. [為 Microsoft Edge 啟用硬體型隔離](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)。

2. 啟用應用程式控制。

   1. 在 Windows 中檢查基底原則。 請參閱 [範例基底原則](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。
   2. 請參閱[Windows Defender 應用程式控制項設計指南](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。
   3. 請參閱[部署 Windows Defender 應用程式控制項 (WDAC) 原則](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。

3. [啟用可控資料夾存取](enable-controlled-folders.md)。

4. [開啟網路保護](enable-network-protection.md)。

5. [啟用 exploit protection](enable-exploit-protection.md)。

6. [設定攻擊面減少規則](enable-attack-surface-reduction.md)。

7. 設定網路防火牆。

   1. 深入瞭解[具有高級安全性的 Windows Defender 防火牆](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
   2. 使用[Windows Defender 防火牆設計指南](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)決定您要如何設計防火牆原則。
   3. 使用[Windows Defender 防火牆部署指南](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)，設定您組織的具有高級安全性的防火牆。

> [!TIP]
> 在大多數情況下，當您設定攻擊面降減功能時，您可以選擇下列方法：

> - Microsoft 端點管理員 (包含 Microsoft Intune 及 Microsoft Endpoint Configuration Manager) 
> - 群組原則
> - PowerShell Cmdlet
