---
title: Microsoft 安全分數
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及安全性系統管理員可以預期。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
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
ms.openlocfilehash: b19c48161d5d0f43c2beb207dd0ee2db8bfb1470
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372021"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="d3992-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="d3992-104">Microsoft Secure Score</span></span>

<span data-ttu-id="d3992-105">Microsoft 安全分數是具有較高的數字，表示所採取的多個改進動作的組織的安全性狀態，度量單位。</span><span class="sxs-lookup"><span data-stu-id="d3992-105">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="d3992-106">下列建議的安全分數可以防止潛在威脅組織。</span><span class="sxs-lookup"><span data-stu-id="d3992-106">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="d3992-107">從 Microsoft 365 安全性中心集中式儀表板，組織可以監視，並在其 Microsoft 365 身分識別、 資料、 app、 裝置和基礎結構的安全性上運作。</span><span class="sxs-lookup"><span data-stu-id="d3992-107">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="d3992-108">安全分數可幫助組織：</span><span class="sxs-lookup"><span data-stu-id="d3992-108">Secure Score helps organizations:</span></span>

* <span data-ttu-id="d3992-109">在組織的安全性狀態的目前狀態報告。</span><span class="sxs-lookup"><span data-stu-id="d3992-109">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="d3992-110">提供可測知性、 可見性、 指導以及控制項，以提高其安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="d3992-110">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="d3992-111">比較基準，並建立關鍵效能指標 (Kpi)。</span><span class="sxs-lookup"><span data-stu-id="d3992-111">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="d3992-112">組織存取的評量和趨勢，與其他 Microsoft 產品整合、 分數比較與類似的組織，以及執行更多功能強大的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="d3992-112">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="d3992-113">分數也可反映協力廠商解決方案時解決建議的動作。</span><span class="sxs-lookup"><span data-stu-id="d3992-113">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="d3992-114">此外，您可以存取您的建議，以及分數透過[Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api)。</span><span class="sxs-lookup"><span data-stu-id="d3992-114">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="d3992-115">了解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="d3992-115">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="d3992-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="d3992-116">How it works</span></span>

<span data-ttu-id="d3992-117">您所設定的特定點建議的安全性功能，執行與安全性相關的工作 （例如檢視報表），或解決與協力廠商應用程式或軟體的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="d3992-117">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="d3992-118">一些改進動作只提供點完全完成時，和某些授與部分點為單位，如果他們使用某些裝置或使用者完成。</span><span class="sxs-lookup"><span data-stu-id="d3992-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="d3992-119">我們示範整組可能的改進功能，無論授權，因此您可以了解安全性最佳做法，並改善您的分數。</span><span class="sxs-lookup"><span data-stu-id="d3992-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="d3992-120">安全分數，無論哪項產品授權您的組織相同擁有哪些保持代表您的絕對的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="d3992-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="d3992-121">請記住，應取得平衡安全性與可用性，並不是每個建議才能為您的環境。</span><span class="sxs-lookup"><span data-stu-id="d3992-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="d3992-122">您的分數會更新以反映視覺效果和改進動作頁面中所呈現的資訊的即時。</span><span class="sxs-lookup"><span data-stu-id="d3992-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="d3992-123">安全分數也每天同步處理以接收關於每個動作您達成點為單位的系統資料。</span><span class="sxs-lookup"><span data-stu-id="d3992-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="d3992-124">如何改進動作，就會獲得</span><span class="sxs-lookup"><span data-stu-id="d3992-124">How improvement actions are scored</span></span>

<span data-ttu-id="d3992-125">二進位的方式，就會獲得最-如果您實作的改進巨集指令，如建立新的原則，或開啟的特定設定，您會收到的資料點的 100%。</span><span class="sxs-lookup"><span data-stu-id="d3992-125">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="d3992-126">其他改進的動作，點都指定的百分比的總組態。</span><span class="sxs-lookup"><span data-stu-id="d3992-126">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="d3992-127">例如，如果改進巨集指令會指出您取得 30 點保護您的所有使用者以多重要素驗證和您只需要 100 個受保護的總使用者 5，會提供您大約 2 點的部分分數 (受保護的 5 / 100 總 \* 30 的最大點數 = 2 點數部分分數)。</span><span class="sxs-lookup"><span data-stu-id="d3992-127">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="d3992-128">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="d3992-128">Products included in Secure Score</span></span>

