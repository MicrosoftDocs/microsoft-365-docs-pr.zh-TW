---
title: 從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
ms.openlocfilehash: 4162e51164120cecaa431ad6883d3ee112ad4880
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796003"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務

> [!NOTE]
> 本文僅適用于合格的 Microsoft Cloud Deutschland customers。

在2018年8月份中，Microsoft 宣佈我們打算從德國的新雲端地區提供完整的 Microsoft 雲端（Azure、Office 365、Dynamics 365 和電源平臺），以更好地啟用我們客戶的數位轉換。 2019 年 8 月，我們宣佈我們正在開放德國的新雲端區域。 自宣佈，我們已宣告 Azure、Office 365、Dynamics 365 和電源平臺的可用性。

新的地區設計目的是為了處理更靈活的德國客戶需求、最新的智慧雲端服務，以及與我們的 Microsoft 365 服務雲端網路的完整連線能力，以及德國內的客戶資料派駐服務。

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>如何遷移至新的德國資料中心區域

現有的 Microsoft Cloud Deutschland 客戶現在可以開始遷移其 Office 365、Dynamics 365 客戶服務，以及電源平臺客戶。 第一個步驟是 [選擇加入由 Microsoft 主導的移轉](./ms-cloud-germany-migration-opt-in.md)，以加入到我們新的德國資料中心區域。

對於選用於 Microsoft 導向方法的組織，遷移預計會在2021年10月的時間開始，且會在2021年10月29日之前完成。 移轉之後，核心客戶資料和訂閱都會移至新的德國區域。

本文提供在遷移期間和遷移後，針對使用者與系統管理員的體驗，以及遷移後，針對使用者所需的動作，以及針對您使用哪些工作負載的客戶，對客戶可能需要的動作，提供 Microsoft 導向的方式。

下列服務將以 Microsoft 主導的方法移轉：

- Azure Active Directory (Azure AD) 
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- 商務用 OneDrive
- 商務用 Skype線上\*\*
- Office 365 群組
- Dynamics 365/電源平臺\*\*\*

\*\*在從 Microsoft Cloud Deutschland 遷移至德文 datacenter 地區時，現有的商務用 Skype 線上客戶將會轉換成 Microsoft Teams。 如需詳細資訊，請參閱[開始進行您的 Microsoft Teams 升級](/microsoftteams/upgrade-start-here)。

\*\*\*這些服務的必要條件和遷移影響會在 [Dynamics 365 客戶參與](/dynamics365/get-started/migrate-data-german-region) 文章中說明。

Office 365 影片即將于年 2021年 3月 1日停用。 如果您選擇將 Office 365 租用者移至新的德國資料中心區域，在 SharePoint Online 遷移完成之後，將不會支援 Office 365 影片。 如需詳細資訊，請參閱 [Microsoft Cloud Deutschland timeline](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="how-is-the-migration-organized"></a>遷移如何進行組織？

下圖顯示遷移至新德文資料中心的十大階段。

:::image type="content" alt-text="遷移至新的德國資料中心的十大階段" source="../media/ms-cloud-germany-migration-opt-in/migration-organization.png" lightbox="../media/ms-cloud-germany-migration-opt-in/migration-organization.png":::

當您 [選擇要進行遷移](./ms-cloud-germany-migration-opt-in.md)時，這些階段便會開始。 大多數的遷移階段都是以執行後端服務作業的方式執行，並在另一個階段之後執行。 在遷移過程中，會透過 Microsoft 365 系統管理中心的訊息中心來傳送其他用戶端的任務和整體遷移狀態的開始。 工作的範例可能包括客戶管理的 DNS 更新、重新設定 Exchange 混合式客戶的混合式設定或 Azure 遷移。

進行選擇時，不會立即開始遷移。 您的組織會新增至預定日後遷移的承租人清單。 您現在可以開始「預備工作」階段，因為這些是確保順利進行遷移和完成時使用的重要專案：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)

