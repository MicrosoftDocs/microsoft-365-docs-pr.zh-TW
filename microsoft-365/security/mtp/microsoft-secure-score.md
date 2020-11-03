---
title: Microsoft 安全分數
description: 說明 microsoft 365 security center 中的 Microsoft 安全分數、如何改善安全性狀態，以及安全性管理員可以預期的狀況。
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
ms.openlocfilehash: a41e05f54a8ba94752c6df91628a2200367ac0f3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843837"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="0768e-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="0768e-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0768e-105">Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。</span><span class="sxs-lookup"><span data-stu-id="0768e-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="0768e-106">可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。</span><span class="sxs-lookup"><span data-stu-id="0768e-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="0768e-107">遵循安全分數建議可保護您的組織免受威脅。</span><span class="sxs-lookup"><span data-stu-id="0768e-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="0768e-108">透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="0768e-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="0768e-109">安全分數可協助組織：</span><span class="sxs-lookup"><span data-stu-id="0768e-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="0768e-110">報告組織安全狀況的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="0768e-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="0768e-111">提供探索性、可見度、指導方針和控制，以提升安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="0768e-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="0768e-112">請與基準進行比較，並建立 (KPIs) 的重要效能指標。</span><span class="sxs-lookup"><span data-stu-id="0768e-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="0768e-113">組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。</span><span class="sxs-lookup"><span data-stu-id="0768e-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="0768e-114">分數也可以反映協力廠商的解決方案如何解決建議的動作。</span><span class="sxs-lookup"><span data-stu-id="0768e-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="0768e-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="0768e-116">How it works</span></span>

<span data-ttu-id="0768e-117">您會在下列動作中取得重點：</span><span class="sxs-lookup"><span data-stu-id="0768e-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="0768e-118">設定推薦的安全性功能</span><span class="sxs-lookup"><span data-stu-id="0768e-118">Configuring recommended security features</span></span>
- <span data-ttu-id="0768e-119">執行安全性相關工作</span><span class="sxs-lookup"><span data-stu-id="0768e-119">Performing security-related tasks</span></span>
- <span data-ttu-id="0768e-120">使用協力廠商應用程式或軟體解決改進動作，或以替代的方式緩解</span><span class="sxs-lookup"><span data-stu-id="0768e-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="0768e-121">有些改進動作只會在完全完成時提供積分。</span><span class="sxs-lookup"><span data-stu-id="0768e-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="0768e-122">有些是在某些裝置或使用者已完成時，有些點會產生部分點。</span><span class="sxs-lookup"><span data-stu-id="0768e-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="0768e-123">如果您無法或不想要制定其中一個 [改進] 動作，您可以選擇接受風險或剩餘風險。</span><span class="sxs-lookup"><span data-stu-id="0768e-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="0768e-124">如果您有其中一個支援的 Microsoft 產品的授權，您會看到這些產品的建議。</span><span class="sxs-lookup"><span data-stu-id="0768e-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="0768e-125">不管授權版、訂閱或計畫為何，我們都會向您展示產品的完整一組可能改進。</span><span class="sxs-lookup"><span data-stu-id="0768e-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="0768e-126">如此一來，您就可以瞭解安全性最佳作法，並改善您的分數。</span><span class="sxs-lookup"><span data-stu-id="0768e-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="0768e-127">不管您的組織擁有的特定產品授權為何，您的絕對安全性狀態（以安全分數表示）都會保持不變。</span><span class="sxs-lookup"><span data-stu-id="0768e-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="0768e-128">請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="0768e-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="0768e-129">您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="0768e-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="0768e-130">安全分數也會每天同步處理每個動作的取得點數的系統資料。</span><span class="sxs-lookup"><span data-stu-id="0768e-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="0768e-131">主要案例</span><span class="sxs-lookup"><span data-stu-id="0768e-131">Key scenarios</span></span>

