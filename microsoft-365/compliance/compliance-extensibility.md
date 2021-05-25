---
title: Microsoft 365 合規性擴充性
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用協力廠商資料連線器和 Microsoft Graph APIs 擴充 Microsoft 365 合規性解決方案。
ms.openlocfilehash: 1fed5ac72c7dbfa4b1be370ec03678e1beecdcd2
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651053"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 合規性擴充性

Microsoft 365 規範解決方案可協助組織智慧地評估其相容性風險、管理和保護機密資料，並有效地回應法規需求。 Microsoft 365 合規性在擴充性案例中非常豐富，可讓組織調整、擴充、整合、加速及支援其相容性解決方案。

合規性擴充性有兩個主要的構造塊：

- **資料連線器**。 用於匯入和封存非 Microsoft 資料，讓您可以將 Microsoft 365 保護和控管功能套用至協力廠商資料。

- **APIs**。 可讓您以程式設計方式存取 Microsoft 365 規範功能。

## <a name="data-connectors"></a>資料連線器

Microsoft 提供可在 Microsoft 365 規範中心設定的協力廠商資料連線器。 如需 Microsoft 所提供的資料連線器清單，請參閱 [協力廠商資料連線器](archiving-third-party-data.md#third-party-data-connectors) 表格。 協力廠商資料連線器的表格也會摘要說明您在 Microsoft 365 中匯入及封存資料後，您可以套用至協力廠商資料的相容性解決方案，以及每個連接器的逐步指示連結。

若要深入瞭解 Microsoft 365 資料連線器，請參閱封存[協力廠商資料](archiving-third-party-data.md)。 如果 Microsoft 365 規範中心中提供的資料連線器不支援協力廠商資料類型，您可以與可以為您提供自訂連接器的合作夥伴合作。 如需您可以使用的合作夥伴清單及此方法的逐步程式，請參閱使用 [協力廠商的合作夥伴來封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)。

### <a name="prerequisites-for-data-connectors"></a>資料連線器的必要條件

在 Microsoft 365 規範中心內，許多可匯入及封存協力廠商資料的資料連線器，都需要在協力廠商資料來源中準備及執行設定工作。 每個協力廠商資料連線器都會詳細記錄這些必要條件。

針對其中一個 Microsoft 合作夥伴提供的 Microsoft 365 規範中心內的資料連線器，您的組織必須與合作夥伴進行業務關係，才能部署連接器。

您可以在[Microsoft 365 合規性授權比較](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)檔中尋找協力廠商資料連線器的授權需求。

## <a name="apis"></a>API

您可以在 microsoft 資訊保護 SDK、microsoft Graph API 及 Office 365 管理活動 API 中取得 Microsoft 365 規範 APIs。 某些規範 APIs 是一組新的安全性和符合性 APIs 的一部分，可讓開發人員 Microsoft 365 客戶、獨立軟體廠商、系統集成商和受管理的安全性服務提供者，以建立高價值的安全性和合規性解決方案。

若要深入瞭解如何存取 Graph APIs，請參閱[Microsoft Graph 的總覽](/graph/overview)。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft 資訊保護 (MIP) SDK

MIP SDK 公開卷標和保護服務，將 Microsoft 365 安全性與合規性中心，向協力廠商應用程式和服務公開。 開發人員可以使用 SDK 建立原生支援，以將標籤和保護套用至檔案。 開發人員可以決定偵測到特定標籤時應採取的動作，以及 MIP 加密資訊的原因。

高層 MIP SDK 使用案例包括：

- 在匯出時，將分類標籤套用至檔案的企業營運應用程式。

- 提供 MIP 標籤原生支援的 CAD/CAM 設計應用程式。

- 可使用 Azure 資訊保護來加密資料的雲端存取安全性經紀人或資料遺失防護解決方案。

若要深入瞭解 MIP SDK、必要條件、其他案例和範例，請參閱 [MIP SDK 一覽](/information-protection/develop/overview)。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Teams DLP 的 Microsoft Graph API

[資料遺失防護 (DLP) ](dlp-microsoft-teams.md)功能廣泛用於 Microsoft Teams，尤其是當組織已轉向遠端工作時。 今年早些時候，我們宣佈 Teams 中的郵件之 Microsoft Graph 變更通知 API 的[公開預覽](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/)。 此 API 可讓開發人員建立應用程式，以便在近乎即時聆聽 Microsoft Teams 郵件，然後為客戶及合作夥伴實施 DLP 案例。 此外，Microsoft Graph Patch API 可讓您將 DLP 動作套用至 Teams 郵件。

這兩個 APIs 會形成 Teams DLP 的 Microsoft Graph API。 您可以從 [範例應用程式](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)開始試用。 如需 Microsoft Teams 郵件 webhooks 的詳細資訊，請參閱[檔](/graph/api/subscription-post-subscriptions)。

如需 Teams DLP 的授權需求，請參閱[Microsoft 365 授權指南以取得安全性 & 相容性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>電子檔探索 (預覽的 Microsoft Graph API) 

透過[Advanced eDiscovery](overview-ediscovery-20.md)，組織可以發現其所在的資料，並使用智慧的機器教學和分析功能管理更多的端對端 eDiscovery 工作流程，以將資料降至相關集–所有資料都保持在 Microsoft 365 安全性和合規性界限內。

GraphAdvanced eDiscovery 可用的 APIs，可用來建立及管理案例、審閱集，以及以可伸縮且可重複的方式複查設定查詢。 這可讓客戶與合作夥伴建立應用程式和工作流程，以自動化常見和重複性的程式，例如建立案例及管理保管人和法律封存。

您可以在公開預覽中使用第一組 eDiscovery Graph APIs。 我們計畫在行事歷年度結束時新增更多功能。 若要深入瞭解這些 APIs 及其他 Advanced eDiscovery 的更新，請參閱此[博客](https://aka.ms/Ignite2020AeDAA)。

如需 Advanced eDiscovery 和 API 的授權需求，請參閱 Microsoft 365 授權指南中的「eDiscovery」一節，以[取得安全性 & 相容性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>用於 Teams 匯出 (預覽的 Microsoft Graph API) 

EnterpriseMicrosoft Teams 的 (EIA) 的資訊封存是我們客戶的重要案例，因為它可讓他們針對法規要求進行求解。 除了在 Microsoft Teams 中封存內容的內建功能之外，客戶和合作夥伴現在可以使用 Teams 匯出 APIs 來解決自訂應用程式和整合案例。 Teams 匯出 APIs 支援高達每秒/每秒/每個應用程式/每個) 租使用者200個要求的 (Teams 的郵件和郵件附件。 已刪除的郵件也可由 API 在刪除之後30天記憶體取。 如需這些 Teams 匯出 APIs 及其如何在應用程式中使用的詳細資訊，請參閱[export content with Microsoft Teams export APIs](/microsoftteams/export-teams-content)。

如需使用 Teams 匯出 APIs 的授權需求，請參閱[Microsoft 365 安全性 & 相容性的授權指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph Connector APIs (預覽) 

透過[microsoft Graph 連接器](/microsoftsearch/connectors-overview)，組織可以編制協力廠商資料的索引，使其顯示在 microsoft 搜尋結果中。 這項功能可展開 Microsoft 365 生產力應用程式中可搜尋的內容來源類型，以及更廣泛的 Microsoft 生態用。 協力廠商資料可以位於內部部署或公用或私人雲端。 從 Advanced eDiscovery 開始，我們啟用 Microsoft 365 連接應用程式的內建符合性值的開發人員預覽。 這可讓整合至 Microsoft 365 生態應用程式的應用程式符合，以讓使用者具備無縫的相容性體驗。 若要深入瞭解如何在您的應用程式視圖中結合 Microsoft Graph Connector APIs，請參閱[建立、更新和刪除 microsoft Graph 中的](/graph/search-index-manage-connections)連線。

