---
title: 評估 Microsoft 威脅防護
description: 設定您的 Microsoft 威脅防護試用實驗室或試驗環境，以嘗試如何設計用來保護裝置、身分識別、資料和應用程式的協同威脅防護解決方案，可協助您的組織
keywords: Microsoft 威脅防護試用版，請嘗試 Microsoft 威脅防護，評估 Microsoft 威脅防護，Microsoft 威脅防護實驗，Microsoft 威脅防護試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 202a5900dedece865f1aa328735477293a8a19c0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201768"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>建立 Microsoft 威脅防護試用實驗室或試驗環境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

建立此試用實驗室或試驗環境的目的，是為了示範 Microsoft 威脅防護的綜合、整合及智慧功能，可在組織中使用偵測、防護、調查和回應。 

本指南會逐步引導您逐步開始 Microsoft 威脅防護評估，以建議的部署路徑為基礎。 目標是在使用試用帳戶時，或在使用完整授權時在實際執行環境中，協助您設定實驗室環境中的整合式 Microsoft 威脅防護服務。 在您的組織中提供安全性作業使用案例給安全性解決方案決策者時，其結果將十分有用。 當您執行攻擊模擬後，如果結果符合，您可以使用 Microsoft 技術銷售人員或組織中的專家的協助，在組織中完整部署及 operationalize。 

本指南將協助您：
- 設定實驗室服務器和電腦
- 使用使用者和群組設定 Active Directory
- 安裝和設定 Azure ATP、Office ATP、Microsoft Defender ATP 和 Microsoft Cloud App Security
- 設定伺服器和電腦的本機原則
- 模仿威脅攻擊，以在 Microsoft 威脅防護中產生測試事件或警示

>[!IMPORTANT]
>為了獲得最佳結果，請盡可能遵循實驗室設定指示。


## <a name="deployment-phases"></a>部署階段

建立 Microsoft 威脅防護試用實驗室環境並部署它時，有三個階段：

|階段 | 描述 | 
|:-------|:-----|
| ![階段1：準備](../../media/prepare.png)<br>[階段1：準備](prepare-mtpeval.md)| 深入瞭解在試用實驗室或試驗環境中部署 Microsoft 威脅防護時，需要考慮的事項： <br><br>-專案關係人和簽核關 <br> -環境考慮 <br>-Access <br>-Azure Active Directory 安裝程式 <br> -設定順序
|  ![階段2：設定](../../media/setup.png) <br>[階段2：設定](setup-mtpeval.md)|  請先取得存取 Microsoft 365 安全中心的初始步驟，以設定您的 Microsoft 威脅防護試用實驗室或試驗環境。 您將會指導您：<br><br>-註冊 Microsoft 365 E5 試用版 <br>  -設定網域<br>-指派 Microsoft 365 E5 授權<br>-完成入口網站中的設定向導|
|  ![階段3：設定板載 &](../../media/config-onboard.png) <br>[階段3：設定板載 &](config-mtpeval.md) | 設定每個 Microsoft 威脅防護 pillar 和板載端點。 您將會指導您：<br><br>-設定 Office 365 的高級威脅防護<br>-設定 Microsoft Cloud App Security<br>-設定 Azure 高級威脅防護<br>-設定 Microsoft Defender 高級威脅防護 


## <a name="in-scope"></a>在範圍內

下列工作位於此指南的範圍內：
-   設定 Azure Active Directory
-   設定 Microsoft 威脅防護
    -   註冊 Microsoft 365 E5 試用版，如果您正在執行試驗，請使用您的完整授權
    -   設定網域
    -   指派 Microsoft 365 E5 授權
    -   在入口網站中完成安裝精靈
-   根據最佳作法設定所有 Microsoft 威脅防護支柱
    -   Office 365 進階威脅防護
    -   Azure 進階威脅防護
    -   Microsoft Cloud App Security
    -   Microsoft Defender 進階威脅防護

## <a name="out-of-scope"></a>超出範圍

下列專案不在本部署指南的範圍內：

-   設定可能會與 Microsoft 威脅防護整合的協力廠商解決方案
-   實際執行環境中的滲透測試

## <a name="next-step"></a>下一步
![階段1：準備](../../media/prepare.png) <br>[階段1：準備](prepare-mtpeval.md) 
<br> 準備您的 Microsoft 威脅防護試用實驗室或試驗環境
