---
title: 'Windows 10 裝置的上架工具和方法 (預覽) '
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
description: 板載 Windows 10 裝置，讓他們可以將感應器資料傳送至 Microsoft 365 合規性解決方案
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769640"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Windows 10 裝置的上架工具和方法 (預覽) 

適用於： 
- [Microsoft 365 端點資料遺失防護 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)

您組織中的裝置必須設定，Microsoft 365 端點資料遺失防護服務才能從這些裝置取得感應器資料。 您可以使用各種方法和部署工具來設定組織中的裝置。

下列為支援的部署工具及方法：

- 群組原則
- Microsoft Endpoint Configuration Manager
- 行動裝置管理 (包括 Microsoft Intune) 
- 本機腳本

## <a name="in-this-section"></a>本節內容
主題 | 描述
:---|:---
[使用群組原則的板載 Windows 10 裝置](dlp-configure-endpoints-gp.md) | 使用群組原則在裝置上部署設定套件。
[使用 Microsoft Endpoint Configuration Manager 的板載 Windows 裝置](dlp-configure-endpoints-sccm.md) | 您可以使用 Microsoft 端點 Configuration Manager (目前的分支) 版本1606或 Microsoft 端點 Configuration Manager (電流分支) 版本1602或更早版本，以在裝置上部署設定套件。
[使用行動裝置管理工具的板載 Windows 10 裝置](dlp-configure-endpoints-mdm.md) | 使用行動裝置管理工具或 Microsoft Intune 在裝置上部署設定套件。
[使用本機腳本的板載 Windows 10 裝置](dlp-configure-endpoints-script.md) | 瞭解如何使用本機腳本，在端點上部署設定套件。
[板載非持久性虛擬桌面基礎結構 (VDI) 裝置](dlp-configure-endpoints-vdi.md) | 瞭解如何使用 configuration 套件來設定 VDI 裝置。