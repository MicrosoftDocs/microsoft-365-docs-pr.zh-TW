---
title: Microsoft 安全分數
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分、如何計算詳細資料，以及安全性管理員可以預期的情況。
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
ms.openlocfilehash: 56c3187999d34ac6d84c1b3857053f82bb40b2a9
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804752"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="4ac50-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="4ac50-104">Microsoft Secure Score</span></span>

<span data-ttu-id="4ac50-105">Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。</span><span class="sxs-lookup"><span data-stu-id="4ac50-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="4ac50-106">遵循安全性分數建議可保護您的組織免受威脅。</span><span class="sxs-lookup"><span data-stu-id="4ac50-106">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="4ac50-107">透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="4ac50-107">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="4ac50-108">安全分數可協助組織：</span><span class="sxs-lookup"><span data-stu-id="4ac50-108">Secure Score helps organizations:</span></span>

* <span data-ttu-id="4ac50-109">報告組織安全狀況的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4ac50-109">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="4ac50-110">提供探索性、可見度、指導方針和控制，以提升安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="4ac50-110">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="4ac50-111">與基準進行比較，並建立關鍵效能指標（KPIs）。</span><span class="sxs-lookup"><span data-stu-id="4ac50-111">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="4ac50-112">組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。</span><span class="sxs-lookup"><span data-stu-id="4ac50-112">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="4ac50-113">分數也可以反映協力廠商的解決方案如何解決建議的動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-113">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="4ac50-114">此外，您可以透過[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)來存取您的建議和評分。</span><span class="sxs-lookup"><span data-stu-id="4ac50-114">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="4ac50-115">深入瞭解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="4ac50-115">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4ac50-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="4ac50-116">How it works</span></span>

<span data-ttu-id="4ac50-117">您可以在設定建議的安全性功能、執行安全性相關工作（如查看報告），或使用協力廠商應用程式或軟體解決改進動作的情況下，取得點數。</span><span class="sxs-lookup"><span data-stu-id="4ac50-117">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="4ac50-118">有些改進動作只會在完全完成時給予點，有些的動作會在某些裝置或使用者完成時提供部分分數。</span><span class="sxs-lookup"><span data-stu-id="4ac50-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="4ac50-119">不管授權為何，我們都會向您顯示一組完整的可能改進功能，讓您瞭解安全性的最佳作法，並提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="4ac50-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="4ac50-120">您的絕對安全性狀態是以安全分數表示，不論貴組織擁有的產品授權為何都會保持不變。</span><span class="sxs-lookup"><span data-stu-id="4ac50-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="4ac50-121">請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="4ac50-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="4ac50-122">您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="4ac50-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="4ac50-123">安全分數也會每天同步處理每個動作的取得點數的系統資料。</span><span class="sxs-lookup"><span data-stu-id="4ac50-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="4ac50-124">如何計分改進動作</span><span class="sxs-lookup"><span data-stu-id="4ac50-124">How improvement actions are scored</span></span>

<span data-ttu-id="4ac50-125">大多數會以二進位方式計分：若您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。</span><span class="sxs-lookup"><span data-stu-id="4ac50-125">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="4ac50-126">在其他改進動作中，點會指定為總設定的百分比。</span><span class="sxs-lookup"><span data-stu-id="4ac50-126">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="4ac50-127">例如，如果改進的動作指出您使用多重要素驗證來保護所有使用者時取得30點，而且您只會保護 100 5% 以上的使用者，則會得到大約2點的部分分數（5個 protected/100 總計 \* 30 最大值 = 2 pt 部分分數）。</span><span class="sxs-lookup"><span data-stu-id="4ac50-127">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="4ac50-128">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="4ac50-128">Products included in Secure Score</span></span>

