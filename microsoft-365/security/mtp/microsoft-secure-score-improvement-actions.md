---
title: 透過 Microsoft 安全分數評估安全性狀況
description: 說明如何採取動作，以改善 Microsoft 365 安全中心的 Microsoft 安全分數。
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
ms.openlocfilehash: 02c79edaa05e7903a8797cdf83c18a4ce69716dc
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920533"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="98294-104">使用 Microsoft 安全分數評估安全性狀況</span><span class="sxs-lookup"><span data-stu-id="98294-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="98294-105">Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。</span><span class="sxs-lookup"><span data-stu-id="98294-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="98294-106">可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。</span><span class="sxs-lookup"><span data-stu-id="98294-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="98294-107">為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="98294-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="98294-108"> (Azure Active Directory 帳戶 & 角色的身分識別) </span><span class="sxs-lookup"><span data-stu-id="98294-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="98294-109">資料 (現在沒有任何改進動作) </span><span class="sxs-lookup"><span data-stu-id="98294-109">Data  (no improvement actions for now)</span></span>
* <span data-ttu-id="98294-110">裝置 (Microsoft Defender for Endpoint，稱為 [裝置的 Microsoft 安全評分](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)) </span><span class="sxs-lookup"><span data-stu-id="98294-110">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="98294-111">App (電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security) </span><span class="sxs-lookup"><span data-stu-id="98294-111">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="98294-112">基礎結構 (現在沒有任何改進動作) </span><span class="sxs-lookup"><span data-stu-id="98294-112">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="98294-113">在最近發行的 Microsoft Secure 得分中，已發行的評分模型已發佈，使 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。</span><span class="sxs-lookup"><span data-stu-id="98294-113">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="98294-114">檢視詳細資料</span><span class="sxs-lookup"><span data-stu-id="98294-114">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="98294-115">在 [Microsoft Secure 得分一覽] 頁面中，瞭解如何在這些群組間分割點，以及可以使用哪些點數。</span><span class="sxs-lookup"><span data-stu-id="98294-115">In the Microsoft Secure Score overview page, see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="98294-116">您也可以取得總分的整體總分、安全分數的歷史趨勢和基準比較，以及可以採取以改善評分的優先改進動作。</span><span class="sxs-lookup"><span data-stu-id="98294-116">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="98294-118">檢查您目前的分數</span><span class="sxs-lookup"><span data-stu-id="98294-118">Check your current score</span></span>

<span data-ttu-id="98294-119">若要檢查您目前的分數，請移至 [Microsoft Secure 得分一覽] 頁面，並尋找包含 **您安全分數** 的麻將牌。</span><span class="sxs-lookup"><span data-stu-id="98294-119">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="98294-120">您的分數會顯示為百分數，以及您已從總可能點數取得的點數。</span><span class="sxs-lookup"><span data-stu-id="98294-120">Your score will be shown as a percentage, along with the number of points you've achieved out of a total possible points.</span></span>

<span data-ttu-id="98294-121">此外，如果您選取分數旁邊的 [ **包含** ] 按鈕，您可以選擇不同的分數視圖。</span><span class="sxs-lookup"><span data-stu-id="98294-121">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="98294-122">這些不同的分數視圖會顯示在 [分數] 磚和 [點] 分解圖上的圖表中。</span><span class="sxs-lookup"><span data-stu-id="98294-122">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="98294-123">以下是您可以新增至您的整體分數視圖的分數，可讓您更完整的整體分數的描述如下：</span><span class="sxs-lookup"><span data-stu-id="98294-123">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="98294-124">已 **計畫分數** ：在計畫的動作完成時顯示預計分數</span><span class="sxs-lookup"><span data-stu-id="98294-124">**Planned score** : Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="98294-125">**目前的授權分數** ：顯示可使用您目前的 Microsoft 授權所能達到的分數</span><span class="sxs-lookup"><span data-stu-id="98294-125">**Current license score** : Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="98294-126">可 **實現分數** ：顯示可透過您的 Microsoft 授權和目前的風險接受程度達到的分數</span><span class="sxs-lookup"><span data-stu-id="98294-126">**Achievable score** : Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="98294-127">如果您已包含所有可能的分數視圖，則此視圖的外觀會如下：</span><span class="sxs-lookup"><span data-stu-id="98294-127">This view is what it will look like if you've included all possible score views:</span></span>

