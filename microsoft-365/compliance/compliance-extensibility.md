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
# <a name="microsoft-365-compliance-extensibility"></a><span data-ttu-id="b2e53-103">Microsoft 365 合規性擴充性</span><span class="sxs-lookup"><span data-stu-id="b2e53-103">Microsoft 365 compliance extensibility</span></span>

<span data-ttu-id="b2e53-104">Microsoft 365 規範解決方案可協助組織智慧地評估其相容性風險、管理和保護機密資料，並有效地回應法規需求。</span><span class="sxs-lookup"><span data-stu-id="b2e53-104">Microsoft 365 compliance solutions help organizations intelligently assess their compliance risks, govern and protect sensitive data, and effectively respond to regulatory requirements.</span></span> <span data-ttu-id="b2e53-105">Microsoft 365 規範在擴充性案例中是很豐富的，可讓組織調整、擴充、整合、加速及支援其合規性解決方案。</span><span class="sxs-lookup"><span data-stu-id="b2e53-105">Microsoft 365 compliance is rich in extensibility scenarios and enables organizations to adapt, extend, integrate, accelerate, and support their compliance solutions.</span></span>

<span data-ttu-id="b2e53-106">合規性擴充性有兩個主要的構造塊：</span><span class="sxs-lookup"><span data-stu-id="b2e53-106">There are two key building blocks for compliance extensibility:</span></span>

- <span data-ttu-id="b2e53-107">**資料連線器**。</span><span class="sxs-lookup"><span data-stu-id="b2e53-107">**Data connectors**.</span></span> <span data-ttu-id="b2e53-108">用於匯入和封存非 Microsoft 資料，讓您可以將 Microsoft 365 保護和管理功能套用至協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="b2e53-108">Use to import and archive non-Microsoft data so you can apply Microsoft 365 protection and governance capabilities to third-party data.</span></span>

- <span data-ttu-id="b2e53-109">**APIs**。</span><span class="sxs-lookup"><span data-stu-id="b2e53-109">**APIs**.</span></span> <span data-ttu-id="b2e53-110">可讓您以程式設計方式存取 Microsoft 365 規範功能。</span><span class="sxs-lookup"><span data-stu-id="b2e53-110">Enables programmatic access to Microsoft 365 compliance capabilities.</span></span>

## <a name="data-connectors"></a><span data-ttu-id="b2e53-111">資料連線器</span><span class="sxs-lookup"><span data-stu-id="b2e53-111">Data connectors</span></span>

<span data-ttu-id="b2e53-112">Microsoft 提供可在 Microsoft 365 規範中心內設定的協力廠商資料連線器。</span><span class="sxs-lookup"><span data-stu-id="b2e53-112">Microsoft provides third-party data connectors that can be configured in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b2e53-113">如需 Microsoft 所提供的資料連線器清單，請參閱 [協力廠商資料連線器](archiving-third-party-data.md#third-party-data-connectors) 表格。</span><span class="sxs-lookup"><span data-stu-id="b2e53-113">For a list of data connectors provided by Microsoft, see the [Third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) table.</span></span> <span data-ttu-id="b2e53-114">協力廠商資料連線器的表格也會摘要說明在 Microsoft 365 中匯入及封存資料後，您可以套用至協力廠商資料的相容性解決方案，以及每個連接器的逐步指示連結。</span><span class="sxs-lookup"><span data-stu-id="b2e53-114">The table of third-party data connectors also summarizes the compliance solutions that you can apply to third-party data after you import and archive data in Microsoft 365, and links to the step-by-step instructions for each connector.</span></span>

<span data-ttu-id="b2e53-115">若要深入瞭解 Microsoft 365 資料連線器，請參閱封存 [協力廠商資料](archiving-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-115">To learn more about Microsoft 365 data connectors, see [Archiving third-party data](archiving-third-party-data.md).</span></span> <span data-ttu-id="b2e53-116">如果 Microsoft 365 規範中心中提供的資料連線器不支援協力廠商資料類型，您可以與可以為您提供自訂連接器的合作夥伴合作。</span><span class="sxs-lookup"><span data-stu-id="b2e53-116">If a third-party data type isn't supported by the data connectors available in the Microsoft 365 compliance center, you can work with a partner who can provide you with a custom connector.</span></span> <span data-ttu-id="b2e53-117">如需您可以使用的合作夥伴清單及此方法的逐步程式，請參閱使用 [協力廠商的合作夥伴來封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-117">For a list of partners you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data](work-with-partner-to-archive-third-party-data.md).</span></span>

### <a name="prerequisites-for-data-connectors"></a><span data-ttu-id="b2e53-118">資料連線器的必要條件</span><span class="sxs-lookup"><span data-stu-id="b2e53-118">Prerequisites for data connectors</span></span>

