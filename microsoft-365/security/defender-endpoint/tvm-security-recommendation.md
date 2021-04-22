---
title: 威脅和弱點管理的安全性建議
description: 取得依威脅及威脅及弱點管理中威脅和價值的可操作安全性建議。
keywords: 威脅和弱點管理，Microsoft Defender for Endpoint tvm security 建議，cybersecurity 建議，可操作的安全性建議
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933730"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="648e2-104">安全性建議-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="648e2-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="648e2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="648e2-105">**Applies to:**</span></span>

- [<span data-ttu-id="648e2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="648e2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="648e2-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="648e2-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="648e2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="648e2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="648e2-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="648e2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="648e2-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="648e2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="648e2-111">組織中所識別的 Cybersecurity 弱點會對應至可操作的安全性建議，並依其影響來設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="648e2-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="648e2-112">優先的建議有助於縮短緩解或修復弱點的時間，以及促進法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="648e2-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="648e2-113">每個安全性建議都包括可操作的修復步驟。</span><span class="sxs-lookup"><span data-stu-id="648e2-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="648e2-114">為了協助進行任務管理，也可以使用 Microsoft Intune 和 Microsoft 端點 Configuration Manager 傳送建議。</span><span class="sxs-lookup"><span data-stu-id="648e2-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="648e2-115">當威脅變化時，建議也會隨著它不斷地從您的環境收集資訊而變更。</span><span class="sxs-lookup"><span data-stu-id="648e2-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="648e2-116">若要取得有關新弱點事件的電子郵件，請參閱 [在 Microsoft Defender For Endpoint 中設定弱點電子郵件通知](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="648e2-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="648e2-117">運作方式</span><span class="sxs-lookup"><span data-stu-id="648e2-117">How it works</span></span>

<span data-ttu-id="648e2-118">組織中的每個裝置都會根據三個重要因素進行計分，以協助客戶在正確的時間集中處理正確的專案。</span><span class="sxs-lookup"><span data-stu-id="648e2-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="648e2-119">**威脅** -組織裝置中的漏洞和入侵行為，以及破壞歷程記錄中的特性。</span><span class="sxs-lookup"><span data-stu-id="648e2-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="648e2-120">根據這些因素，安全性建議會顯示與使用中警示、不斷威脅活動以及其相對應威脅分析報告相關的連結。</span><span class="sxs-lookup"><span data-stu-id="648e2-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="648e2-121">**破壞性可能性** -您的組織的安全性狀況和抵禦威脅的能力</span><span class="sxs-lookup"><span data-stu-id="648e2-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="648e2-122">**業務價值** -您的組織的資產、重要程式和知識屬性</span><span class="sxs-lookup"><span data-stu-id="648e2-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="648e2-123">流覽至安全性建議頁面</span><span class="sxs-lookup"><span data-stu-id="648e2-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="648e2-124">以幾種不同的方式存取安全性建議頁面：</span><span class="sxs-lookup"><span data-stu-id="648e2-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="648e2-125">[Microsoft Defender Security Center](portal-overview.md)中的威脅和弱點管理導覽功能表</span><span class="sxs-lookup"><span data-stu-id="648e2-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="648e2-126">[威脅與弱點管理儀表板](tvm-dashboard-insights.md)中的最高安全性建議</span><span class="sxs-lookup"><span data-stu-id="648e2-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="648e2-127">在下列位置查看相關的安全性建議：</span><span class="sxs-lookup"><span data-stu-id="648e2-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="648e2-128">軟體頁面</span><span class="sxs-lookup"><span data-stu-id="648e2-128">Software page</span></span>
- <span data-ttu-id="648e2-129">裝置頁面</span><span class="sxs-lookup"><span data-stu-id="648e2-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="648e2-130">流覽功能表</span><span class="sxs-lookup"><span data-stu-id="648e2-130">Navigation menu</span></span>

<span data-ttu-id="648e2-131">移至 [威脅與弱點管理] 導覽功能表，然後選取 [ **安全性建議**]。</span><span class="sxs-lookup"><span data-stu-id="648e2-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="648e2-132">此頁面包含組織中所發現之威脅及弱點的安全性建議清單。</span><span class="sxs-lookup"><span data-stu-id="648e2-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="648e2-133">威脅與弱點管理儀表板中的最高安全性建議</span><span class="sxs-lookup"><span data-stu-id="648e2-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="648e2-134">在一天的安全性管理員中，您可以查看[威脅和弱點管理儀表板](tvm-dashboard-insights.md)，以查看[裝置的 Microsoft 安全分數](tvm-microsoft-secure-score-devices.md)並排[公開的總分](tvm-exposure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="648e2-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="648e2-135">其目標是 **降低** 組織面臨的漏洞，並 **增加** 組織的裝置安全性，以更具彈性的 cybersecurity 威脅攻擊。</span><span class="sxs-lookup"><span data-stu-id="648e2-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="648e2-136">最常見的安全性建議清單可協助您達成該目標。</span><span class="sxs-lookup"><span data-stu-id="648e2-136">The top security recommendations list can help you achieve that goal.</span></span>

![安全性建議卡片的範例，具有四個安全性建議。](images/top-security-recommendations350.png)

<span data-ttu-id="648e2-138">最上層的安全性建議會根據上一節所述的重要因素，依可能破壞的可能性和價值，列出改進的機遇優先順序。</span><span class="sxs-lookup"><span data-stu-id="648e2-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="648e2-139">選取建議會帶您前往 [安全性建議] 頁面，以取得更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="648e2-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="648e2-140">安全性建議一覽表</span><span class="sxs-lookup"><span data-stu-id="648e2-140">Security recommendations overview</span></span>

<span data-ttu-id="648e2-141">查看建議、找到的弱點數目、相關元件、威脅洞察力、公開裝置數目、狀態、修正類型、修復活動、對您的暴露分數的影響，以及對裝置的 Microsoft 安全分數和相關的標記。</span><span class="sxs-lookup"><span data-stu-id="648e2-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="648e2-142">已 **公開裝置** 圖的色彩會隨著趨勢變更而變更。</span><span class="sxs-lookup"><span data-stu-id="648e2-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="648e2-143">如果公開的裝置數目增加，則色彩會變成紅色。</span><span class="sxs-lookup"><span data-stu-id="648e2-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="648e2-144">如果公開的裝置數目減少，圖形的色彩會變成綠色。</span><span class="sxs-lookup"><span data-stu-id="648e2-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="648e2-145">威脅和弱點管理顯示在最多 **30 天** 前使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="648e2-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="648e2-146">這與其余的 Microsoft Defender for Endpoint 不同，在此情況下，裝置未使用超過7天，其狀態為「非作用中」。</span><span class="sxs-lookup"><span data-stu-id="648e2-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![安全性建議的登陸頁面範例。](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="648e2-148">圖示</span><span class="sxs-lookup"><span data-stu-id="648e2-148">Icons</span></span>

<span data-ttu-id="648e2-149">有用的圖示也很快就能讓您注意：</span><span class="sxs-lookup"><span data-stu-id="648e2-149">Useful icons also quickly call your attention to:</span></span>
- ![擊中目標的箭號](images/tvm_alert_icon.png) <span data-ttu-id="648e2-151">可能的活動警示</span><span class="sxs-lookup"><span data-stu-id="648e2-151">possible active alerts</span></span>
- ![紅色的錯誤](images/tvm_bug_icon.png) <span data-ttu-id="648e2-153">關聯的公開利用漏洞</span><span class="sxs-lookup"><span data-stu-id="648e2-153">associated public exploits</span></span>
- ![燈泡](images/tvm_insight_icon.png) <span data-ttu-id="648e2-155">建議 insights</span><span class="sxs-lookup"><span data-stu-id="648e2-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="648e2-156">探索安全性建議選項</span><span class="sxs-lookup"><span data-stu-id="648e2-156">Explore security recommendation options</span></span>

<span data-ttu-id="648e2-157">選取您要調查或處理的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="648e2-157">Select the security recommendation that you want to investigate or process.</span></span>

![安全性建議飛出頁面的範例。](images/secrec-flyouteolsw.png)

<span data-ttu-id="648e2-159">您可以從飛出的任何選項，選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="648e2-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="648e2-160">**開啟軟體頁面** -開啟軟體頁面以取得軟體的更多內容，以及其散佈方式。</span><span class="sxs-lookup"><span data-stu-id="648e2-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="648e2-161">此資訊可包含威脅內容、相關的建議、發現的劣勢、公開的裝置數目、發現的漏洞、已安裝軟體的裝置名稱和詳細資訊，以及版本發行。</span><span class="sxs-lookup"><span data-stu-id="648e2-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="648e2-162">[**修正選項**](tvm-remediation.md) -提交修復要求以在 Microsoft Intune 中開啟票證，讓您的 IT 系統管理員挑選並解決。</span><span class="sxs-lookup"><span data-stu-id="648e2-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="648e2-163">在 [修正] 頁面中追蹤修復活動。</span><span class="sxs-lookup"><span data-stu-id="648e2-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="648e2-164">[**例外狀況選項**](tvm-exception.md) -提交例外狀況、提供理由，並設定例外期限（如果您無法修正問題）。</span><span class="sxs-lookup"><span data-stu-id="648e2-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="648e2-165">在裝置上進行軟體變更時，通常需要2個小時，資料才會反映在安全性入口網站中。</span><span class="sxs-lookup"><span data-stu-id="648e2-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="648e2-166">不過，有時可能需要較長的時間。</span><span class="sxs-lookup"><span data-stu-id="648e2-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="648e2-167">設定變更可能需要4到24小時的任何時間。</span><span class="sxs-lookup"><span data-stu-id="648e2-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="648e2-168">調查裝置洩密或影響中的變更</span><span class="sxs-lookup"><span data-stu-id="648e2-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="648e2-169">如果公開的裝置數目很大，或對組織暴露分數和 Microsoft 安全分數影響的影響增加，則安全性建議值得調查。</span><span class="sxs-lookup"><span data-stu-id="648e2-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="648e2-170">選取 [建議] 和 [ **開啟軟體] 頁面**</span><span class="sxs-lookup"><span data-stu-id="648e2-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="648e2-171">選取 [ **事件時程表** ] 索引標籤，以查看與該軟體相關的所有 impactful 事件，例如新的漏洞或新的公開攻擊。</span><span class="sxs-lookup"><span data-stu-id="648e2-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="648e2-172">深入瞭解事件時程表</span><span class="sxs-lookup"><span data-stu-id="648e2-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="648e2-173">決定如何解決增加或組織面臨的風險，例如提交修復要求</span><span class="sxs-lookup"><span data-stu-id="648e2-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="648e2-174">要求修正</span><span class="sxs-lookup"><span data-stu-id="648e2-174">Request remediation</span></span>

<span data-ttu-id="648e2-175">威脅和弱點管理修復功能會透過修正要求工作流程，來橋接安全性和 IT 管理員之間的缺口。</span><span class="sxs-lookup"><span data-stu-id="648e2-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="648e2-176">安全性管理員贊您可要求 IT 管理員從 [ **安全性建議** ] 頁面修正為 Intune 的漏洞。</span><span class="sxs-lookup"><span data-stu-id="648e2-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="648e2-177">深入瞭解修復選項</span><span class="sxs-lookup"><span data-stu-id="648e2-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="648e2-178">如何要求修正</span><span class="sxs-lookup"><span data-stu-id="648e2-178">How to request remediation</span></span>

<span data-ttu-id="648e2-179">選取您要要求修復的安全性建議，然後選取 [ **修正選項**]。</span><span class="sxs-lookup"><span data-stu-id="648e2-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="648e2-180">填寫表單，然後選取 [ **提交要求**]。</span><span class="sxs-lookup"><span data-stu-id="648e2-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="648e2-181">移至 [ [**修復**](tvm-remediation.md) ] 頁面，以查看修正要求的狀態。</span><span class="sxs-lookup"><span data-stu-id="648e2-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="648e2-182">深入瞭解如何要求修正</span><span class="sxs-lookup"><span data-stu-id="648e2-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="648e2-183">例外狀況的檔案</span><span class="sxs-lookup"><span data-stu-id="648e2-183">File for exception</span></span>

<span data-ttu-id="648e2-184">如果目前沒有相關建議，則為修正要求的替代，您可以為建議建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="648e2-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="648e2-185">深入瞭解例外狀況</span><span class="sxs-lookup"><span data-stu-id="648e2-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="648e2-186">只有「例外狀況處理」許可權的使用者才可以新增例外狀況。</span><span class="sxs-lookup"><span data-stu-id="648e2-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="648e2-187">[深入瞭解 RBAC 角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="648e2-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="648e2-188">當為建議建立例外狀況時，建議不再使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="648e2-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="648e2-189">建議狀態會變更為設備群組)  (的 **完整例外** 狀況或 **部分例外** 狀況。</span><span class="sxs-lookup"><span data-stu-id="648e2-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="648e2-190">如何建立例外狀況</span><span class="sxs-lookup"><span data-stu-id="648e2-190">How to create an exception</span></span>

<span data-ttu-id="648e2-191">選取您要為其建立例外狀況的安全性建議，然後選取 [ **例外狀況選項**]。</span><span class="sxs-lookup"><span data-stu-id="648e2-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![顯示「例外選項」按鈕在安全性建議浮出的位置。](images/tvm-exception-options.png)

<span data-ttu-id="648e2-193">填寫表單並提交。</span><span class="sxs-lookup"><span data-stu-id="648e2-193">Fill out the form and submit.</span></span> <span data-ttu-id="648e2-194">若要查看所有例外狀況 (目前及過去) ，請流覽至 **威脅 & 弱點管理**] 功能表底下的 [[修正](tvm-remediation.md)] 頁面，然後選取 [**例外** 狀況] 索引標籤。[深入瞭解如何建立例外](tvm-exception.md#create-an-exception)狀況</span><span class="sxs-lookup"><span data-stu-id="648e2-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="648e2-195">報表 inaccuracy</span><span class="sxs-lookup"><span data-stu-id="648e2-195">Report inaccuracy</span></span>

<span data-ttu-id="648e2-196">當您看到任何不清楚、不准確、不完整或已修正的安全性建議資訊時，您可以報告誤報。</span><span class="sxs-lookup"><span data-stu-id="648e2-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="648e2-197">開啟安全性建議。</span><span class="sxs-lookup"><span data-stu-id="648e2-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="648e2-198">選取您想要報告之安全性建議旁的三個點，然後選取 [ **報表 inaccuracy**]。</span><span class="sxs-lookup"><span data-stu-id="648e2-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![顯示「報表 inaccuracy」按鈕在安全性建議浮出的位置。](images/report-inaccuracy500.png)

3. <span data-ttu-id="648e2-200">從快顯視窗中，選取下拉式功能表中的 [inaccuracy] 類別、填入您的電子郵件地址，以及有關 inaccuracy 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="648e2-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="648e2-201">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="648e2-201">Select **Submit**.</span></span> <span data-ttu-id="648e2-202">您的意見反應會立即傳送給威脅和弱點管理專家。</span><span class="sxs-lookup"><span data-stu-id="648e2-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="648e2-203">相關文章</span><span class="sxs-lookup"><span data-stu-id="648e2-203">Related articles</span></span>

- [<span data-ttu-id="648e2-204">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="648e2-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="648e2-205">儀表板</span><span class="sxs-lookup"><span data-stu-id="648e2-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="648e2-206">暴險分數</span><span class="sxs-lookup"><span data-stu-id="648e2-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="648e2-207">裝置用 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="648e2-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="648e2-208">修正安全性漏洞</span><span class="sxs-lookup"><span data-stu-id="648e2-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="648e2-209">建立及查看安全性建議的例外狀況</span><span class="sxs-lookup"><span data-stu-id="648e2-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="648e2-210">活動時間表</span><span class="sxs-lookup"><span data-stu-id="648e2-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