![您的安全分數，包括已計畫的分數、目前的授權分數，以及能達到的分數](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="98294-129">採取動作以提升您的分數</span><span class="sxs-lookup"><span data-stu-id="98294-129">Take action to improve your score</span></span>

<span data-ttu-id="98294-130">[ **改進動作** ] 索引標籤會列出解決可能攻擊曲面的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="98294-130">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="98294-131">此外，它還包括其狀態 (，以解決、規劃、接受的風險、透過協力廠商解決，以及透過替代的緩解可解決，以及已完成的) 。</span><span class="sxs-lookup"><span data-stu-id="98294-131">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="98294-132">您可以搜尋、篩選和群組所有的「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="98294-132">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="98294-133">排名</span><span class="sxs-lookup"><span data-stu-id="98294-133">Ranking</span></span>

<span data-ttu-id="98294-134">排名是根據剩下的點數、實施難度、使用者影響和複雜性而定。</span><span class="sxs-lookup"><span data-stu-id="98294-134">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="98294-135">最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。</span><span class="sxs-lookup"><span data-stu-id="98294-135">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="98294-136">查看改進動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="98294-136">View improvement action details</span></span>

<span data-ttu-id="98294-137">當您選取特定的 [提升] 動作時，會出現完整的頁面快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="98294-137">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="98294-138">![改進動作飛出範例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *圖2：改進動作飛出範例*</span><span class="sxs-lookup"><span data-stu-id="98294-138">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="98294-139">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="98294-139">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="98294-140">選取 [ **管理** ] 以進入設定畫面並進行變更。</span><span class="sxs-lookup"><span data-stu-id="98294-140">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="98294-141">接著，您將會在飛出的位置看到必要的動作。點通常需要24小時才能更新。</span><span class="sxs-lookup"><span data-stu-id="98294-141">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="98294-142">選取 [ **共用** ]，將直接連結複製到 [改進] 動作。</span><span class="sxs-lookup"><span data-stu-id="98294-142">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="98294-143">您也可以選擇要共用連結的平臺，例如電子郵件、Microsoft 小組、Microsoft Planner 或 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="98294-143">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="98294-144">選取 [ServiceNow 將可讓您建立 ServiceNow 和 Microsoft 365 安全性中心首頁會顯示的變更票證。</span><span class="sxs-lookup"><span data-stu-id="98294-144">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="98294-145">若要深入瞭解，請參閱 [Microsoft 365 security center 和 ServiceNow integration](tickets-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="98294-145">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="98294-146">選擇改進動作狀態</span><span class="sxs-lookup"><span data-stu-id="98294-146">Choose an improvement action status</span></span>

<span data-ttu-id="98294-147">選擇 [改進] 動作特有的任何狀態和記錄附注。</span><span class="sxs-lookup"><span data-stu-id="98294-147">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="98294-148">**若要解決** 此事項-您可以辨識改進動作是必要的，並計畫于未來某一點進行處理。</span><span class="sxs-lookup"><span data-stu-id="98294-148">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="98294-149">這種狀態也適用于已偵測到部分但未完全完成的動作。</span><span class="sxs-lookup"><span data-stu-id="98294-149">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="98294-150">已 **計畫** -已有適當的計畫可完成改進動作。</span><span class="sxs-lookup"><span data-stu-id="98294-150">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="98294-151">已 **接受風險** -安全性絕對應該與可用性進行平衡，而不是每個建議適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="98294-151">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="98294-152">在這種情況下，您可以選擇接受風險或餘下的風險，而不會制定改進動作。</span><span class="sxs-lookup"><span data-stu-id="98294-152">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="98294-153">您不會獲得任何點數，但是動作將不再顯示在 [改進動作] 清單中。</span><span class="sxs-lookup"><span data-stu-id="98294-153">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="98294-154">您可以在歷史記錄中查看此動作，也可以隨時復原。</span><span class="sxs-lookup"><span data-stu-id="98294-154">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="98294-155">**透過協力廠商解決** ，並 **透過替代的緩解措施解決** -改進動作已經由協力廠商應用程式或軟體或內部工具所解決。</span><span class="sxs-lookup"><span data-stu-id="98294-155">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="98294-156">您將會看到必要的動作點，所以您的分數會更好反映整體的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="98294-156">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="98294-157">如果協力廠商或內部工具不再涵蓋該控制項，您可以選擇其他狀態。</span><span class="sxs-lookup"><span data-stu-id="98294-157">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="98294-158">請記住，如果改進動作標示為這兩種狀態，Microsoft 將無法深入瞭解實施的完整性。</span><span class="sxs-lookup"><span data-stu-id="98294-158">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="98294-159">威脅 & 弱點管理的改進動作</span><span class="sxs-lookup"><span data-stu-id="98294-159">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="98294-160">若要在 "Device" 類別中改進動作，您將無法選擇狀態。</span><span class="sxs-lookup"><span data-stu-id="98294-160">For improvement actions in the "Device" category, you won't be able to choose statuses.</span></span> <span data-ttu-id="98294-161">相反地，您會被導向相關 [威脅 & 弱點管理 (TVM) 安全性建議](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 的 [Microsoft Defender security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 採取行動。</span><span class="sxs-lookup"><span data-stu-id="98294-161">Instead, you'll be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="98294-162">您選擇的例外狀況和您所撰寫的對齊方式，都是該入口網站特有的。</span><span class="sxs-lookup"><span data-stu-id="98294-162">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="98294-163">它不會出現在 Microsoft Secure 得分入口網站中。</span><span class="sxs-lookup"><span data-stu-id="98294-163">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="98294-164">已完成的改進動作</span><span class="sxs-lookup"><span data-stu-id="98294-164">Completed improvement actions</span></span>

<span data-ttu-id="98294-165">在完成改進動作的所有可能點之後，[改進動作] 的狀態為「已完成」。</span><span class="sxs-lookup"><span data-stu-id="98294-165">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="98294-166">已完成的改進動作會透過 Microsoft data 加以確認，而且您將無法變更狀態。</span><span class="sxs-lookup"><span data-stu-id="98294-166">Completed improvement actions are confirmed though Microsoft data, and you won't be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="98294-167">評估資訊並複查使用者影響</span><span class="sxs-lookup"><span data-stu-id="98294-167">Assess information and review user impact</span></span>

<span data-ttu-id="98294-168">一 **眼** 就會告訴您，您的類別、可以防禦的攻擊，以及產品。</span><span class="sxs-lookup"><span data-stu-id="98294-168">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="98294-169">[ **使用者影響** ] 顯示使用者在已頒佈改進動作時的體驗，以及 **受影響的使用者** 會顯示誰會體驗。</span><span class="sxs-lookup"><span data-stu-id="98294-169">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="98294-170">實施改進動作</span><span class="sxs-lookup"><span data-stu-id="98294-170">Implement the improvement action</span></span>

<span data-ttu-id="98294-171">「 **實施** 」區段顯示所有必要條件、逐步後續步驟，以完成 [改進] 動作、[改進動作] 的目前實施狀態，以及任何 [深入瞭解] 連結。</span><span class="sxs-lookup"><span data-stu-id="98294-171">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="98294-172">必要條件包括需要取得的任何授權，或是在解決改進動作之前必須完成的動作。</span><span class="sxs-lookup"><span data-stu-id="98294-172">Prerequisites include any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="98294-173">請確定您的授權有足夠的座位，可完成 [改進] 動作，並將這些授權套用至必要的使用者。</span><span class="sxs-lookup"><span data-stu-id="98294-173">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="98294-174">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="98294-174">We want to hear from you</span></span>

<span data-ttu-id="98294-175">如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。</span><span class="sxs-lookup"><span data-stu-id="98294-175">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="98294-176">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="98294-176">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="98294-177">相關資源</span><span class="sxs-lookup"><span data-stu-id="98294-177">Related resources</span></span>

- [<span data-ttu-id="98294-178">Microsoft 安全評分概述</span><span class="sxs-lookup"><span data-stu-id="98294-178">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="98294-179">追蹤您的 Microsoft 安全分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="98294-179">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="98294-180">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="98294-180">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="98294-181">新功能</span><span class="sxs-lookup"><span data-stu-id="98294-181">What's new</span></span>](microsoft-secure-score-whats-new.md)
