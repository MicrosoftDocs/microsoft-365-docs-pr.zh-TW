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
description: 系統管理員可以深入瞭解 Microsoft 365 安全中心的攻擊模擬訓練如何影響員工，以及如何深入瞭解類比和訓練結果。
ms.technology: mdo
ms.openlocfilehash: 93d8829f9fbc4271d33e3208e5564529b4022fc3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059016"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="63c99-103">透過攻擊模擬訓練取得深入解析</span><span class="sxs-lookup"><span data-stu-id="63c99-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="63c99-104">在攻擊模擬訓練中，Microsoft 會根據員工所經歷之類比和訓練的結果，提供深入的見解。</span><span class="sxs-lookup"><span data-stu-id="63c99-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="63c99-105">這些真知灼見會協助您及時瞭解員工的威脅準備工作進度，並建議您在後續步驟中，更好地準備員工和您的環境以進行攻擊。</span><span class="sxs-lookup"><span data-stu-id="63c99-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="63c99-106">我們不斷努力擴充您可以使用的洞察力。</span><span class="sxs-lookup"><span data-stu-id="63c99-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="63c99-107">目前可使用行為影響及建議的動作。</span><span class="sxs-lookup"><span data-stu-id="63c99-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="63c99-108">若要開始，請 [在 Microsoft 365 的安全性中心進行攻擊模擬訓練](https://security.microsoft.com/attacksimulator?viewid=overview)。</span><span class="sxs-lookup"><span data-stu-id="63c99-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="63c99-109">對折衷率影響的行為影響</span><span class="sxs-lookup"><span data-stu-id="63c99-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="63c99-110">在攻擊模擬訓練的 [ **一覽表** ] 索引標籤上，您會發現 **影響折衷率** 卡片的行為。</span><span class="sxs-lookup"><span data-stu-id="63c99-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="63c99-111">這張卡片顯示員工如何處理您所執行的類比，與所 **預測的折衷率** 相對。</span><span class="sxs-lookup"><span data-stu-id="63c99-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="63c99-112">您可以使用這些洞察力，針對相同員工群組執行多個模擬，以追蹤員工威脅準備工作的進度。</span><span class="sxs-lookup"><span data-stu-id="63c99-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="63c99-113">您可以在圖形中看到下列專案：</span><span class="sxs-lookup"><span data-stu-id="63c99-113">In the graph you can see:</span></span>

- <span data-ttu-id="63c99-114">**預測的折衷率** ，反映使用相同類型的負載來模擬的平均威脅率，該匯率是使用來自其他使用攻擊模擬訓練訓練的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="63c99-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="63c99-115">**實際的折衷率** 反映的是類比的員工百分比。</span><span class="sxs-lookup"><span data-stu-id="63c99-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="63c99-116">此外，還 `<number> less susceptible to phishing` 反映實際的員工數目與受攻擊損害率和預測的折衷率之間的差異。</span><span class="sxs-lookup"><span data-stu-id="63c99-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="63c99-117">此員工人數會因未來的類似攻擊而遭到攻破，同時也會 `<percent%> better than predicted rate` 指出員工相對於預測的折衷率的整體效果。</span><span class="sxs-lookup"><span data-stu-id="63c99-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63c99-118">![攻擊類比訓練上的行為影響卡片](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="63c99-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="63c99-119">若要查看更詳細的報告，請按一下 [ **View 模擬和訓練 efficacy 報告**]。</span><span class="sxs-lookup"><span data-stu-id="63c99-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="63c99-120">這個報告提供與類比本身的其他內容相同的資訊 (例如，類比技術和以) 為目標的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="63c99-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="63c99-121">建議的動作</span><span class="sxs-lookup"><span data-stu-id="63c99-121">Recommended actions</span></span>

<span data-ttu-id="63c99-122">在 [ [**模擬** ]](https://security.microsoft.com/attacksimulator?viewid=simulations)索引標籤上，選取類比會帶您前往類比詳細資料，您可以在其中找到 [ **建議的動作** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="63c99-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="63c99-123">建議的動作區段會詳細說明 [Microsoft 安全分數](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score)中提供的建議。</span><span class="sxs-lookup"><span data-stu-id="63c99-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score).</span></span> <span data-ttu-id="63c99-124">這些建議是以類比中所使用的負載為基礎，可協助您保護員工和您的環境。</span><span class="sxs-lookup"><span data-stu-id="63c99-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="63c99-125">按一下每個改進動作會將您帶到其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="63c99-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63c99-126">![攻擊模擬訓練的建議動作區段](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="63c99-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="63c99-127">相關連結</span><span class="sxs-lookup"><span data-stu-id="63c99-127">Related Links</span></span>

[<span data-ttu-id="63c99-128">開始使用攻擊模擬訓練</span><span class="sxs-lookup"><span data-stu-id="63c99-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="63c99-129">建立網路釣魚攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="63c99-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="63c99-130">建立訓練給您人員的負載</span><span class="sxs-lookup"><span data-stu-id="63c99-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
