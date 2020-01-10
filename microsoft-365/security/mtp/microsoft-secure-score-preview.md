---
title: Microsoft 安全分數 （預覽）
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及哪些安全性系統管理員可以預期使用它。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 0f54ee771f4358c5c99c3338366eb277013c15e3
ms.sourcegitcommit: a2e9ab69f99f2069372ccfffd9ef2ffbd8568826
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2020
ms.locfileid: "41012176"
---
# <a name="microsoft-secure-score-preview"></a><span data-ttu-id="1dfde-104">Microsoft 安全分數 （預覽）</span><span class="sxs-lookup"><span data-stu-id="1dfde-104">Microsoft Secure Score (preview)</span></span>

>[!IMPORTANT]
><span data-ttu-id="1dfde-105">一些資訊和有關搶鮮產品，可能會在正式發行之前大幅修改。</span><span class="sxs-lookup"><span data-stu-id="1dfde-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1dfde-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1dfde-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1dfde-107">Microsoft 安全分數是具有較高的數字，表示所採取的多個改進動作的組織的安全性狀態，度量單位。</span><span class="sxs-lookup"><span data-stu-id="1dfde-107">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="1dfde-108">下列建議的安全分數可以防止潛在威脅組織。</span><span class="sxs-lookup"><span data-stu-id="1dfde-108">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="1dfde-109">從 Microsoft 365 安全性中心集中式儀表板，組織可以監視，並在其 Microsoft 365 身分識別、 資料、 app、 裝置和基礎結構的安全性上運作。</span><span class="sxs-lookup"><span data-stu-id="1dfde-109">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="1dfde-110">安全分數可幫助組織：</span><span class="sxs-lookup"><span data-stu-id="1dfde-110">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="1dfde-111">在組織的安全性狀態的目前狀態報告。</span><span class="sxs-lookup"><span data-stu-id="1dfde-111">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="1dfde-112">提供可測知性、 可見性、 指導以及控制項，以提高其安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="1dfde-112">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="1dfde-113">比較基準，並建立關鍵效能指標 (Kpi)。</span><span class="sxs-lookup"><span data-stu-id="1dfde-113">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="1dfde-114">組織存取的評量和趨勢，與其他 Microsoft 產品整合、 分數比較與類似的組織，以及執行更多功能強大的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="1dfde-114">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="1dfde-115">分數也可反映協力廠商解決方案時解決建議的動作。</span><span class="sxs-lookup"><span data-stu-id="1dfde-115">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="1dfde-116">此外，您可以存取您的建議，以及分數透過[Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api)。</span><span class="sxs-lookup"><span data-stu-id="1dfde-116">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="1dfde-117">了解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="1dfde-117">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="1dfde-118">運作方式</span><span class="sxs-lookup"><span data-stu-id="1dfde-118">How it works</span></span>

<span data-ttu-id="1dfde-119">您所設定的特定點建議的安全性功能，執行與安全性相關的工作，或解決與協力廠商應用程式或軟體的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="1dfde-119">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="1dfde-120">一些改進動作只提供點完全完成時，和某些授與部分點為單位，如果他們使用某些裝置或使用者完成。</span><span class="sxs-lookup"><span data-stu-id="1dfde-120">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="1dfde-121">如果您無法或不想要達成其中一個改進動作，您可以選擇接受風險或其餘的風險。</span><span class="sxs-lookup"><span data-stu-id="1dfde-121">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="1dfde-122">我們示範整組可能的改進功能，無論授權，因此您可以了解安全性最佳做法，並改善您的分數。</span><span class="sxs-lookup"><span data-stu-id="1dfde-122">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="1dfde-123">安全分數，無論哪項產品授權您的組織相同擁有哪些保持代表您的絕對的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="1dfde-123">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="1dfde-124">請記住，應取得平衡安全性與可用性，並不是每個建議才能為您的環境。</span><span class="sxs-lookup"><span data-stu-id="1dfde-124">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="1dfde-125">您的分數會更新以反映視覺效果和改進動作頁面中所呈現的資訊的即時。</span><span class="sxs-lookup"><span data-stu-id="1dfde-125">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="1dfde-126">安全分數也每天同步處理以接收關於每個動作您達成點為單位的系統資料。</span><span class="sxs-lookup"><span data-stu-id="1dfde-126">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="1dfde-127">如何改進動作，就會獲得</span><span class="sxs-lookup"><span data-stu-id="1dfde-127">How improvement actions are scored</span></span>

