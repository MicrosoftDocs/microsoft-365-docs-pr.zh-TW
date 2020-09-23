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
description: 瞭解如何使用協力廠商資料連線器和 Microsoft Graph APIs，擴充 Microsoft 365 合規性解決方案。
ms.openlocfilehash: 284125db8243b10f5c8de7e0a37c1b7284709c28
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204329"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 合規性擴充性

Microsoft 365 規範解決方案可協助組織智慧地評估其相容性風險、管理和保護機密資料，並有效地回應法規需求。 Microsoft 365 規範在擴充性案例中是很豐富的，可讓組織調整、擴充、整合、加速及支援其合規性解決方案。

合規性擴充性有兩個主要的構造塊：

- **資料連線器**。 用於匯入和封存非 Microsoft 資料，讓您可以將 Microsoft 365 保護和管理功能套用至協力廠商資料。

- **APIs**。 可讓您以程式設計方式存取 Microsoft 365 規範功能。

## <a name="data-connectors"></a>資料連線器

Microsoft 提供可在 Microsoft 365 規範中心內設定的協力廠商資料連線器。 如需 Microsoft 所提供的資料連線器清單，請參閱 [協力廠商資料連線器](archiving-third-party-data.md#third-party-data-connectors) 表格。 協力廠商資料連線器的表格也會摘要說明在 Microsoft 365 中匯入及封存資料後，您可以套用至協力廠商資料的相容性解決方案，以及每個連接器的逐步指示連結。

若要深入瞭解 Microsoft 365 資料連線器，請參閱封存 [協力廠商資料](archiving-third-party-data.md)。 如果 Microsoft 365 規範中心中提供的資料連線器不支援協力廠商資料類型，您可以與可以為您提供自訂連接器的合作夥伴合作。 如需您可以使用的合作夥伴清單及此方法的逐步程式，請參閱使用 [協力廠商的合作夥伴來封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)。

### <a name="prerequisites-for-data-connectors"></a>資料連線器的必要條件

Microsoft 365 合規性中心有許多可用的資料連線器，可匯入及封存協力廠商資料。您需要在協力廠商資料來源中準備及執行設定工作。 每個協力廠商資料連線器都會詳細記錄這些必要條件。

針對 microsoft 第一個合作夥伴提供的 Microsoft 365 規範中心內的資料連線器，您的組織必須與合作夥伴進行業務關係，才能部署連接器。

您可以在 [Microsoft 365 合規性授權比較](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 檔中尋找協力廠商資料連線器的授權需求。

## <a name="apis"></a>API

Microsoft 365 合規性 APIs 可在 Microsoft 資訊保護 SDK、Microsoft Graph API 及 Office 365 管理活動 API 中取得。 某些規範 APIs 是一組新的安全性和符合性 APIs 的一部分，可讓 Microsoft 365 客戶、獨立軟體廠商、系統集成商和受管理的安全性服務提供者，建立高價值的安全性和合規性解決方案。

若要深入瞭解如何存取圖形 APIs，請參閱 [Microsoft Graph 一覽](https://docs.microsoft.com/graph/overview)。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft 資訊保護 (MIP) SDK

MIP SDK 會向協力廠商應用程式和服務，公開卷標和保護服務的 Microsoft 365 安全性與合規性中心。 開發人員可以使用 SDK 建立原生支援，以將標籤和保護套用至檔案。 開發人員可以決定偵測到特定標籤時應採取的動作，以及 MIP 加密資訊的原因。

高層 MIP SDK 使用案例包括：

- 在匯出時，將分類標籤套用至檔案的企業營運應用程式。

- 提供 MIP 標籤原生支援的 CAD/CAM 設計應用程式。

- 可使用 Azure 資訊保護來加密資料的雲端存取安全性經紀人或資料遺失防護解決方案。

若要深入瞭解 MIP SDK、必要條件、其他案例和範例，請參閱 [MIP SDK 一覽](https://docs.microsoft.com/information-protection/develop/overview)。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph API for 小組 DLP

[資料遺失防護 (DLP) ](dlp-microsoft-teams.md) 功能廣泛用於 Microsoft 小組，尤其是當組織已移動至遠端工作時。 今年早些時候，我們宣佈小組中郵件的 Microsoft Graph 變更通知 API [公開預覽](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) 。 此 API 可讓開發人員建立應用程式，該應用程式可以以近即時的方式收聽 Microsoft 小組郵件，然後為客戶及合作夥伴實施 DLP 案例。 此外，Microsoft Graph Patch API 可讓您將 DLP 動作套用至小組郵件。

這兩個 APIs 會形成小組 DLP 的 Microsoft Graph API。 您可以從 [範例應用程式](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)開始試用。 如需 Microsoft 團隊郵件 webhooks 的詳細資訊，請參閱 [檔](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)。

如需小組 DLP 的授權需求，請參閱 [適用于安全性 & 符合性的 Microsoft 365 授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>用於 eDiscovery 的 Microsoft Graph API (預覽) 

透過 [高級 eDiscovery](overview-ediscovery-20.md)，組織可以發現其所在的資料，並使用智慧的電腦教學和分析功能管理更多端對端 eDiscovery 工作流程，以將資料降至相關集–所有資料都保持在 Microsoft 365 安全性和合規性界限內。

可使用「高級 eDiscovery」的圖形 APIs，以可伸縮且可重複的方式建立及管理案例、審閱集和審閱集合查詢。 這可讓客戶與合作夥伴建立應用程式和工作流程，以自動化常見和重複性的程式，例如建立案例及管理保管人和法律封存。

EDiscovery 的第一組圖形 APIs 可用於公開預覽。 我們計畫在行事歷年度結束時新增更多功能。 若要深入瞭解這些 APIs 及其他有關高級 eDiscovery 的更新，請參閱此 [博客](https://aka.ms/Ignite2020AeDAA)。

如需適用于 Advanced eDiscovery 和 API 的授權需求，請參閱《 [安全性 & 相容性的 Microsoft 365 授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)》中的「eDiscovery」一節。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>團隊的 Microsoft Graph API 匯出 (預覽) 

公司資訊封存 (EIA) Microsoft 團隊是我們客戶的重要案例，因為它可讓他們針對法規需求進行求解。 除了在 Microsoft 小組中封存內容的內建功能之外，客戶和合作夥伴現在還可以使用小組匯出 APIs 來解決自訂應用程式和整合案例。 小組匯出 APIs (支援高達每秒/每秒/每秒/每個應用程式/每個租使用者的200要求) 的團隊郵件和郵件附件。 已刪除的郵件也可由 API 在刪除之後30天記憶體取。 如需這些小組匯出 APIs 及如何在應用程式中使用這些小組的詳細資訊，請參閱 [export content With Microsoft 球隊 export APIs](https://docs.microsoft.com/microsoftteams/export-teams-content)。

如需使用小組匯出 APIs 的授權需求，請參閱 [Microsoft 365 授權指南中的安全性 & 相容性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。
