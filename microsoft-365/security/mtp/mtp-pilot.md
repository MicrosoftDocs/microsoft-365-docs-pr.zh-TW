---
title: 執行試驗 Microsoft 威脅防護專案
description: 在生產環境中執行試驗 Microsoft 威脅防護專案，以有效判斷 Microsoft 威脅防護 (MTP) 的優點和採用方式。
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 88d92558d86e0aa2e90ef04d88a3cd4676386f15
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195624"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>執行試驗 Microsoft 威脅防護專案 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

若要有效判斷 Microsoft 威脅防護 (MTP) 的優點和採用方式，您可以執行試驗專案。 在實際執行環境中啟用 Microsoft 威脅防護，並以定義的使用案例開始之前，最好先進行規劃，以判斷必須在此試驗專案中完成的工作，以及成功的準則。 


## <a name="how-to-use-this-pilot-playbook"></a>如何使用本次試驗行動手冊

本指南概括說明 Microsoft 威脅防護，以及如何設定試驗專案的逐步指導方針。 

![執行 Microsoft 威脅防護試驗的階段](../../media/pilotphases.png)

下列範例時程表視您環境中的適當資源而異。 有些偵測和工作流程可能需要比其他的更多學習時間。

![執行 Microsoft 威脅防護試驗的範例時程表](../../media/pilotimeline.png)

>[!IMPORTANT]
>為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。


### <a name="pilot-playbook-phases"></a>試驗行動手冊階段 

執行 Microsoft 威脅防護試驗有四個階段：

|階段 | 描述 | 
|:-------|:-----|
| ![規劃](../../media/mtp/plan.png)<br>[規劃](mtp-pilot-plan.md)| 深入瞭解在執行 Microsoft 威脅防護試驗專案之前，您需要考慮的事項： <br><br>-範圍 <br> -使用案例 <br>- 需求： <br>-測試計劃 <br> -成功準則 <br> -計分卡 
| ![製備](../../media/prepare.png) <br>[製備](mtp-evaluation.md)|  存取 Microsoft 365 的安全性中心以設定您的 Microsoft 威脅防護試驗環境。 您將會得到指導：<br><br>-識別利益關係人，並尋找您試驗的登出 <br> -環境考慮 <br>-Access <br>-Azure Active Directory 安裝程式 <br> -設定順序 <br> -註冊 Microsoft 365 E5 試用版 <br> -設定網域 <br>-指派 Microsoft 365 E5 授權 <br> -完成入口網站中的設定向導|
| ![攻擊模擬](../../media/mtp/run-sim.png) <br>[攻擊模擬](mtp-pilot-simulate.md) | 若要模擬攻擊，您將會得到下列指導：<br><br>-確認測試環境需求 <br>-執行模擬 <br>-調查事件 <br>-解決事件 
| ![關閉及摘要](../../media/mtp/close.png) <br>[關閉及摘要](mtp-pilot-close.md) | 當您已到達程式的結尾時，系統會將您導向：<br><br>-流覽您的最後一個輸出<br>-向您的專案關係人呈現您的輸出 <br>-提供意見反應 <br>-執行後續步驟 

## <a name="next-step"></a>下一步
|![規劃階段](../../media/mtp/plan.png) <br>[規劃階段](mtp-pilot-plan.md) | 規劃 Microsoft 威脅防護試驗專案 
|:-------|:-----|