<span data-ttu-id="1dfde-128">每個改進動作是值得 10 點或更少。</span><span class="sxs-lookup"><span data-stu-id="1dfde-128">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="1dfde-129">二進位的方式，就會獲得最-如果您實作的改進巨集指令，如建立新的原則，或開啟的特定設定，您會收到的資料點的 100%。</span><span class="sxs-lookup"><span data-stu-id="1dfde-129">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="1dfde-130">其他改進的動作，點都指定的百分比的總組態。</span><span class="sxs-lookup"><span data-stu-id="1dfde-130">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="1dfde-131">例如，如果改進巨集指令會指出您取得 30 點保護您的所有使用者以多重要素驗證和您只需要 100 個受保護的總使用者 5，會提供您大約 2 點的部分分數 (受保護的 5 / 100 總 \* 30 的最大點數 = 2 點數部分分數)。</span><span class="sxs-lookup"><span data-stu-id="1dfde-131">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="1dfde-132">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="1dfde-132">Products included in Secure Score</span></span>

<span data-ttu-id="1dfde-133">目前有 Office 365 （包括 SharePoint Online、 Exchange Online、 OneDrive for Business、 Microsoft 資訊保護和更多），建議 Azure AD，Intune、 Microsoft Defender ATP 和 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="1dfde-133">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, Intune, Microsoft Defender ATP, and Cloud App Security.</span></span> <span data-ttu-id="1dfde-134">建議的其他安全性產品即將推出。</span><span class="sxs-lookup"><span data-stu-id="1dfde-134">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="1dfde-135">建議將涵蓋每個產品相關聯的所有受攻擊面，但它們是不錯的比較基準。</span><span class="sxs-lookup"><span data-stu-id="1dfde-135">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="1dfde-136">您也可以將標示改進動作為所涵蓋的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="1dfde-136">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="1dfde-137">必要的權限</span><span class="sxs-lookup"><span data-stu-id="1dfde-137">Required permissions</span></span>

<span data-ttu-id="1dfde-138">若要存取 Microsoft 安全分數的權限，您必須獲指派其中一個 Azure Active Directory 中的下列角色。</span><span class="sxs-lookup"><span data-stu-id="1dfde-138">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="1dfde-139">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="1dfde-139">Read and write roles</span></span>

<span data-ttu-id="1dfde-140">讀取與寫入權限，您可以進行的變更，並直接互動安全分數。</span><span class="sxs-lookup"><span data-stu-id="1dfde-140">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="1dfde-141">您也可以指派給其他使用者的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="1dfde-141">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="1dfde-142">全域管理員</span><span class="sxs-lookup"><span data-stu-id="1dfde-142">Global administrator</span></span>
* <span data-ttu-id="1dfde-143">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="1dfde-143">Security administrator</span></span>
* <span data-ttu-id="1dfde-144">Exchange 管理員</span><span class="sxs-lookup"><span data-stu-id="1dfde-144">Exchange administrator</span></span>
* <span data-ttu-id="1dfde-145">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="1dfde-145">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="1dfde-146">唯讀的角色</span><span class="sxs-lookup"><span data-stu-id="1dfde-146">Read-only roles</span></span>

