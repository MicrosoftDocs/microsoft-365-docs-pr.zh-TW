---
title: 監視及報告 Microsoft Defender 防毒軟體保護
description: 使用 Configuration Manager 或 security information and event management (SIEM) 工具使用報表，並以 PowerShell 和 WMI 監視 Microsoft Defender AV。
keywords: siem、監控、報告、Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269581"
---
# <a name="report-on-microsoft-defender-antivirus"></a>在 Microsoft Defender 防毒軟體上報告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防毒軟體會內置於 Windows 10、Windows Server 2019 及 Windows Server 2016。 Microsoft Defender 防毒軟體是 Microsoft Defender for Endpoint 中的下一代保護。 下一代保護可協助保護您的裝置免受電子郵件、應用程式、雲端和網路等軟體威脅（如病毒、惡意程式碼和間諜軟體）的威脅。

透過 Microsoft Defender 防毒軟體，您有數個選項可以查看保護狀態及警示。 您可以使用 Microsoft 端點管理員來[監控 Microsoft Defender 防毒軟體](/configmgr/protect/deploy-use/monitor-endpoint-protection)或[建立電子郵件警示](/configmgr/protect/deploy-use/endpoint-configure-alerts)。 或者，您可以使用[Microsoft Intune](/intune/introduction-intune)監視保護。  

Microsoft Operations Management Suite 具有[更新規範增益集](/windows/deployment/update/update-compliance-get-started)，可報告重要的 Microsoft Defender 防毒軟體問題，包括保護更新和即時保護設定。

如果您有協力廠商的安全性資訊和事件管理 (SIEM) server，您也可以使用[Windows Defender 用戶端事件](/windows/win32/events/windows-events)。 

Windows 事件會包含數個安全性事件來源，包括安全性帳戶管理員 (SAM) 事件 ([增強的 Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)，另請參閱[安全性審核](/windows/device-security/auditing/security-auditing-overview)主題) 和[Windows Defender 事件](troubleshoot-microsoft-defender-antivirus.md)。 

您可以使用[Windows 事件收集器](/windows/win32/wec/windows-event-collector)來集中匯總這些事件。 SIEM 伺服器通常會有 Windows 事件的連接器，可讓您在 SIEM server 中關聯所有的安全性事件。 

您也可以 [使用記錄分析中的惡意程式碼評估解決方案，監控惡意程式碼事件](/azure/log-analytics/log-analytics-malware)。

若要使用 PowerShell、WMI 或 Microsoft Azure 來監視或決定狀態，請參閱[ (部署、管理及報告選項表格) ](deploy-manage-report-microsoft-defender-antivirus.md#ref2)。

## <a name="related-articles"></a>相關文章

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 2016 和 2019 上的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md)
- [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)