在承租人遷移開始之前的一周，您會在訊息中心服務中收到通知，最後是所有必要條件都必須完成的最後警告。

遷移會將您的 azure ad 租使用者從以及主權德國 azure ad 服務移至歐盟地區之 azure ad 的 Office 365 服務實例。

下一個階段是將您的租使用者&#39;s 訂閱和使用者授權從德國特定產品遷移至全球產品。

完成所有步驟（包括客戶 Azure 遷移）之後，您的租使用者便會在 Office 365 services 服務中完成，並且將遷移標記為完成。 到目前為止，我們為您提供郵件中心的最後一次更新。 租使用者現在是完全全域 Office 365 組織。

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

在將 Azure AD 的最後一個轉換為全球服務後，就會將所有的用戶端和應用程式完全轉換為使用正確的端點。 最後一次轉換後，會有30天的時段，繼續從 Microsoft Cloud Deutschland service 取得 Azure AD 權杖的可能性。 當30天的時段到期時，用戶端和應用程式將不再能夠存取 Microsoft Cloud Deutschland 的 Azure AD 端點。 應用程式或使用者存取將無法從此點失敗。 您必須確定在此時間視窗關閉之前，所有使用者和應用程式都已遷移到正確的端點。 

## <a name="moving-to-the-new-german-datacenter-regions"></a>移至新的德國資料中心區域

現有的 Microsoft Cloud Deutschland 客戶現在可以開始遷移其 Office 365、Dynamics 365 客戶服務和電源平臺服務。 第一個步驟是 [選擇加入由 Microsoft 主導的移轉](./ms-cloud-germany-migration-opt-in.md)，以加入到我們新的德國資料中心區域。 當您更新訂閱時，會自動加入宣告 Microsoft 輔助遷移。 當發生這種情況時，Microsoft 會在 Microsoft 365 系統管理中心的訊息中心通知客戶租使用者管理員電子郵件。 不過，如果您想要立即開始處理常式，您可以在當今的 Microsoft 365 系統管理中心內直接[加入宣告](./ms-cloud-germany-migration-opt-in.md)。 遷移預計會在2021年10月開始，並于2021年10月29日完成。 

由於遷移，核心客戶資料和訂閱會移至新的德國資料中心區域。

> [!NOTE]
> 本文包含僅限遷移 Office 365 服務的指引。 如果您是在 Microsoft Cloud Deutschland 中執行其他 Azure 工作負載，請參閱 [Azure 德國的遷移指南](/azure/germany/germany-migration-main)。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>如何準備移轉至新的德國資料中心區域中的 Office 365 服務

第一個步驟是通知 Microsoft，讓我們有權將訂閱和資料從 Microsoft Cloud Deutschland 遷移至新的德國資料中心區域的 Office 365 服務。 如需指示，請參閱 [自願加入程式](./ms-cloud-germany-migration-opt-in.md) ，並注意下列事項：

- 所有的已遷移客戶都必須驗證 Office 365 服務的連線[Office 365 URLs 和 IP 位址](urls-and-ip-address-ranges.md)（包括新的德國資料中心區域）。 Inaction 可能會導致服務和用戶端失敗。
- 請複查 [準備工作](ms-cloud-germany-transition-add-pre-work.md) 的活動清單，以確保您的組織已獲悉並準備好進行變更。
- 您應查看 Office 365 平臺服務說明，以瞭解遷移至德文地區後，您的組織將會提供哪些功能和服務。
- 不會遷移試用訂閱，而且會封鎖所有付費訂閱的遷移。 在遷移開始之前，您必須取消任何實驗或轉換為付費訂閱。

## <a name="where-do-i-go-from-here"></a>從這裡移至何處？

請參閱下列常見問題解答一節。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="is-migration-required"></a>需要移轉嗎？