<span data-ttu-id="1dfde-147">具有唯讀存取權，您不能編輯狀態] 或 [備忘稿改進巨集指令、 編輯分數區域，或編輯自訂比較。</span><span class="sxs-lookup"><span data-stu-id="1dfde-147">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="1dfde-148">服務台管理員</span><span class="sxs-lookup"><span data-stu-id="1dfde-148">Helpdesk administrator</span></span>
* <span data-ttu-id="1dfde-149">使用者系統管理員</span><span class="sxs-lookup"><span data-stu-id="1dfde-149">User administrator</span></span>
* <span data-ttu-id="1dfde-150">服務管理員</span><span class="sxs-lookup"><span data-stu-id="1dfde-150">Service administrator</span></span>
* <span data-ttu-id="1dfde-151">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="1dfde-151">Security reader</span></span>
* <span data-ttu-id="1dfde-152">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="1dfde-152">Security operator</span></span>
* <span data-ttu-id="1dfde-153">全域的讀取者</span><span class="sxs-lookup"><span data-stu-id="1dfde-153">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="1dfde-154">Graph API</span><span class="sxs-lookup"><span data-stu-id="1dfde-154">Graph API</span></span>

<span data-ttu-id="1dfde-155">若要存取 Graph API，您需要有下列其中一個角色除了下列範圍：</span><span class="sxs-lookup"><span data-stu-id="1dfde-155">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="1dfde-156">SecurityEvents.Read.All （適用於唯讀角色）</span><span class="sxs-lookup"><span data-stu-id="1dfde-156">SecurityEvents.Read.All (for read-only roles)</span></span>
* <span data-ttu-id="1dfde-157">SecurityEvents.ReadWrite.All (針對讀取和寫入角色)</span><span class="sxs-lookup"><span data-stu-id="1dfde-157">SecurityEvents.ReadWrite.All (for read and write roles)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="1dfde-158">取得您的安全性狀態的可視性</span><span class="sxs-lookup"><span data-stu-id="1dfde-158">Gain visibility into your security posture</span></span>

<span data-ttu-id="1dfde-159">為了協助您更快速地需要的資訊，Microsoft 改進動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="1dfde-159">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="1dfde-160">身分識別 （Azure AD 帳戶 & 角色與 Azure ATP 即將推出）</span><span class="sxs-lookup"><span data-stu-id="1dfde-160">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="1dfde-161">資料 (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="1dfde-161">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="1dfde-162">裝置 （Microsoft Defender ATP 裝置）</span><span class="sxs-lookup"><span data-stu-id="1dfde-162">Device (Microsoft Defender ATP devices)</span></span>
* <span data-ttu-id="1dfde-163">應用程式 （電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）</span><span class="sxs-lookup"><span data-stu-id="1dfde-163">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="1dfde-164">基礎結構 （Azure 的資源）</span><span class="sxs-lookup"><span data-stu-id="1dfde-164">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="1dfde-165">在 [Microsoft 安全分數概觀] 頁面中，您可以看到點分割的方式這些群組與何種點可用之間。</span><span class="sxs-lookup"><span data-stu-id="1dfde-165">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="1dfde-166">[概觀] 頁面上也是以取得總分基準比較，與您安全分數的歷史趨勢的全面檢視的位置，並可以採取來改善您的分數的改進動作的優先順序。</span><span class="sxs-lookup"><span data-stu-id="1dfde-166">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="1dfde-167">![安全分數首頁](../media/secure-score/secure-score-homepage.png)
*圖 1: Microsoft 安全分數概觀] 頁面上*</span><span class="sxs-lookup"><span data-stu-id="1dfde-167">![Secure Score homepage](../media/secure-score/secure-score-homepage.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="1dfde-168">採取動作來改善您的分數</span><span class="sxs-lookup"><span data-stu-id="1dfde-168">Take action to improve your score</span></span>

<span data-ttu-id="1dfde-169">改進動作] 索引標籤列出解決可能受攻擊面，以及其狀態的安全性建議 （已完成且計劃，風險接受，第三廠商，與地址）。</span><span class="sxs-lookup"><span data-stu-id="1dfde-169">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, planned, risk accepted, third party, and to address).</span></span> <span data-ttu-id="1dfde-170">您可以搜尋、 篩選和群組改進的所有動作。</span><span class="sxs-lookup"><span data-stu-id="1dfde-170">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="1dfde-171">排名</span><span class="sxs-lookup"><span data-stu-id="1dfde-171">Ranking</span></span>

