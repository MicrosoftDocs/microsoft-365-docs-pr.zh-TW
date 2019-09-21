---
title: Microsoft 安全分數
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
ms.openlocfilehash: 17d2decc7374d9022c68cbe2f2d58da959f44a7d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078357"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="dffb7-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="dffb7-104">Microsoft Secure Score</span></span>

>[!IMPORTANT]
><span data-ttu-id="dffb7-105">一些資訊和有關搶鮮產品，可能會在正式發行之前大幅修改。</span><span class="sxs-lookup"><span data-stu-id="dffb7-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dffb7-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="dffb7-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="dffb7-107">與 Microsoft 安全分數 Microsoft 365 安全中心內，您可以增加可見性，並控制貴組織的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="dffb7-107">With Microsoft Secure Score in the Microsoft 365 security center, you can have increased visibility and control over your organization’s security posture.</span></span> <span data-ttu-id="dffb7-108">從集中式的儀表板中，您可以監視並改善 Microsoft 365 的身分識別、 資料、 應用程式、 裝置及基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="dffb7-108">From a centralized dashboard you can monitor and improve the security for your Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="dffb7-109">Microsoft 安全分數會提供健全的視覺效果，與其他 Microsoft 產品] 的整合您與其他公司，篩選類別，以及執行更多功能的分數的比較。</span><span class="sxs-lookup"><span data-stu-id="dffb7-109">Microsoft Secure Score gives you robust visualizations, integration with other Microsoft products, comparison of your score with other companies, filtering by category, and much more.</span></span> <span data-ttu-id="dffb7-110">工具]，您可以在組織內完成安全性改進動作與追蹤您的分數的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="dffb7-110">With the tool, you can complete security improvement actions within your organization and track the history of your score.</span></span> <span data-ttu-id="dffb7-111">分數也可反映協力廠商解決方案時解決建議的改進動作。</span><span class="sxs-lookup"><span data-stu-id="dffb7-111">The score can also reflect when third-party solutions have addressed recommended improvement actions.</span></span>  

## <a name="how-it-works"></a><span data-ttu-id="dffb7-112">運作方式</span><span class="sxs-lookup"><span data-stu-id="dffb7-112">How it works</span></span>

<span data-ttu-id="dffb7-113">您所設定的特定點建議的安全性功能，執行與安全性相關的工作 （例如檢視報表），或解決與協力廠商應用程式或軟體的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dffb7-113">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="dffb7-114">某些動作，就會獲得的部分完成時，例如啟用使用者的多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="dffb7-114">Some actions are scored for partial completion, like enabling multi-factor authentication (MFA) for your users.</span></span> <span data-ttu-id="dffb7-115">安全性應該一律平衡與可用性，並不是每個建議適用於您的環境。</span><span class="sxs-lookup"><span data-stu-id="dffb7-115">Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="dffb7-116">必要的權限</span><span class="sxs-lookup"><span data-stu-id="dffb7-116">Required permissions</span></span>

<span data-ttu-id="dffb7-117">目前，若要檢視 Microsoft 安全分數，您必須獲指派其中一個 Azure Active Directory 中的下列角色：</span><span class="sxs-lookup"><span data-stu-id="dffb7-117">Currently, to view Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory:</span></span>

* <span data-ttu-id="dffb7-118">全域管理員</span><span class="sxs-lookup"><span data-stu-id="dffb7-118">Global Administrator</span></span>
* <span data-ttu-id="dffb7-119">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="dffb7-119">Security Administrator</span></span>
* <span data-ttu-id="dffb7-120">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="dffb7-120">Security Reader</span></span>

## <a name="rich-experiences--additional-security-recommendations"></a><span data-ttu-id="dffb7-121">豐富體驗 & 額外的安全性建議</span><span class="sxs-lookup"><span data-stu-id="dffb7-121">Rich experiences & additional security recommendations</span></span>

