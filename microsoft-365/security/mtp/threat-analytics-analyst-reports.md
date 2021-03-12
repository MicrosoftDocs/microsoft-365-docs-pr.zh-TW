---
title: 瞭解威脅分析中的分析報告區段
ms.reviewer: ''
description: 深入瞭解每個威脅分析報告的分析報告區段。 瞭解它如何提供威脅、緩解、偵測、高級搜尋查詢等相關資訊。
keywords: 分析報告、威脅分析、偵測、高級搜尋查詢、緩解
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c82b0a84582d18f8b08b369ff76ba34046c40eba
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727112"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a><span data-ttu-id="5f011-105">瞭解威脅分析中的分析報告</span><span class="sxs-lookup"><span data-stu-id="5f011-105">Understand the analyst report in threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5f011-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="5f011-106">**Applies to:**</span></span>
- <span data-ttu-id="5f011-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f011-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="5f011-108">想要體驗 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="5f011-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5f011-109">您可以 [在實驗室環境中進行評估](https://aka.ms/mtp-trial-lab) ，或 [在實際執行中執行您的試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="5f011-109">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="5f011-110">每個 [威脅分析報告](threat-analytics.md) 都包含動態區段，以及一個稱為「 _分析員報告_」的完整寫入章節。</span><span class="sxs-lookup"><span data-stu-id="5f011-110">Each [threat analytics report](threat-analytics.md) includes dynamic sections and a comprehensive written section called the _analyst report_.</span></span> <span data-ttu-id="5f011-111">若要存取此區段，開啟有關追蹤威脅的報告，然後選取 [ **分析報告** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5f011-111">To access this section, open the report about the tracked threat and select the **Analyst report** tab.</span></span>

![威脅分析報告的分析報告區段影像](../../media/threat-analytics/ta_analystreport_mtp.png)

<span data-ttu-id="5f011-113">_威脅分析報告的分析報告區段_</span><span class="sxs-lookup"><span data-stu-id="5f011-113">_Analyst report section of a threat analytics report_</span></span>

## <a name="scan-the-analyst-report"></a><span data-ttu-id="5f011-114">掃描分析報告</span><span class="sxs-lookup"><span data-stu-id="5f011-114">Scan the analyst report</span></span> 
<span data-ttu-id="5f011-115">分析報告的每一節都是用來提供可行動的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f011-115">Each section of the analyst report is designed to provide actionable information.</span></span> <span data-ttu-id="5f011-116">當報表變化時，大部分的報表會包含下表所述的區段。</span><span class="sxs-lookup"><span data-stu-id="5f011-116">While reports vary, most reports include the sections described in the following table.</span></span>

