---
title: Microsoft 安全分數
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及安全性系統管理員可以預期。
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
ms.openlocfilehash: 74afe39e78990d794368ed19aa5fd5116bee17bb
ms.sourcegitcommit: 0830be61e21570ee3a2589e35c21f358b52585c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "37774906"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="16acf-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="16acf-104">Microsoft Secure Score</span></span>

<span data-ttu-id="16acf-105">Microsoft 安全分數是具有較高的數字，表示所採取的多個改進動作的組織的安全性狀態，度量單位。</span><span class="sxs-lookup"><span data-stu-id="16acf-105">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="16acf-106">從 Microsoft 365 安全性中心集中式儀表板，組織可以監視，並在其 Microsoft 365 身分識別、 資料、 app、 裝置和基礎結構的安全性上運作。</span><span class="sxs-lookup"><span data-stu-id="16acf-106">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="16acf-107">安全分數可幫助組織：</span><span class="sxs-lookup"><span data-stu-id="16acf-107">Secure Score helps organizations:</span></span>

* <span data-ttu-id="16acf-108">在組織的安全性狀態的目前狀態報告。</span><span class="sxs-lookup"><span data-stu-id="16acf-108">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="16acf-109">提供可測知性、 可見性、 指導以及控制項，以提高其安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="16acf-109">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="16acf-110">比較基準，並建立關鍵效能指標 (Kpi)。</span><span class="sxs-lookup"><span data-stu-id="16acf-110">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="16acf-111">組織存取的評量和趨勢，與其他 Microsoft 產品整合、 分數比較與類似的組織，以及執行更多功能強大的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="16acf-111">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="16acf-112">分數也可反映協力廠商解決方案時解決建議的動作。</span><span class="sxs-lookup"><span data-stu-id="16acf-112">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="16acf-113">此外，您可以存取您的建議，以及分數透過[Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api)。</span><span class="sxs-lookup"><span data-stu-id="16acf-113">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="16acf-114">了解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="16acf-114">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="16acf-115">運作方式</span><span class="sxs-lookup"><span data-stu-id="16acf-115">How it works</span></span>

<span data-ttu-id="16acf-116">您所設定的特定點建議的安全性功能，執行與安全性相關的工作 （例如檢視報表），或解決與協力廠商應用程式或軟體的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="16acf-116">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="16acf-117">一些改進動作只提供點完全完成時，和某些授與部分點為單位，如果他們使用某些裝置或使用者完成。</span><span class="sxs-lookup"><span data-stu-id="16acf-117">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="16acf-118">安全性應取得平衡與可用性，並不是每個建議才能為您的環境。</span><span class="sxs-lookup"><span data-stu-id="16acf-118">Security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="16acf-119">您的分數會更新以反映視覺效果和改進動作頁面中所呈現的資訊的即時。</span><span class="sxs-lookup"><span data-stu-id="16acf-119">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="16acf-120">安全分數也每天同步處理以接收關於每個動作您達成點為單位的系統資料。</span><span class="sxs-lookup"><span data-stu-id="16acf-120">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="16acf-121">如何改進動作，就會獲得</span><span class="sxs-lookup"><span data-stu-id="16acf-121">How improvement actions are scored</span></span>

