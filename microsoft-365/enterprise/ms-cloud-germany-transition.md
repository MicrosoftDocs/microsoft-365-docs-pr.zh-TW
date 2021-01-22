---
title: 從 Microsoft Cloud Deutschland 移向新的德國資料中心區域的 Office 365 服務
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
ms.openlocfilehash: 28344f1249e4f51bb9802bf19ca7561182610a7c
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921586"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>從 Microsoft Cloud Deutschland 移向新的德國資料中心區域的 Office 365 服務

> [!NOTE]
> 本文僅適用于合格的 Microsoft Cloud Deutschland 客戶。

Microsoft 在 2018 年 8 月宣佈，我們計畫從德國的新雲端地區提供完整的 Microsoft 雲端 -Azure、Office 365、Dynamics 365 和 Power Platform，以更完善地為我們的客戶進行數位轉換。 2019 年 8 月，我們宣佈我們正在開放德國的新雲端區域。 我們自此宣佈提供 Azure、Office 365、Dynamics 365 和 Power Platform。

新的區域是專為滿足德國客戶不斷演進的需求所設計，這些客戶擁有更大的優勢、最新的智慧型雲端服務，以及 Microsoft 365 服務雲端網路的完全連線性，以及位於德國的客戶資料。

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>如何遷移到新的德國資料中心區域

