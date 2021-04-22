---
title: 部署 Microsoft 365 Defender 支援的服務
description: 深入瞭解可由 Microsoft 365 Defender、其授權需求和部署程式整合的 Microsoft 安全服務
keywords: 部署，授權，支援的服務，布建，設定 Microsoft 365 Defender，M365，授權資格，Microsoft Defender for Endpoint，Microsoft Defender for Office 365，Microsoft Defender for Identity，Microsoft Cloud App Security，MCAS，E5，A5，EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
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
ms.openlocfilehash: 4e1b36423974e46a485727f7e1f158dc6163d834
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935674"
---
# <a name="deploy-supported-services"></a>部署支援服務

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) 整合各種 Microsoft 安全服務，以提供集中式偵測、防護和調查功能，以防禦複雜的攻擊。 本文說明支援的服務、其授權需求、與部署一或多項服務相關的優點與限制，以及您可以個別完全部署這些服務的方式連結。

## <a name="supported-services"></a>支援的服務
Microsoft 365 E5，E5 Security，A5，or A5 安全性授權或有效的授權組合，可提供下列支援服務的存取權，以及您在 Microsoft 365 Security center 中使用 Microsoft 365 Defender 的權力。 [請參閱授權需求](prerequisites.md#licensing-requirements)

| 支援的服務 | 描述 |
| ------ | ------ |
| 適用於端點的 Microsoft Defender | 以強大行為感應器、雲端分析和威脅智慧為基礎的 Endpoint protection 套件 |
|適用於 Office 365 的 Microsoft Defender | Office 365 中的應用程式和資料的高級保護，包括電子郵件和其他共同作業工具 |
| 適用於身分識別的 Microsoft Defender | 使用關聯的 Active Directory 信號，防禦高級威脅、遭到破壞的身分識別，以及惡意內幕用。 |
| Microsoft Cloud App Security | 在您的 Microsoft 和協力廠商雲端服務之間識別及打擊 cyberthreats |

## <a name="deployed-services-and-functionality"></a>部署的服務和功能
當您部署更支援的服務時，Microsoft 365 Defender 可提供更好的可見度、關聯性和修正能力。

### <a name="benefits-of-full-deployment"></a>完整部署的優點
為了取得 Microsoft 365 Defender 的完整優點，我們建議您部署所有支援的服務。 以下是完整部署的一些重要優點：
- 事件會根據所有可用的感應器及服務特有的分析功能，以警示和事件信號進行識別和關聯。
- 自動化調查和修正 (空氣) 行動裝置適用于各種實體類型，包括裝置、信箱和使用者帳戶
- 可查詢更完整的高級搜尋架構，以取得來自裝置、信箱及其他實體的事件和實體資料

### <a name="limited-deployment-scenarios"></a>有限的部署案例
您部署的每個支援服務都會提供一組極其豐富的原始信號，以及相關的資訊。 雖然有限的部署不會造成 Microsoft 365 Defender 功能關閉，但在端點、應用程式、資料及身分識別等範圍內，可提供完整的可見度的功能會受到影響。 同時，任何修正功能都只適用于您已部署之服務可管理的實體。

下表列出每個支援的服務如何提供額外的資料、關聯資料，以及更好的修復與回應功能，以取得額外的洞察力。

| 服務 | 資料 (信號 & 相關的資訊)  | 修正 & 回應範圍 |
| ------ | ------ | ------ |
| 適用於端點的 Microsoft Defender | -端點狀態和原始事件<br />-端點偵測和警示，包含防毒程式、EDR、攻擊面降低<br />-在端點上觀察到的檔案及其他實體的資訊 | 端點 |
|適用於 Office 365 的 Microsoft Defender | -郵件和信箱狀態和原始事件<br />-電子郵件、附件及連結偵測 | -信箱<br />-Microsoft 365 帳戶 |
| 適用於身分識別的 Microsoft Defender | -Active Directory 信號，包括驗證事件<br />-身分識別相關的行為偵測 | 身分識別 |
| Microsoft Cloud App Security | -偵測 unsanctioned cloud app and services (shadow) <br />-向雲端應用程式公開資料<br />-Cloud app 相關聯的威脅活動 | 雲端應用程式 |

## <a name="deploy-the-services"></a>部署服務
部署每個服務時，通常需要為您的租使用者和某些初始設定提供布建。 請參閱下表以瞭解各項服務的部署方式。

| 服務 | 布建指示 | 初始設定 |
| ------ | ------ | ------ |
| 適用於端點的 Microsoft Defender | [Microsoft Defender for Endpoint 部署指南](../defender-endpoint/deployment-phases.md) | *請參閱布建指示* |
|適用於 Office 365 的 Microsoft Defender | *無，使用 Office 365 布建* | [設定適用於 Office 365 的 Microsoft Defender 原則](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| 適用於身分識別的 Microsoft Defender | [快速入門：建立您的 Microsoft Defender for Identity 實例](/azure-advanced-threat-protection/install-atp-step1) | *請參閱布建指示* |
| Microsoft Cloud App Security | *無* | [快速入門： Microsoft Cloud App Security 快速入門](/cloud-app-security/getting-started-with-cloud-app-security) |

部署支援的服務之後，請 [開啟 Microsoft 365 Defender](m365d-enable.md)。

## <a name="related-topics"></a>相關主題

- [Microsoft 365 Defender 概述](microsoft-365-defender.md)
- [開啟 Microsoft 365 Defender](m365d-enable.md)
- [Microsoft Defender for Endpoint 簡介](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365 簡介](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security 概觀](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender 身分識別概述](/azure-advanced-threat-protection/what-is-atp)
