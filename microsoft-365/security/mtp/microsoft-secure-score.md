---
title: Microsoft 安全分數
description: 說明 microsoft 365 security center 中的 Microsoft 安全分數、如何改善安全性狀態，以及安全性管理員可以預期的狀況。
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
ms.openlocfilehash: 57e18d68f6f33482fec3880b56ccad52c719a6d9
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023400"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="85a52-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="85a52-104">Microsoft Secure Score</span></span>

<span data-ttu-id="85a52-105">Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。</span><span class="sxs-lookup"><span data-stu-id="85a52-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="85a52-106">可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。</span><span class="sxs-lookup"><span data-stu-id="85a52-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="85a52-107">遵循安全分數建議可保護您的組織免受威脅。</span><span class="sxs-lookup"><span data-stu-id="85a52-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="85a52-108">透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="85a52-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="85a52-109">安全分數可協助組織：</span><span class="sxs-lookup"><span data-stu-id="85a52-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="85a52-110">報告組織安全狀況的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="85a52-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="85a52-111">提供探索性、可見度、指導方針和控制，以提升安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="85a52-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="85a52-112">與基準進行比較，並建立關鍵效能指標（KPIs）。</span><span class="sxs-lookup"><span data-stu-id="85a52-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="85a52-113">組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。</span><span class="sxs-lookup"><span data-stu-id="85a52-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="85a52-114">分數也可以反映協力廠商的解決方案如何解決建議的動作。</span><span class="sxs-lookup"><span data-stu-id="85a52-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="85a52-115">運作方式</span><span class="sxs-lookup"><span data-stu-id="85a52-115">How it works</span></span>

<span data-ttu-id="85a52-116">您可以在設定推薦的安全性功能、執行安全性相關工作，或使用協力廠商應用程式或軟體來解決改進動作中的點數，也可以指定其他的緩解。</span><span class="sxs-lookup"><span data-stu-id="85a52-116">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="85a52-117">有些改進動作只會在完全完成時給予點，有些的動作會在某些裝置或使用者完成時提供部分分數。</span><span class="sxs-lookup"><span data-stu-id="85a52-117">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="85a52-118">如果您無法或不想要制定其中一個 [改進] 動作，您可以選擇接受風險或剩餘風險。</span><span class="sxs-lookup"><span data-stu-id="85a52-118">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="85a52-119">不管授權為何，我們都會向您顯示一組完整的可能改進功能，讓您瞭解安全性的最佳作法，並提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="85a52-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="85a52-120">您的絕對安全性狀態是以安全分數表示，不論貴組織擁有的產品授權為何都會保持不變。</span><span class="sxs-lookup"><span data-stu-id="85a52-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="85a52-121">請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="85a52-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="85a52-122">您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="85a52-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="85a52-123">安全分數也會每天同步處理每個動作的取得點數的系統資料。</span><span class="sxs-lookup"><span data-stu-id="85a52-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="85a52-124">如何計分改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-124">How improvement actions are scored</span></span>

<span data-ttu-id="85a52-125">每個改進動作都值得10點或更少。</span><span class="sxs-lookup"><span data-stu-id="85a52-125">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="85a52-126">大多數會以二進位方式計分：若您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。</span><span class="sxs-lookup"><span data-stu-id="85a52-126">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="85a52-127">在其他改進動作中，點會指定為總設定的百分比。</span><span class="sxs-lookup"><span data-stu-id="85a52-127">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="85a52-128">例如，如果改進的動作指出您使用多重要素驗證來保護所有使用者時取得10點，而且您只會保護 50 100 的使用者，則會得到部分分數5點（50 protected/100 總計 \* 10 最大值 = 5 pt 部分分數）。</span><span class="sxs-lookup"><span data-stu-id="85a52-128">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="85a52-129">安全分數中包含的產品</span><span class="sxs-lookup"><span data-stu-id="85a52-129">Products included in Secure Score</span></span>

