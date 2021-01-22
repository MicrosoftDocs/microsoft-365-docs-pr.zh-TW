---
title: 評估 Microsoft 365 Defender
description: 設定您的 Microsoft 365 Defender 試用版實驗室或試驗環境，以嘗試並體驗專為保護貴組織中裝置、身分識別、資料和應用程式所設計的安全性解決方案。
keywords: Microsoft 威脅防護試用版，試用 Microsoft 威脅防護，評估 Microsoft 威脅防護，Microsoft 威脅防護評估實驗室，Microsoft 威脅防護試驗，網路安全性，進一步持續性威脅，企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930207"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>建立 Microsoft 365 Defender 試用版實驗室或試驗環境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender


本指南可協助您與使用者和群組一起設定實驗室環境，然後引導您完成 Microsoft 365 Defender 功能設定，以模仿威脅攻擊並取得有意義的試驗結果。 

建立此試驗實驗室或試驗環境的目的是說明全面且整合的 Microsoft 365 Defender 功能。 體驗此智慧型安全性解決方案如何偵測、防止、自動調查及回應貴組織的進一步威脅。 


系統將會引導您完成這些步驟，以根據建議的部署路徑啟動您的 Microsoft 365 Defender 評估。 目標是要協助您將安全性解決方案設定在有試用版帳戶的實驗室環境中，或在具有完整授權之生產環境的試驗環境中。 準備您的試驗實驗室或試驗環境可協助您將安全性作業使用案例呈現給貴組織的決策者。 當您執行完攻擊模擬並滿意結果之後，您可以在貴組織中利用 Microsoft 技術銷售專業人員或專家的協助，在組織中完全部署和運作。 

本指南將可協助您：
- 設定實驗室服務器和電腦
- 設定 Active Directory 與使用者和群組
- 設定 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint，以及 Microsoft Cloud App 安全性
- 設定伺服器和電腦的本地策略
- 在 Microsoft 365 Defender 中模仿威脅攻擊來產生測試事件或警示

>[!IMPORTANT]
>為獲得最佳結果，請盡可能遵循實驗室設定指示。


## <a name="deployment-phases"></a>部署階段

建立 Microsoft 365 Defender 試用版實驗室環境有三個階段。

![部署階段：準備、設定、上機](../../media/evaluation-guide-phases.png)

|階段 | 說明 | 
|:-------|:-----|
|[階段 1：準備](prepare-mtpeval.md)| 瞭解在試驗室或試驗環境中部署 Microsoft 365 Defender 時需考慮哪些專案： <br><br>- 專案關係人與簽簽 <br> - 環境考慮 <br>- Access <br>- Azure Active Directory 設定 <br> - 組組順序
|[階段 2：設定](setup-mtpeval.md)|  採取初始步驟來存取 Microsoft 365 資訊安全中心，以設定您的 Microsoft 365 Defender 試用版實驗室或試驗環境。 系統將會引導您進行：<br><br>- 註冊 Microsoft 365 E5 試用版 <br>  - 設定網域<br>- 指派 Microsoft 365 E5 授權<br>- 完成入口網站中的設定精靈|
|[階段 3：設定&上](config-mtpeval.md) | 設定每個 Microsoft 365 Defender 基礎和上線端點。 系統將會引導您進行：<br><br>- 設定 Office 365 的 Microsoft Defender<br>- 設定 Microsoft Cloud App 安全性<br>- 設定 Microsoft Defender 的身分識別<br>- 設定 Microsoft Defender 端點


完成本指南之後，您將識別出涉及的關係人並取得所需的核准、擁有正確的存取權限、已註冊試用版、已設好網域和每個 Microsoft 365 Defender 基礎，您的端點就會上線至服務。

## <a name="key-capabilities"></a>主要功能

雖然 Microsoft 365 Defender 提供許多功能，但本部署指南的主要用途是引導您上線裝置。 除了上手之外，此指引還可引導您開始使用下列功能。


功能 | 描述 
:---|:---
適用於 Office 365 的 Microsoft Defender | 協助保護您的整個 Office 365 服務不受現今的威脅
適用於身分識別的 Microsoft Defender | 識別並偵測身分識別遭到入侵和惡意測試人員動作的威脅。
Microsoft Cloud App Security | 提供豐富的可見度、控制資料旅行，以及偵測雲端服務中的網路威脅。
適用於端點的 Microsoft Defender | 以完整的端點安全性防止、偵測進一步威脅並提供回應功能。


## <a name="in-scope"></a>範圍中

本指南將說明下列工作：
-   設定 Azure Active Directory
-   設定 Microsoft 365 Defender
    -   註冊 Microsoft 365 E5 試用版，或如果您執行試驗，請使用您的完整授權
    -   設定網域
    -   指派 Microsoft 365 E5 授權
    -   完成入口網站中的設定精靈
-   根據最佳做法設定所有 Microsoft 365 Defender 基礎
    -   適用於 Office 365 的 Microsoft Defender
    -   適用於身分識別的 Microsoft Defender
    -   Microsoft Cloud App Security
    -   適用於端點的 Microsoft Defender

## <a name="out-of-scope"></a>超出範圍

以下是本部署指南的範圍外：

-   可能與 Microsoft 365 Defender 整合的協力廠商解決方案組配置
-   生產環境中的測試測試

## <a name="next-step"></a>下一步
[階段 1：準備](prepare-mtpeval.md) 
<br> 準備您的 Microsoft 365 Defender 試用版實驗室或試驗環境
