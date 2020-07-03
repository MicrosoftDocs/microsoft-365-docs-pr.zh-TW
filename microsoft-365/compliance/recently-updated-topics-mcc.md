---
title: 規範中心的最近更新
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 03/22/2020
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- m365-security-compliance
description: 就像 Microsoft 365 規範中心的功能一樣，我們的說明內容永遠都在發展中。 瞭解本月新增及更新的功能。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fca455540ed3b01af3b9b4d2a6cd1053535f75b7
ms.sourcegitcommit: 8595cb9ffe0ca5556080f24224182381e1d880de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2020
ms.locfileid: "45035638"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Microsoft 365 規範內容的最近更新

就像 Microsoft 365 規範中心的功能一樣，我們的說明內容永遠都在發展中。 我們會持續建立新的文章、更新現有的文章，並根據您的意見反應進行變更。 請參閱下文，以查看當月新增及更新的功能。

> [!TIP]
> 若要在 Microsoft 365 規範中心中保持最新的功能更新，請參閱[microsoft 365 規範中心的新](whats-new.md)功能。

## <a name="march-2020"></a>2020 年 3 月

### <a name="auditing"></a>稽核

[使用高級審計調查已遭破壞的帳戶](mailitemsaccessed-forensics-investigations.md)（新增）<br>有關使用新的*MailItemsAccessed*信箱審核動作進行鑒證調查的新指導方針。

