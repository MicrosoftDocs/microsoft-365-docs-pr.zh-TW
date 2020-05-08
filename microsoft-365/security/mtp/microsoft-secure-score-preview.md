---
title: Microsoft 安全評分（預覽）
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分、如何計算詳細資料，以及安全管理員可以使用的方式。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: w10
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
ms.openlocfilehash: 8277549c683da19dbbf915a7cf673fc731cb8803
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141404"
---
# <a name="microsoft-secure-score-preview"></a><span data-ttu-id="db5e2-104">Microsoft 安全評分（預覽）</span><span class="sxs-lookup"><span data-stu-id="db5e2-104">Microsoft Secure Score (preview)</span></span>

>[!IMPORTANT]
><span data-ttu-id="db5e2-105">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="db5e2-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="db5e2-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="db5e2-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="db5e2-107">Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。</span><span class="sxs-lookup"><span data-stu-id="db5e2-107">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="db5e2-108">可在https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。</span><span class="sxs-lookup"><span data-stu-id="db5e2-108">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="db5e2-109">遵循安全性分數建議可保護您的組織免受威脅。</span><span class="sxs-lookup"><span data-stu-id="db5e2-109">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="db5e2-110">透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="db5e2-110">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="db5e2-111">安全分數可協助組織：</span><span class="sxs-lookup"><span data-stu-id="db5e2-111">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="db5e2-112">報告組織安全狀況的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="db5e2-112">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="db5e2-113">提供探索性、可見度、指導方針和控制，以提升安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="db5e2-113">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="db5e2-114">與基準進行比較，並建立關鍵效能指標（KPIs）。</span><span class="sxs-lookup"><span data-stu-id="db5e2-114">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="db5e2-115">組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。</span><span class="sxs-lookup"><span data-stu-id="db5e2-115">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="db5e2-116">分數也可以反映協力廠商的解決方案如何解決建議的動作。</span><span class="sxs-lookup"><span data-stu-id="db5e2-116">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="db5e2-117">此外，您可以透過[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)來存取您的建議和評分。</span><span class="sxs-lookup"><span data-stu-id="db5e2-117">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="db5e2-118">深入瞭解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="db5e2-118">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="db5e2-119">運作方式</span><span class="sxs-lookup"><span data-stu-id="db5e2-119">How it works</span></span>

<span data-ttu-id="db5e2-120">您可以在設定建議的安全性功能、執行安全性相關工作，或使用協力廠商應用程式或軟體來解決改進動作時，獲得相關的點數。</span><span class="sxs-lookup"><span data-stu-id="db5e2-120">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="db5e2-121">有些改進動作只會在完全完成時給予點，有些的動作會在某些裝置或使用者完成時提供部分分數。</span><span class="sxs-lookup"><span data-stu-id="db5e2-121">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="db5e2-122">如果您無法或不想要制定其中一個 [改進] 動作，您可以選擇接受風險或剩餘風險。</span><span class="sxs-lookup"><span data-stu-id="db5e2-122">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="db5e2-123">不管授權為何，我們都會向您顯示一組完整的可能改進功能，讓您瞭解安全性的最佳作法，並提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="db5e2-123">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="db5e2-124">您的絕對安全性狀態是以安全分數表示，不論貴組織擁有的產品授權為何都會保持不變。</span><span class="sxs-lookup"><span data-stu-id="db5e2-124">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="db5e2-125">請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="db5e2-125">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="db5e2-126">您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="db5e2-126">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="db5e2-127">安全分數也會每天同步處理每個動作的取得點數的系統資料。</span><span class="sxs-lookup"><span data-stu-id="db5e2-127">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="db5e2-128">如何計分改進動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-128">How improvement actions are scored</span></span>

