---
title: '透過模擬攻擊體驗 Microsoft Defender for Endpoint (MDE) '
description: 試驗您的 Microsoft 365 Defender 試用實驗室或試驗環境。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457824"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a>透過模擬攻擊體驗 Microsoft Defender for Endpoint (MDE) 

>[!TIP]
>
>- 深入瞭解 Microsoft Defender for Endpoint 中的最新增強功能： [端點的新](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)功能
>- 在最近的 MITRE 評估中，以試用版的端點示範業界一流的光學器件和偵測功能。 讀取：[從 MITRE ATT 中 Insights&以 CK 為基礎的評估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

您可能想要在將許多裝置上架到服務之前，體驗端點的 Defender。 若要這麼做，您可以在一些測試裝置上執行受控制的攻擊模擬。 在執行模擬後的攻擊之後，您可以查看 Endpoint 的 Endpoint 面對惡意活動的反應，以及如何啟用有效的回應。

## <a name="before-you-begin"></a>開始之前

若要執行提供的任何模擬，您至少需要 [一個架裝置](onboard-configure.md)。

閱讀每個攻擊案例中提供的逐步檔。 每個檔都包括作業系統和應用程式需求，以及針對攻擊案例的詳細指示。

## <a name="run-a-simulation"></a>執行模擬

1. 在 **[** 說明  >  **模擬 & 教學** 課程] 中，選取您要模擬的哪個可用攻擊案例：

   - **案例1：檔丟掉後門** -模擬 socially 工程的引誘檔的傳遞。 檔會啟動巧盡心思的後門，可提供駭客控制權。

   - **案例2： fileless 進攻中的 PowerShell 腳本** -模擬 fileless 攻擊，其受 PowerShell、showcasing 攻擊面不足和裝置教育偵測惡意記憶體活動的偵測。

   - **案例3：自動化事件回應** -觸發自動調查，它會自動 hunts 及 remediates 違犯的專案，以調整您的事件回應容量。

2. 下載並閱讀您所選案例中提供的對應逐步檔。

3. 流覽以 **協助**  >  **模擬 & 教學** 課程，以下載模擬檔案或複製類比腳本。 您可以選擇在測試裝置上下載檔案或腳本，但這不是必要的。

4. 依照練習檔中的指示，在測試裝置上執行類比檔或腳本。

> [!NOTE]
> 類比檔或腳本模仿攻擊活動，但實際上卻是良性的，且不會損害或損害測試裝置。
>

## <a name="alternate-topic-text"></a>替代主題文字

## <a name="simulate-attack-scenarios"></a>類比攻擊案例

透過連線來執行您自己的攻擊模擬，以使用測試裝置。

您可以使用下列方式模擬攻擊案例：

- 「 [自行執行它」攻擊案例](https://securitycenter.windows.com/tutorials)
- 威脅模擬器

您也可以使用 [高級搜尋](advanced-hunting-overview.md) 查詢資料和 [威脅分析](threat-analytics.md) ，以查看有關新興威脅的報告。

### <a name="do-it-yourself-attack-scenarios"></a>自行攻擊案例

如果您正在尋找預先類比，您可以使用我們「 [自己動手」的攻擊案例](https://securitycenter.windows.com/tutorials)。 這些腳本是安全、有記錄且便於使用。 這些案例會反映 Defender 的端點功能，並引導您完成調查經驗。

>[!NOTE]
>使用 RDP 進行與測試裝置的連線。 請確定您的防火牆設定允許 RDP 連線。

1. 連線裝置，並選取 **連線** 以執行攻擊模擬。

    ![測試裝置的 [連接] 按鈕影像](images/test-machine-table.png)

2. 選取 [**連線**] 以儲存 RDP 檔案並加以啟動。

    ![遠端桌面連線的影像](images/remote-connection.png)

    >[!NOTE]
    >如果您沒有在初始設定期間儲存的密碼複本，您可以從功能表中選取 [ **重設密碼** ] 以重設密碼： ![ 重設密碼的影像](images/reset-password-test-machine.png)
    >
    > 裝置會將其狀態變更為「執行重新設定密碼」，然後您會在幾分鐘內看到新的密碼。

3. 輸入在裝置建立步驟中顯示的密碼。

   ![輸入認證的視窗影像](images/enter-password.png)

4. 在裝置上執行自行攻擊模擬。

### <a name="threat-simulator-scenarios"></a>威脅模擬器案例

如果您選擇在實驗室設定期間安裝任何受支援的威脅模擬器，您可以在評估實驗室裝置上執行內建模擬。

使用協力廠商平臺執行威脅模擬是一種很好的方法，可以在實驗室環境的範圍內評估 Microsoft Defender for Endpoint 功能。

>[!NOTE]
>
>在您可以執行模擬之前，請確定符合下列需求：

>- 裝置必須新增至評估實驗室
>- 威脅模擬器必須安裝在評估實驗室中

1. 從入口網站選取 [ **建立類比**]。

2. 選取威脅模擬器。

    ![威脅模擬器選取專案的影像](images/select-simulator.png)

3. 選擇類比或查看類比圖庫，以流覽可用模擬。

    您可以從下列專案進入類比庫：
    - **模擬一覽表** 磚中的主要評估儀表板或
    - 透過流覽流覽窗格 **評估與示教**  >  **類比 & 教學** 課程，然後選取 [**模擬目錄**]。

4. 選取您要在其中執行模擬的裝置。

5. 選取 [ **建立類比**]。

6. 選取 [ **模擬** ] 索引標籤，以查看模擬的進度。查看類比狀態、作用中警示和其他詳細資料。

    ![模擬的影像索引標籤](images/simulations-tab.png)
<br>

執行模擬後，我們鼓勵您逐步完成實驗室進度列，並探索 **Microsoft Defender For Endpoint 會觸發自動調查和修正**。 查看由功能收集及分析的證據。

使用豐富的查詢語言和原始遙測，並查看在威脅分析中所記錄的一些世界範圍威脅，以透過「高級搜尋」搜尋攻擊證據。
