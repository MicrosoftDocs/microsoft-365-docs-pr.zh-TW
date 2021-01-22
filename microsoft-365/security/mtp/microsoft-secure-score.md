---
title: Microsoft 安全分數
description: 說明 Microsoft 365 資訊安全中心的 Microsoft 安全分數、如何改善安全性工作，以及安全性系統管理員可預期的結果。
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
ms.openlocfilehash: a0f4307cc0ed42a8ed53cdeefdb0a7b32eb36d35
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930579"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="e7497-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="e7497-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e7497-105">Microsoft 安全分數是組織安全性措施的度量，數位越高，表示已採取更多改進動作。</span><span class="sxs-lookup"><span data-stu-id="e7497-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="e7497-106">您可以在 https://security.microsoft.com/securescore [Microsoft 365 資訊安全中心找到。](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="e7497-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="e7497-107">遵循安全分數建議可保護貴組織不受威脅。</span><span class="sxs-lookup"><span data-stu-id="e7497-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="e7497-108">組織可以從 Microsoft 365 資訊安全中心的集中式儀表板監控及處理其 Microsoft 365 身分驗證、應用程式和裝置的安全性。</span><span class="sxs-lookup"><span data-stu-id="e7497-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="e7497-109">安全分數可協助組織：</span><span class="sxs-lookup"><span data-stu-id="e7497-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="e7497-110">報告組織安全性措施的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="e7497-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="e7497-111">提供可探索性、可見度、指引及控制，以改善其安全性工作。</span><span class="sxs-lookup"><span data-stu-id="e7497-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="e7497-112">與 kpi 比較並建立 KPI (關鍵) 。</span><span class="sxs-lookup"><span data-stu-id="e7497-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="e7497-113">組織可存取強大的計量和趨勢視覺效果、與其他 Microsoft 產品整合、比對類似組織分數，以及更多功能。</span><span class="sxs-lookup"><span data-stu-id="e7497-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="e7497-114">分數也會反映在協力廠商解決方案已解決建議動作時。</span><span class="sxs-lookup"><span data-stu-id="e7497-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="e7497-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="e7497-116">How it works</span></span>

<span data-ttu-id="e7497-117">您獲得下列動作的點數：</span><span class="sxs-lookup"><span data-stu-id="e7497-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="e7497-118">正在安裝建議的安全性功能</span><span class="sxs-lookup"><span data-stu-id="e7497-118">Configuring recommended security features</span></span>
- <span data-ttu-id="e7497-119">執行安全性相關工作</span><span class="sxs-lookup"><span data-stu-id="e7497-119">Doing security-related tasks</span></span>
- <span data-ttu-id="e7497-120">使用協力廠商應用程式或軟體或替代的降低風險解決改進動作</span><span class="sxs-lookup"><span data-stu-id="e7497-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="e7497-121">部分改進動作只會在完全完成時提供點數。</span><span class="sxs-lookup"><span data-stu-id="e7497-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="e7497-122">如果部分裝置或使用者已完成部分點數，系統會提供部分點數。</span><span class="sxs-lookup"><span data-stu-id="e7497-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="e7497-123">如果您無法或不想執行其中一個改進動作，可以選擇接受風險或剩餘風險。</span><span class="sxs-lookup"><span data-stu-id="e7497-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="e7497-124">如果您擁有其中一個支援的 Microsoft 產品授權，則會看到這些產品的建議。</span><span class="sxs-lookup"><span data-stu-id="e7497-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="e7497-125">不論授權版本、訂閱或方案如何，我們都會顯示完整的產品改良功能。</span><span class="sxs-lookup"><span data-stu-id="e7497-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="e7497-126">如此一來，您可以瞭解安全性最佳作法並改善您的分數。</span><span class="sxs-lookup"><span data-stu-id="e7497-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="e7497-127">無論貴組織擁有特定產品哪些授權，絕對的安全性絕對值會保持相同，以安全分數表示。</span><span class="sxs-lookup"><span data-stu-id="e7497-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="e7497-128">請記住，安全性應該與可用性保持平衡，而並非每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="e7497-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="e7497-129">您的分數會即時更新，以反映視覺效果和改良動作頁面中呈現的資訊。</span><span class="sxs-lookup"><span data-stu-id="e7497-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="e7497-130">安全分數也會每天同步處理，以接收有關您每項動作的已達成分數的系統資料。</span><span class="sxs-lookup"><span data-stu-id="e7497-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="e7497-131">主要案例</span><span class="sxs-lookup"><span data-stu-id="e7497-131">Key scenarios</span></span>

