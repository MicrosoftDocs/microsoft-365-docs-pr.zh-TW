---
title: 部署 Microsoft 365 Defender 支援的服務
description: 瞭解 Microsoft 365 Defender 可整合的 Microsoft 安全性服務、其授權需求及部署程式
keywords: 部署、授權、支援服務、提供、組組 Microsoft Threat Protection、M365、授權資格、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、MCAS、Advanced Threat Protection、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928959"
---
# <a name="deploy-supported-services"></a>部署支援服務

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) 整合了各種 Microsoft 安全性服務，針對複雜的攻擊提供集中式偵測、防護與調查功能。 本文說明支援服務、其授權需求、部署一或多個服務的相關優點和限制，以及可如何個別完全部署服務的連結。

## <a name="supported-services"></a>支援服務
Microsoft 365 E5、E5 安全性、A5 或 A5 安全性授權或有效的授權組合可提供下列支援服務的存取權，並可讓您在 Microsoft 365 安全性中心使用 Microsoft 365 Defender。 [請參閱授權需求](prerequisites.md#licensing-requirements)

| 支援的服務 | 說明 |
| ------ | ------ |
| 適用於端點的 Microsoft Defender | 以強大的感應器、雲端分析和威脅情報為內建的端點防護套件 |
|適用於 Office 365 的 Microsoft Defender | 在 Office 365 中針對您的應用程式和資料進一的保護，包括電子郵件和其他共同處理工具 |
| 適用於身分識別的 Microsoft Defender | 使用相關 Active Directory 訊號來防範進位威脅、身分被入侵和惡意的 Insider |
| Microsoft Cloud App Security | 識別並對抗 Microsoft 和協力廠商雲端服務中的網路威脅 |

## <a name="deployed-services-and-functionality"></a>部署的服務和功能
當您部署更多支援服務時，Microsoft 365 Defender 提供更佳的可見度、關聯性與補救功能。

### <a name="benefits-of-full-deployment"></a>完整部署的好處
若要取得 Microsoft 365 Defender 的完整權益，建議您部署所有支援服務。 以下是完整部署的一些主要優點：
- 事件會依據所有可用的感應器和服務特定的分析功能所發出的警示和事件訊號來識別並關聯事件
- AIR 和 AIR (的自動化調查與補救) 適用于各種實體類型，包括裝置、信箱和使用者帳戶
- 您可以針對來自裝置、信箱和其他實體的事件和實體資料查詢更全方位的進位搜尋架構

### <a name="limited-deployment-scenarios"></a>有限的部署案例
您部署的每個支援服務都提供極豐富的原始訊號以及相關資訊。 雖然有限的部署不會讓 Microsoft 365 Defender 功能關閉，但可全面監控端點、應用程式、資料和身分身分的能力會受到影響。 同時，任何補救功能都僅適用于可受您部署之服務管理的實體。

下表列出每個支援的服務如何提供額外的資料、與資料相互關聯以取得其他深入見解的機會，以及更好的補救和回應功能。

| 服務 | 資料 (表示&相關資訊)  | 補救&範圍 |
| ------ | ------ | ------ |
| 適用於端點的 Microsoft Defender | - 端點狀態和原始事件<br />- 端點偵測和警示，包括防毒軟體、EDR、攻擊面縮小<br />- 端點上所觀察之檔案和其他實體的資訊 | 端點 |
|適用於 Office 365 的 Microsoft Defender | - 郵件和信箱狀態及原始事件<br />- 電子郵件、附件和連結偵測 | - 信箱<br />- Microsoft 365 帳戶 |
| 適用於身分識別的 Microsoft Defender | - Active Directory 訊號，包括驗證事件<br />- 身分識別相關檢發偵測 | 身分識別 |
| Microsoft Cloud App Security | - 偵測未檢查的雲端應用程式和服務， (IT) <br />- 將資料曝光到雲端應用程式<br />- 與雲端應用程式相關的威脅活動 | 雲端應用程式 |

## <a name="deploy-the-services"></a>部署服務
部署每個服務通常需要向您的租使用者進行部署，並且需要一些初始群組原則。 請參閱下表以瞭解每個服務的部署方法。

| 服務 | 提供指示 | 初始設定 |
| ------ | ------ | ------ |
| 適用於端點的 Microsoft Defender | [Microsoft Defender 端點部署指南](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *請參閱提供指示* |
|適用於 Office 365 的 Microsoft Defender | *沒有 ，已與 Office 365 一起提供* | [設定適用於 Office 365 的 Microsoft Defender 原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| 適用於身分識別的 Microsoft Defender | [快速入門：建立您的 Microsoft Defender 以用於身分識別實例](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *請參閱提供指示* |
| Microsoft Cloud App Security | *無* | [快速入門：開始使用 Microsoft Cloud App 安全性](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

部署支援服務後，請[開啟 Microsoft 365 Defender。](mtp-enable.md)

## <a name="related-topics"></a>相關主題

- [Microsoft 365 Defender 概觀](microsoft-threat-protection.md)
- [開啟 Microsoft 365 Defender](mtp-enable.md)
- [Microsoft Defender 端點概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 的 Microsoft Defender 概觀](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概觀](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender 身分識別概觀](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