<span data-ttu-id="16acf-122">二進位的方式，就會獲得最-如果您實作的改進巨集指令，如建立新的原則，或開啟的特定設定，您會收到的資料點的 100%。</span><span class="sxs-lookup"><span data-stu-id="16acf-122">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="16acf-123">其他改進的動作，點都指定的百分比的總組態。</span><span class="sxs-lookup"><span data-stu-id="16acf-123">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="16acf-124">例如，如果改進巨集指令會指出您取得 30 點保護您的所有使用者以多重要素驗證和您只需要 100 個受保護的總使用者 5，會提供您大約 2 點的部分分數 (受保護的 5 / 100 總 \* 30 的最大點數 = 2 點數 部分的分數）。</span><span class="sxs-lookup"><span data-stu-id="16acf-124">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="16acf-125">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="16acf-125">Products included in Secure Score</span></span>

<span data-ttu-id="16acf-126">目前有 Office 365 （包括 SharePoint Online、 Exchange Online、 OneDrive for Business、 Microsoft 資訊保護和更多），建議 Azure AD，Intune 和 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="16acf-126">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, Intune, and Cloud App Security.</span></span> <span data-ttu-id="16acf-127">建議的其他安全性產品，例如 Azure ATP 和 Microsoft Defender ATP 即將推出。</span><span class="sxs-lookup"><span data-stu-id="16acf-127">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="16acf-128">建議將涵蓋每個產品相關聯的所有受攻擊面，但它們是不錯的比較基準。</span><span class="sxs-lookup"><span data-stu-id="16acf-128">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="16acf-129">您也可以將標示改進動作為所涵蓋的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="16acf-129">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="16acf-130">必要的權限</span><span class="sxs-lookup"><span data-stu-id="16acf-130">Required permissions</span></span>

<span data-ttu-id="16acf-131">若要存取 Microsoft 安全分數的權限，您必須獲指派其中一個 Azure Active Directory 中的下列角色。</span><span class="sxs-lookup"><span data-stu-id="16acf-131">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="16acf-132">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="16acf-132">Read and write roles</span></span>

<span data-ttu-id="16acf-133">讀取與寫入權限，您可以進行的變更，並直接互動安全分數。</span><span class="sxs-lookup"><span data-stu-id="16acf-133">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="16acf-134">您也可以指派給其他使用者的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="16acf-134">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="16acf-135">CompanyAdministrator</span><span class="sxs-lookup"><span data-stu-id="16acf-135">CompanyAdministrator</span></span>
* <span data-ttu-id="16acf-136">SecurityAdministrator</span><span class="sxs-lookup"><span data-stu-id="16acf-136">SecurityAdministrator</span></span>
* <span data-ttu-id="16acf-137">ExchangeAdmin</span><span class="sxs-lookup"><span data-stu-id="16acf-137">ExchangeAdmin</span></span>
* <span data-ttu-id="16acf-138">SharePointAdmin</span><span class="sxs-lookup"><span data-stu-id="16acf-138">SharePointAdmin</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="16acf-139">唯讀的角色</span><span class="sxs-lookup"><span data-stu-id="16acf-139">Read-only roles</span></span>

<span data-ttu-id="16acf-140">具有唯讀存取權，您不能編輯狀態] 或 [備忘稿改進巨集指令、 編輯分數區域，或編輯自訂比較。</span><span class="sxs-lookup"><span data-stu-id="16acf-140">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="16acf-141">HelpdeskAdmin</span><span class="sxs-lookup"><span data-stu-id="16acf-141">HelpdeskAdmin</span></span>
* <span data-ttu-id="16acf-142">UserAccountAdmin</span><span class="sxs-lookup"><span data-stu-id="16acf-142">UserAccountAdmin</span></span>
* <span data-ttu-id="16acf-143">ServiceSupportAdmin</span><span class="sxs-lookup"><span data-stu-id="16acf-143">ServiceSupportAdmin</span></span>
* <span data-ttu-id="16acf-144">SecurityReader</span><span class="sxs-lookup"><span data-stu-id="16acf-144">SecurityReader</span></span>
* <span data-ttu-id="16acf-145">SecurityOperator</span><span class="sxs-lookup"><span data-stu-id="16acf-145">SecurityOperator</span></span>
* <span data-ttu-id="16acf-146">GlobalReader</span><span class="sxs-lookup"><span data-stu-id="16acf-146">GlobalReader</span></span>

### <a name="graph-api"></a><span data-ttu-id="16acf-147">Graph API</span><span class="sxs-lookup"><span data-stu-id="16acf-147">Graph API</span></span>

<span data-ttu-id="16acf-148">若要存取 Graph API，您需要有下列其中一個角色除了下列範圍：</span><span class="sxs-lookup"><span data-stu-id="16acf-148">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="16acf-149">SecurityEvents.Read.All （適用於唯讀角色）</span><span class="sxs-lookup"><span data-stu-id="16acf-149">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="16acf-150">SecurityEvents.ReadWrite.All (針對讀取和寫入角色)</span><span class="sxs-lookup"><span data-stu-id="16acf-150">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="16acf-151">取得您的安全性狀態的可視性</span><span class="sxs-lookup"><span data-stu-id="16acf-151">Gain visibility into your security posture</span></span>

<span data-ttu-id="16acf-152">為了協助您更快速地需要的資訊，Microsoft 改進動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="16acf-152">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="16acf-153">身分識別 （Azure AD 帳戶 & 角色與 Azure ATP 即將推出）</span><span class="sxs-lookup"><span data-stu-id="16acf-153">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="16acf-154">資料 (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="16acf-154">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="16acf-155">裝置 （Microsoft Defender ATP 裝置，即將推出）</span><span class="sxs-lookup"><span data-stu-id="16acf-155">Device (Microsoft Defender ATP devices, coming soon)</span></span>
* <span data-ttu-id="16acf-156">應用程式 （電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）</span><span class="sxs-lookup"><span data-stu-id="16acf-156">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="16acf-157">基礎結構 （Azure 的資源）</span><span class="sxs-lookup"><span data-stu-id="16acf-157">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="16acf-158">在 [Microsoft 安全分數概觀] 頁面中，您可以看到點分割的方式這些群組與何種點可用之間。</span><span class="sxs-lookup"><span data-stu-id="16acf-158">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="16acf-159">[概觀] 頁面上也是以取得總分基準比較，與您安全分數的歷史趨勢的全面檢視的位置，並可以採取來改善您的分數的改進動作的優先順序。</span><span class="sxs-lookup"><span data-stu-id="16acf-159">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="16acf-160">![安全分數首頁](../media/secure-score/homepage-original.png)
*圖 1: Microsoft 安全分數概觀] 頁面上*</span><span class="sxs-lookup"><span data-stu-id="16acf-160">![Secure Score homepage](../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="16acf-161">採取動作來改善您的分數</span><span class="sxs-lookup"><span data-stu-id="16acf-161">Take action to improve your score</span></span>

<span data-ttu-id="16acf-162">改進動作] 索引標籤列出的安全性建議該位址可能受攻擊面，以及其狀態 （完成、 沒有完成、 解析透過協力廠商，而且會略過）。</span><span class="sxs-lookup"><span data-stu-id="16acf-162">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="16acf-163">您可以搜尋、 篩選和群組改進的所有動作。</span><span class="sxs-lookup"><span data-stu-id="16acf-163">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="16acf-164">排名</span><span class="sxs-lookup"><span data-stu-id="16acf-164">Ranking</span></span>

<span data-ttu-id="16acf-165">排名根據由左到達成，實作困難，使用者的影響和複雜性的其餘點的數目。</span><span class="sxs-lookup"><span data-stu-id="16acf-165">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="16acf-166">最高排名的改進動作有大量的剩餘低困難、 使用者的影響，與複雜性的點。</span><span class="sxs-lookup"><span data-stu-id="16acf-166">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="16acf-167">動作</span><span class="sxs-lookup"><span data-stu-id="16acf-167">Actions</span></span>

<span data-ttu-id="16acf-168">標示為 [不計分] 動作並不會追蹤由 Microsoft 安全分數。</span><span class="sxs-lookup"><span data-stu-id="16acf-168">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="16acf-169">您仍然可以採取的動作，但完成它們不會影響您的分數。</span><span class="sxs-lookup"><span data-stu-id="16acf-169">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="16acf-170">如果巨集指令會變成在未來追蹤由 Microsoft 安全分數，而且您已經完成它，您的安全分數會自動反映出變更。</span><span class="sxs-lookup"><span data-stu-id="16acf-170">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="16acf-171">當您選取特定的改進巨集指令時，會出現飛入]。</span><span class="sxs-lookup"><span data-stu-id="16acf-171">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="16acf-172">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="16acf-172">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="16acf-173">選取 [**檢視設定**回到 [設定] 畫面，並進行變更。</span><span class="sxs-lookup"><span data-stu-id="16acf-173">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="16acf-174">然後，您會取得的動作是值得，可見的飛出視窗頂端的點。點可能需要 24 小時的時間來更新。</span><span class="sxs-lookup"><span data-stu-id="16acf-174">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="16acf-175">因為由協力廠商應用程式或軟體已處理過的改進巨集指令，請選取 [**解決透過協力廠商**]。</span><span class="sxs-lookup"><span data-stu-id="16acf-175">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="16acf-176">讓您安全分數更妥善地反映您的整體安全性狀態，您會獲得值得了巨集指令的點。</span><span class="sxs-lookup"><span data-stu-id="16acf-176">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="16acf-177">如果協力廠商不再涵蓋控制項，您可以將標示為未完成的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="16acf-177">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="16acf-178">請記住，Microsoft 已不可見性是否分數需求已符合如果改進巨集指令會標示為透過協力廠商解決。</span><span class="sxs-lookup"><span data-stu-id="16acf-178">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="16acf-179">因為您已決定要接受的風險，並不制訂的改進巨集指令，請選取 [**略過**]。</span><span class="sxs-lookup"><span data-stu-id="16acf-179">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="16acf-180">一旦您略過改進巨集指令，總數安全分數點就能得到會減少。</span><span class="sxs-lookup"><span data-stu-id="16acf-180">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="16acf-181">您可以檢視歷程記錄中的此巨集指令或復原在任何時間。</span><span class="sxs-lookup"><span data-stu-id="16acf-181">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="16acf-182">因為改進巨集指令會要求您定期檢閱您的環境以取得，並保留點的一部分，請選取 [**檢閱**]。</span><span class="sxs-lookup"><span data-stu-id="16acf-182">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="16acf-183">例如，信箱轉寄規則應檢閱以確定資料尚未進行挾帶出去，從您的網路以每週為基礎。</span><span class="sxs-lookup"><span data-stu-id="16acf-183">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="16acf-184">您不需要進行任何變更，但需要要執行巨集指令。</span><span class="sxs-lookup"><span data-stu-id="16acf-184">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="16acf-185">若您定期檢閱規則時，您會收到資料點。</span><span class="sxs-lookup"><span data-stu-id="16acf-185">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="16acf-186">如果不是，減少分數。</span><span class="sxs-lookup"><span data-stu-id="16acf-186">If not, the score is reduced.</span></span>

![安全分數改進巨集指令範例](../media/secure-score/secure-score1x450.png) ![安全分數檢閱改進巨集指令範例](../media/secure-score/secure-score2x450.png)

<span data-ttu-id="16acf-189">*圖表 2 & 3： 改進巨集指令延伸顯示*</span><span class="sxs-lookup"><span data-stu-id="16acf-189">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="16acf-190">經過一段時間的監視器增強功能</span><span class="sxs-lookup"><span data-stu-id="16acf-190">Monitor improvements over time</span></span>

<span data-ttu-id="16acf-191">您可以檢視圖表，貴組織的分數經過一段時間**歷程記錄**中的圖形下方] 索引標籤所採取的所選的時間範圍和其屬性，例如產生點及類別中的所有動作的清單。</span><span class="sxs-lookup"><span data-stu-id="16acf-191">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="16acf-192">您可以依類別自訂日期範圍與篩選器。</span><span class="sxs-lookup"><span data-stu-id="16acf-192">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="16acf-193">風險認知</span><span class="sxs-lookup"><span data-stu-id="16acf-193">Risk awareness</span></span>