- [<span data-ttu-id="e7497-132">檢查您目前的分數</span><span class="sxs-lookup"><span data-stu-id="e7497-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="e7497-133">比較您的分數與像您這樣的組織</span><span class="sxs-lookup"><span data-stu-id="e7497-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="e7497-134">查看改進動作並決定行動計畫</span><span class="sxs-lookup"><span data-stu-id="e7497-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="e7497-135">啟動要調查或實施的資料流程</span><span class="sxs-lookup"><span data-stu-id="e7497-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="e7497-136">如何評分改進動作</span><span class="sxs-lookup"><span data-stu-id="e7497-136">How improvement actions are scored</span></span>

<span data-ttu-id="e7497-137">每個改進動作都值 10 分以下，且大部分都是以二進位方式打分數。</span><span class="sxs-lookup"><span data-stu-id="e7497-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="e7497-138">如果您執行改進動作 ，例如建立新政策或開啟特定設定，則 100% 的分數會獲得。</span><span class="sxs-lookup"><span data-stu-id="e7497-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="e7497-139">針對其他改進動作，點數會以在總組數的百分比中提供。</span><span class="sxs-lookup"><span data-stu-id="e7497-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="e7497-140">例如，改進動作會指出，使用多重要素驗證來保護所有使用者，可得到 10 個點數。</span><span class="sxs-lookup"><span data-stu-id="e7497-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="e7497-141">您只有 100 名使用者中的 50 位受到保護，因此您只得到 5 分的部分分數 (50 個受保護的 / 100 個總分 \* 10 個最大 pts = 5 個 pts) 。</span><span class="sxs-lookup"><span data-stu-id="e7497-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="e7497-142">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="e7497-142">Products included in Secure Score</span></span>

<span data-ttu-id="e7497-143">目前提供下列產品的建議：</span><span class="sxs-lookup"><span data-stu-id="e7497-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="e7497-144">Microsoft 365 (包括 Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="e7497-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="e7497-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e7497-145">Azure Active Directory</span></span>
- <span data-ttu-id="e7497-146">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e7497-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="e7497-147">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e7497-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="e7497-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e7497-148">Cloud App Security</span></span>

<span data-ttu-id="e7497-149">我們即將推出其他安全性產品的建議。</span><span class="sxs-lookup"><span data-stu-id="e7497-149">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="e7497-150">建議不會涵蓋所有與每個產品相關的攻擊面，但它們是不錯的比較基準。</span><span class="sxs-lookup"><span data-stu-id="e7497-150">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="e7497-151">您也可以將改進動作標記為協力廠商涵蓋或替代的風險降低。</span><span class="sxs-lookup"><span data-stu-id="e7497-151">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="e7497-152">安全性預設</span><span class="sxs-lookup"><span data-stu-id="e7497-152">Security defaults</span></span>

<span data-ttu-id="e7497-153">Microsoft 安全分數已更新為支援 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)中安全性預設值的改進動作，這可協助貴組織使用預先設定的安全性設定來保護常見的攻擊。</span><span class="sxs-lookup"><span data-stu-id="e7497-153">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="e7497-154">如果您開啟安全性預設值，下列改進動作會獲得完整分數：</span><span class="sxs-lookup"><span data-stu-id="e7497-154">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="e7497-155">確保所有使用者都可以完成多重要素驗證，以安全存取 (9 點) </span><span class="sxs-lookup"><span data-stu-id="e7497-155">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="e7497-156">系統管理角色需要 MFA (10 點) </span><span class="sxs-lookup"><span data-stu-id="e7497-156">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="e7497-157">啟用封鎖舊有 7 點驗證 (驗證) </span><span class="sxs-lookup"><span data-stu-id="e7497-157">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="e7497-158">安全性預設值包含的安全性功能，可提供類似「登錄風險策略」和「使用者風險政策」改進動作的安全性。</span><span class="sxs-lookup"><span data-stu-id="e7497-158">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="e7497-159">建議您將原則狀態更新為「透過替代的安全降低解決方案解決」，而不是在安全性預設值上設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="e7497-159">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="e7497-160">必要的權限</span><span class="sxs-lookup"><span data-stu-id="e7497-160">Required permissions</span></span>

