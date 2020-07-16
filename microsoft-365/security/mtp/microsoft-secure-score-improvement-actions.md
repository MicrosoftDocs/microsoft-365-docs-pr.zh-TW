---
title: 透過 Microsoft 安全分數深入瞭解安全性狀況
description: 說明如何採取動作，以改善 Microsoft 365 安全中心的 Microsoft 安全分數。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
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
ms.openlocfilehash: 0ae1a196f11f383c1d3f9fd2056d5d19e7cdd6da
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45095025"
---
# <a name="gain-visibility-into-your-security-posture-through-microsoft-secure-score"></a><span data-ttu-id="03b9f-104">透過 Microsoft 安全分數深入瞭解安全性狀況</span><span class="sxs-lookup"><span data-stu-id="03b9f-104">Gain visibility into your security posture through Microsoft Secure Score</span></span>

<span data-ttu-id="03b9f-105">Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。</span><span class="sxs-lookup"><span data-stu-id="03b9f-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="03b9f-106">可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。</span><span class="sxs-lookup"><span data-stu-id="03b9f-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="03b9f-107">為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="03b9f-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="03b9f-108"> (Azure AD 帳戶 & 角色的身分識別) </span><span class="sxs-lookup"><span data-stu-id="03b9f-108">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="03b9f-109">資料 (Microsoft 資訊保護) </span><span class="sxs-lookup"><span data-stu-id="03b9f-109">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="03b9f-110">裝置 (Microsoft Defender ATP，稱為設定[分數](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)) </span><span class="sxs-lookup"><span data-stu-id="03b9f-110">Device (Microsoft Defender ATP, known as [Configuration score](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))</span></span>
* <span data-ttu-id="03b9f-111">App (電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security) </span><span class="sxs-lookup"><span data-stu-id="03b9f-111">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="03b9f-112">基礎結構 (現在沒有任何改進動作) </span><span class="sxs-lookup"><span data-stu-id="03b9f-112">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="03b9f-113">在最近發行的 Microsoft Secure 得分中，已發行的評分模型已發佈，使 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。</span><span class="sxs-lookup"><span data-stu-id="03b9f-113">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="03b9f-114">檢視詳細資料</span><span class="sxs-lookup"><span data-stu-id="03b9f-114">View details</span></span>](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

<span data-ttu-id="03b9f-115">在 [Microsoft Secure 得分一覽] 頁面中，您可以看到各群組之間的點數如何分割，以及哪些點可供使用。</span><span class="sxs-lookup"><span data-stu-id="03b9f-115">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="03b9f-116">[一覽表] 頁面也是取得整體總分、您的安全分數與基準比較之歷史趨勢的完整視圖，以及可以採取以改善評分的優先改進動作的位置。</span><span class="sxs-lookup"><span data-stu-id="03b9f-116">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="03b9f-118">檢查您目前的分數</span><span class="sxs-lookup"><span data-stu-id="03b9f-118">Check your current score</span></span>

<span data-ttu-id="03b9f-119">若要檢查您目前的分數，請移至 [Microsoft Secure 得分一覽] 頁面，並尋找包含**您安全分數**的麻將牌。</span><span class="sxs-lookup"><span data-stu-id="03b9f-119">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="03b9f-120">您的分數會顯示為百分數，以及您已從總可能的點數完成的點數。</span><span class="sxs-lookup"><span data-stu-id="03b9f-120">Your score will be shown as a percentage, along with the number of points you have achieved out of a total possible points.</span></span>

<span data-ttu-id="03b9f-121">此外，如果您選取分數旁邊的 [**包含**] 按鈕，您可以選擇不同的分數視圖。</span><span class="sxs-lookup"><span data-stu-id="03b9f-121">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="03b9f-122">這些不同的分數視圖會顯示在 [分數] 磚和 [點] 分解圖上的圖表中。</span><span class="sxs-lookup"><span data-stu-id="03b9f-122">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="03b9f-123">以下是您可以新增至您的整體分數視圖的分數，可讓您更完整的整體分數的描述如下：</span><span class="sxs-lookup"><span data-stu-id="03b9f-123">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="03b9f-124">已**計畫分數**：在計畫的動作完成時顯示預計分數</span><span class="sxs-lookup"><span data-stu-id="03b9f-124">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="03b9f-125">**目前的授權分數**：顯示可使用您目前的 Microsoft 授權所能達到的分數</span><span class="sxs-lookup"><span data-stu-id="03b9f-125">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="03b9f-126">可**實現分數**：顯示可透過您的 Microsoft 授權和目前的風險接受程度達到的分數</span><span class="sxs-lookup"><span data-stu-id="03b9f-126">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="03b9f-127">如果您已包含所有可能的分數視圖，就會呈現此內容：</span><span class="sxs-lookup"><span data-stu-id="03b9f-127">This is what it will look like if you have included all possible score views:</span></span>

![您的安全分數，包括已計畫的分數、目前的授權分數，以及能達到的分數](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="03b9f-129">採取動作以提升您的分數</span><span class="sxs-lookup"><span data-stu-id="03b9f-129">Take action to improve your score</span></span>

<span data-ttu-id="03b9f-130">[**改進動作**] 索引標籤會列出解決可能攻擊面的安全性建議，及其狀態 (，以解決、計畫、接受的風險、透過協力廠商解決、已透過替代的緩解措施解決，以及完成) 。</span><span class="sxs-lookup"><span data-stu-id="03b9f-130">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="03b9f-131">您可以搜尋、篩選和群組所有的「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="03b9f-131">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="03b9f-132">排名</span><span class="sxs-lookup"><span data-stu-id="03b9f-132">Ranking</span></span>

<span data-ttu-id="03b9f-133">排名是根據剩下的剩餘點數、實施難度、使用者影響和複雜性而定。</span><span class="sxs-lookup"><span data-stu-id="03b9f-133">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="03b9f-134">最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。</span><span class="sxs-lookup"><span data-stu-id="03b9f-134">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="03b9f-135">查看改進動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="03b9f-135">View improvement action details</span></span>

<span data-ttu-id="03b9f-136">當您選取特定的 [提升] 動作時，會出現完整的頁面快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="03b9f-136">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="03b9f-137">![改進動作飛出範例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *圖2：改進動作飛出範例*</span><span class="sxs-lookup"><span data-stu-id="03b9f-137">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="03b9f-138">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="03b9f-138">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="03b9f-139">選取 [**管理**] 以進入設定畫面並進行變更。</span><span class="sxs-lookup"><span data-stu-id="03b9f-139">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="03b9f-140">接著，您將會在飛出的位置看到必要的動作。點通常需要24小時才能更新。</span><span class="sxs-lookup"><span data-stu-id="03b9f-140">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="03b9f-141">選取 [**共用**]，將直接連結複製到 [改進] 動作，或選擇用來共用連結的平臺，例如電子郵件、microsoft 小組、microsoft Planner 或 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="03b9f-141">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="03b9f-142">選取 [ServiceNow 將可讓您建立 ServiceNow 和 Microsoft 365 的安全性中心首頁會顯示的變更票證。</span><span class="sxs-lookup"><span data-stu-id="03b9f-142">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="03b9f-143">若要深入瞭解，請參閱[Microsoft 365 security center 和 ServiceNow integration](tickets-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="03b9f-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="03b9f-144">選擇改進動作狀態</span><span class="sxs-lookup"><span data-stu-id="03b9f-144">Choose an improvement action status</span></span>

<span data-ttu-id="03b9f-145">選擇 [改進] 動作特有的任何狀態和記錄附注。</span><span class="sxs-lookup"><span data-stu-id="03b9f-145">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="03b9f-146">您可以選取下列 statues：</span><span class="sxs-lookup"><span data-stu-id="03b9f-146">The statues you can select are the following:</span></span>

* <span data-ttu-id="03b9f-147">**若要解決**此事項，您可以辨識改進動作是必要的，並計畫于未來某一點進行處理。</span><span class="sxs-lookup"><span data-stu-id="03b9f-147">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="03b9f-148">這種狀態也適用于已偵測到部分但未完全完成的動作。</span><span class="sxs-lookup"><span data-stu-id="03b9f-148">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="03b9f-149">已**計畫**-完成改進動作有一些具體的計畫。</span><span class="sxs-lookup"><span data-stu-id="03b9f-149">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="03b9f-150">已**接受風險**-安全性應該一定要與可用性進行平衡，而不是每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="03b9f-150">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="03b9f-151">在這種情況下，您可以選擇接受風險或餘下的風險，而不會制定改進動作。</span><span class="sxs-lookup"><span data-stu-id="03b9f-151">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="03b9f-152">您不會獲得任何點數，但是動作將不再顯示在 [改進動作] 清單中。</span><span class="sxs-lookup"><span data-stu-id="03b9f-152">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="03b9f-153">您可以在歷史記錄中查看此動作，也可以隨時復原。</span><span class="sxs-lookup"><span data-stu-id="03b9f-153">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="03b9f-154">**透過協力廠商解決**，並**透過替代的緩解**措施加以解決--改進動作已經由協力廠商應用程式或軟體或內部工具所解決。</span><span class="sxs-lookup"><span data-stu-id="03b9f-154">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="03b9f-155">您將會獲得值得行動的點數，所以您的分數會更好反映整體的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="03b9f-155">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="03b9f-156">如果協力廠商或內部工具不再涵蓋該控制項，您可以選擇其他狀態。</span><span class="sxs-lookup"><span data-stu-id="03b9f-156">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="03b9f-157">請記住，如果改進動作標示為這兩種狀態，Microsoft 將不會深入瞭解實施的完整性。</span><span class="sxs-lookup"><span data-stu-id="03b9f-157">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="03b9f-158">威脅 & 弱點管理的改進動作</span><span class="sxs-lookup"><span data-stu-id="03b9f-158">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="03b9f-159">在 "Device" 類別中的改進動作，您將無法選擇狀態。</span><span class="sxs-lookup"><span data-stu-id="03b9f-159">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="03b9f-160">相反地，您會被導向相關[威脅 & 弱點管理 (TVM) 安全性建議](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)的[Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)以採取行動。</span><span class="sxs-lookup"><span data-stu-id="03b9f-160">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="03b9f-161">您選擇的例外狀況和您所撰寫的理由將會特定于該入口網站，而且不會出現在 Microsoft Secure 得分入口網站中。</span><span class="sxs-lookup"><span data-stu-id="03b9f-161">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="03b9f-162">已完成的改進動作</span><span class="sxs-lookup"><span data-stu-id="03b9f-162">Completed improvement actions</span></span>

<span data-ttu-id="03b9f-163">在完成改進動作的所有可能點之後，[改進動作] 的狀態為「已完成」。</span><span class="sxs-lookup"><span data-stu-id="03b9f-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="03b9f-164">已完成的改善動作會透過 Microsoft data 加以確認，而且您將無法變更狀態。</span><span class="sxs-lookup"><span data-stu-id="03b9f-164">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="03b9f-165">評估資訊並複查使用者影響</span><span class="sxs-lookup"><span data-stu-id="03b9f-165">Assess information and review user impact</span></span>

<span data-ttu-id="03b9f-166">**在 [一覽**] 區段中，將會告訴您您的類別、可以防禦的攻擊，以及產品。</span><span class="sxs-lookup"><span data-stu-id="03b9f-166">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="03b9f-167">[**使用者影響**] 顯示使用者在已頒佈改進動作時的體驗，以及**受影響的使用者**會顯示誰會體驗。</span><span class="sxs-lookup"><span data-stu-id="03b9f-167">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="03b9f-168">實施改進動作</span><span class="sxs-lookup"><span data-stu-id="03b9f-168">Implement the improvement action</span></span>

<span data-ttu-id="03b9f-169">「**實施**」區段會顯示所有必要條件、逐步後續步驟以完成 [改進] 動作、[改進動作] 的目前實施狀態，以及任何 [深入瞭解] 連結。</span><span class="sxs-lookup"><span data-stu-id="03b9f-169">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="03b9f-170">必要條件會是任何需要取得的授權，或是在解決改進動作之前必須完成的動作。</span><span class="sxs-lookup"><span data-stu-id="03b9f-170">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="03b9f-171">請確定您的授權有足夠的座位，可完成 [改進] 動作，並將這些授權套用至必要的使用者。</span><span class="sxs-lookup"><span data-stu-id="03b9f-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="03b9f-172">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="03b9f-172">We want to hear from you</span></span>

<span data-ttu-id="03b9f-173">如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。</span><span class="sxs-lookup"><span data-stu-id="03b9f-173">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="03b9f-174">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="03b9f-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="03b9f-175">相關資源</span><span class="sxs-lookup"><span data-stu-id="03b9f-175">Related resources</span></span>

- [<span data-ttu-id="03b9f-176">Microsoft 安全評分概述</span><span class="sxs-lookup"><span data-stu-id="03b9f-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="03b9f-177">追蹤您的 Microsoft 安全分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="03b9f-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="03b9f-178">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="03b9f-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)