- [<span data-ttu-id="0768e-132">檢查您目前的分數</span><span class="sxs-lookup"><span data-stu-id="0768e-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="0768e-133">比較您的分數與您的組織</span><span class="sxs-lookup"><span data-stu-id="0768e-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="0768e-134">查看改進動作和決定行動計畫</span><span class="sxs-lookup"><span data-stu-id="0768e-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="0768e-135">啟動工作流程以進行調查或實施</span><span class="sxs-lookup"><span data-stu-id="0768e-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="0768e-136">Microsoft 365 的安全性中心和 ServiceNow 整合</span><span class="sxs-lookup"><span data-stu-id="0768e-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="0768e-137">如何計分改進動作</span><span class="sxs-lookup"><span data-stu-id="0768e-137">How improvement actions are scored</span></span>

<span data-ttu-id="0768e-138">每個改進動作都值得10點或更少，且最多會以二進位方式計分。</span><span class="sxs-lookup"><span data-stu-id="0768e-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="0768e-139">如果您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。</span><span class="sxs-lookup"><span data-stu-id="0768e-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="0768e-140">在其他改進動作中，點會指定為總設定的百分比。</span><span class="sxs-lookup"><span data-stu-id="0768e-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="0768e-141">例如，「改進」動作表明您可以使用多重要素驗證來保護所有使用者，以取得10點。</span><span class="sxs-lookup"><span data-stu-id="0768e-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="0768e-142">您只會保護50的100使用者總數，因此您可以取得5點的部分分數 (50 protected/100 總計 \* 10 最大值 = 5 pt) 。</span><span class="sxs-lookup"><span data-stu-id="0768e-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="0768e-143">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="0768e-143">Products included in Secure Score</span></span>

<span data-ttu-id="0768e-144">目前有 Microsoft 365 (的建議，包括 Exchange Online) 、Azure Active Directory、Microsoft Defender for Endpoint、Microsoft Defender 身分識別及 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="0768e-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="0768e-145">即將推出其他安全性產品的建議。</span><span class="sxs-lookup"><span data-stu-id="0768e-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="0768e-146">建議不涵蓋每項產品相關聯的所有攻擊面，但也是一個很好的基準。</span><span class="sxs-lookup"><span data-stu-id="0768e-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="0768e-147">您也可以將改進動作標示為協力廠商或替代範圍的緩解。</span><span class="sxs-lookup"><span data-stu-id="0768e-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="0768e-148">安全性預設</span><span class="sxs-lookup"><span data-stu-id="0768e-148">Security defaults</span></span>

<span data-ttu-id="0768e-149">Microsoft 安全分數已更新改進動作，以支援 [Azure Active Directory 中的安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，如此可讓您的組織使用預先設定的安全性設定進行常見的攻擊，以協助保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="0768e-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="0768e-150">如果您開啟安全性預設值，您會獲得下列改進動作的完整得分：</span><span class="sxs-lookup"><span data-stu-id="0768e-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="0768e-151">確定所有使用者均可完成 (9 點之安全訪問的多重要素驗證) </span><span class="sxs-lookup"><span data-stu-id="0768e-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="0768e-152">需要對管理角色進行 MFA (10 點) </span><span class="sxs-lookup"><span data-stu-id="0768e-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="0768e-153">啟用原則以封鎖舊版驗證 (7 點) </span><span class="sxs-lookup"><span data-stu-id="0768e-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="0768e-154">安全性預設值包括可提供類似安全性的安全性功能，以「登入風險原則」和「使用者風險原則」改進動作。</span><span class="sxs-lookup"><span data-stu-id="0768e-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="0768e-155">我們建議您將這些原則的安全性設定更新為「透過替代的緩解」來解決，而不是在安全性預設的上方進行。</span><span class="sxs-lookup"><span data-stu-id="0768e-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="0768e-156">必要的權限</span><span class="sxs-lookup"><span data-stu-id="0768e-156">Required permissions</span></span>

<span data-ttu-id="0768e-157">若要具有存取 Microsoft Secure 得分的許可權，您必須在 Azure Active Directory 中為下列其中一個角色指派。</span><span class="sxs-lookup"><span data-stu-id="0768e-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="0768e-158">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="0768e-158">Read and write roles</span></span>

<span data-ttu-id="0768e-159">透過讀取和寫入權限，您可以進行變更，並直接與安全分數互動。</span><span class="sxs-lookup"><span data-stu-id="0768e-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="0768e-160">您也可以將唯讀許可權指派給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="0768e-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="0768e-161">全域管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-161">Global administrator</span></span>
* <span data-ttu-id="0768e-162">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-162">Security administrator</span></span>
* <span data-ttu-id="0768e-163">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-163">Exchange administrator</span></span>
* <span data-ttu-id="0768e-164">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-164">SharePoint administrator</span></span>
* <span data-ttu-id="0768e-165">帳戶管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="0768e-166">唯讀角色</span><span class="sxs-lookup"><span data-stu-id="0768e-166">Read-only roles</span></span>

<span data-ttu-id="0768e-167">若具有唯讀許可權，您就無法編輯 [改進動作]、[編輯計分區域] 或 [編輯自訂比較] 的狀態或附注。</span><span class="sxs-lookup"><span data-stu-id="0768e-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="0768e-168">技術支援管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-168">Helpdesk administrator</span></span>
* <span data-ttu-id="0768e-169">使用者系統管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-169">User administrator</span></span>
* <span data-ttu-id="0768e-170">服務管理員</span><span class="sxs-lookup"><span data-stu-id="0768e-170">Service administrator</span></span>
* <span data-ttu-id="0768e-171">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="0768e-171">Security reader</span></span>
* <span data-ttu-id="0768e-172">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="0768e-172">Security operator</span></span>
* <span data-ttu-id="0768e-173">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="0768e-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="0768e-174">風險認知</span><span class="sxs-lookup"><span data-stu-id="0768e-174">Risk awareness</span></span>

<span data-ttu-id="0768e-175">Microsoft Secure 得分是根據系統設定、使用者行為及其他安全性相關度量，以數位摘要的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="0768e-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="0768e-176">這不是系統或資料遭到破壞的可能性的絕對度量。</span><span class="sxs-lookup"><span data-stu-id="0768e-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="0768e-177">相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。</span><span class="sxs-lookup"><span data-stu-id="0768e-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="0768e-178">無線上服務完全避免遭到安全違規，安全分數不得以任何方式轉譯為保證安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="0768e-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="0768e-179">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="0768e-179">We want to hear from you</span></span>

<span data-ttu-id="0768e-180">如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。</span><span class="sxs-lookup"><span data-stu-id="0768e-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="0768e-181">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="0768e-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="0768e-182">相關資源</span><span class="sxs-lookup"><span data-stu-id="0768e-182">Related resources</span></span>

- [<span data-ttu-id="0768e-183">評估您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="0768e-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="0768e-184">追蹤您的 Microsoft 安全分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="0768e-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="0768e-185">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="0768e-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="0768e-186">新功能</span><span class="sxs-lookup"><span data-stu-id="0768e-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
