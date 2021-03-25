---
title: Windows 10 裝置的上線工具及方法
description: 板載 Windows 10 裝置，讓他們可以將感應器資料傳送至 Microsoft Defender ATP 感應器
keywords: 板載 Windows 10 裝置、群組原則、端點 configuration manager、行動裝置管理、本機腳本、gp、sccm、mdm、intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165534"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Windows 10 裝置的上線工具及方法

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 端點資料遺失防護 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

您組織中的裝置必須設定，讓 Endpoint service 的 Defender 才能從這些裝置取得感應器資料。 您可以使用各種方法和部署工具來設定組織中的裝置。

下列為支援的部署工具及方法：

- 群組原則
- Microsoft Endpoint Configuration Manager
- 行動裝置管理 (包括 Microsoft Intune) 
- 本機腳本

## <a name="in-this-section"></a>本節內容
主題 | 描述
:---|:---
[使用群組原則的板載 Windows 10 裝置](configure-endpoints-gp.md) | 使用群組原則在裝置上部署設定套件。
[使用 Microsoft Endpoint Configuration Manager 的板載 Windows 裝置](configure-endpoints-sccm.md) | 您可以使用 Microsoft 端點管理員 (目前的分支) 版本1606或 Microsoft 端點管理員 (目前的分支) 版本1602或更早版本，以在裝置上部署設定套件。
[使用行動裝置管理工具上線 Windows 10 電腦](configure-endpoints-mdm.md) | 使用行動裝置管理工具或 Microsoft Intune 在裝置上部署設定套件。
[使用本機指令碼上線 Windows 10 裝置](configure-endpoints-script.md) | 瞭解如何使用本機腳本，在端點上部署設定套件。
[上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](configure-endpoints-vdi.md) | 瞭解如何使用 configuration 套件來設定 VDI 裝置。


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
