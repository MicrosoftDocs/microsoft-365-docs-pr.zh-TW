---
title: 透過 Microsoft 安全分數來評估您的安全性工作
description: 說明如何採取動作來改善 Microsoft 365 資訊安全中心的 Microsoft 安全分數。
keywords: Microsoft 安全分數， 安全分數， Office 365 安全分數， Microsoft 安全性分數， Microsoft 365 安全性中心， 改進動作
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
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930639"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="f3918-104">使用 Microsoft 安全分數來評估您的安全性工作</span><span class="sxs-lookup"><span data-stu-id="f3918-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f3918-105">Microsoft 安全分數是組織安全性措施的度量，數位越高，表示已採取更多改進動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="f3918-106">您可以在 https://security.microsoft.com/securescore [Microsoft 365 資訊安全中心找到。](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="f3918-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="f3918-107">為了説明您更快速地瞭解您需要的資訊，Microsoft 改進動作分為多個群組：</span><span class="sxs-lookup"><span data-stu-id="f3918-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="f3918-108">Azure Active Directory (身分識別&角色) </span><span class="sxs-lookup"><span data-stu-id="f3918-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="f3918-109">裝置 (Microsoft Defender for Endpoint，稱為[Microsoft 裝置安全分數) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)</span><span class="sxs-lookup"><span data-stu-id="f3918-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="f3918-110">App (電子郵件和雲端 App，包括 Office 365 和 Microsoft 雲端 App 安全性) </span><span class="sxs-lookup"><span data-stu-id="f3918-110">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="f3918-111">在最新發佈的 Microsoft 安全分數中，已推出改良的計分模型，讓 Microsoft 安全分數暫時與身分識別安全分數和圖形 API 不相容。</span><span class="sxs-lookup"><span data-stu-id="f3918-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="f3918-112">檢視詳細資料</span><span class="sxs-lookup"><span data-stu-id="f3918-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="f3918-113">在 Microsoft 安全分數概觀頁面中，查看在這些群組中分數的分配與可用的分數。</span><span class="sxs-lookup"><span data-stu-id="f3918-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="f3918-114">您也可以全面查看總計分數、安全分數的歷史趨勢和基準比較，以及可採取哪些改進動作來改進分數的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f3918-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="f3918-116">檢查您目前的分數</span><span class="sxs-lookup"><span data-stu-id="f3918-116">Check your current score</span></span>

<span data-ttu-id="f3918-117">若要檢查您目前的分數，請前往 Microsoft 安全分數概觀頁面，並尋找顯示您安全分數 **的磚**。</span><span class="sxs-lookup"><span data-stu-id="f3918-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="f3918-118">您的分數會以百分比顯示，以及您可能在總計可能分數中已成就的點數。</span><span class="sxs-lookup"><span data-stu-id="f3918-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="f3918-119">此外，如果您選取分數旁邊的包含按鈕，您可以選擇不同的分數視圖。</span><span class="sxs-lookup"><span data-stu-id="f3918-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="f3918-120">這些不同的分數視圖會顯示在分數磚和點分解圖的圖形中。</span><span class="sxs-lookup"><span data-stu-id="f3918-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="f3918-121">以下是您可以加到您整體分數的視圖中的分數，以更完整地瞭解整體分數：</span><span class="sxs-lookup"><span data-stu-id="f3918-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="f3918-122">**計畫分數**：完成計畫的動作時顯示預計的分數</span><span class="sxs-lookup"><span data-stu-id="f3918-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="f3918-123">**目前的授權分數**：顯示目前的 Microsoft 授權可以達到的分數</span><span class="sxs-lookup"><span data-stu-id="f3918-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="f3918-124">**可成就的** 分數：顯示能與 Microsoft 授權和目前風險接受度一起達成的成績</span><span class="sxs-lookup"><span data-stu-id="f3918-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="f3918-125">如果您已經包含所有可能的分數視圖，此視圖看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="f3918-125">This view is what it will look like if you've included all possible score views:</span></span>

