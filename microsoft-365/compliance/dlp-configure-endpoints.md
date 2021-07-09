---
title: Windows 10 裝置的上架方法及工具
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 板載 Windows 10 裝置，使其可將感應器資料傳送至 Microsoft 365 規範解決方案
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341697"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Windows 10 裝置的上線工具及方法

**適用於：**
- [Microsoft 365端點資料遺失防護 (DLP) ](./endpoint-dlp-learn-about.md)

您組織中的裝置必須設定，才能讓 Microsoft 365 端點資料遺失防護服務可以從這些裝置取得感應器資料。 您可以使用各種方法和部署工具來設定組織中的裝置。

下列為支援的部署工具及方法：

- 群組原則
- Microsoft Endpoint Configuration Manager
- 行動裝置管理 (包括 Microsoft Intune) 
- 本機腳本

## <a name="in-this-section"></a>本節內容
主題 | 描述
:---|:---
[使用群組原則的板載 Windows 10 裝置](dlp-configure-endpoints-gp.md) | 使用群組原則在裝置上部署設定套件。
[使用 Microsoft Endpoint Configuration Manager 的板載 Windows 裝置](dlp-configure-endpoints-sccm.md) | 您可以使用 Microsoft Endpoint Configuration Manager (目前的分支) 版本1606或 Microsoft Endpoint Configuration Manager (目前的分支) 版本1602或更早版本，以在裝置上部署設定套件。
[使用行動裝置管理工具上線 Windows 10 電腦](dlp-configure-endpoints-mdm.md) | 使用行動裝置管理工具或 Microsoft Intune，在裝置上部署設定套件。
[使用本機指令碼上線 Windows 10 裝置](dlp-configure-endpoints-script.md) | 瞭解如何使用本機腳本，在端點上部署設定套件。
[上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](dlp-configure-endpoints-vdi.md) | 瞭解如何使用 configuration 套件來設定 VDI 裝置。