現有的 Microsoft Cloud Deutschland 客戶現在可以開始遷移他們的 Office 365、Dynamics 365 客戶互動和 Power Platform 客戶。 第一個步驟是 [選擇加入由 Microsoft 主導的移轉](https://aka.ms/office365germanymoveoptin)，以加入到我們新的德國資料中心區域。

對於選擇採用 Microsoft 導向方法的組織，移移預計于 2021 年初開始，並將于 2021 年 10 月 29 日完成。 移轉之後，核心客戶資料和訂閱都會移至新的德國區域。

本文提供 Microsoft 導向移移方法概觀、使用者和系統管理員在移移期間和移移之後的體驗明確，以及客戶根據所使用工作負載可能需採取的動作。

下列服務將以 Microsoft 主導的方法移轉：

- Azure Active Directory (Azure AD) 
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- 商務用 OneDrive

- 商務用 Skype Online\*\*
- Office 365 群組
- Dynamics 365 / Power Platform\*\*\*

\*\*從 Microsoft Cloud Deutschland 移轉至德國資料中心區域期間，現有的商務用 Skype Online 客戶將會移轉至 Microsoft Teams。 如需詳細資訊，請參閱[開始進行您的 Microsoft Teams 升級](https://aka.ms/SkypeToTeams-Home)。

\*\*\*Dynamics [365](https://aka.ms/d365ceoptin) 客戶參與一文將說明這些服務的移移先決條件及影響。

Office 365 影片即將于年 2021年 3月 1日停用。 如果您選擇將 Office 365 租用者移至新的德國資料中心區域，在 SharePoint Online 遷移完成之後，將不會支援 Office 365 影片。 詳細資訊請參閱 Microsoft [Cloud Deutschland 時程表](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="how-is-the-migration-organized"></a>移移會如何組織？

此圖顯示移移至新德國資料中心的九個階段。

![移移至新德國資料中心的九個階段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

這些階段會在您 [加入宣告移移時開始](https://aka.ms/office365germanymoveoptin)。 大部分的移移階段會以後端服務作業方式執行，只需要客戶互動最少，而且會彼此執行一個階段。 額外客戶主導的工作和整體移移狀態的開始，會透過 Microsoft 365 系統管理中心的訊息中心在移移程式期間傳達。 工作範例可能包括客戶管理的 DNS 更新、重新設定 Exchange 混合式客戶的混合式設定，或 Azure 移移。

加入宣告時，移移不會立即開始。 您的組織會新增到排定于稍後移移的租使用者清單中。 您現在可以開始進行工作前階段，這些階段對於確保完成移移和使用成功至關重要：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預先作業](ms-cloud-germany-transition-add-pre-work.md)

在租使用者移入開始的一周之前，您會收到訊息中心服務的通知，指出所有先決條件都必須完成。

此移轉會將 Azure AD 租使用者從主權德國 Azure AD 服務移至歐盟地區的 Azure AD Office 365 服務實例。

下一個階段是將租使用者&#39;的訂閱和使用者授權從德國特定產品移移至全球產品。

完成所有步驟後 ，包括客戶 Azure 移移，您的租使用者即已完成 Office 365 服務服務，且移移會標示為完成。 此時，會提供您訊息中心的最終更新。 租使用者現在是一個完全全域的 Office 365 組織。

您會收到訊息中心文章的移移進度通知。 貼文將出現在特定的里程碑中，並提供步驟進度的指引，以及重要資訊，讓客戶根據程式需求採取行動。 訊息中心的通知在下列里程碑中提供：

- 在 Azure AD (開始 5 個工作天之前開始移) 
- Azure AD 移移完成
- 訂閱和授權移移完成
- SharePoint 移移完成
- Exchange 移移完成
- 商務用 Skype 完成
- 動態完成
- Power BI 完成
- 服務完全完全完成

## <a name="moving-to-the-new-german-datacenter-regions"></a>移動到新的德國資料中心區域

現有的 Microsoft Cloud Deutschland 客戶現在可以開始遷移其 Office 365、Dynamics 365 客戶互動和 Power Platform 服務。 第一個步驟是 [選擇加入由 Microsoft 主導的移轉](https://aka.ms/office365germanymoveoptin)，以加入到我們新的德國資料中心區域。 當您續約訂閱時，會自動加入宣告 Microsoft 協助移移。 發生此情況時，Microsoft 會以電子郵件和 Microsoft 365 系統管理中心的訊息中心通知客戶租使用者管理員。 不過，如果您想要立即開始程式，您現在可以直接在 Microsoft [](https://aka.ms/office365germanymoveoptin) 365 系統管理中心加入宣告。 移移預計于 2021 年初開始，並將于 2021 年 10 月 29 日完成。 

移轉之後，核心客戶資料和訂閱會移至新的德國資料中心區域。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>如何準備移轉至新的德國資料中心區域中的 Office 365 服務

第一個步驟是通知 Microsoft，以便我們將您的訂閱和資料從 Microsoft Cloud Deutschland 遷移到新的德國資料中心地區的 Office 365 服務。 如需指示 [，請參閱加入](https://aka.ms/office365germanymoveoptin) 程式，並請注意：

- 所有移移客戶都需要驗證 Office 365 服務 [Office 365](urls-and-ip-address-ranges.md)URL 和 IP 位址的連線性，包括新的德國資料中心區域。 不回應可能會導致服務與用戶端失敗。
- 請查看工作 [前活動清單](ms-cloud-germany-transition-add-pre-work.md) ，確保貴組織已瞭解變更並做好準備。
- 您應該查看 Office 365 平臺服務描述，以瞭解移移至德國地區之後，貴組織將可享有哪些功能與服務。
- 試用版訂閱將不會移移，而且會封鎖所有付費訂閱的移移。 您必須取消任何試用版或轉換為付費訂閱，才能開始移轉。

## <a name="where-do-i-go-from-here"></a>我要從何處前往？

請查閱下列常見問題區段。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="is-migration-required"></a>需要移轉嗎？

Microsoft 將 Office 365 租使用者從 Microsoft Cloud Deutschland 移向新的德國資料中心地區之 Office 365 服務，無需額外費用。 我們強烈建議您加入宣告以遷移到新的德國資料中心地區，不過我們會繼續為 Microsoft Cloud Deutschland 地區提供必要的安全性更新。

新的德國資料中心區域的 Office 365 服務：

- 為 [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)，以及 [Power BI](https://powerbi.microsoft.com/pricing/) 提供具有市場競爭力的價格。
- 已連接至 Microsoft&#39;全球網路，提供數百個網路邊緣網站、對等位置和出口點，以在全球任何位置提供強大的使用者體驗。
- 協助您在德國符合本地客戶資料的存留需求。
- 提供我們功能完整的全球雲端服務，並提供最新版本的服務和新功能，包括 Office 365 中的 Microsoft Teams 和多重地理位置。 依地區比較 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md) 和 [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) 產品。
- 提供完整的功能、企業級的安全性及全面的功能，協助客戶符合合規性和法規需求。
- 可透過現有的線上服務合約取得。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>不同的 Office 365 雲端服務選項之間的服務可用性為何？
<h2 id="serv-avail"></h2>

Microsoft Cloud Deutschland 雲端服務方案提供下列 15 項服務。 我們不會在 Microsoft Cloud Deutschland 新增服務。

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

目前，新的德國資料中心地區有 39 個服務屬於 Office 365 服務的一部分。 將持續與全球 Office 365 服務一起提供新功能和服務。

1. Exchange Online
2. Exchange Online 的客戶 Lockbox
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
14. SharePoint Online 的客戶 Lockbox
15. 商務用 OneDrive
16. Microsoft Stream
17. 在移 (期間，商務用 Skype 應用程式將會移) 
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
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1、Intune 和 Rights Management Service) 
29. Yammer Enterprise
30. Microsoft Forms
31. 適用于 Office 365 的 Power Automate
32. Power Virtual Agents for Office 365
33. Office 365 的 PowerApps
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. 清單

### <a name="when-will-migration-happen"></a>何時會進行移轉？

**Azure**

如果您只是 Azure 客戶，您今天就可以開始[](https://docs.microsoft.com/azure/germany/germany-migration-main)將 Azure 資源移遷移到另一地區。 

如果您擁有 Office 365、Dynamics 365 或 Power BI 的 Azure，您必須先遵循移轉到程式以確保 AzureAD 能順利移轉到 AzureAD，才能開始進行自我導向 Azure 移轉到。 您必須在服務關閉之前完成 Azure 移移，才能使用 AzureAD 和 Office 365 組織維持 Azure 工作負載。

**Office 365**

立即[選擇加入](https://aka.ms/office365germanymoveoptin) Microsoft 主導的移轉。 當您準備好開始移移時，我們會透過 Microsoft 365 系統管理中心的訊息中心通知您。

**Dynamics 365 和 Power BI**

現在加入宣告 [Dynamics 365](https://aka.ms/D365ceOptIn) 客戶參與和 [Power BI 的 Microsoft](https://aka.ms/PBIOptIn) 導向移移。 當我們準備好開始您的移轉時，我們會透過 Microsoft 365 系統管理中心的訊息中心來通知您。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>我使用的 Office 365 服務價格會變更嗎？

是。 Microsoft&#39;全球雲端區域的定價 (包括新的資料中心地區) 一般而言較低。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>在訂閱移移期間，哪些 SKUS 和授權會適用于我的組織和使用者？

在從 Microsoft Cloud Deutschland 移移至 Office 365 服務期間，德國服務特定 SKU 會取代為相同或類似 SKU 的全域版本。 在大部分情況下，Office 365 服務中的 SKU 都相同，但德國的 SKU 在 Office 365 服務中卻不再提供于其中，因此有一些替代專案。 如果您想要在移移完成後更新指派給貴組織的 SKU，請與您的銷售者聯繫，以新增或修改指派的服務。

| Microsoft Cloud Deutschland - 產品 SKU (DE)  | Microsoft Cloud Global - WW (產品 SKU)  |
| --- | --- |
| 客戶 Lockbox \_ DE (LOCKBOX \_ DE)  | 客戶 Lockbox (LOCKBOX)  |
| Dynamics 365 Enterprise Edition - 其他資料庫儲存 \_ 空間 DE (CRMSTORAGE \_ DE)  | Dynamics 365 Enterprise Edition - CRMSTORAGE (額外的資料庫)  |
| Dynamics 365 Enterprise Edition - 其他非生產實例 \_ DE (CRMTESTINSTANCE \_ DE)  | Dynamics 365 Enterprise Edition - CRMTESTINSTANCE (額外的非生產實例)  |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE DE \_ \_ \_)  | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ \_ 客戶服務)  |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE SALES DE \_ \_)  | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES)  |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS DE \_ \_ \_)  | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM MEMBERS \_)  |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 DE \_)  | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ \_ ENTERPRISE PLAN1)  |
| ECAL Services (E一、EOP、DLP) \_ DE (ECAL \_ SERVICES \_ DE)  | ECAL Services (E一、EOP、DLP)  (ECAL \_ SERVICES)  |
| Enterprise Mobility + Security E3 \_ DE (EMS \_ DE)  | Enterprise Mobility + Security E3 (EMS)  |
| Exchange Online (方案 1) \_ DE (EXCHANGESTANDARD \_ DE)  | Exchange Online (方案 1)  (EXCHANGESTANDARD)  |
| Exchange Online (方案 2) \_ DE (EXCHANGEENTERPRISE \_ DE)  | Exchange Online (方案 2)  (EXCHANGEENTERPRISE)  |
| Exchange Online DE 的 Exchange Online (\_ EXCHANGEARCHIVE \_ \_ ADDON DE)  | Exchange Online 的 Exchange Online (EXCHANGEARCHIVE \_ ADDON)  |
| Exchange Online Archiving for Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE)  | Exchange Server 的 Exchange Online (EXCHANGEARCHIVE)  |
| Exchange Online Essentials \_ DE (EXCHANGE S \_ \_ ESSENTIALS DE \_)  | Exchange Online 基本 (EXCHANGE \_ 基本 \_ 資訊)  |
| Exchange Online Kiosk \_ DE (EXCHANGEDESKLESS \_ DE)  | Exchange Online Kiosk (EXCHANGEDESKLESS)  |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE DE \_)  | Exchange Online Protection (EOP \_ ENTERPRISE)  |
| Microsoft 365 商務標準版 (O365 \_ 商務 \_ 進)  | Microsoft 365 商務標準版 (O365 \_ 商務 \_ 進)  |
| Microsoft Dynamics CRM Online Instance \_ DE (CRMINSTANCE \_ DE)  | Microsoft Dynamics CRM Online 實例 (CRMINSTANCE)  |
| 適用于教職員 DE 的 Office 365 A1 \_ (STANDARDWOFFPACK \_ \_ FACULTY DE)  | 教職員用 Office 365 A1 (STANDARDWOFFPACK \_ 教職員用)  |
| 適用于學生 DE 的 Office 365 A1 (\_ STANDARDWOFFPACK \_ \_ STUDENT DE)  | 學生用 Office 365 A1 (STANDARDWOFFPACK \_ STUDENT)  |
| Office 365 Advanced Compliance \_ DE (EQUIVIO \_ ANALYTICS DE \_)  | Microsoft 365 E5 合規性 (資訊 \_ 保護 \_ 合規性)  |
|適用于 Office 365 的 Microsoft Defender (方案 1) \_ DE (ATP \_ ENTERPRISE DE \_)  |適用于 Office 365 的 Microsoft Defender (方案 1)  (ATP \_ ENTERPRISE)  |
| Office 365 商務基本版 \_ DE (O365 \_ 商務 \_ 基本版 DE \_)  | Microsoft 365 商務基本 (O365 \_ 商務 \_ 基本版)  |
| Office 365 商務進 (\_ 版 DE (O365 \_ BUSINESS PREMIUM DE \_ \_)  | Microsoft 365 商務標準版 (O365 \_ 商務 \_ 進)  |
| Office 365 商務 \_ 版 DE (O365 \_ \_ 商務版 DE)  | 商務用 Microsoft 365 應用程式 (O365 商務版 \_)  |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE)  | Office 365 E1 (STANDARDPACK)  |
| 沒有專業增強版 DE 的 Office 365 E3 \_ (ENTERPRISEPACKWITHOUTPROPLUS \_ DE)  | Office 365 E3 不含專業增強 (ENTERPRISEPACKWITHOUTPROPLUS)  |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE)  | Office 365 E3 (ENTERPRISEPACK)  |
| Office 365 企業版 E1 \_ DE (STANDARDPACK \_ DE)  | Office 365 企業版 E1 (STANDARDPACK)  |
| Office 365 企業版 E3 \_ DE (ENTERPRISEPACK \_ DE)  | Office 365 企業版 E3 (ENTERPRISEPACK)  |
| Office 365 額外檔案儲存 \_ 空間 DE (SHAREPOINTSTORAGE \_ DE)  | Office 365 額外檔案儲存空間 (SHAREPOINTSTORAGE)  |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE)  | Office 365 F1 (DESKLESSPACK)  |
| 適用于教職員 DE 的 Office 365 專業增強 \_ (OFFICESUBSCRIPTION \_ \_ FACULTY DE)  | OFFICE 365 教職員用 Office 365 專業增強 (OFFICESUBSCRIPTION \_ 教職員用)  |
| OFFICE 365 學生用專業增強 \_ 版 DE (OFFICESUBSCRIPTION \_ STUDENT DE \_)  | OFFICE 365 學生用專業增強 (OFFICESUBSCRIPTION \_ 學生版)  |
| Office 365 專業增強 \_ 版 DE (OFFICESUBSCRIPTION \_ DE)  | Office 365 專業增強版 (OFFICESUBSCRIPTION)  |
| \_WACONEDRIVESTANDARD DE (WACONEDRIVESTANDARD DE () 1 方案 \_ 1)  | 商務用 OneDrive (1)  (WACONEDRIVESTANDARD)  |
| \_WACONEDRIVEENTERPRISE DE (DE) 2 (商務用 OneDrive \_ 方案 2)  | 商務用 OneDrive (2 方案 2)  (WACONEDRIVEENTERPRISE)  |
| Power BI Pro for faculty \_ DE (POWER BI PRO \_ \_ \_ \_ FACULTY DE)  | Power BI Pro for faculty (POWER \_ BI \_ PRO \_ FACULTY)  |
| Power BI Pro \_ DE (POWER BI PRO DE \_ \_ \_)  | Power BI Pro (POWER \_ BI \_ PRO)  |
| Project Online 基本版 \_ DE (PROJECTESSENTIALS \_ DE)  | Project Online 基本 (專案)  |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE)  | Project Online Premium (PROJECTPREMIUM)  |
| Project Online 專業 \_ 版 DE (PROFESSIONAL \_ DE)  | Project Online 專業 (PROJECTPROFESSIONAL)  |
| Project Plan 3 \_ DE (PROFESSIONAL \_ DE)  | 專案計劃 3 (PROJECTPROFESSIONAL)  |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE)  | Office 365 E3 (ENTERPRISEPACK)  |
| SharePoint Online (SHAREPOINT ONLINE) \_ DE (SHAREPOINTSTANDARD \_ DE)  | SharePoint Online (SHAREPOINTSTANDARD)  (規劃 1)  |
| SharePoint Online (規劃 2) \_ DE (SHAREPOINTENTERPRISE \_ DE)  | SharePoint Online (SHAREPOINTENTERPRISE)  (規劃 2)  |
| 商務用 Skype Online (方案 1) \_ DE (MCOIMP \_ DE)  | Office 365 E1 (STANDARDPACK)  |
| 商務用 Skype Online (方案 1) \_ DE (MCOIMP \_ DE)  | 商務用 Skype Online (方案 1)  (MCOIMP)  |
| 商務用 Skype Online (方案 2) \_ DE (MCOSTANDARD \_ DE)  | 商務用 Skype Online (MCOSTANDARD)  (方案 2)  |
| 商務用 Skype Plus CAL \_ DE (MCOPLUSCAL \_ DE)  | 商務用 Skype Plus CAL (MCOPLUSCAL)  |
| 教職員用 DE 和 \_ VISIOONLINE 方案1 FAC DE (教職員用 Visio Online \_ \_ 方案 \_ 1)  | 適用于 VISIOONLINE 方案1 FAC (教職員用 Visio Online \_ 方案) \_ 1 |
| Visio Online 方案 1 \_ DE (VISIOONLINE \_ 方案1 DE \_)  | Visio Online 方案 1 (VISIOONLINE \_ 方案1)  |
| 適用于教職員 DE 和 \_ VISIOCLIENT FACULTY DE (的 Visio Online \_ \_ 方案 2)  | 適用于 VISIOCLIENT 教職員和 (的 Visio Online \_ 方案 2)  |
| Visio Online 方案 2 \_ DE (VISIOCLIENT \_ DE)  | Visio Online 方案 2 (VISIOCLIENT)  |
| Visio 方案 1 \_ DE (VISIOONLINE \_ 方案1 DE \_)  | Visio 方案 1 (VISIOONLINE \_ 方案1)  |
| Visio 方案 2 \_ DE (VISIOCLIENT \_ DE)  | Visio 方案 2 (VISIOCLIENT)  |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>如何取得 Microsoft 的協助來移轉到新的區域或解答支援問題？

如有疑問，您可以與我們或您的合作夥伴聯絡：

- 針對 Azure，您可以在 Azure 入口網站中提交[新的支援要求](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)。
- 針對 Office 365，您可以使用 Microsoft 365 系統管理中心的需要協助嗎 &quot; ？連結提交 &quot; [問題](https://portal.office.de/)。
- 如果您是 Dynamics 365 客戶互動和 Power BI 客戶，也有 Office 365，您可以使用 &quot; Microsoft &quot; [365](https://portal.office.de/)系統管理中心的需要協助嗎？連結提交問題。 Dynamics 365 Customer Engagement 支援選項在[這裡](https://docs.microsoft.com/dynamics365/get-started/support/)。 Power BI 支援選項在[這裡](https://powerbi.microsoft.com/support/)。


## <a name="next-step"></a>下一步

[選擇加入移轉](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>其他相關資訊

開始：

- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [移移期間的客戶經驗](ms-cloud-germany-transition-experience.md)

在轉場中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預先作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[裝置](ms-cloud-germany-transition-add-devices.md)、[體驗](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他資訊](ms-cloud-germany-transition-add-adfs.md)。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