| <span data-ttu-id="5f011-117">報表區段</span><span class="sxs-lookup"><span data-stu-id="5f011-117">Report section</span></span> | <span data-ttu-id="5f011-118">描述</span><span class="sxs-lookup"><span data-stu-id="5f011-118">Description</span></span> |
|--|--|
| <span data-ttu-id="5f011-119">摘要</span><span class="sxs-lookup"><span data-stu-id="5f011-119">Executive summary</span></span> | <span data-ttu-id="5f011-120">威脅的概述，包括初次看到的時間、其動機、明確的事件、主要目標，以及不同的工具和技術。</span><span class="sxs-lookup"><span data-stu-id="5f011-120">Overview of the threat, including when it was first seen, its motivations, notable events, major targets, and distinct tools and techniques.</span></span> <span data-ttu-id="5f011-121">您可以使用此資訊來進一步評估如何在您的行業、地理位置和網路內容中排定威脅的優先順序。</span><span class="sxs-lookup"><span data-stu-id="5f011-121">You can use this information to further assess how to prioritize the threat in the context of your industry, geographic location, and network.</span></span> |
| <span data-ttu-id="5f011-122">分析</span><span class="sxs-lookup"><span data-stu-id="5f011-122">Analysis</span></span> | <span data-ttu-id="5f011-123">威脅的技術資訊，包括攻擊的詳細資料，以及攻擊者可能使用新技術或攻擊面的方式</span><span class="sxs-lookup"><span data-stu-id="5f011-123">Technical information about the threats, including the details of an attack and how attackers might utilize a new technique or attack surface</span></span> | 
| <span data-ttu-id="5f011-124">MITRE ATT&所觀察到的 CK 技術</span><span class="sxs-lookup"><span data-stu-id="5f011-124">MITRE ATT&CK techniques observed</span></span> | <span data-ttu-id="5f011-125">觀察到的技巧如何對應至 [MITRE ATT&CK 攻擊架構](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="5f011-125">How observed techniques map to the [MITRE ATT&CK attack framework](https://attack.mitre.org/)</span></span> | 
| [<span data-ttu-id="5f011-126">減輕方式</span><span class="sxs-lookup"><span data-stu-id="5f011-126">Mitigations</span></span>](#apply-additional-mitigations) | <span data-ttu-id="5f011-127">可停止或協助減少威脅影響的建議。</span><span class="sxs-lookup"><span data-stu-id="5f011-127">Recommendations that can stop or help reduce the impact of the threat.</span></span> <span data-ttu-id="5f011-128">本節也包含不會在威脅分析報告中動態追蹤的緩解。</span><span class="sxs-lookup"><span data-stu-id="5f011-128">This section also includes mitigations that aren't tracked dynamically as part of the threat analytics report.</span></span> |
| [<span data-ttu-id="5f011-129">偵測詳細資料</span><span class="sxs-lookup"><span data-stu-id="5f011-129">Detection details</span></span>](#understand-how-each-threat-can-be-detected) | <span data-ttu-id="5f011-130">Microsoft 安全性解決方案所提供的特定及一般偵測，可以呈現與威脅相關聯的活動或元件。</span><span class="sxs-lookup"><span data-stu-id="5f011-130">Specific and generic detections provided by Microsoft security solutions that can surface activity or components associated with the threat.</span></span> | 
| [<span data-ttu-id="5f011-131">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="5f011-131">Advanced hunting</span></span>](#find-subtle-threat-artifacts-using-advanced-hunting) | <span data-ttu-id="5f011-132">以主動識別可能威脅活動的[高級搜尋查詢](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5f011-132">[Advanced hunting queries](advanced-hunting-overview.md) for proactively identifying possible threat activity.</span></span> <span data-ttu-id="5f011-133">大部分的查詢都是為了補充偵測，特別是找出可能惡意的元件或無法動態評估以成為惡意的行為。</span><span class="sxs-lookup"><span data-stu-id="5f011-133">Most queries are provided to supplement detections, especially for locating potentially malicious components or behaviors that couldn't be dynamically assessed to be malicious.</span></span> | 
| <span data-ttu-id="5f011-134">參考</span><span class="sxs-lookup"><span data-stu-id="5f011-134">References</span></span> | <span data-ttu-id="5f011-135">在建立報告期間，由分析員參考的 Microsoft 和協力廠商出版物。</span><span class="sxs-lookup"><span data-stu-id="5f011-135">Microsoft and third-party publications referenced by analysts during the creation of the report.</span></span> <span data-ttu-id="5f011-136">威脅分析內容是以 Microsoft 研究員所驗證的資料為基礎。</span><span class="sxs-lookup"><span data-stu-id="5f011-136">Threat analytics content is based on data validated by Microsoft researchers.</span></span> <span data-ttu-id="5f011-137">公開提供的資訊，協力廠商來源會明確識別。</span><span class="sxs-lookup"><span data-stu-id="5f011-137">Information from publicly available, third-party sources are identified clearly as such.</span></span> | 
| <span data-ttu-id="5f011-138">變更記錄</span><span class="sxs-lookup"><span data-stu-id="5f011-138">Change log</span></span> | <span data-ttu-id="5f011-139">報告發布的時間，以及對報表進行重大變更的時間。</span><span class="sxs-lookup"><span data-stu-id="5f011-139">The time the report was published and when significant changes were made to the report.</span></span> |

## <a name="apply-additional-mitigations"></a><span data-ttu-id="5f011-140">套用其他緩解</span><span class="sxs-lookup"><span data-stu-id="5f011-140">Apply additional mitigations</span></span>
<span data-ttu-id="5f011-141">威脅分析會動態追蹤 [安全性更新和安全設定的狀態](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。</span><span class="sxs-lookup"><span data-stu-id="5f011-141">Threat analytics dynamically tracks the [status of security updates and secure configurations](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices).</span></span> <span data-ttu-id="5f011-142">在 [ **緩解** ] 索引標籤中，此資訊是以圖表和表格的形式提供。</span><span class="sxs-lookup"><span data-stu-id="5f011-142">This information is available as charts and tables in the **Mitigations** tab.</span></span>

<span data-ttu-id="5f011-143">除了這些追蹤的緩解措施之外，「分析員」報告也會討論 _未_ 動態監視的緩解。</span><span class="sxs-lookup"><span data-stu-id="5f011-143">In addition to these tracked mitigations, the analyst report also discusses mitigations that are _not_ dynamically monitored.</span></span> <span data-ttu-id="5f011-144">以下是一些不會動態追蹤之重要緩解事項的範例：</span><span class="sxs-lookup"><span data-stu-id="5f011-144">Here are some examples of important mitigations that are not dynamically tracked:</span></span>

- <span data-ttu-id="5f011-145">封鎖使用 _.lnk_ 附件或其他可疑檔案類型的電子郵件</span><span class="sxs-lookup"><span data-stu-id="5f011-145">Block emails with _.lnk_ attachments or other suspicious file types</span></span>
- <span data-ttu-id="5f011-146">隨機化本機系統管理員密碼</span><span class="sxs-lookup"><span data-stu-id="5f011-146">Randomize local administrator passwords</span></span>
- <span data-ttu-id="5f011-147">教育使用者有關網路釣魚電子郵件和其他威脅媒介的教育</span><span class="sxs-lookup"><span data-stu-id="5f011-147">Educate end users about phishing email and other threat vectors</span></span>
- <span data-ttu-id="5f011-148">開啟特定 [攻擊面減少規則](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)</span><span class="sxs-lookup"><span data-stu-id="5f011-148">Turn on specific [attack surface reduction rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)</span></span>

<span data-ttu-id="5f011-149">雖然您可以使用 [ **緩解** ] 索引標籤，針對威脅評估安全性狀況，但這些建議可讓您採取額外步驟，以提升安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="5f011-149">While you can use the **Mitigations** tab to assess your security posture against a threat, these recommendations let you take additional steps towards improving your security posture.</span></span> <span data-ttu-id="5f011-150">請仔細閱讀分析報告中的所有緩解指導方針，並盡可能加以套用。</span><span class="sxs-lookup"><span data-stu-id="5f011-150">Carefully read all the mitigation guidance in the analyst report and apply them whenever possible.</span></span>

## <a name="understand-how-each-threat-can-be-detected"></a><span data-ttu-id="5f011-151">瞭解每個威脅的偵測方式</span><span class="sxs-lookup"><span data-stu-id="5f011-151">Understand how each threat can be detected</span></span>
<span data-ttu-id="5f011-152">分析報告也會提供 Microsoft Defender 針對端點防病毒和 _端點偵測的偵測，以及_ (EDR) 功能的回應。</span><span class="sxs-lookup"><span data-stu-id="5f011-152">The analyst report also provides the detections from Microsoft Defender for Endpoint antivirus and _endpoint detection and response_ (EDR) capabilities.</span></span>

### <a name="antivirus-detections"></a><span data-ttu-id="5f011-153">防病毒偵測</span><span class="sxs-lookup"><span data-stu-id="5f011-153">Antivirus detections</span></span>
<span data-ttu-id="5f011-154">在已開啟 [Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 功能的裝置上可以使用這些偵測。</span><span class="sxs-lookup"><span data-stu-id="5f011-154">These detections are available on devices with [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) turned on.</span></span> <span data-ttu-id="5f011-155">當這些偵測發生在已架至 Microsoft Defender for Endpoint 的裝置上時，也會觸發報告中的圖表，使其變亮。</span><span class="sxs-lookup"><span data-stu-id="5f011-155">When these detections occur on devices that have been onboarded to Microsoft Defender for Endpoint, they also trigger alerts that light up the charts in the report.</span></span>

>[!NOTE]
><span data-ttu-id="5f011-156">分析員報告也會列出 **一般性** 偵測，除了追蹤威脅特有的元件或行為之外，還可以識別範圍廣泛的威脅。</span><span class="sxs-lookup"><span data-stu-id="5f011-156">The analyst report also lists **generic detections** that can identify a wide-range of threats, in addition to components or behaviors specific to the tracked threat.</span></span> <span data-ttu-id="5f011-157">這些一般偵測不會反映在圖表中。</span><span class="sxs-lookup"><span data-stu-id="5f011-157">These generic detections don't reflect in the charts.</span></span>

### <a name="endpoint-detection-and-response-edr-alerts"></a><span data-ttu-id="5f011-158"> (EDR) 警示的端點偵測和回應</span><span class="sxs-lookup"><span data-stu-id="5f011-158">Endpoint detection and response (EDR) alerts</span></span>
<span data-ttu-id="5f011-159">在 [架至 Microsoft Defender For Endpoint 的裝置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)上會引發 EDR 警示。</span><span class="sxs-lookup"><span data-stu-id="5f011-159">EDR alerts are raised for [devices onboarded to Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span> <span data-ttu-id="5f011-160">這些警示通常會依賴 Microsoft Defender for Endpoint 感應器所收集的安全性信號，以及可充當功能強大之信號來源的其他端點功能（例如防毒軟體、網路保護、防篡改保護）。</span><span class="sxs-lookup"><span data-stu-id="5f011-160">These alerts generally rely on security signals collected by the Microsoft Defender for Endpoint sensor and other endpoint capabilities—such as antivirus, network protection, tamper protection—that serve as powerful signal sources.</span></span>

<span data-ttu-id="5f011-161">如防病毒偵測清單所設計，有些 EDR 警示是設計為一般標記可能不會與追蹤威脅相關聯的可疑行為。</span><span class="sxs-lookup"><span data-stu-id="5f011-161">Like the list of antivirus detections, some EDR alerts are designed to generically flag suspicious behavior that might not be associated with the tracked threat.</span></span> <span data-ttu-id="5f011-162">在這種情況下，報告會將警示明確識別為「一般」，而不會影響報表中的任何圖表。</span><span class="sxs-lookup"><span data-stu-id="5f011-162">In such cases, the report will clearly identify the alert as "generic" and that it doesn't influence any of the charts in the report.</span></span>

### <a name="email-related-detections-and-mitigations"></a><span data-ttu-id="5f011-163">電子郵件相關的偵測和緩解</span><span class="sxs-lookup"><span data-stu-id="5f011-163">Email-related detections and mitigations</span></span>
<span data-ttu-id="5f011-164">Microsoft Defender for Office 365 中的電子郵件相關偵測和緩解功能包含在分析報告中，除了 Microsoft Defender for Endpoint 中已提供的端點資料之外。</span><span class="sxs-lookup"><span data-stu-id="5f011-164">Email-related detections and mitigations from Microsoft Defender for Office 365, are included in analyst reports in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="5f011-165">避免電子郵件嘗試資訊可讓您深入瞭解您的組織是否為分析員報告中威脅 tackled 的目標，即使在傳送或傳送至 [垃圾郵件] 資料夾之前已經有效封鎖此攻擊。</span><span class="sxs-lookup"><span data-stu-id="5f011-165">Prevented email attempt information gives you insights on whether your organization were a target of the threat tackled in the analyst report even if the attack has been effectively blocked before delivery or delivered to the junk mail folder.</span></span>

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a><span data-ttu-id="5f011-166">使用高級搜尋尋找細微威脅工件</span><span class="sxs-lookup"><span data-stu-id="5f011-166">Find subtle threat artifacts using advanced hunting</span></span>
<span data-ttu-id="5f011-167">雖然偵測可讓您自動識別及停止追蹤威脅，但許多攻擊活動都會留下需要其他檢查的細微追蹤。</span><span class="sxs-lookup"><span data-stu-id="5f011-167">While detections allow you to identify and stop the tracked threat automatically, many attack activities leave subtle traces that require additional inspection.</span></span> <span data-ttu-id="5f011-168">有些攻擊動作會表現出也可以是正常的行為，因此會以動態方式偵測這些行為，從而導致運作雜訊或甚至是誤報。</span><span class="sxs-lookup"><span data-stu-id="5f011-168">Some attack activities exhibit behaviors that can also be normal, so detecting them dynamically can result in operational noise or even false positives.</span></span>

<span data-ttu-id="5f011-169">「[高級搜尋](advanced-hunting-overview.md)」是以 Kusto 查詢語言為基礎的查詢介面，可簡化威脅活動的細微標記。</span><span class="sxs-lookup"><span data-stu-id="5f011-169">[Advanced hunting](advanced-hunting-overview.md) provides a query interface based on Kusto Query Language that simplifies locating subtle indicators of threat activity.</span></span> <span data-ttu-id="5f011-170">它也可讓您顯示內容資訊，並確認指示器是否連接至威脅。</span><span class="sxs-lookup"><span data-stu-id="5f011-170">It also allows you to surface contextual information and verify whether indicators are connected to a threat.</span></span>

<span data-ttu-id="5f011-171">分析報告中的高級搜尋查詢已由 Microsoft 分析員經，可供您在 [ [高級搜尋查詢編輯器](https://security.microsoft.com/advanced-hunting)] 中執行。</span><span class="sxs-lookup"><span data-stu-id="5f011-171">Advanced hunting queries in the analyst reports have been vetted by Microsoft analysts and are ready for you to run in the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> <span data-ttu-id="5f011-172">您也可以使用查詢來建立 [自訂偵測規則](custom-detection-rules.md) ，以觸發警示以供未來的相符。</span><span class="sxs-lookup"><span data-stu-id="5f011-172">You can also use the queries to create [custom detection rules](custom-detection-rules.md) that trigger alerts for future matches.</span></span>


>[!NOTE]
> <span data-ttu-id="5f011-173">在 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)中也可以使用威脅分析。</span><span class="sxs-lookup"><span data-stu-id="5f011-173">Threat analytics is also available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics).</span></span> <span data-ttu-id="5f011-174">不過，在 microsoft 365 Defender 威脅分析所擁有的 Office 和 Microsoft Defender 端點之間，它沒有資料整合。</span><span class="sxs-lookup"><span data-stu-id="5f011-174">However, it does not have the data integration between Microsoft Defender for Office and Microsoft Defender for Endpoint that Microsoft 365 Defender threat analytics has.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5f011-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="5f011-175">Related topics</span></span>
- [<span data-ttu-id="5f011-176">威脅分析概觀</span><span class="sxs-lookup"><span data-stu-id="5f011-176">Threat analytics overview</span></span>](threat-analytics.md)
- [<span data-ttu-id="5f011-177">使用高級搜尋主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="5f011-177">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="5f011-178">自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="5f011-178">Custom detection rules</span></span>](custom-detection-rules.md)