microsoft 提供從 Microsoft Cloud Deutschland 到 Office 365 服務的 Office 365 租使用者遷移至新的德國資料中心區域，不需要額外收費。 雖然我們強烈建議您選擇要遷移至新的德國資料中心區域，我們仍會繼續提供必要的安全性更新給 Microsoft Cloud Deutschland region。

在新的德國資料中心區域中 Office 365 服務：

- 為 [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)，以及 [Power BI](https://powerbi.microsoft.com/pricing/) 提供具有市場競爭力的價格。
- 會連線至 Microsoft&#39;s 通用網路，提供數百個網路 edge 網站、對等位置及出局點，以在世界各地提供強健的使用者體驗。
- 協助您在德國符合本地客戶資料的存留需求。
- 以最新的服務和新功能版本（包括 Office 365 中的 Microsoft Teams 和多地理位置）來提供全功能的全域雲端產品。 依地區比較 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md) 和 [Dynamics 365](/dynamics365/get-started/availability) 產品。
- 提供完整的功能、企業級的安全性及全面的功能，協助客戶符合合規性和法規需求。
- 可透過現有的線上服務合約取得。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>不同的 Office 365 雲端服務選項之間的服務可用性為何？
<h2 id="serv-avail"></h2>

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

在新的德國資料中心區域中，目前有39服務可作為 Office 365 服務的一部分。 將持續與全球 Office 365 服務一起提供新功能和服務。

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
11. Office 365 的資訊保護 
12. 進階資料控管
13. SharePoint Online
14. 線上 SharePoint 的客戶加密箱
15. 商務用 OneDrive
16. Microsoft Stream
17. 商務用 Skype (會在遷移期間遷移至 Microsoft Teams) 
18. Cloud PBX
19. PSTN 會議
20. PSTN 電話
21. Microsoft Teams
22. 系統管理報告/使用狀況報告
23. Office 網頁版
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD 進階版 P1、Intune 及 Rights Management Service) 
29. Yammer Enterprise
30. Microsoft Forms
31. Office 365 的 Power Automate
32. Office 365 的 Power Virtual Agents
33. Office 365 的 PowerApps
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. 清單

### <a name="when-will-migration-happen"></a>何時會進行移轉？

**Azure**

如果您是僅限 Azure 客戶，您可以開始將您的 Azure 資源 [遷移](/azure/germany/germany-migration-main) 至其他地區。 

如果您有 Azure 使用 Office 365、Dynamics 365 或 Power BI，必須先遵循 Office 365 服務的遷移程式，以確保成功遷移 azure AD，您才能開始自行定向 azure 遷移。 您必須先完成 Azure 遷移，再完成租使用者遷移，以維護您的 azure AD 和 Office 365 組織的 azure 工作負載。 如需更多詳細資料，請參閱[遷移階段的遷移動作和遷移影響。 Deutschland](ms-cloud-germany-transition-phases.md)

**Office 365**

立即[選擇加入](./ms-cloud-germany-migration-opt-in.md) Microsoft 主導的移轉。 當我們準備好開始您的遷移時，我們會通知您透過 Microsoft 365 系統管理中心的郵件中心。

**Dynamics 365 和 Power BI**

加入宣告 Microsoft 導向的[Dynamics for Dynamics 365 客戶接洽](/dynamics365/get-started/migrate-data-german-region)和[Power BI](/power-bi/admin/service-admin-migrate-data-germany)目前的遷移。 當我們準備好開始您的移轉時，我們會透過 Microsoft 365 系統管理中心的訊息中心來通知您。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>是否要使用 Office 365 服務的價格變更？

是。 Microsoft&#39;s 全域雲端區域中的定價 (包括新的資料中心區域) 通常較低。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>在訂閱遷移期間，將對我的組織和使用者套用哪些 SKUs 和授權？

