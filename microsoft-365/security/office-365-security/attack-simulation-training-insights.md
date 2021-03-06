---
title: 透過攻擊模擬訓練取得深入解析
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解 Microsoft 365 Defender 入口網站中的攻擊模擬訓練如何影響員工，以及如何從類比和訓練結果取得深入瞭解。
ms.technology: mdo
ms.openlocfilehash: e189864a42d025bb5ce720a6edb6c1c2c8c84623
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878373"
---
# <a name="gain-insights-through-attack-simulation-training"></a>透過攻擊模擬訓練取得深入解析

**適用** 于 [Office 365 方案2的 Microsoft Defender](defender-for-office-365.md)

在攻擊模擬訓練中，Microsoft 會根據員工所經歷之類比和訓練的結果，提供深入的見解。 這些真知灼見會協助您及時瞭解員工的威脅準備工作進度，並建議您在後續步驟中，更好地準備員工和您的環境以進行攻擊。

我們不斷努力擴充您可以使用的洞察力。 目前可使用行為影響及建議的動作。 [在 Microsoft 365 Defender 入口網站中開始，以攻擊模擬訓練](https://security.microsoft.com/attacksimulator?viewid=overview)。

## <a name="behavior-impact-on-compromise-rate"></a>對折衷率影響的行為影響

在攻擊模擬訓練的 [ **一覽表** ] 索引標籤上，您會發現 **影響折衷率** 卡片的行為。 這張卡片顯示員工如何處理您所執行的類比，與所 **預測的折衷率** 相對。 您可以使用這些洞察力，針對相同員工群組執行多個模擬，以追蹤員工威脅準備工作的進度。

您可以在圖形中看到下列專案：

- **預測的折衷率**，反映使用相同類型的負載進行模擬的平均威脅率，在其他使用攻擊模擬訓練的 Microsoft 365 承租人中。
- **實際的折衷率** 反映的是類比的員工百分比。

此外，還 `<number> less susceptible to phishing` 反映實際的員工數目與受攻擊損害率和預測的折衷率之間的差異。 此員工人數會因未來的類似攻擊而遭到攻破，同時也會 `<percent%> better than predicted rate` 指出員工相對於預測的折衷率的整體效果。

> [!div class="mx-imgBorder"]
> ![攻擊類比訓練上的行為影響卡片](../../media/attack-sim-preview-behavior-impact-card.png)

若要查看更詳細的報告，請按一下 [ **View 模擬和訓練 efficacy 報告**]。 這個報告提供與類比本身的其他內容相同的資訊 (例如，類比技術和以) 為目標的使用者總數。

## <a name="recommended-actions"></a>建議的動作

在 [ [**模擬** ]](https://security.microsoft.com/attacksimulator?viewid=simulations)索引標籤上，選取類比會帶您前往類比詳細資料，您可以在其中找到 [ **建議的動作** ] 區段。

建議的動作區段會詳細說明 [Microsoft 安全分數](../defender/microsoft-secure-score.md)中提供的建議。 這些建議是以類比中所使用的負載為基礎，可協助您保護員工和您的環境。 按一下每個改進動作會將您帶到其詳細資料。

> [!div class="mx-imgBorder"]
> ![攻擊模擬訓練的建議動作區段](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>相關連結

[開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)

[建立網路釣魚攻擊模擬](attack-simulation-training.md)

[建立訓練給您人員的負載](attack-simulation-training-payloads.md)
