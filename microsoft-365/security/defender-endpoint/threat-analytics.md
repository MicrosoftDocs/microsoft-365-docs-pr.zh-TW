---
title: 使用 Microsoft Defender for Endpoint 威脅分析追蹤和回應新興威脅
ms.reviewer: ''
description: 深入瞭解新興威脅和攻擊技巧，以及如何停止它們。 評估其對您組織的影響，並評估您的組織恢復能力。
keywords: 威脅分析、風險評估、OS 緩解、微碼緩解、緩解狀態
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 63303f9eacd25a8de1c7154ac66c73578bfd495a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924452"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a><span data-ttu-id="57aa2-105">透過威脅分析追蹤並回應新興威脅</span><span class="sxs-lookup"><span data-stu-id="57aa2-105">Track and respond to emerging threats through threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="57aa2-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="57aa2-106">**Applies to:**</span></span>
- [<span data-ttu-id="57aa2-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="57aa2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="57aa2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57aa2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="57aa2-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="57aa2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57aa2-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="57aa2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="57aa2-111">透過經常和 prevalently 的複雜敵人和新威脅，您可以快速：</span><span class="sxs-lookup"><span data-stu-id="57aa2-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="57aa2-112">評估新威脅的影響</span><span class="sxs-lookup"><span data-stu-id="57aa2-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="57aa2-113">檢查威脅的復原能力或洩密</span><span class="sxs-lookup"><span data-stu-id="57aa2-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="57aa2-114">識別您可以採取以停止或包含威脅的動作</span><span class="sxs-lookup"><span data-stu-id="57aa2-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="57aa2-115">威脅分析是一組來自專家 Microsoft security 研究員的報表，涵蓋最相關的威脅，包括：</span><span class="sxs-lookup"><span data-stu-id="57aa2-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="57aa2-116">作用中的威脅演員及其活動</span><span class="sxs-lookup"><span data-stu-id="57aa2-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="57aa2-117">常見和新的攻擊技術</span><span class="sxs-lookup"><span data-stu-id="57aa2-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="57aa2-118">嚴重弱點</span><span class="sxs-lookup"><span data-stu-id="57aa2-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="57aa2-119">常見的攻擊面</span><span class="sxs-lookup"><span data-stu-id="57aa2-119">Common attack surfaces</span></span>
- <span data-ttu-id="57aa2-120">流行惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="57aa2-120">Prevalent malware</span></span>

<span data-ttu-id="57aa2-121">每個報告都提供有關如何防範該威脅的詳細分析威脅和大量指導方針。</span><span class="sxs-lookup"><span data-stu-id="57aa2-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="57aa2-122">它也會整合您網路的資料，指出威脅是否作用中，以及您是否有適當的保護。</span><span class="sxs-lookup"><span data-stu-id="57aa2-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="57aa2-123">請觀看這段簡短的影片，深入瞭解威脅分析如何協助您追蹤最新的威脅並加以停止。</span><span class="sxs-lookup"><span data-stu-id="57aa2-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="57aa2-124">查看威脅分析儀表板</span><span class="sxs-lookup"><span data-stu-id="57aa2-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="57aa2-125">「威脅分析」儀表板是一種非常棒的跳離點，可取得與貴組織最相關的報告。</span><span class="sxs-lookup"><span data-stu-id="57aa2-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="57aa2-126">它會摘要說明下列各節中的威脅：</span><span class="sxs-lookup"><span data-stu-id="57aa2-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="57aa2-127">**最新威脅**-列出最近發佈的威脅報告，以及具有作用中及已解決之警示的裝置數目。</span><span class="sxs-lookup"><span data-stu-id="57aa2-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="57aa2-128">**高影響威脅**-列出對組織具有最高影響的威脅。</span><span class="sxs-lookup"><span data-stu-id="57aa2-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="57aa2-129">本節依照具有作用中警示的裝置數目來排名威脅。</span><span class="sxs-lookup"><span data-stu-id="57aa2-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="57aa2-130">**威脅摘要**-顯示追蹤威脅的整體影響，方法是顯示具有作用中及已解決之警示的威脅數目。</span><span class="sxs-lookup"><span data-stu-id="57aa2-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="57aa2-131">從儀表板選取威脅，以查看該威脅的報告。</span><span class="sxs-lookup"><span data-stu-id="57aa2-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![威脅分析儀表板的影像](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="57aa2-133">查看威脅分析報告</span><span class="sxs-lookup"><span data-stu-id="57aa2-133">View a threat analytics report</span></span>

<span data-ttu-id="57aa2-134">每個威脅分析報告都提供三個區段中的資訊： **綜述**、 **分析員報告** 及 **緩解**。</span><span class="sxs-lookup"><span data-stu-id="57aa2-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="57aa2-135">概覽：快速瞭解威脅、評估其影響，以及複查防護</span><span class="sxs-lookup"><span data-stu-id="57aa2-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="57aa2-136">[ **一覽表** ] 區段提供詳細分析報告的預覽。</span><span class="sxs-lookup"><span data-stu-id="57aa2-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="57aa2-137">它還提供圖表，以強調您的組織面臨的威脅影響，以及透過誤設定及未修補的裝置來公開。</span><span class="sxs-lookup"><span data-stu-id="57aa2-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="57aa2-138">![威脅分析報告的 [威脅分析報告] 區段中的 [一覽] 區段的影像 ](images/ta-overview.png)
 </span><span class="sxs-lookup"><span data-stu-id="57aa2-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="57aa2-139">評估組織的影響</span><span class="sxs-lookup"><span data-stu-id="57aa2-139">Assess the impact to your organization</span></span>
<span data-ttu-id="57aa2-140">每個報告都包含設計用來提供威脅之組織影響的資訊的圖表：</span><span class="sxs-lookup"><span data-stu-id="57aa2-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="57aa2-141">**含警示的裝置**—顯示受到威脅影響之不同裝置的目前數目。</span><span class="sxs-lookup"><span data-stu-id="57aa2-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="57aa2-142">如果有至少一個警示與該威脅相關聯 **，且已** 解決與裝置上的威脅相關的 *所有* 警示，則此裝置會 **分類為作用** 中。</span><span class="sxs-lookup"><span data-stu-id="57aa2-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="57aa2-143">**隨時間變化的裝置**—顯示一段時間內具有作用中和 **已解決** 之 **警示的不同** 裝置數目。</span><span class="sxs-lookup"><span data-stu-id="57aa2-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="57aa2-144">已解決的警示數目會指出組織對與威脅相關聯的提醒回應的快慢程度。</span><span class="sxs-lookup"><span data-stu-id="57aa2-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="57aa2-145">理想狀況下，圖表應該會顯示幾天內所解決的警示。</span><span class="sxs-lookup"><span data-stu-id="57aa2-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="57aa2-146">檢查安全性恢復能力與狀況</span><span class="sxs-lookup"><span data-stu-id="57aa2-146">Review security resilience and posture</span></span>
<span data-ttu-id="57aa2-147">每個報告都包含的圖表，可提供您的組織對特定威脅的彈性程度。</span><span class="sxs-lookup"><span data-stu-id="57aa2-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="57aa2-148">**安全性設定狀態**-顯示已套用建議安全性設定，以協助緩解威脅的裝置數目。</span><span class="sxs-lookup"><span data-stu-id="57aa2-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="57aa2-149">如果裝置已套用 _所有_ 追蹤的設定，則會被視為 **安全** 裝置。</span><span class="sxs-lookup"><span data-stu-id="57aa2-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="57aa2-150">**弱點修補狀態**-顯示已套用安全性更新的裝置數目，或修復威脅所利用之弱點的修補程式。</span><span class="sxs-lookup"><span data-stu-id="57aa2-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="57aa2-151">分析報告：從 Microsoft security 研究員取得專家洞察力</span><span class="sxs-lookup"><span data-stu-id="57aa2-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="57aa2-152">請移至 [ **分析報告** ] 區段，以閱讀詳細的專家級寫功能。</span><span class="sxs-lookup"><span data-stu-id="57aa2-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="57aa2-153">大多數報告提供攻擊鏈的詳細描述，包含對應至 MITRE ATT 的戰術和技術&CK 架構、詳盡的建議清單，以及強大的 [威脅搜尋](advanced-hunting-overview.md) 指導方針。</span><span class="sxs-lookup"><span data-stu-id="57aa2-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="57aa2-154">深入瞭解分析報告</span><span class="sxs-lookup"><span data-stu-id="57aa2-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="57aa2-155">緩解：查看緩解清單和裝置狀態</span><span class="sxs-lookup"><span data-stu-id="57aa2-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="57aa2-156">在 [ **緩解** ] 區段中，複查可協助您增加組織對威脅抵禦能力的特定可行動建議清單。</span><span class="sxs-lookup"><span data-stu-id="57aa2-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="57aa2-157">追蹤的緩解措施清單包括：</span><span class="sxs-lookup"><span data-stu-id="57aa2-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="57aa2-158">**安全性更新**—部署弱點的安全性更新或修補程式</span><span class="sxs-lookup"><span data-stu-id="57aa2-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="57aa2-159">**Microsoft Defender 防毒軟體設定**</span><span class="sxs-lookup"><span data-stu-id="57aa2-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="57aa2-160">安全性智慧版本</span><span class="sxs-lookup"><span data-stu-id="57aa2-160">Security intelligence version</span></span>
  - <span data-ttu-id="57aa2-161">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="57aa2-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="57aa2-162">可能有害的應用程式 (PUA) 保護</span><span class="sxs-lookup"><span data-stu-id="57aa2-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="57aa2-163">即時保護</span><span class="sxs-lookup"><span data-stu-id="57aa2-163">Real-time protection</span></span>
 
<span data-ttu-id="57aa2-164">本節中的緩解資訊包含來自[威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)的資料，也就是從報告中各種連結提供的詳細深入資訊。</span><span class="sxs-lookup"><span data-stu-id="57aa2-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="57aa2-165">![威脅分析報告「威脅分析報告 ](images/ta-mitigations.png)
 _緩解」區段_ 之 [緩解] 區段的影像</span><span class="sxs-lookup"><span data-stu-id="57aa2-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="57aa2-166">其他報告詳細資料與限制</span><span class="sxs-lookup"><span data-stu-id="57aa2-166">Additional report details and limitations</span></span>
<span data-ttu-id="57aa2-167">使用報表時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="57aa2-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="57aa2-168">資料的範圍取決於您以角色為基礎的存取控制 (RBAC) 範圍。</span><span class="sxs-lookup"><span data-stu-id="57aa2-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="57aa2-169">您將會看到 [您可以存取之群組](machine-groups.md)中的裝置狀態。</span><span class="sxs-lookup"><span data-stu-id="57aa2-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="57aa2-170">圖表只會反映所追蹤的緩解。</span><span class="sxs-lookup"><span data-stu-id="57aa2-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="57aa2-171">請查看報告中未顯示圖表的其他緩解。</span><span class="sxs-lookup"><span data-stu-id="57aa2-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="57aa2-172">緩解不會保證完全恢復。</span><span class="sxs-lookup"><span data-stu-id="57aa2-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="57aa2-173">提供的緩解反映改進恢復所需的最佳動作。</span><span class="sxs-lookup"><span data-stu-id="57aa2-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="57aa2-174">如果裝置未將資料傳輸至服務，則會將裝置計為「無法使用」。</span><span class="sxs-lookup"><span data-stu-id="57aa2-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="57aa2-175">防病毒相關的統計資料是以 Microsoft Defender 防毒軟體設定為基礎。</span><span class="sxs-lookup"><span data-stu-id="57aa2-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="57aa2-176">使用協力廠商防病毒解決方案的裝置可能會顯示為「已公開」。</span><span class="sxs-lookup"><span data-stu-id="57aa2-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="57aa2-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="57aa2-177">Related topics</span></span>
- [<span data-ttu-id="57aa2-178">使用高級搜尋主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="57aa2-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="57aa2-179">瞭解分析報告區段</span><span class="sxs-lookup"><span data-stu-id="57aa2-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="57aa2-180">評估並解決安全弱點與洩密問題</span><span class="sxs-lookup"><span data-stu-id="57aa2-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)