<span data-ttu-id="e7497-161">若要擁有存取 Microsoft 安全分數的許可權，您必須在 Azure Active Directory 中指派下列其中一個角色。</span><span class="sxs-lookup"><span data-stu-id="e7497-161">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="e7497-162">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="e7497-162">Read and write roles</span></span>

<span data-ttu-id="e7497-163">您可以變更內容，並直接與安全分數互動。</span><span class="sxs-lookup"><span data-stu-id="e7497-163">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="e7497-164">您也可以指派唯讀存取權給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="e7497-164">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="e7497-165">全域管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-165">Global administrator</span></span>
* <span data-ttu-id="e7497-166">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-166">Security administrator</span></span>
* <span data-ttu-id="e7497-167">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-167">Exchange administrator</span></span>
* <span data-ttu-id="e7497-168">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-168">SharePoint administrator</span></span>
* <span data-ttu-id="e7497-169">帳戶管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-169">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="e7497-170">唯讀角色</span><span class="sxs-lookup"><span data-stu-id="e7497-170">Read-only roles</span></span>

<span data-ttu-id="e7497-171">使用唯讀存取時，您無法編輯狀態或改進動作的備註、編輯分數區域或編輯自訂比較。</span><span class="sxs-lookup"><span data-stu-id="e7497-171">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="e7497-172">技術支援管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-172">Helpdesk administrator</span></span>
* <span data-ttu-id="e7497-173">使用者系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-173">User administrator</span></span>
* <span data-ttu-id="e7497-174">服務管理員</span><span class="sxs-lookup"><span data-stu-id="e7497-174">Service administrator</span></span>
* <span data-ttu-id="e7497-175">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="e7497-175">Security reader</span></span>
* <span data-ttu-id="e7497-176">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="e7497-176">Security operator</span></span>
* <span data-ttu-id="e7497-177">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="e7497-177">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="e7497-178">風險認知</span><span class="sxs-lookup"><span data-stu-id="e7497-178">Risk awareness</span></span>

<span data-ttu-id="e7497-179">Microsoft 安全分數是安全性工作的數位摘要，是以系統組態、使用者行為及其他安全性相關度量為基礎。</span><span class="sxs-lookup"><span data-stu-id="e7497-179">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="e7497-180">並非絕對能測量系統或資料可能會外泄的可能性。</span><span class="sxs-lookup"><span data-stu-id="e7497-180">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="e7497-181">相反地，這代表您于 Microsoft 環境中採用安全性控制項的程度，可協助位移遭到入侵的風險。</span><span class="sxs-lookup"><span data-stu-id="e7497-181">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="e7497-182">任何線上服務都不受安全性威脅，安全分數不應視為以任何方式防範安全性漏洞的保證。</span><span class="sxs-lookup"><span data-stu-id="e7497-182">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="e7497-183">我們想知道您的想法</span><span class="sxs-lookup"><span data-stu-id="e7497-183">We want to hear from you</span></span>

<span data-ttu-id="e7497-184">如有任何問題，請張貼在安全性、隱私權和合規性& [告訴我們](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。</span><span class="sxs-lookup"><span data-stu-id="e7497-184">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="e7497-185">我們正在監控社群，並且會為您提供協助。</span><span class="sxs-lookup"><span data-stu-id="e7497-185">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e7497-186">相關資源</span><span class="sxs-lookup"><span data-stu-id="e7497-186">Related resources</span></span>

- [<span data-ttu-id="e7497-187">評估您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="e7497-187">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="e7497-188">追蹤您的 Microsoft 安全分數記錄並達成目標</span><span class="sxs-lookup"><span data-stu-id="e7497-188">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e7497-189">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="e7497-189">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="e7497-190">新功能</span><span class="sxs-lookup"><span data-stu-id="e7497-190">What's new</span></span>](microsoft-secure-score-whats-new.md)