<span data-ttu-id="dffb7-122">Microsoft 安全分數，我們新增了建議從 Azure AD，Intune 和雲端 App 安全性，建議從 Azure 資訊安全中心和 Microsoft Defender ATP 即將推出。</span><span class="sxs-lookup"><span data-stu-id="dffb7-122">In Microsoft Secure Score, we’ve added recommendations from Azure AD, Intune, and Cloud App Security, with recommendations from Azure Security Center and Microsoft Defender ATP coming soon.</span></span> <span data-ttu-id="dffb7-123">我們也已新增更多 Office 365 安全性建議。</span><span class="sxs-lookup"><span data-stu-id="dffb7-123">We've also added even more Office 365 security recommendations.</span></span> <span data-ttu-id="dffb7-124">與其他的見解和更多的可見性廣泛的 Microsoft 產品和服務，您可以信心最管理有關貴組織的安全性狀況報告。</span><span class="sxs-lookup"><span data-stu-id="dffb7-124">With additional insights and more visibility into a broader set of Microsoft products and services, you can feel confident reporting up to management about your organization’s security health.</span></span> <span data-ttu-id="dffb7-125">您也可以取得您使用[Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)的分數。</span><span class="sxs-lookup"><span data-stu-id="dffb7-125">You can also get your score using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).</span></span>

<span data-ttu-id="dffb7-126">為了協助您更快速地需要的資訊，Microsoft 建議會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="dffb7-126">To help you the information you need more quickly, Microsoft recommendations are organized into groups:</span></span>

* <span data-ttu-id="dffb7-127">身分識別 （Azure AD 帳戶和角色的保護狀態）</span><span class="sxs-lookup"><span data-stu-id="dffb7-127">Identity (protection state of your Azure AD accounts and roles)</span></span>
* <span data-ttu-id="dffb7-128">資料 （Office 365 文件的保護狀態）</span><span class="sxs-lookup"><span data-stu-id="dffb7-128">Data (protection state of your Office 365 documents)</span></span>
* <span data-ttu-id="dffb7-129">裝置的裝置; （保護狀態Microsoft Defender ATP 改進動作即將推出）</span><span class="sxs-lookup"><span data-stu-id="dffb7-129">Device (protection state of your devices; Microsoft Defender ATP improvement actions coming soon)</span></span>
* <span data-ttu-id="dffb7-130">應用程式 （保護狀態的電子郵件部署與雲端應用程式）</span><span class="sxs-lookup"><span data-stu-id="dffb7-130">App (protection state of your email and cloud apps)</span></span>
* <span data-ttu-id="dffb7-131">基礎結構 （您 Azure 的資源的保護狀態; 即將推出）</span><span class="sxs-lookup"><span data-stu-id="dffb7-131">Infrastructure (protection state of your Azure resources; coming soon)</span></span>

<span data-ttu-id="dffb7-132">在 [Microsoft 安全分數概觀] 頁面中，您可以看到點分割的方式這些群組與何種點可用之間。</span><span class="sxs-lookup"><span data-stu-id="dffb7-132">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="dffb7-133">[概觀] 頁面上也是以取得總分基準比較，與您安全分數的歷史趨勢的全面檢視的位置，並可以採取來改善您的分數的改進動作的優先順序。</span><span class="sxs-lookup"><span data-stu-id="dffb7-133">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span> <span data-ttu-id="dffb7-134">您可以使用此資料可採取行動，以您的安全性狀態的重大差異。</span><span class="sxs-lookup"><span data-stu-id="dffb7-134">You can use this data to act and make big differences in your security posture.</span></span>  

<span data-ttu-id="dffb7-135">![M365 首頁](../media/secure-score/homepage-original.png)
*圖 1: Microsoft 安全分數概觀] 頁面上*</span><span class="sxs-lookup"><span data-stu-id="dffb7-135">![M365 homepage](../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="dffb7-136">採取動作來改善您的分數</span><span class="sxs-lookup"><span data-stu-id="dffb7-136">Take action to improve your score</span></span>

<span data-ttu-id="dffb7-137">改進動作] 索引標籤列出所有的安全性建議適用於您的租用戶 （完成、 沒有完成、 解析透過協力廠商，而且會略過） 及其狀態。</span><span class="sxs-lookup"><span data-stu-id="dffb7-137">The improvement actions tab lists all the security recommendations applicable to your tenant along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="dffb7-138">您可以搜尋、 篩選和群組的所有控制項。</span><span class="sxs-lookup"><span data-stu-id="dffb7-138">You can search, filter, and group all the controls.</span></span>  <span data-ttu-id="dffb7-139">排名根據 Microsoft 評估安全性值和努力來完成。</span><span class="sxs-lookup"><span data-stu-id="dffb7-139">Ranking is based on Microsoft’s evaluation of both security value and effort to complete.</span></span>

