---
title: 執行您的試驗 Microsoft 365 Defender 專案
description: 在生產環境中執行試驗 Microsoft 365 Defender 專案，以有效地判斷 Microsoft 365 Defender 的好處和採用。
keywords: Microsoft 威脅防護試驗、執行試驗 Microsoft 威脅防護專案、在生產環境中評估 Microsoft 威脅防護、Microsoft 威脅防護試驗專案、網路安全性、進一步持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋
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
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933027"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>執行您的試驗 Microsoft 365 Defender 專案 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender


本指南可協助執行試驗專案，提供指標以確保您擁有結構良好的計畫、指引您使用受攻擊模擬功能，以及最後結束試驗並移開金鑰，以反映在檔結果上。

![執行 Microsoft 365 Defender 試驗階段](../../media/pilotphases.png)


執行試驗可有效判斷採用 Microsoft 365 Defender 的好處。 在啟用您生產環境中的 Microsoft 365 Defender 並啟動使用案例之前，最好先規劃一下要完成試驗專案的工作，並設定成功準則。 


## <a name="how-to-use-this-pilot-playbook"></a>如何使用此試驗手冊

本指南提供 Microsoft 365 Defender 概觀，以及如何設定試驗專案的逐步指示。 

Microsoft 365 Defender 是一套整合的預先和入侵後企業防護套件，以原生的方式協調端點、身分識別、電子郵件和應用程式的保護、偵測、防護、調查及回應，以提供整合式防護，防範複雜的攻擊。 將下列功能結合並結合成單一安全性解決方案，以這麼做：
  - Microsoft Defender for Endpoint， the new name for Microsoft Defender Advanced Threat Protection (endpoints) 
  - Microsoft Defender for Office 365， the new name for Office 365 ATP (email)  
  - Microsoft Defender for Identity， the new name for Azure ATP (identity)  
  - Microsoft Cloud App 安全性 (應用程式) 

![適用于of_Microsoft使用者 、Microsoft Defender for Endpoint 端點、雲端應用程式、Microsoft Cloud App 安全性及資料之 Microsoft Defender for Office 365 之使用者的 365 Defender 解決方案影像](../../media/mtp/m365pillars.png)

使用整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以整合 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft Cloud App Security 收到的威脅訊號，並判斷威脅的完整範圍和影響、其進入環境方式、影響的範圍，以及目前對組織的影響。 Microsoft 365 Defender 會採取自動動作來防止或停止受攻擊和自我攻擊的信箱、端點和使用者身分識別。 請參閱 [Microsoft 365 Defender 概觀](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 以瞭解詳細資料。



下列範例時程表視您環境中正確的資源而異。 有些偵測和工作流程可能需要比其他偵測和工作流程更多的學習時間。

![執行 Microsoft 365 Defender 試驗的範例時程表](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>為獲得最佳結果，請盡可能遵循試驗指示。


### <a name="pilot-playbook-phases"></a>試驗劇本階段 

執行 Microsoft 365 Defender 試驗有四個階段：

|階段 | 說明 | 
|:-------|:-----|
| [規劃](mtp-pilot-plan.md)<br> ~ 1 天| 瞭解執行 Microsoft 365 Defender 試驗專案前需考慮哪些專案： <br><br>- 範圍 <br> - 使用案例 <br>- 需求： <br>- 測試計劃 <br> - 成功準則 <br> - 計分卡 
| [製備](mtp-evaluation.md) <br>~2 天|  存取 Microsoft 365 資訊安全中心以設定您的 Microsoft 365 Defender 試驗環境。 系統將會引導您進行：<br><br>- 找出專案關係人，並針對您的試驗尋求籤簽 <br> - 環境考慮 <br>- Access <br>- Azure Active Directory 設定 <br> - 組組順序 <br> - 註冊 Microsoft 365 E5 試用版 <br> - 設定網域 <br>- 指派 Microsoft 365 E5 授權 <br> - 完成入口網站中的設定精靈|
| [攻擊模擬](mtp-pilot-simulate.md) <br>~2 天| 若要模擬攻擊，您將受指引到：<br><br>- 確認測試環境需求 <br>- 執行模擬 <br>- 調查事件 <br>- 解決事件 
| [結語和摘要](mtp-pilot-close.md) <br>~ 1 天| 當您已達到程式結尾時，會引導您進行以下操作：<br><br>- 完成最終輸出<br>- 向專案關係人呈現您的輸出 <br>- 提供意見回饋 <br>- 採取下列步驟 

## <a name="next-step"></a>下一步
|[規劃階段](mtp-pilot-plan.md) | 規劃您的 Microsoft 365 Defender 試驗專案 
|:-------|:-----|
