---
title: 設定 Microsoft Defender 防病毒功能
description: 您可以使用 Intune、Microsoft Endpoint Configuration 管理員、群組原則和 PowerShell 來設定 Microsoft Defender 防病毒功能。
keywords: Microsoft Defender 防毒程式，反惡意程式碼，安全性，Defender，configure，configuration，Config Manager，Microsoft Endpoint Configuration Manager，SCCM，Intune，MDM，mobile 裝置管理，GP，群組原則，PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690035"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>設定 Microsoft Defender 防病毒功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以設定 Microsoft Defender 防毒程式的一些工具，包括：

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- 群組原則
- PowerShell Cmdlet
- Windows Management Instrumentation (WMI)

您可以設定下列廣泛的功能類別：

- 雲端提供的保護
- Always on 即時保護，包含行為、啟發式和機器學習型保護
- 使用者如何與個別端點上的用戶端互動

下列文章說明在設定 Microsoft Defender 防病毒時，如何執行主要工作。 每篇文章都包含適用的設定工具 (或工具) 的指示。

|文章  |描述  |
|---------|---------|
|[使用 Microsoft 雲端所提供的 Microsoft Defender 防防毒保護](cloud-protection-microsoft-defender-antivirus.md)     | 使用雲端提供的保護，以進行高級、快速、可靠的防病毒偵測。        |
|[設定行為、啟發式和即時保護](configure-protection-features-microsoft-defender-antivirus.md)     |啟用行為基礎、啟發式和即時防防毒保護。         |
|[使用 Microsoft Defender 防毒軟體設定使用者互動](configure-end-user-interaction-microsoft-defender-antivirus.md) | 設定組織中的使用者與 Microsoft Defender 防毒軟體的互動方式、他們看到的通知，以及是否可以覆寫設定。 |

> [!TIP]
> 您也可以查看 [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md) 主題，以取得每個工具的概述，以及進一步說明的連結。