<span data-ttu-id="16acf-194">Microsoft 安全分數是數字摘要根據系統設定、 使用者行為及其他安全性相關的度量值; 您安全性狀態。它不是絕對的度量單位的方式可能會破壞您的系統或資料。</span><span class="sxs-lookup"><span data-stu-id="16acf-194">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="16acf-195">相反地，它表示要採用的安全性控制 Microsoft 環境中可協助位移正在外洩的風險的程度。</span><span class="sxs-lookup"><span data-stu-id="16acf-195">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="16acf-196">沒有線上服務已完全免於安全性弱點，以及安全分數不應該解譯成保證郵件可以針對任何方式的安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="16acf-196">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="16acf-197">下來什麼？</span><span class="sxs-lookup"><span data-stu-id="16acf-197">What's coming?</span></span>

<span data-ttu-id="16acf-198">若要讓 Microsoft 安全分數較佳的安全性狀態代表並改善可用性，我們會在不久的將來進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="16acf-198">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="16acf-199">您的成績和最大可能分數會變更。</span><span class="sxs-lookup"><span data-stu-id="16acf-199">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="16acf-200">不過，這並不表示您的安全性狀態變更。</span><span class="sxs-lookup"><span data-stu-id="16acf-200">However, this does not imply a change in your security posture.</span></span>