<span data-ttu-id="b2e53-119">Microsoft 365 合規性中心有許多可用的資料連線器，可匯入及封存協力廠商資料。您需要在協力廠商資料來源中準備及執行設定工作。</span><span class="sxs-lookup"><span data-stu-id="b2e53-119">Many of the data connectors available in the Microsoft 365 compliance center to import and archive third-party data require that you prepare and perform configuration tasks in the third-party data source.</span></span> <span data-ttu-id="b2e53-120">每個協力廠商資料連線器都會詳細記錄這些必要條件。</span><span class="sxs-lookup"><span data-stu-id="b2e53-120">These prerequisites are documented in detail for each third-party data connector.</span></span>

<span data-ttu-id="b2e53-121">針對 microsoft 第一個合作夥伴提供的 Microsoft 365 規範中心內的資料連線器，您的組織必須與合作夥伴進行業務關係，才能部署連接器。</span><span class="sxs-lookup"><span data-stu-id="b2e53-121">For data connectors in the Microsoft 365 compliance center provided by one of Microsoft's partners, your organization will need a business relationship with the partner before you can deploy a connector.</span></span>

<span data-ttu-id="b2e53-122">您可以在 [Microsoft 365 合規性授權比較](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 檔中尋找協力廠商資料連線器的授權需求。</span><span class="sxs-lookup"><span data-stu-id="b2e53-122">You can find licensing requirements for third-party data connectors in the [Microsoft 365 Compliance Licensing Comparison](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) document.</span></span>

## <a name="apis"></a><span data-ttu-id="b2e53-123">API</span><span class="sxs-lookup"><span data-stu-id="b2e53-123">APIs</span></span>

<span data-ttu-id="b2e53-124">Microsoft 365 合規性 APIs 可在 Microsoft 資訊保護 SDK、Microsoft Graph API 及 Office 365 管理活動 API 中取得。</span><span class="sxs-lookup"><span data-stu-id="b2e53-124">Microsoft 365 compliance APIs are available in the Microsoft Information Protection SDK, Microsoft Graph API, and the Office 365 Management Activity API.</span></span> <span data-ttu-id="b2e53-125">某些規範 APIs 是一組新的安全性和符合性 APIs 的一部分，可讓 Microsoft 365 客戶、獨立軟體廠商、系統集成商和受管理的安全性服務提供者，建立高價值的安全性和合規性解決方案。</span><span class="sxs-lookup"><span data-stu-id="b2e53-125">Some compliance APIs are part of a new set of security and compliance APIs that enable developers for Microsoft 365 customers, independent software vendors, system integrators, and managed security service providers to build high-value security and compliance solutions.</span></span>

<span data-ttu-id="b2e53-126">若要深入瞭解如何存取圖形 APIs，請參閱 [Microsoft Graph 一覽](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-126">To learn more about how to access Graph APIs, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

### <a name="microsoft-information-protection-mip-sdk"></a><span data-ttu-id="b2e53-127">Microsoft 資訊保護 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="b2e53-127">Microsoft Information Protection (MIP) SDK</span></span>

<span data-ttu-id="b2e53-128">MIP SDK 會向協力廠商應用程式和服務，公開卷標和保護服務的 Microsoft 365 安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="b2e53-128">The MIP SDK exposes the labeling and protection services from Microsoft 365 security and compliance centers to third-party applications and services.</span></span> <span data-ttu-id="b2e53-129">開發人員可以使用 SDK 建立原生支援，以將標籤和保護套用至檔案。</span><span class="sxs-lookup"><span data-stu-id="b2e53-129">Developers can use the SDK to build native support for applying labels and protection to files.</span></span> <span data-ttu-id="b2e53-130">開發人員可以決定偵測到特定標籤時應採取的動作，以及 MIP 加密資訊的原因。</span><span class="sxs-lookup"><span data-stu-id="b2e53-130">Developers can determine which actions should be taken when specific labels are detected, and reason over MIP-encrypted information.</span></span>

<span data-ttu-id="b2e53-131">高層 MIP SDK 使用案例包括：</span><span class="sxs-lookup"><span data-stu-id="b2e53-131">High-level MIP SDK use cases include:</span></span>

- <span data-ttu-id="b2e53-132">在匯出時，將分類標籤套用至檔案的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="b2e53-132">A line-of-business application that applies classification labels to files on export.</span></span>

- <span data-ttu-id="b2e53-133">提供 MIP 標籤原生支援的 CAD/CAM 設計應用程式。</span><span class="sxs-lookup"><span data-stu-id="b2e53-133">A CAD/CAM design application that provides native support for MIP labeling.</span></span>

- <span data-ttu-id="b2e53-134">可使用 Azure 資訊保護來加密資料的雲端存取安全性經紀人或資料遺失防護解決方案。</span><span class="sxs-lookup"><span data-stu-id="b2e53-134">A cloud access security broker or data loss prevention solution that can encrypt data with Azure Information Protection.</span></span>

<span data-ttu-id="b2e53-135">若要深入瞭解 MIP SDK、必要條件、其他案例和範例，請參閱 [MIP SDK 一覽](https://docs.microsoft.com/information-protection/develop/overview)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-135">To learn more about the MIP SDK, prerequisites, additional scenarios, and samples, see [MIP SDK Overview](https://docs.microsoft.com/information-protection/develop/overview).</span></span>

### <a name="microsoft-graph-api-for-teams-dlp"></a><span data-ttu-id="b2e53-136">Microsoft Graph API for 小組 DLP</span><span class="sxs-lookup"><span data-stu-id="b2e53-136">Microsoft Graph API for Teams DLP</span></span>

<span data-ttu-id="b2e53-137">[資料遺失防護 (DLP) ](dlp-microsoft-teams.md) 功能廣泛用於 Microsoft 小組，尤其是當組織已移動至遠端工作時。</span><span class="sxs-lookup"><span data-stu-id="b2e53-137">[Data loss prevention (DLP)](dlp-microsoft-teams.md) capabilities are widely used in Microsoft Teams particularly as organizations have shifted to remote work.</span></span> <span data-ttu-id="b2e53-138">今年早些時候，我們宣佈小組中郵件的 Microsoft Graph 變更通知 API [公開預覽](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) 。</span><span class="sxs-lookup"><span data-stu-id="b2e53-138">Earlier this year we [announced the public preview](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) of the Microsoft Graph Change Notification API for messages in Teams.</span></span> <span data-ttu-id="b2e53-139">此 API 可讓開發人員建立應用程式，該應用程式可以以近即時的方式收聽 Microsoft 小組郵件，然後為客戶及合作夥伴實施 DLP 案例。</span><span class="sxs-lookup"><span data-stu-id="b2e53-139">This API enables developers to build apps that can listen to Microsoft Teams messages in near-real time and then implement DLP scenarios for both customers and partners.</span></span> <span data-ttu-id="b2e53-140">此外，Microsoft Graph Patch API 可讓您將 DLP 動作套用至小組郵件。</span><span class="sxs-lookup"><span data-stu-id="b2e53-140">Additionally, Microsoft Graph Patch API lets you apply DLP actions to Teams messages.</span></span>

<span data-ttu-id="b2e53-141">這兩個 APIs 會形成小組 DLP 的 Microsoft Graph API。</span><span class="sxs-lookup"><span data-stu-id="b2e53-141">These two APIs form the Microsoft Graph API for Teams DLP.</span></span> <span data-ttu-id="b2e53-142">您可以從 [範例應用程式](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)開始試用。</span><span class="sxs-lookup"><span data-stu-id="b2e53-142">You can get started by trying out the [sample app](https://github.com/microsoftgraph/csharp-webhook-with-resource-data).</span></span> <span data-ttu-id="b2e53-143">如需 Microsoft 團隊郵件 webhooks 的詳細資訊，請參閱 [檔](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-143">For more information about Microsoft Teams messaging webhooks, see the [documentation](https://docs.microsoft.com/graph/api/subscription-post-subscriptions).</span></span>

<span data-ttu-id="b2e53-144">如需小組 DLP 的授權需求，請參閱 [適用于安全性 & 符合性的 Microsoft 365 授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-144">For the licensing requirements for Teams DLP, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).</span></span>

### <a name="microsoft-graph-api-for-ediscovery-preview"></a><span data-ttu-id="b2e53-145">用於 eDiscovery 的 Microsoft Graph API (預覽) </span><span class="sxs-lookup"><span data-stu-id="b2e53-145">Microsoft Graph API for eDiscovery (preview)</span></span>

<span data-ttu-id="b2e53-146">透過 [高級 eDiscovery](overview-ediscovery-20.md)，組織可以發現其所在的資料，並使用智慧的電腦教學和分析功能管理更多端對端 eDiscovery 工作流程，以將資料降至相關集–所有資料都保持在 Microsoft 365 安全性和合規性界限內。</span><span class="sxs-lookup"><span data-stu-id="b2e53-146">With [Advanced eDiscovery](overview-ediscovery-20.md), organizations can discover data where it lives, and manage more end-to-end eDiscovery workflows with intelligent machine-learning and analytics capabilities to reduce data to the relevant set – all while the data stays within the Microsoft 365 security and compliance boundary.</span></span>

<span data-ttu-id="b2e53-147">可使用「高級 eDiscovery」的圖形 APIs，以可伸縮且可重複的方式建立及管理案例、審閱集和審閱集合查詢。</span><span class="sxs-lookup"><span data-stu-id="b2e53-147">Graph APIs for Advanced eDiscovery can be used to create and manage cases, review sets, and review set queries in a scalable and repeatable manner.</span></span> <span data-ttu-id="b2e53-148">這可讓客戶與合作夥伴建立應用程式和工作流程，以自動化常見和重複性的程式，例如建立案例及管理保管人和法律封存。</span><span class="sxs-lookup"><span data-stu-id="b2e53-148">This enables customers and partners to create apps and workflows to automate common and repetitive processes such as creating cases and managing custodians and legal holds.</span></span>

<span data-ttu-id="b2e53-149">EDiscovery 的第一組圖形 APIs 可用於公開預覽。</span><span class="sxs-lookup"><span data-stu-id="b2e53-149">The first set of Graph APIs for eDiscovery are available in public preview.</span></span> <span data-ttu-id="b2e53-150">我們計畫在行事歷年度結束時新增更多功能。</span><span class="sxs-lookup"><span data-stu-id="b2e53-150">We plan to add more capabilities by the end of the calendar year.</span></span> <span data-ttu-id="b2e53-151">若要深入瞭解這些 APIs 及其他有關高級 eDiscovery 的更新，請參閱此 [博客](https://aka.ms/Ignite2020AeDAA)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-151">To learn more about these APIs and other updates for Advanced eDiscovery, see this [blog](https://aka.ms/Ignite2020AeDAA).</span></span>

<span data-ttu-id="b2e53-152">如需適用于 Advanced eDiscovery 和 API 的授權需求，請參閱《 [安全性 & 相容性的 Microsoft 365 授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)》中的「eDiscovery」一節。</span><span class="sxs-lookup"><span data-stu-id="b2e53-152">For the licensing requirements for Advanced eDiscovery and the API, see the "eDiscovery" section in the [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).</span></span>

### <a name="microsoft-graph-api-for-teams-export-preview"></a><span data-ttu-id="b2e53-153">團隊的 Microsoft Graph API 匯出 (預覽) </span><span class="sxs-lookup"><span data-stu-id="b2e53-153">Microsoft Graph API for Teams Export (preview)</span></span>

<span data-ttu-id="b2e53-154">公司資訊封存 (EIA) Microsoft 團隊是我們客戶的重要案例，因為它可讓他們針對法規需求進行求解。</span><span class="sxs-lookup"><span data-stu-id="b2e53-154">Enterprise Information Archiving (EIA) for Microsoft Teams is a key scenario for our customers as it allows them to solve for regulatory requirements.</span></span> <span data-ttu-id="b2e53-155">除了在 Microsoft 小組中封存內容的內建功能之外，客戶和合作夥伴現在還可以使用小組匯出 APIs 來解決自訂應用程式和整合案例。</span><span class="sxs-lookup"><span data-stu-id="b2e53-155">In addition to our built-in capabilities for archiving content in Microsoft Teams, customers and partners can now use Teams Export APIs to solve for custom application and integration scenarios.</span></span> <span data-ttu-id="b2e53-156">小組匯出 APIs (支援高達每秒/每秒/每秒/每個應用程式/每個租使用者的200要求) 的團隊郵件和郵件附件。</span><span class="sxs-lookup"><span data-stu-id="b2e53-156">The Teams Export APIs support bulk-export (up to 200 requests per second/per app/per tenant) of Teams messages and message attachments.</span></span> <span data-ttu-id="b2e53-157">已刪除的郵件也可由 API 在刪除之後30天記憶體取。</span><span class="sxs-lookup"><span data-stu-id="b2e53-157">Deleted messages are also accessible by the API for up to 30 days after they are deleted.</span></span> <span data-ttu-id="b2e53-158">如需這些小組匯出 APIs 及如何在應用程式中使用這些小組的詳細資訊，請參閱 [export content With Microsoft 球隊 export APIs](https://docs.microsoft.com/microsoftteams/export-teams-content)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-158">For more information about these Teams Export APIs and how to use them in your applications, see [Export content with the Microsoft Teams Export APIs](https://docs.microsoft.com/microsoftteams/export-teams-content).</span></span>

<span data-ttu-id="b2e53-159">如需使用小組匯出 APIs 的授權需求，請參閱 [Microsoft 365 授權指南中的安全性 & 相容性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="b2e53-159">For the licensing requirements for the use of the Teams Export APIs, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>
