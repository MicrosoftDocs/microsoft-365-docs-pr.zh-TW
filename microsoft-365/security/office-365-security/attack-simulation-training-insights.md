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
ms.openlocfilehash: 6a8ee15f14475a1cebb169ab49bdb0f490c81345
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357348"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="e9b0e-103">透過攻擊模擬訓練取得深入解析</span><span class="sxs-lookup"><span data-stu-id="e9b0e-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="e9b0e-104">在攻擊模擬訓練中，Microsoft 會根據類比和員工的結果，為您提供真知灼見。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="e9b0e-105">這些真知灼見會協助您告訴您員工在威脅準備時所進行的進度，以及建議的後續步驟，以更好地準備員工和您的環境以進行攻擊。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e9b0e-106">我們連續致力於擴大可供您使用的洞察力，並提供目前可用的行為影響和建議動作。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="e9b0e-107">若要開始，請 [在 Microsoft 365 的安全性中心進行攻擊模擬訓練](https://security.microsoft.com/attacksimulator?viewid=overview)。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="e9b0e-108">對折衷率影響的行為影響</span><span class="sxs-lookup"><span data-stu-id="e9b0e-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="e9b0e-109">在 [攻擊模擬訓練] **概述** ] 索引標籤上，您會發現 **影響安全比率** 卡片的行為。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="e9b0e-110">這張卡片顯示員工如何處理類比，與所 **預測的折衷率** 相對。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="e9b0e-111">您可以使用這些洞察力，針對相同員工群組執行多個模擬，以追蹤員工威脅準備工作的進度。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="e9b0e-112">您可以在圖形中看到下列專案：</span><span class="sxs-lookup"><span data-stu-id="e9b0e-112">In the graph you can see:</span></span>

- <span data-ttu-id="e9b0e-113">**預測的折衷率** ，反映使用「攻擊模擬訓練」跨承租人的相同類型負載進行模擬的平均威脅率。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="e9b0e-114">**實際的折衷率** 反映的是類比的員工百分比。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="e9b0e-115">此外，還 `<number> less susceptible to phishing` 反映實際的員工數目與受攻擊損害率和預測的折衷率之間的差異。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="e9b0e-116">此員工人數會因未來的類似攻擊而遭到攻破，同時也會 `<percent%> better than predicted rate` 指出員工相對於預測的折衷率的整體效果。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e9b0e-117">![攻擊類比訓練上的行為影響卡片](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="e9b0e-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="e9b0e-118">若要查看更詳細的報告，請按一下 [ **View 模擬和訓練 efficacy] 報告** ，它會提供與類比本身的其他內容相同的資訊，例如類比技術和目標使用者總數。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="e9b0e-119">建議的動作</span><span class="sxs-lookup"><span data-stu-id="e9b0e-119">Recommended actions</span></span>

<span data-ttu-id="e9b0e-120">在 [ [**模擬** ]](https://security.microsoft.com/attacksimulator?viewid=simulations)索引標籤上，選取任何模擬會將您帶到模擬的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="e9b0e-121">在這裡您會看到 [ **建議的動作** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="e9b0e-122">建議的動作區段會詳細說明 [Microsoft 安全分數](../mtp/microsoft-secure-score.md)中提供的建議。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="e9b0e-123">這些建議是以類比中所使用的負載為基礎，可協助您保護員工和您的環境。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="e9b0e-124">按一下每個改進動作會將您帶到其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e9b0e-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e9b0e-125">![攻擊模擬訓練的建議動作區段](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="e9b0e-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="e9b0e-126">相關連結</span><span class="sxs-lookup"><span data-stu-id="e9b0e-126">Related Links</span></span>

<span data-ttu-id="e9b0e-127">**攻擊模擬** 程式 [建立網路釣魚攻擊模擬](attack-simulation-training.md) ，並 [建立用於訓練人員的負載](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="e9b0e-127">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