### <a name="removing-not-scored-and-review-improvement-actions"></a><span data-ttu-id="16acf-201">移除 「 不計分 」 和 「 檢閱 」 改進動作</span><span class="sxs-lookup"><span data-stu-id="16acf-201">Removing “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="16acf-202">之一的安全分數原則是分數應依照標準化預定且更容易與相關。</span><span class="sxs-lookup"><span data-stu-id="16acf-202">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="16acf-203">具有不是可以測量或可採取行動的改進動作具有已造成混淆。</span><span class="sxs-lookup"><span data-stu-id="16acf-203">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="16acf-204">一個 Microsoft 安全分數僅合理時的每個建議有清除影響分數。</span><span class="sxs-lookup"><span data-stu-id="16acf-204">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="16acf-205">不計分的改進動作不是可以測量的並檢閱動作不會測量為其他改進動作的同一個標準的改進。</span><span class="sxs-lookup"><span data-stu-id="16acf-205">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="16acf-206">基於這些理由，將會暫時移除所有已不會被記錄或需要檢閱頻率的改進動作。</span><span class="sxs-lookup"><span data-stu-id="16acf-206">For these reasons, all improvement actions that were not scored or required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="16acf-207">在您的組件上不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="16acf-207">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="16acf-208">簡化的點系統</span><span class="sxs-lookup"><span data-stu-id="16acf-208">Simplification of the point system</span></span>

