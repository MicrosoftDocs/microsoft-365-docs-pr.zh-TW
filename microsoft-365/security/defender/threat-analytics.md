---
title: 使用威脅分析追蹤並回應新興威脅
ms.reviewer: ''
description: 深入瞭解新興的威脅和攻擊技巧，以及如何加以阻止。 評估其對您組織的影響，並評估您的組織恢復能力。
keywords: 威脅分析、風險評估、Microsoft 365 Defender、M365D、緩解狀態、安全設定、microsoft defender Office 365、microsoft defender Office 365 威脅分析、MDO 威脅分析、整合的 MDE 和 MDO 威脅分析資料、威脅分析資料整合、整合式 Microsoft 365 Defender 威脅分析
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a6de0cb646eb8c12e4863facdb42c1f9494120f9
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105653"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="39944-105">使用威脅分析追蹤並回應新興威脅</span><span class="sxs-lookup"><span data-stu-id="39944-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="39944-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="39944-106">**Applies to:**</span></span>
- <span data-ttu-id="39944-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39944-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="39944-108">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="39944-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="39944-109">您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="39944-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]


<span data-ttu-id="39944-110">威脅分析是來自專家 Microsoft 安全性調查的產品威脅情報解決方案，其設計目的是為了協助安全性小組盡可能有效地應對新興威脅，包括：</span><span class="sxs-lookup"><span data-stu-id="39944-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="39944-111">作用中的威脅演員及其活動</span><span class="sxs-lookup"><span data-stu-id="39944-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="39944-112">常見和新的攻擊技術</span><span class="sxs-lookup"><span data-stu-id="39944-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="39944-113">嚴重弱點</span><span class="sxs-lookup"><span data-stu-id="39944-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="39944-114">常見的攻擊面</span><span class="sxs-lookup"><span data-stu-id="39944-114">Common attack surfaces</span></span>
- <span data-ttu-id="39944-115">流行惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="39944-115">Prevalent malware</span></span>

