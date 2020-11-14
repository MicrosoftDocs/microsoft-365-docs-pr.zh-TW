---
title: 適用於 GDPR 的 Windows 企業版資料處理者服務通知
description: Windows 企業版資料處理者服務如何防止個人資料外洩，以及若發生外洩 Microsoft 會如何回應和通知您。
keywords: Windows 企業版、Microsoft 365、Microsoft 365 文件、GDPR 的資料處理者服務
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: siosulli
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 5d0a5563de2443e5af0f3b7efda0947d4f669cee
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070897"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>適用於 GDPR 的 Windows 企業版資料處理者服務違反通知

>[!NOTE]
>This topic is intended for participants in the data processor service for Windows Enterprise preview program and requires acceptance of specific terms of use. To learn more about the program and agree to the terms of use, see [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Microsoft data processor service for Windows Enterprise takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft data processor service for Windows Enterprise takes extensive security measures to protect against data breaches. These include dedicated threat management teams that proactively anticipate, prevent, and mitigate malicious access.  Internal security measures such as port scanning, perimeter vulnerability scanning, and intrusion detection detect and prevent malicious access, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel. 

Security is built into the Microsoft data processor service for Windows Enterprise from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft's security strategy is to 'assume breach', which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of the data processor service for Windows Enterprise, Microsoft can stay ahead of emerging threats. For more information on the data processor service for Windows Enterprise security, please review these [resources](https://www.microsoft.com/TrustCenter/Security/windows10-security) the data processor service for Windows Enterprise responds to a potential data breach according to the security incident response process. The data processor service for Windows Enterprise security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below: 

|**Stage**|**描述**|
| ------- | ------------- |
| **_1 — 偵測_* _ | 潛在事件的第一個徵兆。 |
| _*_2 — 評估_*_ | 待命事件回應小組成員會評估事件的影響和嚴重性。取決於證據，可能會也可能不會進一步向安全性回應小組呈報評估。 |
| _*_3 — 診斷_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — 穩定及復原_*_ | 事件回應小組會建立復原計劃，以降低問題的風險。危機抑制步驟 (例如隔離受影響的系統) 可能會立即與診斷同步進行。長期風險降低預計要等到眼前的風險過後才會進行規劃。 |
| _*_5 — 結案與檢討_*_ | 事件回應小組會建立概述事件詳細資訊的事後剖析，目的是修改原則、步驟和流程，以避免該事件再次發生。 |

The detection processes used by Microsoft data processor service for Windows Enterprise are designed to discover events that risk the confidentiality, integrity, and availability of the data processor service for Windows Enterprise. Several events can trigger an investigation: 

 - Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
 - 來自 Microsoft Azure 和 Azure Government 上所執行 Microsoft 服務的第一方報告。
 - Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
 - 透過客戶支援入口網站或 Microsoft Azure 與 Azure Government 管理入口網站回報的客戶報告，其中說明了歸因於 Azure 基礎結構的可疑活動 (而非客戶責任範圍內所發生的活動)。
 - Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
 - Azure 服務作業員的呈報。Microsoft 員工都受過訓練，可找出潛在的安全性問題並向上呈報。

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Windows 企業版資料處理者服務的資料外洩回應。 

 Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft data processor service for Windows Enterprise categorizes the information impact of the incident into the following breach categories: 

| _ *類別**             | **定義**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_無_* _               | 沒有任何資訊遭到移除、變更、刪除或以其他方式洩漏出去。 |
| _*_隱私權缺口_*_     | 納稅人、員工、受益人等的敏感性個人資料遭人存取或移除。 |
| _*_專利缺口_*_ | 非機密專利資訊 (例如受保護的關鍵基礎結構資訊 (PCII) 等) 遭人存取或移除。 |
| _*_完整性受損_*_     | 敏感性或專利資訊遭人變更或刪除。 |

The Security Response Team works with Microsoft data processor service for Windows Enterprise Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as: 

 - _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-tuning them as needed. 
 - **安全性事件** ：有人非法存取任何儲存在 Microsoft 設備或 Microsoft 設施上的客戶資料或支援資料，或未經授權存取這類設備或設施，進而造成客戶資料或支援資料遺失、洩漏，或變更的事件。 
 - **須向客戶報告的安全性事件 (CRSI)** ：有人非法或未經授權存取或使用 Microsoft 系統、設備或設施，導致客戶資料洩漏、修改或遺失。 
 - **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident. 

 若要宣告 CRSI，Microsoft 必須先判斷客戶資料已遭到或很有可能已遭到未經授權的存取，且 (或) 有必須通知客戶的法律或合約承諾。雖然並非必要，但您最好了解對特定客戶的影響、資源存取與修復步驟。通常要等到安全性事件的診斷階段結束後，才會宣告事件屬於 CRSI。不過，在所有直接相關的資訊都可供使用時，也可能會隨時宣告。安全性事件管理員必須找出確鑿的證據，足以支持的確發生了須向客戶報告的事件，以開始執行客戶事件通知程序。 

在整個調查過程中，安全性回應小組都會與全球的法律顧問密切合作，以協助確保根據法律義務與對客戶的承諾而執行鑑識。其中對於在各種作業環境下檢視及處理系統和客戶資料也有重要的限制。未得到對應的事件票證中所記錄之事件管理員的明確書面核准前，不得將敏感性或機密資料以及客戶資料傳輸出去。 

Microsoft 會確認是否已成功遏制客戶和商業風險，並實施了矯正措施。如有需要，會進行緊急風險降低步驟，以解決與事件關聯的迫切安全性風險。 

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of the data processor service for Windows Enterprise routine audit cycle. 

## <a name="customer-notice"></a>客戶注意事項

Microsoft data processor service for Windows Enterprise notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of the data processor service for Windows Enterprise. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached. 

After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances: 

 - Microsoft 相信執行通知的動作會增加其他客戶的風險。比方說，通知的動作可能會驚動攻擊者，因而無法補救。 
 - 經 Microsoft 法務部門企業外部和法律事務 (CELA) 和事件執行經理審查過的其他不尋常或特殊情況。 

 Microsoft 的 Windows 企業版資料處理者服務可提供客戶詳細資訊，讓他們能執行內部調查，並協助他們符合對使用者的承諾，而不會過度延遲通知程序。 

系統會以 Microsoft 選擇的任何方式 (包括透過電子郵件) 將個人資料外洩的通知傳送給客戶。系統會將資料外洩的通知，傳送給 Azure 資訊安全中心所提供的安全性連絡人清單；您可遵循[實作方針](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)來設定此清單。若 Azure Defender 未提供連絡人資訊，則會將通知傳送給 Azure 訂用帳戶中的一或多個系統管理員。為了確保可順利傳送通知，客戶有責任確保每個訂用帳戶和線上服務入口網站上的管理連絡人資訊是正確的。

Windows 企業版資料處理者服務小組也可以選擇通知客服 (CSS) 和客戶專案經理 (AM)，或技術支援專案經理 (TAM) 等其他 Microsoft 人員。 這些人員通常與客戶有密切的關係，也有助於快速進行補救 

如需 Microsoft 如何偵測及回應個人資料外洩的詳細資訊，請參閱服務信任入口網站中的 [GDPR 規定的資料外泄通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)。
