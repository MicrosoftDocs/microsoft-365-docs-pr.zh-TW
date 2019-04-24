---
title: GDPR 規定的 Azure 和外洩通知
description: Azure 如何防止個人資料外洩，以及若發生外洩 Microsoft 會如何回應和通知您。
keywords: Azure、Microsoft 365、Microsoft 365 教育版、Microsoft 365 文件、GDPR
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 287175d6f78efa1052e446b230f39c33fc4d5fc6
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286428"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a><span data-ttu-id="f0b21-104">GDPR 規定的 Azure 和外洩通知</span><span class="sxs-lookup"><span data-stu-id="f0b21-104">Azure and Breach Notification Under the GDPR</span></span>

<span data-ttu-id="f0b21-p101">Microsoft Azure 十分重視歐盟一般資料保護規範 (GDPR) 所規定的義務。Microsoft Azure 採取了大量的安全性措施，以防範資料外洩的威脅。這包含實體和邏輯兩方面的安全性控制，和自動化的安全性程序、完整的資訊安全與隱私權原則，以及所有人員的安全性與隱私權教育訓練。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p101">Microsoft Azure takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft Azure takes extensive security measures to protect against data breaches. These include both physical and logical security controls, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel.</span></span>

<span data-ttu-id="f0b21-p102">從一開始 Microsoft Azure 內就已內建各種安全機制，首先是[安全性開發週期](https://www.microsoft.com/sdl/)這項強制性開發程序，結合了「從設計著手保護隱私」和「預設為保護隱私」。Microsoft 安全性策略的最高指導原則是「假設已有缺口」，這是深度防禦策略的延伸。不斷挑戰 Azure 的安全性功能，Microsoft 才能先發制人，對抗接踵而來的新威脅。如需有關 Azure 安全性的詳細資訊，請參閱以下[資源](https://www.microsoft.com/trustcenter/security/azure-security)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p102">Security is built into Microsoft Azure from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft’s security strategy is to “assume breach,” which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of Azure, Microsoft can stay ahead of emerging threats. For more information on Azure security, please review these [resources](https://www.microsoft.com/trustcenter/security/azure-security).</span></span>

<span data-ttu-id="f0b21-p103">Microsoft 設有遍布全球的全天候事件回應服務，努力減少針對 Microsoft Azure 的攻擊所造成的影響。Microsoft 在資料中心採用了極為嚴密的作業和程序，以避免未經授權的存取，包括全天候的視訊監控、訓練精良的安全人員、智慧卡和生物特徵辨識控制等，通過多重安全性與合規性稽核 (例如 [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)) 的驗證。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p103">Microsoft has a global, 24x7 incident response service that works to mitigate the effects of attacks against Microsoft Azure. Attested by multiple security and compliance audits (e.g. [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)), Microsoft employs rigorous operations and processes at its data centers to prevent unauthorized access, including 24x7 video monitoring, trained security personnel, smart cards, and biometric controls.</span></span>

#### <a name="detection-of-potential-breaches"></a><span data-ttu-id="f0b21-114">潛在缺口的偵測</span><span class="sxs-lookup"><span data-stu-id="f0b21-114">Detection of Potential Breaches</span></span>
-------------------------------

<span data-ttu-id="f0b21-p104">由於現代雲端運算的性質，並非在客戶雲端環境所發生的所有資料外洩，都牽涉到 Microsoft Azure 服務。Microsoft 針對 Azure 服務採用責任分擔模型，來定義安全性及營運上的責任。在討論雲端服務的安全性時，責任分擔尤其重要；因為雲端服務提供者和客戶雙方都要對雲端安全性負責。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p104">Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is particularly important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.</span></span>

<span data-ttu-id="f0b21-p105">Microsoft 不會監視或回應客戶責任領域範圍內的安全性事件。我們不會將純由客戶造成的安全性洩漏當作 Azure 安全性事件來處理，且需要客戶的租用戶來負責回應。根據適用的服務合約，客戶事件回應可能會涉及與 Microsoft Azure [客戶支援](https://azure.microsoft.com/support/options/)部門共同作業。Microsoft Azure 也提供了各種服務 (例如 [Azure 資訊安全中心](https://azure.microsoft.com/services/security-center/)) 供客戶利用，以開發和管理安全性事件回應。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p105">Microsoft does not monitor for or respond to security incidents within the customer’s realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure also offers various services (e.g., [Azure Security Center](https://azure.microsoft.com/services/security-center/)) that customers can utilize for developing and managing security incident response.</span></span>

<span data-ttu-id="f0b21-p106">Azure 會根據安全性事件回應程序 (也就是 Microsoft Azure 事件管理計劃的子集) 回應潛在的資料外洩。系統會使用以下五個階段程序來實作 Azure 安全性事件回應：偵測、評估、診斷、穩定，及關閉。安全性事件回應小組可能會隨著調查進度輪流進行診斷和穩定。安全性事件回應程序的概觀說明如下：</span><span class="sxs-lookup"><span data-stu-id="f0b21-p106">Azure responds to a potential data breach according to the security incident response process, which is a subset of the Microsoft Azure incident management plan. Azure’s security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="f0b21-126">階段</span><span class="sxs-lookup"><span data-stu-id="f0b21-126">Stage</span></span></th>
<th align="left"><span data-ttu-id="f0b21-127">說明</span><span class="sxs-lookup"><span data-stu-id="f0b21-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f0b21-128">1</span><span class="sxs-lookup"><span data-stu-id="f0b21-128">-1</span></span></td>
<td align="left"><span data-ttu-id="f0b21-129">偵測</span><span class="sxs-lookup"><span data-stu-id="f0b21-129">Detect</span></span></td>
<td align="left"><span data-ttu-id="f0b21-130">潛在事件的第一個徵兆。</span><span class="sxs-lookup"><span data-stu-id="f0b21-130">First indication of a potential incident.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f0b21-131">2</span><span class="sxs-lookup"><span data-stu-id="f0b21-131">2.</span></span></td>
<td align="left"><span data-ttu-id="f0b21-132">評估</span><span class="sxs-lookup"><span data-stu-id="f0b21-132">Assess</span></span></td>
<td align="left"><span data-ttu-id="f0b21-p107">待命事件回應小組成員會評估事件的影響和嚴重性。取決於證據，可能會也可能不會進一步向安全性回應小組呈報評估。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p107">An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="f0b21-135">3</span><span class="sxs-lookup"><span data-stu-id="f0b21-135">3.</span></span></td>
<td align="left"><span data-ttu-id="f0b21-136">診斷</span><span class="sxs-lookup"><span data-stu-id="f0b21-136">Diagnose</span></span></td>
<td align="left"><p><span data-ttu-id="f0b21-137">安全性回應專家會進行技術或鑑定調查，找出內含項目、風險降低及因應措施策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-137">Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies.</span></span></p>
<p><span data-ttu-id="f0b21-138">若安全性小組相信客戶資料可能遭受非法或未經授權的人員存取，將會同步進行客戶事件通知程序。</span><span class="sxs-lookup"><span data-stu-id="f0b21-138">If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f0b21-139">4</span><span class="sxs-lookup"><span data-stu-id="f0b21-139">4.</span></span></td>
<td align="left"><span data-ttu-id="f0b21-140">穩定及復原</span><span class="sxs-lookup"><span data-stu-id="f0b21-140">Stabilize and Recover</span></span></td>
<td align="left"><span data-ttu-id="f0b21-p108">事件回應小組會建立復原計劃，以降低問題的風險。危機抑制步驟 (例如隔離受影響的系統) 可能會立即與診斷同步進行。長期風險降低預計要等到眼前的風險過後才會進行規劃。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p108">The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="f0b21-144">5</span><span class="sxs-lookup"><span data-stu-id="f0b21-144">5.</span></span></td>
<td align="left"><span data-ttu-id="f0b21-145">結案與檢討</span><span class="sxs-lookup"><span data-stu-id="f0b21-145">Close and Post-Mortem</span></span></td>
<td align="left"><span data-ttu-id="f0b21-146">事件回應小組會建立概述事件詳細資訊的檢討，目的是修改原則、步驟和流程，以避免該事件再次發生。</span><span class="sxs-lookup"><span data-stu-id="f0b21-146">The incident response team creates a post-mortem that outlines the details of the incident, with the intention to revise policies, procedures, and processes to prevent a reoccurrence of the event.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f0b21-147">《[Microsoft Azure 在雲端的安全性回應](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678)》白皮書進一步詳述 Microsoft 在 Azure 中調查、管理以及回應安全性事件的方式。</span><span class="sxs-lookup"><span data-stu-id="f0b21-147">The [Microsoft Azure Security Response in the Cloud](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) white paper further details how Microsoft investigates, manages, and responds to security incidents within Azure.</span></span>

<span data-ttu-id="f0b21-p109">Microsoft Azure 使用的偵測程序旨在探索會讓 Azure 服務的機密性、完整性和可用性遭受風險的事件。有數種事件可能會觸發調查：</span><span class="sxs-lookup"><span data-stu-id="f0b21-p109">The detection processes used by Microsoft Azure are designed to discover events that risk the confidentiality, integrity, and availability of Azure services. Several events can trigger an investigation:</span></span>

-   <span data-ttu-id="f0b21-p110">自動化系統會透過內部監視和警示架構發出警示。這些警示會以病毒碼式警訊 (例如反惡意程式碼軟體、入侵偵測)，或透過旨在分析預期活動並在異常時發出警示的演算法等方式提供。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p110">Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as antimalware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.</span></span>

-   <span data-ttu-id="f0b21-152">來自 Microsoft Azure 和 Azure Government 上所執行 Microsoft 服務的第一方報告。</span><span class="sxs-lookup"><span data-stu-id="f0b21-152">First party reports from Microsoft Services running on Microsoft Azure and Azure Government.</span></span>

-   <span data-ttu-id="f0b21-p111">系統會透過 <secure@microsoft.com> 向 [Microsoft 安全性回應中心 (MSRC)](https://technet.microsoft.com/security/dn440717)報告安全性漏洞。Msrc 會與合作夥伴及全球安全性研究人員合作來防止安全性事件，並進一步提升 Microsoft 產品的安全性。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p111">Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via <secure@microsoft.com>. MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.</span></span>

-   <span data-ttu-id="f0b21-155">透過[客戶支援入口網站](http://www.windowsazure.com/support/contact/)或 Microsoft Azure 與 Azure Government 管理入口網站回報的客戶報告，其中說明了歸因於 Azure 基礎結構的可疑活動 (而非客戶責任範圍內所發生的活動)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-155">Customer reports via the [Customer Support Portal](http://www.windowsazure.com/support/contact/) or Microsoft Azure and Azure Government Management Portal, that describe suspicious activity attributed to the Azure infrastructure (as opposed to activity occurring within the customer’s scope of responsibility).</span></span>

-   <span data-ttu-id="f0b21-p112">安全性[紅隊和藍隊](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活動。此策略利用了具有高度技巧的紅隊來找出並攻擊在 Azure 中的潛在弱點，由 Microsoft 的攻擊性安全專家所組成。負責安全性回應的藍隊必須偵測並防禦紅隊的活動。我們會用紅隊和藍隊雙方的動作，來確認 Azure 所做的安全性回應是否能有效地因應安全性事件。安全性紅隊和藍隊是根據教戰守則進行活動，以協助確保客戶資料能受到保護。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p112">Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly-skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.</span></span>

-   <span data-ttu-id="f0b21-p113">Azure 服務作業員的呈報。Microsoft 員工都受過訓練，可找出潛在的安全性問題並向上呈報。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p113">Escalations by operators of Azure Services. Microsoft employees are trained to identify and escalate potential security issues.</span></span>

#### <a name="azures-data-breach-response"></a><span data-ttu-id="f0b21-163">Azure 的資料外洩回應</span><span class="sxs-lookup"><span data-stu-id="f0b21-163">Azure’s Data Breach Response</span></span>
----------------------------

<span data-ttu-id="f0b21-p114">Microsoft 會判斷功能性影響、復原能力和事件的資訊影響，來指派適當的調查優先順序及嚴重性等級。在調查過程中，優先順序和嚴重性都有可能會變更，取決於新的發現和結論。涉及對客戶資料有迫切或經確認風險的安全性事件，我們會視為高嚴重性而不眠不休地設法解決。Microsoft Azure 將事件的資訊影響分類為下列缺口類別：</span><span class="sxs-lookup"><span data-stu-id="f0b21-p114">Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft Azure categorizes the information impact of the incident into the following breach categories:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f0b21-168">類別</span><span class="sxs-lookup"><span data-stu-id="f0b21-168">Category</span></span></th>
<th align="left"><span data-ttu-id="f0b21-169">定義</span><span class="sxs-lookup"><span data-stu-id="f0b21-169">Definition</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f0b21-170">無</span><span class="sxs-lookup"><span data-stu-id="f0b21-170">None</span></span></td>
<td align="left"><span data-ttu-id="f0b21-171">沒有任何資訊遭到挾帶、變更、刪除或以其他方式洩漏出去。</span><span class="sxs-lookup"><span data-stu-id="f0b21-171">No information was exfiltrated, changed, deleted, or otherwise compromised.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f0b21-172">隱私權缺口</span><span class="sxs-lookup"><span data-stu-id="f0b21-172">Privacy Breach</span></span></td>
<td align="left"><span data-ttu-id="f0b21-173">納稅人、員工、受益人等的敏感性個人資料遭人存取或挾帶出去。</span><span class="sxs-lookup"><span data-stu-id="f0b21-173">Sensitive personal data of taxpayers, employees, beneficiaries, etc. was accessed or exfiltrated.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="f0b21-174">專利缺口</span><span class="sxs-lookup"><span data-stu-id="f0b21-174">Proprietary Breach</span></span></td>
<td align="left"><span data-ttu-id="f0b21-175">非機密專利資訊 (例如受保護的關鍵基礎結構資訊 (PCII) 等) 遭人存取或挾帶出去。</span><span class="sxs-lookup"><span data-stu-id="f0b21-175">Unclassified proprietary information, such as protected critical infrastructure information (PCII), was accessed or exfiltrated.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f0b21-176">完整性受損</span><span class="sxs-lookup"><span data-stu-id="f0b21-176">Integrity Loss</span></span></td>
<td align="left"><span data-ttu-id="f0b21-177">敏感性或專利資訊遭人變更或刪除。</span><span class="sxs-lookup"><span data-stu-id="f0b21-177">Sensitive or proprietary information was changed or deleted.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f0b21-p115">安全性回應小組會與 Microsoft Azure 安全性工程師及主題專家 (SME) 合作，根據證據的事實資料將事件分類。安全性事件可以歸類為：</span><span class="sxs-lookup"><span data-stu-id="f0b21-p115">The Security Response Team works with Microsoft Azure Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as:</span></span>

-   <span data-ttu-id="f0b21-p116">**誤判：** 事件符合偵測準則，但經查明其實是正常商業活動的一部分，且可能需要進行篩選。服務小組會找出誤判的根本原因，並以系統化的方式視需要運用偵測來源和進行微調，<span id="_Toc350859432" class="anchor"></span>來解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p116">**False Positive:** An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-<span id="_Toc350859432" class="anchor"></span>tuning them as needed.</span></span>

-   <span data-ttu-id="f0b21-182">**安全性事件：** 有人非法存取任何儲存在 Microsoft 設備或 Microsoft 設施上的客戶資料或支援資料，或未經授權存取這類設備或設施，進而造成客戶資料或支援資料遺失、洩漏，或變更的事件。</span><span class="sxs-lookup"><span data-stu-id="f0b21-182">**Security Incident:** An incident where unlawful access to any Customer Data or Support Data stored on Microsoft’s equipment or in Microsoft’s facilities, or unauthorized access to such equipment or facilities resulting in loss, disclosure, or alteration of Customer Data or Support Data has occurred.</span></span>

-   <span data-ttu-id="f0b21-183">**須向客戶報告的安全性事件 (CRSI)：** 有人非法或未經授權存取或使用 Microsoft 系統、設備或設施，導致客戶資料洩漏、修改或遺失。</span><span class="sxs-lookup"><span data-stu-id="f0b21-183">**Customer-Reportable Security Incident (CRSI):** An unlawful or unauthorized access to or use of Microsoft’s systems, equipment, or facilities resulting in disclosure, modification, or loss of customer data.</span></span>

-   <span data-ttu-id="f0b21-p117">**隱私權缺口：** 涉及個人資料的安全性事件之子類型。處理程序與安全性事件沒有差別。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p117">**Privacy Breach:** A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.</span></span>

<span data-ttu-id="f0b21-p118">若要宣告 CRSI，Microsoft 必須先判斷客戶資料已遭到或很有可能已遭到未經授權的存取，且 (或) 有必須通知客戶的法律或合約承諾。雖然並非必要，但您最好了解對特定客戶的影響、資源存取與修復步驟。通常要等到安全性事件的診斷階段結束後，才會宣告事件屬於 CRSI。不過，在所有直接相關的資訊都可供使用時，也可能會隨時宣告。安全性事件管理員必須找出確鑿的證據，足以支持的確發生了須向客戶報告的事件，以開始執行客戶事件通知程序。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p118">For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.</span></span>

<span data-ttu-id="f0b21-p119">在整個調查過程中，安全性回應小組都會與全球的法律顧問密切合作，以協助確保根據法律義務與對客戶的承諾而執行鑑識。其中對於在各種作業環境下檢視及處理系統和客戶資料也有重要的限制。未得到對應的事件票證中所記錄之事件管理員的明確書面核准前，不得將敏感性或機密資料以及客戶資料傳輸出去。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p119">Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket.</span></span>

<span data-ttu-id="f0b21-p120">Microsoft 會確認是否已成功遏制客戶和商業風險，並實施了矯正措施。如有需要，會進行緊急風險降低步驟，以解決與事件關聯的迫切安全性風險。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p120">Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken.</span></span>

<span data-ttu-id="f0b21-p121">Microsoft 也會完成資料外洩的內部檢討。在此過程中，會評估回應的充分程度和作業程序，並找出和實施安全性事件回應 SOP 或相關程序所需的任何更新。資料外洩的內部檢討是客戶無法取得的極機密記錄。不過，我們可以將檢討摘要並納入客戶事件通知中。在 Azure 的例行稽核週期中，會向外部稽核者提供這些報告以供審查。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p121">Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal post-mortems for data breaches are highly confidential records not available to customers. Post-mortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure’s routine audit cycle.</span></span>

#### <a name="customer-notification"></a><span data-ttu-id="f0b21-200">客戶通知</span><span class="sxs-lookup"><span data-stu-id="f0b21-200">Customer Notification</span></span>
---------------------

<span data-ttu-id="f0b21-p122">Microsoft Azure 依要求會向客戶和法規機構通知資料外洩。Microsoft 仰賴在 Azure 作業上進行大量的內部劃分。資料流記錄也相當健全。此設計的好處是可以將大部分的事件限制在特定客戶的範圍內。目標是讓受影響客戶的資料遭到外洩時，提供他們正確、實用且及時的通知。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p122">Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of Azure. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached.</span></span>

<span data-ttu-id="f0b21-p123">在宣告 CRSI 後，我們會以最快的速度進行通知程序，同時仍顧及在快速行動下的安全性風險。通常，正在進行事件調查時，就會開始草擬通知。*除了*下列情況，從我們宣告有缺口算起不超過 72 小時內，就會傳送客戶通知：</span><span class="sxs-lookup"><span data-stu-id="f0b21-p123">After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* for the following circumstances:</span></span>

-   <span data-ttu-id="f0b21-p124">Microsoft 相信執行通知的動作會增加其他客戶的風險。比方說，通知的動作可能會驚動攻擊者，因而無法補救。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p124">Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.</span></span>

-   <span data-ttu-id="f0b21-211">經 Microsoft 法務部門企業外部和法律事務 (CELA) 和事件執行經理審查過的其他不尋常或特殊情況。</span><span class="sxs-lookup"><span data-stu-id="f0b21-211">Other unusual or extreme circumstances vetted by Microsoft’s legal department Corporate External and Legal Affairs (CELA) and the Executive Incident Manager.</span></span>

<span data-ttu-id="f0b21-212">Microsoft Azure 可提供客戶詳細資訊，讓他們能執行內部調查，並協助他們符合對使用者的承諾，而不會過度延遲通知程序。</span><span class="sxs-lookup"><span data-stu-id="f0b21-212">Microsoft Azure provides customers with detailed information enabling them to perform internal investigations and assisting them in meeting end user commitments, while not unduly delaying the notification process.</span></span>

<span data-ttu-id="f0b21-p125">系統會以 Microsoft 選擇的任何方式 (包括透過電子郵件) 將個人資料外洩的通知傳送給客戶。系統會將資料外洩的通知，傳送給 Azure 資訊安全中心所提供的安全性連絡人清單；您可遵循[實作方針](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)來設定此清單。若 Azure 資訊安全中心未提供連絡人資訊，則會將通知傳送給 Azure 訂用帳戶中的一或多個系統管理員。為了確保可順利傳送通知，客戶有責任確保每個訂用帳戶和線上服務入口網站上的管理連絡人資訊是正確的。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p125">Notification of a personal data breach will be delivered to the customer by any means Microsoft selects, including via email. Notification of a data breach will be delivered to the list of security contacts provided in Azure Security center, which can be configured by following the [implementation guidelines](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). If contact information is not provided in Azure Security Center, the notification will be sent to one or more administrator in an Azure subscription. To ensure that notification can be successfully delivered, it is the customer’s responsibility to ensure that the administrative contact information on each applicable subscription and online services portal is correct.</span></span>

<span data-ttu-id="f0b21-p126">Microsoft Azure 或 Azure Government 小組也可以選擇通知客戶服務 (CSS) 和客戶帳戶管理員 (AM)，或技術帳戶管理員 (TAM) 等其他 Microsoft 人員。這些人員通常與客戶有密切的關係，也有助於快速進行補救。<span id="_Appendix_A" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="f0b21-p126">The Microsoft Azure or Azure Government team may also elect to notify additional Microsoft personnel such as Customer Service (CSS) and the customer’s Account Manager(s) (AM) or Technical Account Manager(s) (TAM). These individuals often have close relationships with the customer and can facilitate faster remediation<span id="_Appendix_A" class="anchor"></span></span></span>

#### <a name="microsoft-intune-data-breach"></a><span data-ttu-id="f0b21-219">Microsoft InTune 資料外洩</span><span class="sxs-lookup"><span data-stu-id="f0b21-219">Microsoft InTune Data Breach</span></span>
----------------------------

<span data-ttu-id="f0b21-p127">Microsoft Intune 是 Microsoft Enterprise Mobility and Security 套件服務提供項目的重要元件。為了支援資料控管策略，所有的 Microsoft 雲端服務都是依照「Microsoft 從設計著手保護隱私與安全性」和「預設為保護隱私與安全性」方法來開發的。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p127">Microsoft Intune is key component of the Microsoft Enterprise Mobility and Security Suite cloud service offering. To support the data governance strategy, all Microsoft cloud services are developed with the Microsoft Privacy and Security by Design and Privacy and Security by Default methodologies.</span></span>

<span data-ttu-id="f0b21-p128">而 Microsoft Intune 的雲端服務提供項目，也遵循了與 Microsoft Azure 服務小組在確保資料外洩安全的程序上，所採用的相同技術和組織措施。因此，在這份「Microsoft Azure 資料外洩」通知文件中所記錄的任何資訊，也與 Microsoft Intune 服務很類似。例如，Microsoft Intune 也沿用了相同的安全性事件回應程序和生命週期 (從階段 1：偵測到階段 5<strong>：</strong>結案與檢討)，以及相同的客戶安全性事件通知程序。此外，Microsoft Intune 也透過直接與 Microsoft O365 小組合作，履行了對任何使用 Intune 的 Microsoft O365 客戶進行缺口通知的義務。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p128">As such Microsoft Intune ‘s cloud service offering follows the same Technical and Organizational measures the Microsoft Azure service team(s) take for securing against data breach processes. Therefore, any information documented in the “Microsoft Azure Data Breach” notification document here is analogous to the Microsoft Intune service as well. For example, Microsoft Intune has the same Security Incident Response Process and Lifecycle (Stage 1: Detect thru Stage 5<strong>:</strong> Close and Postmortem) and also the same Customer Security Incident Notification process. In addition, Microsoft Intune also fulfills its obligations for Breach Notification for any Microsoft O365 customers using Intune by working directly with the Microsoft O365 team.</span></span>

<span data-ttu-id="f0b21-226">如需 Microsoft 如何偵測及回應個人資料外洩的詳細資訊，請參閱服務信任入口網站中的 [GDPR 規定的資料外泄通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-226">For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.</span></span>


#### <a name="learn-more"></a><span data-ttu-id="f0b21-227">深入了解</span><span class="sxs-lookup"><span data-stu-id="f0b21-227">Learn more</span></span>
[<span data-ttu-id="f0b21-228">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="f0b21-228">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
