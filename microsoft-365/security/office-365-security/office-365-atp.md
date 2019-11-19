---
title: Office 365 進階威脅防護
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 11/15/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 進階威脅防護包括安全附件、安全連結、進階防網路釣魚工具、報告工具以及威脅情報功能。
ms.openlocfilehash: abe11acd2b254405ec432288ae87d12b626f617c
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673409"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 進階威脅防護

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的企業客戶。 如果您使用 Outlook.com、Office 365 家用版或 Office 365 個人版，並且在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="overview"></a>概觀

Office 365 進階威脅防護 (ATP) 可保護組織防範由電子郵件訊息、連結 (URL) 及共同作業工具所造成的惡意威脅。 ATP 包括：

- [威脅防護原則](#configure-atp-policies)：定義威脅防護原則，用來為組織設定適當的保護層級。 

- [報告](#view-office-365-atp-reports)：檢視即時報告來監控組織中 ATP 的效能。 

- [威脅調查與回應功能](#use-threat-investigation-and-response-capabilities)：使用先進的工具來調查、了解、模擬以及防止潛在威脅。 

- [自動事件回應功能](#save-time-with-automated-incident-response)：節省調查和減輕威脅的時間和精力。

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP 方案 1 與方案 2

ATP 包含在 Office 365 E5 中；不過，Office 365 ATP 方案 1 和 Office 365 ATP 方案 2 各為附加元件形式提供某些訂閱使用。 若要深入了解，請參閱 [ATP 方案中功能的可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

如果您沒有 Office 365 ATP，[請開始免費試用](https://go.microsoft.com/fwlink/p/?LinkID=698279)。


## <a name="configure-atp-policies"></a>設定 ATP 原則

有了 Office 365 ATP，貴組織的安全性小組就能在 Office 365 安全與合規性中心中定義原則來設定防護 (請移至[https://protection.office.com](https://protection.office.com) > **威脅管理** > **原則**。) 

> [!TIP]
> 如需定義的原則快速清單，請參閱[防範威脅](protect-against-threats.md)。

為您組織定義的原則會決定預先定義之威脅的行為和保護層級。 原則選項極具彈性。 例如，組織的安全性小組也可以在使用者、組織、收件者和網域層級設定微調的威脅防護。 因為新威脅及挑戰每天都會出現，請務必定期檢閱您的原則。  

- [ATP 安全附件](atp-safe-attachments.md)：透過檢查電子郵件附件中的惡意內容，提供零時差保護，以保護您的郵件系統。 它會將沒有病毒/惡意程式碼簽章的所有郵件與附件路由傳送至特殊的環境，然後使用機器學習和分析技術來偵測惡意意圖。 如果找不到任何可疑的活動，便會將郵件轉寄到信箱。 若要深入了解，請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)。

- [ATP 安全連結](atp-safe-links.md)：提供 URL 的點擊時驗證 (例如在電子郵件訊息和 Office 檔案中)。 保護會持續進行，並在您郵件和 Office 環境間套用。 每次按一下連結時掃描：安全連結仍保持可存取，並且以動態方式封鎖惡意連結。 若要深入了解，請參閱[設定 Office 365 ATP 安全連結原則](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies)。 

- [適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)：透過找出並封鎖小組網站和文件庫中的惡意檔案，在使用者共同作業及共用檔案時保護您的組織。 若要深入了解，請參閱[為 SharePoint、OneDrive 和 Microsoft Teams 開啟 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。 

- [ATP 防網路釣魚保護](atp-anti-phishing.md)：偵測模擬使用者和自訂網域的嘗試。 適用於電腦學習模型和進階模擬偵測演算法，以避免網路釣魚攻擊。 若要深入了解，請參閱[設定 Office 365 ATP 防網路釣魚功能及防網路釣魚原則](set-up-anti-phishing-policies.md)。

## <a name="view-office-365-atp-reports"></a>查看 Office 365 ATP 報告

Office 365 ATP 包含進階的[報告儀表板](view-reports-for-atp.md)以監控 ATP 效能。 您可以在安全性與合規性中心的 [報告] **** >  [儀表板]**** 存取它。 

報告會即時更新，提供您最新的深入解析。 這些報告也提供建議並警示您即將發生的潛在威脅。 預先定義的報告包括下列： 

- [威脅總管 (或即時偵測)](threat-explorer.md)

- [威脅防護狀態報告](view-reports-for-atp.md#threat-protection-status-report)

- [ATP 檔案類型報告](view-reports-for-atp.md#atp-file-types-report)

- [ATP 郵件處置報告](view-reports-for-atp.md#atp-message-disposition-report)

- 還有更多。 

## <a name="use-threat-investigation-and-response-capabilities"></a>使用威脅調查及回應功能

Office 365 ATP 方案 2 中包含業界最佳[威脅調查及回應工具](office-365-ti.md)，可讓組織的安全性小組預期、了解和防止惡意攻擊。 

- [威脅追蹤工具](threat-trackers.md)提供有關戰勝網路安全性問題的最新情報。 例如，您可以檢視有關最新惡意程式碼的資訊，並在它成為組織的實際威脅之前便採取措施。 可用的追蹤器包括：[值得注意的追蹤器](threat-trackers.md#noteworthy-trackers)、[趨勢追蹤器](threat-trackers.md#trending-trackers)、[追蹤的查詢](threat-trackers.md#tracked-queries)和[已儲存的查詢](threat-trackers.md#saved-queries)。

- [威脅總管 (或即時偵測)](threat-explorer.md) (也稱為檔案總管) 是即時的報告，可讓您識別並分析最近的威脅。 您可以設定檔案總管來顯示自訂期間的資料。

- [攻擊模擬器](attack-simulator.md)可讓您在組織中執行真實化攻擊案例以找出漏洞。 目前攻擊類型的模擬可供使用，包括[顯示名稱魚叉式網路釣魚攻擊](attack-simulator.md#display-name-spear-phishing-attack)、[密碼噴濺攻擊](attack-simulator.md#password-spray-attack)、[暴力密碼破解攻擊](attack-simulator.md#brute-force-password-attack)等。
    
## <a name="save-time-with-automated-incident-response"></a>使用自動事件回應節省時間

(**新增！**) 調查潛在的網路攻擊時，時間是關鍵。 愈快找出並減輕威脅，您組織的處境會愈好。 [自動事件回應](automated-investigation-response-office.md) (AIR) 包含一組安全性劇本，可以自動啟動 (例如當警示觸發時)，或手動啟動 (例如從檔案總管中的檢視)。 AIR 可以在緩和威脅方面有效也有效率地節省您安全性作業小組的時間和精力。 若要深入瞭解，請參閱 [Office 365 中的自動事件回應](automated-investigation-response-office.md)。

## <a name="permissions-required-to-use-atp-features"></a>使用 ATP 功能所需的權限

若要存取安全性與合規性中心的 ATP 功能，您必須獲指派適當的角色。 下表包括一些範例：

|角色或角色群組  |可深入了解的資源  |
|---------|---------|
|Office 365 全域系統管理員 |[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|安全性系統管理員 |[Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織管理 |[Exchange Online 中的權限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>和<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

## <a name="get-office-365-atp"></a>取得 Office 365 ATP

Office 365 ATP 包含在某些訂閱中，例如 Microsoft 365 E5、Office 365 E5、Office 365 A5 和 Microsoft 365 商務版。 如果您的訂閱不包含 Office 365 ATP，您可以以附加元件形式為特定訂閱購買 ATP 方案 1 或 ATP 方案 2。 若要深入了解，請參閱下列資源：

- [Office 365 進階威脅防護 (ATP) 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)，以取得包含 ATP 方案的訂閱清單。

- [各進階威脅防護 (ATP) 計劃中可用的功能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)，以取得方案 1 和 2 中包含的功能清單。

- [取得適合的 Office 365 進階威脅防護](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)，以比較方案及購買 Office 365 ATP。

- [開始免費試用](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Office 365 ATP 中的新功能

新功能會持續新增至 Office 365 ATP。 若要深入了解，請參閱下列資源：

- [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供開發中和正在推出的新功能清單。

- [Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)描述各 ATP 方案的功能和可用性。