<span data-ttu-id="85a52-130">目前有 Microsoft 365 （包括 Exchange Online）、Azure AD、Microsoft Defender ATP、Azure ATP 和 Cloud App Security 的建議。</span><span class="sxs-lookup"><span data-stu-id="85a52-130">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="85a52-131">即將推出其他安全性產品的建議。</span><span class="sxs-lookup"><span data-stu-id="85a52-131">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="85a52-132">建議不會涵蓋與各項產品相關聯的所有攻擊面，但也是一個很好的基準。</span><span class="sxs-lookup"><span data-stu-id="85a52-132">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="85a52-133">您也可以將改進動作標示為協力廠商或替代範圍的緩解。</span><span class="sxs-lookup"><span data-stu-id="85a52-133">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="85a52-134">安全性預設</span><span class="sxs-lookup"><span data-stu-id="85a52-134">Security defaults</span></span>

<span data-ttu-id="85a52-135">Microsoft 安全分數已更新改進動作，以支援[Azure Active Directory 中的安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，如此可讓您的組織使用預先設定的安全性設定進行常見的攻擊，以協助保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="85a52-135">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="85a52-136">如果您開啟安全性預設值，您會獲得下列改進動作的完整得分：</span><span class="sxs-lookup"><span data-stu-id="85a52-136">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="85a52-137">確定所有使用者均可完成安全存取的多重要素驗證（9點）</span><span class="sxs-lookup"><span data-stu-id="85a52-137">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="85a52-138">需要對管理角色進行 MFA （10點）</span><span class="sxs-lookup"><span data-stu-id="85a52-138">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="85a52-139">啟用原則以封鎖舊版驗證（7點）</span><span class="sxs-lookup"><span data-stu-id="85a52-139">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="85a52-140">安全性預設值包括可提供類似安全性的安全性功能，以「登入風險原則」和「使用者風險原則」改進動作。</span><span class="sxs-lookup"><span data-stu-id="85a52-140">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="85a52-141">我們建議您將這些原則的安全性設定更新為「透過替代的緩解」來解決，而不是在安全性預設的上方進行。</span><span class="sxs-lookup"><span data-stu-id="85a52-141">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="85a52-142">必要的權限</span><span class="sxs-lookup"><span data-stu-id="85a52-142">Required permissions</span></span>

<span data-ttu-id="85a52-143">若要具有存取 Microsoft Secure 得分的許可權，您必須在 Azure Active Directory 中為下列其中一個角色指派。</span><span class="sxs-lookup"><span data-stu-id="85a52-143">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="85a52-144">讀取和寫入角色</span><span class="sxs-lookup"><span data-stu-id="85a52-144">Read and write roles</span></span>

<span data-ttu-id="85a52-145">透過讀取和寫入權限，您可以進行變更，並直接與安全分數互動。</span><span class="sxs-lookup"><span data-stu-id="85a52-145">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="85a52-146">您也可以將唯讀許可權指派給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="85a52-146">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="85a52-147">全域管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-147">Global administrator</span></span>
* <span data-ttu-id="85a52-148">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-148">Security administrator</span></span>
* <span data-ttu-id="85a52-149">Exchange 系統管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-149">Exchange administrator</span></span>
* <span data-ttu-id="85a52-150">SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-150">SharePoint administrator</span></span>
* <span data-ttu-id="85a52-151">帳戶管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-151">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="85a52-152">唯讀角色</span><span class="sxs-lookup"><span data-stu-id="85a52-152">Read-only roles</span></span>

<span data-ttu-id="85a52-153">若具有唯讀許可權，您就無法編輯 [改進動作]、[編輯計分區域] 或 [編輯自訂比較] 的狀態或附注。</span><span class="sxs-lookup"><span data-stu-id="85a52-153">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="85a52-154">説明台管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-154">Helpdesk administrator</span></span>
* <span data-ttu-id="85a52-155">使用者管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-155">User administrator</span></span>
* <span data-ttu-id="85a52-156">服務管理員</span><span class="sxs-lookup"><span data-stu-id="85a52-156">Service administrator</span></span>
* <span data-ttu-id="85a52-157">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="85a52-157">Security reader</span></span>
* <span data-ttu-id="85a52-158">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="85a52-158">Security operator</span></span>
* <span data-ttu-id="85a52-159">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="85a52-159">Global reader</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="85a52-160">深入瞭解您的安全性狀況</span><span class="sxs-lookup"><span data-stu-id="85a52-160">Gain visibility into your security posture</span></span>

<span data-ttu-id="85a52-161">為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：</span><span class="sxs-lookup"><span data-stu-id="85a52-161">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="85a52-162">Identity （Azure AD 帳戶 & 角色）</span><span class="sxs-lookup"><span data-stu-id="85a52-162">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="85a52-163">資料（Microsoft 資訊保護）</span><span class="sxs-lookup"><span data-stu-id="85a52-163">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="85a52-164">裝置（Microsoft Defender ATP，稱為設定[分數](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)）</span><span class="sxs-lookup"><span data-stu-id="85a52-164">Device (Microsoft Defender ATP, known as [Configuration score](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))</span></span>
* <span data-ttu-id="85a52-165">應用程式（電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）</span><span class="sxs-lookup"><span data-stu-id="85a52-165">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="85a52-166">基礎結構（現在沒有任何改進動作）</span><span class="sxs-lookup"><span data-stu-id="85a52-166">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="85a52-167">在最近發行的 Microsoft Secure 得分中，已發行的評分模型已發佈，使 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。</span><span class="sxs-lookup"><span data-stu-id="85a52-167">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="85a52-168">檢視詳細資料</span><span class="sxs-lookup"><span data-stu-id="85a52-168">View details</span></span>](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

<span data-ttu-id="85a52-169">在 [Microsoft Secure 得分一覽] 頁面中，您可以看到各群組之間的點數如何分割，以及哪些點可供使用。</span><span class="sxs-lookup"><span data-stu-id="85a52-169">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="85a52-170">[一覽表] 頁面也是取得整體總分、您的安全分數與基準比較之歷史趨勢的完整視圖，以及可以採取以改善評分的優先改進動作的位置。</span><span class="sxs-lookup"><span data-stu-id="85a52-170">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="85a52-172">採取動作以提升您的分數</span><span class="sxs-lookup"><span data-stu-id="85a52-172">Take action to improve your score</span></span>

<span data-ttu-id="85a52-173">[**改進動作**] 索引標籤會列出解決可能的攻擊面的安全性建議，及其狀態（to address、已計畫、已被認可的風險、透過協力廠商解決的問題，以及透過取代的緩解，以及已完成）。</span><span class="sxs-lookup"><span data-stu-id="85a52-173">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="85a52-174">您可以搜尋、篩選和群組所有的「改進」動作。</span><span class="sxs-lookup"><span data-stu-id="85a52-174">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="85a52-175">排名</span><span class="sxs-lookup"><span data-stu-id="85a52-175">Ranking</span></span>

<span data-ttu-id="85a52-176">排名是根據剩下的剩餘點數、實施難度、使用者影響和複雜性而定。</span><span class="sxs-lookup"><span data-stu-id="85a52-176">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="85a52-177">最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。</span><span class="sxs-lookup"><span data-stu-id="85a52-177">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="85a52-178">查看改進動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="85a52-178">View improvement action details</span></span>

<span data-ttu-id="85a52-179">當您選取特定的 [提升] 動作時，會出現完整的頁面快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="85a52-179">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="85a52-180">![改進動作飛出範例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *圖2：改進動作飛出範例*</span><span class="sxs-lookup"><span data-stu-id="85a52-180">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="85a52-181">若要完成此動作，您有幾個選項：</span><span class="sxs-lookup"><span data-stu-id="85a52-181">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="85a52-182">選取 [**管理**] 以進入設定畫面並進行變更。</span><span class="sxs-lookup"><span data-stu-id="85a52-182">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="85a52-183">接著，您將會在飛出的位置看到必要的動作。點通常需要24小時才能更新。</span><span class="sxs-lookup"><span data-stu-id="85a52-183">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="85a52-184">選取 [**共用**]，將直接連結複製到 [改進] 動作，或選擇用來共用連結的平臺，例如電子郵件、microsoft 小組、microsoft Planner 或 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="85a52-184">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="85a52-185">選取 [ServiceNow 將可讓您建立 ServiceNow 和 Microsoft 365 的安全性中心首頁會顯示的變更票證。</span><span class="sxs-lookup"><span data-stu-id="85a52-185">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="85a52-186">若要深入瞭解，請參閱[Microsoft 365 Security Center 和 ServiceNow integration](tickets.md)。</span><span class="sxs-lookup"><span data-stu-id="85a52-186">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="85a52-187">選擇改進動作狀態</span><span class="sxs-lookup"><span data-stu-id="85a52-187">Choose an improvement action status</span></span>

<span data-ttu-id="85a52-188">選擇 [改進] 動作特有的任何狀態和記錄附注。</span><span class="sxs-lookup"><span data-stu-id="85a52-188">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="85a52-189">您可以選取下列 statues：</span><span class="sxs-lookup"><span data-stu-id="85a52-189">The statues you can select are the following:</span></span>

* <span data-ttu-id="85a52-190">**若要解決**此事項，您可以辨識改進動作是必要的，並計畫于未來某一點進行處理。</span><span class="sxs-lookup"><span data-stu-id="85a52-190">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="85a52-191">這種狀態也適用于已偵測到部分但未完全完成的動作。</span><span class="sxs-lookup"><span data-stu-id="85a52-191">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="85a52-192">已**計畫**-完成改進動作有一些具體的計畫。</span><span class="sxs-lookup"><span data-stu-id="85a52-192">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="85a52-193">已**接受風險**-安全性應該一定要與可用性進行平衡，而不是每個建議都適用于您的環境。</span><span class="sxs-lookup"><span data-stu-id="85a52-193">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="85a52-194">在這種情況下，您可以選擇接受風險或餘下的風險，而不會制定改進動作。</span><span class="sxs-lookup"><span data-stu-id="85a52-194">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="85a52-195">您不會獲得任何點數，但是動作將不再顯示在 [改進動作] 清單中。</span><span class="sxs-lookup"><span data-stu-id="85a52-195">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="85a52-196">您可以在歷史記錄中查看此動作，也可以隨時復原。</span><span class="sxs-lookup"><span data-stu-id="85a52-196">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="85a52-197">**透過協力廠商解決**，並**透過替代的緩解**措施加以解決--改進動作已經由協力廠商應用程式或軟體或內部工具所解決。</span><span class="sxs-lookup"><span data-stu-id="85a52-197">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="85a52-198">您將會獲得值得行動的點數，所以您的分數會更好反映整體的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="85a52-198">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="85a52-199">如果協力廠商或內部工具不再涵蓋該控制項，您可以選擇其他狀態。</span><span class="sxs-lookup"><span data-stu-id="85a52-199">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="85a52-200">請記住，如果改進動作標示為這兩種狀態，Microsoft 將不會深入瞭解實施的完整性。</span><span class="sxs-lookup"><span data-stu-id="85a52-200">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="85a52-201">威脅 & 弱點管理的改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-201">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="85a52-202">在 "Device" 類別中的改進動作，您將無法選擇狀態。</span><span class="sxs-lookup"><span data-stu-id="85a52-202">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="85a52-203">相反地，您會將[Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)的相關[威脅 & 漏洞管理（TVM）安全性建議](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)，以採取行動。</span><span class="sxs-lookup"><span data-stu-id="85a52-203">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="85a52-204">您選擇的例外狀況和您所撰寫的理由將會特定于該入口網站，而且不會出現在 Microsoft Secure 得分入口網站中。</span><span class="sxs-lookup"><span data-stu-id="85a52-204">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="85a52-205">已完成的改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-205">Completed improvement actions</span></span>

<span data-ttu-id="85a52-206">在完成改進動作的所有可能點之後，[改進動作] 的狀態為「已完成」。</span><span class="sxs-lookup"><span data-stu-id="85a52-206">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="85a52-207">已完成的改善動作會透過 Microsoft data 加以確認，而且您將無法變更狀態。</span><span class="sxs-lookup"><span data-stu-id="85a52-207">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="85a52-208">評估資訊並複查使用者影響</span><span class="sxs-lookup"><span data-stu-id="85a52-208">Assess information and review user impact</span></span>

<span data-ttu-id="85a52-209">**在 [一覽**] 區段中，將會告訴您您的類別、可以防禦的攻擊，以及產品。</span><span class="sxs-lookup"><span data-stu-id="85a52-209">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="85a52-210">[**使用者影響**] 顯示使用者在已頒佈改進動作時的體驗，以及**受影響的使用者**會顯示誰會體驗。</span><span class="sxs-lookup"><span data-stu-id="85a52-210">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="85a52-211">實施改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-211">Implement the improvement action</span></span>

<span data-ttu-id="85a52-212">「**實施**」區段會顯示所有必要條件、逐步後續步驟以完成 [改進] 動作、[改進動作] 的目前實施狀態，以及任何 [深入瞭解] 連結。</span><span class="sxs-lookup"><span data-stu-id="85a52-212">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="85a52-213">必要條件會是任何需要取得的授權，或是在解決改進動作之前必須完成的動作。</span><span class="sxs-lookup"><span data-stu-id="85a52-213">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="85a52-214">請確定您的授權有足夠的座位，可完成 [改進] 動作，並將這些授權套用至必要的使用者。</span><span class="sxs-lookup"><span data-stu-id="85a52-214">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="85a52-215">追蹤您的分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="85a52-215">Track your score history and meet goals</span></span>

<span data-ttu-id="85a52-216">您可以在 [**記錄**] 索引標籤中，在一段時間內，查看組織的分數圖表。在圖形下方會列出所選取時間範圍內所執行的所有動作，以及其屬性，例如結果點和類別。</span><span class="sxs-lookup"><span data-stu-id="85a52-216">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="85a52-217">您可以自訂日期範圍及依類別篩選。</span><span class="sxs-lookup"><span data-stu-id="85a52-217">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="85a52-218">在 [**度量 & 趨勢**] 索引標籤中，有數個圖形可讓您更深入的趨勢及設定目標。</span><span class="sxs-lookup"><span data-stu-id="85a52-218">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="85a52-219">您可以設定整個視覺效果頁面的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="85a52-219">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="85a52-220">視覺化效果包括：</span><span class="sxs-lookup"><span data-stu-id="85a52-220">The visualizations include:</span></span>

* <span data-ttu-id="85a52-221">**您的安全分數區域**-自訂取決於組織的目標和「良好」、「好」和「不良分數」範圍的定義。</span><span class="sxs-lookup"><span data-stu-id="85a52-221">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="85a52-222">**回歸趨勢**-因設定、使用者或裝置變更而 regressed 之點的時程表。</span><span class="sxs-lookup"><span data-stu-id="85a52-222">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="85a52-223">**比較趨勢**-組織的安全分數與其他時間的比較方式。</span><span class="sxs-lookup"><span data-stu-id="85a52-223">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="85a52-224">此視圖可以包含表示具有類似座位元數目之組織之分數平均的行，以及您可以設定的自訂比較視圖。</span><span class="sxs-lookup"><span data-stu-id="85a52-224">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="85a52-225">**風險接受趨勢**-標示為「風險已接受」的「改進」動作時程表。</span><span class="sxs-lookup"><span data-stu-id="85a52-225">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="85a52-226">**得分變更**-已取得的點數，點 regressed，以及後續得分變更，在指定的日期範圍內。</span><span class="sxs-lookup"><span data-stu-id="85a52-226">**Score changes** — The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="85a52-227">風險認知</span><span class="sxs-lookup"><span data-stu-id="85a52-227">Risk awareness</span></span>

<span data-ttu-id="85a52-228">Microsoft Secure 得分是根據系統設定、使用者行為和其他安全性相關度量的安全性狀況的數位摘要;這不是系統或資料被破壞的可能性的絕對度量。</span><span class="sxs-lookup"><span data-stu-id="85a52-228">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="85a52-229">相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。</span><span class="sxs-lookup"><span data-stu-id="85a52-229">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="85a52-230">沒有任何線上服務完全避免安全缺口，安全分數不得以任何方式轉譯為保證安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="85a52-230">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="85a52-231">新功能</span><span class="sxs-lookup"><span data-stu-id="85a52-231">What's new?</span></span> 

<span data-ttu-id="85a52-232">若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。</span><span class="sxs-lookup"><span data-stu-id="85a52-232">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="85a52-233">若要深入瞭解規劃的變更，請參閱[Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)。</span><span class="sxs-lookup"><span data-stu-id="85a52-233">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="85a52-234">不相容身分識別安全分數與圖形 API</span><span class="sxs-lookup"><span data-stu-id="85a52-234">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="85a52-235">在最近發行的 Microsoft Secure 得分中，已發佈一個已改進的計分模型。</span><span class="sxs-lookup"><span data-stu-id="85a52-235">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="85a52-236">這些變更可讓您更靈活且準確的安全性狀況的觀點。</span><span class="sxs-lookup"><span data-stu-id="85a52-236">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="85a52-237">不過，這些更新已讓 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。</span><span class="sxs-lookup"><span data-stu-id="85a52-237">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="85a52-238">在時間內，身分識別安全分數和圖形 API 將採用新的計分模型。</span><span class="sxs-lookup"><span data-stu-id="85a52-238">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="85a52-239">在此之前，客戶會看到 Microsoft 安全評分、身分識別安全分數及圖形 API 所報告的分數差異。</span><span class="sxs-lookup"><span data-stu-id="85a52-239">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="85a52-240">我們對這項不便的任何不便深表歉意，而且正在運作，以確保未來的體驗更具相容性。</span><span class="sxs-lookup"><span data-stu-id="85a52-240">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

### <a name="updated-improvement-actions"></a><span data-ttu-id="85a52-241">更新的改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-241">Updated improvement actions</span></span>

- <span data-ttu-id="85a52-242">新增 Azure Active Directory 改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-242">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="85a52-243">新增 Azure 高級威脅防護改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-243">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="85a52-244">支援 Microsoft Defender ATP[威脅 & 弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)安全性建議</span><span class="sxs-lookup"><span data-stu-id="85a52-244">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="85a52-245">現在提供 TVM 提供的所有發行安全性建議</span><span class="sxs-lookup"><span data-stu-id="85a52-245">All released security recommendations supplied by TVM are now available</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="85a52-246">更新的介面及功能</span><span class="sxs-lookup"><span data-stu-id="85a52-246">Updated interface and functionality</span></span>

* <span data-ttu-id="85a52-247">CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖</span><span class="sxs-lookup"><span data-stu-id="85a52-247">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="85a52-248">追蹤和基準成績的新方法</span><span class="sxs-lookup"><span data-stu-id="85a52-248">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="85a52-249">更好地追蹤和瞭解分數回歸</span><span class="sxs-lookup"><span data-stu-id="85a52-249">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="85a52-250">篩選、標記、搜尋及群組您的改善動作</span><span class="sxs-lookup"><span data-stu-id="85a52-250">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="85a52-251">使用分數預測和規劃的動作來管理您的未來目標</span><span class="sxs-lookup"><span data-stu-id="85a52-251">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="85a52-252">還有更多！</span><span class="sxs-lookup"><span data-stu-id="85a52-252">And more!</span></span>

### <a name="june-2020"></a><span data-ttu-id="85a52-253">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="85a52-253">June 2020</span></span>

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="85a52-254">已移除 Microsoft Defender 高級威脅防護的改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-254">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="85a52-255">開啟攻擊面減少規則</span><span class="sxs-lookup"><span data-stu-id="85a52-255">Turn on Attack Surface Reduction rules</span></span>

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="85a52-256">新增 Microsoft Defender 高級威脅防護的改進動作</span><span class="sxs-lookup"><span data-stu-id="85a52-256">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="85a52-257">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="85a52-257">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="85a52-258">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="85a52-258">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="85a52-259">封鎖所有 Office 應用程式以建立子流程</span><span class="sxs-lookup"><span data-stu-id="85a52-259">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="85a52-260">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="85a52-260">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="85a52-261">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="85a52-261">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="85a52-262">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="85a52-262">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="85a52-263">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="85a52-263">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="85a52-264">封鎖 Office communication application 建立子流程</span><span class="sxs-lookup"><span data-stu-id="85a52-264">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="85a52-265">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="85a52-265">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="85a52-266">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="85a52-266">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="85a52-267">封鎖 Office 應用程式將程式碼注入其他程式</span><span class="sxs-lookup"><span data-stu-id="85a52-267">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="85a52-268">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="85a52-268">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="85a52-269">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="85a52-269">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="85a52-270">從 Windows local security 機關子系統封鎖認證竊取（lsass.exe）</span><span class="sxs-lookup"><span data-stu-id="85a52-270">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="85a52-271">封鎖 Office 宏的 WIN32 API 呼叫</span><span class="sxs-lookup"><span data-stu-id="85a52-271">Block Win32 API calls from Office macros</span></span>


## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="85a52-272">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="85a52-272">We want to hear from you</span></span>

<span data-ttu-id="85a52-273">如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。</span><span class="sxs-lookup"><span data-stu-id="85a52-273">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="85a52-274">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="85a52-274">We're monitoring the community and will provide help.</span></span>