<span data-ttu-id="d3992-129">目前有 Office 365 （包括 SharePoint Online、 Exchange Online、 OneDrive for Business、 Microsoft 資訊保護和更多），建議 Azure AD 和 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="d3992-129">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, and Cloud App Security.</span></span> <span data-ttu-id="d3992-130">建議的其他安全性產品，例如 Azure ATP 和 Microsoft Defender ATP 即將推出。</span><span class="sxs-lookup"><span data-stu-id="d3992-130">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="d3992-131">建議將涵蓋每個產品相關聯的所有受攻擊面，但它們是不錯的比較基準。</span><span class="sxs-lookup"><span data-stu-id="d3992-131">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="d3992-132">您也可以將標示改進動作為所涵蓋的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="d3992-132">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="d3992-133">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d3992-133">Required permissions</span></span>

<span data-ttu-id="d3992-134">若要存取 Microsoft 安全分數的權限，您必須獲指派其中一個 Azure Active Directory 中的下列角色。</span><span class="sxs-lookup"><span data-stu-id="d3992-134">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="d3992-135">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="d3992-135">Read and write roles</span></span>

<span data-ttu-id="d3992-136">讀取與寫入權限，您可以進行的變更，並直接互動安全分數。</span><span class="sxs-lookup"><span data-stu-id="d3992-136">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="d3992-137">您也可以指派給其他使用者的唯讀權限。</span><span class="sxs-lookup"><span data-stu-id="d3992-137">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="d3992-138">全域管理員</span><span class="sxs-lookup"><span data-stu-id="d3992-138">Global administrator</span></span>
* <span data-ttu-id="d3992-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3992-139">Security administrator</span></span>
* <span data-ttu-id="d3992-140">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3992-140">Exchange administrator</span></span>
* <span data-ttu-id="d3992-141">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="d3992-141">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="d3992-142">唯讀的角色</span><span class="sxs-lookup"><span data-stu-id="d3992-142">Read-only roles</span></span>

