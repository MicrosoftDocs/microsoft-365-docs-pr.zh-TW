---
title: GDPR 規定的 Dynamics 365 和外洩通知
description: Dynamics 365 如何防止個人資料外洩，以及若發生外洩 Microsoft 會如何回應和通知您。
keywords: Dynamics 365、Microsoft 365、Microsoft 365 教育版、Microsoft 365 文件、GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
author: herviicban
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 957fbe5713c248ebcac1a986248455c7d98b4935
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431874"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a><span data-ttu-id="b29e8-104">GDPR 規定的 Dynamics 365 和外洩通知</span><span class="sxs-lookup"><span data-stu-id="b29e8-104">Dynamics 365 and Breach Notification Under the GDPR</span></span>

<span data-ttu-id="b29e8-105">Dynamics 365 很認真看待其在一般資料保護規定 (GDPR) 下所需承擔的責任。</span><span class="sxs-lookup"><span data-stu-id="b29e8-105">Dynamics 365 takes its obligations under the General Data Protection Regulation (GDPR) seriously and takes extensive security measures to protect against data breaches.</span></span> <span data-ttu-id="b29e8-106">Microsoft 不斷努力為 Dynamics 365 客戶提供高度安全的企業級服務。</span><span class="sxs-lookup"><span data-stu-id="b29e8-106">Microsoft works continuously to provide highly secure, enterprise-grade services for Dynamics 365 customers.</span></span> <span data-ttu-id="b29e8-107">本節中的資訊提供 Microsoft Dynamics 365 如何保護客戶免於安全性事件/資料外洩的摘要，以及在回應和告知客戶時我們所遵循的程序。</span><span class="sxs-lookup"><span data-stu-id="b29e8-107">Microsoft works continuously to provide highly secure, enterprise-grade services for Dynamics 365 customers. The information in this section provides a summary of how Microsoft Dynamics 365 protects against security incident/data breach and the process we follow to respond and notify our customers.</span></span>

#### <a name="microsoft-dynamics-365-built-in-security-features"></a><span data-ttu-id="b29e8-108">Microsoft Dynamics 365 內建的安全性功能</span><span class="sxs-lookup"><span data-stu-id="b29e8-108">Microsoft Dynamics 365 Built-In Security Features</span></span>

