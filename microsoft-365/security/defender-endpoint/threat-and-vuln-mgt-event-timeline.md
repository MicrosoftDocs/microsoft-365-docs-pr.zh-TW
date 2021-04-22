---
title: 威脅和弱點管理中的事件時程表
description: 事件時程表是一種風險資訊摘要，可協助您解讀組織中的風險被引進方式，以及哪些緩解措施減少。
keywords: 事件時程表，Microsoft Defender for Endpoint 事件時程表，Microsoft Defender for Endpoint tvm 事件時程表，威脅和弱點管理，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933478"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a>事件時程表-威脅和弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

事件時程表是一種危險資訊摘要，可協助您透過新的漏洞或利用手段，協助您解釋風險在組織中的引進方式。 您可以查看可能影響組織風險的事件。 例如，您可以找出已引進的新漏洞、可被攻擊者利用的漏洞、新增至利用方式套件的漏洞，等等。

事件時程表也會告訴您 [暴露分數](tvm-exposure-score.md) 和 [Microsoft 安全評分](tvm-microsoft-secure-score-devices.md) 的情景，以判斷大型變更的原因。 事件可能會影響裝置或您的裝置得分。 根據已設定優先順序的 [安全性建議](tvm-security-recommendation.md)，以降低您的危險性。

>[!TIP]
>若要取得有關新弱點事件的電子郵件，請參閱 [在 Microsoft Defender For Endpoint 中設定弱點電子郵件通知](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-event-timeline-page"></a>流覽至 [事件時程表] 頁面

[威脅和弱點管理儀表板](tvm-dashboard-insights.md)也有三個入門點：

- **組織公開評分**：將滑鼠游標移至 [一段時間的披露分數] 圖表中的事件點上方，然後選取 [查看此天的所有事件]。 事件代表軟體弱點。
- **適用于裝置的 Microsoft 安全計分**：將游標移到 [您的裝置一段時間的分數] 圖表中的事件點上方，然後選取 [查看此天的所有事件]。 事件代表新的設定評估。
- **最上層的事件卡片**：選取上方事件表底部的 [顯示更多]。 這張卡片會顯示過去7天的三個最 impactful 事件。 Impactful 事件可以包含如果事件會影響大量的裝置，或是嚴重缺陷。

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a>裝置圖形的披露分數和 Microsoft 安全評分

在 [威脅與弱點管理] 儀表板中，將游標移到 [曝光分數] 圖上方，以查看該天中影響裝置的主要軟體弱點事件。 將游標移至 [裝置的 Microsoft 安全評分] 圖表，以查看會影響得分的新安全性設定評估。

如果沒有會影響裝置或您的裝置得分的事件，則不會顯示任何事件。

![](images/tvm-event-timeline-exposure-score350.png) 
 ![ 適用于裝置懸停的公開分數懸停 Microsoft 安全分數](images/tvm-event-timeline-device-hover360.png)

### <a name="drill-down-to-events-from-that-day"></a>深入查看該天的事件

選取 [ **顯示此天的所有事件** ] 會帶您前往該天之自訂日期範圍的 [事件時程表] 頁面。

![事件時程表選取的自訂日期範圍](images/tvm-event-timeline-drilldown.png)

選取 [ **自訂範圍** ]，將日期範圍變更為另一個自訂的範圍，或是預先設定的時間範圍。

![事件時程表日期範圍選項](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a>事件時程表概述

在 [事件時程表] 頁面上，您可以查看與事件相關的所有必要資訊。 

功能：

- 自訂欄
- 依事件種類或受影響裝置的百分比篩選
- 每頁 View 30、50或100專案

頁面頂端的兩個大數位會顯示新的漏洞及可攻擊的漏洞數目，而不是事件。 有些事件可能會有多個漏洞，有些漏洞可能會有多個事件。

![事件時程表頁面](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a>Columns

- **Date**： month、day、year
- **事件**： impactful 事件，包含受影響裝置的元件、類型和數目
- **相關元件**：軟體
- 「**原始影響裝置**」：此事件原來發生時，受影響裝置的數目和百分比。 您也可以依原始影響裝置的百分比進行篩選，而不是裝置的總數目。
- **目前受影響的裝置**：此事件目前影響之裝置的目前數量和百分比。 您可以選取 [ **自訂** 欄位] 來找到此欄位。
- **類型**：會反映影響分數的時間戳記事件。 可以篩選它們。
    - 加入利用套件的 exploit
    - 已驗證利用漏洞
    - 新的公開利用方式
    - 新的弱點
    - 新的設定評估
- **分數趨勢**：披露分數趨勢

### <a name="icons"></a>圖示

事件旁會顯示下列圖示：

- ![bug 圖示](images/tvm-black-bug-icon.png) 新的公開利用方式
- ![報告警告圖示](images/report-warning-icon.png) 已發佈新的弱點
- ![exploit 工具組](images/bug-lightning-icon2.png) 在利用方式套件中找到的漏洞
- ![具有警告圖示的 bug 圖示](images/bug-caution-icon2.png) 已驗證利用漏洞

### <a name="drill-down-to-a-specific-event"></a>深入查看特定事件

一旦您選取事件後，就會出現一個快顯視窗，列出會影響裝置的詳細資料和目前 Cve。 您可以顯示更多 Cve 或查看相關的建議。

「分數趨勢」下方的箭號可協助您判斷該事件是否可能升高或降低組織的暴露分數。 暴露程度越高表示裝置變得更容易遭到利用。

![事件時程表浮出控制項](images/tvm-event-timeline-flyout500.png)

從那裡，選取 [ **移至相關安全性建議** ] [ [安全性建議] 頁面](tvm-security-recommendation.md)中的建議，以解決新的軟體弱點。 在安全性建議中讀取描述和弱點詳細資料之後，您可以提交修復要求，並在 [ [修正] 頁面](tvm-remediation.md)中追蹤要求。  

## <a name="view-event-timelines-in-software-pages"></a>在軟體頁面中查看事件時程表

若要開啟 [軟體] 頁面，請選取事件 > 選取 [超連結軟體名稱] (如 [Visual Studio 2017) ] 中的浮出控制項中名為 "相關元件" 的區段中。 [深入瞭解軟體頁面](tvm-software-inventory.md#software-pages)

完整頁面會顯示特定軟體的所有詳細資料。 將滑鼠移到圖形上方，以查看該特定軟體的事件時程表。

![含事件時程表圖形的軟體頁面](images/tvm-event-timeline-software2.png)

流覽至 [事件時程表] 索引標籤，以查看與該軟體相關的所有事件。 您也可以查看安全性建議、發現的漏洞、已安裝的裝置及版本發行。

![含事件時程表索引標籤的軟體頁面](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a>相關主題

- [威脅和弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [儀表板](tvm-dashboard-insights.md)
- [暴險分數](tvm-exposure-score.md)
- [安全性建議](tvm-security-recommendation.md)
- [修正安全性漏洞](tvm-remediation.md)
- [軟體庫存](tvm-software-inventory.md)