從 Microsoft Cloud Deutschland 遷移至 Office 365 服務時，德國服務特有 SKUs 會取代為相同或類似的 SKU 通用版本。 在大部分的情況下，Office 365 服務中的 sku 是相同的，但在某些情況下，德國的 sku 已不再提供 Office 365 服務中的更換專案。 如果您想要在遷移完成後，更新指派給貴組織的 SKU，請與您的賣方聯繫，以新增或修改所指派的服務。

| Microsoft Cloud Deutschland-產品 SKU (DE)  | Microsoft Cloud Global 產品 SKU (WW)  |
| --- | --- |
| 客戶加密箱 \_ de (密碼箱 \_ de)  | 客戶加密箱 (密碼箱)  |
| Dynamics 365 Enterprise Edition 其他資料庫儲存體 \_ de (CRMSTORAGE \_ de)  | Dynamics 365 Enterprise Edition 其他資料庫儲存體 (CRMSTORAGE)  |
| Dynamics 365 Enterprise Edition 額外的非生產實例 \_ de (CRMTESTINSTANCE \_ de)  | Dynamics 365 Enterprise Edition 其他非生產實例 (CRMTESTINSTANCE)  |
| 用於客戶服務的 Dynamics 365 Enterprise Edition \_ DE (DYN365 \_ 企業 \_ 客戶 \_ 服務 \_ de)  | 客戶服務 Enterprise Edition 的 Dynamics 365 (DYN365 \_ Enterprise \_ 客戶 \_ 服務)  |
| 用於銷售 Enterprise Edition \_ DE (DYN365 \_ Enterprise \_ Sales \_ de) 的 Dynamics 365 | Sales Enterprise Edition 的 Dynamics 365 (DYN365 \_ Enterprise \_ Sales)  |
| 適用于小組成員的 Dynamics 365 Enterprise Edition \_ de (DYN365 \_ 企業 \_ 小組 \_ 成員 \_ de)  | 適用于小組成員的 Dynamics 365 Enterprise Edition (DYN365 \_ 企業 \_ 小組 \_ 成員)  |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ Enterprise \_ PLAN1 \_ DE)  | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1)  |
| ECAL 服務 (EOA、EOP、DLP) \_ (ECAL \_ 服務 \_ de)  | ECAL 服務 (EOA、EOP、DLP)  (ECAL \_ 服務)  |
| 企業行動力 + 安全性 E3 \_DE (EMS \_)  | 企業行動力 + 安全性 E3 (EMS)  |
| Exchange Online (方案 1) \_DE (EXCHANGESTANDARD \_ de)  | Exchange Online (方案 1)  (EXCHANGESTANDARD)  |
| Exchange Online (方案 2) \_DE (EXCHANGEENTERPRISE \_ de)  | Exchange Online (方案 2)  (EXCHANGEENTERPRISE)  |
| 適用於 Exchange Online 的 Exchange Online 封存 \_DE (EXCHANGEARCHIVE \_ 載入項 \_)  | 適用於 Exchange Online 的 Exchange Online 封存 (EXCHANGEARCHIVE \_ 載入項)  |
| 適用於 Exchange Server 的 Exchange Online 封存 \_DE (EXCHANGEARCHIVE \_ de)  | 適用於 Exchange Server 的 Exchange Online 封存 (EXCHANGEARCHIVE)  |
| Exchange Online 基本版 \_ (EXCHANGE \_ S \_ 基本版 \_ de)  | Exchange Online 基本版 (Exchange \_ S \_ 基本版)  |
| Exchange Online Kiosk \_DE (EXCHANGEDESKLESS \_ de)  | Exchange Online Kiosk (EXCHANGEDESKLESS)  |
| Exchange Online Protection \_DE (EOP \_ ENTERPRISE \_ de)  | Exchange Online Protection (EOP \_ 企業版)  |
| Microsoft 365 商務標準版 (O365 \_ 商務 \_ 版 PREMIUM)  | Microsoft 365 商務標準版 (O365 \_ 商務 \_ 版 PREMIUM)  |
| Microsoft Dynamics CRM Online實例 \_ de (CRMINSTANCE \_ de)  | Microsoft Dynamics CRM Online實例 (CRMINSTANCE)  |
| Office 365 A1 教職員 \_ (STANDARDWOFFPACK \_ 教職員 \_ de)  | Office 365 A1 教職員 (STANDARDWOFFPACK \_ 教職員)  |
| 學生 \_ (STANDARDWOFFPACK \_ 學生 \_ de) 的 Office 365 A1 | Office 365 A1 學生 (STANDARDWOFFPACK \_ 學生版)  |
| Office 365 進階合規性 \_DE (EQUIVIO \_ ANALYTICS \_ de)  | Microsoft 365 E5 合規性 (資訊 \_ 保護 \_ 合規性)  |
|適用于 Office 365 的 Microsoft Defender (方案 1) \_ DE (ATP \_ ENTERPRISE \_ DE)  |Office 365 的 Microsoft Defender (計畫 1)  (ATP \_ ENTERPRISE)  |
| Office 365 商務基本版 \_DE (O365 \_ 商務 \_ 基本版 \_ de)  | Microsoft 365 商務基本版 (O365 \_ 商務 \_ 基本版)  |
| Office 365 商務進階版 \_DE (O365 \_ 商務 \_ 優質 \_ DE)  | Microsoft 365 商務標準版 (O365 \_ 商務 \_ 版 PREMIUM)  |
| Office 365商務 \_ de (O365 \_ 商務版 \_ de)  | Microsoft 365 Apps 商務版 (O365 \_ 商務)  |
| Office 365\_ (STANDARDPACK \_ de) 上的 E1 de | Office 365E1 (STANDARDPACK)  |
| Office 365E3 無 ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS \_ de)  | Office 365E3 不 ProPlus (ENTERPRISEPACKWITHOUTPROPLUS)  |
| Office 365E3 \_ de (ENTERPRISEPACK \_ de)  | Office 365E3 (ENTERPRISEPACK)  |
| Office 365 企業版\_ (STANDARDPACK \_ de) 上的 E1 de | Office 365 企業版E1 (STANDARDPACK)  |
| Office 365 企業版E3 \_ de (ENTERPRISEPACK \_ de)  | Office 365 企業版E3 (ENTERPRISEPACK)  |
| Office 365其他檔案儲存體 \_ de (SHAREPOINTSTORAGE \_ de)  | Office 365 (SHAREPOINTSTORAGE 的額外檔案儲存體)  |
| Office 365 F1 \_DE (DESKLESSPACK \_ de)  | Office 365 F1 (DESKLESSPACK)  |
| Office 365 專業增強版教職員 \_ (OFFICESUBSCRIPTION \_ 教職員 \_ de)  | Office 365 專業增強版教職員 (OFFICESUBSCRIPTION \_ 教職員)  |
| 學生 \_ (OFFICESUBSCRIPTION \_ 學生 \_ de) 的 Office 365 專業增強版 | Office 365 專業增強版學生 (OFFICESUBSCRIPTION \_ 學生版)  |
| Office 365 專業增強版 \_DE (OFFICESUBSCRIPTION \_ de)  | Office 365 專業增強版 (OFFICESUBSCRIPTION)  |
| 商務用 OneDrive (方案 1) \_DE (WACONEDRIVESTANDARD \_ de)  | 商務用 OneDrive (方案 1)  (WACONEDRIVESTANDARD)  |
| 商務用 OneDrive (方案 2) \_DE (WACONEDRIVEENTERPRISE \_ de)  | 商務用 OneDrive (方案 2)  (WACONEDRIVEENTERPRISE)  |
| Power BI Pro 的教職員 \_ (Power \_ BI \_ Pro \_ 教職員 \_ de)  | Power BI Pro 教職員 (Power \_ BI \_ Pro \_ 教職員)  |
| Power BI Pro \_DE (POWER \_ BI \_ PRO \_ DE)  | Power BI Pro (Power \_ BI \_ Pro)  |
| Project Online 基本版 \_DE (PROJECTESSENTIALS \_ de)  | Project Online 基本版 (PROJECTESSENTIALS)  |
| Project Online 進階版 \_DE (PROJECTPREMIUM \_ de)  | Project Online 進階版 (PROJECTPREMIUM)  |
| Project Online 專業版 \_DE (PROJECTPROFESSIONAL \_ de)  | Project Online 專業版 (PROJECTPROFESSIONAL)  |
| Project 方案 3 \_DE (PROJECTPROFESSIONAL \_ de)  | Project 方案 3 (PROJECTPROFESSIONAL)  |
| Office 365E4 \_ de (ENTERPRISEWITHSCAL \_ de)  | Office 365E3 (ENTERPRISEPACK)  |
| SharePoint Online (方案 1) \_DE (SHAREPOINTSTANDARD \_ de)  | SharePoint Online (方案 1)  (SHAREPOINTSTANDARD)  |
| SharePoint Online (方案 2) \_DE (SHAREPOINTENTERPRISE \_ de)  | SharePoint Online (方案 2)  (SHAREPOINTENTERPRISE)  |
| 商務用 Skype線上 (方案 1) \_ de (MCOIMP \_ de)  | Office 365E1 (STANDARDPACK)  |
| 商務用 Skype線上 (方案 1) \_ de (MCOIMP \_ de)  | 商務用 Skype線上 (方案 1)  (MCOIMP)  |
| 商務用 Skype線上 (方案 2) \_ de (MCOSTANDARD \_ de)  | 商務用 Skype線上 (Plan 2)  (MCOSTANDARD)  |
| 商務用 Skype此外，CAL \_ de (MCOPLUSCAL \_ de)  | 商務用 SkypePlus CAL (MCOPLUSCAL)  |
| Visio線上方案1，教職員 \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE)  | Visio線上方案1，教職員 (VISIOONLINE \_ PLAN1 \_ FAC)  |
| Visio線上方案 1 \_ de (VISIOONLINE \_ PLAN1 \_ de)  | Visio線上方案 1 (VISIOONLINE \_ PLAN1)  |
| Visio線上方案2，教職員 \_ de (VISIOCLIENT \_ 教職員 \_ de)  | Visio線上方案2，教職員 (VISIOCLIENT \_ 教職員)  |
| Visio線上方案 2 \_ de (VISIOCLIENT \_ de)  | Visio線上方案 2 (VISIOCLIENT)  |
| Visio 方案 1 \_DE (VISIOONLINE \_ PLAN1 \_ de)  | Visio 方案 1 (VISIOONLINE \_ PLAN1)  |
| Visio 方案 2 \_DE (VISIOCLIENT \_ de)  | Visio 方案 2 (VISIOCLIENT)  |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>如何取得 Microsoft 的協助來移轉到新的區域或解答支援問題？