<span data-ttu-id="16acf-209">若要跨多個體驗標準化點，每個安全分數改進巨集指令點總計會更新為 10 點值得或更少。</span><span class="sxs-lookup"><span data-stu-id="16acf-209">To standardize points across multiple experiences, each Secure Score improvement action point total will be updated to be worth 10 points or less.</span></span> <span data-ttu-id="16acf-210">視需要在我們今天有的安全性控制和我們將在未來新增的探索寬口氣是更一致。</span><span class="sxs-lookup"><span data-stu-id="16acf-210">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="16acf-211">雖然這是重大變更，您會看到以點合計放置會有不會變更您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="16acf-211">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>  

### <a name="preview-features"></a><span data-ttu-id="16acf-212">預覽功能</span><span class="sxs-lookup"><span data-stu-id="16acf-212">Preview features</span></span>

<span data-ttu-id="16acf-213">預覽版本中，將會包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="16acf-213">The following features will be included in the preview release:</span></span>

* <span data-ttu-id="16acf-214">首席資訊安全長的所有新評量和趨勢檢視，而且會導致層級的討論區</span><span class="sxs-lookup"><span data-stu-id="16acf-214">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="16acf-215">追蹤及基準測試您的分數的新方法</span><span class="sxs-lookup"><span data-stu-id="16acf-215">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="16acf-216">更有效率的追蹤和監控分數衰退</span><span class="sxs-lookup"><span data-stu-id="16acf-216">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="16acf-217">篩選、 標記、 搜尋及群組改進動作</span><span class="sxs-lookup"><span data-stu-id="16acf-217">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="16acf-218">管理向您未來的目標，使用分數估算和計劃的動作</span><span class="sxs-lookup"><span data-stu-id="16acf-218">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="16acf-219">還有更多 ！</span><span class="sxs-lookup"><span data-stu-id="16acf-219">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="16acf-220">我們想要從您聽到</span><span class="sxs-lookup"><span data-stu-id="16acf-220">We want to hear from you</span></span>

<span data-ttu-id="16acf-221">如果您有任何問題，請讓我們知道[安全性、 隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社群中的張貼。</span><span class="sxs-lookup"><span data-stu-id="16acf-221">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="16acf-222">我們正在監視社群，並將提供的說明。</span><span class="sxs-lookup"><span data-stu-id="16acf-222">We're monitoring the community and will provide help.</span></span>