[搜尋審計記錄](search-the-audit-log-in-security-and-compliance.md)檔（更新）<br>變更包括：
- 包含審核記錄中所列 ' app@sharepoint ' 使用者詳細資料的[新章節](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records)。
- [新](search-the-audit-log-in-security-and-compliance.md#quarantine-activities)的隔離活動描述。
- 在 [[使用者管理] 活動](search-the-audit-log-in-security-and-compliance.md#user-administration-activities)區段中，闡明當使用者變更自己的密碼（透過自助式密碼重設）時，會觸發「變更使用者密碼事件」，當系統管理員重設使用者的密碼時，就會觸發「重設使用者密碼」事件。

### <a name="auto-expanding-archive"></a>自動展開封存

無限封存（更新）[的概述](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)<br>新增說明在信箱上啟用自動擴充封存後，您無法刪除主封存或輔助封存中的任何資料夾。

### <a name="compliance-scorecompliance-manager"></a>合規性分數/合規性管理員

所有[合規性分數](compliance-score.md)和[合規性管理員](compliance-manager-overview.md)主題會反映出在四月（兩者仍是公開預覽）所發行產品的更新。 主要更新包括：
- 簡化建立及修改範本的程式
- 範本和動作的版本設定通知和控制
- 同步群組中的一般動作
- 語言支援現在已擴充至中文（簡體）、中文（繁體）、法文、德文、義大利文、日文、韓文、葡萄牙文（巴西）、俄文及西班牙文

### <a name="communication-compliance"></a>通訊合規性

[案例研究-Contoso 會快速設定適用于 Microsoft 小組、Exchange 及 Yammer 通訊的冒犯性語言原則](communication-compliance-case-study.md)（新增）<br>教育和小型企業組織的逐步案例研究，可協助他們快速設定冒犯性語言原則。 增加客戶在組織為 COVID19 回應增加的要求。

[開始使用通訊相容性](communication-compliance-configure.md)（更新）<br>更新授權和許可權需求。

### <a name="customer-key"></a>客戶金鑰

[滾動或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)（已更新）<br>組織更新，協助澄清您可以和不能擲出的按鍵。

[瞭解客戶機碼的可用性機碼](customer-key-availability-key-understand.md)（已更新）<br>新增在 Exchange Online 架構中客戶機碼的澄清。

### <a name="data-loss-prevention"></a>資料外洩防護

[資料遺失防護](data-loss-prevention-policies.md)（更新）綜述<br>更新保留標籤生效所需的時間，以及未設定警示的預設行為原則。

### <a name="ediscovery"></a>電子文件探索

[開始使用高級 eDiscovery](get-started-with-advanced-ediscovery.md) （新增）<br>提供授權和許可權需求的相關資訊、設定全域設定的步驟，以及建立新的案例，以及高級 eDiscovery 工作流程的逐步解說。

[舊版 eDiscovery 工具](legacy-ediscovery-retirement.md)（更新）的退休<br>因公開健康情況狀況，退休日期會移出三個月。 更新的文章 cites 新的退休日期。

### <a name="insider-risk-management"></a>測試人員風險管理

[開始使用「內幕風險管理](insider-risk-management-configure.md)」（更新）<br>更新授權和許可權需求。

[定義資訊障礙原則](information-barriers-policies.md)（已更新）<br>闡明處理速度及所需的時間。 新增有關如何不應該存在通訊錄原則的詳細資訊。 也會有各種 PowerShell 程式碼更新，包括篩選的新程式碼。

[資訊障礙](information-barriers.md)（已更新）<br>已修正某些中斷的連結，以及已更新的 PDF 連結和標題。 根據客戶的意見反應，澄清資訊障礙只支援雙向限制。 單向限制（例如，行銷可以與日貿易通訊，但 day 商貿無法與行銷通訊）不受支援。

[疑難排解資訊障礙](information-barriers-troubleshooting.md)（已更新）<br>新增「疑難排解案例」一節。 已新增如何重新應用資訊障礙之步驟的連結。

### <a name="office-365-message-encryption"></a>Office 365 郵件加密

[管理 Office 365 郵件加密](manage-office-365-message-encryption.md)（已更新）<br>更新以反映強制包裝函式的標準 OME 功能，而非高級功能。 Rewrote PowerShell 範例，以排除對「高級 OME」功能撤銷和到期的所有參照。

[郵件加密常見問題](ome-faq.md)（已更新）<br>闡明只有 web 的 Outlook 可以套用特殊加密。 同樣地，針對所有 Outlook 用戶端，郵件和未受保護的 PDF 附件會繼承 Exchange Online 中的資料遺失防護（DLP）原則或郵件流程規則的 OME 保護。

### <a name="privileged-access-management"></a>特殊權限存取管理

[開始使用特殊許可權存取管理](privileged-access-management-configuration.md)（更新）<br>更新授權和許可權需求。

### <a name="pst-import"></a>PST 匯入

匯[入 PST](faqimporting-pst-files-to-office-365.md)檔案的常見問題（更新）<br>新增有關 PST 匯入處理如何處理重複電子郵件專案的常見問題。

### <a name="sensitivity-labels"></a>敏感度標籤

[深入瞭解敏感度標籤](sensitivity-labels.md)（已更新）<br>新增有關 Azure 入口網站中標籤管理的棄用詳細資料，包括[正式通知](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179)的連結。

[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)（已更新）<br>新增「敏感度」標籤讀取者角色的相關資訊，最初隻為標示 PowerShell Cmdlet 提供支援。

[建立及設定敏感度標籤及其原則](create-sensitivity-labels.md#removing-and-deleting-labels)（更新）<br>新增本節說明移除和刪除標籤的後果。

[使用敏感度標籤來保護 Microsoft 小組、microsoft 365 群組和 SharePoint 網站（公開預覽）中的內容](sensitivity-labels-teams-groups-sites.md)（更新）<br>變更包括：

- 已移除 Azure AD 指示，但連結至[AZURE ad 授權資訊](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。
- 更新 [[如何設定網站和群組設定](sensitivity-labels-teams-groups-sites.md#how-to-configure-site-and-group-settings)] 區段，其中包含**Office 365 群組連線之小組網站的隱私權**資訊，其中包含 [**無**新] 選項。
- 新增附注，說明使用者建立小組、群組和網站時，如何只使用具有網站和群組設定的標籤。 這種功能會逐漸推出給組織。

[使用敏感度標籤來限制存取內容，以套用加密](encryption-sensitivity-labels.md)（更新）<br>[新的區段](encryption-sensitivity-labels.md#example-configurations-for-the-encryption-settings)，其中包含一些最常用設定的範例，以保護檔和電子郵件。

[自動將敏感度標籤套用至內容](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)（更新）<br>說明內建標記與 Azure 資訊保護統一標籤用戶端之間的行為差異。

[在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤](sensitivity-labels-sharepoint-onedrive-files.md)（更新）<br>變更包括：

- 闡明啟用此預覽，除了支援標記和加密的檔之外，還會針對網頁中的標籤，顯示標籤的功能區上的**敏感度**按鈕。
- 更新 Office 365 多地理位置的指示。
- 限制清單具有新的專案，包含當電腦離線或睡眠時，以及刪除標籤時會發生什麼情況。

[在 Office 應用程式中使用敏感度標籤](sensitivity-labels-office-apps.md)（更新）<br>變更包括：

- 將授權資訊移至，以[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)。
- [新章節](sensitivity-labels-office-apps.md#labeling-client-for-desktop-apps)說明如何使用內置於 office 桌面應用程式中的標籤，您必須使用 office 的訂閱版本，而不是單機版。
- 支援的應用程式表格包含適用于 iOS 和 Android 的 Office 應用程式，以及可讓使用者指定 Word、Excel 及 PowerPoint 之許可權的設定更新–現在會向內推出 Windows 和 Mac 的每月通道。  
- [新章節](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-other-labeling-solutions)說明如何使用「群組原則」設定來停用內建的標籤，如果您目前使用的是其他要繼續用於 Windows 電腦的標記解決方案。 
- 更新 [[資訊版權管理（IRM）選項和敏感度標籤](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)] 區段，其建議是使用套用加密的標籤，而不是 IRM 選項，並在兩種保護解決方案混合使用時說明可能的結果。

### <a name="trainable-classifiers"></a>Trainable 分類器

[Trainable 分類器（預覽）快速](classifier-getting-started-with.md)入門（更新）<br>新增如何取代冒犯性語言範本的相關資訊。 同時新增一個表格，列出原始程式碼內建分類器中使用的前25種程式碼語言。

## <a name="february-2020"></a>2020 年 2 月

> [!NOTE]
> 上個月所列的文章可能會因為更新、移動或刪除。 因此，下列部分詳細資料可能會過時，而且可能會中斷連結。

### <a name="auditing"></a>稽核

[Microsoft 365 中的高級核查](advanced-audit.md)（新增）<br>適用于使用 Office 365 E5 或 Microsoft 365 企業版 E5 訂閱的組織，「高級核查」會引入功能（例如審核記錄的長保留期間、新的審核記錄保留原則，以及追蹤郵件讀取的新信箱審核動作），以擴充現有的審計功能。

[管理審核記錄保留原則](audit-log-retention-policies.md)（新增）<br>有關管理審核記錄保留原則的詳細資訊，此新的高級審核功能可讓您將不同服務的審計記錄儲存一年以上。

[管理信箱審核](enable-mailbox-auditing.md#logon-types-and-mailbox-actions)（更新）<br>已新增使用高級審核引進的新 MailItemsAccessed 信箱動作的相關資訊。

[搜尋審計記錄](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)檔（更新）<br>新增敏感度標籤活動的新描述，以及審核[表單共同作業活動](search-the-audit-log-in-security-and-compliance.md#forms-activities-performed-by-coauthors-and-anonymous-responders)的其他資訊。

### <a name="compliance-offerings"></a>合規性方案

[ENISA 資訊保證架構](offering-enisa.md)（新增）<br>新的主題，支援歐盟網路和資訊安全代理（ENISA）資訊保證架構（IAF）。

[服務組織控制（SOC）](offering-SOC.md) （更新）<br>新增的審計參考。

[澳大利亞 Prudential 管制機關（APRA）](offering-APRA-Australia.md) （已更新）<br>新法規標準的對齊內容。

### <a name="customer-key"></a>客戶金鑰

[使用客戶金鑰服務加密](customer-key-overview.md)（新增）<br>新文章會向您介紹客戶重要的概念，如 BitLocker 和服務加密等相關概念，以及它們如何共同運作。

[管理客戶金鑰](customer-key-manage.md)（新增）<br>管理客戶機碼的安裝後指示，包括管理現有 DEPs 與主要 vault 許可權的步驟、完成作業的預估時間、如何驗證加密是否有效，以及如何退出服務。

[擲出或旋轉客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)（新增）<br>說明如何為客戶金鑰滾動客戶管理的金鑰。

[瞭解客戶機碼的可用性金鑰](customer-key-availability-key-understand.md)（新增）<br>可用性機碼的詳細資料覆蓋率-何時及如何用來從重要資訊中復原，以及它存在於客戶重要階層中的地方等等。

[設定 Microsoft 365 的客戶金鑰](customer-key-set-up.md)（已更新）<br>先前標題為「使用客戶金鑰控制 Microsoft 365 中的資料」，本文著重于如何設定 Office 365 的客戶金鑰（包括更新的指示）。

### <a name="data-classification"></a>資料分類

[資料分類公開預覽發行附注（預覽）](data-classification-pub-preview-relnotes.md) （新增）<br>公開預覽的版本資訊會引入新功能，讓您的敏感和標示內容的掃描會在您建立任何原則之前開始。 這可讓您複查現有的保留和敏感度標籤如何影響您的組織，以協助您評估保護和控管原則需求。

### <a name="gdpr"></a>GDPR

[GDPR 和 CCPA 的 Office 365 資料主體要求](gdpr-dsr-Office365.md)（更新）<br>由於[停用應用程式](https://docs.microsoft.com/microsoftteams/expand-teams-across-your-org/shifts/microsoft-staffhub-to-be-retired)，因此已移除對 Microsoft StaffHub 的參照。

在下列文章中新增合規性管理員參考和更新的合規性分數連結。<br>
[一般資料保護規定摘要](gdpr.md)（本文也包括來自信任中心的新 FAQs。）<br>
[Microsoft 365 GDPR 行動計畫 — 前 30 天、90 天及過後的首要工作](gdpr-action-plan.md)<br>
[使用責任整備檢查清單支援 GDPR 計劃](gdpr-arc.md)<br>
[符合 GDPR 的 Azure 責任整備程度檢查清單](gdpr-arc-Azure.md)<br>
[符合 GDPR 的 Dynamics 365 責任整備程度檢查清單](gdpr-arc-Dynamics365.md)<br>
[適用於 Microsoft Office 365 的責任整備檢查清單](gdpr-arc-Office365.md)<br>

### <a name="insider-risk-management"></a>測試人員風險管理

更新下列文章，以支援正式發行的有問必答風險管理。<br>
[深入瞭解 Microsoft 365 中的內幕人士風險管理](insider-risk-management.md)<br>
[開始使用測試人員風險管理](insider-risk-management-configure.md)<br>
[建立及管理測試人員風險原則](insider-risk-management-policies.md)<br>
[調查測試人員風險警示](insider-risk-management-alerts.md)<br>
[對測試人員風險案例採取動作](insider-risk-management-cases.md)<br>
[使用測試人員風險內容總管檢閱資料](insider-risk-management-content-explorer.md)<br>
[將使用者新增到測試人員風險原則](insider-risk-management-users.md)<br>
[建立有問必答風險通知](insider-risk-management-notices.md)<br>

### <a name="records-management"></a>記錄管理

[保留標籤簡介](labels.md)（已更新）<br>根據條件套用保留標籤的區段包括使用 trainable 的分類程式的選項。

### <a name="sensitivity-labels"></a>敏感度標籤

[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)（新增）<br>包含 Azure 資訊保護客戶的指導方針、部署敏感度標籤的程式和步驟的高層次概述、建立及管理標籤的許可權，以及支援標籤的常見案例清單，以及可用的最終使用者檔案清單。

[深入瞭解敏感度標籤](sensitivity-labels.md)（已更新）<br>Retitled 「敏感度標籤」，並將「入門」一節中的資訊移至新文章[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)。

[建立及設定敏感度標籤及其原則](create-sensitivity-labels.md)（更新）<br>將許可權詳細資料移至新文章，[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)。

[使用敏感度標籤來限制存取內容，以套用加密](encryption-sensitivity-labels.md)（更新）<br>新的 [無] 和 [移除] 選項會取代加密切換，而新增「新增任何已驗證的使用者」是立即指派的新許可權。 現在會更新讓使用者指派許可權的區段，以提示使用者在 Word、PowerPoint 及 Excel 中選取自訂許可權。 新章節範例設定如何設定加密設定以支援特定的使用案例。 新區段，列出加密內容的考慮。

[自動將敏感度標籤套用至內容](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)（更新）<br>設定 Office 應用程式自動標籤的區段現在包含使用 trainable 類元的新選項。

[使用敏感度標籤來保護 Microsoft 小組、microsoft 365 群組和 SharePoint 網站（公開預覽）中的內容](sensitivity-labels-teams-groups-sites.md)（更新）<br>進行修訂，以取得更好的閱讀體驗和技術說明。 此外，根據客戶的意見反應，新增[AZURE AD 文章](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)的連結，以啟用預覽，以及將敏感度標籤套用至 azure 入口網站中的 Microsoft 365 群組。 最後，新增一個用於審核敏感度標籤活動的區段。

[啟用 SharePoint 和 OneDrive （公開預覽）中的 Office 檔案敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)（已更新）<br>各種更新包含每個客戶對於此功能運作方式的意見反應的說明，強調新功能只會套用至新的和編輯的檔案，而且在刪除標籤時，您可能只會在測試階段看到的新限制。

[在 Office 應用程式中使用敏感度標籤](sensitivity-labels-office-apps.md)（更新）<br>更新功能表格，讓使用者可以自動指派許可權並對內容套用標籤。 此外，根據客戶的意見反應，新增繼承標籤的電子郵件附件例外狀況。

### <a name="service-descriptions"></a>服務說明

[安全性 & 合規性的 Microsoft 365 授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)（更新）<br>從「Microsoft 365 租使用者層級服務授權指南」 Retitled，以更好地反映內容。

