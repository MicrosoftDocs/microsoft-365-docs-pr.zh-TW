---
title: 適用於 Office 365 的 Microsoft Defender
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 適用於 Office 365 的 Microsoft Defender 包括安全附件、安全連結、進階防網路釣魚工具、報告工具以及威脅情報功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 00dcd5d8f5d18b59de67318049cc1e5807451f14
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022351"
---
# <a name="microsoft-defender-for-office-365"></a>適用於 Office 365 的 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文適用於擁有[適用於 Office 365 的 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 的商務客戶。 如果您使用 Outlook.com、Microsoft 365 家用版或 Microsoft 365 個人版，並且在尋找 Outlook 中的安全連結或安全附件的相關資訊，請參閱[適用於 Microsoft 365 訂閱者的進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

適用於 Office 365 的 Microsoft Defender 可保護貴組織免於來自電子郵件訊息、連結 (URL)，與共同作業工具的惡意威脅。適用於 Office 365 的 Defender 包含:

- **[威脅防護原則](#configure-microsoft-defender-for-office-365-policies)**：定義威脅防護原則，用來為組織設定適當的保護層級。

- **[報告](#view-microsoft-defender-for-office-365-reports)**：檢視即時報告來監控組織中適用於 Office 365 的 Defender 的效能。

- **[威脅調查與回應功能](#use-threat-investigation-and-response-capabilities)**：使用先進的工具來調查、了解、模擬以及防止潛在威脅。

- **[自動化調查及回應功能](office-365-air.md)**：節省調查和減輕威脅的時間和精力。

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>適用於 Office 365 的 Microsoft Defender 互動式指南
在此互動式指南中，您將了解如何使用適用於 Office 365 的 Microsoft Defender 來保護貴組織的安全。 您會看到適用於 Office 365 的 Defender 如何協助您定義保護原則、分析組織面臨的威脅，以及回應攻擊。

[查看互動指南](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>快速入門

如果您剛開始使用適用於 Office 365 的 Microsoft Defender，或欲透過 *實際操作* 來了解，則您可以使用本文作為參考資料，將初始適用於 Office 365 的 Microsoft Defender 設定分成區塊、調查和檢視報告而從中受益。 以下是邏輯早期設定區塊:

- 設定名稱中含有「*反*」的所有專案。
  - 反惡意軟體
  - 反網路釣魚
  - 反垃圾郵件
- 設定名稱中含有「*安全*」的所有專案。
  - 安全連結
  - 安全附件
- 保護工作負載 (例如: SharePoint Online、OneDrive 和 Teams)
- 使用 [零時差自動清除] 進行保護

若要透過實際操作來瞭解，請 [按一下這個連結](protect-against-threats.md)。

> [!NOTE]
> 適用於 Office 365 的 Microsoft Defender 有兩種不同類型的方案。 如果您有「即時偵測」，則您具有 **方案 1** ，而如果你有「威脅瀏覽器」，則您具有 **方案 2**。 您所看到的 [方案] 會影響您能看到的工具，因此請確定您瞭解您的 [方案]。

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2

下表摘要列出每個方案所包含的內容。

****

|適用於 Office 365 的 Microsoft Defender 方案 1|適用於 Office 365 的 Microsoft Defender 方案 2|
|---|---|
|設定、保護和偵測功能： <ul><li>[安全附件](safe-attachments.md)</li><li>[安全連結](safe-links.md)</li><li>[適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)</li><li>[適用於 Office 365 的 Defender 中的反網路釣魚防護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[即時偵測](threat-explorer.md)</li></ul>|適用於 Office 365 的 Microsoft Defender 方案 1 的功能 <br>--- 以及 ---<br> 自動化、調查、補救和教育功能：<ul><li>[威脅追蹤工具](threat-trackers.md)</li><li>[威脅總管](threat-explorer.md)</li><li>[自動調查及回應](office-365-air.md)</li><li>[攻擊模擬器](attack-simulator.md)</li><li>[行銷活動檢視](campaigns.md)</li></ul>|
|

- 適用於 Office 365 的 Microsoft Defender 方案 2 隨附於 Office 365 E5、Office 365 A5、Microsoft 365 E5 安全性和 Microsoft 365 E5。

- 適用於 Office 365 的 Microsoft Defender 方案 1 隨附於 Microsoft 365 商務進階版。

- 適用於 Office 365 的 Microsoft Defender 方案 1 和適用於 Office 365 的 Microsoft Defender 方案 2 均以附加元件形式為特定訂閱提供。 若要深入了解，請參閱[適用於 Office 365 的 Microsoft Defender 方案的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- [安全文件](safe-docs.md)功能僅可供具備 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權 (未包含在適用於 Office 365 的 Microsoft Defender 方案中) 的使用者使用。

- 如果您目前的訂閱未包含適用於 Office 365 的 Microsoft Defender，請[與銷售人員連絡以開始試用](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)，並了解適用於 Office 365 的 Defender 如何能幫助您的組織。

## <a name="configure-microsoft-defender-for-office-365-policies"></a>設定適用於 Office 365 的 Microsoft Defender 原則

有了適用於 Office 365 的 Microsoft Defender，組織的安全性小組就能在安全性與合規性中心中定義原則來設定防護 (移至 <https://protection.office.com> \> **[威脅管理]** \> **[原則]**。)

觀看[此影片](https://www.youtube.com/watch?v=vivvTmWJ_3c)瞭解更多資訊。 

> [!TIP]
> 如需要定義的原則快速清單，請參閱[防範威脅](protect-against-threats.md)。

## <a name="defender-for-office-365-policies"></a>適用於 Office 365 的 Defender 原則

為您組織定義的原則會決定預先定義之威脅的行為和保護層級。 原則選項極具彈性。 例如，組織的安全性小組也可以在使用者、組織、收件者和網域層級設定微調的威脅防護。 因為新威脅及挑戰每天都會出現，請務必定期檢閱您的原則。

- **[安全附件](safe-attachments.md)**：透過檢查電子郵件附件中的惡意內容，提供零時差保護，以保護您的郵件系統。 它會將沒有病毒/惡意程式碼簽章的所有郵件與附件路由傳送至特殊的環境，然後使用機器學習和分析技術來偵測惡意意圖。 如果找不到任何可疑的活動，便會將郵件轉寄到信箱。 若要深入了解，請參閱[設定安全附件原則](set-up-safe-attachments-policies.md)。

- **[安全連結](safe-links.md)**：提供 URL 的點擊時驗證 (例如在電子郵件訊息和 Office 檔案中)。 保護會持續進行，並在您郵件和 Office 環境間套用。 每次按一下連結時掃描：安全連結仍保持可存取，並且以動態方式封鎖惡意連結。 若要深入了解，請參閱[設定安全連結原則](set-up-safe-links-policies.md)。

- **[適用於 SharePoint、OneDrive 及 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)**：透過找出並封鎖小組網站和文件庫中的惡意檔案，在使用者共同作業及共用檔案時保護您的組織。 若要深入了解，請參閱[為 SharePoint、OneDrive 和 Microsoft Teams 開啟適用於 Office 365 的 Defender](turn-on-mdo-for-spo-odb-and-teams.md)。

- **[適用於 Office 365 的 Defender 中的防網路釣魚保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**：偵測模擬使用者和內部或自訂網域的嘗試。 適用於電腦學習模型和進階模擬偵測演算法，以避免網路釣魚攻擊。 若要深入了解，請參閱[在適用於 Office 365 的 Microsoft Defender 中設定防網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="view-microsoft-defender-for-office-365-reports"></a>檢視適用於 Office 365 的 Microsoft Defender 報告

適用於 Office 365 的 Microsoft Defender 包括進階[報告儀表板](view-reports-for-mdo.md)，用來監視適用於 Office 365 的 Defender 的效能。 您可以在 [安全性與合規性中心] 的 **[報告]** \> **[儀表板]** 存取它。

報告會即時更新，提供您最新的深入解析。 這些報告也提供建議並警示您即將發生的潛在威脅。 預先定義的報告包括下列：

- [威脅總管 (或即時偵測)](threat-explorer.md)
- [威脅防護狀態報告](view-reports-for-mdo.md#threat-protection-status-report)
- ... 還有更多功能。

## <a name="use-threat-investigation-and-response-capabilities"></a>使用威脅調查及回應功能

適用於 Office 365 的 Microsoft Defender 方案 2 包含業界最佳[威脅調查及回應工具](office-365-ti.md)，可讓組織的安全性小組預期、了解和防止惡意攻擊。

- **[威脅追蹤工具](threat-trackers.md)** 提供有關戰勝網路安全性問題的最新情報。 例如，您可以檢視有關最新惡意程式碼的資訊，並在它成為組織的實際威脅之前便採取措施。 可用的追蹤器包括：[值得注意的追蹤器](threat-trackers.md#noteworthy-trackers)、[趨勢追蹤器](threat-trackers.md#trending-trackers)、[追蹤的查詢](threat-trackers.md#tracked-queries)和[已儲存的查詢](threat-trackers.md#saved-queries)。

- **[威脅總管 (或即時偵測)](threat-explorer.md)** (也稱為檔案總管) 是即時的報告，可讓您識別並分析最近的威脅。 您可以設定檔案總管來顯示自訂期間的資料。

- **[攻擊模擬器](attack-simulator.md)** 可讓您在組織中執行真實化攻擊案例以找出漏洞。 目前攻擊類型的模擬已可供使用，包括魚叉式網路釣魚憑證竊取和附件攻擊，以及密碼噴濺和暴力密碼破解攻擊等。

## <a name="save-time-with-automated-investigation-and-response"></a>利用自動調查及回應節省時間

(**新增！**) 調查潛在的網路攻擊時，時間是關鍵。 愈快找出並減輕威脅，您組織的處境會愈好。 [自動化調查和回應](office-365-air.md) (AIR) 功能包含一組可以自動啟動 (例如當警示觸發時) 或手動啟動 (例如從檔案總管中的檢視) 的安全性劇本。 AIR 可以在緩和威脅方面有效也有效率地節省您安全性作業小組的時間和精力。 若要深入了解，請參閱 [Office 365 中的AIR](office-365-air.md)。

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>使用適用於 Office 365 的 Microsoft Defender 功能所需的權限

若要在安全性與合規性中心存取適用於 Office 365 的 Microsoft Defender 功能，您必須獲指派適當的角色。下表包含一些範例：

|角色或角色群組|可深入了解的資源|
|---|---|
|全域系統管理員 (可在 Azure Active Directory 或安全性與合規性中心指派)|[關於 Microsoft 365 系統管理員角色](../../admin/add-users/about-admin-roles.md)|
|安全性系統管理員 (可在 Azure Active Directory 或安全性與合規性中心指派)|[Azure Active Directory 中的系統管理員角色權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online 組織管理 (這是在 Exchange Online 中指派)|[Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|搜尋和清除 (僅能在安全性與合規性中心指派)|[安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)|

如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

## <a name="get-microsoft-defender-for-office-365"></a>取得適用於 Office 365 的 Microsoft Defender

適用於 Office 365 的 Microsoft Defender 包含在某些訂閱中，例如 Microsoft 365 E5、Office 365 E5、Office 365 A5 和 Microsoft 365 商務進階版。 如果您的訂閱不包含適用於 Office 365 的 Defender，您可以購買適用於 Office 365 的 Defender 方案 1 或適用於 Office 365 的 Defender 方案 2 做為特定訂閱的附加元件。 若要深入了解，請參閱下列資源：

- [適用於 Office 365 的 Microsoft Defender 可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)，可取得包含適用於 Office 365 的 Defender 方案的訂閱清單。

- [適用於 Office 365 的 Microsoft Defender 方案的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)，可取得方案 1 和 2 中包含的功能清單。

- [取得合適的適用於 Office 365 的 Microsoft Defender](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)，可比較方案並購買適用於 Office 365 的 Defender。

- [開始免費試用](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>適用於 Office 365 的 Microsoft Defender 中的新功能

我們會持續將新功能新增至適用於 Office 365 的 Microsoft Defender。 若要深入了解，請參閱下列資源：

- [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365)提供開發中和正在推出的新功能清單。

- [適用於 Office 365 的 Microsoft Defender 服務描述](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)會描述適用於 Office 365 的 Defender 方案的功能與可用性。

## <a name="see-also"></a>另請參閱

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

- [Microsoft 365 Defender 中的自動化調查及回應 (AIR)](../defender/m365d-autoir.md) 1
