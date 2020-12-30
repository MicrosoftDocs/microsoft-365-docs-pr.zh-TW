---
title: 追蹤您的 Microsoft 安全分數記錄並符合目標
description: 深入瞭解已影響 Microsoft 安全分數的活動。 探索趨勢及設定目標。
keywords: microsoft 安全分數、安全分數、office 365 安全分數、microsoft security 得分、microsoft 365 安全性中心、改進動作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: ed937c90bbc6875ee3d72f710d5ac11d4069cbb6
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738040"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>追蹤您的 Microsoft 安全分數記錄並符合目標

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure 得分](microsoft-secure-score.md) 是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。 可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>深入瞭解已影響分數的活動

在 [ **記錄** ] 索引標籤中，透過一段時間來查看組織的分數圖表。

在圖形下方，會列出所選時間範圍內所執行的所有動作及其屬性，例如結果點和類別。 您可以自訂日期範圍及依類別篩選。

![活動歷程記錄](../../media/secure-score/secure-score-history-activity.png)

如果您選取與活動相關聯的 [改進] 動作，就會出現 [完整的「改進動作」快顯視窗。

若要查看該特定 [改進] 動作的所有歷史記錄，請選取浮出控制項中的 [歷程記錄] 連結。

![改進動作歷程記錄](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>探索趨勢及設定目標

在 [ **度量 & 趨勢** ] 索引標籤中，有數個圖形可讓您更深入的趨勢及設定目標。 您可以設定整個視覺效果頁面的日期範圍。 視覺化效果包括：

* **您的安全分數區域** 自訂取決於您組織的目標和「良好」、「良好」和「不良得分」範圍的定義。
* **回歸趨勢** -因設定、使用者或裝置變更而 regressed 之點的時程表。  
* **比較趨勢** -組織的安全分數與其他時間的比較方式。 此視圖可以包含表示具有類似座位元數目之組織之分數平均的行，以及您可以設定的自訂比較視圖。
* **風險接受趨勢** -標示為「風險已接受」之改進動作的時程表。
* **得分變更** -已取得的點數，點 regressed，以及您在指定的日期範圍內對評分所做的變更。

### <a name="compare-your-score-to-organizations-like-yours"></a>比較您的分數與您的組織

有兩個地方可以查看您的分數如何與您的組織類似。 在這兩個圖表中，您可以選取 [ **管理比較** ]，以查看及編輯組織的資訊。 您也可以根據行業、組織大小、授權及地區建立自訂比較。

#### <a name="comparison-bar-chart"></a>比較橫條圖

比較橫條圖是 [ **一覽** ] 索引標籤。將游標移至圖表上方，以查看分數和排名機會。 比較資料是匿名，因此我們不會確切知道混合中有哪些其他租使用者。

![類似組織分數的柱狀圖圖表](../../media/secure-score/secure-score-comparison-bar.png)

- **像您這樣的組織**：另一個承租人 (的平均分數，前提是我們至少有五個以上的承租人可比較符合下列準則的) ：
    1. 相同的行業
    2. 相同的組織規模
    3. 所有地區
    4. 使用的 Microsoft 產品的80% 類似
    5. 在您的租使用者的20% 範圍內，目前的授權) 可取得的機會 (最大分數。

- **自訂比較**：若要設定，必須選取 [依下列準則 **管理比較** ]：
    1. 選取的工業 (s) 
    2. 選取的組織大小 (s) 
    3. 選取的區域 (s) 
    4. 選取的授權 (s) 
    5. 使用的 Microsoft 產品的80% 類似
    6. 在您的租使用者的20% 範圍內，目前的授權) 可取得的機會 (最大分數。

如果您已做自訂的選取範圍，但結果所包含的其他租使用者少於五個其他租使用者，您將會看到「因數據有限而無法使用」。

#### <a name="comparison-trend"></a>比較趨勢

在 [ **度量 & 趨勢** ] 索引標籤上，查看組織的安全性分數如何與其他時間比較。

![隨時間的類似組織分數的折線圖](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>我們想知道您的想法

如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。 我們正在監視社區，並會提供協助。

## <a name="related-resources"></a>相關資源

- [Microsoft 安全評分概述](microsoft-secure-score.md)
- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
- [新功能](microsoft-secure-score-whats-new.md)
