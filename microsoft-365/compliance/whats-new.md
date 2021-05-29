---
title: Microsoft 365 合規性中心的新功能
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: 是否要將新的解決方案新增至規範中心、根據您的意見，更新現有的功能，或是推出新的和更新的檔，Microsoft 365 可協助您在不斷變更的相容性環境上保持最高的狀態。 請找出我們所學的月份。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae1df2ce6373e4a8f6b01c33e50bea5e6c16ca0a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698949"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 合規性中心的新功能

是否要將新的解決方案加入[Microsoft 365 規範中心](microsoft-365-compliance-center.md)、根據您的意見，更新現有的功能，或是推出新的和更新的檔，Microsoft 365 可協助您在不斷變更的相容性環境上保持最高的狀態。 請參閱下列內容，查看目前的 Microsoft 365 法規遵從性的新功能。

> [!NOTE]
> 有些規範功能會以不同的速度向客戶推出。 如果您還沒有看到功能，請嘗試將您新增至 [目標版本](/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 對其他系統管理中心的進展感興趣嗎？ 請參閱下列文章：<br>[Microsoft 365 系統管理中心的新功能](/office365/admin/whats-new-in-preview)<br>[SharePoint 系統管理中心的新功能](/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender 的新功能](../security/defender/whats-new.md)<br><br>
並流覽[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)，以瞭解已啟動、正在開發中、已取消或之前發行的 Microsoft 365 功能。

## <a name="april-2021"></a>2021 年 4 月

### <a name="advanced-ediscovery"></a>進階電子文件探索

- [Advanced eDiscovery 中的限制](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set)。 組織現在可以使用從審閱集中的單一匯出專案，以較小的專案匯出最多5000000個專案或 500 MB （兩者兩者都小）。

### <a name="data-classification"></a>資料分類

- [活動瀏覽器中可用的標記活動](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>資料連線器

- [設定 connector 以封存 Oracle 資料上的 Cisco Jabber) ]/microsoft-365/compliance/archive-ciscojabberonoracle-data) 
- [設定連接器以封存 PostgreSQL 資料上的 Cisco Jabber) ](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>資料外洩防護

- [資料遺失防護原則提示參考](/microsoft-365/compliance/dlp-policy-tips-reference)的新主題。
- [深入瞭解資料遺失防護](/microsoft-365/compliance/dlp-learn-about-dlp)的新主題。
- [資料遺失防護警示儀表板入門](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)的新主題。

### <a name="retention-policies-and-retention-label-policies"></a>保留原則和保留標籤原則

- Microsoft 365 群組的位置現在可以使用[Set-RetentionCompliancePolicy PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) Cmdlet 搭配應用程式參數，將保留設定套用至只 Microsoft 365 信箱或僅使用連接的 SharePoint 網站。

### <a name="sensitivity-labels"></a>敏感度標籤

Outlook 版本和更新：
- 先前只有 AIP 的整合標籤用戶端支援，內建的標記現在支援 [預設標籤和必要標籤的不同設定](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling)
- MacOS、iOS 和 Android 現在支援 Encrypt-Only
- [Manage Office app 中的靈敏度標籤](/microsoft-365/compliance/sensitivity-labels-office-apps)已更新在[Outlook 功能表格](/microsoft-365/compliance/sensitivity-labels-office-apps#sensitivity-label-capabilities-in-outlook)中的新專案時，會針對內建的標籤，以不同的預設標籤及 Outlook 必要標籤的[預設標籤及必要](/microsoft-365/compliance/sensitivity-labels-office-apps#outlook-specific-options-for-default-label-and-mandatory-labeling)標籤來更新，以支援不同的預設標籤和例外要求的標籤。 此外，macOS/iOS/Android 現在也支援 Encrypt-Only 選項，而且所有包含變數的動態標記現在皆支援所有 Outlook 用戶端。 必要的標籤現在會向其他平臺推出。

## <a name="march-2021"></a>2021 年 3 月

以下是在三月份 Microsoft 365 法規遵從性解決方案和內容的一些變更。

### <a name="advanced-ediscovery"></a>進階電子文件探索

- **Advanced eDiscovery 集合** 現在支援 [新的集合工具和工作流程](/microsoft-365/compliance/collections-overview)。 其他新主題包括 [建立草稿集合](https://docs.microsoft.com/microsoft-365/compliance/create-draft-collection)、 [將草稿集合認可至審閱集](/microsoft-365/compliance/commit-draft-collection)，以及 [集合統計資料和報告](/microsoft-365/compliance/collection-statistics-reports)。
- 將審閱集中的 **檔匯出** 為 [Azure 儲存體](/microsoft-365/compliance/download-export-jobs)帳戶。
- **Advanced eDiscovery 的預測編碼模組**。 首先請參閱新的 [預測編碼](/microsoft-365/compliance/predictive-coding-overview) 功能，以取代已撤銷的相關性模組。

### <a name="data-classification"></a>資料分類

- **資料分類瀏覽器**。 [開始](/microsoft-365/compliance/data-classification-activity-explorer) 使用資料分類瀏覽器。

### <a name="data-connectors"></a>資料連線器

- **私密金鑰**。 已新增私密金鑰的支援，以 [Bloomberg 郵件](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) 資料、 [ICE 聊天](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) 資料和 [立即 Bloomberg](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys) 資料連線器。

### <a name="data-loss-prevention"></a>資料外洩防護

- **Microsoft Teams 支援**。 資料遺失防護支援擴充至[Microsoft Teams](/microsoft-365/compliance/dlp-teams-default-policy)。
- **Microsoft 合規性分機**。 開始使用 [Microsoft 規範擴充](/microsoft-365/compliance/dlp-chrome-get-started)。

### <a name="encryption"></a>加密

- **Microsoft 365 的客戶金鑰**。 Microsoft 365 在租使用者層級 (公開預覽) 的[客戶機碼的概覽](/microsoft-365/compliance/customer-key-tenant-level)。
- **雙金鑰加密**。 深入瞭解如何在 SharePoint 和商務用 OneDrive 中[啟用已標記與受保護的檔支援](/microsoft-365/compliance/double-key-encryption)。

### <a name="insider-risk-management"></a>內部風險管理

下列內部的內幕風險管理功能更新已于三月份發行供公開預覽：

- 建立有問必答風險原則之前，用來識別風險的新分析功能
- 新的風險活動順序偵測支援和管理
- 新的累計 exfiltration 偵測支援
- 新的應用程式原則狀況報告和建議支援
- 新的審計記錄功能與報告
- 原則建立嚮導的增強功能
- 內容 explorer 更新
- 新增使用者管理流程/支援 (新增/移除原則) 中的使用者
-  (去聲使用者原則支援，支援 AAD 整合的新支援) 
- 更新 (REGEX) 原則中的網域支援
- 原則範本增強功能及增強功能

下列主題是更新或新增，以支援下列新功能：

- [深入了解測試人員風險管理](/microsoft-365/compliance/insider-risk-management)
- [測試人員風險管理計畫](/microsoft-365/compliance/insider-risk-management-plan)
- [開始使用「內幕風險管理」設定](/microsoft-365/compliance/insider-risk-management-settings)
- [開始使用測試人員風險管理](/microsoft-365/compliance/insider-risk-management-configure)
- [建立及管理測試人員風險原則](/microsoft-365/compliance/insider-risk-management-policies)
- [調查測試人員風險警示](/microsoft-365/compliance/insider-risk-management-alerts)
- [對測試人員風險案例採取動作](/microsoft-365/compliance/insider-risk-management-cases)
- [使用內部風險稽核記錄來審查活動](/microsoft-365/compliance/insider-risk-management-audit-log)
- [使用測試人員風險內容總管檢閱資料](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [使用使用者儀表板管理工作流程](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>記錄管理

- **檔計畫改進功能**。 更新 [檔計畫](file-plan-manager.md) 時，會移除或改進先前的匯入長度限制。
- **刪除記錄的保留標籤**。 預覽版本支援刪除將專案標記為記錄的 [保留標籤](create-apply-retention-labels.md#deleting-retention-labels) 的功能。

### <a name="sensitive-information-types"></a>敏感性資訊類型

已新增或更新下列主題中的內容：

- [開始使用自訂機密資訊類型](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [了解敏感性資訊類型](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [建立實際資料符合活動的通知](/microsoft-365/compliance/sit-edm-notifications-activities)
- [敏感資訊類型實體定義](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [使用 PowerShell 建立自訂機密資訊類型](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [建立關鍵字字典](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>敏感度標籤

- **DoD 支援**。 支援含 DoD 環境的美國政府承租人。
- **僅限加密 Outlook**。 Outlook 的加密選項會在您選取 [[讓使用者指派許可權](encryption-sensitivity-labels.md#let-users-assign-permissions)] 時包括 Encrypt-Only。
- **在 Office 應用程式中強制執行內建標籤**。 更新[指引](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client)當您已安裝 Azure 資訊保護統一標記用戶端時，如何在 Office 應用程式中強制執行內建標籤。

## <a name="february-2021"></a>2021 年 2 月

以下是在二月份 Microsoft 365 法規遵從性解決方案和內容的一些變更。

### <a name="auditing"></a>稽核

- **管理審核記錄保留原則**。 深入瞭解新的「 [審核保留原則儀表板](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)」。
- **搜尋審核記錄** 檔。 [使用 PowerShell 腳本搜尋審核記錄](/microsoft-365/compliance/audit-log-search-script)。

### <a name="data-classification-content-explorer"></a>資料分類內容瀏覽器

已新增或更新下列主題中的內容：

- [開始使用內容總管](/microsoft-365/compliance/data-classification-content-explorer)
- [資料分類版本資訊](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>資料外洩防護

已新增或更新下列主題中的內容：

- [深入瞭解 Endpoint DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)
- [針對 DLP 原則傳送電子郵件通知並顯示原則提示](https://docs.microsoft.com/microsoft-365/compliance/use-notifications-and-policy-tips)
- [深入瞭解 Microsoft 365 資料遺失防護內部部署掃描器](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [從資料遺失防護開始使用內部部署掃描程式](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [建立 DLP 原則來保護具有 FCI 或其他屬性的文件](https://docs.microsoft.com/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [使用端點資料外洩防護](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-using)
- [開始使用端點資料外洩防護](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>電子文件探索

已新增或更新下列主題中的內容：

- [Microsoft 365 電子檔探索工具中的解密](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-decryption)
- [關鍵字查詢與搜尋條件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Advanced eDiscovery 中的相關性模組退休](https://docs.microsoft.com/microsoft-365/compliance/relevance-module-retirement)
- [使用腳本將使用者新增至核心 eDiscovery 案例中的保留](https://docs.microsoft.com/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>加密

已新增或更新下列主題中的內容：

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Service (RMS) 

- [客戶管理的加密功能](https://docs.microsoft.com/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [使用 AD RMS Exchange Online 郵件加密](https://docs.microsoft.com/microsoft-365/compliance/information-rights-management-in-exchange-online)。 此服務的支援已被取代。 您無法再在 Exchange 混合式環境中使用 AD RMS。 請改為遷移到 Azure RMS。

#### <a name="customer-key"></a>客戶金鑰

- [租使用者層級 Microsoft 365 的客戶金鑰](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level)
- [安全性與合規性綜述](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>資訊版權管理 (IRM)

- [將資訊版權管理 (IRM) 套用至清單或文件庫](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server)。 這兩個國家/地區群不支援此設定：
    - Microsoft Cloud for US Government
    - Microsoft Cloud 德國
    - 以中國為單位運作的 Azure 和 Microsoft 365) 
- [將 IRM 設定為使用內部部署 AD RMS 伺服器](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server)。 已棄用 Exchange 混合式環境中此服務的支援。

### <a name="sensitive-information-types"></a>敏感資訊類型

已新增或更新下列主題中的內容：

- [了解敏感性資訊類型](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-learn-about)
- [使用 PowerShell 建立自訂的敏感性資訊類型](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [建立自訂機密資訊類型，並以精確的資料符合型分類為基礎](https://docs.microsoft.com/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [敏感資訊類型實體定義](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>敏感度標籤

已新增或更新下列主題中的內容：

- **SharePoint 外部共用**。 [容器標籤](sensitivity-labels-teams-groups-sites.md)從 SharePoint 網站進行外部共用的選項現在會以正式發行。 此外，Microsoft 365 系統管理中心和 Planner 現在支援套用這些敏感度標籤。 
- **共同撰寫和 AutoSave**。 在非實際執行承租人中，會以預覽進行測試，將加密檔的 [共同撰寫和 AutoSave](sensitivity-labels-coauthoring.md) 發行。

## <a name="january-2021"></a>2021 年 1 月

### <a name="support-for-card-content-in-teams"></a>Teams 中的卡片內容支援

下列 Microsoft 365 規範解決方案現在支援透過 Teams 訊息中的應用程式所產生的[卡片內容](/microsoftteams/platform/task-modules-and-cards/what-are-cards)的偵測：

- **核心和 Advanced eDiscovery**。 現在，卡片內容可以 [保留](create-ediscovery-holds.md#preserve-card-content) 或納入 [搜尋](/microsoftteams/ediscovery-investigation#search-for-card-content) (套用至內容搜尋) 。
- **Audit**。 [卡片] 活動現在會 [記錄到審核記錄](/microsoftteams/audit-log-events#teams-activities)檔。
- **保留原則**。 現在可以使用保留原則來 [保留和刪除卡片內容](retention-policies-teams.md#whats-included-for-retention-and-deletion)。

### <a name="information-governance-and-records-management"></a>資訊管理與記錄管理

使用資訊控管和記錄管理來處理的[新評估](retention-regulatory-requirements.md#new-zealand-public-records-act)，可協助滿足紐西蘭公開記錄法案的合規性義務。

### <a name="sensitivity-labels"></a>敏感度標籤

- 現在，我們的政府承租人 (GCC 和 GCC-H) 支援敏感度標籤。
- MacOS 的新 [自動標籤](sensitivity-labels-office-apps.md) 支援。

## <a name="december-2020"></a>2020 年 12 月

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>聚光燈：有問必答風險解決方案的新內容

Microsoft 365 法規遵從性內容小組正在運作中建立「內容解決方案」檔，以推廣相容性功能如何搭配使用，以協助符合您的合規性目標。

第一個是將內幕程式風險解決方案結合在一起的內容：通訊法規遵從性、內幕風險管理、資訊障礙及特殊的訪問管理。 以下是您將會發現的內容：

- [內部擁有風險解決方案的新登陸頁面](insider-risk-solution-overview.md)。 包含解決方案可協助緩解、授權需求、部署順序、架構圖例、訓練資源等方面的風險的詳細資料。
- 每個有問必答風險解決方案的新概述文章。 可協助您瞭解、規劃、部署及管理每個解決方案的文章指引及連結：
  - [通訊合規性](communication-compliance-solution-overview.md)
  - [內部風險管理](insider-risk-management-solution-overview.md)
  - [資訊屏障](information-barriers-solution-overview.md)
  - [特殊權限存取管理](privileged-access-management-solution-overview.md)
  
更多即將推出的內容解決方案檔！

### <a name="advanced-ediscovery"></a>進階電子文件探索

改進的工作流程和功能，可[將保管人](add-custodians-to-case.md)和[非 custodial 資料來源](non-custodial-data-sources.md)新增至 Advanced eDiscovery 案例。

### <a name="data-connectors"></a>資料連線器

已[發行四個新的 Veritas 連接器](archiving-third-party-data.md#third-party-data-connectors)： Redtail 講話、Salesforce 交談、ServiceNow 及 Yieldbroker。

### <a name="encryption"></a>加密

[在承租人層級為 Microsoft 365 引進客戶金鑰](customer-key-tenant-level.md)。 使用您提供的金鑰，您可以建立資料加密原則 (DEP) 並指派給租使用者。 DEP 會針對這些工作負載在租使用者上進行資料加密：

- Teams 聊天訊息 (1:1 聊天、群組交談、會議聊天及通道交談) 
- Teams 媒體訊息 (影像、程式碼片段、影片、wiki 影像) 
- Teams 儲存區中儲存的 Teams 通話和會議錄製
- Teams 聊天通知
- 使用 Cortana Teams 聊天建議
- Teams 狀態郵件
- Exchange Online 的使用者和信號資訊

### <a name="records-management"></a>記錄管理

[記錄管理系統管理員角色群組](get-started-with-records-management.md#permissions-required-for-records-management)現在會授與所有記錄管理功能的許可權，包括「處置評審」。

### <a name="sensitivity-labels"></a>敏感度標籤

- [在 Azure Purview 中自動標記資料 (預覽) ](/azure/purview/create-sensitivity-label)。 您現在可以為 Azure Purview 中的資產建立及自動套用敏感度標籤，例如 Azure Blob 儲存區中的檔案和 SQL Server 中的資料庫欄。
- [要求使用者將標籤套用至專案](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)。 這個新的選項又稱為「必要標籤」，這項新選項需要使用者選擇並套用特定案例下的靈敏度標籤。
