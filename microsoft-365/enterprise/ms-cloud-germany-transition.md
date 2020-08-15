---
title: 從 Microsoft Cloud Germany (Microsoft Cloud Deutschland) 移轉到新德國資料中心區域中的 Office 365 服務
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 07/09/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 摘要：了解如何從 Microsoft Cloud Germany (Microsoft Cloud Deutschland) 移轉到新德國資料中心區域中的 Office 365 服務。
ms.openlocfilehash: cfbd3b7406f7c7824f736633e3a4dba6fa5c4bff
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688684"
---
# <a name="migration-from-microsoft-cloud-germany-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>從 Microsoft Cloud Germany (Microsoft Cloud Deutschland) 移轉到新德國資料中心區域中的 Office 365 服務


>[!Note]
>本文僅適用於符合資格的 Microsoft Cloud Germany/Deutschland 客戶。
>

## <a name="cloud-service-offerings-in-germany"></a>德國的雲端服務選項

2018 年 8 月，我們宣佈打算從德國的新雲端區域提供完整的 Microsoft 雲端服務 – Azure、Office 365、Dynamics 365 和 Power Platform – 以為客戶的數位化轉型提供更好的協助。 2019 年 8 月，我們宣佈我們正在開放德國的新雲端區域。 我們宣佈 Azure 將於 8 月發佈，Office 365 將於 12 月發佈。  Dynamics 365 和 Power Platform 預計會在 2020 年第一季推出。  

這些新區域目的在透過更靈活、最新的智慧雲端服務，和與我們全球雲端網路的完全軌接搭配德國境內的客戶資料來滿足德國客戶不斷發展的需求。

## <a name="moving-to-the-new-german-regions"></a>移至新的德國區域

