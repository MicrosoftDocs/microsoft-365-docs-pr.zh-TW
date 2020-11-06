---
title: GDPR 規定的 Azure 和 Dynamics 365 外洩通知
description: Azure 和 Dynamics 365 如何防止個人資料外洩，以及若發生外洩 Microsoft 會如何回應和通知您。
keywords: Azure, Microsoft 365, Dynamics 365, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920256"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>GDPR 規定的 Azure 和 Dynamics 365 外洩通知

Microsoft Azure 十分重視歐盟一般資料保護規範 (GDPR) 所規定的義務。Microsoft Azure 採取了大量的安全性措施，以防範資料外洩的威脅。這包含實體和邏輯兩方面的安全性控制，和自動化的安全性程序、完整的資訊安全與隱私權原則，以及所有人員的安全性與隱私權教育訓練。

從一開始 Microsoft Azure 內就已內建各種安全機制，首先是[安全性開發週期](https://www.microsoft.com/sdl/)這項強制性開發程序，結合了「從設計著手保護隱私」和「預設為保護隱私」。Microsoft 安全性策略的最高指導原則是「假設已有缺口」，這是深度防禦策略的延伸。不斷挑戰 Azure 的安全性功能，Microsoft 才能先發制人，對抗接踵而來的新威脅。如需有關 Azure 安全性的詳細資訊，請參閱以下[資源](https://www.microsoft.com/trustcenter/security/azure-security)。

Microsoft 設有遍布全球的全天候事件回應服務，努力減少針對 Microsoft Azure 的攻擊所造成的影響。Microsoft 在資料中心採用了極為嚴密的作業和程序，以避免未經授權的存取，包括全天候的視訊監控、訓練精良的安全人員、智慧卡和生物特徵辨識控制等，通過多重安全性與合規性稽核 (例如 [ISO/IEC 27018](offering-iso-27018.md)) 的驗證。

## <a name="detection-of-potential-breaches"></a>偵測潛在缺口

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure 也提供各種不同的服務 (例如，[Azure Defender](https://azure.microsoft.com/services/security-center/))，客戶可以用來開發和管理安全性事件回應。

Azure 會根據安全性事件回應程序 (也就是 Microsoft Azure 事件管理計劃的子集) 回應潛在的資料外洩。系統會使用以下五個階段程序來實作 Azure 安全性事件回應：偵測、評估、診斷、穩定，及關閉。安全性事件回應小組可能會隨著調查進度輪流進行診斷和穩定。安全性事件回應程序的概觀說明如下：

|**Stage**|**描述**|
| ------- | ------------- |
| **_1 — 偵測_* _ | 潛在事件的第一個徵兆。 |
| _*_2 — 評估_*_ | 待命事件回應小組成員會評估事件的影響和嚴重性。取決於證據，可能會也可能不會進一步向安全性回應小組呈報評估。 |
| _*_3 — 診斷_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — 穩定及復原_*_ | 事件回應小組會建立復原計劃，以降低問題的風險。危機抑制步驟 (例如隔離受影響的系統) 可能會立即與診斷同步進行。長期風險降低預計要等到眼前的風險過後才會進行規劃。 |
| _*_5 — 結案與檢討_*_ | 事件回應小組會建立概述事件詳細資訊的檢討，目的是修改原則、步驟和流程，以避免該事件再次發生。 |

《[Microsoft Azure 在雲端的安全性回應](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678)》白皮書進一步詳述 Microsoft 在 Azure 中調查、管理以及回應安全性事件的方式。

Microsoft Azure 使用的偵測程序旨在探索會讓 Azure 服務的機密性、完整性和可用性遭受風險的事件。有數種事件可能會觸發調查：

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- 來自 Microsoft Azure 和 Azure Government 上所執行 Microsoft 服務的第一方報告。
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- 透過[客戶支援入口網站](https://www.windowsazure.com/support/contact/)或 Microsoft Azure 與 Azure Government 管理入口網站回報的客戶報告，其中說明了歸因於 Azure 基礎結構的可疑活動 (而非客戶責任範圍內所發生的活動)。
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Azure 服務作業員的呈報。Microsoft 員工都受過訓練，可找出潛在的安全性問題並向上呈報。

## <a name="azures-data-breach-response"></a>Azure 的資料外洩回應

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

Microsoft Azure 將事件的資訊影響分成下列缺口類別：

| _ *類別**             | **定義**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_無_* _               | 沒有任何資訊遭到挾帶、變更、刪除或以其他方式洩漏出去。                                                      |
| _*_隱私權缺口_*_     | 納稅人、員工、受益人等的敏感性個人資料遭人存取或挾帶出去。                                |
| _*_專利缺口_*_ | 非機密專利資訊 (例如受保護的關鍵基礎結構資訊 (PCII) 等) 遭人存取或挾帶出去。 |
| _*_完整性受損_*_     | 敏感性或專利資訊遭人變更或刪除。                                                                     |

安全性回應小組會與 Microsoft Azure 安全性工程師及主題專家 (SME) 合作，根據證據的事實資料將事件分類。安全性事件可以歸類為：

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **安全性事件** ：有人非法存取任何儲存在 Microsoft 設備或 Microsoft 設施上的客戶資料或支援資料，或未經授權存取這類設備或設施，進而造成客戶資料或支援資料遺失、洩漏，或變更的事件。
- **須向客戶報告的安全性/ 隱私權事件 (CRSPI)：** 有人非法或未經授權存取或使用 Microsoft 系統、設備或設施，導致客戶資料洩漏、修改或遺失。
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

在整個調查過程中，安全性回應小組都會與全球的法律顧問密切合作，以協助確保根據法律義務與對客戶的承諾而執行鑑識。其中對於在各種作業環境下檢視及處理系統和客戶資料也有重要的限制。未得到對應的事件票證中所記錄之事件管理員的明確書面核准前，不得將敏感性或機密資料以及客戶資料傳輸出去。

Microsoft 會確認是否已成功遏制客戶和商業風險，並實施了矯正措施。如有需要，會進行緊急風險降低步驟，以解決與事件關聯的迫切安全性風險。

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>客戶通知

Microsoft Azure 依要求會向客戶和法規機構通知資料外洩。Microsoft 仰賴在 Azure 作業上進行大量的內部劃分。資料流記錄也相當健全。此設計的好處是可以將大部分的事件限制在特定客戶的範圍內。目標是讓受影響客戶的資料遭到外洩時，提供他們正確、實用且及時的通知。

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- 經 Microsoft 法務部門企業外部和法律事務 (CELA) 和事件執行經理審查過的其他不尋常或特殊情況。
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

Microsoft Azure 可提供客戶詳細資訊，讓他們能執行內部調查，並協助他們符合對使用者的承諾，而不會過度延遲通知程序。

系統會以 Microsoft 選擇的任何方式 (包括透過電子郵件) 將個人資料外洩的通知傳送給客戶。系統會將資料外洩的通知，傳送給 Azure 資訊安全中心所提供的安全性連絡人清單；您可遵循[實作方針](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)來設定此清單。若 Azure Defender 未提供連絡人資訊，則會將通知傳送給 Azure 訂用帳戶中的一或多個系統管理員。為了確保可順利傳送通知，客戶有責任確保每個訂用帳戶和線上服務入口網站上的管理連絡人資訊是正確的。

Microsoft Azure 或 Azure Government 小組也可以選擇通知客服 (CSS) 和客戶專案經理 (AM)，或技術支援專案經理 (TAM) 等其他 Microsoft 人員。 這些人員通常與客戶有密切的關係，也有助於快速進行補救

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 內建的安全性功能

Microsoft Dynamics 365 利用雲端服務基礎結構和內建安全性功能，確保使用安全性措施和機制來保護資料的安全。此外，Dynamics 365 在下列領域中提供有效資料存取和對資料完整性及隱私權的共同作業：[保護身分識別、資料保護、角色型安全性與威脅管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。

Microsoft Dynamics 365 供應項目遵循相同的技術與組織措施，可評估一或多個 Microsoft Azure 服務小組的資料安全資料外洩程序。 因此，記錄在「Microsoft Azure 資料外洩」通知文件中的任何資訊也類似於 Microsoft Dynamics 365 服務。

## <a name="learn-more"></a>深入了解

[Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
