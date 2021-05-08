---
title: 設定 Microsoft Defender 防毒軟體功能
description: 您可以使用 Intune、Microsoft Endpoint Configuration Manager、群組原則和 PowerShell 設定 Microsoft Defender 防毒軟體功能。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，configure，configuration，Config Manager，Microsoft Endpoint Configuration Manager，SCCM，Intune，MDM，mobile 裝置管理，GP，群組原則，PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275105"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>設定 Microsoft Defender 防毒軟體功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用一些工具設定 Microsoft Defender 防毒軟體，包括：

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- 群組原則
- PowerShell Cmdlet
- Windows Management Instrumentation (WMI)

您可以設定下列廣泛的功能類別：

- 雲端提供的保護
- Always on 即時保護，包含行為、啟發式和機器學習型保護
- 使用者如何與個別端點上的用戶端互動

下列文章說明在設定 Microsoft Defender 防毒軟體時，如何執行主要工作。 每篇文章都包含適用的設定工具 (或工具) 的指示。

|文章  |描述  |
|---------|---------|
|[使用 Microsoft 雲端提供的 Microsoft Defender 防毒軟體保護](cloud-protection-microsoft-defender-antivirus.md)     | 使用雲端提供的保護，以進行高級、快速、可靠的防病毒偵測。        |
|[設定行為、啟發學習法和即時保護](configure-protection-features-microsoft-defender-antivirus.md)     |啟用行為基礎、啟發式和即時防防毒保護。         |
|[設定使用者與 Microsoft Defender 防毒軟體互動互動](configure-end-user-interaction-microsoft-defender-antivirus.md) | 設定組織中的使用者與 Microsoft Defender 防毒軟體互動的方式、他們看到的通知，以及是否可以覆寫設定。 |

> [!TIP]
> 您也可以查看 [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md) 主題，以取得每個工具的概述，以及進一步說明的連結。