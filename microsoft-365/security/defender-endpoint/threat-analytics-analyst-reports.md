---
title: 瞭解威脅分析中的分析報告區段
ms.reviewer: ''
description: 深入瞭解每個威脅分析報告的分析報告區段。 瞭解它如何提供威脅、緩解、偵測、高級搜尋查詢等相關資訊。
keywords: 分析報告、威脅分析、偵測、高級搜尋查詢、緩解
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6529f0badd94d6ca4d95dfbb562a9d352fedb76a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935890"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a><span data-ttu-id="a17b2-105">瞭解威脅分析中的分析報告</span><span class="sxs-lookup"><span data-stu-id="a17b2-105">Understand the analyst report in threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a17b2-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a17b2-106">**Applies to:**</span></span>
- [<span data-ttu-id="a17b2-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a17b2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a17b2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a17b2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a17b2-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="a17b2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a17b2-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a17b2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a17b2-111">每個 [威脅分析報告](threat-analytics.md) 都包含動態區段，以及一個稱為「 _分析員報告_」的完整寫入章節。</span><span class="sxs-lookup"><span data-stu-id="a17b2-111">Each [threat analytics report](threat-analytics.md) includes dynamic sections and a comprehensive written section called the _analyst report_.</span></span> <span data-ttu-id="a17b2-112">若要存取此區段，開啟有關追蹤威脅的報告，然後選取 [ **分析報告** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a17b2-112">To access this section, open the report about the tracked threat and select the **Analyst report** tab.</span></span>

![威脅分析報告的分析報告區段影像](images/ta-analyst-report-small.png)

<span data-ttu-id="a17b2-114">_威脅分析報告的分析報告區段_</span><span class="sxs-lookup"><span data-stu-id="a17b2-114">_Analyst report section of a threat analytics report_</span></span>

## <a name="scan-the-analyst-report"></a><span data-ttu-id="a17b2-115">掃描分析報告</span><span class="sxs-lookup"><span data-stu-id="a17b2-115">Scan the analyst report</span></span> 
<span data-ttu-id="a17b2-116">分析報告的每一節都是用來提供可行動的資訊。</span><span class="sxs-lookup"><span data-stu-id="a17b2-116">Each section of the analyst report is designed to provide actionable information.</span></span> <span data-ttu-id="a17b2-117">當報表變化時，大部分的報表會包含下表所述的區段。</span><span class="sxs-lookup"><span data-stu-id="a17b2-117">While reports vary, most reports include the sections described in the following table.</span></span>

| <span data-ttu-id="a17b2-118">報表區段</span><span class="sxs-lookup"><span data-stu-id="a17b2-118">Report section</span></span> | <span data-ttu-id="a17b2-119">描述</span><span class="sxs-lookup"><span data-stu-id="a17b2-119">Description</span></span> |
|--|--|
| <span data-ttu-id="a17b2-120">摘要</span><span class="sxs-lookup"><span data-stu-id="a17b2-120">Executive summary</span></span> | <span data-ttu-id="a17b2-121">威脅的概述，包括初次看到的時間、其動機、明確的事件、主要目標，以及不同的工具和技術。</span><span class="sxs-lookup"><span data-stu-id="a17b2-121">Overview of the threat, including when it was first seen, its motivations, notable events, major targets, and distinct tools and techniques.</span></span> <span data-ttu-id="a17b2-122">您可以使用此資訊來進一步評估如何在您的行業、地理位置和網路內容中排定威脅的優先順序。</span><span class="sxs-lookup"><span data-stu-id="a17b2-122">You can use this information to further assess how to prioritize the threat in the context of your industry, geographic location, and network.</span></span> |
| <span data-ttu-id="a17b2-123">分析</span><span class="sxs-lookup"><span data-stu-id="a17b2-123">Analysis</span></span> | <span data-ttu-id="a17b2-124">威脅的技術資訊，包括攻擊的詳細資料，以及攻擊者可能使用新技術或攻擊面的方式</span><span class="sxs-lookup"><span data-stu-id="a17b2-124">Technical information about the threats, including the details of an attack and how attackers might utilize a new technique or attack surface</span></span> | 
| <span data-ttu-id="a17b2-125">MITRE ATT&所觀察到的 CK 技術</span><span class="sxs-lookup"><span data-stu-id="a17b2-125">MITRE ATT&CK techniques observed</span></span> | <span data-ttu-id="a17b2-126">觀察到的技巧如何對應至 [MITRE ATT&CK 攻擊架構](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="a17b2-126">How observed techniques map to the [MITRE ATT&CK attack framework](https://attack.mitre.org/)</span></span> | 
| [<span data-ttu-id="a17b2-127">減輕方式</span><span class="sxs-lookup"><span data-stu-id="a17b2-127">Mitigations</span></span>](#apply-additional-mitigations) | <span data-ttu-id="a17b2-128">可停止或協助減少威脅影響的建議。</span><span class="sxs-lookup"><span data-stu-id="a17b2-128">Recommendations that can stop or help reduce the impact of the threat.</span></span> <span data-ttu-id="a17b2-129">本節也包含不會在威脅分析報告中動態追蹤的緩解。</span><span class="sxs-lookup"><span data-stu-id="a17b2-129">This section also includes mitigations that aren't tracked dynamically as part of the threat analytics report.</span></span> |
| [<span data-ttu-id="a17b2-130">偵測詳細資料</span><span class="sxs-lookup"><span data-stu-id="a17b2-130">Detection details</span></span>](#understand-how-each-threat-can-be-detected) | <span data-ttu-id="a17b2-131">Microsoft 安全性解決方案所提供的特定及一般偵測，可以呈現與威脅相關聯的活動或元件。</span><span class="sxs-lookup"><span data-stu-id="a17b2-131">Specific and generic detections provided by Microsoft security solutions that can surface activity or components associated with the threat.</span></span> | 
| [<span data-ttu-id="a17b2-132">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="a17b2-132">Advanced hunting</span></span>](#find-subtle-threat-artifacts-using-advanced-hunting) | <span data-ttu-id="a17b2-133">以主動識別可能威脅活動的[高級搜尋查詢](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a17b2-133">[Advanced hunting queries](advanced-hunting-overview.md) for proactively identifying possible threat activity.</span></span> <span data-ttu-id="a17b2-134">大部分的查詢都是為了補充偵測，特別是找出可能惡意的元件或無法動態評估以成為惡意的行為。</span><span class="sxs-lookup"><span data-stu-id="a17b2-134">Most queries are provided to supplement detections, especially for locating potentially malicious components or behaviors that couldn't be dynamically assessed to be malicious.</span></span> | 
| <span data-ttu-id="a17b2-135">參考</span><span class="sxs-lookup"><span data-stu-id="a17b2-135">References</span></span> | <span data-ttu-id="a17b2-136">在建立報告期間，由分析員參考的 Microsoft 和協力廠商出版物。</span><span class="sxs-lookup"><span data-stu-id="a17b2-136">Microsoft and third-party publications referenced by analysts during the creation of the report.</span></span> <span data-ttu-id="a17b2-137">威脅分析內容是以 Microsoft 研究員所驗證的資料為基礎。</span><span class="sxs-lookup"><span data-stu-id="a17b2-137">Threat analytics content is based on data validated by Microsoft researchers.</span></span> <span data-ttu-id="a17b2-138">公開提供的資訊，協力廠商來源會明確識別。</span><span class="sxs-lookup"><span data-stu-id="a17b2-138">Information from publicly available, third-party sources are identified clearly as such.</span></span> | 
| <span data-ttu-id="a17b2-139">變更記錄</span><span class="sxs-lookup"><span data-stu-id="a17b2-139">Change log</span></span> | <span data-ttu-id="a17b2-140">報告發布的時間，以及對報表進行重大變更的時間。</span><span class="sxs-lookup"><span data-stu-id="a17b2-140">The time the report was published and when significant changes were made to the report.</span></span> |

## <a name="apply-additional-mitigations"></a><span data-ttu-id="a17b2-141">套用其他緩解</span><span class="sxs-lookup"><span data-stu-id="a17b2-141">Apply additional mitigations</span></span>
<span data-ttu-id="a17b2-142">威脅分析會動態追蹤 [安全性更新和安全設定的狀態](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。</span><span class="sxs-lookup"><span data-stu-id="a17b2-142">Threat analytics dynamically tracks the [status of security updates and secure configurations](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices).</span></span> <span data-ttu-id="a17b2-143">在 [ **緩解** ] 索引標籤中，此資訊是以圖表和表格的形式提供。</span><span class="sxs-lookup"><span data-stu-id="a17b2-143">This information is available as charts and tables in the **Mitigations** tab.</span></span>

<span data-ttu-id="a17b2-144">除了這些追蹤的緩解措施之外，「分析員」報告也會討論 _未_ 動態監視的緩解。</span><span class="sxs-lookup"><span data-stu-id="a17b2-144">In addition to these tracked mitigations, the analyst report also discusses mitigations that are _not_ dynamically monitored.</span></span> <span data-ttu-id="a17b2-145">以下是一些不會動態追蹤之重要緩解事項的範例：</span><span class="sxs-lookup"><span data-stu-id="a17b2-145">Here are some examples of important mitigations that are not dynamically tracked:</span></span>

- <span data-ttu-id="a17b2-146">封鎖使用 _.lnk_ 附件或其他可疑檔案類型的電子郵件</span><span class="sxs-lookup"><span data-stu-id="a17b2-146">Block emails with _.lnk_ attachments or other suspicious file types</span></span>
- <span data-ttu-id="a17b2-147">隨機化本機系統管理員密碼</span><span class="sxs-lookup"><span data-stu-id="a17b2-147">Randomize local administrator passwords</span></span>
- <span data-ttu-id="a17b2-148">教育使用者有關網路釣魚電子郵件和其他威脅媒介的教育</span><span class="sxs-lookup"><span data-stu-id="a17b2-148">Educate end users about phishing email and other threat vectors</span></span>
- <span data-ttu-id="a17b2-149">開啟特定 [攻擊面減少規則](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="a17b2-149">Turn on specific [attack surface reduction rules](attack-surface-reduction.md)</span></span>

<span data-ttu-id="a17b2-150">雖然您可以使用 [ **緩解** ] 索引標籤，針對威脅評估安全性狀況，但這些建議可讓您採取額外步驟，以提升安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="a17b2-150">While you can use the **Mitigations** tab to assess your security posture against a threat, these recommendations let you take additional steps towards improving your security posture.</span></span> <span data-ttu-id="a17b2-151">請仔細閱讀分析報告中的所有緩解指導方針，並盡可能加以套用。</span><span class="sxs-lookup"><span data-stu-id="a17b2-151">Carefully read all the mitigation guidance in the analyst report and apply them whenever possible.</span></span>

## <a name="understand-how-each-threat-can-be-detected"></a><span data-ttu-id="a17b2-152">瞭解每個威脅的偵測方式</span><span class="sxs-lookup"><span data-stu-id="a17b2-152">Understand how each threat can be detected</span></span>
<span data-ttu-id="a17b2-153">分析報告也會提供 Microsoft Defender 針對端點防病毒和 _端點偵測的偵測，以及_ (EDR) 功能的回應。</span><span class="sxs-lookup"><span data-stu-id="a17b2-153">The analyst report also provides the detections from Microsoft Defender for Endpoint antivirus and _endpoint detection and response_ (EDR) capabilities.</span></span>

### <a name="antivirus-detections"></a><span data-ttu-id="a17b2-154">防病毒偵測</span><span class="sxs-lookup"><span data-stu-id="a17b2-154">Antivirus detections</span></span>
<span data-ttu-id="a17b2-155">在已開啟 [Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 功能的裝置上可以使用這些偵測。</span><span class="sxs-lookup"><span data-stu-id="a17b2-155">These detections are available on devices with [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) turned on.</span></span> <span data-ttu-id="a17b2-156">當這些偵測發生在已架至 Microsoft Defender for Endpoint 的裝置上時，也會觸發報告中的圖表，使其變亮。</span><span class="sxs-lookup"><span data-stu-id="a17b2-156">When these detections occur on devices that have been onboarded to Microsoft Defender for Endpoint, they also trigger alerts that light up the charts in the report.</span></span>

>[!NOTE]
><span data-ttu-id="a17b2-157">分析員報告也會列出 **一般性** 偵測，除了追蹤威脅特有的元件或行為之外，還可以識別範圍廣泛的威脅。</span><span class="sxs-lookup"><span data-stu-id="a17b2-157">The analyst report also lists **generic detections** that can identify a wide-range of threats, in addition to components or behaviors specific to the tracked threat.</span></span> <span data-ttu-id="a17b2-158">這些一般偵測不會反映在圖表中。</span><span class="sxs-lookup"><span data-stu-id="a17b2-158">These generic detections don't reflect in the charts.</span></span>

### <a name="endpoint-detection-and-response-edr-alerts"></a><span data-ttu-id="a17b2-159"> (EDR) 警示的端點偵測和回應</span><span class="sxs-lookup"><span data-stu-id="a17b2-159">Endpoint detection and response (EDR) alerts</span></span>
<span data-ttu-id="a17b2-160">在 [架至 Microsoft Defender For Endpoint 的裝置](onboard-configure.md)上會引發 EDR 警示。</span><span class="sxs-lookup"><span data-stu-id="a17b2-160">EDR alerts are raised for [devices onboarded to Microsoft Defender for Endpoint](onboard-configure.md).</span></span> <span data-ttu-id="a17b2-161">這些警示通常會依賴 Microsoft Defender for Endpoint 感應器所收集的安全性信號，以及可充當功能強大之信號來源的其他端點功能（例如防毒軟體、網路保護、防篡改保護）。</span><span class="sxs-lookup"><span data-stu-id="a17b2-161">These alerts generally rely on security signals collected by the Microsoft Defender for Endpoint sensor and other endpoint capabilities—such as antivirus, network protection, tamper protection—that serve as powerful signal sources.</span></span>

<span data-ttu-id="a17b2-162">如防病毒偵測清單所設計，有些 EDR 警示是設計為一般標記可能不會與追蹤威脅相關聯的可疑行為。</span><span class="sxs-lookup"><span data-stu-id="a17b2-162">Like the list of antivirus detections, some EDR alerts are designed to generically flag suspicious behavior that might not be associated with the tracked threat.</span></span> <span data-ttu-id="a17b2-163">在這種情況下，報告會將警示明確識別為「一般」，而不會影響報表中的任何圖表。</span><span class="sxs-lookup"><span data-stu-id="a17b2-163">In such cases, the report will clearly identify the alert as "generic" and that it doesn't influence any of the charts in the report.</span></span>

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a><span data-ttu-id="a17b2-164">使用高級搜尋尋找細微威脅工件</span><span class="sxs-lookup"><span data-stu-id="a17b2-164">Find subtle threat artifacts using advanced hunting</span></span>
<span data-ttu-id="a17b2-165">雖然偵測可讓您自動識別及停止追蹤威脅，但許多攻擊活動都會留下需要其他檢查的細微追蹤。</span><span class="sxs-lookup"><span data-stu-id="a17b2-165">While detections allow you to identify and stop the tracked threat automatically, many attack activities leave subtle traces that require additional inspection.</span></span> <span data-ttu-id="a17b2-166">有些攻擊動作會表現出也可以是正常的行為，因此會以動態方式偵測這些行為，從而導致運作雜訊或甚至是誤報。</span><span class="sxs-lookup"><span data-stu-id="a17b2-166">Some attack activities exhibit behaviors that can also be normal, so detecting them dynamically can result in operational noise or even false positives.</span></span>

<span data-ttu-id="a17b2-167">「[高級搜尋](advanced-hunting-overview.md)」是以 Kusto 查詢語言為基礎的查詢介面，可簡化威脅活動的細微標記。</span><span class="sxs-lookup"><span data-stu-id="a17b2-167">[Advanced hunting](advanced-hunting-overview.md) provides a query interface based on Kusto Query Language that simplifies locating subtle indicators of threat activity.</span></span> <span data-ttu-id="a17b2-168">它也可讓您顯示內容資訊，並確認指示器是否連接至威脅。</span><span class="sxs-lookup"><span data-stu-id="a17b2-168">It also allows you to surface contextual information and verify whether indicators are connected to a threat.</span></span>

<span data-ttu-id="a17b2-169">分析報告中的高級搜尋查詢已由 Microsoft 分析員經，可供您在 [ [高級搜尋查詢編輯器](https://securitycenter.windows.com/advanced-hunting)] 中執行。</span><span class="sxs-lookup"><span data-stu-id="a17b2-169">Advanced hunting queries in the analyst reports have been vetted by Microsoft analysts and are ready for you to run in the [advanced hunting query editor](https://securitycenter.windows.com/advanced-hunting).</span></span> <span data-ttu-id="a17b2-170">您也可以使用查詢來建立 [自訂偵測規則](custom-detection-rules.md) ，以觸發警示以供未來的相符。</span><span class="sxs-lookup"><span data-stu-id="a17b2-170">You can also use the queries to create [custom detection rules](custom-detection-rules.md) that trigger alerts for future matches.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a17b2-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="a17b2-171">Related topics</span></span>
- [<span data-ttu-id="a17b2-172">威脅分析概觀</span><span class="sxs-lookup"><span data-stu-id="a17b2-172">Threat analytics overview</span></span>](threat-analytics.md)
- [<span data-ttu-id="a17b2-173">使用高級搜尋主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="a17b2-173">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="a17b2-174">自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="a17b2-174">Custom detection rules</span></span>](custom-detection-rules.md)