<span data-ttu-id="1dfde-172">排名根據由左到達成，實作困難，使用者的影響和複雜性的其餘點的數目。</span><span class="sxs-lookup"><span data-stu-id="1dfde-172">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="1dfde-173">最高排名的改進動作有大量的剩餘低困難、 使用者的影響，與複雜性的點。</span><span class="sxs-lookup"><span data-stu-id="1dfde-173">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="1dfde-174">動作</span><span class="sxs-lookup"><span data-stu-id="1dfde-174">Actions</span></span>

<span data-ttu-id="1dfde-175">當您選取特定的改進巨集指令時，整頁彈出式視窗隨即出現。</span><span class="sxs-lookup"><span data-stu-id="1dfde-175">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="1dfde-176">![改進巨集指令彈出式範例](../media/secure-score/secure-score-improvement-action.png)
*圖 2： 改進巨集指令彈出式範例*</span><span class="sxs-lookup"><span data-stu-id="1dfde-176">![Improvement action flyout example](../media/secure-score/secure-score-improvement-action.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="1dfde-177">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="1dfde-177">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="1dfde-178">選取 [**管理**回到 [設定] 畫面，並進行變更。</span><span class="sxs-lookup"><span data-stu-id="1dfde-178">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="1dfde-179">然後，您將取得巨集指令，值得中為可見的飛出視窗中的點。點通常需要大約 24 小時更新。</span><span class="sxs-lookup"><span data-stu-id="1dfde-179">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="1dfde-180">選取 [**共用**複製直接連結到的改進巨集指令，或選擇要共用的連結，例如電子郵件、 Microsoft Teams、 Microsoft Planner 或 ServiceNow 的平台。</span><span class="sxs-lookup"><span data-stu-id="1dfde-180">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="1dfde-181">選取 ServiceNow 可讓您建立變更票證也就是顯示在 ServiceNow 和 Microsoft 365 安全性中心首頁。</span><span class="sxs-lookup"><span data-stu-id="1dfde-181">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="1dfde-182">若要深入了解，請參閱[Microsoft 365 安全中心和 ServiceNow 整合](tickets.md)。</span><span class="sxs-lookup"><span data-stu-id="1dfde-182">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets.md).</span></span>

* <span data-ttu-id="1dfde-183">選取 [**編輯狀態和記事**] 以編輯任何手動狀態或錄製備忘稿特有的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="1dfde-183">Select **Edit status and notes** to edit any manual statuses or record notes specific to the improvement action.</span></span> <span data-ttu-id="1dfde-184">您可以篩選或群組所改進動作] 索引標籤中狀態。您可以選取雕像如下所示</span><span class="sxs-lookup"><span data-stu-id="1dfde-184">You can filter or group by the statuses in the improvement actions tab. The statues you can select are the following</span></span>

    * <span data-ttu-id="1dfde-185">**地址**-您辨識改進巨集指令是必要的而且打算在未來解決在某個時間點。</span><span class="sxs-lookup"><span data-stu-id="1dfde-185">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="1dfde-186">此狀態下也適用於部分，但未完全完成時會偵測的動作。</span><span class="sxs-lookup"><span data-stu-id="1dfde-186">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
    * <span data-ttu-id="1dfde-187">**計劃**— 中準備就緒可以完成的改進巨集指令沒有具體計劃。</span><span class="sxs-lookup"><span data-stu-id="1dfde-187">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
    * <span data-ttu-id="1dfde-188">**風險接受**— 安全性應該一律平衡與可用性，並不是每個建議適用於您的環境。</span><span class="sxs-lookup"><span data-stu-id="1dfde-188">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="1dfde-189">時，這種情況，您可以選擇要接受風險; 或是其餘的風險，並不制訂的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="1dfde-189">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="1dfde-190">您不會提供任何點，但巨集指令不再是可見的改進動作清單中。</span><span class="sxs-lookup"><span data-stu-id="1dfde-190">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="1dfde-191">您可以檢視歷程記錄中的此巨集指令或復原在任何時間。</span><span class="sxs-lookup"><span data-stu-id="1dfde-191">You can view this action in history or undo it at any time.</span></span>
    * <span data-ttu-id="1dfde-192">**透過協力廠商解決**— 由協力廠商應用程式或軟體已處理過的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="1dfde-192">**Resolve through third party** — The improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="1dfde-193">讓您的成績更妥善地反映您的整體安全性狀態，您將能夠值得了巨集指令的點。</span><span class="sxs-lookup"><span data-stu-id="1dfde-193">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="1dfde-194">如果協力廠商不再涵蓋控制項，您可以選擇另一個狀態。</span><span class="sxs-lookup"><span data-stu-id="1dfde-194">If a third party no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="1dfde-195">請記住，Microsoft 就會有任何可見性實作的完整性，如果改進巨集指令會標示為透過協力廠商解決</span><span class="sxs-lookup"><span data-stu-id="1dfde-195">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as resolved through third party</span></span>

### <a name="prerequisites"></a><span data-ttu-id="1dfde-196">必要條件</span><span class="sxs-lookup"><span data-stu-id="1dfde-196">Prerequisites</span></span>

<span data-ttu-id="1dfde-197">任何需要可獲得授權或需要解決的改進巨集指令先完成的動作，將會列出實作] 區段中的必要條件。</span><span class="sxs-lookup"><span data-stu-id="1dfde-197">Prerequisites in the Implementation section will list any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="1dfde-198">請確定您在您完成的改進巨集指令的授權中有足夠的基座，而且這些授權可套用至所需的使用者。</span><span class="sxs-lookup"><span data-stu-id="1dfde-198">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="1dfde-199">追蹤您的分數歷程記錄，以及達成目標</span><span class="sxs-lookup"><span data-stu-id="1dfde-199">Track your score history and meet goals</span></span>