<span data-ttu-id="4ac50-129">目前有一些建議包括 SharePoint Online、Exchange Online、商務 OneDrive、Microsoft 資訊保護等等）、Azure AD 和 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="4ac50-129">Currently there are recommendations for including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, and Cloud App Security.</span></span> <span data-ttu-id="4ac50-130">即將推出其他安全性產品（如 Azure ATP 和 Microsoft Defender ATP）的建議。</span><span class="sxs-lookup"><span data-stu-id="4ac50-130">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="4ac50-131">建議不會涵蓋與各項產品相關聯的所有攻擊面，但也是一個很好的基準。</span><span class="sxs-lookup"><span data-stu-id="4ac50-131">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="4ac50-132">您也可以將改進動作標示為協力廠商所涵蓋的範圍。</span><span class="sxs-lookup"><span data-stu-id="4ac50-132">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="4ac50-133">必要的權限</span><span class="sxs-lookup"><span data-stu-id="4ac50-133">Required permissions</span></span>

<span data-ttu-id="4ac50-134">若要具有存取 Microsoft Secure 得分的許可權，您必須在 Azure Active Directory 中為下列其中一個角色指派。</span><span class="sxs-lookup"><span data-stu-id="4ac50-134">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="4ac50-135">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="4ac50-135">Read and write roles</span></span>

<span data-ttu-id="4ac50-136">透過讀取和寫入權限，您可以進行變更，並直接與安全分數互動。</span><span class="sxs-lookup"><span data-stu-id="4ac50-136">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="4ac50-137">您也可以將唯讀許可權指派給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="4ac50-137">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="4ac50-138">全域管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-138">Global administrator</span></span>
* <span data-ttu-id="4ac50-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-139">Security administrator</span></span>
* <span data-ttu-id="4ac50-140">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-140">Exchange administrator</span></span>
* <span data-ttu-id="4ac50-141">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-141">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="4ac50-142">唯讀角色</span><span class="sxs-lookup"><span data-stu-id="4ac50-142">Read-only roles</span></span>

<span data-ttu-id="4ac50-143">若具有唯讀許可權，您就無法編輯 [改進動作]、[編輯計分區域] 或 [編輯自訂比較] 的狀態或附注。</span><span class="sxs-lookup"><span data-stu-id="4ac50-143">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="4ac50-144">説明台管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-144">Helpdesk administrator</span></span>
* <span data-ttu-id="4ac50-145">使用者管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-145">User administrator</span></span>
* <span data-ttu-id="4ac50-146">服務管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-146">Service administrator</span></span>
* <span data-ttu-id="4ac50-147">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="4ac50-147">Security reader</span></span>
* <span data-ttu-id="4ac50-148">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="4ac50-148">Security operator</span></span>
* <span data-ttu-id="4ac50-149">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="4ac50-149">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="4ac50-150">圖形 API</span><span class="sxs-lookup"><span data-stu-id="4ac50-150">Graph API</span></span>

<span data-ttu-id="4ac50-151">若要存取 Graph API，除了 role 之外，您還必須具有下列其中一個範圍：</span><span class="sxs-lookup"><span data-stu-id="4ac50-151">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="4ac50-152">SecurityEvents Read。 All （唯讀角色）</span><span class="sxs-lookup"><span data-stu-id="4ac50-152">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="4ac50-153">ReadWrite SecurityEvents （適用于讀取和寫入角色）</span><span class="sxs-lookup"><span data-stu-id="4ac50-153">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="4ac50-154">深入瞭解您的安全性狀況</span><span class="sxs-lookup"><span data-stu-id="4ac50-154">Gain visibility into your security posture</span></span>

