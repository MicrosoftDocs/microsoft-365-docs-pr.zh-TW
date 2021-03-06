---
title: 評估 Microsoft 365 Defender
description: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境，以嘗試用來保護組織中裝置、身分識別、資料和應用程式的安全性解決方案。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457949"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>建立 Microsoft 365 Defender 試用實驗室或試驗環境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender


本指南可協助您使用使用者和群組設定實驗室環境，然後逐步指導您設定 Microsoft 365 Defender 中的功能，讓您可以模仿威脅攻擊，並取得有意義的試用結果。 

建立此試用實驗室或試驗環境的目的是為了示範綜合和整合式的 Microsoft 365 Defender 功能。 體驗這種聰明的安全性解決方案如何偵測、避免、自動調查，並回應貴組織的高級威脅。 


您將會逐步引導您根據建議的部署路徑開始 Microsoft 365 Defender 評估。 其目標是協助您在實驗環境中設定安全性解決方案，以試用帳戶，或在實際執行環境中使用完整授權。 準備您的試用實驗室或試驗環境可協助您向組織中的決策者展示安全性運作案例。 當您執行攻擊模擬並符合結果時，您可以使用 Microsoft 技術銷售人員或組織中的專家的說明，在組織中完整部署及 operationalize。 

本指南將協助您：
- 設定實驗室服務器和電腦
- 使用使用者和群組設定 Active Directory
- 為身分識別設定及設定 microsoft defender 身分識別、microsoft defender for Office 365、microsoft defender for Endpoint 及 Microsoft Cloud App Security
- 設定伺服器和電腦的本機原則
- 模仿威脅攻擊，以在 Microsoft 365 Defender 產生測試事件或警示

>[!IMPORTANT]
>為了獲得最佳結果，請盡可能遵循實驗室設定指示。


## <a name="deployment-phases"></a>部署階段

建立 Microsoft 365 Defender 試用實驗室環境有三個階段。

![部署階段：準備、安裝、板載](../../media/evaluation-guide-phases.png)

|階段 | 描述 | 
|:-------|:-----|
|[階段 1：準備](prepare-m365d-eval.md)| 深入瞭解在試用實驗室或試驗環境中部署 Microsoft 365 Defender 時，需要考慮的事項： <br><br>-專案關係人和簽核關 <br> -環境考慮 <br>-Access <br>-Azure Active Directory 安裝程式 <br> -設定順序
|[階段 2：設定](setup-m365deval.md)|  採取初始步驟，存取 Microsoft 365 的安全性中心以設定 Microsoft 365 Defender 試用實驗室或試驗環境。 您將會指導您：<br><br>-註冊 Microsoft 365 E5 試用版 <br>  -設定網域<br>-指派 Microsoft 365 E5 授權<br>-完成入口網站中的設定向導|
|[階段3：設定板載 &](config-m365d-eval.md) | 設定每個 Microsoft 365 Defender pillar 和板載端點。 您將會指導您：<br><br>-針對 Office 365 設定 Microsoft Defender<br>-設定 Microsoft Cloud App Security<br>-設定 Microsoft Defender 身分識別<br>-設定 Microsoft Defender for Endpoint


當您完成本指南之後，您將會發現相關的專案關係人和所需核准，具有正確的存取權限，已註冊試用、已設定的網域，以及每個 Microsoft 365 Defender 的支柱，而且您的端點會架至服務。

## <a name="key-capabilities"></a>主要功能

雖然 Microsoft 365 Defender 提供許多功能，但此部署指南的主要目的是讓您開始使用上架裝置。 除了上架之外，本指南也可讓您開始使用下列功能。


功能 | 描述 
:---|:---
適用於 Office 365 的 Microsoft Defender | 協助保護整個 Office 365 從當今的威脅環境
適用於身分識別的 Microsoft Defender | 識別並偵測遭到損害的身分識別和惡意的內幕人員動作威脅。
Microsoft Cloud App Security | 提供豐富的可見度、控制資料旅行，以及偵測不同雲端服務的 cyberthreats。
適用於端點的 Microsoft Defender | 利用全面的端點安全性，防止、偵測及提供對高級威脅的回應功能。


## <a name="in-scope"></a>在範圍內

下列工作位於此指南的範圍內：
-   設定 Azure Active Directory
-   設定 Microsoft 365 Defender
    -   在執行試驗時，註冊 Microsoft 365 E5 試用版或使用您的完整授權
    -   設定網域
    -   指派 Microsoft 365 E5 授權
    -   在入口網站中完成安裝精靈
-   根據最佳作法設定所有 Microsoft 365 Defender 的支柱
    -   適用於 Office 365 的 Microsoft Defender
    -   適用於身分識別的 Microsoft Defender
    -   Microsoft Cloud App Security
    -   適用於端點的 Microsoft Defender

## <a name="out-of-scope"></a>超出範圍

下列專案不在本部署指南的範圍內：

-   設定可能與 Microsoft 365 Defender 整合的協力廠商解決方案
-   實際執行環境中的滲透測試

## <a name="next-step"></a>後續步驟
[階段1：準備](prepare-m365d-eval.md) 
<br> 準備您的 Microsoft 365 Defender 試用實驗室或試驗環境
