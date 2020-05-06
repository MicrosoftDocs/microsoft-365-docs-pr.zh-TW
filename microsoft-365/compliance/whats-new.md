---
title: 合規性中心的新功能
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
description: 我們不斷將新功能新增至 Microsoft 365 規範中心，以修正我們所學的問題，並根據您的意見反應進行變更。 請找出我們所學的月份。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 940d316c97370a477c963785ae7e90482b35a46c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034265"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Microsoft 365 規範中心的新功能

我們不斷將新功能新增至[Microsoft 365 規範中心](microsoft-365-compliance-center.md)，以修正我們所學的問題，並根據您的意見反應進行變更。 請參閱下列內容，以查看今天可提供的功能。 有些功能會以不同的速度向客戶推出。 如果您還沒有看到功能，請嘗試將您新增至[目標版本](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 對其他系統管理中心的進展感興趣嗎？ 請參閱下列文章：<br>[Microsoft 365 系統管理中心的新功能](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 系統管理中心的新功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br><br>
請造訪[microsoft 365 藍圖](https://www.microsoft.com/en-us/microsoft-365/roadmap)，以瞭解已啟動、已開發、已取消或先前發佈的 microsoft 365 功能。

## <a name="february-2020"></a>2020 年 2 月

### <a name="insider-risk-management-is-officially-released"></a>已正式發行內幕風險管理

鼓滾，請 .。。<br>「內部人員風險管理」現在可供組織使用下列訂閱：

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) （付費或試用版）
- Microsoft 365 Enterprise E3 訂閱與[Microsoft E5 合規性附加](https://go.microsoft.com/fwlink/?linkid=2120432)元件

請注意，自預覽發行後我們進行了一些改進，包括[新的角色群組](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management)和[全方案設定](insider-risk-management-configure.md#step-4-required-configure-insider-risk-settings)。

一如既往，請在您使用解決方案時留下意見反應，讓我們能夠繼續進行改進。

### <a name="records-management"></a>記錄管理

這個新的解決方案會將所有記錄管理功能置於單一傘底下。 要聞包括記錄的 SharePoint 和 OneDrive 的記錄版本，以及記錄的處置證明。

![Microsoft 365 規範中心內的記錄管理頁面](../media/mcc-records-management-page.png)

[深入瞭解記錄管理](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>解決方案聚光燈： Facebook 和 Twitter 的資料連線器

[最後一個月發行](#just-launched)的資料連線器，我們正在尋找您的協助，以測試下列連接器。

- [Facebook 商務頁面](archive-facebook-data-with-sample-connector.md)。 將 Facebook 商務頁面上的資料匯入及封存至 Microsoft 365。 有益性解決方案（如記錄管理和 eDiscovery）。
- [Twitter](archive-twitter-data-with-sample-connector.md)。 從 Twitter 將資料匯入並封存至 Microsoft 365。 有益性解決方案（如記錄管理和 eDiscovery）。

當您設定和驗證這些連接器時，請讓我們對問題的反應提供反應，哪些是未的，以及我們可如何進行以改進體驗的意見。

## <a name="january-2020"></a>2020 年 1 月

等候已過。 我們很樂意宣告 Microsoft 365 規範中心可供所有使用 Microsoft 365、Office 365、企業行動性 + 安全性（EMS）和 Windows 10 企業版方案的客戶使用。 您在安全性 & 合規性中心內管理的任何資料或原則都是在「規範中心」中提供，所以不需要來回跳轉。

> [!TIP]
> 請再次閱讀去年的更新，以取得我們最近預覽之一些[新方案](#new-compliance-solutions)的複習，以及顯示安全性 & 合規性中心的相容性功能目前在 Microsoft 365 中的活動[藍圖](#updated-compliance-solutions)。

[書簽和頭部]， [https://compliance.microsoft.com](https://compliance.microsoft.com)以導覽您在整個組織中管理法規遵從性的單一光圈。您也可以[閱讀本文](microsoft-365-compliance-center.md)以進一步深入。

![Microsoft 365 規範中心首頁](../media/mcc-home-ga.png)

我們也在本月發佈新的和更新的解決方案。 以下是重點講述的快捷流覽。

### <a name="now-in-preview"></a>現在預覽

**有問必答風險管理（預覽）**

我們很樂意宣告，我們的有問必答風險管理解決方案現在是公開預覽。 簡而言之，有問必答風險管理可協助您的組織，透過提供下列各項，以智慧識別並採取對內幕程式風險的動作：

- 匿名控制，以協助確保使用者的隱私權。
- 智慧原則範本，具有可識別內部攻擊的原生和協力廠商指示符，例如資料洩漏。
- 跨 IT、HR 和法律團隊的整合端對端調查工作流程。

我們很樂意聽到您想像的專案。 當您使用方案時，請留下我們的意見反應，讓我們能確定，我們在提供一般可用性的情況下，滿足您的需求。

[深入瞭解內幕人士風險管理](insider-risk-management.md)

### <a name="just-launched"></a>剛啟動

**通訊合規性**

從預覽階段 Graduating 為 [完整可用性]，通訊相容性是我們新的有問必答風險方案集中的重要元件。 這種強大的解決方案可協助將使用工作流程的通訊風險降到最低，以偵測、調查和採取針對不符合組織標準的郵件進行修正動作。

預覽期間的客戶意見反應極棒。 它會產生數種增強功能，包括初次執行體驗，讓您開始、調查和修正動作的增強功能等等。

[深入瞭解通訊法規遵從性](communication-compliance.md)

![Microsoft 365 規範中心中的通訊相容性頁面，顯示歡迎體驗的第一張卡片](../media/mcc-communication-compliance-page-with-fre.png)

**資料連線器**

先前與 Office 365 安全性 & 合規性中心中的其他「匯入」功能共用空間，資料連線器現在在 Microsoft 365 規範中心擁有其專屬的家用。 使用新的「資料連線器」頁面，從組織的人力資源（HR）檔案和各種協力廠商平臺（如 Facebook、LinkedIn、Twitter 及立即 Bloomberg）匯入和封存您的 Microsoft 365 組織中的信箱資料。 一旦匯入之後，就可以透過數個規範解決方案管理此資料，包括 eDiscovery、內幕風險管理、通訊相容性、審核、保留原則等等。

[深入瞭解資料連線器](archiving-third-party-data.md)

![Microsoft 365 規範中心內的資料連線器頁面](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>值得注意的更新

**遵循規範評分的新評估範本（預覽）**

永遠致力於協助您走出不斷發展的合規性形勢，我們的合規性分數小組已提供一組新的範本，協助您評估組織對最近法規的相容性狀況，並取得如何實施更有效率的控制的指導。 您會看到新的範本：

- ISO/IEC 27701:2019
- 加州消費者隱私法 (CCPA)
- 巴西一般資料保護法（Lei Geral de Proteção de Dados-LGPD）
- SOC 1 Type 2 和 SOC 2 Type 2

[深入瞭解合規性分數範本](compliance-score.md#templates)

## <a name="november--december-2019"></a>11月 & 2019 月

透過節日，我們已開始推出 Ignite 中示範的所有極佳規範解決方案。 大多數是以預覽狀態進行測試，因此請在規範中心的右下方，開啟回饋卡片，以進行測試，並確定讓我們知道您的想法。

![回饋](../media/Feedback_card_MCC.JPG)

### <a name="get-to-know-the-new-neighborhood"></a>瞭解新的鄰居

新的 Microsoft 365 規範中心包括全新的解決方案，以及您從 Office 365 安全性 & 規範中心所知道和喜愛的規範功能。 讓我們進一步深入探討 .。。

#### <a name="new-compliance-solutions"></a>新的規範解決方案

您可能會想知道*解決方案*的含義。 只要雲端已徹底增加業務的方式，也就是針對新的資料竊取及欺詐和要求新規定的方法開啟門。 我們的規範解決方案是整合功能的集合，可協助您協助您管理這些不斷演化的合規性需求。 方案的功能可能包括原則、警示、報告等的組合。

以下是您將會發現的新解決方案摘要。 請留意即將推出的其他人員。

> [!NOTE]
> 這些解決方案僅位於 Microsoft 365 規範中心。 它們無法在 Office 365 安全性 & 規範中心內進行管理。
<br/>

|**新方案**|**描述**|**深入了解**|
|:-----|:-----|:-----|
|Microsoft 合規性分數（預覽） <br/>|從[合規性管理員](compliance-manager-overview.md)內建，相容性分數是一項獨立的功能，具有簡化、便於使用使用者的設計，可協助您瞭解及改善組織的合規性狀況。 它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。 <br/>|[Microsoft 合規性分數概述（預覽）](compliance-score.md)|
|方案目錄（預覽） <br/>|方案目錄是一種可讓您探索、深入瞭解及快速開始使用我們的合規性和風險管理解決方案的單一停止車間。 目錄會組織成三個符合性類別，每個類別包含組成該類別之解決方案的詳細資料。 類別包括資訊保護 & 控管、內幕風險管理，以及探索 & 回應 <br/>|[方案目錄的概覽（預覽）](microsoft-365-solution-catalog.md)|
|通訊相容性（預覽） <br/>|通訊相容性是新的有問必答風險管理類別的一部分，可協助您針對組織中的不適當郵件偵測、捕獲和採取補救措施，以協助將通訊風險降到最低。 此方案透過引進一些新的增強功能（如智慧範本、彈性修復工作流程及可行動的觀點），擴充 Office 365 中監管原則的功能。 <br/>|[Microsoft 365 中的通訊法規遵從性（預覽）](communication-compliance.md)|
|資料分類（預覽） <br/>|我們新的資料分類頁面包含強大的洞察力和工具，可協助您探索和評估敏感資訊和標籤（保留和敏感度）在組織中的內容中的使用方式。 回顧包含機密資訊或已套用標籤的內容、探索各個 Microsoft 365 位置的標籤活動、建立自訂機密資訊類型，以及更多。<br/>|[資料分類概觀 (預覽)](data-classification-overview.md)|
|Trainable 分類器（預覽） <br/>|這個強大的新工具使用我們的機器學習引擎，協助識別您的組織中的內容類別別，例如法規檔或員工合約。 建立後，可使用多個規範方案中的分類器來偵測相關的內容，並加以分類、保護、保留，等等。<br/>|[開始使用可訓練的分類器 (預覽)](classifier-getting-started-with.md)|

#### <a name="updated-compliance-solutions"></a>更新的規範解決方案

如果您已使用 Office 365 的安全性 & 規範中心來滿足您的規範需求，您可能會想要讓某些功能在新的 Microsoft 365 規範中心中的功能成為現實。 以下是協助您尋找新家的快速藍圖。

> [!NOTE]
> 有些功能仍可用於 Office 365 安全性 & 規範中心-以下說明。 不過，我們現在致力於在 Microsoft 365 規範中心預覽這些功能，以繼續調整更新。 
<br/>

|**功能**|**Office 365 安全性與合規性中心**|**Microsoft 365 合規性中心**|**深入了解**|
|:-----|:-----|:-----|:-----|
|進階電子文件探索|eDiscovery > Advanced eDiscovery <br/> https://protection.office.com/advancedediscoverycases |eDiscovery > 高級 <br/> https://compliance.microsoft.com/advancedediscovery | [Microsoft 365 中的高級 eDiscovery 解決方案概述](overview-ediscovery-20.md) |
|警示原則|警示原則 > 警示原則 <br/> https://protection.office.com/alertpolicies |此時，只會在 Office 365 安全性 & 合規性中心管理警示原則。 |[安全性與合規性中心內的警示原則](alert-policies.md) |
|警示|警示 > View alerts <br/> https://protection.office.com/viewalerts |警示 <br/> https://compliance.microsoft.com/compliancealerts |[查看提醒](alert-policies.md#viewing-alerts)|
|封存|資訊管理 > 封存 <br/> https://protection.office.com/archiving |資訊管理 > 封存] 索引標籤 <br/> https://compliance.microsoft.com/informationgovernance?viewid=archive |[啟用封存信箱](enable-archive-mailboxes.md)|
|稽核記錄檔搜尋|搜尋 > 審計記錄搜尋 <br/> https://protection.office.com/unifiedauditlog |審計 <br/> https://compliance.microsoft.com/auditlogsearch | [在安全性 & 規範中心搜尋審核記錄檔](search-the-audit-log-in-security-and-compliance.md)|
|內容搜尋|搜尋 > 內容搜尋 <br/> https://protection.office.com/contentsearchbeta?ContentOnly=1 | 內容搜尋 <br/> https://compliance.microsoft.com/contentsearch |[在 Office 365 中搜尋內容](search-for-content.md) |
|資料連線器|資訊管理 > 封存協力廠商資料 <br/> https://protection.office.com/nativeconnector | 資料連線器 <br/> https://compliance.microsoft.com/connectorlanding |[封存第三方資料](archiving-third-party-data.md)|
|資料外洩防護|資料外洩防護 <br/> https://protection.office.com/datalossprevention |資料外洩防護 <br/> https://compliance.microsoft.com/datalossprevention |[資料外洩防護概觀](data-loss-prevention-policies.md)|
|資料主體要求 |資料隱私權 > 資料主體要求 <br/> https://protection.office.com/dsrcases |資料主體要求 <br/> https://compliance.microsoft.com/datasubjectrequest |[使用 DSR 案例工具管理 GDPR 資料主體要求](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md)|
|電子文件探索|eDiscovery > eDiscovery <br/> https://protection.office.com/ediscoveryv1 |eDiscovery > 核心 <br/> https://compliance.microsoft.com/classicediscovery |[管理電子文件探索案例](ediscovery-cases.md) |
|事件|記錄管理 > 事件 <br/> https://protection.office.com/events |記錄管理 > 事件] 索引標籤 <br/> https://compliance.microsoft.com/recordsmanagement?viewid=events |[事件導向保留的概觀](event-driven-retention.md)|
|檔案計畫|記錄管理 > 檔計畫 <br/> https://protection.office.com/fileplan |記錄管理 > 檔計畫] 索引標籤 <br/> https://compliance.microsoft.com/recordsmanagement?viewid=fileplan |[檔案計劃管理員的概觀](file-plan-manager.md)|
|匯入 PST 檔案|資訊管理 > 匯入 PST 檔案 <br/> https://protection.office.com/importV2 |資訊控管 > 匯入] 索引標籤 <br/> https://compliance.microsoft.com/informationgovernance?viewid=import |[將組織的 PST 檔案匯入的概觀](importing-pst-files-to-office-365.md)|
|標籤活動瀏覽器|資訊控管 > 標籤活動瀏覽器 <br/> https://protection.office.com/labelexplorer |資料分類 > 活動流覽] 索引標籤 <br/> https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer |[檢視套用標籤的內容上的活動 (預覽)](data-classification-activity-explorer.md)|
|保留標籤及標籤原則 |分類 > 保留標籤 > 標籤及標籤原則] 索引標籤 <br/> https://protection.office.com/retentionlabels |資訊控管 > 標籤及標籤原則] 索引標籤 <br/> https://compliance.microsoft.com/informationgovernance?viewid=labels <br/> https://compliance.microsoft.com/informationgovernance?viewid=labelpolicies | [保留標籤概觀](labels.md)|
|保留原則|資訊管理 > 保留 <br/> https://protection.office.com/retention |資訊管理 > 保留] 索引標籤 <br/> https://compliance.microsoft.com/informationgovernance?viewid=retention |[保留原則概觀](retention-policies.md)|
|敏感資訊類型|分類 > 敏感資訊類型 <br/> https://protection.office.com/sensitivetypes |資料分類 > 敏感度資訊類型] 索引標籤 <br/> https://compliance.microsoft.com/dataclassification?viewid=sensitiveinfotypes |[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)|
|敏感度標籤及標籤原則|分類 > 敏感度標籤 > 標籤及標籤原則] 索引標籤 <br/> https://protection.office.com/sensitivity |資訊保護 > 標籤及標籤原則] 索引標籤 <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabels <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabelpolicies |[了解敏感度標籤](sensitivity-labels.md) |
|服務保證|服務保證 <br/> https://protection.office.com/serviceassurance/dashboard |目前，服務保障資源只可在 Office 365 安全性 & 規範中心存取。 |[安全性 & 規範中心的服務保證](service-assurance.md)|
|監督|監督 <br/> https://protection.office.com/supervisoryreviewv2 |通訊合規性 <br/> https://compliance.microsoft.com/supervisoryreview |[Microsoft 365 中的通訊法規遵從性（預覽）](communication-compliance.md) |

## <a name="september-2019"></a>2019 年 9 月

想知道為何在這個月的發行前靜音？ 我們的頭部是建立新的創新規範解決方案，該解決方案會在11月 unveiled [Microsoft Ignite](https://www.microsoft.com/ignite) 。 敬請關注！

### <a name="new-encryption-options-for-sensitivity-labels"></a>敏感度標籤的新加密選項 

設定敏感度標籤的加密時，您現在有兩個選項可讓使用者在手動將標籤套用至電子郵件及檔時，指派許可權：<br>
- 將標籤套用至**Outlook 電子郵件**時，使用者可強制執行與 [不要轉寄] 選項同等的限制。 收件者將可以讀取郵件，但不能轉寄、列印或複製內容。
- 將標籤套用至**Word、PowerPoint 及 Excel**檔案時，系統會提示使用者將存取權限指派給特定的使用者和群組。

[深入了解](encryption-sensitivity-labels.md#let-users-assign-permissions)

## <a name="august-2019"></a>2019 年 8 月

### <a name="update-to-data-investigations"></a>更新資料調查

在執行資料調查時，您現在可以從原始位置刪除專案。 這表示您可以在組織內刪除 Exchange 信箱、SharePoint 網站和 OneDrive 帳戶中的專案。 因為您已將專案收集為證據，所以您可以在證據集中保留這些專案的副本，以進行進一步調查或只保留為參考。 [深入了解](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) 

## <a name="july-2019"></a>2019 年 7 月

### <a name="new-admin-roles"></a>新系統管理員角色

我們發行兩個新的系統管理員角色，以協助管理您組織中的安全性和合規性。請告訴您的所有朋友。

- **合規性資料管理員**。具有此角色的使用者具有在 Microsoft 365 規範中心、Microsoft 365 系統管理中心和 Azure 中保護和追蹤資料的許可權。 他們也可以管理 Exchange 系統管理中心、合規性管理員、小組 & 商務用 Skype 系統管理中心的所有專案，以及建立 Azure 和 Microsoft 365 的支援票證。
- **Security 運算子**。 具有此角色的使用者可以管理提醒，並具有安全相關功能的全域唯讀許可權，包括 Microsoft 365 安全性中心、Azure Active Directory、Identity Protection、特權身分識別管理和 Office 365 安全性 & 合規性中心的所有專案。

[深入瞭解這些角色](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>搜尋及篩選報表

不會在報表的海洋中向內滾動，以找出您想要的專案。 您現在可以搜尋報告（根據其標題），並篩選類別如「標籤」和「符合性」，以及「Office 365」和「Microsoft Cloud App Security」之類的來源。

![具有套用篩選之報表之搜尋和篩選按鈕的螢幕抓隨](../media/mcc_report_filtering.png)