![您的安全分數，包括計畫分數、目前的授權分數和可達成的成績](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="f3918-127">採取動作以改善您的分數</span><span class="sxs-lookup"><span data-stu-id="f3918-127">Take action to improve your score</span></span>

<span data-ttu-id="f3918-128">改進 **動作按鈕** 會列出能解決可能攻擊面的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="f3918-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="f3918-129">它也包括其狀態 (位址、計畫、接受的風險、透過協力廠商解決、透過替代的風險降低和已完成) 。</span><span class="sxs-lookup"><span data-stu-id="f3918-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="f3918-130">您可以搜尋、篩選及分組所有改進動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="f3918-131">排名</span><span class="sxs-lookup"><span data-stu-id="f3918-131">Ranking</span></span>

<span data-ttu-id="f3918-132">排名是根據要達到的點數、執行困難、使用者影響和複雜度來計算。</span><span class="sxs-lookup"><span data-stu-id="f3918-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="f3918-133">排名最高的改進動作有大量的剩餘點數，其困難度、使用者影響和複雜度都較低。</span><span class="sxs-lookup"><span data-stu-id="f3918-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="f3918-134">查看改進動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="f3918-134">View improvement action details</span></span>

<span data-ttu-id="f3918-135">當您選取特定的改進動作時，會出現一個完整頁面飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="f3918-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![改進動作飛出顯示範例](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="f3918-137">若要完成動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="f3918-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="f3918-138">選取 **管理** 以前往組選畫面，然後進行變更。</span><span class="sxs-lookup"><span data-stu-id="f3918-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="f3918-139">接著，您就會獲得動作值得一讀的點數，顯示在飛出飛出中。點數更新通常約需要 24 小時。</span><span class="sxs-lookup"><span data-stu-id="f3918-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="f3918-140">選取 **共用** 以複製改進動作的直接連結。</span><span class="sxs-lookup"><span data-stu-id="f3918-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="f3918-141">您也可以選擇共用連結的平臺，例如電子郵件、Microsoft Teams、Microsoft Planner 或 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="f3918-141">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="f3918-142">選取 ServiceNow 將讓您建立在 ServiceNow 和 Microsoft 365 資訊安全中心首頁中可見的變更票證。</span><span class="sxs-lookup"><span data-stu-id="f3918-142">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="f3918-143">若要深入瞭解，請參閱 [Microsoft 365 資訊安全中心與 ServiceNow 整合](tickets-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f3918-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

<span data-ttu-id="f3918-144">新增 **記** 事以追蹤進度或您想要新增批註的任何專案。</span><span class="sxs-lookup"><span data-stu-id="f3918-144">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="f3918-145">如果您在 **改進動作中** 加入自己的標記，您可以根據這些標記進行篩選。</span><span class="sxs-lookup"><span data-stu-id="f3918-145">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="f3918-146">選擇改進動作狀態</span><span class="sxs-lookup"><span data-stu-id="f3918-146">Choose an improvement action status</span></span>

<span data-ttu-id="f3918-147">選擇任何改進動作的特定狀態並記錄附注。</span><span class="sxs-lookup"><span data-stu-id="f3918-147">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="f3918-148">**解決** - 您瞭解改進動作是必要的，並計畫在未來某一點解決。</span><span class="sxs-lookup"><span data-stu-id="f3918-148">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="f3918-149">此狀態也適用于偵測為部分完成但尚未完成的動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-149">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="f3918-150">**已規劃** - 有具體的計畫可完成改進動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-150">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="f3918-151">**接受的風險** - 安全性應一定會與可用性保持平衡，而並非每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="f3918-151">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="f3918-152">在這種情況下，您可以選擇接受風險或其餘風險，而不是增加改進動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-152">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="f3918-153">您將不會獲得任何點數，但改進動作清單中將不會再顯示該動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-153">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="f3918-154">您可以在歷程記錄中查看此動作，或隨時復原。</span><span class="sxs-lookup"><span data-stu-id="f3918-154">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="f3918-155">**透過協力廠商解決\*\*\*\*並透過替代** 風險降低方式解決 - 協力廠商應用程式或軟體或內部工具已經解決改進動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-155">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="f3918-156">您將獲得值得執行的動作分數，這樣您的分數就更能夠反映整體的安全性表現。</span><span class="sxs-lookup"><span data-stu-id="f3918-156">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="f3918-157">如果協力廠商或內部工具已不再涵蓋該控制項，您可以選擇其他狀態。</span><span class="sxs-lookup"><span data-stu-id="f3918-157">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="f3918-158">請記住，如果改進動作標示為這些狀態之一，Microsoft 將完全無法看到完整的執行。</span><span class="sxs-lookup"><span data-stu-id="f3918-158">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="f3918-159">威脅&弱點管理改進動作</span><span class="sxs-lookup"><span data-stu-id="f3918-159">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="f3918-160">對於「裝置」類別中的改進動作，您無法選擇狀態。</span><span class="sxs-lookup"><span data-stu-id="f3918-160">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="f3918-161">相反地，系統將會將您導向 Microsoft [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) Defender 資訊安全中心的相關威脅和弱點管理[安全性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)建議以採取行動。</span><span class="sxs-lookup"><span data-stu-id="f3918-161">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="f3918-162">您選擇和理由的例外會限制于該入口網站。</span><span class="sxs-lookup"><span data-stu-id="f3918-162">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="f3918-163">它不會在 Microsoft 安全分數入口網站中。</span><span class="sxs-lookup"><span data-stu-id="f3918-163">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="f3918-164">已完成的改進動作</span><span class="sxs-lookup"><span data-stu-id="f3918-164">Completed improvement actions</span></span>

<span data-ttu-id="f3918-165">一旦完成改善動作的所有可能重點後，改進動作會進入「已完成」狀態。</span><span class="sxs-lookup"><span data-stu-id="f3918-165">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="f3918-166">已完成的改進動作雖然 Microsoft 資料已確認，但您無法變更狀態。</span><span class="sxs-lookup"><span data-stu-id="f3918-166">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="f3918-167">評估資訊並評論使用者影響</span><span class="sxs-lookup"><span data-stu-id="f3918-167">Assess information and review user impact</span></span>

<span data-ttu-id="f3918-168">名為快速 **流覽的區** 段會告訴您類別、可防範的攻擊以及產品。</span><span class="sxs-lookup"><span data-stu-id="f3918-168">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="f3918-169">**如果使用者** 有改進行動，使用者的影響會受到影響，而受影響的使用者會受到影響。 </span><span class="sxs-lookup"><span data-stu-id="f3918-169">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="f3918-170">執行改進動作</span><span class="sxs-lookup"><span data-stu-id="f3918-170">Implement the improvement action</span></span>

<span data-ttu-id="f3918-171">The **Implementation section** shows any prerequisites， step-by-step next steps to complete the improvement action， the current implementation status of the improvement action， and any learn more links.</span><span class="sxs-lookup"><span data-stu-id="f3918-171">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="f3918-172">先決條件包括解決改進動作之前需要的任何授權或需完成的動作。</span><span class="sxs-lookup"><span data-stu-id="f3918-172">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="f3918-173">請確定您的授權中有足夠的座位以完成改進動作，而且這些授權已套用至必要的使用者。</span><span class="sxs-lookup"><span data-stu-id="f3918-173">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="f3918-174">我們想知道您的想法</span><span class="sxs-lookup"><span data-stu-id="f3918-174">We want to hear from you</span></span>

<span data-ttu-id="f3918-175">如有任何問題，請張貼在安全性、隱私權和合規性& [告訴我們](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。</span><span class="sxs-lookup"><span data-stu-id="f3918-175">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="f3918-176">我們正在監控社群，並且會為您提供協助。</span><span class="sxs-lookup"><span data-stu-id="f3918-176">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="f3918-177">相關資源</span><span class="sxs-lookup"><span data-stu-id="f3918-177">Related resources</span></span>

- [<span data-ttu-id="f3918-178">Microsoft 安全分數概觀</span><span class="sxs-lookup"><span data-stu-id="f3918-178">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="f3918-179">追蹤您的 Microsoft 安全分數記錄並達成目標</span><span class="sxs-lookup"><span data-stu-id="f3918-179">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="f3918-180">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="f3918-180">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="f3918-181">新功能</span><span class="sxs-lookup"><span data-stu-id="f3918-181">What's new</span></span>](microsoft-secure-score-whats-new.md)