<span data-ttu-id="d3992-143">具有唯讀存取權，您不能編輯狀態] 或 [備忘稿改進巨集指令、 編輯分數區域，或編輯自訂比較。</span><span class="sxs-lookup"><span data-stu-id="d3992-143">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="d3992-144">服務台管理員</span><span class="sxs-lookup"><span data-stu-id="d3992-144">Helpdesk administrator</span></span>
* <span data-ttu-id="d3992-145">使用者管理員</span><span class="sxs-lookup"><span data-stu-id="d3992-145">User administrator</span></span>
* <span data-ttu-id="d3992-146">服務管理員</span><span class="sxs-lookup"><span data-stu-id="d3992-146">Service administrator</span></span>
* <span data-ttu-id="d3992-147">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="d3992-147">Security reader</span></span>
* <span data-ttu-id="d3992-148">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="d3992-148">Security operator</span></span>
* <span data-ttu-id="d3992-149">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="d3992-149">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="d3992-150">Graph API</span><span class="sxs-lookup"><span data-stu-id="d3992-150">Graph API</span></span>

<span data-ttu-id="d3992-151">若要存取 Graph API，您需要有下列其中一個角色除了下列範圍：</span><span class="sxs-lookup"><span data-stu-id="d3992-151">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="d3992-152">SecurityEvents.Read.All （適用於唯讀角色）</span><span class="sxs-lookup"><span data-stu-id="d3992-152">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="d3992-153">SecurityEvents.ReadWrite.All (針對讀取和寫入角色)</span><span class="sxs-lookup"><span data-stu-id="d3992-153">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="d3992-154">取得您的安全性狀態的可視性</span><span class="sxs-lookup"><span data-stu-id="d3992-154">Gain visibility into your security posture</span></span>

<span data-ttu-id="d3992-155">為了協助您更快速地需要的資訊，Microsoft 改進動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="d3992-155">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="d3992-156">身分識別 （Azure AD 帳戶 & 角色與 Azure ATP 即將推出）</span><span class="sxs-lookup"><span data-stu-id="d3992-156">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="d3992-157">資料 (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d3992-157">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="d3992-158">裝置 （Microsoft Defender ATP 裝置，即將推出）</span><span class="sxs-lookup"><span data-stu-id="d3992-158">Device (Microsoft Defender ATP devices, coming soon)</span></span>
* <span data-ttu-id="d3992-159">應用程式 （電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）</span><span class="sxs-lookup"><span data-stu-id="d3992-159">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="d3992-160">基礎結構 （Azure 的資源）</span><span class="sxs-lookup"><span data-stu-id="d3992-160">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="d3992-161">在 [Microsoft 安全分數概觀] 頁面中，您可以看到點分割的方式這些群組與何種點可用之間。</span><span class="sxs-lookup"><span data-stu-id="d3992-161">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="d3992-162">[概觀] 頁面上也是以取得總分基準比較，與您安全分數的歷史趨勢的全面檢視的位置，並可以採取來改善您的分數的改進動作的優先順序。</span><span class="sxs-lookup"><span data-stu-id="d3992-162">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="d3992-163">![安全分數首頁](../../media/secure-score/homepage-original.png)
*圖 1: Microsoft 安全分數概觀] 頁面上*</span><span class="sxs-lookup"><span data-stu-id="d3992-163">![Secure Score homepage](../../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="d3992-164">採取動作來改善您的分數</span><span class="sxs-lookup"><span data-stu-id="d3992-164">Take action to improve your score</span></span>

<span data-ttu-id="d3992-165">改進動作] 索引標籤列出的安全性建議該位址可能受攻擊面，以及其狀態 （完成、 沒有完成、 解析透過協力廠商，而且會略過）。</span><span class="sxs-lookup"><span data-stu-id="d3992-165">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="d3992-166">您可以搜尋、 篩選和群組改進的所有動作。</span><span class="sxs-lookup"><span data-stu-id="d3992-166">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="d3992-167">排名</span><span class="sxs-lookup"><span data-stu-id="d3992-167">Ranking</span></span>

<span data-ttu-id="d3992-168">排名根據由左到達成，實作困難，使用者的影響和複雜性的其餘點的數目。</span><span class="sxs-lookup"><span data-stu-id="d3992-168">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="d3992-169">最高排名的改進動作有大量的剩餘低困難、 使用者的影響，與複雜性的點。</span><span class="sxs-lookup"><span data-stu-id="d3992-169">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="d3992-170">動作</span><span class="sxs-lookup"><span data-stu-id="d3992-170">Actions</span></span>

<span data-ttu-id="d3992-171">標示為 [不計分] 動作並不會追蹤由 Microsoft 安全分數。</span><span class="sxs-lookup"><span data-stu-id="d3992-171">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="d3992-172">您仍然可以採取的動作，但完成它們不會影響您的分數。</span><span class="sxs-lookup"><span data-stu-id="d3992-172">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="d3992-173">如果巨集指令會變成在未來追蹤由 Microsoft 安全分數，而且您已經完成它，您的安全分數會自動反映出變更。</span><span class="sxs-lookup"><span data-stu-id="d3992-173">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="d3992-174">當您選取特定的改進巨集指令時，會出現飛入]。</span><span class="sxs-lookup"><span data-stu-id="d3992-174">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="d3992-175">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="d3992-175">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="d3992-176">選取 [**檢視設定**回到 [設定] 畫面，並進行變更。</span><span class="sxs-lookup"><span data-stu-id="d3992-176">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="d3992-177">然後，您會取得的動作是值得，可見的飛出視窗頂端的點。點可能需要 24 小時的時間來更新。</span><span class="sxs-lookup"><span data-stu-id="d3992-177">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="d3992-178">因為由協力廠商應用程式或軟體已處理過的改進巨集指令，請選取 [**解決透過協力廠商**]。</span><span class="sxs-lookup"><span data-stu-id="d3992-178">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="d3992-179">讓您安全分數更妥善地反映您的整體安全性狀態，您會獲得值得了巨集指令的點。</span><span class="sxs-lookup"><span data-stu-id="d3992-179">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="d3992-180">如果協力廠商不再涵蓋控制項，您可以將標示為未完成的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="d3992-180">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="d3992-181">請記住，Microsoft 已不可見性是否分數需求已符合如果改進巨集指令會標示為透過協力廠商解決。</span><span class="sxs-lookup"><span data-stu-id="d3992-181">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="d3992-182">因為您已決定要接受的風險，並不制訂的改進巨集指令，請選取 [**略過**]。</span><span class="sxs-lookup"><span data-stu-id="d3992-182">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="d3992-183">一旦您略過改進巨集指令，總數安全分數點就能得到會減少。</span><span class="sxs-lookup"><span data-stu-id="d3992-183">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="d3992-184">您可以檢視歷程記錄中的此巨集指令或復原在任何時間。</span><span class="sxs-lookup"><span data-stu-id="d3992-184">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="d3992-185">因為改進巨集指令會要求您定期檢閱您的環境以取得，並保留點的一部分，請選取 [**檢閱**]。</span><span class="sxs-lookup"><span data-stu-id="d3992-185">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="d3992-186">例如，信箱轉寄規則應檢閱以確定資料尚未進行挾帶出去，從您的網路以每週為基礎。</span><span class="sxs-lookup"><span data-stu-id="d3992-186">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="d3992-187">您不需要進行任何變更，但需要要執行巨集指令。</span><span class="sxs-lookup"><span data-stu-id="d3992-187">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="d3992-188">若您定期檢閱規則時，您會收到資料點。</span><span class="sxs-lookup"><span data-stu-id="d3992-188">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="d3992-189">如果不是，減少分數。</span><span class="sxs-lookup"><span data-stu-id="d3992-189">If not, the score is reduced.</span></span>

![安全分數改進巨集指令範例](../../media/secure-score/secure-score1x450.png) ![安全分數檢閱改進巨集指令範例](../../media/secure-score/secure-score2x450.png)

<span data-ttu-id="d3992-192">*圖表 2 & 3： 改進巨集指令延伸顯示*</span><span class="sxs-lookup"><span data-stu-id="d3992-192">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="d3992-193">經過一段時間的監視器增強功能</span><span class="sxs-lookup"><span data-stu-id="d3992-193">Monitor improvements over time</span></span>

<span data-ttu-id="d3992-194">您可以檢視圖表，貴組織的分數經過一段時間**歷程記錄**中的圖形下方] 索引標籤所採取的所選的時間範圍和其屬性，例如產生點及類別中的所有動作的清單。</span><span class="sxs-lookup"><span data-stu-id="d3992-194">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="d3992-195">您可以依類別自訂日期範圍與篩選器。</span><span class="sxs-lookup"><span data-stu-id="d3992-195">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="d3992-196">風險認知</span><span class="sxs-lookup"><span data-stu-id="d3992-196">Risk awareness</span></span>

