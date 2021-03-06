---
title: 使用 WMI 設定 Microsoft Defender 防毒軟體
description: 瞭解如何使用 WMI 腳本來設定及管理 Microsoft Defender 防毒軟體，以在 Microsoft Defender for Endpoint 中取得、修改和更新設定。
keywords: wmi、腳本、windows management instrumentation、設定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764060"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>使用 Windows Management Instrumentation (WMI) 設定及管理 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Windows管理工具 (WMI) 是指令碼介面，可讓您檢索、修改和更新設定。

若要深入瞭解，請參閱 [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page)上的 WMI。

Microsoft Defender 防毒軟體有許多特定的 WMI 類別，可用來執行大部分與群組原則及其他管理工具相同的功能。 許多類別與 [Defender PowerShell Cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)類似。

[MSDN Windows Defender WMIv2 提供者參考程式庫](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)會列出 Microsoft Defender 防毒軟體可用的 WMI 類別，並包含範例腳本。

使用 WMI 所做的變更會影響部署變更之端點上的本機設定。 這表示使用「群組原則」、「Microsoft Endpoint Configuration Manager」或「Microsoft Intune」原則進行的部署，可以覆寫透過 WMI 所做的變更。 

您可以 [設定哪些設定可以在本機上使用本機原則覆寫](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

## <a name="related-topics"></a>相關主題

- [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)