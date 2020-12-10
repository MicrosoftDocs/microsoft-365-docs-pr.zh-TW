---
title: 透過攻擊模擬訓練取得深入解析
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 瞭解 Microsoft 365 security center 中的攻擊模擬訓練如何影響員工，以及如何深入瞭解類比和訓練結果。
ms.openlocfilehash: 772815add47d2e0a61187f2d687ff047a4de9c31
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615177"
---
# <a name="gain-insights-through-attack-simulation-training"></a>透過攻擊模擬訓練取得深入解析

在攻擊模擬訓練中，Microsoft 會根據類比和員工的結果，為您提供真知灼見。 這些真知灼見會協助您告訴您員工在威脅準備時所進行的進度，以及建議的後續步驟，以更好地準備員工和您的環境以進行攻擊。

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

我們連續致力於擴大可供您使用的洞察力，並提供目前可用的行為影響和建議動作。
若要開始，請 [在 Microsoft 365 的安全性中心進行攻擊模擬訓練](https://security.microsoft.com/attacksimulator?viewid=overview)。

## <a name="behavior-impact-on-compromise-rate"></a>對折衷率影響的行為影響

在 [攻擊模擬訓練] **概述** ] 索引標籤上，您會發現 **影響安全比率** 卡片的行為。 這張卡片顯示員工如何處理類比，與所 **預測的折衷率** 相對。 您可以使用這些洞察力，針對相同員工群組執行多個模擬，以追蹤員工威脅準備工作的進度。

您可以在圖形中看到下列專案：

- **預測的折衷率** ，反映使用「攻擊模擬訓練」跨承租人的相同類型負載進行模擬的平均威脅率。
- **實際的折衷率** 反映的是類比的員工百分比。

此外，還 `<number> less susceptible to phishing` 反映實際的員工數目與受攻擊損害率和預測的折衷率之間的差異。 此員工人數會因未來的類似攻擊而遭到攻破，同時也會 `<percent%> better than predicted rate` 指出員工相對於預測的折衷率的整體效果。

> [!div class="mx-imgBorder"]
> ![攻擊類比訓練上的行為影響卡片](../../media/attack-sim-preview-behavior-impact-card.png)

若要查看更詳細的報告，請按一下 [ **View 模擬和訓練 efficacy] 報告** ，它會提供與類比本身的其他內容相同的資訊，例如類比技術和目標使用者總數。

## <a name="recommended-actions"></a>建議的動作

在 [ [**模擬** ]](https://security.microsoft.com/attacksimulator?viewid=simulations)索引標籤上，選取任何模擬會將您帶到模擬的詳細資料。 在這裡您會看到 [ **建議的動作** ] 區段。

建議的動作區段會詳細說明 [Microsoft 安全分數](../mtp/microsoft-secure-score.md)中提供的建議。 這些建議是以類比中所使用的負載為基礎，可協助您保護員工和您的環境。 按一下每個改進動作會將您帶到其詳細資料。

> [!div class="mx-imgBorder"]
> ![攻擊模擬訓練的建議動作區段](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>相關連結

**攻擊模擬** 程式 [建立網路釣魚攻擊模擬](attack-simulation-training.md) ，並 [建立用於訓練人員的負載](attack-simulation-training-payloads.md)
