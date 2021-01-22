---
title: 追蹤您的 Microsoft 安全分數記錄並達成目標
description: 深入瞭解影響 Microsoft 安全分數的活動。 探索趨勢並設定目標。
keywords: Microsoft 安全分數， 安全分數， Office 365 安全分數， Microsoft 安全性分數， microsoft 365 安全性中心， 改進動作
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: c9af6a3ae6f461acfd2968897223446641d5cf09
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925669"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>追蹤您的 Microsoft 安全分數記錄並達成目標

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft 安全](microsoft-secure-score.md) 分數是組織安全性措施的度量，數位越高，表示已採取更多改進動作。 您可以在 https://security.microsoft.com/securescore [Microsoft 365 資訊安全中心找到。](overview-security-center.md)

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>深入瞭解影響您分數的活動

在歷程記錄中，查看貴組織在一 **段時間中的成績** 圖表。

圖表下方是所選時間範圍內採取的所有動作及其屬性的清單，例如產生的點和類別。 您可以自訂日期範圍，並按類別篩選。

![活動歷程記錄](../../media/secure-score/secure-score-history-activity.png)

如果您選取與活動相關的改進動作，將會顯示完整的改進動作飛出視窗。

若要查看該特定改進動作的所有歷程記錄，請選取飛出區中的歷程記錄連結。

![改進動作記錄](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>探索趨勢並設定目標

在資料 **&** 資料趨勢資料標籤中，有一些圖形和圖表可增強您對於趨勢的可見度並設定目標。 您可以設定視覺效果整頁的日期範圍。 視覺效果包括：

* **您的安全分數** 區域 - 根據貴組織的目的和良好、好壞分數範圍的定義來自訂。
* **回歸趨勢** ： 因組式、使用者或裝置變更而回歸的點時程表。  
* **比較趨勢** - 貴組織的安全分數與其他人一段時間的比較。 此視圖可以包含代表擁有類似座位數之組織的分數平均值的線條，以及您可以設定自訂的比較視圖。
* **風險接受趨勢** - 標示為「接受風險」的改進動作時程表。
* **分數變更** - 已獲得分數、點數已減少，以及分數在指定的日期範圍內變更。

### <a name="compare-your-score-to-organizations-like-yours"></a>比較您的分數與像您這樣的組織

有兩個地方可以比較您的分數與類似組織的比較。 在這兩種圖表中，您可以選取管理 **比較** 來查看和編輯貴組織的資訊。 您也可以根據產業、組織大小、授權和地區建立自訂比較。

#### <a name="comparison-bar-chart"></a>比較橫條圖

比較橫條圖是一個概 **觀按鈕** 。將游標停留在圖表上以查看分數和分數的機會。 比較資料受匿名保護，因此我們不知道混合了哪些其他租使用者。

![類似組織分數的橫條圖](../../media/secure-score/secure-score-comparison-bar.png)

- **像您這樣的** 組織：如果我們至少有五個或五 (租使用者來比較符合下列準則) ，其他租使用者的平均分數：
    1. 同一產業
    2. 相同的組織規模
    3. 所有地區
    4. 使用的 Microsoft 產品有 80% 的類似
    5. 從 (租使用者起 20% 範圍內，目前授權所達成) 商機分數

- **自訂比較**：需要根據下列準則選取 **管理比較** 來設定：
    1. 選取的 (資料) 
    2. 選取的組織 (大小) 
    3. 選取 (區域) 
    4. 已選取 (授權) 
    5. 使用的 Microsoft 產品有 80% 的類似
    6. 從 (租使用者起 20% 範圍內，目前授權所達成) 商機分數

如果您已經自訂選擇，但結果少於五個我們可以比較的其他租使用者，則會看到「由於資料有限而無法使用」。

#### <a name="comparison-trend"></a>比較趨勢

在資料 **&** 資料趨勢中，查看貴組織的安全分數與他人在一段時間中的比較。

![類似組織在一段時間中成績的線條圖](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>我們想知道您的想法

如有任何問題，請張貼在安全性、隱私權和合規性& [告訴我們](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。 我們正在監控社群，並且會為您提供協助。

## <a name="related-resources"></a>相關資源

- [Microsoft 安全分數概觀](microsoft-secure-score.md)
- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
- [新功能](microsoft-secure-score-whats-new.md)