<span data-ttu-id="d3992-197">Microsoft 安全分數是數字摘要根據系統設定、 使用者行為及其他安全性相關的度量值; 您安全性狀態。它不是絕對的度量單位的方式可能會破壞您的系統或資料。</span><span class="sxs-lookup"><span data-stu-id="d3992-197">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="d3992-198">相反地，它表示要採用的安全性控制 Microsoft 環境中可協助位移正在外洩的風險的程度。</span><span class="sxs-lookup"><span data-stu-id="d3992-198">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="d3992-199">沒有線上服務已完全免於安全性弱點，以及安全分數不應該解譯成保證郵件可以針對任何方式的安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="d3992-199">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="d3992-200">新功能？</span><span class="sxs-lookup"><span data-stu-id="d3992-200">What's new?</span></span>

<span data-ttu-id="d3992-201">若要讓 Microsoft 安全分數較佳的安全性狀態代表我們已進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="d3992-201">To make Microsoft Secure Score a better representative of your security posture we have made some changes.</span></span>

<span data-ttu-id="d3992-202">若要深入了計劃變更資訊，請參閱[項目即將 Microsoft 安全分數？](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="d3992-202">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

### <a name="removed-not-scored-improvement-actions"></a><span data-ttu-id="d3992-203">已移除 「 不計分 」 改進動作</span><span class="sxs-lookup"><span data-stu-id="d3992-203">Removed “not scored” improvement actions</span></span>

<span data-ttu-id="d3992-204">之一的安全分數原則是分數應依照標準化預定且更容易與相關。</span><span class="sxs-lookup"><span data-stu-id="d3992-204">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="d3992-205">具有不是可以測量或可採取行動的改進動作具有已造成混淆。</span><span class="sxs-lookup"><span data-stu-id="d3992-205">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="d3992-206">Microsoft 安全分數僅合理時的每個建議有清除影響分數。</span><span class="sxs-lookup"><span data-stu-id="d3992-206">Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="d3992-207">不計分改進動作不是可以測量的。</span><span class="sxs-lookup"><span data-stu-id="d3992-207">Not scored improvement actions are not measurable.</span></span>  

<span data-ttu-id="d3992-208">基於這些理由，已被移除已不會被記錄的所有改進動作。</span><span class="sxs-lookup"><span data-stu-id="d3992-208">For these reasons, all improvement actions that were not scored have been removed.</span></span> <span data-ttu-id="d3992-209">在您的組件上不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="d3992-209">No action is needed on your part.</span></span>

### <a name="removed-device-improvement-actions"></a><span data-ttu-id="d3992-210">移除的裝置改進動作</span><span class="sxs-lookup"><span data-stu-id="d3992-210">Removed device improvement actions</span></span>

<span data-ttu-id="d3992-211">Microsoft 安全分數裝置類別的改進動作的評估之後, 被判定那些動作目前評估原則狀態並不裝置的組態狀態。</span><span class="sxs-lookup"><span data-stu-id="d3992-211">After an evaluation of the Microsoft Secure Score device category of improvement actions, it was determined that those actions currently assess the policy state and not the configuration state of devices.</span></span> <span data-ttu-id="d3992-212">因為組態直接繫結至安全性狀態，現有的裝置動作已決定不完全代表組織的狀態。</span><span class="sxs-lookup"><span data-stu-id="d3992-212">Since configuration is directly tied to security posture, the existing device actions were determined to not fully represent organizational posture.</span></span>  <span data-ttu-id="d3992-213">我們將會移除目前的動作裝置類別中為我們可以使用，以提供一組建議直接使用更完整代表裝置安全性狀態的 [診斷資料。</span><span class="sxs-lookup"><span data-stu-id="d3992-213">We will be removing the current actions in the device category as we work to provide a set of recommendations which directly use diagnostic data to more fully represent device security posture.</span></span>

<span data-ttu-id="d3992-214">已移除下列改進動作：</span><span class="sxs-lookup"><span data-stu-id="d3992-214">The following improvement actions have been removed:</span></span>

- <span data-ttu-id="d3992-215">啟用 Microsoft Intune 行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="d3992-215">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="d3992-216">Android 版建立 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="d3992-216">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="d3992-217">建立工作 Android 版的 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="d3992-217">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="d3992-218">Android 版建立 Microsoft Intune 應用程式防護原則</span><span class="sxs-lookup"><span data-stu-id="d3992-218">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="d3992-219">建立 iOS 版 Microsoft Intune 應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="d3992-219">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="d3992-220">標記裝置與指定為不符合任何 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="d3992-220">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="d3992-221">建立 iOS 版 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="d3992-221">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="d3992-222">建立 macOS Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="d3992-222">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="d3992-223">建立 Windows 的 Microsoft Intune 合規性原則</span><span class="sxs-lookup"><span data-stu-id="d3992-223">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="d3992-224">Android 版建立 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="d3992-224">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="d3992-225">建立工作 Android 版的 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="d3992-225">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="d3992-226">建立 macOS 的 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="d3992-226">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="d3992-227">建立 iOS 版 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="d3992-227">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="d3992-228">建立 Windows 的 Microsoft Intune 設定設定檔</span><span class="sxs-lookup"><span data-stu-id="d3992-228">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="d3992-229">啟用 Microsoft Intune 中的增強型的 jailbreak 偵測</span><span class="sxs-lookup"><span data-stu-id="d3992-229">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="d3992-230">需要修正的所有裝置、 防毒和防火牆啟用</span><span class="sxs-lookup"><span data-stu-id="d3992-230">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="d3992-231">啟用 Windows Defender ATP 整合至 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d3992-231">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="d3992-232">建立 Microsoft Intune Windows 資訊保護原則</span><span class="sxs-lookup"><span data-stu-id="d3992-232">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="d3992-233">需要有進階安全性設定的所有裝置</span><span class="sxs-lookup"><span data-stu-id="d3992-233">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="d3992-234">每週檢閱封鎖的裝置報告</span><span class="sxs-lookup"><span data-stu-id="d3992-234">Review blocked devices report weekly</span></span>

### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="d3992-235">移除不符合預期可靠的度量單位的改進動作</span><span class="sxs-lookup"><span data-stu-id="d3992-235">Removed improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="d3992-236">若要確保 Microsoft 安全分數才有意義，以及改進的每一個動作是可以測量且可靠，我們已移除下列改進動作：</span><span class="sxs-lookup"><span data-stu-id="d3992-236">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we have removed the following improvement actions:</span></span>

- <span data-ttu-id="d3992-237">開啟稽核資料記錄</span><span class="sxs-lookup"><span data-stu-id="d3992-237">Turn on audit data recording</span></span>
- <span data-ttu-id="d3992-238">探索風險並不相容的陰影 IT 應用程式</span><span class="sxs-lookup"><span data-stu-id="d3992-238">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="d3992-239">檢閱權限 & 封鎖風險 OAuth 應用程式連線至您的環境</span><span class="sxs-lookup"><span data-stu-id="d3992-239">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="d3992-240">在 SharePoint online 的文件庫設定版本設定</span><span class="sxs-lookup"><span data-stu-id="d3992-240">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="d3992-241">MFA 改進動作更新</span><span class="sxs-lookup"><span data-stu-id="d3992-241">MFA improvement action updates</span></span>

<span data-ttu-id="d3992-242">若要反映適用於企業以確保 upmost 安全性時，套用原則可搭配其業務需求，Microsoft 安全分數已移除以多重要素驗證，為主的三個改進動作，並新增兩個。</span><span class="sxs-lookup"><span data-stu-id="d3992-242">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score has removed three improvement actions centered around multi-factor authentication, and added two.</span></span>

<span data-ttu-id="d3992-243">已移除的改進動作：</span><span class="sxs-lookup"><span data-stu-id="d3992-243">Removed improvement actions:</span></span>

- <span data-ttu-id="d3992-244">登錄所有使用者的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="d3992-244">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="d3992-245">需要 MFA 的所有使用者</span><span class="sxs-lookup"><span data-stu-id="d3992-245">Require MFA for all users</span></span>
- <span data-ttu-id="d3992-246">需要 MFA 的 Azure AD 特殊權限角色</span><span class="sxs-lookup"><span data-stu-id="d3992-246">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="d3992-247">新增的改進動作：</span><span class="sxs-lookup"><span data-stu-id="d3992-247">Added improvement actions:</span></span>

- <span data-ttu-id="d3992-248">確定所有的使用者可以完成的安全存取多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="d3992-248">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="d3992-249">需要 MFA 的系統管理角色</span><span class="sxs-lookup"><span data-stu-id="d3992-249">Require MFA for administrative roles</span></span>

 <span data-ttu-id="d3992-250">這些新的改進動作需要透過您的目錄中註冊您的使用者或系統管理員針對多重要素驗證 (MFA)，以及建立正確的一組原則符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="d3992-250">These new improvement actions require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="d3992-251">主要目標是有彈性，同時確保所有使用者和系統管理員可以驗證與多重因素或風險式身分識別驗證提示。</span><span class="sxs-lookup"><span data-stu-id="d3992-251">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="d3992-252">可能需要的表單具有多個範圍的決策或設定安全性的預設值 （即將年 3 月 16），可讓 Microsoft 決定何時 MFA 的挑戰使用者套用的原則。</span><span class="sxs-lookup"><span data-stu-id="d3992-252">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removed-review-improvement-actions"></a><span data-ttu-id="d3992-253">已移除 「 檢閱 」 改進動作</span><span class="sxs-lookup"><span data-stu-id="d3992-253">Removed “review” improvement actions</span></span>

<span data-ttu-id="d3992-254">之一的安全分數原則是分數應依照標準化預定且更容易與相關。</span><span class="sxs-lookup"><span data-stu-id="d3992-254">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="d3992-255">具有不是可以測量或可採取行動的改進動作具有已造成混淆。</span><span class="sxs-lookup"><span data-stu-id="d3992-255">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="d3992-256">一個 Microsoft 安全分數僅合理時的每個建議有清除影響分數。</span><span class="sxs-lookup"><span data-stu-id="d3992-256">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="d3992-257">檢閱改進動作不會測量至其他改進動作為相同的標準。</span><span class="sxs-lookup"><span data-stu-id="d3992-257">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="d3992-258">基於這些理由，已被暫時移除所有需要檢閱頻率的改進動作。</span><span class="sxs-lookup"><span data-stu-id="d3992-258">For these reasons, all improvement actions that required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="d3992-259">在您的組件上不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="d3992-259">No action is needed on your part.</span></span>

### <a name="preview-features"></a><span data-ttu-id="d3992-260">預覽功能</span><span class="sxs-lookup"><span data-stu-id="d3992-260">Preview features</span></span>

<span data-ttu-id="d3992-261">[預覽版本](microsoft-secure-score-preview.md)中，將會包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="d3992-261">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="d3992-262">首席資訊安全長的所有新評量和趨勢檢視，而且會導致層級的討論區</span><span class="sxs-lookup"><span data-stu-id="d3992-262">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="d3992-263">追蹤及基準測試您的分數的新方法</span><span class="sxs-lookup"><span data-stu-id="d3992-263">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="d3992-264">更有效率的追蹤和監控分數衰退</span><span class="sxs-lookup"><span data-stu-id="d3992-264">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="d3992-265">篩選、 標記、 搜尋及群組改進動作</span><span class="sxs-lookup"><span data-stu-id="d3992-265">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="d3992-266">管理向您未來的目標，使用分數估算和計劃的動作</span><span class="sxs-lookup"><span data-stu-id="d3992-266">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="d3992-267">簡化的點為單位系統</span><span class="sxs-lookup"><span data-stu-id="d3992-267">Simplification of the points system</span></span>
* <span data-ttu-id="d3992-268">還有更多 ！</span><span class="sxs-lookup"><span data-stu-id="d3992-268">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="d3992-269">我們想要從您聽到</span><span class="sxs-lookup"><span data-stu-id="d3992-269">We want to hear from you</span></span>

<span data-ttu-id="d3992-270">如果您有任何問題，請讓我們知道[安全性、 隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社群中的張貼。</span><span class="sxs-lookup"><span data-stu-id="d3992-270">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="d3992-271">我們正在監視社群，並將提供的說明。</span><span class="sxs-lookup"><span data-stu-id="d3992-271">We're monitoring the community and will provide help.</span></span>
