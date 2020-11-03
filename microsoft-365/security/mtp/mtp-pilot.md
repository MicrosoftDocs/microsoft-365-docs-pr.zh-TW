---
title: 執行您的試驗 Microsoft 365 Defender 專案
description: 在生產環境中執行您的試驗 Microsoft 365 Defender 專案，以有效判斷 Microsoft 365 Defender 的優點和採用方式。
keywords: Microsoft 威脅防護試驗，執行試驗 Microsoft 威脅防護專案，評估 Microsoft 威脅防護中的實際執行、Microsoft 威脅防護試驗專案、網路安全性、高級持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查和修正，以及高級搜尋
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 350904022ec86acdbebf109dd5946598643aea83
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843657"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>執行您的試驗 Microsoft 365 Defender 專案 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

若要有效地判斷 Microsoft 365 Defender 的優點和採用方式，您可以執行試驗專案。 在實際執行環境中啟用 Microsoft 365 Defender 並啟動您的使用案例之前，最好要規劃決定要為試驗專案完成的工作，以及設定成功準則。 


## <a name="how-to-use-this-pilot-playbook"></a>如何使用本次試驗行動手冊

本指南概要說明 Microsoft 365 Defender 及如何設定試驗專案的逐步指示。 

Microsoft 365 Defender 是一種整合的後續企業防護套件，其可共同協調各端點、身分識別、電子郵件和應用程式的保護、偵測、防護、調查和回應，以提供複雜攻擊的整合式防護。 這樣做的方式是將下列功能結合到單一安全性解決方案中：
  - Microsoft Defender for Endpoint，Microsoft Defender 高級威脅防護的新名稱 (端點) 
  - Microsoft Defender for Office 365，新的 Office 365 ATP 名稱 (電子郵件)  
  - Microsoft Defender 身分識別，Azure ATP (身分識別的新名稱)  
  - Microsoft Cloud App Security (app) 

![影像 of_Microsoft 365 Defender 解決方案，適用于使用者、Microsoft Defender 身分識別、端點 Microsoft Defender for Endpoint、雲端應用程式、Microsoft Cloud App Security 及 data、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

透過整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以結合 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft Cloud App Security 接收，以及決定威脅的完整範圍和影響、它如何進入環境、其受到影響，以及目前對組織的影響。 Microsoft 365 Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。 如需詳細資訊，請參閱 [Microsoft 365 Defender 概述](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 。

![執行 Microsoft 365 Defender 試驗的階段](../../media/pilotphases.png)

下列範例時程表視您環境中的適當資源而異。 有些偵測和工作流程可能需要比其他的更多學習時間。

![執行 Microsoft 365 Defender 試驗的範例時程表](../../media/pilotimeline.png)

>[!IMPORTANT]
>為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。


### <a name="pilot-playbook-phases"></a>試驗行動手冊階段 

在執行 Microsoft 365 Defender 試驗中有四個階段：

|階段 | 描述 | 
|:-------|:-----|
| ![規劃](../../media/mtp/plan.png)<br>[規劃](mtp-pilot-plan.md)| 深入瞭解在執行 Microsoft 365 Defender 試驗專案之前，您需要考慮的事項： <br><br>-範圍 <br> -使用案例 <br>- 需求： <br>-測試計劃 <br> -成功準則 <br> -計分卡 
| ![製備](../../media/mtp/prep.png) <br>[製備](mtp-evaluation.md)|  存取 Microsoft 365 的安全性中心以設定您的 Microsoft 365 Defender 試驗環境。 您將會指導您：<br><br>-識別利益關係人，並尋找您試驗的登出 <br> -環境考慮 <br>-Access <br>-Azure Active Directory 安裝程式 <br> -設定順序 <br> -註冊 Microsoft 365 E5 試用版 <br> -設定網域 <br>-指派 Microsoft 365 E5 授權 <br> -完成入口網站中的設定向導|
| ![攻擊模擬](../../media/mtp/run-sim.png) <br>[攻擊模擬](mtp-pilot-simulate.md) | 若要模擬攻擊，您將會得到下列指導：<br><br>-確認測試環境需求 <br>-執行模擬 <br>-調查事件 <br>-解決事件 
| ![關閉及摘要](../../media/mtp/close.png) <br>[關閉及摘要](mtp-pilot-close.md) | 當您到達程式的結尾時，系統會將您導向：<br><br>-流覽您的最後一個輸出<br>-向您的專案關係人呈現您的輸出 <br>-提供意見反應 <br>-執行後續步驟 

## <a name="next-step"></a>下一步
|![規劃階段](../../media/mtp/plan.png) <br>[規劃階段](mtp-pilot-plan.md) | 規劃 Microsoft 365 Defender 試驗專案 
|:-------|:-----|
