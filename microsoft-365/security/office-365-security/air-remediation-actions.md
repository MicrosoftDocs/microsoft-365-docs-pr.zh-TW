---
title: Microsoft Defender for Office 365 中的自動調查後續修正動作
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 深入瞭解 Microsoft Defender for Office 365 中的自動調查後續修復動作。
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 74fe6f66d0970fe2725caba7b51bd8a95a34159e
ms.sourcegitcommit: 16e018f8b6eef5dad48eabf179691ead3cebe533
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2020
ms.locfileid: "49725162"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的自動調查後續修正動作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>補救動作

[Microsoft Defender For Office 365](office-365-atp.md) (AIR) 的[自動化調查和回應功能](office-365-air.md)包含某些修正動作。 每次正在執行自動調查或已完成時，您通常會看到一或多個需要由安全性作業團隊核准才能繼續執行的補救動作。 這類修正動作可包含下列專案：

- 虛刪除電子郵件訊息或群集
- 封鎖 URL (點擊時)
- 關閉外部郵件轉寄
- 關閉委派

> [!NOTE]
> 在適用于 Office 365 的 Microsoft Defender 中，自動化調查不會導致自動進行修正動作。 修正動作只會在組織的安全性運作小組核准時採取。

## <a name="threats-and-remediation-actions"></a>威脅和修正動作

下表摘要說明 Office 365 中的威脅及適當的修復動作。 在某些情況下，自動化調查不會產生特定的修復動作。 您的安全性運作小組可以進一步調查並採取適當的動作，如下表所述。

****

|類別|威脅/風險|修正動作 (s) |
|---|---|---|
|電子郵件|惡意程式碼|Soft delete email/cluster <br> 如果叢集中的電子郵件超過少數幾個包含惡意程式碼，則該叢集會被視為惡意。|
|電子郵件|惡意 URL <br>  ([Microsoft Defender For Office 365) 中的安全連結](atp-safe-links.md) 偵測到惡意 URL。|Soft delete email/cluster <p> 包含惡意 URL 的電子郵件被視為惡意的電子郵件。|
|電子郵件|網路釣魚|Soft delete email/cluster <br> 如果叢集中的電子郵件超過許多電子郵件中的網路嘗試次數，則會將該叢集視為網路釣魚。|
|電子郵件|Zapped 網路釣魚 <br>  (電子郵件已傳遞和 [zapped](zero-hour-auto-purge.md)。 ) |Soft delete email/cluster <p> 報告可用於查看 zapped 訊息。 [查看 ZAP 是否移動了郵件和 FAQs](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)。|
|電子郵件|使用者 [報告](enable-the-report-message-add-in.md) 未接的網路釣魚電子郵件|[使用者的報告所觸發的自動調查](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|電子郵件|大量反常 <br>  (最近的電子郵件數量超過上一個7-10 天的符合條件。 ) |自動調查不會產生特定的擱置中動作。 <p> 大量的反常威脅並非明確威脅，但只是最近一天的電子郵件磁片區（與過去的7-10 天相比）的指示。 雖然這可能表示潛在問題，但在惡意 verdicts 或手動複查電子郵件訊息/叢集時，需要確認。 請參閱 [尋找已傳遞的可疑電子郵件](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)。|
|電子郵件|找不到威脅 <br>  (系統未找到任何根據檔、url 或分析電子郵件叢集 verdicts 的威脅。 ) |自動調查不會產生特定的擱置中動作。 <p> 調查完成之後發現和 [zapped](zero-hour-auto-purge.md) 的威脅不會反映在調查的數值結果中，但威脅 [瀏覽器](threat-explorer.md)中可查看此類威脅。|
|使用者|使用者按一下了惡意 URL <br>  (流覽至後來發現為惡意的頁面的使用者，或使用者略過 [安全連結警告頁面](atp-safe-links.md#warning-pages-from-safe-links) 以取得惡意頁面。 ) |自動調查不會產生特定的擱置中動作。 <p> 使用威脅瀏覽器來 [查看有關 URLs 的資料，然後按一下 [verdicts](threat-explorer.md#view-phishing-url-and-click-verdict-data)]。 <p> 如果您的組織使用 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)，請考慮 [調查使用者](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) ，以判斷其帳戶是否遭到破壞。|
|使用者|使用者正在傳送惡意程式碼/網路釣魚|自動調查不會產生特定的擱置中動作。 <p> 使用者可能會報告惡意程式碼/網路釣魚，或可能有人在攻擊中 [哄騙使用者](anti-spoofing-protection.md) 。 使用 [威脅瀏覽器](threat-explorer.md) 來查看及處理包含 [惡意](threat-explorer-views.md#email--malware) 代碼或 [網路釣魚](threat-explorer-views.md#email--phish)的電子郵件。|
|使用者|電子郵件轉寄 <br> 已設定 (信箱轉寄規則，可用於資料 exfiltration。 ) |移除轉移規則 <p> 使用 [郵件流程真知灼見](mail-flow-insights-v2.md)（包括 [自動轉寄的郵件報告](mfi-auto-forwarded-messages-report.md)），以查看更多有關轉寄電子郵件的詳細資訊。|
|使用者|電子郵件委派規則 <br>  (使用者的帳戶已設定委派。 ) |移除委派規則 <p> 如果您的組織使用 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)，請考慮調查取得委派許可權 [的使用者](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 。|
|使用者|資料外流 <br>  (使用者違反電子郵件或檔共用 [DLP 原則](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。 ) |自動調查不會產生特定的擱置中動作。 <p> [查看 DLP 報告並採取動作](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)。|
|使用者|反常電子郵件傳送 <br>  (使用者最近一次7-10 天內傳送的電子郵件。 ) |自動調查不會產生特定的擱置中動作。 <p> 傳送大量電子郵件本身並非惡意的電子郵件;使用者可能只會將電子郵件傳送給一大群組的事件。 若要進行調查，請使用 [郵件流程真知灼見](mail-flow-insights-v2.md)，包含 [郵件流程對應報告](mfi-mail-flow-map-report.md) ，以判斷要進行的動作和採取的動作。|
|

## <a name="next-steps"></a>後續步驟

- [在 Microsoft Defender for Office 365 中查看自動調查的詳細資料和結果](air-view-investigation-results.md)

- [在 Microsoft Defender for Office 365 中進行自動調查後，查看擱置或已完成的修復動作](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>相關文章

- [深入瞭解 Microsoft Defender for Endpoint 中的自動調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [深入瞭解 Microsoft 365 Defender 中的其他功能](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