<span data-ttu-id="db5e2-129">每個改進動作都值得10點或更少。</span><span class="sxs-lookup"><span data-stu-id="db5e2-129">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="db5e2-130">大多數會以二進位方式計分：若您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。</span><span class="sxs-lookup"><span data-stu-id="db5e2-130">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="db5e2-131">在其他改進動作中，點會指定為總設定的百分比。</span><span class="sxs-lookup"><span data-stu-id="db5e2-131">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="db5e2-132">例如，如果改進的動作指出您使用多重要素驗證來保護所有使用者時取得30點，而且您只會保護 100 5% 以上的使用者，則會得到大約2點的部分分數（5個 protected/100 總計 \* 30 最大值 = 2 pt 部分分數）。</span><span class="sxs-lookup"><span data-stu-id="db5e2-132">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="db5e2-133">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="db5e2-133">Products included in Secure Score</span></span>

<span data-ttu-id="db5e2-134">目前有 Microsoft 365 （包括 Exchange Online）、Azure AD、Microsoft Defender ATP、Azure ATP 和 Cloud App Security 的建議。</span><span class="sxs-lookup"><span data-stu-id="db5e2-134">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="db5e2-135">即將推出其他安全性產品的建議。</span><span class="sxs-lookup"><span data-stu-id="db5e2-135">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="db5e2-136">建議不會涵蓋與各項產品相關聯的所有攻擊面，但也是一個很好的基準。</span><span class="sxs-lookup"><span data-stu-id="db5e2-136">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="db5e2-137">您也可以將改進動作標示為協力廠商所涵蓋的範圍。</span><span class="sxs-lookup"><span data-stu-id="db5e2-137">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="db5e2-138">必要的權限</span><span class="sxs-lookup"><span data-stu-id="db5e2-138">Required permissions</span></span>

<span data-ttu-id="db5e2-139">若要具有存取 Microsoft Secure 得分的許可權，您必須在 Azure Active Directory 中為下列其中一個角色指派。</span><span class="sxs-lookup"><span data-stu-id="db5e2-139">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="db5e2-140">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="db5e2-140">Read and write roles</span></span>

<span data-ttu-id="db5e2-141">透過讀取和寫入權限，您可以進行變更，並直接與安全分數互動。</span><span class="sxs-lookup"><span data-stu-id="db5e2-141">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="db5e2-142">您也可以將唯讀許可權指派給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="db5e2-142">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="db5e2-143">全域管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-143">Global administrator</span></span>
* <span data-ttu-id="db5e2-144">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-144">Security administrator</span></span>
* <span data-ttu-id="db5e2-145">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-145">Exchange administrator</span></span>
* <span data-ttu-id="db5e2-146">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-146">SharePoint administrator</span></span>
* <span data-ttu-id="db5e2-147">帳戶管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-147">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="db5e2-148">唯讀角色</span><span class="sxs-lookup"><span data-stu-id="db5e2-148">Read-only roles</span></span>

<span data-ttu-id="db5e2-149">若具有唯讀許可權，您就無法編輯 [改進動作]、[編輯計分區域] 或 [編輯自訂比較] 的狀態或附注。</span><span class="sxs-lookup"><span data-stu-id="db5e2-149">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="db5e2-150">説明台管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-150">Helpdesk administrator</span></span>
* <span data-ttu-id="db5e2-151">使用者管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-151">User administrator</span></span>
* <span data-ttu-id="db5e2-152">服務管理員</span><span class="sxs-lookup"><span data-stu-id="db5e2-152">Service administrator</span></span>
* <span data-ttu-id="db5e2-153">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="db5e2-153">Security reader</span></span>
* <span data-ttu-id="db5e2-154">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="db5e2-154">Security operator</span></span>
* <span data-ttu-id="db5e2-155">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="db5e2-155">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="db5e2-156">圖形 API</span><span class="sxs-lookup"><span data-stu-id="db5e2-156">Graph API</span></span>