<span data-ttu-id="1dfde-200">您可以檢視圖表，貴組織的分數經過一段時間**歷程記錄**中的圖形下方] 索引標籤所採取的所選的時間範圍和其屬性，例如產生點及類別中的所有動作的清單。</span><span class="sxs-lookup"><span data-stu-id="1dfde-200">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="1dfde-201">您可以依類別自訂日期範圍與篩選器。</span><span class="sxs-lookup"><span data-stu-id="1dfde-201">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="1dfde-202">在 [**度量資訊 & 趨勢**] 索引標籤中，有數個圖形與圖表提供更多的可見性趨勢，並設定目標。</span><span class="sxs-lookup"><span data-stu-id="1dfde-202">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="1dfde-203">您可以設定整頁的視覺效果的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1dfde-203">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="1dfde-204">視覺效果包括：</span><span class="sxs-lookup"><span data-stu-id="1dfde-204">The visualizations include:</span></span>

* <span data-ttu-id="1dfde-205">**您的安全分數區域**— 自訂根據貴組織的目標和良好、 沒問題，以及不正確的分數的定義範圍。</span><span class="sxs-lookup"><span data-stu-id="1dfde-205">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="1dfde-206">**迴歸分析趨勢**— 時間表，因為組態、 使用者或裝置變更有迴歸去的點數。</span><span class="sxs-lookup"><span data-stu-id="1dfde-206">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="1dfde-207">**比較趨勢**— 如何貴組織的安全分數會比較給其他人的一段時間。</span><span class="sxs-lookup"><span data-stu-id="1dfde-207">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="1dfde-208">此檢視可包含行代表分數的組織具有類似的基座計數和平均您可以設定自訂比較檢視。</span><span class="sxs-lookup"><span data-stu-id="1dfde-208">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="1dfde-209">**風險驗收趨勢**— 時間表的改進動作標示為 「 公認的風險 」。</span><span class="sxs-lookup"><span data-stu-id="1dfde-209">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="1dfde-210">**分數變更**— 點數目可達到、 points 迴歸，] 或 [新動作新增，以及後續分數變更，在指定的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="1dfde-210">**Score changes** — The number of points achieved, points regressed, or new actions added, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="1dfde-211">風險認知</span><span class="sxs-lookup"><span data-stu-id="1dfde-211">Risk awareness</span></span>

<span data-ttu-id="1dfde-212">Microsoft 安全分數是您的安全性狀態的數字摘要根據系統設定、 使用者行為及其他安全性相關的度量值;它不是絕對的度量單位的方式可能會破壞您的系統或資料。</span><span class="sxs-lookup"><span data-stu-id="1dfde-212">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="1dfde-213">相反地，它表示要採用的安全性控制 Microsoft 環境中可協助位移正在外洩的風險的程度。</span><span class="sxs-lookup"><span data-stu-id="1dfde-213">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="1dfde-214">沒有線上服務已完全免於安全性弱點，以及安全分數不應該解譯成保證郵件可以針對任何方式的安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="1dfde-214">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="1dfde-215">下來什麼？</span><span class="sxs-lookup"><span data-stu-id="1dfde-215">What's coming?</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="1dfde-216">MFA 改進動作更新</span><span class="sxs-lookup"><span data-stu-id="1dfde-216">MFA improvement action updates</span></span>

<span data-ttu-id="1dfde-217">若要反映適用於企業以確保 upmost 安全性時，套用原則可搭配其業務需求，Microsoft 安全分數會移除三個改進動作圍繞多重要素驗證，並新增兩個。</span><span class="sxs-lookup"><span data-stu-id="1dfde-217">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="1dfde-218">會移除三個：</span><span class="sxs-lookup"><span data-stu-id="1dfde-218">The three that will be removed:</span></span>
- <span data-ttu-id="1dfde-219">登錄所有使用者的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="1dfde-219">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="1dfde-220">需要 MFA 的所有使用者</span><span class="sxs-lookup"><span data-stu-id="1dfde-220">Require MFA for all users</span></span>
- <span data-ttu-id="1dfde-221">需要 MFA 的 Azure AD 特殊權限角色</span><span class="sxs-lookup"><span data-stu-id="1dfde-221">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="1dfde-222">新的改進動作：</span><span class="sxs-lookup"><span data-stu-id="1dfde-222">New improvement actions:</span></span>
- <span data-ttu-id="1dfde-223">確定所有的使用者可以完成的安全存取多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="1dfde-223">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="1dfde-224">需要 MFA 的系統管理角色</span><span class="sxs-lookup"><span data-stu-id="1dfde-224">Require MFA for administrative roles</span></span>

 <span data-ttu-id="1dfde-225">這些新的改進動作將會需要透過您的目錄中註冊您的使用者或系統管理員針對多重要素驗證 (MFA)，以及建立正確的一組原則符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="1dfde-225">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="1dfde-226">主要目標是有彈性，同時確保所有使用者和系統管理員可以驗證與多重因素或風險式身分識別驗證提示。</span><span class="sxs-lookup"><span data-stu-id="1dfde-226">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="1dfde-227">可能需要的設定，可讓 Microsoft 決定何時挑戰使用者的 mfa 功能、 安全性預設表單，或具有多個原則套用的範圍決策。</span><span class="sxs-lookup"><span data-stu-id="1dfde-227">That can take the form of setting security defaults that let Microsoft decide when to challenge users for MFA, or having multiple policies that apply scoped decisions.</span></span>

## <a name="whats-new"></a><span data-ttu-id="1dfde-228">新功能？</span><span class="sxs-lookup"><span data-stu-id="1dfde-228">What’s new?</span></span> 

<span data-ttu-id="1dfde-229">讓 Microsoft 安全分數更好您的安全性狀態的人，以及改善可用性，我們已進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="1dfde-229">To make Microsoft Secure Score a better representative of your security posture and improve usability, we have made some changes.</span></span> <span data-ttu-id="1dfde-230">已變更您的成績和最大可能分數。</span><span class="sxs-lookup"><span data-stu-id="1dfde-230">Your score and the maximum possible score have changed.</span></span> <span data-ttu-id="1dfde-231">不過，這並不表示您的安全性狀態變更。</span><span class="sxs-lookup"><span data-stu-id="1dfde-231">However, this does not imply a change in your security posture.</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="1dfde-232">更新的介面和功能</span><span class="sxs-lookup"><span data-stu-id="1dfde-232">Updated interface and functionality</span></span>

* <span data-ttu-id="1dfde-233">首席資訊安全長的所有新評量和趨勢檢視，而且會導致層級的討論區</span><span class="sxs-lookup"><span data-stu-id="1dfde-233">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="1dfde-234">追蹤及基準測試您的分數的新方法</span><span class="sxs-lookup"><span data-stu-id="1dfde-234">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="1dfde-235">更好的追蹤，以及了解適用於分數衰退</span><span class="sxs-lookup"><span data-stu-id="1dfde-235">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="1dfde-236">篩選、 標記、 搜尋及群組改進動作</span><span class="sxs-lookup"><span data-stu-id="1dfde-236">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="1dfde-237">管理向您未來的目標，使用分數估算和計劃的動作</span><span class="sxs-lookup"><span data-stu-id="1dfde-237">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="1dfde-238">還有更多 ！</span><span class="sxs-lookup"><span data-stu-id="1dfde-238">And more!</span></span>

### <a name="removed-not-scored-and-review-improvement-actions"></a><span data-ttu-id="1dfde-239">移除 「 不計分 」 和 「 檢閱 」 改進動作</span><span class="sxs-lookup"><span data-stu-id="1dfde-239">Removed “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="1dfde-240">之一的安全分數原則是分數應依照標準化預定且更容易與相關。</span><span class="sxs-lookup"><span data-stu-id="1dfde-240">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="1dfde-241">具有不是可以測量或可採取行動的改進動作具有已造成混淆。</span><span class="sxs-lookup"><span data-stu-id="1dfde-241">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="1dfde-242">一個 Microsoft 安全分數僅合理時的每個建議有清除影響分數。</span><span class="sxs-lookup"><span data-stu-id="1dfde-242">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="1dfde-243">不計分的改進動作不是可以測量的並檢閱動作不會測量為其他改進動作的同一個標準的改進。</span><span class="sxs-lookup"><span data-stu-id="1dfde-243">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>

<span data-ttu-id="1dfde-244">基於這些理由，已被暫時移除所有已不會被記錄或需要檢閱頻率的改進動作。</span><span class="sxs-lookup"><span data-stu-id="1dfde-244">For these reasons, all improvement actions that were not scored or required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="1dfde-245">在您的組件上不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="1dfde-245">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="1dfde-246">簡化的點系統</span><span class="sxs-lookup"><span data-stu-id="1dfde-246">Simplification of the point system</span></span>

<span data-ttu-id="1dfde-247">若要跨多個體驗標準化點，每個安全分數改進巨集指令點總計已經更新為 10 點值得或更少。</span><span class="sxs-lookup"><span data-stu-id="1dfde-247">To standardize points across multiple experiences, each Secure Score improvement action point total has been updated to be worth 10 points or less.</span></span> <span data-ttu-id="1dfde-248">視需要在我們今天有的安全性控制和我們將在未來新增的探索寬口氣是更一致。</span><span class="sxs-lookup"><span data-stu-id="1dfde-248">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="1dfde-249">雖然這是重大變更，您會看到以點合計放置會有不會變更您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="1dfde-249">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="1dfde-250">我們想要從您聽到</span><span class="sxs-lookup"><span data-stu-id="1dfde-250">We want to hear from you</span></span>

<span data-ttu-id="1dfde-251">如果您有任何問題，請讓我們知道[安全性、 隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社群中的張貼。</span><span class="sxs-lookup"><span data-stu-id="1dfde-251">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="1dfde-252">我們正在監視社群，並將提供的說明。</span><span class="sxs-lookup"><span data-stu-id="1dfde-252">We're monitoring the community and will provide help.</span></span>
