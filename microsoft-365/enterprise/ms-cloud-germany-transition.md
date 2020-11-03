---
title: 從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
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
ms.openlocfilehash: 23ccc30bab5d1045e4716cd637899e20362fc597
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846937"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務

> [!NOTE]
> 本文僅適用于合格的 Microsoft Cloud Deutschland customers。

在2018年8月，Microsoft 宣佈我們對從德國的新雲端地區提供完整的 Microsoft 雲端– Azure、Office 365、Dynamics 365 和電源平臺的目的，以更好地啟用我們客戶的數位轉換。 2019 年 8 月，我們宣佈我們正在開放德國的新雲端區域。 自宣佈，我們已宣告 Azure、Office 365、Dynamics 365 及電源平臺的可用性。

新的地區設計目的是為了處理更靈活的德國客戶需求、最新的智慧雲端服務，以及 Microsoft 365 服務雲端網路的完整連線能力，以及德國內的客戶資料派駐服務。

## <a name="how-to-migrate-to-the-new-german-regions"></a>如何遷移至新的德國地區

現有的 Microsoft Cloud Deutschland 客戶現在可以開始遷移其 Office 365、Dynamics 365 客戶服務，以及電源平臺客戶。 第一個步驟是 [選擇加入由 Microsoft 主導的移轉](https://aka.ms/office365germanymoveoptin)，以加入到我們新的德國資料中心區域。

對於選用於 Microsoft 導向方法的組織，遷移預計會在2021年10月的時間開始，且會在2021年10月29日之前完成。 移轉之後，核心客戶資料和訂閱都會移至新的德國區域。

本文提供在遷移期間和遷移後，針對使用者與系統管理員的體驗，以及遷移後，針對使用者所需的動作，以及針對您使用哪些工作負載的客戶，對客戶可能需要的動作，提供 Microsoft 導向的方式。

下列服務將以 Microsoft 主導的方法移轉：

- Azure Active Directory (Azure AD) 
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- 商務用 OneDrive

- 商務用 Skype Online\*\*
- Office 365 群組
- Dynamics 365/電源平臺\*\*\*

\*\*在從 Microsoft Cloud Deutschland 遷移至德國資料中心地區時，現有商務用 Skype Online 客戶將會轉換至 Microsoft 團隊。 如需詳細資訊，請參閱[開始進行您的 Microsoft Teams 升級](https://aka.ms/SkypeToTeams-Home)。

\*\*\*這些服務的必要條件和遷移影響會在 [Dynamics 365 客戶參與](https://aka.ms/d365ceoptin) 文章中說明。

Office 365 影片即將于年 2021年 3月 1日停用。 如果您選擇將 Office 365 租用者移至新的德國資料中心區域，在 SharePoint Online 遷移完成之後，將不會支援 Office 365 影片。 若要深入瞭解，請按一下 [這裡](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) 。

## <a name="how-is-the-migration-organized"></a>遷移如何進行組織？

此圖代表在遷移至新的德國資料中心時，Office 365 和 Dynamics 365 的各種元件。

![遷移至新的德國資料中心時，Office 365 和 Dynamics 365 的元件](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

遷移是以您 [選擇要進行遷移](https://aka.ms/office365germanymoveoptin)時所有開始的階段執行。 大多數的遷移階段都是以執行後端服務作業的方式執行，並在另一個階段之後執行。 在遷移過程中，會透過 Microsoft 365 系統管理中心的郵件中心來傳送其他用戶端的任務和整體遷移狀態的開始。 工作的範例可能包括客戶管理的 DNS 更新、重新設定 Exchange 混合式客戶的混合式設定或 Azure 遷移。

進行選擇時，不會立即開始遷移。 您的組織會新增至預定日後遷移的承租人清單。 您現在可以開始「準備工作」階段，因為這些都是重要的，可確保順利進行遷移，並在完成時使用。

在承租人遷移開始之前的一周，您會在訊息中心服務中收到通知，最後是所有必要條件都必須完成的最後警告。

遷移會將您的 Azure AD 租使用者從以及主權德國 Azure AD 服務移至歐盟地區之 Azure AD 的 Office 365 服務實例。

下一個階段是從德國特定產品遷移租使用者&#39;s 訂閱和使用者授權。

完成所有步驟（包括客戶 Azure 遷移）之後，您的租使用者便會在 Office 365 服務服務中完成，而且會將遷移標記為完成。 到目前為止，我們為您提供郵件中心的最後一次更新。 租使用者現在並非完全通用的 Office 365 組織。

您會收到訊息中心文章的遷移進度通知。 文章會在特定的里程碑進行，並提供指導方針的指導方針，並提供重要資訊，讓客戶根據程式的需求採取行動。 訊息中心通知是在下列里程碑提供：

- 開始遷移 (于 Azure AD 遷移開始前的5個工作天) 
- Azure AD 遷移完成
- 訂閱和授權遷移完成
- SharePoint 遷移完成
- Exchange 遷移完成
- 商務用 Skype 完成
- Dynamics 完成
- Power BI 完成
- 服務的最後一次轉換已完成

## <a name="moving-to-the-new-german-regions"></a>移至新的德國區域

現有的 Microsoft Cloud 德國 (Microsoft Cloud Deutschland) 客戶現在可以開始遷移其 Office 365、Dynamics 365 客戶服務，以及電源平臺客戶。 第一個步驟是 [選擇加入由 Microsoft 主導的移轉](https://aka.ms/office365germanymoveoptin)，以加入到我們新的德國資料中心區域。 當您更新訂閱時，會自動加入宣告 Microsoft 輔助遷移。 當發生這種情況時，microsoft 會向客戶租使用者管理員傳送電子郵件，並在 Microsoft 365 系統管理中心的訊息中心通知客戶。 不過，如果您想要立即開始處理常式，您可以在目前的 Microsoft 365 系統管理中心中 [選擇直接加入](https://aka.ms/office365germanymoveoptin) 。 遷移預計會在2021年10月開始，並于2021年10月29日完成。 

移轉之後，核心客戶資料和訂閱都會移至新的德國區域。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>如何準備移轉至新的德國資料中心區域中的 Office 365 服務

第一個步驟是通知 Microsoft，讓我們有權將訂閱和資料從 Microsoft Cloud Deutschland 遷移至新的德國資料中心區域中的 Office 365 服務。 如需指示，請參閱 [自願加入程式](https://aka.ms/office365germanymoveoptin) ，並注意下列事項：

- 所有已遷移客戶都需要驗證 Office 365 服務 [Office URLs 365](urls-and-ip-address-ranges.md)的連線能力，以及包含新的德國資料中心區域的 IP 位址。 Inaction 可能會導致服務和用戶端失敗。
- 您應查看 Office 365 平臺服務說明，以瞭解遷移至德文地區後，您的組織將可使用哪些功能和服務。
- 不會遷移試用訂閱，而且會封鎖所有付費訂閱的遷移。 在遷移開始之前，您必須取消任何實驗或轉換為付費訂閱。

## <a name="where-do-i-go-from-here"></a>從這裡移至何處？

請參閱下列常見問題解答一節。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="is-migration-required"></a>需要移轉嗎？

Microsoft 會提供 Office 365 租使用者從 Microsoft Cloud Deutschland 至 Office 365 服務，以供新的德國資料中心區域遷移，不需要額外收費。 雖然我們強烈建議您選擇要遷移至新的德國資料中心區域，我們仍會繼續提供必要的安全性更新給 Microsoft Cloud Deutschland region。

新德文 datacenter 區域中的 Office 365 服務：

- 為 [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)，以及 [Power BI](https://powerbi.microsoft.com/pricing/) 提供具有市場競爭力的價格。
- 會連線至 Microsoft&#39;s 通用網路，提供數百個網路 edge 網站、對等位置及出局點，以在世界各地提供強健的使用者體驗。
- 協助您在德國符合本地客戶資料的存留需求。
- 以最新的服務和新功能版本（包括 Office 365 中的 Microsoft 團隊和多地理位置）提供完整的全域雲端產品。 依地區比較 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md) 和 [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) 產品。
- 提供完整的功能、企業級的安全性及全面的功能，協助客戶符合合規性和法規需求。
- 可透過現有的線上服務合約取得。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>不同的 Office 365 雲端服務選項之間的服務可用性為何？

下列15項服務可在 Microsoft Cloud Deutschland Cloud service 產品中取得。 我們不會將新服務新增至 Microsoft Cloud Deutschland。

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. 群組 (新式群組)
4. Delve 設定檔
5. Exchange Online Protection
6. 適用於 Office 365 的 Defender
7. 進階電子文件探索
8. 進階資料控管
9. SharePoint Online
10. Customer Lockbox (SharePoint Online)
11. 商務用 OneDrive
12. 商務用 Skype Online
13. Word Online、Excel Online、PowerPoint、OneNote、Visio Online
14. Office 365 專業增強版
15. Outlook Mobile

目前新德國資料中心區域提供 29 個服務做為 Office 365 服務的一部分。 將持續與全球 Office 365 服務一起提供新功能和服務。

1. Exchange Online
2. Exchange Online 的客戶加密箱
3. Microsoft 365 群組
4. Delve 設定檔
5. MyAnalytics
6. 工作場所分析
7. Exchange Online Protection
8. 適用於 Office 365 的 Defender
9. 進階電子文件探索
10. 進階安全性管理
11. 資訊版權管理
12. 進階資料控管
13. SharePoint Online
14. 線上 SharePoint 的客戶加密箱
15. 商務用 OneDrive
16. Microsoft Stream
17. 商務用 Skype (會在遷移期間遷移至 Microsoft 團隊) 
18. Cloud PBX
19. PSTN 會議
20. PSTN 電話
21. Microsoft Teams
22. 系統管理報告/使用狀況報告
23. Word Online、Excel Online、PowerPoint、OneNote 和 Visio Online
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook Mobile
28. Enterprise 可移動性 + Security (EMS) E3 (Azure AD Premium P1、Intune 及 Rights Management Service) 
29. Yammer Online

### <a name="when-will-migration-happen"></a>何時會進行移轉？

**Azure**

如果您是僅限 Azure 客戶，您可以開始將您的 Azure 資源 [遷移](https://docs.microsoft.com/azure/germany/germany-migration-main) 至其他地區。 如果您有 Azure 搭配 Office 365、Dynamics 365 或 Power BI，請依照下列步驟進行。

**Office 365**

立即[選擇加入](https://aka.ms/office365germanymoveoptin) Microsoft 主導的移轉。 當我們準備好開始您的遷移時，我們會通知您透過 Microsoft 365 系統管理中心的郵件中心。

**Dynamics 365 和 Power BI**

加入宣告為 [Dynamics 365 客戶服務](https://aka.ms/D365ceOptIn) 和 [Power BI](https://aka.ms/PBIOptIn) 的 Microsoft 導向遷移。 當我們準備好開始您的移轉時，我們會透過 Microsoft 365 系統管理中心的訊息中心來通知您。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>我使用的 Office 365 服務價格是否會變更？

是。 Microsoft&#39;s 全域雲端區域中的定價 (包括新的資料中心區域) 通常較低。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>在訂閱遷移期間，將對我的組織和使用者套用哪些 SKUs 和授權？

在從 Microsoft Cloud Deutschland 遷移至 Office 365 服務時，德國服務特有的 SKUs 會取代為相同或類似 SKU 的全域版本。 在大多數情況下，Office 365 服務中的 SKU 是相同的，但在某些情況下，德國的 SKU 已不再提供于 Office 365 服務中。 如果您想要在遷移完成後，更新指派給貴組織的 SKU，請與您的賣方聯繫，以新增或修改所指派的服務。

| Microsoft Cloud Deutschland-產品 SKU (DE)  | Microsoft Cloud Global 產品 SKU (WW)  |
| --- | --- |
| 客戶加密箱 \_ de (密碼箱 \_ de)  | 客戶加密箱 (密碼箱)  |
| Dynamics 365 Enterprise Edition-額外的資料庫儲存 \_ de (CRMSTORAGE \_ de)  | Dynamics 365 Enterprise Edition-其他資料庫儲存區 (CRMSTORAGE)  |
| Dynamics 365 Enterprise Edition-其他非實際執行的實例 \_ de (CRMTESTINSTANCE \_ de)  | Dynamics 365 Enterprise Edition-其他非生產實例 (CRMTESTINSTANCE)  |
| Dynamics 365 用於客戶服務 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ 客戶 \_ 服務 \_ de)  | 客戶服務 Enterprise Edition 的 Dynamics 365 (DYN365 \_ Enterprise \_ 客戶 \_ 服務)  |
| Dynamics 365 for Sales Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Sales \_ DE)  | Sales Enterprise Edition 的 Dynamics 365 (DYN365 \_ Enterprise \_ Sales)  |
| 適用于小組成員的 Dynamics 365 Enterprise Edition \_ de (DYN365 \_ 企業 \_ 小組 \_ 成員 \_ DE)  | 適用于小組成員的 Dynamics 365 Enterprise Edition (DYN365 \_ 企業 \_ 小組 \_ 成員)  |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ Enterprise \_ PLAN1 \_ de)  | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1)  |
| ECAL Services (EOA、EOP、DLP) \_ de (ECAL \_ service \_ de)  | ECAL Services (EOA、EOP、DLP)  (ECAL \_ 服務)  |
| Enterprise 可移動性 + Security E3 \_ de (EMS \_ de)  | Enterprise 可移動性 + Security E3 (EMS)  |
| Exchange Online (方案 1) \_ de (EXCHANGESTANDARD \_ de)  | Exchange Online (Plan 1)  (EXCHANGESTANDARD)  |
| Exchange Online (方案 2) \_ de (EXCHANGEENTERPRISE \_ de)  | Exchange Online (Plan 2)  (EXCHANGEENTERPRISE)  |
| Exchange online 的 exchange Online 封存 \_ (EXCHANGEARCHIVE \_ 載入項 \_ de)  | Exchange Online 的 exchange Online 封存 (EXCHANGEARCHIVE \_ 載入)  |
| Exchange Online 封存 for Exchange Server \_ de (EXCHANGEARCHIVE \_ de)  | Exchange Server (EXCHANGEARCHIVE 的 exchange Online 封存)  |
| Exchange Online Essentials \_ de (exchange \_ S \_ 基本版 \_)  | Exchange Online 基本版 (EXCHANGE \_ S \_ 基本版)  |
| Exchange Online 展臺 \_ de (EXCHANGEDESKLESS \_ DE)  | Exchange Online Kiosk (EXCHANGEDESKLESS)  |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ de)  | Exchange Online Protection (EOP \_ ENTERPRISE)  |
| Microsoft 365 Business Standard (O365 \_ 商務 \_ 版 PREMIUM)  | Microsoft 365 Business Standard (O365 \_ 商務 \_ 版 PREMIUM)  |
| Microsoft Dynamics CRM Online 實例 \_ de (CRMINSTANCE \_ de)  | Microsoft Dynamics CRM Online 實例 (CRMINSTANCE)  |
| Office 365 A1 供教員 \_ (STANDARDWOFFPACK \_ 教職員 \_ de)  | 適用于教職員工 (STANDARDWOFFPACK 教職員) 的 Office 365 A1 \_ |
| Office 365 A1 學生版 de \_ (STANDARDWOFFPACK \_ 學生版 \_ de)  | Office 365 A1 學生版 (STANDARDWOFFPACK \_ 學生)  |
| Office 365 Advanced 相容性 \_ de (EQUIVIO \_ 分析 \_ de)  | Microsoft 365 E5 規範 (資訊 \_ 保護 \_ 規範)  |
|Microsoft Defender for Office 365 (方案 1) \_ DE (ATP \_ ENTERPRISE \_ DE)  |Microsoft Defender for Office 365 (方案 1)  (ATP \_ ENTERPRISE)  |
| Office 365 商務基本版 \_ de (O365 \_ 商務 \_ 基本型 \_ de)  | Microsoft 365 商務版 (O365 \_ 商務基本版 \_)  |
| Office 365 商務高級版 \_ de (O365 \_ 商務 \_ 優質 \_ de)  | Microsoft 365 Business Standard (O365 \_ 商務 \_ 版 PREMIUM)  |
| Office 365 商務版 \_ de (O365 \_ 商務版 \_ de)  | Microsoft 365 應用程式商務用 (O365 \_ 商務)  |
| Office 365 E1 \_ de (STANDARDPACK \_ DE)  | Office 365 E1 (STANDARDPACK)  |
| 不含 ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS de 的 Office 365 E3 \_)  | 不 ProPlus (ENTERPRISEPACKWITHOUTPROPLUS 的 Office 365 E3)  |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ DE)  | Office 365 E3 (ENTERPRISEPACK)  |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de)  | Office 365 Enterprise E1 (STANDARDPACK)  |
| Office 365 企業版 E3 \_ de (ENTERPRISEPACK \_ de)  | Office 365 企業版 E3 (ENTERPRISEPACK)  |
| Office 365 額外檔案儲存 \_ de (SHAREPOINTSTORAGE \_ de)  | Office 365 額外檔案儲存 (SHAREPOINTSTORAGE)  |
| Office 365 F1 \_ de (DESKLESSPACK \_ DE)  | Office 365 F1 (DESKLESSPACK)  |
| Office 365 ProPlus 的教職員 \_ (OFFICESUBSCRIPTION \_ 教職員 \_ de)  | Office 365 ProPlus，教職員 (OFFICESUBSCRIPTION \_ 教職員)  |
| Office 365 ProPlus 學生 de \_ (OFFICESUBSCRIPTION \_ 學生版 \_)  | Office 365 ProPlus 學生 (OFFICESUBSCRIPTION \_ 學生版)  |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de)  | Office 365 ProPlus (OFFICESUBSCRIPTION)  |
| OneDrive 商務 (方案 1) \_ de (WACONEDRIVESTANDARD \_ de)  | OneDrive 商務 (方案 1)  (WACONEDRIVESTANDARD)  |
| OneDrive 商務 (計畫 2) \_ de (WACONEDRIVEENTERPRISE \_ de)  | OneDrive 商務 (方案 2)  (WACONEDRIVEENTERPRISE)  |
| Power bi Pro 教職員 \_ de (power \_ bi \_ pro \_ 教職員 \_)  | Power bi Pro 教職員 (POWER \_ bi \_ pro \_ 教職員)  |
| Power bi pro \_ de (power \_ bi \_ pro \_ de)  | Power bi Pro (POWER \_ bi \_ pro)  |
| Project Online Essentials \_ de (PROJECTESSENTIALS \_ DE)  | Project Online 基本版 (PROJECTESSENTIALS)  |
| Project Online 高級 \_ DE (PROJECTPREMIUM \_ DE)  | Project Online Premium (PROJECTPREMIUM)  |
| Project Online 專業版 \_ de (PROJECTPROFESSIONAL \_ DE)  | Project Online Professional (PROJECTPROFESSIONAL)  |
| 專案計劃 3 \_ de (PROJECTPROFESSIONAL \_ de)  | 專案計劃 3 (PROJECTPROFESSIONAL)  |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de)  | Office 365 E3 (ENTERPRISEPACK)  |
| SharePoint 線上 (計畫 1) \_ de (SHAREPOINTSTANDARD \_ de)  | SharePoint 線上 (Plan 1)  (SHAREPOINTSTANDARD)  |
| SharePoint 線上 (計畫 2) \_ de (SHAREPOINTENTERPRISE \_ de)  | SharePoint 線上 (Plan 2)  (SHAREPOINTENTERPRISE)  |
| 商務用 Skype Online (方案 1) \_ de (MCOIMP \_ de)  | Office 365 E1 (STANDARDPACK)  |
| 商務用 Skype Online (方案 1) \_ de (MCOIMP \_ de)  | 商務用 Skype Online (Plan 1)  (MCOIMP)  |
| 商務用 Skype Online (方案 2) \_ de (MCOSTANDARD \_ de)  | 商務用 Skype Online (Plan 2)  (MCOSTANDARD)  |
| 商務用 Skype Plus CAL \_ de (MCOPLUSCAL \_ de)  | 商務用 Skype Plus CAL (MCOPLUSCAL)  |
| Visio Online Plan 1，教職員 \_ de (VISIOONLINE \_ PLAN1 \_ FAC \_ DE)  | Visio Online Plan 1，教職員 (VISIOONLINE \_ PLAN1 \_ FAC)  |
| Visio Online 方案 1 \_ de (VISIOONLINE \_ PLAN1 \_ de)  | Visio Online Plan 1 (VISIOONLINE \_ PLAN1)  |
| Visio Online Plan 2 教職員 \_ de (VISIOCLIENT \_ 教職員 \_ de)  | Visio Online Plan 2 教職員 (VISIOCLIENT \_ 教職員)  |
| Visio Online 方案 2 \_ de (VISIOCLIENT \_ de)  | Visio Online Plan 2 (VISIOCLIENT)  |
| Visio Plan 1 \_ de (VISIOONLINE \_ PLAN1 \_ de)  | Visio 方案 1 (VISIOONLINE \_ PLAN1)  |
| Visio 方案 2 \_ de (VISIOCLIENT \_ de)  | Visio 方案 2 (VISIOCLIENT)  |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>如何取得 Microsoft 的協助來移轉到新的區域或解答支援問題？

如有任何問題，您可以聯繫我們或您的合作夥伴：

- 針對 Azure，您可以在 Azure 入口網站中提交[新的支援要求](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)。
- 針對 Office 365，您可以使用 &quot; &quot; [Microsoft 365 系統管理中心](https://portal.office.de/)的 [需要協助] 連結提交問題。
- 如果您是 Dynamics 365 客戶接洽和 Power BI 客戶，也有 Office 365，您可以使用 &quot; &quot; [Microsoft 365 系統管理中心](https://portal.office.de/)的 [需要協助] 連結提交問題。 Dynamics 365 Customer Engagement 支援選項在[這裡](https://docs.microsoft.com/dynamics365/get-started/support/)。 Power BI 支援選項在[這裡](https://powerbi.microsoft.com/support/)。

## <a name="more-information"></a>詳細資訊

其他有關遷移至新的德國資料中心區域的資訊都是即將推出。 將此頁面做成書簽，使您可以存回並保留最新。

- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](https://aka.ms/office365germanymoveoptin)
- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [Office 365 URL 與 IP 位址範圍](https://aka.ms/o365endpoints)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
