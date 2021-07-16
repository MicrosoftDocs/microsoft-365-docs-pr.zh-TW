---
title: 試驗 Microsoft Defender for Endpoint，設定試用版、評估中的測試功能
description: 瞭解如何對 Microsoft Defender for Endpoint (MDE) 執行試驗，包括驗證試驗群組和嘗試功能。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457606"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>試驗 Microsoft Defender for Endpoint

本文將引導您在執行 Microsoft Defender for Endpoint 的試驗過程中執行。 

使用下列步驟來設定和設定 Microsoft Defender for Endpoint 的試驗。 

![將 Microsoft Defender 身分識別新增至 Defender 評估環境的步驟](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- 步驟 1. 驗證試驗群組
- 步驟 2. 嘗試功能

當您試驗 Microsoft Defender for Endpoint 時，您可以選擇先將一些裝置板載至服務，再上架出整個組織。  

然後您可以嘗試可用的功能，例如執行攻擊模擬，並查看端點的 Defender 如何進行惡意活動，以及如何讓您進行有效的回應。 

## <a name="step-1-verify-pilot-group"></a>步驟 1. 驗證試驗群組
完成 [ [啟用評估](eval-defender-endpoint-enable-eval.md) ] 區段中所述的上架步驟之後，您應該會在大約一小時之後看到裝置庫存清單中的裝置。 

當您看到架裝置時，您就可以繼續嘗試試用功能。 

## <a name="step-2-try-out-capabilities"></a>步驟 2. 嘗試功能
現在，您已完成加入部分裝置，並確認他們已向服務報告，請試用現成可用的強大功能，以熟悉產品。

在試驗過程中，您可以輕鬆開始試用某些功能，以查看產品的動作，而不需要經歷複雜的設定步驟。

讓我們從檢出儀表板開始。

### <a name="view-the-device-inventory"></a>查看裝置庫存
在您的網路中，您可以在設備清查中看到端點、網路裝置和 IoT 裝置清單。 它不僅能為您提供網路中裝置的視圖，也提供有關這些裝置的深入資訊，例如網域、風險層級、作業系統平臺及其他詳細資訊，可讓您更輕鬆地識別最具風險的裝置。

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a>查看威脅與弱點管理儀表板 
威脅和弱點管理可協助您將重點放在組織最緊迫和最高風險的弱點上。 在儀表板中，取得組織公開分數、Microsoft 安全分數的裝置、裝置洩密發佈、主要安全性建議、熱門的安全性建議、熱門的軟體、熱門的修復活動，以及主要公開的裝置資料的高層級視圖。 

### <a name="run-a-simulation"></a>執行模擬
Microsoft Defender for Endpoint 隨附「 [自行「執行」」攻擊案例](https://securitycenter.windows.com/tutorials) ，您可以在試驗裝置上執行。  每個檔都包括作業系統和應用程式需求，以及針對攻擊案例的詳細指示。 這些腳本是安全、有記錄且便於使用。 這些案例會反映 Defender 的端點功能，並引導您完成調查經驗。

若要執行提供的任何模擬，您至少需要 [一個架裝置](../defender-endpoint/onboard-configure.md)。

1. 在 **[** 說明  >  **模擬 & 教學** 課程] 中，選取您要模擬的哪個可用攻擊案例：

   - **案例1：檔丟掉後門** -模擬 socially 工程的引誘檔的傳遞。 檔會啟動巧盡心思的後門，可提供駭客控制權。

   - **案例2： fileless 進攻中的 PowerShell 腳本** -模擬 fileless 攻擊，其受 PowerShell、showcasing 攻擊面不足和裝置教育偵測惡意記憶體活動的偵測。

   - **案例3：自動化事件回應** -觸發自動調查，它會自動 hunts 及 remediates 違犯的專案，以調整您的事件回應容量。

2. 下載並閱讀您所選案例中提供的對應逐步檔。

3. 流覽以 **協助**  >  **模擬 & 教學** 課程，以下載模擬檔案或複製類比腳本。 您可以選擇在測試裝置上下載檔案或腳本，但這不是必要的。

4. 依照練習檔中的指示，在測試裝置上執行類比檔或腳本。

> [!NOTE]
> 類比檔或腳本模仿攻擊活動，但實際上卻是良性的，且不會損害或損害測試裝置。

## <a name="next-steps"></a>後續步驟
[評估 Microsoft Cloud App Security](eval-defender-mcas-overview.md)

回到概述以 [評估 Microsoft Defender For Endpoint](eval-defender-endpoint-overview.md)

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述