<span data-ttu-id="dffb7-140">標示為 [不計分] 動作並不會追蹤由 Microsoft 安全分數。</span><span class="sxs-lookup"><span data-stu-id="dffb7-140">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="dffb7-141">您仍然可以採取的動作，但完成它們不會影響您的分數。</span><span class="sxs-lookup"><span data-stu-id="dffb7-141">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="dffb7-142">如果巨集指令會變成在未來追蹤由 Microsoft 安全分數，而且您已經完成它，您的安全分數會自動反映出變更。</span><span class="sxs-lookup"><span data-stu-id="dffb7-142">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="dffb7-143">當您按一下改進巨集指令時，會出現飛入]。</span><span class="sxs-lookup"><span data-stu-id="dffb7-143">When you click on an improvement action, a fly out appears.</span></span> <span data-ttu-id="dffb7-144">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="dffb7-144">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="dffb7-145">選取 [**檢視設定**回到 [設定] 畫面，並進行變更。</span><span class="sxs-lookup"><span data-stu-id="dffb7-145">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="dffb7-146">然後，您將取得動作是值得，顯示出飛出視窗頂端的點。點可能需要 24 小時的時間來更新。</span><span class="sxs-lookup"><span data-stu-id="dffb7-146">You will then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="dffb7-147">因為由協力廠商應用程式或軟體已處理過的改進巨集指令，請選取 [**解決透過協力廠商**]。</span><span class="sxs-lookup"><span data-stu-id="dffb7-147">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="dffb7-148">讓您安全分數更妥善地反映您的整體安全性狀態，您將能夠值得了巨集指令的點。</span><span class="sxs-lookup"><span data-stu-id="dffb7-148">You will gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="dffb7-149">如果協力廠商不再涵蓋控制項，您可以將標示為未完成的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dffb7-149">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="dffb7-150">請記住，Microsoft 就會有任何可見性是否分數需求已符合如果改進巨集指令會標示為透過協力廠商解決。</span><span class="sxs-lookup"><span data-stu-id="dffb7-150">Please keep in mind, Microsoft will have no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="dffb7-151">因為您已決定要接受的風險，並不制訂的改進巨集指令，請選取 [**略過**]。</span><span class="sxs-lookup"><span data-stu-id="dffb7-151">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="dffb7-152">一旦您略過改進巨集指令，總數安全分數點就能得到將會降低。</span><span class="sxs-lookup"><span data-stu-id="dffb7-152">Once you ignore an improvement action, the total number of secure score points you can achieve will be reduced.</span></span> <span data-ttu-id="dffb7-153">您可以檢視歷程記錄中的此巨集指令或復原在任何時間。</span><span class="sxs-lookup"><span data-stu-id="dffb7-153">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="dffb7-154">因為改進巨集指令會要求您定期檢閱您的環境以取得，並保留點的一部分，請選取 [**檢閱**]。</span><span class="sxs-lookup"><span data-stu-id="dffb7-154">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="dffb7-155">例如，信箱轉寄規則應檢閱以確定資料尚未進行挾帶出去，從您的網路以每週為基礎。</span><span class="sxs-lookup"><span data-stu-id="dffb7-155">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="dffb7-156">您不需要進行任何變更，但需要要執行巨集指令。</span><span class="sxs-lookup"><span data-stu-id="dffb7-156">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="dffb7-157">若您定期檢閱規則時，您會收到資料點。</span><span class="sxs-lookup"><span data-stu-id="dffb7-157">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="dffb7-158">如果不是，將會降低分數。</span><span class="sxs-lookup"><span data-stu-id="dffb7-158">If not, the score will be reduced.</span></span>

![M365 首頁](../media/secure-score/secure-score1x450.png) ![M365 首頁](../media/secure-score/secure-score2x450.png)

<span data-ttu-id="dffb7-161">*圖表 2 & 3： 改進巨集指令延伸顯示*</span><span class="sxs-lookup"><span data-stu-id="dffb7-161">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="dffb7-162">經過一段時間的監視器增強功能</span><span class="sxs-lookup"><span data-stu-id="dffb7-162">Monitor improvements over time</span></span>

<span data-ttu-id="dffb7-163">經過一段時間在 [**歷程記錄**] 索引標籤中，您可以檢視您組織的分數的圖形。此檢視包含全域平均產業平均，類似的基座計數，以及所有選取的時間範圍內所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="dffb7-163">You can view a graph of your organization's score over time in the **History** tab. This view includes the global average, industry average, and similar seat count, along with all the actions taken in the selected time range.</span></span> <span data-ttu-id="dffb7-164">您也可以依類別自訂日期範圍與篩選器。</span><span class="sxs-lookup"><span data-stu-id="dffb7-164">You can also customize a date range and filter by category.</span></span>

<span data-ttu-id="dffb7-165">分數的計算一次每日 (大約 1:00 AM PST)。</span><span class="sxs-lookup"><span data-stu-id="dffb7-165">The score is calculated once per day (around 1:00 AM PST).</span></span> <span data-ttu-id="dffb7-166">如果您變更測量的巨集指令，分數會自動更新的下一天。</span><span class="sxs-lookup"><span data-stu-id="dffb7-166">If you make a change to a measured action, the score will automatically update the next day.</span></span> <span data-ttu-id="dffb7-167">務必也請注意，某些其他入口網站會顯示 Microsoft 安全分數部分 （例如 Microsoft defender 資訊安全中心）。</span><span class="sxs-lookup"><span data-stu-id="dffb7-167">It is also important to note that some other portals show parts of the Microsoft Secure Score (like Microsoft Defender Security Center).</span></span> <span data-ttu-id="dffb7-168">如果您完成改進巨集指令，以及分數會增加這些入口網站，可能需要 24 小時的時間的更新分數 」 來顯示在 Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="dffb7-168">If you complete an improvement action and the score is increased in those portals, it may take up to 24 hours for the updated score to display in Microsoft 365 security center.</span></span>  

## <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="dffb7-169">如何改進動作，就會獲得</span><span class="sxs-lookup"><span data-stu-id="dffb7-169">How improvement actions are scored</span></span>

<span data-ttu-id="dffb7-170">二進位的方式，就會獲得最-如果您實作改進的動作，例如建立新的原則，或開啟的特定設定，您會收到的資料點的 100%。</span><span class="sxs-lookup"><span data-stu-id="dffb7-170">Most are scored in a binary fashion - you get 100% of the points if you implement the improvement action, like creating a new policy or turning on a specific setting.</span></span> <span data-ttu-id="dffb7-171">其他改進的動作，點都指定的百分比的總組態。</span><span class="sxs-lookup"><span data-stu-id="dffb7-171">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="dffb7-172">例如，如果改進巨集指令會指出是否您保護您的所有使用者以多重要素驗證，您只需要 5 的 100 個受保護的總使用者，您會收到 30 點，您會提供部分分數的大約 2 點 (受保護的 5 / 100 總 \* 30 的最大點數 = 2 點數部分分數）。</span><span class="sxs-lookup"><span data-stu-id="dffb7-172">For example, if the improvement action states you’ll get 30 points if you protect all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="dffb7-173">風險認知</span><span class="sxs-lookup"><span data-stu-id="dffb7-173">Risk awareness</span></span>

<span data-ttu-id="dffb7-174">Microsoft 安全分數是您的安全性狀態的數字摘要根據系統設定、 使用者行為及其他安全性相關的度量值;它不是絕對的度量單位的方式可能會破壞您的系統或資料。</span><span class="sxs-lookup"><span data-stu-id="dffb7-174">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="dffb7-175">相反地，它表示要採用的安全性控制 Microsoft 環境中可協助位移正在外洩的風險的程度。</span><span class="sxs-lookup"><span data-stu-id="dffb7-175">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="dffb7-176">沒有線上服務已完全免於安全性弱點，以及安全分數不應該解譯成保證郵件可以針對任何方式的安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="dffb7-176">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="dffb7-177">我們想要從您聽到</span><span class="sxs-lookup"><span data-stu-id="dffb7-177">We want to hear from you</span></span>

<span data-ttu-id="dffb7-178">如果您有任何問題，請讓我們知道[安全性、 隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社群中的張貼。</span><span class="sxs-lookup"><span data-stu-id="dffb7-178">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="dffb7-179">我們正在監視社群，並將提供的說明。</span><span class="sxs-lookup"><span data-stu-id="dffb7-179">We're monitoring the community and will provide help.</span></span>
