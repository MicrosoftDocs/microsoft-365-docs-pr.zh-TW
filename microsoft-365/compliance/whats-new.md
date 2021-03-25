---
title: Microsoft 365 合規性中心的新功能
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 若要將新的解決方案加入至規範中心、根據您的意見來更新現有的功能，或是推出新的和更新的檔，Microsoft 365 可協助您保持最新的合規性水準。 請找出我們所學的月份。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c695bc2632e766eb6f14c4e9f7eabbbddff66fd2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164972"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 合規性中心的新功能

無論是將新的解決方案加入至 [Microsoft 365 規範中心](microsoft-365-compliance-center.md)、根據您的意見反應更新現有的功能，或是推出全新和更新的檔，Microsoft 365 都會協助您不斷掌握不斷變化的相容性形勢。 請參閱下列內容，以查看目前的 Microsoft 365 合規性的新功能。

> [!NOTE]
> 有些規範功能會以不同的速度向客戶推出。 如果您還沒有看到功能，請嘗試將您新增至 [目標版本](/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 對其他系統管理中心的進展感興趣嗎？ 請參閱下列文章：<br>[Microsoft 365 系統管理中心的新功能](/office365/admin/whats-new-in-preview)<br>[SharePoint 系統管理中心的新功能](/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender 的新功能](../security/defender/whats-new.md)<br><br>
請造訪 [microsoft 365 藍圖](https://www.microsoft.com/en-us/microsoft-365/roadmap) ，以瞭解已啟動、已開發、已取消或先前發佈的 microsoft 365 功能。

## <a name="january-2021"></a>2021 年 1 月

### <a name="support-for-card-content-in-teams"></a>支援小組中的卡片內容

下列 Microsoft 365 規範解決方案現在支援透過小組訊息中的應用程式所產生的 [卡片內容](/microsoftteams/platform/task-modules-and-cards/what-are-cards) 的偵測：

- **核心和高級 eDiscovery**。 現在，卡片內容可以 [保留](create-ediscovery-holds.md#preserve-card-content) 或納入 [搜尋](/microsoftteams/ediscovery-investigation#search-for-card-content) (套用至內容搜尋) 。
- **Audit**。 [卡片] 活動現在會 [記錄到審核記錄](/microsoftteams/audit-log-events#teams-activities)檔。
- **保留原則**。 現在可以使用保留原則來 [保留和刪除卡片內容](retention-policies-teams.md#whats-included-for-retention-and-deletion)。

### <a name="information-governance-and-records-management"></a>資訊管理與記錄管理

使用資訊控管和記錄管理來處理的[新評估](retention-regulatory-requirements.md#new-zealand-public-records-act)，可協助滿足紐西蘭公開記錄法案的合規性義務。

### <a name="sensitivity-labels"></a>敏感度標籤

- 現在，我們的政府承租人 (GCC 和 GCC-H) 支援敏感度標籤。
- MacOS 的新 [自動標籤](sensitivity-labels-office-apps.md) 支援。

## <a name="december-2020"></a>2020 年 12 月

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>聚光燈：有問必答風險解決方案的新內容

Microsoft 365 合規性內容小組正在運作中建立「內容解決方案」檔，以提升如何搭配使用相容性功能，以協助符合您的合規性目標。

第一個是將內幕程式風險解決方案結合在一起的內容：通訊法規遵從性、內幕風險管理、資訊障礙及特殊的訪問管理。 以下是您將會發現的內容：

- [內部擁有風險解決方案的新登陸頁面](insider-risk-solution-overview.md)。 包含解決方案可協助緩解、授權需求、部署順序、架構圖例、訓練資源等方面的風險的詳細資料。
- 每個有問必答風險解決方案的新概述文章。 可協助您瞭解、規劃、部署及管理每個解決方案的文章指引及連結：
  - [通訊合規性](communication-compliance-solution-overview.md)
  - [有問必答風險管理](insider-risk-management-solution-overview.md)
  - [資訊屏障](information-barriers-solution-overview.md)
  - [特殊權限存取管理](privileged-access-management-solution-overview.md)
  
更多即將推出的內容解決方案檔！

### <a name="advanced-ediscovery"></a>進階電子文件探索

改進的工作流程和功能，可 [將保管人](add-custodians-to-case.md) 和 [非 custodial 資料來源](non-custodial-data-sources.md) 新增至高級 eDiscovery 案例。

### <a name="data-connectors"></a>資料連線器

已[發行四個新的 Veritas 連接器](archiving-third-party-data.md#third-party-data-connectors)： Redtail 講話、Salesforce 交談、ServiceNow 及 Yieldbroker。

### <a name="encryption"></a>加密

[在承租人層級引進 Microsoft 365 的客戶金鑰](customer-key-tenant-level.md)。 使用您提供的金鑰，您可以建立資料加密原則 (DEP) 並指派給租使用者。 DEP 會針對這些工作負載在租使用者上進行資料加密：

- 小組聊天訊息 (1:1 聊天、群組交談、會議聊天及通道交談) 
- 小組媒體郵件 (影像、程式碼片段、影片、wiki 影像) 
- 小組儲存中儲存的小組通話和會議錄製
- 小組聊天通知
- 小娜的小組聊天建議
- 小組狀態郵件
- Exchange Online 的使用者和信號資訊

### <a name="records-management"></a>記錄管理

[記錄管理系統管理員角色群組](get-started-with-records-management.md#permissions-required-for-records-management)現在會授與所有記錄管理功能的許可權，包括「處置評審」。

### <a name="sensitivity-labels"></a>敏感度標籤

- [在 Azure Purview 中自動標記資料 (預覽) ](/azure/purview/create-sensitivity-label)。 您現在可以針對 Azure Purview 中的資產建立和自動套用敏感度標籤，例如 Azure Blob 儲存區中的檔案和 SQL Server 中的資料庫欄。
- [要求使用者將標籤套用至專案](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)。 這個新的選項又稱為「必要標籤」，這項新選項需要使用者選擇並套用特定案例下的靈敏度標籤。

## <a name="november-2020"></a>2020 年 11 月
只會有提醒，我們通常會在預覽狀態中發佈新的和更新的功能，以瞭解如何使用這些功能，讓我們能夠在發佈至一般可用性之前完善並改進這些功能。 在預覽 (和超過) 之後，您的意見反應很重要，所以請務必先開啟規範中心右下方的回饋卡片，讓我們知道您的想法。

![回饋](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>聚光燈：端點資料遺失防護 (DLP) 已發行

[ENDPOINT dlp](endpoint-dlp-learn-about.md) 會將 DLP 的活動監控和保護功能延伸至 Windows 10 裝置上的機密資訊。 在裝置 [架](dlp-configure-endpoints.md) 至 Microsoft 365 規範中心後，您可以設定 DLP 原則，以保護這些裝置上的機密資訊。

### <a name="advanced-ediscovery"></a>進階電子文件探索

為了讓您更容易管理 eDiscovery 工作流程中的加密內容，Microsoft 365 eDiscovery 工具現在整合了附加至電子郵件訊息並在 Exchange 中傳送的 [加密檔案解密](ediscovery-decryption.md) 。 此外，儲存在 SharePoint 和 OneDrive 中的加密檔會在 [Advanced eDiscovery] 中解密。

### <a name="compliance-manager"></a>合規性管理員

- [Microsoft 365 政府版訂閱的支援](compliance-manager.md)。 合規性管理員現在可供美國政府社區 (GCC) 適中和高客戶。
- [合規性管理員的 Microsoft 規範設定分析器](compliance-manager-mcca.md)。 新的 PowerShell 基礎工具，可協助您開始使用合規性管理員，方法是掃描組織的目前設定，並對照 Microsoft 365 建議的最佳作法加以驗證。
- [新的範本](compliance-manager-templates-list.md)。 新增56新範本，並將總合規性管理員範本引入超過230。

### <a name="data-connectors"></a>資料連線器

[預覽中的五個新 Veritas 連接器](archiving-third-party-data.md#third-party-data-connectors)。 新的連接器包括 Reuters 處理、Reuters FX、CellTrust、XIP、泛型 MS SQL 資料庫資料。

### <a name="retention-labels-disposition-review"></a>保留標籤 (處置評審) 

若要在處置檢查過程中查看專案，使用者現在必須是 [內容瀏覽器內容檢視器和內容瀏覽器清單檢視器角色群組](disposition.md#permissions-for-disposition)的成員。 雖然必須複查專案，但在完成處置檢查時，並不需要這些角色群組。

### <a name="sensitivity-labels"></a>敏感度標籤

- [ (預覽) SharePoint 網站的外部共用設定](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings)。 建立群組和網站所使用的標籤時，您會看到一個選項，可控制已套用標籤的 SharePoint 網站的外部共用。 您可以指定允許任何人、新的和現有的來賓、現有來賓或僅限您組織中的使用者共用。 套用標籤時，標籤設定會取代 [SharePoint 系統管理中心內設定的](/sharepoint/change-external-sharing-site)任何外部共用設定。
- [移除已標記檔中的標籤和加密](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document)。 若要從 SharePoint 中的標籤檔中移除標籤和其所強制執行的加密，global admins 和 SharePoint 系統管理員都可以執行新的 `Unlock-SPOSensitivityLabelEncryptedFile` Cmdlet。 即使系統管理員沒有網站或檔案的存取權限，或 Azure Rights Management 服務無法使用，此 Cmdlet 也會執行。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>進階電子文件探索

[CJK 語言支援](ediscovery-cjk-support.md)。 「高級 eDiscovery」現在支援雙位元組字元集語言，統稱為 CJK 語言 (包含簡體中文版的繁體中文、繁體中文、日文和韓文) 。 這些可用於數種高級複查集案例。

### <a name="sensitivity-labels"></a>敏感度標籤

- [標籤範圍](sensitivity-labels.md#label-scopes)。 建立靈敏度標籤時，您會看到新的選項，可定義標籤的範圍。 此選項可讓您設定標籤與電子郵件、容器 (SharePoint 網站和團隊) 或兩者等的標籤。
- [動態內容標示](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 在設定敏感度標籤的內容標示時，您現在可以 `${Item.Label}` `${Item.Location}` 在您的頁首、頁尾或浮水印的文字字串中使用動態變數。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>聚光燈：合規性管理員

Ignite 今年宣佈，合規性分數是 rebranded 為 [合規性管理員](compliance-manager.md)。 此版本會在服務信任入口網站中完成從合規性管理員先前的首頁轉換，並在 Microsoft 365 規範中心引進端對端規範管理解決方案。

觀看下列影片，瞭解合規性管理員如何協助簡化組織管理規範的方式。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>進階稽核

- 新的10年保留審計記錄檔可協助支援長期執行調查，並回應法規、法律和內部責任。
- [三個新的重要事件](advanced-audit.md#access-to-crucial-events-for-investigations)。 下列新事件可協助您調查可能的破壞專案，並決定受損的範圍： Send、SearchQueryInitiatedExchange 及 SearchQueryInitiatedSharePoint。

### <a name="communication-compliance"></a>通訊合規性

- [更新的角色群組](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。 通訊相容性角色群組現在符合「內部使用者風險管理」解決方案可用的角色群組結構。
- [報表儀表板](communication-compliance-feature-reference.md#reports)。 用於查看所有通訊相容性報告的中央位置。 報告構件可讓您快速瞭解對通訊規範活動狀態的整體評估，最常用的洞察力。
- [自動處理電源流程](communication-compliance-feature-reference.md#power-automate-flows)。 設定流程以自動化警示和使用者的工作、在使用者觸發提醒時通知管理員等等。
- 「[改進分類」修正動作](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)。 包含符合 trainable 分類程式之專案的警示可能會受益于意見反應，有助於減少組織中的誤報。 [ **提升分類** ] 選項可讓您提供偵測到的專案是否符合相關通訊遵循原則中設定的分類器的意見反應。 您甚至可以建議其他分類器與專案產生關聯，以提升未來警示的相符準確度。

### <a name="data-connectors"></a>資料連線器

- [新增協力廠商資料連線器](archiving-third-party-data.md#third-party-data-connectors)。 25個新的資料連線器，包含來自 Veritas 和8的14個連接器，從 Telemessage。
- [實體聲譽徽章授予連接器](import-physical-badging-data.md)。 匯入實體聲譽徽章授予資料，例如員工的原始實體存取事件，或是組織之聲譽徽章授予系統所產生的任何實體存取告警。 範例包括辦公樓、伺服器機房或資料中心的專案。 「內部使用者風險管理」解決方案可使用實體聲譽徽章授予資料，協助保護您的組織免受惡意活動或組織內的資料竊取。

### <a name="insider-risk-management"></a>內部風險管理

- [Microsoft 小組整合](insider-risk-management-settings.md#microsoft-teams-preview)。 當團隊整合在「內幕風險設定」中開啟時，您可以與工作小組中的其他專案關係人協調及共同作業，例如安全共用和儲存與個別案例相關的資料、追蹤及檢查分析員和調查人員的回應活動等等。
- [自動處理電源流程](insider-risk-management-settings.md#power-automate-flows-preview)。 設定流程以自動化案例和使用者的重要工作，例如，檢索使用者、警示及案例資訊，以與專案關係人和其他應用程式共用、自動化動作（如張貼至案例記事）等等）。
- [活動總管](insider-risk-management-alerts.md#activity-explorer-preview)。 可用於審閱提醒時，活動 explorer 會提供調查人員和分析工具，以深入查看每個警示的綜合分析工具。 快速查看偵測到風險的啟用時間表，並識別及篩選與提醒相關聯的所有風險活動。

### <a name="retention-policies-and-retention-labels"></a>保留原則和保留標籤

- [對 Yammer 的支援](retention-policies-yammer.md)。 您現在可以使用保留原則來保留和刪除 Yammer 社區郵件和私人郵件。
- 對[小組會議錄製套用標籤](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings)。 建立自動標記原則時，請使用關鍵字查詢編輯器，識別儲存在使用者 OneDrive 帳戶或 SharePoint 中的小組會議錄製。

### <a name="records-management"></a>記錄管理

[支援法規記錄](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)。 將標籤分類為法規記錄會增加標籤所套用的內容限制，並限制標籤本身可用的管理動作。 例如，在套用至內容之後，任何人（甚至全域系統管理員）都可以移除標籤。 [深入瞭解](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) 針對法規記錄允許和封鎖的動作。

### <a name="sensitivity-labels"></a>敏感度標籤

[為美國政府客戶提供支援](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。 目前只有 Azure 資訊保護統一標籤用戶端和掃描器，才支援 GCC、GCC 高階及 DoD 客戶的靈敏度標籤。

### <a name="trainable-classifiers"></a>可訓練分類器

新的重新訓練和意見反應功能可協助提升精確度，並最小化所有自訂分類符和部分預先訓練的分類器的誤報。 這段流程可讓您針對專案是否符合特定的分類器、建議其他分類器與專案產生關聯，以及重新整理分類器以精煉和提高相符精確度。

下列功能包含這項新功能：

> [!NOTE]
> 針對所有功能，如果您至少提供30項回饋回應，我們會建立該分類程式的 retrained 版本，您可以進行查看。 如果有改進，您可以重新發佈分類器。

- [可訓練分類器](classifier-learn-about.md#retraining-classifiers)。 若要改善發佈的分類程式的準確性，您可以提供偵測到的專案是否符合分類程式的意見反應。
- [通訊相容性](classifier-how-to-retrain-comms-compliance.md)。 新增的「 **改進分類** 修復」動作可讓您提供意見，以徵求通訊相容性警示中的專案是否符合通訊合規性原則中設定的分類器。
- [內容總管](classifier-how-to-retrain-content-explorer.md)。 如果您設定保留自動標記原則，以自動將標籤套用至符合 trainable 分類程式的電子郵件，您可以使用內容瀏覽器來查看已標示的專案，並提供專案是否符合分類器的意見反應。

## <a name="august-2020"></a>2020年 8月

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>聚光燈：有問必答風險和通訊相容性更新

這個月的公開預覽的一些新增及增強功能：

**有問必答風險管理**

- 查看我們的六個新 [原則範本](insider-risk-management-policies.md#policy-templates)：
    - 依優先使用者的資料洩漏
    - 因不滿使用者的資料洩漏
    - 一般安全性原則違規
    - 脫離使用者的安全性原則違規
    - 依優先順序的使用者所破壞的安全性原則
    - 不滿的使用者違反安全性原則

- 與 [Microsoft defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 整合可讓您匯入並篩選 microsoft defender，以取得從新的安全性違規原則範本所建立的原則所偵測到的活動的端點警示。 此外，還有相關的 [內幕使用者風險設定](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) ，您可以選擇根據 Microsoft Defender for Endpoint alert 會審狀態，選擇匯入「內幕風險管理」的安全性警示。

    > [!NOTE]
    > 若要利用 Microsoft Defender 做為端點整合 (包括新的安全性原則違規模板) ，您的組織中必須設定 Microsoft Defender for Endpoint。 您也必須 [在 Microsoft defender For endpoint 中設定高級功能](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)，以啟用內部使用者風險管理的 Microsoft defender 端點。
 
- 自訂 [建立原則時的](insider-risk-management-policies.md#create-a-new-policy)指示器閾值。
- 設定 [優先順序的使用者群組](insider-risk-management-settings.md#priority-user-groups-preview) ，以定義組織中的使用者，其活動需要根據其位置、敏感資訊存取權或風險歷程等因素進行深入檢查。
- 使用 Office 365 管理活動 APIs，將 [內幕電腦風險警示詳細資料匯出](insider-risk-management-settings.md#export-alerts-preview) 至組織可能用來管理或匯總「有問必答風險」資料的其他應用程式。
- 新的 [網域設定](insider-risk-management-settings.md#domains-preview) 可協助您定義及控制特定網域中活動的風險層級。

**通訊合規性**

- 當您 [在警示中檢查郵件](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)時，您現在可以在 Microsoft 小組頻道、1:1 和群組聊天中移除不適當的郵件。 移除的郵件和內容會被取代，以解釋因敏感內容而被移除的原則提示。
- 新的 [通訊角色](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (也會包含在) 年9月發行的新通訊符合性角色群組中。
- 新的通訊相容性設定經驗包括 [隱私權](communication-compliance-feature-reference.md#privacy) 和 [注意事項範本](communication-compliance-feature-reference.md#notice-templates)的設定。
- 新的 [分類](communication-compliance-feature-reference.md#classifiers) 器協助偵測成人、racy 及 gory 影像。
- 在 [提醒中檢查郵件](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) 時出現新的「模式偵測」通知，可讓您瞭解使用者對相同行為的重複實例。

### <a name="sensitivity-labels"></a>敏感度標籤

- 針對美國政府租使用者（GCC、GCC-H，和DoD），目前僅支援 Azure 資訊保護統一標籤用戶端和掃描器的敏感標籤。 如需詳細資訊，請參閱 [Azure 資訊保護進階版政府服務描述](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。
- 您現在可以 [使用「安全性 & 規範中心」 PowerShell](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) 建立及設定您在標記系統管理中心中看到的所有設定。 這表示，除了使用 PowerShell 以用於標籤 admin center 以外的設定，您現在可以完全編寫敏感度標籤和敏感度標籤原則的建立及維護功能。

### <a name="records-management-content-overhaul"></a>記錄管理：內容徹底檢修

涵蓋部署步驟、將內容標示為記錄及記錄版本的新檔：

- [開始使用記錄管理](get-started-with-records-management.md)
- [使用保留標籤聲明記錄](declare-records.md)
- [使用記錄版本設定來更新儲存在 SharePoint 或 OneDrive 中的記錄](record-versioning.md)

### <a name="retention-labels--policies"></a>保留標籤 & 原則

保留相關的系統管理員活動現在已記錄下來，可在審核記錄中查看。 如需完整清單，請參閱[保留原則和保留標籤活動](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。

### <a name="advanced-ediscovery"></a>進階電子文件探索

- 在 [將集合新增至審閱集](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)時，您現在可以包含新式附件 (也稱為「雲端附件」 ) 及 SharePoint 檔版本。
- 新的 [直接下載匯出體驗](export-documents-from-review-set.md)，不再需要使用 Azure 存放區瀏覽器來下載案例內容。