如有任何問題，您可以聯繫我們或您的合作夥伴：

- 針對 Azure，您可以在 Azure 入口網站中提交[新的支援要求](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)。
- Office 365，您可以使用 [ &quot; Microsoft 365 系統管理中心] 的 [需要協助] 連結提交問題 &quot; [ ](https://portal.office.de/)。
- 如果您是 Dynamics 365 客戶接洽，並 Power BI 客戶，而且還有 Office 365，您可以使用 [ &quot; Microsoft 365 系統管理中心] 的 [需要協助] 連結提交問題 &quot; [ ](https://portal.office.de/)。 Dynamics 365 Customer Engagement 支援選項在[這裡](/dynamics365/get-started/support/)。 Power BI 支援選項在[這裡](https://powerbi.microsoft.com/support/)。

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>「我的客戶」在全域 Microsoft 雲端中已有 M365 租使用者，除了 Microsoft Cloud Deutschland 租使用者之外。 這兩個承租人是否可以在遷移過程中合併成一個專案？

否，沒有租使用者合併功能。 每個租使用者都有自己的命名空間和唯一識別碼時，承租人會保持分開和唯一的。 如有需要，microsoft 會將 Microsoft Cloud Deutschland 租使用者遷移至全域雲端，否則客戶可以取消並放棄它。


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>做為遷移的一部分，大多數的使用者必須執行哪些動作？
遷移的目的是為了對使用者/客戶的影響降至最低。
- 確定 Office 的應用程式執行最新的可用版本。 
- 在遷移過程中，使用商務用 Skype 的客戶將會轉換成 Teams，而且可能需要在裝置上[下載並安裝 Teams](/deployoffice/teams-install) 。
- 使用者可能需要登出 Office 的應用程式，並在遷移完成後再登入。 
- 執行 OneDrive 同步處理用戶端的客戶必須登出其工作站，然後再次登入，以允許 OneDrive 同步用戶端登入全域 Azure Active Directory 服務。
- 在遷移完成後，請注意新的全域 URLs Outlook Web Access (範例：使用 outlook.office365.com) 。 SharePoint線上用戶端將繼續使用現有的 URL 連線至 MCD 命名空間 (範例： contoso.sharepoint.de) 。


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>哪些客戶受到 Azure Active Directory 遷移的影響？ 

Office 365 的所有客戶都取決於 Azure Active Directory，用以驗證及儲存 Microsoft 託管服務運作所需的重要服務元件。 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Azure Active Directory 遷移有何影響？

在早期階段中 Azure Active Directory 的初次遷移，對客戶體驗沒有任何影響。 在最後一個遷移階段，客戶租使用者的所有服務都完全位於全域服務。 在此最後階段之後，Microsoft Cloud Deutschland 中的 Azure Active Directory 服務可能不再接受授權要求，或提供存取權杖給 Office 服務。


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Office 365 服務的網路連線[URLs 及 IP 位址](./urls-and-ip-address-ranges.md)有何意義？

本文說明合理服務運作所需的必要 URLs 和 IP 位址，以確保良好的客戶體驗。 在相對少見的情況下，有些客戶會嘗試設定網路周邊安全性，以將流量限制在 Microsoft 雲端 Deutschland 服務 IP 範圍的一部分內，以最小化流量流量，而且只能存取服務。


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>如何管理 Exchange Online 的 DNS 變更，使郵件能夠繼續流動？

Microsoft 受管理的 IP 範圍和 DNS 區域會在遷移期間和全域服務遷移時進行轉換。 

客戶管理的 DNS 區域（如自訂網域 MX 記錄）是客戶的責任，不過，為了簡化此遷移，客戶管理的 MX 記錄會指向 office.de 區域中的 Office 365 服務端點，而且 Microsoft 會自動管理此服務端點的遷移。


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>如何管理商務用 Skype 的 DNS 變更？ 
 
所有商務客戶的 Skype 都會轉換成 Microsoft Teams。 遷移至 Teams 不需要客戶 Skype DNS 區域的轉換。 在遷移後，客戶將可以立即登入 Teams 所有功能。
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>在遷移後，是否會 Outlook iOS 和 Android 工作？ 

是。 Microsoft 的建議是，所有客戶都執行最新版本的 Office 用戶端，包括 iOS 和 Android 用戶端的 Outlook。 在完成 Office 365 泛型服務的遷移時，所有 Office 用戶端都必須登出並登入，以從全域服務取得新的 Azure Active Directory 存取權杖。 



## <a name="next-step"></a>下一步

[選擇加入移轉](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>其他資訊

開始：

- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移轉程式資訊](/power-bi/admin/service-admin-migrate-data-germany)
- [開始升級您的 Microsoft Teams](/microsoftteams/upgrade-start-here)