現有的 Microsoft Cloud Germany (Microsoft Cloud Deutschland) 客戶現在可以開始移轉他們的 Office 365、Dynamics 365 Customer Engagement 和 Power Platform BI 客戶。  第一個步驟是 [選擇加入由 Microsoft 主導的移轉](https://aka.ms/office365germanymoveoptin)，以加入到我們新的德國資料中心區域。

如果組織選擇加入由 Microsoft 主導的方式，預期會在 2020 年進行移轉。 移轉之後，核心客戶資料和訂閱都會移至新的德國區域。 

下列服務將以 Microsoft 主導的方法移轉：

- Azure Active Directory
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- 商務用 OneDrive
- 商務用 Skype Online

從 Microsoft Cloud Germany 移轉到德國資料中心區域期間，現有的商務用 Skype Online客戶將過渡為使用 Microsoft Teams。 如需詳細資訊，請參閱[開始進行您的 Microsoft Teams 升級](https://aka.ms/SkypeToTeams-Home)。

- Office 365 群組
- Dynamics 365 / Power Platform

將在 [Dynamics 365 Customer Engagement](https://aka.ms/d365ceoptin) 文章中說明這些服務的移轉先決條件與影響。

Office 365 影片即將于年 2021年 3月 1日停用。 如果您選擇將 Office 365 租用者移至新的德國資料中心區域，在 SharePoint Online 遷移完成之後，將不會支援 Office 365 影片。 [深入了解](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>如何準備移轉至新的德國資料中心區域中的 Office 365 服務

第一個步驟是通知 Microsoft，讓我們獲得您的授權將您的訂閱和資料從 Microsoft Cloud Germany/Deutschland 移轉到新的德國資料中心區域中的 Office 365 服務。  如需相關指示，請參閱[選擇加入程序](ms-cloud-germany-migration-opt-in.md)。

- 所有移轉的客戶都需要驗證與全球 [Office 365 URL 和 IP 位址](urls-and-ip-address-ranges.md)的連線能力，其中包含新的德國資料中心區域。
- 查看 Office 365 平台服務描述，了解您的組織在德國區域完成之後將可使用哪些功能和服務。 
- 移轉將會轉換付費訂閱。  我們無法移轉試用版訂閱。

租用戶的移轉是以後端服務作業的方式執行，不太需要客戶互動。  任何其他的客戶主導的工作和整體移轉狀態都會透過訊息中心，在移轉過程中告知。  工作範例可能包括客戶管理的 DNS 更新，或 Exchange 混合式客戶的混合式設定重新設定。

## <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>在移轉至新的德國資料中心區域中的 Office 365 服務期間的客戶經驗

租用戶的移轉設計為將客戶和系統管理員的影響降至最低。  不過，每個工作負載都有需要考慮的事項。  

### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft Cloud Germany 的 Office/Dynamics 訂閱會以 Azure Active Directory (Azure AD) 重新調整的方式轉換成德國區域。 然後會更新組織，以反映新的全球服務訂閱。 在簡短的訂閱轉移過程中，將會阻止變更訂閱。

### <a name="exchange-online"></a>Exchange Online

Exchange Online 混合式客戶必須重新執行 [混合式設定精靈]，以在移轉之前更新 Microsoft Cloud Germany 的內部部署設定，並在針對全球服務進行清理時重新執行 HCW。 如果客戶擁有自訂網域，可能需要進行額外的 DNS 更新。

信箱會以後端程序的方式移轉，組織中的使用者在移轉期間可能會處於 Microsoft Cloud Germany 或德國區域，且屬於相同的 Exchange 組織 (GAL)。

### <a name="exchange-online-protection"></a>Exchange Online Protection

將後端 Exchange Online Protection 複製到新的德國區域

### <a name="sharepoint-online"></a>SharePoint Online

當 SharePoint Online 移轉到德國區域完成後，會重新建立資料索引。 在重新索引完成時，依賴搜尋索引的功能可能會受到影響。

系統會針對已移轉的組織保留現有的 sharepoint.de Url。

### <a name="onedrive-for-business"></a>商務用 OneDrive

當商務用 OneDrive 移轉至德國區域完成後，會重新建立資料索引。 在重新索引完成時，依賴搜尋索引的功能可能會受到影響。

### <a name="skype-for-business-online"></a>商務用 Skype Online

現有的商務用 Skype Online 客戶將會移轉 Microsoft Teams。 如需詳細資訊，請參閱 [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home)。

### <a name="office-365-video"></a>Office 365 影片
Office 365 影片的內容將會在 SharePoint Online 遷移過程中進行遷移。 然而，Office 365 正在被停用，且在 SharePoint Online 遷移到新的德國資料中心區域之後，將不會支援 Office 365 影片。 在 SharePoint 遷移之後，Office 365 影片中的影片將無法在 Office 365 影片 UI 中播放。

我們不會將 Microsoft Stream 部署到 Microsoft 德國，而且目前沒有對於在新的德國資料中心區域中部署 Microsoft Stream 的時程規劃。 如此一來，此區域中將不會提供 Office 365 影片的任何遷移工具至 Microsoft Stream。 若要保留您的內容，您必須在 2021年 3月 1日之前，手動下載或移動內容。 [深入了解](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)


## <a name="key-differences-between-microsoft-cloud-germany-microsoft-cloud-deutschland-and-office-365-services-in-the-new-german-datacenter-regions"></a>Microsoft Cloud Germany (Microsoft Cloud Deutschland) 和新德國資料中心區域中的 Office 365 服務的主要差別


|| Microsoft Cloud Germany (Microsoft Cloud Deutschland) | 新德國資料中心區域中的 Office 365 服務 |
|:-------|:-----|:-----|
| Microsoft 365 服務可供訂閱，且只有一個 Office 365 租用戶 | 15 個服務 (請參閱 REF) | 29 個服務 (請參閱 REF) |
| 新功能 | 沒有新功能。 | 將與全球 Office 365 服務一起提供新功能。 |
| 資料信任者 | 是 | 否 |
| 與全球 Office 365 租用戶的跨租用戶共同作業 | 否 | 是 |
| 客戶資料存留處 | 客戶資料將個別儲存在德國資料中心。 | Microsoft 會將下列客戶資料單獨儲存在德國：Exchange Online 信箱內容 (電子郵件內文、行事曆項目和電子郵件附件的內容)，SharePoint Online 網站內容以及該網站中儲存的檔案及上傳到商務用 OneDrive 的檔案。 |
| 適用條款 | [線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)與[補充條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="is-migration-required"></a>需要移轉嗎？

Microsoft 提供 Office 365 租用戶從 Microsoft Cloud Germany 移轉到新德國資料中心區域中的 Office 365 服務，且不額外收費。  我們強烈建議您選擇加入移轉到新的德國資料中心區域，我們會繼續提供必要的安全性更新至 Microsoft Cloud Germany 區域。  

新德國資料中心區域中的 Office 365 服務享有額外權益：

- 為 [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)，以及 [Power BI](https://powerbi.microsoft.com/pricing/) 提供具有市場競爭力的價格。 
- 已連線至 Microsoft 全球網路、提供數百個網路邊緣網站、對等位置，以及出口點，以在世界各地為您提供健全的使用者體驗。 
- 協助您在德國符合本地客戶資料的存留需求。 
- 提供功能完整的全球雲端服務，包括最新版本的服務和新功能，包括 Office 365 中的 Microsoft Teasms 和多地理位置。 依地區比較 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md) 和 [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) 產品。
- 提供完整的功能、企業級的安全性及全面的功能，協助客戶符合合規性和法規需求。 
- 可透過現有的線上服務合約取得。

#### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>不同的 Office 365 雲端服務選項之間的服務可用性為何？

Microsoft Cloud Germany (Microsoft Cloud Deutschland) 雲端服務選項提供下列 15 個服務。  我們不會新增服務至 Microsoft Cloud Germany。

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. 群組 (新式群組)
4. Delve 設定檔
5. Exchange Online Protection
6. 進階威脅防護 (ATP)
7. 進階電子文件探索
8. 進階資料控管
9. SharePoint Online
10. Customer Lockbox (SharePoint Online)
11. 商務用 OneDrive
12. 商務用 Skype
13. Word Online、Excel Online、PowerPoint、OneNote、Visio Online
14. Office 365 專業增強版
15. Outlook Mobile

目前新德國資料中心區域提供 29 個服務做為 Office 365 服務的一部分。  將持續與全球 Office 365 服務一起提供新功能和服務。

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. 群組 (新式群組)
4. Delve 設定檔
5. MyAnalytics
6. 工作場所分析
7. Exchange Online Protection
8. 進階威脅防護 (ATP)
9. 進階電子文件探索
10. 進階安全性管理
11. 資訊版權管理
12. 進階資料控管
13. SharePoint Online
14. Customer Lockbox (SharePoint Online)
15. 商務用 OneDrive
16. Microsoft Stream
17. 商務用 Skype (移轉期間將移轉至 Microsoft Teams)
18. Cloud PBX
19. PSTN 會議
20. PSTN 電話
21. Microsoft Teams
22. 系統管理報告/使用狀況報告
23. Word Online、Excel Online、PowerPoint、OneNote 和 Visio Online
24. Planner
25. Sway
26. Office 365 專業增強版
27. Outlook Mobile
28. EMS E3 (Azure Active Directory Premium P1 + Intune + 版權管理服務)
29. Yammer Online

### <a name="when-will-migration-happen"></a>何時會進行移轉？

#### <a name="azure"></a>Azure 

您可以立即將 Azure 資源[移轉](https://docs.microsoft.com/azure/germany/germany-migration-main)到另一個區域。 如果您使用的是 Office 365、Dynamics 365 和/或 Power BI 的 Azure，請按照下列步驟操作。

#### <a name="office-365"></a>Office 365

立即[選擇加入](https://aka.ms/office365germanymoveoptin) Microsoft 主導的移轉。 當我們準備好開始您的移轉時，我們會透過 Microsoft 365 系統管理中心的[訊息中心](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)來通知您。

#### <a name="dynamics-365-and-power-bi"></a>Dynamics 365 和 Power BI

立即為 [Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) 和 [Power BI](https://aka.ms/PBIOptIn) 選擇加入 Microsoft 主導的移轉。 當我們準備好開始您的移轉時，我們會透過 Microsoft 365 系統管理中心的[訊息中心](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)來通知您。

### <a name="will-the-price-change-for-the-office-services-that-i-use"></a>我使用的 Office 服務價格會有變化嗎？

會的，Microsoft 全球雲端區域 (包括新資料中心區域) 的價格通常較低。

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>如何取得 Microsoft 的協助來移轉到新的區域或解答支援問題？

如有任何問題，您可以按照下列步驟或透過合作夥伴與我們聯繫：

- 針對 Azure，您可以在 Azure 入口網站中提交[新的支援要求](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)。
- 針對 Office 365，您可以使用「需要協助嗎？」連結來提交問題 (在 [Microsoft 365 系統管理中心](https://portal.office.de/)中)。
- 對於也有 Office 365 的 Dynamics 365 Customer Engagement 和Power BI 客戶，您可以使用「需要協助嗎？」連結來提交問題 (在 [Microsoft 365 系統管理中心](https://portal.office.de/)中)。 Dynamics 365 Customer Engagement 支援選項在[這裡](https://docs.microsoft.com/dynamics365/get-started/support/)。 Power BI 支援選項在[這裡](https://powerbi.microsoft.com/support/)。

## <a name="more-information"></a>詳細資訊

- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](https://aka.ms/office365germanymoveoptin)
- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [Office 365 URL 與 IP 位址範圍](https://aka.ms/o365endpoints)
- [Office 365 混合組態精靈](https://aka.ms/HybridWizard)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
