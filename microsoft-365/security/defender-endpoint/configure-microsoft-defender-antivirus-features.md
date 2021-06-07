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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789024"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>設定 Microsoft Defender 防毒軟體功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用一些工具設定 Microsoft Defender 防毒軟體，例如：

- 包含 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 的 Microsoft 端點管理員 () 
- 群組原則
- PowerShell Cmdlet
- Windows Management Instrumentation (WMI)

您可以設定下列廣泛的功能類別：

- 雲端提供的保護。 請參閱[雲端提供的保護和 Microsoft Defender 防毒軟體](cloud-protection-microsoft-defender-antivirus.md)
 
- Always on 即時保護，包含行為、啟發式和機器學習型保護。 請參閱 [設定行為、啟發式和即時保護](configure-protection-features-microsoft-defender-antivirus.md)。

- 使用者如何與個別端點上的用戶端互動。 請參閱下列資源：
   
   - [防止使用者看到或與 Microsoft Defender 防毒軟體使用者介面互動](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [防止或允許使用者本機修改 Microsoft Defender 防毒軟體原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> 請參閱 [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md)。