<span data-ttu-id="39944-116">請觀看這段簡短的影片，深入瞭解威脅分析如何協助您追蹤最新的威脅並加以停止。</span><span class="sxs-lookup"><span data-stu-id="39944-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="39944-117">您可以從 Microsoft 365 安全性入口網站導覽列的左上方或專用的儀表板卡，存取威脅分析，以顯示您組織中的主要威脅。深入瞭解使用中或持續進行的行銷活動，並瞭解透過威脅分析所進行的工作，可協助您瞭解安全性運作小組的決策。</span><span class="sxs-lookup"><span data-stu-id="39944-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![威脅分析儀表板的影像](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="39944-119">_在何處存取威脅分析_</span><span class="sxs-lookup"><span data-stu-id="39944-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="39944-120">透過經常和 prevalently 的複雜敵人和新威脅，您可以快速：</span><span class="sxs-lookup"><span data-stu-id="39944-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="39944-121">識別並應對新興威脅</span><span class="sxs-lookup"><span data-stu-id="39944-121">Identify and react to emerging threats</span></span> 
- <span data-ttu-id="39944-122">瞭解您目前是否受到攻擊</span><span class="sxs-lookup"><span data-stu-id="39944-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="39944-123">評估對資產的威脅影響</span><span class="sxs-lookup"><span data-stu-id="39944-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="39944-124">檢查威脅的復原能力或洩密</span><span class="sxs-lookup"><span data-stu-id="39944-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="39944-125">識別您可以採取以停止或包含威脅的緩解、修復或防護動作</span><span class="sxs-lookup"><span data-stu-id="39944-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="39944-126">每個報告都提供有關如何抵禦威脅之追蹤威脅和大量指導的分析。</span><span class="sxs-lookup"><span data-stu-id="39944-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="39944-127">它也會整合您網路的資料，指出威脅是否作用中，以及您是否有適當的保護。</span><span class="sxs-lookup"><span data-stu-id="39944-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="39944-128">查看威脅分析儀表板</span><span class="sxs-lookup"><span data-stu-id="39944-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="39944-129">「威脅分析」儀表板 ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) 會強調最適合您組織的報表。</span><span class="sxs-lookup"><span data-stu-id="39944-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="39944-130">它會摘要說明下列各節中的威脅：</span><span class="sxs-lookup"><span data-stu-id="39944-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="39944-131">**最新威脅**-列出最近發行或更新的威脅報告，以及作用中和已解決的提醒數目。</span><span class="sxs-lookup"><span data-stu-id="39944-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="39944-132">**高影響威脅**-列出對您的組織具有最高影響的威脅。</span><span class="sxs-lookup"><span data-stu-id="39944-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="39944-133">本節會列出最高作用中且已解析之警示數目上限的威脅。</span><span class="sxs-lookup"><span data-stu-id="39944-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="39944-134">**威脅摘要**—顯示所有追蹤威脅的整體影響，只要顯示使用中及已解決之警示的威脅數目。</span><span class="sxs-lookup"><span data-stu-id="39944-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="39944-135">從儀表板選取威脅，以查看該威脅的報告。</span><span class="sxs-lookup"><span data-stu-id="39944-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![威脅分析儀表板的螢幕擷取畫面](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="39944-137">_威脅分析儀表板。您也可以在與您想要讀取之威脅分析報告相關的關鍵字中，按一下 [搜尋] 圖示。_</span><span class="sxs-lookup"><span data-stu-id="39944-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="39944-138">查看威脅分析報告</span><span class="sxs-lookup"><span data-stu-id="39944-138">View a threat analytics report</span></span>

<span data-ttu-id="39944-139">每個威脅分析報告都提供若干區段中的資訊：</span><span class="sxs-lookup"><span data-stu-id="39944-139">Each threat analytics report provides information in several sections:</span></span> 

- [<span data-ttu-id="39944-140">**概觀**</span><span class="sxs-lookup"><span data-stu-id="39944-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses) 
- [<span data-ttu-id="39944-141">**分析報告**</span><span class="sxs-lookup"><span data-stu-id="39944-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="39944-142">**相關的事件**</span><span class="sxs-lookup"><span data-stu-id="39944-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="39944-143">**受影響資產**</span><span class="sxs-lookup"><span data-stu-id="39944-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="39944-144">**禁止電子郵件嘗試**</span><span class="sxs-lookup"><span data-stu-id="39944-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="39944-145">**減輕方式**</span><span class="sxs-lookup"><span data-stu-id="39944-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="39944-146">概覽：快速瞭解威脅、評估其影響，以及複查防護</span><span class="sxs-lookup"><span data-stu-id="39944-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="39944-147">[ **一覽表** ] 區段提供詳細分析報告的預覽。</span><span class="sxs-lookup"><span data-stu-id="39944-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="39944-148">它還提供圖表，以強調您的組織面臨的威脅影響，以及透過誤設定及未修補的裝置來公開。</span><span class="sxs-lookup"><span data-stu-id="39944-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![威脅分析報告之 [一覽] 區段的影像](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="39944-150">_威脅分析報告的一覽區段_</span><span class="sxs-lookup"><span data-stu-id="39944-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="39944-151">評估組織的影響</span><span class="sxs-lookup"><span data-stu-id="39944-151">Assess impact on your organization</span></span>
<span data-ttu-id="39944-152">每個報告都包含設計用來提供威脅之組織影響的資訊的圖表：</span><span class="sxs-lookup"><span data-stu-id="39944-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="39944-153">**相關事件**--透過下列資料，提供對組織之追蹤威脅影響的概覽：</span><span class="sxs-lookup"><span data-stu-id="39944-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="39944-154">作用中警示的數目，以及與其相關聯的主動事件數目</span><span class="sxs-lookup"><span data-stu-id="39944-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="39944-155">主動事件的嚴重性</span><span class="sxs-lookup"><span data-stu-id="39944-155">Severity of active incidents</span></span>
- <span data-ttu-id="39944-156">**隨時間的提醒**-顯示一段時間內 **的相關作用** 中和 **已解決** 的警示數目。</span><span class="sxs-lookup"><span data-stu-id="39944-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="39944-157">已解決的警示數目會指出組織對與威脅相關聯的提醒回應的快慢程度。</span><span class="sxs-lookup"><span data-stu-id="39944-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="39944-158">理想狀況下，圖表應該會顯示幾天內所解決的警示。</span><span class="sxs-lookup"><span data-stu-id="39944-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="39944-159">**受影響的資產**-顯示目前至少有一個與追蹤威脅相關聯之主動警示的不同裝置和電子郵件帳戶的數量 (信箱) 。</span><span class="sxs-lookup"><span data-stu-id="39944-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="39944-160">會針對接收到威脅電子郵件的信箱觸發警示。</span><span class="sxs-lookup"><span data-stu-id="39944-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="39944-161">回顧組織和使用者層級原則，以進行導致威脅電子郵件傳送的覆寫。</span><span class="sxs-lookup"><span data-stu-id="39944-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="39944-162">**禁止電子郵件嘗試**—顯示過去七天內已封鎖或傳送至 [垃圾郵件] 資料夾之前封鎖的電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="39944-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="39944-163">檢查安全性恢復能力與狀況</span><span class="sxs-lookup"><span data-stu-id="39944-163">Review security resilience and posture</span></span>
<span data-ttu-id="39944-164">每個報告都包含的圖表，可提供您的組織對特定威脅的彈性程度。</span><span class="sxs-lookup"><span data-stu-id="39944-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="39944-165">**安全設定狀態**-顯示設定不當的安全性設定裝置數目。</span><span class="sxs-lookup"><span data-stu-id="39944-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="39944-166">套用建議的安全性設定，以協助緩解威脅。</span><span class="sxs-lookup"><span data-stu-id="39944-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="39944-167">如果裝置已套用 _所有_ 追蹤的設定，則會被視為 **安全** 裝置。</span><span class="sxs-lookup"><span data-stu-id="39944-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="39944-168">**弱點修補狀態**-顯示有缺陷裝置的數目。</span><span class="sxs-lookup"><span data-stu-id="39944-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="39944-169">套用安全性更新或修補程式，以解決威脅所利用的漏洞。</span><span class="sxs-lookup"><span data-stu-id="39944-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="39944-170">分析報告：從 Microsoft security 研究員取得專家洞察力</span><span class="sxs-lookup"><span data-stu-id="39944-170">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="39944-171">在 [ **分析報告** ] 區段中，閱讀詳細的專家撰寫。</span><span class="sxs-lookup"><span data-stu-id="39944-171">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="39944-172">大多數報告提供攻擊鏈的詳細描述，包含對應至 MITRE ATT 的戰術和技術&CK 架構、詳盡的建議清單，以及強大的 [威脅搜尋](advanced-hunting-overview.md) 指導方針。</span><span class="sxs-lookup"><span data-stu-id="39944-172">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="39944-173">深入瞭解分析報告</span><span class="sxs-lookup"><span data-stu-id="39944-173">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="39944-174">相關的事件：查看及管理相關的事件</span><span class="sxs-lookup"><span data-stu-id="39944-174">Related incidents: View and manage related incidents</span></span>
<span data-ttu-id="39944-175">[ **相關事件** ] 索引標籤會提供與追蹤威脅相關的所有事件清單。</span><span class="sxs-lookup"><span data-stu-id="39944-175">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="39944-176">您可以指派事件或管理連結至每個事件的警示。</span><span class="sxs-lookup"><span data-stu-id="39944-176">You can assign incidents or manage alerts linked to each incident.</span></span> 

![威脅分析報告之相關事件區段的影像](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="39944-178">_威脅分析報告的相關事件區段_</span><span class="sxs-lookup"><span data-stu-id="39944-178">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="39944-179">受影響的資產：取得受影響的裝置和信箱清單</span><span class="sxs-lookup"><span data-stu-id="39944-179">Impacted assets: Get list of impacted devices and mailboxes</span></span>
<span data-ttu-id="39944-180">如果資產受到作用中未解析的警示影響，便會視為受影響的資產。</span><span class="sxs-lookup"><span data-stu-id="39944-180">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="39944-181">[ **受影響的資產** ] 索引標籤會列出下列受影響的資產類型：</span><span class="sxs-lookup"><span data-stu-id="39944-181">The **Impacted assets** tab lists the following types of impacted assets:</span></span>
- <span data-ttu-id="39944-182">**受影響的裝置**—具有未解析之 Microsoft Defender for Endpoint 警示的端點。</span><span class="sxs-lookup"><span data-stu-id="39944-182">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="39944-183">這些警示通常會引發 sightings 已知威脅指示器和活動。</span><span class="sxs-lookup"><span data-stu-id="39944-183">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="39944-184">**受影響的信箱**：已接收的電子郵件已觸發 Microsoft Defender 以 Office 365 警示的信箱。</span><span class="sxs-lookup"><span data-stu-id="39944-184">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="39944-185">雖然通常會封鎖觸發提醒的郵件，但使用者或組織層級原則也可以覆寫篩選器。</span><span class="sxs-lookup"><span data-stu-id="39944-185">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![威脅分析報告中「受影響的資產」區段的影像](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="39944-187">_威脅分析報告的「受影響的資產」區段_</span><span class="sxs-lookup"><span data-stu-id="39944-187">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="39944-188">禁止電子郵件企圖：查看封鎖或 junked 威脅電子郵件</span><span class="sxs-lookup"><span data-stu-id="39944-188">Prevented email attempts: View blocked or junked threat emails</span></span>
<span data-ttu-id="39944-189">Microsoft Defender for Office 365 通常會封鎖具有已知威脅指示器的電子郵件，包括惡意連結或附件。</span><span class="sxs-lookup"><span data-stu-id="39944-189">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="39944-190">在某些情況下，檢查可疑內容的前瞻性篩選機制，會改為將威脅電子郵件傳送至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="39944-190">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="39944-191">在任何情況下，在裝置上發動惡意程式碼碼威脅的機率都會降低。</span><span class="sxs-lookup"><span data-stu-id="39944-191">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="39944-192">「**防止的電子郵件嘗試**」索引標籤會列出所有已封鎖的電子郵件，再傳送或傳送至 Microsoft Defender for Office 365 的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="39944-192">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![威脅分析報告中「禁止的電子郵件嘗試」區段的影像](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="39944-194">_威脅分析報告的 [防止電子郵件嘗試] 區段_</span><span class="sxs-lookup"><span data-stu-id="39944-194">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="39944-195">緩解：查看緩解清單和裝置狀態</span><span class="sxs-lookup"><span data-stu-id="39944-195">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="39944-196">在 [ **緩解** ] 區段中，複查可協助您增加組織對威脅抵禦能力的特定可行動建議清單。</span><span class="sxs-lookup"><span data-stu-id="39944-196">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="39944-197">追蹤的緩解措施清單包括：</span><span class="sxs-lookup"><span data-stu-id="39944-197">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="39944-198">**安全性更新**-針對架裝置上的漏洞，部署支援的軟體安全性更新</span><span class="sxs-lookup"><span data-stu-id="39944-198">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="39944-199">**支援的安全性設定**</span><span class="sxs-lookup"><span data-stu-id="39944-199">**Supported security configurations**</span></span>
  - <span data-ttu-id="39944-200">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="39944-200">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="39944-201">可能有害的應用程式 (PUA) 保護</span><span class="sxs-lookup"><span data-stu-id="39944-201">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="39944-202">即時保護</span><span class="sxs-lookup"><span data-stu-id="39944-202">Real-time protection</span></span>
 
<span data-ttu-id="39944-203">本節中的緩解資訊包含來自[威脅與弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的資料，也就是從報告中各種連結提供的詳細深入資訊。</span><span class="sxs-lookup"><span data-stu-id="39944-203">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="39944-204">![顯示 ](../../media/threat-analytics/ta_mitigations_mtp.png)
 ![ 弱點詳細資料之威脅分析報告之「緩解」區段之 [安全設定詳細資料] 的 [威脅分析] 區段的 [緩解] 區段的影像](../../media/threat-analytics/ta_mitigations_mtp2.png)</span><span class="sxs-lookup"><span data-stu-id="39944-204">![Image of the mitigations section of a threat analytics report showing secure configuration details](../../media/threat-analytics/ta_mitigations_mtp.png)
![Image of the mitigations section of a threat analytics report showing vulnerability details](../../media/threat-analytics/ta_mitigations_mtp2.png)</span></span>

<span data-ttu-id="39944-205">_威脅分析報告的緩解區段_</span><span class="sxs-lookup"><span data-stu-id="39944-205">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="39944-206">其他報告詳細資料與限制</span><span class="sxs-lookup"><span data-stu-id="39944-206">Additional report details and limitations</span></span>
>[!NOTE]
><span data-ttu-id="39944-207">在統一的安全性體驗中，威脅分析現在不僅適用于 microsoft defender for Endpoint，也適用于 microsoft defender 的 Office E5 授權擁有者。</span><span class="sxs-lookup"><span data-stu-id="39944-207">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
><span data-ttu-id="39944-208">如果您未使用 Microsoft 365 安全性入口網站 (Microsoft 365 Defender) ，您也可以在 (入口網站 Office microsoft defender for Endpoint) 中，查看不含 Microsoft defender Microsoft Defender 資訊安全中心資料 (的報告詳細資料。</span><span class="sxs-lookup"><span data-stu-id="39944-208">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span> 

<span data-ttu-id="39944-209">若要存取威脅分析報告，您需要特定的角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="39944-209">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="39944-210">如需詳細資訊，請參閱[Microsoft 365 Defender 角色型存取控制中的自訂角色](custom-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="39944-210">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>
  - <span data-ttu-id="39944-211">若要查看警示、事件或受影響的資產資料，您必須具有 microsoft defender for Office 或 microsoft defender for Endpoint 警示資料，或兩者的許可權。</span><span class="sxs-lookup"><span data-stu-id="39944-211">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
  - <span data-ttu-id="39944-212">若要查看已禁止的電子郵件嘗試，您必須具有 Microsoft Defender 的許可權，才能 Office 搜尋資料。</span><span class="sxs-lookup"><span data-stu-id="39944-212">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
  - <span data-ttu-id="39944-213">若要查看緩解，您必須具有在 Microsoft Defender for Endpoint 中威脅與弱點管理資料的許可權。</span><span class="sxs-lookup"><span data-stu-id="39944-213">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="39944-214">在查看威脅分析資料時，請記住下列因素：</span><span class="sxs-lookup"><span data-stu-id="39944-214">When looking at the threat analytics data, remember the following factors:</span></span>
- <span data-ttu-id="39944-215">圖表只會反映所追蹤的緩解。</span><span class="sxs-lookup"><span data-stu-id="39944-215">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="39944-216">請查看報告中未顯示圖表的其他緩解。</span><span class="sxs-lookup"><span data-stu-id="39944-216">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="39944-217">緩解不會保證完全恢復。</span><span class="sxs-lookup"><span data-stu-id="39944-217">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="39944-218">提供的緩解反映改進恢復所需的最佳動作。</span><span class="sxs-lookup"><span data-stu-id="39944-218">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="39944-219">如果裝置未將資料傳輸至服務，則會將裝置計為「無法使用」。</span><span class="sxs-lookup"><span data-stu-id="39944-219">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="39944-220">防病毒相關的統計資料是以 Microsoft Defender 防毒軟體設定為基礎。</span><span class="sxs-lookup"><span data-stu-id="39944-220">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="39944-221">使用協力廠商防病毒解決方案的裝置可能會顯示為「已公開」。</span><span class="sxs-lookup"><span data-stu-id="39944-221">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="39944-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="39944-222">Related topics</span></span>
- [<span data-ttu-id="39944-223">使用高級搜尋主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="39944-223">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="39944-224">瞭解分析報告區段</span><span class="sxs-lookup"><span data-stu-id="39944-224">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="39944-225">評估並解決安全弱點與洩密問題</span><span class="sxs-lookup"><span data-stu-id="39944-225">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
