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
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a>GDPR 規定的 Dynamics 365 和外洩通知

Dynamics 365 很認真看待其在一般資料保護規定 (GDPR) 下所需承擔的責任。 Microsoft 不斷努力為 Dynamics 365 客戶提供高度安全的企業級服務。 本節中的資訊提供 Microsoft Dynamics 365 如何保護客戶免於安全性事件/資料外洩的摘要，以及在回應和告知客戶時我們所遵循的程序。

#### <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 內建的安全性功能

Microsoft Dynamics 365 利用雲端服務基礎結構和內建安全性功能，確保使用安全性措施和機制來保護資料的安全。此外，Dynamics 365 在下列領域中提供有效資料存取和對資料完整性及隱私權的共同作業：[保護身分識別、資料保護、角色型安全性與威脅管理](https://www.microsoft.com/trustcenter/security/dynamics365-security)。

#### <a name="incident-response-training"></a>事件回應訓練

使用 Microsoft Dynamics 365 的每位員工，都會獲得適用於其角色的安全性事件和回應程序訓練。每位 Microsoft Dynamics 365 員工在加入時都會接受訓練，之後每年也會接受進修課程訓練。該訓練旨在讓員工對 Microsoft 的安全處理方法有基本了解；因此在訓練完成後，所有的員工會了解到：

-   安全性事件的定義；

-   所有員工都有報告安全性事件的責任；

-   如何將潛在的安全性事件呈報給 Dynamics 365 安全性事件回應小組；

-   Dynamics 365 安全性事件回應小組如何回應安全性事件；

-   關於隱私權的特殊問題 (尤其是客戶隱私權)；

-   在何處可以找到關於安全性和隱私權及呈報連絡人的其他資訊。

#### <a name="how-does-microsoft-dynamics-365-define-security-incident-potential-breaches"></a>Microsoft Dynamics 365 如何定義安全性事件/潛在缺口

安全性事件/資料外洩，指的是有人非法存取儲存在 Microsoft 設備上或 Microsoft 設施中的客戶資料等事件，或未經授權存取這類設備或設施，進而造成客戶資料或支援資料遺失、洩漏或變更的事件。Microsoft 在回應安全性事件/資料外洩時的目標，即是保護客戶資料和 Dynamics 365 服務。Microsoft 管理安全性事件的方法符合[美國國家標準暨技術研究院](https://www.nist.gov/) (NIST) 特殊出版物 (SP) [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) 中的規定。

Microsoft 不會監視或回應屬客戶責任領域範圍內的安全性事件。系統不會將客戶單方面的安全性洩漏當作 Dynamics 365 安全性事件來處理，且這類洩漏需要客戶租用戶來管理回應工作。客戶事件回應可能會考量適當的服務合約，與 Microsoft Dynamics 365 客戶支援共同作業。

#### <a name="detection-of-potential-breaches"></a>偵測潛在缺口

Dynamics 365 會根據安全性事件回應程序 (也就是 Microsoft Dynamics 365 事件管理計劃的子集) 回應潛在的資料外洩。系統會使用以下五階段的程序來實作 Dynamics 365 安全性事件回應：偵測、評估、診斷、穩定與結案。安全性事件回應小組可能會隨著調查進度輪流進行診斷和穩定階段。安全性事件回應程序的概觀說明如下：

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">階段</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">偵測</td>
<td align="left">事件調查的第一個指示。</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">評估</td>
<td align="left">待命事件回應小組成員會評估事件的影響和嚴重性。取決於證據，可能會也可能不會進一步向安全性回應小組呈報評估。</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">診斷/調查</td>
<td align="left"><p>安全性回應專家進行技術或鑑定調查、找出內含項目、風險降低及因應措施策略。</p>
<p>若安全性小組相信客戶資料可能遭受非法或未經授權的人員存取，將會同步進行客戶事件通知程序。</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">穩定及復原</td>
<td align="left">事件回應小組會建立復原計劃，以降低問題的風險。危機抑制步驟 (例如隔離受影響的系統) 可能會立即與診斷同步進行。長期風險降低預計要等到眼前的風險過後才會進行規劃。</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">結案與檢討</td>
<td align="left">事件回應小組會建立概述事件詳細資訊的檢討，目的是修改原則、步驟和流程，以避免該事件再次發生。</td>
</tr>
</tbody>
</table>

《[動態安全性事件管理](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)》白皮書 (英文) 會進一步詳述 Microsoft 在 Dynamics 365 中調查、管理以及回應安全性事件的方式。

Microsoft Dynamics 365 使用的偵測程序旨在探索會讓 Dynamics 365 服務的機密性、完整性和可用性遭受風險的事件。有數種事件可能會觸發調查：

-   自動化系統透過內部監視和警示架構發出警示。這些警示會以病毒碼式警訊 (例如反惡意程式碼軟體、入侵偵測)，或透過旨在分析預期活動並在異常時發出警示的演算法等方式提供。

-   第一方報告在公用雲端中部署的執行中 Microsoft Dynamics 365 服務，以及在主權雲端中部署的 Microsoft Dynamics 365 服務。

-   [Microsoft 安全性回應中心 (MSRC)](https://technet.microsoft.com/security/dn440717) 收到透過 <secure@microsoft.com> 所回報的安全性漏洞。MSRC 會與合作夥伴及全球安全性研究人員合作來防止安全性事件，並進一步提升 Microsoft 產品的安全性。

-   說明歸因於 Microsoft Dynamics 365 服務之可疑活動 (而非客戶責任範圍內所發生的活動) 的客戶報告。

-   安全性[紅隊和藍隊](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)活動。此策略利用了具有高度技巧的紅隊來找出並攻擊在 Microsoft Dynamics 365 服務中的潛在弱點，由 Microsoft 的攻擊性安全專家所組成。負責安全性回應的藍隊必須偵測並防禦紅隊的活動。我們會用紅隊和藍隊雙方的動作，來確認 Microsoft Dynamics 365 所做的安全性回應是否能有效地因應安全性事件。安全性紅隊和藍隊活動的執行皆符合責任的要求，以協助確保對客戶資料的保護。

-   Microsoft Dynamics 365 服務操作員的呈報。Microsoft 員工都受過訓練，可找出潛在的安全性問題並向上呈報。

#### <a name="microsoft-dynamics-365-data-breach-response"></a>Microsoft Dynamics 365 資料外洩回應

Microsoft 會判斷功能性影響、復原能力和事件的資訊影響，來指派適當的調查優先順序及嚴重性等級。在調查過程中，優先順序和嚴重性都有可能因為新的發現和結論而變更。涉及對客戶資料有迫切或經確認風險的安全性事件，我們會視為高嚴重性而不眠不休地設法解決。Microsoft Dynamics 365 將隱私權缺口定義為「線上服務使用者或 Microsoft 員工個人資料」的漏洞。

安全性回應小組會與 Microsoft Dynamics 365 安全性工程師及主題專家 (SME) 合作，根據證據的事實資料將事件分類。安全性事件可以歸類為：

-   **誤判：** 事件符合偵測準則，但經查明其實是正常商業活動的一部分，且可能需要進行篩選。服務小組會找出誤判的根本原因，並以系統化的方式視需要運用偵測來源和進行微調，<span id="_Toc350859432" class="anchor"></span>來解決這些問題。

-   **安全性事件：** 有人非法存取任何儲存在 Microsoft 設備或 Microsoft 設施上的客戶資料或支援資料，或未經授權存取這類設備或設施，進而造成客戶資料或支援資料遺失、洩漏或變更的事件。

-   **須向客戶報告的安全性事件 (CRSI)：** 有人非法或未經授權存取或使用 Microsoft 系統、設備或設施，導致客戶資料洩漏、修改或遺失。

-   **隱私權事件：** 涉及個人資料的安全性事件之子類型。處理程序與安全性事件沒有差別。

若要宣告 CRSI，Microsoft 必須先判斷客戶資料已遭到或很有可能已遭到未經授權的存取，且 (或) 有必須通知客戶的法律或合約承諾。雖然並非必要，但您最好了解對特定客戶的影響、資源存取與修復步驟。通常要等到安全性事件的診斷階段結束後，才會宣告事件屬於 CRSI。不過，在所有直接相關的資訊都可供使用時，也可能會隨時宣告。安全性事件管理員必須找出確鑿的證據，足以支持的確發生了須向客戶報告的事件，以開始執行客戶事件通知程序。

在整個調查過程中，安全性回應小組都會與全球的法律顧問密切合作，以協助確保根據法律義務與對客戶的承諾而執行鑑識。其中對於在各種作業環境下檢視及處理系統和客戶資料也有重要的限制。未得到對應的事件票證中所記錄之事件管理員的明確書面核准前，不得將敏感性或機密資料以及客戶資料傳輸出去。

Microsoft 會確認是否已成功遏制客戶和商業風險，並實施了矯正措施。如有需要，會進行緊急風險降低步驟，以解決與事件關聯的迫切安全性風險。

Microsoft 也會完成資料外洩的內部檢討。 在此過程中，會評估回應的充分程度和作業程序，並找出和實施 Microsoft 內部安全性原則或相關程序所需的任何更新。 資料外洩的內部檢討是不提供給客戶的高度機密記錄。 但是，可將檢討節錄並包含在其他客戶事件的通知中。 在 Dynamics 365 的例行稽核週期中，會向外部稽核者提供這些報告以供審查。

#### <a name="customer-notification"></a>客戶通知

Microsoft Dynamics 365 依要求會向客戶和法規機構通知資料外洩。Microsoft 仰賴在 Dynamics 365 服務操作上進行大量的內部劃分。資料流記錄也相當健全。此設計的好處是可以將大部分的事件限制在特定客戶的範圍內。目標是讓受影響客戶的資料遭到外洩時，提供他們正確、實用且及時的通知。

在宣告 CRSI 後，我們會以最快的速度進行通知程序，同時仍顧及在快速行動下的安全性風險。通常，正在進行事件調查時，就會開始草擬通知。*除了*下列情況，從我們宣告有缺口算起，就會盡快傳送客戶通知：

-   Microsoft 相信執行通知的動作會增加其他客戶的風險。比方說，通知的動作可能會驚動攻擊者，因而無法補救。

-   經 Microsoft 法務部門和事件執行經理審查過的其他不尋常或特殊情況。

Microsoft Dynamics 365 可提供客戶詳細資訊，讓他們能執行內部調查，並協助他們符合對使用者的承諾，而不會過度延遲通知程序。

系統會以 Microsoft 選取的任何方式 (包括透過電子郵件)，將個人資料外洩的通知傳送給客戶。系統會將資料外洩的通知傳送至 Office 安全中心中提供的客戶連絡人/系統管理員清單 (僅限受影響租用戶)，此清單可由客戶/租用戶系統管理員進行設定。為了確保可順利傳送通知，客戶有責任確保每個訂用帳戶和線上服務入口網站上的管理連絡人資訊是正確的。

Microsoft Dynamics 365 小組也可以選擇通知客戶服務 (CSS) 和客戶帳戶管理員 (AM)，或技術帳戶管理員 (TAM) 等其他 Microsoft 人員。這些人員通常與客戶有密切的關係，也有助於快速進行補救。<span id="_Appendix_A" class="anchor"></span>

#### <a name="learn-more"></a>深入了解
[Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)