<span data-ttu-id="4ac50-155">為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="4ac50-155">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="4ac50-156">Identity （Azure AD 帳戶 & 角色）</span><span class="sxs-lookup"><span data-stu-id="4ac50-156">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="4ac50-157">資料（Microsoft 資訊保護）</span><span class="sxs-lookup"><span data-stu-id="4ac50-157">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="4ac50-158">裝置（現在沒有任何改進動作）</span><span class="sxs-lookup"><span data-stu-id="4ac50-158">Device (no improvement actions for now)</span></span>
* <span data-ttu-id="4ac50-159">應用程式（電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）</span><span class="sxs-lookup"><span data-stu-id="4ac50-159">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="4ac50-160">基礎結構（現在沒有任何改進動作）</span><span class="sxs-lookup"><span data-stu-id="4ac50-160">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="4ac50-161">在 [Microsoft Secure 得分一覽] 頁面中，您可以看到各群組之間的點數如何分割，以及哪些點可供使用。</span><span class="sxs-lookup"><span data-stu-id="4ac50-161">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="4ac50-162">[一覽表] 頁面也是取得整體總分、您的安全分數與基準比較之歷史趨勢的完整視圖，以及可以採取以改善評分的優先改進動作的位置。</span><span class="sxs-lookup"><span data-stu-id="4ac50-162">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="4ac50-163">![安全分數主頁](../../media/secure-score/homepage-original.png)
*圖1： Microsoft Secure 得分一覽頁面*</span><span class="sxs-lookup"><span data-stu-id="4ac50-163">![Secure Score homepage](../../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="4ac50-164">採取動作以提升您的分數</span><span class="sxs-lookup"><span data-stu-id="4ac50-164">Take action to improve your score</span></span>

<span data-ttu-id="4ac50-165">[改進動作] 索引標籤會列出解決可能攻擊面的安全性建議，及其狀態（已完成，尚未完成，已透過協力廠商解決，且被忽略）。</span><span class="sxs-lookup"><span data-stu-id="4ac50-165">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="4ac50-166">您可以搜尋、篩選和群組所有的「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-166">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="4ac50-167">排名</span><span class="sxs-lookup"><span data-stu-id="4ac50-167">Ranking</span></span>

<span data-ttu-id="4ac50-168">排名是根據剩下的剩餘點數、實施難度、使用者影響和複雜性而定。</span><span class="sxs-lookup"><span data-stu-id="4ac50-168">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="4ac50-169">最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。</span><span class="sxs-lookup"><span data-stu-id="4ac50-169">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="4ac50-170">動作</span><span class="sxs-lookup"><span data-stu-id="4ac50-170">Actions</span></span>

<span data-ttu-id="4ac50-171">標為 [未評分] 的動作不會由 Microsoft 安全分數追蹤。</span><span class="sxs-lookup"><span data-stu-id="4ac50-171">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="4ac50-172">您仍然可以採取動作，但完成這些動作不會影響您的分數。</span><span class="sxs-lookup"><span data-stu-id="4ac50-172">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="4ac50-173">如果您未來的動作成為 Microsoft 安全得分，而且您已完成，您的安全分數會自動反映變更。</span><span class="sxs-lookup"><span data-stu-id="4ac50-173">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="4ac50-174">當您選取特定的 [改進] 動作時，會出現 [飛出]。</span><span class="sxs-lookup"><span data-stu-id="4ac50-174">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="4ac50-175">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="4ac50-175">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="4ac50-176">選取 [**查看設定**] 以進入設定畫面，然後進行變更。</span><span class="sxs-lookup"><span data-stu-id="4ac50-176">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="4ac50-177">然後，您可以在飛出的最上方看到所要採取動作的點。最多可能需要24小時才能更新點數。</span><span class="sxs-lookup"><span data-stu-id="4ac50-177">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="4ac50-178">選取 [**透過協力廠商解決**]，因為改進動作已經由協力廠商應用程式或軟體所定址。</span><span class="sxs-lookup"><span data-stu-id="4ac50-178">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="4ac50-179">您可以取得行動的價值，讓您的安全分數更好地反映整體的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="4ac50-179">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="4ac50-180">如果協力廠商不再涵蓋該控制項，您可以將 [改進] 動作標示為 [未完成]。</span><span class="sxs-lookup"><span data-stu-id="4ac50-180">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="4ac50-181">請記住，如果改進動作標示為透過協力廠商解決，則 Microsoft 無法查看是否符合評分需求。</span><span class="sxs-lookup"><span data-stu-id="4ac50-181">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="4ac50-182">選取 [**略**過]，因為您已決定接受風險，而不會制定「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-182">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="4ac50-183">一旦您忽略 [改進] 動作，您可以達到的安全分數點總數即會減少。</span><span class="sxs-lookup"><span data-stu-id="4ac50-183">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="4ac50-184">您可以在歷史記錄中查看此動作，也可以隨時復原。</span><span class="sxs-lookup"><span data-stu-id="4ac50-184">You can view this action in history or undo it at any time.</span></span>

![安全分數改進動作範例](../../media/secure-score/secure-score1x450.png)

<span data-ttu-id="4ac50-186">*圖 2 & 3：改善動作 flyouts*</span><span class="sxs-lookup"><span data-stu-id="4ac50-186">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="4ac50-187">監視隨時間的改進</span><span class="sxs-lookup"><span data-stu-id="4ac50-187">Monitor improvements over time</span></span>

<span data-ttu-id="4ac50-188">您可以在 [**記錄**] 索引標籤中，在一段時間內，查看組織的分數圖表。在圖形下方會列出所選取時間範圍內所執行的所有動作，以及其屬性，例如結果點和類別。</span><span class="sxs-lookup"><span data-stu-id="4ac50-188">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="4ac50-189">您可以自訂日期範圍及依類別篩選。</span><span class="sxs-lookup"><span data-stu-id="4ac50-189">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="4ac50-190">風險認知</span><span class="sxs-lookup"><span data-stu-id="4ac50-190">Risk awareness</span></span>

<span data-ttu-id="4ac50-191">Microsoft Secure 得分是根據系統設定、使用者行為和其他安全性相關度量的安全性狀態的數值摘要;這不是系統或資料被破壞的可能性的絕對度量。</span><span class="sxs-lookup"><span data-stu-id="4ac50-191">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="4ac50-192">相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。</span><span class="sxs-lookup"><span data-stu-id="4ac50-192">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="4ac50-193">沒有任何線上服務完全避免安全缺口，安全分數不得以任何方式轉譯為保證安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="4ac50-193">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="4ac50-194">新功能</span><span class="sxs-lookup"><span data-stu-id="4ac50-194">What's new?</span></span>

<span data-ttu-id="4ac50-195">若要讓 Microsoft 安全評分為您安全性狀況的更好代表，我們進行了一些變更。</span><span class="sxs-lookup"><span data-stu-id="4ac50-195">To make Microsoft Secure Score a better representative of your security posture we have made some changes.</span></span> <span data-ttu-id="4ac50-196">若要深入瞭解規劃的變更，請參閱[Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="4ac50-196">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

### <a name="april-21st-2020"></a><span data-ttu-id="4ac50-197">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="4ac50-197">April 21st 2020</span></span>

#### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="4ac50-198">移除不符合可靠度量期望的改進動作，或不提供安全狀況的有用標記法</span><span class="sxs-lookup"><span data-stu-id="4ac50-198">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="4ac50-199">為了確保 Microsoft 安全分數有意義，且每個改進動作都有意義且可靠，我們正在移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-199">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="4ac50-200">將 IRM 保護套用至檔</span><span class="sxs-lookup"><span data-stu-id="4ac50-200">Apply IRM protections to documents</span></span>
- <span data-ttu-id="4ac50-201">套用資料遺失防護原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-201">Apply Data Loss Prevention policies</span></span>

### <a name="january---march-2020"></a><span data-ttu-id="4ac50-202">一月份-2020 年3月</span><span class="sxs-lookup"><span data-stu-id="4ac50-202">January - March 2020</span></span>

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="4ac50-203">支援 Azure AD 改進動作的安全性預設值</span><span class="sxs-lookup"><span data-stu-id="4ac50-203">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="4ac50-204">Microsoft Secure 得分會更新改進動作，以支援[AZURE AD 中的安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，如此可讓您的組織使用預先設定的常見攻擊安全性設定，以協助保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="4ac50-204">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="4ac50-205">這會影響下列改進動作：</span><span class="sxs-lookup"><span data-stu-id="4ac50-205">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="4ac50-206">確定所有使用者均可完成安全存取的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="4ac50-206">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="4ac50-207">需要對管理角色進行 MFA</span><span class="sxs-lookup"><span data-stu-id="4ac50-207">Require MFA for administrative roles</span></span>
- <span data-ttu-id="4ac50-208">啟用原則以封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="4ac50-208">Enable policy to block legacy authentication</span></span>

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="4ac50-209">移除不符合可靠度量期望的改進動作，或沒有提供安全狀況的有用標記法</span><span class="sxs-lookup"><span data-stu-id="4ac50-209">Removed improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="4ac50-210">為了確保 Microsoft 安全分數有意義，且每個改進動作都有意義且可靠，我們正在移除下列改進動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-210">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="4ac50-211">將使用者檔儲存在商務 OneDrive 中</span><span class="sxs-lookup"><span data-stu-id="4ac50-211">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="4ac50-212">設定 Office 365 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-212">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="4ac50-213">設定 Office 365 安全連結以驗證 URLs</span><span class="sxs-lookup"><span data-stu-id="4ac50-213">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="4ac50-214">不允許信箱委派</span><span class="sxs-lookup"><span data-stu-id="4ac50-214">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="4ac50-215">允許網站和檔的匿名來賓共用連結</span><span class="sxs-lookup"><span data-stu-id="4ac50-215">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="4ac50-216">開啟 Cloud App Security 主控台</span><span class="sxs-lookup"><span data-stu-id="4ac50-216">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="4ac50-217">設定外部共用連結的到期時間</span><span class="sxs-lookup"><span data-stu-id="4ac50-217">Configure expiration time for external sharing links</span></span>
- <span data-ttu-id="4ac50-218">開啟審計資料記錄</span><span class="sxs-lookup"><span data-stu-id="4ac50-218">Turn on audit data recording</span></span>
- <span data-ttu-id="4ac50-219">探索危險且不相容的陰影 IT 應用程式</span><span class="sxs-lookup"><span data-stu-id="4ac50-219">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="4ac50-220">檢查許可權 & 會封鎖連接至您環境的危險 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="4ac50-220">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="4ac50-221">設定 SharePoint 線上文件庫的版本設定</span><span class="sxs-lookup"><span data-stu-id="4ac50-221">Set up versioning on SharePoint online document libraries</span></span>
- <span data-ttu-id="4ac50-222">刪除/封鎖過去30天內未使用的帳戶</span><span class="sxs-lookup"><span data-stu-id="4ac50-222">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="4ac50-223">指定少於5個全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="4ac50-223">Designate fewer than 5 global admins</span></span>

#### <a name="removed-not-scored-improvement-actions"></a><span data-ttu-id="4ac50-224">移除「未計分」的改進動作</span><span class="sxs-lookup"><span data-stu-id="4ac50-224">Removed "not scored" improvement actions</span></span>

<span data-ttu-id="4ac50-225">安全分數的原則之一是，分數應該是標準化的，且與的功能非常輕鬆。</span><span class="sxs-lookup"><span data-stu-id="4ac50-225">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="4ac50-226">具有不具可度量或具可操作性的改進動作已導致混淆。</span><span class="sxs-lookup"><span data-stu-id="4ac50-226">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="4ac50-227">只有在每個建議都會對分數有明確影響時，Microsoft 安全評分才有意義。</span><span class="sxs-lookup"><span data-stu-id="4ac50-227">Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="4ac50-228">不計分的改善動作不可度量。</span><span class="sxs-lookup"><span data-stu-id="4ac50-228">Not scored improvement actions are not measurable.</span></span>  

<span data-ttu-id="4ac50-229">基於這些原因，已移除所有未計分的改善動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-229">For these reasons, all improvement actions that were not scored have been removed.</span></span> <span data-ttu-id="4ac50-230">您的元件不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-230">No action is needed on your part.</span></span>

#### <a name="removed-device-improvement-actions"></a><span data-ttu-id="4ac50-231">移除裝置改進動作</span><span class="sxs-lookup"><span data-stu-id="4ac50-231">Removed device improvement actions</span></span>

<span data-ttu-id="4ac50-232">評估 [改進動作] 的 Microsoft Secure 得分裝置類別之後，它決定這些動作目前評估原則狀態，而不是裝置的設定狀態。</span><span class="sxs-lookup"><span data-stu-id="4ac50-232">After an evaluation of the Microsoft Secure Score device category of improvement actions, it was determined that those actions currently assess the policy state and not the configuration state of devices.</span></span> <span data-ttu-id="4ac50-233">因為設定會直接與安全性狀況相關聯，所以現有的裝置動作決定不完全代表組織狀況。</span><span class="sxs-lookup"><span data-stu-id="4ac50-233">Since configuration is directly tied to security posture, the existing device actions were determined to not fully represent organizational posture.</span></span>  <span data-ttu-id="4ac50-234">當我們運作時，將會移除裝置類別中目前的動作，以提供一組建議，以直接使用診斷資料，以更完整地代表裝置安全狀況。</span><span class="sxs-lookup"><span data-stu-id="4ac50-234">We will be removing the current actions in the device category as we work to provide a set of recommendations which directly use diagnostic data to more fully represent device security posture.</span></span>

<span data-ttu-id="4ac50-235">已移除下列改進動作：</span><span class="sxs-lookup"><span data-stu-id="4ac50-235">The following improvement actions have been removed:</span></span>

- <span data-ttu-id="4ac50-236">啟用 Microsoft Intune 行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="4ac50-236">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="4ac50-237">建立適用于 Android 的 Microsoft Intune 符合性原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-237">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="4ac50-238">建立適用于 Android 的 Microsoft Intune 符合性原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-238">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="4ac50-239">建立適用于 Android 的 Microsoft Intune 應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-239">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="4ac50-240">為 iOS 建立 Microsoft Intune 應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-240">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="4ac50-241">標示未指派為不相容的 Microsoft Intune 符合性原則的裝置</span><span class="sxs-lookup"><span data-stu-id="4ac50-241">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="4ac50-242">為 iOS 建立 Microsoft Intune 符合性原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-242">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="4ac50-243">為 macOS 建立 Microsoft Intune 符合性原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-243">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="4ac50-244">建立適用于 Windows 的 Microsoft Intune 符合性原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-244">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="4ac50-245">建立適用于 Android 的 Microsoft Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="4ac50-245">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="4ac50-246">建立適用于 Android 的 Microsoft Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="4ac50-246">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="4ac50-247">為 macOS 建立 Microsoft Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="4ac50-247">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="4ac50-248">為 iOS 建立 Microsoft Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="4ac50-248">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="4ac50-249">建立 Windows 的 Microsoft Intune 設定檔</span><span class="sxs-lookup"><span data-stu-id="4ac50-249">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="4ac50-250">在 Microsoft Intune 中啟用增強型 jailbreak 偵測</span><span class="sxs-lookup"><span data-stu-id="4ac50-250">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="4ac50-251">需要修補所有裝置，並已啟用防病毒及防火牆</span><span class="sxs-lookup"><span data-stu-id="4ac50-251">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="4ac50-252">啟用 Windows Defender ATP 整合至 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4ac50-252">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="4ac50-253">建立 Microsoft Intune Windows 資訊保護原則</span><span class="sxs-lookup"><span data-stu-id="4ac50-253">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="4ac50-254">要求所有裝置都具有高級安全性設定</span><span class="sxs-lookup"><span data-stu-id="4ac50-254">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="4ac50-255">每週複查封鎖的裝置報告</span><span class="sxs-lookup"><span data-stu-id="4ac50-255">Review blocked devices report weekly</span></span>

#### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="4ac50-256">MFA 改進動作更新</span><span class="sxs-lookup"><span data-stu-id="4ac50-256">MFA improvement action updates</span></span>

<span data-ttu-id="4ac50-257">為了反映公司在套用與業務搭配運作的原則時，是否需要確保 upmost 安全性，Microsoft 安全分數已移除三個改進動作（圍繞多重要素驗證），並新增兩個動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-257">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score has removed three improvement actions centered around multi-factor authentication, and added two.</span></span>

<span data-ttu-id="4ac50-258">已移除改進動作：</span><span class="sxs-lookup"><span data-stu-id="4ac50-258">Removed improvement actions:</span></span>

- <span data-ttu-id="4ac50-259">為多重要素驗證註冊所有使用者</span><span class="sxs-lookup"><span data-stu-id="4ac50-259">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="4ac50-260">需要對所有使用者進行 MFA</span><span class="sxs-lookup"><span data-stu-id="4ac50-260">Require MFA for all users</span></span>
- <span data-ttu-id="4ac50-261">Azure AD 特權角色需要 MFA</span><span class="sxs-lookup"><span data-stu-id="4ac50-261">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="4ac50-262">新增改進動作：</span><span class="sxs-lookup"><span data-stu-id="4ac50-262">Added improvement actions:</span></span>

- <span data-ttu-id="4ac50-263">確定所有使用者均可完成安全存取的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="4ac50-263">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="4ac50-264">需要對管理角色進行 MFA</span><span class="sxs-lookup"><span data-stu-id="4ac50-264">Require MFA for administrative roles</span></span>

 <span data-ttu-id="4ac50-265">這些新的改進動作需要在您的目錄上登錄使用者或系統管理員以進行多重要素驗證（MFA），並建立符合組織需求的適當原則集合。</span><span class="sxs-lookup"><span data-stu-id="4ac50-265">These new improvement actions require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="4ac50-266">主要目標具有彈性，可確保所有使用者和系統管理員都能使用多個因素或以風險為基礎的身分識別驗證提示進行驗證。</span><span class="sxs-lookup"><span data-stu-id="4ac50-266">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="4ac50-267">這可以採取多種原則套用範圍決策，或設定安全性預設值（即將推出3月16日），讓 Microsoft 決定何時對使用者進行 MFA 的質詢。</span><span class="sxs-lookup"><span data-stu-id="4ac50-267">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

#### <a name="removed-review-improvement-actions"></a><span data-ttu-id="4ac50-268">已移除「複查」改進動作</span><span class="sxs-lookup"><span data-stu-id="4ac50-268">Removed "review" improvement actions</span></span>

<span data-ttu-id="4ac50-269">安全分數的原則之一是，分數應該是標準化的，且與的功能非常輕鬆。</span><span class="sxs-lookup"><span data-stu-id="4ac50-269">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="4ac50-270">具有不具可度量或具可操作性的改進動作已導致混淆。</span><span class="sxs-lookup"><span data-stu-id="4ac50-270">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="4ac50-271">只有在每個建議都會對分數有明確影響時，其中一個 Microsoft 安全評分才有意義。</span><span class="sxs-lookup"><span data-stu-id="4ac50-271">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="4ac50-272">「審閱改進」動作與其他 [改進動作] 的標準不是度量。</span><span class="sxs-lookup"><span data-stu-id="4ac50-272">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="4ac50-273">基於這些原因，所有需要審閱節奏的改進動作都會暫時移除。</span><span class="sxs-lookup"><span data-stu-id="4ac50-273">For these reasons, all improvement actions that required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="4ac50-274">您的元件不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="4ac50-274">No action is needed on your part.</span></span>

### <a name="preview-features"></a><span data-ttu-id="4ac50-275">預覽功能</span><span class="sxs-lookup"><span data-stu-id="4ac50-275">Preview features</span></span>

<span data-ttu-id="4ac50-276">[預覽版本](microsoft-secure-score-preview.md)中會包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="4ac50-276">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="4ac50-277">CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖</span><span class="sxs-lookup"><span data-stu-id="4ac50-277">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="4ac50-278">追蹤和基準成績的新方法</span><span class="sxs-lookup"><span data-stu-id="4ac50-278">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="4ac50-279">更好地追蹤和監控分數回歸</span><span class="sxs-lookup"><span data-stu-id="4ac50-279">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="4ac50-280">篩選、標記、搜尋及群組您的改善動作</span><span class="sxs-lookup"><span data-stu-id="4ac50-280">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="4ac50-281">使用分數預測和規劃的動作來管理您的未來目標</span><span class="sxs-lookup"><span data-stu-id="4ac50-281">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="4ac50-282">簡化點數系統</span><span class="sxs-lookup"><span data-stu-id="4ac50-282">Simplification of the points system</span></span>
* <span data-ttu-id="4ac50-283">還有更多！</span><span class="sxs-lookup"><span data-stu-id="4ac50-283">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="4ac50-284">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="4ac50-284">We want to hear from you</span></span>

<span data-ttu-id="4ac50-285">如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。</span><span class="sxs-lookup"><span data-stu-id="4ac50-285">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="4ac50-286">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="4ac50-286">We're monitoring the community and will provide help.</span></span>
