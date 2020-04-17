---
title: Office 365 中的修復動作自動化調查和回應
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 深入瞭解 Office 365 Advanced 威脅防護方案2中自動化調查和回應功能的修復動作。
ms.openlocfilehash: d0f08c3e89882e21263c18246612949ea68ac1ad
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528926"
---
# <a name="remediation-actions-in-office-365"></a>Office 365 中的修復動作

## <a name="remediation-actions"></a>補救動作

Office 365 中的[自動化調查和回應功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)（AIR）[高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（Office 365 ATP）方案2包含某些修正動作。 當自動調查執行或完成時，您通常會看到一或多項修正動作需要由安全性作業小組進行核准，才能繼續進行。 這類修正動作可包含下列專案：

- 虛刪除電子郵件訊息或群集
- 封鎖 URL (點擊時)
- 關閉外部郵件轉寄
- 關閉委派

> [!NOTE]
> 在 Office 365 ATP 中，自動化調查不會自動修正。 只有組織的安全小組核准時，才會採取補救措施。

## <a name="threats-and-remediation-actions"></a>威脅和修正動作

下表摘要說明 Office 365 ATP 中的威脅及適當的修復動作。 在某些情況下，自動化調查不會產生特定的修復動作。 您的安全性運作小組可以進一步調查並採取適當的動作，如下表所述。

||||
|---|---|---|
|**類別**|**威脅/風險**|**修正動作**|
|電子郵件|惡意程式碼| Soft delete email/cluster <br/><br/>如果叢集中的電子郵件超過少數幾個包含惡意程式碼，則該叢集會被視為惡意。|
|電子郵件|惡意 URL<br/>（ [Office 365 ATP 安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works)偵測到惡意 URL。）|Soft delete email/cluster <br/><br/>包含惡意 URL 的電子郵件被視為惡意的電子郵件。|
|電子郵件|釣魚| Soft delete email/cluster <br/><br/>如果叢集中的電子郵件超過許多電子郵件中的網路嘗試次數，則會將該叢集視為網路釣魚。|
|電子郵件|Zapped 網路釣魚 <br/>（電子郵件訊息已傳遞和[zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)。）|Soft delete email/cluster <br/><br/>報告可用於查看 zapped 訊息。 [查看 ZAP 是否移動了郵件和 FAQs](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message)。|
|電子郵件|使用者[報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)未接的網路釣魚電子郵件| [使用者的報告所觸發的自動調查](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|電子郵件|大量反常 <br/>（最近的電子郵件數量超過先前的7-10 天，以符合準則）。|自動調查不會產生特定的擱置中動作。 <br/><br/>大量的反常威脅並非明確威脅，但只是最近一天的電子郵件磁片區（與過去的7-10 天相比）的指示。 雖然這可能表示潛在問題，但在惡意 verdicts 或手動複查電子郵件訊息/叢集時，需要確認。 請參閱[尋找和刪除已傳遞的可疑電子郵件](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered)。|
|電子郵件|找不到威脅 <br/>（根據電子郵件叢集 verdicts 的檔案、url 或分析，系統找不到任何威脅。）|自動調查不會產生特定的擱置中動作。 <br/><br/>調查完成之後發現和[zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)的威脅不會反映在調查的數值結果中，但威脅[瀏覽器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)中可查看此類威脅。|
|使用者|使用者按一下了惡意 URL <br/>（流覽至後來發現為惡意的頁面的使用者，或使用者略過 [[安全連結] 警告頁面](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages)以取得惡意頁面）。|自動調查不會產生特定的擱置中動作。 <br/><br/>使用威脅瀏覽器來[查看有關 URLs 的資料，然後按一下 [verdicts](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict)]。 <br/><br/>如果您的組織使用[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/)，請考慮[調查使用者](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)，以判斷其帳戶是否遭到破壞。|
|使用者|使用者正在傳送惡意程式碼/網路釣魚|自動調查不會產生特定的擱置中動作。 <br/><br/>使用者可能會報告惡意程式碼/網路釣魚，或可能有人在攻擊中[哄騙使用者](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection)。 使用[威脅瀏覽器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)來查看及處理包含[惡意](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware)代碼或[網路釣魚](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)的電子郵件。|
|使用者|電子郵件轉寄 <br/>（已設定信箱轉寄規則，可供資料 exfiltration 使用。）|移除轉移規則 <br/><br/>使用[郵件流程真知灼見](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)（包括[自動轉寄的郵件報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)），以查看更多有關轉寄電子郵件的詳細資訊。|
|使用者|電子郵件委派規則 <br/>（使用者的帳戶已設定委派。）|移除委派規則 <br/><br/> 如果您的組織使用[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/)，請考慮調查取得委派許可權[的使用者](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)。|
|使用者|資料 exfiltration<br/>（使用者違反電子郵件或檔共用[DLP 原則](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)）。|自動調查不會產生特定的擱置中動作。 <br/><br/>[查看 DLP 報告並採取動作](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)。|
|使用者|反常電子郵件傳送 <br/>（最近一次7-10 天內，使用者最近傳送過的電子郵件。）|自動調查不會產生特定的擱置中動作。 <br/><br/>傳送大量電子郵件本身並非惡意的電子郵件;使用者可能只會將電子郵件傳送給一大群組的事件。 若要進行調查，請使用[郵件流程真知灼見](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)，包含[郵件流程對應報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report)，以判斷要進行的動作和採取的動作。|
|

## <a name="next-steps"></a>後續步驟

- [在 Office 365 中查看自動調查的詳細資料和結果](air-view-investigation-results.md)

- [在 Office 365 中進行自動調查後，查看擱置或已完成的修復動作](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>相關文章

- [Microsoft Defender 高級威脅防護中的自動調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [深入瞭解 Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
