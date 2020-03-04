---
title: 部署 Microsoft 威脅防護所支援的服務
description: 了解可由 Microsoft 威脅防護、 其授權需求，以及部署程序整合的 Microsoft 安全性服務
keywords: 部署、 授權、 支援的服務，佈建，設定 Microsoft 威脅防護，M365，授權資格，Microsoft Defender ATP、 MDATP、 Office 365 ATP、 Azure ATP、 Microsoft Cloud App Security、 MCAS，進階威脅防護，E5、 A5、 EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b19907517f94cc8b6dbf041cccf56f1d8e232f2f
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374201"
---
# <a name="deploy-supported-services"></a>部署支援服務

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 威脅防護](microsoft-threat-protection.md)整合不同的 Microsoft 安全性服務，以提供集中式的偵測、 預防和複雜的攻擊的調查功能。 本文說明支援的服務，其授權需求、 的優點與限制與部署方式您可以完全予以部署個別的一或多個服務，以及連結相關聯。

## <a name="supported-services"></a>支援的服務
[Microsoft 365 E5、 E5 安全性、 A5，或 A5 安全性或有效的授權組合](prerequisites.md#licensing-requirements)提供下列存取支援的服務和賦與您在 Microsoft 365 安全性中心中使用 Microsoft 威脅防護。

| 支援的服務 | 說明 |
| ------ | ------ |
| Microsoft Defender ATP | 內建功能強大的行為感應、 雲端分析和威脅情報周圍的端點保護套件 |
| Office 365 ATP | 進階的保護您的應用程式和 Office 365，包括電子郵件和其他協同作業工具中的資料 |
| Azure ATP | 針對進階的威脅、 遭入侵的身分識別及惡意內部人員使用的防護措施相互關聯的 Active Directory 訊號 |
| Microsoft Cloud App Security | 識別並 combats cyberthreats 跨 Microsoft 和協力廠商雲端服務 |

## <a name="deployed-services-and-functionality"></a>部署的服務和功能
您在部署更多支援的服務時，Microsoft 威脅防護會提供較佳的可見性、 相互關聯及修復。

### <a name="benefits-of-full-deployment"></a>完整部署的優點
若要取得 Microsoft 威脅防護的完整優點，我們建議部署支援的所有服務。 以下是一些完整部署的主要優點：
- 識別並相互關聯為基礎的警告與從所有可用的感應器與特定服務的分析功能事件訊號事件
- 自動化調查並修復 （空調） playbooks 套用不同的實體類型，包括裝置、 信箱及使用者帳戶
- 更多進階的狩獵結構描述可以查詢事件及實體資料從裝置、 信箱及其他實體

### <a name="limited-deployment-scenarios"></a>有限的部署案例
每個支援的服務，您將部署提供極豐富的未經處理信號，以及相關的資訊。 雖然有限的部署不會造成 Microsoft 威脅防護功能關閉，會影響其能夠跨端點、 應用程式、 資料和身分識別提供完整的可見性。 在此同時，任何修復功能僅適用於您已部署的服務可管理的實體。

下表列出每個支援的服務如何提供額外的資料，相互關聯的資料，並更好的補救和回應功能，以取得額外的深入解析的機會。

| 服務 | 資料 （訊號 & 相互關聯的資訊） | 修復 & 回應範圍 |
| ------ | ------ | ------ |
| Microsoft Defender ATP | -端點狀態和未經處理的事件<br />-端點偵測及警示，包括防毒軟體，EDR，來進行攻擊縮減<br />-檔案和觀察到的端點上其他實體資訊 | 端點 |
| Office 365 ATP | 對郵件的信箱狀態和未經處理的事件<br />-電子郵件附件，並將連結偵測 | 信箱<br />-Office 365 帳戶 |
| Azure ATP | -Active Directory 訊號，包括驗證事件<br />-身分識別相關的行為偵測 | 身分識別 |
| Microsoft Cloud App Security | -偵測的 unsanctioned 的雲端應用程式 & 服務 （陰影 IT）<br />-洩露到雲端的應用程式的資料<br />-威脅活動相關聯的雲端應用程式 | 雲端應用程式 |

## <a name="deploy-the-services"></a>部署服務
部署每個服務通常需要對您的租用戶與某些初始設定佈建。 請參閱下表以了解每個這些服務的部署方式。

| 服務 | 佈建的指示 | 初始設定 |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [驗證授權佈建和設定的設定完成 Microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/licensing) | *請參閱佈建指示* |
| Office 365 ATP | *無使用 Office 365 佈建* | [設定 ATP 原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [快速入門： 建立您的 Azure ATP 執行個體](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *請參閱佈建指示* |
| Microsoft Cloud App Security | *無* | [快速入門： 開始使用 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

一旦您已部署支援的服務，[開啟 [Microsoft Threat Protection](mtp-enable.md)。

## <a name="related-topics"></a>相關主題

- [Microsoft 威脅防護概觀](microsoft-threat-protection.md)
- [開啟 Microsoft 威脅防護](mtp-enable.md)
- [Microsoft Defender ATP 概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概觀](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概觀](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概觀](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