<span data-ttu-id="db5e2-157">若要存取 Graph API，除了 role 之外，您還必須具有下列其中一個範圍：</span><span class="sxs-lookup"><span data-stu-id="db5e2-157">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="db5e2-158">SecurityEvents Read。 All （適用于唯讀角色）</span><span class="sxs-lookup"><span data-stu-id="db5e2-158">SecurityEvents.Read.All (for read-only roles)</span></span>
* <span data-ttu-id="db5e2-159">ReadWrite SecurityEvents （適用于讀取和寫入角色）</span><span class="sxs-lookup"><span data-stu-id="db5e2-159">SecurityEvents.ReadWrite.All (for read and write roles)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="db5e2-160">深入瞭解您的安全性狀況</span><span class="sxs-lookup"><span data-stu-id="db5e2-160">Gain visibility into your security posture</span></span>

<span data-ttu-id="db5e2-161">為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="db5e2-161">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="db5e2-162">Identity （Azure AD 帳戶 & 角色）</span><span class="sxs-lookup"><span data-stu-id="db5e2-162">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="db5e2-163">資料（Microsoft 資訊保護）</span><span class="sxs-lookup"><span data-stu-id="db5e2-163">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="db5e2-164">裝置（Microsoft Defender ATP）</span><span class="sxs-lookup"><span data-stu-id="db5e2-164">Device (Microsoft Defender ATP)</span></span>
* <span data-ttu-id="db5e2-165">應用程式（電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）</span><span class="sxs-lookup"><span data-stu-id="db5e2-165">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="db5e2-166">基礎結構（現在沒有任何改進動作）</span><span class="sxs-lookup"><span data-stu-id="db5e2-166">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="db5e2-167">在 [Microsoft Secure 得分一覽] 頁面中，您可以看到各群組之間的點數如何分割，以及哪些點可供使用。</span><span class="sxs-lookup"><span data-stu-id="db5e2-167">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="db5e2-168">[一覽表] 頁面也是取得整體總分、您的安全分數與基準比較之歷史趨勢的完整視圖，以及可以採取以改善評分的優先改進動作的位置。</span><span class="sxs-lookup"><span data-stu-id="db5e2-168">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="db5e2-169">![安全分數主頁](../../media/secure-score/secure-score-homepage.png)
*圖1： Microsoft Secure 得分一覽頁面*</span><span class="sxs-lookup"><span data-stu-id="db5e2-169">![Secure Score homepage](../../media/secure-score/secure-score-homepage.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="db5e2-170">採取動作以提升您的分數</span><span class="sxs-lookup"><span data-stu-id="db5e2-170">Take action to improve your score</span></span>

<span data-ttu-id="db5e2-171">[**改進動作**] 索引標籤會列出解決可能的攻擊面的安全性建議，及其狀態（to address、已計畫、已被認可的風險、透過協力廠商解決的問題，以及透過取代的緩解，以及已完成）。</span><span class="sxs-lookup"><span data-stu-id="db5e2-171">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="db5e2-172">您可以搜尋、篩選和群組所有的「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="db5e2-172">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="db5e2-173">排名</span><span class="sxs-lookup"><span data-stu-id="db5e2-173">Ranking</span></span>

<span data-ttu-id="db5e2-174">排名是根據剩下的剩餘點數、實施難度、使用者影響和複雜性而定。</span><span class="sxs-lookup"><span data-stu-id="db5e2-174">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="db5e2-175">最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。</span><span class="sxs-lookup"><span data-stu-id="db5e2-175">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="db5e2-176">查看改進動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="db5e2-176">View improvement action details</span></span>

<span data-ttu-id="db5e2-177">當您選取特定的 [提升] 動作時，會出現完整的頁面快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="db5e2-177">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="db5e2-178">![改進動作飛出](../../media/secure-score/secure-score-improvement-action-details.png)
範例*圖2：改進動作飛出範例*</span><span class="sxs-lookup"><span data-stu-id="db5e2-178">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="db5e2-179">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="db5e2-179">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="db5e2-180">選取 [**管理**] 以進入設定畫面並進行變更。</span><span class="sxs-lookup"><span data-stu-id="db5e2-180">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="db5e2-181">接著，您將會在飛出的位置看到必要的動作。點通常需要24小時才能更新。</span><span class="sxs-lookup"><span data-stu-id="db5e2-181">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="db5e2-182">選取 [**共用**]，將直接連結複製到 [改進] 動作，或選擇用來共用連結的平臺，例如電子郵件、microsoft 小組、microsoft Planner 或 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="db5e2-182">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="db5e2-183">選取 [ServiceNow 將可讓您建立 ServiceNow 和 Microsoft 365 的安全性中心首頁會顯示的變更票證。</span><span class="sxs-lookup"><span data-stu-id="db5e2-183">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="db5e2-184">若要深入瞭解，請參閱[Microsoft 365 Security Center 和 ServiceNow integration](tickets.md)。</span><span class="sxs-lookup"><span data-stu-id="db5e2-184">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="db5e2-185">選擇改進動作狀態</span><span class="sxs-lookup"><span data-stu-id="db5e2-185">Choose an improvement action status</span></span>

<span data-ttu-id="db5e2-186">選擇 [改進] 動作特有的任何狀態和記錄附注。</span><span class="sxs-lookup"><span data-stu-id="db5e2-186">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="db5e2-187">您可以選取下列 statues：</span><span class="sxs-lookup"><span data-stu-id="db5e2-187">The statues you can select are the following:</span></span>

* <span data-ttu-id="db5e2-188">**若要解決**此事項，您可以辨識改進動作是必要的，並計畫于未來某一點進行處理。</span><span class="sxs-lookup"><span data-stu-id="db5e2-188">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="db5e2-189">這種狀態也適用于已偵測到部分但未完全完成的動作。</span><span class="sxs-lookup"><span data-stu-id="db5e2-189">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="db5e2-190">已**計畫**-完成改進動作有一些具體的計畫。</span><span class="sxs-lookup"><span data-stu-id="db5e2-190">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="db5e2-191">已**接受風險**-安全性應該一定要與可用性進行平衡，而不是每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="db5e2-191">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="db5e2-192">在這種情況下，您可以選擇接受風險或餘下的風險，而不會制定改進動作。</span><span class="sxs-lookup"><span data-stu-id="db5e2-192">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="db5e2-193">您不會獲得任何點數，但是動作將不再顯示在 [改進動作] 清單中。</span><span class="sxs-lookup"><span data-stu-id="db5e2-193">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="db5e2-194">您可以在歷史記錄中查看此動作，也可以隨時復原。</span><span class="sxs-lookup"><span data-stu-id="db5e2-194">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="db5e2-195">**透過協力廠商解決**，並**透過替代的緩解**措施加以解決--改進動作已經由協力廠商應用程式或軟體或內部工具所解決。</span><span class="sxs-lookup"><span data-stu-id="db5e2-195">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="db5e2-196">您將會獲得值得行動的點數，所以您的分數會更好反映整體的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="db5e2-196">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="db5e2-197">如果協力廠商或內部工具不再涵蓋該控制項，您可以選擇其他狀態。</span><span class="sxs-lookup"><span data-stu-id="db5e2-197">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="db5e2-198">請記住，如果改進動作標示為這兩種狀態，Microsoft 將不會深入瞭解實施的完整性。</span><span class="sxs-lookup"><span data-stu-id="db5e2-198">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="db5e2-199">威脅 & 弱點管理的改進動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-199">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="db5e2-200">在 "Device" 類別中的改進動作，您將無法選擇狀態。</span><span class="sxs-lookup"><span data-stu-id="db5e2-200">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="db5e2-201">相反地，您會將[Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)的相關[威脅 & 漏洞管理（TVM）安全性建議](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)，以採取行動。</span><span class="sxs-lookup"><span data-stu-id="db5e2-201">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="db5e2-202">您選擇的例外狀況和您所撰寫的理由將會特定于該入口網站，而且不會出現在 Microsoft Secure 得分入口網站中。</span><span class="sxs-lookup"><span data-stu-id="db5e2-202">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="db5e2-203">已完成的改進動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-203">Completed improvement actions</span></span>

<span data-ttu-id="db5e2-204">在完成改進動作的所有可能點之後，[改進動作] 的狀態為「已完成」。</span><span class="sxs-lookup"><span data-stu-id="db5e2-204">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="db5e2-205">已完成的改善動作會透過 Microsoft data 加以確認，而且您將無法變更狀態。</span><span class="sxs-lookup"><span data-stu-id="db5e2-205">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="db5e2-206">評估資訊並複查使用者影響</span><span class="sxs-lookup"><span data-stu-id="db5e2-206">Assess information and review user impact</span></span>

<span data-ttu-id="db5e2-207">**在 [一覽**] 區段中，將會告訴您您的類別、可以防禦的攻擊，以及產品。</span><span class="sxs-lookup"><span data-stu-id="db5e2-207">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="db5e2-208">[**使用者影響**] 顯示使用者在已頒佈改進動作時的體驗，以及**受影響的使用者**會顯示誰會體驗。</span><span class="sxs-lookup"><span data-stu-id="db5e2-208">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="db5e2-209">實施改進動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-209">Implement the improvement action</span></span>

<span data-ttu-id="db5e2-210">「**實施**」區段會顯示所有必要條件、逐步後續步驟以完成 [改進] 動作、[改進動作] 的目前實施狀態，以及任何 [深入瞭解] 連結。</span><span class="sxs-lookup"><span data-stu-id="db5e2-210">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="db5e2-211">必要條件會是任何需要取得的授權，或是在解決改進動作之前必須完成的動作。</span><span class="sxs-lookup"><span data-stu-id="db5e2-211">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="db5e2-212">請確定您的授權有足夠的座位，可完成 [改進] 動作，並將這些授權套用至必要的使用者。</span><span class="sxs-lookup"><span data-stu-id="db5e2-212">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="db5e2-213">追蹤您的分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="db5e2-213">Track your score history and meet goals</span></span>

<span data-ttu-id="db5e2-214">您可以在 [**記錄**] 索引標籤中，在一段時間內，查看組織的分數圖表。在圖形下方會列出所選取時間範圍內所執行的所有動作，以及其屬性，例如結果點和類別。</span><span class="sxs-lookup"><span data-stu-id="db5e2-214">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="db5e2-215">您可以自訂日期範圍及依類別篩選。</span><span class="sxs-lookup"><span data-stu-id="db5e2-215">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="db5e2-216">在 [**度量 & 趨勢**] 索引標籤中，有數個圖形可讓您更深入的趨勢及設定目標。</span><span class="sxs-lookup"><span data-stu-id="db5e2-216">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="db5e2-217">您可以設定整個視覺效果頁面的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="db5e2-217">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="db5e2-218">視覺化效果包括：</span><span class="sxs-lookup"><span data-stu-id="db5e2-218">The visualizations include:</span></span>

* <span data-ttu-id="db5e2-219">**您的安全分數區域**-自訂取決於組織的目標和「良好」、「好」和「不良分數」範圍的定義。</span><span class="sxs-lookup"><span data-stu-id="db5e2-219">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="db5e2-220">**回歸趨勢**-因設定、使用者或裝置變更而 regressed 之點的時程表。</span><span class="sxs-lookup"><span data-stu-id="db5e2-220">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="db5e2-221">**比較趨勢**-組織的安全分數與其他時間的比較方式。</span><span class="sxs-lookup"><span data-stu-id="db5e2-221">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="db5e2-222">此視圖可以包含表示具有類似座位元數目之組織之分數平均的行，以及您可以設定的自訂比較視圖。</span><span class="sxs-lookup"><span data-stu-id="db5e2-222">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="db5e2-223">**風險接受趨勢**-標示為「風險已接受」的「改進」動作時程表。</span><span class="sxs-lookup"><span data-stu-id="db5e2-223">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="db5e2-224">**得分變更**-已取得的點數，點 regressed，以及後續得分變更，在指定的日期範圍內。</span><span class="sxs-lookup"><span data-stu-id="db5e2-224">**Score changes** — The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="db5e2-225">風險認知</span><span class="sxs-lookup"><span data-stu-id="db5e2-225">Risk awareness</span></span>

<span data-ttu-id="db5e2-226">Microsoft Secure 得分是根據系統設定、使用者行為和其他安全性相關度量的安全性狀況的數位摘要;這不是系統或資料被破壞的可能性的絕對度量。</span><span class="sxs-lookup"><span data-stu-id="db5e2-226">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="db5e2-227">相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。</span><span class="sxs-lookup"><span data-stu-id="db5e2-227">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="db5e2-228">沒有任何線上服務完全避免安全缺口，安全分數不得以任何方式轉譯為保證安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="db5e2-228">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="db5e2-229">新功能</span><span class="sxs-lookup"><span data-stu-id="db5e2-229">What's new?</span></span> 

<span data-ttu-id="db5e2-230">若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。</span><span class="sxs-lookup"><span data-stu-id="db5e2-230">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="db5e2-231">若要深入瞭解規劃的變更，請參閱[Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)。</span><span class="sxs-lookup"><span data-stu-id="db5e2-231">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

### <a name="april-2020"></a><span data-ttu-id="db5e2-232">2020 年 4 月</span><span class="sxs-lookup"><span data-stu-id="db5e2-232">April 2020</span></span>

#### <a name="added-azure-active-directory-improvement-action"></a><span data-ttu-id="db5e2-233">新增 Azure Active Directory 改進動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-233">Added Azure Active Directory improvement action</span></span>

- <span data-ttu-id="db5e2-234">不允許使用者將同意授與未受管理的應用程式（目前已發行版本本中提供）</span><span class="sxs-lookup"><span data-stu-id="db5e2-234">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a><span data-ttu-id="db5e2-235">新增 Azure 高級威脅防護改進動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-235">Added Azure Advanced Threat Protection improvement actions</span></span>

- <span data-ttu-id="db5e2-236">停用網域控制站上的幕後列印程式服務</span><span class="sxs-lookup"><span data-stu-id="db5e2-236">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="db5e2-237">修改不安全的 Kerberos 委派以防止模仿</span><span class="sxs-lookup"><span data-stu-id="db5e2-237">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="db5e2-238">使用 Microsoft LAPS 保護和管理本機系統管理員密碼</span><span class="sxs-lookup"><span data-stu-id="db5e2-238">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="db5e2-239">降低橫向移動路徑對機密實體的風險</span><span class="sxs-lookup"><span data-stu-id="db5e2-239">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="db5e2-240">移除敏感群組中的睡眠帳戶</span><span class="sxs-lookup"><span data-stu-id="db5e2-240">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="db5e2-241">從實體中移除不安全的 SID 歷程記錄屬性</span><span class="sxs-lookup"><span data-stu-id="db5e2-241">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="db5e2-242">解決不安全的帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="db5e2-242">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="db5e2-243">停止清除文字認證曝光</span><span class="sxs-lookup"><span data-stu-id="db5e2-243">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="db5e2-244">停止舊版通訊協定通訊</span><span class="sxs-lookup"><span data-stu-id="db5e2-244">Stop legacy protocols communication</span></span>
- <span data-ttu-id="db5e2-245">停止弱密碼使用</span><span class="sxs-lookup"><span data-stu-id="db5e2-245">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="db5e2-246">支援 Microsoft Defender ATP 威脅 & 漏洞管理（TVM）安全性建議</span><span class="sxs-lookup"><span data-stu-id="db5e2-246">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>

<span data-ttu-id="db5e2-247">現在提供 TVM 提供的所有發佈安全性建議。</span><span class="sxs-lookup"><span data-stu-id="db5e2-247">All released security recommendations supplied by TVM are now available.</span></span>

### <a name="january---march-2020"></a><span data-ttu-id="db5e2-248">一月份-2020 年3月</span><span class="sxs-lookup"><span data-stu-id="db5e2-248">January - March 2020</span></span>

#### <a name="updated-interface-and-functionality"></a><span data-ttu-id="db5e2-249">更新的介面及功能</span><span class="sxs-lookup"><span data-stu-id="db5e2-249">Updated interface and functionality</span></span>

* <span data-ttu-id="db5e2-250">CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖</span><span class="sxs-lookup"><span data-stu-id="db5e2-250">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="db5e2-251">追蹤和基準成績的新方法</span><span class="sxs-lookup"><span data-stu-id="db5e2-251">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="db5e2-252">更好地追蹤和瞭解分數回歸</span><span class="sxs-lookup"><span data-stu-id="db5e2-252">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="db5e2-253">篩選、標記、搜尋及群組您的改善動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-253">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="db5e2-254">使用分數預測和規劃的動作來管理您的未來目標</span><span class="sxs-lookup"><span data-stu-id="db5e2-254">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="db5e2-255">還有更多！</span><span class="sxs-lookup"><span data-stu-id="db5e2-255">And more!</span></span>

#### <a name="removed-not-scored-and-review-improvement-actions"></a><span data-ttu-id="db5e2-256">移除「未評分」和「複查」改進動作</span><span class="sxs-lookup"><span data-stu-id="db5e2-256">Removed "not scored" and "review" improvement actions</span></span>

<span data-ttu-id="db5e2-257">安全分數的原則之一是，分數應該是標準化的，且與的功能非常輕鬆。</span><span class="sxs-lookup"><span data-stu-id="db5e2-257">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="db5e2-258">具有不具可度量或具可操作性的改進動作已導致混淆。</span><span class="sxs-lookup"><span data-stu-id="db5e2-258">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="db5e2-259">只有在每個建議都會對分數有明確影響時，其中一個 Microsoft 安全評分才有意義。</span><span class="sxs-lookup"><span data-stu-id="db5e2-259">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="db5e2-260">不計分的改善動作不是可測量的，而且與其他改進動作相比，檢查改進動作不會以相同的標準進行度量。</span><span class="sxs-lookup"><span data-stu-id="db5e2-260">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>

<span data-ttu-id="db5e2-261">基於這些原因，所有未計分或要求的改善動作都會暫時移除。</span><span class="sxs-lookup"><span data-stu-id="db5e2-261">For these reasons, all improvement actions that were not scored or required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="db5e2-262">您的元件不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="db5e2-262">No action is needed on your part.</span></span>

#### <a name="simplification-of-the-point-system"></a><span data-ttu-id="db5e2-263">簡化了點系統</span><span class="sxs-lookup"><span data-stu-id="db5e2-263">Simplification of the point system</span></span>

<span data-ttu-id="db5e2-264">若要在多個經驗上標準化點，每個安全分數改進動作點總數已更新為10點以內。</span><span class="sxs-lookup"><span data-stu-id="db5e2-264">To standardize points across multiple experiences, each Secure Score improvement action point total has been updated to be worth 10 points or less.</span></span> <span data-ttu-id="db5e2-265">在目前我們所做的安全性控制的廣泛 breather，以及未來將新增的安全性控制措施，都有一定的一致性。</span><span class="sxs-lookup"><span data-stu-id="db5e2-265">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="db5e2-266">雖然這是一項重大的變更，但您會看到點上有一個下沉，但是安全性狀況不會有任何變更。</span><span class="sxs-lookup"><span data-stu-id="db5e2-266">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="db5e2-267">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="db5e2-267">We want to hear from you</span></span>

<span data-ttu-id="db5e2-268">如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。</span><span class="sxs-lookup"><span data-stu-id="db5e2-268">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="db5e2-269">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="db5e2-269">We're monitoring the community and will provide help.</span></span>