<span data-ttu-id="b29e8-p102">Microsoft Dynamics 365 利用雲端服務基礎結構和內建安全性功能，確保使用安全性措施和機制來保護資料的安全。此外，Dynamics 365 在下列領域中提供有效資料存取和對資料完整性及隱私權的共同作業：[保護身分識別、資料保護、角色型安全性與威脅管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p102">Microsoft Dynamics 365 takes advantage of the cloud service infrastructure and built-in security features to keep data safe using security measures and mechanisms to protect data. In addition, Dynamics 365 provides efficient data access and collaboration with data integrity and privacy in the following areas: [secure identity, data protection, role based security and threat management](https://www.microsoft.com/trustcenter/security/dynamics365-security).</span></span>

#### <a name="incident-response-training"></a><span data-ttu-id="b29e8-111">事件回應訓練</span><span class="sxs-lookup"><span data-stu-id="b29e8-111">Incident Response Training</span></span>

<span data-ttu-id="b29e8-p103">使用 Microsoft Dynamics 365 的每位員工，都會獲得適用於其角色的安全性事件和回應程序訓練。每位 Microsoft Dynamics 365 員工在加入時都會接受訓練，之後每年也會接受進修課程訓練。該訓練旨在讓員工對 Microsoft 的安全處理方法有基本了解；因此在訓練完成後，所有的員工會了解到：</span><span class="sxs-lookup"><span data-stu-id="b29e8-p103">Each employee working on Microsoft Dynamics 365 is provided with training regarding security incidents and response procedures that are appropriate to their role. Every Microsoft Dynamics 365 employee receives training upon joining, and annual refresher training every year thereafter. The training is designed to provide the employee with a basic understanding of Microsoft’s approach to security so that upon completion of training, all employees understand:</span></span>

-   <span data-ttu-id="b29e8-115">安全性事件的定義；</span><span class="sxs-lookup"><span data-stu-id="b29e8-115">The definition of a security incident;</span></span>

-   <span data-ttu-id="b29e8-116">所有員工都有報告安全性事件的責任；</span><span class="sxs-lookup"><span data-stu-id="b29e8-116">The responsibility of all employees to report security incidents;</span></span>

-   <span data-ttu-id="b29e8-117">如何將潛在的安全性事件呈報給 Dynamics 365 安全性事件回應小組；</span><span class="sxs-lookup"><span data-stu-id="b29e8-117">How to escalate a potential security incident to Dynamics 365 Security Incident Response team;</span></span>

-   <span data-ttu-id="b29e8-118">Dynamics 365 安全性事件回應小組如何回應安全性事件；</span><span class="sxs-lookup"><span data-stu-id="b29e8-118">How the Dynamics 365 Security incident Response team responds to security incident;</span></span>

-   <span data-ttu-id="b29e8-119">關於隱私權的特殊問題 (尤其是客戶隱私權)；</span><span class="sxs-lookup"><span data-stu-id="b29e8-119">Special concerns regarding privacy, particularly customer privacy;</span></span>

-   <span data-ttu-id="b29e8-120">在何處可以找到關於安全性和隱私權及呈報連絡人的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="b29e8-120">Where to find additional information about security and privacy, and escalation contacts.</span></span>

#### <a name="how-does-microsoft-dynamics-365-define-security-incident-potential-breaches"></a><span data-ttu-id="b29e8-121">Microsoft Dynamics 365 如何定義安全性事件/潛在缺口</span><span class="sxs-lookup"><span data-stu-id="b29e8-121">How does Microsoft Dynamics 365 define Security Incident/ Potential Breaches</span></span>

<span data-ttu-id="b29e8-p104">安全性事件/資料外洩，指的是有人非法存取儲存在 Microsoft 設備上或 Microsoft 設施中的客戶資料等事件，或未經授權存取這類設備或設施，進而造成客戶資料或支援資料遺失、洩漏或變更的事件。Microsoft 在回應安全性事件/資料外洩時的目標，即是保護客戶資料和 Dynamics 365 服務。Microsoft 管理安全性事件的方法符合[美國國家標準暨技術研究院](https://www.nist.gov/) (NIST) 特殊出版物 (SP) [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) 中的規定。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p104">A security incident/ data breach refers to events such as unlawful access to customer’s data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such equipment or facilities that has the potential to result in the loss, disclosure or alteration of customer data. Microsoft’s goal when responding to security incidents/ data breach is to protect customer data and Dynamics 365 services. Microsoft’s approach to managing a security incident conforms to the [National Institute of Standards and Technology](https://www.nist.gov/) (NIST) Special Publication (SP) [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf).</span></span>

<span data-ttu-id="b29e8-p105">Microsoft 不會監視或回應屬客戶責任領域範圍內的安全性事件。系統不會將客戶單方面的安全性洩漏當作 Dynamics 365 安全性事件來處理，且這類洩漏需要客戶租用戶來管理回應工作。客戶事件回應可能會考量適當的服務合約，與 Microsoft Dynamics 365 客戶支援共同作業。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p105">Microsoft does not monitor for or respond to security incidents within the customer’s realm of responsibility. A customer-only security compromise would not be processed as a Dynamics 365 security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Dynamics 365 customer support, given appropriate service contracts.</span></span>

#### <a name="detection-of-potential-breaches"></a><span data-ttu-id="b29e8-128">偵測潛在缺口</span><span class="sxs-lookup"><span data-stu-id="b29e8-128">Detection of Potential Breaches</span></span>

<span data-ttu-id="b29e8-p106">Dynamics 365 會根據安全性事件回應程序 (也就是 Microsoft Dynamics 365 事件管理計劃的子集) 回應潛在的資料外洩。系統會使用以下五階段的程序來實作 Dynamics 365 安全性事件回應：偵測、評估、診斷、穩定與結案。安全性事件回應小組可能會隨著調查進度輪流進行診斷和穩定階段。安全性事件回應程序的概觀說明如下：</span><span class="sxs-lookup"><span data-stu-id="b29e8-p106">Dynamics 365 responds to a potential data breach according to the security incident response process, which is a subset of the Microsoft Dynamics 365 incident management plan. Dynamics 365 security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="b29e8-133">階段</span><span class="sxs-lookup"><span data-stu-id="b29e8-133">Stage</span></span></th>
<th align="left"><span data-ttu-id="b29e8-134">說明</span><span class="sxs-lookup"><span data-stu-id="b29e8-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="b29e8-135">1</span><span class="sxs-lookup"><span data-stu-id="b29e8-135">1</span></span></td>
<td align="left"><span data-ttu-id="b29e8-136">偵測</span><span class="sxs-lookup"><span data-stu-id="b29e8-136">Detect</span></span></td>
<td align="left"><span data-ttu-id="b29e8-137">事件調查的第一個指示。</span><span class="sxs-lookup"><span data-stu-id="b29e8-137">First indication of an event investigation.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b29e8-138">2</span><span class="sxs-lookup"><span data-stu-id="b29e8-138">2</span></span></td>
<td align="left"><span data-ttu-id="b29e8-139">評估</span><span class="sxs-lookup"><span data-stu-id="b29e8-139">Assess</span></span></td>
<td align="left"><span data-ttu-id="b29e8-p107">待命事件回應小組成員會評估事件的影響和嚴重性。取決於證據，可能會也可能不會進一步向安全性回應小組呈報評估。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p107">An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b29e8-142">3</span><span class="sxs-lookup"><span data-stu-id="b29e8-142">3</span></span></td>
<td align="left"><span data-ttu-id="b29e8-143">診斷/調查</span><span class="sxs-lookup"><span data-stu-id="b29e8-143">Diagnose/ Investigate</span></span></td>
<td align="left"><p><span data-ttu-id="b29e8-144">安全性回應專家進行技術或鑑定調查、找出內含項目、風險降低及因應措施策略。</span><span class="sxs-lookup"><span data-stu-id="b29e8-144">Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies.</span></span></p>
<p><span data-ttu-id="b29e8-145">若安全性小組相信客戶資料可能遭受非法或未經授權的人員存取，將會同步進行客戶事件通知程序。</span><span class="sxs-lookup"><span data-stu-id="b29e8-145">If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, parallel execution of the Customer Incident Notification process begins in parallel.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b29e8-146">4</span><span class="sxs-lookup"><span data-stu-id="b29e8-146">4</span></span></td>
<td align="left"><span data-ttu-id="b29e8-147">穩定及復原</span><span class="sxs-lookup"><span data-stu-id="b29e8-147">Stabilize and Recover</span></span></td>
<td align="left"><span data-ttu-id="b29e8-p108">事件回應小組會建立復原計劃，以降低問題的風險。危機抑制步驟 (例如隔離受影響的系統) 可能會立即與診斷同步進行。長期風險降低預計要等到眼前的風險過後才會進行規劃。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p108">The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b29e8-151">5</span><span class="sxs-lookup"><span data-stu-id="b29e8-151">5</span></span></td>
<td align="left"><span data-ttu-id="b29e8-152">結案與檢討</span><span class="sxs-lookup"><span data-stu-id="b29e8-152">Close and Post-Mortem</span></span></td>
<td align="left"><span data-ttu-id="b29e8-153">事件回應小組會建立概述事件詳細資訊的檢討，目的是修改原則、步驟和流程，以避免該事件再次發生。</span><span class="sxs-lookup"><span data-stu-id="b29e8-153">The incident response team creates a post-mortem that outlines the details of the incident, with the intention to revise policies, procedures, and processes to prevent a reoccurrence of the event.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b29e8-154">《[動態安全性事件管理](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)》白皮書 (英文) 會進一步詳述 Microsoft 在 Dynamics 365 中調查、管理以及回應安全性事件的方式。</span><span class="sxs-lookup"><span data-stu-id="b29e8-154">The [Dynamics Security Incident Management](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) white paper further details how Microsoft investigates, manages, and responds to security incidents within Dynamics 365.</span></span>

<span data-ttu-id="b29e8-p109">Microsoft Dynamics 365 使用的偵測程序旨在探索會讓 Dynamics 365 服務的機密性、完整性和可用性遭受風險的事件。有數種事件可能會觸發調查：</span><span class="sxs-lookup"><span data-stu-id="b29e8-p109">The detection processes used by Microsoft Dynamics 365 are designed to discover events that risk the confidentiality, integrity, and availability of Dynamics 365 services. Several events can trigger an investigation:</span></span>

-   <span data-ttu-id="b29e8-p110">自動化系統透過內部監視和警示架構發出警示。這些警示會以病毒碼式警訊 (例如反惡意程式碼軟體、入侵偵測)，或透過旨在分析預期活動並在異常時發出警示的演算法等方式提供。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p110">Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as antimalware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.</span></span>

-   <span data-ttu-id="b29e8-159">第一方報告在公用雲端中部署的執行中 Microsoft Dynamics 365 服務，以及在主權雲端中部署的 Microsoft Dynamics 365 服務。</span><span class="sxs-lookup"><span data-stu-id="b29e8-159">First party reports running Microsoft Dynamics 365 services deployed in Public Cloud and Microsoft Dynamics 365 services deployed in Sovereign Cloud.</span></span>

-   <span data-ttu-id="b29e8-p111">[Microsoft 安全性回應中心 (MSRC)](https://technet.microsoft.com/security/dn440717) 收到透過 <secure@microsoft.com> 所回報的安全性漏洞。MSRC 會與合作夥伴及全球安全性研究人員合作來防止安全性事件，並進一步提升 Microsoft 產品的安全性。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p111">Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via <secure@microsoft.com>. MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.</span></span>

-   <span data-ttu-id="b29e8-162">說明歸因於 Microsoft Dynamics 365 服務之可疑活動 (而非客戶責任範圍內所發生的活動) 的客戶報告。</span><span class="sxs-lookup"><span data-stu-id="b29e8-162">Customer reports that describe suspicious activity attributed to the Microsoft Dynamics 365 Services (as opposed to activity occurring within the customer’s scope of responsibility).</span></span>

-   <span data-ttu-id="b29e8-p112">安全性[紅隊和藍隊](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活動。此策略利用了具有高度技巧的紅隊來找出並攻擊在 Microsoft Dynamics 365 服務中的潛在弱點，由 Microsoft 的攻擊性安全專家所組成。負責安全性回應的藍隊必須偵測並防禦紅隊的活動。我們會用紅隊和藍隊雙方的動作，來確認 Microsoft Dynamics 365 所做的安全性回應是否能有效地因應安全性事件。安全性紅隊和藍隊活動的執行皆符合責任的要求，以協助確保對客戶資料的保護。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p112">Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly-skilled Red team of offensive security experts to uncover and attack potential weaknesses in Microsoft Dynamics 365 services. The security response Blue team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Microsoft Dynamics 365 security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under requirements of responsibility to help ensure the protection of customer data.</span></span>

-   <span data-ttu-id="b29e8-p113">Microsoft Dynamics 365 服務操作員的呈報。Microsoft 員工都受過訓練，可找出潛在的安全性問題並向上呈報。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p113">Escalations by operators of Microsoft Dynamics 365 services. Microsoft employees are trained to identify and escalate potential security issues.</span></span>

#### <a name="microsoft-dynamics-365-data-breach-response"></a><span data-ttu-id="b29e8-170">Microsoft Dynamics 365 資料外洩回應</span><span class="sxs-lookup"><span data-stu-id="b29e8-170">Microsoft Dynamics 365 Data Breach Response</span></span>

<span data-ttu-id="b29e8-p114">Microsoft 會判斷功能性影響、復原能力和事件的資訊影響，來指派適當的調查優先順序及嚴重性等級。在調查過程中，優先順序和嚴重性都有可能因為新的發現和結論而變更。涉及對客戶資料有迫切或經確認風險的安全性事件，我們會視為高嚴重性而不眠不休地設法解決。Microsoft Dynamics 365 將隱私權缺口定義為「線上服務使用者或 Microsoft 員工個人資料」的漏洞。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p114">Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft Dynamics 365 defines privacy breach as a breach of “personal data of an online service end user or Microsoft employees.”</span></span>

<span data-ttu-id="b29e8-p115">安全性回應小組會與 Microsoft Dynamics 365 安全性工程師及主題專家 (SME) 合作，根據證據的事實資料將事件分類。安全性事件可以歸類為：</span><span class="sxs-lookup"><span data-stu-id="b29e8-p115">The Security Response Team works with Microsoft Dynamics 365 Security Engineers and Subject Matter Experts (SMEs) to classify the event based on factual data from the evidence. A security event may be classified as:</span></span>

-   <span data-ttu-id="b29e8-p116">**誤判：** 事件符合偵測準則，但經查明其實是正常商業活動的一部分，且可能需要進行篩選。服務小組會找出誤判的根本原因，並以系統化的方式視需要運用偵測來源和進行微調，<span id="_Toc350859432" class="anchor"></span>來解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p116">**False Positive:** An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-<span id="_Toc350859432" class="anchor"></span>tuning them as needed.</span></span>

-   <span data-ttu-id="b29e8-179">**安全性事件：** 有人非法存取任何儲存在 Microsoft 設備或 Microsoft 設施上的客戶資料或支援資料，或未經授權存取這類設備或設施，進而造成客戶資料或支援資料遺失、洩漏或變更的事件。</span><span class="sxs-lookup"><span data-stu-id="b29e8-179">**Security Incident:** An incident where unlawful access to any Customer Data or Support Data stored on Microsoft’s equipment or in Microsoft’s facilities, or unauthorized access to such equipment or facilities resulting in loss, disclosure, or alteration of Customer Data or Support Data has occurred.</span></span>

-   <span data-ttu-id="b29e8-180">**須向客戶報告的安全性事件 (CRSI)：** 有人非法或未經授權存取或使用 Microsoft 系統、設備或設施，導致客戶資料洩漏、修改或遺失。</span><span class="sxs-lookup"><span data-stu-id="b29e8-180">**Customer-Reportable Security Incident (CRSI):** Unlawful or unauthorized access to or use of Microsoft’s systems, equipment, or facilities resulting in disclosure, modification, or loss of customer data.</span></span>

-   <span data-ttu-id="b29e8-p117">**隱私權事件：** 涉及個人資料的安全性事件之子類型。處理程序與安全性事件沒有差別。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p117">**Privacy Incident:** A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.</span></span>

<span data-ttu-id="b29e8-p118">若要宣告 CRSI，Microsoft 必須先判斷客戶資料已遭到或很有可能已遭到未經授權的存取，且 (或) 有必須通知客戶的法律或合約承諾。雖然並非必要，但您最好了解對特定客戶的影響、資源存取與修復步驟。通常要等到安全性事件的診斷階段結束後，才會宣告事件屬於 CRSI。不過，在所有直接相關的資訊都可供使用時，也可能會隨時宣告。安全性事件管理員必須找出確鑿的證據，足以支持的確發生了須向客戶報告的事件，以開始執行客戶事件通知程序。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p118">For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.</span></span>

<span data-ttu-id="b29e8-p119">在整個調查過程中，安全性回應小組都會與全球的法律顧問密切合作，以協助確保根據法律義務與對客戶的承諾而執行鑑識。其中對於在各種作業環境下檢視及處理系統和客戶資料也有重要的限制。未得到對應的事件票證中所記錄之事件管理員的明確書面核准前，不得將敏感性或機密資料以及客戶資料傳輸出去。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p119">Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket.</span></span>

<span data-ttu-id="b29e8-p120">Microsoft 會確認是否已成功遏制客戶和商業風險，並實施了矯正措施。如有需要，會進行緊急風險降低步驟，以解決與事件關聯的迫切安全性風險。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p120">Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken.</span></span>

<span data-ttu-id="b29e8-193">Microsoft 也會完成資料外洩的內部檢討。</span><span class="sxs-lookup"><span data-stu-id="b29e8-193">Microsoft also completes an internal post-mortem for data breaches.</span></span> <span data-ttu-id="b29e8-194">在此過程中，會評估回應的充分程度和作業程序，並找出和實施 Microsoft 內部安全性原則或相關程序所需的任何更新。</span><span class="sxs-lookup"><span data-stu-id="b29e8-194">As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to Microsoft’s internal security policies or related processes are identified and implemented.</span></span> <span data-ttu-id="b29e8-195">資料外洩的內部檢討是不提供給客戶的高度機密記錄。</span><span class="sxs-lookup"><span data-stu-id="b29e8-195">Internal postmortems for data breaches are highly confidential records not available to customers.</span></span> <span data-ttu-id="b29e8-196">但是，可將檢討節錄並包含在其他客戶事件的通知中。</span><span class="sxs-lookup"><span data-stu-id="b29e8-196">Postmortems may, however, be summarized and included in other customer event notifications.</span></span> <span data-ttu-id="b29e8-197">在 Dynamics 365 的例行稽核週期中，會向外部稽核者提供這些報告以供審查。</span><span class="sxs-lookup"><span data-stu-id="b29e8-197">These reports are provided to external auditors for review as part of Dynamics 365 routine audit cycle.</span></span>

#### <a name="customer-notification"></a><span data-ttu-id="b29e8-198">客戶通知</span><span class="sxs-lookup"><span data-stu-id="b29e8-198">Customer Notification</span></span>

<span data-ttu-id="b29e8-p122">Microsoft Dynamics 365 依要求會向客戶和法規機構通知資料外洩。Microsoft 仰賴在 Dynamics 365 服務操作上進行大量的內部劃分。資料流記錄也相當健全。此設計的好處是可以將大部分的事件限制在特定客戶的範圍內。目標是讓受影響客戶的資料遭到外洩時，提供他們正確、實用且及時的通知。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p122">Microsoft Dynamics 365 notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of Dynamics 365 services. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached.</span></span>

<span data-ttu-id="b29e8-p123">在宣告 CRSI 後，我們會以最快的速度進行通知程序，同時仍顧及在快速行動下的安全性風險。通常，正在進行事件調查時，就會開始草擬通知。*除了*下列情況，從我們宣告有缺口算起，就會盡快傳送客戶通知：</span><span class="sxs-lookup"><span data-stu-id="b29e8-p123">The notification process upon a declared CRSI will occur as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered promptly from the time we declared a breach *except* for the following circumstances:</span></span>

-   <span data-ttu-id="b29e8-p124">Microsoft 相信執行通知的動作會增加其他客戶的風險。比方說，通知的動作可能會驚動攻擊者，因而無法補救。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p124">Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.</span></span>

-   <span data-ttu-id="b29e8-209">經 Microsoft 法務部門和事件執行經理審查過的其他不尋常或特殊情況。</span><span class="sxs-lookup"><span data-stu-id="b29e8-209">Other unusual or extreme circumstances vetted by Microsoft’s legal department and the Executive Incident Manager.</span></span>

<span data-ttu-id="b29e8-210">Microsoft Dynamics 365 可提供客戶詳細資訊，讓他們能執行內部調查，並協助他們符合對使用者的承諾，而不會過度延遲通知程序。</span><span class="sxs-lookup"><span data-stu-id="b29e8-210">Microsoft Dynamics 365 provides customers with detailed information enabling them to perform internal investigations and assisting them in meeting end user commitments, while not unduly delaying the notification process.</span></span>

<span data-ttu-id="b29e8-p125">系統會以 Microsoft 選取的任何方式 (包括透過電子郵件)，將個人資料外洩的通知傳送給客戶。系統會將資料外洩的通知傳送至 Office 安全中心中提供的客戶連絡人/系統管理員清單 (僅限受影響租用戶)，此清單可由客戶/租用戶系統管理員進行設定。為了確保可順利傳送通知，客戶有責任確保每個訂用帳戶和線上服務入口網站上的管理連絡人資訊是正確的。</span><span class="sxs-lookup"><span data-stu-id="b29e8-p125">Notification of a personal data breach will be delivered to the customer by any means Microsoft selects, including via email. Notification of a data breach will be delivered to the list of customer contacts/ admins (only affected tenants) provided in Office Security Center, which is configurable by the customer/ tenant admin. To ensure that notification can be successfully delivered, it is the customer’s responsibility to ensure that the administrative contact information on each applicable subscription and online services portal is correct.</span></span>

<span data-ttu-id="b29e8-p126">Microsoft Dynamics 365 小組也可以選擇通知客戶服務 (CSS) 和客戶帳戶管理員 (AM)，或技術帳戶管理員 (TAM) 等其他 Microsoft 人員。這些人員通常與客戶有密切的關係，也有助於快速進行補救。<span id="_Appendix_A" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="b29e8-p126">The Microsoft Dynamics 365 team may also elect to notify additional Microsoft personnel such as Customer Service (CSS) and the customer’s Account Manager(s) (AM) or Technical Account Manager(s) (TAM). These individuals often have close relationships with the customer and can facilitate faster remediation.<span id="_Appendix_A" class="anchor"></span></span></span>

#### <a name="learn-more"></a><span data-ttu-id="b29e8-215">深入了解</span><span class="sxs-lookup"><span data-stu-id="b29e8-215">Learn more</span></span>
[<span data-ttu-id="b29e8-216">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="b29e8-216">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)